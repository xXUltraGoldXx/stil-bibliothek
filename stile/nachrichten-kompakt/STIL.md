# Stil: Nachrichten kompakt

## Kurzbeschreibung und Stimmung
Ein sachliches, vertrauenswürdiges Nachrichtenportal. Viele Meldungen stehen dicht, aber geordnet auf hellgrauem Grund. Kennzeichen sind kräftige Serifen-Schlagzeilen mit enger Laufweite, kleine Sans-Meta-Zeilen, schwarze Rechteck-Knöpfe und ein einziges Rot für Eilmeldungen und die aktive Rubrik. Alles ist flach: Radius 0, keine Schatten, keine Verläufe. Gefühl: Verlässlichkeit, Überblick, Tempo ohne Hektik.

## Farbpalette
- Seitengrund `#f6f6f6`, Kartenfläche und Kopfzeile `#ffffff`
- Text primär `#202224`, sekundär `#545658`, gedämpft `#8a8c8e`
- Reines Schwarz `#000000` für Knöpfe, Logo-Flächen und Rahmen
- Linie und Trenner `#e6e8ea`
- Dunkle Fläche (Fußzeile, Hinweisleiste) `#323232`, darin Text `#bebebe` bzw. `#ffffff`, Aktionstext Orange `#f6a21d`
- Signalrot `#b80000` für Eilmeldungs-Marke und aktive Rubrik, `#eb0000` nur für kleine Punkte
- Gewichtung: etwa 55 % Grau-Grund, 40 % Weiß, Rest dunkel. Rot bleibt unter 2 % der Fläche

## Typografie
- Schlagzeilen: Source Serif 4 (Google Fonts), Gewicht 500 bis 600, Laufweite -0.02em
- Stufen: H1/Aufmacher 2rem mit Zeilenhöhe 2.25rem (mobil 1.5rem), H2 1.75rem/2rem (mobil 1.5rem/1.75rem), H3 1.5rem/1.75rem (mobil 1.25rem/1.5rem), Teaser-Titel 1.125rem/1.375rem
- Fließtext und Teaser-Text: Source Serif 4, 0.875rem bis 1.125rem, Gewicht 400, Zeilenhöhe 1.3 bis 1.4, Farbe `#202224`
- Meta, Navigation, Knöpfe, Formularfelder: Public Sans (Google Fonts), 0.75rem bis 1rem, Gewicht 500, Meta mit Laufweite 0.01em
- Gewichte nur 400, 500, 700. Versalien kaum, höchstens kleine Marken mit 0.05em Laufweite
- Source Serif 4 und Public Sans (Google Fonts)

## Abstände und Raster
- Maximalbreite 1248px, seitlich 1rem Rand, mobil Breite 100 % minus 2rem
- 12-Spalten-Raster, Lücken 0.75rem bis 1rem, vertikal 0.5rem zwischen Titel und Text
- Innenabstände klein: 0.5rem, 0.75rem, 1rem, 1.5rem; Knöpfe 0.5rem 0.75rem
- Teaser trennt eine 1px-Linie `#e6e8ea`, Abschnitte trennt 1.5rem bis 2rem Luft
- Dicht, aber nie überfüllt: höchstens 3 Textebenen pro Teaser (Titel, Zweizeiler, Meta)

## Layout-Muster
- Kopfzeile weiß, 80px hoch: links Menü-Symbol, Mitte Wortmarke als schwarze Quadrate, rechts schwarzer Knopf und Textlink
- Darunter Rubrikleiste, zentriert, 0.875rem Public Sans 500, aktive Rubrik mit 3px roter Unterkante
- Aufmacher: drei Spalten (4/5/3 von 12). Links Text-Aufmacher mit großer Serifen-Schlagzeile, Mitte großes Bild, rechts Stapel kleinerer Teaser mit Bild oben
- Danach Rubrikblöcke: Titelzeile mit Linie, darunter vier Teaser nebeneinander (mobil einspaltig)
- Eilmeldungs-Marke vor der Schlagzeile: roter Punkt plus rotes Wort, Gewicht 700
- Fußzeile dunkel `#323232`, vierspaltige Linkliste

## Komponenten
- Primärknopf: Fläche `#000000`, Text `#ffffff`, Public Sans 500, 1rem, Padding 0.5rem 1rem, Radius 0, Höhe mindestens 44px
- Sekundärknopf: transparent, 2px Rahmen `#000000`, Text schwarz, Padding 0.5rem 0.75rem
- Teaser: Bild (16:9 oder 3:2), Titel Serif 500, Zweizeiler `#545658`, Meta-Zeile (Rubrik, Zeit) 0.75rem
- Eingabefeld: Fläche `rgba(239,239,239,0.3)`, kein Rand, Padding 0.8rem, Fokus 2px schwarzer Rand
- Hinweisleiste unten: `#323232`, Titel weiß, Aktionen in Orange `#f6a21d`
- Radien 0, Schatten keine

## Bildsprache
Dokumentarische, nüchterne Fotos in gedeckten Farben, ohne Filter, ohne Rahmen. Bilder stehen randlos bündig mit der Textspalte, meist 16:9 oder 3:2. Porträts und Szenen, keine Stockfoto-Posen. Im Beispiel werden sie durch flache CSS-Flächen in Grautönen mit einfachen SVG-Formen ersetzt.

## Animation
Nahezu keine. Hover: Titel wird unterstrichen (0.15s), Knopf wechselt auf `#323232`. Kein Parallax, keine Einblend-Effekte. Fokusrahmen sind sichtbar und 2px stark.

## Tonfall
Sachlich, knapp, neutral. Schlagzeilen sind vollständige Aussagen im Präsens, ohne Ausrufezeichen und ohne Werbesprache. Der Zweizeiler nennt Ort, Zahl oder Beteiligte. Meta-Zeilen nennen Rubrik und Alter ("vor 3 Std.").

## Mach
- Serifen-Schlagzeilen mit enger Laufweite und Zeilenhöhe nahe 1.15
- Grauen Seitengrund mit weißen Flächen kombinieren
- Genau ein Rot, nur für Eilmeldung und aktive Rubrik
- Schwarze, eckige Knöpfe mit klaren Zuständen
- Teaser konsequent im gleichen Muster: Bild, Titel, Zweizeiler, Meta
- Mobil auf eine Spalte umbrechen, Teaser-Reihenfolge beibehalten

## Mach nicht
- Keine Rundungen, Schatten, Verläufe oder Glas-Effekte
- Keine bunten Knöpfe, keine Pillenform
- Keine Sans-Serif-Schlagzeilen
- Keine großen Leerflächen oder Hero-Slogans über die ganze Breite
- Keine Emoji, keine Icon-Kreise
- Keine Animationen, die Lesen stören

## Typische KI-Fehler in diesem Stil
- Knöpfe und Karten mit 8px Radius und Schatten, obwohl alles eckig und flach sein muss
- Schlagzeilen in Sans-Serif oder zu fett (800 statt 500)
- Rot als Markenfarbe für Knöpfe und Links, statt nur als kleines Signal
- Zu viel Weißraum, sodass das dichte Nachrichtenraster wie eine Marketingseite wirkt
- Teaser ohne Meta-Zeile oder mit uneinheitlichem Aufbau
- Reinweißer Seitengrund statt `#f6f6f6`, wodurch die Kartenflächen nicht mehr abgesetzt sind
