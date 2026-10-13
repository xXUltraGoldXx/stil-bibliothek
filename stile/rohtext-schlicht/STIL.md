# Stil: Rohtext schlicht

## Kurzbeschreibung und Stimmung
Das Dokument in seiner ursprünglichen Form: weißer Grund, schwarze Serifenschrift, eine fette Überschrift, eine Aufzählung mit blauen, unterstrichenen Links und eine graue Trennlinie. Es gibt keine Karten, keine Bilder, keine Farbflächen und keine Effekte. Gefühl: Webseite aus der Frühzeit des Netzes, ehrlich, sofort lesbar, werkzeughaft. Der Reiz liegt im vollständigen Verzicht auf Dekoration. Inhalt und Verweise stehen allein.

## Farbpalette
- Grund: Weiß `#ffffff` (gemessen transparent, also der Browser-Standard)
- Text: Schwarz `#000000`
- Link: klassisches Linkblau `#0000ee`
- Besuchter Link: `#551a8b`
- Trennlinie: Grau `#808080`, 1px
- Keine weitere Farbe, keine Verläufe, keine Tönungen, keine Flächen

## Typografie
- Einzige Schrift: Times New Roman. Als Google-Font-Entsprechung dient Tinos, metrisch kompatibel. Als Rückfall Times New Roman, dann serif.
- Fließtext und Listen: 1rem (16px), Gewicht 400, Zeilenhöhe normal (etwa 1.15), Laufweite normal
- Überschrift H1: 2rem (32px), Gewicht 700, Zeilenhöhe normal
- Nur zwei Größen und zwei Gewichte im ganzen Dokument: 16px/400 und 32px/700
- Keine Versalien, keine Kursivierung als Stilmittel, keine Laufweiten-Spielerei
- Linkbeschreibungen folgen nach Leerzeichen, Bindestrich und Leerzeichen

## Abstände und Raster
- Seitenrand 8px (0.5rem), kein Container, keine Maximalbreite: Inhalt läuft über die volle Fensterbreite
- Überschrift: Außenabstand etwa 0.67em oben und unten
- Aufzählung: linker Einzug 40px (2.5rem), Listenpunkte als Scheibe
- Listeneinträge ohne Zusatzabstand, ein Eintrag etwa 18px hoch, Umbruch bei schmalem Fenster ohne Anpassung
- Trennlinie: `hr` mit 1px grauer Linie, dazu 8px Außenabstand
- Es gibt kein Raster, keine Spalten und keine Lücken. Alles ist ein einziger Fluss von oben nach unten.

## Layout-Muster
- Seitenaufbau: H1, Liste mit Verweisen, Trennlinie, ein Rücklink mit Pfeil nach links
- Eine Spalte, linksbündig, keine Zentrierung
- Mobil identisch zu Desktop: gleiche Größen, gleicher Einzug, Zeilen brechen einfach um
- Gliederung geschieht nur durch Überschrift, Liste und Linie, nie durch Kästen oder Hintergründe

## Komponenten
- Link: `#0000ee`, unterstrichen, kein Hover-Effekt nötig, besucht `#551a8b`
- Listeneintrag: Link, dann Gedankenstrich und ein kurzer Beschreibungssatz in Schwarz
- Trennlinie: graue 1px-Linie über die volle Breite
- Knöpfe, Formulare, Karten, Icons: nicht vorhanden. Wenn unvermeidlich, als Link darstellen.
- Radien: 0, Schatten: keine, Ränder: außer der Linie keine

## Bildsprache
Keine Bilder. Wo ein Platzhalter nötig ist, genügt ein schlichter Rahmen von 1px in `#808080` mit eingerückter Optik (inset) und einer Beschriftung in 16px Serif. Keine Fotos, keine Illustrationen, keine Icons.

## Animation
Keine. Keine Übergänge, keine Einblendungen, kein Scroll-Verhalten. Der Fokusring des Browsers bleibt sichtbar.

## Tonfall
Knapp, sachlich, beschreibend. Jeder Eintrag nennt einen Namen und erklärt in einem Halbsatz, was dahintersteckt. Keine Werbesprache, keine Ausrufezeichen, keine Emoji. Eher Verzeichnis als Prospekt.

## Mach
- Nur Serifenschrift in 16px und 32px verwenden
- Links in `#0000ee` unterstreichen, besuchte in `#551a8b`
- Inhalte als Liste mit Einzug 40px und Beschreibung nach Gedankenstrich ordnen
- Mit einer grauen 1px-Linie abschließen und einen Rücklink anbieten
- Echte semantische Elemente nutzen: `h1`, `ul`, `hr`, `a`
- Zeilenlänge im Beispiel auf etwa 80 Zeichen begrenzen, damit lange Fenster lesbar bleiben

## Mach nicht
- Keine Farbflächen, Verläufe, Schatten oder abgerundeten Ecken
- Keine Sans-Serif-Schrift und keine Zierschriften
- Keine Karten, Kachelraster, Hero-Flächen oder Knöpfe
- Keine Icons, keine Emoji, keine Animationen
- Keine zusätzlichen Akzentfarben neben Blau und Violett für Links

## Typische KI-Fehler in diesem Stil
- Die Seite wird "veredelt": Sans-Serif, Karten, Schatten und Pastellfarben schleichen sich ein und zerstören die Rohheit.
- Links werden ohne Unterstreichung oder in einem modernen Blau gesetzt statt in `#0000ee`.
- Es entsteht ein zentrierter Container mit Hero-Bereich, obwohl der Stil nur Überschrift und Liste kennt.
- Es werden viele Schriftgrößen und Gewichte eingeführt, statt bei 16px/400 und 32px/700 zu bleiben.
- Hover-Animationen, Knöpfe und Icons werden ergänzt, obwohl der Stil sie nicht kennt.
- Die Liste wird in Kacheln umgebaut, statt Einzug und Aufzählungspunkte beizubehalten.
