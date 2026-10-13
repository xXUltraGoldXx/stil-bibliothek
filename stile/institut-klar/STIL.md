# Stil: Institut klar

## Kurzbeschreibung und Stimmung
Eine Informationsseite einer großen öffentlichen Einrichtung: sachlich, vertrauenswürdig, gut lesbar. Tiefes Marineblau gibt Struktur (Leisten, Navigation, Titel), kühles Hellgrau und Weiß tragen den Inhalt. Ein großes Foto mit Titel in einem dunkelblauen Balken eröffnet die Seite, darunter folgen Nachrichten-Karten und Themenlisten. Gefühl: Verlässlichkeit, Zugänglichkeit, Dringlichkeit ohne Alarm.

## Farbpalette
- Seitenhintergrund `#f6f7f9`, Flächen weiß `#ffffff`, zweite Fläche `#edeff3`, Linien `#c9cfdb`
- Navigationsleiste `#0c2b64`, obere Leiste und Karten auf Blau `#274375`, tiefes Marine `#00205c` für Überschriften, Titel-Balken und Knöpfe
- H2 in `#092862`, Fließtext `#3c4245`
- Aktionsblau `#0078d4` (Hover), `#006cbe` (Ruhe), `#005ca3` (aktiv) für Links und Fokus
- Ein warmes Gelb `#f5ac25` ausschließlich für den einen Spenden-/Haupt-Aufruf, Text darauf `#000000`
- Titel-Balken: `rgba(0,32,92,0.85)` mit weißer Schrift
- Keine Verläufe außer dezenter Bildabdunklung, keine bunten Zweitfarben

## Typografie
- Eine Familie: Noto Sans (Google Fonts), Gewichte 400 und 700, Rückfall Arial
- Hero-Titel 50px (3.125rem), Gewicht 700, Zeilenhöhe 80px im Balken; mobil 25px
- H2 26px (1.625rem), Gewicht 700, Farbe `#092862`; mobil 20px
- H3/Kartentitel 18px (1.125rem), Gewicht 700, Zeilenhöhe 1.5
- Fließtext 16px, Zeilenhöhe 24px, Gewicht 400; Meta 14px mit Zeilenhöhe 21px
- Navigation 15px, Gewicht 700, weiß auf Marine
- Laufweite normal, keine Versalien, keine Kursive

## Abstände und Raster
- Maximalbreite 1280px, seitlicher Rand 30px (mobil 15px)
- Kartenraster 3 Spalten ab 900px, 2 ab 600px, sonst 1 Spalte, Lücke 30px
- Innenabstände: 4, 8, 15, 24, 30, 40px
- Abschnitte trennt großzügiger Weißraum von etwa 60px oben und unten
- Fließtext höchstens 70 Zeichen breit

## Layout-Muster
- Zwei Leisten übereinander: schmale Hilfsleiste `#274375` (Region, Suche, Sprache), dann weiße Kopfzeile mit Logo links und gelbem Aufruf rechts, dann Marine-Navigation mit Pfeil-Indikatoren
- Hero: vollbreites Foto, Titel horizontal mittig im halbtransparenten Marine-Balken, darunter ein kompakter Knopf "Weiterlesen"
- Abschnittskopf: H2 links, Link "Alle →" rechts, darunter dünne Linie
- Nachrichten-Karten: Bild oben, darunter Datum, Kategorie und Titel in fetter Schrift
- Dunkle Datenzone in Marine mit großen Kennzahlen, danach Themen-Liste in Weiß

## Komponenten
- Haupt-Knopf: Marine `#00205c`, weiße Schrift, Radius 4px, Padding 8px 30px, keine Schatten
- Aufruf-Knopf: Gelb `#f5ac25`, schwarze fette Schrift, Radius 4px
- Navigation: weiß, fett, Pfeil nach unten als kleiner Winkel; Hover mit Unterstreichung 2px
- Karten: weiß, Radius 4px oben, 1px Linie `#c9cfdb`, keine Schatten
- Fokus: 2px Umriss in `#64789c` plus 2px Abstand; Kontrast mindestens 4.5:1
- Links: Marine, fett, unterstrichen bei Hover

## Bildsprache
Dokumentarische, echte Menschenfotos in warmen, natürlichen Farben, nah und mit Blickkontakt, nie gestellt oder gefiltert. Seitenverhältnis 16:9 für Karten, Hero etwa 2.5:1 auf Desktop. Eine kleine Credit-Zeile als eingeklapptes Feld unten rechts im Bild. Im Beispiel: CSS-Flächen in Blau- und Grautönen als Platzhalter.

## Animation
Kaum vorhanden. Farbübergänge bei Hover 0.15s, Aufklappen von Menüs 0.2s. Kein Parallax, keine Einblend-Effekte, `prefers-reduced-motion` respektieren.

## Tonfall
Klar, neutral, erklärend. Kurze Sätze, aktive Verben, Zahlen und Fakten vor Adjektiven. Überschriften nennen Thema und Aussage, kein Marketing-Jargon, keine Ausrufezeichen.

## Mach
- Marine für Struktur, Weiß und Hellgrau für Inhalt
- Genau einen gelben Aufruf pro Seite
- Titel im halbtransparenten Balken über dem Foto
- Radius 4px durchgängig, Schatten weglassen
- Fette Schrift für Navigation, Titel und Links, Regular für Fließtext
- Hohe Kontraste und sichtbare Fokuszustände

## Mach nicht
- Keine Verläufe, Glas- oder Neon-Effekte
- Keine zweite Akzentfarbe neben Gelb und Aktionsblau
- Keine Serifen, keine Versalien-Schlagzeilen
- Keine runden Pillen-Knöpfe, keine Radien über 4px
- Keine Schatten, keine schwebenden Karten
- Keine Stock-Illustrationen mit Verlaufsfiguren

## Typische KI-Fehler in diesem Stil
- Marineblau durch ein helles Tech-Blau ersetzt, wodurch die Würde verloren geht
- Gelb mehrfach verwendet, statt nur für einen Aufruf
- Hero-Titel ohne Balken direkt aufs Foto gelegt und dadurch schlecht lesbar
- Karten mit großen Radien und Schatten statt flacher 4px-Karten mit Linie
- Zu viele Schriftgewichte und Schriftfamilien statt Noto Sans 400/700
- Navigation zentriert und klein statt linksbündig, fett und breit
- Werbesprache statt sachlicher, faktenbasierter Texte
