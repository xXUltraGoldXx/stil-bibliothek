# Stil: Verlauf freundlich

## Kurzbeschreibung und Stimmung
Ein heller, einladender Werkzeug-Auftritt für kreative Software. Der Einstieg ist ein vollflächiger Farbverlauf von Violett über Blau und Türkis bis zu einem hellen Lavendel. Darauf steht eine große, weiße Frage in der Mitte, darunter ein heller Pill-Knopf und eine Reihe leicht gekippter, bunter Sticker. Danach wechseln weiße Abschnitte mit einzelnen sehr dunklen Blöcken (`#0f1015`). Gefühl: zugänglich, spielerisch, aber professionell genug für Teams.

## Farbpalette
- Hintergrund hell `#ffffff`, Verlaufsausklang `#f6f7f8` und `#f1ebff`
- Tinte `#0f1015`, sekundärer Text `rgba(15,16,21,.85)` und `rgba(16,18,25,.7)`
- Dunkle Fläche `#0f1015` mit Text `#ffffff` und `rgba(255,255,255,.9)`
- Link- und Akzentviolett `#8947f0`, Violett-Start `#992bff`, Indigo `#5a32fa`
- Türkis `#13a3b5`, Eisblau `#93e8f6`, Cyan `#12bcc4`
- Hero-Verlauf von oben nach unten: `#992bff` 0%, `#5a32fa` 30%, `#13a3b5` 57%, `#93e8f6` 77%, `#f1ebff` 95%
- Knopf-Verlauf quer: `#12bcc4`, `#5a32fa`, `#7332d8`
- Kachelfarben als Flächen: Rosa `#ffd6d8`, Butter `#ffe9ac`, Koralle bis Rot `#ff697a` bis `#eb2139`, Orange `#fec19c` bis `#ff6108`, Blau `#0a87cc` bis `#97e1ee`

## Typografie
- Schrift: Figtree, Rückfall Helvetica, Arial, sans-serif
- Hero-Frage: 4rem bis 5rem, Gewicht 500, Zeilenhöhe 1.1, Laufweite -0.01em
- H2: 2.25rem bis 3.5rem, Gewicht 600, Zeilenhöhe 1.1, Laufweite -0.01em
- Zwischentitel: 1.75rem, Gewicht 500, Zeilenhöhe 1.25
- Text: 1rem bis 1.125rem, Gewicht 400, Zeilenhöhe 1.5
- UI und Menü: 0.875rem, Gewicht 500 bis 600, Zeilenhöhe 1.55
- Kleines Label: 0.6875rem, Gewicht 700, Versalien, Laufweite 0.1em
- Überschriften nie fett über 600, Größe trägt die Hierarchie

## Abstände und Raster
- Basis 4px: 4, 8, 12, 16, 24, 32, 48, 72
- Seitenrand 3rem Desktop, 1.25rem mobil. Inhaltsbreite 1216px, Hero-Text bis 980px
- Abschnitte vertikal 4.5rem bis 6rem
- Raster 3 bis 4 Spalten, Lücke 1.5rem. Karten innen 1.5rem bis 2rem
- Mobil: eine Spalte, Sticker-Reihe bricht in 2 bis 3 Spalten um

## Layout-Muster
- Kopfzeile transparent auf dem Verlauf: Logo links, Menü mittig, zwei Pill-Knöpfe rechts
- Hero: zentrierte Frage, ein Satz Unterzeile, ein heller Hauptknopf, darunter zwei versetzte Reihen schwebender Sticker (je 5 und 4, leicht gedreht)
- Danach: weißer Abschnitt mit Feature-Kacheln, ein dunkler Block mit großem Aussagesatz, ein Verlaufsband als Aufruf, Fußzeile mit vielen Link-Spalten
- Abwechslung: links Text, rechts Vorschau-Fläche, dann gespiegelt

## Komponenten
- Hauptknopf im Hero: Fläche `#ebecff`, Text `#0f1015`, Gewicht 600, Radius 12px, Höhe 3.4rem, innen 0 1.75rem, Schatten `0 2px 5px rgba(21,30,130,.12), 0 6px 12px rgba(21,30,130,.06)`
- Zweitknopf: transparent, 1px Rand `rgba(255,255,255,.4)`, weißer Text, Radius 10px
- Knopf auf Weiß: Verlauf quer (Cyan, Indigo, Violett), weißer Text, Radius 10px, innerer Glanz `inset 0 1px .5px rgba(255,255,255,.25)`
- Karten: Radius 12px oder 24px, Fläche in Pastell oder Verlauf, kein Rand, kein Schatten oder nur der feine Doppelschatten oben
- Tags und Chips: Radius 9999px
- Links: Violett `#8947f0`, ohne Unterstreichung, Hover mit Unterstreichung

## Bildsprache
Bunte, glänzende Sticker und Mini-Vorschauen mit weichen Kanten: Farbrad, Herz mit Funken, Fußball, Code-Pille, Textkachel. Jedes Motiv ist ein eigenes Objekt auf dem Verlauf, leicht gekippt (-8° bis 8°). In Beispielen als CSS-Flächen und Inline-SVG mit Verläufen. Keine Fotos ohne Rahmung, keine grauen Stock-Szenen.

## Animation
Sticker schweben sanft (translateY ±8px, 5s bis 7s, ease-in-out, versetzt). Knöpfe heben sich beim Hover um 1px, Schatten wird etwas stärker (0.2s). Eingeblendete Abschnitte mit 0.5s Fade und 16px Aufwärtsbewegung. `prefers-reduced-motion` schaltet alles ab.

## Tonfall
Duzend, direkt, ermutigend. Der Einstieg ist eine Frage. Kurze Verben wie "gestalte", "starte", "probier". Keine Fachwörter, keine Drohkulisse. Knopftexte nennen das Ergebnis, nicht den Vorgang.

## Mach
- Hero als vollflächiger mehrstufiger Verlauf mit weißer Schrift
- Eine einzige zentrale Handlung pro Bildschirm, als heller Pill-Knopf
- Sticker versetzt und gekippt statt Screenshots im Raster
- Weiß als Standard, dunkle Blöcke gezielt als Pause
- Radien 10px bis 12px für UI, 24px für große Flächen, 9999px für Chips
- Gewichte 400 bis 600 mischen, nie über 700

## Mach nicht
- Keine harten Kanten und keine Radien unter 8px
- Keine schwarze Schrift auf dem violetten Teil des Verlaufs
- Keine Serifen, keine Versalien-Überschriften
- Keine Verläufe in mehr als einem Abschnitt gleichzeitig außer Band und Hero
- Keine dicken Rahmen und keine harten, dunklen Schlagschatten
- Keine Stockfoto-Raster als Hero

## Typische KI-Fehler in diesem Stil
- Verlauf nur zweifarbig (Violett nach Blau) statt der mehrstufigen Fahrt bis Eisblau und Lavendel
- Hero-Text fett (700) statt mittelstark (500) und dadurch schwer
- Sticker exakt ausgerichtet und gleich groß, wodurch die Leichtigkeit fehlt
- Hauptknopf violett auf Violett, statt hell auf dem Verlauf
- Zu viele Schatten und Rahmen auf Karten, der Stil lebt von flachen Pastellflächen
- Dunkler Block in reinem Schwarz `#000` statt Tintenton `#0f1015`
- Hero links ausgerichtet statt zentriert
