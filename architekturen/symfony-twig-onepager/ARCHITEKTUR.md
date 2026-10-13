# Firmenwebsite mit Symfony, Vue-Build und Video-Hintergruenden (Release-Layout)

## Kurzbeschreibung

Die oeffentliche Firmenwebsite ist **keine rein statische Seite**, sondern eine kleine Symfony-Anwendung mit Twig-Templates, die eine einzige Seite (One-Pager) mit Portfolio, Produkten und Kontakt ausliefert. Inhalte (Ueber mich, Skills, Projekte, Produkte, Impressum) kommen zur Laufzeit aus einer internen API und werden gecacht. Das Frontend ist ein per Webpack Encore gebauter Mix aus Vue 3, Bootstrap, GSAP/Three.js und eigenem CSS. Die filmische Optik entsteht durch Hintergrundvideos, Scroll-Animationen und Partikel.

Wichtig fuer das Verstaendnis: Das Verzeichnis folgt einem Capistrano-artigen Layout (`releases/`, `shared/`, `current`). Es gibt zwei Betriebsarten: `current` als Symlink auf ein Release (empfohlen) oder, einfacher, `current/` als normales Verzeichnis mit Git-Checkout, das per `git pull` und Build aktualisiert wird.

## Passt für / passt nicht für

Passt fuer:
- Eine repraesentative Ein-Seiten-Website mit wenigen Routen (Startseite, Impressum, Kontakt, Sitemap), die Inhalte aus einer API zieht.
- Seiten mit starkem visuellem Anspruch (Video, Scroll-Animation), bei denen SEO trotzdem serverseitig gerendert sein muss.
- Mehrsprachige Seiten (Deutsch/Englisch) mit Cookie-basierter Sprachwahl.

Passt nicht fuer:
- Reine Visitenkarten ohne Inhaltsquelle: dann reicht echtes statisches HTML aus einem Generator, ohne PHP.
- Seiten mit hohem Besucherverkehr ohne vorgeschaltetes Caching: jede Anfrage durchlaeuft PHP.
- Redaktionell gepflegte Seiten ohne API: ein CMS oder Markdown-Build ist einfacher.

## Sprache und Stack

- **PHP 8.4+ (Laufzeit PHP 8.5 im Container) mit aktuellem Symfony**: Routing, Twig, Cache, Validator, Mailer. Server-Rendering liefert vollstaendiges HTML fuer Suchmaschinen.
- **Twig** fuer Layouts und Seiten; Ausgabe von Strukturdaten (JSON-LD) mit `JSON_HEX_TAG`.
- **Webpack Encore 5** (aktuelle Node-LTS-Version) mit Babel/core-js: gehashte Dateinamen, `manifest.json` und `entrypoints.json`; zwei Einstiege (`app`, `portfolio`).
- **Vue 3** (ohne Laufzeit-Compiler) nur fuer Formulare und Verwaltungsteile; **Bootstrap 5** fuer Raster; **Axios** fuer API-Aufrufe im Browser.
- **GSAP ScrollTrigger und Three.js** fuer die Inszenierung; Three.js wird erst nach dem Laden per `import()` nachgeladen.
- **Symfony HttpClient** fuer die Inhalts-API (JWT-Anmeldung mit Ablaufpruefung), **Symfony Cache** gegen wiederholte API-Aufrufe.
- **DeepL-Client** fuer Uebersetzungen mit Cache.
- **Apache** im Container `php-app` (Host-Netzwerk) mit `FallbackResource /index.php`; TLS und Weiterleitung uebernimmt Traefik.

## Ordnerstruktur

```
<PROJEKTE>/example.org/
├── current/              # aktive Version (Symlink auf ein Release oder Git-Checkout)
│   ├── public/           # DocumentRoot: index.php, build/, videos/, images/, robots.txt
│   │   ├── build/        # Encore-Ausgabe mit Hash im Namen, manifest.json
│   │   ├── videos/       # MP4 + WebP-Poster je Abschnitt (hero, flug, feuer, ruhe)
│   │   └── images/       # WebP-Bilder, og-image.jpg, Icons
│   ├── src/              # Controller, Service (ApiService, Zaehler), Twig-Erweiterungen
│   ├── templates/        # base.html.twig, default/index.html.twig, sitemap.xml.twig
│   ├── assets/           # Quellcode Frontend (portfolio/: Effekte wie reveal.js, three/)
│   ├── config/           # Symfony-Konfiguration
│   ├── progress/         # Notizen zur Umsetzung (STATUS.md, Plan, offene Punkte)
│   └── .env              # vorhanden, Inhalt nicht im Repo-Doku
├── releases/             # Release-Verzeichnisse
├── shared/               # .env.local, var/, public/uploads: Ziele fuer Symlinks pro Release
├── deploy.sh             # Capistrano-artige Vorlage (clone, composer, cache, Symlink-Swap)
├── backups/  logs/  ssl/ # nicht Teil der Architektur
└── *.mp4                 # Rohvideos (Quellmaterial, nicht ausgeliefert)
```

## Schichten und Verantwortlichkeiten

- **Controller** (`DefaultController`, `KontaktController`, `ImpressumController`): duenn, holen Daten ueber den Service, waehlen Locale aus Cookie (`DE_de` als Standard), rendern Twig.
- **Service `ApiService`**: einziger Zugriff auf die Inhalts-API (Login per JWT, Wiederverwendung bis Ablauf, Sortierung, Filter). Controller kennen keine URLs.
- **Twig-Erweiterungen**: Uebersetzung (`translate('key')`) und globale Werte.
- **EventListener**: Besucherzaehler pro Hauptanfrage.
- **Frontend-Module**: je Effekt eine Datei (`reveal.js`, `parallax.js`, `three/partikel.js`), Einstieg `portfolio/main.js`.

## Namens- und Methodenkonventionen

- PHP: PSR-12, Klassen `UpperCamelCase`, Routen per Attribut, Namen mit Praefix `app_`.
- Frontend: Dateien in `camelCase.js`, CSS-Klassen kebab-case (`hero-video`, `lazy-video`), Design-Variablen in `tokens.css`.
- Medien: Video und Poster mit gleichem Basisnamen (`flug.mp4`, `flug-poster.webp`).

```php
#[Route('/sitemap.xml', name: 'app_sitemap')]
public function sitemap(): Response
{
    $response = $this->render('default/sitemap.xml.twig', [...]);
    $response->headers->set('Content-Type', 'application/xml');
    return $response;
}
```

```
<video class="lazy-video" data-src="/videos/flug.mp4"
       poster="/videos/flug-poster.webp" muted loop playsinline preload="none"></video>
```

## Datenhaltung

- Keine eigene Datenbank in der Website: Inhalte, Kontaktnachrichten und Besucherzaehler liegen in der internen API.
- Lokal nur Symfony-Cache und Logs unter `var/` (im Release-Layout nach `shared/var` verlinkt) und Uploads unter `public/uploads`.
- Medien (Video, Bilder) liegen als Dateien in `public/` und sind Teil des Deployments.

## Fehlerbehandlung und Logging

- Monolog schreibt nach `var/log`; in Produktion muss `APP_ENV=prod` gesetzt sein.
- Fehlt ein API-Wert, liefert der Service ein leeres Array; die Seite rendert ohne den Abschnitt statt mit Fehlerseite.
- Der Besucherzaehler darf die Seite nie blockieren.
- Bekannte, harmlose Konsolenmeldungen: 404 fuer fehlende Projektbilder in `uploads/`; solche Fehler fallen im Browser-Test auf und sollten bereinigt werden.
- Apache-Zugriffslog laeuft im Container nach stdout.

## Tests

- PHPUnit ist konfiguriert (`phpunit.xml.dist`, `tests/`), die Abdeckung ist gering.
- Frontend-Pruefung per Browser (Playwright/Headless): Konsole ohne Fehler, Dark- und Light-Theme, Vollseiten-Scroll, Handy 390 Pixel.
- Build-Pruefung: `npm run build` muss ohne Fehler laufen (bei Konflikten transitiver Abhaengigkeiten Versionen per `overrides` pinnen).
- Lighthouse/Core Web Vitals nach Aenderungen an Videos oder Scripts.

## Sicherheit

- Geheimnisse (API-Zugang, DeepL, `APP_SECRET`) nur in `.env.local`/Umgebung, nie im Repo.
- `.htaccess`-Regel und Container-Apache sperren `.env`, `.git`, `.ht*`; DocumentRoot ist `public/`, nie das Projektverzeichnis.
- JSON-LD mit `JSON_HEX_TAG` ausgeben, Twig-Autoescaping nicht umgehen (`|raw` nur fuer kontrolliertes JSON).
- Kontaktformulare immer mit CSRF-Token, Validator-Regeln und Rate-Limit absichern, bevor Daten an eine API weitergereicht werden.
- Webhooks immer mit HMAC-Signaturpruefung absichern; Deploy-Webhooks besser gar nicht oeffentlich ausliefern.
- Schreibrechte nur auf `var/` und `uploads/`, Code gehoert `www-data` mit Modus 644/755.

## Konfiguration und Geheimnisse

- `.env` (Standardwerte) ist im Checkout vorhanden; echte Werte in `shared/.env.local`, das per Symlink eingehaengt wird.
- Neue Variablen immer zusaetzlich als Platzhalter in `.env.example` dokumentieren.
- Zugangsdaten gehoeren in die Secret-Verwaltung und werden nur beim Einrichten uebertragen.

## Deploy

Platzhalter in spitzen Klammern (`<STACK>`, `<auth-middleware>`, `<https-redirect>`, `meine-org/...`, `*.example.org`) sind durch die eigene Umgebung zu ersetzen. Die Beispiele gehen von Docker, Traefik als Reverse Proxy und einem externen Docker-Netzwerk `web` aus; andere Proxys und Orchestrierungen funktionieren sinngemäß genauso.

**Klassischer Ablauf:** Die Website laeuft klassisch im Container `php-app` (Host-Netzwerk, Apache auf einem internen Port); ein Vhost `example.org.conf` setzt `DocumentRoot .../current/public`, `FallbackResource /index.php` und leitet `www.` per 301 um. Traefik nimmt TLS an und reicht weiter. Der gebaute Frontend-Stand (`public/build/`) und die Videos sind **im Git-Repository eingecheckt**: gebaut wird lokal bzw. in der Entwicklung, auf dem Server genuegt `git pull` in `current/`, bei Bedarf `composer install --no-dev -o`, `APP_ENV=prod php bin/console cache:clear` und `apachectl -k graceful` im Container. Das ist nicht atomar: waehrend des Pulls ist die Seite kurz inkonsistent.

**Vorbereitetes Release-Layout** (`deploy.sh`, noch nicht aktiv; Repository-URL ist ein Platzhalter):
1. `git clone --depth=1` nach `releases/<Zeitstempel>`.
2. `shared/.env.local`, `shared/var`, `shared/public/uploads` per Symlink einhaengen.
3. `composer install --no-dev --optimize-autoloader`, Cache warmup.
4. Rechte setzen, **`ln -sfn releases/<ts> current`** (atomarer Wechsel), `apachectl -k graceful`.
5. Alte Releases entfernen (die letzten 5 bleiben). Migrationen bewusst auskommentiert.
Hinweis: Das Skript baut das Frontend nicht; das passt nur, solange `public/build/` im Repo liegt. Vor Aktivierung muss `current/` vom Verzeichnis zum Symlink werden.

**Ziel (Docker + Traefik):** eigener Dienst im Stack, Image mit gebautem Frontend (Multi-Stage: Node-Build, dann PHP-Apache; `public/build/` dann nicht mehr im Repo), Labels fuer Router und `certresolver=le`, Healthcheck auf `/`, `.env` per Compose-Datei; Releases werden Image-Tags, Rollback = vorheriger Tag. Siehe Verbesserungen.

## Typische Fehler

- **`current` ist ein Verzeichnis**: `ln -sfn` darauf legt den Link in das Verzeichnis statt es zu ersetzen. Erst umbenennen, dann verlinken.
- **Build vergessen einzuchecken**: `public/build/` liegt im Repo; fehlen die neuen Hash-Dateien, verweist die Seite auf 404-Dateien. Gleichzeitig blaeht das Repo mit Videos und Bundles auf.
- **Videos zu gross**: ein einziges Hero-Video blockiert mobil das Laden. Loesung: kleineres `hero-mobil.mp4` per `<source media="(max-width: 768px)">`, restliche Videos `preload="none"` und per IntersectionObserver nachgeladen.
- **iOS-Autoplay**: Videos muessen per Code stumm gesetzt werden (`muted`, `playsinline`) und starten teils erst bei der ersten Beruehrung.
- **Three.js im Hauptbundle**: verzoegert den First Paint; per `import()` nach dem Laden einbinden.
- **Rohvideos**: Quellvideos (oft Dutzende MB) gehoeren nicht in `public/` und nicht ins Repo; nicht aus Versehen ausliefern.
- **Node-Versionskonflikte** bei transitiven Abhaengigkeiten: Version pinnen.
- **Doppelte Deploy-Skripte** widersprechen sich schnell: genau ein Deploy-Skript pflegen.
- **Leeres `shared/`**: Eine leere `.env.local` verdeckt per Symlink die echte Konfiguration; vor dem Umschalten pruefen.

### Verbesserungen für neue Projekte

- Wirklich statisch, wenn die Inhalte sich selten aendern: Build-Zeit-Rendering, Auslieferung per Nginx/Caddy-Container, keine PHP-Laufzeit.
- Ein Container je Release (Image-Tag), gebautes Frontend im Image; Rollback per Tag statt Symlink.
- Videos mit ffmpeg in mehreren Aufloesungen (H.264 und AV1/WebM), `Range`-Requests und Cache-Header (`immutable`), Poster als WebP; Rohmaterial ausserhalb des Repos.
- Seitenweites HTTP-Caching (Reverse Proxy oder `Cache-Control` fuer die Startseite), Gzip/Brotli.
- Sitemap, Canonical, hreflang, OG-Bilder und JSON-LD in einer Testliste mit Lighthouse-Grenzwerten.
- Einheitliches Deploy-Skript im Repo, das Build, Migrationen und Healthcheck umfasst.
- `.env.example` und Secrets nur ueber Compose.

## Checkliste

- DocumentRoot ist `public/`, Fallback auf `index.php`.
- `APP_ENV=prod`, Cache nach jedem Deploy geleert.
- Frontend-Build mit gehashten Dateien Teil des Deployments.
- `current` ist ein Symlink auf ein Release, nicht ein Verzeichnis.
- `shared/` enthaelt `.env.local`, `var/`, Uploads.
- Videos komprimiert, mobile Variante, Poster, `preload="none"` ausser Hero.
- `prefers-reduced-motion` respektiert, Videos stumm.
- Sitemap, `robots.txt`, Meta-Description, OG-Bild, JSON-LD vorhanden.
- Bilder als WebP mit `loading="lazy"` und `alt`.
- Keine Geheimnisse im Repo, `.env.example` mit Platzhaltern.
- Healthcheck und Browser-Test (Konsole ohne Fehler, Handy 390 Pixel).
- Rollback-Weg getestet (alter Release oder Tag).
