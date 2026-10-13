# Stil: Marktplatz Kacheln

## Kurzbeschreibung und Stimmung
Ein Onlinekaufhaus-Stil. Der Seitengrund ist ein ruhiges Hellgrau (#f0f0f0). Darauf liegen weiße Karten mit 16px Radius, die Gutscheine, Themenwelten und Marken bündeln. Es gibt keine Schatten, keine Verläufe und keine Zierrahmen. Die Trennung entsteht allein durch den Kontrast von Grau und Weiß. Ein einziges kräftiges Rot (#dc001d) markiert jede Handlung. Alles andere bleibt Schwarz, Dunkelgrau und Weiß. Die Stimmung ist freundlich, sachlich und übersichtlich. Sie wirkt dicht, aber nie laut, weil die Typografie klein und gleichmäßig bleibt.

Kern des Stils sind drei Dinge: die Kartenlogik (weiß auf grau, rund, ohne Schatten), die rote Pille als Handlungsaufruf und die horizontal scrollenden Kartenreihen mit rundem Pfeilknopf am Rand.

## Farbpalette
- Seitengrund: #f0f0f0 (größte Fläche)
- Karte / Fläche: #ffffff
- Text primär: #212121; reine Überschriften und Navigation dürfen #000000 sein
- Text sekundär: #6d6d6d (Navigation, Hinweise, Platzhalter)
- Aktion und Aktionsmarke: #dc001d, Text darauf #ffffff
- Akzentfläche warm: #ffc5a5 (Pfirsich, nur für große Aktionsbänder, sparsam)
- Link-Blau: #2366cb (nur Textlinks im Fließtext)
- Linien: #e5e5e5 oder gestrichelt #ccc
- Fehler: #b30023 auf #ffe2e2
Rot ist rund 1 % der Fläche. Weiß etwa ein Drittel, Grau etwa zwei Drittel.

## Typografie
Gewählt ist Figtree aus Google Fonts, eine klare Grotesk mit offenen Formen. Gewichte: 400, 700, 800.
- Seitentitel (h1): 1.5rem bis 2.5rem, Gewicht 800, Zeilenhöhe 1.2
- Abschnittstitel: 2rem auf Desktop, 1.75rem mobil, Gewicht 800
- Kartentitel (h3): 1rem, Gewicht 700, Zeilenhöhe 1.5
- Fließtext: 0.875rem (14px), Gewicht 400, Zeilenhöhe 1.714 (24px)
- Eingabe: 1rem
- Kleintext, Labels: 0.75rem, Zeilenhöhe 1.33
- Laufweite normal, keine Großbuchstaben-Auszeichnung
Über jedem großen Titel steht oft eine Zeile in 1rem, Gewicht 400, als Rubrik. Der Kontrast entsteht durch Gewicht 400 gegen 800, nicht durch Größe.

## Abstände und Raster
- Basiseinheit 4px, gängige Werte 4, 8, 12, 16, 24, 40px
- Innenabstand von Karten: 8px außen, 16px bei Textkarten
- Lücke zwischen Karten: 8px bis 16px
- Maximale Inhaltsbreite 1152px (72rem), seitlicher Rand 16px
- Breakpoints: 22.5rem, 28rem, 48rem, 62rem, 77rem
- Abschnitte trennt 24px bis 40px vertikaler Raum auf grauem Grund

## Layout-Muster
- Kopfzeile: Wortmarke links, breite Suchpille in der Mitte, kleine Symbole mit Beschriftung rechts. Darunter zwei Zeilen Hauptnavigation in #6d6d6d, gleichmäßig verteilt.
- Gutschein-Reihe: drei weiße Karten nebeneinander, abgeschnitten am rechten Rand, mit rundem weißem Pfeilknopf.
- Themenkarten: weiße Karten, Rubrik und Titel oben, darunter eine 8px-gerundete Bildfläche.
- Abschnitt mit Kopf: Rubrik, großer Titel, danach Karten in voller Breite auf weißem oder grauem Band.
- Mobil: eine Spalte, Karussells scrollen horizontal, Karten ca. 85 % der Breite.

## Komponenten
- Aktionspille: Hintergrund #dc001d, Text #fff, Gewicht 700, 14px, Radius 8px, Höhe 32px, Innenabstand 0 16px, kleiner Pfeil rechts. Kein Schatten, kein Rand.
- Marke auf Gutschein: quadratisches rotes Feld 58px mit weißem, fettem Wert, Radius 4px.
- Gutschein-Karte: weiß, Radius 16px, gestrichelte Trennlinie zwischen Kopf und Fuß, links Gültigkeit in 12px, rechts Aktionspille.
- Suchpille: Hintergrund #f0f0f0, Radius 24px, Höhe 48px, Innenabstand links 16px, Platzhalter #6d6d6d.
- Pfeilknopf: 32px Kreis, weiß, 1px Rand #e5e5e5, Pfeil in #212121.
- Themenkarte: weiß, Radius 16px, Innenabstand 8px, Bildfläche Radius 8px.
- Navigationspunkt: 16px, #6d6d6d, zentriert; Sonderpunkt in Rot.

## Bildsprache
Freigestellte oder ruhig ausgeleuchtete Produktbilder auf hellgrauem Grund, gerundet mit 8px, immer in Kartenrahmen. Quadratisch bis 4:3. Keine Vollflächen-Heldenbilder, keine Overlays. Als Platzhalter dienen helle Grauflächen (#e5e5e5 bis #f7f7f7) mit einfachen SVG-Formen.

## Animation
Zurückhaltend. Karussells scrollen mit Wischgeste oder Pfeilknopf, weich mit Scroll-Snap. Hover: Aktionspille wird dunkler (#b30023), 150ms. Keine Parallaxe, keine Einblend-Effekte.

## Tonfall
Direkt, duzend, praktisch. Kurze Rubrikzeilen (zwei bis vier Wörter) über kurzen Titeln. Handlungsaufrufe sind Verben im Infinitiv oder Substantiv mit Zweck, etwa Aktivierung oder Ansehen. Keine Ausrufezeichen-Ketten, kein Fachjargon.

## Mach
- Weiße Karten auf #f0f0f0 mit 16px Radius, ganz ohne Schatten
- Rot (#dc001d) ausschließlich für Handlung und Aktionsmarken
- Ein Schriftschnitt-Kontrast: 400 für Rubriken, 700 bis 800 für Titel
- Fließtext bei 14px mit 24px Zeilenhöhe
- Karten in Reihen, am Rand angeschnitten, mit rundem Pfeilknopf
- Abstände aus dem 4px-Raster, Lücken 8px oder 16px
- Bildflächen mit 8px Radius in einer Karte einbetten

## Mach nicht
- Keine Schlagschatten, Verläufe oder Glasflächen
- Kein zweites Aktionsrot-Äquivalent, kein Orange, Grün oder Lila als Akzent
- Keine Serifenschriften, keine Versalien-Auszeichnung
- Keine spitzen Ecken bei Karten und Aktionen (Radius 0 ist falsch)
- Keine Vollbild-Heldenbilder mit Textüberlagerung
- Keine Kartenränder in Farbe

## Typische KI-Fehler
- Schatten unter Karten ergänzen, weil Karten angeblich schweben müssen. Hier trennt nur Grau gegen Weiß.
- Den Seitengrund weiß machen. Dann verschwindet die Kartenlogik.
- Die Aktionsfarbe auf Überschriften, Icons und Rahmen verteilen und damit entwerten.
- Überschriften zu groß setzen. Der Stil lebt von 14px Fließtext und 16px Kartentiteln.
- Pillen vollrund (999px) machen. Die Aktion hat 8px, nur die Suche ist rund.
- Ein großes Heldenbild an den Anfang stellen, statt Gutscheinen und Kartenreihen.
