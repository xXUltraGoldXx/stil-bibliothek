# Stil: Fachmarkt freundlich

## Kurzbeschreibung und Stimmung
Ein großer, ordentlicher Online-Fachhandel: kühles Hellgrau als Grundfläche, weiße Kacheln, eine schwarze Servicezeile ganz oben und ein einziger leuchtend grüner Pillen-Knopf als Handlungsaufruf. Die Seite wirkt zugänglich und kompetent. Sie ist dicht an Auswahl, aber nie laut. Gefühl: freundlicher Fachverkäufer, der gut sortiert ist und nicht drängelt.

## Farbpalette
- Seitenfläche `#f3f3f3`, Karten und Eingabefelder `#ffffff`
- Servicezeile und dunkle Flächen `#070707`, Overlay-Abdunklung `rgba(0,0,0,0.7)`
- Text `#1f1f1f`, sekundär `#686868`, gedämpft `#8a8a8a`, Hilfstext auf Dunkel `#a8a8a8`
- Haarlinien `#e6e6e6`, Rahmen von Feldern `#b4b4b4`
- Akzent Grün `#13e47c` nur für Hauptknöpfe, Häkchen und Link-Unterstreichungen
- Mint-Fläche `#e8fafb` für Hinweis- und Dialogkästen
- Sparsam: Violett `#7e00f3` und Cyan `#00ddf6` nur als winzige Marker, nie als Flächen
- Status: Erfolg `#00b27d`, Warnung `#e0af0b`, Fehler `#e64155`
- Keine Verläufe, Schatten nur bei schwebenden Dialogen (`0 0 26px rgba(28,28,28,0.2)`)

## Typografie
- Eine Familie: Open Sans (Google Fonts), Gewichte 400, 600, 700
- H2 36px (2.25rem), Gewicht 700, Zeilenhöhe 46px, Laufweite -1.6px, zentriert
- H1/H3 28px (1.75rem), Gewicht 700, Zeilenhöhe 36px, Laufweite -0.7px
- Knopftext 18px (1.125rem), Gewicht 700, Laufweite -0.36px
- Fließtext 16px, Zeilenhöhe 24px; Listen und Navigation 14px mit 20 bis 22px Zeilenhöhe
- Meta und Kleingedrucktes 12px, Zeilenhöhe 16px
- Mobil: H2 22px, H1 20px, Text 14px, Knopf 16px; Überschriften behalten die enge Laufweite
- Links in Grau `#686868`, unterstrichen oder mit grüner Linie

## Abstände und Raster
- Basis 4px: Abstände 4, 8, 12, 16, 24, 32, 40px
- Innenabstand von Karten 16 bis 32px, Knöpfe 0 23px Seitenpolster bei 48px Höhe
- Inhaltsbreite 1200px, Seitenrand 40px Desktop, 16px Mobil
- Kategorien in 3 Spalten mit 40px Lücke, mobil 1 bis 2 Spalten
- Zwischen Sektionen 64 bis 96px, Überschrift zu Inhalt 32px

## Layout-Muster
- Kopf in drei Ebenen: schwarze Servicezeile (Versand, Kontakt), weiße Hauptzeile mit Menü, pillenförmiger Suche und Icons, darunter Inhalt
- Willkommens-Überschrift zentriert, darunter ein Band aus breiten Teaser-Kacheln mit Radius 6px
- Vertrauensleiste: Symbol links, kurzer Text rechts, drei bis vier Punkte nebeneinander
- Kategorieraster: Bild links, Name rechts, unten eine Haarlinie, ohne Kasten
- Mint-Dialog oder Hinweisband mit Illustration links und Text rechts

## Komponenten
- Hauptknopf: Pille (Radius 50px), Fläche `#13e47c`, Rand 1px gleiche Farbe, 700; Text im Beispiel dunkel `#07140d`, weil Weiß auf Grün zu wenig Kontrast hat
- Zweitknopf: Textlink mit 1px grüner Unterstreichung
- Suchfeld: Pille (Radius 9999px), 1px Rahmen `#6b7280`, Innenpolster links 20px, rechts 80px für das Lupen-Symbol
- Karten: Radius 6px (Dialoge 12px), Weiß, kein Rand oder Haarlinie
- Kleine Etiketten: Radius 2 bis 4px
- Icons als dünne Linienicons 24px in `#1f1f1f`

## Bildsprache
Produktfotos freigestellt auf hellem Grund, Stimmungsbilder mit dunklem Overlay für Teaser. Dazu eine kleine freundliche Illustrationsfigur für Hinweise. Im Beispiel: CSS-Flächen und einfache SVG-Formen in Grau, Mint und Schwarz als Platzhalter.

## Animation
Zurückhaltend. Hover auf Kacheln und Links in 0.15s (Farbwechsel, Unterstreichung). Karussell mit weichem Verschieben 0.3s. Dialoge blenden in 0.2s ein. Keine Parallax-Effekte.

## Tonfall
Persönlich und hilfsbereit, per Sie, kurze klare Sätze. Überschriften als einfache Benennung ("Unsere Kategorien"). Dazwischen ein Augenzwinkern, aber nie Verkaufsdruck. Preise und Versandvorteile sachlich genannt.

## Mach
- Grauen Grund `#f3f3f3` mit weißen Karten kombinieren
- Genau eine Akzentfarbe: Grün als Pille
- Überschriften zentriert, fett, mit enger Laufweite
- Schwarze Servicezeile mit Versand- und Kontakthinweisen
- Haarlinien statt schwerer Kästen im Kategorieraster
- Dichte Auswahl, aber klare 4px-Abstände

## Mach nicht
- Keine Verläufe, keine dicken Schatten, keine Glasflächen
- Keine eckigen Hauptknöpfe
- Kein zweites Akzentgrün oder Violett als große Fläche
- Keine Serifen, keine Versalien-Überschriften
- Keine Weiß-auf-Grün-Schrift in kleinen Größen

## Typische KI-Fehler in diesem Stil
- Den Hintergrund rein weiß machen, statt `#f3f3f3` mit weißen Karten
- Knöpfe mit Radius 8px statt echter Pille
- Violett und Cyan aus der Markenpalette als Flächen oder Verläufe verwenden
- Überschriften ohne negative Laufweite und zu leicht gesetzt
- Kategorien als schattige Kacheln statt als Zeilen mit Haarlinie
- Weiße Schrift auf `#13e47c` bei 14px, die kaum lesbar ist
- Servicezeile oben vergessen, wodurch die Seite generisch wirkt
