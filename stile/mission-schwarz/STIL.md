# Stil: Mission Schwarz

## Kurzbeschreibung und Stimmung
Ein Nachrichten- und Forschungsportal im Dunkeln: Kopfzeile und Fuß in reinem Schwarz, dazwischen eine helle Lesefläche. Der Einstieg ist eine vollflächige Bildbühne mit riesiger weißer Schlagzeile, kurzem Lead und einem roten Knopf. Darunter eine Zeile mit drei Verweisen, die durch Mono-Etiketten in Versalien gegliedert sind. Gefühl: Missionskontrolle, Sachlichkeit, Weite, Vertrauen. Die Gestaltung ist flach, ohne Schatten und ohne Rundungen außer bei kleinen Kreis-Markern.

## Farbpalette
- Schwarz `#000000` für Kopfzeile, Hero-Bühne und Fuß
- Nachtgrau `#1b1b21` für dunkle Kästen, `#33333a` für feine Flächen
- Papierweiß `#ffffff` und Hellgrau `#f6f6f6` für Lesebereiche
- Text auf hell `#1b1b1b`, auf dunkel `#ffffff`
- Gedämpft auf dunkel: `#b9b9bb`, `#959599`, `#58585b`; auf hell `#717173`
- Genau ein Signalrot `#cc4038` für den Haupt-Knopf, Pfeil-Kreise und Live-Marke
- Verlauf nur als Abdunklung über Bildern: 66° von `#000000` nach transparent, Ende bei 99 %
- Linien: 1px `rgba(255,255,255,.2)` auf Schwarz

## Typografie
- Schlagzeilen und Navigation: Inter (Google Fonts), Gewicht 700, Zeilenhöhe 1.05
- Fließtext: Public Sans (Google Fonts), 1rem, Gewicht 400, Zeilenhöhe 1.65 (26px)
- Etiketten: DM Mono (Google Fonts), 0.7rem, Gewicht 500, Versalien, Laufweite 3.5px
- Hero-Titel 4.5rem Desktop, 2.25rem mobil; Abschnittstitel 3rem Desktop, 2.25rem mobil; Kartentitel 1.375rem; Lead 1.1rem
- Gewichte: 400 für Text, 700 für alles Betonte, 800 sehr sparsam
- Titel linksbündig, nie zentriert, nie Versalien

## Abstände und Raster
- Seitenrand 1.5rem (24px) überall, Kopf 16px 24px, Fuß 56px 24px
- Inhaltsbreite bis 1200px, Lesespalte 38rem
- Abschnitte vertikal 4.5rem (72px), Innenabstand von Karten 1.5rem
- Drei gleich breite Spalten für Mission-Verweise und Karten, Lücke 1rem
- Mobil: eine Spalte, Verweise untereinander mit dünner Linie dazwischen

## Layout-Muster
- Kopfzeile schwarz: links Menü und Suchfeld, Mitte Markenzeichen, rechts zwei bis drei Navigationspunkte mit Chevron und eine Live-Marke
- Hero: volle Breite, Mindesthöhe 40rem, Bild-Platzhalter mit Verlauf von links, Text unten links
- Unter dem Hero: Dreierleiste aus Etikett plus Titel mit rotem Pfeil-Kreis, obere Linie je Eintrag
- Hellabschnitt "Aktuelles": großer Titel links, kleiner Verweis mit Pfeil rechts, darunter Kartenraster auf Hellgrau
- Dunkler Zahlenabschnitt in Nachtgrau, Fuß in Schwarz mit mehrspaltigen Linklisten

## Komponenten
- Haupt-Knopf: Fläche `#cc4038`, weiße Schrift Inter 700 1.1rem, Radius 4px, Padding 0.75rem 1.25rem; mobil volle Breite
- Pfeil-Marker: Kreis 1.25rem, Radius 50%, Rot, weißer Pfeil
- Live-Marke: 1px roter Rand, Mono 0.7rem, Versalien
- Suchfeld: schwarz, 1px Rand `#565c65`, Radius 0, Schrift 0.94rem, Padding 0 8px
- Karten: weiß auf Hellgrau, kein Rand, keine Schatten, Radius 0, Bildfläche oben, darunter Etikett und Titel
- Pause-Knopf: schwarzer Kreis 3rem mit weißem Symbol
- Links: weiß auf Dunkel, unterstrichen erst beim Hover

## Bildsprache
Weite, kühle Fotografie mit großer Tiefe: Ozean, Himmel, Technik im Gegenlicht, wenig Menschen, kein Stock-Look. Jedes Bild bekommt links eine Abdunklung für Text. Im Beispiel sind Bildflächen CSS-Verläufe in Blau-, Grau- und Schwarztönen mit einfachen SVG-Formen.

## Animation
Ruhig und funktional. Hero-Wechsel mit Überblendung 0.6s, Ladekreis um das Vorschaubild, Hover auf Pfeil-Markern leichter Versatz um 3px in 0.2s. Keine Parallax-Effekte, keine springenden Elemente.

## Tonfall
Sachlich, berichtend, im Präsens oder Perfekt, mit Uhrzeit, Ort und Zahl. Titel nennen Ereignis und Subjekt in wenigen Wörtern. Knöpfe sind kurze Handlungen wie "Mehr lesen". Keine Superlative.

## Mach
- Schwarz als Grundfläche für Kopf, Hero und Fuß, Weiß für Lesebereiche
- Titel in Inter 700 sehr groß, direkt auf dem Bild
- Mono-Etiketten in Versalien mit 3.5px Laufweite über jedem Verweis
- Rot nur für Haupt-Knopf, Pfeil-Kreise, Live-Marke
- Dünne Linien `rgba(255,255,255,.2)` zur Gliederung
- Schatten komplett weglassen

## Mach nicht
- Keine Karten mit Schatten oder großen Radien
- Keine zweite Akzentfarbe, kein Blau-Violett-Verlauf
- Keine zentrierten Titel und keine Versalien in Schlagzeilen
- Keine Serifenschrift
- Keine Emoji, keine bunten Icon-Kacheln
- Kein heller Hero mit dunkler Schrift

## Typische KI-Fehler in diesem Stil
- Rot als Fläche für ganze Abschnitte statt nur für Knopf und Marker
- Hero ohne Abdunklung, sodass weiße Schrift auf hellem Bild kaum lesbar ist
- Mono-Etiketten ohne Versalien und ohne weite Laufweite
- Abgerundete Karten mit weichem Schatten statt flacher Kästen
- Titel zu klein (unter 2.25rem) und dadurch ohne Bühnenwirkung
- Auf dem Handy bleibt die Dreierleiste nebeneinander und läuft über
