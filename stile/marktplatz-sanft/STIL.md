# Stil: Marktplatz sanft

## Kurzbeschreibung und Stimmung
Ein Online-Markt für den Alltag: hell, freundlich, übersichtlich und dicht an Angeboten. Fast der gesamte Text steht in einem einzigen gedeckten Marineblau auf kühlem Hellgrau und Weiß. Weiche Radien, pillenförmige Knöpfe und Suchfelder, flache Kacheln mit kaum sichtbarem Schatten. Gefühl: Man findet sofort, was man sucht, und wird nie angeschrien. Vertrauen und Orientierung gehen vor Show.

## Farbpalette
- Text und Primärfarbe: Marineblau `#192f50` (praktisch jeder Text, jeder gefüllte Knopf, jeder kräftige Rand)
- Seitenfläche: Hellgrau-Blau `#f0f3f7` (größte Fläche, auch Fußbereich und Eingabefelder)
- Karten und Kopfbereich: Weiß `#ffffff`
- Gedämpftes Grau `#899099` für Platzhalter, Sekundärtext und Symbole im Ruhezustand
- Trennlinien `#e5e5e5` und `#f0f3f7` (1px)
- Zarte Aktionsflächen: Rosé `#f7eff5` und Lavendel `#e7e0ef`, nur für einzelne Teaser
- Kräftige Farbe kommt nur aus Aktionsbannern (zum Beispiel ein tiefes Waldgrün `#0f6b3d`) und aus Produktbildern, nie aus der Oberfläche selbst
- Keine Verläufe auf Knöpfen und Karten

## Typografie
- Eine Schriftfamilie für alles: Source Sans 3 (Google Fonts), eine warme, leicht schmale Humanist-Grotesk
- Gewichte: 400 Fließtext, 500 Überschriften und Knöpfe, 700 sehr selten (Preise, Hervorhebung)
- H1 2.5rem (40px) auf Desktop, 1.5rem mobil, Zeilenhöhe 1.5, Gewicht 500
- H2 1.5rem, Zeilenhöhe 1.5; H3 1.25rem, Zeilenhöhe 1.5
- Text 1rem, Zeilenhöhe 1.5; Nebentext 0.875rem (Zeilenhöhe 1.5); Kleintext 0.75rem bis 0.8125rem
- Laufweite normal, keine Versalien, keine Kursive. Überschriften sind schlicht, nur über Größe und Gewicht 500 abgesetzt

## Abstände und Raster
- Maximale Inhaltsbreite 1200px, seitlicher Rand 2.5rem (40px) Desktop, 1rem mobil
- Abstandsskala: 4, 8, 10, 16, 24, 30px; Innenabstand von Karten 16px bis 24px
- Lücken in Kachelreihen 8px bis 16px, bei Chips und Icons 4px bis 8px
- Produktreihen: 4 bis 5 Spalten Desktop, 2 Spalten mobil, oder horizontal scrollbare Reihe mit Pfeilknopf
- Abschnitte trennt vor allem der Wechsel von Hellgrau zu Weiß, nicht Linien; Abschnittsabstand 3rem bis 4rem

## Layout-Muster
- Kopfbereich in Schichten: schmale Hilfsleiste mit Textlinks (0.875rem), darunter Logo links, breite Pillen-Suche in der Mitte, Symbole (Ort, Merkliste, Konto, Warenkorb) rechts, darunter eine Hauptnavigation mit Textlinks in 1rem
- Vorteilsleiste: drei kurze Aussagen mit kleinem Symbol in einer Zeile, 0.875rem, Gewicht 500
- Hero: breites Banner mit gefärbtem Hintergrund, Motiv links, weiße Textkarte mit Radius 12px rechts, darunter Punktanzeige (fünf Kreise, aktiver gefüllt Marineblau)
- Danach eine schlichte H1 in Marineblau, dann Rubriken mit H2 und Kachelreihen
- Fußbereich auf Hellgrau, 30px Innenabstand oben und unten, Linkspalten in 0.875rem

## Komponenten
- Primärknopf: Pille (Radius 44px), Marineblau gefüllt, weißer Text 1rem Gewicht 500, Innenabstand 0.75rem 1.5rem, Rand 2px in derselben Farbe. Zwei Knöpfe nebeneinander teilen sich die Breite
- Sekundärknopf: Pille, weiß oder transparent, 2px Rand in Marineblau, Text Marineblau
- Suchfeld: Pille (Radius 30px), Hintergrund `#f0f3f7`, Rand 2px transparent, Innenabstand links 24px, rechts 40px für das Lupensymbol, Platzhalter `#899099`
- Karten: Weiß, Radius 12px, Schatten `1px 1px 2px rgba(0,0,0,.04), 1px 4px 8px rgba(0,0,0,.08)`, nur auf Kacheln mit Inhalt
- Kleine Flächen (Etiketten, Bildecken) Radius 8px; Pfeil- und Punktknöpfe Vollkreis
- Fokus: 2px Rand in Marineblau, deutlich sichtbar
- Symbole: einfarbig Marineblau, gefüllte Glyphen, 24px

## Bildsprache
Helle, saubere Produktfotos auf weißem oder sehr hellem Grund, freigestellt, mit viel Luft. Aktionsbanner mit satter Hintergrundfarbe und Menschen oder Verpackungen. Bilder haben Ecken mit Radius 8px bis 12px. Im Beispiel dienen weiche CSS-Flächen und einfache SVG-Formen als Platzhalter.

## Animation
Zurückhaltend und funktional: Karussell mit Pfeil und Punkten, Überblendung 0.3s, Hover auf Kacheln hebt den Schatten leicht an. Knöpfe wechseln in 0.2s die Tönung. Kein Parallax, keine Einflug-Effekte.

## Tonfall
Direkt, freundlich, per Du. Kurze, konkrete Nutzenaussagen ("Kostenlos ab 59 Euro", "Heute bestellt, in zwei Stunden abholbereit"). Keine Superlative, keine Ausrufezeichen-Ketten, Fragen als Einstieg sparsam.

## Mach
- Alles in Marineblau `#192f50` setzen, nicht in Schwarz
- Hellgrau `#f0f3f7` als Seitenfläche, Weiß nur für Karten und Kopfbereich
- Pillen für Knöpfe (44px) und Suche (30px), Karten mit 12px
- Gewichte 400 und 500 nutzen, Hierarchie über Größe
- Navigation und Vorteilsleiste vor den Inhalt stellen
- Zwei Primärknöpfe gleich breit nebeneinander, wenn eine Entscheidung ansteht
- Auf Mobil einspaltig stapeln, Knöpfe volle Breite

## Mach nicht
- Kein reines Schwarz für Text, kein kaltes Grau außer `#899099` für Nebensächliches
- Keine großen Schatten, keine Glasflächen, keine Verläufe
- Keine eckigen Knöpfe, keine Rahmen-Eingabefelder mit scharfen Ecken
- Keine Versalien und keine Laufweiten-Spielereien
- Keine zweite Akzentfarbe in der Oberfläche; Farbe gehört in Bilder und Banner
- Keine riesigen Schlagzeilen über 2.5rem

## Typische KI-Fehler in diesem Stil
- Reines Schwarz oder dunkles Anthrazit statt Marineblau `#192f50` verwendet
- Seite komplett weiß gelassen, sodass die Hellgrau-Weiß-Schichtung fehlt
- Knöpfe mit 8px Radius statt Pille, oder Knöpfe in lauter Akzentfarbe
- Zu viel Whitespace und große Hero-Schlagzeilen wie bei einem Marketing-Auftritt; der Stil ist dicht und funktional
- Kopfbereich ohne Suche und Navigation, nur Logo und ein Knopf
- Dicke, dunkle Schatten auf Karten statt der kaum sichtbaren zweilagigen Schatten
- Fett (700) überall statt 500
