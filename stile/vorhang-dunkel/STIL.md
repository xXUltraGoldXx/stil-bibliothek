# Stil: Vorhang dunkel

## Kurzbeschreibung und Stimmung
Eine schwarze Bühne kurz vor Beginn der Vorstellung. Große Versalienzeilen in einer eleganten Serife stehen in kurzen Blöcken, jede Zeile gegen die vorige seitlich versetzt, getrennt von hauchdünnen Linien. Dazu kleine Monospace-Angaben wie ein Zählerstand am unteren Rand. Die Stimmung ist ruhig, konzentriert und leicht theatralisch. Fast alles ist Text, kaum etwas ist Dekoration.

## Farbpalette
- Bühne (Hauptfläche) `#131313`
- Papier (Text auf Dunkel, helle Gegenfläche) `#f9f9f9`
- Hellgrau `#e9e9e9` für Markierungsflächen, etwa ein invertiertes Wort hinter einer Überschrift
- Dunkelgrau `#626262` für Nebentext und deaktivierte Zeilen
- Haarlinie: 1px solid `rgba(233,233,233,0.18)` auf Dunkel
- Keine Akzentfarbe. Kontrast entsteht allein durch Schwarz, Weiß und Grauabstufungen. Keine Verläufe.

## Typografie
- Schlagzeilen: Instrument Serif (Google Fonts), Gewicht 400, Versalien, Größe 1.7rem (27px) bis 2.1rem, Zeilenhöhe 1, Laufweite -0.02em. Für größere Auftritte bis 3rem
- Fließtext und Navigation: IBM Plex Mono (Google Fonts), Gewicht 400, 0.85rem (13.5px), Zeilenhöhe 1.5. Instrument Serif und IBM Plex Mono sind frei verfügbare Google Fonts
- Meta und Zähler: IBM Plex Mono, 0.74rem (11.85px), Laufweite -0.02em
- Lead-Zeile: Instrument Serif, 2.1rem (33.9px), Zeilenhöhe 1, Groß- und Kleinschreibung
- Es gibt nur Gewicht 400. Hierarchie entsteht über Größe, Schriftfamilie und Versalien, niemals über Fettdruck

## Abstände und Raster
- Acht Spalten, Spaltenlücke 1.6rem, Außenrand 0.8rem
- Spaltenbreite: 12.5vw minus 1.6rem
- Innenabstände sehr klein: 0.26rem, 0.42rem, 0.55rem. Große Ruhe entsteht durch leere dunkle Flächen, nicht durch Polster
- Zeilenblöcke sind oben und unten von Haarlinien eingefasst; dazwischen 2rem bis 4rem Leerraum
- Sektionen sind mindestens eine Bildschirmhöhe oder zumindest 70vh hoch

## Layout-Muster
- Eröffnung: leere dunkle Fläche oben, in der Mitte ein Block aus fünf Versalienzeilen, jede Zeile um eine oder zwei Spalten gegenüber der vorigen versetzt (rechts, links, mittig im Wechsel)
- Wiederholung desselben Blocks mit leicht anderem Versatz, zwischen den Blöcken Haarlinie und ein leerer Streifen
- Am unteren Rand mittig ein kleiner Zähler mit Dreieck und Prozentwert
- Eine helle Sektion in `#f9f9f9` mit dunklem Text dient als einziger Wechsel; dort gleiche Typografie, invertiert
- Mobil: Versatz halbieren, Zeilen laufen nicht über den Rand

## Komponenten
- Knöpfe: reine Textknöpfe in Monospace, ohne Rahmen, ohne Füllung, Innenabstand 0.42rem oben und unten, Hover mit Unterstreichung
- Navigation: kleine Monospace-Links in Papierfarbe, am Rand verteilt
- Markierung: ein Wort in Überschrift auf `#e9e9e9` mit dunkler Schrift, Innenabstand 0 0.26rem
- Fortschrittszähler: Dreieck und Zahl in 0.74rem
- Radien 0, Schatten keine, Rahmen nur als Haarlinie

## Bildsprache
Bilder treten zurück. Wo sie nötig sind, erscheinen sie als schmale, dunkle Flächen mit Haarlinienrahmen oder als einfarbige Grautöne zwischen `#131313` und `#626262`. Im Beispiel dienen CSS-Flächen mit feinen Linienmustern als Platzhalter. Kein Foto mit Rahmen, Schatten oder Verlauf.

## Animation
Animation ist ein Kernelement: Zeilen werden nacheinander eingeblendet, gleiten seitlich in ihre Position oder bauen sich Buchstabe für Buchstabe auf, wobei Wiederholungen des ersten Buchstabens als blasse Spur davonlaufen. Dauer 0.6s bis 1.2s, sanftes ease-out, Versatz zwischen Zeilen 0.12s. Ein Zähler läuft hoch bis 100%. Bei reduzierter Bewegung wird alles statisch gezeigt.

## Tonfall
Kurz, ruhig, in Aufforderungen und Zuständen formuliert, wie Hinweise vor Beginn einer Aufführung. Fünf Zeilen pro Block, jede nur wenige Wörter. Keine Ausrufezeichen, keine Werbesprache.

## Mach
- Versalien-Serife in 1.7rem bis 2.1rem mit Laufweite -0.02em
- Zeilen gestaffelt versetzen, Haarlinien `rgba(233,233,233,0.18)` als Rahmen
- Monospace nur klein, 0.74rem bis 0.85rem
- Viel dunkle Leere, Blöcke mittig im Bildschirm
- Nur Gewicht 400 verwenden
- Einblendungen zeilenweise staffeln

## Mach nicht
- Keine Akzentfarbe, keine Verläufe, keine Schatten
- Keine abgerundeten Ecken
- Kein Fettdruck
- Keine Kacheln oder Karten mit Füllung
- Keine Emoji und keine Icon-Kreise
- Keine zentrierte Dreierreihe mit Symbolen

## Typische KI-Fehler in diesem Stil
- Reinweiß `#ffffff` und Reinschwarz `#000000` statt der leicht gedämpften `#f9f9f9` und `#131313`
- Überschriften fett gesetzt, obwohl der Stil nur Gewicht 400 kennt
- Alle Zeilen zentriert statt gestaffelt versetzt
- Monospace für Schlagzeilen und Serife für Kleintext, also vertauschte Rollen
- Neonfarbe als Akzent oder Glow-Schatten, was den ruhigen Bühnencharakter zerstört
- Zu viel Inhalt pro Bildschirm; der Stil lebt von wenigen Zeilen und Leerraum
