# Stil: Bonbon Katalog

## Kurzbeschreibung und Stimmung
Ein weißer Schaufenster-Katalog, in dem die Bildflächen die Farbe liefern und die Oberfläche ruhig bleibt. Eine rosa Ankündigungsleiste, eine zentrierte Kopfzeile mit Mittelachse, ein breiter Bildstreifen mit drei Feldern und darunter Kachelreihen mit kleinen Etiketten. Alles ist rund: Pillen-Knöpfe, Etiketten, Kartenecken. Die Schrift ist mittelstark und weit gesetzt. Gefühl: Kosmetikregal, Geschenkpapier, gute Laune ohne Lärm.

## Farbpalette
- Grund Weiß `#ffffff`, Flächen `#f5f5f5`, Feldgrau `#ebebf0`
- Signal Rosa `#ff849e`, nur als Leiste, Etikett oder Akzentfläche
- Text Schwarz `#000000`, gedämpft `#363638`
- Creme `#fdf2e7` für Schrift auf Rosa oder Schwarz
- Pastell-Akzente nur in Bildflächen: Flieder `#c9b6e8`, Hellblau `#cfe3ff`, Beere `#c2184b`
- Haarlinien `#eeeeee` (1px), Feldrand `#f5f5f5` (2px)
- Keine Verläufe auf der Oberfläche, nur in Bildplatzhaltern

## Typografie
- Eine einzige Familie: Outfit (Google Fonts) als Ersatz für die erkannte, dort nicht verfügbare Rundschrift. Gewicht 500 für alles, 700 für kleine Überschriften
- Fließtext 0.975rem (ca. 15.6px), Zeilenhöhe 1.7, Laufweite 0.05em
- H1 2.55rem, Zeilenhöhe 1.2, Laufweite 0.05em, Gewicht 500; mobil 2.3rem
- H2 1.6rem, Zeilenhöhe 1.3, Laufweite 0.05em
- H3 0.94rem, Gewicht 700, Laufweite 0.05em
- Knopfschrift 0.8rem, Gewicht 700, Versalien, Laufweite 0.1em
- Keine Serifen, keine Kursive, keine extremen Größen

## Abstände und Raster
- Seitenrand 1rem (16px), Inhalt volle Breite bis max. 1400px
- Kachelraster: 4 Spalten ab 900px, 2 ab 600px, mobil 1,5 Spalten mit seitlichem Wischen im Container
- Lücke zwischen Kacheln 1rem, kleine Lücken 5px zwischen Etiketten
- Abschnitte trennt vertikaler Raum von 3rem, nicht Linien
- Kopfzeile: 10px oben, Logoreihe 83px hoch, darunter Menüleiste mit 24px Zeilenhöhe

## Layout-Muster
- Oben die rosa Ankündigungsleiste, 35px hoch, Creme-Text zentriert
- Kopf: Suche links, Wortmarke mittig, Symbole rechts; darunter zentrierte Textnavigation
- Hero: breiter Streifen in drei Feldern, mittleres Feld Flieder mit Titel, äußere Felder Bildflächen, darunter drei Punkte als Pager
- Danach linksbündig H2, ein Satz Text, ein schwarzer Pillen-Knopf
- Dann Reihe von Produktkacheln mit Etiketten oben links und Herz oben rechts
- Zwischen den Reihen jeweils ein Titel mit Link "alle ansehen" als Text

## Komponenten
- Primärknopf: schwarz `#000000`, Creme-Text, Radius 9999px, Höhe 48px, Innenabstand 0 2rem
- Sekundärknopf: Hellblau `#cfe3ff` mit schwarzem Text in der Hero-Fläche
- Runder Symbolknopf 48px, Hintergrund `#ebebf0`, Rand 2px `#f5f5f5`
- Etikett: Radius 9999px, 1px schwarzer Rand, Weiß, 0.7rem Text, Innenabstand 3px 10px
- Karten: Radius 10px, Bildfläche oben, darunter Name (Gewicht 500) und Preis
- Schatten: nur `0 1px 2px rgba(0,0,0,.24)` für schwebende Mini-Knöpfe, `0 4px 8px rgba(0,0,0,.2)` für Pop-ups
- Eingabefeld: Radius 9999px, 1px schwarzer Rand, Höhe 45px

## Bildsprache
Dichte, farbstarke Produkt- und Gesichtsfotos, die ganze Felder füllen, Pastell- und Beerentöne, viel Glanz. Typografie in den Bildern ist grafisch und verspielt. Im Beispiel ersetzen CSS-Flächen aus Verläufen und einfachen SVG-Formen jedes Foto.

## Animation
Zurückhaltend: Karussell mit weichem Schieben (0.4s), Herz und Knöpfe mit leichtem Skalieren (1.04) im Hover, 0.2s. Keine Parallax-Effekte, kein Dauerblinken.

## Tonfall
Kurz, freundlich, direkt. Aktionen als zwei Wörter ("Jetzt ansehen"). Aktuelle Sammlungen werden mit einem Satz vorgestellt, der Vorfreude weckt. Keine Fachsprache, kein Druck.

## Mach
- Eine Signalfarbe in Rosa sparsam einsetzen, den Rest Weiß und Schwarz halten
- Alle Knöpfe als schwarze Pillen mit Creme-Schrift
- Weit gesetzte Rundschrift (0.05em) in einem einzigen Gewicht
- Etiketten ("neu", "limitiert") auf jeder Kachel
- Bildflächen groß und bunt, Oberfläche leise

## Mach nicht
- Keine eckigen Knöpfe, keine Radien unter 8px
- Keine zweite Signalfarbe auf der Oberfläche
- Keine Serifen- oder Schreibschrift im Fließtext
- Keine dicken Schatten und keine Glasflächen
- Keine dunkle Seite, der Grund bleibt Weiß

## Typische KI-Fehler in diesem Stil
- Rosa als Vollfläche für die ganze Seite oder Karten statt als Leiste und Akzent
- Knopfradius 6px statt Pille, wodurch der Charakter verloren geht
- Laufweite vergessen, Text wirkt eng und gewöhnlich
- Zu viele Gewichte, Überschriften in 800 statt 500
- Kacheln ohne Etiketten und Herz, wodurch die Kataloganmutung fehlt
- Hero als einzelnes Bild statt dreigeteiltem Streifen
