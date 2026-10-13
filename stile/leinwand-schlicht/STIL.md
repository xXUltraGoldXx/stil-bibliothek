# Stil: Leinwand schlicht

## Kurzbeschreibung und Stimmung
Eine weiße Leinwand, auf der das Produkt die einzige Farbe liefert. Die Oberfläche ist strikt schwarzweiß: leichte, eng gesetzte Grotesk-Schlagzeilen, kleine Mono-Versalien-Labels, große Weißräume und schwarze Flächen als Kontrast (Knöpfe, Fußbereich, Hinweisbox). Gefühl: souverän, werkzeughaft, ruhig, ohne Dekoration. Der Aufbau ist eine lange Folge klar getrennter Abschnitte, jeder mit einer knappen Aussage und einer Bildbühne.

## Farbpalette
- Fläche: Weiß `#ffffff` (ca. 88 % der Fläche), Schwarz `#000000` für Fußbereich, Primärknöpfe und Hinweisboxen
- Text: Schwarz `#000000`; sekundär Schwarz mit 54 % Deckkraft (`rgba(0,0,0,.54)`) für Labels und Nebentext; auf Schwarz Weiß und `rgba(255,255,255,.6)`
- Linien und Rahmen: `rgba(0,0,0,.16)` 1px; auf Schwarz `rgba(255,255,255,.16)`
- Hover-Fläche für helle Elemente: `rgba(0,0,0,.04)`
- Akzentfarben gibt es nur INNERHALB der Bildplatzhalter und Produktmotive: Violett `#a98bf8`, Dunkelviolett `#3b2d63`, Gelb `#ffff5c`, Blau `#00b6ff`, Salbeigrün `#7fb58f`. Nie für Text, Knöpfe oder Rahmen der Oberfläche
- Keine Verläufe auf der Oberfläche, keine getönten Hintergründe

## Typografie
- Hauptschrift: Inter Tight (Google Fonts), variable Gewichte, Standard 400, leichter Fließtext 330
- Mono-Schrift: DM Mono (Google Fonts), nur für Labels
- Display: 5.5rem bis 3.5rem (clamp), Gewicht 400, Zeilenhöhe 1, Laufweite -0.078rem (ca. -1.25px)
- H2: 2.75rem (Mobil 2rem), Gewicht 400, Zeilenhöhe 1.1, Laufweite -0.04rem
- H3 und Karten-Titel: 1.875rem bzw. 1.375rem, Gewicht 400, Zeilenhöhe 1.2
- Fließtext: 1.125rem, Gewicht 330, Zeilenhöhe 1.4; Mobil 0.875rem bis 1rem
- Navigation und Knöpfe: 1rem, Gewicht 400, Laufweite -0.01em
- Labels: DM Mono 0.875rem (Mobil 0.75rem), Versalien, Laufweite 0.03rem, Farbe 54 % Schwarz
- Nie Fettschnitte über 500; Hierarchie entsteht durch Größe und Weißraum

## Abstände und Raster
- Basiseinheit 0.25rem; Stufen 0.25, 0.5, 0.75, 1, 1.5, 2, 2.5, 3.5, 4, 5, 7.5rem
- Raster: 4 Spalten mobil, 12 ab Desktop, Außenrand 1rem mobil und 2.5rem Desktop, Lücke 1rem bis 1.5rem, maximale Inhaltsbreite 95rem (1520px)
- Abschnitte haben 5rem Innenabstand oben und unten (Desktop), 2.5rem mobil; der Fußbereich 7.5rem Desktop, 5rem mobil
- Innenabstand Knöpfe: 0.75rem 1.5rem; kleine Chips 0.375rem 0.75rem
- Fließtext höchstens ca. 45ch breit; Schlagzeilen dürfen schmal umbrechen (vier kurze Zeilen sind erwünscht)

## Layout-Muster
- Kopfzeile: weiß, 78px hoch, unten 1px Linie `rgba(0,0,0,.16)`; links Logo-Platzhalter und Menüpunkte mit kleinem Pfeil, rechts Textlink, heller Knopf mit Rahmen, schwarzer Hauptknopf. Mobil: nur Logo, Hauptknopf und Menüsymbol
- Hero: links schmale Schlagzeile über vier Zeilen, mittig eine große überlappende Bildbühne aus mehreren Flächen, rechts ein großer schwarzer Knopf. Mobil: Schlagzeile oben, Bühne darunter
- Folgeabschnitte: Mono-Label, große Aussage, kurzer Text, danach eine breite Bildbühne oder ein Raster aus Produktkarten
- Karten: Bildfläche mit Radius 1.5rem, darunter Titel und eine Zeile Beschreibung, keine sichtbare Kartenbox
- Raster aus vielen kleinen Logo-Platzhaltern (6 bis 8 Spalten) als Vertrauensblock
- Abschluss: voller schwarzer Fußbereich mit Weiß-Text, mehrspaltige Linklisten, Mono-Labels als Spaltenköpfe
- Hinweisbox (Cookies): schwarz, Radius 1rem, unten rechts fixiert, mit zwei weißen Knöpfen

## Komponenten
- Primärknopf: Schwarz `#000`, Text Weiß, Radius 0.5rem (klein) oder 1rem (groß, 5.25rem hoher Hero-Knopf mit 1.75rem Text), kein Schatten
- Sekundärknopf: Weiß, 1px Rahmen `rgba(0,0,0,.16)`, Text Schwarz, Radius 0.5rem
- Knopf auf Schwarz: Weiß mit Schwarztext, Radius 0.5rem, volle Breite mobil
- Textlink: ohne Unterstreichung in der Navigation, im Fließtext unterstrichen
- Chips und Tabs: Pillenform (9999px), 1px Rand, aktiv Schwarz gefüllt
- Rundungen: 2px (Mikro), 4px, 8px (Knöpfe), 16px (Boxen), 24px (Bildkarten), 9999px (Pillen), 50% (Punkte)
- Schatten: praktisch keine; höchstens ein 1px Innenring `0 0 0 1px rgba(0,0,0,.16) inset`. Für schwebende Elemente sehr weich `0 0.25rem 2rem rgba(0,0,0,.1)`
- Fokusring: 2px Schwarz mit 2px Abstand

## Bildsprache
Das Produkt ist die Bühne: mehrere farbige Flächen (Violett, Dunkelviolett, Salbeigrün) übereinander gestapelt, mit eingebetteten Oberflächen-Ausschnitten, Raster-Mustern aus gelben Punkten und kleinen Bedienelementen. Die Motive sind farbig und gesättigt, der Rahmen drumherum bleibt weiß. Im Beispiel: Flächen und Kreise aus CSS und SVG in den Akzentfarben als Platzhalter, ohne Fotos.

## Animation
Zurückhaltend. Hover auf Knöpfen: Hintergrund wechselt in 0.15s (hell: `rgba(0,0,0,.04)`, schwarz: `#222`). Bildbühnen dürfen beim Einblenden 0.4s hochgleiten (translateY 1rem) und einblenden. Menü-Pfeile drehen sich um 180° in 0.2s. Keine Parallax-Effekte, keine Dauerschleifen auf der Oberfläche.

## Tonfall
Kurz, sachlich, einladend. Aussagesätze mit wenigen Wörtern, Verben für Knöpfe ("Loslegen", "Vertrieb kontaktieren"). Keine Superlative, keine Ausrufezeichen, direkte Ansprache. Labels benennen nur die Kategorie.

## Mach
- Eine Schrift in Gewicht 400 und leichter, Hierarchie über Größe (88/56/44/30/18/16px) und enge Laufweite
- Mono-Versalien-Labels (54 % Schwarz) über jeder Abschnittsüberschrift
- Schwarz als einzige Oberflächenfarbe neben Weiß: Knöpfe, Hinweisbox, Fußbereich
- Farbe nur in den Produktbühnen, diese großzügig und überlappend
- 5rem Abschnittsabstand, viel Weißraum, schmale Textspalten
- Pillen für Chips, 0.5rem Radius für Knöpfe, 1.5rem für Bildkarten

## Mach nicht
- Keine farbigen Knöpfe, Links oder Überschriften
- Keine Fettschnitte, keine Serifen, keine Kursive
- Keine Verläufe, keine dicken Schatten, keine Glaseffekte
- Keine grauen Sektionshintergründe als Rhythmus; Wechsel nur Weiß zu Schwarz
- Keine Emoji, keine Icon-Kreise in Farbe
- Keine zentrierten Dreier-Kachelreihen mit Icons als Standardlösung

## Typische KI-Fehler in diesem Stil
- Fettes Gewicht (600 bis 700) für Schlagzeilen statt 400 mit enger Laufweite; dadurch wirkt es wie ein Standard-SaaS
- Eine bunte Primärfarbe für Knöpfe und Links einführen, obwohl die Oberfläche schwarzweiß bleiben muss
- Mono-Labels vergessen oder in Fettschrift und Farbe setzen statt in 54 % Schwarz und Versalien
- Bildbühnen als einzelnes flaches Rechteck mit Schlagschatten umsetzen statt als überlappende Flächen ohne Schatten
- Grau hinterlegte Wechselabschnitte statt Weiß und gelegentlichem vollem Schwarz
- Zu kleine Abschnittsabstände (unter 4rem) und zentrierte Schlagzeilen statt linksbündiger, schmal umbrochener Aussage
