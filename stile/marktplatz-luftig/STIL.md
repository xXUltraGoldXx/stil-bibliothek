# Stil: Marktplatz luftig

## Kurzbeschreibung und Stimmung
Eine helle, freundliche Entdeckungsoberfläche: viel Weiß, große Bilder mit stark gerundeten Ecken und winzige, ruhige Beschriftungen darunter. Im Zentrum stehen eine schwebende Pillen-Suche und waagerechte Reihen aus Bildkacheln. Gefühl: durchblättern, vergleichen, unkompliziert auswählen. Die Oberfläche tritt zurück, die Bilder tragen die Seite. Genau ein warmes Beerenrot markiert die Hauptaktion.

## Farbpalette
- Hintergrund `#ffffff`, Fußbereich und sanfte Verläufe `#f7f7f7`
- Text primär `#222222`, sekundär `#6c6c6c` (Beschriftungen, Untertitel, Platzhalter)
- Linien und Rahmen `#dddddd`, feine Trennlinie `#ebebeb`, Kreis-Knöpfe `#f2f2f2`
- Akzent genau einmal: Beerenrot `#cf2a58`, nur für den Such-Knopf, die Hauptaktion und kleine Markierungen
- Der Kopfbereich läuft von `#ffffff` (bis etwa 40 %) in `#f8f8f8`
- Keine zweite Signalfarbe, keine dunklen Flächen

## Typografie
- Schrift: Figtree (Google Fonts), geometrische, runde Grotesk. Rückfall: system-ui, sans-serif
- Seitentitel: 1.75rem (28px), Gewicht 700, Zeilenhöhe 1.43
- Abschnittstitel: 1.25rem (20px), Gewicht 600, Laufweite -0.01em (etwa -0.18px), Zeilenhöhe 1.2
- Kartentitel und Navigation: 0.875rem (14px), Gewicht 500
- Beschriftung, Preis, Untertitel: 0.75rem bis 0.8125rem (12 bis 13px), Gewicht 400, Zeilenhöhe 1.33, Farbe `#6c6c6c`
- Mikrotext (Badges): 0.6875rem, Gewicht 600
- Gewichte nur 400, 500, 600, 700. Keine Versalien, keine Kursive

## Abstände und Raster
- Seitenrand 2rem (32px) am Desktop, 1rem mobil. Maximalbreite 1280px
- Abschnitte mit etwa 2.5rem Abstand dazwischen, Titelzeile zu Reihe 1rem
- Kachelreihen mit 0.75rem bis 1rem Lücke. Desktop sechs bis zehn Kacheln pro Reihe, Tablet drei, Mobil zwei
- Innenabstände klein und regelmäßig: 4px, 8px, 12px, 24px, 32px
- Beschriftung unter Bildern mit 8px Abstand, Zeilen eng (2px bis 4px)

## Layout-Muster
- Kopfzeile: Wortmarke links, mittig vier Text-Reiter mit kleiner Illustration und Unterstrich beim aktiven Reiter, rechts ein Textlink und zwei runde Grau-Knöpfe
- Darunter eine schwebende Pillen-Suche mit drei Feldern (Beschriftung fett 12px, Platzhalter grau), senkrechte Trenner, am Ende ein roter Kreis-Knopf
- Danach untereinander gestapelte Reihen: Titel links (optional mit kleinem Pfeil-Kreis), zwei runde Pfeil-Knöpfe rechts, darunter die Kacheln
- Reihe 1: quadratische Orts-Kacheln (etwa 109px) mit zwei Zeilen Beschriftung
- Reihe 2: Angebotskarten mit hohem Bild (Seitenverhältnis etwa 1 zu 0.95), Badge oben links, Herz oben rechts, drei Textzeilen darunter
- Fuß: Hellgraue Fläche `#f7f7f7`, mehrspaltige Linkliste in 12 bis 14px

## Komponenten
- Bildkacheln: Radius 20px (Karten oben 20px, unten ggf. 10px bei Orts-Kacheln mit Verlauf), keine Rahmen
- Badge: weiße, halbtransparente Pille (`rgba(255,255,255,0.8)`), Radius 100px, Text 12px Gewicht 600, links oben mit 12px Abstand
- Herz-Symbol: weißer Umriss mit dunkler Füllung bei 0.5 Deckkraft, rechts oben
- Kreis-Knöpfe: 32px bis 40px, Hintergrund `#f2f2f2`, Radius 50 %, Pfeil-Symbol 14px. Deaktiviert mit 0.4 Deckkraft
- Pillen-Suche: Radius 100px, Höhe etwa 64px, Schatten `0 0 0 1px rgba(0,0,0,0.02), 0 8px 24px rgba(0,0,0,0.1)`
- Sekundärer Knopf: weiß, 1px `#dddddd`, Radius 40px, Padding 10px 19px, Gewicht 500
- Primärer Knopf: Hintergrund `#cf2a58`, Text weiß, Radius 50px, Gewicht 600
- Schatten zart und dreilagig: `0 0 0 1px rgba(0,0,0,0.02), 0 2px 6px rgba(0,0,0,0.04), 0 4px 8px rgba(0,0,0,0.1)`
- Eingabefelder ohne Rahmen, Hervorhebung durch Hintergrund `#ebebeb` beim Hover

## Bildsprache
Kräftige, warme, echte Fotografie ohne Filter: Orte, Innenräume, Fassaden, Details. Jedes Bild füllt seine Kachel vollflächig und wird nur durch die Rundung begrenzt. Im Beispiel: Flächen aus CSS-Verläufen in warmen Erdtönen, Sand, Salbei und Dunkelblau mit einfachen SVG-Formen als Platzhalter.

## Animation
- Weiche Federbewegung: Dauer 450 bis 580ms mit leichtem Überschwingen für Knöpfe und Reiter
- Standard-Kurve `cubic-bezier(0.2, 0, 0, 1)`, Einblenden `cubic-bezier(0.1, 0.9, 0.2, 1)`
- Hover: Karte hebt sich nicht, nur das Herz und die Pfeil-Knöpfe reagieren (Skalierung 1.04)
- Waagerechtes Scrollen mit sanftem Einrasten. Keine Parallax-Effekte

## Tonfall
Freundlich, kurz, du-Ansprache. Beschriftungen sind knappe Stichworte ("Tolle Restaurants", "Küstencharme"), Titel sind einladende Teilsätze mit "für dich". Preise und Zeiträume sachlich in einer Zeile. Keine Ausrufezeichen, keine Werbesprache.

## Mach
- Bilder groß, Text klein und grau darunter
- Radius 20px für alle Bildflächen, Pillen und Kreise für Bedienelemente
- Weiße Fläche dominiert, Struktur nur durch Abstand und Reihen
- Beerenrot sparsam: Such-Knopf, Hauptaktion, nie als Fläche
- Jede Reihe hat Titel links und Pfeil-Knöpfe rechts
- Beschriftung in zwei bis drei Zeilen: Titel (500), Detail (grau), Preis/Bewertung

## Mach nicht
- Keine dunklen Hintergründe, keine großen Verlaufsflächen
- Keine eckigen Bildkacheln und keine Radien unter 8px bei Bildern
- Keine schweren Schatten, kein Rahmen um jede Karte
- Keine Überschriften über 1.75rem, kein Heldentext mit Riesenschrift
- Keine zweite Akzentfarbe, keine bunten Knöpfe
- Keine zentrierte Marketing-Spalte mit Slogan

## Typische KI-Fehler in diesem Stil
- Zu große, laute Überschriften statt der winzigen 12 bis 14px Beschriftungen
- Karten mit Rahmen, Innenabstand und Schatten, obwohl Bild und Text frei auf Weiß stehen
- Rot als Hintergrund für ganze Flächen oder als Linkfarbe
- Rechteckige oder nur 4px gerundete Bildecken
- Raster mit festen Spalten statt waagerechter Reihen mit Pfeil-Knöpfen
- Fehlende Pillen-Suche oder Reiter mit Symbolen, wodurch der Entdecken-Charakter verloren geht
- Zentrierte Hero-Sektion mit großem Foto und Slogan
