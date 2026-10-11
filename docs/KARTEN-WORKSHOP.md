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
| 02.6 | Verhalten bereits erkundeter Bereiche | Als Nächstes |

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

### Nächste Entscheidung 02.6 – Bereits erkundete Bereiche

- **A:** Sobald ein Bereich außerhalb der aktuellen Sicht liegt, wird er wieder vollständig schwarz/versteckt.
- **B:** Einmal erkundete Bereiche bleiben auf der Karte sichtbar, aber abgedunkelt; aktuelle Gegner und Veränderungen außerhalb der Sicht werden nicht automatisch angezeigt.
- **C:** **Pro Szene konfigurierbar:** volle Verdeckung oder Erkundungserinnerung, gegebenenfalls durch den Spielleiter überschreibbar.

Nach 02.6 folgen weitere Sichtdetails, mehrere Karten auf einer Szene, Szenenfreigaben, interaktive Objekte und Importformate. Die konkrete Entwicklungsreihenfolge wird erst nach Abschluss des gesamten Feature-Workshops festgelegt.
