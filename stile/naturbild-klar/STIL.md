# Stil: Naturbild klar

## Kurzbeschreibung und Stimmung
Ein ruhiger, ehrlicher Katalog-Auftritt: Das Bild trägt die Seite, die Oberfläche bleibt Schwarz, Weiß und Hellgrau. Eine große, eng gesetzte Schlagzeile in Weiß liegt auf einem abgedunkelten Vollformat-Bild, darunter folgen schlichte Produkt- und Geschichten-Raster. Gefühl: robust, sachlich, draußen zu Hause, ohne Werbelärm. Der Kern des Stils sind die Bildbühne mit knapper Schlagzeile, die weißen Pillen-Knöpfe und die Reihe unterstrichener Kategorie-Tabs.

## Farbpalette
- Schwarz `#000000` für Ankündigungsleiste, Fußzeile, dunkle Bänder und Text auf hellem Grund
- Weiß `#ffffff` für Kopfzeile, Hauptflächen und Text auf Bildern
- Hellgrau `#f5f5f5` für abgesetzte Bänder und Kartenflächen
- Mittelgrau `#cccccc` für Linien und Text auf Schwarz, `#f2f2f2` für sehr helle Zweittexte
- Bildabdunklung: Schwarz mit 35 bis 45 % Deckkraft über dem Bild, damit weiße Schrift lesbar bleibt
- Keine Akzentfarbe: Farbe kommt ausschließlich aus den Bildern. Verläufe nur als Abdunklung von unten

## Typografie
- Hauptschrift: DM Sans (Google Fonts) als Ersatz für die erkannte, nicht frei verfügbare Grotesk; Gewichte 300, 500, 700
- Schlagzeilen Gewicht 500, Laufweite eng: H1 4rem (Mobil 2.5rem) mit Zeilenhöhe 1.1 und -0.02em; H2 3rem (Mobil 2rem) mit 1.1 und -0.02em; H3 2.5rem bzw. 1.75rem mit -0.02em
- Fließtext Gewicht 300, 1rem, Zeilenhöhe 1.5; Lead auf Bildern 1.125rem Gewicht 500
- Navigation und Tabs 0.875rem bis 1rem, Gewicht 300 bis 500, normale Laufweite
- Meta und Kleintexte 0.6875rem bis 0.75rem, Zeilenhöhe 1.4
- Zweitschrift für Geschichten und Zitate: Source Serif 4 (Ersatz für eine Antiqua), Gewicht 400, sparsam
- Keine Versalien, keine Sperrung

## Abstände und Raster
- Inhaltsbreite 1280px für Bühnen, Textspalte höchstens 640px
- Seitenrand 4rem Desktop, 1.5rem Mobil; Innenabstände in Schritten von 0.5rem (8, 16, 24, 32, 80)
- Abschnitte trennt 5rem Luft; Kategorie-Tabs liegen auf einer 1px-Linie in `#cccccc`
- Produktraster: 4 Spalten Desktop, 2 Spalten Tablet und Mobil, Lücke 1rem
- Geschichten: 3 Spalten Desktop, 1 Spalte Mobil

## Layout-Muster
- Oben eine schwarze Ankündigungsleiste (3rem hoch) mit zentrierter Kurzmeldung und kleinen Links links, darunter weiße Kopfzeile mit Wortmarke links, Icons rechts, Hauptnavigation in zweiter Zeile
- Hero: Vollformat-Bildbühne, rund 37rem hoch, Text unten links, Schlagzeile, ein Satz, zwei Pillen-Knöpfe nebeneinander
- Danach eine Tab-Reihe mit Kategorien und Linie darunter, dann ein Raster aus Bildkacheln mit knapper Beschriftung
- Wechsel zwischen weißen und hellgrauen Bändern, ein schwarzes Band für Engagement-Botschaft, schwarze Fußzeile mit bis zu 7.5rem Bodenabstand

## Komponenten
- Primärknopf auf Bild: weiße Pille, Radius 30px, Innenabstand 0.75rem 1.75rem, Text schwarz, Gewicht 500
- Knopf auf Weiß: schwarze Pille, weißer Text; Hover invertiert (Umrandung 1px)
- Kategorie-Tabs: Text 1rem, 0.5rem Innenabstand, aktiver Tab mit 2px schwarzer Unterlinie
- Karten: Bildfläche Radius 8px, Text darunter ohne Kasten, Name Gewicht 500, Preis oder Meta Gewicht 300
- Schatten: nur für schwebende Menüs (`0 4px 5px rgba(0,0,0,.14), 0 1px 10px rgba(0,0,0,.12), 0 2px 4px -1px rgba(0,0,0,.2)`), sonst keine
- Kleine runde Icon-Knöpfe (Radius 50%, weiß, 2.25rem) für Bildnachweis oder Merkliste

## Bildsprache
Dokumentarische Fotografie echter Menschen in Wetter und Landschaft, grobkörnig, gedeckte Erdfarben, nie gestellt-glatt. Bilder laufen randlos in voller Breite, Produkte stehen freigestellt auf Hellgrau. Im Beispiel ersetzen CSS-Verläufe in Waldgrün, Schiefer und Sand die Fotos, mit dunkler Abdeckung für die Schrift.

## Animation
Zurückhaltend: Hover-Wechsel bei Knöpfen und Tabs in 0.2s, sanftes Zoomen der Kachelbilder auf 1.03 in 0.4s. Karussells dürfen horizontal wischen. Keine Parallax-Effekte, keine Einblend-Orgien.

## Tonfall
Sachlich, direkt und werteorientiert. Kurze Sätze, konkrete Nutzen (Wetter, Haltbarkeit, Reparatur), kein Superlativ-Gerede. Schlagzeilen nennen die Sache beim Namen.

## Mach
- Bildbühne mit abgedunkeltem Foto und weißer, enger Schlagzeile
- Pillen-Knöpfe mit Radius 30px, Bildkacheln mit Radius 8px, alles andere eckig
- Schwarz, Weiß, Hellgrau als einziges Farbgerüst
- Gewicht 300 für Text, 500 für Schlagzeilen und Knöpfe
- Negative Laufweite bei großen Schlagzeilen
- Tab-Reihe mit Linie als Kategorie-Navigation

## Mach nicht
- Keine Akzentfarben, keine bunten Knöpfe
- Keine Schatten auf Karten, keine Verläufe als Dekor
- Keine Versalien-Schlagzeilen
- Keine Glas-Effekte, keine Emoji
- Keine zentrierten Textblöcke auf Bildern, Text bleibt links unten

## Typische KI-Fehler in diesem Stil
- Bild-Hero ohne Abdunklung, weiße Schrift schlecht lesbar
- Zu viele Radien: Alles wird eine runde Karte statt nur Pillen und Bildkacheln
- Schlagzeilen mit normaler Laufweite und Gewicht 700 statt eng und 500
- Eine Akzentfarbe (Blau, Grün) als Knopffarbe ergänzt
- Fließtext in Gewicht 400 statt 300, wodurch der leichte Ton verloren geht
- Fußzeile hellgrau statt schwarz
