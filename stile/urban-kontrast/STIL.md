# Stil: Urban Kontrast

## Kurzbeschreibung und Stimmung
Ein nüchterner, sportlicher Shop-Stil auf Basis von reinem Weiß und tiefem Schwarz. Große, eng gesetzte DIN-artige Grotesk-Überschriften stehen auf dunklen Vollbild-Flächen mit Fotografie, darunter folgt ein heller, dicht organisierter Katalogbereich mit Navigation, Filter-Chips und Produktkacheln. Es gibt keine Schatten, kaum Rahmen und fast keine Rundung: Tiefe entsteht allein durch den Wechsel von Hell und Dunkel. Die Stimmung ist urban, präzise und selbstbewusst, wie ein Technik-Katalog mit Street-Fotografie. Farbe ist die Ausnahme und nur für Sale (Rot) oder einen einzelnen Aktionsknopf (Mint) erlaubt.

## Farbpalette
```css
--weiss:#ffffff;      /* Hauptfläche, ca. 60 % */
--schwarz:#000000;    /* Hero, Footer, Bänder, ca. 30 % */
--tinte:#121212;      /* Text auf Hell, Überschriften */
--grau-hell:#f5f5f5;  /* Chips, Eingabefelder */
--grau-linie:#e9e9e9; /* 1px Trennlinien */
--grau-dunkel:#303030;/* Flächen auf Schwarz */
--text-hell:#c9c9c9;  /* Fließtext auf Schwarz */
--text-dezent:#9b9b9b;/* Meta, Platzhalter */
--sale:#eb0037;       /* nur Sale und Preisaktionen */
--akzent:#3affb8;     /* ein einziger Aktionsknopf pro Ansicht */
```
Hintergründe sind fast nur Weiß und Schwarz, Grautöne dienen als Struktur. Rot kommt in unter 1 % der Fläche vor, meist als einzelnes Menüwort. Text auf Schwarz ist #f5f5f5 für Überschriften und #c9c9c9 für Absätze.

## Typografie
Schrift: Barlow (400, 500), Rückfall Helvetica Neue, Arial, sans-serif.
- Hero-Display: 8.75rem (140px) Desktop, 2.5rem Mobil, Zeilenhöhe 1, Laufweite -2px (ca. -0.015em), Gewicht 400.
- H1/Seitentitel: 1.75rem, Gewicht 500, Zeilenhöhe 32px, Laufweite -0.6px.
- Abschnittstitel: 2.5rem (40px), Gewicht 400, Zeilenhöhe 44px, Laufweite -1.2px; Mobil 2rem.
- Unterüberschrift: 1.25 bis 1.5rem, Zeilenhöhe 1.3.
- Fließtext: 1rem, Zeilenhöhe 24px, Laufweite -0.2px.
- Navigation, Knöpfe, Chips: 0.875rem bis 1rem, Zeilenhöhe 18px, Laufweite -0.1px.
- Keine Versalien, keine Unterstreichungen als Schmuck. Es gibt nur zwei Gewichte: 400 und 500.

## Abstände und Raster
Maximale Inhaltsbreite 1200px, seitlicher Rand 40px Desktop und 20px Mobil. Basisraster 4px: Kleinabstände 4, 8, 16, 20, 32, 40, 80px. Abschnitte haben vertikal 80px (Mobil 40 bis 60px). Lücken in Kachelgrids 16 bis 32px, in Chip-Reihen 8px. Produktraster 4 Spalten auf Desktop, 2 auf Tablet, 1 bis 2 auf Mobil. Der Inhalt ist linksbündig an einer harten Kante ausgerichtet.

## Layout-Muster
- Dreistufiger Kopfbereich: Hilfsleiste (Stores, Service), Hauptleiste mit zentriertem Wortzeichen und Icons rechts, darunter Kategorie-Leiste mit Suchfeld rechts. Trennung über 1px #e9e9e9.
- Horizontale Chip-Reihe mit Modellnamen direkt unter dem Kopf, auf Mobil seitlich scrollend innerhalb des eigenen Containers.
- Hero: Vollbreite, mindestens 900px hoch (Mobil 844px), dunkel abgedunkeltes Motiv, Kicker klein, Display-Titel links, darunter ein Knopf.
- Danach wechseln helle Katalogbänder und schwarze Story-Bänder mit Vollbildmotiv.
- Footer auf #000 mit mehrspaltigen Linklisten in #f5f5f5.

## Komponenten
- Chip: Hintergrund #f5f5f5, Radius 4px, Padding 12px 16px, Text 0.875rem #121212, Pfeil nach rechts als Zusatz.
- Primärknopf: Hintergrund #121212 oder #000, Text #fff, Radius 4px, Höhe 48px, Padding 0 24px. Auf Fotos als halbtransparente graue Fläche mit weißem Text.
- Aktionsknopf: Hintergrund #3affb8, Text #000, Gewicht 500, Radius 4px.
- Suchfeld: Hintergrund #f5f5f5, Radius 4px, keine Umrandung, Innenabstand links 8px, rechts 60px für das Icon.
- Produktkachel: Bildfläche #f5f5f5 mit 4:3, kein Rahmen, Name 1rem 500, Preis 1rem 400, Sale-Preis in #eb0037.
- Icons: dünne Linien-Icons (1.5px Strich), schwarz.
- Alle Elemente ohne Schatten.

## Bildsprache
Dokumentarische Street- und Sportfotografie bei Tageslicht, Menschen in Bewegung, urbane Kulissen, leicht entsättigt und für Text mit schwarzem Verlauf (20 bis 50 % Deckkraft) abgedunkelt. Produktfreisteller auf hellgrauem Grund. Keine Illustrationen, keine Stockfotos mit Posen. Als Platzhalter dienen Verläufe aus #303030 nach #000 mit feinen geometrischen Linien.

## Animation
Zurückhaltend und funktional: Hover auf Knöpfen und Chips wechselt die Hintergrundfarbe in 150ms ease (Chip zu #e9e9e9, Knopf zu #303030). Pfeile in Chips verschieben sich um 2px nach rechts. Bildflächen skalieren bei Hover höchstens auf 1.03 in 300ms. Keine Parallax-Effekte, keine Einblend-Orgien.

## Tonfall
Kurz, direkt und sachlich, mit kleinen sportlichen Setzungen. Überschriften bestehen aus zwei bis fünf Wörtern, oft als halber Satz, der sich über zwei Zeilen bricht. Beschriftungen sind knappe Substantive oder Imperative („Zum Modell“). Keine Ausrufezeichen, keine Superlative.

## Mach
- Weiß und Schwarz als großflächiger Wechsel, Grau nur als Struktur.
- Display-Titel groß und eng (Laufweite -2px) auf dunklem Foto.
- Radien strikt 4px (maximal 6px), Pille nur für ein einzelnes rundes Element.
- Nur Gewichte 400 und 500 verwenden.
- Chips als schnelle Navigation unter dem Kopf einsetzen.
- Rot nur für Sale, Mint nur für einen Aktionsknopf.
- Trennung über Fläche und 1px-Linien in #e9e9e9.

## Mach nicht
- Keine Schatten, Verläufe auf Knöpfen oder Glasflächen.
- Keine fetten Gewichte ab 600 und keine Versalien-Überschriften.
- Keine bunten Akzentfarben jenseits von Rot und Mint.
- Keine großen Radien (über 6px) an Karten und Knöpfen.
- Keine zentrierten Fließtextblöcke.
- Keine verspielten Illustrationen oder Emojis.

## Typische KI-Fehler in diesem Stil
- Weiche Kartenschatten und 16px-Radien ergänzen, obwohl der Stil flach und fast eckig ist.
- Laufweite vergessen: Große Titel wirken ohne -2px locker und verlieren den Charakter.
- Fette 700er-Überschriften statt Regular 400 beziehungsweise Medium 500.
- Mint oder Rot als Flächenfarbe einsetzen statt als sparsamen Akzent.
- Hero hell statt dunkel gestalten; der Wechsel Schwarz zu Weiß fehlt dann.
- Zu viele Linien und Rahmen um Kacheln, obwohl Fläche und Weißraum trennen.
- Mobil Chips umbrechen statt scrollen lassen und damit horizontalen Überlauf der Seite erzeugen.
