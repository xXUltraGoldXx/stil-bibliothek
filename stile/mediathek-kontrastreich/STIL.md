# Stil: Mediathek kontrastreich

## Kurzbeschreibung und Stimmung
Eine Video- und Vortragsbibliothek: sachlich, offen, neugierig. Weiße und hellgraue Flächen tragen die Orientierung, tiefschwarze Abschnitte geben Inhalten eine Bühne. Große, eng gesetzte Inter-Schlagzeilen treffen auf kleine, versale Navigation und genau ein Signalrot. Die Bilder sind die Hauptdarsteller, die Oberfläche bleibt zurückhaltend. Gefühl: Kulturprogramm, Wissenskanal, kuratierte Mediathek.

## Farbpalette
- Grund: Weiß `#ffffff` (Hauptfläche), Hellgrau `#f6f6f6` für abgesetzte Bänder
- Bühne: Fast-Schwarz `#121212` für Sektionen mit Bild-Schwerpunkt, Anthrazit `#262626` für Chips und Kacheln darauf, reines Schwarz `#000000` nur für Bildflächen
- Text: Tinte `#121212`, sekundär `#696969`, Meta `#767676`, auf Dunkel Weiß `#ffffff` und gedämpftes Grau `#b5b5b5`
- Signal: Rot `#de1c34` für Rubrik-Labels, Mitgliedschafts-Knopf (Fläche `#d91e18`) und Hervorhebungen. Rot nie als Großfläche
- Linien: `#d9d9d9` hell, `rgba(18,18,18,.16)` fein, auf Dunkel `#4d4d4d`
- Ein seltener Blau-Ton `#2763ff` ist nur für Fokus und Fortschritt gedacht

## Typografie
- Eine Familie: Inter (Google Fonts), Gewichte 400, 600, 700
- Hero-Schlagzeile: 2.5 bis 3.5rem, Gewicht 700, Zeilenhöhe 1.1, Laufweite -0.04em
- Großer Abschnittstitel auf Schwarz: bis 5.25rem (84px), Gewicht 600, Laufweite -0.04em, Zeilenhöhe 1
- Kachel-Titel: 1.125 bis 2rem, Gewicht 600, Laufweite -0.02em, Zeilenhöhe 1.1
- Fließtext: 0.875 bis 1rem, Zeilenhöhe 1.3, Farbe `#696969` oder `#121212`
- Navigation und Rubriken: 0.75 bis 0.875rem, Versalien, Gewicht 600, Laufweite 0.04em
- Meta (Sprecher, Aufrufe, Alter): 0.75rem, Gewicht 400, `#767676`
- Viele kleine Größen (12, 14, 18 px) und wenige sehr große (32, 84 px): kein weicher Verlauf dazwischen

## Abstände und Raster
- Seitenbreite max. 1280px, Innenrand 40px Desktop, 16 bis 24px mobil
- Spaltenraster mit 4 gleichen Kacheln, Lücke 40px, dazwischen 1px Trennlinie `#d9d9d9`
- Abstandsskala: 4, 8, 12, 16, 20, 24, 40, 56, 64px; 20px ist das häufigste Innenmaß
- Sektionen mit 56 bis 64px vertikalem Abstand, Kachelinhalt 8 bis 12px
- Hero: Text links und Bild rechts etwa 1:1, Bild im Format 16:9

## Layout-Muster
- Kopfleiste weiß, 56 bis 64px hoch, unten 1px Linie: Wortmarke links, versale Navigation rechts, Mitgliedschafts-Knopf in Rot, Such-Symbol
- Hero: Rubrik in Rot, große Schlagzeile, dreizeiliger Anreißer, Sprecher und Meta, rechts großes Bild mit Dauer-Marke unten rechts
- Kachelreihe direkt unter dem Hero, getrennt von dünner Linie
- Dunkles Band: riesiger Titel links, "Alle ansehen" als Textlink rechts, darunter eine Reihe Themen-Chips und horizontal angeordnete Kacheln
- Mobil: eine Spalte, Bild randlos über die volle Breite, Rubrik und Titel darunter

## Komponenten
- Dauer-Marke: kleines Rechteck unten rechts im Bild, Fläche `rgba(0,0,0,.7)`, weiße Schrift 0.6875rem, Gewicht 700, Radius 2px
- Chips: Fläche `#262626`, weißer Text 600, Radius 4px, Innenabstand 8px 16px; aktiv Weiß mit dunklem Text
- Primärknopf: Rot `#d91e18`, weißer Text, Versalien 0.8125rem, Gewicht 700, Radius 4px, Innenabstand 10px 16px
- Sekundärknopf: 1px Rahmen in Tinte, transparent, gleiche Schrift
- Runde Icon-Knöpfe (24 bis 40px) für Pfeile und Suche, Radius 50%
- Karten: ohne Rahmen und Schatten, nur Bild, Rubrik, Titel, Meta. Schatten allenfalls ein ganz weicher 0 2px 4px bei schwebenden Elementen

## Bildsprache
Dokumentarische Bühnen- und Studioaufnahmen: Sprecher als Halbfigur, warmes Licht, dunkler oder farbiger Hintergrund. Alle Bilder im Format 16:9, randlos oder mit 4px Radius. Im Beispiel ersetzen CSS-Verläufe in Schwarz, Violett, Orange und Blau die Fotos, ergänzt durch eine schlichte Silhouette aus SVG.

## Animation
Zurückhaltend. Hover auf Kacheln: Titel unterstrichen oder Bild 1.03-fach, 0.2s ease. Karussell mit Pfeilen und Fortschrittsbalken, Übergang 0.3s. Keine Parallax-Effekte, keine springenden Elemente.

## Tonfall
Neugierig, klar, einladend. Kurze Aussagetitel, Anreißer aus ein bis drei Sätzen mit konkretem Detail. Meta-Zeilen nüchtern: Sprecher, Aufrufe, Alter, Dauer. Keine Superlative.

## Mach
- Weiße Orientierung und schwarze Bühnenbänder im Wechsel
- Ein Rot, sparsam: Rubrik, Mitgliedschaft, Hervorhebung
- Enge Laufweite bei Schlagzeilen, versale kleine Navigation
- Dauer-Marke auf jedem Videobild
- Sehr großer Abschnittstitel auf Schwarz mit kleinem Textlink gegenüber
- Kleine Radien: 2px und 4px

## Mach nicht
- Keine Pastellfarben, keine Verläufe auf Flächen
- Keine großen Radien oder Pillenformen bei Knöpfen
- Keine schweren Schatten, keine Glasflächen
- Keine zweite Schriftfamilie
- Kein Rot in Flächen größer als ein Knopf

## Typische KI-Fehler in diesem Stil
- Laufweite bleibt normal, wodurch die Schlagzeilen weich statt straff wirken
- Dunkler Bereich wird mittelgrau statt `#121212`, dadurch fehlt der Bühnenkontrast
- Knöpfe werden zu runden Pillen mit Schatten
- Dauer-Marke und Rubrik-Label fehlen, die Kacheln wirken dann wie Blogkarten
- Rot wird für Überschriften, Links und Ränder gleichzeitig benutzt
- Alle Texte gleich groß: die starke Spreizung zwischen 12 und 84px geht verloren
