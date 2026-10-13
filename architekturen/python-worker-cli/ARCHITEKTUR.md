# Python Worker / CLI mit systemd-Timer

## Kurzbeschreibung

Ein kleiner Python-Dienst für wiederkehrende Aufgaben ohne eigene Oberfläche: prüfen, sammeln, berichten, aufräumen. Er ist ein Kommandozeilenprogramm mit Unterbefehlen (`pruefen`, `bericht`, `status`). Ein systemd-Timer startet es in festen Abständen als `oneshot`-Dienst, eine Dateisperre verhindert Überschneidungen, das Ergebnis landet atomar in einer Statusdatei, die andere Teile (z. B. ein Panel) lesen.

Herkunft und Reifegrad: Die Grundmuster (oneshot-Dienst plus Timer, Unterbefehl per Argument, Statusdatei mit Schreiben-und-Umbenennen, `flock` gegen Doppelstart, Zugangsdaten nur aus dem Secret-Helfer, Parallelprüfung mit Thread-Pool) sind aus mehreren produktiven Host-Skripten abgelesen. Die Skripte sind einzelne Dateien nur mit Standardbibliothek, ohne Tests und ohne Paketierung. Paketierung (`pyproject.toml`, venv), argparse-Unterbefehle, pytest und Logging stammen aus öffentlicher Best Practice und sind in diesen Skripten so noch nicht im Einsatz; daher gilt die Beschreibung insgesamt als recherchiert.

## Passt für / passt nicht für

Passt für:
- Erreichbarkeits- und Gesundheitsprüfungen, Sammler, Importer, Berichte, Aufräumjobs
- Aufgaben, die in Sekunden bis wenigen Minuten fertig sind und in festem Takt laufen
- Ergebnisse, die als JSON-Datei oder Meldung reichen

Passt nicht für:
- Dauerläufer mit Verbindungen oder Zustand im Speicher (dafür eine Schleife im Container)
- Aufgaben mit Warteschlange, Wiederholung und vielen parallelen Workern (dann ein Job-System)
- Alles mit Oberfläche oder eigener API; die liest nur die Statusdatei
- Echtzeit-Reaktion unter einer Minute

## Sprache und Stack

- **Python 3** in der aktuell vom Betriebssystem gelieferten Version, mindestens 3.11: `tomllib`, bessere Typannotationen, keine Zusatzpakete für Basisaufgaben
- **argparse** (Standardbibliothek) für Unterbefehle; **Typer** nur, wenn viele Befehle und Hilfetexte anfallen. Ein Befehl braucht kein Framework
- **Standardbibliothek zuerst**: `urllib`, `json`, `subprocess`, `fcntl`, `concurrent.futures`, `logging`, `pathlib`. Wenige Abhängigkeiten, weniger Pflege
- **requests/httpx** nur, wenn Standardbibliothek spürbar umständlich wird
- **pyproject.toml** mit Einstiegspunkt (`[project.scripts]`) und **venv**, sobald es Abhängigkeiten oder mehrere Module gibt
- **pytest** für Tests, **ruff** für Lint und Format
- **systemd** (Service plus Timer) als Planer; kein cron, weil Journal, Ressourcenlimits und Abhängigkeiten dabei sind

## Ordnerstruktur

```
worker/
├── pyproject.toml            # Metadaten, Abhängigkeiten, Einstiegspunkt, ruff/pytest-Einstellungen
├── README.md                 # Zweck, Aufruf, Statusformat
├── .env.example              # Platzhalter für Umgebungsvariablen
├── src/worker/
│   ├── __init__.py
│   ├── cli.py                # argparse, Unterbefehle, Exit-Codes
│   ├── config.py             # Pfade und Einstellungen aus Umgebung/Datei
│   ├── checks.py             # fachliche Prüfungen, reine Funktionen
│   ├── status.py             # Statusdatei lesen/atomar schreiben
│   ├── lock.py               # flock-Kontext
│   └── secrets.py            # Zugang zum Secret-Helfer, nie loggen
├── tests/
│   ├── conftest.py           # tmp_path-Status, gefälschte Netzwerkfunktionen
│   ├── test_checks.py        # Fachlogik
│   └── test_status.py        # Atomarität, Altstatus mit fehlenden Feldern
├── systemd/
│   ├── worker.service        # Type=oneshot
│   └── worker.timer          # OnCalendar
└── .gitignore                # venv, __pycache__, .env, Statusdaten
```

## Schichten und Verantwortlichkeiten

- **cli.py**: nur Argumente lesen, Sperre nehmen, Fachfunktion aufrufen, Exit-Code setzen. Keine Fachlogik.
- **checks.py**: Prüfungen als reine Funktionen mit Eingabe und Ergebnis-Dict. Netzwerk und Prozesse kommen als Parameter oder werden in Tests ersetzt.
- **status.py**: einzige Stelle, die die Statusdatei schreibt. Schreiben in `status.json.neu`, danach `os.replace`, damit Leser nie eine halbe Datei sehen.
- **lock.py**: nichtblockierende Dateisperre; wer sie nicht bekommt, beendet sich mit Hinweis und Exit-Code 0.
- **secrets.py**: holt Zugangsdaten zur Laufzeit aus dem Secret-Helfer oder der Umgebung, hält sie nur im Speicher und schreibt sie nie in Status oder Log.
- **systemd**: Planung, Benutzer, Zeitlimit, Speicherlimit. Das Programm kennt seinen Takt nicht.

## Namens- und Methodenkonventionen

Module und Funktionen `snake_case`, Befehle als Verben (`pruefen`, `bericht`), Konstanten oben im Modul in Großbuchstaben. Funktionen liefern Daten zurück, ausgegeben wird nur in `cli.py`.

```python
# cli.py
def main(argv: list[str] | None = None) -> int:
    parser = argparse.ArgumentParser(prog="worker")
    sub = parser.add_subparsers(dest="befehl", required=True)
    sub.add_parser("pruefen", help="Prüfungen ausführen und Status schreiben")
    args = parser.parse_args(argv)
    with sperre(config.LOCKDATEI) as bekommen:
        if not bekommen:
            log.info("Läuft bereits.")
            return 0
        if args.befehl == "pruefen":
            return pruefen()
    return 2

if __name__ == "__main__":
    raise SystemExit(main())
```

```python
# status.py: atomar schreiben
def schreibe(pfad: Path, daten: dict) -> None:
    tmp = pfad.with_suffix(".json.neu")
    tmp.write_text(json.dumps(daten, ensure_ascii=False, indent=1), encoding="utf-8")
    os.replace(tmp, pfad)
```

```python
# sperre über flock
@contextmanager
def sperre(pfad):
    f = open(pfad, "a")
    try:
        fcntl.flock(f, fcntl.LOCK_EX | fcntl.LOCK_NB)
        yield True
    except BlockingIOError:
        yield False
    finally:
        f.close()
```

## Datenhaltung

- Ergebnis: eine JSON-Datei in einem festen Datenordner (z. B. `daten/status.json`), Zeitstempel in UTC mit Zeitzone, Eigentümer so gesetzt, dass der Leser (Webserver, Panel) sie lesen kann.
- Verlauf als begrenzte Liste im selben Dokument (z. B. die letzten 288 Einträge bei 5-Minuten-Takt), nicht als wachsende Datei.
- Beim Schreiben den **alten Status einlesen** und übernehmen, was in diesem Lauf nicht neu ermittelt wurde (z. B. teure Prüfungen, die nur alle 15 Minuten laufen). Kaputte oder fehlende Datei gilt als leerer Status.
- Wird es größer als ein paar hundert KB oder braucht es Abfragen, auf SQLite wechseln.
- Idempotenz: ein Lauf darf beliebig oft hintereinander laufen und liefert denselben Zustand; Meldungen (Mail, Telegram) nur bei Zustandswechsel und mit gemerktem Letztstand, sonst kommt jede Meldung alle fünf Minuten.

## Fehlerbehandlung und Logging

- Jede Einzelprüfung fängt ihre Fehler selbst und liefert ein Ergebnis wie `{"code": 0, "fehler": "Timeout"}`. Ein Fehler bei einem Ziel darf die anderen nicht abbrechen.
- Nur Fehler, die den ganzen Lauf betreffen, beenden mit Exit-Code ungleich 0; systemd zeigt den Dienst dann als fehlgeschlagen.
- Logging über das Modul `logging` auf stderr, systemd sammelt es im Journal. Stufen verwenden, Uhrzeit weglassen (das Journal setzt sie).
- Fehlerart (Klassenname, kurze Meldung) in den Status schreiben, nie Zugangsdaten, URLs mit Token oder Roh-Antworten.
- Zeitlimits an jedem Netzwerk- und Prozessaufruf (`timeout=`); ohne sie hängt der Lauf und die Sperre blockiert alle Folgeläufe.
- Parallele Prüfungen mit `ThreadPoolExecutor` (begrenzte Worker-Zahl), nicht mit selbstgebauten Threads.

## Tests

- **pytest** mit `tmp_path` für Status und Sperre; keine Tests gegen das echte Netz oder echte Zugänge.
- Netzwerk- und Secret-Aufrufe über Parameter oder `monkeypatch` ersetzen. Das gelingt nur, wenn die Fachlogik sie nicht fest verdrahtet.
- Testfälle: Normalfall, Zeitüberschreitung, kaputte Antwort, fehlende oder alte Statusdatei, Sperre belegt, atomares Schreiben (keine `.neu`-Datei bleibt liegen).
- `ruff check` und `ruff format --check` vor dem Commit; optional `mypy` für die Kernmodule.
- Manueller Gegencheck: `systemd-analyze calendar '<Ausdruck>'` für den Timer und ein einmaliger Lauf als der Dienstbenutzer.

## Sicherheit

- Der Dienst läuft als eigener, unprivilegierter Benutzer, nicht als root, sofern nichts anderes zwingt. Dateirechte der Statusdatei nur so weit öffnen wie nötig.
- systemd-Härtung: `NoNewPrivileges=true`, `ProtectSystem=strict` mit `ReadWritePaths=` für den Datenordner, `PrivateTmp=true`, `MemoryMax=`, `TimeoutStartSec=`.
- Zugangsdaten nie als Befehlszeilenargument (sichtbar in der Prozessliste), nie im Status, nie im Journal.
- Eingaben aus dem Netz (Antworten, Logzeilen) als nicht vertrauenswürdig behandeln: kürzen, nicht als Befehl ausführen, bei `subprocess` Argumentliste statt Shell-String.
- Entfernte Befehle über SSH nur mit festem Befehlstext, ohne Eingaben aus Daten zusammenzubauen.
- Abhängigkeiten fixieren (`pip freeze` oder Lock-Datei) und gelegentlich prüfen.

## Konfiguration und Geheimnisse

- Konfiguration in dieser Reihenfolge: Standardwerte im Code, Datei im Projekt (ohne Geheimnisse), Umgebungsvariablen aus `EnvironmentFile=` in der Unit.
- `.env` und jede Datei mit Zugangsdaten gehören nie ins Repository und in `.gitignore`; im Repo liegt nur `.env.example` mit Platzhaltern.
- Geheimnisse zur Laufzeit aus der Secret-Verwaltung holen (Hilfsprogramm als Unterprozess, Ausgabe nur im Speicher), die Unit setzt höchstens den Namen des Eintrags, nie den Wert.
- Pfade (Daten-, Sperrdatei) als Konstanten oder Umgebungsvariablen, damit Tests sie umlenken können.

## Deploy

Platzhalter in spitzen Klammern (`<STACK>`, `<auth-middleware>`, `<https-redirect>`, `meine-org/...`, `*.example.org`) sind durch die eigene Umgebung zu ersetzen. Die Beispiele gehen von Docker, Traefik als Reverse Proxy und einem externen Docker-Netzwerk `web` aus; andere Proxys und Orchestrierungen funktionieren sinngemäß genauso.

Variante A, klassisch auf dem Host: Programm liegt auf dem Host, systemd startet es.

```
# worker.service
[Unit]
Description=Worker: <Aufgabe>
[Service]
Type=oneshot
User=<unprivilegierter-benutzer>
ExecStart=<WORKER_DIR>/venv/bin/worker pruefen
TimeoutStartSec=240
MemoryMax=300M
Nice=10

# worker.timer
[Timer]
OnCalendar=*:0/5
Persistent=false
[Install]
WantedBy=timers.target
```

- Aktivieren mit `systemctl daemon-reload` und `systemctl enable --now worker.timer`; die Unit-Dateien liegen im Repo und werden nach `/etc/systemd/system` kopiert oder verlinkt.
- `Persistent=false`, wenn verpasste Läufe nach einem Neustart nicht nachgeholt werden sollen (Prüfungen); `Persistent=true` bei täglichen Berichten. Bei Zufallsversatz `RandomizedDelaySec=` setzen.
- Zusätzliche Aktionen (Lebenszeichen an ein Dashboard, Meldung bei Start und Ende) als Drop-in unter `<unit>.service.d/*.conf` mit `ExecStartPre=-` und `ExecStopPost=-`, damit ein Fehler dort den Lauf nicht abbricht.
- Die Statusdatei liegt im Datenordner des Panels, das sie liest; das Panel läuft als Container hinter Traefik (bei Bedarf mit einer Auth-Middleware) und bindet den Ordner schreibgeschützt ein.

Variante B: als Container (`python:3-slim`, venv-Abhängigkeiten) mit `restart: "no"` und Start per Host-Timer über `docker compose run --rm`; sinnvoll, wenn der Host sauber bleiben soll. Ein Healthcheck ist bei kurzlebigen Läufen nicht nötig; die Überwachung prüft das Alter der Statusdatei.

## Typische Fehler

- **Überschneidende Läufe**: ohne Sperre startet der Timer einen zweiten Lauf, während der erste hängt. Sperre plus Zeitlimits.
- **Halb geschriebene Statusdatei**: direkt in die Zieldatei schreiben lässt Leser kaputte JSON sehen. Immer temporäre Datei und `os.replace`.
- **Zugriffsrechte**: Datei gehört dem Dienstbenutzer, der Leser kann sie nicht öffnen. Eigentümer nach dem Schreiben setzen.
- **Meldungsflut**: bei jedem Lauf dieselbe Warnung. Letztstand merken und nur bei Wechsel melden.
- **Zeitzonen**: `OnCalendar` ohne Zeitzone läuft in Systemzeit; im Status UTC mit Offset speichern.
- **Veralteter Status ohne Warnung**: stirbt der Timer, bleibt die Datei stehen und sieht gesund aus. Die Anzeige muss das Alter prüfen.
- **Zu teure Prüfungen im kurzen Takt**: langsame Prüfungen (SSH, große Logs) im eigenen, selteneren Takt innerhalb des Laufs und alten Wert übernehmen.
- **Geheimnisse im Journal**: Fehlertexte von Bibliotheken enthalten oft die URL samt Token. Vor dem Loggen kürzen oder filtern.
- **Systempython ändern**: Pakete in den Systeminterpreter zu installieren bricht beim OS-Update; venv benutzen.

### Verbesserungen für neue Projekte

- Gleich als Paket mit `pyproject.toml` und Einstiegspunkt anlegen statt als einzelne Datei im Home-Verzeichnis.
- Fachlogik von Ein- und Ausgabe trennen, damit sie ohne Netz testbar ist.
- Ein gemeinsames Hilfsmodul für Sperre, atomares Schreiben und Secret-Zugriff, statt in jedem Skript zu kopieren.
- Strukturierte Logs mit `logging` statt `print`.
- Die Unit-Dateien ins Repository nehmen und per Installationsskript verteilen.

## Checkliste

- Ein Einstiegspunkt mit Unterbefehlen und klaren Exit-Codes
- Sperre per `flock` nichtblockierend, bei Belegung sauber beenden
- Zeitlimit an jedem Netzwerk- und Prozessaufruf
- Einzelfehler pro Ziel abfangen, Lauf fortsetzen
- Statusdatei atomar schreiben, alten Stand bei Teilprüfungen übernehmen
- Meldungen nur bei Zustandswechsel
- Lauf ist idempotent und darf beliebig oft starten
- Keine Geheimnisse in Argumenten, Status oder Journal
- `.env` nicht im Repo, `.env.example` mit Platzhaltern
- Unit mit `Type=oneshot`, `TimeoutStartSec`, `MemoryMax`, eigener Benutzer
- Timer-Ausdruck mit `systemd-analyze calendar` geprüft, `Persistent` bewusst gewählt
- pytest-Tests ohne Netz, `ruff` sauber
- Anzeige prüft das Alter der Statusdatei
