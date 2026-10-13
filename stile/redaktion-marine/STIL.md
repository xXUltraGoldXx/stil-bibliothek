# Stil: Redaktion Marine

## Kurzbeschreibung und Stimmung
Ein großes Nachrichtenportal: weißer Grund, sehr viele Teaser auf engem Raum, geordnet durch ein feines Linienraster und klare Rubrikfarben. Die Seite wirkt sachlich, glaubwürdig und gut sortiert. Über dem Inhalt liegt ein tiefes Marineblau (`#0c3068`) als Kopfband, der Text ist fast schwarz (`#121212`). Dichte ist gewollt: Lesende sollen auf einen Blick viele Themen überblicken, ohne dass es laut wird. Gefühl: Tageszeitung, die ins Netz übersetzt wurde, Information vor Dekoration.

## Farbpalette
- Grund: Weiß `#ffffff` (Hauptfläche), Hellgrau `#f6f6f6` für Trennbänder und Kästen, `#ededed` für Platzhalter und Avatare
- Text: Tinte `#121212`, sekundär `#707070` (Meta, Zeitangaben), `#333333` für Zweittitel
- Marine `#0c3068` für Kopfband und Hauptknopf, dunkler `#0a2552` für Unterflächen, Hellblau `#c4daf8` für Hinweisflächen
- Signalrot `#bb1212` für Kicker (Rubrikzeile über der Schlagzeile) und Textlinks
- Gelb `#f5dc1a` nur als kleiner Akzent (Balken, Marker), nie als große Fläche
- Rubrikfarben für Kicker und Oberlinie: Meinung `#bc5010` (Fläche `#fff4f2`), Sport `#0b7aae`, Kultur `#7c6a52` (Fläche `#fef9f5`), Lebensart `#b04585` (Fläche `#fef1f8`)
- Linien `#dcdcdc` 1px, kräftigere Linien `#bababa` 1px oder `#333333` 2px. Keine Schatten, Verlauf nur als Schwarz-Abdunklung unter Bildtiteln (transparent zu 80 % Schwarz)

## Typografie
- Schlagzeilen: Serife mit kräftigem Strich, z. B. Source Serif 4 (Google Fonts), Gewichte 500 (Teaser) und 700 (Rubrikkopf, Hero)
- Text und Oberfläche: serifenlose Humanist-Grotesk, z. B. Source Sans 3, Gewichte 400 und 700
- Stufen (Desktop): Rubrikkopf 28px/32px, Hero-Schlagzeile 34px, Teaser-Schlagzeile 20px/23px Gewicht 500, kleine Teaser 17px/19.5px, Standfirst und Fließtext 14px bis 15px/18px, Meta 12px/15px
- Stufen (Mobil): Rubrikkopf 24px/27.6px, Teaser 17px/19.5px, Text 14px bis 15px
- Laufweite normal, keine Versalien, keine Sperrung. Betonung durch Gewicht, nicht durch Größe
- Kicker steht in Rubrik- oder Rotfarbe, gleiche Serife, 15px, Gewicht 500, direkt über der Schlagzeile
- Schlagzeilen linksbündig, nie zentriert, höchstens 3 bis 4 Zeilen

## Abstände und Raster
- Basis 4px: Abstände 4, 8, 12, 16, 24, 40px. Häufigste Lücken zwischen Elementen innerhalb eines Teasers 8px bis 12px
- Feines Spaltenraster mit 24 Spalten ab Desktop, 14 Spalten mobil. Maximale Breite 1280px, Inhalt innen mit 20px Rand
- Rubrikkopf links in einer schmalen Spalte (ca. 1/6 der Breite), rechts daneben die Teaser in 3 bis 4 Spalten
- Spalten werden durch 1px-Linien `#dcdcdc` getrennt, nicht durch Lücken allein
- Zwischen Rubriken ein `#f6f6f6`-Band von ca. 100 bis 300px Höhe oder eine 1px-Linie
- Mobil: eine Spalte, Teaser vertikal gestapelt, Bild links klein oder oben voll breit

## Layout-Muster
- Kopf: Marineblaues Band mit großem Titelschriftzug rechts, Hauptnavigation als große Serifen-Links in Weiß (Aktives mit roter oder gelber Unterlinie 4px), darunter eine Zeile kleiner Unterthemen
- Hinweisband in Hellblau `#c4daf8` mit Info-Symbol und Schließen-Kreuz
- Hero: Rubrikname groß links, in der Mitte Kicker, große Schlagzeile und Standfirst, rechts ein breites Bild (ca. 55 % der Breite)
- Raster: Rubrikkopf links, daneben 3 bis 4 Teaser-Spalten, oben je eine farbige 1px- oder 2px-Linie
- Meinungsblock: Teaser auf getönter Fläche mit runden Autorenporträts (Radius 50 %)
- Abschluss: grauer Fußbereich mit dichten Linklisten in 12px Fett

## Komponenten
- Hauptknopf: Pillenform, Radius 36px, Fläche `#0c3068`, Text Weiß, 17px Gewicht 700, Höhe 40px bis 44px, Innenabstand 0 20px
- Zweitknopf: gleiche Pille, Weiß mit 1px Rand `#0c3068`, Text Marine
- Karussell-Pfeile: Kreis 40px, Marine, weißer Pfeil
- Teaser: Kicker, Schlagzeile, optional Standfirst 14px, Meta 12px grau. Kein Rahmen, keine Fläche, Oberlinie 1px
- Autoren-Avatar: Kreis 98px Desktop, Fläche `#ededed`
- Eingabefelder: 1px Rand `#bababa`, Radius 0, Höhe 44px
- Hinweiskästen, Ausklapper: Fläche `#f6f6f6`, 1px Linie `#dcdcdc`, Pfeil `#707070`
- Links im Text: Rot `#bb1212` mit 1px Unterlinie `#dcdcdc`, Hover Unterlinie Rot
- Radien: 0 für alles außer Pillenknöpfe (36px) und Kreise (50 %). Schatten: keine

## Bildsprache
Dokumentarische Pressefotografie in natürlichen Farben, scharf, ohne Filter. Querformat 5:3 oder 3:2, bei Hero größer. Porträts als Kreise. Bilder tragen oft eine dunkle Verlaufsfläche unten, auf der weiße Schlagzeilen stehen. Im Beispiel dienen CSS-Flächen in Grau- und Blautönen mit feiner Schraffur als Platzhalter.

## Animation
Kaum vorhanden. Hover: Unterlinie wird rot, Teaser-Schlagzeile färbt sich leicht ab (0.15s). Karussell schiebt seitlich (0.3s ease). Keine Parallax, keine Einblendungen beim Scrollen.

## Tonfall
Sachlich, knapp, informativ. Schlagzeilen sind vollständige Aussagesätze mit Subjekt und Verb, meist 8 bis 14 Wörter. Standfirsts ergänzen ein Detail statt zu wiederholen. Meinungsstücke dürfen pointierter sein. Aufrufe zum Abonnieren sind ruhig und erklärend, ohne Ausrufezeichen.

## Mach
- Viele Teaser pro Bildschirm, dicht aber mit 8px bis 12px Luft innerhalb jedes Teasers
- Serifen-Schlagzeilen in Gewicht 500, Rubrikköpfe in 700
- Kicker in Rubrikfarbe über jeder Schlagzeile
- 1px-Linien `#dcdcdc` als Gliederung, farbige Oberlinie je Rubrik
- Marineblaues Kopfband und Pillenknopf als einziger starker Farbblock
- Grauen Streifen `#f6f6f6` zwischen Rubriken setzen
- Meta (Zeit, Autor) in 12px grau unter jedem Teaser

## Mach nicht
- Keine Schatten, keine Kartenkästen mit Rundung
- Keine Sans-Serif-Schlagzeilen und keine Versalien-Schlagzeilen
- Keine zentrierten Hero-Texte, keine großen Gradient-Flächen
- Kein Gelb als Flächenfarbe, kein Rot als Knopffarbe
- Keine Emoji, keine Illustrationen im Cartoon-Stil
- Keine großen Leerräume, keine 100px-Abstände zwischen Teasern

## Typische KI-Fehler in diesem Stil
- Zu viel Luft: großzügige SaaS-Abstände statt dichtem Nachrichtenraster
- Rubrikfarben vergessen, alles nur Marine oder nur Schwarz
- Knöpfe eckig statt Pille, oder Teaser-Karten mit Radius und Schatten
- Schlagzeilen zu leicht (Gewicht 400) oder zu fett (900), statt 500 für Teaser und 700 für Rubrikköpfe
- Fehlende Kicker und Meta-Zeilen, dadurch sieht es nicht mehr nach Redaktion aus
- Hero zentriert mit Verlauf-Hintergrund statt linksbündiger Schlagzeile neben Bild
- Marineblau als Fließtextfarbe verwendet statt `#121212`
