# Stil: Galerie klar

## Kurzbeschreibung und Stimmung
Eine helle Plattform für kreative Arbeit: weißer Grund, nachtblaue Tinte, ein einziges Pink als Akzent. Die Bilder tragen die Seite, die Oberfläche tritt zurück. Alle Bedienelemente sind weiche Pillen oder leicht abgerundete Flächen. Gefühl: freundlich, professionell, einladend, mit hoher Dichte an Inhalten bei viel Weißraum um die Kopfzone.

## Farbpalette
- Grund `#ffffff`, Flächen grau `#f3f3f6`, Linien und Chip-Rahmen `#e7e7e9`, Hover-Fläche `#ecebf0`
- Tinte `#15132c` (Text, Überschriften, primärer Knopf), Text sekundär `#6e6d7a`, Text tertiär `#9e9ea7`
- Akzent Pink `#e2578f`, Hover `#b04369`, helle Tönung `#fce7ef` (Häkchen-Kreise, Hinweisband `#fdf0f8`)
- Der Akzent steht nur für ein Schlüsselwort der Schlagzeile, Häkchen, den Such-Knopf und Hover. Nie als Fläche für ganze Abschnitte
- Dunkle Fläche für Abschluss-Band: Tinte `#15132c` mit weißem Text
- Keine Verläufe auf der Oberfläche, Verläufe nur in Bildplatzhaltern

## Typografie
- Eine Familie: Mona Sans (Google Fonts), Rückfall Helvetica Neue, Arial
- H1: 3.25rem (Mobil 1.7rem), Gewicht 600, Zeilenhöhe 1.2, Laufweite normal, Schlüsselwort in Pink
- H2: 2rem, Gewicht 600, Zeilenhöhe 1.2
- Fließtext und Listen: 1.0625rem bis 1.125rem, Gewicht 400 bis 500, Zeilenhöhe 1.5
- Navigation 1rem, Gewicht 500. Knöpfe 0.875rem, Gewicht 600
- Meta, Tabs, Chips: 0.75rem bis 0.875rem, Gewicht 500 bis 600, Kapitälchen-Labels in Versalien mit Laufweite 0.04em
- Gewichte 400, 500, 600, 800 genügen. Keine Serifen, kein Kursiv

## Abstände und Raster
- Basis 4px, bevorzugt 8, 12, 16, 24, 40, 72
- Seitenrand 40px Desktop, 16px Mobil, Inhaltsbreite bis 1280px, Kopfzone mit 72px Innenrand
- Kachelraster: vier Spalten ab 1100px, drei ab 800px, zwei ab 560px, sonst eine Spalte, Lücke 24px
- Lücken innerhalb von Zeilen (Chips, Meta, Listen) 8px, bei Gruppen 12px
- Abschnittsabstand oben und unten 72px Desktop, 40px Mobil

## Layout-Muster
- Kopfleiste: Wortmarke links, Navigation mittig-links, rechts Textlink und dunkle Pillen-Schaltfläche
- Hinweisband unter der Leiste: volle Breite, Radius 999px, Tönung `#fdf0f8`, Text mittig mit Mini-Knopf
- Hero zweispaltig 5/6: links Umschalter-Pille, Schlagzeile, Häkchenliste, Knopf; rechts große Bildkachel (Radius 24px) mit schwebender weißer Pille als Bildnachweis unten rechts
- Danach Tab-Reihe, große Suchleiste, Chip-Reihe "Beliebt" und rechts ein Auswahlfeld
- Hauptfläche: dichtes Kachelraster mit Bild oben, Meta-Zeile darunter
- Abschluss: dunkles Band mit abgerundeten Ecken (24px), kurze Aussage, ein weißer Knopf

## Komponenten
- Primärknopf: Tinte gefüllt, weißer Text, Radius 999px, Höhe 48px, Innenabstand 0 24px. Hover leicht aufgehellt `#2a2940`
- Sekundärknopf: weiß, 1px Rand `#e7e7e9`, Radius 999px, Höhe 36px
- Umschalter und Tabs: Fläche `#f3f3f6`, aktives Segment weiß mit 1px Rand, Radius 999px, Versalien 0.75rem
- Suchleiste: Fläche `#f3f3f6`, Radius 999px, Höhe 56px, rechts runder Pink-Knopf 40px mit weißer Lupe
- Chips: weiß, 1px Rand `#e7e7e9`, Radius 999px, Innenabstand 6px 16px, 0.875rem
- Bildkachel: Radius 12px, Seitenverhältnis 4:3, keine Schatten. Beim Hover dunkler Schleier und Titel unten im Bild
- Meta-Zeile: Avatar-Kreis 24px, Name 0.875rem Gewicht 600, kleine Pille "Plus" in Fläche `#ecebf0`, rechts Zähler in `#6e6d7a`
- Häkchen: Kreis 24px in `#fce7ef` mit Pink-Haken
- Schatten nur einer: `0 4px 4px rgba(6,3,24,.01)` bzw. `0 6px 16px -4px rgba(35,38,59,.15)` für schwebende Pillen und Menüs

## Bildsprache
Hochwertige, kräftige Motive in großen Kacheln: glänzende 3D-Objekte, Oberflächen-Renderings, Illustrationen, Oberflächen-Ansichten. Bilder sind immer das Farbigste auf der Seite, die Oberfläche bleibt neutral. Ecken immer gerundet (12px Kacheln, 24px Hero). Im Beispiel: CSS-Verläufe und einfache SVG-Formen als Platzhalter.

## Animation
Kurz und weich: Hover-Übergänge 0.15s bis 0.2s ease auf Hintergrund, Rahmen und Schleier. Kacheln heben sich nicht und skalieren höchstens um 1.02. Menüs blenden in 0.2s ein. Keine Parallax-Effekte, keine Dauerschleifen.

## Tonfall
Direkt, einladend, handlungsorientiert. Kurze Aufforderungen im Imperativ, Nutzenpunkte in drei knappen Zeilen, Sie-lose Ansprache mit "du" oder neutral. Keine Fachsprache, keine Übertreibungen.

## Mach
- Weiß als Grundfläche, Tinte `#15132c` statt reinem Schwarz
- Alles Interaktive als Pille (Radius 999px), Bildflächen mit 12px oder 24px
- Pink nur sparsam: ein Schlüsselwort, Häkchen, Such-Knopf
- Dichte, gleichmäßige Kachelraster mit identischer Meta-Zeile
- Eine Schrift in vier Gewichten, Hierarchie über Größe und Gewicht
- Dünne 1px-Rahmen in `#e7e7e9` statt Schatten

## Mach nicht
- Keine scharfen Ecken an Knöpfen, Chips oder Eingabefeldern
- Keine großen weichen Schlagschatten auf Kacheln
- Keine Pink-Flächen für Abschnitte oder volle Knöpfe außer dem Such-Knopf
- Keine Serifenschrift, keine Versal-Schlagzeilen
- Keine zweite Akzentfarbe, keine bunten Verläufe in der Oberfläche
- Keine zentrierten, schmalen Textspalten als Hero, der Hero ist zweispaltig

## Typische KI-Fehler in diesem Stil
- Pink als Primärknopf-Farbe verwenden, obwohl der Primärknopf nachtblau ist
- Kacheln mit Schatten und Rahmen zugleich bauen, wo hier nur Bild und Meta stehen
- Knöpfe mit 6px Radius statt voller Pille
- Reines Schwarz `#000` oder kühles Grau statt `#15132c` und `#f3f3f6`
- Suchleiste als weißes Feld mit Rahmen statt als graue Pille mit rundem Knopf
- Schlagzeile komplett einfarbig, ohne das Pink-Schlüsselwort
- Zu wenig Dichte: nur drei große Karten statt vielzeiligem Kachelraster
