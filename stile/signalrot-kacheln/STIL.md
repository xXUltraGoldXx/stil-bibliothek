# Stil: Signalrot Kacheln

## Kurzbeschreibung und Stimmung
Ein Schaufenster für Entdecker: eine kräftig rote Kopfzeile, eine schmale rote Icon-Leiste am linken Rand, darunter eine dunkle Bühne für ein großes Hauptmotiv und danach ein heller, dichter Teppich aus kleinen Karten. Die Seite wirkt freundlich, farbstark und geordnet. Die Schrift ist schlicht, die Bilder machen die Show. Gefühl: ein gut sortierter Laden, in dem man gern weiterklickt.

## Farbpalette
- Signalrot `#d9232b` für Kopfzeile, Icon-Leiste, Hauptknöpfe und aktive Pillen; Hover/gedrückt `#b01c24`; Aufhellung `#f04a43`
- Bühne und Fußbereich fast schwarz `#0e0e0e`; Overlays `rgba(0,0,0,.75)`
- Seitenfläche Weiß `#ffffff`, Kartenfläche und Abschnittsband Hellgrau `#f5f6f7`
- Text Schwarz `#000000`, Grautöne `#232426`, `#424447`, `#494c4f`, `#676a6d`, Meta `#696969`
- Linien gestrichelt `#d4d7d9`
- Link-Blau `#3860be` nur für Textlinks im Fließtext
- Rot ist die einzige Akzentfarbe. Bunt wird es nur durch die Bilder

## Typografie
- Eine Familie: Fira Sans (Google Fonts), Gewichte 400, 500, 600, 700
- Basis 14px (0.875rem), Zeilenhöhe 1.4; Fließtext in Karten 13px (0.8125rem) mit Zeilenhöhe 1.5
- Kartentitel 14px bis 16px, Gewicht 700; Überschriften der Bühne bis 28px (1.75rem), Gewicht 700
- Meta, Labels, Daten: 11px (0.6875rem), Gewicht 600, Versalien nur bei Labels wie „Neu“, Laufweite 0.01em
- Rang- und Zahlenangaben in Fira Mono 11px, Gewicht 700
- Die Schriftgrößen sind klein, der Kontrast entsteht durch Gewicht (400 gegen 700), nicht durch Größe

## Abstände und Raster
- Maximale Inhaltsbreite 1176px, Seitenrand 16px mobil, 24px Desktop
- Abstandsskala: 4, 8, 12, 16, 20, 24, 32px; Karteninnenabstand 12px
- Kartenraster: 5 Spalten Desktop, 3 Tablet, 2 Mobil, Lücke 8px bis 16px
- Linke Icon-Leiste 88px breit, Desktop fest; mobil entfällt sie zugunsten einer Icon-Zeile oben
- Abschnitte sind durch 32px bis 48px Leerraum und gelegentlich eine gestrichelte 1px-Linie getrennt

## Layout-Muster
- Kopfzeile in Rot, 72px hoch, Marke links, drei Icon-Knöpfe mit Beschriftung rechts
- Linke Leiste: rote Kacheln von etwa 88px Höhe, Icon oben, Kurzbeschriftung 11px darunter
- Bühne: dunkles Band, Hauptmotiv mit 4px-Radius, Pfeilknöpfe links und rechts, daneben angeschnittene Nachbarmotive, darunter eine Zeile mit Kurztext und weißem Knopf
- Abschnittskopf: Überschrift links, Pillen-Umschalter („Highlights / Neuigkeiten“) rechts
- Danach Kartenraster auf hellgrauem Band, gemischt mit einer breiten Doppelkarte (Bild links, Text rechts)

## Komponenten
- Hauptknopf: Rot gefüllt, weiße Schrift 600, Radius 4px, Höhe 40px, volle Breite in Dialogen
- Zweitknopf: weiß mit 1px Rotrahmen, rote Schrift
- Bühnen-Knopf: weiß, schwarze Schrift 600, Radius 4px
- Pillen-Umschalter: Radius 999px, aktiv Rot mit Weiß, inaktiv Hellgrau mit Schwarz
- Karte: Radius 4px, Bild oben randlos, Inhalt 12px, Titel 700, Meta 11px grau, Fußzeile mit gestrichelter 1px-Linie
- Label „Neu“: roter Streifen in der Bildecke oben links, Versalien 11px, unten rechts 4px gerundet
- Rangzahl in Mono, Preis 700, Altpreis 12px durchgestrichen
- Schatten fast keine: höchstens `0 0 4px rgba(0,0,0,.2)` bei schwebenden Elementen

## Bildsprache
Farbstarke, bildfüllende Motive mit Figuren und Szenen, freigestellt vor kräftigen Hintergründen. Zur Lesbarkeit liegt unten ein Verlauf von `rgba(0,0,0,.5)` nach transparent. Bilder haben meist 4px runde Ecken, kleine Kartenbilder sind quadratisch oder im 16:9-Format. Im Beispiel dienen CSS-Verläufe und SVG-Formen als Platzhalter.

## Animation
Zurückhaltend und funktional: Bühne mit Wischen oder Pfeilen, Wechsel in 0.4s. Hover auf Karten: leichtes Anheben des Bildes um 1.02 Skalierung in 0.2s. Knöpfe wechseln in 0.15s zur dunkleren Rotstufe. Keine Parallax-Effekte.

## Tonfall
Direkt, einladend, kurz. Aktive Verben, kurze Hinweise wie Datum und Verfügbarkeit, keine langen Absätze. Die Ansprache ist locker, aber sachlich.

## Mach
- Rot nur für Kopfzeile, Leiste, Hauptknöpfe und aktive Zustände
- Dunkle Bühne oben, helle Karten darunter, Wechsel in klaren Bändern
- Radius durchgängig 4px, Pillen 999px
- Gestrichelte 1px-Linien in `#d4d7d9` als Trenner
- Kleine Schrift mit starkem Gewichtskontrast
- Auf jeder Karte Titel, Meta und eine Kleinzeile

## Mach nicht
- Keine großen Serifen- oder Display-Schriften
- Keine Schatten über `0 0 4px`
- Keine zweite Akzentfarbe neben Rot
- Keine großen Radien über 8px an Karten
- Kein Fließtext in langen Absätzen
- Keine Vollflächen-Verläufe in Farbe

## Typische KI-Fehler in diesem Stil
- Kopfzeile in Rot vergessen oder zu dunklem Rot geändert, wodurch der Wiedererkennungswert fehlt
- Überschriften zu groß gesetzt, obwohl der Stil mit 14px bis 16px arbeitet
- Karten mit weichen großen Schatten und 16px+ Radius statt flach und 4px
- Gestrichelte Trennlinien durch durchgezogene ersetzt
- Die Icon-Leiste weggelassen, sodass die Seite wie eine Standard-Landingpage wirkt
- Das Raster zu locker: 3 große Karten statt 5 kleiner
