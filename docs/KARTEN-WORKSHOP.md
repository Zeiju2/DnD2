# AdventureShift – Karten-Workshop: beschlossene Funktionen

**Stand:** 11.10.2026  
**Status:** Entscheidungen zum Karten- und Szenensystem. Kein Programmcode. Der Hauptkatalog steht in [FEATURE-WORKSHOP.md](FEATURE-WORKSHOP.md); hier werden die Kartendetails fortgeführt.

## Bisherige Entscheidungen

| Punkt | Entscheidung | Status |
| --- | --- | --- |
| 02.1 | Kartenbilder hochladen **und** Karten direkt im Browser erstellen | Beschlossen: C |
| 02.2 | **Schnellmodus** zum Skizzieren und **erweiterter Baumodus** mit Tiles/Bauteilen und Ebenen; beide bearbeiten dieselbe Szene | Beschlossen: C |
| 02.3 | **Taktikkarten**, **Welt-/Reisekarten**, **Story-/Atmosphäre-Szenen** sowie **freier Spieltisch** | Beschlossen: C |
| 02.4 | **Rasterfrei**, **Quadratraster** oder **Hexraster**, frei konfigurierbare Maßeinheit und Maßstab je Szene | Beschlossen: C |
| 02.5 | Manuelle Sichtfreigabe und dynamische Sicht, pro Szene wählbar; Spielleiter kann jederzeit eingreifen | Beschlossen: C |
| 02.6 | Erkundete Flächen vollständig verbergen oder abgedunkelt als Erinnerung anzeigen | Beschlossen: C |
| 02.7 | Sicht und Entdeckungen pro Szene gemeinsam oder individuell verwalten | Beschlossen: C |
| 02.8 | Einfache und dynamische Beleuchtung, feste und bewegliche Lichtquellen | Beschlossen: C |
| 02.9 | Wände, Türen und Fenster – Sicht, Licht und Bewegung | Als Nächstes |

## 02.4 – Raster und Maßstab (11.10.2026)

**Beschluss:** Für jede Szene kann der Spielleiter Rastermodus, Feldgröße, Maßstab und Maßeinheit einstellen. Beispiele: 1 Feld = 1 Meter, 1 Feld = 1,5 Meter, 1 Feld = 5 Fuß, oder eine eigene frei benannte Einheit.

- Rastermodi: **kein Raster**, **Quadrat**, **Hex**.
- Das Raster kann sichtbar oder verborgen sein, ohne Kartenbild, Token, Objekte oder Zeichnungen zu löschen.
- **Rasteranzeige** und **Einrasten am Raster (Snap)** sollen getrennte Einstellungen sein. Freie Bewegung bleibt bei Bedarf möglich.
- Marker und Figuren benötigen rasterunabhängige kanonische Weltpositionen; Rendern und Messung beziehen sich auf die Szeneinstellungen.
- Ein Szenenwechsel soll weder Charaktere noch Kampagneninventare beeinflussen.
- Alle Einstellungen und Positionen müssen bei Reconnect und Neustart erhalten bleiben.

**Offen und nicht als beschlossen zu behandeln:** Hexausrichtung (spitze/flache Oberkante), Diagonalbewegungsregeln, Positionieren und Ausrichten des Rasters über importierten Bildern, Raster-Snap im Kampf, konkrete Distanz-/Reichweitenberechnung bei unterschiedlichen Regelwerken sowie MVP-Priorität.

### Technische Vorbereitung (Entwurf)

Ein konfigurierbares `SceneGrid`-Objekt könnte Felder für `kind` (`none`, `square`, `hex`), `cellSize`, `origin`, `scale`, `unit`, `visible` und `snap` besitzen. Dies ist nur ein konzeptionelles Beispiel, noch keine endgültige API. Positionsspeicherung und Darstellung müssen entkoppelt bleiben.

## 02.5 – Sichtbereiche und Nebel des Krieges (11.10.2026)

**Beschlossen: Variante C – manueller und dynamischer Sichtmodus, je Szene einstellbar.**

- **Manueller Modus:** Der Spielleiter kann Kartenbereiche gezielt aufdecken und wieder verdecken, z. B. durch Malen/Markieren von Sichtflächen.
- **Dynamischer Modus:** Der sichtbare Bereich ergibt sich aus Figurenposition, konfigurierbarer Sichtweite sowie später Wänden, Türen, Hindernissen, Licht und besonderen Sichtfähigkeiten.
- **Spielleiter-Eingriff:** Auch bei dynamischer Sicht kann der Spielleiter Bereiche manuell aufdecken oder verbergen, ohne den Modus wechseln zu müssen.
- **Rechte und Geheimnisse:** Verborgene Tokens, Gegner, Fallen, Notizen und nicht freigegebene Kartenelemente dürfen nicht lediglich visuell mit Nebel überdeckt werden. Der Server muss den für jeden Empfänger erlaubten Zustand berechnen und nur berechtigte Informationen an dessen Browser übertragen.
- **Persistenz:** Einstellungen, manuelle Aufdeckungen und notwendige Sichtzustände bleiben bei Reconnect und Serverneustart erhalten.
- **Szenentypen:** Fog/Sichtberechnung ist optional; Storyansichten oder freie Spieltische müssen es nicht verwenden.

**Noch offen:** Ob Entdeckungen für alle Spieler geteilt oder individuell gespeichert werden, wie Licht- und Wandberechnung im Detail funktioniert, wie Spielleiter-Übersteuerungen priorisiert werden, ob Sichtverläufe gespeichert werden und welche Teile zur ersten Version gehören.

## 02.6 – Bereits erkundete Bereiche (11.10.2026)

**Beschlossen: Variante C – pro Szene konfigurierbar.**

Der Spielleiter wählt, wie sich Kartenbereiche nach dem Verlassen der aktuellen Sicht verhalten:
- **Vollständig verdecken:** Bereits besuchte Bereiche verschwinden wieder vollständig im Nebel.
- **Erkundungserinnerung:** Bereits erkundete Bereiche bleiben als abgedunkelte, bekannte Kartenfläche sichtbar.
- **Manuelle Übersteuerung:** Der Spielleiter kann jederzeit wieder Bereiche aufdecken oder verdecken.

**Aktuelle Sicht ist nicht dasselbe wie Erinnerung.** Gegner, bewegliche Figuren, Fallen und neue Veränderungen in einem aktuell nicht sichtbaren Bereich werden durch eine gespeicherte Kartenerinnerung nicht automatisch sichtbar. Vertrauliche Objektdaten bleiben serverseitig geschützt.

**Technischer Entwurf:** Aktuell sichtbare Flächen, erkundete Flächen und manuelle Spielleiter-Übersteuerungen getrennt verwalten. Die Szeneneinstellung sowie notwendige Zustände müssen bei Reconnect und Neustart erhalten bleiben.

**Noch offen:** Gemeinsame oder individuelle Entdeckungshistorie, Erinnerung an ehemals sichtbare statische Objekte, Vorrang manueller Änderungen und Verhalten beim Wechsel des Erinnerungsmodus.

## 02.7 – Gemeinsame oder individuelle Sicht (11.10.2026)

**Beschlossen: Variante C – pro Szene wählbar.**

- **Gemeinsame Gruppensicht:** Die für die Gruppe freigegebenen aktuell sichtbaren Bereiche und die Erkundungserinnerung werden gemeinsam verwaltet. Entdeckt ein Mitglied einen neuen Raum, wird dieser gemäß den Szeneneinstellungen auch für die anderen Gruppenmitglieder freigegeben.
- **Individuelle Sicht:** Jeder Spieler sieht die Bereiche, die seiner eigenen Sicht und seinen Freigaben entsprechen, und besitzt eine eigene Entdeckungshistorie. Das unterstützt getrennte Gruppen oder geheime Erkundungen.
- **Spielleiter-Übersteuerung:** Der Spielleiter kann in beiden Modi einzelne Bereiche gezielt zeigen oder verbergen. Nicht für den jeweiligen Empfänger freigegebene NPCs, Fallen, Geheimräume und andere sensitive Objektdaten bleiben serverseitig verborgen.
- **Zusammenhang mit 02.6:** Gemeinsame/individuelle Sicht ist **unabhängig** davon, ob erkundete Flächen wieder komplett verschwinden oder als abgedunkelte Erinnerung bleiben.
- **Persistenz:** Szenenmodus, erkundete Sichtflächen und notwendige Freigaben bleiben bei Reconnect und Serverneustart erhalten.

**Technische Planung:** Szenenweites Sichtprofil plus gegebenenfalls getrennte Spieler-Sichtzustände, die serverseitig in eine erlaubte Gruppensicht bzw. individuelle Sicht umgerechnet werden. Der Browser bekommt nur berechtigte Daten. Die genaue Frage, ob einzelne Figuren eines Spielers ihre Sicht kombinieren, bleibt für die spätere Detailplanung offen.

**Weitere offene Punkte:** Umgang mit getrennten Gruppen und einem späteren Zusammenführen ihrer Entdeckungen, manuelle Freigaben nur an ausgewählte Spieler, mehrere Charaktere pro Spieler und Wechsel des Modus innerhalb einer laufenden Szene.

## 02.8 – Licht und Dunkelheit (11.10.2026)

**Beschlossen: Variante C – pro Szene einfache oder dynamische Beleuchtung.**

- **Einfach:** Licht wird optisch dargestellt; Sicht steuert der Spielleiter über die bereits beschlossenen Nebel- und Sichtoptionen.
- **Dynamisch:** Umgebungshelligkeit, Dunkelheit und Lichtquellen beeinflussen die Szene und können mit der dynamischen Sichtberechnung interagieren.
- **Feste Lichtquellen:** Fackeln, Straßenlampen, Lagerfeuer oder Raumbeleuchtung.
- **Bewegliche Lichtquellen:** Taschenlampen, Laternen oder Scheinwerfer, die einer Figur, einem Gegenstand oder einem Fahrzeug folgen.
- **Pro Lichtquelle einstellbar:** Farbe, Reichweite, Intensität, Richtung/Lichtkegel und Ein-/Ausschaltzustand. Berechtigte Spieleraktionen und Story-Ereignisse dürfen Lichtquellen schalten; der Spielleiter kann eingreifen.
- **Persistenz:** Einstellungen und aktive Lichtzustände bleiben nach Neustart oder Neuverbindung erhalten.

**Technischer Planungsgrundsatz:** Lichtdarstellung, Sicht- und Schattengeometrie, Fog-of-War-Masken und serverseitiger Geheimnisschutz sind getrennte Komponenten. Lichtquellen sollen als wiederverwendbare Komponenten für Szenenobjekte, Charaktere und Fahrzeuge funktionieren.

**Offen:** Schattenqualität und Performance, Akku/Brennstoff, zeitliche und rundenbasierte Lichtdauer, Nachtsicht/Spezialsicht, genaue Wechselwirkung mit Hindernissen und Entwicklungsreihenfolge.

## Nächste Entscheidung 02.9 – Wände, Türen und Fenster

- **A:** Nur dekorative Darstellung; Sicht- und Bewegungsgrenzen verwaltet der Spielleiter manuell.
- **B:** Standardautomatik: Wände blockieren Sicht/Licht/Bewegung, Türen ändern diese Regeln beim Öffnen, Fenster erlauben Sicht, aber keine Bewegung.
- **C:** Pro Objekt frei konfigurierbar: Sicht, Licht und Bewegung getrennt blockierbar; Türen/Fenster und besondere Barrieren können eigene Regeln und Zustandswechsel haben.

Weitere Kartenthemen danach: mehrere Karten in einer Szene, Freigaben, interaktive Objekte und Importformate.
