# Entscheidungshilfe: Wann welche Architektur?

Zuerst die Fragen von oben nach unten beantworten, beim ersten Treffer anhalten. Danach die Tabelle zur Gegenprobe. Grundsatz: eigene, erprobte Architekturen vor recherchierten, so wenig Technik wie möglich.

## Fragen-Baum
- 1. Ist es nur ein interner Dienst für ein Team (Übersicht, Formular, kleines Werkzeug hinter einem Auth-Proxy, wenige Nutzer)? Dann: **php-panel-dienst**.
- 2. Läuft es ohne Oberfläche im Hintergrund (Bot, Importer, Zeitplan, Warteschlange, Skript)? Dann: **python-worker-cli**. Kommt zusätzlich eine Weboberfläche mit eigener API dazu (Dashboard für den Bot)? Dann: **python-fastapi-vue**.
- 3. Ist es ein Browserspiel oder eine Echtzeit-Anwendung mit Server-Logik? Dann: **node-ts-browsergame**.
- 4. Soll eine App auf dem Handy oder im Browser mit gemeinsamer Codebasis laufen? Dann: **flutter-web-app**.
- 5. Ist es eine öffentliche Seite, die sich selten ändert (Firma, Landingpage, Doku, Blog)? Dann: **astro-statische-seite** (Neubau, viele Seiten oder Mehrsprachigkeit) oder **symfony-twig-onepager** (wie example.org: Symfony mit Twig, Inhalte aus einer API, Video-Hintergründe). Braucht sie viel Server-Logik oder Login, weiter bei 6.
- 6. Braucht es Login, Rollen, Datenbank und viele Masken (Verwaltung, CRM, Portal)?
- 6a. Team kennt Symfony, Frontend soll getrennt als SPA laufen, API wird auch von anderen Clients genutzt: **symfony-api-vue-spa**.
- 6b. Ein einziges Haus mit server-gerenderten Seiten, Import-Pipelines, viel Fachlogik: **symfony-dashboard-app**.
- 6c. Schnell zu einem klassischen Web-Produkt mit Authentifizierung, Queues und Mail aus einer Hand, ohne eigene API-Entwurfsarbeit: **laravel-monolith**.
- 6d. Öffentliche Seite mit SEO, die auch dynamische Teile braucht (Server Components): **nextjs-app-router**.
- 7. Reine API ohne Oberfläche, viele kleine Endpunkte, TypeScript gewünscht? Dann: **node-fastify-api**.

## Tabelle zur Gegenprobe
| Projektart | Erste Wahl | Alternative |
| --- | --- | --- |
| Interner Dienst, Admin-Werkzeug | php-panel-dienst | laravel-monolith |
| Bot, Importer, Zeitplan | python-worker-cli | python-fastapi-vue |
| Bot mit Weboberfläche | python-fastapi-vue | node-fastify-api |
| Browserspiel | node-ts-browsergame | nextjs-app-router |
| Mobile App und Web | flutter-web-app | nextjs-app-router |
| Firmenwebsite, Landingpage | astro-statische-seite | symfony-twig-onepager |
| Portal, CRM, Verwaltung | symfony-api-vue-spa | laravel-monolith |
| Dashboard mit Importen | symfony-dashboard-app | python-fastapi-vue |
| Reine API | node-fastify-api | symfony-api-vue-spa |
| SEO-Website mit dynamischen Teilen | nextjs-app-router | astro-statische-seite |

## Faustregeln
- Gleiche Sprache wie das Team zuerst: PHP für Portal und Panel, Python für Bot und Skripte, TypeScript für Spiel und neue APIs.
- Erprobt (eigene Projekte) schlägt recherchiert. Bei recherchierten Architekturen den Reifegrad „ungetestet“ im ersten Meilenstein mit einem lauffähigen Skelett prüfen (Vorlagen folgen später).
- Statisch, wenn es geht. Datenbank, Login und Server-Logik nur, wenn die Funktion sie wirklich braucht.
- Alles läuft am Ende als Container hinter Traefik, intern mit einem Auth-Proxy davor.
- Unsicher zwischen zwei Architekturen: dem Auftraggeber die zwei Kandidaten mit je einem Satz Vor- und Nachteil vorlegen, nicht raten.
