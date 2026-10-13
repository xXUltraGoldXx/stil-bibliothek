# Stil: Livebühne hell

## Kurzbeschreibung und Stimmung
Helle, sachliche Plattform-Oberfläche für Live-Video und Inhaltsentdeckung. Der Grund ist ein kühles Hellgrau (#f7f7f8), Text fast schwarz (#0e0e10), und ein einziges kräftiges Violett (#8b4ff2, Textvariante #5c16c5) markiert alles Interaktive. Die Seite ist dicht und funktional: kleine 14px-Schrift, viele Kacheln, schmale Seitenleiste, runde Pillen. Die Bilder sind laut, die Oberfläche bleibt leise. Gefühl: Fernsehprogramm-Übersicht, die man ständig benutzt, kein Prospekt.

## Farbpalette
- Grund: `#f7f7f8`; Flächen weiß `#ffffff`; Zwischenfläche `#efeff1`
- Neutrale Pillenfläche (Knöpfe, Tags): `rgba(173,173,184,.22)`; Rand `rgba(173,173,184,.43)`
- Text: `#0e0e10`, sekundär `#3b3b44`, gedämpft `#53535f`
- Akzent Violett `#8b4ff2` (Primärknopf), Link- und Überschriftenton `#5c16c5`, Hover `#6e30dc`
- Dunkles Band: `#330c6e` Grund, `#451093` für Knopf-Hover-Flächen, Text weiß
- Live-Signal Rot `#eb0400` (Marke) und `#e91916` (Punkt), nur für "live" und Zähler
- Medien-Overlay: Verlauf von unten `rgba(0,0,0,.8)` nach transparent, Zahlen weiß darauf

## Typografie
- Eine Familie: Inter
- Basis 0.875rem (14px), Zeilenhöhe 1.4 (19.6px); Meta 0.75rem (12px) mit 1.4
- Überschrift Abschnitt: 1.125rem (18px), Gewicht 500, Laufweite -0.01em, Farbe `#5c16c5`
- Kartentitel und Knöpfe: 0.875rem, Gewicht 600
- Gewichte nur 400, 500, 600. Keine Versalien außer der Live-Marke (0.75rem, 600)
- Hero-Titel im Beispiel darf bis 2.5rem wachsen, Gewicht 600, Laufweite -0.02em; sonst bleibt die Skala klein

## Abstände und Raster
- Leiter in px: 2, 4, 5, 8, 12, 16, 20, 24, 32, 48; Innenabstand meist 8px
- Seitenleiste 240px breit links, Hauptbereich daneben, Inhalt bis ca. 1040px
- Kartenraster: 3 Spalten ab 1024px, 2 ab 640px, 1 darunter; Lücke 16px
- Sektionen mit nur 24 bis 32px Abstand, getrennt durch eine 1px-Linie `rgba(173,173,184,.43)`

## Layout-Muster
- Kopfzeile 50px hoch, weiß, links Logo-Platzhalter und "Entdecken", mittig Suchfeld, rechts Pillenknöpfe
- Hero: großer 16:9-Player-Platzhalter links, rechts Infospalte (Name, Kategorie in Violett, Zuschauerzahl, Tags)
- Kartenreihen mit violetter Überschrift, darunter drei Kacheln und mittig "Mehr anzeigen" über einer Linie
- Festes dunkelviolettes Band am unteren Rand mit Aufruf und weißer Pille
- Mobil: Seitenleiste entfällt, Kacheln einspaltig, Band wird gestapelt

## Komponenten
- Kachel: Vorschaufläche 16:9, Radius 4px, darauf oben links Live-Marke (rot, weiß, Radius 4px, Padding 1px 5px), unten links Zuschauerzahl auf dunklem Overlay; darunter runder Avatar (30px), Titel (600, einzeilig mit Ellipse), Kategorie in `#53535f`, Tags
- Primärknopf: Pille (Radius 9000px), `#8b4ff2`, weiße Schrift 600, Höhe 30px, Padding 0 10px; Hover `#6e30dc`
- Sekundärknopf: Pille, `rgba(173,173,184,.22)`, Text `#0e0e10`, 600; Hover etwas dunkler
- Tag: Pille, gleiche graue Fläche, 12px, 600, Padding 2px 8px
- Suchfeld: weiß, Rand 1px `rgba(50,50,57,.62)` als Innenschatten, Radius 6px, Padding 0 12px, Höhe 34px; Fokus: 2px violetter Ring
- Schatten nur für schwebende Dinge: `0 6px 16px rgba(0,0,0,.22), 0 0 4px rgba(0,0,0,.08)`; Kacheln selbst ohne Schatten
- Seitenlistenzeile: Avatar 30px rund, Name 600, darunter Kategorie, rechts roter Punkt mit Zahl

## Bildsprache
Bunte, belebte Bildschirmmotive: Spielszenen, Gesichter in Kreisen, Chatfenster. Die Bilder liefern alle Farbe, die Oberfläche bleibt neutral. Avatare immer rund. Im Beispiel: Verläufe und einfache SVG-Formen als Platzhalter, nie echte Fotos.

## Animation
Kurz und funktional: Hover auf Knöpfen und Kacheln 100 bis 150ms, Farbwechsel statt Bewegung; Kachel hebt sich beim Hover höchstens 2px. Kein Parallax, keine langen Einblendungen. `prefers-reduced-motion` respektieren.

## Tonfall
Direkt, kurz, aktiv und gegenwartsbezogen: Imperative wie "Jetzt ansehen", "Mehr anzeigen", Zählwörter statt Beschreibungen. Du-Form, keine Werbesprache, kaum Satzzeichen-Schmuck.

## Mach
- Hellgrauen Grund mit weißen Flächen und genau einem Violett als Interaktionsfarbe
- Alles klein und dicht halten: 14px Text, Meta 12px
- Pillen für Knöpfe und Tags, 4px Radius für Kacheln und Marken
- Rot ausschließlich für Live-Status und Zähler
- Bild und Zahl über Overlay-Verlauf lesbar machen
- Überschriften in `#5c16c5`, nicht in Schwarz

## Mach nicht
- Keine großen Display-Schriften, keine Hero-Fläche mit viel Leerraum
- Kein dunkler Standardmodus als Hauptlook, das Band unten ist die einzige dunkle Fläche
- Keine harten Schatten auf Kacheln, keine Verläufe auf Knöpfen
- Keine zweite Akzentfarbe neben Violett und Live-Rot
- Keine eckigen Knöpfe, keine Versalien-Überschriften

## Typische KI-Fehler in diesem Stil
- Zu viel Luft: großzügige Sektionen und Riesenüberschriften statt dichter Kachelreihen
- Dunkles Design gewählt, weil "Streaming" assoziiert wird, obwohl der Grund hellgrau ist
- Violett überall: Flächen, Verläufe und Rahmen violett statt nur Knopf, Link und Überschrift
- Rot für Fehler oder Knöpfe statt nur für Live-Marken
- Kacheln mit großem Radius und Schatten (Karten-Look), statt 4px und flach
- Avatare eckig oder fehlend; Kacheln ohne Zuschauerzahl und Tags wirken leer
