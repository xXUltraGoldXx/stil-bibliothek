# Stil: Marine weich

## Kurzbeschreibung und Stimmung
Ein warmer, ruhiger Shop-Auftritt: cremeweißer Grund, ein einziges tiefes Marineblau für Text, Flächen und Knöpfe, dazu große Fotoflächen. Eine elegante Serifen-Schlagzeile trifft auf eine freundliche, runde Sans-Serif. Gefühl: Schlafzimmer am Sonntagmorgen, hochwertig, aber nie steif. Die Seite verkauft durch Ruhe, klare Wege und viel Luft, nicht durch Lärm.

## Farbpalette
- Grund (Seite) `#fdfaf8`, warmes Off-White, nie reines Weiß als Seitenhintergrund
- Creme `#f9f3ed` für abgesetzte Bänder und Kartenflächen
- Marine `#283455` als Hauptfarbe: Fließtext, Überschriften, Knöpfe, dunkle Bänder (ca. ein Drittel der Fläche)
- Dunstblau `#dde3ec` für Filter-Chips, Kategorie-Kacheln und Highlight-Flächen
- Weiß `#ffffff` für Text auf Marine, helle Knöpfe auf Marine, Karten
- Grün `#417823` nur für Preisvorteile, Rabatt und "verfügbar"
- Grau `#6e6e6e` für Nebentext, Linien `#dddddd` (1px)
- Warnton `#aa3f00` nur für kleine Zähler-Punkte
- Keine Verläufe außer einem dunklen Schleier über Fotos (Schwarz 0.6 bis 0.88 von unten)

## Typografie
- Schlagzeilen groß (Hero, Bandtitel): DM Serif Display (Google Fonts) als Ersatz für eine kontrastreiche Display-Serife, Gewicht 400, Zeilenhöhe 1.15, Farbe Weiß auf Marine oder Foto
- Überschriften und UI: Figtree (Google Fonts) als Ersatz für eine runde Geometrik-Sans, Gewicht 700, Laufweite -0.01em
- Fließtext: Figtree 400, 1rem bis 1.125rem, Zeilenhöhe 1.5
- Stufen: Hero 3.75rem (mobil 2.8rem), Bandtitel 2.25rem, H2 1.5rem (mobil 1.25rem), Lead 1.25rem, Text 1rem, Knopf und Meta 0.875rem
- Leicht negative Laufweite (-0.01em) auf Sans-Text, keine Versalien außer in sehr kleinen Markierungen (0.75rem, Laufweite 0.1em) und einer Hero-Zeile in Versalien Figtree 700

## Abstände und Raster
- Maximale Breite 1440px, seitlicher Innenabstand 4rem (64px) auf Desktop, 1.5rem (24px) mobil
- Abstandsleiter: 0.5, 1, 1.5, 2.5, 4 rem
- Produktraster 4 Spalten ab 1024px, 2 Spalten ab 600px, mobil 2 enge Spalten oder horizontal wischbar, Lücke 1rem
- Bänder und Sektionen vertikal 3rem bis 4rem Abstand
- Hairlines 1px `#dddddd` trennen Listen, Footer-Blöcke und Menüs

## Layout-Muster
- Oben: schmale Marine-Leiste (Höhe 60px) mit zentrierter, unterstrichener Hinweiszeile und Pfeilen links und rechts
- Header auf Grund-Farbe, 91px hoch: Logo links, Hauptnavigation mittig (Figtree 1.25rem, Marine), rechts Suche mit Unterlinie und Icons
- Direkt darunter ein Marine-Band (ca. 104px): Serifen-Titel links, Satz mittig, heller Pillen-Knopf rechts
- Hero: vollbreites Foto (ca. 600px hoch) mit Schleier, zentriert unten Versalien-Zeile, Lead und zwei Pillen-Knöpfe nebeneinander
- Danach Kategorie-Chips, Produktreihen mit Pfeilen, Mosaik aus großen Bildkacheln mit Beschriftung, Creme-Band mit Vorteilen, Newsletter, vierspaltiger Footer

## Komponenten
- Primärknopf: Marine gefüllt, Weiß, Figtree 700 0.875rem, Radius 20px (Pille), Höhe 56px, Innenabstand 0 1.75rem; auf Marine-Flächen invertiert (Weiß mit Marine-Text)
- Sekundärknopf: 2px Rand Marine, transparent
- Chips: Dunstblau, Radius 20px, Höhe 39px, Text Marine
- Karten: Bildfläche mit Radius 12px, darunter Titel (Marine 700), Bewertung, Preis; keine Kartenrahmen, kein Schatten
- Eingabefelder: nur Unterlinie 1px Marine, Platzhalter grau
- Radien: 2px und 4px für Kleinteile, 12px bis 16px für Bilder, 20px für Knöpfe, 50% für Rundknöpfe (Pause, Zähler)
- Schatten fast keine; nur schwebende Rundknöpfe `0 0 25px rgba(0,0,0,.2)`

## Bildsprache
Großformatige, warme, lebensnahe Fotografie mit Menschen und Textilien in natürlichem Licht, gedeckte Töne (Creme, Blau, Sand, Streifen). Bilder laufen vollbreit oder mit 12px Radius. Text auf Fotos liegt auf einem dunklen Schleier. Im Beispiel: CSS-Flächen aus Streifen und weichen Verläufen in Creme, Dunstblau und Sand als Platzhalter.

## Animation
Zurückhaltend: Karussell-Pfeile, sanfter Wechsel der Hinweiszeile, Hover mit leichter Abdunklung des Knopfes (0.2s) und 1.03 Zoom auf Bildern (0.4s). Ein Pause-Knopf gehört zu jedem automatischen Bewegtbild. Kein Parallax, kein Springen.

## Tonfall
Freundlich, direkt, leicht humorvoll, in kurzen Sätzen. Nutzenorientiert (Ersparnis, Komfort, Versand), Knopftexte als klare Verben ("Entdecken", "Bündel ansehen"). Keine Fachwörter, keine Übertreibung.

## Mach
- Marine als einzige Hauptfarbe auf warmem Off-White und Creme
- Serife nur für Hero und Bandtitel, alles andere Figtree
- Pillen-Knöpfe mit 20px Radius, mindestens 56px hoch
- Große Fotoflächen mit dunklem Schleier und zentriertem Text
- Kategorien als Dunstblau-Chips und ruhige Produktraster
- Grün nur für Vorteile und Preise

## Mach nicht
- Kein reines Weiß als Seitengrund, kein Schwarz als Textfarbe
- Keine knalligen Zweitfarben, keine Neon-Verläufe
- Keine eckigen Knöpfe, keine Schatten auf Karten
- Keine Serife im Fließtext oder in Navigation
- Keine dichte Textwand; höchstens zwei Zeilen Beschreibung pro Karte

## Typische KI-Fehler in diesem Stil
- Reines Weiß `#ffffff` und Schwarz statt Off-White `#fdfaf8` und Marine `#283455`
- Knopfradius zu klein (4px) oder voll rund bei Textknöpfen; richtig sind 20px
- Serife überall oder gar nicht, statt gezielt für Hero und Bandtitel
- Zusätzliche Akzentfarben (Orange, Violett) neben Marine, Grün nur für Preisvorteile
- Karten mit Rahmen und Schatten statt freistehender Bildfläche mit 12px Radius
- Hero-Text ohne dunklen Schleier, dadurch schlecht lesbar
- Zu enge Abstände; die Seite muss luftig bleiben (3rem bis 4rem zwischen Sektionen)
