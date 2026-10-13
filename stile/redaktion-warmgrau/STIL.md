# Stil: Redaktion warmgrau

## Kurzbeschreibung und Stimmung
Ein Nachrichtenportal-Stil: eine volle Kopfleiste in kräftigem Orangerot (#E64415) mit weißem Wortlogo, darunter eine helle Navigationszeile und ein warmgrauer Seitengrund (#F1EFED), auf dem weiße Karten (#FFFFFF) mit minimalem Schatten liegen. Die Überschriften sind schwere Slab-Serifen in Schwarz, der Fließtext eine neutrale Sans. Die Stimmung ist seriös, aufgeräumt und informationsdicht, mit genau einer Signalfarbe für Links, Kennzeichnungen und Hauptknöpfe.

## Farbpalette
- Seitengrund: #F1EFED (warmes Hellgrau, großflächig hinter den Karten)
- Karte/Fläche: #FFFFFF (größter Flächenanteil)
- Text: #000000; Sekundärtext: #5C5A58; gedämpft: #BBB9B7
- Signalfarbe: #E64415 (Kopfleiste, Hauptknöpfe, Rubrikzeilen, kleine Plus-Marker)
- Dunkles Rot für Links auf Weiß: #811D00; Hellrosa-Tönung für Hinweisflächen: #FFE5DE
- Linien: #DDDBD9 (Trenner), #989694 (Eingabefelder, Umrandung)
- Rubrikfarben nur als Paare aus heller Fläche und dunkler Schrift: Blau #DDE7FE/#163683, Grün #CAFBD9/#264C32, Violett #E7E3FF/#4F2A5F, Gelb #F7E8BC/#3D2C26
- Verlauf nur als Textschutz auf Bildern: von transparent nach #000000 von oben nach unten.

## Typografie
- Überschriften: Roboto Slab, Gewicht 800, Zeilenhöhe 1,2, Laufweite normal. Hauptschlagzeile 2,25rem (36px) auf Desktop, 1,75rem mobil.
- Zwischenüberschriften: 1,5rem, Gewicht 700, Zeilenhöhe 1,26; Kartentitel 1,125rem bis 1,25rem.
- Text und Oberfläche: Source Sans 3 (Ersatz für eine UI-Sans), 1rem/1,38 für Fließtext, 1,125rem für Teaser, 0,875rem für Meta, Gewichte 400 und 700.
- Rubrikzeile über der Schlagzeile: 0,875rem, Gewicht 700, Versalien nicht nötig, Farbe #5C5A58 oder #E64415.
- Textbreite maximal 600px bzw. 40em, keine Blocksatz-Absätze.

## Abstände und Raster
- Basis 8px: Werte 8, 16, 24, 32, 40, 64px (0,5 / 1 / 1,5 / 2 / 2,5 / 4rem).
- Karteninnenabstand 24px Desktop, 16px mobil; Lücken im Raster 16px, größere Gruppen 24px.
- Inhaltsbreite 1008px (zentriert), Kopfleiste und Navigation laufen über 1280px voll.
- Raster: 12 Spalten, Hauptkarte 8 Spalten plus Nebenspalte 4; Teaser-Reihen zu 3 oder 4 gleich breiten Karten, mobil einspaltig.
- Kopfleiste 80px hoch (mobil 48px), Navigationszeile 56px.

## Layout-Muster
- Oben: orangerote Kopfleiste mit Wortlogo links, Textlink und Anmeldeknopf rechts; darunter weiße Navigationszeile mit Menüsymbol und Rubrikliste.
- Danach Seitengrund in Warmgrau mit einer großen Aufmacherkarte: Rubrikzeile, vierzeilige Slab-Schlagzeile, Teaser, Metazeile, rechts Bildfläche.
- Darunter ein dichter Stapel aus Karten in Reihen; Abschnitte werden durch 1px-Linie #DDDBD9 und eine fette Slab-Zwischenüberschrift getrennt.
- Rubrikblöcke wechseln den Grund: weiß, warmgrau, Hellrosa #FFE5DE, selten tiefschwarz.
- Fußbereich in Warmgrau mit schlichter Linkliste in 0,875rem.

## Komponenten
- Hauptknopf: Fläche #E64415, Text #FFFFFF, Gewicht 700, 1rem, Höhe 44px, Radius 1.5px, Pfeilzeichen rechts.
- Zweitknopf: weiß mit 1px Rand #989694, Text schwarz, gleiche Höhe.
- Kartensymbol-Knopf: rund (50%), weiß, Text oder Symbol in #E64415.
- Karte: #FFFFFF, Radius 8px, Schatten 0 1px 4px rgba(0,0,0,0.1), Innenabstand 24px.
- Eingabefeld: weiß, 1px #989694, Radius 1.5px, 14px Text, Innenabstand links 12px, rechts 48px für ein Symbol.
- Marker: kleines Quadrat #E64415 mit weißem Plus vor Titeln für Bezahlinhalte.
- Fokus: 2px innen liegender Ring in #E64415.
- Links im Text: #811D00, unterstrichen, Gewicht 700.

## Bildsprache
Dokumentarische, rechteckige Fotos mit Radius 1.5px, oft im Format 3:2 oder 16:9, ohne Rahmen. Bei Text auf Bild ein Verlauf von transparent nach Schwarz am unteren Rand. Piktogramme sind einfarbige Linien-Icons (1.5px Strich) in Schwarz oder Signalrot. Runde Avatare oder Autorenporträts 40px, 50% Radius. Platzhalter sind warmgraue Flächen (#DDDBD9) mit dezenter Diagonale.

## Animation
Kaum Bewegung: Farbwechsel von Links und Knöpfen in 150ms ease, Karten heben sich nicht an. Menüs und Dialoge blenden in 200ms ein. Keine Parallaxe, kein Autoplay-Karussell, bei prefers-reduced-motion keine Übergänge.

## Tonfall
Sachlich, präzise, in vollständigen Sätzen. Schlagzeilen sind Aussagen mit konkretem Inhalt, gern mit Zahlen oder einem Zitat in Anführungszeichen. Teaser erklären in ein bis zwei Sätzen den Kern. Meta-Angaben (Lesedauer, Zeit seit Veröffentlichung) knapp und nüchtern. Keine Ausrufezeichen, keine Werbesprache.

## Mach
- Warmgrauen Grund (#F1EFED) mit weißen Karten kombinieren.
- Eine Signalfarbe (#E64415) für Kopfleiste, Hauptknopf und Rubrikzeilen verwenden.
- Slab 800 für Schlagzeilen, Sans für alles andere.
- Radien klein halten: 1.5px bei Knöpfen und Feldern, 8px nur bei Karten.
- Dichte Informationshierarchie: Rubrik, Schlagzeile, Teaser, Meta.
- Trennlinien 1px in #DDDBD9 statt großer Leerräume.

## Mach nicht
- Keine Pillenknöpfe, keine großen Radien über 8px.
- Keine zweite Akzentfarbe neben Orangerot, außer den Rubrikpaaren in kleinen Flächen.
- Keine starken Schatten, keine Glasflächen, keine Verläufe auf Flächen.
- Keine Zierschriften, keine Slab im Fließtext.
- Keine zentrierten Langtexte und keine Textzeilen über 40em.

## Typische KI-Fehler in diesem Stil
- Slab-Überschriften zu leicht (400) setzen; sie brauchen 700 bis 800.
- Weißen Seitengrund statt Warmgrau nehmen, dadurch verschwinden die Karten.
- Das Orangerot als Verlauf oder in vielen Nuancen verwenden statt als einzelnen flachen Ton.
- Knöpfe abrunden oder mit Schatten versehen; sie sind flach mit 1.5px Radius.
- Die Navigationszeile weglassen, obwohl sie die Informationsdichte trägt.
- Rubrikfarben als große Flächen einsetzen statt als kleine Pastell/Dunkel-Paare.
