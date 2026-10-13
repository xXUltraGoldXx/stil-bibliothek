# Stil: Service klar

## Kurzbeschreibung und Stimmung
Ein funktionaler Service-Auftritt, der Menschen schnell zur Handlung bringt. Hellgrauer Grund, weiße Flächen, sehr dunkles Blaugrau für Text und genau ein kräftiges Signalrot für die Hauptaktion. Im Zentrum steht eine große Such- und Eingabemaske direkt unter dem Kopfbereich. Gefühl: verlässlich, öffentlich, übersichtlich, ohne Schnickschnack. Die Seite wirkt wie ein gut beschildertes Auskunftssystem: jede Fläche hat einen Zweck, jede Aktion ist sofort erkennbar.

## Farbpalette
- Seitengrund `#f0f3f5`, Karten und Kopfbereich `#ffffff`
- Text `#282d37`, sekundär `#3c414b`, gedämpft `#646973`
- Linien und Feldflächen `#d7dce1`
- Signalrot `#e1252f` nur für die Hauptaktion, aktive Unterstreichungen und kleine Akzente (Pfeile, Markierungen)
- Warnorange `#d96000` für Hinweiskästen mit 2px Rahmen, Link-Blau `#0c3992` für Textlinks in der Nebennavigation
- Dunkle Pille `#16181b` mit weißem Text für den gewählten Zustand
- Bildüberlagerung `rgba(0,0,0,.7)` nur für Dialoge
- Keine Verläufe, Rot nie als großer Hintergrund

## Typografie
- Eine serifenlose Familie in zwei Rollen: Source Sans 3 (Google Fonts)
- Überschriften: Gewicht 900, h1 2rem (Mobil 1.5rem), h2 1.5rem (Mobil 1.25rem), h3 1.125rem, Zeilenhöhe 1.25
- Fließtext: Gewicht 400, 1rem, Zeilenhöhe 1.4 (22,4px), auf Mobil 0.875rem
- Hervorhebungen und Navigation: Gewicht 700
- Meta und Kleingedrucktes: 0.75 bis 0.875rem, Farbe `#646973`
- Keine Versalien, keine Laufweitenspielereien, normale Laufweite überall

## Abstände und Raster
- Maximale Breite 1280px, Inhaltsspalte 1200px, auf Mobil Seitenrand 0.5rem
- Innenabstände aus der Reihe 8, 12, 16, 20, 32, 40, 72px (0.5, 0.75, 1, 1.25, 2, 2.5, 4.5rem)
- Karten innen meist 1.25rem, Abschnitte vertikal 2.5 bis 4.5rem
- Lücken zwischen Elementen 1rem, enge Gruppen 0.25rem
- Kartenraster: 3 oder 4 Spalten ab 960px, 2 ab 768px, 1 darunter

## Layout-Muster
- Oben: schmale Meta-Leiste (Grau `#f0f3f5`, 2rem hoch) mit Zielgruppen-Umschalter links und Hilfe-Links rechts
- Darunter weißer Kopfbereich mit Logo links, Hauptnavigation in fetter Schrift, rechts Suche und Anmelden, Schatten 0 2px 8px rgba(0,0,0,.3)
- Hero: breites Bildfeld (Platzhalter) mit einer hellen Angebotskarte rechts darüber, direkt darunter die überlappende Eingabemaske
- Danach Hinweiskästen, Kachelreihe mit Angeboten, Schnellzugriffe als Pillenreihe, Fußbereich mit Spaltenlisten auf grauem Grund
- Alles linksbündig, nur die Hauptaktion rechts am Zeilenende

## Komponenten
- Eingabemaske: weiße Karte, Radius 12px, Schatten wie Kopf, Titel fett mit 3px roter Kurzlinie darunter, Felder mit Grundton `#d7dce1`, Radius 4px, Höhe 3.5rem, Symbol links
- Hauptknopf: Rot `#e1252f`, Text weiß, fett, Radius 4px, Höhe 3.5rem, Innenabstand 0 2rem, Hover dunkler `#b81c26`
- Zweitknopf: weiß, 1px Rahmen `#282d37`, Radius 4px, Text 1rem
- Pillen: Radius 999px, gewählt dunkel `#16181b` mit weißem Text, ungewählt `#d7dce1`
- Hinweiskasten: weiß, 2px Rahmen Orange, linker Streifen Orange mit Symbol, Schließen-Symbol rechts
- Karten: weiß, Radius 12px oder 4px oben, kein Schatten, Bildfläche oben, Titel fett, Text darunter
- Links: unterstrichen, Pfeil-Symbol davor oder danach, Fokusrahmen sichtbar 2px

## Bildsprache
Fotografisch, warm, mit Menschen im Alltag, groß beschnitten und leicht abgedunkelt, damit Karten darüber lesbar bleiben. Dazu schlichte Linienpiktogramme in Textfarbe und eine Rot-Variante für aktive Zustände. Im Beispiel: Bildflächen als CSS-Platzhalter in Graublau mit feinen senkrechten Streifen und eine einfache SVG-Figur.

## Animation
Zurückhaltend und funktional: 0.2s Farbwechsel bei Hover, Ausklappen von Menüs in 0.25s, Karussell mit Wischgeste. Keine Parallax-, Schwebe- oder Einblend-Effekte beim Scrollen.

## Tonfall
Direkt, höflich, handlungsorientiert. Kurze Verben als Knopftexte ("Suchen", "Anzeigen", "Anmelden"), Überschriften als Sachbegriff in zwei bis vier Wörtern, Hinweise klar mit Ursache und nächstem Schritt. Keine Superlative, keine Werbesprache.

## Mach
- Die Eingabemaske als größte, hellste Fläche direkt im ersten Bildschirm platzieren
- Genau eine rote Aktion pro Bereich
- Überschriften in 900er Gewicht, Fließtext in 400er, sonst nichts
- Hinweise als Kasten mit Orange-Rahmen und klarem Schließen-Symbol
- Radien nur 4px (Felder, Knöpfe) und 12px (Karten, Masken)
- Weiß auf hellgrauem Grund für Trennung, Linien nur 1px `#d7dce1`
- Sichtbare Fokuszustände und Mindesthöhe 3rem für Bedienelemente

## Mach nicht
- Keine Verläufe, keine Neonfarben, keine zweite Akzentfarbe neben Rot und Orange-Warnung
- Keine großen Schatten, nur den einen kleinen Schatten für Kopf und Maske
- Keine Serifen, keine Versalien-Überschriften
- Kein dunkler Seitenhintergrund
- Keine zentrierte Marketing-Heldenzeile mit Mega-Schlagzeile
- Keine vollrunden Knöpfe außer Pillen für Filter

## Typische KI-Fehler in diesem Stil
- Rot als Flächenfarbe für ganze Abschnitte oder Hero statt als einzelne Aktion
- Die Eingabemaske klein oder unter dem Falz verstecken, obwohl sie der Kern ist
- Überschriften mit Gewicht 600 statt 900, dadurch fehlt der Kontrast zum Fließtext
- Weiche, große Schatten und Radien von 20px und mehr auf allen Karten
- Dreier-Kachelreihe mit Icon-Kreis, Schlagzeile und Marketing-Satz, zentriert
- Zu viel Weißraum und zu große Hero-Typografie, so geht der Werkzeugcharakter verloren
- Hinweiskasten ohne Orange-Rahmen oder ohne Schließen-Symbol
