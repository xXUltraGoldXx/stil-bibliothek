# Stil: Amtsblau schlicht

## Kurzbeschreibung und Stimmung
Öffentlicher Dienst im Browser. Eine kräftige blaue Kopffläche, direkt darunter eine große Schlagzeile und ein Suchfeld, danach weiße Seite mit schwarzem Text und unterstrichenen blauen Links. Der Stil dient dem schnellen Finden und Erledigen. Er wirkt ruhig, vertrauenswürdig und unauffällig, ohne Dekor. Eckige Flächen, Gewicht 400 und 700, dazu ein gelber Fokusring als einziges auffälliges Signal.

## Farbpalette
- Marke und Kopffläche: Blau `#2575b3`
- Text: Schwarz `#0b0c0c`, sekundärer Text `#505a5f`
- Seitenhintergrund außen und Fußbereich: `#f4f8fb`, Inhaltsfläche Weiß `#ffffff`
- Links: `#1f6aa8`, Hover `#0f385c`, besucht `#54319f`, aktiv `#0b0c0c`
- Hauptknopf Grün `#1a8057` (Hover `#0a7242`), Knopfkante `#083d29`
- Fokus: Gelb `#ffdd00` mit schwarzer Unterkante `#0b0c0c`
- Fehler `#ca3535`, Linien `#cecece`, helle Blauflächen `#d2e2f1`, Rahmen für Flächen `#8eb8dc`
- Keine Verläufe, keine Transparenzspiele, keine weiteren Akzentfarben

## Typografie
- Eine einzige Schriftfamilie, serifenlos: Noto Sans (Google Fonts), Rückfall Arial
- Gewichte nur 400 und 700
- Fließtext 1.1875rem (19px), Zeilenhöhe 1.316 (25px), Farbe `#0b0c0c`
- H1 3.4375rem (55px), Zeilenhöhe 1.2, fett, weiß auf Blau. Mobil 2.5rem
- H2 1.5rem (24px), Zeilenhöhe 1.25, fett. Mobil 1.3125rem
- Navigation und Kleingedrucktes 1rem
- Laufweite normal, keine Versalien, keine Kursive als Gestaltungsmittel
- Textspalte höchstens 630px (etwa 66 Zeichen)

## Abstände und Raster
- Inhaltsbreite 960px, zentriert, seitlich 15px Rand mobil, 30px ab Tablet
- 12 Spalten, Lücke 30px. Kleine Gruppen mit 15px Lücke
- Abstandsskala: 5, 10, 15, 20, 30, 40, 60px
- Hero-Fläche: oben 10px nach der Kopfleiste, unten 40px Innenabstand
- Haltepunkte: 40.0625rem (Tablet), 48.0625rem (Desktop)
- Fußbereich: 40px oben, 25px unten

## Layout-Muster
- Oben ein Hinweisbalken auf `#f4f8fb` mit Titel, zwei Sätzen und zwei Knöpfen nebeneinander
- Kopfleiste vollflächig Blau 62px hoch mit Wortmarke links, Menü und Suche rechts
- Hero: linksbündige weiße Schlagzeile in der linken Hälfte, darunter Beschriftung "Suche" und ein breites Feld mit Knopf an der Kante
- Danach eine einspaltige Liste oder dreispaltiges Raster aus Textlinks mit kleiner Bildmarke links, durch 1px Linien getrennt
- Abschnitte mit H2, kurzem Satz und Linkliste. Eine 4px dicke Blaulinie links oder oben markiert Hinweise
- Fuß: viele Linkspalten auf hellem Grund, oben eine Linie

## Komponenten
- Hauptknopf: Grün `#1a8057`, weißer Text 1.1875rem, Rand 2px transparent, Innenabstand 8px 10px 7px, Radius 0, Schatten `0 2px 0 #083d29`. Beim Klicken 2px nach unten
- Zweitknopf: grau `#f3f2f1` mit Schatten `0 2px 0 #929191`
- Suchfeld: Weiß, 2px Rand `#0b0c0c`, Höhe 50px, Radius 0, Knopf in `#d2e2f1` bündig angesetzt
- Eingabefelder: 2px schwarzer Rand, Innenabstand 6px, Beschriftung darüber fett
- Links: immer unterstrichen, Unterstreichung 1px, Hover dunkler und dicker
- Fokus: Hintergrund Gelb `#ffdd00`, schwarzer Text, 3px schwarze Unterkante, keine Fokus-Entfernung
- Hinweisbox: 4px Blaurand links, Weiß, Innenabstand 20px
- Radien überall 0, Schatten nur als Knopfkante

## Bildsprache
Kaum Fotos. Kleine, flache Symbole in Blau oder Weiß, 24px bis 80px, mit klarer Kontur. Bildplatzhalter in `#b1b4b6` oder `#d2e2f1`, immer mit Textalternative. Keine dekorativen Großbilder, keine Illustrationen mit Verläufen.

## Animation
Praktisch keine. Dauer 0s als Grundwert. Erlaubt sind nur sofortige Zustandswechsel bei Hover, Fokus und Klick, dazu das Aufklappen von Menüs ohne Übergang. Bewegung hält niemanden vom Ziel ab.

## Tonfall
Kurze, direkte Sätze in einfacher Sprache. Verben am Anfang bei Handlungen ("Antrag stellen", "Termin prüfen"). Keine Werbung, keine Ausrufezeichen, keine Floskeln. Überschriften sagen, was auf der Seite zu tun ist.

## Mach
- Eine Aktion pro Bildschirmbereich, ein einziger grüner Hauptknopf
- Starken Kontrast halten, mindestens 4.5:1, Text auf Blau nur Weiß
- Alle Links unterstrichen, Fokus deutlich gelb
- Linke Ausrichtung, schmale Textspalte, viel Weiß um Textblöcke
- Listen und Linien statt Karten

## Mach nicht
- Keine Rundungen, keine weichen Schatten, keine Verläufe
- Keine Animationen, Karussells oder automatisch wechselnde Inhalte
- Keine zentrierten Hero-Texte, keine Kachelreihen mit Icon-Kreisen
- Keine zweite Akzentfarbe neben Blau und Grün
- Keine Link-Entfernung der Unterstreichung, keine grauen Platzhaltertexte als Beschriftung

## Typische KI-Fehler in diesem Stil
- Weich gerundete Knöpfe und Karten mit Schatten statt scharfer Kanten
- Hero zentriert und mit Verlauf, statt linksbündig auf glattem Blau
- Fokusring weggelassen oder durch einen dünnen blauen Rahmen ersetzt
- Schrift zu klein (unter 1.125rem) und zu hell grau gesetzt
- Mehrere bunte Knöpfe nebeneinander statt eines grünen Hauptknopfs
- Links ohne Unterstreichung, nur in Blau eingefärbt
