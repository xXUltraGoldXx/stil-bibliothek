# Next.js App Router

## Kurzbeschreibung

Eine Full-Stack-Webanwendung mit Next.js im App Router. Seiten und Layouts sind standardmäßig Server Components und laden Daten direkt auf dem Server; nur interaktive Teile werden zu Client Components. Schreibzugriffe laufen über Server Actions oder Route Handlers. Für den Betrieb wird mit `output: 'standalone'` gebaut und das Ergebnis in einem schlanken Node-Container hinter Traefik ausgeliefert.

## Passt für / passt nicht für

Passt für Web-Apps und Websites mit gemischtem Inhalt (teils statisch, teils pro Nutzer), mit SEO-Anforderung, Login und Datenbankzugriff aus einer Codebasis.

Passt nicht für reine statische Seiten ohne Dynamik (dann reicht ein Static-Site-Generator), für Backends mit vielen Hintergrundjobs und langen Verbindungen als Kern (besser eigener API-Dienst) und für Teams, die keinen Node-Betrieb im Container wollen.

## Sprache und Stack

- **TypeScript** im strikten Modus: Typen von der Datenbank bis zur Komponente.
- **Next.js** (App Router), aktuelle stabile Version, und **React** in der dazu passenden Hauptversion.
- **Node.js**, aktuelle LTS, als Laufzeit im Container.
- **Tailwind CSS** oder CSS-Module: Styling ohne globale Konflikte.
- **Zod**: Validierung von Eingaben an Server Actions und Route Handlers.
- **Datenzugriff** über Prisma oder Drizzle bzw. direkten Datenbanktreiber, gekapselt in einer Datenschicht.
- **Auth.js** oder eigene Session-Lösung mit signierten, httpOnly-Cookies.
- **Vitest** für Logik, **Playwright** für Ende-zu-Ende; **ESLint** mit der Next-Konfiguration.
- **Paketmanager**: einer pro Projekt, mit Lockfile im Repo.

## Ordnerstruktur

```
projekt/
├── src/
│   ├── app/                  # Routen im App Router
│   │   ├── layout.tsx        # Wurzel-Layout (Server Component)
│   │   ├── page.tsx          # Startseite
│   │   ├── (marketing)/      # Routengruppe ohne URL-Segment
│   │   ├── dashboard/
│   │   │   ├── page.tsx      # Seite, lädt Daten serverseitig
│   │   │   ├── loading.tsx   # Ladezustand (Streaming)
│   │   │   ├── error.tsx     # Fehlergrenze (Client Component)
│   │   │   └── actions.ts    # Server Actions dieser Route
│   │   ├── api/health/route.ts   # Route Handler: Healthcheck
│   │   └── api/webhooks/route.ts # Route Handler für externe Aufrufer
│   ├── components/           # UI-Bausteine, standardmäßig Server Components
│   │   └── ui/               # kleine, wiederverwendbare Client-Bausteine
│   ├── lib/
│   │   ├── db.ts             # Datenbank-Client (einmalig, nicht pro Request)
│   │   ├── env.ts            # validierte Umgebungsvariablen
│   │   └── auth.ts           # Session lesen und prüfen
│   ├── data/                 # Datenzugriff: Abfragen als Funktionen
│   └── middleware.ts         # leichte Prüfungen vor dem Rendern (Proxy-Datei je nach Version)
├── public/                   # statische Dateien
├── next.config.ts            # output: 'standalone'
├── .env.example              # Platzhalter
└── Dockerfile                # mehrstufig
```

## Schichten und Verantwortlichkeiten

- **Server Components** (Standard): rendern auf dem Server, dürfen `async` sein und direkt auf die Datenschicht zugreifen. Kein Browser-API, kein State.
- **Client Components** (`'use client'`): nur für Interaktion, Formularzustand, Browser-APIs. Klein halten und möglichst als Blätter im Baum einsetzen.
- **Datenschicht** (`src/data`): einzige Stelle mit Datenbankzugriff. Funktionen geben schlanke, typisierte Objekte zurück, keine rohen Modelle mit sensiblen Feldern.
- **Server Actions**: Mutationen aus Formularen. Jede Action validiert die Eingabe, prüft die Session und die Berechtigung und stößt danach Revalidierung an.
- **Route Handlers** (`route.ts`): HTTP-Endpunkte für Webhooks, Healthcheck, externe Clients und Dateiauslieferung.
- **Middleware**: nur leichte Vorprüfungen (Weiterleitung, Header). Keine Datenbankzugriffe, keine schwere Logik.

Die Grenze Server/Client ist die wichtigste Architekturentscheidung: Alles, was Geheimnisse oder Datenbank berührt, bleibt auf dem Server.

## Namens- und Methodenkonventionen

- Dateien der Router-Konvention heißen fest: `page.tsx`, `layout.tsx`, `loading.tsx`, `error.tsx`, `not-found.tsx`, `route.ts`.
- Komponenten PascalCase (`UserCard.tsx`), Hilfsmodule kebab-case (`format-date.ts`), Funktionen camelCase.
- Server-only-Module mit `import 'server-only'` absichern.

```tsx
// src/app/dashboard/page.tsx
import { getOrders } from '@/data/orders';
import { requireSession } from '@/lib/auth';

export default async function Page() {
  const session = await requireSession();
  const orders = await getOrders(session.userId);
  return <OrderList orders={orders} />;
}
```

```ts
// src/app/dashboard/actions.ts
'use server';
import { z } from 'zod';
const Input = z.object({ title: z.string().min(1).max(120) });

export async function createOrder(formData: FormData) {
  const session = await requireSession();
  const parsed = Input.safeParse(Object.fromEntries(formData));
  if (!parsed.success) return { error: 'Ungültige Eingabe' };
  await insertOrder(session.userId, parsed.data);
  revalidatePath('/dashboard');
}
```

## Datenhaltung

- Relationale Datenbank über Prisma oder Drizzle; Migrationen versioniert im Repo.
- Datenbank-Client als Singleton, sonst erschöpft der Dev-Server mit Hot Reload die Verbindungen.
- **Caching** bewusst wählen: Das Verhalten von `fetch`-Caching, Datencache und statischem Rendering unterscheidet sich zwischen Next-Versionen. Pro Seite festlegen, ob sie statisch, zeitgesteuert revalidiert (`revalidate`) oder dynamisch ist, und die Dokumentation der eingesetzten Version prüfen.
- Nach Mutationen gezielt `revalidatePath` oder `revalidateTag` aufrufen.
- Seiten, die Cookies, Header oder Suchparameter lesen, sind dynamisch und werden nicht statisch erzeugt.
- Hochgeladene Dateien nicht ins Image und nicht ins `public/` zur Laufzeit schreiben; auf ein Volume oder Objektspeicher.
- Mehrere Container: der Standard-Cache liegt im Dateisystem des Containers; bei Skalierung einen gemeinsamen Cache-Handler einsetzen.

## Fehlerbehandlung und Logging

- `error.tsx` fängt Render-Fehler je Routensegment, `not-found.tsx` und `notFound()` behandeln fehlende Ressourcen, `global-error.tsx` die Wurzel.
- Erwartbare Fehler in Server Actions als Rückgabewert (`{ error }`), unerwartete werfen.
- Route Handlers geben passende Statuscodes und JSON-Fehler zurück.
- Fehlermeldungen an den Browser enthalten keine internen Details; Produktionsbuilds blenden Server-Fehlertexte aus.
- Logging strukturiert auf stdout (z. B. mit pino), damit Docker es sammelt; `console.log` nicht flächendeckend streuen.
- Healthcheck-Route `/api/health` ohne Datenbankzugriff, bei Bedarf eine zweite mit Prüfung.

## Tests

- **Vitest** für reine Funktionen: Datenschicht-Mapping, Validierungsschemas, Formatierer.
- Server Components lassen sich schlecht per Komponententest prüfen; Logik deshalb in testbare Funktionen auslagern.
- **Playwright** für die wichtigen Abläufe: Login, Formular absenden, Fehlerfall.
- Route Handlers direkt mit Request-Objekten aufrufen und Antwort prüfen.
- Typprüfung (`tsc --noEmit`) und Lint laufen in der CI vor dem Build.

## Sicherheit

- Server Actions sind öffentlich erreichbare Endpunkte: **jede** Action prüft Session, Berechtigung und Eingabe, auch wenn das Formular nur für Angemeldete sichtbar ist.
- Nur Variablen mit Präfix `NEXT_PUBLIC_` gelangen in den Browser; Geheimnisse nie so benennen.
- Daten an Client Components als Props sind für den Nutzer sichtbar: nur das übergeben, was angezeigt wird.
- Middleware allein ist keine Autorisierung; Rechte zusätzlich in der Datenschicht prüfen.
- Sicherheits-Header (CSP, `X-Content-Type-Options`, `Referrer-Policy`) in `next.config.ts` setzen.
- Webhooks mit Signatur prüfen; Raw-Body vor dem Parsen verwenden.
- Cookies: `httpOnly`, `secure`, `sameSite`.
- Abhängigkeiten per `npm audit` bzw. Äquivalent prüfen.

## Konfiguration und Geheimnisse

- Umgebungsvariablen über `.env`-Dateien lokal und Compose-Umgebung auf dem Server. `.env*` nie ins Repository, nur `.env.example` mit Platzhaltern.
- `src/lib/env.ts` validiert beim Start mit Zod und bricht bei fehlenden Werten ab.
- `NEXT_PUBLIC_*` werden beim **Build** eingebettet; Änderungen erfordern einen neuen Build, nicht nur einen Neustart.
- Serverseitige Variablen werden zur Laufzeit gelesen. Geheimnisse stammen aus einer zentralen Secret-Verwaltung.

## Deploy

Platzhalter in spitzen Klammern (`<STACK>`, `<auth-middleware>`, `<https-redirect>`, `meine-org/...`, `*.example.org`) sind durch die eigene Umgebung zu ersetzen. Die Beispiele gehen von Docker, Traefik als Reverse Proxy und einem externen Docker-Netzwerk `web` aus; andere Proxys und Orchestrierungen funktionieren sinngemäß genauso.

Muster: ein Docker-Container im Netzwerk `web`, Traefik routet über Labels, Dienst in der zentralen Compose-Datei unter `<STACK>`.

- **Next-Konfiguration**: `output: 'standalone'` erzeugt einen eigenständigen Server mit nur den benötigten Abhängigkeiten.
- **Dockerfile** mehrstufig: Stufe `deps` (Lockfile-Installation), Stufe `build` (`next build`), Laufzeitstufe auf schlankem Node-Image. Kopiert werden `.next/standalone`, `.next/static` und `public`. Start mit `node server.js`, Benutzer ohne Root-Rechte.
- **Umgebung**: `PORT=3000`, `HOSTNAME=0.0.0.0`, `TZ=Europe/Berlin`.
- **Labels** (interne Werkzeuge ergänzen `traefik.http.routers.meineapp.middlewares=<auth-middleware>@docker`):

```
networks: [web]
labels:
  - "traefik.enable=true"
  - "traefik.http.services.meineapp.loadbalancer.server.port=3000"
  - "traefik.http.routers.meineapp.rule=Host(`meineapp.example.org`)"
  - "traefik.http.routers.meineapp.entrypoints=websecure"
  - "traefik.http.routers.meineapp.tls.certresolver=le"
  - "traefik.http.routers.meineapp-http.rule=Host(`meineapp.example.org`)"
  - "traefik.http.routers.meineapp-http.entrypoints=web"
  - "traefik.http.routers.meineapp-http.middlewares=<https-redirect>@file"
```

- **Healthcheck**: HTTP-Aufruf von `/api/health` im Container.
- **Volumes**: nur für Uploads oder Cache nötig; Code und `.next` sind im Image.
- **Release**: Image neu bauen, Container neu erstellen, Migrationen als eigener einmaliger Schritt; `restart: unless-stopped`.

## Typische Fehler

- `'use client'` zu hoch im Baum: ganze Seiten werden zu Client Components, das Bundle wächst.
- Geheimnis oder Datenbankobjekt als Prop an eine Client Component übergeben.
- Server Action ohne Berechtigungsprüfung, weil die Oberfläche "es schon verhindert".
- Unklare Cache-Erwartung: veraltete Daten, weil Revalidierung fehlt, oder dauernd dynamische Seiten durch ungewolltes Lesen von Cookies.
- `NEXT_PUBLIC_*` nach dem Build ändern und wundern, dass nichts passiert.
- `public/` und `.next/static` beim Standalone-Image nicht mitkopiert: fehlende Bilder und Assets.
- Server lauscht nur auf localhost im Container, Traefik erreicht ihn nicht (`HOSTNAME` fehlt).
- Datenbank-Client pro Request neu erzeugt.
- Middleware mit Datenbankzugriff oder Node-only-Bibliotheken.
- Uploads ins Containerdateisystem geschrieben und beim Neustart verloren.
- Hinter Traefik falsche Basis-URL in Absolute-URL-Logik.

## Checkliste

- Server Components als Standard, `'use client'` nur an Blättern
- Datenbankzugriff nur in der Datenschicht, mit `server-only` geschützt
- Jede Server Action validiert Eingabe und prüft Session und Recht
- Caching pro Seite bewusst entschieden und für die eingesetzte Version geprüft
- Umgebungsvariablen mit Zod validiert, `.env.example` vorhanden
- `output: 'standalone'`, mehrstufiges Dockerfile, Nicht-Root-Benutzer
- `static` und `public` im Image enthalten
- `HOSTNAME=0.0.0.0`, Port in Traefik-Label passt
- Healthcheck-Route vorhanden
- Traefik-Labels, Netzwerk `web`, ggf. Auth-Middleware
- Uploads auf Volume oder Objektspeicher
- `tsc`, Lint und Tests in der CI vor dem Build
