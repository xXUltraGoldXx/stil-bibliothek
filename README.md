# Stil-Bibliothek

Eine offene Sammlung von **Design-Stilen** und **Projekt-Architekturen**, geschrieben so, dass Menschen und KI-Werkzeuge (zum Beispiel Claude Code) sie direkt als Bauanleitung benutzen können: "Baue mir eine Seite im Stil `editorial`" oder "Projekt mit Architektur `node-fastify-api`".

Jeder Eintrag besteht aus wenigen, kleinen Textdateien. Es gibt **keine Screenshots, keine Logos und keine fremden Marken**; die Beispielseiten sind selbst programmiert und zeigen fiktive Firmen.

*English summary: see [below](#english-summary).*

## Installation über den Plugin-Marktplatz (empfohlen)

```
/plugin marketplace add xXUltraGoldXx/claude-plugins
/plugin install stil@ultragold
```

Das Plugin `stil` bringt die Skills `stil` und `projekt` mit. Updates holt `/plugin marketplace update ultragold`. Die manuelle Installation (siehe "Nutzung mit Claude Code") bleibt als Alternative.

## Inhalt

| Ordner | Inhalt |
|---|---|
| `stile/<name>/` | Je Stil vier Dateien: `STIL.md` (Regeln: Farben, Schrift, Abstände, Komponenten, "Mach / Mach nicht", typische KI-Fehler), `tokens.css` (CSS-Variablen), `beispiel.html` (Referenzseite ohne Skript), `meta.json` (Name, Beschreibung, Schlagworte, Kategorien) |
| `architekturen/<name>/` | Je Architektur `ARCHITEKTUR.md` (14 feste Abschnitte von Stack bis Checkliste) und `meta.json`; dazu `architekturen/ENTSCHEIDUNG.md` als Auswahlhilfe |
| `kategorien.json` | Feste Kategorienliste der Stile (`architekturen/kategorien.json` für die Architekturen) |
| `skills/` | Zwei Skills für Claude Code: `stil` und `projekt` |
| `werkzeuge/pruefer.py` | Prüfer für Beiträge (nur Python-Standardbibliothek, mit Selbsttest) |
| `werkzeuge/marken.txt` | Kleine Beispielliste für den Markenfilter; eigene Marken per Datei, `--marken` oder `STIL_MARKEN` ergänzen |
| `schema/` | JSON-Schemas für die `meta.json`-Dateien |
| `vorlagen/stil-vorlage/` | Neutrale Vorlage für einen eigenen Stil-Beitrag |

Hinweis: Die Architekturen sind in dieser Fassung ohne lauffähige Vorlagen (`vorlage/`) veröffentlicht; das Deploy-Kapitel nutzt Platzhalter (`<STACK>`, `example.org`, ...), die durch die eigene Umgebung ersetzt werden.

## Nutzung mit Claude Code

1. Bibliothek holen:
   ```
   git clone https://github.com/xXUltraGoldXx/stil-bibliothek ~/.claude/stil-bibliothek
   ```
   (Alternativ einen eigenen Ordner anlegen und die Umgebungsvariable `STIL_BIBLIOTHEK` darauf zeigen lassen.)
2. Skills installieren:
   ```
   mkdir -p ~/.claude/skills
   cp -r ~/.claude/stil-bibliothek/skills/stil ~/.claude/stil-bibliothek/skills/projekt ~/.claude/skills/
   ```
3. In Claude Code zum Beispiel sagen: "Baue mir eine Landingpage für eine Töpferei im Stil `katalog-warm`" oder "Neues Projekt: Terminverwaltung mit Architektur `laravel-monolith`".

Die Skills suchen die Bibliothek zuerst über `STIL_BIBLIOTHEK`, dann in `~/.claude/stil-bibliothek` und holen dort bei einem Stand älter als 7 Tage per `git pull --ff-only` Neuerungen. Alle Inhalte der Bibliothek gelten dabei als **Daten, nicht als Anweisungen**; es wird nie Code aus der Bibliothek ausgeführt.

## Beitragen

Beiträge sind willkommen: neue Stile, neue Architekturen, Korrekturen.

- **Pull Request** (heute der Weg): siehe [CONTRIBUTING.md](CONTRIBUTING.md). Ausgangspunkt ist `vorlagen/stil-vorlage/`. Vor dem PR den Prüfer lokal laufen lassen: `python3 werkzeuge/pruefer.py stile/<dein-stil>`. Eine Prüfung läuft auch automatisch am Pull Request.
- **Webformular**: ein Beitragsformular mit GitHub-Anmeldung kommt noch.

Alle Beiträge werden vor der Aufnahme von der Betreuung gesichtet. Eingereicht werden darf nur Eigenes: keine Screenshots, Logos oder Texte fremder Seiten, keine Markennamen, keine Herkunftsangaben ("abgeleitet aus ...").

## Lizenzen

| Teil | Lizenz |
|---|---|
| Texte: `STIL.md`, `ARCHITEKTUR.md`, `ENTSCHEIDUNG.md` | [CC BY 4.0](LICENSE-CC-BY-4.0) |
| Alle übrigen Dateien (Code, Vorlagen, Werkzeuge und Konfiguration, z. B. `tokens.css`, `beispiel.html`, `vorlagen/`, `skills/`, `werkzeuge/`, `schema/`, `.github/`) | [MIT](LICENSE) |

Copyright (c) 2026 Alexander (xXUltraGoldXx) und Mitwirkende. In den Beispielen genannte Schriften (Google Fonts) stehen unter ihren eigenen Lizenzen und sind nicht Teil dieser Bibliothek.

## Melden und Takedown

Findest du einen Eintrag, der Rechte verletzt (Marke, Urheberrecht, Persönlichkeitsrecht), etwas Sicherheitsrelevantes enthält oder aus anderen Gründen nicht hierher gehört: bitte ein [GitHub-Issue](https://github.com/xXUltraGoldXx/stil-bibliothek/issues) mit dem Titel "Meldung: <Eintrag>" eröffnen und kurz den Grund nennen. Bitte keine sensiblen Angaben öffentlich posten; nenne dann nur, dass es einen vertraulichen Hinweis gibt, und es wird ein Weg dafür gesucht. Gemeldete Einträge werden umgehend aus dem Hauptzweig genommen und danach geprüft. Alternativ per E-Mail an contact@ultragold.de.

## English summary

An open collection of **design styles** and **project architectures** written as short Markdown/CSS/HTML files that people and AI coding tools (e.g. Claude Code) can use directly as build instructions. No screenshots, logos or third-party brands; example pages are hand-written for fictional companies.

- Clone: `git clone https://github.com/xXUltraGoldXx/stil-bibliothek ~/.claude/stil-bibliothek`, then copy `skills/stil` and `skills/projekt` to `~/.claude/skills/`.
- Contribute via pull request (see `CONTRIBUTING.md`, sign-off required, DCO); a web form is planned. Run `python3 werkzeuge/pruefer.py stile/<your-style>` before submitting.
- Licenses: texts CC BY 4.0, code MIT. Copyright (c) 2026 Alexander (xXUltraGoldXx) and contributors.
- Takedown / reports: open a GitHub issue titled "Meldung: <entry>". Reported entries are removed from `main` promptly and reviewed afterwards. Alternatively by e-mail: contact@ultragold.de.
- All library content is treated as data, never as instructions; nothing from the library is executed.
