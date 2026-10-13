# Stil: Monochrom präzise

## Kurzbeschreibung und Stimmung
Hell, neutral und kompromisslos reduziert. Ein fast weißer Grund (`#fafafa`), Text in Fast-Schwarz (`#171717`), dazu ein einziger Fokus-Körper pro Bildschirm. Die Wirkung kommt aus Typografie: sehr große Headlines mit stark negativer Laufweite, darunter kleine, nüchterne 14px-Texte. Flächen werden nicht durch Schatten, sondern durch 1px-Haarlinien in `#ebebeb` getrennt. Gefühl: Entwicklerwerkzeug, Labor, Schweizer Präzision.

## Farbpalette
- Seitengrund: `#fafafa`; Karten und Knopf-Flächen: `#ffffff`
- Text primär: `#171717`; Text sekundär: `#4d4d4d` (der häufigste Textton, ca. 55 % des Textes); Text schwach: `#666666`; Text auf Dunkel: `#c9c9c9` und `#ffffff`
- Linien und Ränder: `#ebebeb`, 1px
- Dunkle Flächen: `#171717` (Primärknöpfe, einzelne Kontrastbänder, Fußbereich)
- Link-/Fokusblau: `#0070f3`, nur für Textlinks und Fokusring
- Verläufe nur als Beiwerk: weicher Radial-Schein in Weiß/Hellgrau hinter dem Hero-Körper; ein schmales Spektrum-Band (Grün, Gelb, Rot, Violett, Cyan) höchstens als 2–4px hohe Linie
- Hintergründe der Seite laufen unten und an den Rändern per Verlauf nach `#fafafa` aus

## Typografie
- Schrift: Geist (Google Fonts), Mono: Geist Mono
- Display/H1: 4rem (64px), Zeilenhöhe 1, Laufweite -0.06em, Gewicht 400
- H2: 3.5rem (56px), Zeilenhöhe 1, Laufweite -0.06em, Gewicht 450
- H3/Abschnittstitel: 1.5rem (24px), Zeilenhöhe 2rem, Laufweite -0.04em, Gewicht 450–500
- Fließtext: 0.875rem (14px), Zeilenhöhe 1.25rem, Gewicht 400, Farbe `#4d4d4d`; Lead 1rem/1.5rem
- Labels und Kennzahlen: Geist Mono 0.75rem (12px), Zeilenhöhe 1rem, keine Versalien nötig
- Mobil: H1 3rem/3.5rem (-0.06em), H2 2rem/2.5rem (-0.05em)
- Gewichte nur 400, 450, 500. Nie Fett über 500

## Abstände und Raster
- Basis 4px; häufige Werte: 0.25, 0.5, 0.75, 1, 1.5, 2.5, 3rem
- Seitenrand 1.5rem (24px), Inhalt volle Breite bis max. 1448px
- Kleine Lücken zwischen Elementen: 6px (Knopfgruppen, Listen), 12px bei Gruppen
- Sektionen vertikal 6–10rem, viel Leerraum um den Hero
- Raster: 12 Spalten gedacht; praktisch 3 Spalten (Text | Körper | Liste) im Hero, 3 oder 4 Spalten bei Karten, Lücken 0 mit Haarlinien oder 1.5rem

## Layout-Muster
- Kopfzeile: Marke links, 3–4 Textlinks in `#4d4d4d`, rechts drei Knöpfe (zwei hell, einer dunkel)
- Schmale Ankündigungszeile zentriert unter der Kopfzeile
- Hero: dreispaltig. Links riesige Headline mit Knopf-Paar, Mitte ein einzelner dunkler geometrischer Körper mit weichem Schein, rechts drei kurze Zeilen in 16px. Mobil gestapelt
- Logoband: eine Reihe gleich hoher, einfarbiger Wortmarken in Grau, gleichmäßig verteilt
- Inhaltsabschnitte: Titel links, Beschreibung daneben, darunter Rasterkarten mit Haarlinien
- Fuß: 2.5rem Innenabstand oben/unten, 14px Text, Spalten mit Linklisten

## Komponenten
- Primärknopf: Pille (Radius 999px), Fläche `#171717`, Text `#ffffff`, Innenabstand 0.5rem 1.125rem, 14–16px, Gewicht 500
- Sekundärknopf: Pille, Fläche `#ffffff`, Rand 1px `#ebebeb`, Text `#171717`
- Kleine Knöpfe in der Kopfzeile: Radius 6px statt Pille, gleiche Farben
- Karten: `#ffffff`, Radius 6px bis 8px, Rand-Schatten `0 0 0 1px #ebebeb`; Hover: Rand dunkler (`#c9c9c9`) oder weicher Schatten `0 2px 8px rgba(0,0,0,.08)`
- Textlinks: `#0070f3`, Radius 6px, bei Hover Hinterlegung `#ffffff`
- Tags/Kennzeichen: Geist Mono 12px, Rand 1px, Radius 6px oder Pille
- Eingabefelder: transparent bis weiß, Rand 1px `#ebebeb`, Radius 6px, Fokus mit blauem Ring

## Bildsprache
Ein einzelner, stark vereinfachter dunkler Körper (geometrische Grundform) auf hellem Grund, umgeben von einem weißen Lichthof und weichem Schlagschatten. Dazu graue Wortmarken-Reihen und Produkt-Oberflächen in weißen Rahmen mit Haarlinie. Keine Fotos, keine Illustrationen mit Farbe. Im Beispiel: CSS-Formen und graue Balken als Platzhalter.

## Animation
Zurückhaltend und schnell: Hover 150ms ease, sanftes Einblenden mit 8px Verschiebung über 500ms. Der Hero-Körper darf sehr langsam schweben (8s, 6px Hub). Kein Springen, keine Drehungen. `prefers-reduced-motion` respektieren.

## Tonfall
Knapp, sachlich, technisch kompetent. Kurze Hauptsätze, Aufzählungen aus drei Halbsätzen, Verben im Imperativ auf Knöpfen („Starten“, „Gespräch buchen“). Keine Ausrufezeichen, keine Superlative.

## Mach
- Seitengrund `#fafafa`, Karten `#ffffff`, Trennung durch 1px `#ebebeb`
- Headlines sehr groß mit Laufweite -0.06em und Zeilenhöhe 1
- Genau ein dunkler Primärknopf pro Sichtbereich, daneben ein heller Pillenknopf
- Viel Leerraum, ein Fokusobjekt im Hero
- Geist Mono für Kleinstinformationen (Nummern, Befehle, Tags)
- Fokusring sichtbar (2px `#0070f3`), Kontrast mindestens 4.5:1

## Mach nicht
- Keine Farbflächen, keine bunten Akzentknöpfe; Blau nur für Links
- Keine großen, dunklen Schlagschatten auf Karten, keine Glasflächen
- Kein reines Schwarz als Seitengrund im hellen Modus, kein Fettdruck über 500
- Keine Emoji, keine Verlaufstexte, keine dekorativen Icons in Farbe
- Keine Versalien-Headlines, keine zentrierten langen Fließtexte

## Typische KI-Fehler in diesem Stil
- Laufweite der Headlines vergessen: ohne -0.06em wirkt es generisch
- Zu kleine Headlines (unter 3rem am Desktop) und zu viel Fließtext darunter
- Weiße Seitenfläche `#ffffff` statt `#fafafa`, dadurch verschwinden Karten und Haarlinien
- Schatten statt Haarlinie, Karten mit Radius über 12px
- Blauen Verlaufsknopf oder Violett-Töne ergänzen (Rückfall in den KI-Standardlook)
- Mehrere gleichwertige dunkle Knöpfe nebeneinander
- Fettes Gewicht (600/700) für Headlines
