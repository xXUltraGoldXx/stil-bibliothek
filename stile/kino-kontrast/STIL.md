# Stil: Kino Kontrast

## Kurzbeschreibung und Stimmung
Dunkel, filmisch, direkt. Ein vollflächiges Motiv füllt den Einstieg, darüber sitzt linksbündig ein großer weißer Titel in kräftigem Schnitt. Rot ist die einzige Signalfarbe: Etikett, Hauptknopf, Piktogramme. Alle Kanten sind rechtwinklig, nichts ist weich oder verspielt. Die Wirkung: Kinoleinwand mit Bedienleiste, selbstbewusst und ohne Schnörkel. Dazu kommen nüchterne helle Grauflächen für Hinweisleisten und den Fußbereich.

## Farbpalette
- Grund (Hauptfläche, flächenmäßig dominant): Schwarz `#000000`
- Dunkle Stufen: `#1b1b1b` (Hero-Grund), `#25242a` (Leisten), `#333333` (Kacheln, Trennflächen), `#2d2d2d` (Eingabefelder)
- Hell: Weiß `#ffffff` (Text auf Dunkel), Hellgrau `#f2f2f2` (Hinweisleiste, Fußbereich), `#ebebeb` (Standardknopf auf Hellgrau)
- Text auf Hell: Schwarz `#000000`, gedämpft `#616161`
- Signalrot `#e51212` für Etikett, Hauptknopf, Piktogramme, Preis-Hinweise; nie als Fließtext-Grund
- Zweitakzent sparsam: Grün `#1c8420` für Textlinks auf Hell und Häkchen, Gelb `#ffd800` nur für Hinweisstreifen, Blau `#0067b8` nur für Links im Hinweistext
- Text auf Dunkel gedämpft: `rgba(255,255,255,.75)`; Bildabdunklung unten: Verlauf von transparent nach `#000000`

## Typografie
- Eine humanistische Groteske für alles: Source Sans 3 (Google Fonts)
- H1/Hero-Titel: Gewicht 700, `clamp(2.25rem,5vw,3.9rem)` (Desktop ca. 62px), Zeilenhöhe 1.16, Laufweite -0.01em, Weiß
- H2: 700, `clamp(1.6rem,3vw,1.9rem)`, Zeilenhöhe 1.2
- Untertitel unter dem Titel: 400, 1.4rem, Weiß
- Fließtext: 400, 0.95rem bis 1rem, Zeilenhöhe 1.5
- Etiketten und Knöpfe: Versalien, Gewicht 700 (Knöpfe auch 900), Laufweite 0.065em, 0.9rem
- Kleintext und Fußbereich: 0.7rem, Zeilenhöhe 1.5, Grau `#616161`
- Gewichte: 400, 600, 700, 900. Kein Kursiv, keine Verläufe auf Text

## Abstände und Raster
- Basis 8px: 0.5, 1, 1.5, 2, 3, 4rem
- Seitenrand Desktop 4rem (64px), Mobil 1rem; Inhaltsbreite bis 1600px
- Sektionen vertikal 3.5 bis 5rem
- Kachelraster: 3 oder 4 Spalten ab 860px, 2 ab 540px, sonst 1; Lücke 1rem
- Haltepunkte: 540px, 860px, 1084px, 1400px

## Layout-Muster
- Hinweisleiste ganz oben: Hellgrau, Text links, drei Knöpfe rechts, mobil untereinander
- Navigationsleiste: schwarz, Wortmarke links, Menüpunkte 1rem Weiß, rechts Suche und Profilkreis
- Hero: Vollbildmotiv (Platzhalter aus dunklen Verläufen), Textblock in der rechten Hälfte, vertikal mittig. Mobil: Motiv oben, Text darunter auf Schwarz
- Piktogramm-Reihe: sechs rote Linien-Symbole mit kurzem Weißtext, gleichmäßig verteilt
- Kachelreihen: Bildfläche im Format 16:9 oder 3:4, darunter Titel und kurze Zeile, keine Rahmen
- Fußbereich: Hellgrau mit mehrspaltiger Linkliste in 0.7rem

## Komponenten
- Hauptknopf: Fläche `#e51212`, weiße Versalien 700, Radius 0, Innenabstand 0.75rem 1.5rem, nachgestellter Winkel "›" als Zeichen; Hover `#c80000`
- Textknopf: ohne Fläche, weiße Versalien, gleicher Winkel; Hover mit 2px Unterstreichung
- Standardknopf auf Hellgrau: `#ebebeb`, schwarzer Text 400, 0.95rem, Radius 0
- Etikett: kleine rote Box, weiße Versalien 700, 0.8rem, Innenabstand 0.2rem 0.5rem, Laufweite 0.065em
- Eingabefeld: Fläche `#2d2d2d`, 1px Rand `#7cc400`, Radius 0, weißer Text
- Fokus: 2px weißer Rahmen mit 2px Abstand
- Profilkreis: einziges rundes Element, 36px, 1px weißer Rand
- Schatten: keine; Tiefe entsteht durch Motiv und Verlauf

## Bildsprache
Großformatige, düstere, filmische Motive mit warmen Lichtpunkten, Rauch, Glut und starken Silhouetten. Immer dunkel gegradet, unten in Schwarz auslaufend, damit Text und nächste Sektion sauber anschließen. Im Beispiel: CSS-Verläufe, Radial-Lichter und einfache SVG-Silhouetten als Platzhalter. Piktogramme als rote Linien-SVGs mit 3px Strichstärke.

## Animation
Zurückhaltend und funktional. Hover 150 bis 200ms auf Farbe, kein Hüpfen. Hero-Motiv darf langsam skalieren (1.0 auf 1.04 in 12s), Pausen-Knopf unten links als 36px-Quadrat mit weißem Rand. `prefers-reduced-motion` respektieren.

## Tonfall
Kurz, aktiv, im Imperativ: Titel in zwei bis vier Wörtern, ein Untertitel mit einem Satz, Knöpfe mit Verb in Versalien. Du-Form. Keine Floskeln, keine Ausrufezeichen.

## Mach
- Schwarz als Hauptfläche, Rot nur an drei bis vier Stellen pro Bildschirm
- Rechtwinklige Kanten überall, Radius 0
- Titel groß, weiß, Gewicht 700, linksbündig
- Knöpfe in Versalien mit Winkelzeichen
- Motiv unten in Schwarz auslaufen lassen
- Text auf Dunkel immer Weiß, Kontrast mindestens 4.5:1

## Mach nicht
- Keine Rundungen an Karten und Knöpfen, keine Pillen
- Keine Schatten, kein Glas, keine Verläufe auf Text
- Kein zweites Rot oder Rot als Flächenfüllung großer Blöcke
- Keine Serifenschrift, keine Zierschriften
- Keine hellen Flächen im Hauptbereich, Hellgrau nur für Leiste und Fußbereich
- Keine Emoji

## Typische KI-Fehler in diesem Stil
- Abgerundete Knöpfe und Karten statt rechtwinklig
- Rot überall verteilt (Überschriften, Rahmen, Hintergründe) statt gezielt an Etikett, Hauptknopf, Piktogrammen
- Reines Weiß als Seitengrund statt Schwarz, oder dunkelgrauer Grund statt echtem Schwarz
- Titel zentriert und klein statt groß, links und fett
- Knopftext in Groß- und Kleinschreibung statt Versalien
- Neon-Grün oder Blau als Hauptakzent (Rückfall in Standard-Gaming-Look)
- Zu viele Schatten und Glows, die dem flachen Charakter widersprechen
