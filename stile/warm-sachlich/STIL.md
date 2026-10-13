# Stil: Warm sachlich

## Kurzbeschreibung und Stimmung
Eine aufgeräumte Produkt- und Arbeitsplattform-Seite: warmes Off-White statt kaltem Grau, dazu Graphit statt Schwarz und ein einziges kräftiges Blau für jede Handlung. Alles wirkt flach, ruhig und vertrauenswürdig. Die Seite wechselt in großen Bändern zwischen hellem Papierton (`#f7f5f2`), reinem Weiß (`#ffffff`) und einem dunklen Graphit-Band (`#1e1919`). Produktbilder zeigen eine ruhige Oberfläche in einem abgerundeten Rahmen, nichts schreit. Gefühl: organisiertes Büro, Werkbank mit Ordnung, souveräne Alltagssoftware.

## Farbpalette
- Seitengrund hell: `#f7f5f2` (warmes Off-White), Variante für Flächen und Chips `#eee9e2`, Feinton `#faf9f7`
- Weiß `#ffffff` für Wechselbänder und Karten auf Off-White
- Graphit `#1e1919` für Überschriften und dunkle Bänder, tieferes Schwarz `#000000` nur für Fußbereiche oder Verlaufsenden, Verlauf `#292c31` nach `#000000` höchstens einmal je Seite
- Fließtext sekundär: `#524a3e` mit 82 % Deckkraft; auf dunklem Grund `#f7f5f2` bei 60 % Deckkraft
- Aktion: genau ein Blau `#0061fe`, nur für Hauptknopf, Fokusrahmen und kleine Textlinks. Hover etwas dunkler `#0050d4`
- Akzent sehr sparsam: Magenta `#cd2f7b` nur für winzige Hinweise oder Marken-Icons
- Flächenanteile grob: Weiß 40 %, Off-White 25 %, Graphit 20 %, Rest Schwarz und Verlauf

## Typografie
- Schlagzeilen: Familjen Grotesk (Google Fonts) als Ersatz für eine breitere, geometrisch-charaktervolle Groteske. Gewicht 500, Zeilenhöhe 1.2, Laufweite normal
- Fließtext und Oberfläche: Hanken Grotesk (Google Fonts). Gewichte 400 und 500, 700 nur für kurze Hervorhebungen
- Hero-H1: 2.5rem (40px) auf Desktop, 2rem auf Mobil, Zeilenhöhe 1.2
- Bereichs-H2 im Band: 2rem, auf Mobil 1.5rem
- Karten-H3: 1.25rem, Gewicht 500
- Lead-Absatz: 1.25rem, Zeilenhöhe 1.5, sekundärer Ton
- Fließtext: 1rem, Zeilenhöhe 1.5; kleine Meta 0.875rem, Zeilenhöhe 1.4; Mikrotext 0.75rem
- Keine Versalien, keine Sperrung, keine Kursive. Hierarchie entsteht über Größe und Gewicht 500 gegen 400

## Abstände und Raster
- Basiseinheit 8px (0.5rem). Skala: 4, 8, 12, 16, 24, 32, 48, 72, 96, 120px
- Inhaltsbreite maximal 1440px, Seitenrand 24px (Mobil 24px)
- Navigation 72px hoch, innen 16px 24px
- Bänder: oben und unten 72px bis 120px, auf Mobil 48px bis 72px
- Karten innen 24px, Lücken zwischen Karten 32px, Lücken in Textgruppen 16px und 12px
- Spalten: Hero zweispaltig (Text etwa 5 von 12, Bild 7 von 12), Kartenraster dreispaltig, ab 800px Breite einspaltig
- Textbreite im Hero höchstens 34rem (ca. 544px)

## Layout-Muster
- Navigationsleiste oben auf Weiß: Logo links, Links in Gewicht 500, rechts ein blauer Hauptknopf, unten 1px Linie in `#eee9e2`
- Hero auf Off-White: links H1, Lead, Hauptknopf; rechts eine große Produktoberfläche als Platzhalter in abgerundetem Rahmen, ragt gern über den rechten Rand hinaus. Viel Luft darunter (ca. 96px)
- Vertrauenszeile: eine zentrierte Aussage in Gewicht 500, darunter eine Reihe von fünf Logo-Flächen in Schwarz-Weiß
- Dunkles Band: kleine Überschrift oben, zentrierte H2 in Hellton, darunter ein dreispaltiges Raster mit Icon, Titel, kurzem Text und Textlink mit Pfeil
- Weiße Bänder: abwechselnd Text links/Bild rechts und umgekehrt, je Band ein Aussagesatz, ein Absatz, ein Link
- Schluss: Off-White-Band mit Handlungsaufruf, dann Fußbereich in Graphit

## Komponenten
- Hauptknopf: Hintergrund `#0061fe`, Text weiß, Gewicht 500, 1rem, Innenabstand 16px 24px, Radius 12px, mit Pfeil rechts im Abstand 16px. Kein Schatten
- Sekundärknopf: weiß oder transparent, Rahmen 2px solid `#1e1919`, Radius 12px, gleiche Maße
- Textlink: Gewicht 500, 1px Unterstreichung mit Abstand 3px, Pfeil `→` danach; Fokus 2px solid `#0061fe`
- Chips: Hintergrund `#eee9e2`, Radius 999px, 0.75rem Text, Innenabstand 4px 12px
- Karten: auf Weiß Hintergrund `#f7f5f2`, auf Graphit transparent mit 1px Linie in Hellton bei 16 % Deckkraft; Radius 16px; keine Schatten
- Radien: 8px (kleine Elemente), 12px (Knöpfe, Eingaben), 16px (Karten, Bildrahmen), 20px (große Produktflächen)
- Schatten: keine. Tiefe nur durch Flächenwechsel und 1px Linien in `#eee9e2`

## Bildsprache
Ruhige Produktoberflächen als Hauptbild: helle UI mit Seitenleiste, Kachelraster und einem davorgesetzten Mobilgerät, alles in abgerundetem Rahmen. Ergänzend hochwertige Motivfotos mit gedeckten Farben und viel Negativraum sowie einfarbige Logo-Flächen. Im Beispiel: CSS-Flächen in Off-White, Blau-Tönen und Graphit mit einfachen Blöcken als Oberflächenplatzhalter, Icons als kleine SVG-Formen.

## Animation
Sehr zurückhaltend. Übergänge 0.125s bis 0.333s mit ease-out für Hover und Fokus (Farbwechsel des Knopfs, Pfeil rückt 4px nach rechts). Seitenwechsel oder Bänder bauen sich ohne Parallax auf; höchstens ein weiches Einblenden in 0.7s. Eine Pausetaste für laufende Logo-Reihen gehört zum Stil, wenn etwas automatisch läuft.

## Tonfall
Sachlich, freundlich, direkt. Kurze Sätze mit konkretem Nutzen, Ansprache in der Sie-Form. Überschriften als ruhige Aussage mit Gegensatz oder Versprechen, nie laut. Knopftexte nennen die Handlung: etwa „Kostenlos testen“, „Jetzt verknüpfen“, „Mehr erfahren“. Keine Ausrufezeichen, keine Superlative.

## Mach
- Warmes Off-White `#f7f5f2` als Grundton, Weiß und Graphit als Wechselbänder
- Genau ein Blau `#0061fe` für alle primären Handlungen
- Überschriften in Gewicht 500, Fließtext in 400 mit Zeilenhöhe 1.5
- Großzügige vertikale Abstände von 72px bis 120px zwischen Bändern
- Radius 12px bei Knöpfen, 16px bei Karten, durchgängig flach ohne Schatten
- Produktoberfläche als großes, abgerundetes Hauptbild im Hero
- Textlinks mit Pfeil `→` in jeder Kartenreihe

## Mach nicht
- Keine Schatten, keine Glüheffekte, keine Glasflächen
- Kein reines Schwarz als großer Seitengrund, Graphit `#1e1919` verwenden
- Kein zweites Signalblau und keine bunten Knopffarben
- Keine Versalien-Überschriften, keine fetten Gewichte über 500 in Headlines
- Keine harten Ecken (0px) und keine Vollrunde bei Knöpfen
- Keine kalten Blaugrau-Töne als Seitengrund
- Keine dichten Kachelwände ohne Luft

## Typische KI-Fehler in diesem Stil
- Kaltes Weiß oder Grau statt des warmen Off-White `#f7f5f2`, wodurch die Wärme verloren geht
- Schatten unter Karten und Knöpfen, obwohl der Stil komplett flach ist
- Zu viele Akzentfarben: Blau, Magenta und Grün gleichzeitig statt eines einzigen Blaus
- Schlagzeilen in Gewicht 700 bis 900 statt 500, dadurch wirkt es plump
- Dunkles Band in reinem Schwarz statt in Graphit `#1e1919`
- Hero zentriert mit kleinem Bild, statt Text links und großer Oberfläche rechts
- Zu enge Bänder: weniger als 72px Luft zwischen Abschnitten
