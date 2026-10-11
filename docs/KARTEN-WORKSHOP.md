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
| 02.19 | Umgang mit Node-Ereignissen in nicht aktiven Szenen | Als Nächstes |

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

## Nächste Entscheidung 02.19 – Ereignisse in inaktiven Szenen

- **A – Sofort ausführen:** Eine Node kann Objekte in einer nicht angezeigten Szene sofort verändern. Der neue Zustand ist beim Betreten bereits vorhanden.
- **B – Bis zur Aktivierung vormerken:** Aktionen werden erst ausgeführt, wenn die Zielszene aktiviert wird.
- **C – Pro Regel konfigurierbar (Empfehlung):** Der Spielleiter kann wählen, ob das Ereignis sofort ausgeführt, bis zur Aktivierung vorgemerkt oder nur bei aktiver Szene ausgeführt werden darf. Die gewählte Semantik wird serverseitig gespeichert und nachvollziehbar gemacht.

Danach folgen Port-Datentypen, Debugging, Reaktionsfolgen und weitere Detailregeln.
