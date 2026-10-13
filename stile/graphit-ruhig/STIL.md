# Stil: Graphit ruhig

## Kurzbeschreibung und Stimmung
Ein dunkler, ruhiger Werkzeug-Look für Software-Produkte. Der Grund ist fast Schwarz mit minimal kühlem Stich, der Text steigt in drei Grautönen auf, und Struktur entsteht fast nur durch 1px-Haarlinien in 8 % Weiß. Farbe ist die Ausnahme: ein einziger Indigo-Ton für Aktionen, sonst nur Grau. Die Seite lebt von einer großen, eng gesetzten Headline links oben und einem Produkt-Screen, der groß, dunkel und am Rand angeschnitten unter dem Hero liegt. Gefühl: konzentriert, schnell, erwachsen, ohne Effekthascherei.

## Farbpalette
- Canvas: `#08090a`; Flächenstufen `#0f1011`, `#161718`; Hover-Fläche `rgba(255,255,255,.02)`, Karten `rgba(255,255,255,.01)` bis `.02`
- Text in vier Stufen: Primär `#f7f8f8`, Sekundär `#d0d6e0`, Gedämpft `#8a8f98`, Schwach `#62666d`
- Haarlinien: `rgba(255,255,255,.08)` Standard, `.12` für hervorgehobene Ränder, `.05` für sehr leise Trenner
- Aktion/Akzent: Indigo `#6c76dc`, Text darauf `#ffffff`
- Heller Primärknopf: `#e6e6e6` bis `#f7f8f8` mit Text `#08090a`
- Statusfarben nur in winzigen Punkten und Tags: Gelb `#e4f222`, Orange `#f7bf8b`, Rosa `#f79ce0`, Türkis `#83dcdc`, Grün `#27a644`, Rot `#f34e52`
- Hero-Ausklang: vertikaler Übergang von `#08090a` nach einem hellen Grau `#d0d6e0` am unteren Rand des Screen-Bereichs, sehr weich und zusätzlich abgedunkelt
- Lichtschein: Radial-Verlauf `rgba(255,255,255,.04)` nach transparent, nur als Hintergrundtiefe

## Typografie
- Eine Familie: Inter (variabel), Fallback System-Sans. Mono: JetBrains Mono (Google Fonts)
- Gewichte: 400 Fließtext, 510 (ersatzweise 500) für Headlines, Knöpfe, Navigation und Labels, 590 (ersatzweise 600) für kleine Überschriften; 300 selten für Zahlen
- H1: 64px / 64px (4rem, Zeilenhöhe 1), Laufweite -0.022em, Farbe `#f7f8f8`; mobil 38px / 1.1
- H2: 40px / 44px, Laufweite -0.022em, oft in Gedämpft `#8a8f98`; mobil 24px / 1.33
- H3: 20px / 1.33, Gewicht 590, Laufweite -0.012em, Farbe `#d0d6e0`
- Fließtext: 15px / 24px, Laufweite -0.011em, Farbe `#8a8f98`; Lead im Hero 15 bis 16px
- Klein: 13px / 19.5px für Knöpfe und Meta, 12px für Labels
- Mono: 11 bis 12px, Versalien, Laufweite .08em, Farbe `#62666d` für Figurenbeschriftungen ("FIG 0.1")
- Zweifarbige Aussagesätze: erste Hälfte `#f7f8f8`, zweite Hälfte `#8a8f98`, gleiche Größe und Gewicht

## Abstände und Raster
- Basis 4px, gängige Werte 4, 6, 8, 12, 16, 24, 32, 40
- Seitenrand 32px (mobil 16 bis 24px), Inhaltsbreite bis etwa 1280px
- Sektionen vertikal 96 bis 160px, Hero oben etwa 200px Luft über der Headline
- Spalten 3 oder 2, Trennung durch vertikale Haarlinien statt Lücken oder Karten-Boxen
- Innenabstand von Panels 32px, Listenzeilen 4 bis 8px, Knöpfe 0 12px bis 0 16px bei 32px Höhe

## Layout-Muster
- Hero linksbündig: große Headline über zwei Zeilen, darunter kurzer Gedämpft-Text links, rechts auf gleicher Höhe ein kleiner Link mit Pfeil
- Direkt darunter ein breiter Produkt-Screen, der rechts und unten aus dem Bild läuft, mit 1px-Rand und 8 bis 12px Radius
- Logo-Reihe: sieben Wortmarken in einer Zeile, gleiche Höhe, helles Grau, darunter ein Mono-Satz in `#62666d`
- Aussagesatz in 32 bis 40px, zweifarbig, über ganze Breite
- Drei Spalten mit Haarlinien dazwischen: oben Mono-Figurenlabel, darunter eine Linienzeichnung (isometrische Körper), darunter H3 und kurzer Text
- Zweispaltiger Abschnitt: links H2 in zwei Zeilen, rechts Absatz und Pfeil-Link; darunter ein UI-Ausschnitt, der angeschnitten ist
- Ganz oben optional ein 32px hoher Indigo-Streifen mit weißem Text

## Komponenten
- Navigation: 72px hoch, Haarlinie unten, Links 13 bis 14px in `#8a8f98`, Hover `#f7f8f8`; rechts Textlink "Anmelden" und heller Pillenknopf
- Primärknopf: Pille (9999px), Fläche `#e6e6e6`, Text `#08090a`, 14px, Gewicht 510, Höhe 32px
- Aktionsknopf: Indigo `#6c76dc`, Text weiß, Radius 8px, Höhe 32px
- Sekundär: transparent, Text `#8a8f98`, Radius 9999px, Hover Fläche `rgba(255,255,255,.04)`
- Panels: Fläche `#0f1011`, Rand `1px solid rgba(255,255,255,.08)`, Radius 8 bis 12px, innen zusätzlich `inset 0 0 0 .5px rgba(255,255,255,.08)`
- Code- und ID-Chips: Mono 12px, Fläche `#161718`, Radius 4 bis 6px, Rand `.08`
- Tags: Pille, 12px, Rand `.08`, farbiger 6px-Punkt davor
- Schatten selten: `0 2px 32px rgba(0,0,0,.25)` für schwebende Panels

## Bildsprache
Hauptmotiv ist der Produkt-Screen selbst: dunkle Oberfläche, Seitenleiste, Ticket-Detail, Aktivitätsliste, schwebendes Chat-Panel. Er ist echt wirkend, aber leise, mit gedämpften Grautönen und nur kleinen Farbpunkten. Dazu feine Linienzeichnungen isometrischer Körper (Stapel, Würfelgruppe, Lamellen) in 1px `rgba(255,255,255,.35)` auf Schwarz, ohne Füllung. Keine Fotos, keine Illustrationen mit Farbflächen. Im Beispiel: CSS-Panels und Inline-SVG als Platzhalter.

## Animation
Zurückhaltend und schnell: Hover 150 bis 200ms, Ease-out; Einblenden von unten 12 bis 20px in 0.5s; Screen-Inhalte können sich nacheinander ruhig füllen. Nichts hüpft, nichts blinkt. `prefers-reduced-motion` respektieren.

## Tonfall
Sachlich, knapp, kompetent. Kurze Sätze, Produktkategorie klar benannt, keine Ausrufezeichen, keine Superlative. Lead-Texte zwei Zeilen lang, Abschnittstitel als Substantivgruppen ("Eingang und Anbindungen"). Sie-Form oder neutral.

## Mach
- Fast schwarzen Grund `#08090a` mit Haarlinien statt Boxen und Schatten
- Headlines groß (64px), Gewicht 510, Laufweite -0.022em
- Texthierarchie über vier Graustufen statt über Farbe
- Indigo nur für eine Hauptaktion pro Ansicht
- Produkt-Screen groß und angeschnitten zeigen
- Mono-Labels klein und leise für Struktur
- Kontrast: Fließtext mindestens `#8a8f98` auf `#08090a` (etwa 6:1)

## Mach nicht
- Keine Verläufe auf Text, keine Neon-Glows, keine bunten Karten
- Kein reines Schwarz `#000` und kein reines Weiß als Fläche
- Keine dicken Rahmen, keine großen Schlagschatten, keine Radien über 12px bei Panels
- Keine Gewichte über 590, keine Versalien-Headlines
- Keine Emoji, keine Stockfotos

## Typische KI-Fehler in diesem Stil
- Mehrere Akzentfarben gleichzeitig statt eines einzigen Indigo-Tons
- Glasmorphismus mit Blur und leuchtenden Rändern statt flacher Flächen mit 8%-Haarlinie
- Headline zu fett (700) und zu locker gesetzt, die enge Laufweite fehlt
- Zentrierter Hero mit zwei bunten Knöpfen statt linksbündiger Headline mit leisem Textlink
- Karten mit Schatten und großem Radius statt Spalten mit vertikalen Trennlinien
- Text-Grau zu dunkel (`#62666d`) für Fließtext, Kontrast unzureichend
- Produkt-Screen vollständig eingerahmt statt angeschnitten
