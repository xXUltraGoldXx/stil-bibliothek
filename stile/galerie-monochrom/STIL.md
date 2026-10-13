# Stil: Galerie monochrom

## Kurzbeschreibung und Stimmung
Ein kuratiertes, ausstellungsartiges Interface: Der Grund ist ein sehr helles Grau (#f8f8f8), Text und Primärflächen sind fast schwarz (#222222). Die Bühne gehört den Inhalten (Projektbilder, Karten, Rankings); die Oberfläche tritt zurück. Einziger lauter Moment ist der gewaltige Versal-Titel (bis 112 px, Gewicht 600, Zeilenhöhe 1.0). Alles andere ist leicht (Gewicht 300), ruhig und sachlich. Farbe kommt nur als kleine, bewusst gesetzte Pastell- oder Signalfläche vor. Schatten gibt es nicht; Tiefe entsteht durch Grauabstufungen, dünne Linien und eine dunkle Überlagerung (rgba(0,0,0,.7)) hinter Dialogen.

## Farbpalette
- Grund: #f8f8f8 (Seite), #ededed (Rahmen, Suchfeld, Chips-Hintergrund), #e9e9e9 (flächige Absetzung), #ffffff (Karten, Eingabefelder).
- Tinte: #222222 für Text, Primärbutton, dunkle Abschnitte und Dock-Navigation. Sekundärtext auf Dunkel: #dedede. Auf Dunkel Weiß #ffffff.
- Linien: 1 px #ededed (hell), 1 px #222222 (Outline-Button, Tags), 1 px rgba(255,255,255,.3) auf Dunkel.
- Signal: #ee6a38 (Orange, Fehler, Zähler und kleine Marker, höchstens 2 % der Fläche).
- Kategorie-Pastelle, nur als kleine Flächen oder Karten-Hintergründe: Mint #aaeec4 / #e2f4e9, Gelb #fff083 / #fffbe2, Korall #ffc5b1, Himmelblau #b4d7f8, Violett #502bd8 nur als einzelner Punkt oder Badge.
- Überlagerung: rgba(0,0,0,.7) hinter Dialogen; Glasflächen rgba(255,255,255,.9).
- Kein Verlauf, außer einem harten Kantenverlauf (10 % dunkel, Rest transparent) als Fortschrittsbalken.

## Typografie
- Schrift: Inter Tight (Google Fonts, Gewichte 300 bis 700), Rückfall system-ui, sans-serif.
- H1: Versalien, 600, Zeilenhöhe 1.0, Größe clamp(2.75rem, 9vw, 7rem) (Desktop 112 px, Mobil 42 px), Laufweite normal.
- H2 und H3 (Abschnitt): 600, 1.5 bis 2.5 rem, Zeilenhöhe 1.15; Versalien nur bei Haupttiteln.
- Fließtext: 300, 0.9375 rem (15 px), Zeilenhöhe 28 px (1.87), Maximalbreite 62ch.
- UI-Text (Navigation, Links, Buttons): 14 px, Gewicht 400 bis 500; Navigation 500.
- Meta/Label: 11 bis 13 px, Gewicht 400 bis 500, keine Versalien, keine Sperrung.
- Hervorhebung durch Gewicht 600, nicht durch Kursiv. Links in Fließtext: Gewicht 600 mit 1 px Unterstreichung in 30 % Tinte.
- Großer Kontrast der Größen: 15 px Text gegen 112 px Titel, wenig Zwischenstufen (18, 20, 24, 39 px).

## Abstände und Raster
- Basis 4 px; gängige Werte: 8, 12, 20, 24, 32, 51 px (0.5, 0.75, 1.25, 1.5, 2, 3.2 rem).
- Seitenrand: 10 px bei vollbreiten Bildflächen, 50 px (Desktop) bzw. 20 px (Mobil) bei Navigation und Text.
- Spaltenabstand (Gutter) 20 px; Kartenabstand 20 px; Inhalte in Karten 24 bis 32 px Innenabstand.
- Maximalbreite Inhalt 1200 px; Bildflächen dürfen fast randlos bis 1260 px laufen.
- Kopfzeile 54 bis 71 px hoch. Eingabefelder 48 px hoch, 16 px seitlicher Innenabstand.
- Radien: 4 px (Tags), 8 px (Standard: Buttons, Karten, Bilder), 14 px (Dialoge, große Karten), 50 % (Avatare, Punkte).
- Abschnitte vertikal 64 bis 96 px Abstand, mobil 48 px.

## Layout-Muster
- Kopfzeile: Logo links, Hauptnavigation daneben, mittig breites Suchfeld (#ededed, 8 px Radius), rechts Textlinks und zwei Buttons (ein gefüllter dunkler, ein Outline).
- Hero: zentrierte Kleinzeile (Datum-Tag, Kategorie), darunter riesiger Versal-Titel, darunter fast randloses Vollbild mit 8 px Radius und eingelegter weißer Karte.
- Danach Kartenraster 3 bis 4 Spalten mit Seitenverhältnis 16 / 12; Vorschaubild oben, darunter Titel (600) und Meta (300) in einer Zeile mit Avatar.
- Abwechselnd helle und dunkle (#222) Vollflächen als Rhythmus; auf Dunkel weißer Text.
- Schwebende Dock-Navigation unten mittig: dunkle Leiste (#222), 14 px Radius, Segmente mit Text, rechts ein heller Hauptsegment-Button.
- Mobil: alle Spalten stapeln sich einspaltig, Navigation wird zu Menü-Button, Titel 42 px.

## Komponenten
- Primärbutton: Hintergrund #222, Text #fff, 14 px / 400, Höhe 48 bis 60 px, Innenabstand 0 24 px, Radius 8 px, kein Schatten. Hover: #3e3e3e.
- Outline-Button: transparent, 1 px #222, Radius 8 px, gleiche Maße.
- Textlinks: 14 px, 500, Unterstreichung 1 px erst bei Hover oder als Dauerlinie bei Dialog-Links.
- Tag/Chip: 1 px #222 oder Hintergrund #ededed, Radius 4 px, 13 px Text, Innenabstand 2 8 px.
- Badge „neu": dunkles Feld #3e3e3e, weißer Text 10.5 px, Radius 4 px.
- Karte: Weiß (#fff), Radius 8 bis 14 px, keine Linie oder 1 px #ededed, kein Schatten.
- Suchfeld: #ededed, Radius 8 px, 42 bis 48 px hoch, Lupe links (38 px Einzug).
- Dialog: Weiß/#f8f8f8, 840 px breit, Radius 14 px, 38 px Innenabstand, Titel 20 px / 600, Text 15 px / 300; Hauptbutton links, zwei unterstrichene Textlinks rechts; Überlagerung rgba(0,0,0,.7).
- Dock-Navigation: #222, Segmente mit Hintergrund #3e3e3e, Text #dedede 13 px.

## Bildsprache
- Große, dichte Fotos und Screenshots von Arbeiten, randnah, immer mit 8 px Radius. Bilder dürfen unscharf und abgedunkelt als Hintergrund dienen.
- Auf Karten Seitenverhältnis 16 / 12, im Panorama 2 / 1 oder 19 / 10.
- Logos erscheinen als kleine, einfarbig dunkle Zeichen auf hellem Feld im Raster.
- Avatare rund, 32 px.
- In Platzhaltern: einfache Grauflächen (#e9e9e9 bis #cfcfcf) mit leichtem Diagonalverlauf oder Pastellfläche.

## Animation
- Zurückhaltend und funktional: Hover auf Karten mit leichtem Bildzoom (scale 1.03, 400 ms, ease-out), Buttons wechseln Farbe in 200 ms.
- Dock-Navigation blendet beim Scrollen ein (Verschieben um 16 px plus Einblenden, 300 ms).
- Dialoge blenden mit der Überlagerung in 250 ms ein.
- Keine Dauerschleifen, kein Parallax-Spektakel; prefers-reduced-motion respektieren.

## Tonfall
Sachlich, knapp, kuratorisch. Kurze Etiketten statt Sätze („Projekt der Woche", „Kategorie: Webdesign"). Direkte Ansprache in Buttons mit zwei bis drei Wörtern. Keine Ausrufezeichen, kein Marketing-Überschwang, Zahlen und Daten als Beleg.

## Mach
- Titel in Versalien, 600, Zeilenhöhe 1.0, so groß wie der Platz erlaubt.
- Fließtext 300 mit 28 px Zeilenhöhe in #222 auf #f8f8f8.
- Radius 8 px konsequent für Buttons, Karten und Bilder.
- Dunkle #222-Flächen im Wechsel mit hellen Abschnitten.
- Farbe nur als kleine Kategorie-Pastelle oder Orange (#ee6a38) als Signal.
- Bildflächen fast randlos (10 px Rand) und möglichst groß.
- Dünne 1-px-Linien in #ededed statt Schatten.

## Mach nicht
- Keine Schatten, keine Glüheffekte, keine Verläufe in Flächen.
- Keine Serifenschrift und keine zweite Schriftfamilie.
- Keine großen Pastellflächen als Seitenhintergrund.
- Keine Gewichte unter 300 im Fließtext, keine Kursive.
- Keine runden Pillen-Buttons; Radius bleibt 8 px.
- Keine Sperrschrift und keine Versalien im Fließtext.
- Nicht mehr als ein Signal-Orange-Element pro Bildschirm.

## Typische KI-Fehler in diesem Stil
- Weißen Grund (#fff) statt #f8f8f8 verwenden: dadurch verschwindet die Abstufung zu weißen Karten.
- Weiche Schatten unter Karten ergänzen; der Stil kommt ganz ohne aus.
- Den Titel zu klein setzen (unter 64 px Desktop) oder mit Laufweite und normalem Gemischtschreiben abschwächen.
- Pillenförmige Buttons und 24-px-Radien nehmen statt 8 px.
- Fließtext in Gewicht 400 setzen, so verliert sich die leichte Anmutung gegen den 600er Titel.
- Zu viele Akzentfarben gleichzeitig; Pastelle nur klein und jeweils eine pro Kategorie.
- Dock-Navigation oder Dialog vergessen, die den dunklen Gegenpol zur hellen Seite bilden.
