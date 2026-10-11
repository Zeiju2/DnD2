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
| 02.13 | Zentrales Aktion-Reaktion-System für interaktive Objekte, ohne Programmierkenntnisse | Beschlossen: C |
| 02.14 | Einfacher Regelassistent und visueller Ablaufeditor für dasselbe Regelmodell | Beschlossen: C |
| 02.15 | Frei kombinierbare Auslöser einschließlich Echtzeit und Spielrunden | Beschlossen: C |
| 02.16 | Zeit-/Rundenauslöser pro Regel einmalig oder wiederkehrend, mit steuerbarem Start/Pause/Reset/Abbruch | Beschlossen: C |
| 02.17 | UND/ODER/NICHT-Bedingungsgruppen und Node-System mit Objekt-Ein-/Ausgängen | Beschlossen: C |
| 02.18 | Kampagnenweite Node-Verbindungen über Szenen und Stockwerke hinweg | Beschlossen: C |
| 02.19 | Ausführung in inaktiven Szenen pro Regel: sofort, vormerken oder nur wenn aktiv | Beschlossen: C |
| 02.20 | Typisierte Node-Ports mit farblich codierten Leitungen, Signal-Iststand und expliziten Inverter-Nodes | Beschlossen: C |
| 02.21 | Ereignisimpulse, anliegende Werte und Spieler-Halteschalter | Beschlossen: C |
| 02.22 | Türreaktion bei Signalverlust konfigurierbar; Schalter oder gehaltenen Taster wählen | Beschlossen: C |
| 02.23 | Tür/Barriere reagiert pro Objekt auf Figuren im Durchgang: warten, öffnen oder Schließen erzwingen | Beschlossen: C |
| 02.24 | Folgen gefährlicher Türen und Barrieren: globale Kampagnenstandards mit Objektausnahmen | Beschlossen: C |
| 02.25 | Änderung globaler Kampagnenregeln: Vorschau, Auswahl Altbestand/Neuanlagen, Ausnahmen schützen | Beschlossen: C |
| 02.26 | Frei benannte Node-Arbeitsbereiche, Gruppen, Untergraphen und kampagnenweite Querverbindungen | Beschlossen: C |
| 02.27 | Wiederverwendbare parametrisierbare Node-Bausteine und drei unabhängige Ansichten | Beschlossen: C, ergänzt |
| 02.28 | Automatische Layouts mit manueller Neuanordnung und Positionen-Fixierung | Beschlossen: C |
| 02.29 | Szenenübergreifende Leitungen: direkt oder über beschriftete Rahmen-Übergangspunkte | Beschlossen: C |
| 02.30 | Frei festlegbare primäre Anzeige-Szene oder „Kampagnenweit“ mit Referenzen in anderen Szenen | Beschlossen: C |
| 02.31 | Vollständige Node-Diagnose mit Live-Iststand, Ereignisverlauf, Schrittfolge und Breakpoints | Beschlossen: C |
| 02.32 | Gespeicherte Testszenarien mit Ausgangszustand, Eingaben, Echtzeit/Runden und Soll-Ist-Vergleich | Beschlossen: C |
| 02.33 | Testläufe pro Schaltung manuell, nach Änderungen oder vor Aktivierung festlegen | Beschlossen: C |
| 02.34 | Test-Freigaberegel je Kampagne und Schaltung: Warnung, Sperre und protokollierte Übersteuerung | Beschlossen: C |
| 02.35 | Konfigurierbare Konfliktregeln für gleichzeitige Node-Aktionen, Kampagnenstandard und Objektausnahmen | Beschlossen: C |
| 02.36 | Mehrfach-Halter je Taster wählbar, mit globalem Kampagnenstandard und Objektausnahmen | Beschlossen: C + globaler Standard |
| 02.37 | Verbindungsabbruch beim Halten: globale Sofortfreigabe oder begrenzte Nachfrist, Ausnahmen je Taster | Beschlossen: C |
| 02.38 | Bewegung, Aktionen, Reichweite und Figurenzustand beim Halten: Kampagnenstandard mit Ausnahmen | Beschlossen: C |
| 02.39 | Interaktionsreichweite global mit Ausnahmen; Präsenz- und Bewegungsmelder als Node-Objekte | Beschlossen: C + Sensoren |
| 02.40 | Sensorfilter je Sensortyp frei konfigurierbar, globale Standards und Objektausnahmen | Beschlossen: C |
| 02.41 | Frei gestaltbare Sensorzonen und deren globale Sichtbarkeit mit Objektausnahmen | Beschlossen: C + Sichtbarkeit |
| 02.42 | Hindernis-/Sichtlinienverhalten je Sensortyp: Kampagnenstandards und Sensor-Ausnahmen | Beschlossen: C |
| 02.43 | Licht und Dunkelheit sensortypabhängig, Kampagnenstandards mit Ausnahmen je Sensor | Beschlossen: C |
| 02.44 | Sensortypabhängige Verzögerung, Nachlauf, Wiederholungsimpulse und quittierbare Alarme | Beschlossen: C |
| 02.45 | Berechtigte Sensoralarm-Quittierung per SL, Bedienobjekt oder Node: global und je Sensor | Beschlossen: C |
| 02.46 | Quittieren und Zurücksetzen bei weiterhin bestehender Gefahr | Als Nächstes |

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

## 02.13 – Interaktive Objekte und Aktion-Reaktion-System (11.10.2026)

**Beschlossen: Variante C – frei konfigurierbare Interaktionen und ein zentrales, übersichtliches Aktion-Reaktion-System.** Der Spielleiter soll ohne Programmierkenntnisse selbst bestimmen können, was ein Ereignis auslöst, welche Bedingungen dafür gelten und welche Reaktionen eintreten.

### Grundmodell: WENN – FALLS – DANN

1. **Auslöser (WENN):** Ein Spieler klickt oder benutzt ein Objekt, betritt einen Bereich, gibt einen Code ein, bewegt eine Figur, ein Zustand verändert sich oder ein Zeit-/Rundenereignis tritt ein. Die konkrete vollständige Auslöserliste wird später beschlossen.
2. **Bedingungen (FALLS):** Beispielsweise passende Berechtigung, Schlüssel/Keycard im Inventar, richtiger Code, aktivierter Schalter, bestimmter Objektzustand oder erfüllte Questbedingung. Bedingungen sollen sich bei Bedarf mit UND/ODER verknüpfen lassen.
3. **Reaktionen (DANN):** Beispielsweise Tür öffnen/verschließen, Licht schalten, Alarm auslösen, Falle aktivieren, Figur teleportieren, neue Etage nach 02.11 bekannt machen, Gegenstände freigeben, NPC erscheinen lassen, Mitteilung anzeigen oder ein anderes Ereignis auslösen. Mehrere Folgen und geordnete Abläufe sollen möglich sein.

**Beispiel:** Spieler betätigt Schalter -> System prüft Schlüsselkarte und Berechtigung -> Geheimtür öffnet sich, Alarm geht aus und Raumbeleuchtung wird eingeschaltet. Das System muss auch einfache Ein-Schritt-Regeln ohne unnötige Konfiguration ermöglichen.

### Verbindliche Bedienanforderungen

- **Eine wiederverwendbare Oberfläche für alle Objektarten:** Türen, Schalter, Truhen, Terminals, Fahrzeuge, Fallen, Figuren, Gegenstände, Szenen- und Story-Ereignisse. Keine getrennte Programmlogik oder eigene komplizierte Bedienung je Objekttyp.
- **Ohne Programmierung:** Auslöser, Bedingungen und Reaktionen aus verständlich benannten Auswahlmöglichkeiten zusammenstellen; keine Pflicht, Code, Skripte oder Konfigurationsdateien zu schreiben.
- **Übersichtlich:** Kurze menschenlesbare Regelzusammenfassung (z. B. „Wenn Schalter A betätigt wird und Karte B vorhanden ist, öffne Tür C“), klare Unterscheidung von Auslöser/Bedingung/Reaktion, leicht auffindbare Verknüpfungen und sinnvolle Vorlagen.
- **Einfacher Einstieg und komplexe Möglichkeiten:** Eine einzelne Wenn-Dann-Regel soll schnell angelegt werden können. Fortgeschrittene Regeln können mehrere Bedingungen, mehrere Aktionen, Verzweigungen, Reihenfolgen und ggf. Verzögerungen/Timer verwenden. Deren genaue Grenzen, UI und Semantik werden separat festgelegt.
- **Testen und Fehlersuche:** Regel vor der Spielrunde prüfen können; erkennbar machen, welches Zielobjekt fehlt, welche Bedingung nicht erfüllt ist oder warum ein Ereignis nicht ausgelöst hat. Spielleiterseitiges Ereignis-/Ausführungsprotokoll ohne Preisgabe von Geheimnissen an Spieler.
- **Vorlagen:** Beispielsweise „Schalter öffnet Tür“, „Bodenplatte löst Falle aus“, „Code startet Alarm“, „Portal wechselt Stockwerk“, „Lampe schalten“; Vorlagen müssen anpassbar sein.

### Technische und Sicherheitsanforderungen

- **Gemeinsamer serverautoritärer Ereignis-/Regelkern** mit typisierten Auslösern, Bedingungen und erlaubten Aktionen sowie überprüften Zielobjekt-Referenzen; regelwerks- und genreunabhängig.
- **Sicherheit:** Berechtigungen und Geheimdaten konsequent serverseitig prüfen. Nur erlaubte Reaktionen; keine beliebigen, ungeprüften Benutzerskripte.
- **Konsistenz:** Objektzustände und Inventaränderungen transaktional, konkurrierende Aktionen kontrolliert und Folgewirkungen idempotent, damit etwa Fallen nicht durch Doppelanfragen zweimal explodieren.
- **Vermeidung von Endlosschleifen:** Ein Regelereignis, das weitere Ereignisse auslöst, muss mit Ausführungsgrenzen/Zyklenschutz verarbeitet werden.
- **Persistenz/Mehrspieler:** Regeln, aktivierte/deaktivierte Zustände und notwendige Timer nach Reconnect und Serverneustart erhalten; nur berechtigte Spieler über Folgen informieren.
- **Offen:** Exakte Auslöser-/Aktionsbibliothek, Regeln für mehrstufige Abfolgen und Verzögerungen, Ereignis-Reihenfolge, Versions-/Undo-Verhalten, maximaler Umfang und Einführungsphase.

## 02.14 – Bedienung des Aktion-Reaktion-Editors (11.10.2026)

**Beschlossen: Variante C – einfacher Regelassistent UND visueller Ablaufeditor für dasselbe Regelmodell.**

- **Einfacher Regelassistent:** Schrittweise, verständlich beschriftete Auswahl von **WENN (Auslöser)**, **FALLS (Bedingungen)** und **DANN (Reaktionen)**. Gut für schnelle und überschaubare Regeln, ohne grafische Knoten verknüpfen zu müssen.
- **Visueller Ablaufeditor:** Blöcke/Knoten mit Verbindungen für komplexe Ereignisketten, mehrere Aktionen, Verzweigungen, Reihenfolge und optional später Zeitbedingungen.
- **Eine gemeinsame Regeldefinition:** Wechsel zwischen beiden Ansichten ohne doppelte oder abweichende Regeln und ohne Informationsverlust; Speichern aus einer Ansicht aktualisiert die andere.
- **Komplexität sicher behandeln:** Wenn eine Regel Knoten oder Verknüpfungen enthält, die der einfache Assistent nicht vollständig bearbeiten kann, wird sie dort als verständliche, gegebenenfalls nur teilweise bearbeitbare Zusammenfassung angezeigt. Beim Zurückwechseln dürfen weder Verzweigungen noch Parameter stillschweigend gelöscht oder verändert werden. Erweiterte Funktionen bleiben im visuellen Modus bearbeitbar.
- **Nutzerführung:** Durchsuchbare Objekt- und Ereignisauswahl, einsteigerfreundliche Vorlagen, klare Beschriftungen und Verknüpfungsvorschau, menschenlesbare Zusammenfassung der Regel.
- **Test und Fehlersuche:** In beiden Ansichten Möglichkeit zur Prüfung/Simulation vor der Freigabe, Anzeige erkannter Fehler oder fehlender Referenzen und ein verständliches, nur für berechtigte Spielleiter sichtbares Ausführungsprotokoll.
- **Sicherheit:** Beide Oberflächen verwenden dieselbe validierte, serverseitig ausgeführte und berechtigungsgeschützte Ereignisdefinition; keine frei ausführbaren Nutzerskripte.

**Technische Planung:** Die Regelstruktur muss unabhängig von einer konkreten Oberfläche gespeichert werden. Der Assistent und die grafische Ansicht sind zwei Bearbeitungsoberflächen für dasselbe Modell. Regeländerungen werden geprüft, Versionierung/Undo und Testmodus sind vorzusehen; genaue UI-Details, Vorlagen, Simulationsumfang und Kopier-/Vorlagenfunktionen bleiben offen.

## 02.15 – Umfangreiches Auslösersystem mit Echtzeit und Spielrunden (11.10.2026)

**Beschlossen: Variante C – ereignisübergreifend konfigurierbare Auslöser, ausdrücklich in beiden Zeitmodellen.**

### Geplante Auslöserkategorien

- **Direkte Aktionen:** Anklicken, Benutzen, Öffnen/Schließen, Schalter betätigen, Terminal bedienen, manuelle Spielleiteraktion.
- **Bewegung und Umgebung:** Bereich betreten oder verlassen, sich einem Objekt nähern, Figur oder Fahrzeug bewegen; weitere Distanz- und Kollisionsregeln später.
- **Zustandsänderungen:** Türzustand, Schalter, Lichtquelle, Schloss/Falle, NPC-/Fahrzeugstatus, Regeln aus anderen Objekten.
- **Gegenstände und Inventar:** Aufheben, Ablegen, Ausrüsten, Verwenden, Verbrauch einer Ladung, Schlüssel/Keycard einsetzen.
- **Codes und Sicherheit:** Richtige oder falsche Codeeingabe, bestimmter Fehlversuchsschwellenwert, Entriegelung, Falle ausgelöst; bestehendes Zugangssystem aus 01.10–01.16 wiederverwenden.
- **Story und Spielverlauf:** Questfortschritt, individuelle Story-Flags, Spielleiterereignis und Regelereignisse; konkretes Datenmodell später.
- **Echtzeit-Auslöser:** **Sekunden, Minuten oder Stunden** nach einem definierten Startpunkt oder Ereignis (z. B. drei Echtzeitsekunden nach Betreten einer Bodenplatte).
- **Rundenbasierte Auslöser:** **Nach einer festgelegten Anzahl Spielrunden** oder bei einem definierten Rundenereignis, sofern die Kampagne einen Rundenmodus verwendet (z. B. Alarm nach zwei abgeschlossenen Runden).

### Zwingende Trennung beider Zeitarten

- **Echtzeit** und **Spielrunden** sind eigenständige, pro Auslöser wählbare Zeitgrundlagen, ohne automatische Umrechnung. Ein Ablauf von zwei Runden ist nicht gleich einer festen Zahl Sekunden.
- **Ohne aktives Rundensystem** dürfen rundenbasierte Regeln nicht irrtümlich durch verstrichene Echtzeit auslösen.
- **02.16 beschlossen:** Einmalige oder wiederkehrende Timer und deren Starten, Pausieren, Fortsetzen, Zurücksetzen und Abbrechen sind pro Regel konfigurierbar. **Weiterhin offen:** Exakte Semantik bei pausierter Kampagne, ausgeschaltetem Server, Offline-Spielern und gleichzeitigen Ereignissen.
- Bereits definierte Echtzeit- und Rundenwirkungen auf Gegenstände, Schlösser und Fallen sollen dieselben grundlegenden Zeitkonzepte nutzen, aber je Objekt eigene Regeln behalten.

### Ausführung und Bedienung

- Auslöser sind im **einfachen Regelassistenten** und im **visuellen Ablaufeditor** aus 02.14 auswählbar, mit klaren Bezeichnungen wie „Wenn Spieler Bereich betritt“, „Nach 30 Sekunden“ oder „Nach 3 Spielrunden“.
- Bedingungen (FALLS) und Reaktionen (DANN) werden getrennt von den Auslösern modelliert; mehrere Reaktionen und objektübergreifende Ketten bleiben möglich.
- Ereignisse, Timer und Rundenzähler werden serverautoritär und nach Berechtigung verarbeitet, bei Reconnect/Neustart persistent; doppelte Clientaktionen lösen keine doppelte Konsequenz aus.
- Ereignisketten erhalten Limits gegen unendliche Schleifen. Der Spielleiter kann geplante Auslöser vorab testen, ohne das echte Spiel zu verändern.

**Offen:** Konkrete Timersemantik bei pausierter Kampagne oder Serverausfall, Bedingungen/Operatoren, Reihenfolge bei gleichzeitigen Auslösern, Auslöser- und Reaktionsbibliothek im Detail und Implementierungsphase. **Einmalig/wiederkehrend und steuerbarer Timerzustand sind durch 02.16 entschieden.**

## 02.16 – Einmalige und wiederkehrende Zeit-/Rundenauslöser (11.10.2026)

**Beschlossen: Variante C – pro Regel frei konfigurierbar.**

- **Einmalig:** Ein Auslöser tritt nach einer eingestellten Dauer (z. B. 30 Echtzeitsekunden) oder einer definierten Zahl Spielrunden genau einmal ein.
- **Wiederkehrend:** Ein Auslöser kann nach einem bestimmten Echtzeit- oder Rundenintervall mehrfach eintreten (z. B. alle 20 Sekunden oder jede zweite Runde).
- **Steuerung durch Aktionen/Ereignisse:** Timer lassen sich je nach Regel **starten, pausieren, fortsetzen, zurücksetzen, neu starten oder abbrechen**, auch über andere Auslöser oder eine berechtigte Spielleiteraktion.
- **Zeitarten getrennt:** Ein Echtzeitintervall ist keine feste Zahl Spielrunden. Rundenbasierte Zeitabläufe benötigen einen aktiven Rundenzähler; das Aktion-Reaktion-System darf sie nicht von sich aus mit Sekunden simulieren.
- **Einheitliches No-Code-Design:** Der einfache Regelassistent und der visuelle Ablaufeditor aus 02.14 bieten dieselben Konfigurationsmöglichkeiten für Wiederholung, Intervall und zulässige Steueraktionen, soweit die Oberfläche diese Regeln darstellen kann.
- **Sicherheit und Konsistenz:** Persistente Timerzustände, Zuordnung zur Regel/Objektinstanz, autorisierte Änderungen und idempotente Ausführung; ein einzelner Tick darf bei doppelten Anfragen oder nach Reconnect nicht mehrfach als dieselbe Auslösung verarbeitet werden. Wiederkehrende Auslöser sind dennoch bewusst mehrere Ereignisse.
- **Beispiele:** Nach Betreten eines Bereichs nach 5 Sekunden einmal eine Tür schließen; alle 3 Spielrunden eine Warnleuchte einschalten, solange ein Alarm aktiv ist; Countdown durch einen Schalter anhalten oder zurücksetzen.

**Noch offen:** Ob Echtzeit beim Pausieren der Kampagne oder bei ausgeschaltetem Server weiterläuft, ob versäumte wiederkehrende Ereignisse nachgeholt oder übersprungen werden, maximale Wiederholungszahl, parallele Timer, Zeitanzeige für Spieler und genaues Verhalten beim Speichern/Laden. Keine stillschweigende Festlegung zu diesen Punkten.

## 02.17 – Bedingungsgruppen und objektgebundenes Node-System (11.10.2026)

**Beschlossen: Variante C – frei kombinierbare UND-/ODER-/NICHT-Bedingungen, einschließlich gruppierter und verschachtelter Bedingungen.** Dazu die ausdrückliche Anforderung: Ein späteres **visuelles Node-/Verbindungssystem** ist nicht nur eine optionale Darstellung, sondern ein grundlegender Baustein für das Aktion-Reaktion-Konzept.

### Objekte besitzen von Anfang an Ein- und Ausgänge

1. **Beim Platzieren wird jedes interaktive Objekt benannt**, z. B. eine Tür mit dem Namen „Nordtor“ in der Szene „Festung“, Stockwerk „Erdgeschoss“. Der Spielleiter soll den Namen später ändern können.
2. **Passende Anschlüsse (Ports) stehen ab Erstellung für jedes Objekt bereit:** Bereits beim Platzieren erhält jedes Szenenobjekt eine typabhängige Anschlussdefinition; eine Tür besitzt sinnvolle Tür-Ein-/Ausgänge, ein Schalter andere und ein Fahrzeug eigene. Auch zunächst dekorative Objekte bleiben als Node auffindbar und können einen kleinen Satz allgemeiner Steuerports besitzen oder später erweiterte Fähigkeiten erhalten. Die Ports sind Teil des Objekttyps und können mit geeigneten Erweiterungsmodulen später ergänzt werden.
3. **Objekt-Node über eine Such-/Ereignisauswahl einfügen:** Die Palette bietet verständliche Bezeichnungen nach dem Muster `Tür – [Szene] – [Stockwerk] – [Türname]` mit Such- und Filterfunktionen. Wird die Node im Ablaufeditor platziert, verweist sie auf **dasselbe bereits existierende Szenenobjekt**, nicht auf eine Kopie.
4. **Ein- und Ausgänge durch Verbindungen/Pfade koppeln:** Der Spielleiter zieht eine Verbindung von einem Ereignis-Ausgang zu einem passenden Aktions-Eingang; Bedingungen und Zwischenschritte können dazwischenliegen. So entstehen einfache oder komplexe Schaltungen ohne Programmierung.
5. **Regeln bleiben auch im einfachen Assistenten nutzbar (02.14):** Die Node-Ansicht ist die detaillierte grafische Darstellung derselben Regeldefinition. In der Assistentenansicht sollen einfache Verbindungen und komplexere Regeln als verständlicher Text erkennbar bleiben, ohne Graphen beim Umschalten zu verlieren.

### Beispiel einer Tür-Node

**Objektbezeichnung in der Auswahl:** `Tür – Festung – Erdgeschoss – Nordtor`

| Typ | Anschluss-Beispiele | Verhalten |
| --- | --- | --- |
| **Eingang (Aktion)** | `Entriegeln`, `Öffnen`, `Schließen`, `Verriegeln` | Ein verbundenes Ereignis fordert die jeweilige Zustandsänderung an; tatsächliche Zulässigkeit wird serverseitig geprüft |
| **Ausgang (Ereignis)** | `Bei Benutzung`, `Entriegelt`, `Geöffnet`, `Geschlossen`, `Verriegelt`, `Zugriff verweigert` | Sendet das Ereignis an verbundene Nodes, sobald das jeweilige Ereignis tatsächlich eintritt |
| **Bedingungswerte (optional)** | `Ist verriegelt?`, `Ist offen?` | Werte können als Bedingung gelesen werden, statt eine Aktion zu starten |

**Beispielverschaltung:** `Schalter – aktiviert` → `Bedingung: passende Keycard UND Alarm aus` → `Tür – Nordtor [Eingang: Entriegeln]` → `Tür – Nordtor [Ausgang: Entriegelt]` → `Tür – Nordtor [Eingang: Öffnen]`.

Die Tür-Eingänge dürfen nicht unkontrolliert bestehende Rechte/Schlösser umgehen. Gegebenenfalls muss die Automatik ausdrücklich berechtigt sein oder zuvor die vorgesehenen Voraussetzungen erfüllen. Ein fehlgeschlagener Aktionsversuch darf nicht fälschlich ein „Entriegelt“-Ereignis ausgeben.

### Wiederverwendbares Architekturprinzip

- **Objekttyp definiert Port-Vorlage:** z. B. `Door`, `Switch`, `Light`, `Vehicle`, `Trap`, `Container`, `Terminal`, `Timer`, `Character`; anwendbare Ein-/Ausgänge ergeben sich aus den Fähigkeiten des Objekts und sollen im Editor angezeigt werden.
- **Objektinstanz erhält stabile ID:** Referenzen in Verbindungen verwenden interne unveränderliche IDs, nicht den sichtbaren Türnamen. Umbenennen einer Szene/Tür/Etage aktualisiert nur die Anzeige, nicht bestehende Verbindungen.
- **Port- und Verbindungstypen:** Ereignis-Ausgänge und Aktions-Eingänge sowie Bedingungs-/Datenwerte dürfen nicht ohne Prüfung beliebig verbunden werden. Ungültige Verknüpfungen werden verständlich erklärt, nicht stillschweigend ausgeführt. Genaue Typspezifikation ist eine offene Detailfrage.
- **Lebenszyklus:** Objekt löschen, verschieben oder seine Fähigkeiten ändern muss in betroffenen Graphen sichtbar werden, z. B. als klar markierte fehlende Referenz; keine unbeabsichtigte Bindung an ein anderes Objekt mit gleichem Namen.
- **Serverautorität:** Alle Node-Aktionen prüfen Berechtigungen, gültige Zustände, Szene-/Spielerfreigaben und vorhandene Voraussetzungen. Ereignisse werden synchronisiert; Zyklen, doppelte Auslösung und unendliche Ketten sind abzufangen.
- **Genre-/Regelwerkneutralität:** Das System ist auch für Items, Fallen, NPCs, Fahrzeuge, Quests, Zeit- und Runden-Timer geeignet. Spezialisierte Module können neue Node-/Port-Vorlagen anbieten, ohne bestehende Regeln zu ändern.

**Mit 02.18 entschieden:** Node-Verbindungen können **kampagnenweit**, also auch über Szenen- und Stockwerksgrenzen hinweg, aufgebaut werden. **Weiterhin offen:** Umgang mit inaktiven Szenen (02.19), genaue Ereignis- und Datenports, Gruppierung von Bedingungen/Werten, Graph-Verwaltung, Debug-Ansicht, Vorlagen, Reihenfolge konkurrierender Ereignisse und Implementierungsphase.

## 02.18 – Kampagnenweite Node-Verbindungen (11.10.2026)

**Beschlossen: Variante C – Verbindungen dürfen jede passende Node innerhalb derselben Kampagne erreichen.** Das schließt andere Stockwerke und andere Szenen derselben Kampagne ausdrücklich ein.

- **Beispiel:** Ein Terminal im Raumschiff-Kontrollraum sendet das Ereignis `Code bestätigt` über einen Verbindungspfad an `Tür – Maschinenraum – Unterdeck – Schott A`, Eingang `Entriegeln`. Der erfolgreiche Statuswechsel kann weitere Nodes benachrichtigen.
- **Node-Auswahl:** Objekte anderer Szenen/Stockwerke erscheinen in der durchsuchbaren Palette mit ihrem vollständigen Namen und Ort. Die referenzierte Objekt-ID bleibt stabil, auch wenn Tür oder Szene umbenannt wird.
- **Kampagnengrenze:** Es werden **keine unkontrollierten Verbindungen in andere Kampagnen** zugelassen. Verbindungsziele und zulässige Aktionseingänge werden serverseitig auf identische Kampagne und passende Berechtigungen geprüft.
- **Unabhängig von geöffnetem Browser:** Für die Auswertung einer Verbindung darf nicht erforderlich sein, dass ein Spieler gerade die Zielszene in seinem Browser anzeigt. Wie schnell bzw. wann Änderungen an **inaktiven Szenen** stattfinden, entscheiden wir ausdrücklich in 02.19.
- **Geheimnisse und Freigaben:** Die Existenz anderer/geheimer Szenen, Stockwerke und Objekte darf durch eine Verbindung nicht an unberechtigte Spieler gelangen. Sichtbarkeit der Graphen und Spielleiter-Rechte getrennt von der Spieleransicht; Clients erhalten nur freigegebene Zustandsänderungen.
- **Verkettung und Zuverlässigkeit:** Weitergeleitete Ereignisse benötigen eindeutige Kennungen, Berechtigungs- und Zustandsprüfung sowie Begrenzungen gegen endlose Schleifen. Zielobjekte und Verbindungen müssen persistent bleiben; fehlende/gelöschte Ziele werden als Fehler angezeigt, nicht durch gleichnamige Objekte ersetzt.
- **Echtzeit und Spielrunden:** Beide Zeitmodelle aus 02.15/02.16 können auch kampagnenweite Verbindungen auslösen; der Zielort ändert die Zeitsemantik nicht automatisch.

**Technische Planung:** Objekt- und Node-IDs kampagnenweit referenzierbar; `campaign_id` für jede Referenz prüfen. Ereignisse über einen serverseitigen Ereignisrouter an Ziel-Objektinstanzen zustellen, ohne die grafische Zielszene laden zu müssen. Das tatsächliche Verhalten bei inaktiven Ziel-Szenen bleibt offen.

## 02.19 – Node-Ereignisse in inaktiven Szenen (11.10.2026)

**Beschlossen: Variante C – pro Regel frei konfigurierbarer Ausführungsmodus**, auch wenn die Zielszene gerade in keinem Spielerbrowser angezeigt wird.

- **Sofort ausführen:** Der Server wendet die Wirkung unmittelbar auf das Zielobjekt in der anderen Szene an. Beispiel: Ein Terminal entriegelt sofort die Maschinenraumtür; diese ist beim späteren Betreten bereits entriegelt.
- **Bis zur Szenenaktivierung vormerken:** Der Server speichert die ausstehende Aktion zuverlässig und führt sie beim Aktivieren der Zielszene aus. Beispiel: Eine Begrüßungssequenz oder ein vorbereiteter Alarm beginnt erst beim Betreten bzw. Aktivieren.
- **Nur bei aktiver Zielszene:** Die Aktion wird nur ausgeführt, wenn die Szene zum Auslösezeitpunkt aktiv ist; sonst **entfällt sie und wird nicht nachgeholt**. Beispiel: Ein kurzlebiger optischer Effekt soll in einer unbenutzten Szene nicht später abgespielt werden.

**Zentrale Anforderungen:**
- Der Spielleiter kann die Ausführungsart für jede Node-Regel wählen, sowohl im Regelassistenten als auch im visuellen Node-Editor. Die Einstellung gehört zur gespeicherten Regel, nicht zur Grafikverbindung allein.
- Eine vorgemerkte Aktion ist **nicht bereits erfolgreich ausgeführt**. Beim tatsächlichen Ausführungszeitpunkt müssen aktuelle Zielobjektzustände, Berechtigungen und Bedingungen erneut geprüft werden. Ungültige oder gelöschte Ziele dürfen nicht stillschweigend ersetzt werden.
- Vorgemerkte Einträge erhalten eindeutige IDs und nachvollziehbare Zustände (z. B. wartend, ausgeführt, übersprungen, fehlgeschlagen, abgebrochen). Ein und derselbe Eintrag darf nicht mehrfach ausgeführt werden; wiederkehrende Ereignisse aus 02.16 besitzen dagegen jeweils eigene Auslösungen.
- Wirkungen und Warteschlangen müssen Verbindungsabbrüche und Serverneustarts überstehen; nur berechtigte Spielleiter sehen die interne Warteliste und Fehlerursachen. Eine entfernte Szene wird durch Node-Verbindungen **nicht automatisch für Spieler freigegeben**.
- Echtzeit- und Rundenereignisse aus 02.15/02.16 bleiben zwei getrennte Zeitgrundlagen. Der Modus „bis Szenenaktivierung“ ersetzt nicht die explizit konfigurierte Timerlogik.

**Noch offen:** Was genau als „Szenenaktivierung“ gilt (z. B. durch einen Spieler, eine Gruppe oder den Spielleiter), Umgang mit mehreren Gruppen, Gültigkeitsdauer einer Vormerkung, Reihenfolge konkurrierender Ereignisse und das Nachholen wiederholter Auslösungen. Diese Regeln werden später einzeln festgelegt.

## 02.20 – Typisierte Node-Ports, farbige Leitungen, Signalanzeige und Inverter (11.10.2026)

**Beschlossen: Variante C – vollständig typisierte Ein- und Ausgänge**, mit zusätzlichen verbindlichen Anforderungen für die Bedienbarkeit und die spätere saubere technische Planung.

### 1. Ein- und Ausgänge für unterschiedliche Signal- und Datenarten

- **Aktion/Ereignis:** Ein Ausgang meldet eine tatsächlich erfolgte Aktion bzw. ein Ereignis; ein passender Eingang kann eine Aktion anfordern (z. B. `Tür.Entriegelt` -> `Licht.Einschalten`).
- **Boolescher Zustand (Ja/Nein):** z. B. `Tür.IstVerriegelt` oder `Schalter.IstAn`.
- **Zahlenwerte:** z. B. verbleibende Ladungen, Entfernung, Rundenanzahl oder andere regelunabhängige numerische Werte.
- **Textwerte:** z. B. Nachrichten oder freigegebene Statusbezeichnungen; geheime Codes müssen vertraulich bleiben.
- **Typisierte Referenzen:** Verweise auf Figuren, Gegenstände und andere Szenenobjekte (später eventuell Szenen, Stockwerke, Gruppen).
- **Erweiterbare Typen:** Die Port-Vorlagen werden versionierbar geplant, sodass Module neue Typen/Ports ergänzen können.

Nur **kompatible Ports** sollen sich verbinden lassen. Im Editor sind Ein- und Ausgangsrichtung sowie Datentyp klar erkennbar; fehlerhafte Verbindungen erhalten verständliche Hinweise statt stiller Konvertierungen.

### 2. Farblich codierte Verbindungen – zusätzlich ausdrücklich beschlossen

- Jede Leitung/Portart erhält eine **eindeutige visuelle Typ-Kennzeichnung durch Farbe**, z. B. getrennte Kategorien für Ereignis, Boolesches Signal, Zahl, Text oder Objektverweis. Die tatsächlichen Farben legen wir später gemeinsam im UI-Design fest.
- **Farbe kennzeichnet den Typ**, der **aktuelle Signalzustand wird davon unabhängig** kenntlich gemacht, beispielsweise durch Leuchtintensität, Linienanimation, Markierung und beschriftete Statusanzeige. Damit sind „verbunden“, „kein Signal“, „Signal liegt an“ und „Fehler“ unterscheidbar.
- Für Zugänglichkeit nicht nur auf Farbe vertrauen: Port-Symbole, kurze Typbezeichnungen und optional einblendbare Signaltexte müssen die Bedeutung ebenfalls erklären.

### 3. Ist-Zustand und Signallauf im Test

- Im Node-Editor ist in der **Test-/Diagnoseansicht** erkennbar, ob ein Ein-/Ausgang **physisch verbunden**, aber derzeit **inaktiv**, oder ob dort **tatsächlich ein Signal/Wert** anliegt bzw. gerade ein Ereignis eintrifft.
- Eine vorhandene Verbindung bedeutet **nicht**, dass sie aktiv ist. Bei Dauerwerten sollte der aktuelle Wert angezeigt werden (z. B. `false`, `true`, `3`); bei Ereignissen wenigstens die sichtbare Auslösung bzw. das zuletzt beobachtete Ereignis.
- Der Spielleiter kann entlang der Verbindungen nachvollziehen, **an welcher Node ein Signal angekommen ist, welche Bedingung erfüllt wurde und warum etwas nicht ausgeführt wurde**.
- **Realen Ist-Zustand** aus dem autoritativen Server unterscheiden von einer **isolierten Simulation/Testausführung**, die keine tatsächlichen Türen, Inventare, Fallen oder Timer verändern darf.
- Aus der fehlenden Anzeige bei einer inaktiven Szene oder nicht freigegebenen Datenquelle darf niemals auf einen falschen Zustand geschlossen werden; berechtigte Diagnose und verständliche Statushinweise sind erforderlich.

### 4. Explizite Inverter-Nodes – zusätzlich ausdrücklich beschlossen

- Jeder für **logische Signale** geeignete Eingang oder Ausgang kann durch Vorschalten bzw. Nachschalten einer **sichtbaren Inverter-Node (NICHT/NOT)** logisch umgekehrt werden. Die Umkehrung soll als eigener Knoten im Graphen sichtbar bleiben statt einer versteckten Option am Port.
- Grundprinzip: `TRUE` -> **Inverter** -> `FALSE` und `FALSE` -> **Inverter** -> `TRUE`. Ein Beispiel: `Tür.IstVerriegelt` -> `NOT` -> `Freigabe erlaubt`.
- Eine Inverter-Node besitzt einen **passenden booleschen Eingang und einen booleschen Ausgang**; Porttypprüfung verhindert, dass z. B. Text, ein Ereignisimpuls oder eine Figurenreferenz ohne explizite Typkonvertierung als boolescher Wert behandelt wird.
- **02.21 beschlossen:** Ereignisports übertragen Impulse; Zustands-/Datenports liefern anliegende Werte. Präzise Impulsdauer und Unterbrechungsverhalten von Halteaktionen werden später spezifiziert. Für Ereignisse wird **keine stillschweigende „Umkehrung“** angenommen.

### Technische Qualitätsanforderungen

Node- und Portvorlagen erhalten stabile IDs/Typdefinitionen; Kanten besitzen Quell-/Zielportreferenzen und ihren Datentyp. Der **Graphzustand**, der **aktuelle Server-Signalzustand**, **letzter Ereignisimpuls** und die **rein grafische Präsentation** (Farbe, Linienführung, Hervorhebung) dürfen nicht vermischt werden. Statusänderungen werden nur für berechtigte Spielleiter dargestellt; doppelte Events, Endlosschleifen, konkurrierende Ausführungen und nicht mehr vorhandene Referenzen sind explizit zu behandeln. **Besondere Sorgfalt bei Spezifikation und Tests vor der Implementierung ist verbindliche Anforderung.**

**Noch offen:** Genaue Typ- und Portfamilien, die Farbpalette, Verhalten und Lebensdauer von Signalen, eventuelle Konverter-Nodes, Datenschutz bei Debug-Daten, Höchstgröße eines Graphen, Live-Debug-Frequenz und Undo/Versionierung.

## 02.21 – Impulse, Dauersignale und Halteschalter (11.10.2026)

**Beschlossen: Variante C.** Das Node-System unterstützt **kurze Ereignisimpulse** und **dauerhaft anliegende Zustands-/Datenwerte**, abhängig vom Porttyp.

- **Betätigungsimpuls:** Beim Betätigen kann ein einzelnes Ereignis ausgegeben werden. Dies ist kein dauerhaftes Signal.
- **Schalter (rastend):** Das platzierte Schaltobjekt besitzt den Modus **Schalter**; es speichert EIN oder AUS bis zur nächsten Betätigung.
- **Taster (gehalten):** Das gleiche Objekt kann stattdessen als **Taster** konfiguriert sein. Der boolesche Ausgang bleibt nur während des tatsächlichen Haltens EIN und wird beim Loslassen AUS. Ein zusätzlicher kurzer Ereignisimpuls beim Drücken ist ein separater Port, kein Ersatz für den Haltezustand.
- **Kooperatives Mehrspieler-Beispiel:** Spieler A hält den Schalter, sodass `Schalter.Gehalten = true` gilt. Dadurch ist eine verbundene Tür oder Barriere passierbar, während Spieler B hindurchgeht. Spieler A und B können gleichzeitig unabhängig handeln. Beim Loslassen wird `false` übertragen. Das Verhalten der Tür beim Signalverlust legen wir in 02.22 fest.
- **Node-Diagnose:** Der Spielleiter erkennt getrennt, ob eine Leitung verbunden ist, ob ein anliegendes Signal EIN oder AUS ist, ob gerade ein Ereignisimpuls eintrifft und ob ein Fehler vorliegt. Der reale Server-Iststand ist von einer gefahrlosen Simulation zu unterscheiden.
- **Inverter:** Eine sichtbare NOT-Node kehrt boolesche Dauerzustände um; Ereignisimpulse werden ohne gesonderte Umwandlung nicht invertiert.
- **Serverlogik:** Halteaktionen werden an berechtigte Spieler-/Figurenaktionen gebunden. Server validiert Start, Aufrechterhaltung und Ende. Verbindungsverlust, Reichweite, Spielerwechsel und gleichzeitiges Halten durch mehrere Figuren sind gesondert zu spezifizieren. Clients dürfen nicht unbegrenzt ein aktives Signal behaupten, nachdem die Aktion ungültig geworden ist.

**Noch offen:** Genauer Lebenszyklus von Halteaktionen, Eingabebedienung auf Maus/Touch/Tastatur, sichere Kollision bei schließender Tür, Impulsdauer und Ausführung bei Netzwerkstörungen. Die sofortige physische Schließung bei Signalverlust ist ausdrücklich **nicht** automatisch beschlossen.

## 02.22 – Türreaktion bei Signalverlust und Schalter-/Taster-Modus (11.10.2026)

**Beschlossen: Variante C – pro Zielobjekt konfigurierbar.** Wenn ein anliegendes Haltesignal wegfällt, kann die angeschlossene Tür oder Barriere **sofort** in den Ausgangszustand zurückkehren, **geöffnet/aktiviert bleiben** oder **nach einer einstellbaren Echtzeitdauer bzw. Anzahl von Spielrunden** reagieren.

**Zusätzliche ausdrückliche Vorgabe:** Beim Anlegen und Bearbeiten eines Schaltobjekts gibt es eine verständliche Einstellung **Schalter oder Taster**:

| Modus | Bedienung | Boolescher Ausgang |
| --- | --- | --- |
| **Schalter** | Einmal betätigen schaltet um; erneutes Betätigen wieder zurück | Bleibt EIN oder AUS bis zur nächsten Zustandsänderung |
| **Taster** | Muss gedrückt bzw. gehalten werden | EIN nur solange eine berechtigte Halteaktion andauert; beim Loslassen AUS |

Ein getrennt nutzbarer **Ereignisimpuls beim Betätigen** bleibt möglich, darf aber nicht fälschlich den anliegenden Zustand eines Tasters ersetzen.

**Kooperatives Beispiel:** Spieler A hält einen Taster. Dessen `IstGedrückt`-Ausgang liefert EIN und ermöglicht Spieler B den Durchgang durch die Tür. Beim Loslassen wird AUS übertragen. Ob die Tür schließt oder offen bleibt, bestimmt **die eigene Einstellung dieser Tür**. Schalter-Modus und Tür-Reaktion sind somit getrennte Konfigurationen.

**Technische Anforderungen:** Objektinstanzen bekommen eine persistente Betriebsart `Schalter/Taster`, einen booleschen Ist-Zustand sowie separate Ereignisausgänge. Halteaktionen werden vom Server einer berechtigten Figur zugeordnet; Clients dürfen kein ungültig gewordenes Signal endlos aufrechterhalten. Die genaue Behandlung von Verbindungsabbrüchen, gleichzeitigen Haltern und Eingabegeräten bleibt zu spezifizieren. Verzögerungen verwenden getrennte Echtzeit- und Runden-Timer. Im Node-Test sind Verbindung, anliegendes EIN/AUS und Betätigungsimpuls unterscheidbar.

**Nicht vorweggenommen:** Eine sich schließende Tür kann mit einer Figur im Durchgang kollidieren. Schadensfolgen, Bewegung und Sicherheitsverhalten sind noch nicht entschieden; keine automatische Einklemm- oder Schadenregel annehmen.

## 02.23 – Figuren im Durchgang bei schließenden Türen und Barrieren (11.10.2026)

**Beschlossen: Variante C – das Verhalten ist pro Tür oder Barriere konfigurierbar.**

- **Warten / Schließen verhindern:** Ist der Durchgang belegt, wird das Schließen nicht vollendet. Das Schließen kann nach Freigabe des Durchgangs erneut versucht werden; die genaue Wiederholungsregel wird später festgelegt.
- **Wieder öffnen:** Erkennt die Tür beim Schließversuch eine Figur, stoppt sie und öffnet wieder; dieser Zustandswechsel kann andere Nodes ansteuern.
- **Trotz Hindernis schließen:** Der Spielleiter kann eine gefährliche Tür oder Barriere so einstellen, dass ihr Schließvorgang auch bei belegtem Durchgang fortgesetzt wird. Welche Auswirkungen das auf betroffene Figuren hat, ist **nicht automatisch vorgeschrieben**, sondern folgt aus einem getrennten, später zu konfigurierenden Effekt/Regelprofil.

**Beispiel:** Spieler A lässt einen gehaltenen Taster los. Die Tür versucht gemäß 02.22 zu schließen, während Spieler B noch im Türrahmen steht. Die Einstellung dieser Tür entscheidet, ob sie wartet, wieder aufschwingt oder trotz Hindernis den Schließvorgang fortsetzt.

### Anforderungen für das Node- und Bewegungsmodell

- Die Durchgangserkennung muss die tatsächliche Platzierung von Figuren und den logischen Tür-/Barrierenbereich berücksichtigen; reine Bildschirmgrafik ist kein zuverlässiger Kollisionsnachweis. Genauer Algorithmus, Token-Größe, Raster-/Freibewegung, Fahrzeuge und unterschiedliche Höhen bleiben separat offen.
- **Schließbefehl ist nicht automatisch erfolgreiches Schließen:** Für das Node-System unterscheiden wir Ereignisse wie `Schließen angefordert`, `Hindernis erkannt`, `Schließen blockiert`, `Wieder geöffnet` und `Geschlossen`. Erfolgs-Ausgänge feuern nur nach tatsächlichem Statuswechsel.
- Mehrspielerbewegungen und Schließversuche werden serverseitig konsistent verarbeitet. Doppelte Netzwerknachrichten dürfen keine unbeabsichtigten mehrfachen Auswirkungen erzeugen.
- Schalter-/Tastermodus aus 02.22 sowie Echtzeit-/Rundenverzögerungen bleiben unabhängig von der Kollisionseinstellung des Zielobjekts.
- **Keine vorausgesetzten Schäden oder automatische Verschiebung von Figuren:** Wer Schaden erhält, wie eine Figur blockiert oder verschoben wird und welche Rettungsmöglichkeiten bestehen, sind gesonderte Spielregelentscheidungen. Der Spielleiter kann eine Tür als gefährlich konfigurieren, ohne dass AdventureShift ein festes D&D-Schadenssystem erzwingt.
- Der Spielleiter sieht im Node-Testmodus den realen Schließstatus sowie gegebenenfalls Hinderniserkennung und gewählte Reaktion; eine isolierte Simulation darf keine echte Figur verletzen oder bewegen.

**Noch offen:** Kollisionsgeometrie und Größe, gleichzeitige Figuren, Verhalten bei dauerhaft blockiertem Durchgang, Schadens- und Bewegungseffekte, Effekte wiederkehrender Schließversuche und Definition von „trotz Hindernis geschlossen“ im konkreten Regelprofil.

## 02.24 – Folgen gefährlicher Türen und globale Kampagnenstandards (11.10.2026)

**Beschlossen: Variante C mit ausdrücklicher Erweiterung – solche Verhaltensregeln werden bereits bei der Kampagnenerstellung zentral festgelegt.**

### Globale Vorgaben bei der Kampagnenerstellung

- Unter **Kampagneneinstellungen → Spielregeln → Umgebung und Interaktionen** (Arbeitstitel) kann der Spielleiter **globale Standardregeln** festlegen. Insbesondere für Türen, Schleusen, Tore, Fallen und Barrieren sollen sich wiederkehrende Einstellungen und Konsequenzen nicht an jedem neuen Objekt einzeln wiederholen müssen.
- **Typische Voreinstellungen:** Verhalten bei Figur im Durchgang aus 02.23 (warten, wieder öffnen, erzwungen schließen); zulässige Folgen einer erzwungenen Schließung (kein zusätzlicher Effekt, Warnung/Alarm, Schadens-/Statuseffekt, Node-/Story-Ereignis); gegebenenfalls Regeln mit **Echtzeit** oder **Spielrunden**.
- Die Kampagneneinstellung verweist bei Schadens-/Statusberechnung auf das **aktivierte Regelprofil**, soweit vorhanden. Der Systemkern schreibt keinen festen D&D-Schaden vor. Ohne passendes Regelmodul darf keine nicht konfigurierte automatische Schadensberechnung angenommen werden.
- **Vererbung und individuelle Ausnahmen:** Neue Objekte übernehmen zunächst die **globalen Kampagnenstandards** ihres Typs. Die Spielleiter können für besondere Objekte einzelne Eigenschaften **bewusst überschreiben**, etwa eine Sicherheitsschleuse mit gefährlichem Schließverhalten. Eine Ausnahme soll klar als solche markiert sein.
- **Nicht nur Türen:** Das Prinzip zentraler Kampagnenstandards soll für ähnliche allgemein nutzbare Objekt- und Interaktionsregeln vorbereitet werden, statt später zahlreiche unabhängige Eigenschaftsfenster pflegen zu müssen. Welche anderen Einstellungen im Kampagnenassistenten erscheinen, wird im Kampagnen-Workshop detailliert geklärt.
- **Regeln und Signalgraph getrennt:** Der Standard bestimmt das normale Objektverhalten; das Node-System kann zusätzliche definierte Ereignisse auslösen. Freigaben, Schlüssel-/Codeprüfung und Sicherheitsvorgaben dürfen durch die globale Vererbung nicht unbeabsichtigt umgangen werden.

### Beispiel

Kampagne: Standardtüren warten, wenn eine Figur im Durchgang steht; **kein automatischer Schaden**. Eine eigens konfigurierte Sicherheitsschleuse darf stattdessen schließen und ein Node-Ereignis `Einklemmung erkannt` auslösen, dessen Folgen das aktive Regelprofil definiert.

### Architektur- und UX-Folgen

Kampagneneinstellungen benötigen versionierbare, serverseitig geprüfte **Regelprofile und Standardwerte**, die per Objekttyp an Instanzen vererbt werden können. Jede Objekt-Eigenschaft sollte erkennbar machen: **„Kampagnenstandard“** oder **„individuell überschrieben“**. In der Spielleiteransicht sind die tatsächlich wirksamen Werte (Ist-Konfiguration) zu zeigen. Änderung von Kampagnenregeln erfordert nachvollziehbare Auswirkungen auf vorhandene Instanzen.

**Mit 02.25 entschieden:** Änderungen an Kampagnenstandards bieten vorab eine Vorschau und eine Wahl zwischen nur künftigen Objekten oder auch bestehenden, bisher nicht individuell überschriebenen Objekten. Bereits gesetzte individuelle Ausnahmen bleiben geschützt. **Offen:** Pflichtangaben im Kampagnenassistenten, Regelprofilwechsel, genaue Konflikt-/Rollback-Semantik und die technische Vererbungsauflösung.

## 02.25 – Änderungen globaler Kampagnenregeln während einer Kampagne (11.10.2026)

**Beschlossen: Variante C – bei jeder Änderung mit Vorschau wählbar, ob bestehende Objekte aktualisiert werden.**

- **Vorschau vor dem Speichern:** Der Spielleiter sieht für die betroffene Einstellung den bisherigen und neuen Standard, die betroffenen Objekttypen sowie eine nachvollziehbare Aufschlüsselung: vorhandene Objekte ohne Ausnahme, vorhandene mit individueller Ausnahme und neu zu erstellende Objekte. Geheime Objekte bleiben vor unberechtigten Spielern geschützt.
- **Wahl bei jeder Änderung:** (1) **Nur für künftig neu erstellte Objekte** oder (2) **auch auf vorhandene Objekte ohne individuelle Ausnahme anwenden**. Bereits festgelegte Ausnahmen werden bei beiden Varianten respektiert und nicht überschrieben.
- **Alte Werte erhalten:** Bei der Auswahl „nur künftige Objekte“ behalten bestehende Objekte ihren wirksamen bisherigen Wert, obwohl sich der neue Kampagnenstandard für Neuanlagen ändert. Dazu muss die technische Vererbung bestehende Werte gegebenenfalls als historische Vorlage/Snapshot sichern, statt sie versehentlich dynamisch mitzuändern.
- **Bestehende Objekte aktualisieren:** Bei bewusster Anwendung auf den Altbestand ändern sich ausschließlich die ausgewählten, bisher nicht individuell überschriebenen Eigenschaften. Nach Möglichkeit den bisherigen und neuen wirksamen Wert anzeigen; eine individuelle Ausnahme bleibt sichtbar und unverändert.
- **Bewusste Freigabe:** Der Spielleiter bestätigt die Änderung erst nach Vorschau. Serverseitige Rechteprüfung, nachvollziehbare Speicherung und Versions-/Änderungsprotokoll sind erforderlich. Fehler bei teilweise möglichen Aktualisierungen dürfen nicht still übergangen werden.
- **Laufender Spielzustand:** Änderung einer Türregel ist von einem tatsächlichen Türöffnungs- oder Türschließereignis zu unterscheiden. Keine unvorhergesehenen Node-Auslösungen nur durch das Umschreiben einer Einstellung. Welche bereits aktiven Timer/Schaltungen neu bewertet werden, ist später separat zu spezifizieren.
- **Genre- und Regelprofilneutral:** Die Vererbungslogik soll für Türen, Fallen, allgemeine Objektinteraktionen und künftige Kampagnenstandardwerte gelten; kein festes D&D-System voraussetzen.

**Beispiel:** In einer Kampagne lautet der bisherige Standard „Tür wartet bei Hindernis“. Der Spielleiter ändert ihn auf „Tür öffnet wieder“. Er kann auswählen, ob diese Regel erst für neue Türen gilt oder auch für die bestehenden Standardtüren. Eine besondere Sicherheitstür mit eigener Einstellung „trotz Hindernis schließen“ bleibt in beiden Fällen unverändert.

**Noch zu spezifizieren:** Nachträgliche Rücknahme/Undo, Versionsmigration, aktive Spielereignisse beim Regelwechsel, Auswahl einzelner Objektgruppen innerhalb einer globalen Änderung und Verhältnis von Regelprofil- zu Kampagnenstandards.

## 02.26 – Frei organisierbare Node-Arbeitsbereiche (11.10.2026)

**Beschlossen: Variante C – frei benannte und organisierbare Node-Pläne mit Gruppen, Untergraphen und kampagnenweiten Verknüpfungen.**

- **Mehrere Node-Arbeitsbereiche:** Spielleiter können beliebig viele logisch getrennte, benannte Arbeitsflächen innerhalb einer Kampagne anlegen, um beispielsweise „Türen und Schalter“, „Fallen“, „Hauptquest“ oder „Raumschiffsteuerung“ getrennt zu bearbeiten. Die genaue technische Obergrenze für sehr große Kampagnen ist später zu prüfen.
- **Freie Organisation:** Ein Arbeitsbereich lässt sich nach Szene, Stockwerk, Thema oder Funktion benennen und ordnen; die Zuordnung ist organisatorisch, **keine technische Beschränkung der Verbindungen** auf diese Szene oder dieses Stockwerk.
- **Gruppen und Untergraphen:** Zusammengehörige Nodes können auf einer Arbeitsfläche gruppiert, umbenannt, eingeklappt und wieder aufgeklappt werden. Ein Untergraph lässt sich als übersichtlicher Block mit klaren Ein-/Ausgängen darstellen, während seine innere Schaltung weiterbearbeitbar bleibt.
- **Kampagnenweite Querverbindungen:** Die Entscheidung 02.18 gilt auch über verschiedene Arbeitsbereiche hinweg. Eine Leitung von „Türen und Schalter“ kann einen Eingang einer Node in „Hauptquest“ ansteuern. Querverbindungen müssen als nachvollziehbare Referenzen und sichtbare Übergänge erkennbar bleiben; nichts darf beim Einklappen stillschweigend getrennt werden.
- **Gesamtübersicht:** Eine durchsuchbare Liste/Übersicht zeigt alle Arbeitsbereiche und Querverbindungen, einschließlich Quell- und Zielort. Navigationsfunktionen sollen von einer referenzierten Node oder Verbindung zum richtigen Plan führen.
- **Farbcodes und Iststand erhalten:** Port- und Leitungstypen bleiben wie 02.20 farblich codiert, die Testansicht unterscheidet weiterhin verbundenes Kabel, aktiven Zustand, Ereignisimpuls und Fehler, auch bei Übergängen zwischen Arbeitsbereichen.
- **Objekt-Identität bewahren:** Ein Objekt-Node ist eine **Referenz auf eine konkrete, stabile Objektinstanz**, nicht automatisch eine neue Tür, ein neuer Schalter oder eine Kopie des Objektzustands. Ein Objekt kann aus mehreren Ansichten referenziert werden, darf dadurch aber keine widersprüchlichen Spielzustände erhalten.
- **Rechte und Geheimnisse:** Arbeitsbereiche mit vertraulichen Spielleiter-Schaltungen bleiben für unberechtigte Spieler verborgen. Verschieben, Umgruppieren oder Umbenennen ändert nicht unbemerkt die Sicherheit der referenzierten Szenen oder Objekte.
- **Persistenz:** Zugehörigkeiten, Gruppierung, Untergraph-Ansichten, Layout, Zoom und Positionen sollten unabhängig von den autoritativen Ausführungsregeln speicherbar sein. Änderungen an der Darstellung dürfen keine echte Node-Aktion auslösen.

**Technische Planung:** Ein logischer kampagnenweiter Graph bzw. verknüpfbare Teilgraphen mit stabilen Objekt-, Node-, Port- und Kanten-IDs. Arbeitsbereiche/Groups sind persistente editorseitige Ordnungs- und Sichtstrukturen. Für gruppierte Bausteine gelten explizite Schnittstellenports; die tatsächliche Signalauswertung verbleibt beim Server. Zwischen Arbeitsbereichen sind klare Sprungverweise und Referenz-/Verbindungsprüfungen vorzusehen.

**Mit 02.27 entschieden:** Wiederverwendbare parametrisierbare Untergraph-Vorlagen mit Ein-/Ausgängen, stabilen Versionen sowie drei Layoutansichten: manuell, automatisch szenenweise gerahmt und automatisch szenenunabhängig. **Weiter offen:** Details von Untergraph-Schnittstellen, Navigation bei tausenden Nodes, frei definierte Hierarchie, Mehrpersonenbearbeitung, algorithmische Leitungsführung und Kopierregeln.

## 02.27 – Wiederverwendbare Node-Bausteine und drei Layoutansichten (11.10.2026)

**Beschlossen: Variante C – wiederverwendbare, parametrisierbare Node-Bausteine mit definierter Schnittstelle, ergänzt durch drei unterschiedliche Darstellungsansichten desselben Node-Netzes.**

### Wiederverwendbare Schaltungs-Bausteine

- Ein Spielleiter kann eine Node-Gruppe bzw. einen Untergraphen als **benannte Vorlage** speichern, mit klaren **Eingangs- und Ausgangsports** und **einstellbaren Parametern** (z. B. Zeitverzögerung, Anzahl Spielrunden, boolesche Optionen).
- Beispiel: „Zeitgesteuerte Sicherheitstür“ umfasst Taster-/Schalterlogik, Timer, Bedingungen und Türsteuerung. Beim Einsetzen werden die konkreten Tür-/Schalterinstanzen und die benötigten Parameter gewählt.
- Eine gespeicherte Vorlage ist **nicht automatisch eine zweite echte Tür**: Objektverweise werden beim Einsetzen ausdrücklich auf vorhandene konkrete Objekte gebunden; die internen Node- und Portreferenzen sind stabil und validierbar.
- Vorlagen erhalten eine **Version**. Ändert der Spielleiter die Vorlage später, dürfen bereits eingesetzte Schaltungen **nicht ungefragt oder mit Informationsverlust** geändert werden. Ob eine Instanz Updates bewusst übernimmt, wird separat geplant.
- Als wiederverwendbarer Untergraph kann ein Baustein kompakt dargestellt und für die Bearbeitung wieder aufgeklappt werden; dies passt zum Beschluss 02.26 über Gruppen und mehrere Node-Arbeitsbereiche.

### Drei Ansichten (ausdrückliche zusätzliche Produktvorgabe)

**Ansicht 1 – Manuelle Spielleiteransicht**
- Originale Arbeitsansicht, in der der Spielleiter Nodes selbst platziert, ausrichtet und nach eigenen Wünschen organisiert.
- Bewahrt dessen **handgesetzte Positionen**, eigene Arbeitsbereiche, Gruppen und Pfadführung. Keine automatische Anordnung überschreibt diese Arbeit stillschweigend.

**Ansicht 2 – Automatische Szenenansicht**
- Beim Umschalten werden Nodes automatisch räumlich **nach ihrer Szenenzuordnung gruppiert** und möglichst übersichtlich angeordnet.
- **Jede Szene erhält einen klar abgegrenzten rechteckigen Rahmen mit sichtbarem Szenentitel**. Nodes, die zu dieser Szene gehören, werden innerhalb des Rahmens platziert; die Rahmen wachsen bei Bedarf mit.
- Innerhalb jeder Szenengruppe sollen Node-Überlappungen und Leitungskreuzungen **möglichst gering** sein. Beziehungen zwischen Szenen werden mit nachvollziehbaren, typfarbigen Verbindungen über Rahmengrenzen hinweg visualisiert.
- Logik-/Timer-/Kampagnen-Nodes ohne eindeutige Szenenzuordnung erhalten eine passende, als **„Kampagnenweit / ohne Szene“** gekennzeichnete Gruppe statt einer erfundenen Szenenzuordnung. Bei Bezug zu mehreren Szenen ist die eindeutige Gruppierungsregel später zu spezifizieren; kein ungewolltes Duplizieren von Objekt-/Logikzustand.

**Ansicht 3 – Automatische Gesamtansicht**
- Ebenfalls automatische räumliche Anordnung aller im gewählten Umfang sichtbaren Nodes, aber **vollständig unabhängig von Szenengruppierung** und Szenenrahmen.
- Der Anordnungsalgorithmus kann dabei primär die **Verbindungsstruktur** berücksichtigen: nah zusammengehörige Nodes sinnvoll positionieren, Kollisionen zwischen Nodes vermeiden und Leitungsüberkreuzungen sowie unnötig lange Kabel möglichst minimieren.
- Diese Ansicht soll für das Verstehen längerer kampagnenweiter Signalketten geeignet sein, ohne szenenweise Aufteilung zu erzwingen.

### Gemeinsame Grenzen und Anforderungen

- **Eine einzige funktionale Schaltungsdefinition:** Alle drei Ansichten verwenden **dieselben Node-/Objekt-/Port-/Kanten-IDs, die gleiche Ausführungslogik und dieselben zugriffsberechtigten Ist-Signalwerte**. Sie sind **Ansichten**, keine voneinander abweichenden Kopien der Schaltung.
- **Ansichtswechsel darf die manuelle Ansicht nicht verändern:** Die von Hand gesetzten Positionen und Organisation bleiben gespeichert; für die automatischen Ansichten gibt es unabhängige berechnete und ggf. zwischengespeicherte Layoutdaten.
- **„Möglichst ohne Überschneidungen“ als klares Optimierungsziel:** Node-Karten und Gruppenrahmen sollen sich nicht überdecken, Signalwege sollen lesbar bleiben, Leitungskreuzungen soweit praktikabel reduzieren. Bei sehr großen/komplexen Graphen sind absolute Kreuzungsfreiheit oder exakte optimale Graphlayouts nicht garantiert. Stabile, nachvollziehbare Anordnung ist wichtiger als hektisches Hin- und Herspringen.
- **Gleichbleibende Darstellung der Signale:** Farblich typisierte Leitungen, aktive/inaktive Zustände, Impulse und Diagnosefehler aus 02.20/02.21 bleiben in allen Ansichten erkennbar. Die Test-/Simulationsfunktion ändert durch Layoutwechsel keine echten Spielzustände.
- **Skalierung und Navigation:** Zoomen, Verschieben, Suche, Auswahl, „auf Inhalt einpassen“, zu Node/Szene springen und visuelle Übergänge beim automatischen Umordnen sind als UX-Anforderungen vorzusehen. Das Detailverhalten und die Layoutaktualisierung bleiben noch offen.
- **Rechte:** Nur autorisierte Spielleiter dürfen versteckte Szene-/Objektinformationen in der Gesamtschaltung sehen; Spieler erhalten durch eine automatische Szenenübersicht keine neuen Geheimdaten.
- **Server vs. Anzeige:** Automatische Positionierung und Leitungsrouting sind **reine editorseitige Layoutberechnung**; der eigentliche Aktionsgraph und die serverseitige Regelverarbeitung bleiben unverändert.

**02.28 beschlossen:** Automatische Ansichten können beim ersten Aufruf und bei relevanten Änderungen neu layoutet werden; 'Neu anordnen', Pausieren und Fixieren kontrollieren die Aktualisierung. Die manuelle Spielleiteransicht bleibt unangetastet. **Weiter offen:** genaue Regeln für einzelne fixierte Nodes, mehrere Szenenzuordnungen, Leitungsrouting, Layoutanimationen, große Graphen sowie Vorlagenverwaltung.

## 02.28 – Automatische Neuanordnung mit Fixierfunktion (11.10.2026)

**Beschlossen: Variante C – automatische Layoutberechnung mit Kontrolle und Fixiermöglichkeiten.**

- **Erstes Öffnen oder Wechsel in eine automatische Ansicht:** Szenenansicht und freie Gesamtansicht erzeugen ein passendes Layout mit ausreichenden Abständen, möglichst wenigen Überschneidungen und nachvollziehbaren Verbindungen.
- **Relevante Graphänderungen:** Neue bzw. entfernte Nodes, neue Verbindungen und veränderte Gruppierungen dürfen eine automatische, möglichst schonende Aktualisierung der jeweiligen Ansicht auslösen. Es sollen nach Möglichkeit nur betroffene Bereiche verschoben werden, damit der restliche Graph für den Spielleiter räumlich wiedererkennbar bleibt.
- **'Neu anordnen':** In beiden automatischen Ansichten gibt es eine explizite Aktion, um das gesamte sichtbare Netz bzw. den gewählten Bereich neu zu layouten. Dabei gelten weiterhin die Gruppierungsregeln der gewählten Ansicht (Szenenrahmen in Ansicht 2, ohne Szenengruppierung in Ansicht 3).
- **'Positionen fixieren' / Auto-Anordnung pausieren:** Der Spielleiter kann die automatische Neupositionierung während des Bearbeitens vorübergehend anhalten, um zu verhindern, dass Nodes und Verbindungen ständig ihre Position wechseln. Ein klar sichtbarer Status zeigt, ob der Auto-Layout-Modus momentan aktiv oder fixiert ist. Fixierung lässt die Schaltung weiter funktionieren; nur die Darstellung wird festgehalten.
- **Manuelle Ansicht dauerhaft schützen:** Die vom Spielleiter eigenständig gesetzten Positionen, Gruppen und die manuelle Anordnung aus Ansicht 1 werden **niemals** durch Berechnung oder Fixierung der automatischen Ansichten überschrieben. Beim Zurückwechseln ist die ursprüngliche Anordnung unverändert wieder da.
- **Ein Graph, getrennte Layoutzustände:** Die drei Ansichten teilen die gleichen logischen Node-/Port-/Kanten-/Objekt-IDs und Signalzustände, aber haben unabhängige Layoutkoordinaten bzw. Darstellungscaches. Ansicht wechseln, Layout neu berechnen oder fixieren ist **keine Node-Aktion** und darf keine Schalter, Timer, Türen oder Fallenauslöser aktivieren.
- **Wartende Layoutänderungen:** Wenn während der Fixierung neue Nodes hinzukommen oder Verbindungen geändert werden, gehen sie im Graphen nicht verloren. Ihre Darstellung wird auch im fixierten Modus nachvollziehbar ergänzt bzw. eine ausstehende Layoutaktualisierung kenntlich gemacht. Die genaue Strategie, wie neue Nodes zunächst positioniert werden, bleibt offen.
- **Testansicht und Rechte:** Farben, aktive/inaktive Signalzustände und Fehlersymbole funktionieren auch bei fixierter Anordnung. Geheime Objekte und Szeneinformationen dürfen durch Auto-Layout nicht an Spieler weitergegeben werden.
- **Leistungsziel:** Bei großen Graphen unnötige permanente Neuberechnung vermeiden; stabile räumliche Orientierung ist wichtiger als nach jeder kleinen Zustandsänderung ein optimales, aber völlig anderes Layout.

**Mit 02.29 entschieden:** Direkte Kabel über Szenenrahmen oder kompakte beschriftete Rahmen-Übergangspunkte sind in der Szenenansicht umschaltbar; beide spiegeln identische Verbindungen und Signalzustände wider. **Weiter offen:** einzelne fixierte Nodes, genaue Neuberechnungsregeln, Leitungsrouting, Zoom-/Animationsverhalten, Layoutalgorithmus und Grenzfälle bei großen Graphen.

## 02.29 – Verbindungen zwischen Szenenrahmen wahlweise direkt oder kompakt (11.10.2026)

**Beschlossen: Variante C – beide Darstellungsarten sind in der automatischen Szenenansicht umschaltbar.**

### Ansicht „Direkte Leitungen“

- Farbig typisierte Kabel verlaufen **direkt von den Ports der Quell-Node zu den Ports der Ziel-Node**, auch wenn sie Szenenrahmen kreuzen.
- Die Leitung soll sich bis zu beiden Endpunkten nachvollziehen lassen; beim Darüberfahren bzw. Auswählen werden zusammengehörige Kabel und Portbezeichnungen hervorgehoben.
- Der Layoutalgorithmus minimiert soweit sinnvoll verdeckte Ports, Überlagerungen, unlesbare Kreuzungen und unnötig lange Wege; absolute Kreuzungsfreiheit ist bei komplexen Graphen nicht garantiert.

### Ansicht „Übergangspunkte am Szenenrahmen“

- Szenenübergreifende Kabel werden **an eindeutig beschrifteten Ein- und Ausgangspunkten am rechteckigen Szenenrahmen** dargestellt, z. B. `Ausgang → Maschinenraum / Schott A / Öffnen`.
- Die Punkte sind **grafische Weiterleitungen/Anker**, keine zusätzlichen funktionalen Nodes und keine neu angelegten Ereignisregeln. Sie referenzieren dieselbe bestehende Kante zwischen realen Node-/Port-IDs.
- Durch Anklicken/Anwählen eines Übergangspunkts lässt sich **die Gegenstelle finden, hervorheben und anspringen**. Quelle, Ziel, Szenenname und Porttyp bleiben auffindbar.
- Bei vielen Verbindungen dürfen Übergangspunkte zur Entlastung der Darstellung kompakt gruppiert werden, sofern **jede zugrunde liegende Verbindung einzeln identifizierbar** bleibt. Das genaue Bündelungsverhalten wird später gestaltet.

### Gemeinsame technische und UX-Vorgaben

- **Umschalter innerhalb der Szenenansicht:** „Direkte Leitungen“ / „Übergangspunkte“ ohne Verlust von Graphinformationen oder Bewegung der manuell gesetzten Nodes. Es ist eine Präsentationsoption, keine Änderung der Signal- oder Ereignisverarbeitung.
- **Farbkodierung und Iststand (02.20/02.21):** Beide Darstellungen erhalten korrekte Leitungstypfarben, Angaben zu verbunden/nicht aktiv/Signal aktiv, Ereignisimpulsen und Fehlern. Kompakte Übergangspunkte zeigen Signalstatus ebenso nachvollziehbar wie direkte Leitungen.
- **Gleicher kanonischer Graph:** Eine Verbindung besitzt weiterhin genau eine autoritative Quell-/Zielidentität. Keine duplizierten Schaltungen, keine neuen Ports im Servermodell allein wegen eines Rahmenübergangs.
- **Ansichten getrennt (02.27/02.28):** Manuelle Spielleiteransicht und automatische szenenunabhängige Gesamtansicht bleiben von der gewählten szenenbezogenen Kabeldarstellung unberührt; Fixier-/Neu-anordnen-Funktionen wirken nur auf die Layoutdaten.
- **Rechte und Navigation:** Geheime Szenen-/Objektverknüpfungen bleiben für unberechtigte Teilnehmer unsichtbar; nur autorisierte Spielleiter dürfen zu verborgenen Zielen springen.

**Mit 02.30 entschieden:** Mehrfach szenenbezogene Nodes erhalten einen frei wählbaren primären Anzeigeort (eine Szene oder „Kampagnenweit“), mit Referenz-/Übergangspunkten in anderen Szenen statt Node-Kopien. **Weiter offen:** Standardwahl für direkte Leitungen/Übergänge, Leitungskabel-Routing, Bündelung, Statusaktualisierungsrate und Zoom-abhängige Details.

## 02.30 – Primärer Anzeigeort für mehrfach szenenbezogene Nodes (11.10.2026)

**Beschlossen: Variante C – der Spielleiter kann für eine Node, die mehrere Szenen betrifft, die primäre Szene oder „Kampagnenweit“ als ihren Anzeige-Heimatort festlegen.** Andere Szenen erhalten bei Bedarf nur beschriftete Referenz-/Übergangspunkte.

### Verbindliche Darstellung

- **Wählbarer Anzeigeort:** Der Spielleiter kann einem szenenübergreifenden Timer, einer Bedingung oder einer Logik-Node als primären Anzeigeort **eine konkrete Szene oder den Bereich „Kampagnenweit“** geben. Die Position innerhalb dieses Rahmens wird von der automatischen Szenenansicht nach 02.27–02.28 berechnet.
- **Ein echter Node-Zustand:** In der automatischen Szenenansicht erscheint die eigentliche Node genau einmal am primären Anzeigeort. Die weiteren Szenen zeigen bei Bedarf **beschriftete Referenzen/Anschlüsse**, über die man dieselbe Node erreichen, hervorheben und ihren Status nachvollziehen kann. **Keine Duplikate der Ausführung, Signale, Timer oder Objektzustände.**
- **Referenzen bleiben interaktiv:** Ein Klick auf den Referenz-/Übergangspunkt navigiert zur primären Node und zeigt die relevante Verbindung. Der Anzeigeort und die aktuellen Porttypen/-werte bleiben verständlich. Bei der alternativen Darstellung mit direkten Leitungen aus 02.29 darf die Kante dennoch direkt zur eigentlichen Node laufen.
- **Trennung von Ort und Logik:** Der primäre **Anzeigeort ist eine reine Editor-/Layoutzuordnung**. Er ändert **nicht** die echte Szenen- und Stockwerkszuordnung eines bereits platzierten Tür-, Schalter-, NPC- oder anderen Szenenobjekts. Ein Umgruppieren kann niemals physisch eine Tür in eine andere Szene versetzen.
- **„Kampagnenweit“:** Nodes ohne eindeutige Szenenzugehörigkeit oder mit kampagnenübergreifenden Abhängigkeiten innerhalb derselben Kampagne können gesammelt in einem eigenen, eindeutig benannten Rahmen stehen. Querverweise zu betroffenen Szenen bleiben sichtbar; Szenen-IDs werden nicht erfunden.
- **Persistenz und Bearbeitung:** Die Anzeige-Heimat lässt sich später ändern und wird als eigene Präferenz/Eigenschaft der Graphdarstellung gespeichert. Bei Änderung bleiben stabile Node-/Port-/Kanten-IDs, Ausführungsregeln, Signalzustände und die vom Spielleiter angelegte **manuelle Ansicht** unverändert.
- **Umbenennen, Löschen und Sicherheit:** Namen von Szenen werden in den Referenzen aktualisiert; bei entfernten Szene-/Objektreferenzen ist ein verständlicher Hinweis erforderlich, statt still auf andere Ziele umzubiegen. Versteckte Szenen- und Node-Details bleiben ausschließlich für berechtigte Spielleiter sichtbar.

**Technische Abgrenzung:** Die Zuordnung `scene_auto_display_home = scene_id | campaign_wide` ist ein **Präsentationsattribut**, getrennt von `physical_scene_id` eines Szenenobjekts sowie getrennt von der logischen Node-/Event-Definition. Querverweise sind reine UI-Projektionen derselben Graphkante, keine neuen serverseitigen Ports oder zusätzlichen Auslöser. Die exakten Feldnamen sind nicht verbindlich.

**Noch offen:** Automatische Vorgabe für neue Mehr-Szenen-Nodes, besondere Fälle von dynamischer Szenenzuordnung, Mehrfachbezüge an Stockwerke, Darstellung der Referenzen bei hohem Verbindungsaufkommen und endgültige Layout-/Navigationsdetails.

## 02.31 – Vollständiger Node-Test- und Debugmodus (11.10.2026)

**Beschlossen: Variante C – Live-Iststand, Ereignisprotokoll und umfassende isolierte Schritt-für-Schritt-Simulation mit Breakpoints.**

### 1. Live-Iststand – nur beobachten

- **Direkt an Port und Verbindung:** Anzeige, ob ein Kabel angeschlossen ist, ob ein boolescher Dauerwert `true` oder `false` ist, welcher Zahlen-/Textwert aktuell vorliegt, ob zuletzt ein Ereignisimpuls einging und ob Fehler/ungültige Referenzen bestehen. **Verbindung vorhanden ≠ Signal liegt an.**
- **Farblich codierte Signalpfade:** Die Leitungstypfarben aus 02.20 gelten unverändert. Zusätzliche Hervorhebung und Beschriftung zeigen die aktuell aktiven bzw. zuletzt durchlaufenen Pfade; allein die Farbe darf nicht die Bedeutung tragen.
- **Szenen und Arbeitsbereiche:** Live-Status und Fehlerhinweise müssen über szenenübergreifende Verbindungen (02.18/02.29), Untergraphen und die drei Ansichten (02.27) nachvollziehbar bleiben.
- **Read-only-Diagnose:** Das Ansehen von Live-Signalen, Verlauf und aktuellen Werten darf **keine** Aktionen auslösen, **keine** echten Timer anhalten und **keine** Spielobjekte verändern.

### 2. Ereignisverlauf und Ursachenanalyse

- Ein verständliches Spielleiter-Protokoll dokumentiert je beobachtetem Ausführungsschritt die auslösende Node und den Port, den betroffenen Graph-/Szenen-/Objektbezug, Zeitpunkt bzw. Spielrunde, weitergeleitete Werte, ausgewertete Bedingungen, Folgereaktionen und Fehler.
- Bei fehlgeschlagenen oder gestoppten Ketten soll der Editor den **Grund** zeigen: Bedingung falsch, Eingang nicht verbunden, falscher Porttyp, fehlende Rechte, nicht aktive Szene gemäß 02.19, gelöschte Objekt-Referenz oder durch Schleifenschutz unterbrochen.
- Einzelne Ereignisse bzw. Graphketten können im Editor wiedergefunden, gefiltert und hervorgehoben werden. **Live-Blick** und **historisches Protokoll** klar getrennt beschriften.
- Die Aufbewahrung, datenschutzkonforme Berechtigungen und Größe des Protokolls werden später detailliert geplant; verborgene Spielleiterinformationen niemals an nicht berechtigte Spieler liefern.

### 3. Isolierte Simulation mit Haltepunkten

- Der Spielleiter kann eine **Testausführung unabhängig vom laufenden Spiel** starten. Die Simulation verwendet eine gesonderte Zustandskopie bzw. isolierte Testwelt und darf reale Türen, Figuren, Inventare, Fallen, Timer, Entdeckungszustände oder Spielrunden **nicht** verändern.
- **Schrittweise verfolgen:** Die Simulation kann nach jedem Schritt angehalten und vorwärts bewegt werden. Ein aktiver Signalpfad, Eingangs-/Ausgangswerte, erfüllte/nicht erfüllte Bedingungen und geplanter Folgeeffekt werden verständlich angezeigt.
- **Breakpoints (Haltepunkte):** An einer Node oder einem Verbindungsschritt kann ein Haltepunkt gesetzt werden. Während der **Simulation** stoppt die Verarbeitung dort, sodass Werte kontrolliert werden können, bevor der nächste Schritt ausgelöst wird.
- **Fehler sichtbar machen:** Port-/Typkonflikte, fehlende Objektbindung, unerlaubte Aktion, nicht ausgelöste oder nicht erfüllte Bedingung, unbeabsichtigte Zyklen, wiederholte Ereignisse und zurückgestellte Aktionen müssen diagnostizierbar sein.
- **Echtzeit- und Rundenlogik** bleiben zwei getrennte Zeitgrundlagen (02.15–02.16). Exakte Bedienung von virtueller Zeit und virtuellen Spielrunden wird später entschieden.
- **Dieselbe fachliche Logik:** Simulation und tatsächliche Serverausführung sollen dieselben validierten Regeldefinitionen und fachlichen Prüfungen verwenden, statt durch eine oberflächliche Browseranimation voneinander abweichende Ergebnisse zu liefern. Simulationseffekte werden nicht in die reale Kampagne zurückgeschrieben.

### UX, Rechte und Qualität

- „**Live beobachten**“ und „**Simulation starten**“ sind deutlich unterschiedliche Bedienmodi. Es darf nicht unklar sein, ob der tatsächliche oder ein simulierter Iststand angezeigt wird.
- Fehler und Ursachen auch für Anfänger in **lesbaren Sätzen**, für fortgeschrittene Spielleiter zusätzlich technisch exakt und portbezogen darstellen.
- Szenen- und Kampagnen-Geheimnisse, Codewerte und Berechtigungen aus den vorigen Entscheidungen auch im Debugger schützen.
- Log- und Statusdaten nicht ungebremst sammeln; große Graphen müssen performant bleiben. Die Grenzen, Filter und Exportformate sind später zu planen.

**02.32 beschlossen:** Speicherung wiederholbarer Testfälle mit Ausgangszuständen, definierten Aktionen, Echtzeit-/Rundenschritten und Soll-Ist-Prüfungen. **Weiter offen:** Zeitpunkt automatischer Regressionstests (02.33), virtuelle Zeitführung im Detail, Protokollaufbewahrung, Breakpoint-Details, parallele Signalpfade, Export und große Graphen.

## 02.32 – Wiederholbare Node-Tests mit gespeicherten Soll-Ergebnissen (11.10.2026)

**Beschlossen: Variante C – komplette, speicherbare und wiederholbare Testszenarien mit Ausgangszuständen, Eingabefolgen, kontrolliertem Zeitverlauf und automatischem Soll-Ist-Vergleich.**

### Aufbau eines Testszenarios

- **Name und Geltungsbereich:** Der Spielleiter benennt einen Test und ordnet ihn einer Node-Schaltung, einer Gruppe/Untergraph-Vorlage, einem Arbeitsbereich oder einer übergreifenden Ereigniskette zu. Testeinstellungen und Testfälle sind persistent und versionierbar.
- **Isolierter Startzustand:** Ein Test enthält oder referenziert explizite Startwerte für relevante Türen, Schalter/Taster, Inventare, Figurenpositionen, Objektzustände, Berechtigungen, Signale und Timer. Keine unbeabsichtigte Abhängigkeit vom gerade live laufenden Spielzustand.
- **Eingabeschritte:** Der Spielleiter kann Aktionen wie Taster drücken/halten/loslassen, Schalter umlegen, Figur bewegen, Codeeingabe simulieren, Objektzustand ändern, NPC-/Questereignis auslösen oder die Aktivierung einer Szene simulieren. Nur kompatible, validierte Testaktionen zulassen.
- **Zeitsteuerung:** Echtzeit- und Rundenfortschritte sind **getrennte, kontrollierbare Eingaben**: zum Beispiel '5 simulierte Sekunden weiter' oder '2 simulierte Spielrunden weiter'. Beide Zeitbasen werden nicht stillschweigend ineinander umgerechnet.
- **Soll-Ergebnisse:** Pro Schritt oder Testende können erwartete Ausgänge, anliegende Portwerte, tatsächlich gesendete Ereignisimpulse, Objektzustände (z. B. Tür offen), Bedingungen, verbotene Aktionen und fehlende Auslösungen festgelegt werden. Auch 'darf nicht passieren' ist ein gültiger Testfall.
- **Vergleich:** Der Debugger zeigt je Prüfung **erfüllt/fehlgeschlagen**, tatsächlichen und erwarteten Wert sowie den zugehörigen Node-/Portpfad. Bei Abweichungen direkt zur betroffenen Node, Bedingung und zum relevanten Trace-Schritt springen.
- **Manuelle Tests bleiben möglich:** Zusätzlich zu gespeicherten Szenarien darf ein Spielleiter weiterhin einzelne Testsignale von Hand setzen und eine Kette Schritt für Schritt untersuchen (02.31).

### Konkretes Mehrspieler-Beispiel

**Test 'Taster hält Sicherheitstür frei':** (1) Taster ist anfangs AUS und Tür geschlossen; (2) Spieler A hält Taster -> Erwartung: Ausgang EIN und Tür freigegeben; (3) Spieler B passiert den Durchgang -> Erwartung: Bewegung erlaubt; (4) Spieler A lässt los -> Erwartung: Ausgang AUS; (5) der Test vergleicht anschließend die Türreaktion mit ihrer individuell eingestellten Regel aus 02.22/02.23. Sämtliche Figuren, Türen und Zeiten sind dabei nur simuliert.

### Wiederholung und Sicherheit

- Testszenarien können gespeichert, kopiert, erneut gestartet und **nach Änderungen an Schaltungen** erneut ausgeführt werden. Der Spielleiter sieht die Ergebnisse je Durchlauf sowie nach Möglichkeit, was sich seit dem letzten Test verändert hat.
- Der Test benutzt **dieselbe validierte fachliche Node-Auswertungslogik** wie das echte Spiel, jedoch einen **vollständig isolierten Testkontext**. Weder echte Kampagnenobjekte noch Inventare, Echtzeit-Timer, Spielrunden, Fog-of-War, Chatnachrichten oder externe Aktionen dürfen verändert werden.
- Referenzen in Tests sollen stabile Objekt-/Node-/Port-IDs verwenden und beim Kopieren von Vorlagen ausdrücklich auf Testobjekte gemappt werden. Fehlende oder umbenannte Referenzen werden verständlich angezeigt und nicht heimlich auf gleichnamige andere Objekte gebunden.
- Zufallseffekte und simultane Spieleraktionen müssen reproduzierbar testbar werden; konkrete Seed-/Ablaufsteuerung wird später festgelegt. Nichtdeterministische Ergebnisse dürfen keine irreführenden Erfolgsmeldungen erzeugen.
- Geheimnisse, private Spielleiterdaten und Testprotokolle dürfen nur berechtigten Personen zugänglich sein; Grenzen für Testdauer, Schleifen und Datenvolumen einplanen.

**02.33 beschlossen:** Testläufe pro Schaltung manuell, automatisch nach relevanten Änderungen und/oder vor Aktivierung konfigurierbar. **Weiter offen:** Sperr- oder Warnverhalten (02.34), Versionierung von Teständerungen, Zufall/gleichzeitige Ereignisse, Testfixtures, Export, Sammelberichte und Reihenfolge.

## 02.33 – Ausführungszeitpunkte gespeicherter Node-Tests (11.10.2026)

**Beschlossen: Variante C – der Spielleiter wählt pro Node-Schaltung, wann ihre gespeicherten Tests ausgeführt werden.** Die Methoden dürfen je Schaltung kombinierbar sein; es gibt keinen Zwang, jede Schaltung automatisch bei jedem Bearbeitungsschritt durchzutesten.

### Drei Testauslöser

- **Manuell:** Spielleiter können einzelne Tests oder die gesamten zugeordneten Testszenarien jederzeit gezielt starten.
- **Automatisch nach relevanten Änderungen:** Beim Speichern oder Übernehmen einer echten Änderung an der Node-Logik, Portverbindung, Parametrisierung, Objektbindung oder passenden Vorlage werden betroffene gespeicherte Tests in einem isolierten Kontext erneut geprüft. Reine Layoutaktionen (Node verschieben, Ansicht wechseln, Szenenrahmen automatisch anordnen) sollen **keinen Logiktest auslösen**. Bei schneller Änderungsfolge Tests sinnvoll bündeln, nicht nach jedem Tastendruck starten.
- **Vor Aktivierung/Freigabe:** Der Spielleiter kann für eine Schaltung eine zusätzliche Testprüfung vor dem Wirksamschalten bzw. Freigeben vorsehen. Ergebnisse sind klar sichtbar und der geprüften Version der Schaltung zugeordnet. **02.34 beschlossen:** Das Verhalten bei fehlgeschlagenen, fehlenden oder veralteten Tests hängt von der gewählten Kampagnen-/Schaltungsrichtlinie ab.

### Bedienung, Nachvollziehbarkeit und Sicherheit

- **Einstellung pro Schaltung:** Auswahl im Eigenschaften-/Testbereich des betreffenden Graphen; passende globale Standardvorgaben bei Kampagnenerstellung sind als spätere mögliche Ergänzung vorzusehen (vgl. 02.24–02.25), ohne die individuelle Steuerung abzuschaffen.
- **Ergebnisstatus:** Für die geprüfte Graph-/Vorlagenversion lesbar anzeigen: bestanden, fehlgeschlagen, noch nie ausgeführt, nach relevanter Änderung veraltet, Test läuft oder Test technisch nicht ausführbar. Eine alte erfolgreiche Prüfung darf nicht irreführend als aktuelle Freigabe angezeigt werden.
- **Betroffene Tests erkennen:** Testzuordnungen und Abhängigkeiten (Schaltung, Untergraph, Vorlage, referenziertes Objekt) nutzen; Tests anderer unabhängiger Pläne nicht unnötig starten. Bei Querverbindungen zwischen Arbeitsbereichen/Szenen die relevanten Abhängigkeiten verfolgen.
- **Ausführung ohne Nebenwirkungen:** Auch automatische und Vor-Freigabe-Prüfungen erfolgen ausschließlich in der **isolierten Simulation aus 02.31/02.32**, nie in der echten Kampagne. Keine unkontrollierten Live-Aktionen, beschädigten Inventare, ausgelösten Fallen, veränderten Timern oder blockierten Echtzeit-Spielabläufe.
- **Grenzen und Fehlersuche:** Ressourcenlimits, Abbruch, Testprotokolle, Soll-Ist-Differenzen, Zuordnung zur konkreten Graphversion sowie klare Hinweise bei fehlenden/ungültigen Testfixtures. Berechtigungsprüfung und Geheimdatenschutz bleiben bestehen.
- **Aktivierungsprüfung ist keine automatische Sicherheitsfreigabe:** Die tatsächliche Ausführung von Nodes bleibt bei allen Testmodi serverseitig validiert. **02.34 beschlossen:** Per Kampagne mit optionaler Schaltungsausnahme Warnung oder verpflichtend erfolgreicher Test; ausdrücklich erlaubte und protokollierte Übersteuerung nur für berechtigte Spielleiter. Technisch ungültige/unerlaubte Graphen bleiben unabhängig davon gesperrt.

**02.34 beschlossen:** Kampagnenstandard und optionale Schaltungsausnahmen für Warnung, Aktivierungssperre sowie separat erlaubte, protokollierte Spielleiter-Übersteuerung. **Weiter offen:** konkreter Standardwert im Kampagnenerstellungs-Assistenten, Änderungserkennung/Testbündelung, maximale Laufzeit, laufende Tests während weiterer Bearbeitung und parallele Signalkonflikte (02.35).

## 02.34 – Fehlgeschlagene Tests und Freigaberichtlinie (11.10.2026)

**Beschlossen: Variante C – bei Kampagnenerstellung global einstellbar, pro Schaltung bei Bedarf individuell überschreibbar.** Bei nicht bestandenen, fehlenden oder veralteten Testergebnissen gilt die gewählte Freigaberichtlinie.

### Richtlinie und Vererbung

- **Kampagnenstandard:** Im Bereich Kampagneneinstellungen / Spielregeln / Node-Testfreigabe (Arbeitstitel) legt ein berechtigter Spielleiter den Standard für die Kampagne fest. Eine neu angelegte Node-Schaltung übernimmt die passende Richtlinie zunächst aus dem Kampagnenprofil.
- **Abweichung pro Schaltung:** Der Spielleiter kann für eine bestimmte Schaltung oder einen wiederverwendbaren Baustein eine ausdrücklich gekennzeichnete Ausnahme konfigurieren. Eine globale Änderung darf individuelle Ausnahmen nicht stillschweigend ersetzen (02.24–02.25).
- **Warnmodus:** Tests mit fehlgeschlagenem, noch fehlendem oder veraltetem Ergebnis sind klar sichtbar, verhindern aber allein durch ihren Status nicht die Aktivierung. Eine erfolgreiche Testprüfung darf nicht vorgetäuscht werden.
- **Strenger Modus:** Für die entsprechend verpflichtenden Tests ist ein **aktuelles, erfolgreiches Ergebnis zur exakt freizugebenden Schaltungsversion** erforderlich; ansonsten wird deren Aktivierung/Freigabe abgewiesen.
- **Optionale Übersteuerung:** Der Kampagnen-/Schaltungsstandard kann ausdrücklich festlegen, ob ein **berechtigter Spielleiter** die testbedingte Sperre im Einzelfall nach Warnung bewusst übersteuern darf. Der Vorgang ist mit Identität, Zeitpunkt, Grund, Graphversion, Testergebnissen und Entscheidung nachvollziehbar zu protokollieren.

### Freigabe und technische Grenzen

- **Testzustände differenzieren:** Bestanden, fehlgeschlagen, nie ausgeführt, aufgrund von Änderungen veraltet, noch laufend oder technisch nicht ausführbar sind unterschiedliche Zustände. Der Regelmodus bestimmt, ob diese für eine Freigabe toleriert werden. Niemals einen veralteten Erfolg als neuen Erfolg anzeigen.
- **Sperre betrifft testbedingte Freigabe:** Eine ausdrücklich erlaubte Übersteuerung darf **keine fehlenden Berechtigungen, inkompatiblen Ports, kaputten Objektreferenzen, invaliden Regeldefinitionen oder sonstige unverzichtbare Sicherheitsprüfungen** umgehen.
- **Autoritativ und versionsbezogen:** Die Freigabeentscheidung muss serverseitig auf die tatsächlich aktuelle Graphversion, das gültige Regelprofil und die dazu gehörigen Testergebnisse bezogen werden. Parallel vorgenommene Änderungen dürfen nicht unbemerkt zwischen Test und Freigabe eingeschoben werden.
- **Simulation bleibt isoliert:** Die Prüfung vor Freigabe nutzt den Sandbox-Testmodus aus 02.31–02.33; kein echter Tür- oder Fallenimpuls wird beim Testen ausgelöst.
- **Bedienung:** Sichtbare Statusanzeige am Graphen (z. B. Warnung, freigabebereit, testbedingt gesperrt, übersteuert) mit nachvollziehbarer Erklärung und direktem Sprung zu fehlgeschlagenen Assertions und betroffenen Nodes. Details zu Berechtigungsebenen und Änderungs-/Audit-Aufbewahrung werden später festgelegt.

**Noch offen:** Die konkrete vorbelegte Warn-/Streng-Richtlinie bei neu erzeugten Kampagnen, wählbare Kategorien von Pflicht- und optionalen Tests, Ablauf einer Übersteuerung, mögliche Ablaufzeit einer Ausnahme und Veröffentlichung in Mehrspielergruppen. Konflikte gleichzeitiger Node-Aktionen sind ab 02.35 durch kampagnenweit vorgegebene und objektbezogen überschreibbare Regeln zu behandeln; genaue Konfliktalgorithmen bleiben eine spätere Detailplanung. Unverzichtbare Sicherheitsprüfungen gelten weiterhin.

## 02.35 – Konfliktregeln für gleichzeitig eintreffende Node-Aktionen (12.10.2026)

**Beschlossen: Variante C – Konflikte werden regelwerksneutral, serverautoritativ und konfigurierbar aufgelöst.** Der Spielleiter kann bei der **Kampagnenerstellung** globale Standards festlegen; **pro Objekt bzw. geeigneter Aktion** sind bewusst gekennzeichnete Ausnahmen möglich (Vererbungsregeln 02.24–02.25).

### Konfigurierbare Strategien

- **Eingangsreihenfolge:** Für dasselbe Ziel eintreffende, konkurrierende Befehle werden in einer eindeutig nachvollziehbaren serverseitigen Reihenfolge verarbeitet. Reihenfolge nicht allein an unzuverlässiger Browserzeit festmachen.
- **Prioritäten:** Unterschiedliche Node-Auslöser, Eingänge oder Aktionsarten können definierte Vorränge besitzen, z. B. Sicherheitssperre vor gewöhnlichem Öffnungsbefehl. **Gleichstand und spätere Wiederaufnahme** sind später genau zu spezifizieren.
- **Gegenseitige Sperre / Serialisierung:** Ein Objekt kann während einer kritischen Zustandsänderung widersprüchliche neue Aktionen vorübergehend ablehnen, zurückstellen oder gemäß später festzulegenden Regeln ausführen; keine unabsichtliche gleichzeitige Ausführung.
- **Definierte Zusammenführung:** Kompatible anliegende Signale oder Werte dürfen nach einer ausdrücklich ausgewählten Regel (z. B. boolesche UND-/ODER-Verknüpfung über geeignete Bedingungs-Nodes) zusammengeführt werden. **Event-Impulse, Boolesche Werte und Aktionsbefehle nicht stillschweigend gleichsetzen oder ohne Typprüfung vermischen.**

### Beispiel

Ein Spieler hält einen Taster, der die Tür freigeben soll. Gleichzeitig befiehlt ein Echtzeittimer der Tür, sich zu schließen. Das aktive Konfliktprofil dieser Tür entscheidet nachvollziehbar, ob Vorrang, Eingangsreihenfolge, gegenseitige Sperre oder ein definiertes Signalzusammenspiel gilt. Der tatsächliche Türzustand und die gefeuerten Ereignisausgänge ergeben sich **nur aus der erfolgreich verarbeiteten Aktion**, nicht bereits aus einem eingehenden Befehl.

### Anforderungen

- **Kampagnenstandard und Ausnahme:** Im Kampagnenassistenten ist ein Standardprofil für Konflikte vorzusehen; neue Objekte übernehmen es zunächst. Der Spielleiter kann bei einer Tür, einem Schalter, einer Falle, einem Fahrzeug oder einem anderen unterstützten Objekt gezielt einen abweichenden Modus einstellen. Änderungen der globalen Vorgabe bieten die Vorschau und Auswahl für Bestandsobjekte aus 02.25.
- **Atomare Ausführung:** Ein einziges serverautoritatives Verfahren entscheidet bei konkurrierenden Ereignissen über konsistente Objektzustände. Doppelte Netzwerkereignisse nicht mehrfach anwenden; gleichzeitige Ausführung, Rekursion und unerlaubte Aktionskombinationen absichern.
- **Gleichzeitigkeit definieren:** Bei praktisch gleichzeitigen Aktionen sind verlässliche Ereignis-IDs, Serverreihenfolge und ggf. Kampagnen-Rundenschritte zu berücksichtigen. Exakte zeitliche Konfliktfenster, Gleichstandsregeln und Warteschlangenverhalten folgen später.
- **Zusammenspiel mit 02.17/02.20/02.21:** Bedingungs-Nodes können UND/ODER/NICHT, ein Taster liefert ein anliegendes boolesches Haltesignal, und ein Schalter kann rasten. Die Konfliktpolitik **ergänzt** diese Logik, statt automatisch andere Signaltypen zu konvertieren.
- **Debugger und Tests:** Der Spielleiter sieht im Live-/Testprotokoll (02.31–02.33), welche Ereignisse konkurrierten, welche Regel griff, welche Aktion umgesetzt, unterdrückt oder verschoben wurde und warum. Gleichzeitige Testereignisse müssen in isolierten Soll-Ist-Szenarien nachvollziehbar überprüfbar sein.
- **Rechte und Sicherheitsgrenzen:** Priorität darf Zugriffs-/Sicherheitsrechte, Verriegelungsregeln, ungültige Ports und zwingende Servervalidierung nicht umgehen. Einstellungen und geheime Ausführungsdetails sind nur berechtigten Spielleitern sichtbar.

**Noch offen:** Exakte Prioritätsstufen und Tie-Breaker, Zeitfenster, Queue/Timeout, Konflikte von Impulsen gegen Dauerzustände, Zusammenführung mehrerer Halter, Konflikte von Eingaben aus mehreren Szenen und Behandlung laufender Animationen. **02.36 beschlossen:** Gleichzeitige Halter desselben Tasters werden anhand eines Kampagnenstandards mit gezielten Ausnahmen pro Taster ausgewertet; Details zum Verbindungsabbruch folgen 02.37.

## 02.36 – Gemeinsames Halten von Tastern: Kampagnenstandard und Ausnahmen (12.10.2026)

**Beschlossen: Variante C mit ausdrücklicher Erweiterung – die Regel für gleichzeitig haltende Figuren wird bereits bei der Kampagnenerstellung als globaler Standard festgelegt; jeder Taster darf eine eigene, klar erkennbare Ausnahme verwenden.**

### Konfigurierbare Mehrspieler-Modi

- **Exklusiv ein Halter:** Höchstens eine berechtigte Figur hält einen konkreten Taster gleichzeitig. Eine zweite Halteaktion wird nicht zusätzlich gezählt; die Reaktion auf einen solchen Versuch ist verständlich.
- **Mehrere Halter, mindestens einer genügt:** Mehrere berechtigte Figuren dürfen gleichzeitig halten. Das boolesche Haltesignal ist EIN, solange **mindestens eine gültige, noch laufende Halteaktion** existiert; erst wenn die letzte endet, wird AUS.
- **Einstellbare Mindestzahl N:** Ein Taster benötigt mindestens **N verschiedene berechtigte, gleichzeitig haltende Figuren** (N >= 1). Sein boolescher Ausgang ist EIN nur bei aktiver Halterzahl >= N; fällt die Zahl darunter, wird der Ausgang wieder AUS. Dies erlaubt Rätsel, bei denen z. B. zwei oder drei Figuren gemeinsam einen Mechanismus bedienen müssen.

### Globaler Standard bei der Kampagnenerstellung

- Im Kampagnenassistenten unter **Spielregeln → Umgebung / Interaktionen → Taster-Mehrspielerregel** (Arbeitstitel) setzt der Spielleiter eine Vorgabe für neu angelegte Taster; diese Regel ist **kein festes D&D-Regelwerk**.
- Bei einer einzelnen Tasterinstanz kann der Spielleiter von der Vorgabe abweichen, z. B. global „mindestens einer“ und für einen schweren Torhebel „mindestens zwei“. Die Eigenschaften zeigen eindeutig **„Kampagnenstandard“ oder „individuelle Ausnahme“** samt effektivem Modus und gegebenenfalls N.
- Änderungen globaler Vorgaben erfolgen gemäß 02.25 mit **Vorschau und Wahl**, ob nur neue oder auch bereits vorhandene, nicht individuell überschreibende Taster betroffen sind. Explizite Ausnahmen werden nicht stillschweigend verändert.
- Die Halterzahl-Regel gilt ausschließlich für den **gehaltenen Tastermodus** aus 02.22; ein rastender **Schalter** funktioniert weiterhin ohne Halten. Beide Objekt-Modi und ihre typisierten Ausgänge bleiben erhalten.

### Signalzustand, Beispiele und Serverausführung

- **Beispiel 1 – mindestens einer:** Zwei Figuren halten denselben Taster; lässt eine los, bleibt das Signal EIN, solange die andere gültig weiterhält.
- **Beispiel 2 – mindestens zwei:** Spieler A hält zunächst allein: 1/2, Ausgang AUS. Spieler B beginnt ebenfalls zu halten: 2/2, Ausgang EIN und Tür wird gemäß verknüpfter Regel freigegeben. Einer lässt los: 1/2, Ausgang AUS. Ob die Tür dann unmittelbar oder verzögert reagiert, bestimmt weiterhin das Zielobjekt nach 02.22.
- **Unterschiedliche Halter zählen:** Der Server zählt unterschiedliche, berechtigte Figuren/Halteaktionen ohne doppeltes Zählen durch dieselbe Figur, wiederholte Netzwerknachrichten oder parallele Eingabegeräte. Die genaue Regel zu Mehrfachfiguren pro Nutzer und Interaktionsreichweite bleibt gesondert zu spezifizieren.
- **Typisierte Outputs:** Der boolesche Ausgang `IstAktiv` ergibt sich aus der aktiven Halterzahl und der gewählten Schwelle; ergänzende Statuswerte/Events wie `AktiveHalterzahl`, `SchwelleErreicht` oder `SchwelleUnterschritten` sind sinnvolle Vorlagen für den späteren Portkatalog.
- **Live-Anzeige und isolierte Tests:** Der Spielleiter kann aktive Halterzahl, geforderte Mindestzahl, Haltezustand und Signalabfall beobachten. Gespeicherte Testszenarien können mehrere Spieler gleichzeitig halten und loslassen lassen, ohne die reale Kampagne zu beeinflussen.
- **Sicherheit:** Jede Halteaktion erhält eine serverseitig geprüfte Figuren-/Interaktionszuordnung; Rollen, Zugriff, Doppelanfragen und gleichzeitige Änderungen werden zuverlässig verarbeitet. Eine ungültig gewordene Halteaktion darf ein Signal nicht dauerhaft auf EIN halten. **02.37 beschlossen:** Abbruch bei Verbindungsverlust erfolgt anhand des globalen bzw. am Taster überschriebenen Sofort-/Nachfrist-Profils. Nach Fristende zählt ein abgemeldeter Halter nicht mehr.

**Mit 02.37 entschieden:** Die Kampagne hat einen Standard für Verbindungsabbrüche: Halteaktion sofort beenden oder begrenzte Echtzeit-Nachfrist erlauben, mit Objektausnahmen und serverseitiger Neubewertung der Halterzahl. **Weiter offen:** Unterbrechung beim Bewegen/Verlassen der Reichweite (02.38), mehrere Figuren pro Nutzer, Sichtbarkeit der Halter, technische Erkennung verlorener Verbindungen und Schutz vor unerreichbar hohen Mindestzahlen. Die Ziel-Türreaktion bleibt unabhängig.

## 02.37 – Verbindungsverlust beim Halten eines Tasters (12.10.2026)

**Beschlossen: Variante C – der Spielleiter kann bereits bei der Kampagnenerstellung festlegen, wie eine laufende Taster-Halteaktion bei Verbindungsabbruch behandelt wird. Einzelne Taster dürfen vom Standard abweichen.**

### Global wählbare Verbindungsabbruch-Regel

- **Sofort beenden:** Sobald der Server den Verbindungsverlust einer haltenden Figur erkannt hat, wird deren Halteaktion beendet. Ihre Figur zählt nicht mehr zur Halterzahl; `IstAktiv` wird nach den Halteschwellen aus 02.36 neu berechnet.
- **Begrenzte Wiederverbindungsfrist:** Statt sofort zu lösen, darf eine Figur für eine **vorher konfigurierte, endliche Echtzeitdauer** als vorübergehend gehalten gelten. Nach Ablauf endet diese Halteaktion serverseitig sicher und die Mindesthalterzahl wird erneut bewertet. Eine unendliche Frist ist **nicht** vorgesehen.
- **Wiederverbinden:** Verbindet sich derselbe berechtigte Spieler rechtzeitig erneut, wird die bestehende Halteaktion nach Prüfung der Figur-/Sitzungszuordnung und aktuellen Objektbedingungen fortgeführt, **ohne doppelt zu zählen**. Ein anderer Spieler darf die Halteaktion nicht durch bloßes Nachahmen einer Clientnachricht übernehmen.
- **Kampagnenstandards und Tasterausnahmen:** Der globale Modus und die gegebenenfalls erlaubte Frist gelten für neu angelegte Taster; an jedem konkreten Taster kann der Spielleiter den Modus und die Frist ausdrücklich ändern. Die UI zeigt die Herkunft der wirksamen Einstellung. Spätere Änderungen am Kampagnenstandard folgen der Vorschau-/Bestandsschutzregel 02.25.

### Mehrspieler-Schaltung und Node-Zustand

- **Mehrere Halter:** Für N=2 zählen während einer erlaubten Nachfrist die gültigen bzw. befristet aufrechterhaltenen Halteaktionen nach der Regel der jeweiligen Tasterinstanz. Scheidet ein Halter endgültig aus und sinkt die Halterzahl unter N, fällt das anliegende boolesche Signal auf AUS. Weitere, noch verbundene Spieler halten weiterhin unabhängig.
- **Klare Statusanzeige:** Live-Debugger, Objekt-Eigenschaften und isolierte Tests können `Verbunden/Hält`, `Verbindung unterbrochen – Frist läuft` und `Halteaktion beendet` unterscheiden; aktiver Halterstand, erforderliches N und gegebenenfalls Restfrist sind nachvollziehbar. Nicht als echte Spielerpräsenz ausgeben, wenn nur eine Nachfrist läuft.
- **Türreaktion bleibt getrennt:** Sobald der Tasterausgang auf AUS wechselt, entscheidet wie bisher die **Konfiguration der Ziel-Tür** aus 02.22 (sofort zurückstellen, offen bleiben, verzögert) über die Wirkung. Der Verbindungsabbruch erhält keine eigene versteckte Tür-Sonderregel.
- **Isolierte Tests:** Einen Disconnect, eine Wiederverbindung innerhalb/außerhalb der Frist, den Ablauf einer Nachfrist und den Wechsel des Schwellenwerts (z. B. 2/2 -> 1/2) als speicherbare Tests aus 02.32 unterstützen.

### Serverseitige Absicherung und offene Implementierungsdetails

- Server ist allein für den echten Zeitpunkt der **erkannten** Unterbrechung, den Zeitablauf der Nachfrist, deren Aufhebung und den Signalwechsel verantwortlich. Die Frist folgt **Echtzeit**, nicht automatisch Spielrunden, und wird unabhängig von Client-Timern ermittelt.
- Abbruch-/Wiederaufnahmeereignisse benötigen eindeutige IDs, damit wiederholte Netzwerkpakete und neue Browser-Verbindungen weder zusätzliche Halter noch ein dauerhaftes EIN erzeugen.
- **Sicherheit:** Bei widerrufener Berechtigung, zerstörtem Taster, ungültigem Haltezustand oder anderer zwingender Spielregel darf eine Frist keine ungültige Aktion künstlich fortsetzen. Diese Prüfungen stehen über einer Verbindungsabbruch-Komfortregel.
- Die exakte Verbindungsverlust-Erkennung (Heartbeat/Timeout), die konkrete maximale Nachfrist, die Persistenz eines offenen Grace-Timers bei Serverneustart und das Verhalten bei pausierter Kampagne bleiben zur technischen Detailplanung offen.

## 02.38 – Bewegung und andere Aktionen beim Halten eines Tasters (12.10.2026)

**Beschlossen: Variante C – bei der Kampagnenerstellung zentral konfigurierbar, mit individuellen Ausnahmen an einzelnen Tastern.**

- **Bewegung:** Der Spielleiter legt fest, ob die haltende Figur während einer gültigen Halteaktion stillstehen muss oder sich bewegen darf. Wenn das Bewegen das Halten aufhebt, wird die Halteaktion serverseitig beendet; ob unzulässige Bewegungen alternativ abgewiesen werden, wird später separat entschieden.
- **Interaktionsdistanz:** Ein ortsfester Taster kann eine begrenzte Reichweite erfordern, während ein tragbarer oder fernbedienbarer Taster eigene Reichweitenregeln haben kann. Die genauen Distanzregeln folgen in 02.39.
- **Zusätzliche Handlungen:** Der Kampagnenstandard und mögliche Tasterausnahmen legen fest, welche weiteren Figurenaktionen parallel erlaubt sind oder das Halten unterbrechen, beispielsweise Sprechen, Inventarbenutzung, Angreifen oder Gegenstände verwenden. Das aktive Regelprofil bestimmt verfügbare Aktionen.
- **Figurenzustände:** Regeln können eine Halteaktion bei passenden Zustandswechseln wie Handlungsunfähigkeit oder Bewusstlosigkeit beenden. Es gibt keine fest eingebaute D&D-spezifische Statusliste; die Zustände stammen gegebenenfalls aus dem Regelprofil.
- **Globale Voreinstellung und Ausnahmen:** Neue Taster übernehmen den Kampagnenstandard; der Spielleiter darf einzelne Eigenschaften je Taster sichtbar überschreiben. Änderungen des globalen Standards folgen 02.25: Vorschau, Wahl nur für neue oder auch bestehende Standardobjekte, Schutz individueller Ausnahmen.
- **Schalter bleiben separat:** Ein rastender Schalter erfordert kein aktives Halten (02.22). Die Halterzahlregel (02.36) und Wiederverbindungsfrist (02.37) bleiben unabhängige Konfigurationen.
- **Signalaktualisierung:** Wenn eine Halteaktion endet, berechnet der Server die aktiven Halter (02.36) und den booleschen Ausgang neu. Das angeschlossene Objekt reagiert gemäß seinen eigenen Signalverlustregeln aus 02.22.
- **Testbarkeit:** Live-Debugger und isolierte Tests sollen anzeigen, ob eine Bewegung, Reichweitenüberschreitung, verbotene Aktion oder ein relevanter Figurenzustand die Halteaktion beendete. Bei mehreren Spielern wird ausschließlich der betroffene Halter entfernt; doppelte Clientereignisse dürfen nicht doppelt wirken.

**Mit 02.39 entschieden:** Standard-Interaktionsreichweite und zugehörige Distanzmessung werden bei Kampagnenerstellung festgelegt, mit individuell markierten Abweichungen. Präsenz- und Bewegungsmelder sind zusätzlich als eigene Node-fähige Objekttypen vorgesehen; Erfassungsbereich und manuelle Bedienreichweite bleiben getrennte Eigenschaften. **Weiter offen:** Exakte Formeln/Skalen der Distanzmessung, Maus-/Tastatur-/Touch-Bedienung, Bewegung zurückweisen oder Halten beenden, Zustandskatalog und Besonderheiten tragbarer/Fahrzeugauslöser.

## 02.39 – Interaktionsreichweiten und Präsenz-/Bewegungsmelder (12.10.2026)

**Beschlossen: Variante C – die Standardreichweite und Distanzmessung für Schalter/Taster werden zentral bei der Kampagnenerstellung festgelegt; jedes Objekt kann eine eigene Ausnahme verwenden. Zusätzliche ausdrückliche Anforderung: Platzierbare Präsenzmelder und Bewegungsmelder sind als eigene Node-fähige Szenenobjekte vorzusehen.**

### 1. Bedienreichweite von Schaltern und Tastern

- **Kampagnenweiter Standard:** Der Spielleiter wählt eine Standard-Bedienreichweite und die passende Distanzmessregel. Die Skalierung muss zum Raster/maßstabsfreien/Hex-/Quadrat-Szenenmodell aus 02.4 passen und darf kein D&D-festes Feldmaß voraussetzen. Die konkrete Berechnungsformel bleibt offen.
- **Individuelle Objektausnahmen:** Ein Wandtaster kann Berührung erfordern, ein Schaltpult aus geringer Distanz bedienbar sein und ein Funkschalter eine abweichende Reichweite oder andere Interaktionsvoraussetzungen besitzen. Die wirksame Einstellung und ihre Herkunft (Kampagnenstandard/Objektausnahme) sind deutlich sichtbar.
- **Start und Halten getrennt prüfen:** Der Server validiert die zulässige Distanz beim Betätigen und bei einem gehaltenen Taster regelmäßig bzw. bei relevanter Bewegung. Wird die Haltebedingung ungültig, endet die Halteaktion nach 02.38 und Halterzahl/Signal werden neu berechnet.
- **Globale Änderungen:** Bei Änderung eines Standards greift die Vorschau-/Bestandsobjekt-/Ausnahmeregel aus 02.25. Bestehende bewusst gesetzte Ausnahmen werden nicht ohne Zustimmung überschrieben.

### 2. Interaktive Sensoren als Szenen- und Node-Objekte

- **Präsenzmelder:** Erkennt, ob mindestens ein zulässiges Ziel **im eingestellten Erfassungsbereich vorhanden** ist, unabhängig davon, ob das Ziel sich gerade bewegt. Ein typischer **boolescher Zustandsausgang** `Präsenz = EIN/AUS` ist aktiv, solange die definierte Präsenzbedingung zutrifft. Zusätzliche Ereignisausgänge wie `Bereich betreten` / `Bereich verlassen` sind vorgesehen.
- **Bewegungsmelder:** Erkennt **Bewegung eines zulässigen Ziels im Erfassungsbereich**; im Unterschied zum Präsenzmelder ist eine stillstehende Figur nicht allein wegen ihrer Anwesenheit ein Bewegungstreffer. Typischer **Ereignisausgang** `Bewegung erkannt`, mögliche kontinuierliche Bewegungsstatuswerte und Auslöse-/Rücksetzzeiten werden später detailliert entschieden.
- **Beim Platzieren benennbar:** Etwa `Präsenzmelder – Labor – Eingang Nord` oder `Bewegungsmelder – Hangar – Tor 3`. Beide gehören als eigenständige Objekttypen in die Karten-/Szenenbibliothek und liefern automatisch passende, typisierte **Ein-/Ausgangsports** für den bereits beschlossenen visuellen Node-Editor (02.17/02.20). Konkrete Ports und Sensoreinstellungen bleiben erweiterbar.
- **Auslöseketten:** Ein Präsenzmelder kann das Licht solange einschalten, wie sich eine Figur im Raum aufhält; ein Bewegungsmelder kann beim Vorbeilaufen einen Alarm oder Timer auslösen. Beide lassen sich mit Bedingungen, Inverter-Nodes, Echtzeit-/Rundenregeln und kampagnenweiten Schaltungen kombinieren.
- **Erfassungsbereich getrennt von Bedienreichweite:** Die **Reichweite, Form und Orientierung der Sensorzone** sind eigene Objekteigenschaften und nicht automatisch die Reichweite zum manuellen Bedienen dieses Sensors. Globale Erfassungsstandards mit gezielten Objekt-Ausnahmen sollen im Kampagnenassistenten vorbereitet werden; genaue Zonenformen, Sicht-/Wandblockade und Reichweitenberechnung folgen später.
- **Konfigurierbare Sensorziele:** Welche Figur-, NPC-, Tier-, Fahrzeug- oder sonstigen Objektarten ein Sensor erkennt, wie Sensitivität/Filter funktionieren und ob Verstecken/Sichtblockaden die Erkennung ändern, bleibt für 02.40 und weitere Detailentscheidungen offen. Keine pauschale Erkennung sämtlicher versteckter Objekte oder Figuren annehmen.

### 3. Serverlogik, Geheimnisschutz und Debugging

- Sensoren lesen **serverautoritär ausgewertete Szenenpositionen, Bewegung und zutreffende Zielkategorien**; nicht allein die gezeichnete Browserposition oder die Clientmeldung. Szenen-/Stockwerkszuordnung, Rasteroptionen und relevante Berechtigungen berücksichtigen.
- Die Sensorzone darf in der Spielleiteransicht sichtbar und bearbeitbar sein, auch wenn der Sensor bzw. seine Regeln für Spieler verborgen bleiben. **Sensorauslösung bedeutet nicht automatisch, dass die ausgelöste Figur durch Fog-of-War sichtbar wird** oder dass geheime Entitäten an nicht berechtigte Clients gesendet werden.
- Im Node-Testmodus sind Zustand/Impuls und erkannte Wechsel nachvollziehbar. Isolierte Tests sollen `Figur betritt Zone`, `Figur bleibt stehen`, `Figur bewegt sich innerhalb` und `Figur verlässt Zone` einschließlich mehrerer Figuren und Spielrunden/Echtzeit prüfen können. Ein simulierter Alarm darf niemals im realen Spiel aktiviert werden.
- Sensoren dürfen kein fest vorprogrammiertes Schaltziel benötigen, sondern ihre typisierten Ausgänge über dieselben farbig codierten Node-Leitungen und Bedingungen an beliebige berechtigte Reaktions-Nodes liefern.

**Noch offen:** Zielklassen und Filter (02.40), genaue Sensorzone (Kreis/Rechteck/Sichtkegel), Messskala, Wände/Hindernisse, Sichtlinie, Sensitivität, kontinuierliche Bewegung versus Einzelimpuls, Rücksetzen/Wiederholen, größere Sensorzahlen und Performance.

### Ergänzung zu 02.39 – Settingabhängige Kameras, Rauchmelder und erweiterbare Sensorarten (12.10.2026)

**Ausdrückliche Nutzeranforderung:** Neben Präsenz- und Bewegungsmeldern können je nach **Kampagnensetting** auch **Kameras, Rauchmelder und weitere passende Sensoren** eingesetzt werden. Das Sensor-/Node-System darf deshalb nicht auf nur zwei fest verdrahtete Gerätetypen beschränkt werden.

- **Kamera / Überwachungskamera:** Platzierbares und benennbares Szenenobjekt mit **Blickfeld bzw. Erfassungszone**, Ausrichtung und für das Setting/Modul geeigneten Erkennungsarten. Mögliche typisierte Node-Ausgänge: `Ziel erkannt`, `Bewegung erkannt`, `Alarm` oder `Kamera aktiv`. Ob Kameras zusätzlich eine aufrufbare simulierte In-Game-Sicht/Kameraansicht oder Aufzeichnungen liefern, ist eine **gesonderte spätere Entscheidung**; keine reale Video-Hardware oder Videostreamingpflicht wird vorausgesetzt.
- **Rauchmelder:** Platzierbares, benennbares Szenenobjekt, das auf den **serverseitig modellierten Rauch-/Gefahrenzustand** seiner Erfassungszone reagiert. Mögliche Node-Ausgänge: `Rauch erkannt` als Ereignis und `Rauchalarm aktiv` als boolescher Zustand. Der Melder darf nicht voraussetzen, dass bereits eine globale Rauchsimulation existiert; passende Umweltzustände/Regelmodule oder ausdrücklich gesetzte Story-/Node-Werte müssen als Datenquelle vorgesehen werden.
- **Weitere Sensorfamilien je Setting:** Erweiterbare Vorlagen statt einer endgültig geschlossenen Liste, z. B. Temperatur-/Hitze-, Gas-, Licht-, Geräusch-, Laser-/Lichtschranken- oder magische Detektoren als **mögliche** spätere Typen. Nicht alle Beispiele sind bereits als einzelne konkrete Funktionen vollständig entschieden; die Fähigkeit zum Erweitern ist die Produktvorgabe.
- **Setting-/Kampagnenbibliothek:** Die für den Spielleiter angebotenen Sensorvorlagen sollen sich nach Genre/Regelprofil/Kampagnenauswahl sinnvoll filtern oder freischalten lassen. Fantasy-Szenen können andere Vorlagen verwenden als Science-Fiction- oder Cyberpunk-Szenen, ohne separate Event-Engines zu brauchen.
- **Gemeinsame Infrastruktur:** Sensorobjekte haben stabile IDs, Szenenzuordnung, Objektnamen, passende typisierte Eingänge/Ausgänge, kampagnenweite Verbindungen, farbcodierte Leitungen und Live-Istwerte im Test-/Debugmodus. Sensor-**Erfassungsbereich**, relevante Ziel-/Umweltmerkmale, Empfindlichkeit/Schwellenwert, Aktiviert/Deaktiviert und etwaige Hindernis-/Sichtregeln sind je nach Sensorfähigkeit konfigurierbar; genauer Portkatalog und Geometrie folgen später.
- **Unterschiedliche Datenquellen:** Kameras, Präsenzmelder und Bewegungsmelder können Position, Bewegung und Sichtbedingungen auswerten; Rauchmelder dagegen **Umwelt-/Gefahrenzustände**. Diese Arten von Eingaben dürfen nicht als dieselbe Figurenerkennungslogik behandelt werden.
- **Kampagnenstandards und Ausnahmen:** Sinnvolle Vorlagen und Defaultparameter bei Kampagnenerstellung vorsehen, mit gezielten Abweichungen pro Sensor und Bestandsänderungs-/Ausnahmeregeln nach 02.24–02.25.
- **Sicht- und Geheimnisschutz:** Eine Kamera- oder Melderauslösung berechtigt nicht automatisch zur Offenlegung geheimer Figuren, Szenen, Sensoren oder der überwachten Bereiche. Simulierte Sensorreaktionen bleiben im isolierten Node-Test ohne reale Alarm- oder Spielwirkungen.
- **Abgrenzung:** Gemeint sind zunächst **virtuelle Kampagnenobjekte**. Schnittstellen zu physischen Kameras oder Rauchmeldern sind weder vorausgesetzt noch beschlossen.

**Mit 02.40 entschieden:** Sensorfähigkeiten bestimmen die erlaubten, frei kombinierbaren Ziel-/Merkmals-/Fraktions-/Umweltfilter und Schwellenwerte; globale Kampagnenstandards mit bewusst gesetzten Objektausnahmen. **Weiter offen:** Erfassungsgeometrie (02.41), Wände/Sichtlinie/Licht, konkrete Schwellen-/Einheitenprofile, Alarm-Rücksetzung, Kamerasichten/Aufzeichnungen, virtuelle Umweltmodellierung, zusätzliche Sensortypen und Umsetzung.

## 02.40 – Frei konfigurierbare Sensorfilter (12.10.2026)

**Beschlossen: Variante C – Sensoren erhalten frei konfigurierbare, aber zu ihren Fähigkeiten passende Erkennungsfilter. Die Kampagnenerstellung bietet globale Standards; ein einzelner Sensor kann davon ausdrücklich abweichen.**

### Filter abhängig von der Sensorart

- **Präsenzmelder:** Geeignete Zielarten auswählen, z. B. Spielerfiguren, NPCs/Kreaturen, Tiere, Fahrzeuge, Gegenstände oder weitere durch das Regel-/Szenenmodell beschriebene Entitäten. Präsenz bedeutet weiterhin „geeignetes Ziel befindet sich im Bereich“, auch wenn es stillsteht.
- **Bewegungsmelder:** Filter für Zielarten und Bewegung; nur passende Bewegungsereignisse auswerten. Stillstehende Anwesenheit allein ist kein Bewegungsereignis.
- **Kameras:** Zu ihren Sicht-/Erkennungsfähigkeiten passende Kriterien, z. B. ausgewählte Figuren, Fraktionen, Charakter-/Objekt-Tags, definierte Zustände oder Bewegung innerhalb des Blickfeldes. Ob eine Kamera tatsächliche eigene Aufnahmen/Bilder liefert, wird getrennt geplant.
- **Rauch- und weitere Umweltmelder:** Passende, vorhandene **Umweltwerte oder Gefahrzustände** auswählen und mit Vergleichs-/Schwellwerten verknüpfen, z. B. Rauchwert über einem einstellbaren Schwellwert oder Hitze-/Gasalarm. Ein Rauchmelder benötigt eine **gültige Datenquelle** (Umweltmodul, Story-/SL-Zustand oder erlaubte Node-Eingabe), nicht eine vorausgesetzte globale Physiksimulation.
- **Weitere settingabhängige Sensoren:** Die Sensorfamilien sind erweiterbar; konkrete Datentypen und erlaubte Vergleichsmöglichkeiten stammen aus ihren versionierten Fähigkeiten-/Portvorlagen. Unpassende Filter wie „Rauchkonzentration“ für einen gewöhnlichen Präsenzmelder dürfen ohne passendes Erweiterungsmodul nicht frei erfunden werden.

### Logik, Kampagnenstandards und Ausnahmen

- **Mehrere passende Bedingungen:** Filter lassen sich mit den beschlossenen **UND/ODER/NICHT-Gruppen aus 02.17** und den zulässigen typspezifischen Vergleichen kombinieren. Beispiel Kamera: `(Zielart Spielerfigur UND Fraktion feindlich) ODER Ziel-Tag Eindringling`.
- **Voreinstellungen bei Kampagnenerstellung:** Sensortypen erhalten passende Standardfilter, Zielgruppen und wo sinnvoll Schwellenwerte aus dem Kampagnen- bzw. Genreprofil. Neue Sensoren übernehmen diese Voreinstellungen.
- **Pro Sensor gezielt abweichen:** Jedes Objekt kann eigene Zielkategorien, Tags, Bedingungen oder Schwellen festlegen, klar als **Kampagnenstandard** oder **individuelle Ausnahme** gekennzeichnet. Änderungen an globalen Regeln mit Vorschau, Altbestand-Auswahl und Ausnahmeschutz nach 02.25.
- **Eindeutige Portausgabe:** Sensoren geben entsprechend ihrem Typ anliegende Zustandswerte, Zahlenwerte und/oder Ereignisimpulse über typisierte Ports aus. Ein Ausgang wird nur aktiviert, wenn die Erkennungsbedingungen tatsächlich erfüllt wurden; „Kabel verbunden“ heißt weiterhin nicht „Signal erkannt“.
- **Serverautorität und Berechtigungen:** Der Server wertet gültige Positionen, Entitätstags/-zustände oder die tatsächlich vorhandenen Umweltwerte aus. Versteckte Sensoren und Zielinformationen dürfen durch Filterresultate, Node-Logs oder Kameras nicht an unberechtigte Spieler gelangen.
- **Einfach und fortgeschritten:** Filtervorlagen mit verständlicher Auswahl für Anfänger, frei kombinierbare Bedingungsgruppen und Node-Logik für Fortgeschrittene, ohne unkontrolliert ausführbare Skripte. Falsche Kombinationen oder fehlende Datenquellen werden erklärt.
- **Testbarkeit:** Der isolierte Debugger kann Ziele mit verschiedenen Kategorien/Tags, Bewegungswechsel, Fraktionen sowie eine veränderte Rauch-/Umweltgröße simulieren und das tatsächliche Filterergebnis mit der erwarteten Auslösung vergleichen. Die Liveansicht zeigt Signal und Filterentscheidung nur berechtigten Spielleitern.

**Abgrenzung:** Dieses Feature beschreibt virtuelle Objekte einer Kampagne, keine Überwachung realer Personen oder Anbindung realer Kameras/Rauchmelder. Eine vorgegebene Kamera-Aufzeichnung, echte Rauchphysik oder eine fest verdrahtete Liste zusätzlicher Sensoren wird hier nicht beschlossen.

**Mit 02.41 entschieden:** Sensorzonen mit Kreis, Rechteck, Sichtkegel oder frei zeichnbarem Polygon direkt im Karteneditor bearbeiten; Sichtbarkeit der Zonen wird als Kampagnenstandard mit gezielten Sensor-Ausnahmen gespeichert. **Weiter offen:** Sichtlinien-/Wand- und Lichtblockaden (02.42), genaue Stockwerks-/Geometrie- und Schwellenregeln, mehrstufige Alarme, Rücksetzzeiten, Kameraansichten und Umweltmodule.

## 02.41 – Flexible Sensorzonen und global steuerbare Sichtbarkeit (12.10.2026)

**Beschlossen: Variante C – Sensoren unterstützen Kreis, Rechteck, gerichteten Sichtkegel und frei gezeichnete Polygone. Zusätzliche ausdrückliche Produktanforderung: Die Sichtbarkeit der Sensor-Erfassungsbereiche wird bei der Kampagnenerstellung global festgelegt, mit bewussten Ausnahmen für einzelne Sensoren.**

### Formen und Bearbeitung im Karteneditor

- **Standardformen:** Kreis mit Radius, Rechteck mit Maßen/Drehung, Sichtkegel mit Richtung/Öffnungswinkel/Reichweite sowie frei gezeichnete **Polygonzonen** mit veränderbaren Eckpunkten.
- **Direkt im Karteneditor:** Der Spielleiter kann eine Zone aufziehen/zeichnen, verschieben, skalieren, drehen und später an Griffpunkten bearbeiten. Die Darstellung von Grenzen und Flächen soll bei Zoom und unterschiedlichen Kartenmaßstäben verständlich bleiben.
- **Objektgebundene Erfassung:** Die Zone gehört zu einer stabil identifizierten Kamera, einem Präsenz-/Bewegungs-, Rauch- oder sonstigen Sensor. Sie kann je Sensortyp eine geeignete vorgegebene Form erhalten und am Objekt bewusst überschrieben werden. Ob Zone und Sensor beim Verschieben automatisch gekoppelt bleiben, ist bei der Detailumsetzung zu klären; die Objektzuordnung darf dabei nicht verloren gehen.
- **Eine gemeinsame Sensorlogik:** Der Server verwendet die gespeicherte **logische Geometrie** und Szenen-/Stockwerkszuordnung zur Ermittlung der tatsächlichen Erfassung. Eine gezeichnete Markierung ist nur eine Visualisierung, niemals die alleinige Grundlage der Spiellogik.
- **Validierung:** Unsinnige Maße, ungültige/selbstschneidende Polygone und nicht zuordenbare Karten-/Stockwerksbezüge müssen erkannt werden; die konkrete Flächen-, Koordinaten- und Höhenberechnung bleibt für die technische Planung offen.
- **Nicht automatisch durch Wände hindurch:** In dieser Entscheidung wird **noch nicht** festgelegt, wie Mauern, Fenster, Türen oder Sicht-/Lichtbedingungen eine Zone begrenzen. Das folgt in 02.42.

### Sichtbarkeit der Sensorzonen – globaler Standard mit Ausnahmen

- **Kampagnenerstellung:** Der Spielleiter bestimmt eine zentrale **Sichtbarkeitsrichtlinie für Sensor-Erfassungsbereiche**, statt bei jedem Sensor dieselbe Sichtbarkeit erneut einzustellen. Mögliche Freigaben sind **nur für berechtigte Spielleiter** oder zusätzlich **für freigegebene Spieler bzw. Gruppen** sichtbar; welche feingranularen Freigaben als Oberfläche verfügbar sind, wird später im Berechtigungs- und Sichtbarkeitsdesign präzisiert.
- **Ausnahme je Sensor:** Ein einzelner Präsenzmelder, Rauchmelder oder eine Kamera darf von diesem Standard abweichen. Die Objekt-Eigenschaften zeigen klar „Kampagnenstandard“ oder „individuelle Ausnahme“ und den **wirksamen** Sichtbarkeitsstatus.
- **Änderung späterer Standards:** Globale Anpassungen folgen 02.25: Vorschau der betroffenen Zonen, wahlweise nur neue Sensoren oder zusätzlich bestehende Sensoren ohne Ausnahme; gezielte Ausnahmen bleiben geschützt.
- **SL-Editorvorschau separat:** Berechtigte Spielleiter können die Zonen beim Bearbeiten und Debuggen einblenden, um Form, Ausrichtung, Reichweite und Auslösungen zu prüfen. Diese **Editoranzeige ist nicht gleich Spielerfreigabe**.
- **Geheimnisschutz:** Für Spieler nicht freigegebene Bereiche, verborgene Kameras/Sensoren und interne Erkennungsdaten dürfen nicht bloß unsichtbar gezeichnet werden; der Server liefert nicht berechtigten Clients diese Zone/Metadaten gar nicht. Spielerfreigabe einer Zone ist außerdem **getrennt von der Sichtbarkeit des Sensorgehäuses, von Fog-of-War, von Figurenpositionen und von der Sensor-Aktivität**. Eine sichtbare Zone darf keine versteckten Figuren automatisch enthüllen.
- **Sichtbar heißt nicht aktiv:** Die Visualisierung der Erfassungsfläche und der aktuelle Erkennungszustand/Impuls sind getrennte Größen. Live-Iststand und isolierter Simulationstest aus 02.20/02.31–02.32 bleiben funktionsfähig, auch wenn Spieler die Zone nicht sehen dürfen.

### Beispiele

- Eine Überwachungskamera nutzt einen gedrehten Sichtkegel, dessen Grenze Spieler je nach Kampagnenrichtlinie erkennen oder nicht erkennen können.
- Ein Präsenzmelder in einem unregelmäßig geschnittenen Raum nutzt eine Polygonzone, die der Spielleiter direkt auf der Karte anlegt.
- Ein Rauchmelder hat einen rechteckigen oder polygonalen Erfassungsbereich; seine Rauch-Erkennung setzt weiterhin eine reale Datenquelle innerhalb der Spielsimulation voraus.
- Eine geheime Falle verwendet eine **nur für Spielleiter sichtbare** Sensorzone als bewusste Ausnahme, auch wenn andere, öffentlich angekündigte Gefahrenzonen für die Spieler eingeblendet werden.

**Mit 02.42 entschieden:** Hindernisse wirken abhängig vom Sensortyp – unabhängig von Hindernissen, per Sichtlinie oder nach definierten Durchdringungs-/Blockaderegeln; Kampagnenstandards und Sensorausnahmen. **Weiter offen:** Erfassung über mehrere Stockwerke, konkrete Licht-/Dunkelheitseinflüsse (02.43), feingranulare Spieler-/Gruppenfreigabe, Darstellungsstil, bewegliche Sensorzonen und Umweltwerte.

## 02.42 – Wände, Türen und Hindernisse bei Sensoren (12.10.2026)

**Beschlossen: Variante C – je Sensortyp konfigurierbare Hindernisprüfung mit globalen Kampagnenstandards und individuellen Ausnahmen pro Sensor.**

### Drei grundlegende Erfassungsstrategien

- **Hindernisunabhängig:** Ein entsprechend befähigter Sensor wertet passende Ziele innerhalb seiner Erfassungszone aus, ohne Wände bzw. Türen als pauschalen Ausschluss zu behandeln. Diese Fähigkeit muss bewusst zum Sensortyp bzw. Regelmodul passen.
- **Sichtlinienabhängig:** Kameras und andere optische Sensoren können eine freie Sichtverbindung zwischen Sensor und Ziel voraussetzen. Undurchsichtige, sichtblockierende Wände und entsprechend geschlossene Türen verhindern die Erkennung; offene Türen können die Sicht freigeben. Ob Fenster durchsichtig sind, folgt ihren bestehenden individuellen Sichtblockade-Eigenschaften (02.9).
- **Eigene sensorabhängige Hindernis-/Materialregeln:** Bestimmte Sensoren können Materialien oder Objektarten unterschiedlich behandeln, z. B. ein magischer, thermischer oder ein anderer spezieller Detektor, der ausgewählte Barrieren durchdringen darf. Konkrete Durchdringungsfähigkeit und Materialkatalog sind später pro Sensortyp/Modul zu spezifizieren; keine universelle Durchdringung annehmen.

### Kampagnenstandards, konkrete Sensoren und Änderungen

- **Globaler Standard bei der Kampagnenerstellung:** Für unterstützte Sensorfamilien werden geeignete Standard-Hindernisprofile festgelegt; beispielsweise bei normalen optischen Kameras Sichtlinienprüfung. Diese globale Vorgabe darf keine technischen Fähigkeiten an einen Sensor erfinden, der sie nicht besitzt.
- **Individuelle Ausnahmen:** Ein einzelner Sensor darf – innerhalb seiner tatsächlich verfügbaren Fähigkeiten – vom Kampagnenstandard abweichende, sichtbar markierte Hindernis-/Durchdringungsregeln nutzen. Änderungen globaler Regeln folgen 02.25 mit Vorschau, Bestandsschutz und Schutz eigener Ausnahmen.
- **Bestehende Hindernis-Komponenten wiederverwenden:** Die Sicht-, Licht- und Bewegungsblockade von Wänden, Türen und Fenstern aus 02.9 sind **getrennte Eigenschaften**. Eine bewegungsblockierende, aber sichtdurchlässige Glasscheibe verhindert nicht schon allein deshalb eine optische Sichtlinie. Ein spezieller Sensor kann ein anderes Blockadeprofil verwenden.
- **Dynamische Neuauswertung:** Tür öffnen/schließen, Hindernis verändern/zerstören oder einen Sensor bzw. ein Ziel bewegen kann die tatsächlich erfassten Ziele verändern. Der Server muss die betroffenen Erkennungszustände konsistent neu ermitteln, ohne allein einem Client zu vertrauen.
- **Rauchmelder und Umweltwerte:** Ein Rauchmelder prüft einen gültigen Rauch-/Gefahrenwert in seiner Zone, nicht einfach die Sichtlinie zu einer Figur. Ob und wie Rauch durch Türen, Fenster oder Öffnungen strömt, ist Sache eines gesondert zu definierenden Umwelt-/Ausbreitungsmodells und **nicht** automatisch durch diese Entscheidung festgelegt.
- **Stockwerke:** Wände, Sensoren und Ziele dürfen nicht ohne nachvollziehbare Regeln über Stockwerksgrenzen hinweg gemischt werden; vertikale Reichweiten, Treppenöffnungen und durchdringende Sensoren über mehrere Ebenen bleiben gesondert offen.

### Editor, Signale und Sicherheit

- **Sensorzone ≠ wirksame Erfassungsfläche:** Die gezeichnete Zone aus 02.41 ist zunächst der geometrische Suchbereich. Abhängig von Hindernisregeln kann der **tatsächlich erfasste Teil** kleiner sein. Im Spielleiter-Editor/Testmodus sollen Hindernis- und Sichtlinien-Blockaden sowie Gründe für Treffer/Nicht-Treffer nachvollziehbar angezeigt werden.
- **Typisierte Node-Ports:** Detektionszustände und Ereignisimpulse bleiben wie in 02.20/02.21 unterscheidbar und können in allen Ansichten an Alarm, Licht, Tür oder Storylogik weitergegeben werden. Eine blockierte Erkennung darf kein erfolgreiches „Ziel erkannt“-Ereignis erzeugen.
- **Geheimnisschutz:** Selbst eine bewusst durchdringende Kamera/Sensorregel hebt niemals automatisch Fog-of-War oder Spielerrechte auf; verborgene Sensoren, Zonen, Ziele und interne Erkennungswerte nur an berechtigte Clients übertragen.
- **Isolierte Tests:** Hindernis öffnen/schließen, Glasfenster, undurchsichtige Wand, sensorabhängige Durchdringung und geänderte Zonen lassen sich im Debugger mit Soll-/Ist-Prüfung testen, ohne echte Spielszenen zu verändern.

**Mit 02.43 entschieden:** Je Sensortyp abhängige Licht-/Dunkelheitsprüfung, darunter normale Kameras, Nachtsicht, Wärmebild und nichtoptische Sensoren; Kampagnenstandards mit Objektausnahmen. **Weiter offen:** Material-/Sensortyp-Matrix, Hindernisgeometrie, Stockwerke, konkrete Lichtskala/Spezialoptik-Profile, Wahrnehmungsalgorithmus, Geräusch-/Rauch-Ausbreitung sowie Auslöse- und Rücksetzverhalten (02.44).

## 02.43 – Licht und Dunkelheit bei Sensoren (12.10.2026)

**Beschlossen: Variante C – die Lichtabhängigkeit wird je Sensortyp beziehungsweise Sensormodul frei innerhalb seiner zulässigen Fähigkeiten konfiguriert. Der Spielleiter wählt passende globale Standardeinstellungen bei der Kampagnenerstellung; einzelne Sensoren können davon abweichen.**

### Erkennungsprofile

- **Gewöhnliche optische Kamera:** Kann eine **ausreichende Beleuchtung** des Ziels bzw. der erfassten Umgebung benötigen. Liegt die serverseitig ausgewertete Helligkeit unter einem geeigneten, konfigurierten Schwellenwert, wird das Ziel nicht allein wegen seiner Position im Sichtkegel als optisch erkannt.
- **Nachtsichtkamera / Restlichtverstärker:** Darf abhängig von ihren definierten Fähigkeiten schwaches Licht nutzen oder andere zulässige Nacht-Erkennungsregeln anwenden. **Nachtsicht ist nicht pauschal dasselbe wie Wände durchsehen**; die Hindernisprüfung aus 02.42 bleibt unabhängig.
- **Wärmebildsensor:** Kann für ein geeignetes Ziel **verfügbare Wärme-/Temperaturmerkmale oder entsprechende Regelprofilwerte** auswerten und von normalem sichtbarem Licht unabhängig sein. Temperatur- oder Wärmebilder benötigen eine gültige simulierte Datenquelle; eine realistische Wärmephysik wird nicht automatisch vorausgesetzt.
- **Bewegungs- und Präsenzmelder:** Lichtabhängigkeit richtet sich nach der konkret ausgewählten Sensortechnik. Passive Präsenz- oder nichtoptische Bewegungsmelder müssen nicht automatisch sichtbares Licht erfordern; eine auf optischer Bilderkennung basierende Variante kann Licht prüfen.
- **Rauch-/Gas-/Hitze-/magische Sensoren:** Nutzen ihre jeweilige Umwelt- bzw. settingabhängige Erkennungsquelle. Sichtbare Dunkelheit ist für einen Rauchmelder keine generelle Sperre. Magische Sensoren können nur die vom zugehörigen Regel-/Objekttyp wirklich vorgesehenen Lichtregeln umgehen.

### Einstellung, Ausnahmen und dynamische Neubewertung

- **Bei der Kampagnenerstellung:** Passende Sensortyp-Defaults konfigurieren, beispielsweise `sichtbares Licht nötig`, `bei schwachem Licht möglich` oder `sichtlichtunabhängig` mit gegebenenfalls geeigneten Schwellen. Nur die vom gewählten Sensorprofil unterstützten Varianten anbieten; der genaue Lichtmaßstab bleibt offen.
- **Je Sensor überschreibbar:** Eine gewöhnliche Kamera kann eine bewusst gesetzte Abweichung erhalten, **soweit ihre Fähigkeiten diese erlauben** (etwa ein konfiguriertes Nachtsichtmodul). Die UI unterscheidet geerbten Kampagnenstandard, individuelle Ausnahme und effektiv geltendes Profil.
- **Änderung der globalen Vorgabe:** Vorschau und Wahl zwischen nur neu erzeugten oder auch bestehenden, nicht explizit überschriebenen Sensoren; individuelle Ausnahmen schützen (02.25).
- **Beleuchtung als wirkliche Spielgröße:** Der Server verwendet die kanonischen Lichtquellen, Licht- und Sichtblockaden und gegebenenfalls gültige Umweltdaten des Szenenmodells (02.6 und 02.9). Geht ein Licht an/aus, bewegt sich eine Lichtquelle oder ändert sich die Dunkelheit, müssen betroffene Sensoren nachvollziehbar neu bewertet werden. Eine bloße grafische Helligkeitsanimation im Client darf keine Detektion begründen.
- **Getrennte Regeln:** Erfassungsgeometrie (02.41), Hindernisse (02.42), Lichtabhängigkeit (02.43), Ziel-/Umweltfilter (02.40), Sichtbarkeit von Sensorzonen (02.41) und Sensor-Ausgangslogik sind unabhängige, gemeinsam auszuwertende Dimensionen.
- **Node-Ports und Debugger:** Die tatsächliche Erkennung kann einen getypten booleschen Ausgang beziehungsweise Ereignisimpuls erzeugen. Im berechtigten Debugger erläutern Zustände wie `Ziel in Zone, aber zu dunkel`, `Nachtsicht verfügbar`, `Wärmesignal nicht vorhanden`, `Sicht durch Wand blockiert` den jeweiligen Grund.
- **Isolation, Sicherheit und Geheimhaltung:** Gespeicherte Tests können Licht an-/ausschalten, Nachtsichtfähigkeiten variieren und Treffer/Nichttreffer prüfen, ohne die echte Kampagne zu verändern. Sensorerkennung darf keine verborgenen Objekte, Figuren oder sensorinternen Details unberechtigt an Spieler freigeben.

**02.44 beschlossen:** Pro Sensortyp konfigurierbare Ansprech-/Nachlauf-/Wiederholungszeiten und speicherbare quittierbare Alarme, jeweils mit globalen Standards und Objektausnahmen sowie Echtzeit- und Rundenzeitbasis. **Weiter offen:** Quittierungsrechte und Resetwege (02.45), Licht-/Wärmedetailmodelle, Timer-Neustart, Pause-/Offline- und Performanceverhalten.

## 02.44 – Sensor-Auslösezeiten, Nachlauf und quittierbare Alarme (12.10.2026)

**Beschlossen: Variante C – Sensoren erhalten je nach Sensortyp frei konfigurierbare Auslöse-, Halte- und Rücksetzregeln. Die Kampagnenerstellung legt globale Standards je Sensortyp fest, mit sichtbar markierten Ausnahmen pro Sensor.**

### Unterstützte Modi

- **Sofortige Auslösung:** Die erfolgreich geprüfte Erkennungsbedingung kann unmittelbar einen booleschen Zustand ändern und/oder einen Ereignisimpuls ausgeben; Impuls und anliegender Wert sind gemäß 02.20–02.21 zu unterscheiden.
- **Ansprech-/Auslöseverzögerung:** Ein Sensor reagiert erst, nachdem eine qualifizierte Bedingung lang genug bestand. Beispiel: Kamera erkennt einen Eindringling erst nach einer gewählten Verweildauer. Verhalten bei einer kurzen Unterbrechung innerhalb der Verzögerung später detaillieren.
- **Fortbestehender Zustandsausgang:** Präsenz kann als EIN anliegen, solange tatsächlich mindestens ein geeignetes Ziel die Erkennungsregel erfüllt; die Roh-Erkennung und ein nachfolgend gespeicherter Alarm müssen getrennt behandelt werden.
- **Nachlaufzeit:** Nach Wegfall der Erkennung kann ein Ausgang eine wählbare Dauer aktiv bleiben. Beispiel: Licht bleibt nach Verlassen des Raums noch eine Weile an. Ob erneute Erkennung den Nachlauf zurücksetzt oder verlängert, wird später präzisiert.
- **Wiederholte Impulse:** Ein dafür geeigneter Sensor kann bei weiter bestehender Bedingung in konfigurierbaren, begrenzten Abständen erneut Ereignisse ausgeben. Ereignisschleifenschutz und Duplikaterkennung gelten weiterhin.
- **Gespeicherter/quittierbarer Alarm:** Ein Alarmsignal kann nach einem Treffer dauerhaft aktiv bleiben, selbst wenn die Erkennungsbedingung entfällt, bis ein ausdrücklich vorgesehenes Reset-/Quittierungsereignis akzeptiert wurde. Rechte und Resetwege werden in 02.45 gesondert entschieden.
- **Fähigkeitsgrenzen:** Aus einer Einstellung darf keine nicht vorhandene Sensortechnik entstehen. Kamera-, Rauch-, Präsenz-, Bewegungs- und settingabhängige Sensorvorlagen bieten nur die für sie unterstützten Modi und Porttypen an.

### Voreinstellungen und zeitliche Grundlagen

- **Kampagnenweite Standards:** Je Sensortyp Standardmodus, erlaubte Ansprechdauer, Nachlauf, Wiederholungsintervalle und gegebenenfalls Alarm-Speicherverhalten im Kampagnenerstellungs-Assistenten definieren.
- **Individuelle Sensor-Ausnahmen:** Der Spielleiter kann einzelne Sensoren anders konfigurieren und sieht geerbte bzw. überschriebene Werte. Spätere Änderung der Kampagnenstandards mit Vorschau/Bestandsauswahl und Schutz von Ausnahmen gemäß 02.25.
- **Echtzeit oder Runden:** Eine passende Verzögerung und ein Nachlauf können wahlweise in echten Sekunden/Minuten oder Spielrunden bemessen sein. Die Zeitgrundlagen sind ausdrücklich getrennt und werden nicht automatisch ineinander umgerechnet (02.15–02.16).
- **Unabhängig von Erkennungsbedingungen:** Zielarten/Filter (02.40), Zonenform/Sichtbarkeit (02.41), Hindernisse (02.42), Licht (02.43), Rohdetektion und die spätere Alarmrücksetzung sind getrennte Eigenschaften.

### Serverseitige Logik, Tests und Geheimnisse

- **Autoritativer Sensorzustand:** Server startet, unterbricht und beendet Zeitgeber; er erstellt die daraus folgenden Signaländerungen atomar. Wiederholte Netzwerkereignisse dürfen keinen doppelten Alarm oder unerwartete Verlängerungen verursachen.
- **Debug-Modus:** Spielleiter sehen nachvollziehbar Rohdetektion, laufende Auslöseverzögerung, Zustand EIN/AUS, aktive Nachlaufzeit, nächsten wiederholten Impuls, gespeicherten Alarm sowie akzeptierte/abgelehnte Resets. Die genauen Namen von Ports/Statuswerten folgen später.
- **Wiederholbare Tests:** In der isolierten Simulation können Auslöseverzögerungen, kurzzeitiges Betreten und Verlassen, Nachlauf, erneute Erkennung, wiederholte Impulse sowie Alarmquittierungen im Echtzeit- oder Rundenmodus überprüft werden. Keine echten Türen, Timer oder Spielzustände verändern.
- **Sicherheits- und Sichtbarkeitskontrolle:** Sensorreset nur nach serverseitiger Autorisierung. Interne Signale/Alarmdaten und versteckte Sensoren dürfen nicht an unberechtigte Spieler gesendet werden; die Zone-Sichtbarkeit aus 02.41 bleibt unabhängig.

**02.45 beschlossen:** Berechtigungen und Resetwege für Alarme über Kampagnenstandard und Sensor-Ausnahmen mit überprüften SL-Aktionen, Bedienobjekten und Node-/Szenen-Ereignissen; alle Vorgänge werden protokolliert. **Weiter offen:** Quittierung und Rücksetzung bei fortbestehender Gefahr (02.46), erneute Erkennung während Nachlauf, Entprellung/Wiederholungsgrenzen, Timer bei Pause/Neustart, Persistenz und Skalierung.

## 02.45 – Berechtigte Sensoralarm-Quittierung über SL, Bediengeräte und Node-Signale (12.10.2026)

**Beschlossen: Variante C – der Spielleiter definiert im Kampagnenassistenten einen globalen Berechtigungs- und Auslöse-Standard für quittierbare/gespeicherte Sensoralarme, der pro Sensor gezielt überschrieben werden kann.**

### Mögliche Quittierungs- und Resetwege

- **Direkte Spielleiteraktion:** Eine berechtigte Spielleitung darf über die Sensor-Eigenschaften, eine Alarmliste oder den Node-Editor den Quittierungs-/Resetvorgang anfordern. Der Server prüft die Kampagnenrolle und den zugeordneten Sensor.
- **Bedienobjekt im Spiel:** Ein vom Spielleiter platzierter Reset-Taster, ein Terminal, eine Alarmzentrale oder ein vergleichbares settingabhängiges Objekt kann eine Quittierung auslösen, sofern die konkrete Figur zum Bedienobjekt Zugang hat, die Bedieninteraktion zulässig ist und die Sensor-Quittierungsrichtlinie sie ausdrücklich gestattet.
- **Node-/Szenenereignis:** Ein geeignetes, überprüftes Node-Signal oder definiertes Szenenereignis kann eine Alarm-Quittierung bzw. einen Reset anfordern. Das Signal darf die Sensor-Berechtigungsprüfung **nicht umgehen**: Herkunft, Berechtigungskontext und zulässige Automationsquelle werden serverseitig validiert. Automatische Resets nur nach explizit autorisierter Regel.
- **Beschränkung nach Rollen und Figuren:** Der Spielleiter kann bestimmen, welche Spielleiter-/Mitspielleiter-Rollen, Spielerrollen, Figuren/Fraktionen oder explizit freigegebenen Akteure und Bedienobjekte einen bestimmten Alarm quittieren dürfen. Zugriff auf das Bedienobjekt allein ist nicht zwingend bereits eine Resetberechtigung.
- **Passende Sensortypen:** Quittierung/Reset ist nur für Sensoren und Signalzustände verfügbar, die einen gespeicherten bzw. quittierpflichtigen Alarm oder eine eigene Resetfunktion tatsächlich unterstützen. Ein einfacher Präsenzzustand braucht nicht unnötig eine Quittierung.

### Globale Vorgaben und Objektausnahmen

- **Bei Kampagnenerstellung:** Voreinstellung für autorisierte Rollen/Akteure, zulässige Bedienwege und die verfügbaren Reset-/Quittierereignisse festlegen. Genre und Regelprofil dürfen passende Vorgaben liefern, die Event-Engine bleibt generisch.
- **Pro Sensor abweichend:** Eine geheime Sicherheitskamera kann ausschließlich durch den SL zurücksetzbar sein, während ein öffentlicher Rauchmelder über eine berechtigte Alarmzentrale quittiert werden darf. Die wirksamen, geerbten und individuell überschriebenen Einstellungen sind sichtbar markiert.
- **Globale Einstellungen später ändern:** Vorschau, wahlweise nur neue oder auch bisher nicht individuell überschriebene Sensoren und Schutz bestehender Ausnahmen gemäß 02.24–02.25.
- **Rechte und Geheimnisschutz:** Spieler müssen weder einen versteckten Sensor noch seinen internen Alarmzustand kennen, wenn sie dazu nicht berechtigt sind. Die Bedienbarkeit einer Resetstelle und Sichtbarkeit von Sensorzonen (02.41) sind voneinander unabhängig.

### Serverseitige Prüfung, Audit und Debugging

- **Jede Anforderung prüfen:** Authentifizierte Identität bzw. vertrauenswürdige Automationsquelle, Kampagnen-/Szenenzuordnung, Rollen-/Figurenrecht, Objektrechte und die konkret freigegebene Resetmethode werden geprüft. Ein bloßes Clientkommando oder irgendein angeschlossenes Node-Kabel darf einen Alarm nicht ungeprüft zurücksetzen.
- **Audit:** Akzeptierte und abgelehnte Vorgänge werden für berechtigte Spielleiter nachvollziehbar erfasst, einschließlich Zeitpunkt/Spielrunde, Sensor, handelnder Figur/Rolle oder Automationsquelle, Resetweg, vorherigem/nachherigem Zustand und Abweisungsgrund. Aufbewahrungsfrist und Detailtiefe später entscheiden.
- **Atomarer Statuswechsel:** Serverseitiger Alarmzustand und relevante Node-Ausgänge dürfen nicht doppelt oder widersprüchlich verändert werden, auch nicht bei konkurrierenden Reset-, Alarm- und Auslöseereignissen (02.35). Wiederholte Netzwerkpakete sind sicher zu deduplizieren.
- **Quittieren ist nicht automatisch Gefahrenbeseitigung:** Eine Reset-Anforderung ändert nicht die real ausgewertete Präsenz-, Rauch- oder Sicherheitsbedingung. **Ob ein Alarm bei weiterhin anliegender Gefahr überhaupt zurückgesetzt werden darf und wie Quittierung versus Alarm-Rücksetzung wirken, entscheiden wir gesondert in 02.46.**
- **Isolierte Tests:** Szenarien prüfen berechtigte/unberechtigte SL- und Spieleraktionen, Alarmterminal, Node-Reset, konkurrierende Ereignisse und fehlende Sensorberechtigung. Simulation schreibt niemals echte Alarme oder Kampagnenzustände.

**Noch offen:** Umgang mit aktiv fortbestehender Gefahrenbedingung (02.46), Trennung von Stummschalten/Quittieren/physischem Reset, Mehrpersonenfreigabe, eventuelle Sicherheitsfreigaben für automatische Node-Resets, Auditaufbewahrung, Rechte bei Gruppenwechsel und konkrete Alarmzentrale-UI.

## Nächste Entscheidung 02.46 – Darf ein Alarm quittiert werden, solange die Gefahr noch besteht?

- **A – Rücksetzung erst nach Entwarnung:** Solange der Sensor die Gefahr weiterhin erkennt, wird der Reset abgewiesen; der Alarm bleibt aktiv.
- **B – Sofortiger Reset mit erneuter Auslösung:** Ein berechtigter Reset ist jederzeit möglich, aber solange die Gefahr anliegt, kann der Alarm unmittelbar erneut auslösen.
- **C – Quittierung und Reset getrennt konfigurierbar (Empfehlung):** Der Spielleiter legt global nach Sensortyp fest, ob die Quittierung z. B. nur einen Alarmton verstummen lässt, während die Gefahr weiter sichtbar bleibt, und wann der gespeicherte Alarm wirklich zurückgesetzt werden darf. Pro Sensor gelten mögliche Ausnahmen; bestehende Gefahr darf nicht unbemerkt als beseitigt erscheinen.
