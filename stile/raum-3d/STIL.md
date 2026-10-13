# Stil: Raum-3D

## Kurzbeschreibung und Stimmung
Räumlich, klar, handwerklich. Die Seite wirkt wie ein Modell auf einem Tisch: Ebenen liegen übereinander, Karten schweben, ein Fluchtpunkt ordnet alles. Tiefe entsteht durch Perspektive, Versatz und Schatten, nicht durch Effekt-Farben. Passt zu Produkten, Architektur, Konfiguratoren, Hardware und Visualisierung.

## Farbpalette
- Grund: `#e8ecf3`, tiefer `#dbe1ec`; Ebenen von hinten nach vorn heller: `#c9d3e6`, `#f3f6fb`, `#ffffff`
- Text: `#141a2e`, sekundär `#4a5470`, schwach `#7b86a3`; Linien `#c3cde0`
- Akzent Orange `#ff6a2b` nur für die Hauptaktion; kühles Blau `#3d5afe` für die oberste, schwebende Ebene und Überzeilen
- Dunkle Fläche (Abschluss) `#141a2e`
- Farbe trägt Rang: je weiter vorn, desto heller und gesättigter

## Typografie
- Überschriften: Sora (Google Fonts), Gewicht 700, Laufweite -0.02em, Zeilenhöhe 1.08
- Fließtext: Inter 400/500, 1rem bis 1.2rem, max. 46ch
- Überzeilen: IBM Plex Mono 500, 0.75rem, Versalien, Laufweite 0.14em
- Hero `clamp(2.6rem, 6.5vw, 5.25rem)`, H2 `clamp(1.8rem, 3.4vw, 2.9rem)`
- Text bleibt flach und lesbar: nie gekippt, nie auf bewegten Flächen unter 4.5:1 Kontrast

## Abstände und Raster
- Sektionen: `clamp(4.5rem, 10vw, 8rem)` Abstand, Inhalt max. 1160px
- Hero zweispaltig (Text links, Bühne rechts), Karten im 3er-Raster mit 1.75rem Lücke
- Tiefenstufen als feste Werte: 0px, 46px, 92px (Ebene 1 bis 3); Schwebehub höchstens 120px
- Radien 10, 18, 26px; keine eckigen Karten

## Layout-Muster
- Hero: Überzeile, Headline, ein Lead-Satz, zwei Knöpfe; rechts die Bühne mit drei gestapelten, gekippten Ebenen (Kippung etwa 58 Grad um X, minus 32 Grad um Z)
- Kartenreihe: drei Karten, bei Hover kippen sie zur Seite und treten um 24px nach vorn
- Raumsektion: Text neben einem langsam kreisenden Würfel aus sechs Flächen
- Kennzahlen als eine breite, erhöhte Karte; Abschluss als dunkle Karte mit hartem Bodenschatten

## Komponenten
- Knopf: 18px Radius, unten ein fester Sockel (`0 6px 0` in dunklerer Tönung), beim Hover sinkt er um 3px ein
- Karte: weiß, 1px Linie, Schatten in zwei Lagen (`0 4px 8px` plus `0 28px 60px -18px`), Hover mit `rotateX(6deg) rotateY(-8deg) translateZ(24px)`
- Ebene: halbtransparent oder matt, mit Beschriftung in Mono, Bodenschatten unter der untersten
- Würfel: sechs Flächen, 1px Konturlinie in Blau, Füllung 12 Prozent, obere Fläche in Orange

## Bildsprache
Keine Fotos nötig: Ebenen, Würfel und Schatten sind das Bild. Im Beispiel entstehen sie rein aus CSS. In echten Projekten dürfen freigestellte Renderings oder Modelle dazukommen, immer mit weichem Bodenschatten und gleicher Lichtrichtung (von links oben).

## Animation
Langsam und schwer, nie hektisch. Bühne dreht in 18s hin und her, die oberste Ebene schwebt in 7s auf und ab, der Würfel kreist in 14s. Hover-Übergänge 420ms mit `cubic-bezier(.2,.8,.2,1)`. Nur `transform` und `opacity` animieren. `prefers-reduced-motion` respektieren: alle Dauerbewegungen aus, Hover nur noch als Zustandswechsel.

Umsetzung in echten Projekten: einfache Tiefe per CSS mit `perspective`, `transform-style: preserve-3d` und `translateZ` (Eltern bekommt die Perspektive, Kinder die Tiefe; `overflow: hidden` am Eltern zerstört die 3D-Ebene). Für echte Modelle, drehbare Produkte oder Konfiguratoren die Bibliothek Three.js oder ein Modell-Viewer-Bauteil verwenden: eine Szene, ein Licht von links oben, weicher Bodenschatten, Kamera mit leichter Neigung, Modell im glTF-Format. Canvas lädt erst, wenn es sichtbar wird (Intersection Observer), dazu ein statisches Vorschaubild als Ersatz für schwache Geräte und für Nutzer mit reduzierter Bewegung. Frame-Rate bei 60 begrenzen, Pixeldichte höchstens 2.

## Tonfall
Konkret, räumlich, ruhig. Verben des Bauens und Stapelns: legen, tragen, stellen, umrunden. Kurze Sätze, keine Superlative. Beispiel: "Jede Schicht trägt die nächste."

## Mach
- Eine Lichtrichtung für alle Schatten (links oben)
- Tiefe nach Rang: wichtig vorn, Hintergrund matt
- Perspektive am Eltern setzen, nicht an jedem Kind
- Text nie kippen, nur Flächen und Karten
- Auf Mobil Kippwinkel und Tiefen halbieren, Bühne nie breiter als der Bildschirm
- Immer einen ruhigen Zustand bieten, wenn der Nutzer weniger Bewegung wünscht

## Mach nicht
- Keine Neon-Verläufe oder Glüheffekte als Tiefenersatz
- Keine Drehung von Fließtext
- Keine Tiefe auf allem: höchstens drei Ebenen pro Bildschirm
- Keine harten, schwarzen Schatten in Gegenrichtung zur Lichtquelle
- Keine Dauerrotation schneller als 10 Sekunden pro Umlauf
- Kein schweres 3D-Modell ohne Ersatzbild

## Typische KI-Fehler in diesem Stil
- Jede Karte bekommt dieselbe wilde Drehung, sodass nichts mehr Rang hat
- Perspektive fehlt oder ist so stark, dass Ränder verzerren und Text unlesbar wird
- Schatten zeigen in verschiedene Richtungen
- Kippende Elemente ragen über den Bildrand und erzeugen horizontales Scrollen auf Mobil
- Three.js wird für eine einzelne Karte geladen, obwohl CSS-Transformationen reichen
- Die Bewegung läuft ohne Rücksicht auf reduzierte Bewegung weiter
