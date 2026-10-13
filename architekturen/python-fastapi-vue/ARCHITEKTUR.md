# Python FastAPI + Vue (Bot mit Engine-Prozessen)

## Kurzbeschreibung

Ein Repository mit drei Teilen: FastAPI-App (`api/`), mehrere langlaufende Engine-Prozesse (`engine/`) und Vue-3-Oberfläche (`frontend/`). Alle teilen eine SQLite-Datenbank im WAL-Modus. Die API bedient die Oberfläche und ändert Einstellungen; die Engine-Prozesse erledigen die Arbeit (Marktdaten holen, entscheiden, Orders auslösen, Papier-Simulationen) und laufen als eigene Container mit demselben Code per Bind-Mount.

Zustand wandert über die Datenbank, nicht über Aufrufe zwischen Prozessen: Die API schreibt eine Einstellung, die Schleife liest sie im nächsten Durchlauf. Der Aufbau läuft im Bot produktiv.

## Passt für / passt nicht für

Passt für:
- Bots, Sammler und Überwachungen mit eigener Oberfläche
- Einzelbetrieb auf einem Host mit wenigen Nutzern
- Rechenlastige Projekte (pandas, numpy, ccxt), bei denen Request-Durchsatz zweitrangig ist

Passt nicht für:
- Viele gleichzeitige Schreiber: SQLite genügt nur wegen der kleinen Schreibrate
- Öffentliche Mehrmandanten-Anwendungen (Rollen sind einfach: beobachter, trader, admin)
- Horizontale Skalierung; Zustand im Prozess (z. B. Fehlversuchszähler) wird nicht geteilt
- Seiten mit SEO-Bedarf; die Oberfläche ist eine SPA hinter Login

## Sprache und Stack

- **Python 3.14** (`python:3.14-slim`): eine Laufzeit für API und Engine
- **FastAPI 0.139** mit **Pydantic 2** und uvicorn: Typprüfung an der Grenze, OpenAPI gratis
- **SQLAlchemy 2** auf **SQLite (WAL)**: keine zweite Datenbank, Backup ist eine Datei
- **ccxt**, **pandas**, **numpy**: Börsenzugang und Kennzahlen
- **bcrypt** und JWT für die Anmeldung, **cryptography** für Schlüssel in der Datenbank
- **pytest**: Tests ohne Netzwerk gegen In-Memory-SQLite
- **Vue 3.5**, **Vite 8**, **Pinia 3**, **vue-router 4**, **axios**, **lightweight-charts 5**: schlanke SPA ohne Server-Rendering
- Abhängigkeiten fixiert in `requirements.txt`; das Image nutzt eine Lock-Datei

## Ordnerstruktur

```
projekt/
├── api/
│   └── main.py          # alle Routen, Auth-Dependencies, Watchdog-Task
├── engine/              # Fachlogik und Schleifen, ein Modul je Aufgabe
│   ├── store.py         # Modelle, Session, Migrationen, Defaults
│   ├── security.py      # Passwort-Hash, JWT, Schlüssel-Verschlüsselung
│   ├── audit.py         # Audit-Log
│   ├── exchange.py      # Börsen-Wrapper, gecachter Client
│   ├── strategy.py      # reine Signalberechnung
│   ├── risk.py          # Positionsgröße, Limits, Kill-Switch
│   ├── executor.py      # Orders, Stop-Überwachung
│   ├── loop.py          # Hauptschleife (eigener Container)
│   ├── schatten.py      # Aufsicht: Papier-Schleifen als Threads
│   └── watchdog.py      # Herzschlag-Prüfung, nur lesend
├── frontend/
│   ├── src/views/       # eine Datei je Seite
│   ├── src/components/  # Bausteine und Panels
│   ├── src/stores/      # Pinia (Anmeldung)
│   ├── src/router/      # Routen, Rollen-Guards
│   └── src/api.js       # axios mit Token
├── tests/               # pytest, conftest.py mit In-Memory-DB
├── scripts/             # Messungen und Einmal-Werkzeuge
├── deploy/              # systemd-Units für Sammler-Timer
├── data/                # SQLite, Schlüssel (nicht im Repo)
├── setup.py             # DB anlegen, Admin-Benutzer
├── Context.md           # Stand, Dienste, Regeln
├── todo.md              # Aufgaben, Wiedervorlagen
└── Analytic.md          # Messungen und Befunde
```

## Schichten und Verantwortlichkeiten

- **Oberfläche**: zeigt an und löst Aktionen aus, keine Geschäftsregeln. Der Router-Guard ist nur Komfort, maßgeblich ist der Server.
- **API**: Eingabe prüfen (Pydantic), Rolle prüfen (`require_role`), Fachmodul aufrufen, JSON zurückgeben. Ein Test stellt sicher, dass keine Route ohne Rollen-Dependency existiert.
- **Fachmodule**: reine Funktionen (strategy, scoring, exit_rules) getrennt von Modulen mit Seiteneffekten (executor, exchange). Live-Code und Simulator nutzen dieselben reinen Funktionen.
- **Schleifen**: ein Durchlauf ist `tick(client)` und gibt die Wartezeit zurück. Fehler werden im Tick gefangen.
- **Aufsicht**: startet Schleifen als Threads, setzt sie bei Fehlern mit Backoff (10 s bis 600 s) neu auf.
- **Persistenz**: Modelle, Session-Fabrik, kleine idempotente Migrationen, Einstellungen als Key-Value-Tabelle.
- **Watchdog**: liest Herzschläge, ruft nie die Börse auf, wirft nie.

## Namens- und Methodenkonventionen

Module und Funktionen `snake_case`, Klassen `PascalCase`, private Helfer mit Unterstrich, Eingabemodelle enden auf `In`. Kommentare erklären das Warum.

```python
class UserCreateIn(BaseModel):
    username: str
    password: str
    role: str = "beobachter"

@app.post("/api/users")
def create_user(body: UserCreateIn, user: store.User = Depends(require_role("admin"))):
    with store.SessionLocal() as s:
        ...                          # prüfen, schreiben
        audit.log_action(s, user, "user_create", body.username, {})
    return {"ok": True}
```

Schleifen-Modul:

```python
def make_client(): ...               # Client ohne Schlüssel

def tick(client) -> float:           # Rückgabe = Sekunden bis zum nächsten Durchlauf
    with store.SessionLocal() as s:
        if not enabled(s):
            return 60.0
        ...
        heartbeat(s)
    return 30.0
```

Tests: `tests/test_<modul>.py`, Funktionen `test_<verhalten>`, Datenbank über die Fixture `session`.

## Datenhaltung

- Eine SQLite-Datei unter `data/`, WAL, `busy_timeout` 10 s: API, Engine und Schatten schreiben gleichzeitig.
- Jeder Thread und Durchlauf öffnet eine eigene Session (`with SessionLocal() as s`), nie teilen.
- Einstellungen als Key-Value mit JSON-Werten; Schleifen lesen sie je Durchlauf, eine Änderung braucht keinen Neustart.
- Herzschläge sind Einstellungen mit Zeitstempel (`<name>_heartbeat`) und Grundlage der Überwachung.
- Neue Tabellen über `create_all`, neue Spalten über idempotente `_migrate_*`-Funktionen (PRAGMA-Prüfung). Kein Migrationswerkzeug.
- Börsen-Schlüssel liegen verschlüsselt in der Datenbank, der Schlüssel dazu als Datei in `data/`.
- Backup: Datei samt WAL und SHM kopieren.

## Fehlerbehandlung und Logging

- API: `HTTPException` mit Statuscode und deutscher Meldung; Pydantic liefert 422.
- Schleifen: Fehler im Tick fangen, Traceback per `print(..., flush=True)` ins Container-Log, weiterlaufen. `SystemExit` gilt als bewusster Sicherheitsabbruch und startet nicht neu.
- Entscheidungshilfen (KI-Prüfung) fallen im Zweifel auf die sichere Seite (kein Kauf); Auswertungen dürfen den Handel nie stören.
- Fachliche Entscheidungen landen in einer Tabelle (`DecisionLog`) und sind in der Oberfläche sichtbar, Sicherheitsrelevantes zusätzlich im Audit-Log.
- Der Watchdog meldet still gewordene Schleifen per Telegram. Jede Schleife schreibt in jedem Durchlauf einen Herzschlag, auch ohne Ereignis.

## Tests

- `pytest tests/ -q` vor jedem Deploy; Datenbank ist In-Memory-SQLite (`StaticPool`), Börse und KI werden gemockt.
- `conftest.py` ersetzt `store.engine` und `store.SessionLocal` per `monkeypatch`, die Produktionsdatenbank bleibt unberührt.
- Querschnittstests: jede Route hat eine Rollen-Prüfung; Paritätstests sichern, dass Live-Code und Simulator dieselbe Regel nutzen.
- Neue Wirkung zuerst messen (Backtest, Papier-Schatten), nie zwei Wirkungsänderungen ohne Vergleichsfenster.
- Frontend: kein Testlauf, geprüft wird der Build und der Browser.

## Sicherheit

- bcrypt-Hash und JWT mit `token_version`: Änderung von Rolle, Passwort oder Aktiv-Status macht alte Tokens sofort ungültig.
- Rollen `beobachter` < `trader` < `admin`, serverseitig je Route; kritische Schalter (Live-Modus, Hebel) nur für Admin.
- Brute-Force-Schutz beim Login (5 Fehlversuche in 15 Minuten), bewusst im Speicher.
- Audit-Log für Login, Einstellungen, Schlüssel, Kill-Switch und Benutzerverwaltung.
- Börsen-Schlüssel nur verschlüsselt, nie in Antworten oder Logs, ohne Auszahlungsrecht.
- Container laufen unprivilegiert (`33:33`), die API lauscht nur lokal und wird vom Webserver durchgereicht.
- Papier-Schleifen bekommen Clients ohne Schlüssel und können keine echten Orders auslösen.

## Konfiguration und Geheimnisse

- Fachliche Konfiguration lebt in der Datenbank (in der Oberfläche änderbar), technische in Umgebungsvariablen der Compose-Datei (z. B. `SCHATTEN_LOOPS`).
- `.env`-Dateien und Schlüsseldateien in `data/` stehen in `.gitignore` und gehören nie ins Repository; als Vorlage dient eine `.env.example` mit Platzhaltern.
- Zugangsdaten für Börse, KI und Mail kommen über die Oberfläche (verschlüsselt gespeichert) oder aus der Secret-Verwaltung; im Code stehen keine Werte.
- `setup.py` legt den Admin einmalig an; das Passwort wird beim Aufruf übergeben.

## Deploy

Platzhalter in spitzen Klammern (`<STACK>`, `<auth-middleware>`, `<https-redirect>`, `meine-org/...`, `*.example.org`) sind durch die eigene Umgebung zu ersetzen. Die Beispiele gehen von Docker, Traefik als Reverse Proxy und einem externen Docker-Netzwerk `web` aus; andere Proxys und Orchestrierungen funktionieren sinngemäß genauso.

- Compose-Projekt unter `<STACK>/bot`: ein Image (`meine-org/worker`, Basis `python:3.14-slim`) mit den Abhängigkeiten aus der Lock-Datei, der Code kommt per **Bind-Mount** vom Projektordner. Ein Code-Update wirkt nach Container-Neustart ohne Image-Build.
- Je Rolle ein Container aus einem YAML-Anker: `bot-api` (uvicorn), `bot-engine`, `bot-longterm`, `bot-schatten`. Gemeinsam `network_mode: host`, `user: "33:33"`, `restart: unless-stopped`, `stop_grace_period: 30s`, `mem_limit` wo nötig.
- Neustart: `docker restart bot-api bot-engine bot-longterm bot-schatten`. Alte systemd-Dienste für dieselben Prozesse sind maskiert.
- Frontend: `npm run build`; der Webserver-Container liefert `frontend/dist` statisch und reicht `/api/` an den lokalen API-Port durch. Traefik routet den Host auf den Webserver-Dienst, TLS per Let's Encrypt.
- Sammler und Berichte laufen als systemd-Timer auf dem Host (`Type=oneshot`, `User=www-data`, `MemoryMax`, `Nice`), Units in `deploy/`.
- Healthcheck: `GET /api/health` liefert `{"ok": true}`; Schleifen überwacht der Herzschlag.
- Keine Auth-Middleware, die Anwendung meldet selbst an (JWT).

## Typische Fehler

- **Zwei Engines gleichzeitig**: alter systemd-Dienst und Container handeln doppelt. Alte Units maskieren.
- **Alte Tokens nach Deploy**: ändert sich das Token-Schema, sind alle Sitzungen ungültig.
- **Stille Schleife**: eine Schleife, die nur bei Ereignissen schreibt, ist nicht überwachbar; aus einem leeren Entscheidungslog nicht auf Ausfall schließen.
- **Fehlalarm nach Neustart**: der Watchdog braucht eine Karenzzeit, sonst alarmiert er auf den veralteten Snapshot.
- **Task ohne Referenz**: `asyncio.create_task` ohne gehaltene Referenz kann der Garbage Collector einsammeln.
- **ccxt nicht threadsicher**: ein geteilter Client braucht eine Sperre pro Aufruf.
- **Verschluckte Rate-Limit-Fehler** in Order-Funktionen; Verhalten ändern braucht eine Entscheidung.
- **Einzelfenster-Effekte**: kurze Messfenster führen zu falschen Schlüssen; Lern-, Prüf- und Vortest-Zeitraum trennen.
- **Überschriebene Werte**: globale Einstellungen überschreiben Strategie-Werte; die Oberfläche muss den wirksamen Wert zeigen.
- **Vergessene Migration**: Tests auf frischer DB sind grün, der Bestand hat die Spalte nicht.

### Verbesserungen für neue Projekte

- `api/main.py` früh in `APIRouter`-Module je Fachgebiet teilen (große Moduldateien mit mehreren tausend Zeilen sind schwer wartbar).
- Alembic statt handgeschriebener `_migrate_*`-Funktionen.
- Einstellungen als typisiertes Pydantic-Modell statt loser Key-Value-Zugriffe.
- `logging` mit Stufen statt `print`; Lifespan-Handler statt `@app.on_event`.
- Einen gemeinsamen Herzschlag-Helfer für alle Schleifen von Anfang an.
- Frontend-Tests (Vitest) für Auth-Store und Rollen-Guards.
- Unveränderliche Releases statt Bind-Mount auf das Arbeitsverzeichnis, damit nie ein halber Stand live läuft.

## Checkliste

- Jede neue Route hat eine Rollen-Dependency und ist im Vollständigkeitstest erfasst
- Eingaben über Pydantic-Modelle mit Grenzwerten
- Neue Schleife: `tick(client)`, Herzschlag, Fehlerfang, Eintrag in der Aufsicht
- Schemaänderung mit idempotenter Migration und Test gegen eine Bestands-DB
- Tests ohne Netzwerk und ohne Produktionsdatenbank
- `.env`, `data/`, Schlüssel und DB-Dateien in `.gitignore`
- Keine Geheimnisse in Logs, Antworten oder Commits
- Kritische Schalter nur Admin und im Audit-Log
- Vor dem Deploy `pytest`, danach Container neu starten und `/api/health` prüfen
- Frontend gebaut, `dist/` nicht im Repo
- Neue Wirkung zuerst als Papier-Schatten oder Backtest messen
- Context.md und todo.md fortschreiben
