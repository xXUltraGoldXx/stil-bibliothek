# Stil: Sand weich

## Kurzbeschreibung und Stimmung
Ein freundlicher, natürlicher Produkt-Shop-Auftritt. Der Seitengrund ist ein warmes Greige, darauf liegen große, weich gerundete Bildflächen und weiße Karten. Eine abgerundete, halbtransparente Navigationsleiste schwebt über dem Hero-Foto. Dunkle Streifen (Hinweisleiste, Footer) setzen ruhige Anker. Gefühl: bequem, ehrlich, alltagsnah, nie laut.

## Farbpalette
- Grund (Body) Sand `#ece9e2`, zweiter Ton `#e0dacf` für Chips und Flächen
- Karten und Overlays Weiß `#ffffff`
- Text Schwarz `#000000`, Fließtext `#1f1f1f`, sekundär `#575757`
- Anker-Dunkel `#212121` für Hinweisleiste und Footer, Text darauf Weiß
- Bildabdunklung: `rgba(0,0,0,.15)` flächig, am Rand Radialverlauf `rgba(0,0,0,.25)` zu transparent
- Produktfarben nur als gedeckte Kachelflächen: Schieferblau `#4f6478`, Kaffee `#4a3a37`, Altrosa `#8a625c`, Salbei `#7f8c78`
- Keine Signalfarbe. Akzent entsteht durch Foto und Kachelfarbe

## Typografie
- Haupt: Grotesk, Hanken Grotesk (Google Fonts), Gewichte 400, 500, 700
- Akzent mono: IBM Plex Mono 400, 0.75rem, Versalien, für Kollektions-Zeilen
- Akzent Serife: Playfair Display 400 sparsam für einzelne Zitate
- Hero-Zeile 1.5rem (Desktop), Laufweite 0.04em, Gewicht 400, Zeilenhöhe 2rem; Abschnittstitel 2.5rem/3.75rem, Gewicht 500
- Labels, Navigation, Knöpfe: 0.75 bis 0.875rem, Gewicht 500, Versalien, Laufweite 0.05em
- Fließtext 1rem, Zeilenhöhe 1.3 bis 1.5
- Mobil: Titel 1.875rem (Zeilenhöhe 2.8rem), Labels 0.75rem

## Abstände und Raster
- Basis 4px, gängig 8, 16, 24, 32, 40, 80px
- Seitenrand nur 10px, Bildkacheln laufen fast randlos
- Produktraster 4 Spalten Desktop, Lücke 10 bis 20px, 2 Spalten mobil
- Footer-Innenabstand 80px 40px 20px (mobil 50px 20px)
- Abschnitte vertikal 56 bis 80px Abstand

## Layout-Muster
- Oben dünne dunkle Hinweisleiste mit zentriertem Einzeiler, Pfeile links und rechts
- Hero: ein riesiges Foto mit Radius 16px, fast randlos; schwebende Navigationsleiste (Weiß, Radius 16px) darin; Text und zwei Pillen-Knöpfe unten rechts
- Darunter Reihe von vier hohen Farbkacheln mit Radius 16px
- Karussell-Zeilen mit Produktkarten, Titel in Versalien darüber
- Footer dunkel `#212121`, mehrspaltige Linklisten, kleine Schrift

## Komponenten
- Knöpfe: Pille (Radius 9999px), halbtransparent hell auf Foto oder Weiß, Versalien 0.875rem, Gewicht 500, Innenabstand 8px 25px
- Navigation: Leiste Radius 16px, Links Versalien mittig, Icons rechts
- Karten: Weiß oder Kachelfarbe, Radius 16px, keine oder nur sehr leichte Schatten (`0 2px 6px rgba(0,0,0,.1)`)
- Bilder oben mit Radius 16px, unten eckig, wenn sie an Text grenzen
- Overlay-Dialog: Weiß, Radius 8px, zentrierte Überschrift 1.5rem, Schließen-Kreuz oben rechts
- Chips: Radius 9999px, 1px Rand `#575757` oder inset-Ring
- Fokus: 3px weißer Rand auf Foto

## Bildsprache
Lebensnahe Fotos im Alltag draußen, Stadt oder Natur, gedämpfte Farben, leichte dunkle Überlagerung, damit weiße Schrift lesbar bleibt. Personen in Bewegung, Produkt nah im Bild. Im Beispiel: CSS-Verläufe in Sand-, Salbei- und Schiefertönen als Platzhalter.

## Animation
Zurückhaltend: Karussell-Gleiten (0.4s ease), Hover auf Knöpfen als Aufhellung (0.2s), Einblenden von Overlays mit Opacity 0.3s. Keine Parallax-Effekte, keine springenden Elemente.

## Tonfall
Kurz, warm, direkt. Wenige Wörter, positive Eigenschaftswörter, Versalien nur für Navigation und Knöpfe. Hinweise sachlich und höflich.

## Mach
- Sandfarbenen Grund `#ece9e2` mit weißen und dunklen Flächen mischen
- Alles Große mit Radius 16px, Knöpfe als Pille
- Schwebende, abgerundete Navigationsleiste über dem Hero
- Kleine Versalien-Labels mit Laufweite 0.05em
- Fotos fast bis zum Rand, 10px Seitenrand
- Dunkle Hinweisleiste und dunklen Footer als Rahmen

## Mach nicht
- Keine kräftigen Neonfarben oder Verläufe auf Flächen
- Keine harten, scharfkantigen Boxen und keine schweren Schatten
- Keine Serifen-Überschriften als Regel
- Keine breiten Seitenränder, die Fotos einsperren
- Keine langen Fließtexte im Hero

## Typische KI-Fehler in diesem Stil
- Reinweißer Seitengrund statt warmem Sand
- Eckige Knöpfe oder Pillen mit kräftiger Farbfüllung statt hell und halbtransparent
- Zu viel Schatten und Verlauf, wodurch der natürliche Eindruck verloren geht
- Hero mit großem Seitenrand statt randnaher Bildfläche mit Radius
- Navigation als flacher, voller Balken statt schwebender, gerundeter Leiste
- Überschriften zu groß und zu fett; der Stil lebt von leisen Größen
