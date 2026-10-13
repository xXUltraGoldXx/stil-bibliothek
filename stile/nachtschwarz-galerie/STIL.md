# Stil: Nachtschwarz Galerie

## Kurzbeschreibung und Stimmung
Eine Ausstellung im abgedunkelten Raum: fast schwarze Flächen, darauf großformatige Motive, wenig Text, ruhige Schlagzeilen im Regelgewicht. Die Oberfläche ist präzise und leise, Luxus entsteht durch Weite, Kontrast und Zurückhaltung. Einzelne helle Karten mit starken Rundungen (Dialoge, Panels) setzen Akzente auf dem dunklen Grund. Gefühl: Automobil-Showroom bei Nacht, technisch, hochwertig, ohne Lautstärke.

## Farbpalette
- Leinwand dunkel `#010205`, Reinschwarz `#000000` für Überlagerungen und Primärknöpfe
- Fläche dunkel `#19191a` für Karten und Panels auf Schwarz
- Text auf Dunkel `#fafbff`, gedämpft `rgba(246,246,248,0.56)`, leise `rgba(246,246,248,0.45)`
- Helle Fläche `#f1f1f4` und Weiß `#ffffff` für Dialoge und helle Abschnitte, Text darauf `#010205`
- Sekundärknopf hell `#dcdce0`, auf Dunkel Milchglas `rgba(107,107,112,0.23)` mit 32px Weichzeichnung
- Link- und Fokusfarbe `#1a44ea` (hell) bzw. `#178bff` (dunkel), auf Schwarz auch helles Lila-Blau `#9e9eff`
- Statusfarben nur funktional: Erfolg `#10c47f`, Warnung `#f4882a`, Fehler `#fc4040`
- Bildabdunklung: Verlauf von `rgba(0,0,0,0.8)` am Rand zu transparent, damit Text lesbar bleibt
- Keine Akzentfarbe als Flächenfarbe. Farbe kommt aus dem Motiv.

## Typografie
- Schmalgrotesk: Barlow Semi Condensed (Google Fonts), Gewichte 400 und 600. Fallback Arial Narrow, Arial, sans-serif
- Fließtext 1rem, Zeilenhöhe 1.5 (24px), Gewicht 400, Laufweite normal
- Meta und Knopftext 0.875rem, Zeilenhöhe 1.55
- Hero-Schlagzeile fluid bis 4.2rem (ca. 67px Desktop, 35px Mobil), Zeilenhöhe 1.2, Gewicht 400, nicht fett
- Schlagzeilen H2 zwischen 1.8rem und 3.2rem, Gewicht 400, Zeilenhöhe 1.2
- Gewicht 600 nur für kurze Hervorhebungen und Navigationszustände
- Keine Versalien, keine gesperrte Schrift. Sentence case, die Schmalheit der Schrift trägt den Charakter

## Abstände und Raster
- Seitenrand Desktop 124px (ca. 7.75rem), Mobil 16px bis 30px
- Skala statisch: 4, 8, 16, 32, 48, 80px. Fluid: 16 bis 36px (Elemente), 32 bis 76px (Gruppen), 80 bis 200px (Abschnitte)
- Innenabstand Knöpfe 14px 28px, Dialoge 58px innen auf Desktop, 33px auf Mobil
- Lücke zwischen Knöpfen 16px, zwischen Karten 12 bis 28px
- Inhaltsbreite bis 1032px zentriert, Hero und Bildflächen vollbreit
- Textspalten höchstens 70 Zeichen

## Layout-Muster
- Kopfzeile transparent über dem Hero: links Menü, Mitte Markenzeichen, rechts zwei Icons
- Hero vollflächig dunkel, Motiv mittig, Schlagzeile unten links, darunter ein einzelner Milchglas-Knopf, unten rechts ein runder Pausenknopf
- Abschnitte als vollbreite Bildbühnen mit je einer Schlagzeile und einem Link, Wechsel zwischen reinem Schwarz und `#19191a`
- Kartenreihen mit zwei bis drei großen Karten, Radius 24px, Bild oben, wenig Text
- Footer sehr hoch, `#010205`, mehrspaltige Linklisten in gedämpftem Weiß

## Komponenten
- Primärknopf: Fläche `#000000` auf hellem Grund bzw. `#fafbff` auf dunklem Grund, Radius 12px, Höhe 56px, Text 1rem im Regelgewicht
- Sekundärknopf: `#dcdce0` auf Hell oder Milchglas auf Dunkel, gleiche Maße
- Dialog und Panel: Weiß, Radius 32px, Schatten `0 8px 40px rgba(0,0,0,0.16)`
- Karten: Radius 24px, Fläche `#19191a`, kein Rand
- Runde Icon-Knöpfe: 56px Durchmesser, Milchglas, Radius voll
- Links: Unterstreichung auf hellem Grund, auf Dunkel Farbe `#9e9eff`
- Fokus: 2px Ring `#1a44ea` mit 2px Abstand
- Schatten sparsam: `0 3px 8px`, `0 4px 16px`, `0 8px 40px`, je mit 16% Schwarz

## Bildsprache
Großflächig, dunkel, filmisch ausgeleuchtet, Motiv vor schwarzem Grund mit warmen Lichtkanten. Bilder laufen randlos bis zum Viewport. Texte liegen auf Verlaufsabdunklung. Im Beispiel sind es CSS-Verläufe aus radialen Lichtflecken auf Schwarz.

## Animation
Ruhig und gleichmäßig: Dauern 0.25s (Hover), 0.4s (Panels), 0.6s (Einblenden), 1.2s (große Bildwechsel), Kurve `cubic-bezier(.25,.1,.25,1)`. Bildbühnen dürfen automatisch wechseln, brauchen aber einen sichtbaren Pausenknopf. Weichzeichnung von Milchglas wird sanft eingeblendet. Bewegung respektiert `prefers-reduced-motion`.

## Tonfall
Souverän, knapp, sachlich. Kurze Sätze, kaum Ausrufe, keine Superlative. Schlagzeilen benennen ein Ding oder eine Haltung in wenigen Wörtern. Knopftexte sind Verben wie "Mehr entdecken".

## Mach
- Dunkle Flächen dominieren, helle Karten nur gezielt
- Schlagzeilen im Regelgewicht 400, groß und luftig
- Radien konsequent: 12px Knöpfe, 24px Karten, 32px Dialoge
- Milchglas statt dicker Rahmen
- Sichtbarer Fokusring und Pausenknopf bei Bewegung
- Viel leerer Raum um ein einzelnes Motiv

## Mach nicht
- Keine bunten Verläufe, keine Neonfarben
- Keine fetten Schlagzeilen und keine Versalien
- Keine scharfen Ecken bei Karten und Knöpfen
- Keine dicken Rahmen oder harten Schlagschatten
- Keine dichten Kachelraster mit viel Text
- Keine reinweiße Seite als Hauptgrund

## Typische KI-Fehler in diesem Stil
- Reines `#000` überall, ohne die Abstufung mit `#010205` und `#19191a`, wodurch Karten verschwinden
- Schlagzeilen in Fett 700, obwohl der Stil im Regelgewicht lebt
- Eine auffällige Akzentfarbe (Rot, Gold) als Knopffläche ergänzt
- Breite Standardschrift statt einer Schmalgrotesk, dadurch geht die Eleganz verloren
- Knöpfe als Pillen mit vollem Radius, obwohl 12px gilt
- Text direkt auf Bildern ohne Abdunklungsverlauf
- Zu viele Karten und zu wenig Leerraum
