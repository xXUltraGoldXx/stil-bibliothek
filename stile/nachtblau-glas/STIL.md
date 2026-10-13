# Stil: Nachtblau Glas

## Kurzbeschreibung und Stimmung
Dunkles Bedienfeld im Petrol-Nachtblau. Halbtransparente Glasflächen mit Haarlinien-Rand liegen über einem abgedunkelten Hintergrund (Foto oder Verlauf). Ein einziger warmer Bernstein-Ton markiert Aktion und Zustand, ein kühles Cyan taucht nur als winziges Technik-Detail auf. Die Stimmung ist ruhig, konzentriert und werkzeugartig, wie eine Konsole, auf der man etwas erledigt. Die Oberfläche tritt zurück, der Inhalt steht im Mittelpunkt.

## Farbpalette
- Seitengrund: `#0b1a24`; Radial-Verlauf von `#46646f` (Mitte, sehr dezent) nach `#0b1a24`
- Flächen: Panel `#071e28` (Deckkraft .96), tiefer Einsatz `#020e14` (Karten-Felder, Kartenflächen), Fußleiste `rgba(4,23,29,.55)`
- Glas: `rgba(10,28,40,.76)` mit Rand `1px solid rgba(222,238,244,.18)`
- Text: Hell `#eaf3f6`, gedämpft `#b4ced6`, schwach `#92aeb6`, Linktext `rgba(229,242,244,.7)`
- Akzent Bernstein `#f0bc67` (hell `#ffca85`, Variante `#e3b56e`); Fläche des Primärknopfs `rgba(240,188,103,.55)` bis voll
- Tech-Akzent Cyan `#70dbe1`, nur für Haarlinien und kleine Zustände (Rand `rgba(93,217,232,.24)`)
- Fehler/Warnung: `#ff9999`, sehr sparsam
- Kein reines Schwarz, kein reines Weiß

## Typografie
- Eine Familie: Lato (Google Fonts), Gewichte 400, 700, 900
- Überschriften: Gewicht 400, 1.5 bis 2.5rem, Zeilenhöhe 1.2, Laufweite 0.01em. Die Größe trägt, nicht das Gewicht
- Fließtext: 0.9375rem bis 1rem, Zeilenhöhe 1.6, Farbe `#b4ced6`
- Labels (FROM, TO, Kategorien): 0.6875rem, Gewicht 900, Versalien, Laufweite 0.14em, gedämpfte Farbe
- Knopf- und Kartentitel: Gewicht 700, 0.9375rem
- Kleintext und Fußzeile: 0.75rem, Zeilenhöhe 1.5 (nicht kleiner)
- Gewichte nur 400, 700, 900. Keine Kursivschrift, keine Verläufe auf Text

## Abstände und Raster
- Leiter in px: 4, 8, 12, 14, 20, 32, 48, 72
- Panel-Innenabstand 20px, Lücken in Formularen und Reihen 8 bis 12px
- Inhalt max. 1120px, Panel max. 1100px, seitlicher Rand 16px mobil
- Raster: 2 Spalten für Felder und Karten (Lücke 12px), 1 Spalte unter 700px
- Sektionen 56 bis 96px vertikal; dicht innerhalb eines Panels, großzügig dazwischen

## Layout-Muster
- Aufbau als Stapel von Glas-Panels über einem dunklen Hintergrund, kein Vollflächen-Wechsel
- Kopfzeile: Titel links, kleine Pillen und runde Icon-Knöpfe rechts
- Panel-Kopf: Frage oder Überschrift links, Status-Pille und Abbrechen-Knopf rechts
- Felder nebeneinander (Label links im Feld, Platzhalter rechts davon)
- Großer Inhaltsbereich (Karte, Vorschau, Daten) als tiefe `#020e14`-Fläche mit Radius 18px
- Fußzeile des Panels: Statustext links, Primärknopf rechts
- Fixierte Fortschrittskarte oben mittig (Titel, Prozentwert in Bernstein, 4px-Balken)

## Komponenten
- Panel: Glas, Radius 18px, Rand 1px `rgba(222,238,244,.18)`, Schatten `0 20px 70px rgba(0,0,0,.53)`, `backdrop-filter: blur(14px)`
- Primärknopf: Radius 8px, Bernstein-Fläche `#f0bc67` (gedämpft `rgba(240,188,103,.55)` im Wartezustand), dunkle Schrift `#071e28`, Gewicht 700, Pfeil-Icon rechts
- Sekundärknopf: transparent, Rand `1px solid rgba(222,238,244,.18)`, Radius 8px, helle Schrift
- Runder Icon-Knopf: 42px, Radius 50%, Fläche `rgba(10,28,40,.76)`, Schatten `0 18px 50px rgba(0,7,13,.2)`
- Pille (Status): Radius 999px, Rand `rgba(240,185,95,.48)`, Bernsteintext, Gewicht 700
- Feld: Fläche `rgba(255,255,255,.03)`, Rand 1px, Radius 8px, Höhe 52px; Fokus: Rand Bernstein, kein Glow
- Fortschrittsbalken: Höhe 4px, Spur `#36505b`, Füllung Bernstein
- Hover: Rand wird heller, nie Bewegung über 1px

## Bildsprache
Abgedunkelte Innenraum- und Landschaftsmotive, dunkel gegradet, wenig Sättigung, Bernstein als Lichtfarbe. Bilder liegen hinter den Glas-Panels, nie als helle Flächen davor. Produkt- und Datenansichten stehen in tiefen Einsätzen. Im Beispiel: CSS-Verläufe und SVG-Linien als Platzhalter.

## Animation
Zurückhaltend und funktional: Hover und Fokus 160 bis 220ms, ease-out; Fortschrittsbalken füllt linear; Panels blenden mit 400ms und 8px Versatz ein. Keine Sprünge, kein Wackeln, keine Parallax-Effekte. `prefers-reduced-motion` respektieren.

## Tonfall
Kurz, sachlich, handlungsorientiert, Sie-Form oder neutral. Beschriftungen nennen die nächste Handlung („Weiter“, „Ziel wählen“). Statusmeldungen sagen, was gerade passiert. Keine Ausrufezeichen, kein Marketing-Pathos.

## Mach
- Nachtblauen Grund, Glas-Panels mit Haarlinien-Rand und weichem, tiefem Schatten verwenden
- Genau eine Warmfarbe (Bernstein) für Aktion und Zustand
- Überschriften in Gewicht 400, Labels in 900 und Versalien
- Kontrast mindestens 4.5:1, Fließtext nie unter 0.875rem
- Zustände zeigen: Laden, leer, aktiv, deaktiviert (gedämpfter Bernstein)

## Mach nicht
- Kein reines Schwarz `#000`, kein reines Weiß, keine hellen Flächen
- Kein Verlaufstext, keine bunten Mehrfarb-Paletten, keine Emoji
- Keine massiven Überschriften in Gewicht 700 oder 900
- Keine eckigen Panels (Radius unter 8px) und keine harten Schatten
- Kein Cyan als Flächenfarbe

## Typische KI-Fehler in diesem Stil
- Cyan oder Blau-Violett als Hauptakzent statt Bernstein (Rückfall in den Standard-Neon-Look)
- Glas ohne Rand und ohne Schatten, die Panels verschwinden im Grund
- Fette, laute Überschriften statt leichter 400er-Schrift
- Winzige 10-11px-Texte übernehmen, die auf Mobilgeräten unlesbar sind
- Reines Schwarz als Grund und weiße Schrift, wodurch die Petrol-Tiefe fehlt
- Mehrere Akzentfarben gleichzeitig (Bernstein, Cyan, Rot) statt einer
