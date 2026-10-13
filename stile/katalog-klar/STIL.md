# Stil: Katalog klar

## Kurzbeschreibung und Stimmung
Ein heller, freundlicher Versandhaus-Katalog im Browser. Weißer Grund, große ruhige Motivflächen in Sand- und Taupetönen, darüber wenige, klare Textblöcke. Eine orangefarbene Ankündigungsleiste setzt oben einen warmen Akzent, schwarze Knöpfe führen entschlossen zum Sortiment. Gefühl: übersichtlich, zugänglich, alltagstauglich, nie laut oder luxuriös.

## Farbpalette
- Grund Weiß `#ffffff`, Fläche Grau-Lila `#dad9e0` (Kategorie- und Bildkacheln), Sand `#c1ac9d`, Creme `#f1ebe6`
- Text Schwarz `#000000`, Überschriften und Zweittext `#454545`, gedämpft `#666666`, Meta `#707275`
- Ankündigungsleiste Orange `#ffad4f`
- Signal Rot `#be181a` (Aktion, Preisaktion, Badges), Rot-Text `#d21929`, Rot-Tint `#ffe5e5`
- Linien `#dddddd`, Kontrollrahmen `#a5a5a5`
- Knöpfe: Schwarz gefüllt mit weißem Text, oder weiß mit 1px Rahmen in Schwarz
- Keine Verläufe, Schatten nur für festgeklebte Leisten

## Typografie
- Schrift Text und UI: Source Sans 3 (Google Fonts), Gewichte 400, 600, 700
- Überschriften und Navigation: eine runde, geometrische Versalien-Schrift: Jost (Google Fonts), Gewicht 400 bis 500, Versalien, Laufweite 0.03em
- Hero-Titel 2.5rem (Mobil 2rem), Zeilenhöhe 1.2, H2 1.625rem mit Zeilenhöhe 2rem, Gewicht 400, Farbe `#454545`
- Fließtext 1rem, Zeilenhöhe 1.25rem; kleine Texte 0.875rem (Zeilenhöhe 1.375rem); Meta 0.75rem
- Knopftext 0.875rem, Versalien, Laufweite 0.03em
- Gewicht 400 dominiert, Fett (700) nur für Codes, Preise und Kurzbetonung

## Abstände und Raster
- Basiseinheit 4px, gängige Stufen 4, 8, 12, 16, 32px
- Inhaltsbreite maximal 1280px, Hero und Bildbänder randlos über die volle Breite
- Produktraster: 4 Spalten ab Desktop, 2 Spalten mobil, Lücke 8px bis 16px
- Sektionsabstand 32px bis 64px, innerhalb von Karten 8px
- Kopfzeile 77px hoch, Ankündigungsleiste 64px (Mobil 80px)

## Layout-Muster
- Oben: Ankündigungsleiste in Orange mit Text und Code, darunter weiße Kopfzeile mit Wortmarke links, versaler Hauptnavigation, Suchfeld mit Unterlinie und Icon-Reihe rechts
- Mobil: Navigation als horizontal scrollbare Textleiste mit dünnen senkrechten Trennern
- Hero: vollflächiges Motivbild, Textblock klar auf einer ruhigen Bildhälfte (rechts), Titel, ein Satz, ein schwarzer Knopf
- Danach Kategorie-Kacheln, Produktraster mit Karten ohne Rahmen, Service-Streifen, Newsletter, mehrspaltiger Fußbereich
- Bilder tragen das Layout, Text ist knapp

## Komponenten
- Primärknopf: schwarz `#000`, Text weiß, Radius 4px, Höhe 36px, Innenabstand 8px 16px, mit kleinem Chevron
- Sekundärknopf: weiß, 1px Rahmen schwarz, Radius 4px
- Suchfeld: nur Unterlinie 1px schwarz, 14px Text, Innenabstand 8px 0
- Produktkarte: Bildfläche (Seitenverhältnis 3:4), darunter Name 0.875rem, Preis, bei Aktion Preis in Rot `#be181a`; Herz-Icon oben rechts im Bild
- Badge: rot, weißer Text, Radius 2px, 0.75rem
- Cookie-/Hinweisleiste unten, weiß, Schatten `0 -2px 8px rgba(0,0,0,.25)`
- Radien nur 2px und 4px, Kreis 50% für Icon-Knöpfe

## Bildsprache
Großformatige Modefotografie im Studiolicht oder Interieur, weiche Beige-, Taupe- und Grautöne, Personen im Dreiviertelbild, viel freie Fläche für Text. Im Beispiel: CSS-Flächen in `#dad9e0`, `#c1ac9d` und `#f1ebe6` mit schlichten SVG-Silhouetten als Platzhalter.

## Animation
Zurückhaltend. Hover auf Karten: Bild 1.03 skaliert in 0.3s, Knopf Hover mit Aufhellung auf `#303030`. Aufklappbare Leiste mit 0.2s. Keine Parallax-Effekte, keine Autoplay-Spielereien.

## Tonfall
Du-Ansprache, freundlich, kurz und konkret. Aufforderungen im Imperativ ("Finde dein Outfit"), Versalien nur in Knöpfen und Navigation. Keine Superlative, keine Ausrufezeichen-Kaskaden.

## Mach
- Weißen Grund und große Motivflächen kombinieren
- Genau einen Akzent oben (Orange) und Rot nur für Preis und Aktion
- Navigation in Versalien, Fließtext in 400 und 16px
- Knöpfe schwarz, Radius 4px, mit Chevron
- Produktkarten ohne Rahmen, Text knapp darunter
- Mobil: 2 Spalten und scrollbare Kategorieleiste

## Mach nicht
- Keine Verläufe, keine bunten Knopffarben
- Keine großen Radien über 8px, keine Glas- oder Neon-Effekte
- Keine dekorativen Serifen oder Handschriften
- Keine dunklen Seitenhintergründe
- Keine dichten Textblöcke über dem Bild

## Typische KI-Fehler in diesem Stil
- Rot als Flächenfarbe für Knöpfe statt Schwarz
- Zu stark abgerundete, schwebende Karten mit Schatten
- Navigation in Kleinbuchstaben und fett, wodurch der Katalogcharakter fehlt
- Hero mit zentriertem Text auf dunklem Overlay statt Text auf ruhiger Bildhälfte
- Orange Leiste vergessen oder als Seitenakzent überall verteilt
- Zu viel Weißraum zwischen Produktkarten, das Raster wirkt dann nicht wie ein Sortiment
