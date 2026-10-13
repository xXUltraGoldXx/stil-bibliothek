# Symfony-API mit Vue-SPA

## Kurzbeschreibung

API-first in einem Repository: `api/` ist eine reine JSON-API (Symfony, API Platform, Doctrine, JWT), `frontend/` eine eigenständige Vue-3-SPA, gebaut mit Vite. Kein Twig für Fachseiten, keine Server-Session. Der Browser hält ein JWT im `localStorage` und schickt es als Bearer-Token mit.

Der Aufbau trägt Fachanwendungen wie Formular-Designer, Kalender oder PDF-Ausgabe und lässt sich mandantenfähig erweitern (Mandantentrennung, Rechtegruppen, Integrationstests); diese Erfahrungen sind unten eingearbeitet.

Der Webserver liefert unter `/` die statische SPA aus `frontend/dist`, unter `/api` das Symfony-`public/index.php`; alles Übrige fällt auf `index.html` zurück.

## Passt für / passt nicht für

Passt für:
- Interne Fachanwendungen mit Login, Rollen und vielen CRUD-Listen.
- Systeme, die später eine zweite Oberfläche (App, Integration) bekommen.
- Stark interaktive Oberflächen (Drag and Drop, Kalender-Grids).

Passt nicht für:
- Öffentliche Seiten mit SEO-Bedarf (die SPA liefert nur eine leere Hülle).
- Kleine Verwaltungen mit wenigen Formularen; Twig wäre einfacher.
- Sitzungen, die sofort widerrufbar sein müssen: ein JWT gilt bis zum Ablauf.

## Sprache und Stack

- **PHP 8.4+** (`composer.json`), im Container 8.5: Attribute statt Annotationen.
- **Symfony** (aktuelle Version): Framework, Security, Serializer, Validator.
- **API Platform 5.0**: CRUD, Pagination und Filter direkt aus Entity-Attributen, spart Controller.
- **Doctrine ORM 3.6 mit MySQL**: ein Server, je Projekt eigene Datenbank und eigener Benutzer.
- **LexikJWT 3.2**: JSON-Login, signierte Tokens. **NelmioCors** für die Freigabe der eigenen Domain. **dompdf 3.1** für PDF.
- **Vue 3.5, Vite 8, Pinia 3, vue-router 4, axios, vue-i18n 11**: Pinia hält Login und Benutzer, axios kapselt den Token, i18n liefert Deutsch und Englisch.
- Kein TypeScript, keine Komponentenbibliothek; Icons und Komponenten sind Eigenbau.

## Ordnerstruktur

```
projekt/
├── api/                      # Symfony-App (eigenes composer.json)
│   ├── config/packages/      # security, api_platform, doctrine, lexik_jwt, nelmio_cors
│   ├── config/routes.yaml    # nur api_login (POST, ohne Controller)
│   ├── config/jwt/           # Schlüsselpaar, nie im Repo
│   ├── migrations/           # Doctrine-Migrations
│   ├── public/index.php      # einziger Einstieg der API
│   ├── src/Entity/           # Entities mit #[ApiResource]
│   ├── src/Repository/       # je Entity ein Repository
│   ├── src/State/            # Processor und Provider
│   ├── src/Controller/       # Sonderfälle: /api/me, PDF
│   ├── src/Security/         # Voter, Rechtekatalog (bei Mandantenfähigkeit)
│   ├── tests/                # PHPUnit
│   └── .env.example          # Platzhalter
├── frontend/
│   ├── vite.config.js        # Vue-Plugin
│   └── src/
│       ├── main.js           # App, Pinia, Router, i18n
│       ├── api.js            # axios mit Token- und 401-Interceptor
│       ├── permissions.js    # Rechtekatalog (customers.manage ...)
│       ├── router/index.js   # Routen, Lazy-Loading, Guard
│       ├── stores/auth.js    # Token, Benutzer, can(...)
│       ├── views/            # eine Datei je Seite
│       ├── components/       # Shell, Formulare, Modals, Icons
│       ├── locales/          # de.json, en.json
│       └── assets/app.css    # Design-Tokens
├── scripts/                  # Betriebsskripte (Demo-Reset, Seed)
└── todo.md                   # Roadmap
```

## Schichten und Verantwortlichkeiten

- **Entity**: Datenmodell, Validierung, Serializer-Gruppen (`customer:read`, `customer:write`) und Zugriffsregeln je Operation im `#[ApiResource]`.
- **Processor**: setzt abgeleitete Felder vor dem Speichern (Ersteller, Passwort-Hash, Mandant) und reicht an den Standard-Persist-Processor weiter. **Provider** schränken Lesezugriffe ein.
- **Controller**: nur wo API Platform nicht passt: `/api/me`, Passwortwechsel, PDF.
- **Security**: Firewall `login` (json_login) und `api` (stateless, `jwt`); `access_control` verlangt für `/api` volle Authentifizierung außer Login und Doku.
- **Frontend**: `api.js` ist die einzige Stelle mit Token-Logik; bei 401 Token löschen und zum Login. Der Router-Guard lädt `/api/me` und sperrt Admin-Routen. `auth.can(...)` blendet Menüs aus, Administratoren dürfen alles.
- Rechte im Frontend sind Komfort, maßgeblich sind die Regeln an den Entities.

## Namens- und Methodenkonventionen

Englische Namen, Entity im Singular, Rechteschlüssel als `bereich.aktion`.

```php
#[ORM\Entity(repositoryClass: CustomerRepository::class)]
#[ApiResource(
    operations: [
        new GetCollection(),
        new Post(security: "is_granted('ROLE_ADMIN') or 'customers.manage' in user.getPermissions()"),
        new Delete(security: "is_granted('ROLE_ADMIN')"),
    ],
    normalizationContext: ['groups' => ['customer:read']],
    denormalizationContext: ['groups' => ['customer:write']],
)]
class Customer { /* Felder mit #[Groups] und #[Assert\NotBlank] */ }
```

Ein Processor folgt immer diesem Muster:

```php
public function process(mixed $data, Operation $operation, array $uriVariables = [], array $context = []): mixed
{
    // abgeleitete Felder setzen
    return $this->persistProcessor->process($data, $operation, $uriVariables, $context);
}
```

Frontend: `<Thema>View.vue`, `<Thema>Modal.vue`, `stores/<name>.js`. URLs deutsch (`/kunden`), Routennamen englisch. Texte nie fest im Template, sondern als i18n-Schlüssel. Die API antwortet mit `application/ld+json`, Listen stehen unter `hydra:member`.

## Datenhaltung

- MySQL, je Projekt eigene Datenbank und eigener Benutzer.
- Flexible Inhalte (Formularschema, ausgefüllte Daten, Rechteliste) als JSON-Spalten: kleines Modell, aber keine Abfragen auf Feldebene.
- Reservierte SQL-Wörter meiden (`schema` heißt in der Datenbank `field_schema`).
- Mehrere Firmen (Mandantenfähigkeit): Entity `Tenant`, jede Fachentity trägt `tenant`, Isolation über einen Doctrine-Filter aus dem angemeldeten Benutzer. Ein vergessenes `WHERE` darf nie Fremddaten zeigen.
- Regel: Schemaänderungen immer als Doctrine-Migration einchecken, nicht per `doctrine:schema:update` auf der Produktion.

## Fehlerbehandlung und Logging

- Validierung liefert 422 mit Feldliste, fehlendes Token 401, fehlendes Recht 403. Das Frontend behandelt nur 401 global.
- Eigene Controller werfen Symfony-HTTP-Exceptions statt selbstgebauter JSON-Fehler.
- Logging über Monolog. Regel: Passwortwechsel und andere sicherheitsrelevante Änderungen in ein unveränderliches Änderungsprotokoll (Audit-Log) schreiben.
- Ein 500 zeigt sich oft nur über den Webserver, während die Konsole grün ist (alter Cache).

## Tests

- Mindestens eine API-Matrix-Prüfung (Admin und eingeschränkter Benutzer) und Sichtabnahme; automatisierte Tests sind der Regelfall.
- PHPUnit mit Unit-Tests (Rechte, Verschlüsselung) und Integrationstests (Mandantentrennung, Endpunktabsicherung, Rechtegruppen). Der Nutzen liegt in den Integrationstests, weil Fehler an Zugriffsregeln entstehen. Aufruf: `cd api && vendor/bin/phpunit`.
- Frontend ohne Tests.

## Sicherheit

- Passwörter mit dem `auto`-Hasher, Hashing im Processor.
- JWT mit Schlüsselpaar und Passphrase, je Projekt eigene Schlüssel. Gegenprobe: Token eines Projekts muss am anderen 401 liefern.
- Token-Laufzeit Bundle-Standard (eine Stunde); ein Passwortwechsel entwertet alte Tokens nicht. Bei Bedarf Token-Version am Benutzer ergänzen.
- Das Token im `localStorage` ist bei XSS lesbar; keine ungeprüften HTML-Inhalte rendern.
- Zugriffsregeln an jede Entity-Operation, Löschen nur für Admin.
- CORS nur für die eigene Domain. Der Webserver sperrt `.env`, `.git`, `.ht`. Debug-Endpunkte aus Altsystemen wurden nicht übernommen.

## Konfiguration und Geheimnisse

- `api/.env` hält nur Voreinstellungen. Echte Werte stehen in `api/.env.local` auf dem Server und nie im Repo; `.gitignore` schließt `.env.*` (außer `.env.example`), `config/jwt/*.pem`, `vendor/`, `var/`, `node_modules/`, `dist/` aus.
- `.env.example` mit Platzhaltern:

```
APP_ENV=prod
APP_SECRET=hier-zufaelligen-wert-eintragen
DATABASE_URL="mysql://benutzer:passwort@dbhost:3306/datenbank?serverVersion=8.4"
CORS_ALLOW_ORIGIN='^https://beispiel\.example$'
JWT_SECRET_KEY=%kernel.project_dir%/config/jwt/private.pem
JWT_PUBLIC_KEY=%kernel.project_dir%/config/jwt/public.pem
JWT_PASSPHRASE=platzhalter
```

- Zugangsdaten gehören in die Secret-Verwaltung, nicht in Statusdateien. Jede Kopie (Demo, Variante) bekommt eigene Datenbank, `APP_SECRET` und JWT-Schlüssel.

## Deploy

Platzhalter in spitzen Klammern (`<STACK>`, `<auth-middleware>`, `<https-redirect>`, `meine-org/...`, `*.example.org`) sind durch die eigene Umgebung zu ersetzen. Die Beispiele gehen von Docker, Traefik als Reverse Proxy und einem externen Docker-Netzwerk `web` aus; andere Proxys und Orchestrierungen funktionieren sinngemäß genauso.

Unter `<STACK>` hat das Projekt keinen eigenen Container, sondern einen virtuellen Host im gemeinsamen Container `php-app` (Apache, PHP 8.5, Image `meine-org/php-app`). Der Code bleibt unter `<PROJEKTE>/<domain>` und wird per Bind-Mount eingehängt. Es gibt keine Releases und keinen Symlink-Wechsel: Deploy erfolgt direkt im Arbeitsverzeichnis. Die Datenbank läuft im Container `db` (MySQL 8.4).

Davor steht Traefik v3 (Netz `web`, Resolver `le`). Die Routen stehen in `traefik/dynamic/php-app.yml`: je Domain ein Router auf `websecure` mit `tls.certResolver: le` und einer auf `web` mit Middleware `nach-https`, beide zum Service `php-app`. Ein Auth-Proxy ist nicht vorgeschaltet, die App hat ihren Login; für Admin-Werkzeuge hängt `<auth-middleware>@docker` am Router. Der vHost liegt in `php-app/sites/<domain>.conf`:

```
<VirtualHost *:8081>
    ServerName portal.example
    DocumentRoot <PROJEKTE>/portal/frontend/dist
    <Directory <PROJEKTE>/portal/frontend/dist>
        FallbackResource /index.html
    </Directory>
    Alias /__api <PROJEKTE>/portal/api/public
    RewriteEngine On
    RewriteRule ^/api(/.*)?$ /__api/index.php [PT,L]
</VirtualHost>
```

Die Apache-Konfiguration des Containers reicht den Authorization-Header an PHP durch und übernimmt Client-IP und HTTPS aus den Forwarded-Headern; ohne den Header-Durchgriff ist jede API-Anfrage 401. OPcache prüft Zeitstempel alle zwei Sekunden. Einen Healthcheck pro Seite gibt es nicht; geprüft wird per Aufruf von `/` und `/api/me`.

```
API:  cd api && php bin/console cache:clear --env=prod && chown -R www-data:www-data var/
SPA:  cd frontend && npm run build && chown -R www-data:www-data dist/
```


## Typische Fehler

- **Falscher Cache-Besitzer**: `cache:clear` als root hinterlässt `var/` mit falschen Rechten, danach 500 nur über den Webserver. Besonders bei kopierten Demo-Instanzen.
- **Schema-Update legt Spalten nicht immer an**: Es kann vorkommen, dass eine Spalte (z. B. `tenant_id`) fehlt. Danach `DESCRIBE <tabelle>` prüfen und notfalls `ALTER TABLE`.
- **Reservierte MySQL-Wörter** als Feldnamen brechen das Schema.
- **Login-Route**: `json_login` braucht eine Route `api_login` (Pfad und POST) in `routes.yaml`, aber keinen Controller.
- **Authorization-Header fehlt**: ohne Durchreichung im Apache 401 überall.
- **Rechte nur im Frontend**: ein ausgeblendeter Menüpunkt schützt nichts. Mit einem eingeschränkten Testbenutzer gegenprüfen.
- **Mandant nicht gesetzt**: Processor, die den Standard-Persist umgehen, brauchen einen Listener. Der Mandantenfilter darf den User-Provider nicht filtern, sonst bricht der Login.
- **Demo-Kopie driftet**: Änderungen wandern nicht automatisch; `.env.local` der Demo behalten, Cache leeren.
- **Zugänge in Statusdateien**: Zugangsdaten gehören nie in Markdown- oder Statusdateien.

### Verbesserungen für neue Projekte

- Doctrine-Migrations von Anfang an erzeugen und committen, im Betrieb nur `migrations:migrate`.
- Release-Ordner mit Symlink-Wechsel statt Bauen im Produktionsverzeichnis.
- Eigener Compose-Ordner mit Traefik-Labels statt geteiltem `php-app`; Deploy und Rollback unabhängig von anderen Seiten.
- Integrationstests für Zugriffsregeln und eine kurze CI-Pipeline von Beginn an; Voter mit zentralem Rechtekatalog.
- TypeScript und Vitest im Frontend, einheitliches Fehlerformat der API.
- HttpOnly-Cookie oder Refresh-Token mit Widerruf statt `localStorage`; Audit-Log für Anmeldung und Passwortwechsel.

## Checkliste

- Repository mit `api/` und `frontend/`, `.gitignore` für Geheimnisse, `vendor`, `var`, `dist`.
- `.env.example` mit Platzhaltern, echte Werte nur in `.env.local` auf dem Server.
- Eigene Datenbank und eigener Benutzer, Migrationen committet.
- Eigenes JWT-Schlüsselpaar mit Passphrase, Gegenprobe gegen andere Projekte.
- Firewalls `login` und `api`, `access_control` für alles unter `/api`.
- Jede Entity-Operation mit eigener Zugriffsregel, Serializer-Gruppen getrennt für Lesen und Schreiben.
- Processor für Ersteller, Passwort-Hash und Mandant.
- Frontend: `api.js` mit Interceptoren, Router-Guard, Rechte-Helper, i18n-Schlüssel.
- vHost mit `FallbackResource`, `/api`-Rewrite; Traefik-Router mit `le` und `nach-https`.
- Nach dem Deploy: Cache leeren, Besitzer von `var/`, Spalten per `DESCRIBE`, Login und `/api/me` testen.
- Integrationstests für Rechte und Mandantentrennung.
