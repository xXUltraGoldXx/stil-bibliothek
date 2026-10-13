# Stil: Werkbank dunkel

## Kurzbeschreibung und Stimmung
Ein kleines Werkzeug auf warmem, fast schwarzem Grund. Alles passiert in einer schmalen Spalte von 880px: Kästen mit eingekerbten Ecken enthalten Auswahlfelder, Zahlen und Schaltflächen, dazwischen stehen große, ungezwungene Sätze. Die Stimmung ist werkstattartig, verspielt und freundlich-nerdig, nicht glatt wie ein Konzern-Dashboard. Kein Schatten, keine Verläufe auf Flächen. Nur ein sanfter warmer Schimmer am oberen Seitenrand. Ein Orange führt das Auge, ein Grün meldet "läuft".

## Farbpalette
- Seitengrund `#000000`, darüber ein warmer Schimmer oben (radialer Verlauf von `#2a1c10` zu transparent, nur im oberen Seitenrand)
- Werkbank-Grund `#14130f`, Kasten-Fläche `#1e1c18`
- Linien und Rahmen `#322f28`, immer 2px
- Text primär `#f3efe6` (warmes Elfenbein), sekundär `#a39c8e` (der meiste Text, etwa zwei Drittel)
- Akzent Orange `#fb923c` für Zahlen, Links, aktive Zustände; als Rahmen oder Unterstreichung mit 40 % Deckkraft
- Orange-Tint `#2a1c10` für leichte Hervorhebungen
- Erfolg Grün `#4ade80`, Fläche dazu `rgba(74,222,128,.12)`, Rand `rgba(74,222,128,.45)`
- Keine weiteren Farben

## Typografie
- Eine System-Sans: ui-sans-serif, system-ui, "Segoe UI", Roboto, sans-serif. Das Logo ist eine Systemschrift in Gewicht 700 (keine Webschrift nötig)
- H1/Wortmarke: 4rem (64px, mobil 2.4rem), Gewicht 700, Zeilenhöhe 1, Laufweite -0.03em
- Große Satzzeile: 2.1rem, Gewicht 400, Zeilenhöhe 1.4, Farbe sekundär, Zahl darin in Orange 700
- Fließtext 1.05rem (16.8px), Zeilenhöhe 1.5, sekundär
- UI-Text 0.9rem (14.4px), Zeilenhöhe 1.5
- Kleinschrift-Label: 0.72rem (11.5px), Versalien, Laufweite 0.08em, Gewicht 600, sekundär
- Gewichte nur 400, 600, 700

## Abstände und Raster
- Inhaltsbreite maximal 880px, zentriert, seitlich mindestens 16px
- Alles einspaltig gestapelt, nur kleine Paare nebeneinander (zwei Kästen mit schmaler Mitte, drei Schaltflächen in einer Reihe)
- Innenabstand der Kästen 16px bis 20px, Lücken in 8px, 12px, 16px
- Abstand zwischen Blöcken 32px, großer Abschnittsabstand 51px
- Mobil bricht alles auf eine Spalte, Kästen laufen fast randlos

## Layout-Muster
- Kopf: Wortmarke links, kleine Skizzenfläche rechts (CSS-Platzhalter), darunter zentrierter Zweizeiler
- Zwei Kästen mit Auswahlfeldern nebeneinander, in der Mitte eine schmale Spalte mit zwei runden Knöpfen
- Eine große Satzzeile mit eingebettetem Zahlenfeld, darunter ein Pfeil
- Statusleiste: links Pille "Aktualisiert", rechts rundes Zahnrad und grüne Pille
- Vorschau-Kasten mit großem Beispieltext, darunter eine dünne Fortschrittsleiste
- Ausgabe-Kasten mit drei breiten Pillen-Knöpfen, danach eine Liste von Voreinstellungen

## Komponenten
- Kasten: Fläche `#1e1c18`, 2px Rand `#322f28`, an allen vier Ecken konkav eingekerbt (Radius 14px, Kerbe nach innen, nicht abgerundet)
- Auswahlfelder und Eingaben: transparent, ohne Kasten, nur untere Linie 2px in Orange 40 %, Padding 5px 6px, Pfeil rechts
- Pillen-Knöpfe: Radius 999px, 2px Rand `#322f28`, Gewicht 600, ausgegraut bis aktiv; aktiv mit orangefarbenem Rand
- Runde Knöpfe: 40px, Radius 50%, Fläche `#1e1c18`, Rand `#322f28`
- Status-Pille grün: Text `#4ade80`, Fläche 12 % Grün, Rand 45 % Grün
- Links Orange ohne Unterstreichung, Hover Unterstreichung
- Fokus: 2px Orange-Umriss mit 3px Abstand

## Bildsprache
Rohe, handgezeichnete Skizzen, weiße Strichzeichnungen auf Schwarz, etwas schräg und selbstironisch. Im Beispiel als CSS/SVG-Platzhalter mit einfachen weißen Linien (Kreis, Strichfigur) auf `#000`. Keine Fotos, keine Verläufe, keine Stockmotive.

## Animation
Funktional und knapp. Zustandswechsel 150ms ease für Rand und Farbe. Eine Fortschrittsleiste füllt sich beim "Aktualisieren", Live-Pille kann einmal sanft pulsieren (Deckkraft 1 zu 0.6, 2s). Kein Parallax, keine Eingangsanimationen.

## Tonfall
Direkt, locker, leicht frech, in kurzen Sätzen. Anweisungen als Handlung ("Mischen, strecken, quetschen"). Kleine Statusmeldungen in Alltagssprache. Kein Marketingdeutsch.

## Mach
- Schmale 880px-Spalte, alles gestapelt
- Eingekerbte Ecken konsequent bei jedem Kasten
- Sekundärtext in `#a39c8e` als Normalfall, Elfenbein nur für Wichtiges
- Orange nur für Zahlen, Auswahl-Linien und Aktives
- Versal-Labels über jedem Feld
- Eine große Satzzeile als Herzstück der Seite

## Mach nicht
- Keine Schatten, keine Glasflächen, keine Verläufe auf Kästen
- Keine runden Karten mit Radius 14px nach außen (Kerben statt Rundung)
- Kein reines Weiß `#fff` und kein reines Schwarz als Kastenfläche
- Keine Mehrspalten-Kachelraster, keine Heldenfläche in voller Breite
- Keine zweite Akzentfarbe neben Orange und Grün

## Typische KI-Fehler in diesem Stil
- Aus den Kerbecken werden normale `border-radius`-Ecken, und der Werkzeugcharakter verschwindet
- Kalte Grautöne (`#111`, `#888`) statt der warmen Brauntöne
- Zu breite Layouts, 1200px mit Dreierkacheln statt 880px Einspalter
- Orange wird zur Füllfarbe großer Knöpfe statt Linie und Zahl
- Schatten und Glow auf Kästen
- Fettgedruckte Fließtexte oder Gewicht 800 und höher
- Fehlende Versal-Labels, wodurch die Formularlogik verloren geht
