# Flutter-Web-App (Dashboard-Client mit JWT-API)

## Kurzbeschreibung

Eine Single-Page-App, die mit Flutter fuer das Web gebaut wird (`flutter build web --release`) und als statische Dateien ausgeliefert wird. Sie ist der mobile Client fuer ein Symfony-Backend mit API Platform (JWT-Anmeldung, Hydra-JSON): Login, Startseite mit Kennzahlen, Finanzbereich (Konten, Buchungen, Ausgaben, Fixkosten, Diagramme) und Verwaltung der Website-Inhalte. Es gibt keinen eigenen Server: der Webserver liefert nur `index.html`, `main.dart.js`, `canvaskit/` und Assets; alle Daten kommen per HTTPS vom Backend.

Der Code ist nach Features gegliedert (`features/finance`, `features/stats`, `features/websites`) mit den Schichten api, models, repository, state, ui. Das Handy ist die Hauptzielgruppe, daher gibt es viele Viewport-Tests bei 300 bis 412 Pixel Breite.

## Passt für / passt nicht für

Passt fuer:
- Interne oder angemeldete Anwendungen (Dashboards, Formulare, Diagramme), die auf Handy und Desktop gleich aussehen sollen.
- Teams, die ohnehin Flutter fuer Android/iOS nutzen und dieselbe Codebasis im Browser anbieten wollen.
- Clients fuer eine bestehende REST/JSON-API.

Passt nicht fuer:
- Oeffentliche Seiten mit SEO-Anspruch: Flutter Web rendert in ein Canvas, Inhalte sind fuer Suchmaschinen kaum lesbar.
- Sehr kleine Erstladezeiten: `main.dart.js` und CanvasKit sind mehrere Megabyte gross.
- Textlastige Seiten mit Browser-Eigenheiten (Textmarkieren, Barrierefreiheit, Autofill): dort ist HTML/Vue besser.

## Sprache und Stack

- **Dart** (SDK `^3.8.1`) und **Flutter** (stabiler Kanal, Material 3): eine Codebasis, Hot Reload, Widget-Tests.
- **provider ^6** mit `ChangeNotifier` fuer Zustand: einfach, ausreichend, gut testbar. Der Bildschirmzustand liegt in einem Controller (`FinanceDashboardController`).
- **Navigator mit benannten Routen** (`MaterialApp.routes`: `/login`, `/dashboard`, `/finance`): bei drei Seiten genug; bei Deep-Links `go_router` erwaegen.
- **http ^1.6** fuer API-Aufrufe, **shared_preferences ^2.5** fuer Token und Einstellungen (im Web: localStorage).
- **fl_chart ^1** fuer Linien-, Balken- und Kreisdiagramme; **intl ^0.20** fuer Zahlen- und Datumsformate (`de_DE`).
- **flutter_lints ^5** und `flutter analyze` als statische Pruefung; `flutter_test` fuer Unit- und Widget-Tests.
- **Webserver**: Apache im Container (`meine-org/php-app`), SPA-Fallback auf `index.html`.

## Ordnerstruktur

```
app.example.org/
├── source/                      # Flutter-Projekt (Git, Branch master)
│   ├── pubspec.yaml             # Abhaengigkeiten, SDK-Version
│   ├── analysis_options.yaml    # Lints
│   ├── lib/
│   │   ├── main.dart            # Start: Locale, AuthService.init(), MaterialApp, Routen
│   │   ├── auth_service.dart    # Singleton: Login, JWT, Basis-URL, Session-Pruefung
│   │   ├── login_page.dart      # Anmeldeseite
│   │   ├── dashboard_page.dart  # Rahmen mit Bottom-Navigation
│   │   └── features/
│   │       ├── finance/
│   │       │   ├── api/         # FinanceApi (HTTP), HydraCollection (Paging)
│   │       │   ├── models/      # Datenklassen, json_parsing.dart
│   │       │   ├── domain/      # FinanceAggregator (reine Berechnung)
│   │       │   ├── repository/  # FinanceRepository (duenne Weiterleitung)
│   │       │   ├── state/       # FinanceDashboardController (ChangeNotifier)
│   │       │   └── ui/          # Seiten, Views, Formular-Sheets, widgets/, charts/
│   │       ├── stats/ui/        # Kennzahlen-Raster der Startseite
│   │       └── websites/        # API und UI fuer die Website-Verwaltung
│   ├── test/                    # Unit- und Widget-Tests, support/viewport_helpers.dart
│   ├── web/                     # index.html, manifest.json, Icons
│   └── build/web/               # Build-Ausgabe (nicht im Git)
├── current/                     # ausgelieferter Build (ein echtes Verzeichnis)
├── backups/                     # Sicherungen vor jedem Deploy (letzte 3)
├── deploy.sh                    # baut optional und ersetzt current/ per rsync
├── Analyse.md  Context.md  TODO.md
```

## Schichten und Verantwortlichkeiten

- **ui**: Widgets, Formulare als Bottom-Sheets, Diagramme. Keine HTTP-Aufrufe, keine Berechnung.
- **state**: ein `ChangeNotifier` je Seite haelt Auswahl (Monat, Jahr, Konto), geladene Rohdaten und abgeleitete Sicht, ruft `notifyListeners()`.
- **domain**: reine Funktionen (Summen, Gruppierung, Filter), ohne Flutter-Import, schnell testbar.
- **repository**: Schnittstelle zwischen State und API; in Tests ersetzt man sie durch ein Fake.
- **api**: baut URLs aus der Basis-URL, setzt `Authorization: Bearer`, parst Hydra-Sammlungen, wirft `FinanceApiException` mit Statuscode.
- **auth_service**: einziger Ort fuer Token, Anmeldung, Auto-Login und Basis-URL.

## Namens- und Methodenkonventionen

- Dateien `snake_case.dart`, Klassen `UpperCamelCase`, private Member mit `_`. Je Widget-Datei eine Hauptklasse (`finance_overview_view.dart` enthaelt `FinanceOverviewView`).
- Suffixe: `*_page`, `*_view`, `*_section`, `*_form_sheet`, `*_controller`, `*_api`, `*_repository`.
- Tests spiegeln den Namen (`finance_write_path_test.dart`) und nutzen gemeinsame Helfer.

```dart
// Basis-URL zur Build-Zeit festlegen, sonst zeigt die App auf den eigenen Origin
static const String apiBaseUrlOverride =
    String.fromEnvironment('API_BASE_URL', defaultValue: '');

Future<List<Booking>> bookings() async {
  final res = await _client.get(_uri('/api/bookings'), headers: _auth.headers);
  if (res.statusCode != 200) {
    throw FinanceApiException('Buchungen laden fehlgeschlagen',
        statusCode: res.statusCode, responseBody: res.body);
  }
  return HydraCollection.parse(res.body).map(Booking.fromJson).toList();
}
```

```dart
class FinanceDashboardController extends ChangeNotifier {
  Future<void> load() async {
    _loading = true; notifyListeners();
    try { _rawData = await _repository.loadOverview(); _data = _aggregator.apply(_rawData!); }
    catch (e) { _error = e.toString(); }
    finally { _loading = false; notifyListeners(); }
  }
}
```

## Datenhaltung

- Keine lokale Datenbank. Die Wahrheit liegt im Backend; die App haelt Daten im Speicher des Controllers.
- `shared_preferences` speichert JWT und die Option "angemeldet bleiben". Im Web ist das localStorage, also von Skripten derselben Origin lesbar.
- Listen kommen seitenweise als Hydra-Sammlung (`next`-Link); der Client folgt den Links, bis alles geladen ist.
- Beim Laden gemischter Daten (Konten, Buchungen) berechnet `FinanceAggregator` die Sicht; die Rohdaten bleiben unveraendert.

## Fehlerbehandlung und Logging

- API-Fehler als eigene Exception mit Statuscode; die UI zeigt eine Fehlerflaeche (`error_state.dart`) mit Wiederholen, nie ein stilles Schlucken.
- Formulare zeigen Validierungsfehler sichtbar; der Fehlerpfad beim Speichern gibt eine Nutzermeldung aus.
- Wiederkehrende Fehlerklasse "gequetschter Text": breite `leading`/`trailing` in `ListTile` lassen dem Titel zu wenig Platz, der Text bricht buchstabenweise um, ohne dass ein Overflow gemeldet wird. Dafuer gibt es einen eigenen Testhelfer.
- Im Browser hilft die Konsole; Release-Builds enthalten keine Debug-Ausgaben, `print` in Produktivcode vermeiden.
- Server-Seite: Apache-Zugriffslog des Containers; Fehler im Backend stehen im Backend-Log.

## Tests

- `flutter test` fuehrt alle Tests aus; Ziel: alle Tests gruen, Abdeckung wachsend.
- **Viewport-Tests**: `atViewport()` setzt Breiten (300 bis 412 Pixel), `expectFullyVisible()` und `expectTextNotSqueezed()` pruefen Sichtbarkeit und Textumbruch. Bei jedem neuen Listen-Widget beide setzen.
- **Schreibpfad-Tests**: Formular ausfuellen, Speichern antippen, pruefen, dass Repository/API mit richtigem Payload aufgerufen wird. Repository faken, nicht die API.
- **Unit-Tests** fuer Aggregator, Basis-URL-Aufloesung und API-Pfade.
- Hinweise: `pumpAndSettle` haengt bei dauerhaft laufenden Animationen; stattdessen feste `pump(Duration)`-Schritte. Die Standardflaeche von `flutter_test` ist 800x600; breite Views brauchen eine angepasste `physicalSize`.
- Vor dem Deploy: `flutter analyze` (Baseline beachten) und ein Test im echten Browser inklusive Login.

## Sicherheit

- Anmeldung per JWT im `Authorization`-Header (Bearer). Kein Cookie, daher kein klassisches CSRF; XSS wiegt dafuer schwerer, weil das Token im localStorage liegt.
- Regel: Zugangsdaten (Passwort) nie im lokalen Speicher des Browsers ablegen. "Angemeldet bleiben" funktioniert besser mit kurzlebigem Token plus Refresh-Mechanismus oder httpOnly-Cookie.
- Backend muss CORS fuer die App-Origin freigeben, einschliesslich `PATCH` und `DELETE`; fehlende Methoden zeigen sich als scheinbar defekte Schreibaktionen (Preflight liefert 405).
- Die App-Domain hat keinen Auth-Proxy davor, weil sie sich selbst anmeldet; Schutz liegt komplett im Backend.
- Security-Header (CSP, `X-Content-Type-Options`, `Referrer-Policy`) am Webserver setzen. Flutter Web braucht fuer CanvasKit `wasm-unsafe-eval` bzw. Skript-Erlaubnis fuer die eigene Origin.
- Keine Schluessel im Dart-Code: alles im Client ist fuer Nutzer lesbar.

## Konfiguration und Geheimnisse

- Konfiguration zur Build-Zeit mit `--dart-define=API_BASE_URL=https://<backend>`; ohne den Parameter fragt die App den eigenen Origin an (statische Dateien antworten mit 405, der Login scheitert).
- Es gibt keine `.env` im Flutter-Projekt; Werte sind keine Geheimnisse, weil sie im Bundle stehen.
- Zugangsdaten und Tokens des Backends gehoeren in die Secret-Verwaltung und nie in `source/`.

## Deploy

Platzhalter in spitzen Klammern (`<STACK>`, `<auth-middleware>`, `<https-redirect>`, `meine-org/...`, `*.example.org`) sind durch die eigene Umgebung zu ersetzen. Die Beispiele gehen von Docker, Traefik als Reverse Proxy und einem externen Docker-Netzwerk `web` aus; andere Proxys und Orchestrierungen funktionieren sinngemäß genauso.

**Klassischer Ablauf:** `deploy.sh` baut (`flutter build web --release --dart-define=API_BASE_URL=...`, Flutter-SDK per Snap) oder uebernimmt einen fertigen `build/web`-Ordner. Danach: Sicherung des alten Stands nach `backups/pre_deploy_<Zeit>`, `rsync --checksum --delete` nach `current/`, Rechte `www-data`, 755 fuer Ordner und 644 fuer Dateien, Pruefung mit `cmp`, nur die letzten 3 Sicherungen bleiben. Der Ablauf ist **in-place**, kein Symlink-Wechsel, weil `current` ein echtes Verzeichnis ist; ein Symlink-Deploy wurde bewusst zurueckgestellt.

Ausgeliefert wird nicht aus einem eigenen Container, sondern vom gemeinsamen Apache im Container `php-app` (Host-Netz, interner Port), per Traefik-Router (Datei `php-app.yml`: Host-Regel, `websecure`, Zertifikat `le`, Weiterleitung von HTTP auf HTTPS). Der Vhost zeigt auf `current/` mit `FallbackResource /index.html` fuer den SPA-Fallback.

**Cache-Regeln:** `canvaskit/` darf lange gecacht werden (30 Tage); `main.dart.js`, `flutter_bootstrap.js`, `flutter_service_worker.js` und `index.html` haben keine Versionsnummer im Namen und brauchen `no-cache` mit ETag. Liefert der Server sie mit `immutable` und einem Jahr aus, sieht der Browser nach dem Deploy den alten Build.

**Ziel (Docker + Traefik):** Multi-Stage-Image (Flutter-Build-Stage, dann `nginx` oder Caddy mit den Dateien), eigener Compose-Dienst mit Labels fuer Router, TLS, Healthcheck auf `/` und Security-Header als Traefik-Middleware; Releases sind Image-Tags, Rollback = vorheriger Tag. Der Build laeuft in CI statt auf dem Server (das SDK kostet 1 bis 2 GB, der Build braucht Arbeitsspeicher oder Swap).

## Typische Fehler

- **Falscher Hostname im Build**: `--dart-define=API_BASE_URL` vergessen, Login ruft die App-Domain statt des Backends (HTTP 405). Kein Test findet das, nur eine Pruefung im Browser.
- **Veralteter Build im Browser** wegen falscher Cache-Header oder Service Worker; nach dem Deploy hart neu laden und Header pruefen.
- **CORS**: Schreibaktionen (`PATCH`) scheitern, obwohl der Dart-Code stimmt; Preflight gegen das Backend pruefen.
- **`current` ist ein Verzeichnis**: ein Skript mit `ln -sfn` legt den Link in das Verzeichnis statt es zu ersetzen.
- **Mobile Layout**: unbeschraenkte `Row`-Breiten, `DropdownButtonFormField` ohne `isExpanded`, Filterleisten ohne `Flexible`/`Wrap` verursachen Overflow oder gequetschten Text.
- **`pumpAndSettle` in Tests** mit dauerhaft laufender Animation (Session-Fortschritt) laeuft in ein Timeout.
- **Fakes auf falscher Ebene**: Repository-Methoden, die nicht ueber eine gemeinsame Funktion laufen, rufen unbemerkt die echte API auf (Netzwerk im Test gesperrt, HTTP 400).
- **Analyzer-Baseline** wird ignoriert: neue Warnungen gehen in den alten unter.
- **Build ohne genug RAM**: ohne Swap bricht `flutter build web` auf dem Server ab.
- **Abgehakte Reviews ohne Review**: Qualitaetsschritte nicht nachtraeglich als erledigt markieren.

### Verbesserungen für neue Projekte

- Zugangsdaten nie speichern; nur ein Refresh-Token in einem `HttpOnly`-Cookie oder kurzlebiges Token, dazu CSP.
- Build in CI und als Image, `API_BASE_URL` als Pipeline-Variable; Deploy ueber Image-Tag statt `rsync`.
- Eigener Compose-Dienst mit Healthcheck, Security-Header und Cache-Regeln im Image.
- `go_router` mit Deep-Links und geschuetzten Routen; Zustand mit einem durchgaengigen Muster (`provider` oder Riverpod).
- Einheitliche Fehlerklasse fuer alle APIs statt je Feature eine.
- Viewport-Tests von Anfang an in der CI; Analyzer-Baseline auf null.
- Flutter-Version im Repo fixieren (z. B. FVM) und `pubspec.lock` einchecken.
- Dokumentation (Context.md) bei Infrastrukturwechseln sofort nachziehen.

## Checkliste

- `flutter pub get`, `flutter analyze` und `flutter test` laufen sauber.
- Build mit `--release` und `--dart-define=API_BASE_URL=<Backend>`.
- Backend: CORS fuer die App-Origin mit allen genutzten Methoden.
- Webserver: SPA-Fallback auf `index.html`, TLS ueber Traefik.
- Cache: `no-cache` mit ETag fuer unversionierte Dateien, lange Laufzeit nur fuer `canvaskit/`.
- Vor dem Deploy Sicherung; Rotation der Sicherungen.
- Dateirechte `www-data`, 755/644 nach dem Kopieren.
- Nach dem Deploy: Login im echten Browser, ein Schreibvorgang, Hash von `main.dart.js` mit dem Build vergleichen.
- Handy-Breiten 360, 375 und 412 Pixel geprueft.
- Keine Zugangsdaten oder Schluessel im Code.
- Rollback-Weg vorhanden (Sicherung oder Image-Tag).
