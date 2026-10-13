# Stil: Brutalist

## Kurzbeschreibung und Stimmung
Roh, laut, ehrlich. Wie Beton: sichtbare Struktur, keine Kosmetik. Dicke schwarze Rahmen, harte versetzte Schatten, Monospace-Text, Grellfarbe auf Grau. Wirkt bewusst "unfertig", ist aber streng durchdacht und gut lesbar.

## Farbpalette
- Hintergrund Betongrau `#e8e8e3`, Flächen Weiß `#ffffff`, Schwarz `#000000`
- Grellgelb `#ffe600` als Hauptsignal
- Optional je Seite eine zweite Grellfarbe: Alarmrot `#ff2d1a` oder Blau `#1a3cff`
- Keine Verläufe, keine Transparenz, keine Pastelltöne

## Typografie
- Headlines: Archivo Black, GROSSBUCHSTABEN, enge Zeilenhöhe 0.9, bis 10rem
- Text: Space Mono, 1rem, Zeilenhöhe 1.5
- Gewichte: nur Regular und Bold (Mono), Display ist schon fett
- Links immer unterstrichen. Zahlen und Labels in Mono-Versalien
- Absichtlich harte Größensprünge, kein sanfter Verlauf der Größen

## Abstände und Raster
- Sichtbares Raster: Kästen mit 4px-Rahmen stoßen direkt aneinander (Rahmen teilen sich)
- Abstände in 1.5rem-Schritten, Innenabstand der Kästen 1.5 bis 2rem
- Asymmetrie erlaubt: ungleich breite Spalten, linksbündig, kein Zentrieren als Reflex

## Layout-Muster
- Hero: gigantische Versalien-Headline, direkt darunter Gelber Kasten mit Kurztext und Knopf. Optional laufendes Textband (Marquee) in Schwarz
- Sektionen: nummeriert ("01 /", "02 /"), Rahmen-Gitter
- Karten: Weiße Kästen, 4px Rahmen, harter Schatten 8px, bei Hover 4px versetzt
- CTA: ganzflächig Gelb oder Rot mit riesiger Schrift

## Komponenten
- Knöpfe: Rechteck, 4px Rahmen, harter Schatten, Hover: Schatten verschwindet und Knopf rückt hinein (translate 4px)
- Formulare: weiße Felder mit 4px Rahmen, Fokus: Gelb
- Radien: immer 0. Schatten: nur hart, nie weich
- Tabellen/Listen mit sichtbaren Linien

## Bildsprache
Grobe Raster, Schwarzweiß, hoher Kontrast, Dithering, Systemschriften als Bild, ASCII. Im Beispiel: Streifen und Blöcke aus CSS.

## Animation
Hart und sprunghaft: Schatten-Versatz, Farbumschlag, Textband. Keine weichen Übergänge (höchstens 80ms). `prefers-reduced-motion` abschalten.

## Tonfall
Direkt, kurz, imperativ, ohne Höflichkeitsfloskeln. Versalien für Kernaussagen. Beispiel: "WIR BAUEN. DU ZAHLST NICHT FÜR LUFT."

## Mach
- Dicke Rahmen und harte Schatten konsequent überall
- Maximal 2 Grellfarben plus Schwarz/Weiß/Grau
- Riesige Versalien, Mono-Fließtext
- Lesbarkeit sichern (Kontrast, Zeilenlänge unter 70 Zeichen)

## Mach nicht
- Keine Rundungen, keine weichen Schatten, keine Verläufe, kein Glas
- Keine Pastellfarben, keine Emoji-Icons
- Keine zentrierte Mittelmäßigkeit: entweder laut oder gar nicht
- Keine feinen 1px-Linien
- Nicht "unleserlich" mit "brutalistisch" verwechseln

## Typische KI-Fehler in diesem Stil
- Weiche Schatten und 8px Radien bleiben "aus Gewohnheit" drin
- Zu viele Farben, dadurch Regenbogen statt Härte
- Zu zahm: dünne Rahmen, normale Abstände, am Ende ein Standard-Look mit Mono-Schrift
- Mobil bricht der Text über den Rand (lange Versalien-Wörter ohne Umbruch)
