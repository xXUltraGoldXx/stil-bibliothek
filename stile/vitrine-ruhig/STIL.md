# Stil: Vitrine ruhig

## Kurzbeschreibung und Stimmung
Eine Produktvitrine: Jede Bildschirmhöhe zeigt genau ein Objekt, eine kurze zentrierte Überschrift, eine Unterzeile und zwei Pillen-Knöpfe. Die Seite wechselt Abschnitt für Abschnitt zwischen reinem Schwarz (#000000) und hellem Grau (#f5f5f7). Es gibt keine Schatten, keine Rahmen und keine Dekoration. Farbe kommt nur vom Objekt selbst und von einem einzigen Blau (#0071e3). Die Stimmung ist ruhig, selbstsicher und präzise, wie ein beleuchtetes Schaufenster bei Nacht.

## Farbpalette
- Bühne dunkel: #000000 (Hero und Kachelflächen), Variante #040405
- Bühne hell: #f5f5f7 (Abschnittsflächen und Fußbereich), Papierweiß #ffffff als Grundfläche
- Text auf Hell: #1d1d1f; sekundär rgba(0,0,0,0.56); tertiär #86868b
- Text auf Dunkel: #f5f5f7; sekundär rgba(255,255,255,0.8)
- Akzent Knopf: #0071e3; Link auf Hell #0066cc; Link auf Dunkel #2997ff
- Navigationsleiste: rgba(0,0,0,0.8) mit Weichzeichner, 44px hoch
- Hinweisband: #1d1d1f, Text weiß
- Verlauf nur als Abdunklung über Bildflächen, zum Beispiel von transparent auf rgba(0,0,0,0.5)
- Anteile: etwa 45 % Schwarz, 40 % Hellgrau, unter 2 % Blau

## Typografie
- Schrift: Inter 400, 600 und 700, Rückfall Helvetica Neue und Arial
- Hero-Überschrift: 3.5rem (56px), Gewicht 600, Zeilenhöhe 1.07, Laufweite -0.28px
- Abschnittsüberschrift: 2.5rem (40px), Gewicht 600, Zeilenhöhe 1.1
- Unterzeile: 1.75rem (28px), Gewicht 400, Zeilenhöhe 1.14, Laufweite +0.2px
- Fließtext und Links: 1.0625rem (17px), Zeilenhöhe 1.47, Laufweite -0.37px
- Kleintext und Fußbereich: 0.75rem (12px), Zeilenhöhe 1.33, Farbe rgba(0,0,0,0.56)
- Mobil: Überschrift 2rem, Unterzeile 1.1875rem
- Nur Gewichte 400, 600, 700; keine Großbuchstaben-Spationierung, kein Kursiv

## Abstände und Raster
- Inhaltsbreite 1260px, Hero bis 1680px, mittig zentriert
- Abschnitte vertikal 5rem bis 7rem, Hero mindestens 580px hoch
- Kachelraster: zwei Spalten, Lücke 12px bis 15px; mobil eine Spalte
- Innenabstand Knopf 11px 21px; Kacheln 3rem; Navigationseinträge 0 8px
- Überschrift zu Unterzeile 0.4em, Unterzeile zu Knöpfen 1.6rem
- Basiseinheit 4px, häufige Schritte: 8, 12, 16, 24, 48, 56

## Layout-Muster
1. Schmale dunkle Navigation, 44px, Einträge 12px bis 14px
2. Hero in Schwarz: Überschrift, Unterzeile und zwei Pillen mittig, darunter das Objekt in voller Breite
3. Heller Abschnitt in #f5f5f7 mit großer zentrierter Überschrift
4. Kachelpaar mit 12px Lücke, jede Kachel mit Überschrift oben, zwei Textlinks, Objekt unten
5. Schmale Zeile mit Logoreihe oder Kennzahlen
6. Hellgrauer Fußbereich mit mehrspaltigen Linklisten in 12px

## Komponenten
- Primärknopf: Fläche #0071e3, Text #ffffff, 17px, Radius 980px, Padding 11px 21px
- Sekundärknopf: transparent, Rand 1px solid #2997ff (auf Hell #0066cc), Text in Rand-Farbe, gleiche Pille
- Textlink: #0066cc, mit nachgestelltem Pfeil oder Winkel, ohne Unterstreichung, beim Hover Unterstreichung
- Kachel: Radius 0 bis 18px, keine Rahmen, keine Schatten, Fläche Schwarz oder #f5f5f7
- Navigation: Weichzeichner 20px, Höhe 44px, Text rgba(255,255,255,0.8)
- Fokusring: 2px solid #0071e3, Versatz 1px

## Bildsprache
Ein einzelnes Objekt, freigestellt auf einfarbiger Fläche, großflächig und leicht angeschnitten, mit weichem Streiflicht an den Kanten. Hintergründe sind schwarz oder hellgrau, nie Fotos mit Umgebung. Keine Icons außer feinen Linien-Symbolen in der Navigation. Platzhalter: Flächen mit sanftem Radialverlauf und einer abgerundeten Grundform.

## Animation
Zurückhaltend und scrollgebunden: Objekte skalieren oder blenden beim Scrollen weich ein (Dauer 0.6s bis 1s, Kurve cubic-bezier(0.28,0.11,0.32,1)). Knöpfe wechseln beim Hover die Fläche zu #0077ed in 0.3s. Keine Sprünge, kein Wackeln, keine Dauerschleifen. Bewegung respektiert prefers-reduced-motion.

## Tonfall
Kurz, bestimmt, in Wortmarken statt Sätzen. Überschrift ein bis drei Wörter, Unterzeile ein Satz mit Punkt. Handlungsaufrufe sind Verben im Infinitiv: "Mehr erfahren", "Kaufen". Keine Ausrufezeichen, keine Superlativ-Ketten, keine Fachbegriffe im Hero.

## Mach
- Pro Abschnitt eine Aussage, eine Überschrift, höchstens zwei Knöpfe
- Schwarz und #f5f5f7 abwechseln, Übergänge als harte Kanten
- Überschriften mit leicht negativer Laufweite und Gewicht 600 setzen
- Blau nur für Handlung und Links verwenden
- Pillenform (Radius 980px) für alle Knöpfe
- Viel Leerraum um das Objekt lassen
- Textfarben über Transparenz abstufen (0.88, 0.72, 0.56, 0.48)

## Mach nicht
- Keine Schatten, Verläufe auf Flächen oder Glühen
- Keine zweite Akzentfarbe, kein Orange, kein Verlaufstext
- Keine eckigen Primärknöpfe, keine Umrandung um Kacheln
- Keine Gewichte unter 400 oder über 700
- Keine linksbündigen Hero-Blöcke mit langen Absätzen
- Keine bunten Icon-Raster

## Typische KI-Fehler in diesem Stil
- Weiche Schatten oder Glassflächen unter Kacheln ergänzen, obwohl der Stil flach ist
- Hero linksbündig mit Fließtext setzen statt mittig und kurz
- Weiß statt Hellgrau #f5f5f7 für die Wechselabschnitte nehmen, so verschwindet der Rhythmus
- Reines Weiß für Text auf Schwarz verwenden, obwohl #f5f5f7 gemeint ist
- Knöpfe mit 8px-Radius statt Pille bauen
- Überschriften zu leicht (300) oder zu fett (800) wählen
- Mehrere Blautöne oder einen Verlauf-Button einführen
