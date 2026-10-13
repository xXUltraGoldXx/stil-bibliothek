# Stil: Spielfeld hell

## Kurzbeschreibung und Stimmung
Hell, freundlich und spielerisch-klar. Viel Weiß, wenig Text, eine große zentrale Figur-Illustration und kräftige Flächenfarben. Das Besondere sind die plastischen Knöpfe: Sie haben eine dicke, dunklere Unterkante und werden beim Drücken wirklich eingedrückt. Der Eindruck ist der eines Lernspiels: motivierend, übersichtlich, nie bedrohlich. Der Kern des Stils sind die weiße Fläche, die gesättigten Akzentfarben und die haptischen Knöpfe.

## Farbpalette
- Hintergrund: Weiß `#ffffff`, Flächen und Linien `#e5e5e5`, Hover-Fläche `#f7f7f7`
- Text: Überschrift `#4b4b4b`, Fließtext `#777777`, Grundtext und Navigation `#3c3c3c`, Platzhalter und Deaktiviertes `#afafaf`
- Primär Grün `#5ec41a`, Unterkante `#5aa012`, Hover `#6acf26`
- Sekundär Blau `#2ca8ea`, Unterkante `#2c93cb`; Blau auch für Textlinks und sekundäre Knopfschrift
- Tiefes Nachtblau `#100f3e` für genau einen dunklen Vollbreiten-Abschnitt, Text darauf Weiß
- Sparsam als Illustrationsfarben: Gelb `#ffc800`, Orange `#ff9600`, Rosa `#ff86d0`, Violett `#a560f6`
- Fußbereich: Vollfläche Grün `#5ec41a`

## Typografie
- Eine einzige gerundete Groteske für alles: Nunito (Google Fonts), Rückfall sans-serif.
- H1: 2rem (32px), Gewicht 700, Farbe `#4b4b4b`, zentriert, Zeilenhöhe 1.35
- H2: 3rem (48px) auf dem Desktop, 2.25rem mobil, Gewicht 700, Farbe Grün `#5ec41a`
- Fließtext: 1.0625rem (17px), Gewicht 500, Zeilenhöhe 1.4 (24px), Farbe `#777777`
- Knopf- und Label-Schrift: 0.9375rem (15px), Gewicht 700, Versalien, Laufweite 0.8px
- Nur die Gewichte 500 und 700. Kein Gewicht 300, keine Kursive.

## Abstände und Raster
- Grundleiter in px: 8, 12, 16, 24, 32, 48, 70, 96
- Abschnitte vertikal 70 bis 96px, Inhalt zentriert, Hauptspalte bis 1000px, Textspalten 480 bis 500px breit
- Zweispaltiger Hero mit Bild links und Text rechts, Lücke 80px; mobil einspaltig, Bild oben
- Karten im Raster mit 3 Spalten, Lücke 24px, mobil 1 Spalte
- Knopfhöhe 50px, seitliches Padding 16 bis 24px

## Layout-Muster
- Kopfzeile: Wortmarke links, kleines Versal-Label rechts in `#afafaf`, viel Weiß darunter
- Hero: Illustration und Text mit zentrierter Headline, darunter zwei gestapelte Vollbreit-Knöpfe (330px breit): oben Grün, unten weiß umrandet
- Wechselnde Merkmal-Abschnitte: Bild und Text im Wechsel links und rechts, jeweils eine Überschrift und ein kurzer Absatz
- Genau ein dunkler Nachtblau-Abschnitt (900px hoch) mit zentrierter Bühne als Kontrast
- Abschluss: grüner Fußbereich in voller Breite, davor ein Aufruf mit Knopfpaar

## Komponenten
- Primärknopf: Grün `#5ec41a`, weiße Versalschrift, Radius 12px, Unterkante als Schatten `0 4px 0 #5aa012`; Hover heller; aktiv: `translateY(4px)` und Schatten 0
- Sekundärknopf: Weiß, 2px-Rand `#e5e5e5`, Schatten `0 4px 0 #e5e5e5`, Schrift Blau `#2ca8ea`, Versalien
- Blauer Knopf `#2ca8ea` mit Unterkante `#2c93cb` für Zustimmung in Hinweisleisten
- Karten: Weiß, 2px-Rand `#e5e5e5`, Radius 16px, Unterkante `0 4px 0 #e5e5e5`, kein weicher Schatten
- Hinweisleiste unten fest: Weiß mit 2px-Trennlinie oben, Text links, zwei Knöpfe rechts
- Textlinks: Blau `#2ca8ea`, unterstrichen

## Bildsprache
Flache, runde, gut gelaunte Figuren und Gegenstände in gesättigten Farben, ohne Konturlinien, ohne Verläufe, mit weichen Formen. Eine große Gruppen-Illustration als Blickfang statt Fotos. Im Beispiel: CSS-Formen und Inline-SVG aus Kreisen und Blobs in Grün, Blau, Gelb und Rosa als Platzhalter.

## Animation
Kurz und knackig: Knopf-Druck in 100ms linear, Hover 150ms. Figuren dürfen sanft schweben (4 bis 6s, 8px Hub). Kein Parallax, keine langen Einblendungen. `prefers-reduced-motion` respektieren.

## Tonfall
Duzend, warm, motivierend und kurz. Eine Aussage pro Überschrift, Versprechen statt Erklärung, leichter Humor. Knopfbeschriftungen sind Aufforderungen aus ein bis drei Wörtern.

## Mach
- Weiß als Grund, Farbe nur für Knöpfe, H2 und Illustrationen
- Jeder Knopf mit dicker Unterkante und Druck-Effekt
- Radius konsequent 12px bei Knöpfen und 16px bei Karten
- 2px-Linien in `#e5e5e5` statt Schatten
- Versalien nur bei Knöpfen und Labels
- Kontrast: weißer Text auf Grün nur groß und fett, sonst dunkles Grau

## Mach nicht
- Keine weichen, diffusen Schatten und keine Glasflächen
- Keine Verläufe auf Flächen oder Text
- Keine dünnen Schriftschnitte und keine Serifen
- Keine spitzen Ecken und keine 1px-Haarlinien
- Keine dunklen Seiten im Normalfall, nur der eine Nachtblau-Abschnitt
- Keine Fotos von realen Menschen

## Typische KI-Fehler in diesem Stil
- Knöpfe flach ohne Unterkante gebaut, dadurch geht der plastische Charakter verloren
- Weicher Drop-Shadow statt hartem Versatz-Schatten ohne Unschärfe
- Zu viele Farben gleichzeitig: Grün und Blau sind die Leitfarben, alle anderen nur in Illustrationen
- Eckige oder zu stark gerundete Pillen statt 12px-Radius
- Textblöcke zu lang und zu dicht, der Stil lebt von sehr wenig Text
- Überschriften in Schwarz `#000` statt Grau `#4b4b4b`
- Hover-Effekte mit Anheben statt Eindrücken
