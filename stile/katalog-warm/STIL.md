# Stil: Katalog warm

## Kurzbeschreibung und Stimmung
Ein hochwertiger Online-Katalog für Wohnprodukte. Eine zarte, große Serifen-Schlagzeile steht auf einem vollflächigen, warmen Foto. Darunter folgen helle, ruhige Produktkarten auf kühlem Hellgrau. Der Bereich um die Inhalte ist neutral, die Wärme kommt aus den Bildern und aus einem schmalen Terrakotta-Band oben. Gefühl: gepflegtes Einrichtungshaus, einladend, sachlich, mit klaren Verkaufsimpulsen (Aktion, Kategorie-Tabs, Merkliste).

## Farbpalette
- Tinte (Text, Hauptknopf, Kopfzeilen): `#1a1817`
- Grundfläche: `#f7f7f7`, Kartenfläche und Kopfzeile `#ffffff`, Linien und zweite Fläche `#e6e6e6`
- Sekundärtext, inaktive Tabs: `#808080`, dunkleres Grau `#4d4d4d`
- Signalrot für Aktionsknopf und Rabatt-Plaketten: `#c8102e`, Hover `#b90003`; Rot als Text (Sale-Menüpunkt): `#b30000`
- Terracotta-Band (Ankündigungsleiste): `#da8d55`, dunkle Schrift darauf `#3b1e14`
- Warmes Creme `#f6f4ef` für einzelne Textbänder
- Über Fotos: Verlauf von schwarz 20 % bis 30 % bei 75 % Höhe, dann transparent, damit weiße Schrift lesbar bleibt
- Rot sparsam: Knopf, Plakette, ein Menüpunkt. Keine weiteren Akzentfarben.

## Typografie
- Schlagzeilen: leichte Serife, Newsreader (Google Fonts), Gewicht 400, Laufweite 0.004em. Hero bis 5.6rem (90px) mit Zeilenhöhe 1.22, Abschnittstitel 2.5rem bis 3.25rem (40 bis 52px) mit Zeilenhöhe 1.2. Mobil Hero 2.25rem, Titel 1.9rem.
- Fließ- und UI-Text: Manrope (Google Fonts), Gewichte 500, 600, 800. Basisgröße 0.8125rem (13px), Laufweite 0.01em, Zeilenhöhe 1.5; Navigation und Links 0.9375rem (15px).
- Knöpfe, Tabs, Menü, Kicker: Versalien, Manrope 800 (Knöpfe) bzw. 500 bis 600 (Menü), 0.9375rem, Laufweite 0.15em.
- Kleine Meta- und Plakettentexte: 0.6875rem (11px), Gewicht 800, Versalien, Laufweite 0.1em.
- Stufen: Hero, Titel, Kicker, Navigation, Text, Meta. Kein Text unter 11px.

## Abstände und Raster
- Seitenrand 3rem Desktop (48px), 1rem mobil (16px); Inhalte bis 1280px.
- Kartenreihe: Karten ca. 254px breit, 1rem Lücke, am Rand angeschnitten (Hinweis auf Weiterwischen).
- Abschnittsabstand 4rem bis 5rem, mobil 2.5rem.
- Kartenpolster 0.75rem, Tabs mit 2rem Lücke, Knopfpolster 20px 48px 22px (mobil 20px 16px 22px).
- Abstufung der Innenabstände: 2, 5, 10, 16, 24, 32, 48, 60 px.

## Layout-Muster
- Ganz oben Ankündigungsband (Terracotta, zentrierter kleiner Text, rechts Nebenlinks), darunter weiße Kopfzeile mit Wortmarke links, breitem Suchfeld in der Mitte und Symbolen rechts, darunter eine zentrierte Menüzeile in Versalien mit feiner Linie.
- Hero: vollbreites Foto, ca. 500px hoch, Kicker in Versalien, riesige zentrierte Serifen-Zeile, ein roter Knopf; alles mittig.
- Danach zentrierte Abschnittstitel mit Tab-Leiste (aktiver Tab Tinte mit 2px Unterstrich, andere grau) und einer waagerechten Karten-Reihe.
- Fußbereich: 12-Spalten-Raster, mobil 4 Spalten, Linklisten in Manrope 500.

## Komponenten
- Hauptknopf: rechteckig (Radius 0), Fläche Tinte `#1a1817` oder Rot `#c8102e`, Schrift weiß, Versalien, Manrope 800, 0.9375rem, Laufweite 0.15em, kein Schatten.
- Plakette "Sale": Pille, Radius 999px, Rot, weiße Versalien 0.6875rem, links oben auf der Karte.
- Produktkarte: Fläche `#f7f7f7`, Radius 12px, kein Schatten, Bildfläche oben, darunter Name (Gewicht 600), Preis, Herz-Symbol rechts oben als Linienzeichnung.
- Suchfeld: weiß, 1px Rand `#e6e6e6`, Radius 4px, Platzhalter grau.
- Tabs: Text-Tabs, aktiv mit Unterstrich, inaktiv `#808080`.
- Eingabefelder allgemein: weiß, 10px Polster, kein dicker Rahmen.
- Schatten: praktisch keine. Radien: 0 für Knöpfe, 4px für Felder, 12px für Karten.

## Bildsprache
Warme, gemütliche Innenraum- und Detailfotos mit Tiefenschärfe, Erdtöne (Ocker, Braun, Sand), oft mit Tieren oder Menschen im Alltag. Produktbilder frei auf hellgrauem Grund. Im Beispiel: CSS-Verläufe und Muster in Erdtönen als Platzhalter, keine echten Bilder.

## Animation
Dezent. Ankündigungsband und Hero dürfen als Karussell wechseln (mit Pause-Knopf im Kreis unten rechts). Hover bei Knöpfen: Farbwechsel in 0.2s. Karten-Reihe wischt horizontal. Keine Parallax-Effekte, keine großen Bewegungen.

## Tonfall
Freundlich, kurz, handelsnah. Aktionen klar benannt ("Jetzt ansehen"), kurze Zeitangaben und Prozentzahlen als Schlagzeile. Keine Übertreibung, keine Ausrufezeichen-Ketten.

## Mach
- Leichte Serifen-Schlagzeile in Gewicht 400 mit Versalien-Sans für alles Bedienbare
- Genau ein rechteckiger, kräftiger Knopf pro Bildschirmbereich
- Foto mit dunklem Verlauf unterlegen, damit weiße Schrift trägt
- Karten auf `#f7f7f7` mit 12px Radius, ohne Schatten
- Terracotta-Band oben als warmer Farbakzent
- Karten am Rand anschneiden, damit Wischen erkennbar ist

## Mach nicht
- Keine fetten Serifen-Schlagzeilen und keine Sans-Serif-Hero-Zeile
- Keine runden Knöpfe, keine Schatten unter Knöpfen
- Kein zweites Rot und keine Blau- oder Grüntöne als Akzent
- Keine Rahmen um Karten, keine Verläufe auf Flächen außer über Fotos
- Keine Fließtexte über 13px in zentrierter Ausrichtung

## Typische KI-Fehler in diesem Stil
- Knöpfe mit runden Ecken oder Pillenform statt eckig
- Schlagzeile in fetter Serife oder Sans statt leichter Serife mit Gewicht 400
- Versalien-Knöpfe ohne Laufweite (0.15em fehlt), dadurch wirken sie billig
- Karten mit Schatten und Rand statt flacher hellgrauer Fläche
- Rot großflächig statt nur Knopf, Plakette und ein Menüpunkt
- Hero ohne dunklen Verlauf, weiße Schrift auf hellem Bild kaum lesbar
- Basisschrift auf 16px aufgeblasen statt 13px mit großzügigem Zeilenabstand
