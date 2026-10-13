# Stil: Sportlich plakativ

## Kurzbeschreibung und Stimmung
Ein Sportartikel-Schaufenster im Browser. Die Oberfläche ist fast farblos: weißer Grund, Schwarz `#111111`, vier Graustufen. Alle Wucht kommt aus vollflächigen Bildbühnen und einer riesigen, extrem engen Versalien-Schlagzeile (Zeilenhöhe 1.0), die auf dem Bild sitzt. Kleine, runde Pillen-Knöpfe sind die einzigen Bedienelemente im Vordergrund. Gefühl: Motivationsplakat trifft aufgeräumter Katalog. Direkt, schnell, athletisch, ohne Dekor.

## Farbpalette
- Grund `#ffffff`, Fläche `#f5f5f5` (Utility-Leiste, Suchfeld, Kartenflächen), Fläche stark `#e5e5e5` (Linien, Bildplatzhalter)
- Text `#111111`, sekundärer Text `#707072` (Meta, Beschreibungen, Platzhalter)
- Auf Bildern und dunklen Flächen: Weiß `#ffffff`, Bühne dunkel `#111111`
- Genau ein Akzent `#ff5000` für Preisaktion oder ein kleines Etikett, höchstens einmal pro Bildschirm
- Fehler und Rabatt `#d30005`, nur funktional
- Keine Verläufe als Dekor, außer einem dunklen Schleier (`rgba(17,17,17,.35)`) hinter Text auf Bildern

## Typografie
- Display (Schlagzeilen auf Bühnen): Barlow Condensed (Google Fonts), Gewicht 800, Versalien, Zeilenhöhe 1.0, Laufweite normal bis -0.01em. Größen: Mobil 2.5rem (40px), Desktop bis 4.75rem (76px), Hero bis 6rem
- Titel (Karten, Abschnitte ohne Bühne): Inter, Gewicht 500, 1.5rem bis 2.5rem, Zeilenhöhe 1.2, Groß-/Kleinschreibung normal
- Text und UI: Inter 400 und 500, 1rem, Zeilenhöhe 1.5; kleiner Text 0.875rem und 0.75rem (Zeilenhöhe 1.5)
- Navigation: Inter 500, 1rem
- Mittleres Gewicht (500) trägt fast alles, es gibt nur 400 und 500, kein Fett im Fließtext
- Display: eine Futura-nahe, kondensierte Google-Schrift; Text: Inter

## Abstände und Raster
- Basis 4px, gängige Werte: 6, 12, 16, 24, 36, 48px
- Seitenrand 48px Desktop, 24px Mobil, volle Breite für Bühnen, Inhalte bis max. 1824px
- Raster: Karten in 2 oder 3 Spalten mit 12px Lücke (eng, fast Kachelwand), Bühnen volle Breite
- Utility-Leiste 36px hoch, Hauptnavigation 60px hoch
- Abschnitte trennen sich durch 48px Abstand, nicht durch Linien
- Footer: Innenabstand 48px (Mobil 48px 24px)

## Layout-Muster
- Kopf: schmale graue Leiste mit Hilfe-Links rechts, darunter weiße Navigationszeile: Logo links, Hauptlinks mittig, Suchpille und Icons rechts. Mobil: Logo links, Icons und Menü rechts
- Hero: Vollbild-Bühne, mindestens 70vh, Schlagzeile und Kurztext unten auf dem Bild (Mobil zentriert, Desktop linksbündig), darunter zwei Pillen nebeneinander
- Danach eine Folge weiterer Bühnen im Wechsel mit einer Kachelwand (3 Spalten Desktop, 1 bis 2 Mobil), jede Kachel Bild mit Titel darunter
- Produktzeilen: Bild auf `#f5f5f5`, darunter Name (500), Kategorie in Grau, Preis (500)
- Abschluss: Mitgliedsbereich auf Grau, dann Footer

## Komponenten
- Primärknopf: Pille, Radius 30px, Fläche `#111111`, Text weiß, Padding 6px 24px bis 12px 24px, Inter 500, 1rem
- Knopf auf Bildern: weiße Pille, Text `#111111`, gleiche Maße; zweiter Knopf gleich, optional mit kleinem Pfeil-Icon
- Sekundärknopf: Pille mit 1px Rand `#e5e5e5`, Text `#111111`
- Suchfeld: Pille Radius 24px, Fläche `#f5f5f5`, kein Rand, Lupen-Icon links
- Karten: Radius 8px nur bei Bildflächen, kein Rahmen; ein weicher Schatten `0 4px 8px rgba(17,17,17,.06), 0 0 24px 4px rgba(17,17,17,.03)` nur für schwebende Elemente wie Menüs
- Links: Text 500, ohne Unterstreichung, Hover mit 1px Unterstreichung
- Icons: dünne Linienicons, 24px, Strichstärke 1.5px, Farbe `#111111`

## Bildsprache
Großformatige, kontrastreiche Aktionsbilder, bildfüllend und randlos, oft dunkel oder entsättigt, mit Körper und Bewegung im Anschnitt. Produktbilder freigestellt auf `#f5f5f5`. Text sitzt direkt auf dem Bild. Im Beispiel: CSS-Flächen in Schwarz und Grau mit feinem Linienraster als Platzhalter.

## Animation
Zurückhaltend und schnell: Hover auf Pillen kippt die Fläche von `#111111` zu `#707072` in 0.15s, auf Weiß zu `#e5e5e5`. Karten-Bilder dürfen 0.3s lang um 3% zoomen. Keine Parallax-Effekte, kein Scroll-Zaubern.

## Tonfall
Kurz, im Imperativ, motivierend. Schlagzeilen aus zwei bis vier Wörtern, oft mit Punkt nach jedem Wort. Unterzeile ein bis zwei Sätze mit konkretem Nutzen. Knopfbeschriftungen ein Wort: Shoppen, Ansehen, Entdecken. Direkte Ansprache ohne Floskeln.

## Mach
- Schlagzeile in Versalien, Zeilenhöhe 1.0, auf vollflächigem Bild
- Weißer Grund, Schwarz für Text, Grau `#707072` für Nebensächliches
- Pillen mit Radius 30px als einzige Knopfform
- Enge Kachelwand mit 12px Lücke
- Gewicht 500 als Standard für UI-Text
- Dunklen Schleier hinter Text auf hellen Bildern setzen

## Mach nicht
- Keine bunten Farbflächen, kein zweiter Akzent
- Keine eckigen Knöpfe, keine Knöpfe mit Schatten
- Keine fetten Fließtexte, kein Gewicht 700 in Inter
- Keine Serifen, keine Schreibschrift
- Keine Rahmen um Karten, keine Doppelrahmen
- Keine langen Schlagzeilen über vier Wörter

## Typische KI-Fehler in diesem Stil
- Schlagzeile in normaler Groß-/Kleinschreibung und mit Zeilenhöhe 1.4 statt Versalien bei 1.0
- Knöpfe mit Radius 4px oder 8px statt Pille mit 30px
- Zu viel Weißraum und zentrierte Dreierreihen mit Icon-Kreisen, statt Vollbild-Bühnen und enger Kachelwand
- Ein farbiger Akzent oder Verlauf in jeder Sektion, statt fast reinem Schwarz-Weiß-Grau
- Text unter dem Bild statt auf dem Bild in der Hero-Bühne
- Schwere Schatten und Rahmen auf Karten
