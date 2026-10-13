# Astro statische Seite

## Kurzbeschreibung

Eine inhaltsgetriebene Website mit Astro, die zur Build-Zeit zu reinem HTML, CSS und wenig JavaScript gerendert wird. Inhalte liegen als Markdown, MDX oder Daten in Content Collections mit Schema. Interaktive Teile sind Islands: einzelne Komponenten, die gezielt im Browser hydriert werden. Das Ergebnis ist ein Ordner `dist/` mit statischen Dateien, den ein nginx-, Caddy- oder Apache-Container hinter Traefik ausliefert.

## Passt für / passt nicht für

Passt für Firmenseiten, Landingpages, Blogs, Dokumentation und Portfolios mit überwiegend festem Inhalt, guten Ladezeiten und SEO-Anspruch, auch mehrsprachig.

Passt nicht für Anwendungen mit Login, nutzerspezifischen Daten und vielen Schreibzugriffen (dann Next.js oder ein Framework mit Backend), für Seiten, die sich sekündlich ändern, und für Projekte, bei denen Redakteure ohne Build-Prozess sofort live publizieren müssen.

## Sprache und Stack

- **TypeScript** im strikten Modus (`astro/tsconfigs/strict`): typisierte Props und Collections.
- **Astro**, aktuelle stabile Version: statischer Build als Standard, wenig JavaScript im Browser.
- **Node.js**, aktuelle LTS, nur zur Build-Zeit.
- **Content Collections** mit Zod-Schema: geprüfte Inhalte, typsichere Abfragen.
- **Markdown/MDX** für Texte; MDX nur, wo Komponenten im Text nötig sind.
- **Island-Frameworks** (Preact, Svelte oder React) nur bei echtem Bedarf an Interaktivität.
- **Sitemap-Integration** (`@astrojs/sitemap`) und Bildoptimierung über `astro:assets`.
- **CSS**: scoped Styles in `.astro`-Dateien oder Tailwind.
- **Auslieferung**: nginx oder Caddy im Container, alternativ Apache.

## Ordnerstruktur

```
projekt/
├── src/
│   ├── content/                 # Content Collections
│   │   ├── blog/                # Beiträge als .md/.mdx
│   │   └── seiten/              # sonstige Seiteninhalte
│   ├── content.config.ts        # Collections mit Zod-Schema
│   ├── pages/                   # Dateibasiertes Routing
│   │   ├── index.astro          # Startseite
│   │   ├── [lang]/              # Sprachvarianten (de, en)
│   │   ├── blog/[...slug].astro # Detailseiten aus der Collection
│   │   └── 404.astro            # Fehlerseite
│   ├── layouts/                 # Seitenrahmen mit Head, SEO, Navigation
│   ├── components/              # .astro-Komponenten, ohne Client-JS
│   │   └── islands/             # interaktive Komponenten mit client:-Direktive
│   ├── i18n/                    # Übersetzungstexte und Hilfsfunktionen
│   ├── assets/                  # Bilder, die optimiert werden sollen
│   └── styles/                  # globale Styles, Variablen
├── public/                      # unveränderte Dateien: robots.txt, Favicons, Schriften
├── astro.config.mjs             # site, i18n, Integrationen, output
├── nginx.conf                   # Auslieferung: Cache-Header, 404, Weiterleitungen
├── .env.example                 # Platzhalter
└── Dockerfile                   # mehrstufig: Build, dann nginx/Caddy
```

## Schichten und Verantwortlichkeiten

- **Content**: Texte und Daten in `src/content`, vom Schema geprüft. Ein Build mit ungültigem Frontmatter schlägt fehl, statt fehlerhafte Seiten zu erzeugen.
- **Pages**: Routen und Seitenaufbau. Laden Inhalte per `getCollection()` und reichen sie an Layouts und Komponenten weiter.
- **Layouts**: gemeinsamer Rahmen mit Head, Meta-Tags, Navigation und Footer.
- **Komponenten**: reine `.astro`-Komponenten ohne Browser-JavaScript, Props typisiert.
- **Islands**: nur für Interaktion (Formular, Filter, Slider). Hydrierung gezielt mit `client:visible`, `client:idle` oder `client:load`.
- **Build**: erzeugt `dist/`; danach existiert keine Laufzeitlogik mehr.
- **Webserver**: liefert Dateien aus, setzt Cache-Header und Weiterleitungen.

## Namens- und Methodenkonventionen

- Komponenten und Layouts PascalCase (`HeroSection.astro`), Seiten und Content-Dateien kleingeschrieben mit Bindestrich (`ueber-uns.astro`, `mein-beitrag.md`).
- Collections im Singular oder klaren Plural, einheitlich pro Projekt.
- Frontmatter-Felder camelCase, Datum als `pubDate`.

```ts
// src/content.config.ts
import { defineCollection, z } from 'astro:content';
import { glob } from 'astro/loaders';

const blog = defineCollection({
  loader: glob({ pattern: '**/*.md', base: './src/content/blog' }),
  schema: z.object({
    title: z.string(),
    description: z.string().max(160),
    pubDate: z.date(),
    draft: z.boolean().default(false),
  }),
});
export const collections = { blog };
```

```astro
---
import { getCollection } from 'astro:content';
const posts = (await getCollection('blog', (p) => !p.data.draft))
  .sort((a, b) => b.data.pubDate.valueOf() - a.data.pubDate.valueOf());
---
<ul>{posts.map((p) => <li><a href={`/blog/${p.id}/`}>{p.data.title}</a></li>)}</ul>
```

## Datenhaltung

- Es gibt zur Laufzeit keine Datenbank. Inhalte stammen aus Dateien im Repo oder werden beim Build von einer API geholt.
- Externe Daten (Headless-CMS, API) nur beim Build abrufen; Änderungen dort erfordern einen neuen Build, etwa per Webhook.
- Bilder aus `src/assets` über `<Image />` oder `<Picture />` einbinden: Größen, moderne Formate und Abmessungen entstehen beim Build. Bilder in `public/` werden nicht optimiert.
- Formulare brauchen einen externen Endpunkt oder einen kleinen separaten Dienst; die statische Seite selbst speichert nichts.
- Optionaler Server-Modus (SSR mit Adapter) ist ein anderer Aufbau und hier nicht gemeint.

## Fehlerbehandlung und Logging

- Fehler fallen früh im Build auf: Schemaverletzungen, fehlende Bilder, TypeScript-Fehler. `astro check` in der CI ausführen.
- `404.astro` liefert die Fehlerseite; der Webserver verweist darauf.
- Im Betrieb loggt der Webserver Zugriffe und Fehler nach stdout und stderr, damit Docker sie sammelt.
- Islands behandeln Fehler im Browser selbst (Fallback-Anzeige); kein stilles Schlucken.
- Defekte Links vor dem Release mit einem Link-Checker über `dist/` prüfen.

## Tests

- **Build als Test**: `astro build` und `astro check` müssen fehlerfrei laufen.
- Schemas der Collections sind der wichtigste automatische Inhaltstest.
- Logik in Hilfsfunktionen (Übersetzung, Datum, Sortierung) mit Vitest prüfen.
- Interaktive Islands mit Komponententests oder Playwright.
- Stichproben auf `dist/`: Sitemap vorhanden, `lang`-Attribut, Canonical-Links, keine `noindex`-Reste.
- Lighthouse oder ähnliche Messung für Ladezeit, Barrierefreiheit und SEO.

## Sicherheit

- Statische Auslieferung hat kaum Angriffsfläche; der Webserver läuft ohne Schreibrechte auf die Inhalte.
- Sicherheits-Header im Webserver setzen: `Content-Security-Policy`, `X-Content-Type-Options`, `Referrer-Policy`.
- Keine Geheimnisse in Quelltext oder `PUBLIC_*`-Variablen: Alles, was in den Build eingebettet wird, ist öffentlich.
- Inhalte aus fremden Quellen (CMS, Nutzerbeiträge) nicht ungeprüft mit `set:html` einsetzen.
- Externe Skripte (Analytics, Karten) nur mit Einwilligung laden und bevorzugt selbst hosten.
- Formular-Endpunkte außerhalb der Seite selbst absichern (Validierung, Rate Limit, Spam-Schutz).

## Konfiguration und Geheimnisse

- `astro.config.mjs` enthält `site` (öffentliche Basis-URL, nötig für Sitemap und Canonical), `i18n` und Integrationen.
- Umgebungsvariablen nur für Build-Parameter; mit `PUBLIC_` beginnende Werte stehen im Browser. `.env` nie ins Repository, `.env.example` mit Platzhaltern.
- Zugangsdaten für CMS oder API, die der Build braucht, stammen aus einer zentralen Secret-Verwaltung und werden als Build-Argument oder Umgebung der CI übergeben, nicht ins Image geschrieben.

## Deploy

Platzhalter in spitzen Klammern (`<STACK>`, `<auth-middleware>`, `<https-redirect>`, `meine-org/...`, `*.example.org`) sind durch die eigene Umgebung zu ersetzen. Die Beispiele gehen von Docker, Traefik als Reverse Proxy und einem externen Docker-Netzwerk `web` aus; andere Proxys und Orchestrierungen funktionieren sinngemäß genauso.

Muster: ein Docker-Container im Netzwerk `web`, Traefik routet über Labels, Dienst in der zentralen Compose-Datei unter `<STACK>`.

- **Dockerfile** mehrstufig: Stufe 1 Node (`npm ci`, `astro build`), Stufe 2 schlankes nginx- oder Caddy-Image mit `dist/` unter dem Document Root und eigener Konfiguration. Alternativ liegt `dist/` als schreibgeschütztes Volume (`:ro`) in einem Apache-Container wie bei PHP-Seiten.
- **Webserver-Konfiguration**: lange Cache-Dauer für gehashte Dateien unter `/_astro/`, kurze für HTML, `try_files` mit Verzeichnis-Index, eigene 404-Seite, gzip bzw. Brotli.
- **Labels** (interne Seiten ergänzen `traefik.http.routers.meineseite.middlewares=<auth-middleware>@docker`):

```
networks: [web]
labels:
  - "traefik.enable=true"
  - "traefik.http.services.meineseite.loadbalancer.server.port=80"
  - "traefik.http.routers.meineseite.rule=Host(`meineseite.example.org`)"
  - "traefik.http.routers.meineseite.entrypoints=websecure"
  - "traefik.http.routers.meineseite.tls.certresolver=le"
  - "traefik.http.routers.meineseite-http.rule=Host(`meineseite.example.org`)"
  - "traefik.http.routers.meineseite-http.entrypoints=web"
  - "traefik.http.routers.meineseite-http.middlewares=<https-redirect>@file"
```

- **Healthcheck**: einfacher HTTP-Aufruf der Startseite im Container.
- **Release**: neues Image bauen, Container neu erstellen; Rollback über das vorige Image. Es gibt keinen Zustand und keine Migrationen.
- `restart: unless-stopped`.

## Typische Fehler

- `site` in `astro.config.mjs` fehlt oder ist falsch: Sitemap und Canonical-Links zeigen auf falsche Adressen.
- Bilder in `public/` statt `src/assets`: keine Optimierung, große Dateien.
- Zu viele Islands oder `client:load` überall: das JavaScript-Bundle wächst, der Vorteil von Astro geht verloren.
- Trailing-Slash-Einstellung passt nicht zur Webserver-Konfiguration: Weiterleitungsschleifen oder 404.
- Mehrsprachigkeit ohne `hreflang` und ohne Sprachumschalter, der auf die gleiche Seite der anderen Sprache verweist.
- Entwurf (`draft`) landet im Build, weil der Filter fehlt.
- Inhalte im CMS geändert, aber kein Rebuild ausgelöst.
- Geheimnisse in `PUBLIC_*`-Variablen.
- Falscher Cache auf HTML: Änderungen erscheinen erst verzögert.
- 404-Seite nicht im Webserver hinterlegt, Standardfehlerseite erscheint.

## Checkliste

- `site` gesetzt, Sitemap und `robots.txt` vorhanden
- Jede Seite mit eindeutigem Titel, Beschreibung, Canonical und Open-Graph-Daten
- Bilder über `astro:assets`, mit Breite, Höhe und `alt`
- Collections mit Zod-Schema, Entwürfe gefiltert
- Islands nur wo nötig, mit passender `client:`-Direktive
- Mehrsprachigkeit mit `hreflang` und gespiegelten Routen
- `astro check` und `astro build` in der CI grün
- Mehrstufiges Dockerfile, Webserver mit Cache-Regeln und 404-Seite
- Sicherheits-Header gesetzt
- Traefik-Labels, Netzwerk `web`, ggf. Auth-Middleware
- Healthcheck definiert, Rollback über vorheriges Image möglich
- `.env.example` vorhanden, keine Geheimnisse im Build
