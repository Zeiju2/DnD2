# AdventureShift – Charakter-Workshop: Beschluss 03.6 C – kontrollierte, selektive Migration bestehender Charaktere

**Stand:** 16.10.2026. Verbindlich gewählt **03.6 C**. **Nächste strukturelle Frage: 03.7 – berechnete/abgeleitete Charakterwerte**.
**Status:** Fachplanung mit Datenmodell, Berechtigungen, Ablauf und Abnahmetests. **Keine Softwareimplementierung**; konkrete Datenbank-/API-Verträge, UI, Mappingformeln und MVP erst später.
**Bezüge:** [03.1 C – typisierte Bogen-/Instanzversionen](CHARAKTER-WORKSHOP-03.1.md) · [03.2 C – Zuordnung/Kontrollrechte](CHARAKTER-WORKSHOP-03.2.md) · [03.3 C – separate Entwurfs-/Veröffentlichungsrechte](CHARAKTER-WORKSHOP-03.3.md) · [03.4 C – versionierte Klassen/Fähigkeiten/Skills](CHARAKTER-WORKSHOP-03.4.md) · [03.5 C – optionale Progression](CHARAKTER-WORKSHOP-03.5.md) · [01 Inventar, 02 Karten/Nodes, 05 Würfel und 07 Regelmodule](FEATURE-WORKSHOP.md) · [Planungsstandard](PLANUNGSSTANDARD.md).

## 1. Verbindliche Entscheidung

Der Projektinhaber hat **C** entschieden: Beim Veröffentlichen einer neuen Charakterbogen-Vorlage, Klassen-, Fähigkeits- oder Regelversion werden bestehende Figuren **nicht ungeprüft und automatisch** überschrieben. Bestehende Charakterinstanzen behalten ihren bisher gültigen Vorlagen-/Regel-/Skill-/Klassen-/Progressionszustand, bis ein **gesondert dazu berechtigter Actor** eine oder mehrere **ausgewählte Charaktere** anhand einer geschützten **Migrationsvorschau mit typisiertem Mapping** erfolgreich überprüft und **explizit** auf eine gültige Zielversion umstellt.

**Beispiel:** Nach zehn Spielsitzungen veröffentlicht die SL eine neue Vorlage. Ein Attribut wird nur umbenannt, eine bisherige Fähigkeit in mehrere Optionen aufgeteilt und die zulässige Energiekapazität verändert. Die Umbenennung lässt sich über die technische Feld-ID sicher zuordnen; die Aufteilung benötigt eine klare fachliche Entscheidung. Der neue Ressourcenwert muss nach gültiger Regel behandelt werden. Ungeklärte Schritte dürfen nicht still Werte löschen oder eine automatische Umschulung auslösen. Andere Figuren können vorerst legal auf ihrer bisherigen Version weiterspielen.

**Nicht gewählt:** A – jede neue Version sofort auf alle Figuren übertragen, auch bei Datenverlust – und B – jeder vorhandene Charakter muss für immer auf seiner ersten Version verbleiben, ohne je migrieren zu können. **C ist keine beliebige rückwirkende Regeländerung aller schon gespielten Aktionen und keine Zusage automatischer verlustfreier Konvertierung beliebiger Systeme.**

## 2. Zentrale Datenstruktur und Schnittstellen

1. **Bestehende Charakter-ID bleibt:** CharacterInstance aus 03.1 behält ihre stabile Identität, tatsächlich gespeicherte Basis-/Ressourcen-/Skill-/XP-/Punktwerte, Beziehungen zu 03.2-Besitz/Kontrolle sowie getrennte Karten-/Token-/Inventarinstanzen aus 01/02.
2. **Pinning auf Versionen:** Jede Figur verweist explizit auf die gültigen veröffentlichten Versionen ihrer SheetTemplate-/FieldDefinition-/Class-/Ability-/Skill-/Progression-/RulePack-Definitionen aus 03.1–03.5. Das reine Veröffentlichen neuer Versionen verändert diese Verweise nicht automatisch.
3. **Zieldefinitionen:** Ein zulässiges Ziel kann eine oder mehrere veröffentlichte kompatible Modulversionen umfassen. Drafts, widerrufene RulePacks, unlizenzierte Assets und fremde Kampagnenversionen sind ohne aktuelle Berechtigung keine gültigen Migrationsziele.
4. **Migrationsentwurf:** MigrationPlan bzw. CharacterMigrationDraft (nur Arbeitsbegriffe) enthält berechtigte Charakterauswahl, konkrete Ausgangs-/Zielversionen, CharacterRevision, getypte Feld-/Ressourcen-/Skill-/Class-/Ability-/XP-/Punkte-Mappings, benannte unaufgelöste Konflikte und die für die Anwendung erforderlichen Freigaben. Ein solcher Entwurf ist **nichtweltwirksam**.
5. **Stabile Feld-IDs:** Eine bloße Umbenennung eines Feldes bei unveränderter technischer ID darf den Wert nicht zurücksetzen. Aufteilen, Zusammenführen, Entfernen, Umtypisieren oder Ersetzen von Feldern ist eine echte migrationsrelevante Änderung und kann nicht nach zufällig gleichen Anzeigenamen gemappt werden.
6. **Typisierte Konvertierung:** Abweichende Datentypen, Einheiten, Wertebereiche, Ressourcenmaxima, Startwerte und notwendige neue Pflichtfelder müssen nach explizit erlaubten Konversionsregeln geprüft werden. Keine unkontrollierte Rundung, Wertlöschung, Typumdeutung oder Veränderung von Charaktersicht-/Editrechten.
7. **Skill-/Klassenbezüge:** Klassen-, Skill- und Fähigkeitsauswahlreferenzen aus 03.4 können bei neuen Definitionen abweichen. Eine entfernte Fähigkeit darf nicht einfach verschwinden oder kostenlos doppelt durch zwei neue ersetzt werden. Fehlt ein valider Umstieg, sind Blocker oder gezielt freigegebene geschützte Legacy-Zuordnung nötig.
8. **Progression:** 03.5-Fortschrittsstände, ausgebbare Punkte, XP, Ränge, bereits gewählte Verbesserungen und früher echte Vergabe-/Ausgabeereignisse sind gesondert zu prüfen. Neue Kosten-/Levelkurven werden nicht rückwirkend still auf abgeschlossene Aufstiege abgerechnet; kein doppelter Award oder negative Punktkonten ohne explizit erlaubte Regel.
9. **Keine Datenverluste:** Nicht eindeutig zuordenbare Bestandswerte werden nicht stillschweigend entfernt. Falls für einen gültigen Umstieg eine ausdrücklich erlaubte, geschützte Legacy-Aufbewahrung nötig ist, muss diese mit klarer Zugriffs-/Speicherpolicy geplant werden; sonst die Migration blockieren. Keine unbefristete öffentliche Historie oder Geheimnisfreigabe.
10. **Abgeleitete Wirkungen:** Klassen- und Itemmodifikatoren, temporäre Zustände und sonstige abgeleitete Quellen bleiben vom gespeicherten Basiswert getrennt. Eine neue gültige Regelversion darf zulässige abgeleitete Werte **für neue Aktionen** anders berechnen, nicht frühere Würfe oder verbrauchte Gegenstände nachträglich rückgängig machen.
11. **Auswahl statt globalem Rollout:** Eine SL kann nach heute gültiger Kampagnen-/Charakterpolicy einzelne ausgewählte Figuren migrieren; andere bleiben auf alten gültigen Definitionen. Gleichzeitige unterschiedliche Bogen-/RulePack-Versionen in einer Kampagne sind als zulässiger Übergangszustand vorzusehen.
12. **Vorschaurechte:** Berechtigte Vorschau zeigt nur autorisierte Quell-/Zieldaten. Geheime SL-/NPC-Felder, verborgene Klassen, private Charakterwerte und nicht lizenzierte RulePack-/Assettexte werden unberechtigten Spielerbrowsern **nicht** geliefert, auch nicht als versteckte Payloads oder Fehlermetadaten.
13. **Gesonderte Migrationsrechte:** Vorlagenbearbeitung, 03.3-Publikation, normaler Feldedit und 03.2-Charaktersteuerung sind **nicht automatisch** Berechtigungen zum Übertragen eines fremden Charakters auf neue Regeln. MigrationPreview, MigrationApprove und MigrationCommit brauchen bei Bedarf eigene Rechte/Freigaben nach 02.25-Standards und Ausnahmen.
14. **Alte Version nicht über heutige ACL stellen:** Pinning auf bisherige Regeln erlaubt nicht, gesperrte Quellen, Lizenzen, Skills oder Aktionen weiter zu nutzen, wenn aktuelle Rechte oder zwingende Sicherheitsbedingungen sie verbieten. Wenn eine alte Funktion nicht mehr rechtmäßig nutzbar ist, wird sie gesperrt, bis ein gültiger Weg vorliegt.
15. **Pro-Charakter-Transaktion:** Jede Figur migriert ganz oder gar nicht. Auch ein Batch mehrerer ausgewählter Figuren darf **keine halb migrierte Figur** hinterlassen; Ergebnisse sind pro Figur nachvollziehbar. Übergreifende Batch-Atomarität und Mengenbegrenzung erst bei technischer Umsetzung entscheiden.
16. **Versionskonflikte:** Bei Änderungen von Charakterwerten, Skillständen, ResourceState, Regelversion, Zugriff oder Inventory-Abhängigkeiten **seit der Preview** muss der VPS vor dem Commit die Lage erneut prüfen und gegebenenfalls eine neue Preview verlangen. Kein Lost Update durch veraltete Clientdaten.
17. **Einmalige Wirkung:** Idempotente Operation-ID verhindert Doppelmigration oder zusätzliche zufällige Klassenpunkte, XP, Items, Token oder Nodezustände durch erneute Browseranfrage, doppelte Socket-Ereignisse oder Reconnect.
18. **Vergangenheit bleibt:** Frühere Würfel, ausgegebene Munition, gelöste Quests, geöffnete Türen, reale Node-/NPC-Aktionen und vorherige Inventartransfers bleiben als echte Spielweltzustände erhalten. Diese werden weder neu ausgeführt noch durch Schema-Migration zurückgesetzt.
19. **Spätere konkrete Umsetzung:** Regelwerksgenaue Feldkonverter, Migrationsdialoge, UI-Struktur, Batchgrößen, Speicher-/Retentionkonzepte, Backups, technische DB/API und MVP erst später konkretisieren, solange die obigen strukturellen Garantien eingehalten werden.

## 3. Verbindlicher Ablauf

**Publikation:** Eine Person mit 03.3-Publishrecht veröffentlicht eine neue gültige Charakter-/Klassen-/Regelversion. Bestehende CharacterInstances und ihre Versionreferenzen bleiben unverändert.

**Berechtigte Auswahl:** Der Actor darf eine definierte Auswahl konkreter Charakterinstanzen, deren alte zulässige Quellen und die Zielversionsreferenzen zur geplanten Migration angeben. Ein bloßer Klassenname oder eine fremde Character-ID verleiht keine Migrationsrechte.

**Typsicherer Entwurf:** Server erstellt anhand der gültigen Definitionsversionen ein Mapping und meldet explizit Konflikte bei Feldtypen, Splits/Merges, Skill-/Klassenabhängigkeiten, Punktekosten, Ressourcenlimits, ggf. fehlender Lizenz oder unsichtbaren Feldern. Keine echten Werte/Token/Items beim Berechnen dieses Plans verändern.

**Auswirkungsvorschau:** Berechtigte Personen sehen nur die für sie erlaubten Veränderungen und blockierenden Fragen. Eine Preview ist keine Vollsimulation vergangener Spielsitzungen und kein Commit.

**Commit:** Der VPS prüft erneut Identität, Kampagne, aktuelle Figuren- und Migrationsberechtigung, Quell-/Ziel-RulePack, gesicherte Vorlagen- und Feldtypen, CharacterRevision, Mappingentscheidungen, Event-/Item-/XP-Abhängigkeiten und ggf. SL-Freigabe. Nur dann wird die ausgewählte Figur in einer atomaren, idempotenten Transaktion migriert und eine aktuelle berechtigte Realtime-Projektion ausgeliefert.

**Abbruch/Fehler:** Kein teilweises Migrationsresultat, keine doppelte Fortschrittsvergabe, kein Überschreiben fremder Spielerwerte. Alte heute erlaubte Version bleibt zugeordnet, sofern nicht zwingende aktuelle Rechte sie begrenzen.

## 4. Konzeptioneller Umsetzungsplan

1. Gültige stabile Vorlagen-/Field-/Class-/Ability-/Skill-/Progression-/RulePackversionsreferenzen auf CharacterInstances und erworbenen Definitionen nachvollziehbar ablegen.
2. Eigenes migrationsberechtigtes API-/Server-Fachmodul und nichtweltwirksamen MigrationDraft mit charakterbezogenen Source-/Target-/Mapping-/Revision-Daten entwerfen; autorisierte Auswahl und Preview separat sichern.
3. Typisierte Feldkonverter und explizite Blocker für inkompatible Änderungen, unbekannte Zieldefinitionen, Ressourcengrenzen, Punkt-/Abilitykonflikte und ungelöste Abhängigkeiten konzipieren.
4. Vollständige Servervalidierung vor atomarem CharacterCommit inklusive Rule-/Asset-/Lizenz-/Actor-/Character-/TargetACL, Quelle/Ziel und aktueller Revision; idempotente und konfliktsichere Verarbeitung.
5. Regel-/Würfel-/Inventar-/Token-/Node-/Progression-Adapter so trennen, dass nur aktuelle erlaubte Definitionen auf **zukünftige Aktionen** wirken und alte reale Ereignisse unverändert bleiben.
6. Tests für gemischte Definitionen innerhalb einer Kampagne, mehrere Figuren, unzugängliche alte Version, SLAcl, unveröffentlichte Drafts, Cache-/CrossCampaign-Leak, zwei Browser und Reconnect planen.
7. Exakte UI/API/DB-/Converteralgorithmen später festlegen. Als nächste Architekturentscheidung **03.7** abgeleitete und berechnete Charakterwerte klären.

## 5. Fachliche Abnahmetests

| Fall | Erwartetes Ergebnis |
| --- | --- |
| Neue Version publiziert | Kein existierender Charakter wird ohne ausdrückliche Migration verändert |
| Feld „Technik“ umbenannt, stabile ID gleich | Kein Werteverlust, Referenz bleibt gültig |
| Attribut wechselt Zahl zu Text | Typprüfung und explizite Konversion oder Blocker |
| Altes Feld weg ohne Mapping | Kein stilles Löschen, Legacy-Lösung oder blockierter Commit |
| Klasse wird aufgespalten | Keine kostenlose Doppelvergabe alter Fähigkeiten |
| XP-/Punkteregel ändert sich | Keine rückwirkende doppelte Vergabe und kein ungeprüfter Punktabzug |
| Ressource erhält neues Maximum | Explizite gültige Mapping-/Bereichsentscheidung, kein stilles Clamping |
| Alte Figur A migriert, Figur B nicht | Beide behalten eigene passende Versionsbezüge |
| Unberechtigter Spieler will migrieren | Kein Commit und keine private Charakter-/RulePack-Preview |
| Vorlageneditor hat kein Migrationsrecht | Publish-/Editrecht allein ermächtigt nicht zur CharacterMigration |
| Temporär beherrschender Controller aus 03.2 | Kein automatisch erhaltenes Migrations-/Adminrecht |
| Geheime NPC-Felder im Mapping | Keine Freigabe an andere Spieler/Browser |
| Zielklasse ist unpubliziert oder Lizenz entzogen | Keine Migration auf unzulässiges RulePack |
| Alter Regelstand ist nicht mehr rechtmäßig nutzbar | Alte Aktionen bleiben gesperrt trotz Versionpin |
| Charakter ändert sich nach Preview | Stale-Zustand blockiert Commit bzw. erfordert neue Prüfung |
| Zwei Tabs senden denselben MigrationCommit | Höchstens eine erfolgreiche Operation, keine doppelten Fähigkeiten |
| Eine Figur aus einem Batch hat Fehler | Figur bleibt vollständig unverändert, keine Halbversion |
| Inventar/Token/Quest/Würfel bereits verändert | Keine Rückabwicklung oder Replay durch reine Schemamigration |
| Reconnect nach erfolgreichem Commit | Nur aktuelle autorisierte Figurenversion, kein zweiter Commit |
| CrossCampaign-RulePack-ID erraten | Kein Zugriff auf fremde Klassen/Regeldaten |

## 6. Beschlussgrenze und nächste Frage

**03.6 C verbindlich beschlossen:** Selektive, explizit genehmigte und typgeprüfte Migration bestehender CharacterInstances nach ausschließlich berechtigten Quell-/Zielversionen, mit Preview und klaren Blockern, pro Figur atomarem und idempotentem Commit. Kein stiller Werteverlust, kein doppelter Aufstieg/Item-/Würfel-/Weltcommit, keine versteckte SL-/NPC-Datenfreigabe. Bestehende gültige Charaktere können auf verschiedenen Versionen verbleiben.

**Nicht entschieden:** Konkrete numerische Mappingformeln, UI, technische Transaktions-/DB-/API-Schemata, Batchgrößen, Archivretention, MVP und spätere regelwerkspezifische Erweiterungen. Keine Softwareimplementierung.

## Nächste Entscheidung 03.7 – Wie werden abgeleitete Charakterwerte berechnet?

**Beispiel:** Eine Figur hat einen gespeicherten Stärkewert, einen Klassenbonus und ein ausgerüstetes Item. Daraus könnten regelwerksabhängig Angriff, Verteidigung oder Tragkraft entstehen. Wie werden solche Zusammenhänge grundsätzlich modelliert?

- **A – Nur manuell:** Kein strukturiertes Berechnungssystem. Berechtigte Spieler/SL tragen alle abgeleiteten Felder nach Bedarf selbst ein.
- **B – Beliebiger freier Code:** Vorlagen dürfen unbeschränkt ausführbaren Browser-/Servercode für Wertformeln verwenden, ohne Rechte-, Typ-, Zyklus- und Ressourcenprüfung.
- **C – Optionale, sichere typisierte Berechnungsregeln (Empfehlung):** Ein versioniertes Regelprofil kann definierte Felder, Skill-/Klassen-/Item-/Statuseffekte als typisierte Abhängigkeiten samt geprüften Formelausdrücken kombinieren. VPS prüft Rechte, Versionen, Typen, fehlende Quellen, Zyklen und Ressourcen; berechnete Werte ändern gespeicherte Basiswerte nicht und werden nur an Berechtigte projiziert. Manuelle Kampagnen können das System deaktivieren; konkrete Formeln/Defaults/UI später.
