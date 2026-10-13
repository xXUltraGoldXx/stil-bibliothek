# Stil: Sportkatalog kantig

## Kurzbeschreibung und Stimmung
Ein selbstbewusster Online-Katalog im Sport- und Streetwear-Umfeld. Die Seite ist überwiegend weiß, wird oben von einer tiefschwarzen Navigationsleiste gerahmt und unten von einem schwarzen Fußbereich abgeschlossen. Dazwischen tragen große Fotos die Stimmung. Die Typografie ist schmal, fett und meist in Versalien, wie auf einem Trikot oder Etikett. Ein einziges helles Flieder-Band (`#d7dcfe`) markiert Aktionen. Gefühl: direkt, sportlich, übersichtlich, kaufbereit. Jede Kachel führt mit genau einem Knopf zum nächsten Schritt.

## Farbpalette
- Grund: Weiß `#ffffff`, nimmt rund 80 % der Fläche ein
- Text und Leisten: Tiefschwarz `#191919` (Navigation, Fuß, Fließtext, Knopf-Füllung)
- Reines Schwarz `#000000` für Overlays, Hinweisleisten und Hero-Verläufe
- Aktionsband: Flieder `#d7dcfe`, nur für eine schmale Banderole unter der Navigation, Text darauf `#191919`
- Graustufen: `#dfe0e1` (Text auf Schwarz), `#a1a8af` (Fußtexte, Zweittext), `#7c7e83` (Hinweise), `#e5e7eb` (Feldrahmen), `#676d75` (feine Rahmen auf Schwarz)
- Keine Akzentfarbe außer Flieder. Keine Farbverläufe außer einem Abdunkeln über Fotos

## Typografie
- Eine Schriftfamilie, DIN-artig und schmal: Barlow Semi Condensed (Google Fonts), Gewichte 400 und 700, Rückfall Arial Narrow, Arial
- Nur zwei Gewichte: 400 und 700. Nichts dazwischen
- H1 (Hero): 3rem (48px), Zeilenhöhe 1, Gewicht 700, Versalien, Weiß auf Foto. Mobil 1.75rem
- H2 (Abschnittstitel): 2rem (32px), Zeilenhöhe 1.125, 700, Versalien, zentriert. Mobil 1.75rem
- Kachel-Titel: 1.25rem bis 1.75rem, 700, Versalien, zentriert
- Untertitel unter Titeln: 0.8125rem (13px), 400, Versalien, Laufweite 0.01em, Zeilenhöhe 1.5
- Fließtext 1rem (16px), Zeilenhöhe 1.5 (24px)
- Knopfschrift 0.8125rem bis 1rem, 700, Versalien
- Kleingedrucktes 0.75rem bis 0.875rem, Grau `#a1a8af`

## Abstände und Raster
- Basiseinheit 4px, gängige Stufen 4, 8, 12, 16, 24, 32, 40, 64px
- Seitenrand 20px (mobil 16px), maximale Inhaltsbreite 1600px
- Kachelraster: 3 Spalten mit 16px Lücke, zweite Reihe mit 2 großen Spalten, mobil 1 Spalte
- Innenabstand Knöpfe 12px 16px, Felder 14px 12px
- Abschnitte trennt viel Weiß: 64px oben und unten, Titel zu Raster 24px
- Keine Trennlinien zwischen Abschnitten, die Fotoflächen gliedern allein

## Layout-Muster
- Oben eine schmale weiße Hinweiszeile (Versalien, 0.8125rem, mittig, Unterstreichung bei Link)
- Darunter die schwarze Navigationsleiste, 80px hoch: links Wortmarke, daneben Hauptkategorien in Versalien 700, rechts Suchfeld mit 1px Rahmen und Icons
- Flieder-Banderole, mittig: fetter Titel, Satz, zwei unterstrichene Links
- Hero: vollbreites Foto, Text links unten, großer Titel, Untertitel, weißer Knopf
- Danach Abschnitte mit mittigem Titel, darunter Foto-Kacheln. Unter jedem Foto: Titel, Untertitel, ein schwarzer Knopf, alles mittig
- Schwarzer Fußbereich in vier Spalten mit Linklisten in Grau, Spaltenüberschriften in Versalien 700

## Komponenten
- Primärknopf auf hellem Grund: Fläche `#191919`, Text weiß, 700, Versalien, Radius 2px, Padding 12px 16px
- Primärknopf auf Foto oder Schwarz: Fläche weiß, Text `#191919`, gleiche Form
- Sekundärknopf: transparent, Text weiß oder schwarz, nur Text oder 1px Rahmen
- Textlinks: 700, Versalien, 2px Unterstreichung statt Farbwechsel
- Suchfeld: 1px Rahmen `#676d75`, Radius 2px, Icon plus Text
- Eingabefelder: 1px `#e5e7eb`, Radius 0, Schrift 700 mit Laufweite 0.02em
- Runde Elemente (Radius 9999px) nur für kleine Symbolknöpfe und Zähler
- Schatten: nur einer, `0 0 18px rgba(0,0,0,.2)` für schwebende Panels

## Bildsprache
Großformatige Produkt- und Personenfotos, ohne Rahmen, bündig in der Kachel, hohe Sättigung, oft Studio mit dunklem oder farbigem Hintergrund und Straßenszenen. Keine Bildunterschriften, der Titel darunter übernimmt das. Im Beispiel: CSS-Flächen aus Farbverläufen und einfachen SVG-Formen in Schwarz, Grau und Flieder als Platzhalter.

## Animation
Zurückhaltend. Knöpfe wechseln in 0.2s die Fläche (Schwarz zu `#333333`, Weiß zu `#dfe0e1`). Menüs und Panels blenden in 0.25s ein. Fotos dürfen beim Hover um höchstens 3 % zoomen. Keine Parallax, keine Dauerschleifen.

## Tonfall
Kurz, direkt, imperativ. Titel aus zwei bis vier Wörtern, Untertitel als knappe Zeile mit einem Bild im Kopf. Aktionen heißen immer "Jetzt …" oder ähnlich knapp. Du-Ansprache. Kein Fließtext-Blabla, Sätze unter 12 Wörtern.

## Mach
- Weißen Grund, schwarze Leisten und Fotos als einzige große Farbquellen verwenden
- Versalien für Titel, Navigation und Knöpfe, schmale Schrift in nur 400 und 700
- Kachelmuster wiederholen: Foto, Titel, Untertitel, ein Knopf, mittig
- Flieder `#d7dcfe` sparsam als einzelnes Band einsetzen
- Knopfradius 2px, Padding 12px 16px
- Auf Mobil Raster auf eine Spalte stapeln, Knöpfe bleiben gut greifbar (mindestens 44px Höhe)

## Mach nicht
- Keine Pastellkarten mit großen Radien, keine Schatten außer dem einen
- Keine Serifenschrift, keine Gewichte 300 oder 500
- Keine Farbverlaufs-Knöpfe, keine zweite Akzentfarbe
- Keine langen Fließtexte in der Kachel
- Keine Trennlinien zwischen Abschnitten
- Keine Kleinschreibung in Titeln und Knöpfen

## Typische KI-Fehler in diesem Stil
- Runde Pillenknöpfe oder große Radien statt scharfer 2px-Kanten
- Breite, runde Sans-Serif wie bei SaaS-Seiten statt einer schmalen DIN-artigen Schrift
- Flieder oder eine Akzentfarbe großflächig eingesetzt statt als schmales Band
- Kacheln mit Rahmen, Schatten oder Kartenhintergrund, obwohl das Foto bündig und ohne Karte steht
- Titel in Satzschreibung statt Versalien und linksbündig statt mittig
- Navigation hell statt tiefschwarz, wodurch der Kontrast zum Weiß fehlt
- Zu viel Text und zu viele Knöpfe pro Kachel
