# Stil: Leinwand klar

## Kurzbeschreibung und Stimmung
Ein heller, sehr ruhiger Produktauftritt, der Bildmaterial wie eine Leinwand behandelt. Oben steht ein großes, rundum abgerundetes Heldenbild mit abgedunkeltem Foto und weißer Schlagzeile. Darunter wechseln sich fast weiße Flächen mit einem tiefen blauschwarzen Block ab. Das einzige Farbsignal ist ein eisiges Cyan auf den Hauptknöpfen. Gefühl: souverän, freundlich, werkzeugartig, nie laut.

## Farbpalette
- Seitengrund `#fafcfd` (fast weiß, kühl), Flächen und Hover `#f1f5f9`
- Dunkelabschnitt `#141a20`, Karten darauf `#192028`, Linien/Chips darauf `#28313a`
- Text: Überschrift und Links `#0a0e12`, Fließtext `#23313b`, Sekundärtext `#4c5864`, gedämpft `#3d4751`, auf Dunkel gedämpft `#a9b2bc`, auf Dunkel hell `#fafcfd`
- Signal Cyan `#17d5ff`, Hover/Fläche etwas tiefer `#00b8e0`. Nur für primäre Knöpfe und Play-Symbole, nie für Text
- Bildabdunkelung: Schwarzschleier `rgba(10,14,18,.4)`
- Keine Verläufe in der Oberfläche selbst, Verläufe nur als Bildplatzhalter

## Typografie
- Grotesk mit engem Zug: Inter Tight (Google Fonts). Mono für Eyebrows: IBM Plex Mono
- Hero-H1 und große H2: 4.5rem (Mobil 2.5rem), Gewicht 500, Zeilenhöhe 1, Laufweite -0.05em
- Abschnitts-H2: 2.5rem, Gewicht 500, Laufweite -0.04em
- H3 (Kartentitel): 1.5rem, Gewicht 500, Zeilenhöhe 1.1, Laufweite -0.04em
- Lead: 1.125rem bis 1.25rem, Gewicht 400, Zeilenhöhe 1.4, Laufweite -0.03em
- Fließtext: 1rem, Gewicht 400, Zeilenhöhe 1.5, Laufweite -0.02em; Kartentext 0.875rem
- Eyebrow: IBM Plex Mono, 1rem, Versalien, Gewicht 400, Laufweite -0.03em
- Gewichte nur 400 und 500, Fett (700) praktisch nie

## Abstände und Raster
- Maximalbreite 1440px, Seitenrand außen 2rem (Mobil 1rem), Textblöcke höchstens 40rem
- Basiseinheit 4px, häufige Schritte 8, 16, 20, 24, 32, 40, 56 px
- Abschnitte vertikal 5rem bis 7rem Abstand
- Kachelraster 3 Spalten mit 2.5rem Lücke, darunter eine zweite Reihe; unter 800px eine Spalte
- Innenabstand Knopf 1rem 1.5rem, Link-Chip 8px

## Layout-Muster
- Kopfzeile: Wortmarke links, Menüpunkte mit kleinem Chevron, rechts Textlink und Cyan-Knopf, alles in einer Zeile ohne Linie
- Hero: Bildfläche mit 2rem Rand rundum, Radius 16px, Inhalt zentriert: Mono-Eyebrow, zweizeilige Schlagzeile in Weiß, Zweizeiler, ein Cyan-Knopf. Unten rechts eine kleine Glas-Karte mit Play-Symbol und Kurztext
- Direkt darunter ein Logoband in Grau, einzeilig
- Intro-Abschnitt: zentrierte Aussage-Überschrift, Text rechts eingerückt, ein Cyan-Knopf
- Dunkelabschnitt: Überschrift zentriert, darunter 3 mal 2 Kacheln, jede mit Bildfläche oben, Titel, zwei Zeilen Text und Ghost-Knopf
- Heller Abschnitt: Überschrift links, Text in schmaler Spalte, darunter Bild links und Liste mit Icon, Titel, Pfeil und Beschreibung rechts

## Komponenten
- Primärknopf: Cyan `#17d5ff`, Text `#0a0e12`, Gewicht 500, 1rem, Radius 12px, Innenabstand 1rem 1.5rem, Pfeil → nach dem Text, Hover `#00b8e0`
- Ghost-Knopf auf Dunkel: Fläche `#28313a`, Text `#a9b2bc`, Radius 8px, Innenabstand 0.75rem 1rem, Pfeil
- Navigationslink: 1rem, Gewicht 400, Radius 8px mit transparentem Grund, Hover `#f1f5f9`
- Glas-Karte: `rgba(255,255,255,.6)` mit Unschärfe 12px, Radius 16px
- Kachel: Bildfläche Radius 12px, Karte selbst ohne Rand und ohne Schatten
- Schwebende Panels (z. B. Hinweise): Schatten `0 0 32px -5px rgba(14,18,22,.24)`, Radius 16px
- Radien: 6, 8, 12, 16px; Kreise nur für Icon-Schaltflächen

## Bildsprache
Warme, natürliche Alltagsfotos mit Menschen bei der Arbeit, im Hero stark abgedunkelt (Schleier 40 %), damit weiße Schrift lesbar bleibt. Produktansichten erscheinen als schematische Oberflächen mit grauen Balken statt Text. Im Beispiel: CSS-Verläufe in gedeckten Tönen und einfache SVG-Formen als Platzhalter, jeweils mit abgerundeten Ecken.

## Animation
Zurückhaltend. Hover-Wechsel der Knopffarbe und des Link-Hintergrunds in 0.2s. Das Logoband läuft langsam und endlos seitlich (30s linear), stoppt bei Hover. Bei reduzierter Bewegung abschalten. Keine Parallax-Effekte.

## Tonfall
Kurz, einladend, selbstbewusst. Schlagzeilen sind knappe Aussagen mit Du-Bezug, Absätze erklären in zwei Sätzen den Nutzen. Knopftexte sind Verben ("Kostenlos starten", "Demo anfragen"), Lernlinks benennen das Thema.

## Mach
- Seitengrund `#fafcfd`, Dunkelabschnitt `#141a20`, Cyan nur auf Knöpfen
- Schlagzeilen in gewicht 500 mit negativer Laufweite
- Mono-Eyebrow in Versalien über der Hero-Schlagzeile
- Heldenbild mit Rand und 16px Radius, nicht randlos
- Pfeil in jedem Knopf und Lernlink
- Kachelreihen mit Bild oben, dann Titel, Text und Ghost-Knopf

## Mach nicht
- Keine harten schwarzen Ränder oder dicke Linien
- Kein Fettdruck 700 für Überschriften
- Kein zweiter Akzent neben Cyan
- Keine eckigen Knöpfe, keine Pillenform für Hauptknöpfe
- Keine starken Schatten auf Karten
- Keine Emoji

## Typische KI-Fehler in diesem Stil
- Cyan zu großflächig verwendet, etwa als Abschnittshintergrund oder Textfarbe statt nur auf Knöpfen
- Überschriften ohne negative Laufweite und mit Gewicht 700, wodurch der enge, ruhige Zug verloren geht
- Heldenbild randlos über die ganze Breite statt mit Rand und 16px Radius
- Dunkelabschnitt in reinem Schwarz `#000` statt blauschwarz `#141a20`
- Weißer Text auf Cyan oder fehlender Abdunkelungsschleier, sodass die Hero-Schrift schwer lesbar ist
- Kacheln mit Schatten und Rahmen statt flacher Bildfläche mit Text darunter
