# Stil: Erdton ruhig

## Kurzbeschreibung und Stimmung
Ruhig, sachlich, handwerklich-architektonisch. Der Auftritt beginnt mit einer anthrazitfarbenen Bühne (`#262626`), auf der wenige große Wörter und ein Foto mit angeschnittenen Ecken stehen. Danach folgen weiße Flächen mit sehr kleinem Fließtext in Mittelgrau und eine Folge gestapelter Farbflächen in gedämpften Erdtönen. Das Gefühl: ein gut gepflegtes Büro, in dem Zuhören vor Gestalten kommt. Kern des Stils sind die gestapelten Erdfarben-Flächen, die leichte Grotesk in nur einem Gewicht und der Kontrast zwischen riesiger Headline und winziger Detailschrift.

## Farbpalette
- Grund hell: `#ffffff`; Grund dunkel (Hero, Fußbereich): `#262626`
- Text: Fast-Schwarz `#111111` für Titel, Mittelgrau `#747474` für Fließtext und Metadaten (häufigste Textfarbe), Hellgrau `#a3a3a3` auf Dunkel, Weiß `#ffffff` auf Dunkel
- Linien und Platzhalter: `#d6d6d6`
- Erdton-Flächen, jeweils eine pro Panel: Braungrau `#625653`, Terrakotta `#925434`, Dunstblau `#c9d3df`, Moosgrau `#707569`, Sand `#e3c1aa`
- Schrift auf dunklen Erdtönen (Braungrau, Terrakotta, Moosgrau): Weiß; auf hellen (Dunstblau, Sand): `#262626`
- Knopf auf Bildern: `rgba(14,14,14,.6)` mit weißem Text
- Kein Akzent im Sinne einer Signalfarbe; die Farbe kommt allein aus den Erdton-Flächen und den Fotos

## Typografie
- Eine einzige Familie: geometrische Grotesk, Hanken Grotesk (Google Fonts), Gewicht 400
- Fast alles Gewicht 400; Gewicht 600 nur ausnahmsweise für ein einzelnes Detail
- Laufweite normal, keine Versalien, keine Mono-Schrift
- Display (Hero-Wörter): `clamp(2.875rem, 5.9vw, 4.7rem)`, Zeilenhöhe 1 (75px bei 1280px)
- Statement-Headline: 3.5rem (56px) Desktop, Zeilenhöhe 1.1; Panel-Titel 3rem (50px) bzw. 2.375rem (38px); kleine Überschrift 1.75rem
- Fließtext 0.875rem (14px), Zeilenhöhe 1.35, Farbe `#747474`; Navigation und Links 1rem; Mikrotext (Zähler wie 1 / 5, Hochzahlen) 0.75rem
- Mobil: Display ca. 2.875rem, Statement 2.75rem, Zeilenhöhe 1.05 bis 1.1

## Abstände und Raster
- Maximalbreite 1280px, Seitenrand 2rem Desktop, 1rem Mobil
- Zwei Schichten: ein feines 26-Spalten-Raster für Platzierung (Text im Statement beginnt etwa in Spalte 8), im Alltag zwei bis drei Blöcke pro Zeile
- Innenabstände der Panels: 0.9rem bis 1.6rem (15, 20, 25px); Lücken klein: 2, 7, 10, 13px
- Sektionen vertikal 6 bis 8.5rem (Abstandsvariable 8.5rem), Fußbereich beginnt mit 7.5rem Luft
- Radien: 4px an Kleinteilen, 6px an Knöpfen, 13px an Bildern, 50% an runden Pfeil-Symbolen

## Layout-Muster
- Hero: volle Fensterhöhe, anthrazit, zentriert, drei Elemente nebeneinander: links zwei gestapelte Wörter, in der Mitte ein Foto mit abgeschnittenen Ecken (diagonal), rechts zwei gestapelte Wörter tiefer versetzt. Mobil: die drei Elemente untereinander, versetzt links und rechts
- Panel-Stapel: fünf volle Streifen von je ca. 17rem Höhe direkt übereinander, jeder in eigener Erdfarbe, links oben der Titel, unten links Kurzzeile und Zähler "2 / 5", rechts unten ein kleines Vorschaubild mit angeschnittener Ecke, am rechten Rand ein schmaler Bildstreifen
- Statement: sehr große Headline über zwei bis drei Zeilen links, darunter zweispaltig: links Mikrotext, rechts kleiner Absatz mit Textlink
- Arbeitsproben: Überschrift links, darunter Filterleiste mit Haarlinie, Kacheln in drei Spalten
- Fußbereich: wieder anthrazit, viele kleine Links in Spalten

## Komponenten
- Textlink mit Pfeil: 1rem, unten 1px-Linie `#d6d6d6`, daneben runder Pfeil-Kreis (50%, Fläche `#d6d6d6`, 1.5rem)
- Filter: Textlinks mit Hochzahl für Anzahl (0.75rem), Haarlinie darunter 1px `#d6d6d6`
- Knopf auf Bild: Radius 6px, Fläche `rgba(14,14,14,.6)`, weißer Text 1rem, Innenabstand 0.5rem 0.9rem
- Panel-Unterlinks: weißer Text 0.75rem, 1px weiße Unterlinie, Pfeil rechtsbündig
- Bildrahmen: Radius 13px oder diagonal abgeschnittene Ecken (clip-path)
- Keine Schatten (alle gemessenen Schattenwerte leer), keine Verläufe

## Bildsprache
Echte, ruhige Architektur- und Innenraumfotos in natürlichem Licht, dämmrig oder bei klarem Himmel, ohne Menschenmassen. Fotos werden zugeschnitten, nicht verfremdet; einzelne Ecken sind diagonal abgeschnitten. Farben der Panels sind aus den Fotos gezogen (Backstein, Holz, Himmel, Grün, Sand). Im Beispiel: CSS-Flächen in Erdtönen als Platzhalter.

## Animation
Zurückhaltend. Panels und Wörter blenden mit 0.6s Ease-out ein oder schieben sich 1.5rem nach oben; der Hero-Bereich darf beim Scrollen die Wörter zueinander verschieben. Hover: Unterlinie wird dunkler, 200ms. Kein Federn, kein Wackeln. `prefers-reduced-motion` respektieren.

## Tonfall
Ruhig, menschlich, in kurzen Dreiklängen ("Hören. Planen. Gestalten."), Haltung statt Werbung. Sätze mit klarem Subjekt, wenig Adjektive, Wir-Form, Sie-Form für Ansprache.

## Mach
- Weißer Grund mit einem anthrazitfarbenen Hero und Fußbereich
- Panel-Stapel in genau den fünf Erdtönen, jede Fläche eine Farbe
- Riesige Headline gegen winzigen Fließtext (14px) stellen
- Nur Gewicht 400, die Wirkung kommt aus Größe und Weißraum
- Haarlinien `#d6d6d6` zum Gliedern statt Kästen
- Kontrast beachten: weiße Schrift nur auf den dunklen Erdtönen

## Mach nicht
- Keine Schatten, keine Verläufe, keine Glasflächen
- Keine knalligen Akzentfarben und keine Neon-Töne
- Keine fetten Gewichte, keine Versalien-Labels
- Keine großen Radien an Karten (maximal 13px an Bildern)
- Keine Stock-Fotos mit Menschen in Anzügen, keine Icon-Sammlungen

## Typische KI-Fehler in diesem Stil
- Panels bekommen Verläufe oder Schatten, obwohl der Stil flach ist
- Fließtext wird auf 16px oder größer gesetzt, wodurch das Größengefälle verschwindet
- Fette Headlines (600 oder 700) statt Gewicht 400
- Erdtöne werden durch Pastell- oder Primärfarben ersetzt, oder alle Panels bekommen dieselbe Farbe
- Weiße Schrift auf Dunstblau oder Sand (zu wenig Kontrast)
- Hero wird linksbündig mit Knopf-Paar gebaut statt als Wortpaar-Bühne mit Bild
- Karten mit großen Radien und Rändern statt Haarlinien
