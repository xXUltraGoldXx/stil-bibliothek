# Stil: Weich freundlich

## Kurzbeschreibung und Stimmung
Eine helle, warme Oberfläche, die Vertrauen schafft, ohne zu belehren. Der Hintergrund ist ein leicht warmes Off-White, darauf liegen große weiße Karten mit sehr runden Ecken. Eine einzige kräftige Orange-Fläche markiert die wichtigste Handlung, alles andere bleibt ruhig und neutral. Vier Pastelltöne (Himmelblau, Pfirsich, Mintgrün, Butter) sorgen für Freundlichkeit in Abschnitten und Etiketten. Das Gefühl: ein hilfsbereiter Alltagsbegleiter, kein Technikprodukt. Große, enge Schlagzeilen in normalem Gewicht, wenig Text, viel Luft, kleine Illustrationen statt Fotos.

## Farbpalette
- Seitengrund oben `#fbfaf9`, Abschnittsgrund warm `#f7f5f2`, Karten und Knöpfe `#ffffff`
- Text `rgba(0,0,0,.96)` (praktisch Schwarz), sekundärer Text `rgba(0,0,0,.66)`
- Handlungsfarbe Orange `#f26a2e`, nur für den einen Hauptknopf pro Ansicht, Text darauf weiß
- Link- und Akzentblau `#1074cc`, Fokus und Markenblau `#3969ef`
- Pastellflächen: Himmel `#cbeaff`, Pfirsich `#ffe4cc`, Mint `#cfebda`, Butter `#ffeab8`
- Passende Textfarben auf Pastell: Himmel `#01142d`, Pfirsich `#290e0a`, Mint `#082119`, Butter `#240f04`
- Zweitknopf neutral `#eeeeee`, Haarlinien `rgba(0,0,0,.08)` und `rgba(0,0,0,.12)`
- Keine Verläufe, kein Dunkelmodus als Grundlage

## Typografie
- Eine geometrisch-humanistische Grotesk: Figtree (Google Fonts), Gewichte 400, 500, 700. Offene Formen und runde Rundungen.
- Schlagzeile: 3.25rem (52px) auf Desktop, 2.75rem (44px) mobil, Gewicht 400, Zeilenhöhe 1, Laufweite -1px. Das normale Gewicht ist Absicht.
- Abschnittstitel: 2.75rem Desktop, 2.25rem mobil, Zeilenhöhe 1.1, Laufweite -1px
- Kartentitel 1.25rem, Zeilenhöhe 1.4; Fließtext 1rem, Zeilenhöhe 1.5; Kartentext 0.875rem, Zeilenhöhe 1.43
- Knopftext 0.875rem, Gewicht 500 bis 700
- Etiketten 0.675rem (10.8px), Versalien, Laufweite 0.04em, Farbe sekundär
- Fett (700) nur für Knopftexte, Menüpunkte und kurze Betonungen

## Abstände und Raster
- Basis 4px; häufige Werte 8, 12, 16, 24, 36, 40, 64, 80px
- Inhaltsbreite 1152px bei Kopfzeile, Textbereiche höchstens 900px, Kartenpaare etwa 280px breit je Karte mit 16px Lücke
- Karteninnenabstand 24 bis 36px, Knopf innen 0 11px bei 16px Zeilenhöhe, in der Praxis Höhe 40 bis 46px
- Abschnitte trennt großzügiger Leerraum von 64 bis 80px oben und unten, keine Linien
- Mobil eine Spalte, Karten bis 280px breit mittig, Seitenrand 16px

## Layout-Muster
- Kopfzeile: Wortmarke links, Suchfeld als weiße Pille in der Mitte, rechts ein Textknopf und ein Menüsymbol. Mobil bricht das Suchfeld in eine zweite Zeile.
- Hero: zentrierte zweizeilige Schlagzeile mit einem kleinen Symbol mitten im Satz, darunter zwei weiße Karten nebeneinander, darunter ein kurzer Vertrauenssatz in 0.875rem
- Zwischen Hero und Folgeabschnitt ein halbrunder Pfeilknopf, der in die weiße Fläche ragt; die weiße Folgefläche beginnt mit Radius 32px oben
- Folgeabschnitte: Etikett, große Aussage-Überschrift, darunter ein Raster aus Pastellkarten mit Illustrationsplatzhalter
- Danach vollflächige Abschnitte, jeweils eine Aussage mit einer Illustration

## Komponenten
- Karte: weiß, Radius 32px 32px 32px 0 (die untere linke Ecke bleibt eckig, wie eine Sprechblase), Schatten `0 2px 4px rgba(0,0,0,.04), 0 4px 20px rgba(0,0,0,.04)`, Inhalt mittig
- Pastellkarte: Radius 24px bis 40px, keine Kontur, kein Schatten
- Etikett auf Karte: Pastell-Himmel, Radius 32px oben links und unten rechts, innen 8px 16px, Versalien 0.675rem, sitzt in der Kartenecke
- Hauptknopf: Orange `#f26a2e`, weiße Schrift 0.875rem Gewicht 700, Radius 999px, Höhe 40px
- Zweitknopf: `#eeeeee`, schwarze Schrift, gleiche Form
- Kleiner Knopf: weiß, 1px Rand `rgba(0,0,0,.08)`, Schatten `0 1px 2px rgba(0,0,0,.06)`, Radius 999px
- Suchfeld: weiß, Radius 999px, Schatten `0 8px 16px rgba(0,0,0,.06), 0 2px 6px rgba(0,0,0,.06), 0 0 0 1px rgba(0,0,0,.08)`, darin ein segmentierter Umschalter als graue Pille mit weißem aktivem Segment
- Fokus: 2px Ring in `#3969ef`, Rand sonst transparent

## Bildsprache
Kleine, handgezeichnet wirkende Illustrationen mit weichen Umrissen und warmen Flächen, etwa ein Vergrößerungsglas, ein Schild, eine Wolke. Etwa 64 bis 96px groß, mittig über dem Kartentext. Keine Fotos als Hauptmotiv. Als Platzhalter dienen runde oder abgerundete CSS-Flächen und einfaches Inline-SVG in Pastell und Orange.

## Animation
Zurückhaltend. Knöpfe und Karten wechseln beim Hover in 0.15s die Hintergrundhelligkeit; Karten heben sich höchstens um 2px. Pfeilknopf darf sanft 4px auf und ab wippen (1.6s). Alles wird bei prefers-reduced-motion abgeschaltet. Keine Parallax-Effekte, keine großen Einblendungen.

## Tonfall
Direkt, warm, in kurzen Sätzen. Ansprache mit "du". Ein Satz Nutzen, ein Satz Beruhigung. Kurze Versprechen wie "kostenlos" und "ohne Haken" stehen offen da. Keine Fachwörter, keine Superlative, Ausrufezeichen höchstens einmal pro Seite im Hero.

## Mach
- Warmes Off-White als Grund, weiße Karten mit Radius 32px, eine eckige Ecke je Karte
- Genau eine Orange-Fläche pro Bildschirm für die Hauptaktion
- Schlagzeilen im Gewicht 400 mit Laufweite -1px
- Pastellflächen für Gruppen, mit dunkel getönter Textfarbe statt reinem Schwarz
- Pillenform für alle Knöpfe und das Suchfeld
- Kleine Illustrationen mittig über kurzen Kartentexten
- Großzügiger Leerraum (64 bis 80px) statt Trennlinien

## Mach nicht
- Keine harten Ecken an Karten außer der bewussten einen Ecke
- Keine schweren fetten Schlagzeilen
- Kein zweites Orange oder neonfarbene Akzente
- Keine Verläufe, keine dunklen Flächen, keine Glas-Effekte
- Keine Fotos als Kartendekoration, keine Stockmotive
- Keine großen Schatten; nur die leisen Schatten oben

## Typische KI-Fehler in diesem Stil
- Alle Knöpfe orange gefärbt, wodurch die Hauptaktion untergeht
- Schlagzeilen in Gewicht 700 oder 800 statt 400
- Karten mit gleichmäßigem Radius an allen vier Ecken und kräftigem Schatten, sodass die sprechblasenartige Ecke fehlt
- Pastellflächen mit reinem Schwarz als Text statt der getönten Dunkelfarbe
- Kalt-weißer Grund `#ffffff` überall statt des warmen Off-Whites `#f7f5f2`
- Zu viel Text auf den Karten: mehr als drei Zeilen zerstören die Ruhe
- Rechteckige oder nur leicht gerundete Knöpfe statt voller Pille
