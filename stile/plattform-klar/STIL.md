# Stil: Plattform klar

## Kurzbeschreibung und Stimmung
Helle, großzügige Produktseite für eine technische Plattform mit breitem Angebot. Fast alles ist Weiß oder ein kaltes Hellgrau, die Schrift ist schwarz und fett in den Überschriften, und genau ein warmes Orange setzt die Akzente. Ein sehr dunkles Nachtblau bildet den Fuß der Seite. Gefühl: souverän, schnell, unaufgeregt, Infrastruktur, der man vertraut.

## Farbpalette
- Fläche Weiß `#ffffff` (Hauptfläche, rund 80 % der Seite)
- Fläche Kaltgrau `#f8f8fb` für abgesetzte Bänder, Info-Karten und Kacheln
- Nachtblau `#070033` nur für Fuß und gelegentliche dunkle Bänder, Text darauf `#ffffff`
- Signal-Orange `#ff6633` für Rubrik-Zeilen, Knopfrahmen, Pfeile, Hover-Linien und kleine Flächen
- Text primär `#000000`, sekundär `rgba(34, 34, 34, 0.6)` (entspricht etwa `#222222` bei 60 %)
- Hero-Hintergrund: weicher warmer Verlauf von `#ffb27a` über `#ff8a4c` nach `#ffffff` am unteren Rand, flächig und diffus, nie als Muster
- Dezenter Violett-Verlauf `#883aea` zu `#e0ccfa` nur als seltene Bildplatzhalter-Füllung
- Rahmen: 1px, entweder Orange (Knöpfe) oder `#e6e6ee` (Karten)

## Typografie
- Eine Familie: Inter (Google Fonts), Gewichte 400, 500, 600, 700
- H1 3.75rem (60px), Gewicht 600, Zeilenhöhe 1, mobil 2.25rem
- H2 3rem (48px), Gewicht 600, Zeilenhöhe 1, mobil 2.25rem
- H3 2.25rem (36px), Gewicht 600, Zeilenhöhe 1.1, mobil 1.875rem
- Lead und Fließtext 1rem bis 1.125rem, Gewicht 400, Zeilenhöhe 1.5
- Kleintext 0.875rem (Zeilenhöhe 1.25) und Meta 0.75rem (Zeilenhöhe 1.33) in `rgba(34,34,34,0.6)`
- Rubrik-Zeile über Überschriften: Versalien, Orange, Laufweite 0.075em (1.2px), Gewicht 500
- Betonung in der H1: das letzte Wort in hellem Grau `#9a9aa5` statt Orange
- Keine Kursive, kein Serifen-Einsatz, kein negativer Buchstabenabstand

## Abstände und Raster
- Maximalbreite Inhalt 75rem (1200px), seitlicher Rand 5rem Desktop, 1.25rem mobil
- Abstand zwischen Sektionen 5rem bis 6rem vertikal, mobil 3.5rem
- Innenabstände in einer 4er-Skala: 0.25, 0.5, 0.75, 1, 1.5, 2, 2.5, 3rem
- Kartenlücke 1.5rem, Knopflücke 2rem, Textlücke in Spalten 2rem
- Spalten: 12er-Raster, Kacheln 3 oder 4 nebeneinander, Text und Medien 6 zu 6
- Textblöcke maximal 42rem breit

## Layout-Muster
- Kopfzeile: Weiß, schmale Utility-Zeile oben (Support, Telefon, Sprache), darunter Hauptnavigation als einfache Textlinks mit Abstand 2.5rem, rechts ein Rahmenknopf und ein gefüllter Knopf
- Hero: linksbündig, H1 über drei Zeilen, Lead, zwei Knöpfe nebeneinander, darunter ein Band mit zwei horizontalen Info-Karten (Vorschaubild links, Titel, Zweizeiler, Pfeil-Link)
- Folgesektionen: Rubrik-Zeile, H2, Lead, Link mit Pfeil; daneben oder darunter ein Bildplatzhalter. Weiß und Kaltgrau wechseln sich ab
- Kachelreihen für Produkte: 3 bis 4 Karten, linksbündig, mit Titel, Kurztext und Pfeil-Link
- Logo-Reihe: graue, ruhige Marken in einer Zeile mit viel Luft
- Abschluss: Handlungsaufruf-Band, dann Nachtblau-Fuß mit vier bis fünf Linkspalten

## Komponenten
- Primärknopf: Fläche Orange `#ff6633`, Text schwarz, Radius 0.5rem, Innenabstand 0.75rem 1rem, Gewicht 500
- Sekundärknopf: transparent, 1px Rahmen Orange, Text schwarz, gleiche Maße
- Hover: Primär dunkelt auf `#e8531f`, Sekundär füllt sich mit `#fff3ed`, Übergang 0.2s
- Karten: Weiß oder `#f8f8fb`, Radius 0.5rem, Innenabstand 1.5rem, meist ohne Schatten; hervorgehobene Karte Schatten `0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.05)`
- Pfeil-Link: Text schwarz, dahinter ein kleiner orangefarbener Pfeil "›"
- Eingabefelder: transparent, nur untere Linie 1px, 0.875rem Text
- Radien: 0.5rem für alles Interaktive und alle Karten, sonst 0

## Bildsprache
Produktbezogene Illustrationen und Oberflächen-Ausschnitte auf ruhigem Grund, Karten-Vorschaubilder mit Orange-Violett-Verlauf und 0.5rem Radius. Der Hero lebt von einem weichen warmen Farbverlauf. Im Beispiel: CSS-Flächen mit Verläufen und einfachen SVG-Formen als Platzhalter, keine Fotos von Personen.

## Animation
Zurückhaltend und funktional. Hover-Übergänge 0.2s, Karten heben sich höchstens 2px. Optional langsam driftender Hero-Verlauf (20s, kaum sichtbar). Keine Parallax-Effekte, kein Einfliegen von Text.

## Tonfall
Sachlich, direkt, nutzenorientiert. Kurze Aussagesätze mit Verben ("verbinden, schützen, entwickeln"), konkrete Begriffe statt Floskeln, keine Ausrufezeichen. Knopftexte sind Handlungen: "Kostenlos starten", "Tarife ansehen".

## Mach
- Weiß als Standard, Kaltgrau `#f8f8fb` für Rhythmus
- Überschriften groß, Gewicht 600, eng gesetzt (Zeilenhöhe 1)
- Orange sparsam: Rubrik-Zeile, Knopfrahmen, Pfeile
- Radius durchgehend 0.5rem
- Linksbündige Texte mit klarer Hierarchie
- Nachtblauer Fuß als einziger dunkler Block

## Mach nicht
- Keine zweite Akzentfarbe neben Orange
- Keine Schatten auf allem, keine starken Glows
- Keine zentrierten Hero-Texte mit Zierschrift
- Keine Pillen-Knöpfe, keine Radien über 0.5rem
- Keine großen Orange-Flächen außer dem Hero-Verlauf
- Keine dunkle Seite mit Neon

## Typische KI-Fehler in diesem Stil
- Orange als Vollfläche für ganze Sektionen statt als sparsames Signal
- Überschriften in Gewicht 800 oder 900 statt 600
- Schwerer Schatten und große Radien an Karten, wodurch es verspielt wirkt
- Hero zentriert gesetzt, obwohl er linksbündig sein soll
- Zu viele Farben in Kacheln (Blau, Grün, Lila), statt Weiß und Kaltgrau
- Rubrik-Zeile vergessen oder in Kleinbuchstaben ohne Laufweite
- Fuß in reinem Schwarz statt in tiefem Nachtblau `#070033`
