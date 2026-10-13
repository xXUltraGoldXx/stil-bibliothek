# Stil: Ultragold (Inferno)

## Kurzbeschreibung und Stimmung
Dunkel, warm, hochwertig-technisch. Tiefes Schwarz mit Violett-Stich, Gold und Glutorange als Licht, Glas-Karten, die schweben. Gefühl: Schmiede trifft Raumschiff-Cockpit (Design "Inferno"). Dieser Stil ist das eigene Markendesign des Autors und als Stilvorlage frei nutzbar. Name und Logo der Marke Ultragold werden nicht übernommen; eigene Projekte setzen ihren eigenen Namen und ihr eigenes Logo ein.

## Farbpalette
- Hintergrund: `#07050a` (Canvas), Abstufungen `#0d0810`, `#160e1b`; Seitengrund als Radial-Verlauf von oben `#160e1b` nach `#07050a`
- Text: Creme `#f5ede6`, gedämpft `#b8a9a6`, schwach `#7d6e6c`
- Akzent Gold `#f2b544` (hell `#ffd98a`), Glut/Ember `#ff5a36` (hell `#ff8a5b`)
- Inferno-Verlauf: 135 Grad von Ember nach Gold, nur für Knöpfe, Linien, Hervorhebungen
- Sparsam: Arc-Violett `#8c6bff` als dritte Farbe für Tech-Details
- Glasflächen: `rgba(255,255,255,.045)` mit 1px-Rand `rgba(255,255,255,.09)`

## Typografie
- Headlines und Zahlen: Space Grotesk, Gewicht 600, enge Laufweite (-0.02em), Zeilenhöhe 1.1
- Fließtext: Inter 1rem, Zeilenhöhe 1.6, Farbe gedämpft
- Labels, Kennzahlen, Tags: JetBrains Mono, 0.75rem, Versalien, Laufweite .12em, Gold
- Größen: Display `clamp(2.75rem,6vw,5.5rem)`, H1 bis 3.5rem, H2 bis 2.5rem, H3 bis 1.5rem, Lead bis 1.25rem
- Nur Gewichte 400, 500, 600. Hervorhebung im Wort durch Inferno-Verlauf auf Text (genau ein Wort pro Headline)

## Abstände und Raster
- 4er-Abstandsleiter in rem: 0.25, 0.5, 0.75, 1, 1.5, 2, 3, 4, 6, 8
- Sektionen 4.5 bis 8rem vertikal, Inhalt max. 1160px
- Karten im Raster 3 oder 2 Spalten, Lücke 1.5rem; Hero linksbündig oder zentriert, nicht beides mischen

## Layout-Muster
- Hero: Mono-Label (Eyebrow), große Headline mit einem Verlaufswort, Lead, Knopf-Paar, dahinter Glut-Schein (Radial-Gradient in Ember/Gold, niedrige Deckkraft) oder Video/Bild
- Sektionen: Mono-Nummer ("01"), H2, Lead, Glas-Karten
- Karten: Glas, Radius 28px, 1px-Rand, bei Hover folgt ein Lichtschein der Maus oder der Rand wird goldener
- CTA: breite Glaskarte mit Glut-Hintergrund und Inferno-Knopf

## Komponenten
- Primärknopf: Pille, Inferno-Verlauf, dunkle Schrift `#1c0a05`, Gewicht 600; Hover: leichter Lift (-2px) und Glow
- Sekundärknopf: Pille, Glasfläche, heller 1px-Rand, Creme-Text
- Formulare: dunkle Felder (`#0d0810`), 1px-Rand, Radius 18px, Fokus: Gold-Rand plus Glow
- Schatten: `0 24px 70px -24px rgba(0,0,0,.7)`; Glow in Gold/Ember nur an Interaktion
- Tags: Pillen mit Mono-Text

## Bildsprache
Dunkle, filmische Motive, Funken, Glut, Metall, Drachen/Feuer-Anmutung, Produkt-Screens in Glasrahmen. Immer dunkel gegradet, Goldlicht. Keine hellen Stock-Fotos. Im Beispiel: CSS-Glut und Glasflächen als Platzhalter.

## Animation
Langsam und filmisch: Einblenden mit 0.7s Ease-out, Glut pulsiert sehr leicht, Hover 280ms. Kein Hüpfen, kein Wackeln. `prefers-reduced-motion` respektieren.

## Tonfall
Selbstbewusst, direkt, technisch-kompetent, Sie-Form oder neutral. Kurze starke Aussagen, konkrete Leistung statt Floskeln.

## Mach
- Dunkler Grund, Gold/Ember als Lichtquelle, Rest zurückhaltend
- Genau ein Verlaufswort pro Headline
- Glas-Karten mit 1px-Rand und großem Radius
- Mono-Labels für Struktur (Nummern, Tags, Kennzahlen)
- Kontrast: Text mindestens 4.5:1, Gold nie auf Gold

## Mach nicht
- Kein lila-blauer Standardverlauf, Violett nur als kleiner Akzent
- Kein reines Schwarz `#000` und kein reines Weiß, immer warme Töne
- Keine hellen Flächen im Standardmodus
- Keine bunten Mehrfarb-Paletten, keine Emoji
- Keine harten Schatten, keine eckigen Karten

## Typische KI-Fehler in diesem Stil
- Zu viel Gold: alles gold statt gezielter Lichtpunkte
- Verlauf auf Fließtext oder auf jeder Headline
- Blau-Violett statt Ember-Gold (Rückfall in den Standard-KI-Look)
- Gold-Schrift auf Gold-Fläche oder zu dunkles Grau auf Schwarz, zu geringer Kontrast
- Glas ohne Rand, daher flau
