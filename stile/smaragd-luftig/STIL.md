# Stil: Smaragd luftig

## Kurzbeschreibung und Stimmung
Hell, leise und leicht. Der Grund ist Weiß und ein sehr kühles Blaugrau (`#f8fafc`), darüber liegt ein kaum sichtbares Raster. Überschriften sind extrem dünn gesetzt (Gewicht 200), und ein einziges frisches Smaragdgrün (`#34d399`) setzt die Signale: Hauptknopf, Hervorhebungswort, kleine Labels. Das Produkt zeigt sich als Programmfenster mit weichem, großem Schatten. Gefühl: ein aufgeräumter Werkzeugkasten, der sich nicht aufdrängt. Der Kern des Stils sind das Zusammenspiel aus hauchdünner Display-Schrift und tiefgrünem Text, die Pillenform bei Knöpfen und die Fensterdarstellung des Produkts.

## Farbpalette
- Grund: Weiß `#ffffff`, Wechselfläche `#f8fafc`, Verlaufsfläche von `#f8fafc` nach `#f1f5f9` (180 Grad)
- Text Hauptfarbe: Tiefgrün `#022c22` (Überschriften H2/H3, Links, Navigation)
- Fließtext: Grüngrau `#2c4a3f` für lange Absätze, Schiefer `#475569` für Lead und Beschreibungen
- Schwach: `#64748b` für Nebeninfos, `#94a3b8` auf dunklem Grund
- H1 darf in Nachtblau `#0f172a` stehen
- Akzent: Smaragd `#34d399` (Knopf, Hervorhebungswort), Tiefgrün-Akzent `#059669` für Links und Labels auf Weiß, `#047857` für Text auf hellgrünem Grund
- Dunkelfläche nur für den Fuß: `#0f172a` mit Text `#94a3b8`
- Linien: `#e2e8f0`, grünlich `rgba(5,150,105,.12)`, betont `rgba(5,150,105,.28)`
- Raster im Hero: 1px-Linien `rgba(51,65,85,.04)`, Kachel 48px
- Weiche Lichtflecken: Radial-Verläufe `rgba(148,163,184,.22)` und ein Hauch Grün `rgba(141,162,144,.25)`, nie kräftig

## Typografie
- Headlines: Geist (Google Fonts), Gewicht 200, Laufweite -0.03em, Zeilenhöhe 1.1 (H1) bis 1.2 (H2)
- H1: bis 3.6rem (57.6px), mobil 2.5rem; H2: bis 3.25rem (52px), mobil 2.25rem
- H3: Geist 1.3rem (20.8px), Gewicht 700, Laufweite -0.01em, Zeilenhöhe 1.6
- Fließtext: DM Sans 1rem bis 1.1rem (Lead 17.6px), Gewicht 400, Zeilenhöhe 1.65
- Knöpfe und UI-Texte: Geist 0.8125rem bis 0.9375rem, Gewicht 500
- Eyebrow-Labels: Geist, 0.75rem, Gewicht 600, Versalien, Laufweite 0.13em, Farbe `#059669`
- Code- und Dateinamen: Geist Mono 0.85em auf `#f1f5f9` mit Radius 6px
- Gewichte sonst nur 400, 500, 600, 700. Hervorhebung in der H1: die zweite Zeile in `#34d399`, gleiches dünnes Gewicht

## Abstände und Raster
- Basis 8px: 0.5, 1, 1.5, 2, 3, 4, 6, 8rem
- Inhaltsbreite 1200px, seitlich 2rem (mobil 1rem)
- Sektionen 5rem bis 7rem vertikal, Wechsel zwischen Weiß und `#f8fafc`
- Kartenraster: 3 Spalten, Lücke 1.5rem; Hero 2 Spalten (Text links, Fenster rechts) mit Lücke 4rem
- Innenabstand Karten 1.75rem bis 2rem, Knopfgruppen Lücke 0.5rem bis 0.75rem

## Layout-Muster
- Hero: Raster-Hintergrund, Text linksbündig, daneben das Programmfenster mit schwebender Mitteilungskarte; darunter kleiner Hinweis-Pillenlink
- Sektionskopf zentriert: Eyebrow, H2 mit dünnem Gewicht, Lead mit max. 60ch
- Drei Schritt-Karten mit Nummernlabel ("01 / Titel") in Grün, H3, kurzer Text
- Auswahl-Panel: eine große weiße Karte (Radius 24px) mit Titel, Satz und Reihe von Pillen
- Zweigeteilte Vorschau: links Dialog, rechts Ergebnis, gemeinsam in einer Karte mit Trennlinie
- Fuß dunkel `#0f172a`, schlicht in zwei Blöcken

## Komponenten
- Primärknopf: Pille (999px), Fläche `#34d399`, Rand 1px `#34d399`, Text `#022c22`, Gewicht 500; Hero-Variante Padding 0.9rem 1.75rem, Navigation 7px 16px bei 13px Schrift
- Sekundärknopf: Pille, Weiß, 1px-Rand `#e2e8f0`, Text `#022c22`, Schatten `0 1px 2px rgba(15,23,42,.05)` plus innere weiße Oberkante
- Karten: Weiß oder `#f8fafc`, 1px-Rand `rgba(5,150,105,.12)`, Radius 24px, Schatten `0 1px 3px rgba(0,0,0,.01), 0 8px 24px rgba(15,23,42,.04)`
- Programmfenster: Radius 24px, Titelleiste mit drei runden Fensterknöpfen (50%), Schatten `0 32px 80px rgba(15,23,42,.18), 0 8px 24px rgba(15,23,42,.1), 0 0 0 1px rgba(51,65,85,.12)`
- Pillen-Tags: Radius 999px, Hintergrund `#ecfdf5`, Text `#047857`, 0.75rem
- Eingabefelder: Radius 10px, 1px-Rand `rgba(5,150,105,.28)`, Fokus Rand `#34d399`
- Mitteilungskarte: Weiß, Radius 16px, großer weicher Schatten, leicht über den Fensterrand gesetzt

## Bildsprache
Das Produkt selbst ist das Bild: helle Oberflächen im Fensterrahmen, kleine Interface-Ausschnitte (Liste, Chat, Vorschau), dazu eine feine geometrische Marke in Grün. Keine Fotos von Menschen, keine Stockbilder. Hintergründe sind Raster und weiche Lichtflecken. Im Beispiel: CSS-Flächen und Inline-SVG als Platzhalter.

## Animation
Zurückhaltend. Hover 200ms bis 250ms mit `ease`: Knopf hebt sich 1px, Rand wird grünlicher. Ein langsames Weiterschalten der Fensterbilder (Punkte unter dem Fenster) und sanftes Einblenden mit 0.6s sind passend. Kein Hüpfen, keine Parallaxe, `prefers-reduced-motion` respektieren.

## Tonfall
Ruhig, klar, nutzenorientiert. Kurze Sätze, die ein Versprechen in einem Bild fassen, danach ein nüchterner Satz zur Funktionsweise. Du-Form oder neutral, keine Ausrufezeichen, keine Superlative.

## Mach
- H1 und H2 mit Geist Gewicht 200 und negativer Laufweite setzen
- Grün sparsam: ein Knopf, ein Hervorhebungswort, kleine Labels
- Alle Knöpfe als Pillen, alle Karten mit 24px Radius und 1px-Rand
- Text auf Weiß in `#022c22`, `#2c4a3f` oder `#475569`, mindestens 4.5:1
- Zwischen Abschnitten Weiß und `#f8fafc` abwechseln
- Produkt als Fenster mit großem, weichem Schatten zeigen

## Mach nicht
- Keine fetten Überschriften (kein Gewicht über 200 bei H1/H2)
- Kein Schwarz `#000`, kein kräftiger Schlagschatten, keine harten Ränder
- Keine zweite Akzentfarbe neben Smaragd, kein Violett-Verlauf
- Keine eckigen Knöpfe, keine Versalien bei Überschriften
- Kein Grün als Textfarbe für lange Absätze

## Typische KI-Fehler in diesem Stil
- H1 in Gewicht 600 oder 700 statt hauchdünn, dadurch geht die Luftigkeit verloren
- Smaragd `#34d399` als Textfarbe für kleine Schrift auf Weiß (Kontrast zu gering, dafür `#059669`)
- Zu viel Grün: Karten, Rahmen und Überschriften alle grün statt eines gezielten Signals
- Rastergrund zu kräftig, sichtbar statt kaum wahrnehmbar (Deckkraft über .06)
- Karten mit kleinem Radius oder mit dunklem Schlagschatten statt weichem Schatten
- Reines Grau statt kühlem Blaugrau und Tiefgrün, Text wirkt dadurch kalt und beliebig
