# Stil: Verspielt-bunt

## Kurzbeschreibung und Stimmung
Fröhlich, warm, freundlich, ein bisschen chaotisch. Wie ein Aufkleberbogen oder ein Kinderbuch: runde Formen, dicke Konturen, mehrere kräftige Farben, kleine Hüpf-Animationen. Spaß, aber lesbar.

## Farbpalette
- Hintergrund warmes Creme `#fff7e6`, Text und Konturen tiefes Indigo `#2b2150` (nie reines Schwarz)
- Sechs Spielfarben: Rosa `#ff6fa8`, Gelb `#ffd23f`, Mint `#3ddbb0`, Himmelblau `#4cc9f0`, Lila `#9b5de5`, Orange `#ff9f1c`
- Jede Sektion/Karte bekommt eine Hauptfarbe, die Farben wechseln sich ab
- Text auf Farbflächen immer Indigo (Kontrast prüfen), Weiß nur auf Lila

## Typografie
- Headlines: Fredoka (Google Fonts), Gewicht 600 bis 700, rund und groß (bis 6.5rem)
- Text: Nunito, 1.15rem, Gewicht 400 bis 700, Zeilenhöhe 1.6
- Einzelne Wörter in Headlines farbig hinterlegt oder leicht gedreht (-2 bis 3 Grad)
- Keine Versalien-Schreie, keine dünnen Schnitte

## Abstände und Raster
- Locker und luftig, aber verspielt: Karten leicht versetzt und gedreht (±1 bis 2 Grad)
- Raster 2 bis 3 Spalten, Blasen und Sterne als Deko dazwischen
- Innenabstand der Karten 1.5 bis 2rem, große Außenabstände

## Layout-Muster
- Hero: große Headline mit farbigem Wort, kurzer Satz, großer runder Knopf, daneben ein Maskottchen/Blob aus CSS
- Sektionen: Karten wie Sticker in wechselnden Farben, Wellen- oder Zickzack-Trenner zwischen Sektionen
- CTA: farbige Riesenblase mit Knopf

## Komponenten
- Knöpfe: Pille, 3px Indigo-Kontur, harter Farbschatten unten `0 6px 0`, beim Drücken nach unten rutschen
- Karten: 32px Radius, 3px Kontur, Farbfüllung
- Formulare: runde Felder, dicke Kontur, Fokus in Gelb
- Schatten: nur "Sticker"-Schatten (versetzt, ohne Weichzeichner)

## Bildsprache
Illustrationen aus einfachen Formen, Blobs, Sterne, Wolken, Smileys aus CSS/SVG. Keine Fotos, keine Stock-Bilder. Im Beispiel: ein SVG-Maskottchen.

## Animation
Federnd und kurz: Hüpfen (Ease mit Überschwingen), Wackeln beim Hover, schwebende Deko. Maximal 2 gleichzeitig sichtbare Dauer-Animationen, `prefers-reduced-motion` respektieren.

## Tonfall
Duzen, freundlich, Wortspiele erlaubt, kurze Sätze, Ausrufezeichen sparsam, einzelne Emojis erlaubt. Beispiel: "Hallo, Farbklecks! Lass uns loslegen."

## Mach
- Mehrere Farben, aber mit System (Reihenfolge, Indigo als Anker)
- Alles rund: Radien, Kontur, Formen
- Konsequent dicke Kontur und Sticker-Schatten
- Spaß ohne Lesbarkeitsverlust

## Mach nicht
- Keine spitzen Ecken, keine dünnen 1px-Linien
- Kein Schwarz, kein kaltes Grau
- Keine Verläufe-Orgie (Flächen sind einfarbig)
- Nicht mehr als zwei Dauer-Animationen
- Keine Fließtexte auf farbigem Grund mit schlechtem Kontrast

## Typische KI-Fehler in diesem Stil
- Pastell mit weißer Schrift, unlesbar
- Regenbogen ohne Anker, wirkt chaotisch statt fröhlich
- Verlauf-Knöpfe und weiche Schatten statt Kontur und Sticker-Schatten
- Zu seriöser Text, der zum Look nicht passt
- Dauerhüpfen aller Elemente gleichzeitig
