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
| 02.9 | Wände, Türen, Fenster: Sicht, Licht und Bewegung pro Objekt getrennt blockierbar | Beschlossen: C |
| 02.10 | Mehrere Kartenbilder frei angeordnet, überlagert und als Stockwerke/Ebenen | Beschlossen: C |
| 02.11 | Szenen für Spieler vorbereiten, verbergen und freigeben | Als Nächstes |

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

## 02.9 – Wände, Türen und Fenster (11.10.2026)

**Beschlossen: Variante C – pro Hindernis frei konfigurierbar.**

- **Unabhängige Eigenschaften:** Wände, Türen, Fenster, Glasflächen, Kraftfelder und andere Hindernisse können getrennt **Sicht**, **Licht** und **Bewegung** blockieren oder passieren lassen.
- **Beispiele:** Eine Steinwand blockiert alle drei; Glas lässt Licht und Sicht durch, blockiert jedoch Bewegung; eine magische Barriere kann nur Bewegung verhindern.
- **Interaktive Zustände:** Türen, Fenster und Barrieren besitzen optional Zustände wie geöffnet, geschlossen, verriegelt, zerstört oder deaktiviert. Zustandsänderungen können ihre Blockade- und Sichtregeln verändern.
- **Verbindung zum universellen Schloss-/Fallensystem (01.10–01.16):** Eine Tür kann Schlüssel, Keycards, Codes, Fehlversuchsgrenzen und Folgen besitzen. Eine Verriegelung ist nicht gleichbedeutend mit einer Licht- oder Sichtbarriere.
- **Verborgene Objekte:** Geheime Türen, unsichtbare Barrieren und versteckte Fallen dürfen vor Entdeckung oder SL-Freigabe nicht als Geheimnis im Spielerclient sichtbar werden. Berechtigte Spiellogik bleibt serverseitig.
- **Persistenz und Mehrspieler:** Zustandswechsel werden synchronisiert und nach Reconnect/Neustart wiederhergestellt. Sicht-/Lichtberechnung und gegebenenfalls Bewegungskollision verwenden den aktuellen Zustand.

**Technische Vorbereitung:** Wiederverwendbare Hindernis-/Durchlasskomponente an Szenenobjekten mit Sicht-, Licht- und Bewegungseigenschaften; keine hardcodierten Regeln je Objektgrafik. Der Zeichen-/Tile-Editor muss logische Hindernisse von bloß dekorativ gemalten Linien unterscheiden.

**Noch offen:** Ausmaß der Kollision (Token-Größen, Fahrzeuge, fliegende Figuren), besondere Einweg-/Spezialbarrieren, genaue Sichtlinienberechnung und welche Zustandsübergänge animiert werden.

## 02.10 – Mehrere Karten und Stockwerke in einer Szene (11.10.2026)

**Beschlossen: Variante C – frei kombinierbare Karten und Stockwerke.**

- **Mehrere Kartenbilder:** Ein Spielleiter kann mehrere Karten innerhalb derselben Szene platzieren: nebeneinander, überlappend oder auf unterschiedlichen Karten-/Bild-Ebenen.
- **Anordnung:** Jedes eingefügte Kartenbild kann unabhängig **verschoben, gedreht und skaliert** werden; individuelle Ausrichtung auf einen gemeinsamen Szenenmaßstab ist vorzusehen.
- **Stockwerke/Etagen:** Szenen dürfen mehrere getrennte Stockwerke wie Keller, Erdgeschoss und Obergeschoss besitzen, zwischen denen der Spielleiter ohne Szenenwechsel umschaltet.
- **Positionen und Objekte:** Tokens, Türen, Hindernisse, Lichtquellen, Fallen und andere Objekte werden der richtigen Kartenfläche bzw. Etage zugeordnet. Das Umschalten entfernt keine Spielobjekte.
- **Sicht und Geheimnisse:** Nebel des Krieges, Licht und berechtigte Sichtbereiche müssen auch in mehrstöckigen Szenen funktionieren. Ein verborgenes Stockwerk oder geheimer Kartenabschnitt darf nicht bloß optisch ausgeblendet sein; nicht berechtigte Clients bekommen keine vertraulichen Daten.
- **Spielzustand:** Etagenzuordnung, Transformationsdaten, Platzierungen und Sichtzustände werden persistent gespeichert und synchronisiert.

**Technischer Entwurf:** Eine Szene besitzt mehrere Kartenbild-Instanzen mit individuellen Transformationsdaten (Position/Rotation/Skalierung/Reihenfolge) sowie logische Ebenen und optionale Stockwerke. Eine **Render-Ebene** (z. B. Dekoration) ist nicht dasselbe wie ein **Stockwerk** (z. B. Obergeschoss); beides separat modellieren. Lokale Koordinaten je Kartenbild müssen auf den Szenenraum transformierbar sein.

**Noch offen:** Wie Figuren Treppen, Aufzüge, Portale und andere Stockwerksübergänge benutzen; ob verschiedene Spieler gleichzeitig unterschiedliche Etagen sehen; getrennte oder gemeinsame Fog-Masken je Stockwerk; Kollisionsberechnung über mehrere Etagen; Begrenzung von Bildgröße/Anzahl; Import mehrstöckiger Dateien.

## Nächste Entscheidung 02.11 – Szenen vorbereiten und freigeben

- **A – Alles sofort sichtbar:** Änderungen und neue Szenen werden direkt an alle Spieler übertragen.
- **B – Entwurf und Freigabe:** Spielleiter bereiten Szenen privat vor und geben eine Szene später für alle gleichzeitig frei.
- **C – Flexible Freigabe pro Szene:** Private Vorbereitung mit Spielleiter-Vorschau, Freigabe für alle oder ausgewählte Spieler/Gruppen; spätere Änderungen und Freigaben sind gezielt steuerbar.

Danach planen wir Kartenimporte, Szenenobjekte und weitere Details.
