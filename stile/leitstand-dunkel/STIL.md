# Stil: Leitstand dunkel

## Kurzbeschreibung und Stimmung
Ein Instrumentenpult bei Nacht. Eine fast schwarze Fläche (`#05070d`) trägt eine vollflächige Datenszene, darüber liegen schmale, halbtransparente Glaspanels mit sehr kleiner, dichter Schrift. Die Oberfläche wirkt wie ein Werkzeug für Fachleute: viel Information auf wenig Raum, ruhig, präzise, technisch. Cyan leuchtet als Informationsfarbe, ein einziges Orange markiert die eine wichtige Handlung. Die Szene ist der Inhalt, die Oberfläche ordnet sich ihr unter.

## Farbpalette
- Grund: Nachtschwarz `#05070d`, darauf nur dunkle Blautöne
- Panel-Glas: `rgba(6,22,36,0.55)`, Mobil dichter `rgba(13,20,36,0.92)`
- Feldfüllung: `rgba(20,80,110,0.12)`, Mobil `rgba(20,50,80,0.9)`
- Erhöhte Fläche (Schalter, Chips): `#1c2a4a` und `#16203a`
- Text primär (Überschriften, Werte, Feldtext): Eisblau `#a8f2ff`
- Text Basis: `#dfe6f5`; sekundär `#8fa3c8`; gedämpft (Hilfetexte, Leerzustände) `#5d6d8e`
- Rahmen: Cyan `rgba(90,220,255,0.45)` für aktive Elemente, `#2c3a5c` für Strukturlinien
- Handlung: Orange `#f15f2c`, Text darauf `#ffffff`. Nur ein Knopf pro Ansicht
- Hinweis Amber `#ffd166`, Warnung Rot `#ff8a8a`
- Datenpunkte dürfen bunt sein (Rot, Hellblau, Gelb, Violett), die Oberfläche selbst nicht

## Typografie
- Systemschrift: `system-ui, sans-serif` (keine Webfont nötig, bewusst nüchtern). Für Zahlen, Zeitstempel und Kennungen `ui-monospace, Consolas, monospace`
- Basisgröße 13px (0.8125rem), Zeilenhöhe 1.45
- Meta und Chips 11px (0.6875rem), Zeilenhöhe 1.45; Beschriftungen 12px (0.75rem)
- Panel-Titel 15px (0.9375rem), Gewicht 600, Farbe `#a8f2ff`
- Listenüberschriften 14px, Gewicht 700, `#dfe6f5`
- Große Zahlen höchstens 20px (1.25rem). Auch eine Landingpage bleibt klein und dicht; Hero-Titel höchstens 1.75rem
- Gewichte nur 400, 600, 700. Laufweite normal, keine Versalien-Orgie

## Abstände und Raster
- Kleinteilig: Innenabstände 3, 4, 8, 9, 12, 18px; Lücken 6, 7, 8, 10px
- Panel-Innenabstand 14px bis 18px, Panel-Breite etwa 330px
- Desktop: Panel links oder oben am Rand mit 10px Abstand zur Fensterkante, Rest ist Szene
- Mobil (390px): Panels werden zu schmalen Leisten und Overlays, Bedienelemente als Raster aus 46px-Feldern (Touch-Ziele), 34px bis 36px für Nebenschalter
- Keine breiten Textspalten; Zeilen kurz halten, höchstens etwa 48 Zeichen

## Layout-Muster
- Vollflächige Szene (Canvas oder Platzhalter) als Hintergrund, alles Weitere schwebt darüber
- Linkes Seitenpanel in voller Höhe mit Titel, Kurzstatistik, Suchfeld, Knopfreihe, Baumliste und Fußnote
- Obere Leiste schmal und halbtransparent, mit Zeitstempel in Monospace, einem "Live"-Chip und einer Zeitleiste
- Ecken tragen kleine runde Schalter (Hilfe, Schließen)
- Auf der Landingpage: Szene als Hero, Panel als Textträger, Daten-Kacheln im Raster, Baumliste als Funktionsübersicht, ein Orange-Knopf am Ende

## Komponenten
- Panel: Glasfläche, Rand 1px `#2c3a5c`, Radius 10px bis 12px, Außenglühen `0 0 18px rgba(80,200,255,0.22)` plus innen `inset 0 0 26px rgba(80,200,255,0.1)`
- Knopf (Standard): Fläche `rgba(20,80,110,0.12)`, Rand 1px `rgba(90,220,255,0.45)`, Radius 6px, Text `#a8f2ff` 11px, Innenabstand 3px 9px
- Knopf (Handlung): `#f15f2c`, Text weiß, Radius 6px, Innenabstand 3px 9px bis 6px 10px
- Eingabefeld: Radius 6px, Innenabstand 5px 8px, 13px, gleiche Füllung und Rand wie Standardknopf
- Aktiver Schalter: Unterkante als `inset 0 -2px 0 rgba(120,190,255,0.85)`
- Runde Schalter: Radius 50%, 34px bis 46px, Fläche `rgba(13,20,36,0.85)`
- Chips und Zähler: Radius 3px, 11px, Monospace für Zahlen
- Baumliste: Pfeil, Kästchen, Farbpunkt, Name, rechts ausgerichteter Zähler; ausgewählte Zeile mit `#1c2a4a`

## Bildsprache
Dunkle Datenszenen: Punktwolken, Bahnen, feine Linien, Himmelskörper, gedämpfte Beschriftungen in Amber oder Weiß direkt an Objekten. Viel Schwarz, wenige leuchtende Farben, hohe Dichte im Zentrum und Auslaufen zum Rand. Im Beispiel entstehen Szene und Punkte rein aus CSS-Verläufen und Inline-SVG.

## Animation
Funktional und zurückhaltend. Langsames Rotieren oder Driften der Szene, ein sanft pulsierender Punkt am "Live"-Chip (1.6s), Hover auf Knöpfen mit Rahmen, der von 0.45 auf 0.8 Deckkraft geht (0.15s). Keine Sprünge, keine Parallax-Effekte; bei `prefers-reduced-motion` alles ruhig stellen.

## Tonfall
Knapp, sachlich, mit Zahlen. Beschriftungen wie ein Messgerät: Wert, Einheit, Stand. Ehrliche Hinweise zu Genauigkeit und Grenzen (zum Beispiel "nicht maßstäblich"). Keine Werbesprache, keine Ausrufezeichen.

## Mach
- Kleine Schrift (11px bis 13px) in Eisblau auf Nachtblau, gute Kontraste einhalten
- Glaspanels mit Cyan-Rand und weichem Außenglühen
- Genau ein orangefarbener Handlungsknopf
- Zahlen in Monospace, Zähler rechtsbündig
- Mobil: große Touch-Felder (46px) im Raster
- Stand, Zeitstempel und Quelle sichtbar angeben

## Mach nicht
- Keine hellen Flächen, kein Weiß als Hintergrund
- Keine großen Headlines und keine Hero-Typografie über 1.75rem
- Keine Verläufe auf Knöpfen, keine Schlagschatten nach unten
- Kein zweites Orange-Element neben dem Handlungsknopf
- Keine Radien über 12px außer bei runden Schaltern
- Keine Stockfotos und Illustrationen mit Menschen

## Typische KI-Fehler in diesem Stil
- Zu große, luftige Schrift: Das Pult wirkt wie eine gewöhnliche SaaS-Seite statt dicht und klein
- Neon-Glühen überall, statt nur Panelrand und aktive Schalter dezent zu betonen
- Deckende, graue Panels statt halbtransparentem Glas über einer sichtbaren Szene
- Orange für mehrere Knöpfe oder als Dekor
- Violette Verläufe als "Weltraum-Klischee" statt Nachtschwarz mit Blautönen
- Fehlende Monospace-Zahlen und fehlende Zeitstempel, wodurch der Messgeräte-Eindruck verloren geht
