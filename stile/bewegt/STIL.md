# Stil: Bewegt

## Kurzbeschreibung und Stimmung
Lebendig, freundlich, mit Schwung. Die Seite reagiert: Elemente kommen nacheinander herein, Knöpfe federn, Karten kippen leicht, ein Laufband und ein sich drehender Stempel geben Takt. Bewegung ist hier Gestaltungsmaterial mit festen Dauern und Kurven, kein Zierrat. Der Inhalt bleibt auch ohne Bewegung vollständig lesbar.

## Farbpalette
- Grund: Creme `#fff6e8`, Flächen Weiß `#ffffff`, Linien `#e7dcc9`
- Tinte: `#1a1330`, sekundär `#5b5470`
- Hauptfarbe Koralle `#ff4d3d`; Begleiter Gelb `#ffc83d`, Minze `#2fd4a0`, Violett `#6a4cff` (Zahlen, Flächen)
- Alle Farbflächen mit 2px Tintenkontur; Bewegung wirkt auf klaren Flächen besser als auf Verläufen

## Typografie
- Überschriften: Bricolage Grotesque 800, Laufweite -0.025em, Zeilenhöhe 1.05
- Fließtext: DM Sans 400/500, 1.0625rem, Zeilenhöhe 1.6
- Hero `clamp(2.8rem, 7.5vw, 6rem)`, H2 `clamp(1.9rem, 3.8vw, 3.1rem)`
- Ein einzelnes Wort der Headline darf in Koralle wippen (`inline-block`), nie mehr als eines

## Abstände und Raster
- Sektionen `clamp(4rem, 9vw, 7.5rem)`, Inhalt max. 1160px
- Karten im 3er-Raster mit 1.5rem Lücke, mobil einspaltig
- Radien 12, 20, 32px und Pille; Konturen 2px; Sockelschatten `0 3px 0` in Tinte
- Staffelung: jedes Element 90ms nach dem vorigen, höchstens 6 Stufen

## Layout-Muster
- Hero: Headline, Lead, zwei Knöpfe, darüber ein rotierender Stempel als Blickfang; alles kommt gestaffelt herein
- Laufband in Tintenfarbe zwischen Hero und Inhalt, Begriffe mit Zierzeichen getrennt
- Kartenreihe, Kennzahlen, farbige Abschlussfläche; alles unterhalb des ersten Bildschirms blendet beim Scrollen ein

## Komponenten
- Knopf: Pille, 2px Kontur, Sockelschatten; Hover hebt um 6px und vergrößert den Sockel, Klick drückt auf 2px; Pfeil im Knopf rutscht 6px nach rechts
- Karte: 32px Radius, Hover `translateY(-6px) rotate(-2deg)`, Symbolfläche dreht 18 Grad und wächst auf 1.12
- Link: Unterstreichung wächst von links in 320ms
- Fortschrittsbalken oben: 5px Koralle, skaliert mit der Scrollposition

## Bildsprache
Flache Farbformen, Symbole aus Grundformen, kein Foto-Rauschen. Formen dürfen sich drehen, wippen oder wandern. Im Beispiel sind es reine CSS-Flächen.

## Animation
Vier feste Dauern: 180ms (Klick), 320ms (Hover), 700ms (Einblenden), 24 bis 28s (Dauerschleifen). Zwei Kurven: Feder `cubic-bezier(.34,1.56,.64,1)` für Reaktionen, Ausklang `cubic-bezier(.16,1,.3,1)` für Einblenden. Nur `transform` und `opacity` bewegen. Einblenden: 32px nach oben, gestaffelt. Beim Scrollen: CSS-Animation mit `animation-timeline: view()` und `animation-range: entry 0% entry 55%`, abgesichert mit `@supports`; ohne Unterstützung bleibt alles sichtbar (Grundzustand ist sichtbar, die Animation macht es erst unsichtbar). Laufband mit `animation-play-state: paused` bei Hover. `prefers-reduced-motion: reduce` schaltet alle Animationen und Übergänge ab, Inhalte stehen dann sofort fest.

Umsetzung in echten Projekten: zuerst CSS (Keyframes, Übergänge, scrollgesteuerte Animationen). Für Zeitabläufe über mehrere Elemente, Pfade oder Bewegung nach Nutzereingabe eine Animationsbibliothek wie GSAP mit ScrollTrigger oder Motion einsetzen, geladen erst bei Bedarf. Ältere Browser bekommen die Fallback-Variante mit einem Intersection Observer, der eine Klasse zum Einblenden setzt. Layout-Eigenschaften (Breite, Höhe, Position) nie animieren, kein `will-change` auf allem, Seitenleistung mit Messung prüfen.

## Tonfall
Munter, direkt, kurze Sätze. Verben der Bewegung: schwingen, federn, fließen, laufen. Höchstens ein Ausrufezeichen pro Seite. Beispiel: "Bringen wir Ihre Seite in Schwung."

## Mach
- Feste Dauern und Kurven aus den Tokens verwenden
- Jede Hover-Reaktion kleiner als 8px oder 4 Grad
- Gestaffelt einblenden, aber höchstens 6 Stufen und unter einer Sekunde Gesamtzeit
- Fallback und Ruhemodus von Anfang an mitbauen
- Dauerbewegung nur an zwei Stellen pro Seite (zum Beispiel Laufband und Stempel)
- Laufband bei Hover anhalten

## Mach nicht
- Keine Bewegung, die Lesen oder Klicken erschwert
- Keine Animation von Breite, Höhe, Rand oder Position
- Kein Text, der sich bewegt, während man ihn liest
- Kein Blinken, keine Bewegung über 3 Hz
- Kein Parallax-Ruckeln und keine gekoppelte Scrollhöhe, die das Scrollen bremst
- Keine Animation ohne Ruhemodus

## Typische KI-Fehler in diesem Stil
- Alles hüpft, wippt und leuchtet gleichzeitig, nichts hat Rang
- Einblenden setzt den Grundzustand auf unsichtbar; ohne Unterstützung des Browsers bleibt die Seite leer
- Eigene Dauern und Kurven an jeder Stelle statt der festen Werte
- `transition: all` löst unerwünschte Layoutsprünge aus
- Laufband verursacht horizontales Scrollen, weil der Container nicht abschneidet
- `prefers-reduced-motion` fehlt oder blendet Inhalte aus statt sie sofort zu zeigen
