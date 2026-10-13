# Node Fastify API

## Kurzbeschreibung

Eine JSON-API auf Node.js mit Fastify. Der Aufbau folgt dem Plugin-System: Jede Funktionseinheit (Datenbank, Auth, Fachmodul) ist ein gekapseltes Plugin mit eigenem Gültigkeitsbereich. Routen definieren JSON-Schemas für Eingabe und Ausgabe; Fastify validiert damit und serialisiert schnell. Logging übernimmt pino, Tests laufen über `inject()` ohne echten Netzwerkport. Ausgeliefert wird als mehrstufig gebautes Docker-Image hinter Traefik.

## Passt für / passt nicht für

Passt für schlanke JSON-APIs, interne Dienste, Webhook-Empfänger und Backends für SPAs oder Apps, bei denen Durchsatz, Validierung und klare Modulgrenzen zählen.

Passt nicht für serverseitig gerenderte Webseiten mit viel Template-Logik (dann Next.js oder Laravel), für Projekte mit sehr vielen eingebauten Funktionen aus einem Guss (Admin-Oberfläche, ORM, Mailversand: bei Fastify selbst zusammenstellen) und für CPU-lastige Berechnungen im Request (blockiert die Event Loop).

## Sprache und Stack

- **TypeScript** im strikten Modus: Typen für Routen, Schemas und Konfiguration.
- **Node.js**, aktuelle LTS, im Container.
- **Fastify**, aktuelle Hauptversion: Plugin-Architektur, eingebaute Schema-Validierung, hohe Geschwindigkeit.
- **Schemas**: JSON Schema mit TypeBox (Typen werden aus dem Schema abgeleitet) oder Zod mit Type-Provider. Ein Ansatz pro Projekt.
- **pino**: in Fastify eingebautes, strukturiertes JSON-Logging.
- **Datenzugriff**: Postgres-Treiber, Kysely, Drizzle oder Prisma; gekapselt in einer Repository-Schicht.
- **Tests**: `node:test` (eingebaut) oder Vitest.
- **Build**: `tsc` oder esbuild; Start des kompilierten JavaScript, nicht per ts-node.

## Ordnerstruktur

```
projekt/
├── src/
│   ├── server.ts          # Einstieg: baut die App, lauscht, Signalbehandlung
│   ├── app.ts             # buildApp(): registriert Plugins und Module (testbar)
│   ├── config.ts          # Umgebung lesen und validieren
│   ├── plugins/           # übergreifende Plugins mit fastify-plugin
│   │   ├── db.ts          # Datenbankverbindung, decorate('db')
│   │   ├── auth.ts        # Authentifizierung, Hook onRequest
│   │   └── errors.ts      # zentraler Error-Handler
│   ├── modules/
│   │   └── orders/        # ein Fachmodul pro Ordner
│   │       ├── routes.ts      # Routen mit Schemas
│   │       ├── schemas.ts     # TypeBox/Zod-Schemas und Typen
│   │       ├── service.ts     # Fachlogik
│   │       └── repository.ts  # Datenbankzugriff
│   └── lib/               # kleine Hilfen ohne Fastify-Bezug
├── test/                  # Tests, spiegeln die Modulstruktur
├── migrations/            # SQL- oder Tool-Migrationen
├── Dockerfile             # mehrstufig
├── .env.example           # Platzhalter
└── tsconfig.json          # strikt
```

## Schichten und Verantwortlichkeiten

- **App-Fabrik** (`buildApp`): erzeugt die Fastify-Instanz mit Optionen, registriert Plugins und Module. Gleiche Funktion für Server und Tests.
- **Plugins**: gekapselte Einheiten. Normale Plugins sehen nur ihren eigenen Bereich; mit `fastify-plugin` gebaute Plugins (Datenbank, Auth) wirken bewusst auf die Eltern-Instanz.
- **Routen**: nur HTTP-Belange: Schema, Statuscodes, Aufruf des Service. Keine Datenbankabfragen.
- **Service**: Fachlogik und Regeln, unabhängig von HTTP.
- **Repository**: einzige Stelle mit Datenbankzugriff, gibt typisierte Objekte zurück.
- **Hooks**: `onRequest` für Authentifizierung, `preHandler` für Rechteprüfung, `onClose` zum sauberen Beenden.

Abhängigkeiten laufen von Route über Service zum Repository; Dienste werden per `decorate` oder Konstruktor bereitgestellt, nicht per globalem Import.

## Namens- und Methodenkonventionen

- Dateien kebab-case oder klein (`routes.ts`), Typen PascalCase, Funktionen camelCase.
- Pro Modul ein Plugin, das mit `fastify.register(ordersRoutes, { prefix: '/orders' })` eingebunden wird.
- Jede Route hat ein Schema für `params`/`querystring`/`body` und für jede Antwort.

```ts
// src/modules/orders/routes.ts
import { FastifyPluginAsyncTypebox } from '@fastify/type-provider-typebox';
import { Type } from '@sinclair/typebox';

const routes: FastifyPluginAsyncTypebox = async (app) => {
  app.post('/', {
    schema: {
      body: Type.Object({ title: Type.String({ minLength: 1, maxLength: 120 }) }),
      response: { 201: Type.Object({ id: Type.String(), title: Type.String() }) },
    },
    onRequest: [app.authenticate],
  }, async (request, reply) => {
    const order = await app.orders.create(request.user.id, request.body);
    return reply.code(201).send(order);
  });
};
export default routes;
```

Handler sind `async`; Rückgabewert oder `reply.send()`, nie beides.

## Datenhaltung

- Relationale Datenbank mit Migrationen im Repo; Schemaänderungen nie von Hand auf dem Server.
- Verbindungspool einmal im Plugin `db` erzeugen, bei `onClose` schließen.
- Zugriff ausschließlich über Repositories; Parameter immer gebunden, nie Strings zusammenbauen.
- Transaktionen in der Service-Schicht über den Repository-Kontext.
- Antwort-Schemas begrenzen, welche Felder die API verlässt (Passwort-Hashes, interne Spalten).
- Caches oder Queues (Redis) als eigene Plugins mit klarer Schnittstelle.
- Dateien und Zustand gehören nicht ins Container-Dateisystem.

## Fehlerbehandlung und Logging

- Zentraler `setErrorHandler`: Validierungsfehler werden zu 400 mit Feldangaben, bekannte Fachfehler zu passenden Statuscodes, alles andere zu 500 ohne interne Details.
- Eigene Fehlerklassen mit Statuscode (`NotFoundError`, `ConflictError`); Fastify-eigene Fehler (`@fastify/sensible`) wiederverwenden.
- Einheitliches Fehlerformat in allen Routen, im Schema beschrieben.
- **pino**: JSON-Zeilen auf stdout. Pro Request gibt es eine Request-ID; `request.log` nutzen statt eines globalen Loggers, damit Zeilen zusammenhängen.
- `redact` für Header und Felder wie Authorization, Cookies, Passwörter.
- Log-Level über Umgebung (`info` Produktion, `debug` lokal); keine Meldungen im Fließtext mit eingebetteten Daten.
- Unbehandelte Promise-Fehler und Signale (`SIGTERM`) abfangen und über `app.close()` sauber beenden.
- Healthcheck-Route `/health` ohne Authentifizierung.

## Tests

- **`app.inject()`** statt echter Netzwerkaufrufe: schnell, ohne Port, direkt gegen `buildApp()`.
- Test-Datenbank getrennt (eigener Container oder Schema), pro Testlauf zurückgesetzt.
- Service-Logik mit Fake-Repositories als Unit-Test.
- Jede Route: Erfolg, ungültige Eingabe, fehlende Anmeldung, fehlendes Recht.
- Schema-Verträge prüfen: Antwort enthält nur erlaubte Felder.

```ts
import { test } from 'node:test';
import assert from 'node:assert/strict';
import { buildApp } from '../src/app.js';

test('POST /orders ohne Login ergibt 401', async () => {
  const app = await buildApp();
  const res = await app.inject({ method: 'POST', url: '/orders', payload: { title: 'x' } });
  assert.equal(res.statusCode, 401);
  await app.close();
});
```

## Sicherheit

- Eingaben ausschließlich über Schemas zulassen; unbekannte Felder werden entfernt bzw. abgelehnt.
- `@fastify/helmet` für Sicherheits-Header, `@fastify/cors` mit expliziter Herkunftsliste, `@fastify/rate-limit` für Login und teure Routen.
- Authentifizierung per signiertem Token (`@fastify/jwt`) oder Session-Cookie; Rechte pro Route in `preHandler` prüfen.
- Request-Größe begrenzen (`bodyLimit`).
- Fehlerantworten ohne Stacktraces.
- Hinter Traefik `trustProxy` setzen, sonst stimmen Client-Adresse und Rate-Limit nicht.
- Abhängigkeiten regelmäßig per `npm audit` prüfen; Container als Nicht-Root-Benutzer.

## Konfiguration und Geheimnisse

- Alle Einstellungen aus Umgebungsvariablen, gelesen und validiert in `src/config.ts` (Schema mit Standardwerten, Abbruch beim Start bei fehlenden Werten).
- `.env` nie im Repository; `.env.example` mit Platzhaltern für `PORT`, `HOST`, `LOG_LEVEL`, `DATABASE_URL`, `JWT_SECRET`.
- Geheimnisse stammen aus einer zentralen Secret-Verwaltung und werden auf dem Server in die Compose-Umgebung eingetragen.
- Keine Konfiguration im Code festschreiben, die sich zwischen Umgebungen unterscheidet.

## Deploy

Platzhalter in spitzen Klammern (`<STACK>`, `<auth-middleware>`, `<https-redirect>`, `meine-org/...`, `*.example.org`) sind durch die eigene Umgebung zu ersetzen. Die Beispiele gehen von Docker, Traefik als Reverse Proxy und einem externen Docker-Netzwerk `web` aus; andere Proxys und Orchestrierungen funktionieren sinngemäß genauso.

Muster: ein Docker-Container im Netzwerk `web`, Traefik routet über Labels, Dienst in der zentralen Compose-Datei unter `<STACK>`.

- **Dockerfile** mehrstufig: Stufe `deps` (`npm ci`), Stufe `build` (`tsc`), Laufzeitstufe mit `npm ci --omit=dev`, kompiliertem `dist/` und Nicht-Root-Benutzer. Start mit `node dist/server.js`.
- **Wichtig**: `host: '0.0.0.0'` beim Lauschen, sonst erreicht Traefik den Dienst nicht. Signalbehandlung für `SIGTERM`, damit Neustarts sauber sind.
- **Healthcheck** im Image oder in Compose: HTTP-Aufruf von `/health` (Node-Fetch oder ein kleines Skript, wenn kein curl im Image ist).
- **Labels** (interne APIs ergänzen `traefik.http.routers.meineapi.middlewares=<auth-middleware>@docker`):

```
networks: [web]
labels:
  - "traefik.enable=true"
  - "traefik.http.services.meineapi.loadbalancer.server.port=3000"
  - "traefik.http.routers.meineapi.rule=Host(`meineapi.example.org`)"
  - "traefik.http.routers.meineapi.entrypoints=websecure"
  - "traefik.http.routers.meineapi.tls.certresolver=le"
  - "traefik.http.routers.meineapi-http.rule=Host(`meineapi.example.org`)"
  - "traefik.http.routers.meineapi-http.entrypoints=web"
  - "traefik.http.routers.meineapi-http.middlewares=<https-redirect>@file"
```

- **Volumes**: normalerweise keine; Zustand liegt in Datenbank oder Objektspeicher.
- **Release**: Image bauen, Migrationen als einmaliger Schritt, Container neu erstellen; `restart: unless-stopped`, `TZ=Europe/Berlin`.

## Typische Fehler

- Server lauscht auf `127.0.0.1` im Container: Traefik meldet Gateway-Fehler.
- Plugin-Kapselung missverstanden: eine mit `decorate` hinzugefügte Eigenschaft ist im Elternbereich nicht sichtbar, weil `fastify-plugin` fehlt.
- Routen ohne Antwort-Schema: langsamere Serialisierung und versehentlich ausgelieferte interne Felder.
- `async`-Handler, der zusätzlich `reply.send()` aufruft oder einen Wert nicht zurückgibt: hängende Anfragen.
- Blockierende Arbeit (große Schleifen, synchrones Hashen) in Handlern: die Event Loop steht.
- Globaler Logger statt `request.log`: Logzeilen lassen sich nicht pro Anfrage zuordnen.
- Kein sauberes Beenden: offene Verbindungen und abgebrochene Requests bei jedem Deployment.
- Fehlendes `trustProxy`: Rate Limit zählt alle Nutzer unter der Proxy-Adresse.
- Konfiguration nicht validiert: der Dienst startet mit leeren Geheimnissen.
- Tests starten einen echten Port statt `inject()`: langsam und instabil.
- `ts-node` im Produktionsimage.

## Checkliste

- `buildApp()` getrennt von `server.ts`, damit Tests ohne Port laufen
- Jede Route mit Schema für Eingabe und Antwort
- Datenbank, Auth und Fehlerbehandlung als Plugins mit passender Kapselung
- Zentraler Error-Handler mit einheitlichem Fehlerformat
- pino mit `redact`, Request-ID, Log-Level per Umgebung
- Konfiguration beim Start validiert, `.env.example` vorhanden
- Sicherheits-Plugins: helmet, cors, rate-limit; `bodyLimit` gesetzt
- Tests mit `inject()`: Erfolg, Validierungsfehler, 401, 403
- Mehrstufiges Dockerfile, Nicht-Root, `host: '0.0.0.0'`
- Sauberes Beenden bei `SIGTERM`
- Healthcheck-Route und Container-Healthcheck
- Traefik-Labels, Netzwerk `web`, ggf. Auth-Middleware
