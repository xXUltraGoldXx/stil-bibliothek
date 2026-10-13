# Stil: Portal sachlich

## Kurzbeschreibung und Stimmung
Eine zentrierte Einstiegsseite, die wie ein nüchternes Verzeichnis wirkt: weiße Fläche, viel Leerraum, eine schmale Mittelspalte, darunter ein hellgraues Linienraster mit Verweisen. Es gibt nur eine Akzentfarbe, Blau `#3366cc`, und die gehört ausschließlich dem, was klickbar ist. Gefühl: nüchtern, neutral, vertrauenswürdig, dienstbar. Das Design verkauft nichts, es führt zum Ziel (Suche, Sprachwahl, Themenverweise).

## Farbpalette
- Fläche `#ffffff`, zweite Fläche `#f8f9fa` für Infokästen und Fußbereich
- Text primär `#202122`, sekundär `#54595d` (Beschreibungen, Zählungen), Platzhalter `#72777d`
- Akzent und Links `#3366cc`, Hover `#3056a9`, aktiv `#233566`, besucht `#6a60b0`
- Linien und Rahmen `#a2a9b1`, Haarlinien in `#c8ccd1`
- Fehler `#bf3c2c`, Erfolg `#177860` nur für Rückmeldungen
- Keine Verläufe, keine Schatten, keine weiteren Akzentfarben

## Typografie
- Wortmarke und H1: Serife, 2rem, Gewicht 700, Zeilenhöhe 1.03, Kapitälchen-Anmutung möglich
- Alles andere: Systemschrift (-apple-system, Segoe UI, Roboto, Helvetica, Arial)
- Basis 14px (0.875rem), Zeilenhöhe 1.5; Meta und Zählungen 0.8125rem (13px) in `#54595d`
- Verweistitel 1rem, Gewicht 700, Blau; Abschnittsüberschriften 0.8125rem, Gewicht 700, Text `#202122`
- Nur zwei Gewichte: 400 und 700. Laufweite normal, keine Versalien
- Absätze in Einführungen 1.0625rem (17px), Zeilenhöhe 1.55

## Abstände und Raster
- Mittelspalte höchstens 500px für Suche und Texte, Verweisgruppen bis 960px
- Basiseinheit 0.8125rem (13px); gängige Abstände 0.5rem, 0.8rem, 1rem, 1.6rem, 2.6rem, 3.75rem
- Innenabstand Knöpfe 0.5rem 1rem, Infokästen 0.8rem 1rem
- Dreispaltiges Raster für Verweise, Lücke 1.6rem; unter 700px eine Spalte
- Radius überall 2px, nie mehr
- Trennung durch 1px-Linien in `#a2a9b1`, nicht durch Flächenwechsel allein

## Layout-Muster
- Kopf: zentrierte Serifen-Wortmarke, darunter ein Einzeiler als Beschreibung
- Mitte: Ring aus Verweisen links und rechts (je Titel in Blau, darunter Zählung in Grau), in der Mitte ein rundes Emblem; die Verweise sind jeweils zur Mitte hin ausgerichtet
- Darunter die Suchzeile (max. 500px) und ein Nebenknopf mit Haarlinien links und rechts
- Waagerechte Linie über die volle Breite, dann ein Fußbereich: Textblock links, rechts ein Raster aus Icon, Titel und Einzeiler
- Mobil: Ring wird zweispaltige Liste, Emblem entfällt oder steht darüber

## Komponenten
- Suchfeld: 1px Rahmen `#3366cc`, Radius 2px links, daran bündig ein blauer Knopf mit Radius 0 2px 2px 0; Feldhöhe etwa 2.75rem
- Primärknopf: Fläche `#3366cc`, Text weiß, Gewicht 700, 1rem, Rahmen 1px gleiche Farbe, Padding 0.5rem 1rem
- Sekundärknopf: weiße Fläche, Rahmen 1px `#a2a9b1`, Text Blau, Gewicht 700, Radius 2px
- Links: Blau ohne Unterstreichung, Hover unterstrichen und `#3056a9`
- Infokasten: Fläche `#f8f9fa`, Radius 2px, kein Rahmen, Titel blau fett, Text grau
- Fokus: 1px innerer Ring in `#3366cc` (`box-shadow: inset 0 0 0 1px`), sonst keine Schatten

## Bildsprache
Ein einziges, ruhiges Emblem als Mittelpunkt, kleine flache Piktogramme je Verweis (ca. 2.5rem, einfache Formen, eigene Farben je Eintrag erlaubt, aber klein). Keine Fotos, keine Hero-Bilder. Im Beispiel: Kreise und Formen aus CSS und Inline-SVG als Platzhalter.

## Animation
Praktisch keine. Farbwechsel bei Hover in 0.15s, Fokusring sofort. Keine Einblendungen, keine Parallax-Effekte, keine Bewegung beim Laden.

## Tonfall
Sachlich, kurz, neutral. Beschreibungen als Nominalgruppen („Freie Bildersammlung“), Zählungen mit Zahl und Einheit. Keine Ausrufezeichen, keine Werbeversprechen, direkte Ansprache nur dort, wo gehandelt wird.

## Mach
- Genau eine Akzentfarbe (`#3366cc`) nur für Klickbares
- Serife nur für Wortmarke und H1, Rest Systemschrift
- Zentrierte schmale Mittelspalte mit viel Weiß
- Titel plus Einzeiler plus Zählung als Grundbaustein jedes Verweises
- Haarlinien `#a2a9b1` und 2px Radius konsequent

## Mach nicht
- Keine Schatten, keine Verläufe, keine großen Radien
- Keine Hero-Fotos, keine großen Werbeflächen, keine Animationen
- Keine zweite Akzentfarbe, keine Versalien-Überschriften
- Keine Gewichte außer 400 und 700
- Keine Kachelkarten mit Rahmen und Hintergrund für jeden Verweis

## Typische KI-Fehler in diesem Stil
- Blau wird zur Flächenfarbe für Banner und Hero, obwohl es nur Verweisen und dem einen Knopf zusteht
- Karten mit Schatten und 12px-Radius statt flacher Verweise mit Haarlinien
- Serife auch für Fließtext und Verweise, wodurch die Systemschrift-Nüchternheit fehlt
- Suchfeld und Knopf getrennt mit Abstand statt bündig verbunden
- Zu große Typografie: H1 über 2.5rem und Basisschrift über 16px zerstören die dichte Informationsanmutung
- Verweise ohne grauen Einzeiler oder Zählung, dadurch wirkt die Seite wie eine Marketingseite
