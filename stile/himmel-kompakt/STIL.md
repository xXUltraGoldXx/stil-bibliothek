# Stil: Himmel kompakt

## Kurzbeschreibung und Stimmung
Hell-dunkel im Wechsel: ein weiter, fotografischer Himmelsverlauf von `#5592d2` nach `#439adc` im Hero, danach tiefes Schwarz `#000000` und Anthrazit `#191c1f` für Produktbühnen, dazwischen weiße Flächen. Alles ist flach (keine Schatten), rund (Pillen und große Radien) und selbstbewusst. Eine sehr große, eng gesetzte Grotesk-Headline trägt jede Seite, die Oberfläche wirkt wie eine moderne Finanz-App: klar, schnell, freundlich-souverän.

## Farbpalette
- Himmel-Verlauf (Hero): `linear-gradient(#5592d2, #439adc)`, Text darauf weiß
- Banner-Streifen oben: `linear-gradient(90deg, #2a3ff5, #7aa8f5)`, Text weiß, 0.75rem, Gewicht 600
- Schwarz `#000000` und Anthrazit `#191c1f` für dunkle Abschnitte und Footer
- Weiß `#ffffff` für Seitengrund, Knöpfe auf Dunkel und Karten; Seitenhintergrund außen `#f7f7f7`
- Text auf Hell: `#1f1f1f`, gedämpft `#717173`, Linien und Hilfstext auf Dunkel `#c9c9cd`
- Glas auf Dunkel: `rgba(255,255,255,0.1)`, Rahmen auf Foto 2px `rgba(255,255,255,0.8)`
- Ein einziger Akzent im Produkt-Detail erlaubt (Indigo `#5a60e8` für Icon-Kreise), sonst keine weiteren Farben

## Typografie
- Headlines, Zahlen, Knöpfe: Hanken Grotesk (Google Fonts, ähnlich der erkannten Marketing-Grotesk, die dort nicht verfügbar ist), Gewicht 500, Zeilenhöhe 1.0
- Fließtext und Kleintext: Inter 400, 0.75 bis 1rem, Zeilenhöhe 1.5, Laufweite 0.015em
- Display: `clamp(3rem, 6.6vw, 5.3rem)` (Desktop ca. 84px, Mobil 48px), Laufweite -0.025em
- H2: `clamp(2.25rem, 4vw, 3.15rem)` (Desktop ca. 50px, Mobil 36px), Laufweite -0.012em
- Untertitel 1.125rem, Gewicht 500; Kleintext-Hervorhebung 0.75rem, Gewicht 600
- Gewichte nur 400, 500, 600; keine Versalien, keine Monospace-Schrift

## Abstände und Raster
- Basis 4px: 0.25, 0.5, 0.75, 1, 1.5, 2.5, 3.5, 4.5, 6rem
- Innenabstand Knopf 0.5rem 1.25rem (Hero-Knopf 0.65rem 1.5rem), Karten 1.5rem
- Inhaltsbreite 1000px, links und rechts bündig auf einer Kante (Desktop-Seitenrand ca. 140px)
- Lücken 0.5, 1, 1.5rem; Sektionen 4.5 bis 7rem vertikal
- Textblöcke maximal 720px breit; Karten in 3 oder 2 Spalten, mobil eine Spalte

## Layout-Muster
- Banner-Streifen, darunter Navigation auf dem Hero-Bild: Logo links, Links nach links gruppiert, Login und weißer Pillen-Knopf rechts
- Hero linksbündig: Display-Headline, kurzer Lead, dunkle Pille; rechts oder darunter ein Telefon-Rahmen (2px weiße Kontur, Radius 22.5px) mit großer Zahl in der Mitte
- Dunkle Produktbühne: große H2 weiß, Karten in `#191c1f` mit Radius 20px
- Heller Abschnitt mit Kennzahlen: große Zahlen in Grotesk 500, kleine graue Erklärung
- Abschluss: Anthrazit-Footer mit vier Linkspalten in 0.75rem

## Komponenten
- Primärknopf dunkel: Pille (`9999px`), Fläche `#1f1f1f`, Text weiß, Grotesk 500, 1rem
- Primärknopf hell (auf Foto/Dunkel): Pille, Fläche `#ffffff`, Text `#000000`
- Sekundär: Pille ohne Fläche, nur Text weiß oder 2px weißer Rand
- Karten: Radius 20px, flach, ohne Schatten und ohne Rand auf Dunkel; auf Hell Fläche `#f7f7f7`
- Navigation: halbtransparentes Schwarz `rgba(0,0,0,0.5)` nur als Mobil-Menü
- Icon-Kreise: 3rem, Radius 9999px, Indigo oder `rgba(255,255,255,0.1)`
- Statt Schatten trennt Flächenfarbe; Tiefe entsteht nur durch Bild und Überlagerung

## Bildsprache
Großformatige, helle Porträt- und Lifestyle-Fotos vor offenem Himmel, Menschen blicken direkt, Produkt-UI (Telefon-Rahmen, Kontostand, Listenzeilen) überlagert das Foto. Im Beispiel: CSS-Verläufe und Wolken aus Radial-Verläufen als Platzhalter, Telefon-Rahmen als Kontur.

## Animation
Kurz und weich: 200 bis 300ms mit `cubic-bezier(0.15, 0.5, 0.5, 1)`, 450ms für größere Einblendungen. Hover: Knopf hellt oder dunkelt minimal, keine Hüpfer. Skeleton 1.5s. `prefers-reduced-motion` respektieren.

## Tonfall
Direkt, freundlich, im Du. Kurze Aussagen mit Nutzenversprechen, Zahlen konkret, kaum Fachjargon. Knopftexte sind Handlungen in zwei bis vier Wörtern.

## Mach
- Genau eine riesige Headline pro Hero, Laufweite deutlich negativ
- Pillen für alle Knöpfe, Radius 20px für Karten, 22.5px für Telefon-Rahmen
- Flächen wechseln zwischen Himmel, Schwarz und Weiß; je Abschnitt eine Fläche
- Weißen Text auf dem Himmel nur groß (ab 1.125rem) setzen
- Alles auf einer linken Kante ausrichten, Inhalt maximal 1000px

## Mach nicht
- Keine Schatten, keine Glüheffekte
- Keine kleinen Radien unter 12px außer bei Eingabefeldern
- Keine Verläufe auf Text, keine Mehrfarb-Paletten
- Kein Serif, keine Versalien-Labels
- Keine Rahmen auf Karten, keine dicken Linien außer dem Telefon-Rahmen

## Typische KI-Fehler in diesem Stil
- Weicher Schlagschatten unter Karten und Knöpfen eingebaut, obwohl der Stil komplett flach ist
- Headline zu klein oder mit normaler Laufweite gesetzt; die enge, große Grotesk fehlt
- Knöpfe mit 8px Radius statt Pille
- Himmel-Verlauf zu violett oder zu stark gesättigt; er bleibt im Bereich `#5592d2` bis `#439adc`
- Zu viele Farben und Akzente, statt strikt Blau, Schwarz, Weiß
- Mittig zentrierter Hero statt linksbündig mit Telefon-Überlagerung
