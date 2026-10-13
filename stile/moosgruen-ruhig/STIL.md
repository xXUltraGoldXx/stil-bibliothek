# Stil: Moosgrün ruhig

## Kurzbeschreibung und Stimmung
Ruhiger, warmer Online-Laden für nachhaltige Alltagsprodukte. Gebrochenes Weiß, ein gedecktes Waldgrün und große Fotoflächen mit dunklem Verlauf bilden den Rahmen. Eine weiche Serifen-Schlagzeile trifft auf eine freundliche, runde Sans. Bedienelemente sind flach, ohne Schatten und fast ohne Rahmen. Gefühl: draußen sein, ehrlich, unaufgeregt, produktnah.

## Farbpalette
- Seitengrund `#f4f4f2`, Flächen und Kopfzeile `#eeeee9`
- Tiefes Waldgrün `#475a4f` für Ankündigungsleiste und große Bänder, `#516559` für Primärknöpfe und Akzente, Hover `#47594e`, helles Grün `#66776c` für Zweitflächen
- Text `#111827`, sekundär `#424242`, gedämpft `#838381`
- Auf grünen Flächen und Fotos: Text `#eeeee9`, Knöpfe in `#eeeee9` mit grünem Text
- Linien `#c3c3c0` und `#d9d9d5`, 1px. Bildplatzhalter `#e4e4df`
- Foto-Overlay: Verlauf 23deg von `rgba(0,0,0,0.2)` bei 20 % zu transparent
- Keine Schatten, keine weiteren Akzentfarben

## Typografie
- Schlagzeilen: weiche Display-Serife, im Beispiel Fraunces (Google Fonts), Gewicht 400, Zeilenhöhe 1.1
- Text und UI: runde Sans, im Beispiel Nunito (Google Fonts)
- Hero-Titel 3.75rem (Mobil 2.25rem), H2 2.25rem (Mobil 1.875rem), H3 1.25rem
- Fließtext 0.9375rem (15px), Zeilenhöhe 1.5, Gewicht 400
- Meta, Navigation, Knöpfe, Tabs: Versalien, 0.75 bis 0.9375rem, Laufweite 0.05 bis 0.14em, Knöpfe Gewicht 700
- Fett (700) nur für Knöpfe, Preise, Kleinstüberschriften

## Abstände und Raster
- Seitenrand 2rem Desktop, 1.25rem Mobil. Inhalt bis 1280px
- Basis 4px: Werte 0.25, 0.5, 1, 1.5, 2, 2.5, 4rem
- Sektionen: 4rem vertikal Desktop, 2.5rem Mobil
- Produktraster: 4 Spalten, Lücke 1rem, auf Mobil 2 Spalten
- Ankündigungsleiste 40px hoch, Kopfzeile ca. 80px hoch

## Layout-Muster
- Ankündigungsleiste in Grün, zentrierter Einzeiler in Versalien
- Kopfzeile in `#eeeee9`: Marke links, Navigation in Versalien, Symbole rechts
- Hero: vollflächige Bildfläche 600px hoch mit Verlauf, Text unten links (Eyebrow, Serifen-Titel, Zweizeiler, ein Knopf)
- Produktband: H2 links, Pfeilknöpfe rechts, darunter Tabs mit grüner Unterstreichung, dann Kartenraster
- Grünes Band mit drei Kennzahlen in Serife
- Story: Bild und Text im 50/50-Raster, Text vertikal zentriert
- Newsletter: Zeile mit Eingabe (nur untere Linie) und Knopf
- Fußzeile: dunkles Grün, vier Spalten mit Linklisten

## Komponenten
- Primärknopf: `#516559`, Text `#eeeee9`, Versalien, Gewicht 700, Laufweite 0.1em, Radius 4px, Innenabstand 0.9rem 2rem
- Knopf auf Foto: Fläche `#eeeee9`, Text `#475a4f`
- Pillen und Filter: Radius 9999px, 1px Linie `#c3c3c0`, aktiv grün gefüllt
- Tabs: Versalien, Laufweite 0.1em, aktiv Text `#475a4f` mit 2px Unterstreichung
- Runde Pfeilknöpfe 40px (Radius 50 %), Fläche `#c3c3c0`
- Produktkarten: Bild ohne Radius auf `#e4e4df`, darunter Name 0.9375rem, Preis fett, kleine Meta-Zeile in `#838381`
- Eingabe: transparent, nur 1px Unterlinie, Innenabstand 0.4rem 2rem 0.4rem 0
- Schatten: keine

## Bildsprache
Natürliches Licht, Menschen im Alltag, warme Erdtöne vor ruhigen Hintergründen, Produkte großflächig und eng angeschnitten. Fotos bekommen einen sanften dunklen Verlauf von unten links, damit helle Schrift lesbar bleibt. Im Beispiel: CSS-Flächen in Grün- und Sandtönen mit Verlauf, dazu einfache SVG-Formen.

## Animation
Zurückhaltend. Farbübergang bei Knöpfen und Links (0.2s), Karussell mit horizontalem Gleiten, sanftes Einblenden von Bildern. Keine Parallax-Effekte, keine springenden Elemente.

## Tonfall
Freundlich, direkt, aktiv. Kurze Sätze mit konkretem Nutzen (Menge, Rabatt, Frist, Wirkung). Wirkungsversprechen werden mit Zahlen belegt. Keine Ironie, keine Übertreibung. Eyebrows und Navigation in Versalien.

## Mach
- Gebrochenes Weiß und Waldgrün als Basis, Text nur in `#111827`
- Serife für H1 und H2, runde Sans für alles andere
- Große Fotoflächen mit Verlauf und linksbündigem Text unten
- Versalien mit Laufweite für Navigation, Tabs und Knöpfe
- Knöpfe mit 4px Radius, flach, ohne Schatten
- Produktkarten mit schlichtem Bild, Name und Preis, zwei Spalten auf Mobil
- Kennzahlen als Beleg im grünen Band

## Mach nicht
- Keine Schatten, keine Glasflächen, keine Neonfarben
- Keine reinweißen Seitenflächen, kein Schwarz als Grund
- Keine Serife im Fließtext
- Keine großen Radien auf Karten und Bildern (nur Pillen und Rundknöpfe)
- Keine Emoji, keine bunten Kategorie-Farben
- Keine Parallax- oder Scroll-Spielereien

## Typische KI-Fehler in diesem Stil
- Reinweiß `#ffffff` statt `#f4f4f2` und `#eeeee9`, wodurch die Wärme verloren geht
- Ein kräftiges Grün (z. B. `#22c55e`) statt des gedeckten `#516559`
- Karten mit Schatten und 16px Radius, obwohl Bilder hier eckig bleiben
- Serife auch in Navigation, Knöpfen und Fließtext
- Hero ohne Verlauf, sodass helle Schrift auf hellen Fotoflächen schlecht lesbar ist
- Zentrierte Hero-Texte statt linksbündig unten
- Knöpfe in Kleinbuchstaben statt Versalien mit Laufweite
