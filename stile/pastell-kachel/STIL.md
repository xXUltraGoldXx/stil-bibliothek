# Stil: Pastell Kachel

## Kurzbeschreibung und Stimmung
Ein heller, freundlicher Shop-Stil. Die Basis ist reines Weiß mit fast schwarzem Text (#0b0b0b). Darauf liegen große, flächige Pastellblöcke in Rosa (#fadadd) und Flieder (#fab7fc). Überschriften stehen in kräftigem, geometrischem Sans, gern rot (#e20000) und in Versalien. Aktionen sind tiefgrün (#12504c) und als Pillen geformt. Eine schmale Ankündigungsleiste in Magenta (#dd004f) sitzt über allem. Bilder sind abgerundete Kacheln mit zentrierter, fetter Beschriftung darunter. Die Stimmung ist lebendig, appetitlich und unkompliziert, nie edel-zurückhaltend und nie technisch.

## Farbpalette
- Papier: #ffffff (Hauptfläche, Kopfzeile)
- Hellgrau: #f8f8f8 und #fafafa (ruhige Zwischenflächen)
- Tinte: #0b0b0b (Text), #141414 (Fließtext), #3e3e3e (sekundär), #666666 (Meta)
- Rosa-Pastell: #fadadd (Fußzeile, Bänder, Karten)
- Flieder-Pastell: #fab7fc (Akzentband, Hervorhebung)
- Aktionsgrün: #12504c, Hover #1b7a74, Text darauf #ffffff
- Magenta: #dd004f (Ankündigungsleiste, Sekundärknopf #f91f64)
- Display-Rot: #e20000 (Überschriften, Preise, Aktionstexte)
- Dunkles Weinbraun für Text auf Rosa: #5a2830
- Schwarz #000000 nur für Vollbild-Medienflächen und Outline-Knöpfe
Gewichtung: etwa 75 % Weiß und Hellgrau, 15 % Pastell, 10 % Grün, Magenta, Rot und Schwarz.

## Typografie
Display: eine Futura-artige Schrift, Jost (Google Fonts). Gewicht 700, Versalien für Bandüberschriften, Zeilenhöhe 1.25.
Text und Navigation: Work Sans, Gewichte 400, 500, 600.
Akzente (Kategorienamen, Zwischenüberschriften): Rubik 500 bis 700 oder ersatzweise Work Sans 700.
Größen: H1 und Band-Headline clamp(1.75rem, 4vw, 2.6rem); H2 1.68rem (26.9px); H3 1.44rem; Kategorie-Label 1.15rem bei 700; Fließtext 0.94rem (15px) mit Zeilenhöhe 1.6 und Laufweite 0.1px; Navigation 0.9rem; Meta und Badges 0.75rem mit Laufweite 0.5px, Versalien.
```css
h2 { font-family: "Jost", sans-serif; font-weight: 700; color: #e20000; }
```

## Abstände und Raster
Inhaltsbreite maximal 1440px, Seitenrand 60px am Desktop, 20 bis 24px mobil. Innenabstände kommen aus der Reihe 4, 10, 13, 15, 20, 55, 60px. Lücken 10px zwischen Kleinteilen, 20px zwischen Kacheln. Abschnitte trennen 48 bis 80px vertikal. Kategorie-Raster: sechs Spalten am Desktop (Kachel ca. 160px breit), drei Spalten bei Tablet, zwei mobil. Kopfzeile 70px hoch, Ankündigungsleiste 50px (mobil 41px). Fußzeile mit 48px oben, 20px seitlich, 24px unten.

## Layout-Muster
- Kopfzeile: Menü-Symbol links, Wortmarke mittig, Symbole für Suche, Konto und Warenkorb rechts, Weiß, 70px.
- Ankündigungsleiste in Magenta mit kurzem Text und Mini-Pille.
- Hero als Vollbreiten-Bild mit linksbündigem Textblock: Badge, große Headline, Unterzeile, Pillen-Knopf.
- Reihe runder Bildkacheln mit fetter Beschriftung.
- Pastellband mit zentrierter roter Versal-Headline.
- Produktraster mit Karten, darunter Erklärabschnitte als Zweispalter (Bild und Text im Wechsel).
- Rosa Fußzeile mit mehrspaltigen Linklisten.

## Komponenten
- Primärknopf: Hintergrund #12504c, Text #fff, Gewicht 700, 0.94rem, Radius 30px, Padding 13px 28px.
- Sekundärknopf: Magenta #f91f64 oder Outline mit 1px Rand in Grün, Hover mit Grün bei 20 % Deckung.
- Badge: Pille in #e20000, weißer Text, 0.75rem, Versalien.
- Bildkachel: Radius 8 bis 12px, Format 1:1 bis 4:5, Label darunter zentriert, 700.
- Karte: weiß oder #f8f8f8, Radius 12px, 1px Rand #e2e2e2, Schatten 0 4px 14px rgba(0,0,0,.18) nur bei Hover.
- Overlay oder Dialog: Radius 8px, Schatten 0 32px 68px rgba(0,0,0,.3).
- Eingabe: transparent, 2px Rand #c1c1c1, Radius 5px.

## Bildsprache
Warme, farbige Lifestyle-Fotos mit Menschen, Händen und Schalen; kräftige, gesättigte Hintergründe hinter Produkten. Gerundete Ecken, kein harter Anschnitt. Auf Hero-Bildern liegt ein Verlauf von unten (schwarz 55 % zu transparent bei 65 %), damit weißer Text lesbar bleibt. Als Platzhalter: Flächen in Pastell mit einfachen SVG-Formen (Kreis, Schale, Blatt).

## Animation
Zurückhaltend: Hover-Übergänge 150 bis 200ms ease für Farbe und Schatten, Kacheln heben sich um 2 bis 4px. Ein kurzes Einblenden beim Laden (Overlay in Schwarz, dann weich ausgeblendet). Keine Dauerbewegung außer optional einem Karussell mit manueller Steuerung.

## Tonfall
Direkt, duzend, kurz, mit Aufforderung und leichter Dringlichkeit in Leisten (begrenzte Aktion, jetzt sichern). Headlines als kurze Aussagesätze in Versalien. Beschreibungen konkret und sinnlich, ohne Fachjargon.

## Mach
- Weiß als Grundfläche, Pastell in großen, ruhigen Blöcken.
- Rote Display-Headlines in Jost 700, im Band gern in Versalien.
- Aktionen als grüne Pillen mit Radius 30px.
- Kategorien als Kachelreihe mit fetter, zentrierter Beschriftung.
- Magenta nur für die Leiste und seltene Sekundäraktionen.
- Mobil: zwei Kachelspalten, Seitenrand 20 bis 24px, Menü hinter Symbol.

## Mach nicht
- Keine dunklen Seitenhintergründe, außer als Medienfläche.
- Keine harten Ecken an Knöpfen und Bildkacheln.
- Kein Verlauf als Dekoration auf Flächen und keine Neonfarben.
- Keine Serifenschrift.
- Nicht mehr als zwei Pastelltöne pro Bildschirm.
- Keine schweren, großen Schatten auf normalen Karten.

## Typische KI-Fehler
- Das Rot als Fließtextfarbe verwenden. Es gehört nur auf Headlines, Preise und Badges.
- Grün und Magenta gleichwertig mischen. Grün ist Standardaktion, Magenta die Ausnahme.
- Pastellflächen zu blass oder grau anlegen. Rosa und Flieder müssen deutlich gesättigt bleiben.
- Knöpfe mit 4px Radius statt Pillenform bauen.
- Überschriften in einer neutralen Systemschrift statt einer geometrischen Display-Schrift setzen.
- Kachel-Labels linksbündig und dünn setzen statt zentriert und fett.
- Alles mit Schatten und Verläufen aufladen, obwohl der Stil flach und hell ist.
