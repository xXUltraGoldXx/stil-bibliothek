# Stil: Katalog kantig

## Kurzbeschreibung und Stimmung
Heller, sportlicher Shop-Auftritt. Weißer Grund, fast schwarze Schrift, kühle Grautöne und rechteckige Bildkacheln ohne Rundung. Die Fotografie ist der Hauptdarsteller, die Oberfläche tritt zurück. Dazu kommen kompakte kondensierte Versalien-Überschriften, die Tempo und Energie liefern. Gefühl: Trainingsraum trifft Katalog, sachlich, schnell, ohne Dekor.

## Farbpalette
- Grund: Weiß `#ffffff`; helle Fläche `#f4f5f6`; Bildkachel-Grau `#dee0e3` (größte gemessene Fläche nach Weiß)
- Text: Tinte `#0d1012`, gedämpft `#767a7f` (häufigste Textfarbe für Nebeninfos), Mittelgrau `#444444`, schwach `#9fa3a8`
- Dunkelflächen: `#0d1012` für Hero-Banner, Pop-ups, Footer-Bänder; Verlauf von transparent nach `#0d1012` unten über Fotos, damit Text lesbar bleibt
- Overlay über Fotos: `rgba(0,0,0,.5)`
- Linien: 1px `#dee0e3`; auf dunklem Grund 1px Weiß
- Einziger Farbakzent: Mintgrün `#42b296` nur für kleine Etiketten (zum Beispiel "Neu"), nie für Flächen oder Knöpfe
- Glas nur selten: `rgba(255,255,255,.75)` mit Weichzeichnung 10px für schwebende Leisten

## Typografie
- Display und Überschriften: Bebas Neue (Google Fonts, kondensiert, Versalien), Gewicht 400, Laufweite 0.01em, Zeilenhöhe 0.9 bis 1.0
- Fließtext, Navigation, Knöpfe: Inter, 0.875rem (14px), Zeilenhöhe 1.4, Gewicht 400; Hervorhebungen 500 oder 600
- Größen: Hero-Headline `clamp(2.4rem,6vw,3.6rem)`, Abschnittstitel 1.6 bis 2.85rem (Mobil 2rem), Kachel- und Kartentitel 1.2rem, Kleintext 0.75rem
- Nebeninfos wie Preis, Farbe, Größe: 0.75rem in `#767a7f`
- Überschriften groß und eng, Fließtext klein und ruhig: starker Größensprung, wenig Gewichtswechsel

## Abstände und Raster
- Leiter in rem: 0.2, 0.4, 0.8, 1, 1.6, 2.4, 3.2, 4, 4.8, 6.4, 8
- Seitenrand 40px Desktop, 16px Mobil; Inhalt breit, bis 1200px Inhaltsbreite plus Rand
- Produktraster: 4 Spalten Desktop, 2 Spalten Mobil, Lücke 4 bis 8px (fast bündig); Kachelseitenverhältnis 3:4
- Knöpfe innen `16px 24px`; Leisten innen `8px 16px`
- Abschnitte vertikal 4 bis 6.4rem Abstand

## Layout-Muster
- Oben schmale Hinweisleiste (Versandhinweis, zentriert, unterstrichen), darunter Navigation: Kategorien links, Wortmarke mittig, Symbole rechts
- Hero: großer dunkler Banner im Seitenrand (nicht randlos), Text unten links über Verlauf, zwei eckige Knöpfe nebeneinander
- Darunter Abschnittskopf: Versalien-Titel links, kleiner unterstrichener Textlink direkt daneben ("Alle ansehen"-Prinzip)
- Produktkacheln dicht im Raster; Herz-Symbol oben rechts in der Kachel
- Kategorie-Kacheln: Foto-Fläche mit Titel unten links auf dunklem Verlauf
- Footer: mehrspaltige Linkspalten, klein und grau

## Komponenten
- Primärknopf: rechteckig, Radius 0, Fläche Weiß `#ffffff` mit Text `#0d1012` auf Foto, oder Fläche `#0d1012` mit weißem Text auf hellem Grund; Innenabstand 16px 24px; Hover: Fläche invertiert oder `#dee0e3`
- Sekundärknopf: Radius 0, transparent, 1px Rand in Textfarbe
- Runde Elemente nur als Symbolknöpfe (Radius 50%), etwa Herz, Farbpunkte
- Karten haben keinen Rahmen und keinen Schatten; Kachel = Bild plus zwei Textzeilen
- Pop-up und Overlay: dunkel `#0d1012`, Radius 16px, Schatten `0 0 18px rgba(0,0,0,.2)`; schwebende Leisten dürfen `0 4px 15px rgba(0,0,0,.1)`
- Kleine Radien nur 2px oder 4px für Etiketten und Eingabefelder
- Links: 0.75 bis 0.875rem, unterstrichen, Farbe gedämpft

## Bildsprache
Sportliche Personenfotos und Produktfreisteller auf neutralem, hellgrauem Studiohintergrund, einheitlich geschnitten, Motive in ruhigen, gedeckten Tönen. Hero-Motive dunkel, mit Bewegtbild möglich. Im Beispiel: graue CSS-Flächen `#dee0e3` mit einfachen SVG-Silhouetten als Platzhalter, dunkle Verlaufsflächen für den Hero.

## Animation
Zurückhaltend und funktional. Hover 150 bis 200ms mit Ease-out, nur Farbumschlag oder leichter Bildzoom (scale 1.03). Hero darf Bewegtbild enthalten, mit sichtbarem Pausenknopf. Keine Sprünge, keine Einblend-Orgien. `prefers-reduced-motion` respektieren.

## Tonfall
Direkt, kurz, aktiv, Du-Ansprache oder neutral. Imperative Kurzformeln für Knöpfe ("Neu ansehen"), konkrete Nutzenangaben wie Versand und Rückgabe statt Floskeln. Überschriften als knappe Versalien-Aussagen.

## Mach
- Weißer Grund, Tinte `#0d1012`, Grau `#dee0e3` als Kachelfläche
- Rechte Winkel: Radius 0 für Knöpfe, Bilder und Karten
- Überschriften in kondensierten Versalien, Rest in schlichter Grotesk 14px
- Produktkacheln dicht, 2 Spalten Mobil, 4 Desktop
- Text auf Fotos immer mit dunklem Verlauf oder Overlay absichern
- Kontrast mindestens 4.5:1; `#767a7f` nur auf Weiß, nie auf `#dee0e3` bei Kleintext

## Mach nicht
- Keine Pillenknöpfe und keine großen Rundungen an Knöpfen oder Karten
- Keine bunten Akzentflächen, kein Verlauf als Gestaltungsmittel außer dem Foto-Abdunkeln
- Keine Schlagschatten an Kacheln, keine Rahmen um Produktkarten
- Keine Serifen, keine verspielten Schriften, keine Emoji
- Keine breiten Fließtextblöcke; Text bleibt kurz

## Typische KI-Fehler in diesem Stil
- Runde Pillenknöpfe und abgerundete Karten (der Stil ist kantig)
- Überschriften in Normalschrift mit Groß-/Kleinschreibung statt kondensierter Versalien
- Zu viel Luft zwischen den Kacheln statt dichtem Raster, oder zu viel Farbe statt Grau und Tinte
- Weißer Text direkt auf hellem Foto ohne Verlauf, mangelhafter Kontrast
- Schatten, Rahmen und Hover-Effekte an jeder Karte
- Dunkler Modus als Standard statt weißem Grund mit einzelnen dunklen Bändern
