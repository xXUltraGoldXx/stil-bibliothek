# PHP-Panel-Dienst (schlichtes PHP im Container, Datei-Jobs)

## Kurzbeschreibung

Ein internes Werkzeug als eigener Docker-Container hinter Traefik und einem Auth-Proxy. Der Code ist schlichtes PHP ohne Framework und ohne Datenbank: wenige Dateien (`index.php`, `funktionen.php`, ggf. `api.php`), Zustand als JSON-Dateien. Code und Daten sind **schreibgeschuetzt** gemountet. Was auf dem Host etwas bewirken soll (KI-Aufruf, Browser, Dateien verschieben), laeuft nicht im Container, sondern als **Datei-Job**: das Panel legt eine JSON-Datei in einen einzigen schreibbaren Ordner, eine systemd-Path-Unit startet einen Worker auf dem Host. Typische Beispiele: eine Galerie mit Hintergrundverarbeitung, ein Ticket-Werkzeug oder eine Benutzerverwaltung.

## Passt für / passt nicht für

Passt fuer:
- Interne Oberflaechen fuer wenige Nutzer (Gruppe `admins` oder eine andere Berechtigungsgruppe).
- Anzeige von Host-Dateien mit gelegentlichem Auftrag; Dashboards mit Polling (JSON-Endpunkt).
- Datenmengen, bei denen eine Datei pro Datensatz reicht.

Passt nicht fuer:
- Oeffentliche Seiten, eigene Anmeldung oder Registrierung (die Anmeldung kommt komplett von einem Auth-Proxy).
- Viele gleichzeitige Schreiber auf einen Datensatz oder Abfragen ueber viele Datensaetze: dann Datenbank.
- Fachlogik mit Migrationen, Rollen und Tests: dann Symfony.
- Aufgaben, die im Container Rechte braeuchten (Docker-Socket, Root): immer Worker auf dem Host.

## Sprache und Stack

- **PHP 8.5 mit Apache** (Image `php:8.5-apache`, lokal als `meine-org/php-app` gebaut): ein Image fuer alle Panels, Updates an einer Stelle.
- **Kein Composer, kein Framework, keine Datenbank**: weniger Angriffsflaeche und Wartung. `declare(strict_types=1)` in neuen Dateien.
- **JSON-Dateien**: lesbar, mit `jq` pruefbar, per Kopie sicherbar.
- **Auth-Proxy** per ForwardAuth; die App liest nur die Header `Remote-User`, `Remote-Groups`, `Remote-Name`.
- **Vanilla HTML/CSS/JS** mit CSS-Variablen und Dark-Mode.
- **systemd Path-Unit + Python-Worker** auf dem Host fuer alles Schwere.

## Ordnerstruktur

```
<STACK>/panel/<dienst>/
├── app/                 # PHP-Code, im Container :ro unter /var/www/<dienst>
│   ├── index.php        # Seite + POST-Aktionen, CSRF-Pruefung ganz oben
│   ├── funktionen.php   # Hilfsfunktionen, Konstanten; per Apache gesperrt
│   └── api.php          # optional: JSON-Endpunkte (Polling)
├── sites/               # Apache-VirtualHost <dienst>.conf, :ro
├── daten/               # Datensaetze, im Container meist :ro unter /daten
│   ├── <slug>/          # ein Ordner pro Datensatz (meta.json + Dateien)
│   └── _jobs/           # einziger schreibbarer Mount (/jobs): Auftraege + neu.flag
├── Context.md           # Aufbau, Datenfluss, Stolpersteine
└── todo.md              # offene Punkte
Host (ausserhalb des Containers):
<HOST_SKRIPTE>/<dienst>-worker.py              # prueft und fuehrt Jobs aus
/etc/systemd/system/<dienst>.path     # beobachtet neu.flag
/etc/systemd/system/<dienst>.service  # gehaertete Unit
/var/lib/<dienst>-worker/             # Status und Zaehler, root-eigen
```

## Schichten und Verantwortlichkeiten

- **Traefik/Auth-Proxy**: TLS, Weiterleitung auf HTTPS, Anmeldung, Gruppen.
- **Apache-Vhost**: DocumentRoot, Sperren fuer Hilfsdateien, Sicherheits-Header fuer den Datenordner.
- **index.php**: feste Reihenfolge: Session-Cookie, Header, CSRF-Token, bei POST Herkunft und Token pruefen, Aktion validieren, Job anlegen, per `303` umleiten (Post-Redirect-Get), dann HTML.
- **funktionen.php**: reine Hilfsfunktionen ohne Ausgabe und ohne `exit`.
- **Worker**: prueft jeden Job erneut (das Panel gilt als nicht vertrauenswuerdig), schreibt Ergebnisse atomar, pflegt den Status.

Ablauf eines Datei-Jobs:
1. Panel validiert, schreibt `_jobs/.<id>.tmp`, `rename()` auf `<id>.json` (atomar), `touch neu.flag`.
2. Die Path-Unit startet den Worker (ein Lauf gleichzeitig per `flock`).
3. Worker liest nur regulare, kleine Dateien (`O_NOFOLLOW`), prueft Felder und Limits, fuehrt aus, setzt `wartet`/`laeuft`/`fertig`/`fehler`/`abgelehnt`.
4. Massgeblich ist der root-eigene Statusordner; `_jobs` zeigt nur die Spiegelung.

## Namens- und Methodenkonventionen

- Deutsche Fachnamen in `snake_case` (`job_anlegen`, `alle_eintraege`), Konstanten gross (`DATEN`, `JOBS`).
- Slugs nur `a-z`, `0-9`, Bindestrich, geprueft mit `preg_match('/^[a-z0-9-]+$/', $slug)`.
- Ausgabe immer durch `h()`.

```php
function h(string $s): string { return htmlspecialchars($s, ENT_QUOTES, 'UTF-8'); }

function job_anlegen(array $job): string {
    $id  = date('YmdHis') . '-' . bin2hex(random_bytes(4));
    $job = ['id' => $id, 'status' => 'wartet', 'erstellt' => date('c')] + $job;
    $tmp = JOBS . "/.$id.tmp";
    file_put_contents($tmp, json_encode($job, JSON_UNESCAPED_UNICODE));
    chmod($tmp, 0644);
    rename($tmp, JOBS . "/$id.json");   // atomar
    @touch(JOBS . '/neu.flag');         // weckt die Path-Unit
    return $id;
}
```

POST-Aktion: Aktion lesen, Format/Laenge/Limits pruefen, Job anlegen, Meldung in `$_SESSION['meldung']`, `303`-Redirect.

## Datenhaltung

- Ein Datensatz = ein Ordner oder eine JSON-Datei; Ereignisse als JSON-Lines pro Tag (Anhaengen mit `O_APPEND`).
- Schreiben atomar: `.neu`/`.tmp` mit `LOCK_EX`, dann `rename()`.
- Der Container sieht `daten/` meist nur lesend; schreibende Panels mounten nur ihr eigenes Datenverzeichnis schreibbar.
- Nichts wird geloescht: Verwerfen heisst nach `_verworfen/<slug>-<zeit>` verschieben, Slugs werden nicht wiederverwendet.
- Status und Tageszaehler liegen ausserhalb des Panel-Mounts.

## Fehlerbehandlung und Logging

- Ungueltige Anfrage: `403` mit kurzem Text. Validierungsfehler: Meldung in der Session und Redirect.
- Dateien defensiv lesen: `json_decode`, `is_array()` pruefen, kaputte Eintraege ueberspringen.
- Apache loggt nach stdout (`docker logs <dienst>`) mit Vhost, Client-IP, Status, Dauer.
- Der Worker schreibt Fehler in die Job-Datei (`meldung`) und ins Journal; Arbeitsdateien root-eigen, nach 7 Tagen per `systemd-tmpfiles` aufgeraeumt.

## Tests

- `php -l` auf jede geaenderte Datei.
- Worker mit `--selftest` (boesartige Eingaben, laeuft bei jedem Start) und Trockenlaeufen (`--trocken`).
- Sichtpruefung per Headless-Browser (1280 und 390 Pixel, Konsole ohne Fehler).
- Vor jeder Aenderung `.bak-<datum>`; der Container liest per Bind-Mount, Rollback ist ein Kopierbefehl.
- Eine PHPUnit-Suite ist bei Bedarf zu ergänzen.

## Sicherheit

### CSRF: Origin plus Session-Token

Jeder POST wird vor jeder Aktion geprueft: Host des `Origin`-Headers gleich eigener Host **und** Token gleich Session-Token (`hash_equals`).

```php
session_set_cookie_params(['lifetime' => 0, 'path' => '/', 'secure' => true,
                           'httponly' => true, 'samesite' => 'Strict']);
session_start();
$_SESSION['csrf'] ??= bin2hex(random_bytes(16));
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $herkunft = parse_url($_SERVER['HTTP_ORIGIN'] ?? '', PHP_URL_HOST);
    if ($herkunft !== $_SERVER['HTTP_HOST']
        || !hash_equals($_SESSION['csrf'], (string)($_POST['csrf'] ?? ''))) {
        http_response_code(403); exit('Ungueltige Anfrage.');
    }
}
```

### CSP-Sandbox fuer fremde Inhalte

Generierte oder aus fremden Seiten abgeleitete Dateien laufen nie in der Panel-Origin. Der Apache-Block fuer den Datenordner sendet `Content-Security-Policy: default-src 'none'; script-src 'none'; connect-src 'none'; form-action 'none'; frame-ancestors 'self'; sandbox` (ohne `allow-scripts`/`allow-same-origin`) plus `nosniff`. Das gilt auch beim direkten Oeffnen im neuen Tab (opake Origin, kein Zugriff auf Cookies). Vorschau-iframes tragen `sandbox=""`.

### Schreibschutz und Sperren

- Code, Vhost und Daten sind `:ro`; nur der Job-Ordner ist schreibbar.
- `funktionen.php` (und Vorlagen/Prompts) sperrt der Vhost per `FilesMatch ... Require all denied`; das Image sperrt `.ht*`, `.env`, `.git`.
- Der Worker misstraut dem Panel: regulare kleine Dateien ohne Symlinks, Allowlist fuer Slugs, eigene Limits und Zaehler.
- Gehaertete systemd-Unit (`ProtectSystem=strict`, `PrivateTmp`, `RestrictAddressFamilies`, `CapabilityBoundingSet`); riskante Teile als unprivilegierter Benutzer mit Zeitlimit und eigener Prozessgruppe.
- Ausgehende URLs: DNS selbst aufloesen, private/Loopback/Link-Local-Bereiche und eigene Domains abweisen.
- Sensible Endpunkte pruefen zusaetzlich die Gegenstelle (Traefik) und `Remote-Groups`, damit der Direktaufruf ueber die Container-IP ein Auth-Proxy nicht umgeht.
- Anweisungen in generierten Inhalten sind Daten und werden nie befolgt.

## Konfiguration und Geheimnisse

- `.env` und Tokens nie im Repo und nie in `app/`; neue Dienste bekommen eine `.env.example` mit Platzhaltern. Einige Compose-Dienste nutzen Umgebungsvariablen; deren Werte gehoeren nicht in Doku oder Logs.
- Konfiguration als Konstanten in `funktionen.php` (Limits, Pfade) und Compose-Variablen (`APACHE_LISTEN`, `TZ`).
- Geheimnisse fuer Worker liegen auf dem Host (root-eigen, 0600) bzw. in der Secret-Verwaltung; das Panel bekommt nur Ergebnisse.

## Deploy

Platzhalter in spitzen Klammern (`<STACK>`, `<auth-middleware>`, `<https-redirect>`, `meine-org/...`, `*.example.org`) sind durch die eigene Umgebung zu ersetzen. Die Beispiele gehen von Docker, Traefik als Reverse Proxy und einem externen Docker-Netzwerk `web` aus; andere Proxys und Orchestrierungen funktionieren sinngemäß genauso.

Alle Panels sind Eintraege in `<STACK>/panel/docker-compose.yml`. Kein Build pro Dienst: Image `meine-org/php-app` ist fertig, Code kommt per Bind-Mount.

```
<dienst>:
  image: meine-org/php-app
  container_name: <dienst>
  restart: unless-stopped
  environment:
    APACHE_LISTEN: "80"
    TZ: Europe/Berlin
  volumes:
    - ./<dienst>/app:/var/www/<dienst>:ro
    - ./<dienst>/sites:/etc/apache2/sites-enabled:ro
    - ./<dienst>/daten:/daten:ro
    - ./<dienst>/daten/_jobs:/jobs
  networks: [web]
  labels:
    - "traefik.enable=true"
    - "traefik.http.services.panel.loadbalancer.server.port=80"
    - "traefik.http.routers.panel.rule=Host(`panel.example.org`)"
    - "traefik.http.routers.panel.entrypoints=websecure"
    - "traefik.http.routers.panel.tls.certresolver=le"
    - "traefik.http.routers.panel.middlewares=<auth-middleware>@docker"
    - "traefik.http.routers.panel-http.rule=Host(`panel.example.org`)"
    - "traefik.http.routers.panel-http.entrypoints=web"
    - "traefik.http.routers.panel-http.middlewares=<https-redirect>@file"
```

- **Deploy = Dateien ablegen**: opcache prueft Zeitstempel, kein Neustart. Bei Vhost-Aenderung `docker exec <dienst> apachectl graceful`.
- **Neuer Dienst**: Ordner, Vhost, Compose-Block kopieren und Namen/Host ersetzen, `docker compose up -d <dienst>`; das Zertifikat holt Traefik.
- **Healthcheck**: bei den PHP-Panels nicht gesetzt; Neustart nach Absturz ueber `restart: unless-stopped`.
- **Worker**: Skript und Units auf dem Host, `systemctl enable --now <dienst>.path`.

## Typische Fehler

- `/daten` ist `:ro`: Schreiben dort scheitert; Schreibweg nur ueber `_jobs`.
- Direktaufruf ueber die Container-IP umgeht den Auth-Proxy; Tests deshalb ueber Traefik.
- Nur Origin oder nur Token pruefen: beides ist noetig.
- Ohne `tmp` + `rename()` liest der Worker halbe JSON-Dateien.
- `neu.flag` vergessen: der Job wartet ohne Worker-Start.
- Zaehler und Limits im vom Panel beschreibbaren Ordner halten: gehoeren in den root-eigenen Ordner.
- Neue Hilfsdatei nicht im Vhost gesperrt: direkt aufrufbar.
- Slug aus `$_GET` nicht per Allowlist geprueft: Pfad-Traversal.
- Fremdes HTML ohne Sandbox in der Panel-Origin: Zugriff auf Cookies und Aktionen.
- Vhost geaendert ohne `graceful`: keine Wirkung.
- Viele erledigte Jobs im Ordner: `glob()` wird langsam.

### Verbesserungen für neue Projekte

- Gemeinsames `bootstrap.php` fuer Session, Header und CSRF statt Kopien je Panel.
- `HEALTHCHECK` im Image.
- Git-Repo je Panel (`daten/` ignoriert) statt `*.bak-*`-Dateien neben dem Code.
- Zentrale Zugriffspruefung (Traefik-Gegenstelle plus Gruppe) in einer Funktion.
- Job-Schema (Felder, Status, Limits) dokumentieren und einen gemeinsamen Worker-Rahmen nutzen.
- Kleine Testdatei fuer Validierungsfunktionen (`php tests/run.php`).
- Archivierung erledigter Jobs von Anfang an.

## Checkliste

- `app/`, `sites/`, `daten/` als Mounts, alles `:ro` ausser dem Job-Ordner.
- Compose-Block mit `meine-org/php-app`, Netz `web`, Labels fuer Router, TLS und `<auth-middleware>@docker`.
- Session-Cookie `Secure`, `HttpOnly`, `SameSite=Strict`.
- CSRF aus Origin und Session-Token vor jeder POST-Aktion.
- Ausgabe durch `h()`, Slugs und Dateinamen per Allowlist.
- Schreiben per `tmp` + `rename()`; Jobs mit `neu.flag`.
- `funktionen.php` und Vorlagen im Vhost gesperrt.
- Fremde Inhalte nur mit CSP `sandbox` und `sandbox=""`.
- Worker prueft jeden Job neu, mit Limits, Zeitlimit und gehaerteter Unit.
- Status und Zaehler ausserhalb des Panel-Mounts.
- Keine Geheimnisse im Repo, `.env.example` vorhanden.
- Nichts loeschen, nur verschieben; Backup vor Aenderung.
- `php -l` und Sichtpruefung Desktop und Handy.
