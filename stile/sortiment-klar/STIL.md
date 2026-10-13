# Stil: Sortiment klar

## Kurzbeschreibung und Stimmung
Ein heller, geradliniger Shop-Auftritt. Weißer Grund, großflächige Produkt- und Motivbilder, die bis an den Rand laufen, darunter wenig Text in einer runden, geometrischen Sans. Schlagzeilen sind fett und enden mit einem Punkt, Untertitel sind leise und kurz. Gefühl: übersichtlich, ehrlich, alltagstauglich, ohne Schnickschnack. Das Bild verkauft, die Typografie ordnet.

## Farbpalette
- Grund `#ffffff`, Fläche Hellgrau `#ededed` (Bildgründe, Streifen), warmes Greige `#f2f0ea` (Hinweisleisten, Sekundärknöpfe, Kästen)
- Text `#1c1c1c`, Überschriften `#212121`, sekundärer Text `#595959`, Hilfstext `#9d9d9d`
- Primärknopf `#212121` mit weißer Schrift
- Funktionsfarbe Grün `#008a11` (Angebot, Preisnachlass, Bestätigung), heller Grünton `#eaf6ee` für Hinweisflächen
- Sternebewertung Gelb `#f9ca4f`, nur für Sterne
- Linien: 1px `#ededed`, in Formularen `#d9d9d9`
- Keine Verläufe, kaum Schatten. Farbe kommt aus den Bildern, nicht aus der Oberfläche.

## Typografie
- Schrift: Figtree (Google Fonts), geometrisch und rund, Gewichte 400, 500, 700.
- Hauptschlagzeile (Abschnitt): 3.75rem Desktop, 1.75rem Mobil, Gewicht 700, Zeilenhöhe 1, Satz endet mit Punkt
- Kategorie-Titel auf Bildern: 1.5rem bis 1.75rem, Gewicht 700, ebenfalls mit Punkt
- Hero-Titel mobil: 1.75rem bis 2.25rem, Gewicht 700
- Produktname: 1rem, Gewicht 500, Zeilenhöhe 1.6
- Untertitel und Fließtext: 1rem, Gewicht 400, Zeilenhöhe 1.6, Farbe `#333` bis `#595959`
- Varianten, Bewertungen: 0.875rem; Mikrotext 0.75rem mit Laufweite 0.02em
- Knopfbeschriftung: 0.875rem bis 1rem, Gewicht 500 bis 700, keine Versalien
- Nur eine Schriftfamilie, Hierarchie über Größe und Gewicht (400, 500, 700).

## Abstände und Raster
- Seitenrand 1rem mobil, 2.5rem bis 3.2rem Desktop (Textköpfe starten bei etwa 3.2rem)
- Abschnitte: 3rem bis 4.5rem vertikal Abstand, Schlagzeile und Untertitel eng gekoppelt (0.5rem)
- Produktreihe: fünf Spalten ohne Zwischenraum, Bild 288px breit (Verhältnis 1 zu 1,0), Textblock mit 2.5rem Einzug
- Kategoriekacheln: drei Spalten bündig, ohne Lücke, Titel oben links im Bild
- Innenabstände in 0.5rem-Schritten: 0.5, 0.75, 1, 1.25, 2, 2.5rem
- Max. Inhaltsbreite für Textblöcke 40rem, Bildflächen dürfen volle Breite nutzen.

## Layout-Muster
- Kopfzeile: weiß, 4.5rem hoch, links Menü-Symbol, Wortmarke mittig, rechts Suchfeld, Konto, Warenkorb. Darüber optional schmale Hinweisleiste in Greige.
- Hero: vollflächiges Motiv, Schlagzeile und Kurzzeile oben links, ein dunkler Knopf unten links, Seitenindikator als drei dünne Striche.
- Bestseller: Schlagzeile mit Punkt, Untertitel, dann Bildreihe ohne Lücken, darunter Name, Variante, Sterne mit Anzahl.
- Kategorien: bündige Bildkacheln mit Titel im Bild.
- Vorteilsleiste: drei bis vier kurze Zusagen in Greige.
- Abschluss: Newsletter-Kasten und schlichter Fuß.

## Komponenten
- Primärknopf: Hintergrund `#212121`, Text weiß, Radius 4px, Höhe 3.25rem, Innenabstand 0.9rem 2rem, Gewicht 700. Mobil im Hero breit (etwa 185px).
- Sekundärknopf: Greige `#f2f0ea`, Text `#1c1c1c`, Radius 0 bis 4px, Innenabstand 0.5rem.
- Suchfeld: 1px Rahmen `#9d9d9d`, Radius 5px, Höhe 2.1rem, kleiner Platzhaltertext, Lupe links.
- Sterne: fünf gelbe Sterne, daneben Anzahl in Klammern 0.875rem.
- Punktindikator: drei Punkte 6px, aktiver dunkler `#9d9d9d`, andere `#ededed`.
- Angebotsmarke: Grün `#008a11`, Text weiß, Radius 4px, 0.75rem.
- Radien nur 4px, 5px, 8px. Schatten fast keine.

## Bildsprache
Studiofotos auf ruhigem, warmgrauem Grund, Personen oder Produkte mittig, natürliches Licht, freundlicher Ausdruck. Bilder laufen randlos, ohne Rahmen, ohne Rundung, ohne Lücken. Im Beispiel: Flächen in Warmgrau `#d9d5cf` bis `#ededed` mit einfachen SVG-Formen als Platzhalter.

## Animation
Zurückhaltend und funktional. Horizontales Wischen und Einrasten bei Produktreihen, Seitenindikator wechselt weich. Schubladen gleiten mit `cubic-bezier(0.645, 0.045, 0.355, 1)` in 0.3s. Hover: Knopf wird leicht heller (`#3a3a3a`), Bild optional 1.03-facher Zoom in 0.4s.

## Tonfall
Kurz, direkt, alltagsnah. Schlagzeile als Behauptung mit Punkt, Untertitel in einem Satz. Du-Ansprache, keine Superlative im Fließtext, Zahlen und Fakten (Stückzahl, Bewertungen) statt Floskeln.

## Mach
- Schlagzeilen fett (700) mit Punkt, Untertitel in 1rem direkt darunter
- Bilder bündig und randlos, Raster ohne Lücken
- Produktblock: Name 500, Variante 400, Sterne mit Anzahl
- Ein dunkler Primärknopf pro Bereich
- Grün nur für Angebot und Bestätigung, Gelb nur für Sterne
- Genug Weißraum zwischen den Abschnitten (3rem bis 4.5rem)

## Mach nicht
- Keine Verläufe, keine Neonfarben, keine Glasflächen
- Keine großen Radien (über 8px) und keine Kartenschatten
- Keine zweite Schriftfamilie, keine Serifen
- Keine Versalien-Knöpfe mit weiter Laufweite
- Keine Rahmen oder Abstände um Produktbilder
- Keine bunten Knöpfe

## Typische KI-Fehler in diesem Stil
- Produktkarten mit Rahmen, Rundung und Schatten statt bündiger, randloser Bilder
- Schlagzeilen ohne Punkt und in mittlerem Gewicht statt fett
- Zu viele Akzentfarben: Grün und Gelb breiten sich auf Knöpfe und Flächen aus
- Zentrierte Überschriften statt linksbündiger Köpfe
- Weißraum zu knapp oder Bildreihe mit Lücken
- Knöpfe als bunte Pillen statt dunkel mit 4px Radius
