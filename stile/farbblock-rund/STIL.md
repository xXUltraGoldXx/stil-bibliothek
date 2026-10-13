# Stil: Farbblock Rund

## Kurzbeschreibung und Stimmung
Eine Seite aus großen, vollflächigen Farbblöcken in Gelb, Blau, Violett, Türkis und Grün, getrennt durch weiße Ruhezonen. Dazu eine runde, kräftige Grotesk, Pillen-Knöpfe und nahezu schwarze Schrift. Das Gefühl: Spielzimmer mit Ordnung. Fröhlich und einladend, aber nie chaotisch, weil jede Farbfläche genau eine Aufgabe hat. Der Kern ist die Kombination aus mutigen Flächenfarben, 999px-runden Knöpfen und sehr klarer, kontrastreicher Typografie.

## Farbpalette
- Signalgelb `#ffd502` für Kopfzeile, Hauptflächen und Hervorhebungen, helles Butter `#ffef7a` für sanfte Bänder
- Kobaltblau `#005ad2` für große Bühnenflächen, Linkblau `#006db7` nur für Textlinks
- Violett `#4c2f92`, Indigo `#4637a0` für Themenbänder
- Türkis `#71ccd5` für leichte, freundliche Bänder
- Tannengrün `#004a2d` als ruhiger, dunkler Gegenpol
- Tinte `#141414` für Überschriften und Footer, Fließtext `#2c2c2c`, Weiß `#ffffff`, Hellgrau `#f2f2f2`
- Rot `#fb1514` nur für kleine Marken wie Sale-Etiketten, nie als Fläche
- Verhältnis: etwa 50 % Weiß, 30 % Schwarz-/Dunkelflächen, 20 % Farbblöcke. Pro Block eine Farbe, keine Verläufe
- Text auf Gelb, Butter und Türkis ist Tinte, auf Blau, Violett, Grün und Schwarz ist er Weiß

## Typografie
- Eine einzige Familie: Outfit (Google Fonts), Gewichte 400, 500, 700
- Schlagzeilen: Gewicht 700, Zeilenhöhe 1.35, H2 `clamp(1.4rem,3vw,2.2rem)` (rund 28.6px Desktop, 22px Mobil), H1 bis 2.6rem
- H3 und Kartentitel: 1.17rem, Gewicht 700
- Fließtext: 1rem, Gewicht 400, Zeilenhöhe 1.5
- Kleintext und Meta: 0.875rem bis 0.75rem, Gewicht 500, Laufweite 0.01em, Zeilenhöhe 1.5
- Knopfbeschriftung: Gewicht 500 bis 700, Versalien nur bei Spiel- und Aktionsknöpfen
- Keine Serifen, keine Kursive, keine extrem großen Display-Größen. Kontrast entsteht über Gewicht und Farbfläche

## Abstände und Raster
- Basis 4px, gebräuchliche Stufen: 4, 8, 12, 16, 20, 24, 32, 40, 56
- Max. Inhaltsbreite 1280px mit 16px Seitenrand mobil und 40px Desktop
- Raster: 4 Kacheln pro Reihe ab 1000px, 2 ab 600px, 1 darunter, Lücke 16px
- Farbblöcke laufen randlos über die volle Breite, der Inhalt darin sitzt im Container
- Abschnittshöhe: 56px Innenabstand oben und unten, zwischen Blöcken weiße Zonen von 40px
- Brüche (Breakpoints): 36em, 56em, 75em

## Layout-Muster
- Kopfzeile: gelbe Leiste, 102px hoch am Desktop, Logo-Platzhalter links, Pillen-Navigation, Icon-Knöpfe rechts
- Hero: zweigeteilte Bühne, links Blau mit Weiß-Text, rechts Gelb mit Tinte-Text, mobil gestapelt
- Kachelreihen: farbige Karten mit Bildfläche oben (Radius 8px oben) und Textblock unten
- Themenbänder: volle Breite in Violett, Türkis oder Grün mit zweispaltigem Inhalt, Text links, Bildfläche rechts, Reihenfolge wechselt
- Abschnittstitel stehen linksbündig mit kurzer Unterzeile und Pillen-Link rechts
- Footer: Tinte `#141414`, vier Linkspalten, weiße Schrift

## Komponenten
- Primärknopf: Pille mit Radius 999px, Innenabstand 12px 24px, Tinte gefüllt mit Weiß-Text oder Weiß gefüllt mit Tinte-Text auf Farbflächen
- Sekundärknopf: Pille mit 2px Rahmen in Tinte, transparent
- Fokus: 2px Ring in Tinte mit 2px Abstand, bei Blau-Flächen in Weiß
- Karten: Radius 8px, flach, Rand 1px `rgba(0,0,0,.06)` auf Weiß, keine Schatten
- Runde Icon-Knöpfe: Kreis 48px, Weiß, 2px Linien-Icon in Tinte
- Etiketten: kleine Pillen, Radius 999px, 12px Text, Gelb oder Rot
- Eingabefelder: Pille, Höhe 48px, 2px Rand `rgba(0,0,0,.74)`
- Schatten fast nie, nur ein 1px-Innenring `#b0b0b0` bei Auswahlfeldern

## Bildsprache
Freigestellte, helle Produkt- und Figurenbilder auf einfarbigem Grund, der zur Blockfarbe passt. Fröhliche, klare Motive ohne Beiwerk. Im Beispiel ersetzen CSS-Flächen aus Kreisen und Rechtecken in den Palettenfarben die Bilder. Bildflächen oben mit 8px Radius, immer mit klarer Farbe hinterlegt.

## Animation
Kurz und federnd: Knöpfe skalieren beim Hover auf 1.04 in 0.15s, Karten heben sich um 4px in 0.2s. Fokusring erscheint sofort. Keine Parallax-Effekte, keine Dauerschleifen. Bei prefers-reduced-motion entfallen alle Bewegungen.

## Tonfall
Direkt, warm, in der Du-Form. Kurze Sätze, Einladung zum Entdecken und Mitmachen, Aktionsverben auf Knöpfen ("Entdecken", "Jetzt starten"). Keine Fachsprache, keine Ironie, kein Druck.

## Mach
- Volle Farbblöcke mit genau einer Farbe und passender Schriftfarbe
- Pillen-Knöpfe mit Radius 999px, Tinte oder Weiß
- Eine Schriftfamilie in 400, 500, 700
- 8px Radius für Karten und Bildflächen, 4px-Raster einhalten
- Weiße Pausen zwischen den Farbflächen
- Meta-Text klein (12 bis 14px) mit leichter Laufweite

## Mach nicht
- Keine Verläufe, keine Glas- oder Neon-Effekte
- Keine Schatten unter Karten
- Keine eckigen Knöpfe
- Keine mehr als eine Farbe pro Block
- Keine Serifen oder Kursive
- Kein Grauton als Fließtext unter `#2c2c2c`

## Typische KI-Fehler in diesem Stil
- Alle Farben in einen Regenbogen-Streifen gemischt statt klare, einfarbige Blöcke
- Knöpfe mit 8px Radius statt vollrunder Pille
- Schatten und Verläufe auf Karten ergänzt, die hier flach sind
- Weiße Schrift auf Gelb oder Türkis, was zu wenig Kontrast gibt
- Zu großzügige Display-Schlagzeilen, wo eigentlich 28px mit Gewicht 700 reicht
- Hero komplett einfarbig statt zweigeteilt, und Kachelreihen zentriert statt randlos in Blöcken
