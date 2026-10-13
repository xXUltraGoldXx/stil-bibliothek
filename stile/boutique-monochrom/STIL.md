# Stil: Boutique monochrom

## Kurzbeschreibung und Stimmung
Digitale Luxus-Boutique: reines Weiß, reines Schwarz, dazwischen große, ruhige Bildflächen. Die Oberfläche tritt zurück wie ein Schaufenster, die Ware und das Bild sprechen. Gemessen wurde durchgehend Schwarz (#000000) auf Weiß (#ffffff), kein Radius, kein Schatten, ein einziges Textgewicht (400) und eine konstante Laufweite von 0.5px. Gefühl: leise, kuratiert, teuer, ohne Dekor.

Kern des Stils: eine feine Antiqua für wenige Schlagzeilen, eine schlichte geometrische Sans in kleinen 12px für alles andere, zweigeteilte Vollbild-Einstiege und gedämpfte Hilfsflächen aus Hellgrau.

## Farbpalette
- Weiß `#ffffff` Grundfläche, nahezu 100 % der Fläche (Variante `#fefefe` für Bänder)
- Schwarz `#000000` für Text, Hauptknopf, Linien, Kopfband
- Hellgrau `#f3f3f3` für Zweitknöpfe und Flächen auf Mobil
- Linien `#dfdfdf` (fein) und `#999999` (Eingabefelder, Platzhaltertext)
- Kopfband (Hinweisleiste) in Anthrazit `#333333` mit weißem Text
- Keine Akzentfarbe. Farbe kommt ausschließlich aus den Bildern
- Keine Verläufe außer einem weißen Ausblendverlauf an Karussell-Rändern

## Typografie
- Schlagzeilen: Marcellus (Google Fonts, ähnlich zur gemessenen Optima), Gewicht 400, 20px/26px als Seitentitel, 28px/33.6px für Abschnitte, bis 44px/52.8px im Hero. Mobil 18px, 24px, 34px
- Alles andere: Nunito Sans (Google Fonts, ähnlich zur gemessenen Avenir Next), Gewicht 400, 12px mit Zeilenhöhe 16.8px, Laufweite 0.5px
- Navigation und Knopf-Links in Versalien, 12px (Mobil 14px)
- Fließtext in 14 bis 16px, nur wo wirklich gelesen wird
- Nie fett. Hierarchie entsteht durch Schriftfamilie, Größe und Versalien, nicht durch Gewicht
- Gemessen: Zeilenhöhe etwa 1.4 für Sans, 1.3 für Antiqua

## Abstände und Raster
- Seitenrand 30px Desktop (1.875rem), 12px Mobil, volle Breite ohne Maximalbreite für Bildbereiche
- Textspalten höchstens 640px
- Innenabstand Knopf 10px, Listen und Leisten 9 bis 10px, Blöcke 24px, 30px, 40px, selten 82px
- Raster: zwei gleiche Hälften für den Einstieg, vier bis sechs gleiche Spalten für Produktreihen, Lücke 8 bis 12px, Mobil 24px zwischen Blöcken
- Schlagzeile mit 8px Abstand nach unten

## Layout-Muster
- Oben: schmale Hinweisleiste (dunkel, zentrierter Text), dann Kopfzeile mit zentriertem Wortmarken-Platzhalter, Sprachwahl rechts, darunter Navigationsleiste: links vier Versalien-Einträge, rechts Symbole (Suche, Konto, Merkliste, Tasche) als dünne Linienzeichnungen
- Einstieg: Vollbild-Zweiteilung, zwei Bildflächen nebeneinander (je 640px bei 1280px), darauf mittig eine zarte Antiqua-Beschriftung in Weiß
- Danach lange vertikale Reihenfolge aus Bildkacheln und Produktreihen, kaum Text dazwischen
- Mobil: Hälften werden gestapelt, Reihen horizontal wischbar oder zweispaltig
- Modale Dialoge: weiße Fläche 540px breit, linksbündiger Text, zwei gestapelte Knöpfe mittig

## Komponenten
- Hauptknopf: Schwarz `#000000`, Text weiß, 1px Rand schwarz, Radius 0, Innenabstand 10px, 250px breit, Text mittig
- Zweitknopf: Hellgrau `#f3f3f3`, Text schwarz, gleiche Maße
- Links: Text schwarz, unterstrichen nur im Fließtext, Navigation ohne Unterstreichung
- Eingaben: nur feine Linie unten (`#999999`), transparent, 16px auf Mobil
- Karten: keine Kästen, kein Rand. Bild, darunter zwei Zeilen 12px (Bezeichnung in Versalien, Name, Preis)
- Symbole: 1px Linie, 20px, schwarz
- Radien 0 überall. Schatten keine (höchstens eine weiße 1px-Kante)

## Bildsprache
Großformatige Modefotografie, natürliches Licht, warme gedämpfte Töne, Personen in ruhiger Haltung, oft bis zum Rand angeschnitten. Bilder tragen das Seitenbild fast allein, auf einer Seite sind es dutzende. Keine Rahmen, keine Rundungen, keine Overlays außer einer leichten Abdunklung für Text. Im Beispiel: Flächen aus CSS in Sand-, Stein- und Grautönen.

## Animation
Kaum vorhanden. Höchstens Einblenden (0.4s ease) und Bildwechsel per Überblendung, Hover mit minimalem Deckkraftwechsel (0.8). Kein Parallax, kein Springen, keine Skalierungen.

## Tonfall
Knapp, höflich, förmlich. Kurze Bezeichnungen statt Sätzen, Sie-Ansprache, Service-Hinweise sachlich (Versand, Rückgabe). Keine Ausrufezeichen, keine Rabattsprache.

## Mach
- Ausschließlich Schwarz, Weiß und ein helles Grau
- Antiqua nur für Schlagzeilen, Sans in 12px für den Rest
- Alles eckig, flach, ohne Schatten
- Bilder groß, bis an den Rand, Text sparsam darüber
- Laufweite 0.5px auf allem
- Versalien für Navigation und Rubriken
- Knöpfe schmal gestapelt statt nebeneinander

## Mach nicht
- Keine Akzentfarben, keine bunten Etiketten
- Keine fetten Schriftschnitte (nur 400)
- Keine abgerundeten Ecken, keine Schatten, keine Kartenrahmen
- Keine großen Sans-Schlagzeilen
- Keine Emoji, keine gefüllten Icon-Kreise
- Keine Mehrfach-Dreierkacheln mit Textblöcken und Pfeilen

## Typische KI-Fehler in diesem Stil
- Fette Überschriften und Knöpfe, obwohl im Stil alles Gewicht 400 ist
- Schrift zu groß: 12px-Basis wird auf 16 bis 18px aufgeblasen, dadurch geht die Zurückhaltung verloren
- Goldton oder Akzentfarbe "für Luxus" ergänzt, statt rein Schwarz-Weiß
- Karten mit Rahmen, Radius oder Schatten statt freier Bilder mit zwei Textzeilen
- Hero als Text-links-Bild-rechts mit großem Verkaufsslogan, statt zwei gleich großer Bildhälften
- Laufweite vergessen, dadurch wirkt die Sans zu dicht
