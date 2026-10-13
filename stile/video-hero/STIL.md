# Stil: Video-Hero

## Kurzbeschreibung und Stimmung
Kinoformat. Eine großflächige Bewegtbild-Bühne füllt den ersten Bildschirm, der Text liegt als ruhiges Overlay darüber, darunter folgen helle, stille Abschnitte. Der Film trägt die Marke, Worte sind Untertitel. Wirkt hochwertig, emotional und ruhig. Passt zu Film, Reise, Marken, Gastronomie, Immobilien und Produktlaunches.

## Farbpalette
- Kino-Schwarz `#08090c`, Stufen `#101218`, `#1a1d27`
- Text auf Dunkel: Papier `#f4f1ec`, gedämpft `#a9adbb`; Linien `rgba(244,241,236,.16)`
- Lichtakzent warmes Orange `#ffb86b` und `#ff7a45`; kühles Gegenlicht `#4d7cff`
- Filmtöne für Platzhalter: Tiefblau `#0b2540`, Stahlblau `#2a4f7a`, Abendorange `#ff9a5a`, Nachtviolett `#1b1030`
- Abschluss-Sektion invertiert: Papier `#f4f1ec` mit Text `#15171d`

## Typografie
- Titel: Archivo 800, Laufweite -0.03em, Zeilenhöhe 0.98, `clamp(3rem, 9.5vw, 8.5rem)`, höchstens 4 Wörter
- Fließtext: Inter Tight 400/500, 1.0625rem bis 1.2rem
- Überzeilen und Kapitel: JetBrains Mono 500, 0.75rem, Versalien, Laufweite 0.16em
- Text über dem Film immer mit weichem Schatten (`0 2px 40px rgba(0,0,0,.45)`) und Verdunkelungsverlauf darunter

## Abstände und Raster
- Bühne: Höhe `100vh`, mindestens 560px, höchstens 980px; Inhalt unten ausgerichtet
- Sektionen darunter `clamp(4.5rem, 10vw, 8.5rem)` Abstand, Inhalt max. 1240px
- Zwei Spalten für Text und Standbild, Dreierreihe für Arbeiten (4:5), Kennzahlen dreispaltig
- Radien 8 und 14px, Knöpfe als Pille

## Layout-Muster
- Bühne: Film als unterste Ebene (leicht größer als der Rahmen, damit die Kamerafahrt keine Ränder zeigt), darüber Licht-Ebenen, Körnung und Verdunkelungsverlauf, ganz oben Kopfzeile, Titel, Lead mit Knopf und die Kapitelleiste
- Danach ruhige Abschnitte im Wechsel von Text und Standbild, am Ende eine helle Abschlussfläche
- Kapitelleiste mit vier Marken, die sich nacheinander füllen, zeigt den Verlauf des Films

## Komponenten
- Knopf: Pille in Papierfarbe mit rundem Abspielzeichen links, Hover Skalierung 1.04
- Kapitel-Marke: 2px Linie, Beschriftung in Mono, aktive Linie füllt sich in Orange
- Standbild: 14px Radius, 1px Linie, Bildunterschrift in Mono unten links
- Kopfzeile: Wortmarke links, wenige Links rechts, kein Hintergrund

## Bildsprache
Das Bewegtbild ist der Held: weite Totalen, warmes Gegenlicht, ruhige Kamerafahrten, wenig Schnitte. Im Beispiel ersetzen CSS-Verläufe, wandernde Lichtflecken und eine langsame Skalierung den Film. Keine Stock-Clips mit Händeschütteln, keine schnellen Schnittfolgen.

## Animation
Ruhig und langsam wie eine Kamerafahrt: Film-Ebene skaliert in 26s von 1.0 auf 1.12, Lichtflecken wandern in 18 bis 23s, Kapitelleiste füllt sich in 26s. Nur `transform` und `opacity`. Hover 300ms. `prefers-reduced-motion` respektieren: Bewegung aus, Standbild zeigen.

Umsetzung in echten Projekten: Auf der Bühne ein Video-Element mit `autoplay`, `muted`, `loop`, `playsinline` und `preload="metadata"`, Objektanpassung `object-fit: cover`, ein Standbild als `poster` und als Ersatz. Zwei Formate (MP4 mit H.264 und WebM), Länge 8 bis 20 Sekunden als Schleife, Datei höchstens 3 bis 5 MB für die Bühne, ohne Ton. Für Nutzer mit reduzierter Bewegung, auf sparsamen Verbindungen oder auf kleinen Geräten nur das Standbild laden (Videoquelle erst per Medienabfrage oder Skript nachladen). Ein sichtbarer Pause-Knopf ist Pflicht, sobald das Video länger als 5 Sekunden läuft. Der Text über dem Film braucht Verdunkelungsverlauf und mindestens 4.5:1 Kontrast an der hellsten Stelle des Films. Längere Filme (Showreel) öffnen in einem eigenen Player mit Ton, nie automatisch.

## Tonfall
Wenige Worte, bildhaft, ruhig. Titel als kurzer Satz mit Punkt. Keine Marketing-Floskeln, keine Ausrufezeichen. Beispiel: "Das Licht bleibt."

## Mach
- Den ersten Bildschirm vollständig dem Film geben
- Text unten links, höchstens Titel, ein Satz und ein Knopf
- Verdunkelungsverlauf und Kontrast prüfen, an der hellsten Filmstelle
- Standbild als Ersatz und Pause-Knopf von Anfang an einplanen
- Ruhige, helle oder dunkle Flächen unter der Bühne, damit der Film wirkt
- Bühne auf Mobil auf mindestens 560px Höhe halten, Titel verkleinern statt umbrechen lassen

## Mach nicht
- Kein Video mit Ton, das von selbst startet
- Keine schnellen Schnitte oder Zoomfahrten über 1.15
- Kein langer Text auf dem Film
- Keine Videodatei über 5 MB auf der Bühne
- Kein Karussell aus mehreren Filmen
- Keine Bewegung ohne Standbild-Ersatz

## Typische KI-Fehler in diesem Stil
- Das Video ist heller als erwartet und der weiße Titel wird unlesbar, weil der Verdunkelungsverlauf fehlt
- Ein großes Video wird auf Mobil voll geladen und verbraucht Datenvolumen
- Es gibt weder Standbild noch Pause-Knopf, Nutzer mit reduzierter Bewegung sehen trotzdem Bewegung
- Die Bühne ist höher als der Bildschirm, der Knopf liegt außerhalb des ersten Bildes
- Der Film zeigt Ränder, weil er nicht größer als sein Rahmen ist
- Sieben Effekte gleichzeitig statt einer ruhigen Fahrt
