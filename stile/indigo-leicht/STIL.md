# Stil: Indigo Leicht

## Kurzbeschreibung und Stimmung
Ein heller, technisch-präziser Auftritt für Software-Produkte. Weiße Flächen, sehr leichte Schrift (Gewicht 300) und kühle Blaugrautöne erzeugen Ruhe und Vertrauen. Ein einziges kräftiges Indigo (`#5a44f0`) markiert Handlung. Ein großer, weich verlaufender Farbakzent aus Violett, Pink, Orange und Gold im Hero bringt Wärme und Wiedererkennung. Gefühl: souverän, leise, hochwertig, ingenieurhaft sauber.

## Farbpalette
- Hintergrund Weiß `#ffffff`, Wechselfläche `#f8fafd`, Hairline-Flächen `#e5edf5`
- Überschriften Tiefblau `#061b31`, Fließtext `#50617a`, gedämpft `#64748d`, Hilfstext `#839bc8`
- Akzent Indigo `#5a44f0` für Primärknöpfe, Links, Hervorhebungen; Hover `#4a3ccb`
- Dunkle Sektion Nachtblau `#0d1738` mit weißem Text und `#a3b5d6` als Zweittext
- Verlaufsfarben nur für dekorative Flächen: Violett `#8683f2`, Pink `#ea58c6`, Orange `#f59a6c`, Gold `#f5d06a`, Lavendel `#c28cf5`
- Rahmen: 1px `#e5edf5`; aktive oder hervorgehobene Rahmen 1px `#bcbcf3`
- Etwa 80 Prozent Weiß und Hellgrau, 10 Prozent Nachtblau, unter 5 Prozent Verlauf

## Typografie
- Eine variable Grotesk für alles: Inter (Google Fonts) in Gewicht 300 für Text und Überschriften, 400 für Knöpfe und Links
- H1 2.75rem (Mobil 2.125rem), Gewicht 300, Zeilenhöhe 1.15, Laufweite -0.02em
- H2 2rem (Mobil 1.375rem), Zeilenhöhe 1.1, Laufweite -0.02em
- H3 1.625rem (Mobil 1.25rem), Zeilenhöhe 1.12
- Fließtext 1rem bis 1.125rem, Zeilenhöhe 1.4 bis 1.5, Farbe `#50617a`
- Lead-Absatz 1.375rem bis 2rem in `#64748d`, Laufweite -0.02em
- Kleinstes Meta 0.6875rem bis 0.75rem mit 0.01em Laufweite, nie Versalien
- Typisches Muster: ein Satz in Tiefblau, direkt weiterlaufend ein zweiter in Grau, in derselben Zeile und Größe

## Abstände und Raster
- Basis 4px, übliche Stufen 8, 16, 24, 32, 40, 64px
- Inhaltsbreite max. 1080px bei 1280px Fenster, seitlicher Rand 24px (Mobil 16px)
- Sektionen mit 80 bis 112px vertikalem Abstand, Mobil 56px
- Karten innen 24px, Lücken im Raster 16 bis 32px
- 12 Spalten, Textblöcke höchstens 620px breit
- Feine 1px-Linien in `#e5edf5` trennen Bereiche und Logoleisten

## Layout-Muster
- Hero: linksbündig, kleine Statuszeile, große leichte Schlagzeile, Lead, zwei Knöpfe nebeneinander; rechts ein weicher Farbverlauf, der angeschnitten in den Rand läuft
- Direkt darunter eine Leiste mit Partner-Platzhaltern zwischen zwei Hairlines
- Wechsel zwischen weißen Sektionen, einer `#f8fafd`-Sektion und einer nachtblauen Sektion
- Sektionskopf: Aussage in Tiefblau plus Fortsetzung in Grau, darunter Textlink mit Pfeil
- Feature-Raster: 2 bis 3 Spalten, Karten mit Hairline und sehr zarter Schattenstufe
- Abschluss: heller Fußbereich in `#f8fafd` mit Linkspalten

## Komponenten
- Primärknopf: Fläche `#5a44f0`, Text weiß, 400, 0.9375rem, Padding 12px 20px, Radius 4px, Pfeil "›" hinter dem Text
- Sekundärknopf: weiß, 1px Rahmen `#bcbcf3`, Text Indigo, gleicher Radius
- Textlink: Indigo, 400, Pfeil dahinter, kein Unterstrich bis Hover
- Karte: weiß, 1px `#e5edf5`, Radius 6px, Schatten `0 15px 35px rgba(50,50,93,.12)` nur für schwebende Elemente, sonst `0 3px 6px rgba(23,23,23,.06)`
- Navigation: weiß, 76px hoch, untere Hairline, Punkte 400 in `#061b31`
- Status-Pille und Tags: Radius 4px, Hintergrund `#f2f7fe`, Text Indigo, 0.75rem
- Eingabefelder: 1px `#e5edf5`, Radius 4px, Fokus Rahmen Indigo

## Bildsprache
Produktoberflächen als saubere, schwebende Ausschnitte mit zarter Schattenstufe, dazu abstrakte Farbverläufe als große Dekofläche (radiale Verläufe aus Violett, Pink, Orange, Gold, weich ausgeblendet). Logos als einfarbige Graustufen in einer Leiste. Im Beispiel: CSS-Verläufe und Inline-SVG als Platzhalter, keine Fotos.

## Animation
Zurückhaltend und flüssig. Hover auf Knöpfen: Farbwechsel in 0.15s. Pfeile rücken 3px nach rechts. Karten heben sich um 2px und der Schatten wird weicher (0.2s). Der Verlauf im Hero darf langsam driften (20s, ease-in-out) und wird bei reduzierter Bewegung abgeschaltet. Keine Sprünge, kein Parallax.

## Tonfall
Klar, selbstbewusst, sachlich. Kurze Aussagesätze mit konkretem Nutzen, Zahlen und Fachbegriffe ohne Erklärfloskeln. Der zweite Satz einer Überschrift führt den Gedanken weiter. Keine Ausrufezeichen, keine Superlative ohne Beleg.

## Mach
- Gewicht 300 für Überschriften und Fließtext, enge Laufweite bei großen Größen
- Genau ein Akzent: Indigo `#5a44f0` für Handlung
- Tiefblau `#061b31` für Überschriften statt Schwarz
- Hairlines `#e5edf5` und viel Weißraum zur Gliederung
- Radien klein halten: 4px Knöpfe, 6px Karten
- Eine nachtblaue Sektion als Kontrast einbauen
- Verlauf nur als großer, einzelner dekorativer Akzent

## Mach nicht
- Keine fetten Überschriften (700 und mehr)
- Keine großen Radien oder Pillenknöpfe
- Keine harten, dunklen Schatten
- Kein reines Schwarz für Text
- Keine Verlaufsknöpfe oder Verlaufstexte im Fließtext
- Keine Versalien-Labels
- Keine Emoji und keine bunten Icon-Kreise

## Typische KI-Fehler in diesem Stil
- Überschriften in 600 oder 700 gesetzt, wodurch die leichte Eleganz verloren geht
- Verlauf über die ganze Seite oder als Hintergrund jeder Sektion statt als ein Akzent
- Violett-Weiß-Standardlook mit Pillenknöpfen und 16px-Radien
- Zu viele Akzentfarben neben Indigo, etwa Grün und Orange für Knöpfe
- Schatten zu stark und schwarz statt blaustichig und weich
- Zeilenhöhe zu groß (1.7 und mehr) bei Überschriften, die eng bleiben müssen
- Weißraum zu knapp, Sektionen wirken gedrängt
