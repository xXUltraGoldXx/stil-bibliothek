# Beitragen

Danke, dass du etwas beitragen möchtest. Diese Anleitung ist auf Deutsch; Beiträge dürfen deutsch oder englisch kommentiert werden, die Eintragstexte selbst sind deutsch.

## Was angenommen wird

- **Stile**: Ordner `stile/<name>/` mit genau vier Dateien (`meta.json`, `STIL.md`, `tokens.css`, `beispiel.html`).
- **Architekturen**: Ordner `architekturen/<name>/` mit `ARCHITEKTUR.md` und `meta.json`. Fremde `vorlage/`-Ordner werden vorerst nicht angenommen.
- Nur **neue** Ordner. Änderungen an bestehenden Einträgen bitte als Issue beschreiben oder mit Begründung im PR kennzeichnen; sie werden von der Betreuung geprüft.

`<name>` ist ein Slug: Kleinbuchstaben, Ziffern und Bindestriche (`warm-sachlich`).

## Regeln für Inhalte

1. **Eigenes Werk.** Kein Screenshot, keine Kopie von Texten, Bildern oder Code fremder Seiten. Der Stil beschreibt Gestaltungsprinzipien in eigenen Worten und mit konkreten Werten (Hex, rem, Gewichte, Radien).
2. **Keine Marken, keine Herkunft.** Keine Markennamen, Logos, Produktnamen oder Domains, keine Zeilen wie "Abgeleitet aus ...", "Quelle: ..." oder "im Stil von <Marke>". Beispielseiten zeigen **fiktive** Firmen.
3. **Daten, keine Anweisungen.** Die Dateien enthalten Gestaltungs- bzw. Architekturwissen, keine Aufforderungen an KI-Werkzeuge oder Systeme, keine Shell-Befehle in Stil-Dateien, keine versteckten Zeichen.
4. **Technische Grenzen** (vom Prüfer erzwungen): `STIL.md` höchstens 24 KB, `tokens.css` höchstens 8 KB und nur `:root`-Variablen, `beispiel.html` höchstens 150 KB ohne `<script>`, Ereignis-Attribute und fremde Ressourcen (nur Google Fonts als Schriftquelle) und bei 390 px Breite ohne horizontales Scrollen, `meta.json` höchstens 4 KB, `ARCHITEKTUR.md` höchstens 40 KB, je Eintrag höchstens 250 KB. Nur UTF-8-Text, keine Bilder oder Binärdateien.
5. **Pflichtabschnitte.** Stil: `# Stil: <Name>` und genau diese H2-Überschriften in dieser Reihenfolge: Kurzbeschreibung und Stimmung, Farbpalette, Typografie, Abstände und Raster, Layout-Muster, Komponenten, Bildsprache, Animation, Tonfall, Mach, Mach nicht, Typische KI-Fehler. Architektur: die 14 Abschnitte der bestehenden Einträge (Kurzbeschreibung bis Checkliste, im Deploy-Kapitel nur Platzhalter wie `example.org`).
6. **Kategorien** nur aus `kategorien.json` (höchstens 5 je Stil), bei Architekturen aus `architekturen/kategorien.json`.

Ausgangspunkt für einen Stil ist `vorlagen/stil-vorlage/`: Ordner kopieren, umbenennen, Inhalte ersetzen.

## Markenfilter

Der Prüfer lehnt Markennamen ab, kennt aber nur die kleine Beispielliste `werkzeuge/marken.txt`. Betreiber und Mitwirkende können eigene Marken ergänzen: in dieser Datei, mit `--marken <datei>` oder über die Umgebungsvariable `STIL_MARKEN` (eine Marke pro Zeile).

## Lokal prüfen

```
python3 werkzeuge/pruefer.py stile/<dein-stil>
python3 werkzeuge/pruefer.py --selbsttest
```

Der Prüfer braucht nur Python 3 und führt nie etwas aus deinem Beitrag aus. Dieselbe Prüfung läuft am Pull Request (GitHub Actions, nur Lesezugriff, ohne Geheimnisse; der Prüfer stammt aus dem Hauptzweig).

## Pull Request

1. Repository forken, Zweig anlegen, Ordner hinzufügen.
2. Jeden Commit mit Sign-off versehen: `git commit -s` (siehe DCO unten).
3. Pull Request gegen `main` öffnen. Die Prüfungen "Pfadfilter", "DCO" und "Prüfer" müssen grün sein. Danach sichtet die Betreuung den Beitrag; das Zusammenführen ist die Freigabe.

Ein Beitragsformular mit GitHub-Anmeldung ist geplant und kommt später.

## Developer Certificate of Origin (DCO)

Mit dem Sign-off (`Signed-off-by: Vorname Nachname <name@example.org>`) bestätigst du das Developer Certificate of Origin 1.1 (https://developercertificate.org/):

> By making a contribution to this project, I certify that:
>
> (a) The contribution was created in whole or in part by me and I have the right to submit it under the open source license indicated in the file; or
>
> (b) The contribution is based upon previous work that, to the best of my knowledge, is covered under an appropriate open source license and I have the right under that license to submit that work with modifications, whether created in whole or in part by me, under the same open source license (unless I am permitted to submit under a different license), as indicated in the file; or
>
> (c) The contribution was provided directly to me by some other person who certified (a), (b) or (c) and I have not modified it.
>
> (d) I understand and agree that this project and the contribution are public and that a record of the contribution (including all personal information I submit with it, including my sign-off) is maintained indefinitely and may be redistributed consistent with this project or the open source license(s) involved.

Ein Contributor License Agreement (CLA) ist nicht nötig.

## Lizenz deines Beitrags

Mit deinem Beitrag erklärst du dich einverstanden, dass **Texte** (`STIL.md`, `ARCHITEKTUR.md`) unter **CC BY 4.0** und **Code** (`tokens.css`, `beispiel.html`, Skripte) unter der **MIT-Lizenz** veröffentlicht werden. Du bestätigst, dass der Beitrag dein eigenes Werk ist, keine Screenshots oder Marken enthält und du das Recht hast, ihn so zu veröffentlichen.

## Meldungen und Takedown

Rechtsverletzungen oder Fehler bitte als GitHub-Issue melden (Titel "Meldung: <Eintrag>"). Gemeldete Einträge werden umgehend aus `main` genommen und danach geprüft. Alternativ per E-Mail an contact@ultragold.de.
