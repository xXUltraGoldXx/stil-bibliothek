# Stil: Produkt hell

## Kurzbeschreibung und Stimmung
Ruhig, selbstsicher, hochwertig. Wenig Elemente, riesige Typografie, sehr viel Weißraum. Das Produkt (oder ein Platzhalter dafür) ist der Held, alles andere tritt zurück. Es werden nur die Prinzipien übernommen, keine Marken, Logos, Produktnamen oder fremde Bilder.

## Farbpalette
- Hintergrund: `#ffffff`, Wechsel-Sektionen `#f5f5f7`, einzelne dunkle Sektion `#000000`
- Text: `#1d1d1f`, sekundär `#6e6e73`, auf Dunkel `#f5f5f7`
- Eine einzige Akzentfarbe: Blau `#0071e3` (nur für Links und Primärknöpfe)
- Linien: `#d2d2d7`, nur sparsam
- Keine Verläufe als Dekoration, keine zweite Akzentfarbe

## Typografie
- Schrift: Inter (Google Fonts) mit System-Fallback `system-ui`, `Segoe UI`
- Hero: `clamp(2.75rem, 8vw, 6rem)`, Gewicht 700, Laufweite -0.03em, Zeilenhöhe 1.05
- H2: `clamp(2rem, 5vw, 3.5rem)`, Gewicht 700; Lead-Text 1.2 bis 1.75rem, Gewicht 400, Farbe sekundär
- Fließtext 1.0625rem, Zeilenhöhe 1.5, max. 680px Breite
- Nur Gewichte 400, 600, 700. Kein Kursiv, keine Versalien außer winzigen Überzeilen (Eyebrow, 0.8125rem, 600)

## Abstände und Raster
- Sektionen: vertikal 5 bis 9rem Abstand, Inhalt zentriert, max. 1080px
- Text immer zentriert in Hero und Kernaussagen, Karten im 2er- oder 3er-Raster mit 1.5rem Lücke
- Großzügig statt dicht: im Zweifel doppelt so viel Abstand

## Layout-Muster
- Hero: Eyebrow, Riesen-Headline (max. 6 Wörter), ein Lead-Satz, zwei Aktionen (Primärknopf + Textlink mit Pfeil), darunter großes Produktbild-Platzhalter
- Sektionen: eine Aussage pro Sektion, Headline, ein Satz, optional eine Grafik. Abwechselnd weiß, hellgrau, schwarz
- Karten: abgerundet (28px), hellgrau auf Weiß, keine Rahmen, kein Schatten oder nur ein sehr weicher
- CTA: zentrierter Abschluss mit einer Headline und einem Knopf

## Komponenten
- Primärknopf: Pille (980px), Blau, weiße Schrift, 17px, Innenabstand 12x22px, Hover leicht heller
- Sekundär: Textlink in Blau mit "›" am Ende, Unterstreichung erst bei Hover
- Formularfelder: 12px Radius, 1px Linie, Fokus mit blauem 4px-Ring
- Schatten: nur `0 4px 30px rgba(0,0,0,.08)`, selten
- Navigation: schmal, 48px hoch, halbtransparent mit Weichzeichner, kleine Schrift

## Bildsprache
Produkt freigestellt auf ruhigem Grund, große Flächen, weiches Licht. Im Beispiel: CSS-Verläufe und abgerundete Formen als Produkt-Platzhalter. Keine Stock-Menschen, keine Icons-Wolken.

## Animation
Dezent: Einblenden mit leichtem Hochschieben (24px, 0.6s, Ease `cubic-bezier(.28,.11,.32,1)`), beim Scrollen. `prefers-reduced-motion` respektieren. Keine Hüpf-, Dreh- oder Glüheffekte.

## Tonfall
Kurz, ruhig, positiv, präzise. Kurze Sätze, Punkt am Ende. Keine Ausrufezeichen, keine Superlativ-Ketten. Beispiel: "Einfach da. Einfach gut."

## Mach
- Eine Aussage pro Bildschirmhöhe
- Genau eine Akzentfarbe
- Riesige Headline, kleiner Rest
- Viel Weißraum, zentrierte Ausrichtung
- Mindestkontrast 4.5:1, Touch-Ziele mindestens 44px

## Mach nicht
- Keine Verläufe auf Texten oder Flächen als Effekt
- Keine dicken Rahmen, keine harten Schatten
- Keine Emojis, keine bunten Icons
- Keine Fließtext-Blöcke über 680px Breite
- Keine dritte Schrift, keine Schriftmischung

## Typische KI-Fehler in diesem Stil
- Zu viele Informationen pro Sektion, also zu wenig Weißraum
- Mehrere Akzentfarben oder ein blau-lila Verlauf statt reinem Blau
- Karten mit Rahmen und Schatten und Verlauf zugleich
- Headlines in Mittelgröße statt wirklich groß
- Fremde Marken oder Produktnamen nachgebaut
