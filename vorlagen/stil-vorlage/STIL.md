# Stil: Stil-Vorlage

## Kurzbeschreibung und Stimmung
Zwei bis vier Sätze: Wie wirkt der Stil (ruhig, laut, technisch, warm)? Für welche Art von Seite eignet er sich? Beschreibe den Eindruck mit konkreten Merkmalen statt Floskeln. Beispiel: Helle Fläche, ein dunkler Akzent, viel Weißraum, große Überschriften.

## Farbpalette
- Grund: `#ffffff`
- Text: `#1a1a1a`, gedämpfter Text `#5c5c5c`
- Akzent: `#2457d6` (nur für Knöpfe und Links)
- Linien und Flächen: `#e6e6e6`
- Jede Farbe mit Hex-Wert und Einsatzort nennen. Die Werte müssen zu `tokens.css` passen.

## Typografie
- Schriften nur aus Google Fonts oder System-Schriften, mit Rückfall (`system-ui, sans-serif`).
- Überschriften: Familie, Gewicht, Größe in rem, Zeilenhöhe.
- Fließtext: 1rem bis 1.125rem, Zeilenhöhe 1.5 bis 1.7.
- Mobil (390 px) die verkleinerten Größen angeben.

## Abstände und Raster
- Basiseinheit 8px; Abstände als Vielfache (8, 16, 24, 48, 96).
- Inhaltsbreite maximal 1120px, seitlicher Rand mobil 16px.
- Raster: 12 Spalten Desktop, 1 Spalte mobil, Lücke 24px.

## Layout-Muster
- Kopfzeile mit Wortmarke links und Navigation rechts.
- Hero mit Überschrift, einem Satz und einem Knopf.
- Abschnitte abwechselnd Text und Kacheln.
- Fußzeile mit Kontakt und rechtlichen Links.

## Komponenten
- Knopf: Füllung in Akzentfarbe, Radius 8px, Innenabstand 12px 20px, Hover etwas dunkler.
- Karte: heller Grund, Rahmen 1px in Linienfarbe, Radius 12px.
- Formularfeld: Rahmen 1px, Radius 8px, deutlicher Fokusrahmen.

## Bildsprache
Beschreibe, welche Bilder passen (Fotos, Illustrationen, Muster) und wie sie beschnitten werden. In der Beispielseite stehen Platzhalter aus CSS-Flächen oder SVG; keine fremden Fotos, Logos oder Marken verwenden.

## Animation
Dezente Übergänge von 150 bis 250 ms für Hover und Fokus. Keine Dauerbewegung. `prefers-reduced-motion` respektieren. Wenn der Stil Bewegung braucht, Dauer und Kurve (`ease-out`) angeben.

## Tonfall
Kurze, klare Sätze. Aktive Verben auf Knöpfen ("Termin buchen"). Keine Ausrufezeichen, keine leeren Superlative. Beispieltexte in der Sprache der Zielgruppe.

## Mach
- Wenige Farben, konsequent eingesetzt
- Große Überschriften, viel Weißraum
- Kontrast mindestens 4.5 zu 1 für Text
- Auf 390 px prüfen, kein horizontales Scrollen

## Mach nicht
- Mehr als eine Akzentfarbe
- Schatten und Verläufe ohne Funktion
- Text unter 14px
- Fremde Marken, Logos oder Bilder

## Typische KI-Fehler
- Violett-blauer Verlauf als Standard
- Drei gleiche Kacheln mit Symbol, Titel und Satz
- Glas-Karten ohne Anlass
- Floskeln wie "Innovative Lösungen für Ihre Zukunft"
- Alle Abstände gleich groß, kein Rhythmus
