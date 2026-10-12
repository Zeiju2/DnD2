# AdventureShift – Karten-Workshop: Beschluss 02.82 C

**Stand:** 12.10.2026 – Beschlüsse 02.1 bis 02.82; als Nächstes 02.83  
**Status:** Verbindliche fachliche Entscheidung, Umsetzungsplanung und Abnahmetests. Kein implementierter Programmcode, keine finale API oder Datenbankmigration.  
**Bezüge:** [Karten-Hauptworkshop](KARTEN-WORKSHOP.md) · [02.25 Vorgaben/Bestandsschutz](KARTEN-WORKSHOP.md) · [02.77 Node-Fehlerpfade](KARTEN-WORKSHOP-02.77.md) · [02.80 Laufzeitversionen](KARTEN-WORKSHOP-02.80.md) · [02.81 Mehrpersonenbearbeitung](KARTEN-WORKSHOP-02.81.md)

## 02.82 – Konfigurierbare Graphversionshistorie mit sicherem Undo, Vergleich und Wiederherstellung

**Verbindlich beschlossen: Variante C.** Berechtigte Spielleitungen können nach **Kampagnen-/Regelprofilstandard** und ausdrücklich gekennzeichneten **Graph-/Arbeitsbereich-/Untergraph-/Rollen-Ausnahmen** auf nachvollziehbare Graph- und Entwurfsversionen zugreifen, Änderungen rückgängig machen/wiederholen, Versionen vergleichen, eine alternative Kopie bzw. einen neuen Entwurfszweig aus einem historischen Stand anlegen und eine frühere **Graphdefinition** kontrolliert wiederherstellen. Bestands-/Vererbungs- und Änderungsvorschau nach 02.25; tatsächliche Zugriffs-/Freigaberechte aus 02.81 bleiben zwingend.

**Zentrale Grenze:** Ein historischer Graphstand enthält fachliche Node-/Kanten-/Port-/Regel-/Layoutdefinitionen, **nicht automatisch einen früheren Spielweltzustand**. Ein Restore darf niemals unbemerkt geschehene Türöffnungen, Spielerpositionen, Fog-Erkundung, Würfelchecks, Inventarkosten, Alarme, Spawns, Nachrichten oder Turngenerationen zurücksetzen oder wiederholen. Diese realen Effekte haben eigene serverautoritative Zustände und das einmalige Ereignis-/Effektprotokoll aus 02.35/02.63–02.80.

### 1. Historie, Vergleich und zulässige Bearbeitung

- **Versionsverlauf:** Berechtigt sichtbare, unveränderlich identifizierbare veröffentlichte Graphversionen mit Parent-/Herkunftsbezug, Veröffentlichungsgrund/Zeit, berechtigtem Urheber/Freigeber, Betroffenheit und dokumentierten Änderungen. Optional versionierte Entwurfssicherungen/Zwischenstände getrennt führen. Inhalt und Sichtbarkeit nach Kampagnen-/Graph-/Untergraph-/Rollenpolicy, nicht pauschal für alle Spieler und SL.
- **Undo/Redo im Entwurf:** Schritte im berechtigten aktuellen Draft gezielt rückgängig machen oder wiederholen. Bei Mehrpersonenbearbeitung 02.81 gilt Undo als neuer, gegen **die aktuelle Version** geprüfter Edit: keine stillschweigende Löschung fremder inzwischen gültiger Änderungen. Bei kollidierendem Undo muss eine berechtigte Konflikt-/Merge-Entscheidung erfolgen. Das Drücken von Undo löst keine echte Spiel-Node aus.
- **Vergleichen:** Zwei berechtigt einsehbare Versionen auf semantische Unterschiede prüfen: Nodes, Parameter, Ports/Porttypen, Kanten, Untergraph-/Vorlageninstanzen, Regeln, Timer-/Fan-out-/Join-Definitionen und getrennt editorseitige Positionen/Layouts. Hinzufügen, Entfernen, Umbenennen, Referenzänderungen, Geheimnisschutz, Ein-/Ausgangstypen und mögliche Laufzeitfolgen klar unterscheiden. Nur Namen/Positionen sind nicht identisch mit stabilen Node-/Objekt-IDs.
- **Kopieren/Verzweigen:** Einen berechtigt zugänglichen historischen Graphstand als **neuen unveröffentlichten Entwurf** zur Bearbeitung/Konfliktanalyse übernehmen. Dabei Ziel-/Objekt-/Vorlagenreferenzen im aktuellen Kampagnen-Scope validieren; keine heimliche Kopie bestehender realer Figur-/Tür-/Inventarinstanzen. Keine automatische Veröffentlichung, Weitergabe fremder Geheimnisse oder doppelte Graphwirkung.
- **Wiederherstellen als neue Version:** „Version X wiederherstellen“ bedeutet **eine neue, vor dem Commit geprüfte Graphveröffentlichung** mit Herkunftsverweis auf X, nicht stilles Verschieben der aktiven Version auf einen alten Snapshot und erst recht kein Überschreiben/Verfälschen der Historie. Auswirkungsvorschau und gezielte Freigabe nach 02.81; aktive und wartende Graphabläufe gemäß 02.80 prüfen.
- **Geltungsbereich einer Wiederherstellung:** Je wirksamer Policy darf eine autorisierte Graphfassung vollständig oder ein geeignetes, in sich konsistentes Untergraph-/Node-/Layout-Teilset wiederhergestellt werden. Teil-Restore nur mit expliziter Typ-/Port-/Kanten-/Ziel-/Vorlagen-/Cross-Scene-Referenzprüfung und Konfliktlösung; keine unbemerkt gebrochenen Verbindungen zu nicht restaurierten Bereichen.
- **Rollen und Rechte:** Lesen, Vergleichen, eigene Entwurfsaktionen rückgängig machen, Wiederherstellungsentwurf anlegen, Merge-/Restorekonflikte entscheiden und endgültig veröffentlichen sind **getrennte Berechtigungen**. Graphhistorie ist keine Hintertür für bereits widerrufene Rechte, versteckte Szenen oder geheime Fallen. Vergleiche und Autoren-/Änderungsmetadaten werden pro berechtigtem Empfänger gefiltert.
- **Retention/Archivierung:** Versionen und Zwischenstände dürfen gemäß fachlich konfigurierbarer, später zu konkretisierender Speicher-/Aufbewahrungsregel archiviert bzw. nach gültiger Policy gelöscht werden. **Noch von aktiven GraphExecution-/Timer-/Join-/Checkabläufen oder einer notwendigen Audit-/Sicherheitsprüfung referenzierte Versionen nicht unkontrolliert entfernen.** Keine pauschale Pflicht zu unendlicher Draftaufbewahrung und keine heutige Festlegung konkreter Fristen oder Speichergrößen.

### 2. Sichere Restore- und Veröffentlichungsabfolge

1. **Autorisierung und historische Referenz:** Nur berechtigte SL-/Bearbeiterrolle, gültiger Kampagnen-/Graph-/Untergraph-Scope und wirklich verfügbare Version X. Alte Zugriffsrechte aus Version X werden **nicht** als aktuelle Freigabe übernommen.
2. **Neue Entwurfsrevision:** Historische Definition mit stabilem Herkunftsverweis als neuen Vorschlagsstand ausarbeiten, ohne aktuellen veröffentlichten Stand zu verändern. Der alte Eintrag bleibt unverändert im Verlauf.
3. **Semantische Diff- und Impact-Vorschau:** Aktuellen veröffentlichten Stand, Zielvorschlag und zwischenzeitlich anderer SL vorgenommene Änderungen vergleichen. Besonders entfernte Nodes, Porttypänderungen, Referenzen in andere Szenen, Untergraph-Vorlagen, Änderungen an Sicherheits-/Geheimnis- und Zugriffsregeln markieren.
4. **Konfliktbehandlung nach 02.81:** Bei veraltetem Basisstand, konkurrierenden SL-Edits und kollidierenden Berechtigungen sicheren Merge/Neuabgleich oder ausdrücklich berechtigte Entscheidung verlangen; kein blindes Last-Writer-Wins. Ein privater Entwurf eines anderen SL wird nicht ohne Berechtigung gelöscht.
5. **Validierung/Tests:** Node-/Port-/Kanten-/Objekt-/Timer-/Join-Rechte, Geheimnisgrenzen und ggf. Testfreigabe nach 02.31–02.34 für die geplante Publikation prüfen. Fehlende, inzwischen gelöschte echte Objekte und widerrufene Berechtigungen dürfen nicht durch historische Referenzen wiederhergestellt werden.
6. **Explizite atomare Publikation:** Erfolgreiche Freigabe erstellt einen **neuen PublishedGraphVersion-Datensatz** mit dem gerade erwarteten Basisstand, Herkunft aus X, eindeutiger Freigabe-/Commit-ID und geprüftem effektiven Inhalt. Reconnect, Doppelklick oder Serverneustart darf keine zweite Veröffentlichung erzeugen.
7. **In-Flight-Ausführungen nach 02.80 C:** Laufende/pausierte/pending Timer-, Fan-out-, Join-, Check- und Graphinstanzen je aktiver Graphänderungspolicy auf gültiger alter Logik abschließen, ggf. sicher pausiert/SL-bestätigt migrieren oder kontrolliert beenden. Alte System-/Objekt-/Ressourcenrechte vor **jedem** verspäteten Effekt erneut validieren; kein implizites Neuwürfeln, Nachholen oder Neuabspielen alter Weltaktionen.
8. **Zustands-/Effekttrennung:** Die neue Graphdefinition verändert grundsätzlich **nicht rückwirkend** bereits geschehenes Spieler-/Figuren-/Objekt-/Inventar-/NPC-/Alarm-/Quest-/Turn-/Würfelergebnis. Wo eine künftige berechtigte Zustandsänderung gewollt ist, muss sie als **neue, einzeln autorisierte und protokollierte Spielweltaktion** gesondert geplant/ausgeführt werden; sie ist keine versteckte Restore-Nebenwirkung.
9. **Audit, Zugriff und Geheimnisse:** Autorisierte Graphversion, Ursprung, Vergleich, Konfliktentscheide, Restaurationsfreigabe, betroffene alte/live Instanzen und tatsächliche Publikation nachvollziehbar für Berechtigte protokollieren; Spielern und unberechtigten Bearbeitern niemals geheime Node-/Fallentypen, Nutzeridentitäten, Check-IDs oder Szenenziele preisgeben.

### 3. Umsetzungsplanung – noch kein Code

Konzeptionelle Platzhalternamen: `GraphRevision`, `GraphHistoryPolicy`, `DraftUndoOperation`, `GraphVersionDiff`, `GraphRestoreProposal`, `GraphRestoreImpact`, `GraphPublicationRequest`, `PublishedGraphVersion`, `GraphRevisionRetentionPolicy`. Verknüpft: stabile Graph-/Kampagnen-/Node-/Port-/Kanten-/Untergraph-/Vorlagen-IDs; Basis-/Ziel-/Parent-/Origin-Versionen; Bearbeiter-/Genehmigerrechte; Draft-/Publishedstatus; Änderungs-/Merge-/Restore-IDs; ggf. fachliche Versionreferenzen laufender Ausführungen. Ob Snapshots, Deltas oder eine Kombination persistent verwendet werden, ist eine spätere Implementierungsentscheidung. Graphversionshistorie, tatsächliche Welt-Eventledger und Server-/Datenbank-Backups bleiben **getrennte Ebenen**.

**Geplante Schritte:** (1) Graph- und Entwurfsrevisionen auf bestehende 02.80/02.81-Identität/Rechte aufbauen und historisch unveränderlich referenzieren; (2) reversible, versionsgeprüfte Draft-Operationen (Undo/Redo) und sichere Diff-/Vergleichs-/Vorschlagsansichten; (3) graphsemantische Import-/Restore-/Teilrestore-Prüfung und Konfliktauflösung einschließlich Vorlagen und Cross-Scene-Kanten; (4) neue atomare Publikation mit Live-Impact aus 02.80, Idempotenz und ggf. Testfreigabe; (5) rechte-/geheimnisgeschützte Revision-/Audit-Projektionen, Retention- und Backup-Konzept sowie isolierte Race-/Reconnect-/Regressions-/Wiederanlauftests. Konkrete UX, Zahlenwerte, Fristen, Dateiformate und Frameworks erst später entscheiden.

### 4. Abnahmeszenarien

| Test | Erwartung |
| --- | --- |
| SL bearbeitet Port eines unveröffentlichten Entwurfs, drückt Undo/Redo | Nur zulässige Graph-/Entwurfsänderung, keine Tür-, Alarm-, Würfel- oder Itemwirkung |
| SL A führt Undo auf alter Entwurfsversion aus, SL B hat inzwischen denselben Port geändert | Versions-/Mergekonflikt statt stilles Überschreiben von Bs Änderung |
| Berechtigter Vergleich gestern/heute | Node-/Port-/Kanten-/Regel-/Layoutänderungen nach stabilen IDs, vertrauliche Unterschiede nur für Berechtigte |
| Alte Graphversion als Alternative kopieren | Neuer Draft; aktive Publikation und echte Objekte unverändert |
| Gestern vorhandene Tür wurde aus der Szene gelöscht | Restore darf sie nicht allein durch einen alten Nodeverweis wiederherstellen; sichere Ablehnung/Anpassung |
| Neue Graphversion verändert Krit-/Jackpot-/Timer-Node | Alte wirkliche Würfe/Ergebnisports/Occurrence-IDs und bereits gezahlte Gewinne bleiben unverändert |
| Puzzle-Tür wurde geöffnet, danach Graphrevision zurückgesetzt | Reale Tür bleibt offen, solange keine eigene neu autorisierte zulässige Spielweltaktion sie schließt |
| Join aus 02.79 wartet, während ältere Graphfassung veröffentlicht wird | 02.80-C-Lebenszyklus/Versionierung schützt aktuelle Erwartungsmenge und bereits verbuchte Branch-/Effekt-IDs |
| Unberechtigter Mitarbeiter ruft historische Geheimfallenversion auf | Kein Zugang zu Inhalt, Diff, Metadaten oder Existenzdetails |
| Zwei Spielleitungen versuchen Restore mit derselben veralteten Basis | Atomare Publication-Compare-Prüfung; höchstens eine auf Basis gültige Veröffentlichung, andere muss neu prüfen |
| Wiederholte Restore-Anforderung nach Reconnect | Gleiche Restore-/Publication-ID, keine zweite Node- oder Weltwirkung |
| Historische Version wird noch von laufendem Timer referenziert | Archiv-/Aufbewahrungspolitik beschädigt den aktiven Restore-/Abschluss-/Auditkontext nicht |
| Nur Layoutposition wiederherstellen | Keine Änderung an echter Node-/Port-/Regel- oder Spielweltwirkung |
| Serverausfall während Veröffentlichung | Konsistente wiederaufnehmbare Publikations-/Revisionshistorie, kein halb überschriebenes Graph- oder Weltmodell |

### 5. Abgrenzung und nächste Frage

- **02.82 C** betrifft die Wiederherstellung von **Node-Graphdefinitionen**, nicht automatisch die Wiederherstellung von Kartenbildern, Wänden, Ebenen oder gezeichneten Szenenobjekten. Reine Map-/Szenen-Undo- und Versionierungsdetails sind in 02.2 ausdrücklich noch offen.
- **02.83** entscheidet daher als eigene fachliche Folgefrage, ob und wie eine vergleichbare **Undo-/Versions-/Wiederherstellungsfunktion für Karten und Szeneneditorinhalte** vorgesehen werden soll. Diese darf nicht unbemerkt tatsächliche Figurenposition, erkundete Fog-Bereiche, vergangene Timer, NPC-Wissen oder Weltfolgen zurücksetzen.
- **02.81 C** bleibt für Mehrpersonen-Edit/Publikationskonflikte zuständig, **02.80 C** für laufende Ausführungen bei Graphversionwechseln. Das bisherige Sicherheits-/Rollen-/Geheimnismodell und 02.25-Bestandsschutz gelten weiterhin.
- Globale Kampagnenassistentenführung, allgemeine Modulabschaltungen, konkrete Speicherung/Dateiformate und MVP-Priorität weiterhin erst nach abgeschlossenem Featureworkshop; Ausnahme zur Deaktivierung der Akustiksimulation aus 02.51 bleibt bestehen.

## Nächste Entscheidung 02.83 – Undo, Versionsverlauf und Wiederherstellung im Karten-/Szeneneditor

**Beispiel:** Eine Spielleitung hat in einer Szene Wände, Tiles, Räume und Ebenen bearbeitet und stellt später fest, dass eine ältere Kartenanordnung besser war. Inzwischen haben Spieler die Szene erkundet und Figuren bewegt.

- **A – Nur lokales Undo/Redo:** Lediglich nicht veröffentlichte aktuelle Karten-/Zeichenänderungen rückgängig machen; keine gezielte Historie veröffentlichter Szeneneditorstände.
- **B – Kompletter Szenen-Rollback:** Frühere Kartenfassung auswählen und zugleich ohne separate Prüfung alle inzwischen geschehenen Szenen-/Figuren-/Fog-/Inventar-/Timer-/NPC-/Weltzustände automatisch zurücksetzen.
- **C – Konfigurierbare sichere Karten-/Szenenversionen (Empfehlung):** Je Kampagnen-/Szenen-/Ebene-/Bereichs- und Bearbeiterrechten Historie, Vergleich, Undo/Redo und kontrollierte Wiederherstellung von **Editorinhalten** wie Kartenbildern, Tiles, Wänden, Räumen und Layern erlauben. Wie bei 02.82 als neue geprüfte Veröffentlichung; laufende Node-/Objektreferenzen und Sicht-/Kollisionsregeln beachten, ohne real bereits geschehene Erkundung, Figurenbewegung, Würfe oder Inventarwirkungen ungeprüft zurückzusetzen.
