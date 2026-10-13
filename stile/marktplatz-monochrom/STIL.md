# Stil: Marktplatz monochrom

## Kurzbeschreibung und Stimmung
Ein großer, übersichtlicher Online-Katalog: reines Weiß als Grund, tiefes Schwarz für Text und Knöpfe, hellgraue Flächen zum Gruppieren. Farbe kommt fast nur aus den Bildern. Ein einziges Orangerot `#d2451e` dient als Ankündigungsband, ein Sale-Rot `#da0410` als Textsignal. Gefühl: klar, sachlich, freundlich, schnell zu überblicken. Der Stil ist dicht, aber nie laut.

## Farbpalette
- Grund `#ffffff` (mit Abstand größte Fläche), Fläche `#f1f1f1` für Kacheln, Chips und Bildplatzhalter
- Text und Knöpfe `#000000`, sekundärer Text `#5c6169`
- Linie `#d2d8dd` (1px), Fokus- und Outline-Ring Schwarz
- Signal Orangerot `#d2451e` nur für das schmale Ankündigungsband oben
- Sale-Rot `#da0410` nur für einzelne Wörter (zum Beispiel ein Menüpunkt, Preis)
- Invertierte Blöcke: Hintergrund `#000000`, Text `#ffffff`
- Keine Verläufe, keine farbigen Schatten

## Typografie
- Eine einzige serifenlose Familie: Inter (Google Fonts) mit Gewichten 400, 520 und 650, Fallback Helvetica, Arial
- Hero-Überschrift 2.375rem (38px), Zeilenhöhe 44px (2.75rem), Gewicht 650, Laufweite -0.2px
- H2 1.5rem (24px) / 1.875rem, Gewicht 650, Laufweite -0.08px
- H3 und Kartentitel 1rem / 1.5rem, Gewicht 650
- Fließtext und Navigation 0.875rem (14px) / 1.25rem, Gewicht 400; Menüs und Knöpfe 1rem, Gewicht 520
- Kleintext, Preise, Rechtliches 0.75rem (12px) / 1rem
- Keine Versalien, keine Sperrung, keine Serifen. Die Stufen sind eng: 12, 14, 16, 22, 24, 38

## Abstände und Raster
- Maximale Inhaltsbreite 1216px, seitlicher Rand 2rem (Mobil 1rem)
- Abstandsskala: 4, 6, 8, 12, 16, 24, 32, 36px. Typisch sind kleine Innenabstände (6 bis 12px) in Chips und Listen
- Kartenraster: 4 Spalten ab 1024px, 2 Spalten darunter, Lücke 1rem
- Abschnitte trennt Weißraum von 2.25rem (36px) bis 3rem, keine dicken Linien
- Dünne Linien `#d2d8dd` nur dort, wo Listen oder Eingaben Halt brauchen

## Layout-Muster
- Ganz oben ein schmales Ankündigungsband in Orangerot mit weißem, zentriertem 12px-Text
- Kopfzeile: Hauptbereiche links fett (1rem, 650), Wortmarke mittig, Icons rechts; darunter eine zweite Zeile mit Unterkategorien in 14px
- Hero zweispaltig: links großes Bild mit 12px Radius und runden Pfeil-Knöpfen, rechts Überschrift und darunter Einstiegs-Chips
- Danach Produktreihen als Kachelraster: Bild oben, darunter Marke, Titel, Preis
- Ein schwarzer Vollbreiten-Block mit weißer Überschrift und weißem Pillen-Knopf als Kontrast
- Fußbereich in Hellgrau, Linkspalten in 14px

## Komponenten
- Primärknopf: Pille (Radius 9999px), Hintergrund `#000`, Text `#fff`, Gewicht 520, Innenabstand 0.75rem 1.5rem
- Sekundärknopf: Pille, transparent, Ring `box-shadow: inset 0 0 0 1px #000`, Innenabstand 8px 16px
- Auf Schwarz: weiße Pille mit schwarzem Text
- Chips: Pille, Fläche `#f1f1f1`, 14px, Innenabstand 6px 12px
- Runde Icon-Knöpfe (40px) in Weiß mit Pfeil auf Bildern
- Bild- und Kartenradius 12px, kleine Tags 4px
- Eingaben: ohne Kasten, 16px, Innenabstand 10px 12px, Linie unten `#d2d8dd`; Fokus mit 2px schwarzem Ring
- Schatten gibt es nur als Innenring (1px oder 2px Schwarz), nie als weichen Fall-Schatten

## Bildsprache
Warme, redaktionelle Fotos mit Personen und Räumen, ruhiger Hintergrund, gedeckte Erdtöne. Produktbilder auf hellem Grund, einheitliches Hochformat. Alle Bilder mit 12px Radius. Im Beispiel: Flächen in `#f1f1f1` und weichen Grautönen als CSS-Platzhalter, ergänzt durch einfache SVG-Formen.

## Animation
Zurückhaltend. Hover auf Knöpfen und Karten: 0.15s Farb- oder Ringwechsel (Ring von 1px auf 2px). Karussell-Wechsel per Gleiten, 0.3s. Keine Parallax-Effekte, keine Einblend-Orgien.

## Tonfall
Direkt, per Du, kurz und hilfsbereit. Fragen als Einstieg ("Wo möchtest du beginnen?"), Aussagen in einem Satz, keine Ausrufezeichen-Ketten. Aktionen als klare Verben auf Knöpfen.

## Mach
- Weiß und Schwarz dominieren, Hellgrau gruppiert
- Pillen für alle Knöpfe und Chips, 12px für alle Bildkacheln
- Eine Schriftfamilie, Hierarchie über Gewicht 650 und Größe
- Dichte Kachelraster mit gleichmäßigen Lücken
- Einen schwarzen Kontrastblock pro Seite
- Signalfarben nur in kleinen Dosen

## Mach nicht
- Keine weichen Fall-Schatten, keine Verläufe
- Keine Serifen, keine Versalien-Überschriften
- Keine bunten Knöpfe, keine Pastellflächen
- Keine eckigen Primärknöpfe
- Kein Orangerot als große Fläche

## Typische KI-Fehler in diesem Stil
- Knöpfe mit 6 bis 8px Radius statt voller Pille
- Karten mit Schatten und Rahmen, obwohl der Stil flach ist
- Zu große, zu luftige Überschriften (4rem und mehr), statt kompakter 38px
- Akzentfarbe (Orangerot oder Sale-Rot) auf Knöpfen und Links verteilt
- Hero komplett zentriert, statt Bild links und Text rechts
- Hauptmenü in Versalien oder mit Unterstrich, statt schlichtem 650er Text
- Zu wenig Kacheln: Der Stil lebt von Dichte, nicht von drei großen Karten
