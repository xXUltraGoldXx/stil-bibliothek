# Stil: Mitternacht leicht

## Kurzbeschreibung und Stimmung
Eine Produkt- und Plattformseite bei Nacht. Der Grund ist fast schwarz mit grünlichem oder tiefblauem Unterton, darauf stehen sehr große, auffallend dünne Schlagzeilen in Weiß. Weiche Lichtflecken aus Verläufen geben Tiefe, ohne laut zu werden. Knöpfe sind weiße Pillen und die einzigen harten Kontraste. Gefühl: souverän, ambitioniert, filmisch, ruhig. Der Stil trägt große Versprechen, ohne zu schreien.

## Farbpalette
- Grund Hauptfläche `#02090a` (Schwarz mit Grünstich), Seitenrand und Fuß `#000000`
- Wechselflächen für Abschnitte: Tiefgrün `#041e18`, Nachtblau `#000a1e`, Petrol `#061a1c`
- Text primär `#ffffff`, sekundär `#9797a2`, Fließtext auf Dunkel `#a1a1aa`, hell abgesetzt `#bdbdca`
- Akzent: Minzgrün `#36f4a4`, sparsam für Kennzahlen, Marker, kleine Labels
- Linien: `rgba(255,255,255,0.1)` mit 1px
- Glühen: radiales Blau `rgba(18,96,255,0.35)` zu transparent bei 50 Prozent; Verlauf Violett `#2c007f` zu Nachtblau `#000a1d`
- Knopf-Weiß `#ffffff` mit schwarzem Text. Keine weiteren Akzentfarben

## Typografie
- Eine Familie: Inter (Google Fonts)
- Hero-Schlagzeile: 6rem (96px) auf Desktop, 3.5rem (56px) mobil, Gewicht 300, Zeilenhöhe 1.08, Laufweite -0.02em
- Sektions-Schlagzeile: 3.5rem (56px), mobil 2.25rem, Gewicht 300, Zeilenhöhe 1.08, Laufweite -0.03em
- Unterüberschrift: 1.5rem bis 2.75rem, Gewicht 300, Laufweite -0.01em
- Lead und Fließtext: 1.125rem (18px) bis 1.25rem, Gewicht 330 bis 420, Zeilenhöhe 1.4
- Navigation und Knöpfe: 1rem, Gewicht 450 bis 550
- Meta und Labels: 0.75rem bis 0.875rem, Gewicht 420, optional Versalien mit Laufweite 0.06em
- Zahlen und Code optional in Monospace-Systemschrift
- Prinzip: Größe und Leichtigkeit statt Fettdruck. Fett kommt praktisch nie vor

## Abstände und Raster
- Container 1100px, seitlicher Seitenrand 90px auf Desktop, 16px mobil
- Abschnitte vertikal 5rem bis 8rem (80 bis 128px), mobil 4rem
- Lücken im Raster: 4rem (64px) zwischen Spalten, 1rem bis 2.5rem in Karten
- Innenabstand Karten 1.5rem bis 2rem, Knöpfe 0.8rem 1.6rem
- Fußbereich 5rem oben und unten, fünfspaltig, mobil einspaltig
- Abschnitte sind meist einspaltige Blöcke mit eingebetteten Zwei- oder Dreier-Rastern

## Layout-Muster
- Kopfzeile: 72px hoch, Logo links, Navigation daneben, rechts Textlink und weiße Pillen-CTA
- Hero: bildfüllende dunkle Fläche mit Verlaufsglühen, Schlagzeile linksbündig im unteren Drittel, Lead darunter, zwei Knöpfe (weiß gefüllt und weiß umrandet) nebeneinander
- Danach beginnt die nächste Fläche mit oberen Rundungen von 20px, als würde eine Karte über das Hero schieben
- Sektionen: große Schlagzeile, darunter Raster aus Karten oder Kennzahlen, Farbwechsel zwischen Schwarzgrün, Nachtblau und Tiefgrün
- Logo-Reihe: kleine, graue Marken-Platzhalter in einer Zeile
- Schlusssektion: große Schlagzeile, ein Knopf, darunter der Fuß

## Komponenten
- Primärknopf: Pille (Radius 9999px), Weiß `#ffffff`, Text `#000000`, Gewicht 500, Höhe 44 bis 56px
- Sekundärknopf: Pille, transparent, 2px weißer Rand, weißer Text
- Textlink: weiß, unterstrichen mobil, mit kleinem Dreieck oder Pfeil als Marker
- Karten: Radius 12px, Fläche `#061a1c` oder halbtransparent weiß 0.05, 1px Rand `rgba(255,255,255,0.1)`
- Eingabefeld: Radius 8px, Fläche `rgba(255,255,255,0.1)`, 1px heller Rand, Text 1rem
- Sektions-Container oben mit 20px Rundung
- Schatten: kaum. Höchstens ein 1px heller Ring `rgba(255,255,255,0.08)` oder ein weicher schwarzer Schatten `0 8px 32px rgba(0,0,0,0.25)` für schwebende Elemente

## Bildsprache
Cineastische, dunkel getönte Fotos und Produktansichten, oft als Vollfläche mit Abdunklung oben und unten. Menschen im Bild, nah und ungestellt. Produktoberflächen erscheinen als helle Fenster auf dunklem Grund. Im Beispiel dienen CSS-Flächen aus Verläufen und Glühpunkten als Platzhalter, ohne Fotos.

## Animation
Sanft und langsam. Einblenden mit leichtem Aufwärtsgleiten (0.6s, ease-out), Hover bei Knöpfen mit Aufhellung (0.2s), Hintergrundvideo oder Verlaufsbewegung im Hero. Keine Sprünge, kein Federn, kein Rotieren.

## Tonfall
Ambitioniert, direkt, persönlich. Anrede in der du-Form, kurze Fragen als Schlagzeile, danach ein ruhiger Lead mit Versprechen. Wenige Worte pro Überschrift (zwei bis neun), keine Fachsprache, keine Ausrufezeichen.

## Mach
- Schlagzeilen groß (3.5rem bis 6rem) und dünn (Gewicht 300)
- Grund fast schwarz mit Grün- oder Blauschimmer, Abschnitte wechseln die Tönung
- Genau eine weiße Pillen-Primäraktion pro Sichtfeld
- Verlaufsglühen als Tiefe statt Schatten
- Obere Rundung 20px bei Sektionen, die über die vorherige schieben
- Minzgrün nur für Zahlen und kleine Marker
- Großzügiger Weißraum von 5rem bis 8rem

## Mach nicht
- Keine fetten Überschriften, kein Gewicht über 550
- Kein reines Schwarz als einzige Fläche, es braucht die Grün- und Blautöne
- Keine kantigen Knöpfe, keine bunten Knopffarben
- Keine hellen Sektionen im Wechsel mit dunklen
- Keine harten Schlagschatten und keine bunten Verläufe über mehrere Farben
- Keine Emoji und keine Icon-Kreise in Bunt

## Typische KI-Fehler in diesem Stil
- Überschriften in Gewicht 700, wodurch die leichte Eleganz verloren geht
- Reines `#000` überall, ohne grünliche oder bläuliche Tönung und ohne Glühen
- Rechteckige oder nur leicht gerundete Knöpfe statt vollrunder Pillen
- Minzgrün als Flächen- oder Knopffarbe, statt als sparsamer Akzent
- Zentrierte Layouts mit Kleintext; der Stil lebt von linksbündigen, großen Schlagzeilen
- Zu viele Karten mit sichtbaren Schatten statt feiner heller Ränder
- Zu enge Zeilenhöhe im Fließtext; sie bleibt bei etwa 1.4
