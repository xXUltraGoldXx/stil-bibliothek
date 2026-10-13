# Stil: Schwarzstahl Rot

## Kurzbeschreibung und Stimmung
Eine tiefschwarze Bühne für präzise, technische Produkte. Ein einziges Signalrot setzt Akzente, die Schrift ist eine schmale, kräftige Versalien-Grotesk. Der Eindruck ist ruhig, hochwertig und industriell. Der Hero besteht fast nur aus einer riesigen Schlagzeile, die Produktfotos liegen als helle Objekte auf dunklem Grund. Gefühl: Werkzeugkatalog trifft Premium-Marke, nüchtern und kompromisslos.

## Farbpalette
- Tiefschwarz `#000000` für Hero, Header und Footer
- Seitengrund `#0a0a0a` für Inhaltsabschnitte, Karten `#111111`, Flächen-Grau `#141414`
- Signalrot `#df0023`: Knöpfe, Kennzahlen, Links, kleine Rubrik-Zeilen, dünne Linien. Rote Tönung für Hover-Flächen `rgba(223,0,35,.15)`, roter Rahmen `rgba(223,0,35,.3)`
- Text: Weiß `#ffffff` für Überschriften, Hellgrau `#a0a0a0` für Fließtext, `#c7c7c7` für Zwischenstufen
- Linien: `rgba(255,255,255,.06)` bis `.1`, 1px
- Keine Verläufe außer einem kaum sichtbaren Wechsel zwischen `#0a0a0a` und `#0e0e0e`. Keine Schatten

## Typografie
- Schlagzeilen und Navigation: Oswald, Gewicht 600 bis 700, Versalien bei H1, auf Mobil auch bei H2 und H3
- Fließtext und Meta: Inter, Gewicht 400 und 500
- H1: 6rem (Desktop) bis 2.5rem (Mobil), Zeilenhöhe 1.1, Laufweite 0.05em bis 2px
- H2: 2.6rem Desktop, 1.8rem Mobil, Gewicht 700. H3: 1.35rem, Gewicht 600
- Text: 0.85rem bis 1rem, Zeilenhöhe 1.5 bis 1.6, Farbe `#a0a0a0`
- Rubrikzeile: Inter 0.8rem, Gewicht 500, Versalien, Laufweite 0.2em, Rot
- Knöpfe und Menü: Oswald 1rem, Versalien, Laufweite 1px
- Kennzahlen: Oswald 700, 3.5rem, Rot

## Abstände und Raster
- Inhaltsbreite maximal 1152px, seitlich 20px Innenabstand (Mobil 20px)
- Abschnitte: 80px bis 100px vertikal, Mobil 56px
- Kartenraster: vier Spalten mit 16px bis 24px Lücke, ab 900px zwei, ab 560px eine Spalte
- Karteninnenabstand 20px, Knopfinnenabstand 10px 24px (Mobil 14px 24px)
- Header 80px hoch (Mobil 64px), unten 1px Linie `rgba(255,255,255,.1)`
- Hero füllt mindestens 90vh, Inhalt mittig

## Layout-Muster
- Header: Logo-Platzhalter links, Menü mittig in Oswald-Versalien, roter Kontakt-Knopf rechts
- Hero: kleine Zeile oben (Grau oder Rot), darunter eine gewaltige Outline-Schlagzeile (transparente Füllung, 2px weiße Kontur, unten eine weiße Kante), darunter ein roter Knopf. Am Fuß eine 1px breite rote Linie als Scroll-Hinweis
- Produktabschnitt: zentrierte H2, kurze graue Unterzeile, vier gleich hohe Karten mit Bildfläche oben, Titel, Text und roter Textlink mit Pfeil
- Kennzahlen: zentrierte H2, ein Satz, darunter drei rote Zahlen mit grauer Versalien-Beschriftung
- Footer: Logo links, drei Linklisten rechts, darunter volle Trennlinie und kleiner Rechtstext

## Komponenten
- Primärknopf: Fläche `#df0023`, Rahmen 1px `#df0023`, Text weiß, Oswald-Versalien, Radius 4px, kein Schatten. Hover: etwas dunkleres Rot `#b8001d`
- Karten: Fläche `#111111`, Rahmen 1px `rgba(255,255,255,.06)`, Radius 12px, Bild bündig am oberen Rand, Hover hebt den Rahmen auf `rgba(223,0,35,.3)` an
- Textlink: Rot, Inter 500, mit Pfeil "→", Hover heller
- Sprachwahl und Menüpunkte: Weiß, Versalien, ohne Unterstreichung
- Schatten gibt es nicht, Tiefe entsteht durch Flächenabstufung von `#000` zu `#0a0a0a` zu `#111`

## Bildsprache
Produktfotos als freigestellte oder auf dunklem Studiohintergrund fotografierte Objekte in kühlem Licht mit Metallglanz. Der Hintergrund ist anthrazit und geht in das Seitenschwarz über. Einzelne goldene oder rote Details dürfen funkeln. Im Beispiel: CSS-Flächen aus dunklen Verläufen mit einem hellen, metallisch wirkenden Formelement als Platzhalter.

## Animation
Zurückhaltend und sauber: Einblenden und leichtes Hochgleiten (0.6s, ease-out) beim Erscheinen, Hover auf Karten und Knöpfen 0.2s bis 0.3s. Der Hero darf die Schlagzeile von Kontur zu Füllung wechseln lassen. Ein Lichtfleck, der dem Zeiger folgt, ist möglich. Respektiere prefers-reduced-motion.

## Tonfall
Knapp, sachlich, selbstbewusst. Zweiwort-Schlagzeilen im Imperativ oder als Behauptung. Konkrete Eigenschaften statt Schwärmerei, Zahlen und Fakten als Beleg. Unterzeilen in einem Satz.

## Mach
- Fast alles in Schwarz und Anthrazit halten, Rot nur für Handlung und Kennzahl
- Hero mit einer sehr großen Versalien-Schlagzeile in Oswald
- Karten gleich hoch, Bild oben, roter Textlink unten
- Dünne 1px-Linien in Weiß mit 6 bis 10 Prozent Deckkraft
- Große rote Kennzahlen mit kleiner grauer Beschriftung
- Mobil: Schlagzeile umbrechen lassen, Knopf mittig, Menü einklappen

## Mach nicht
- Keine weißen oder hellen Flächen als Abschnittsgrund
- Keine zweite Akzentfarbe, kein Blau, kein Verlauf-Rot
- Keine Schatten, kein Glas-Effekt, keine bunten Icons
- Keine serifenlose Standardschrift für Schlagzeilen statt Oswald
- Keine runden Pillen-Knöpfe, Radius bleibt 4px

## Typische KI-Fehler in diesem Stil
- Reines Schwarz überall, ohne die Abstufung `#000`, `#0a0a0a`, `#111`, wodurch die Karten verschwinden
- Rot als Hintergrund ganzer Abschnitte statt als sparsamer Akzent
- Schlagzeilen in Mixed Case und Gewicht 400, dadurch geht der technische Ausdruck verloren
- Karten mit Glow, Schatten oder großem Radius über 12px
- Grauer Text unter 4.5:1 Kontrast auf Schwarz, etwa `#555`, statt `#a0a0a0`
- Outline-Schlagzeile ohne ausreichende Strichstärke, auf Mobil unlesbar
