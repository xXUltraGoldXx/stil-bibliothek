# Stil: Mediathek dunkel

## Kurzbeschreibung und Stimmung
Dunkle, kompakte Medien-App-Oberfläche. Der Grund ist nahezu schwarz, darauf liegen Panels in abgestuften Grautönen, Regale mit quadratischen Cover-Kacheln und kurze, fette Titel. Ein einziger Akzent, ein leuchtendes Grün, markiert Aktion und Zustand. Alles wirkt dicht, ruhig und werkzeughaft: Inhalte stehen im Vordergrund, die Oberfläche tritt zurück. Gefühl: abends im Wohnzimmer eine Bibliothek durchstöbern.

## Farbpalette
- Seitengrund: `#161616`, tiefste Ebene (Seitenleiste, Kopfzeile): `#000000`
- Panels und Kacheln: `#1c1c1c`, Eingabefelder und runde Icon-Knöpfe: `#232323`, Hover-Fläche: `#383838`, Hilfslinien und Platzhalter: `#595959`
- Text: Weiß `#ffffff` für Titel und aktive Elemente, Grau `#b9b9b9` für Fließtext, Meta und Navigation, Rand `#818181`
- Akzent Grün `#27c95b` (Hover `#4cd784`), nur für Wiedergabe-/Hauptaktion, Zustände und kleine Marker
- Helles Band: `#eeeeee` mit Text `#1c1c1c` und schwarzen Pillen, nur einmal pro Seite (Hinweis- oder Abschlussband)
- Sparsam als Cover-Farben (nie als UI-Farbe): Magenta `#e1009d`, Braun `#a3694f`, Verlauf 90 Grad von `#af2896` nach `#509bf5`
- Oberer Verlauf in Kopfbereichen: von `rgba(0,0,0,.6)` nach `#161616`

## Typografie
- Eine Grotesk für alles: Figtree (Google Fonts); Gewichte 400, 600, 700, 800
- H1 bis 3rem, Gewicht 800, Zeilenhöhe 1.1; H2 1.5rem (Mobil 1.25rem), Gewicht 700, Farbe Weiß; H3 1rem, Gewicht 700
- Fließtext 0.875rem bis 1rem, Gewicht 400, Farbe `#b9b9b9`, Zeilenhöhe 1.5
- Meta und Untertitel 0.75rem bis 0.8125rem, Grau
- Versalien nur für Rechtliches und Zustimmungs-Knöpfe: 0.8125rem, Gewicht 700, Laufweite 0.12em
- Kein Kursiv, keine Serifen, keine Gewichte über 800

## Abstände und Raster
- Basis 4px, bevorzugte Stufen: 4, 8, 12, 16, 24, 32, 48 (in rem: 0.25, 0.5, 0.75, 1, 1.5, 2, 3)
- Innenabstand Panels 12 bis 16px, Knöpfe 12px 32px, Kachel-Lücken 24px, Textlücken 4 bis 8px
- Regale: Raster aus quadratischen Kacheln, `repeat(auto-fill, minmax(9.5rem, 1fr))`, Lücke 1.5rem
- Inhaltsbreite max. 1160px, Seitenrand 16px mobil, 24px Desktop
- Abschnitte vertikal 2.5 bis 4rem, deutlich dichter als bei Marketing-Seiten

## Layout-Muster
- Kopfzeile: schwarz, links Zeichen, mittig Suchfeld als Pille, rechts Textlinks und weiße Pille "Anmelden"
- Zweispaltige App-Hülle möglich: schmale Seitenleiste `#000` (Panels `#161616`) und Hauptfläche `#161616` mit Radius 8px
- Regale: Überschrift links (H2), "Alle anzeigen" als kleiner grauer Link rechts, darunter eine Reihe Cover-Kacheln mit Titel (weiß, 600) und Untertitel (grau)
- Panels in der Seitenleiste: `#1c1c1c`-Karten mit fettem Titel, einem Satz Grau und einer weißen Pille
- Helles Band am Seitenende oder unten: volle Breite, `#eee`, links Text, rechts Pillen-Knöpfe

## Komponenten
- Hauptknopf hell: Pille (Radius 9999px), Fläche `#ffffff`, Text `#000000`, Gewicht 700, Hover Skalierung 1.04
- Akzentknopf: runder Wiedergabe-Knopf oder Pille in `#27c95b`, Text `#000000`
- Dunkler Pillenknopf im hellen Band: `#1c1c1c`, Text weiß, Versalien
- Runde Icon-Knöpfe: 48px Kreis, `#232323`, Icon grau, Hover weiß
- Suchfeld: Pille (Radius 500px), Fläche `#232323`, Innenabstand 12px 48px, kein Rand, Fokus: 2px weißer Rand
- Kacheln: Radius 6px (Künstler-Kacheln 50%), Hover: Panel `#232323`, grüner Wiedergabe-Knopf blendet unten rechts ein
- Schatten: `0 8px 24px rgba(0,0,0,.5)` für schwebende Kacheln, Menüs und Overlays; sonst keine Schatten

## Bildsprache
Quadratische Cover als Hauptbildform: kräftige, gesättigte, stark gestaltete Motive (Typografie-Cover, Porträts, Produktfotos), die auf dem dunklen Grund leuchten. Radius 6px, bei Personen kreisrund. Bilder tragen die Farbe, die Oberfläche bleibt neutral grau. Im Beispiel: CSS-Verläufe und Formen als Platzhalter, keine Fotos.

## Animation
Funktional und knapp: Hover 150 bis 200ms, ease-out. Wiedergabe-Knopf blendet ein und rutscht 8px nach oben, Knöpfe skalieren auf 1.04. Keine großen Eingangsanimationen, kein Parallax. `prefers-reduced-motion` respektieren.

## Tonfall
Freundlich, direkt, du-Form. Kurze Imperative und Fragen ("Erstelle deine erste Liste", "Was möchtest du hören?"). Keine Superlative, keine Fachbegriffe, ein Satz Erklärung pro Panel.

## Mach
- Grund `#161616`, Panels `#1c1c1c`, Tiefstes `#000`: drei Ebenen, mehr nicht
- Grün `#27c95b` nur für die eine Hauptaktion und Zustände
- Alle Knöpfe als Pillen, Kacheln mit 6px Radius
- Titel weiß und fett, alles Nebensächliche in `#b9b9b9`
- Kachel-Regale mit Titel und Untertitel, rechts oben "Alle anzeigen"
- Dichte beibehalten: kleine Schrift (14px), enge Abstände (4 bis 12px) in Listen

## Mach nicht
- Keine weißen Seitenflächen als Standard, Weiß nur für Text, Pillen und das eine helle Band
- Kein zweiter Akzent neben Grün, keine bunten Buttons
- Keine großen Radien auf Kacheln (kein 24px), keine eckigen Pillen
- Keine Linien-Rahmen um Panels, Trennung nur durch Flächenstufen
- Keine Verläufe in der Bedienoberfläche, nur in Cover-Motiven
- Keine ausgedehnten Fließtexte in Weiß, Fließtext bleibt grau

## Typische KI-Fehler in diesem Stil
- Grün auf allem: Überschriften, Links und Icons grün statt nur die Hauptaktion
- Reines Schwarz als Seitengrund statt `#161616`, dadurch gehen die Panel-Stufen verloren
- Zu luftige Marketing-Abstände (96px Sektionen) statt der dichten App-Rhythmik
- Karten mit Rand und Schlagschatten statt flacher Flächenstufen
- Knöpfe mit 8px Radius statt vollen Pillen, oder Grün-Knopf mit weißer Schrift (Kontrast zu gering, Text muss schwarz sein)
- Hero mit riesiger Headline und Stockfoto, statt Regalen aus Cover-Kacheln
