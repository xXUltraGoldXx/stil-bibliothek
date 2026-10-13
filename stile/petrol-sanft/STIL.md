# Stil: Petrol sanft

## Kurzbeschreibung und Stimmung
Vertrauenswürdiges Produkt-Design für Dienstleistungen, die einfach und menschlich wirken sollen. Tiefes Petrolgrün trifft auf warmes Sandweiß und reines Weiß. Große, ruhige Schlagzeilen im Normalgewicht, vollständig abgerundete Knöpfe, sehr großzügig gerundete Flächen und keinerlei Schatten. Gefühl: aufgeräumt, wach, freundlich, nie laut.

## Farbpalette
- Weiß `#ffffff` als Hauptfläche (größter Anteil)
- Sand `#ede7e0` und Sand hell `#faf8f5` für Wechselflächen, Kopfzeile und Karten
- Petrol dunkel `#003b39` für Hero, Kontrastbänder und Fußzeile
- Petrol mittel `#045e58` für Hover und Verläufe von Flächen zu Flächen (nur als Flächenwechsel, nie als Farbverlauf)
- Petrol hell `#088177` als Aktionsfarbe für Hauptknöpfe und Akzentbänder
- Text `#1b1b1b`, auf dunklem Grund `#ffffff`, Links und Betonungen in `#003b39`
- Sandlinie `rgba(198,178,159,0.25)` für feine Flächen und Rahmen, Rahmen sonst `#d9d9d9` 1px
- Keine Schatten, keine Farbverläufe, keine weitere Signalfarbe

## Typografie
- Schlagzeilen: breite Grotesk, Outfit (Google Fonts), Gewicht 400, Laufweite normal
- Fließtext und UI: DM Sans, Gewichte 400 und 500, Laufweite 0.02em (entspricht etwa 0.3px bei 16px)
- H1 5rem (Mobil 3rem), Zeilenhöhe 1.1; H2 3.6rem (Mobil 2.4rem), Zeilenhöhe 1.1
- H3 1.125rem, Gewicht 500, Zeilenhöhe 1.55
- Fließtext 1rem, Zeilenhöhe 1.5; Lead 1.25rem, Zeilenhöhe 1.5; Klein 0.875rem, Zeilenhöhe 1.4
- Nur zwei Gewichte: 400 und 500. Kein Fett, keine Versalien, kein Kursiv

## Abstände und Raster
- Maximale Breite 1464px, Seitenrand 80px Desktop, 20px Mobil
- Abschnitte vertikal 80px bis 112px Abstand (Mobil 56px)
- Innenabstände in Karten 32px, in Knöpfen 12px 24px, kleine Abstände in Schritten 4, 8, 12, 16, 24, 40, 48, 56
- Lücken zwischen Kacheln 16px bis 24px
- Raster: 12 Spalten, Zweier- und Dreierteilungen, Fließtext maximal 60 Zeichen breit
- Kopfzeile 12px 80px Innenabstand auf Sand hell

## Layout-Muster
- Hero: vollflächig Petrol dunkel (oder Bildfläche), zentrierte Schlagzeile in Weiß, ein Lead-Absatz, ein heller Pillen-Knopf
- Wechsel von Weiß, Sand und Petrol-Bändern, jeder Abschnitt eine eigene Fläche mit einer Aussage
- Leistungs-Kacheln: Sandfläche, Radius 32px, Schlagzeile klein, kurzer Text, Bildplatzhalter oben
- Zweispalter: Text links, großer abgerundeter Bildplatzhalter (Radius 40px) rechts, im Wechsel
- Zahlenband in Petrol hell mit weißen großen Ziffern
- Abschluss: Petrol dunkel mit einem Knopf, darunter kompakte Fußzeile

## Komponenten
- Hauptknopf: Pille (Radius 999px), Hintergrund `#003b39` oder `#088177`, Text Weiß, Gewicht 500, Innenabstand 12px 24px
- Zweitknopf: Pille auf Sand `#ede7e0`, Text `#003b39`
- Knopf auf dunklem Grund: Pille Weiß mit Text `#003b39`
- Karten: Radius 24px bis 40px, keine Rahmen, keine Schatten, Flächenfarbe trägt die Form
- Kleine Etiketten: Pille, Sand mit Text `#003b39`, 0.875rem
- Navigation: schlichte Textlinks 1.125rem in `#1b1b1b`, rechts Zweitknopf und Hauptknopf
- Eingabefelder: Radius 8px, 1px Rahmen `#d9d9d9`, Fokus Rahmen `#088177`
- Hinweisleisten oben abgerundet 16px 16px 0 0

## Bildsprache
Natürliche, warme Fotos von Menschen im Alltag, weiches Tageslicht, gedeckte Grüntöne. Bilder laufen vollflächig oder in großen Rundungen (24px bis 40px). Im Beispiel stehen CSS-Flächen in Petrol- und Sandtönen mit einfachen SVG-Formen als Platzhalter.

## Animation
Zurückhaltend. Knöpfe wechseln in 0.2s die Hintergrundfarbe (Petrol dunkel zu Petrol mittel). Abschnitte dürfen mit 0.4s sanft einblenden. Kein Parallax, keine springenden Effekte.

## Tonfall
Klar, direkt, persönlich. Kurze Sätze, du-Ansprache, Nutzen vor Technik. Schlagzeilen sind ganze Aussagen mit Satzzeichen, keine Schlagwort-Ketten. Freundlich, aber ohne Ausrufezeichen.

## Mach
- Weiß und Sand als Hauptflächen, Petrol dunkel als starken Kontrast
- Alle Knöpfe als volle Pillen, Karten mit 24px bis 40px Radius
- Schlagzeilen groß im Gewicht 400, Fließtext 16px mit 24px Zeilenhöhe
- Wenige, große Flächen statt vieler kleiner Elemente
- Ein Hauptknopf pro Abschnitt

## Mach nicht
- Keine Schatten, keine Verläufe, keine Glaseffekte
- Keine fetten Schlagzeilen (über Gewicht 500)
- Keine eckigen Knöpfe, keine Rahmen als Hauptform
- Keine knalligen Zusatzfarben neben Petrol und Sand
- Keine Versalien-Etiketten, keine Emoji

## Typische KI-Fehler in diesem Stil
- Schlagzeilen in Fettschrift (700) statt ruhigem Normalgewicht
- Knöpfe mit 8px Radius statt vollständiger Pille
- Schatten unter Karten, obwohl der Stil nur mit Flächenfarben arbeitet
- Kaltes Grau oder reines Schwarz statt warmem Sand und Petrolgrün
- Zu viele kleine Kacheln und Icons, statt weniger großer Flächen
- Violette oder blaue Akzente zusätzlich zu Petrol
