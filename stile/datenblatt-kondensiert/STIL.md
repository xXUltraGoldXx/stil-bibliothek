# Stil: Datenblatt kondensiert

## Kurzbeschreibung und Stimmung
Ein technisches Datenblatt auf warmem Papier. Enge, kräftige Grotesk-Schlagzeilen, kleine Monospace-Werte, harte 2px-Rahmen in Tinte und genau ein Signalorange. Das Gefühl ist das eines gut gebauten Messgeräts: sachlich, präzise, ehrlich und ohne Marketing-Glanz. Die Seite zeigt ihr Produkt als Gerät mit echten Zahlen, nicht als Versprechen.

## Farbpalette
- Papier (Seitenhintergrund) `#f7f6f2`, Papier gedimmt für abgesetzte Sektionen `#eceae2`, Panel weiß `#ffffff`
- Tinte `#141414` für Überschriften, Rahmen, dunkle Bänder und Hauptknöpfe; sekundärer Text `#4a4a4a`
- Linie fein `#d8d4c8`
- Signalorange `#F4501E` nur für Rubriknummern, einen Primärknopf, Fokusring und kleine Akzente; dunkle Variante für Text auf hellem Grund `#9c440f`
- Statusgrün `#2e7d32` und Fehlerrot `#c62828` nur für Zustände
- Geräteflächen als kühles Silber-Verlauf: `linear-gradient(155deg,#fcfcfd,#e8eaed)`; Verläufe sonst nirgends

## Typografie
- Schlagzeilen: Barlow Condensed (Google Fonts), Gewicht 700. H1 76px (mobil 41.6px) mit Zeilenhöhe 0.95 und Laufweite -0.01em; H2 44px (mobil 32px) mit Zeilenhöhe 1; H3 24px mit Laufweite 0.01em
- Fließtext: Barlow 400, 1.19rem (19px) im Lead, sonst 0.95rem bis 1rem, Zeilenhöhe 1.55, Farbe `#4a4a4a`
- Werte, Ticker, Rubriknummern: JetBrains Mono 400, 0.78rem, Versalien, Laufweite 0.12em bis 0.2em
- Links und Knopftexte: Barlow Condensed 700, Versalien, Laufweite 0.02em, 1rem bis 1.35rem
- Gewichte: 400 Text, 600 Labels, 700 Schlagzeilen und Knöpfe

## Abstände und Raster
- Maximale Inhaltsbreite 1080px, zentriert, seitlich mindestens 24px
- Sektionen oben und unten 64px, mobil 44px
- Karten- und Panel-Innenabstand 20px bis 24px, Lücken 8px, 14px, 22px, 32px
- Hero und Detail als Zweispalter (1.2fr zu 1fr), unter 800px einspaltig
- Sektionen werden durch 2px-Tintenlinien getrennt oder durch Wechsel zwischen Papier und gedimmtem Papier

## Layout-Muster
- Kopfzeile: 62px hoch, Papier mit 94% Deckkraft, unten 2px Tintenlinie, links Marke in Versalien, rechts Textlinks und ein dunkler Knopf
- Hero: Tag mit 2px Rahmen, riesige zweizeilige Schlagzeile, Lead, rechts ein Geräte-Mockup mit Display voller Messwerte
- Direkt unter dem Hero ein schwarzes Band (50px) mit Monospace-Fakten in Versalien, horizontal gereiht, auf Mobil umbrechend
- Sektionen beginnen mit Rubrik "01 — Titel" in Orange Mono, dann H2, dann Einleitung
- Eine nummerierte Liste mit dünnen Linien, bei der der aktive Punkt aufklappt, ersetzt klassische Kachelreihen
- Zweiteiliger Kontrastblock: links Tinte, rechts Orange, je mit Versalien-Titel

## Komponenten
- Tag: 2px Rahmen in Tinte, Radius 0, Padding 12px 14px, Mono oder Barlow 700 Versalien, Laufweite 0.12em
- Primärknopf: Orange `#F4501E`, Text weiß, Barlow Condensed 700 Versalien mit Pfeil, Radius 0 bis 6px, Padding 14px 22px
- Sekundärknopf: 2px Rahmen in Tinte, transparent, gleiche Schrift; Hover füllt mit Tinte
- Dunkler Knopf in der Kopfzeile: Tinte, Papiertext, Radius 6px
- Panel: weiß, 1px Rahmen `#d8d4c8`, Radius 0, keine Schatten
- Geräte-Mockup: Radius 38px bis 46px, Silberverlauf, Schatten `0 20px 44px rgba(20,20,20,.22)` plus feiner heller Innenrand
- Fokus: 3px Papier, außen 2px Orange
- Messwert-Kachel: 2px Rahmen, kleines Label in Mono, große Zahl in Barlow Condensed 700

## Bildsprache
Das Produkt selbst ist das Bild: ein Gerät oder Bildschirm mit lesbaren Zahlen, Schwarz auf Weiß, wie ein E-Paper-Display. Bildschirmfotos stecken in Geräterahmen mit Silberverlauf und weichem Schatten. Keine Stockfotos, keine Menschen, keine Illustrationen. Im Beispiel entstehen Gerät und Display rein aus CSS-Flächen und Zahlen.

## Animation
Nahezu keine. Hover-Wechsel 0.15s bis 0.2s auf Farbe und Hintergrund, Aufklappen der Listenpunkte ohne Bewegung oder mit 0.2s Höhenübergang. Kein Parallax, keine Scroll-Effekte, keine Einblendungen.

## Tonfall
Sachlich, konkret, in kurzen Aussagesätzen. Zahlen und Einheiten statt Adjektiven, ehrliche Hinweise zu Grenzen ("Du kaufst und schützt das Board selbst"). Duzen ist passend. Überschriften benennen, was etwas tut, nicht wie begeisternd es ist.

## Mach
- Schlagzeilen immer in enger Grotesk Gewicht 700, Fließtext in der normalen Breite derselben Familie
- Ein Orange pro Ansicht als Leitfarbe, sonst Tinte und Papier
- Rubriken nummerieren und in Mono-Versalien setzen
- Fakten als schwarzes Ticker-Band mit Monospace zeigen
- Produkt als Gerät mit echten, plausiblen Messwerten darstellen
- Harte 2px-Rahmen in Tinte für Tags, Messkacheln und Sekundärknöpfe
- Abwechselnd Papier und gedimmtes Papier für Sektionen

## Mach nicht
- Keine Verläufe außer dem silbernen Gerätekörper
- Keine großen weichen Kartenschatten auf Inhalten
- Keine Emoji und keine runden Icon-Kreise als Dekor
- Keine zweite Akzentfarbe neben dem Orange
- Keine zentrierte Dreier-Kachelreihe mit Icons als Standardlösung
- Keine Serifen und keine verspielten Schriften
- Keine Stockfotos

## Typische KI-Fehler in diesem Stil
- Die Schlagzeile in normaler Breite statt in der engen Condensed-Variante setzen, wodurch der technische Charakter verschwindet
- Orange großflächig für Hintergründe und viele Knöpfe nutzen statt sparsam
- Allen Karten runde Ecken und weiche Schatten geben, obwohl Rahmen eckig und flach sind
- Das Papier durch reines Weiß `#ffffff` ersetzen und damit den warmen Ton verlieren
- Monospace weglassen, sodass Ticker und Rubriknummern wie normaler Text wirken
- Platzhalter-Lorem und vage Adjektive statt konkreter Zahlen und Einheiten
- Kopfzeile ohne die 2px-Tintenlinie darunter
