# Laravel-Monolith

## Kurzbeschreibung

Ein klassischer Laravel-Monolith: eine Codebasis für Web-Oberfläche, JSON-API, Hintergrundjobs und Scheduler. Requests laufen durch Routing und Middleware in schlanke Controller, die Fachlogik an Services oder Actions delegieren. Eloquent übernimmt die Persistenz, Form Requests validieren, Policies prüfen Rechte, Queues nehmen langlaufende Arbeit ab. Im Container läuft die Anwendung hinter Traefik; Laravel Sail gibt es nur lokal.

## Passt für / passt nicht für

Passt für Web-Apps mit Login, Formularen und Rollen, für JSON-APIs mit relationaler Datenbank und für Projekte, die Queues, Mails, Scheduler und Migrationen aus einer Hand brauchen.

Passt nicht für rein statische Seiten (zu schwer), für Dienste mit dauerhaften Verbindungen als Kern und für kleinste Webhook-Skripte, bei denen das Framework mehr Last als Nutzen bringt.

## Sprache und Stack

- **PHP**, aktuelle stabile Version mit Sicherheitsunterstützung (die von Laravel unterstützte Spanne): Typisierung und Enums.
- **Laravel**, aktuelle Hauptversion: Routing, Eloquent, Queue, Scheduler, Validierung, Auth in einem Framework.
- **Composer** mit PSR-4-Autoloading.
- **MySQL/MariaDB oder PostgreSQL**: relationale Daten; SQLite nur für Tests.
- **Queue-Backend** `database`, bei Last Redis.
- **Pest oder PHPUnit**: je Projekt eines, nicht mischen.
- **Blade mit Livewire/Inertia** oder reine API; Vite als Bundler.
- **Larastan und Pint**: statische Analyse und Codestil.
- **Sail**: nur lokale Entwicklung, nie als Produktions-Image.

## Ordnerstruktur

```
projekt/
├── app/
│   ├── Actions/          # ein Anwendungsfall pro Klasse
│   ├── Console/Commands/ # Artisan-Befehle
│   ├── Enums/            # Status und Typen
│   ├── Http/
│   │   ├── Controllers/  # dünn: Request -> Service -> Response
│   │   ├── Middleware/   # eigene Middleware
│   │   ├── Requests/     # Form Requests: Validierung, Autorisierung
│   │   └── Resources/    # JSON-Form der API-Antworten
│   ├── Jobs/             # Queue-Jobs
│   ├── Models/           # Eloquent: Relationen, Casts, Scopes
│   ├── Policies/         # Rechte je Modell
│   └── Services/         # Fachlogik über mehrere Modelle
├── bootstrap/            # App-Start, Middleware, Exception-Handling
├── config/               # Konfiguration, einzige Stelle für env()
├── database/             # migrations, factories, seeders
├── public/               # Document Root
├── resources/            # views (Blade), js, css
├── routes/               # web.php, api.php, console.php
├── storage/              # Logs, Cache, Uploads (Volume)
├── tests/                # Feature und Unit
├── .env.example          # Platzhalter, keine echten Werte
└── Dockerfile            # mehrstufig
```

## Schichten und Verantwortlichkeiten

- **Route und Middleware**: URL zuordnen, Auth, Throttling, Locale.
- **Form Request**: `rules()` validiert, `authorize()` prüft grob; der Controller nutzt nur `validated()`.
- **Controller**: holt validierte Daten, ruft eine Action oder einen Service, gibt Response oder Resource zurück. Keine Abfrage- und Berechnungslogik.
- **Action**: ein Anwendungsfall, nutzbar aus Controller, Job und Artisan-Befehl.
- **Service**: bündelt Fachlogik über mehrere Modelle oder externe Schnittstellen; kennt weder Request noch Response.
- **Model**: Relationen, Casts, Scopes; keine Orchestrierung.
- **Policy**: Wer darf was mit welchem Modell, aufgerufen per `authorize()`.
- **Job**: asynchron, idempotent, mit Retry und Backoff.

Abhängigkeitsrichtung: Controller -> Action/Service -> Model, nie umgekehrt.

## Namens- und Methodenkonventionen

- Klassen im Singular, PascalCase: `Invoice`, `InvoicePolicy`, `StoreInvoiceRequest`, `InvoiceResource`.
- Tabellen im Plural snake_case (`invoices`), Fremdschlüssel `invoice_id`.
- Ressourcen-Controller mit `index`, `show`, `store`, `update`, `destroy`.
- Typen an Parametern und Rückgaben, `declare(strict_types=1)`.

```php
class InvoiceController extends Controller
{
    public function store(StoreInvoiceRequest $request, CreateInvoice $create): InvoiceResource
    {
        $this->authorize('create', Invoice::class);
        return new InvoiceResource($create->execute($request->user(), $request->validated()));
    }
}

class CreateInvoice
{
    public function execute(User $user, array $data): Invoice
    {
        return DB::transaction(function () use ($user, $data) {
            $invoice = $user->invoices()->create($data);
            SendInvoiceMail::dispatch($invoice)->afterCommit();
            return $invoice;
        });
    }
}
```

## Datenhaltung

- Schema nur über Migrationen im Repo; ausgelieferte Migrationen bleiben unverändert, Änderungen kommen als neue Migration.
- Fremdschlüssel und Indizes in der Migration anlegen.
- `$fillable` explizit pflegen, nie `$guarded = []`.
- N+1 vermeiden: `with()` nutzen, in Entwicklung `Model::preventLazyLoading()` aktivieren.
- Mehrere Schreibvorgänge in `DB::transaction()`; abhängige Jobs mit `afterCommit()`.
- Dateien über das Storage-System auf einem Volume, nicht im Image.
- Cache und Sessions in `database` oder Redis, nicht `file` bei mehreren Containern.

## Fehlerbehandlung und Logging

- Zentrale Behandlung in `bootstrap/app.php`: fachliche Exceptions werden auf Statuscodes abgebildet, API-Fehler als einheitliches JSON.
- Validierungsfehler liefern automatisch 422.
- Logging über die Log-Facade, im Container Kanal `stderr`, damit Docker die Logs sammelt. Kontext als Array, keine Daten im Meldungstext.
- Keine Passwörter, Tokens oder personenbezogenen Daten loggen.
- `APP_DEBUG=false` in Produktion.
- Fehlgeschlagene Jobs landen in `failed_jobs`; Alarm bei wachsender Zahl.
- Healthcheck-Route `/up` des Frameworks nutzen.

## Tests

- **Feature-Tests** als Rückgrat: HTTP-Aufruf, Datenbankzustand, Antwort; `RefreshDatabase` und Factories.
- **Unit-Tests** für reine Logik in Actions und Services.
- Externes ersetzen mit `Http::fake()`, `Mail::fake()`, `Queue::fake()`, `Storage::fake()`.
- Policies getrennt testen: erlaubt, verboten, nicht angemeldet.
- Bei engine-spezifischem SQL die echte Datenbank-Engine in der Testumgebung nutzen.
- Pint und Larastan laufen in der CI neben den Tests.

```
php artisan test
vendor/bin/pint --test
vendor/bin/phpstan analyse
```

## Sicherheit

- CSRF für Web-Routen aktiv (`@csrf`); APIs mit Token-Authentifizierung (Sanctum).
- Autorisierung über Policies, nicht nur über ausgeblendete Buttons.
- Jede Eingabe im Form Request validieren, Uploads nach Typ und Größe prüfen.
- SQL nur mit Bindings; bei `DB::raw` und `whereRaw` Parameter binden.
- Blade maskiert mit `{{ }}`; `{!! !!}` nur für sichere Inhalte.
- Rate Limiting auf Login und sensible Endpunkte.
- `APP_KEY` geheim halten; ein Wechsel entwertet Sessions und verschlüsselte Daten.
- Hinter Traefik vertrauenswürdige Proxys konfigurieren, damit Schema und Client-Adresse stimmen.
- `composer audit` regelmäßig.

## Konfiguration und Geheimnisse

- Konfiguration über Umgebungsvariablen. Die `.env` liegt nie im Repository; im Repo steht `.env.example` mit Platzhaltern (`APP_ENV`, `APP_DEBUG`, `APP_URL`, `APP_KEY=`, `DB_*`, `QUEUE_CONNECTION`, `MAIL_*`).
- `env()` nur in `config/*.php`, sonst liefert es nach `config:cache` den Wert `null`.
- Geheimnisse stammen aus einer zentralen Secret-Verwaltung und werden auf dem Server hinterlegt, nicht ins Image gebacken.

## Deploy

Platzhalter in spitzen Klammern (`<STACK>`, `<auth-middleware>`, `<https-redirect>`, `meine-org/...`, `*.example.org`) sind durch die eigene Umgebung zu ersetzen. Die Beispiele gehen von Docker, Traefik als Reverse Proxy und einem externen Docker-Netzwerk `web` aus; andere Proxys und Orchestrierungen funktionieren sinngemäß genauso.

Muster: ein Docker-Container im Netzwerk `web`, Traefik findet ihn über Labels, die Dienste stehen in der zentralen Compose-Datei unter `<STACK>`.

- **Image**: mehrstufig. Composer-Stufe (`--no-dev --optimize-autoloader`), Asset-Stufe (Node/Vite), Laufzeitstufe mit PHP und Code. Entweder php-fpm plus nginx oder Apache mit PHP-Modul wie bei einem PHP-Dienst. Document Root ist `public/`.
- **Labels** (öffentliche App; interne Werkzeuge ergänzen `traefik.http.routers.meineapp.middlewares=<auth-middleware>@docker`):

```
networks: [web]
labels:
  - "traefik.enable=true"
  - "traefik.http.services.meineapp.loadbalancer.server.port=80"
  - "traefik.http.routers.meineapp.rule=Host(`meineapp.example.org`)"
  - "traefik.http.routers.meineapp.entrypoints=websecure"
  - "traefik.http.routers.meineapp.tls.certresolver=le"
  - "traefik.http.routers.meineapp-http.rule=Host(`meineapp.example.org`)"
  - "traefik.http.routers.meineapp-http.entrypoints=web"
  - "traefik.http.routers.meineapp-http.middlewares=<https-redirect>@file"
```

- **Volumes**: `storage/` persistent; Umgebungsvariablen aus der Compose-Umgebung.
- **Healthcheck**: HTTP-Aufruf von `/up` im Container.
- **Release**: Image bauen, Container neu erstellen, einmalig `php artisan migrate --force`, dann `config:cache`, `route:cache`, `view:cache`.
- **Queue und Scheduler**: eigene Container aus demselben Image mit anderem Startbefehl (`queue:work`, `schedule:work`), ohne Labels.
- `restart: unless-stopped`, Zeitzone per `TZ`.

## Typische Fehler

- Fachlogik in Controllern und Models; Controller wachsen auf hunderte Zeilen.
- `env()` außerhalb von `config/`: nach `config:cache` ist der Wert `null`.
- N+1-Abfragen, weil Relationen erst in der Schleife geladen werden.
- Job wird vor dem Commit abgeschickt und findet den Datensatz nicht (`afterCommit()` fehlt).
- `storage/` nicht als Volume: Uploads verschwinden beim Neustart; fehlende Schreibrechte für den Webserver-Benutzer.
- Migrationen bei jedem Containerstart: konkurrierende Schemaänderungen bei mehreren Instanzen.
- `APP_DEBUG=true` in Produktion.
- Fehlende Proxy-Konfiguration hinter Traefik: falsche Schemata in URLs, Mixed Content.
- Queue-Worker läuft nach dem Deployment mit altem Code weiter.
- Offenes Mass Assignment: Rollenfelder per Formular überschreibbar.
- Sail-Konfiguration als Produktionsbasis.

## Checkliste

- Controller dünn, Logik in Actions oder Services
- Jede Eingabe läuft durch einen Form Request
- Jede Ressource hat eine Policy
- Schema nur über Migrationen, ausgelieferte unverändert
- `$fillable` gepflegt, Lazy Loading in Entwicklung verboten
- `env()` nur in `config/`, `.env.example` vollständig
- `APP_DEBUG=false`, `APP_KEY` gesetzt und geheim
- Logs nach stderr, Healthcheck vorhanden
- Mehrstufiges Dockerfile, Document Root `public/`
- Traefik-Labels, Netzwerk `web`, ggf. Auth-Middleware
- `storage/` auf einem Volume
- Migrationen als eigener Schritt, Worker nach Release neu gestartet
- Tests, Pint und Larastan grün in der CI
