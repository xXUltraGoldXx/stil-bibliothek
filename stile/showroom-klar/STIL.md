# Stil: Showroom klar

## Kurzbeschreibung und Stimmung
Hochwertig, ruhig und präzise. Der Einstieg ist eine schwarze Bühne mit einem dunkel gegradeten Vollflächenbild und einer feinen, hellen Serifen-Headline. Darunter folgen weiße und sehr helle graue Flächen mit viel Luft, dunkelgrauem Text und genau einer Akzentfarbe: einem klaren Blau, das fast nur auf Pillen-Knöpfen und Links vorkommt. Das Gefühl ist das eines modernen Showrooms: wenig Dekoration, große Motive, jede Aussage hat Raum. Die Seite wechselt in Blöcken zwischen Schwarz und Weiß, es gibt keine Mischtöne und keine Verläufe außer dem Auslaufen des Bildes ins Schwarz.

## Farbpalette
- Bühne: Schwarz `#000000` für Kopfzeile, Hero, Medienblöcke und Fußbereich; Karten auf Schwarz `#141414`
- Fläche hell: Weiß `#ffffff` als Hauptgrund, Hellgrau `#f8f8f8` für abgesetzte Bänder und Karten auf Weiß
- Text auf Weiß: Dunkelgrau `#333333` (Standard), `#262626` für starke Stellen, `#696969` für Nebentext, `#9f9f9f` für Hinweise
- Text auf Schwarz: Weiß `#ffffff` für Headlines, `#e8e8e8` für Fließtext und Knopftext
- Akzent Blau `#0078d6` (dunkel `#004f8d`), nur für Primärknöpfe, Fokusrahmen, Links und kleine Aktivmarker
- Linien: `#bbbbbb` oder `rgba(0,0,0,.1)` auf Hell, `#333333` auf Dunkel
- Bildauslauf: Verlauf von transparent nach `#000000`, Deckung ab 72 Prozent voll, damit Bild und schwarzer Grund ohne Kante ineinander übergehen

## Typografie
- Headlines (H1, H2): Cormorant Garamond, Gewicht 400 bis 500, Zeilenhöhe 1.125, Laufweite normal, Groß- und Kleinschreibung, nie Versalien
- Fließtext, Knöpfe, Navigation: Source Sans 3, Gewicht 400, Laufweite 0.2px, Zeilenhöhe 1.55
- Kleine Überschriften (H3) und Links: Source Sans 3, Gewicht 700
- Größen Desktop: H1 4rem (64px), H2 3rem (48px), H3 1.5rem (24px), Lead 1.125rem (18px), Text 1rem, Klein 0.875rem, Mini 0.75rem
- Größen Mobil: H1 2.5rem, H2 2rem, H3 1.25rem, Text 1rem, Links 0.875rem
- Nur Gewichte 400 und 700. Die Serife trägt die Emotion, die Sans die Information
- Cormorant Garamond und Source Sans 3 (Google Fonts) passen in Charakter und Proportion zusammen

## Abstände und Raster
- Leiter in px: 4, 8, 12, 16, 24, 32, 48, 64, 96. Der 8er-Schritt dominiert
- Sektionen vertikal 4 bis 6rem, mobil 3rem
- Inhaltsbreite 1160px, Seitenrand 16px mobil, 32px ab Tablet; der Hero-Text sitzt linksbündig auf Höhe des Inhaltsrands
- Textspalten maximal 435 bis 560px, Absatz folgt der Headline mit 24 bis 32px Abstand
- Kartenraster 3 Spalten (2 auf Tablet, 1 mobil), Lücke 24px; Knopfreihen mit 8 bis 12px Lücke

## Layout-Muster
- Kopfzeile: schwarz, 84px hoch, dreiteilig: links Menü-Symbol, Mitte Wortmarke, rechts Symbole und Anmelde-Link
- Hero: Vollbreite, Bild dunkel gegradet, links schmale Textspalte mit H1 in drei kurzen Zeilen, Lead, zwei Pillen. Unten läuft das Bild per Verlauf ins Schwarz
- Danach wechseln Blöcke: weiß mit Kartenreihe, schwarzer Medienblock mit großem Motiv und Text, hellgraues Band mit Kennzahlen, Abschluss mit einzelnem Aufruf
- Hinweisfenster (Cookies, Dialoge): weiße Fläche, Radius 12px, am unteren Rand mittig, Serifen-Titel, rechtsbündige Knopfreihe, darunter unterstrichene Textlinks

## Komponenten
- Primärknopf: Pille (Radius 9999px), Fläche `#0078d6`, Text weiß, Source Sans 3 Gewicht 700, Höhe 40 bis 48px, Innenabstand 0 32px; Hover: Fläche `#004f8d`
- Sekundärknopf auf Schwarz: Pille, Fläche `#000000`, 1px-Rand `#e8e8e8`, Text `#e8e8e8`; auf Weiß: Rand `#333333`, Text `#333333`
- Mobil: Knöpfe volle Breite, 12px Abstand untereinander
- Karten: Radius 12px, Fläche `#f8f8f8` auf Weiß oder `#141414` auf Schwarz, Schatten `0 0 2px rgba(0,0,0,.1), 0 2px 4px rgba(0,0,0,.1)`, kein Rand
- Links: Gewicht 700, 2px Unterstreichung in Textfarbe mit 2px Abstand, bei Hover Farbe `#0078d6`
- Eingabefelder: transparent mit 1px-Linie `#9f9f9f`, Radius 4px, Fokus `#0078d6`
- Runde Symbolflächen: Radius 50%, 32px, Fläche `#333333`

## Bildsprache
Großformatige, dunkel gegradete Motive mit Tiefe: Nahaufnahmen von Gesichtern, Materialien und Produkten, filmisches Licht, viel Schwarz im Bild, der Fokus sitzt rechts, damit links Text steht. Bilder laufen randlos über die volle Breite und werden unten ins Schwarz ausgeblendet. Keine hellen Stock-Fotos, keine Collagen, keine Rahmen. Im Beispiel dienen CSS-Verläufe in Grau und Schwarz als Platzhalter.

## Animation
Zurückhaltend. Einblenden und leichtes Anheben um 16px in 0.6s mit Ease-out, Hover auf Knöpfen und Links 200ms nur als Farbwechsel. Bilder dürfen langsam um etwa 3 Prozent skalieren. Kein Hüpfen, kein Wackeln, kein Parallax-Übertreiben. `prefers-reduced-motion` respektieren.

## Tonfall
Souverän, sachlich, in Sie-Form. Kurze, ruhige Sätze, Aussagen mit Punkt am Ende, wenige Adjektive, keine Ausrufezeichen. Knopftexte sind Verben: "Mehr erfahren", "Termin vereinbaren".

## Mach
- Schwarze Bühne für den Einstieg, weiße Flächen für Inhalt, Blöcke klar trennen
- Headlines in feiner Serife, Gewicht 400, Fließtext in Sans mit Laufweite 0.2px
- Blau `#0078d6` nur für Handlungen, höchstens ein bis zwei blaue Elemente pro Bildschirm
- Pillen für Knöpfe, 12px Radius für Karten und Dialoge
- Bild unten per Verlauf ins Schwarz auslaufen lassen
- Text mindestens 4.5:1 Kontrast, Weiß auf Schwarz, `#333333` auf Weiß

## Mach nicht
- Keine zweite Akzentfarbe, keine bunten Verläufe, kein Blau als Flächenfarbe für ganze Blöcke
- Keine fetten Serifen und keine Versalien-Headlines
- Keine harten oder farbigen Schatten, keine Rahmen um Bilder
- Keine eckigen Primärknöpfe, keine Emoji, keine Ausrufezeichen
- Kein Grau auf Schwarz unter `#9f9f9f` für lesbaren Text

## Typische KI-Fehler in diesem Stil
- Sans-Headlines statt feiner Serife, dadurch geht der Premium-Charakter verloren
- Blau zu großflächig oder mit Verlauf eingesetzt, statt nur an Knöpfen und Links
- Hero hell und mit Kartenbild statt schwarz, vollflächig und filmisch
- Zu enge Abstände: der Stil lebt von 4 bis 6rem Luft zwischen Blöcken
- Karten mit Rand und starkem Schatten statt flächig mit minimalem Doppelschatten
- Bildkante sichtbar, weil der Auslauf ins Schwarz fehlt
- Fließtext ohne Laufweite und in Schwarz `#000000` statt `#333333`
