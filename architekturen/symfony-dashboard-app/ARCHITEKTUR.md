# Symfony-Dashboard (server-gerendert)

## Kurzbeschreibung

Symfony-Monolith: Controller rendern Twig-Templates, Anmeldung per Formular mit Session und Remember-me, Doctrine mit MySQL. Dazu kommen Vue-3-Inseln für einzelne Bausteine (Webpack Encore), Stimulus als Gerüst und eine kleine JSON-API unter `/api` (JWT bzw. API-Token) für die Flutter-App.

Beispiel ist ein Dashboard mit öffentlichen Seiten, Buchhaltung und einer Import-Pipeline für Kontoumsätze (CSV, PDF, Foto, App-Screenshots mit OCR). Der Code liegt in `current/`, das direkt als Basis des Document Root dient (`current/public`). `shared/` und `releases/` gibt es nicht, und `current` ist ein echtes Verzeichnis, kein Symlink.

Gegenüber Symfony-API mit Vue-SPA liegt der Unterschied im Kern: hier rendert der Server die Seiten, die API ist ein Nebenzweig, das Migrationsverzeichnis enthält echte Versionen, Hintergrundarbeit läuft über Messenger, und Systemprogramme (poppler, Tesseract) gehören zur Anwendung.

## Passt für / passt nicht für

Passt für:
- Verwaltungs- und Auswertungsoberflächen für wenige Benutzer mit Formularen, Tabellen und Diagrammen.
- Öffentlicher und geschützter Teil in derselben Codebasis.
- Schwere Dateiverarbeitung (Upload, OCR, Parser) als Services, die Oberfläche und API gemeinsam nutzen.

Passt nicht für:
- Sehr interaktive Einzelseiten (Designer, Kalender-Grids); dort ist eine SPA besser.
- Mehrere unabhängige Frontends auf derselben Datenbasis.
- Hohe Last oder Releases mit sofortigem Rollback; der In-place-Deploy bietet das nicht.

## Sprache und Stack

- **PHP 8.4+** (`composer.json`), im Container 8.5.
- **Symfony** (aktuelle Version) mit Security, Twig, Messenger, Mailer, Stimulus: ein Framework für Formulare, Sessions, Konsole.
- **Twig 3**: Basislayouts `base.html.twig` und `base_login.html.twig`, Teilvorlagen für Sidebar und Topbar.
- **Doctrine ORM 3, DBAL 4, Migrations** mit MySQL.
- **API Platform 4.1 und LexikJWT** für die App-Schnittstelle, dazu ein eigener Authenticator für API-Token.
- **Webpack Encore 5** mit Vue 3, Stimulus und Chart.js; ein Entry `app`, Ausgabe nach `public/build`.
- **Messenger mit Doctrine-Transport** (`async`, `failed`) für Mails und Nachrichten.
- **poppler-utils und Tesseract (Deutsch)** im Container: PDF-Text und OCR lokal und kostenlos.
- **PHPUnit 12** mit SQLite-Testdatenbank.

## Ordnerstruktur

```
current/                       # Projektwurzel und Deploy-Ziel
├── assets/                    # Quellen für Encore (app.js, vue/, controllers/, styles/)
├── bin/console                # Symfony-CLI
├── config/packages/           # security, messenger, doctrine, webpack_encore
├── deploy/                    # Host-Hilfsprogramm und systemd-Units
├── docs/                      # Fachdoku (Import, App-API)
├── migrations/                # Doctrine-Versionen
├── public/                    # Document Root: index.php, build/, uploads/
├── src/
│   ├── Controller/            # Seiten; Api/ für JSON-Endpunkte der App
│   ├── Entity/                # Doctrine-Entities
│   ├── Repository/            # je Entity ein Repository
│   ├── Form/                  # Formulartypen
│   ├── Service/               # Fachlogik (Buchungen, Statistik)
│   │   └── BankImport/        # Parser, Schwärzung, Duplikate, Klassifizierung
│   ├── Security/              # Login-Authenticator, API-Token, JWT-Subscriber
│   ├── EventSubscriber/       # Login-Erfolg, Einmal-Anmeldung
│   ├── Command/               # Konsolenbefehle für wiederkehrende Buchungen
│   └── Twig/                  # Twig-Erweiterungen
├── templates/                 # Twig je Bereich plus partial/
├── tests/                     # Controller-, Service-, Importtests, Fixtures
├── translations/
├── var/                       # Cache, Logs, Entwürfe, Spool (nicht im Repo)
└── .env, .env.local, .env.test
```

## Schichten und Verantwortlichkeiten

- **Controller** prüfen Rechte per `#[IsGranted]`, rufen Services und rendern Twig oder JSON. Keine Fachlogik. Seiten- und API-Controller teilen dieselben Services.
- **Services**: `BookingService` und `PrivateAccountManagementService` pflegen Buchungen und Kontostand, `AccountingCalculator` rechnet, `StatisticsService` aggregiert.
- **Import-Pipeline**: `BankImportService` ist die Fassade über `DocumentTextExtractor` (CSV, pdftotext, Tesseract), `Redactor`, den Parsern, `ScreenshotMerger`, `DuplicateDetector` und `TransactionClassifier`.
- **Entwurfsprinzip**: Der Import schreibt zunächst nichts in die Datenbank, sondern legt einen JSON-Entwurf unter `var/` ab (außerhalb des Webroots, Verfall nach 24 Stunden). Erst „Übernehmen“ schreibt in einer Transaktion.
- **Security**: Firewall `main` (Formular, Session, Remember-me), `api_login` (json_login unter `/auth`), `api_jwt` (`/api` mit API-Token-Authenticator und JWT). Standard in `access_control` ist `ROLE_USER`.
- **Messenger**: asynchron mit drei Wiederholungen und Fehler-Transport.

## Namens- und Methodenkonventionen

Englische Klassennamen, deutsche Routen und Oberflächentexte, Controller `final`, Rechte als Klassenattribut.

```php
#[Route('/privates-konto/import')]
#[IsGranted('ROLE_ADMIN')]
final class BankImportController extends AbstractController
{
    public function __construct(private BankImportService $import) {}

    #[Route('/{id}', name: 'private_account_import_preview',
            requirements: ['id' => '[a-f0-9]{32}'], methods: ['GET'])]
    public function preview(string $id): Response { /* Service rufen, Twig rendern */ }
}
```

Routennamen `bereich_unterbereich_aktion`, API-Routen mit `api_`. Ein API-Endpunkt liefert JSON mit deutschen Schlüsseln:

```php
#[Route('/konten', name: 'api_import_accounts', methods: ['GET'])]
public function accounts(BankAccountRepository $accounts): JsonResponse
{
    return $this->json(['konten' => array_map(fn ($a) => [
        'id' => $a->getId(), 'name' => $a->getName(),
    ], $accounts->findAllActive())]);
}
```

Migrationen heißen `VersionJJJJMMTTHHMMSS`. Grenzen stehen als `public const` im Service (`MAX_BYTES`, `MAX_FILES`), Fachfehler als eigene Klasse (`ImportException`).

## Datenhaltung

- MySQL über `DATABASE_URL`; Schemaänderungen nur über Migrationen.
- `PrivateBooking` trägt Monat, Jahr, Typ, Betrag und seit dem Import Buchungstag, Fingerabdruck (`import_hash`) und Kategorie. Gelerntes liegt in `bank_import_rule` (Kategorie-Regeln) und `bank_import_mapping` (Spaltenzuordnung je Konto).
- Dateisystem: `public/uploads` (öffentliche Bilder), `var/bank-import` (Entwürfe), `var/bank-ki` (Spool für die KI-Hilfe).
- Hochgeladene Auszüge werden nach dem Lesen gelöscht; nur der geschwärzte Text bleibt im Entwurf.
- Tests nutzen SQLite, nie die Produktionsdatenbank.

## Fehlerbehandlung und Logging

- Fachfehler im Import sind `ImportException` mit lesbarem Text; der Controller zeigt ihn als Flash-Meldung. Ungültige Formulare liefern 422.
- Unsichere Erkennung ist eine Markierung in der Vorschau (gelb, mit Grund), kein Fehler: „möglich doppelt“, „Vorzeichen unsicher“, „evtl. fehlt ein Screenshot“. Der Nutzer entscheidet vor dem Übernehmen.
- API-Endpunkte antworten mit JSON und passendem Status; Anmeldefehler laufen über eigene Handler.
- Monolog nach `var/log` bzw. stderr. Kontoinhalte werden nicht protokolliert. Fehlgeschlagene Messenger-Nachrichten landen in `failed`.

## Tests

- PHPUnit 12 mit `DatabaseWebTestCase` für Controllertests, Service-Tests ohne Datenbank.
- Der Import ist dicht getestet: Parser (CSV, PDF, App-Liste), Schwärzung, Zusammenführen von Screenshots, Duplikate, Klassifizierung, Seiten und API.
- Testdaten sind synthetisch (kleiner PDF-Generator, erzeugte Auszüge, per Skript gebaute Screenshots mit Überlappung). Echte Kontodaten gehören nie in Fixtures.
- Aufruf: `php bin/phpunit tests/Service/BankImport tests/Controller/BankImport*`. Rote Tests werden sofort bereinigt, nie liegen gelassen.

## Sicherheit

- Formular-Login mit CSRF, Remember-me für sieben Tage. `ROLE_ADMIN` für Import und Verwaltung, an jeder Klasse per `#[IsGranted]`.
- App-Zugang über JWT oder langlebige API-Token; nur der Token-Endpunkt ist öffentlich.
- **Datensparsamkeit**: `Redactor` schwärzt IBAN, BIC, Kartennummern, bezeichnete Nummern, lange Ziffernfolgen, E-Mail-Adressen und die Anschrift des Kontoinhabers, bevor irgendetwas weiterverarbeitet wird.
- **KI-Hilfe standardmäßig aus.** Nur geschwärzter Text geht an den Host-Dienst, und nur wenn kein IBAN-artiges Muster und keine Ziffernfolge ab acht Stellen übrig ist.
- **Host-Dienst** (Python, root): öffnet den Spool-Pfad Komponente für Komponente ohne Symlinks, prüft den Besitzer, legt Antworten exklusiv an und startet den Aufruf ohne Werkzeuge. Nötig, weil der Pfad dem Webserver-Benutzer gehört. Das Skript wird nach `/usr/local/sbin` kopiert, nie aus dem Projektordner gestartet.
- Upload-Grenzen: 10 MB je Datei, höchstens 30 Bilder und 50 MB je Vorgang, Prüfung von Erweiterung und MIME-Typ.

## Konfiguration und Geheimnisse

- `.env` (versioniert) enthält nur Voreinstellungen. `.env.local` auf dem Server hält `DATABASE_URL`, `APP_SECRET`, `MAILER_DSN`, `MESSENGER_TRANSPORT_DSN` und JWT-Passphrase, nicht im Repo und nur für root und den Webserver lesbar. `.env.test` zeigt auf SQLite.
- Regel: Jedes Projekt bekommt eine `.env.example` mit Platzhaltern:

```
APP_ENV=prod
APP_SECRET=hier-zufaelligen-wert-eintragen
DATABASE_URL="mysql://benutzer:passwort@dbhost:3306/datenbank?serverVersion=8.4"
MESSENGER_TRANSPORT_DSN=doctrine://default
MAILER_DSN=null://null
JWT_PASSPHRASE=platzhalter
```

- Zugangsdaten gehören in die Secret-Verwaltung, nicht in Repo oder Doku.

## Deploy

Platzhalter in spitzen Klammern (`<STACK>`, `<auth-middleware>`, `<https-redirect>`, `meine-org/...`, `*.example.org`) sind durch die eigene Umgebung zu ersetzen. Die Beispiele gehen von Docker, Traefik als Reverse Proxy und einem externen Docker-Netzwerk `web` aus; andere Proxys und Orchestrierungen funktionieren sinngemäß genauso.

Das Dashboard läuft im gemeinsamen Container `php-app` (Apache, PHP 8.5, Image `meine-org/php-app`, Dockerfile unter `<STACK>/php-app`). Der Code wird von `<PROJEKTE>` eingehängt. Davor steht Traefik v3 mit Resolver `le`: je Domain ein Router auf `websecure` und einer auf `web` mit Middleware `nach-https`, beide zum Service `php-app` (Datei `traefik/dynamic/php-app.yml`). Der Login kommt aus der Anwendung, nicht aus einem Auth-Proxy. Der vHost liegt in `php-app/sites/<domain>.conf`:

```
<VirtualHost *:8081>
    ServerName dashboard.example
    DocumentRoot <PROJEKTE>/dashboard/current/public
    php_admin_value max_file_uploads 40
    php_admin_value post_max_size 60M
    <Directory <PROJEKTE>/dashboard/current/public>
        FallbackResource /index.php
    </Directory>
</VirtualHost>
```

Das Image bringt `poppler-utils` und `tesseract-ocr-deu` mit; im Dockerfile festgehalten, überleben sie einen Neubau. Für Messenger läuft der Container `worker-dashboard` aus demselben Image (`php bin/console messenger:consume async --time-limit=3600 --env=prod`, Benutzer `www-data`, Neustart durch Docker). Die Datenbank liegt im Container `db`.

Der Deploy ist **in-place**: Dateien in `current/` ersetzen, Cache leeren, nur neue Migrationen ausführen.

```
php bin/console cache:clear --env=prod
php bin/console doctrine:migrations:migrate --no-interaction   # oder gezielt: migrations:execute <Version> --up
chown -R www-data:www-data var/
npm run build                                                  # nur bei Änderungen an assets/
```

OPcache prüft Zeitstempel alle zwei Sekunden, ein Neustart des Containers ist normalerweise unnötig. Der Host-Dienst besteht aus einer systemd-Pfad-Unit (beobachtet den Spool) und einer gehärteten oneshot-Dienst-Unit. Healthcheck: Startseite und Anmeldeseite aufrufen.

## Typische Fehler

- **Migrationen**: Jede Schemaänderung gehört in eine Migration. Passen Versionsliste und Schema nicht zusammen, Migrationen gezielt mit `migrations:execute` anwenden.
- **Besitzer im Cache**: `cache:clear` als root hinterlässt `var/` mit falschem Besitzer, danach 500.
- **Upload-Grenzen**: Die Container-Voreinstellung (20 Dateien, 32 MB) reicht für mehrere Screenshots nicht; Grenzen im vHost setzen.
- **OCR-Pakete nur live installiert**: ohne Eintrag im Dockerfile fehlen sie nach dem Neubau.
- **Nachgebaute Bank-Layouts**: Die Profile einzelner Banken und App-Screenshots sind aus Erfahrung nachgebaut; erst echte Dateien zeigen Abweichungen. Deshalb ist alles in der Vorschau korrigierbar.
- **Vorzeichen bei Screenshots**: Apps zeigen Ausgaben teils ohne Minus; solche Beträge werden als unsicher markiert.
- **Überlappung beim Zusammenführen**: Zwei echte gleiche Buchungen am selben Tag dürfen nicht verschwinden; verglichen wird nur das Fenster am Bildrand.
- **Rote Alt-Tests** bleiben unbemerkt, wenn die Suite nicht regelmäßig läuft.
- **Große Controller**: Portfolio, Buchhaltung und App-API in einer Anwendung; wachsende Controller früh in Services und kleinere Controller aufteilen.

### Verbesserungen für neue Projekte

- Release-Ordner mit Symlink-Wechsel oder gebautes Image statt In-place-Deploy.
- Alle Schemaänderungen konsequent über Migrationen, fest im Deploy-Ablauf.
- Eigener Compose-Ordner mit Traefik-Labels, Healthcheck und eigenem Worker statt geteiltem `php-app`.
- `.env.example` pflegen, Suite in einer Pipeline laufen lassen.
- Große Controller früh in Services teilen; Oberfläche und API immer über denselben Service anbinden, wie beim Import.
- Den root-Host-Dienst für die KI-Hilfe durch einen Worker im Container ersetzen.

## Checkliste

- `.gitignore` für `.env.local`, `vendor`, `var`, `public/build`, `node_modules`.
- `.env.example` mit Platzhaltern, echte Werte nur in `.env.local` auf dem Server.
- Firewalls getrennt: Formular-Login für die Oberfläche, stateless für `/api`, Standard `ROLE_USER`.
- Jede Controller-Klasse mit `#[IsGranted]`, Formulare mit CSRF.
- Fachlogik nur in Services; Oberfläche und API teilen sie.
- Jede Schemaänderung als Migration, vorher an einer Kopie getestet.
- Dateiverarbeitung mit Größen- und Typgrenzen, Entwurf außerhalb des Webroots, Löschen nach dem Lesen.
- Sensible Daten vor jeder Weiterverarbeitung schwärzen und nicht protokollieren.
- Tests mit synthetischen Daten und SQLite, Suite regelmäßig ausführen.
- vHost mit `FallbackResource /index.php`; Traefik-Router mit `le` und `nach-https`.
- Worker-Container für Messenger mit Zeitlimit.
- Nach dem Deploy: Cache leeren, Migrationen, Besitzer von `var/`, Assets gebaut, Anmeldung getestet.
