# Stil: Elfenbein ruhig

## Kurzbeschreibung und Stimmung
Ein warmer, papierartiger Auftritt für Organisationen, die ernsthaft und zugleich menschlich wirken wollen. Elfenbeinfarbene Flächen, fast schwarze Tinte, eine fette Grotesk für kurze Aussagen und eine elegante Serife für alles, was gelesen werden soll. Große, weich gerundete Karten liegen flach auf dem Grund, ohne Schatten. Ein einziger gedämpfter Terrakotta-Ton dient als Akzent. Gefühl: Forschungsinstitut trifft Buchverlag, ruhig, klar, nicht laut.

## Farbpalette
- Seitengrund (Hauptfläche) `#f3f0e7`, Körper-Grund und helle Karten `#faf9f5`
- Sandton für Kästen und Bildflächen `#e3dacc`, Elfenbein dunkel für Hover und Tags `#e8e6dc`
- Tinte `#141413` für Text, Knöpfe und den dunklen Fußbereich
- Gedämpfter Text auf Hell: Tinte mit 60 % Deckkraft; auf Dunkel `#b0aea5` und `#e8e6dc`
- Akzent Terrakotta `#d07e5e`, dunkler `#bb6845` für Hover oder Text; nur für einen Hauptknopf je Ansicht und Kleinigkeiten
- Linien: 1px Tinte mit 10 % Deckkraft; selten 1px volle Tinte für Umrisse
- Keine Verläufe, keine Schatten. Die dunkle Fläche (`#141413`) kommt nur einmal großflächig vor: Fußbereich oder ein Schlussband

## Typografie
- Schlagzeile H1: Schibsted Grotesk (Google Fonts), Gewicht 700, 3.6rem (Mobil 2.5rem), Zeilenhöhe 1.1, einzelne Schlüsselwörter unterstrichen
- Große Zwischenüberschrift H2: Newsreader (Google Fonts, Serife), Gewicht 400, 4.4rem (Mobil 3rem), Laufweite -0.015em, Zeilenhöhe 1.15
- H3 und Kartentitel: Grotesk, Gewicht 600, 1.5rem, Zeilenhöhe 1.3
- Fließtext und Lead: Serife, 1.25rem bis 1.5rem, Zeilenhöhe 1.4, Gewicht 400
- Navigation, Knöpfe, Meta, Tags: Grotesk, 0.75rem bis 1rem, Gewicht 400 bis 500, Laufweite -0.015em, keine Versalien
- Links im Text: Serife, Gewicht 600, Unterstreichung
- Mono nur bei Code, System-Monospace

## Abstände und Raster
- Seitenrand 4rem Desktop, 1.5rem Mobil; Inhaltsbreite maximal 1150px
- Zwei Spalten im Kopfbereich: links Schlagzeile (etwa 7/12), rechts Lead-Text (etwa 5/12), unten bündig ausgerichtet
- Abstandsskala: 0.25, 0.5, 0.75, 1, 1.5, 2, 2.5, 3, 4, 6, 7.5 rem
- Abschnitte trennt großzügiger Weißraum von 6rem bis 7.5rem, Karteninnenraum 2rem bis 4rem
- Lückenmaß in Kartenrastern 2rem, in Knopfgruppen 0.5rem
- Textspalten höchstens 56rem breit

## Layout-Muster
- Kopfzeile schlicht: Wortmarke links in Versalien aus der Grotesk, Navigation rechts, ein dunkler Knopf mit Pfeilteil ganz rechts
- Hero: ohne Bild, nur Typografie in zwei Spalten, darunter eine sehr große helle Karte (Radius 24px) mit zentrierter Illustration als Platzhalter
- Abschnitte: Überschrift in großer Serife links, kurze Erklärung rechts, darunter zwei oder drei Karten nebeneinander mit gleichen Höhen
- Listen von Beiträgen als Zeilen mit dünner Linie darüber, Titel links, Rubrik und Datum rechts
- Schluss: dunkler Fußbereich mit mehrspaltigen Linklisten in `#b0aea5`

## Komponenten
- Hauptknopf: Tinte `#141413` gefüllt, Text `#faf9f5`, Radius 8px, Innenabstand 0.75rem 1.25rem; rechts ein abgetrennter Pfeilteil mit 1px hellerer Trennlinie
- Akzentknopf: `#d07e5e` gefüllt, Text Tinte oder Elfenbein, Radius 8px
- Zweitknopf: transparent, 1px Rahmen in Tinte, Radius 8px
- Karten: Radius 16px bis 24px, Fläche `#faf9f5` auf `#f3f0e7` oder `#e3dacc`, kein Rand, kein Schatten
- Tags: Radius 8px, Fläche `#e8e6dc`, Grotesk 0.75rem
- Cookie- oder Hinweisfenster: dunkle Karte, Radius 24px, Titel in Grotesk 600
- Eingabefelder: Radius 8px, 1px Rahmen mit 10 % Tinte, Fläche `#faf9f5`
- Fokus: 2px Linie in `#bb6845` mit 2px Abstand

## Bildsprache
Handgezeichnete, leicht unperfekte Linienillustrationen und große ruhige Formen auf hellem Grund: ein gekippter Schriftzug, ein Bogen mit feiner Strichstruktur, warme Erdtöne. Keine Stockfotos mit Menschen im Büro, keine Glanzeffekte. Im Beispiel dienen CSS-Flächen in Sand, Elfenbein und Terrakotta sowie einfache SVG-Striche als Platzhalter.

## Animation
Zurückhaltend. Hover auf Knöpfen und Karten: Farbwechsel in 0.2s (Elfenbein zu Elfenbein dunkel, Terrakotta zu `#bb6845`). Einblenden von Abschnitten höchstens als 0.4s Fade mit 8px Verschiebung. Illustrationen dürfen sanft schweben (6s, 6px). Kein Parallax, keine Bewegung bei prefers-reduced-motion.

## Tonfall
Sachlich, nachdenklich, verantwortungsvoll. Aussagesätze statt Werbeversprechen, wenige Superlative, konkrete Beispiele. Die Überschrift darf eine Haltung ausdrücken. Anrede neutral und respektvoll, kurze Sätze neben einem längeren erklärenden Satz.

## Mach
- Kontrast der Familien: fette Grotesk für kurze Aussagen, Serife für Lesetext und große Zwischenüberschriften
- Flächen in drei warmen Hellstufen schichten: `#f3f0e7`, `#faf9f5`, `#e3dacc`
- Radien konsequent 8px (Knöpfe, Tags), 16px bis 24px (Karten)
- Viel Weißraum, wenige Elemente pro Bildschirm
- Terrakotta sparsam, höchstens ein Akzentknopf pro Ansicht
- Einzelne Wörter in der Schlagzeile unterstreichen statt farbig markieren

## Mach nicht
- Keine Schatten, keine Verläufe, keine Glaseffekte
- Kein reines Weiß als Seitengrund und kein reines Schwarz
- Keine Neonfarben, kein Blau als Akzent
- Keine Versalien-Meta-Zeilen mit großer Laufweite
- Keine vollrunden Pillenknöpfe, keine Emoji
- Keine dichten Kachelwände; höchstens drei Karten nebeneinander

## Typische KI-Fehler in diesem Stil
- Alles in Sans-Serif gesetzt; die Serife für Lesetext und große H2 fehlt und der Buchcharakter geht verloren
- Weißer Grund `#ffffff` statt Elfenbein, dadurch kalt und generisch
- Karten mit Schatten und Rahmen, obwohl der Stil flach ist
- Terrakotta als Fläche oder Verlauf über die ganze Seite statt als sparsamer Akzent
- H1 in dünner Serife und H2 in fetter Grotesk vertauscht
- Pillenförmige Knöpfe und Icon-Kreise im SaaS-Stil
- Zu enge Abschnitte: weniger als 4rem Abstand
