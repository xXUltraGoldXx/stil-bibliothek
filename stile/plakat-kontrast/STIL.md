# Stil: Plakat Kontrast

## Kurzbeschreibung und Stimmung
Sportlich, knapp, selbstbewusst. Ein bildfüllender, dunkler Einstieg mit dünnen vertikalen Rasterlinien, einer riesigen Zahl in der Mitte und kleinen Kennzahlen in den Ecken, wie ein Rennplakat oder eine Startaufstellung. Danach wechselt die Seite auf Weiß mit wenigen, sehr großen Versalien-Aussagen. Genau eine Signalfarbe (Gelb) setzt Akzente, alles andere ist Schwarz, Weiß und Grau. Keine Schatten, kaum Rundungen, keine Dekoration außer Linien.

## Farbpalette
- Schwarz `#000000` für Hero, Footer und Menüflächen; Fließtext auf Weiß `#333333`
- Weiß `#ffffff` als Hauptfläche der Inhaltsabschnitte; Hellgrau `#f2f2f2` nur selten für Eingabefelder und Trennflächen
- Signalgelb `#fed60a`: Knöpfe, Menüsymbol, hervorgehobene Wortgruppen, nie als Fläche größer als ein Band
- Text auf Schwarz: Weiß `#ffffff`, gedämpft `rgba(255,255,255,.8)`, schwach `rgba(255,255,255,.5)`
- Linien: auf Dunkel `rgba(255,255,255,.2)`, auf Hell `rgba(0,0,0,.05)` bis `rgba(0,0,0,.1)`
- Verläufe nur als Ausblendung: Schwarz nach transparent am unteren Rand des Heldenbilds, damit Text lesbar bleibt

## Typografie
- Überschriften, Kennzahlen, Knopfbeschriftung: Anton (Google Fonts), immer VERSALIEN, Zeilenhöhe 1 bis 1.1, Laufweite normal
- Fließtext und Navigation: Helvetica, Arial, sans-serif, Zeilenhöhe 1.4, klein
- Größen: Riesenzahl `clamp(8rem,22vw,10rem)`, H1/H2 `clamp(2.25rem,5vw,4rem)`, Statement bis 4rem, Kennzahl 1.75rem, Kleintitel 1.45rem
- Fließtext 0.875 bis 1rem, Kennzahl-Beschriftung 0.8rem, Farbe gedämpft
- Gewichte: Anton nur 400 (wirkt von Natur aus fett), Helvetica 400 und 700 (700 für Ortsangaben, Werte)
- Hervorhebung: ganze Wortgruppen im Statement in Gelb oder auf gelber Markierung, nie einzelne Buchstaben

## Abstände und Raster
- Seitenrand 5rem auf Desktop, 1.5rem mobil
- Sektionen vertikal 5rem (klein), 8rem (normal), 10.5rem (groß)
- Lücken: 0.5rem, 1rem, 1.5rem, 4rem; Innenabstand von Kennzahl-Blöcken 1.5 bis 2rem
- Hero-Raster: 6 Spalten, getrennt durch 1px-Linien in `rgba(255,255,255,.2)`; Inhalte hängen an Ecken und Mitte
- Radius klein: 0.25rem für Knöpfe und Felder, 0 für Flächen; keine Schatten

## Layout-Muster
- Hero: bildfüllend, mindestens 100vh, dunkel gegradet. Oben links Logozeichen, oben rechts quadratischer gelber Menüknopf. Links Block mit 3 gestapelten Kennzahlen, Mitte eine riesige weiße Zahl, rechts ein rechtsbündiger Block mit kurzen Fakten, unten links Name und Satz, unten rechts "Nächstes Ereignis" mit Wert
- Statement-Abschnitt: weiß, zentriert, 6 bis 8 Zeilen Versalien in Anton, einzelne Wortgruppen gelb markiert; kleine Schwarzweiß-Bilder asymmetrisch am Rand (links oben, rechts unten)
- Partner-Wand: Logos in zwei versetzten Spalten, dazwischen viel Weiß, abschließend ein gelber Knopf zentriert
- Footer: schwarze Fläche, schlicht

## Komponenten
- Primärknopf: Gelb `#fed60a`, schwarze Anton-Versalien 1rem, Radius 0.25rem, Innenabstand 0.75rem 1.25rem, Pfeil-Symbol dahinter; Hover: Hintergrund wird Schwarz, Text Gelb (150ms)
- Menüknopf: Quadrat 2rem, Gelb, schwarzes Gleichheitszeichen
- Kennzahl: Zahl in Anton 1.75rem weiß, darunter Beschriftung 0.8rem gedämpft
- Eingabefeld: Hintergrund `rgba(0,0,0,.05)`, ohne Rand, Radius 0.25rem, Innenabstand 0.5rem 0.9rem
- Linien: 1px, nur als Raster oder Trenner

## Bildsprache
Dunkle, kontrastreiche Action- und Porträtaufnahmen mit warmen Gelb- und Orangelichtern, Vollbild, stark vignettiert. Kleine Bilder im Inhalt in Schwarzweiß. Logos einfarbig schwarz. Im Beispiel: CSS-Verläufe in Schwarz mit gelbem Schein als Platzhalter, keine echten Fotos.

## Animation
Zurückhaltend und schnell: Hover 150 bis 200ms, sanftes Einblenden der Statement-Zeilen (0.6s ease-out, 20px nach oben). Keine Dauerbewegung. `prefers-reduced-motion` respektieren.

## Tonfall
Kurz, direkt, persönlich und leistungsorientiert. Ich-Aussagen oder knappe Fakten, Zahlen statt Adjektive. Aussagen enden mit Punkt, Beschriftungen bleiben bei ein bis drei Wörtern.

## Mach
- Hero bildfüllend und dunkel, mit 6-Spalten-Linienraster und einer Riesenzahl
- Alle Überschriften in Anton-Versalien, Fließtext klein in Helvetica
- Gelb sparsam: Knöpfe, Menüknopf, Markierungen
- Viel Weißraum zwischen den hellen Abschnitten
- Kennzahlen immer als Paar aus großer Zahl und kleiner Beschriftung
- Statements als Gelb auf Weiß nur bei sehr großer Schrift (ab 2.5rem), sonst gelbe Markierung mit schwarzem Text

## Mach nicht
- Keine Schatten, keine Verläufe außer Ausblendungen
- Keine Schriftmischung mit Serifen, keine Kleinbuchstaben-Überschriften
- Keine großen Rundungen, keine Pillen (maximal 0.5rem)
- Keine zweite Akzentfarbe neben Gelb
- Keine bunten Logos, keine Emoji
- Kein gelber Fließtext auf Weiß

## Typische KI-Fehler in diesem Stil
- Überschriften in Normalschrift statt Anton-Versalien, oder Anton mit Fettung
- Gelb als große Hintergrundfläche oder als Textfarbe für kleine Schrift auf Weiß
- Weiche Kartenschatten und große Radien einbauen, weil sie "modern" wirken
- Hero ohne Rasterlinien und ohne Riesenzahl, stattdessen zentrierte Standard-Headline mit zwei Knöpfen
- Fließtext zu groß und zu dunkel gesetzt, wodurch die Spannung zu den Riesenüberschriften fehlt
- Dunkle Abschnitte durchgängig wiederholen, statt nach dem Hero hart auf Weiß zu wechseln
