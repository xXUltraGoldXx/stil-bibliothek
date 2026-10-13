# Stil: Freundlich warm

## Kurzbeschreibung und Stimmung
Eine Produkt- und Marketingseite, die Software nahbar macht. Eine weiche, lesbare Serife für Schlagzeilen trifft auf eine schlichte, neutrale Grotesk für alles Funktionale. Statt kaltem Schwarz und Blau dominiert ein warmes Braunschwarz (`#2a2418`). Genau ein Signal leuchtet: Butter-Gelb (`#fbdc35`), reserviert für Knöpfe, Pfeile, Sterne und die kursive Betonung in der Hero-Zeile. Gefühl: ein freundlicher Laden mit guter Beratung, kein Konzern-Dashboard. Große Fotos mit dunklem Verlauf, runde weiche Karten, ruhige Flächen in Weiß, Hellgrau und Sand.

## Farbpalette
- Tinte (Text, dunkle Flächen, Ringe): `#2a2418`
- Tinte gedämpft für Nebentext: `rgba(42,36,24,.65)`, Fließtext in Sektionen `#403b3b`
- Signal Butter-Gelb: `#fbdc35` (Knopffläche), Hover-Marker `rgba(251,220,53,.65)`, Hellton auf Dunkel `#fcf3c8`
- Weiß `#ffffff` Hauptfläche, Hellgrau `#f5f5f5` für Kartenbereiche, Eisblau `#f0f4f6` selten für Produkt-Mockups
- Sand `#ebe1cd` für Zitat- und Hinweisbänder
- Senf `#dfb36a` ausschließlich für den Footer und eine einzelne Akzentfläche
- Dunkelbraun für Leisten: `#39352c`, Ankündigungsleiste in `#2a2418`
- Linkfarbe im Fließtext Petrol `#004e56`, in Navigation und Karten Tinte
- Linien: `#bcbab6` (1px), Deaktiviert `#dbd9d2`
- Foto-Verlauf von oben nach unten: `rgba(42,36,24,0)` 0%, `rgba(42,36,24,.55)` 45%, `rgba(42,36,24,.82)` 100%

## Typografie
- Schlagzeilen: Fraunces (Google Fonts), Gewicht 400, nie fett. Variable Achsen weich halten (SOFT 100, falls verfügbar).
- UI und Fließtext: Figtree (Google Fonts) als Ersatz für die neutrale Grotesk, Gewichte 400, 500, 600.
- Hero-H1: 4rem (64px), Zeilenhöhe 1.2, Laufweite -1.2px, auf Mobil 2.25rem (36px) mit Zeilenhöhe 1.3
- H2: 2.2rem (35px), Zeilenhöhe 1, Laufweite -0.5px, Mobil 1.8rem
- H3 (Kartentitel): 1.4rem, Zeilenhöhe 1.33, Gewicht 400
- Betonung: Kursiv in `#fbdc35` auf dunklem Foto, zweite Zeile der Hero-Schlagzeile
- Lead: 1.25rem, Zeilenhöhe 1.4. Fließtext 1rem, Zeilenhöhe 1.5. Info-Text 0.8125rem, Zeilenhöhe 1.25. Rechtstext 0.6875rem
- Knopftext: 0.8125rem (13px), Gewicht 500, Zeilenhöhe 1.5, keine Versalien
- Keine Laufweite bei Fließtext, Überschriften leicht enger

## Abstände und Raster
- Basiseinheit 4px: 4, 8, 12, 16, 24, 32, 48, 64 als feste Stufen
- Modul-Innenabstand 48px (3rem), reduziert 24px; Sektionen vertikal 64 bis 80px
- Inhaltsbreite 1152px bei 1280px Fenster, Textspalten 640px, Hero-Text bis 960px zentriert
- Karten: Innenabstand 24px, Lücke 16 bis 24px, zwei Spalten ab 800px, darunter eine
- Karten innen zweispaltig: Text links, Bildfläche rechts, Pfeil-Link unten links
- Mobil: 16px Seitenrand, Karten volle Breite, Knöpfe volle Breite

## Layout-Muster
- Ankündigungsleiste oben: 42px hoch, `#2a2418`, weißer 13px-Text, ein unterstrichener Link
- Navigation weiß, 68px hoch, links Wortmarke, Mitte Menüpunkte, rechts Telefon, gelber Knopf, Umriss-Knopf
- Hero: Vollbreites Foto, dunkler Verlauf von unten, zentrierte Schlagzeile in Weiß mit gelber Kursivzeile, Lead, ein großer gelber Knopf, darunter Sterne-Bewertung und Siegel-Reihe. Mobil linksbündig
- Direkt unter dem Hero eine dunkelbraune Leiste (`#39352c`) mit Hinweis links und Pfeil-Link rechts
- Kartenbereich auf `#f5f5f5`: Abschnittstitel links, 2x2 weiße Karten, darunter ein zentrierter Pillen-Knopf
- Wechselnde Bänder: Weiß, Hellgrau, Dunkelbraun mit großer Serifenaussage, Sand mit Zitat, Senf-Footer
- Siegel-Reihe: eine Zeile gedämpfter Logos auf Foto, zentriert

## Komponenten
- Primärknopf: Fläche `#fbdc35`, Ring `0 0 0 1px #2a2418`, Radius 2em (Pille), Innenabstand 16px 24px, Text `#2a2418` 13px Gewicht 500. Hover: Ring bleibt, Fläche wird `#fcf3c8`
- Sekundärknopf: Weiß, gleicher Ring und Radius, Tinte
- Pfeil-Link: Text plus kleiner gelber Kreis (28 bis 32px) mit Tinte-Pfeil
- Karte: Weiß, Radius 24px, Schatten `0 15.5px 44px rgba(0,0,0,.086)`, innen eine Bildfläche mit Radius 16px
- Häkchenliste: kleiner dunkler Kreis mit weißem Haken, Text 13px
- Tab-Leiste: Pille mit 1px Rand, aktiver Tab als gefüllte Tinte-Pille mit weißer Schrift
- Eingabefelder: 1px Rand `#bcbab6`, Radius 4px, Fokus Ring 2px Tinte
- Radien: 4px (Felder), 16px (Bildflächen), 24px (Karten), 2em (Knöpfe)
- Schatten nur auf Karten und schwebenden Panels; Fokus: Ring 2px Tinte mit 2px Abstand

## Bildsprache
Warme, echte Fotos von Menschen bei der Arbeit, Handwerk und Alltag, mit gedämpftem Licht und Erdtönen. Auf Fotos immer der braune Verlauf für Lesbarkeit. Produkt-Mockups sitzen auf sandfarbenen oder eisblauen Flächen mit 16px-Radius. Illustrationen sind sparsam, flächig, in Tinte, Gelb und Sand. Im Beispiel: Flächen aus CSS-Verläufen und einfache SVG-Formen als Platzhalter.

## Animation
Zurückhaltend. Übergänge 0.2s mit `cubic-bezier(0,0,0,1)` für Einblenden von Menüs und Hover (Deckkraft, Hintergrund). Pfeil-Kreise dürfen sich 2px nach rechts bewegen. Keine Parallax, keine Dauerschleifen. `prefers-reduced-motion` respektieren.

## Tonfall
Direkt, hilfsbereit, in Du-Form. Kurze Aussagesätze mit Nutzenversprechen, konkrete Zahlen als Beleg. Schlagzeile in zwei Teilen: Kernaussage, dann kursive Ergänzung, die Reibung nimmt. Knopftexte sind Verben mit geringem Risiko, zum Beispiel "Kostenlos testen".

## Mach
- Schlagzeilen in Serife, Gewicht 400, mit kursiver Betonung in Gelb auf dunklem Grund
- Tinte `#2a2418` statt reinem Schwarz für Text und Dunkelflächen
- Gelb nur für Handlungen: Knöpfe, Pfeile, Sterne
- Knöpfe als Pillen mit 1px Tinte-Ring
- Karten mit 24px Radius, weichem großem Schatten und einem Pfeil-Link
- Fotos mit Verlauf `rgba(42,36,24,0)` bis `rgba(42,36,24,.82)`
- Wechselnde Bänder in Weiß, Hellgrau, Dunkelbraun, Sand und Senf
- Zahlen und Siegel als Belege direkt unter dem Hero

## Mach nicht
- Kein reines Schwarz `#000` als Flächenfarbe, kein kühles Blau
- Kein Gelb für Fließtext auf Weiß, es hat keinen Kontrast
- Keine fetten Serifen, keine Versalien in Schlagzeilen
- Keine eckigen Knöpfe, keine Verläufe auf Knöpfen
- Keine harten Schlagschatten und keine Kartenrahmen zusätzlich zum Schatten
- Keine zweite Signalfarbe neben Gelb
- Keine Fachbegriff-Schlagzeilen, keine Sie-Form

## Typische KI-Fehler in diesem Stil
- Grotesk für Schlagzeilen gewählt, wodurch die weiche Serife als Markenzeichen fehlt
- Gelb als Hintergrund ganzer Sektionen statt als kleiner Signalpunkt
- Knöpfe ohne Tinte-Ring, dadurch wirkt das Gelb flach und verwaschen
- Schwarz `#000` statt warmem Braunschwarz, das Ergebnis wirkt kalt
- Foto-Hero ohne Verlauf, weiße Schrift verliert Kontrast
- Karten zu eckig oder mit dünnem Rahmen statt weichem Schatten
- Kursive Betonung weggelassen oder in Weiß statt Gelb gesetzt
- Zu viele Bildkacheln ohne Text, der Nutzen geht verloren
