# Stil: Katalog hell

## Kurzbeschreibung und Stimmung
Eine Medien-Galerie im Browser: kühles Grauweiß als Bühne, darauf hochformatige Bildkacheln in Reihen, die seitlich weiterlaufen. Die Oberfläche tritt zurück, die Bilder tragen die Farbe. Gefühl: aufgeräumtes Schaufenster, freundlich, übersichtlich, ohne Schnickschnack. Der Kern des Stils sind die Kachelreihe mit schlichter Beschriftung darunter und die zentrierten, leisen Rubrik-Überschriften.

## Farbpalette
- Seitengrund `#f8f9fa`, Reihenband `#f1f2f3`, Karten-/Kopfzeilenfläche `#ffffff`
- Text: Schwarz `#000000` für Titel, `#222222` für Überschriften, `#333333` für Nebentext, Fließtext `rgba(0,0,0,.7)`
- Dunkle Kontrastfläche: `#3a3e41` auslaufend in `#1c1d1f` (Verlauf von oben nach unten), Text darauf `#ffffff`
- Haarlinie `rgba(0,0,0,.05)`
- Keine Signalfarbe in der Oberfläche; Farbe kommt nur aus den Bildern. Im Beispiel: Platzhalter in gedämpftem Blau, Violett und Petrol

## Typografie
- Eine humanistische Sans: Source Sans 3 (Google Fonts), Gewichte 400, 600, 700
- Überschriften der Reihen: 1.25rem (20px), Gewicht 400, Zeilenhöhe 1.2, zentriert, Farbe `#222222`
- Große Aussage auf Dunkel: 1.9rem (30px) mobil 1.5rem, Gewicht 400, Zeilenhöhe 1.2, Weiß
- Kartentitel: 1.125rem (18px), Gewicht 400, Zeilenhöhe 1.5, linksbündig unter dem Bild
- Fließtext und Navigation: 1rem, Zeilenhöhe 1.2 bis 1.5
- Meta/Labels: 0.75rem bis 0.875rem, Versalien nur für kleine Beschriftungen, Gewicht 700
- Laufweite normal, keine Sperrung. Gewichte bleiben meist 400; Fett nur punktuell

## Abstände und Raster
- Inhaltsbreite maximal 1024px bis 1120px, zentriert, seitlicher Rand 80px Desktop, 20px mobil
- Kachelreihe: 5 Karten à ca. 205px Breite, Lücke 24px, die sechste ragt angeschnitten heraus
- Zweispaltige Großkacheln: je 550px, Lücke 20px
- Abschnitte vertikal 80px Abstand, Überschrift zu Reihe 30px
- Innenabstände aus der Reihe 8, 12, 20, 30, 40px

## Layout-Muster
- Schlanke weiße Kopfzeile (Höhe ca. 63px) mit Navigation
- Vollbreiter dunkler Hero-Block mit Verlauf `#3a3e41` zu `#1c1d1f`
- Darunter Bänder in `#f1f2f3`: zentrierte Rubrik-Überschrift, dann horizontale Reihe hochformatiger Kacheln mit Titel darunter
- Weiter unten zwei große Querkacheln nebeneinander, mobil untereinander
- Abschluss mit weißer Fußzeile, Links in `#333333`

## Komponenten
- Bildkarte: Seitenverhältnis 2:3, Radius 2px, Schatten `0 0 1px rgba(0,0,0,.25)`, Titel darunter ohne Kasten
- Pfeilknopf des Karussells: weißer Kreis, 44px, Radius 100%, dunkler Chevron, sitzt am rechten Rand der Reihe
- Primärknopf: weiß `#ffffff`, Text `#000000`, Radius 5px, Innenabstand 20px, 2px Rahmen in Schwarz, Gewicht 400
- Navigationslinks: 17.6px, Gewicht 600, Schwarz
- Große Kacheln: Radius 0 bis 2px, Bildfläche randlos

## Bildsprache
Hochformatige Titelmotive, farbstark und detailreich, in großem Kontrast zur neutralen Oberfläche. Querformatige Großkacheln mit dunklem Nachthimmel oder satten Violett-Blau-Verläufen und kleinen Funkelpunkten. Im Beispiel: CSS-Flächen mit Verläufen und einfachen SVG-Sternen als Platzhalter, keine echten Motive.

## Animation
Zurückhaltend: Karussell schiebt seitlich weich (0.4s ease), Kacheln heben sich beim Hover minimal um 2px, Pfeilknopf blendet auf Hover leicht ein. Keine Parallax-Effekte, keine großen Einblendungen.

## Tonfall
Kurz, sachlich, einladend. Überschriften aus ein bis vier Wörtern, Kartentitel nur der Name. Keine Ausrufezeichen, keine Werbefloskeln.

## Mach
- Reihen aus gleich großen Hochformat-Kacheln mit angeschnittener letzter Karte
- Rubrik-Überschrift zentriert, klein (20px), Gewicht 400
- Hellgrauer Grund `#f1f2f3`, weiße Kopfzeile, ein dunkler Verlaufsblock als Kontrast
- Radien klein (2px), Schatten nur als Haarschatten
- Bilder tragen die Farbe, die Oberfläche bleibt neutral

## Mach nicht
- Keine Akzentfarbe für Knöpfe oder Überschriften
- Keine großen Radien oder weiche, weite Schatten
- Keine fetten, riesigen Headlines
- Keine Textblöcke auf den Kacheln, Titel stehen darunter
- Keine Kästen um Kartentitel

## Typische KI-Fehler in diesem Stil
- Eine Markenfarbe für Knöpfe und Links ergänzen, obwohl die Oberfläche neutral bleiben soll
- Karten mit 16px Radius und großem Schatten statt 2px und Haarschatten
- Überschriften groß und fett statt 20px in Gewicht 400
- Kachelreihe als Raster mit Umbruch statt als horizontale Reihe mit angeschnittener Karte
- Querformat-Kacheln statt 2:3 Hochformat
- Titel in die Bildfläche gelegt statt darunter
