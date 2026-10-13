# Stil: Katalog kompakt

## Kurzbeschreibung und Stimmung
Ein Online-Kaufhaus, das vor allem Auswahl zeigt. Die Oberfläche ist streng neutral: Schwarz, Weiß und zwei helle Grautöne. Die Farbe kommt allein aus den Produkt- und Kampagnenbildern. Die Typografie ist klein und sachlich, Beschriftungen stehen oft in Versalien. Die Seite ist dicht gepackt, mit Utility-Leiste, Hauptnavigation, Kategorie-Leiste, Vorteilsleiste und Kachelreihen. Gefühl: großer Katalog, schnell zu überblicken, ohne Dekoration. Die Hauptfläche ist Schwarz (Hero, Vorteilsleiste, Footer-Akzente) und Weiß (Raster), dazwischen liegt Hellgrau `#f4f4f5` für Flächen und Eingabefelder.

## Farbpalette
- Schwarz `#000000` für Text, Leisten, primäre Knöpfe und dunkle Bühnen
- Weiß `#ffffff` für Seitenfläche und Kartenhintergrund
- Hellgrau `#f4f4f5` und `#f5f5f5` für Suchfeld, Kategorie-Flächen, Bildhintergründe der Kacheln
- Textgrau `#434343` für Beschreibungen, Preise alt, Meta
- Linie `#d9d9d9`, 1px
- Signalrot `#d9232a` nur für Sale-Marken, Preisnachlass und kleine Zähler-Punkte
- Neongelb `#f9ff00` nur als winziger Akzent (Icon-Fläche), nie als Flächenfarbe
- Halbtransparentes Weiß `rgba(255,255,255,.7)` für schwebende Pfeil- und Leistenflächen auf Bildern
- Verlauf nur als Bildabdunklung: von transparent nach `rgba(0,0,0,.4)` unten, damit weiße Schrift auf Fotos lesbar bleibt

## Typografie
- Schrift: Inter (Google Fonts), Fallback system-ui
- Gewichte: 400 für Fließtext und Navigation, 500 für Überschriften, Knöpfe und Labels, 700 sparsam für Hervorhebungen
- Größen: H2 1.75rem (28px) Gewicht 500, Zeilenhöhe 1.15; H3 1.5rem (24px); Text und Navigation 1rem; Knöpfe 0.875rem; Standardgröße für Karten, Preise und Meta 0.75rem (12px), Zeilenhöhe 1.5
- Mikro-Labels 0.625rem bis 0.5625rem (10px und 9px), Versalien, Laufweite 0.04em, Gewicht 500, zum Beispiel für Marken in Kacheln oder Vorteilsleiste
- Große Bühnenzeile in Versalien, Gewicht 500 bis 700, etwa 2rem
- Keine Serifen, kein Kursiv, keine Zierschrift

## Abstände und Raster
- Basiseinheit 4px, Stufen 4, 8, 16, 24, 32
- Innenabstand Knöpfe und Leistenzellen 8px, Karteninhalt 8px bis 16px
- Lücken zwischen Kacheln 4px bis 8px (sehr eng), zwischen Elementen in einer Zeile 4px
- Containerbreite `calc(100% - 42px)`, maximal etwa 1280px; Seitenrand mobil 16px
- Produktraster: 6 Spalten ab 1100px, 4 ab 800px, 2 mobil
- Linien 1px `#d9d9d9` trennen Leisten; Sektionen sind durch Hellgrau-Flächen statt Leerraum getrennt

## Layout-Muster
- Oben von außen nach innen: Utility-Leiste in Hellgrau mit kleinen Text-Links (12px) und Sprachwahl, Hauptzeile mit Zielgruppen-Tabs links (aktiver Tab mit schwarzem Unterstrich 2px), Wortmarke mittig, Icons rechts, darunter Kategorie-Leiste mit Suchfeld rechts, danach schwarze Vorteilsleiste mit drei Versal-Hinweisen
- Hero: zweigeteilte dunkle Bühne, links Text-Block mit Pille-Label, Versal-Titel, Fortschrittspunkte und Mini-Kacheln, rechts großes Kampagnenbild mit Weiß-Pfeilen
- Danach Reihen mit Überschrift links und Mini-Link rechts, darunter horizontale oder gerasterte Kacheln
- Footer: viele Link-Spalten, dicht, mobil einspaltig

## Komponenten
- Primärknopf: Schwarz gefüllt, weiße Schrift 14px Gewicht 500, Radius 4px, Höhe 48px, volle Breite in Bannern
- Sekundärknopf: transparent, 1px Innenrahmen `#000`, Radius 4px
- Textknopf: nur Schrift 14px/500, Padding 0 8px
- Pille: Weiß, Radius 999px, 10px Versalien, Padding 4px 12px, liegt auf Bildern
- Suchfeld: Fläche `#f5f5f5`, Radius 8px, kein Rand, Lupen-Icon links, 12.8px Text
- Produktkachel: Bild `#f4f4f5` im Format 3:4, Radius 4px; darunter Marke 12px/500, Titel 12px/400 `#434343`, Preis 12px/500, Herz-Icon oben rechts in weißem Kreis
- Rabatt-Marke: Rot `#d9232a`, weiße Schrift 10px, Radius 2px
- Schatten sparsam: Navigation `0 2px 5px rgba(0,0,0,.1)`, schwebende Pfeile `0 0 8px rgba(0,0,0,.24)`, Karten-Popups `0 2px 10px rgba(0,0,0,.08)`
- Radien: 2px, 4px, 8px, 16px für große Bildhälften, 999px für Pillen und Kreise

## Bildsprache
Menschen- und Produktfotos mit viel Bildfläche, Models im Vollbild oder Freisteller auf Hellgrau. Kampagnenbilder sind farbig und kontrastreich, die Oberfläche bleibt dagegen neutral. Auf dunklen Bühnen liegen Fotos mit leichter Abdunklung (`rgba(0,0,0,.16)` oben). Im Beispiel: Flächen aus CSS-Verläufen in Grau, Sand und gedeckten Tönen als Platzhalter.

## Animation
Funktional und knapp. Karussell mit horizontalem Gleiten (0.3s ease), Punkte-Anzeige als wandernde Weißpille, Hover bei Kacheln: zweites Bild oder leichter Wechsel der Herz-Fläche. Knopf-Hover: Hintergrund `#434343`, 0.15s. Kein Parallax, keine Einblend-Orgien.

## Tonfall
Direkt, praktisch, zugewandt. Kurze Imperative und Nutzenhinweise wie Versand, Rückgabe und Zahlungsart in Versalien. Aktionen sind benannt, nicht umschrieben. Keine Pathos-Sprache, Zahlen und Fristen konkret nennen.

## Mach
- Kleine Schrift (12px) für fast alles in Kacheln, Größensprung nur bei Rubrik-Überschriften
- Schwarz, Weiß, Hellgrau konsequent, Farbe nur aus Bildern
- Eng gepackte Kachelraster mit 4px bis 8px Lücke
- Mehrstufige Kopfzone mit Utility-Leiste, Tabs, Kategorien und schwarzer Vorteilsleiste
- Versal-Mikro-Labels für Hinweise und Marken
- Radius 4px als Standard, Pillen für Filter und Labels
- Rot nur für Sale und Rabatt

## Mach nicht
- Keine Farbverläufe oder bunten Flächen in der Oberfläche
- Keine großen Radien (über 8px) an Knöpfen oder Karten
- Keine Serifen, keine Zierschrift
- Keine großzügigen Leerräume zwischen Kacheln
- Keine Schatten auf allen Karten
- Keine Gelb- oder Rot-Flächen als Hintergrund für Sektionen

## Typische KI-Fehler in diesem Stil
- Zu große Typografie und zu viel Weißraum, so dass der Katalog-Eindruck verloren geht
- Karten mit großen Radien und weichen Schatten statt flacher Kacheln mit 4px
- Akzentfarbe (Blau oder Violett) hinzugefügt, obwohl die Oberfläche nur Schwarz, Weiß und Grau nutzt
- Kopfzone auf eine einzige Zeile reduziert, ohne Utility-Leiste, Kategorie-Leiste und Vorteilsleiste
- Produkttexte in 16px statt 12px, Preise ohne klare Gewichtsabstufung
- Zentrierte Marketing-Hero mit großem Slogan statt zweigeteilter Bühne mit Kampagnenbild
