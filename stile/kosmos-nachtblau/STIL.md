# Stil: Kosmos nachtblau

## Kurzbeschreibung und Stimmung
Dunkel, ruhig, selbstbewusst-technisch. Der Seitengrund ist ein kühles Blauschwarz. Im Hero verläuft er von Mitternachtsblau (`#000240`) nach Schwarz. Von unten steigt ein violetter Lichtkegel mit feinen Sternpunkten auf, und darin schwebt der Produkt-Screen. Die Seite wirkt wie ein Nachthimmel über einer Werkbank. Die Headline ist groß, zentriert und eng gesetzt, und es gibt genau einen kräftig grünen Knopf. Alles andere bleibt Weiß, Grau und Glasrand.

## Farbpalette
- Seitengrund: `#111a24`, tiefste Flächen und Abschnittswechsel `#000000`, Fußbereich `#0f1511`
- Hero-Verlauf: von oben `#000240` nach transparent/Schwarz (`linear-gradient(#000240, rgba(0,0,0,0))`)
- Lichtkegel: Radial-Verlauf von unten, `#e6b7fe` (10 %), `#5049c2` (20 %), `rgba(87,78,255,0)` (60 %). Nur hinter dem Produkt-Screen, nie als Vollflächenfarbe
- Text: Weiß `#ffffff` für Headlines, `rgba(255,255,255,.85)` für Lead, gedämpft `#a4aea6`, schwach `#7c8980`
- Link- und Hervorhebungsfarbe: Hellblau `#a2daff`
- Primäraktion: Grün `#138636` (Hover `#1a9a40`), Schrift weiß
- Sekundär-Fläche: `rgba(255,255,255,.06)`, kräftiger `rgba(255,255,255,.2)`
- Linien: `rgba(255,255,255,.1)`, Knopfrand sekundär `rgba(255,255,255,.6)`, dezente Trenner `#191f1b`
- Fokus-Blau `#1f6feb`

## Typografie
- Schrift: Inter (Google Fonts, Gewichte 400 bis 600) mit System-Fallback; für Code und Labels JetBrains Mono oder die System-Monospace.
- H1: 4rem (Mobil 2.5rem), Gewicht 400, Zeilenhöhe 1.08, Laufweite -0.035em (-2.24px), zentriert, Weiß
- H2: 2.5rem (Mobil 2rem), Gewicht 500, Zeilenhöhe 1.2
- H3: 1.375rem (Mobil 1.25rem), Gewicht 600, Zeilenhöhe 1.4
- Fließtext und Lead: 1.125rem, Gewicht 400, Zeilenhöhe 1.5, Laufweite +0.01em
- Navigation und Knöpfe: 1rem, Gewicht 500 bis 600
- Klein und Labels: 0.875rem bzw. 0.75rem, Mono, Versalien nur für Code-Kopfzeilen
- Gewichte: 400, 500, 600. Keine Fettschrift über 600, keine Kursivschrift

## Abstände und Raster
- Leiter in rem: 0.25, 0.5, 0.75, 1, 1.5, 2, 3, 4, 6
- Innenabstände: Knöpfe 0.75rem x 1.25rem, Karten 1.5 bis 2rem, große Rahmen 3 bis 4rem
- Lücken: 0.75rem, 1rem, 1.5rem; zwischen Abschnitten 6rem (Mobil 4rem)
- Inhaltsbreite max. 1280px, Textblöcke 600px, Headline bis 924px
- Header 1rem vertikal, volle Breite, Inhalt links Logo und Menü, rechts Suche und Knöpfe

## Layout-Muster
- Hero: zentriert. Headline in zwei Zeilen, darunter ein dreizeiliger Lead mit 600px Breite, dann eine Aktionszeile aus Eingabefeld mit eingebettetem grünem Knopf und einem Umriss-Knopf. Auf dem Handy stapeln sich die Elemente in voller Breite.
- Darunter der Lichtkegel mit einigen schwebenden hellen Formen und feinen Sternpunkten, der in einen großen Produkt-Screen übergeht.
- Reiter-Pille: eine breite Kapsel mit fünf Reitern, aktiver Reiter mit hellerer Fläche, darunter ein kurzer zentrierter Erklärsatz.
- Logo-Band: Kundenlogos einfarbig, hell-grau, in einer Reihe, am Rand ausgeblendet.
- Danach lange Abschnitte auf Schwarz mit großen Karten (Radius 24px, obere Kante rund) und einem eigenen Lichtkegel je Abschnitt.
- Fußbereich dunkelgrün-schwarz `#0f1511`, mehrspaltige Linklisten in Grau.

## Komponenten
- Primärknopf: grün `#138636`, weiße Schrift 600, Radius 6px, Höhe 2.75rem, Hover heller
- Sekundärknopf: transparente Fläche, 1px-Rand `rgba(255,255,255,.6)`, Radius 6px, weiße Schrift
- Kleine Header-Knöpfe: 1px-Rand `rgba(255,255,255,.1)`, Radius 6px; "Anmelden" dunkel, "Registrieren" auf `rgba(255,255,255,.12)`
- Eingabefeld: helle Fläche `#e6e6ee` mit Innenschatten-Rand, Radius 8px, Schrift dunkel `#24292f`; der Knopf sitzt im Feld
- Reiter-Pille: Radius 60px, 1px-Rand `rgba(255,255,255,.2)`, aktiver Reiter Fläche `rgba(255,255,255,.2)`
- Karten und Screen-Rahmen: Fläche `rgba(255,255,255,.06)`, 1px-Rand `rgba(255,255,255,.1)`, Radius 12px bis 24px, keine Schlagschatten
- Kleine Symbolknöpfe (Pause, nach oben): Kreis 50 %, Fläche `rgba(255,255,255,.2)`

## Bildsprache
Produkt-Screens als Hauptbild: dunkle Code-Editor-Oberfläche in einem hell umrandeten Rahmen mit rundem Rand. Dazu abstrakte weiche Formen, Sternpunkte und Lichtkegel in Violett und Hellblau. Kundenlogos einfarbig und gedämpft. Keine Stockfotos mit Menschen. Im Beispiel: CSS-Verläufe, Inline-SVG-Sterne und ein gezeichneter Code-Rahmen als Platzhalter.

## Animation
Ruhig und weich. Hover und Fokus 100 bis 200ms mit `cubic-bezier(.25,.1,.25,1)`, Einblenden 300 bis 500ms mit `cubic-bezier(.3,.8,.6,1)`. Der Lichtkegel atmet langsam (8s, Deckkraft 0.8 bis 1). Sterne funkeln leicht. Das Logo-Band läuft langsam seitwärts und hat einen Pause-Knopf. `prefers-reduced-motion` abschalten.

## Tonfall
Gemeinschaftlich, klar, zukunftsgewandt. Kurze Aussagesätze mit einer großen Idee in der Headline und einem sachlichen Lead darunter. Wir-Perspektive, direkte Ansprache, keine Superlative, keine Ausrufezeichen. Knopftexte sind Verben ("Konto anlegen", "App laden").

## Mach
- Hero zentriert, Headline in zwei Zeilen mit eng gesetzter Laufweite
- Seitengrund `#111a24`, Hero-Verlauf von `#000240` nach Schwarz
- Genau ein grüner Primärknopf pro Ansicht, daneben ein Umriss-Knopf
- Lichtkegel in Violett hinter dem Produkt-Screen
- Rahmen als 1px-Linie in Weiß mit niedriger Deckkraft, Radius 6 bis 24px
- Weiß für Headlines, Grau `#a4aea6` für Nebentext
- Gewicht 400 für die große Headline nutzen (variable Schrift)
- Mobil: alles einspaltig, Knöpfe in voller Breite, H1 auf 2.5rem

## Mach nicht
- Keine Schlagschatten, Schatten ersetzt der helle Rand
- Kein Grün außer für die Primäraktion
- Keine hellen Seitenflächen, keine weißen Abschnitte
- Kein Verlauftext, keine Neon-Farben außerhalb des Lichtkegels
- Keine Pillenform für normale Knöpfe (Pille nur für die Reiter-Kapsel)
- Keine Headline in Versalien, keine Gewichte über 600
- Keine Stockfotos

## Typische KI-Fehler in diesem Stil
- Headline zu fett (700+) und mit normaler Laufweite statt Gewicht 400 und -0.035em
- Seitengrund reines Schwarz oder Violett-Vollfläche statt `#111a24` mit gezieltem Lichtkegel
- Mehrere grüne oder bunte Knöpfe, sodass der Primärknopf nicht mehr hervorsticht
- Schlagschatten und Glow an jeder Karte statt dünner heller Ränder
- Lichtkegel als flächiger Vollbild-Verlauf, der den Text überdeckt (Kontrast unter 4.5:1)
- Knöpfe als Pillen oder mit großem Radius statt 6px
- Hero linksbündig statt zentriert
- Lead in Weiß mit vollem Gewicht statt 400 mit gedämpfter Farbe
