# Stil: Pixel Kontrast

## Kurzbeschreibung und Stimmung
Ein selbstbewusster, offener Auftritt auf klaren Flächen: abwechselnd Tiefschwarz (`#161616`) und Weiß, dazu ein einziges Signalgrün (`#00d230`) und eine zarte rosa Fläche (`#fff1f8`) als Ruhepunkt. Die Schlagzeilen sind sehr groß, eng gesetzt und kräftig. Das prägende Motiv ist die Pixeltreppe: Abschnittsübergänge laufen nicht gerade, sondern in rechteckigen Stufen, ähnlich einem Bitmap-Rand. Alles ist flach, ohne Schatten, ohne Radien über 4px. Gefühl: Haltung, Technik mit Gewissen, freundlich und direkt.

## Farbpalette
- Tiefschwarz `#161616` für Hero, Feature-Bänder und Footer (größte Fläche der Seite)
- Reines Schwarz `#000000` für Text auf Weiß, Knöpfe und Rahmen
- Weiß `#ffffff` Grundfläche und Text auf Schwarz
- Zartrosa `#fff1f8` als eine helle Akzentfläche pro Seite, Rosa `#ff97e2` nur als Detail
- Signalgrün `#00d230` ausschließlich für das Pixelmotiv, kleine Marker und Fokus
- Grau: `#414141` Sekundärtext, `#6d6d6d` Hinweise, `#b3b3b3` Linien auf Schwarz, `#e8e8e8` Linien auf Weiß
- Links im Fließtext `#0060df` (auf Schwarz `#80ebff`), Hover `#0250bb`
- Keine Verläufe, keine Schatten

## Typografie
- Schlagzeilen: markante Grotesk mit leicht eigenwilligem Charakter, Gewicht 600, Familjen Grotesk (Google Fonts)
- Fließtext und Knöpfe: Instrument Sans (Google Fonts), Gewicht 400, Knöpfe 700
- Hero-H1 5rem (Mobil 3rem), Zeilenhöhe 1, Laufweite -0.01em
- H2 2rem bis 3rem, Zeilenhöhe 1.125; H3 1.5rem, Zeilenhöhe 1.17
- Lead-Text 1.5rem, Zeilenhöhe 1.25 bis 1.4; Text 1rem bis 1.125rem, Zeilenhöhe 1.5; Klein 0.875rem; Label 0.75rem
- Keine Ligaturen, keine Versalien, keine Kursive als Stilmittel
- Textbreite maximal etwa 60 Zeichen

## Abstände und Raster
- Basis 8px: Abstandsskala 4, 8, 16, 24, 32, 48, 64, 80px
- Seitenrand 16px mobil, 24px bis 48px Desktop; Spaltenlücke 8px bis 24px
- Maximalbreite 1440px, Text im Hero auf ca. 714px begrenzt
- Abschnittsabstand 48px mobil, 80px bis 96px Desktop
- Innenabstand Knopf 6px 24px
- Pixeltreppen-Übergänge: 90px hoch Desktop, 40px mobil

## Layout-Muster
- Navigation: weiße schmale Leiste (57px), Wortmarke links, wenige Links mittig in Gewicht 600
- Hero: Tiefschwarz, linksbündige Schlagzeile, Lead darunter, Text-Link mit Unterstrich, rechts ein großes grünes Pixelzeichen als reine Fläche
- Hero-Unterkante als Pixeltreppe in Stufen (Schwarz zu Weiß)
- Danach wechseln weiße Abschnitte mit großer, linksbündiger Aussage-Schlagzeile und kurzem Lead-Text, Tiefschwarz-Bänder für Produktkarten, eine rosa Fläche für einen Zitat- oder Haltungsblock
- Footer: tiefschwarz, mehrspaltige Linklisten
- Wechsel der Flächen statt Trennlinien

## Komponenten
- Primärknopf: Schwarz gefüllt, weißer Text 700, 2px Rahmen schwarz, Radius 4px, Innenabstand 6px 24px; auf Schwarz invertiert (weiß gefüllt)
- Sekundärknopf: transparent, 2px Rahmen, gleiche Maße
- Text-Link: Gewicht 600, 2px Unterstrich, Hover Farbwechsel
- Karten: eckig (Radius 0) auf Tiefschwarz mit `#414141`-Rahmen 1px, Bildfläche oben, Titel in Weiß, Kurztext in `#e0e0e6`
- Pause-Schalter für Animation: kleiner Kasten 1px Rahmen, 0.75rem Text
- Fokus: 2px Rahmen in Grün
- Schatten: keine

## Bildsprache
Grafische Flächen statt Fotos im Hero: ein großes Pixelzeichen in Grün auf Schwarz. Produktbilder als ruhige, farbige Kacheln. Illustrationen blockig und flach, aus Rechtecken gebaut. Im Beispiel: CSS-Flächen und Inline-SVG aus Quadraten als Platzhalter.

## Animation
Zurückhaltend. Pixelmotiv darf sich schrittweise (steps) aufbauen, höchstens 0.4s. Immer ein sichtbarer Schalter zum Anhalten. Hover: Farbwechsel 0.15s. Bei prefers-reduced-motion keine Bewegung.

## Tonfall
Direkt, persönlich, in der Du-Form. Kurze Sätze, positive Aussagen mit klarer Haltung zu Privatsphäre und Kontrolle. Schlagzeilen als Einladung oder Versprechen. Keine Fachbegriffe ohne Erklärung.

## Mach
- Extrem große, enge Schlagzeilen gegen viel Weißraum
- Flächen abwechseln: Schwarz, Weiß, ein Mal Rosa
- Pixeltreppe an mindestens einem Übergang
- Grün sehr sparsam, nur als Motiv und Fokus
- Knöpfe mit 2px Rahmen und 4px Radius
- Immer Kontrast von mindestens 7:1

## Mach nicht
- Keine Schatten, keine Verläufe, keine Glasflächen
- Keine runden Karten, keine Pillen-Knöpfe
- Kein Grün als Flächenfarbe für ganze Abschnitte
- Keine Serifen, keine Versal-Schlagzeilen
- Keine Emoji, keine Icon-Kreise

## Typische KI-Fehler in diesem Stil
- Grün und Rosa gleichberechtigt einsetzen, dadurch Bonbonoptik statt Schwarzweiß
- Karten mit Radius 16px und weichen Schatten
- Hero-Schlagzeile zu klein und zu locker gesetzt (Zeilenhöhe 1.4 statt 1.0)
- Abschnittsübergänge als gerade Linie statt Pixeltreppe
- Zentrierte Layouts statt linksbündiger Aussagen
- Mehrere Primärknöpfe nebeneinander
