# Stil: Notizbuch kursiv

## Kurzbeschreibung und Stimmung
Ein persönliches Schreib-Blog im Browser: warmes Papierweiß, fette kursive Serifen-Schlagzeilen, Fließtext in einer weichen Serife und Metadaten in Monospace-Versalien. Das Layout ist flach, ohne Kästen, ohne Schatten, nur 1px-Linien trennen. Ein einziger orangeroter Akzent und ein Indigo für Links und Titel sorgen für Wiedererkennung. Kleine Pixelmuster (Zellen-Automaten) in Orange sind der verspielte Kontrapunkt zur ruhigen Typografie. Gefühl: Notizheft eines Programmierers, aufgeräumt, neugierig, lesefreundlich.

## Farbpalette
- Papier (Hintergrund) `#FAFAF7`, reinweiß `#FFFFFF` nur für Eingabefelder
- Tinte (Überschriften, Haupttext) `#16170E`
- Gedämpfte Tinte (Fließtext, Nav, Beschreibungen) `#5A5C50`
- Linien `#D5D4C9`, immer 1px
- Akzent Orangerot `#C2410C`: Rubrik-Labels, Tags, Punkt hinter der Schlagzeile, aktiver Nav-Punkt, Pixelmuster
- Indigo `#3D49A6`: Beitragstitel, Links, Primärknopf (Fläche), Pixelmuster im Fuß
- Textfarbe auf Indigo: Papier `#FAFAF7`
- Keine Verläufe, keine Schatten (Ausnahme: das schwebende Mobil-Menü)

## Typografie
- Schlagzeilen: Crimson Pro (Google Fonts), kursiv, Gewicht 800 für H1, 700 für H2
- H1: 3.5rem (56px), Zeilenhöhe 1, Laufweite -0.025em; mobil 2.25rem
- H2 und Beitragstitel: 2rem (32px), Zeilenhöhe 1.15, Laufweite -0.015em; mobil 1.5rem
- Fließtext: Lora 400, 1.125rem (18px), Zeilenhöhe 1.5, Farbe `#5A5C50`; mobil 1rem
- Meta, Navigation, Tags, Knöpfe: Space Mono 400, 0.6875rem (11px), Versalien, Laufweite 0.14em
- Datum in Mono, 0.8125rem, ohne Versalien, Farbe `#5A5C50`
- Link-Listen (Schlüssel/Wert) in Space Mono 0.8125rem, Schlüssel grau, Wert Indigo mit 1px Unterstrich in Linienfarbe
- Nur Gewichte 400, 700, 800; keine hellen Schnitte

## Abstände und Raster
- Maximale Breite 1200px, Seitenrand 2rem (mobil 1.25rem), Inhalt 1088px
- 12-Spalten-Raster: Seitenleiste 4 Spalten, Beitragsliste 8 Spalten, Lücke 2rem
- Abstände in Vielfachen von 0.25rem: 0.5, 0.875, 1, 1.75, 2, 3.5rem
- Beiträge: je 1.5rem Innenabstand oben und unten, getrennt durch 1px-Linie
- Hero: 3.5rem oben, 2.5rem unten
- Radien überall 0

## Layout-Muster
- Kopfzeile: links ein kursives Monogramm mit orangem Punkt, Navigation mittig in Mono-Versalien, rechts ein kleines Symbol; darunter 1px-Linie über die volle Breite
- Hero: linksbündige Riesenschlagzeile (max. 11 Wörter, endet mit orangem Punkt), darunter ein kurzer grauer Untertitel; rechts zwei kleine Pixelmuster, oben und unten
- Trenner: Linie links und rechts, in der Mitte ein orangefarbenes Mono-Label
- Zweispaltig: links Vorstellung, Link-Liste, Tags, Pixelfeld; rechts die Beitragsliste
- Fuß: Linie, links breites Pixelband in Indigo, rechts Abo-Zeile, Kleingedrucktes, Fußnavigation

## Komponenten
- Beitragseintrag: Titel kursiv Indigo, darunter eine Meta-Zeile (Datum grau, Tags orange mit Mittelpunkt als Trenner), darunter ein Zweizeiler in grauer Serife
- Tags: Mono-Versalien in Orange, nur Text, keine Pillen
- Primärknopf: rechteckig, Radius 0, Fläche `#3D49A6`, Text Papier, Mono-Versalien Fett 700, Innenabstand 0.875rem 1.25rem
- Eingabefeld: weiß, 1px Linienrahmen `#D5D4C9`, Mono 0.9375rem, Innenabstand 0.75rem 0.875rem, Radius 0
- Textlinks: Indigo, 1px Unterstrich in Linienfarbe, beim Hover Unterstrich in Indigo
- Mobilmenü: einziger Schwebeblock, Papier, 1px Linie, Radius 10px, weicher Schatten `0 12px 32px rgba(22,23,14,.16)`

## Bildsprache
Keine Fotos. Der Bildersatz sind Pixelmuster aus quadratischen Zellen (4 bis 6px) in Orange oder Indigo, locker verstreut wie Zustände eines Zellen-Automaten, mit viel Leerraum. Gliederung durch Muster statt Bild: je eines neben der Schlagzeile, eines in der Seitenleiste, ein breites Band im Fuß. Alles ohne Rahmen auf dem Papier.

## Animation
- Einziger Ausdruck: Pixelmuster, die schrittweise (steps) flackern oder wandern, langsam, 1 bis 2 Schritte pro Sekunde
- Links: Unterstrich-Farbe wechselt in 0.2s mit `cubic-bezier(0.2, 0, 0, 1)`
- Knöpfe: Hintergrund wechselt in 0.2s zu Orange, optional leichte Federkurve `cubic-bezier(0.34, 1.56, 0.64, 1)` bei kleinen Bewegungen
- Mit prefers-reduced-motion alles ausschalten
- Keine Parallax-Effekte, keine großen Einblendungen

## Tonfall
Persönlich, neugierig, knapp. Ich-Form, kurze Sätze, konkrete Themen statt Versprechen. Beschreibungen sind Zweizeiler, die Lust auf den Beitrag machen. Metadaten sind trocken (Datum, Tags). Kein Marketingsprech, keine Ausrufezeichen.

## Mach
- Schlagzeile kursiv, schwer, eng gesetzt, mit orangem Schlusspunkt
- Linien statt Kästen: 1px `#D5D4C9` zwischen allen Einträgen
- Jede Liste mit Meta-Zeile (Datum plus Tags in Mono-Versalien)
- Orange sparsam: Tags, Labels, Punkte, Pixelmuster
- Indigo für alles Anklickbare und Titel
- Pixelmuster als einzige Dekoration
- Seitenleiste mit Selbstvorstellung und Link-Liste
- Mobil: alles einspaltig, Pixelmuster verkleinern

## Mach nicht
- Keine Karten mit Rundung oder Schatten, keine Pillen für Tags
- Keine Sans-Serif-Schlagzeilen
- Kein Reinschwarz `#000` und kein Reinweiß als Seitenhintergrund
- Keine Fotos, keine Icon-Kreise, keine Emoji
- Keine Verläufe und keine zweite Akzentfarbe
- Keine zentrierte Dreierreihe aus Kacheln
- Keine Zeilenlängen über etwa 75 Zeichen

## Typische KI-Fehler in diesem Stil
- Schlagzeile steif gesetzt statt kursiv und fett; die Kursive ist der Charakter
- Tags als bunte Pillen mit Hintergrund statt als Mono-Text in Orange
- Orange und Indigo gemischt auf Flächen; Orange bleibt Detail, Indigo nur Text und Knopf
- Pixelmuster als glatte Illustration oder Verlauf gezeichnet statt aus echten quadratischen Zellen
- Meta in der Serife oder in einer Sans-Serif statt in Space Mono
- Weicher Schatten und Radius an Karten und Knöpfen, obwohl der Stil flach und eckig ist
- Seitenleiste fehlt, dadurch wirkt die Seite wie ein generischer Blog-Feed
- Laufweite der Schlagzeile nicht negativ, dadurch wirkt sie locker statt kompakt
