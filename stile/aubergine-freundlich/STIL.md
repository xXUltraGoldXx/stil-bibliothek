# Stil: Aubergine freundlich

## Kurzbeschreibung und Stimmung
Eine helle, offene Produktseite für Teamsoftware. Weißer Grund mit zartem Lavendelschimmer, dazu große Flächen in tiefer Aubergine, die dem Seitenverlauf Rhythmus geben. Die Schlagzeilen sind groß, geometrisch und fett, der Fließtext ist schlicht und gut lesbar. Gefühl: kompetent, einladend, nie kühl. Der Kern des Stils ist der Wechsel zwischen luftigen weißen Abschnitten und einer dunklen Aubergine-Bühne mit weich geschwungener Unterkante, dazu Knöpfe in Versalien und runde Karten mit weichem Schatten.

## Farbpalette
- Grund Weiß `#ffffff`, Text Schwarz `#000000`, Fließtext sekundär `#5c5c5c`
- Aubergine tief `#4f2360` für Bühnenflächen, Fußbereich und Hover-Zustände
- Primärknopf Violett `#7d0f9c`, Text weiß; Akzent hell `#a012cd` für Hervorhebungen und Verlaufsende
- Lavendel `#f9f0ff` für Kartenflächen und Abschnitte, abgeschwächt `rgba(249,237,255,.25)`
- Linkblau `#0b5cab` nur für Textlinks im Fließtext
- Rahmen neutral `#c9c9c9`, feine Trennlinie `rgba(0,0,0,.04)`
- Verläufe: oben auf der Seite von Lavendel `#f9f0ff` nach Weiß; weiche Farbflecken (Rosa `rgba(255,100,150,.25)`, Blau `rgba(100,150,255,.25)`) als radiale Schimmer hinter Produktbildern
- Textmenge: Schwarz dominiert deutlich, Aubergine ist die einzige große Flächenfarbe

## Typografie
- Schlagzeilen: geometrische Grotesk, Jost (Google Fonts), Gewicht 700 für H1 und H3, 600 für H2
- Fließtext und Knöpfe: Nunito Sans (Google Fonts) als nahe, freundliche Ersatzschrift, Gewichte 400, 600, 700
- H1 4rem (Mobil 2rem), Zeilenhöhe 1.125, Laufweite -0.012em
- H2 3.6rem (Mobil 1.75rem), Zeilenhöhe 1.25, Gewicht 600, auf Aubergine in Weiß
- H3 1.5rem (Mobil 1.4rem), Gewicht 700, Zeilenhöhe 1.3
- Text 1rem bis 1.125rem, Zeilenhöhe 1.5; Lead 1.125rem
- Knöpfe und Kleinlabels: 0.875rem, Gewicht 700, Versalien, Laufweite 0.057em
- Meta-Labels 0.75rem, Versalien, Gewicht 700, Violett

## Abstände und Raster
- Inhaltsbreite 1200px, Text- und Hero-Block höchstens 960px, zentriert
- Basiseinheit 8px: 8, 12, 16, 24, 32, 40, 48 px
- Abschnitte vertikal 5rem bis 7rem Abstand (Mobil 3.5rem)
- Karten innen 24px, Lücke zwischen Karten 32px, Lücke in Knopfgruppen 8px bis 16px
- Seitenrand Mobil 24px, Desktop 32px
- Drei Spalten für Karten, zwei Spalten für Text plus Bild; unter 800px eine Spalte

## Layout-Muster
- Hero: zentriert, große Zweizeilen-H1, kurzer Lead, zwei Knöpfe nebeneinander (gefüllt und Kontur), darunter eine Vertrauenszeile und ein breites Produktfenster als Platzhalter
- Bühne: volle Breite in Aubergine, zentrierte Weiß-Schlagzeile, links eine Liste von Funktionen mit hervorgehobenem aktivem Eintrag als weiße Pille, rechts das Bildfenster; Unterkante als große Wölbung (Radius 48px bis 50%)
- Kartenreihe mit Titelzeile, Pfeil-Schaltern rechts und Karten mit Lavendel-Bildfläche oben
- Abschluss: Aubergine-Band mit kurzer Schlagzeile und zwei Knöpfen
- Fuß: mehrspaltige Linkliste auf Weiß

## Komponenten
- Primärknopf: Violett `#7d0f9c`, Weiß, Radius 4px, Padding 19px 40px (Mobil volle Breite), Versalien 0.875rem, Gewicht 700
- Sekundärknopf: transparent, 1px Rahmen `#7d0f9c`, Text Violett, gleiche Maße, oft mit Pfeil "→"
- Auf Aubergine: weißer Rahmen und weiße Schrift
- Karten: Weiß, Radius 16px, Schatten `0 0 32px rgba(0,0,0,.1)`, Kopfbild mit Radius 16px 16px 0 0 in Lavendel, darunter Meta-Label, H3, Zweizeiler
- Pillen: Radius 999px, Lavendel-Fläche oder weiß auf Aubergine, 0.75rem Innenabstand vertikal, 1.25rem horizontal
- Badges: kleine Pille, Lavendel, Versalien 0.7rem
- Produktfenster: Radius 16px, dunkle Aubergine-Kopfleiste mit drei Punkten, helle Innenflächen mit grauen Platzhalterbalken
- Navigation: weiß, 80px hoch, Links 1rem Gewicht 600, rechts ein Konturknopf und ein gefüllter Knopf

## Bildsprache
Produktoberflächen als saubere Fenster mit abgerundeten Ecken, grauen Textbalken und kleinen farbigen App-Symbolen, dazu funkelnde Sterne und Punkte auf der Aubergine-Fläche. Bunte, freundliche Akzente nur in kleinen Symbolen. Im Beispiel bestehen alle Bilder aus CSS-Flächen und Inline-SVG: Fensterrahmen, Balken, Kreise, Vierzack-Sterne.

## Animation
Ruhig und beiläufig: Hover auf Knöpfen wechselt die Fläche in Aubergine `#4f2360` in 0.2s; Karten heben sich um 4px mit stärkerem Schatten (0.25s). Aktive Funktion in der Liste wechselt weich per Hintergrund-Übergang. Sterne dürfen langsam funkeln (3s, Opazität 0.4 bis 1). Alles mit prefers-reduced-motion abschaltbar.

## Tonfall
Direkt, freundlich, in der Du-Form. Kurze Aussagesätze, Nutzen vor Technik, konkrete Beispiele aus dem Arbeitsalltag. Schlagzeilen als vollständige Aussage in Satzschreibung. Knopftexte sind Handlungen in Versalien.

## Mach
- Große, fette Schlagzeile, Zweizeiler, zentriert im Hero
- Eine tiefe Aubergine-Bühne pro Seite mit geschwungener Unterkante
- Knöpfe als Paar: gefüllt Violett plus Kontur
- Karten mit Radius 16px und weichem 32px-Schatten
- Lavendel-Verlauf am Seitenanfang, Farbschimmer hinter Produktbildern
- Aktiven Eintrag in Listen als weiße Pille hervorheben
- Vertrauenszeile mit einer Reihe neutraler Platzhalter unter dem Hero

## Mach nicht
- Keine zweite Dunkelfarbe neben Aubergine, kein reines Schwarz als Fläche
- Keine harten Kanten bei Karten und Bildfenstern, kein Radius unter 4px
- Keine Kleinbuchstaben-Knöpfe und keine Pastellknöpfe
- Keine Fließtexte in Lavendel oder Violett, Text bleibt Schwarz oder Grau
- Keine Schlagschatten mit Versatz nach unten über 20px
- Keine Serifen, keine Schmuckschriften

## Typische KI-Fehler in diesem Stil
- Aubergine wird zu Lila, Blau oder Neonviolett verschoben; das Primärviolett `#7d0f9c` und die Bühne `#4f2360` müssen verschieden und satt bleiben
- Knöpfe werden vollrund (Pille) statt mit 4px Radius gebaut
- Die Wölbung der Bühnenunterkante fehlt, die Fläche endet als gerader Block
- Schlagzeilen werden zu leicht oder zu klein gesetzt; H1 braucht Gewicht 700 und mindestens 4rem am Desktop
- Karten bekommen Rahmen statt weichem, breitem Schatten
- Zu viele Farben in Symbolen verteilt statt Weiß, Schwarz, Violett und Aubergine als Gerüst
- Lavendel-Verlauf wird über die ganze Seite gezogen statt nur oben und hinter Produktbildern
