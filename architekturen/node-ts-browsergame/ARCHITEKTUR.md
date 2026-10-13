# Node/TypeScript Browsergame (autoritativer Server)

## Kurzbeschreibung

Ein Single-Player-Browsergame mit serverseitig autoritativer Spiellogik. Drei npm-Workspaces teilen sich ein Repository: `shared` (reine Regeln und Typen), `server` (Fastify, MySQL, Spielaktionen) und `client` (Phaser-Szenen plus HTML-Overlays). Inhalte wie Quests, Dialoge, Kunden und Items stehen als JSON in `content/` und sind Daten, kein Code.

Der Spielstand ist ein einziges JSON-Dokument je Nutzer. Jede Aktion läuft als Transaktion: Zeile sperren, Welt weiterticken, Regel anwenden, Zustand zurückschreiben. Der Client zeigt nur an und schickt Absichten.

Der Aufbau befindet sich im Entwicklungsstadium und ist noch nicht produktiv; die Beschreibung stammt aus dem tatsächlichen Code.

## Passt für / passt nicht für

Passt für:
- Aufbau-, Management- und Wirtschaftsspiele mit Geld, Timern, Quests und Inventar
- Spiele, bei denen Betrug (Geld, Zeit, Position) verhindert werden soll
- Inhaltsreiche Spiele, die Autoren ohne Codeänderung erweitern sollen

Passt nicht für:
- Echtzeit-Mehrspieler mit vielen gleichzeitigen Spielern; es gibt kein Netzprotokoll mit Synchronisation, nur HTTP
- Spiele mit riesigen Spielständen: das Save-Dokument wird bei jeder Aktion komplett gelesen und geschrieben
- Reine Offline-Spiele ohne Konto

## Sprache und Stack

- **TypeScript 5.9** in allen Workspaces, Modulsystem ESM: ein Typsatz für Client, Server und Regeln
- **Node 24** (Image `node:24-slim`): aktuelle LTS-Linie, `--env-file` ohne dotenv
- **Fastify 5** mit cookie-, rate-limit- und static-Plugin: schlank, schnell, gute Typen
- **MySQL 8.4** über `mysql2` (Pool, Unix-Socket): robuste Zeilensperren für Save-Transaktionen
- **bcryptjs** für Passwörter, Sitzungen als Token in Cookie plus Tabelle
- **Phaser 3.90** und **Vite 8** im Client: 2D-Szenen, schneller Build; UI-Panels als DOM-Overlays
- **Vitest 3** in allen Workspaces
- npm-Workspaces, damit `@projekt/shared` ohne Veröffentlichung eingebunden wird

## Ordnerstruktur

```
projekt/
├── shared/src/           # reine Regeln, Typen, Konstanten (kein I/O)
│   ├── types.ts          # SaveState und Definitionen
│   ├── economy.ts        # Geld, Deckel, Zufall mit Seed
│   ├── <thema>.ts        # eine Datei je Regelbereich (quests, ruf, automatik ...)
│   ├── <thema>.test.ts   # Test direkt daneben
│   └── index.ts          # Re-Exports aller Module
├── server/src/
│   ├── main.ts           # Start, Port, Migrationen
│   ├── app.ts            # Fastify, Plugins, Origin-Prüfung, Static, SPA-Fallback
│   ├── routes/           # auth.ts, game.ts (dünn: Eingabe, Aktion, Antwort)
│   ├── game/             # engine.ts: Aktionen als reine Funktionen, errors.ts
│   ├── repo/             # saves.ts, users.ts, sessions.ts (SQL)
│   ├── db/               # pool.ts (MySQL-Pool)
│   ├── migrations/sql/   # 001_init.sql ... fortlaufend
│   ├── http/             # auth-guard.ts, session.ts
│   └── content.ts        # lädt content/*.json und prüft sie beim Start
├── client/src/
│   ├── main.ts           # Start, Autosave, Netz
│   ├── scenes/           # Phaser-Szenen (GameScene)
│   ├── ui/               # DOM-Overlays (Büro-OS, Dialoge, Minispiele)
│   ├── art/              # code-erzeugte Vektorgrafik
│   ├── audio/, net/, events/, util/
│   └── state.ts          # Client-Spiegel des Spielstands
├── content/              # Spielinhalt als JSON (quests, dialoge, kunden, items ...)
├── docs/                 # Pläne, Befunde, Textstil
├── deploy-dev.sh         # Build, Release-Ordner, Symlink, Health, Rollback
├── GAME.md               # Spieldesign
├── Context.md            # Stand, Fallen, Browsercheck-Hinweise
└── todo.md               # Runden, Befunde, offene Punkte
```

## Schichten und Verantwortlichkeiten

- **shared**: reine Funktionen und Konstanten ohne I/O. Alles, was Client und Server gleich wissen müssen (Geschwindigkeitsfaktor, Deckel, Preise, Klassifikationen), steht nur hier.
- **content**: JSON-Dateien, beim Serverstart geladen und durch einen Content-Test auf Konsistenz geprüft (Verweise, Überschneidungen, Textstil).
- **engine.ts**: jede Spielaktion ist `(save, args..., now?) => SaveState`. Keine Datenbank, kein `Date.now()`, die Zeit wird als Parameter übergeben.
- **routes**: validieren Eingaben, rufen über `runAction` die Engine in einer Transaktion auf und übersetzen `ActionError` in Statuscode und Meldung.
- **repo**: einzige Stelle mit SQL. `withSaveTransaction` sperrt die Save-Zeile (`FOR UPDATE`), parst den Zustand und schreibt ihn zurück.
- **client**: rendert, nimmt Eingaben und Touch-Steuerung entgegen, schätzt voraus, übernimmt aber immer die Serverantwort.

## Namens- und Methodenkonventionen

Dateien `kleinbuchstaben-mit-bindestrich.ts` oder ein Wort, Funktionen `camelCase`, Typen `PascalCase`, Konstanten `SCREAMING_SNAKE`, Spielinhalte deutsch, Code-Bezeichner meist deutsch-englisch gemischt. Aktionsfunktionen heißen nach dem Verb (`collectPfand`, `buyShopItem`, `toggleFahrrad`).

```ts
export function useParkbank(save: SaveState, x: number, y: number,
                            scene: string, now: Date = new Date()): SaveState {
  if (!isNear(save, x, y)) throw new ActionError('Zu weit weg.', 400);
  // Regel prüfen, dann neuen Zustand zurückgeben (nie mutieren)
  return { ...save, energy: Math.min(100, save.energy + 10) };
}
```

Route:

```ts
app.post('/api/game/action/parkbank', { preHandler: requireAuth },
  async (req, reply) => runAction(req.userId, reply, (save) => {
    const next = useParkbank(save, body.x, body.y, body.scene);
    return { next, response: next };
  }));
```

Neue Spielstandfelder werden optional (`feld?: ...`) deklariert, `saves.ts` setzt Standardwerte und migriert Altstände.

## Datenhaltung

- MySQL: Tabellen für Nutzer, Sitzungen und Spielstände. Der Spielstand liegt als JSON in einer Spalte (`saves.state`).
- Migrationen: nummerierte SQL-Dateien in `migrations/sql`, ein Läufer mit Tabelle `schema_migrations`, jede Datei in einer Transaktion. Das Build kopiert die Dateien in `dist`.
- Spielstand-Migration passiert beim Laden (`normalizeSave`, `migrate*`), nicht per SQL. Reihenfolge der Migrationsschritte ist wichtig.
- Zufall ist deterministisch: Seeds aus Tagesdatum, Ort und einem serverseitigen Geheimnis (`seed-secret`), damit Ergebnisse nicht erraten oder neu gewürfelt werden können.
- Offline-Fortschritt wird beim Login aus Zeitstempeln berechnet (gedeckelt auf 2 Stunden).
- Tests laufen gegen eine eigene Test-Datenbank; fehlt `DB_NAME`, bricht der Pool laut ab.

## Fehlerbehandlung und Logging

- `ActionError(message, statusCode, code)` für erwartbare Regelverstöße; `handleActionError` macht daraus eine JSON-Antwort `{ error, code }`. Alles andere wird erneut geworfen und von Fastify zu 500.
- Fastify-Logger an (`logger: true`), Ausgabe im Container-Log; keine Spielstände und Geheimnisse loggen.
- Rate-Limit 300 pro Minute auf `/api/`, Statische Dateien ausgenommen.
- 404 unter `/api/` und für Dateien mit Endung bleibt 404, alles andere fällt auf `index.html` (SPA).

## Tests

- **shared**: Vitest-Unit-Tests neben jeder Regeldatei, ohne Datenbank.
- **server**: Engine-Tests als reine Funktionen (die größte Gruppe), Route- und Repo-Tests gegen die Test-Datenbank, Content-Test für alle JSON-Dateien. `vitest.setup.ts` lädt `.env.test` und überschreibt bewusst geerbte Variablen, damit nie gegen die Entwicklungsdatenbank getestet wird.
- **client**: Vitest für Regeln der Minispiele und Gesten.
- Befehl: `npm test` im Wurzelordner, `npm run typecheck` zusätzlich.
- Browsercheck zusätzlich per puppeteer-core und Chromium gegen eine lokale Instanz mit Testdatenbank; Testkonten werden am Ende per ID gelöscht.

## Sicherheit

- Der Server ist autoritativ für Geld, Timer, Quests, Inventar und Position: Der Client sendet Absichten, nie Ergebnisse. Bewegungen laufen gegen ein serverseitiges Bewegungsbudget.
- Aktionen mit Ortsbezug prüfen die Nähe serverseitig.
- Origin-Prüfung bei schreibenden Requests, `trustProxy` nur für den lokalen Proxy, damit `X-Forwarded-For` nicht gefälscht werden kann.
- Sicherheits-Header setzt der Proxy, nicht die App, damit nichts doppelt oder abweichend ist.
- Sitzungstoken im Cookie, serverseitig in der Tabelle geprüft; Passwörter nur als bcrypt-Hash.
- Zufall mit serverseitigem Geheimnis, nie im Client.

## Konfiguration und Geheimnisse

- Umgebungsvariablen: `PORT`, `HOST`, `DB_SOCKET` oder `DB_HOST`, `DB_NAME`, `DB_USER`, `DB_PASSWORD`, `SEED_SECRET`, `CLIENT_DIST`, `NODE_ENV`.
- `.env` und `.env.test` existieren lokal und stehen in `.gitignore`; im Repo liegt nur `.env.example` mit Platzhaltern.
- Auf dem Server liegt die `.env` einmalig in einem gemeinsamen Ordner außerhalb der Releases (Rechte 640, Gruppe des Webservers). `SEED_SECRET` zufällig erzeugen und nie ausgeben.
- Werte aus der Secret-Verwaltung beziehen, nicht in Skripte schreiben.

## Deploy

Platzhalter in spitzen Klammern (`<STACK>`, `<auth-middleware>`, `<https-redirect>`, `meine-org/...`, `*.example.org`) sind durch die eigene Umgebung zu ersetzen. Die Beispiele gehen von Docker, Traefik als Reverse Proxy und einem externen Docker-Netzwerk `web` aus; andere Proxys und Orchestrierungen funktionieren sinngemäß genauso.

- `deploy-dev.sh` baut im Repo (`npm install`, `npm run build`) und stellt eine **unveränderliche Release** unter einem Basisordner zusammen: `releases/<Zeitstempel>/` mit `server/dist`, `shared/dist`, `client/dist`, `content/` und `node_modules`.
- Danach laufen die Migrationen gegen die neue Release (mit der gemeinsamen `.env`), Rechte werden gesetzt, und der Symlink `current` wird **atomar** umgeschaltet (`ln -sfn` auf `current.tmp`, dann `mv -T`).
- Der Container wird neu gestartet und ein Healthcheck pollt einen Content-Endpunkt bis zu 15 Sekunden. Schlägt er fehl, wird der Symlink auf die vorige Release zurückgesetzt und neu gestartet. Es bleiben die letzten drei Releases.
- Compose-Projekt unter `<STACK>/game`: Image `node:24-slim`, `user: "33:33"`, Basisordner read-only gemountet, MySQL-Socket gemountet, Start per `node --env-file=<shared>/.env dist/main.js`, `HOST=0.0.0.0` im Container.
- Traefik-Labels: `traefik.enable=true`, Router für `websecure` mit `tls.certresolver=le`, ein HTTP-Router mit der Weiterleitungs-Middleware, Service-Port als Loadbalancer-Port. Netz `web` extern. Der Port wird nur lokal für den Healthcheck veröffentlicht.
- Keine Auth-Middleware; die Anmeldung macht das Spiel selbst.

## Typische Fehler

- **Veraltetes `shared/dist`**: Server und Client importieren das gebaute Paket; ein alter Build täuscht grüne Tests mit altem Verhalten vor. Erst `shared` bauen.
- **Konstante nur auf einer Seite**: der Geschwindigkeitsfaktor des Fahrrads muss im Client und im Server bekannt sein, sonst lehnt der Server normales Fahren ab.
- **Boni aus mehreren Quellen ohne gemeinsamen Deckel**: Tageslimits für Erholung und Mali bei Delegation und Automatik brauchen einen Deckel über die Summe, nicht je Quelle.
- **Gesperrter Inhalt unerreichbar**: ein Kauf hinter einer Dialogoption, die an eine Quest gebunden ist, war ohne die Quest nicht erreichbar. Zugangswege einzeln prüfen.
- **Reihenfolge von Migrationen**: Spielstand-Migrationen müssen vor jedem Zugriff auf neue Felder laufen.
- **Fixtures**: viele Tests bauen `SaveState` als vollständiges Literal; ein neues Pflichtfeld bricht Dutzende Tests. Felder optional anlegen.
- **Browsercheck-Fallen**: ein frisches Testkonto ohne Aussehen und Branche zeigt den Editor statt des Spiels; eine per SQL gesetzte Position auf einer Kollisionsfläche springt beim Laden zurück zum Startpunkt.
- **Headless ohne GPU** liefert nur 2 bis 4 FPS; Zeitlogik nach Wanduhr, nicht nach Frames.

### Verbesserungen für neue Projekte

- Spielstand in mehrere Spalten oder Tabellen gliedern, damit nicht jede Aktion das ganze Dokument schreibt.
- Eine Schema-Validierung (z. B. zod) für Save und Content statt handgeschriebener Prüfungen.
- `engine.ts` früh in Module je Systemgruppe teilen (heute eine sehr große Datei).
- Content-Schemata als Typen aus JSON generieren, damit Autoren früh Fehler sehen.
- Von Anfang an die unveränderliche Release mit Symlink und Rollback vorsehen und `shared` im Build vor allem anderen bauen.
- Lint und Formatierung (ESLint, Prettier) einführen.

## Checkliste

- Neue Regel zuerst in `shared`, mit Test neben der Datei
- Aktion als reine Funktion `(save, ..., now) => SaveState`, keine Uhr und keine Datenbank darin
- Route nur über `runAction` und `requireAuth`
- Neue Spielstandfelder optional, mit Standardwert und Migration in `saves.ts`
- Tageslimits und Boni über die Summe aller Quellen deckeln
- Inhalte in `content/*.json`, Content-Test erweitern
- Serverseitige Prüfung für Position, Geld und Zeit
- `.env`, `.env.test` nicht committen, `.env.example` pflegen
- `npm run typecheck` und `npm test` vor jedem Merge
- Deploy nur über das Skript mit Release, Healthcheck und Rollback
- Browsercheck auf Desktop und Handy mit Testkonto, danach Testdaten per ID löschen
- Context.md und todo.md fortschreiben
