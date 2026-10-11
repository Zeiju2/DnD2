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
| 02.11 | Private Szenenvorbereitung, gezielte Freigabe und Entdeckung von Stockwerken über sichtbare Zugänge | Beschlossen: C |
| 02.12 | Erweiterbarer Bild- und VTT-Import mit Vorschau und auswählbarer Metadatenübernahme | Beschlossen: C |
| 02.13 | Interaktive Kartenobjekte und Auslöser | Als Nächstes |

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

## 02.11 – Szenen vorbereiten und flexibel freigeben (11.10.2026)

**Beschlossen: Variante C – flexible Freigabe von Szenen und Inhalten.**

- **Privater Entwurf:** Spielleiter können Szenen, Stockwerke und Objekte vorbereiten, ohne dass Spieler diese schon sehen oder ihre Existenz erfahren.
- **Spielervorschau:** Spielleiter können prüfen, wie die Szene für einen bestimmten Spieler oder eine Gruppe mit ihren tatsächlichen Rechten aussieht.
- **Gezielte Freigabe:** Szenen werden wahlweise allen, ausgewählten Gruppen oder einzelnen Spielern zugänglich. Auch nachträglich können neue Stockwerke und Inhalte gezielt veröffentlicht oder weiter verborgen bleiben.
- **Freigaberegel für Stockwerke – zusätzlich ausdrücklich gewünscht:** Pro Stockwerk ist einstellbar, dass seine **Existenz und Auswahlmöglichkeit für Spieler erst sichtbar wird, sobald sie einen zugeordneten Zugang tatsächlich sehen** (beispielsweise Treppe, Leiter, Aufzug, Luke, Tür, Portal oder Fahrzeugzugang). Die Freigabe wird durch das Entdecken des Zugangspunkts ausgelöst, **nicht erst beim Betreten**. Spielleiter dürfen Stockwerke außerdem gezielt sofort freigeben.
- **Entdecken ist nicht Betreten und nicht vollständiges Aufdecken:** Die Entdeckung eines Zugangs kann eine Etage im Etagenwähler bekannt machen, gibt aber **nicht automatisch alle Räume, Gegner, Fallen oder Kartendetails dieser Etage preis**. Sicht/Fog, Zugangsregeln, Schlösser und tatsächlicher Stockwerkswechsel gelten unabhängig voneinander.
- **Gruppensicht vs. individuelle Sicht (02.7):** Im gemeinsamen Sichtmodus kann die Entdeckung für die Gruppe gelten; im individuellen Modus nur für berechtigte Entdecker. Die Feinheiten bei Gruppenwechsel und mehreren verbundenen Zugängen bleiben offen.
- **Geheime Zugänge:** Ein verborgener Treppenaufgang löst keine Enthüllung aus, bevor der Zugang selbst nach den geltenden Sicht-/Entdeckungsregeln sichtbar bzw. entdeckt wurde.
- **Serverseitiger Schutz und Persistenz:** Zugangsbeobachtung, Entdeckungsfreigabe, Veröffentlichungsstatus und Empfängerrechte werden serverseitig geprüft, gespeichert und an berechtigte Clients synchronisiert. Eine bloße UI-Ausblendung reicht nicht aus.

**Technische Planungsfolgen:** Die Konzepte **Szenenentwurf**, **Freigabe für Spieler/Gruppe**, **Stockwerk entdeckt**, **Zugangspunkt erkannt**, **aktuelle Sicht**, **Stockwerk begehbar** und **Inhalt per Fog sichtbar** müssen getrennt modelliert werden. Zugangspunkte können eine Liste verknüpfter Stockwerke freischalten. Noch offen: Priorität mehrerer Zugänge, erneutes Verbergen bereits bekannter Stockwerke, Etagenwechsel und Szenenfreigabe während paralleler Spielgruppen.

## 02.12 – Erweiterbares Kartenimport-System (11.10.2026)

**Beschlossen: Variante C – Bilder und unterstützte VTT-Daten importieren, mit Vorschau und frei wählbarer Datenübernahme.**

- **Bildimport:** Kartenbilder wie PNG, JPG und WebP sollen sich als bearbeitbare Szenenhintergründe importieren lassen.
- **VTT-Import:** Ein erweiterbares Importsystem für geeignete Austauschformate, z. B. DD2VTT/UVTT, ist vorzusehen. Welche konkreten Varianten vollständig unterstützt werden, muss anhand ihrer Spezifikationen und Testdateien geprüft werden; nicht jede Datei enthält alle nachfolgend genannten Daten.
- **Importvorschau:** Vor der Übernahme sieht der Spielleiter, welche Inhalte und Metadaten erkannt wurden, und kann sie gezielt auswählen: Kartenbild, Raster/Maßstab, Wände/Sichtlinien, Lichtquellen, Türen und weitere unterstützte Objekte, soweit in der Quelle vorhanden.
- **Zuordnung:** Importierte Wände, Lichtquellen oder Türen sollen nach Möglichkeit in die bereits geplanten generischen Szenenobjekte umgewandelt werden. Nicht unterstützte Eigenschaften werden kenntlich gemacht; der Spielleiter kann sie anschließend manuell ergänzen.
- **Erweiterbarkeit:** Spätere Importadapter für weitere Kartenwerkzeuge/Dateiformate können ergänzt werden, ohne den Szeneneditor neu entwerfen zu müssen.
- **Sicherheit:** Dateien validieren, Größe/Typ begrenzen, keine unkontrollierten Makros/Skripte aus importierten Daten ausführen. Interaktive Objekte und Geheimnisse erst nach Spielleiterprüfung/Freigabe an berechtigte Spieler übertragen.
- **Erhalt des Originals:** Quelldatei/Bild nicht destruktiv verändern; eingefügte Karten und übernommene Objekte bleiben im AdventureShift-Editor separat editierbar.

**Noch offen:** Exakte Liste unterstützter Dateiformate und Versionsvarianten, Umgang mit mehrstöckigen Dateien, Export zurück in Fremdformate, fehlende oder abweichende Einheiten, Vorschau- und Fehlerbehandlung sowie konkrete Implementierungsreihenfolge.

## Nächste Entscheidung 02.13 – Interaktive Kartenobjekte

- **A – Spielleiteraktionen:** Objekte sind dekorativ; nur der Spielleiter führt spielrelevante Ereignisse manuell aus.
- **B – Vorgegebene Interaktionen:** Spieler können passende Objekte anklicken und festgelegte Standardaktionen auslösen, etwa eine Tür öffnen, Truhe durchsuchen oder einen Schalter betätigen.
- **C – Pro Objekt frei konfigurierbar:** Spielleiter können Berechtigungen, Aktionen und Ereignisauslöser für Kartenobjekte kombinieren, z. B. Schalter öffnen Türen, Teleportfelder versetzen Figuren, Terminals starten Alarme oder Schatztruhen geben Beute frei. Sichere vordefinierte Aktionen statt frei ausführbarer Skripte.

Danach planen wir weitere Szenenobjekt-, Export- und Assetdetails.
