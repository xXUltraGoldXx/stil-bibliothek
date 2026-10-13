# Stil: Kino Glut

## Kurzbeschreibung und Stimmung
Dunkel, filmisch, direkt. Reines Schwarz als Bühne, dahinter eine schräg gekachelte Wand aus abgedunkelten Motiven, davor eine zentrierte Riesen-Headline in Weiß und ein einziger, leuchtend roter Knopf. Der rote Akzent `#d4161f` ist das Signal, alles andere tritt zurück. Dazu ein Schimmer aus Nachtblau und Weinrot an den Rändern und ein gebogener, rot glühender Horizont zwischen Hero und Folgeabschnitt. Gefühl: Vorspann im Kinosaal, ein Klick bis zum Ziel.

## Farbpalette
- Grund: Schwarz `#000000`; Flächen in Stufen `#232323`, `#2d2d2d`; halbtransparente Leiste `rgba(22,22,22,.7)`
- Text: Weiß `#ffffff`, gedämpft `rgba(255,255,255,.7)`, schwach `rgba(255,255,255,.5)`
- Akzent: Signalrot `#d4161f`, Hover etwas dunkler `#ad1019`; Glut-Rot für Schein `#6f181d` und `#461518`
- Karten-Verlauf: 149 Grad von Nachtblau `#192247` nach Dunkelpflaume `#210e17`
- Banner-Verlauf: 91 Grad von `#261733` nach `#151a3f`
- Blauer Lichtkegel oben: `radial-gradient` aus `rgba(64,97,231,.4)`, nur als feiner Schein
- Linien und Feldränder: `1px solid rgba(128,128,128,.7)`
- Helle Fläche `#f2f2f2` nur für Hinweis-Leisten (zum Beispiel Cookie-Hinweis) mit dunklem Text `#333333`

## Typografie
- Eine Groteskschrift für alles: Figtree (Google Fonts), Gewichte 400, 500, 700
- H1: 3.5rem (Mobil 2rem), Gewicht 700, Zeilenhöhe 1.25, zentriert, Weiß
- H2: 1.5rem (Mobil 1.125rem), Gewicht 500; auf Feature-Abschnitten größer bis 3rem, Gewicht 700
- Lead-Zeile unter der H1: 1.25rem, Gewicht 500
- Fließtext 1rem, Gewicht 400, Zeilenhöhe 1.5; Kleintext 0.8125rem bis 0.875rem
- Knöpfe: 1.5rem Gewicht 500 im Hero, 0.875rem Gewicht 500 im Kopfbereich
- Keine Versalien, keine Laufweiten-Spielereien, normale Laufweite

## Abstände und Raster
- Leiter in px: 2, 4, 8, 12, 16, 24, 32, 48, 72
- Innenabstand Hauptknopf 12px 24px (Mobil 8px 16px), kleiner Knopf 4px 16px
- Karten-Innenabstand 24px, Abschnitte 48 bis 72px vertikal, Inhalt max. 1152px
- Kleine Lücken zwischen Listenzeilen: 2px bis 8px
- Hero-Inhalt in schmaler Spalte (Text etwa 588px, Formularzeile bis 590px), zentriert
- Feature-Abschnitte zweispaltig (Text und Bildfläche), Mobil einspaltig

## Layout-Muster
- Kopfzeile: Wortmarke links, rechts Sprachwahl (Umriss) und kleiner roter Knopf
- Hero: Vollbreite Motivwand schräg gedreht und abgedunkelt, Schwarzverlauf von unten, dazu zentrierte H1, Lead, Satz mit Aufforderung, Formularzeile aus Eingabefeld und rotem Großknopf
- Übergang: gebogener Horizont (obere Rundung, 2 bis 3px roter Rand, darunter blauer Schein)
- Info-Banner: breite Karte mit Nachtblau-Verlauf, Radius 16px, Symbol links, Text und Sekundärknopf
- Feature-Zeilen: Text und Motivfläche im Wechsel
- Frageliste: aufklappbare Zeilen auf `#2d2d2d`, 8px Abstand dazwischen
- Abschluss: Fußzeile in gedämpftem Weiß

## Komponenten
- Primärknopf: Fläche `#d4161f`, Text weiß, Radius 4px, Gewicht 500, Pfeil-Symbol rechts im Hero; Hover `#ad1019`
- Sekundärknopf: `rgba(109,109,110,.7)` bis `#2d2d2d`, weißer Text, Radius 4px
- Eingabefeld: Hintergrund `rgba(22,22,22,.7)`, Rand `1px solid rgba(128,128,128,.7)`, Radius 4px, Höhe etwa 56px, Beschriftung schwebt im Feld (oben 24px Innenabstand, unten 8px)
- Sprachwahl: Umriss 1px grau, Radius 4px, Text 1rem
- Karten: Radius 16px, kein harter Schatten; höchstens `0 0 18px rgba(0,0,0,.2)`
- Radien-Skala: 2px, 4px, 8px, 16px
- Fokus: weißer 2px-Ring, gut sichtbar

## Bildsprache
Filmische Plakat-Kacheln, stark abgedunkelt, gedreht um etwa minus 12 Grad und so dicht gesetzt, dass eine Wand entsteht. Farben gedeckt: Rot, Blau, Pflaume, Erdtöne. Darüber immer Schwarzverlauf, damit Text lesbar bleibt. Kleine verspielte Symbole (3D-artig, rot) als Blickfang. Im Beispiel: CSS-Verläufe als Kacheln, SVG als Symbol, keine Fotos.

## Animation
Zurückhaltend. Hover auf Knöpfen 200ms Farbwechsel, Aufklappen der Fragezeilen 250ms, sanftes Einblenden der Hero-Wand. Keine Sprünge, kein Wackeln, keine Parallax-Effekte. `prefers-reduced-motion` respektieren.

## Tonfall
Kurz, klar, einladend, Sie-Form. Gegenüberstellung in zwei knappen Sätzen als Slogan, danach ein konkreter Preis- oder Nutzenhinweis und eine direkte Frage mit nächstem Schritt. Keine Fachsprache, keine Ausrufezeichen-Ketten.

## Mach
- Schwarzer Grund, genau ein Rot `#d4161f` für die Hauptaktion pro Ansicht
- H1 zentriert, Gewicht 700, Weiß; Lead darunter in Gewicht 500
- Formularzeile aus Feld und Großknopf auf gleicher Höhe, Mobil untereinander
- Motivwand immer mit Schwarzverlauf abdunkeln, Text mindestens 4.5:1 Kontrast
- Radius klein halten: 4px für Knöpfe und Felder, 16px für große Karten
- Gebogenen roten Horizont als Trenner zwischen Hero und Rest einsetzen
- Fragelisten mit 8px Abstand und `#2d2d2d`-Zeilen

## Mach nicht
- Keine Pillenknöpfe, keine runden 28px-Karten
- Kein zweites kräftiges Akzentrot oder bunte Mehrfarb-Knöpfe
- Keine hellen Seitenflächen; Hellgrau nur für Hinweisleisten
- Keine Serifenschrift, keine Versalien-Labels
- Keine harten Schlagschatten, kein Glas-Effekt
- Keine linksbündige Hero-Headline

## Typische KI-Fehler in diesem Stil
- Grund als Grau `#111` statt echtes Schwarz `#000`, dadurch fehlt die Tiefe
- Rot überall verwendet (Überschriften, Rahmen, Icons), statt nur für die Hauptaktion
- Motivwand ohne Abdunklung: Text auf bunten Kacheln, schlecht lesbar
- Knöpfe als Pillen oder mit Verlauf und Glow, statt flach mit 4px Radius
- Hero linksbündig oder mit Zwei-Spalten-Raster, statt zentriert und schmal
- Blau-Violett-Verlauf als Seitengrund statt als kleiner Schein am Rand
- Formularzeile auf Mobil nebeneinander gequetscht, Knopf zu klein
