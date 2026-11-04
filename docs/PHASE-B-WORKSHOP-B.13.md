# AdventureShift – Phase B, Beschluss B.13 C: abhängigkeitssichere vertikale Fachintegration

**Nachfolgender Beschluss B.14 C (04.11.2026):** [Zentrale versionierte Fachvertragsänderungen mit DomainOwner-/ConsumerImpact-/Kompatibilitäts-/Migration-/Security-/Source-/History-/Privacy-/World-/OriginalReceipt-/Regressionsgates](PHASE-B-WORKSHOP-B.14.md). Fachverträge dürfen kontrolliert weiterentwickelt werden, ohne bestehende Kampagnenpins still zu migrieren, OriginalReceipts umzudeuten, unsichere DualWrites einzuführen oder eigene Fach-/WorldEngines zu erzeugen. **B.11 ist weiterhin nicht ausgeführt, B.12 nicht produktionsgehärtet und B.13 nicht implementiert.** Technische Contractfreigabe ersetzt weder echten fachlichen WorldCommit noch B.2-/B.8-/B.9-/14.6-/15.4-Releasegates. **Nächste Grundfrage B.15: versionsgebundene beschlussverknüpfte Entwicklungsaufträge.**

**Stand:** 04.11.2026. **B.13 C vom Projektinhaber ausdrücklich beschlossen.**
**Status:** Verbindliche Integrations- und Architekturgrundstruktur für die spätere Implementierung. **Noch kein B.11-Technikspike ausgeführt, keine B.12-Komponente produktionsgehärtet, keine Software als spielbar freigegeben und keine finale Stackwahl.**
**Entscheidung C:** Die Software wächst **nicht** als isoliert fertiggestelltes Gesamtbackend und **nicht** als vorgezogene Mock-Oberfläche. Nach tatsächlich geprüftem B.11-/B.12-Sicherheitskern entwickeln wir **risiko- und abhängigkeitsgesteuerte, funktionsfähige vertikale Fachinkremente**: jeweils passende eigene Browserhandlung/GM-/Player-Sicht, serverseitige fachliche Autorisierung und Regelprüfung, ein zuständiger DomainOwner, kanonische Transaktion/OriginalOperationReceipt, gezielte Realtime-/Media-/Historyprojektion, Persistenz und positive wie negative MultiBrowser-/Recoverytests.
**Releaseschranke:** Ein intern bestandenes Inkrement ist keine öffentlich oder produktiv freigegebene spielbare Version. **B.2 B** bleibt für den ersten Spielrelease verbindlich: echte, umfassend zusammenwirkende Node-/NPC-/Kampf-/Initiative-/Charakter-/Würfel-/Inventar-/Quest-/Regel-/Kartenfunktionen mit den bisherigen Rechten und **B.8/B.9**-Gesamtabnahmen.
**V1-Grenzen:** Selbst hostbarer Single-VPS, SL/Spieler in eigenen Browsern, **genau ein aktiver Spielleiter je Kampagne**, eine kanonische CampaignWorld und genau eine gültige WorldWriter-Autorität. Genres und RulePacks bleiben flexibel; aktivierte Module und Automatikmodi folgen B.3, ohne stilles Freischalten oder Schattenwelt.
**Querverweise:** [B.1](PHASE-B-WORKSHOP-B.1.md) (Inkremente) · [B.2](PHASE-B-WORKSHOP-B.2.md) (erster Spielrelease) · [B.3](PHASE-B-WORKSHOP-B.3.md) (Capabilities/Module) · [B.4](PHASE-B-WORKSHOP-B.4.md) (Fachowner/Contracts) · [B.5](PHASE-B-WORKSHOP-B.5.md) (projektiertes Realtime) · [B.6](PHASE-B-WORKSHOP-B.6.md) (Vorladen) · [B.7](PHASE-B-WORKSHOP-B.7.md) (Reconnect/Offline) · [B.8](PHASE-B-WORKSHOP-B.8.md) (Releasegates) · [B.9](PHASE-B-WORKSHOP-B.9.md) (R1/R2) · [B.10](PHASE-B-WORKSHOP-B.10.md) (ADR/Stack) · [B.11](PHASE-B-WORKSHOP-B.11.md) (Technikspike) · [B.12](PHASE-B-WORKSHOP-B.12.md) (Codeübernahme); [14.1](SICHERHEIT-WORKSHOP-14.1.md) · [14.2](SICHERHEIT-WORKSHOP-14.2.md) · [14.6](SICHERHEIT-WORKSHOP-14.6.md) · [14.7](SICHERHEIT-WORKSHOP-14.7.md) · [14.8](SICHERHEIT-WORKSHOP-14.8.md) · [14.9](SICHERHEIT-WORKSHOP-14.9.md) · [14.12](SICHERHEIT-WORKSHOP-14.12.md) · [14.13](SICHERHEIT-WORKSHOP-14.13.md).

## 1. Fester gemeinsamer Fach- und Sicherheitsweg

Eine externe Liveaktion durchläuft durchgehend **Browserverhalten/ActionIntent → serverseitige Auth-/Campaign-/GmEpoch-/Actor-/Owner-/Source-/History-/Fog-/Rule-/Quota-Prüfung → genau zuständigen fachlichen CommandOwner → tatsächlich zulässige DomainTransition → autorisierter 14.12-/14.13-WorldCommit → persistentes OriginalOperationReceipt → B.5/13.x-viewerberechtigte Projektion und Realtime-Zustellung**.

1. **Kein Clientzustand als Weltwahrheit:** UI, Canvas, Optimistic View, Debugfixture, Animation, vorab geladenes Asset, Browsercache und lokal bearbeiteter Entwurf sind keine WorldAction und keine zweiten Datenbanken.
2. **Keine Fachschattenengine:** Turn-/Action-/Rule-/Roll-/NPC-/Inventory-/Quest-/Character-/Node-/Traktorwirkungen führen nur über ihre vorhandenen Fachowner und den einen WorldWriter; CrossStore-Ausgaben über Outbox/Reconciliation statt erfundener globaler ACID-Transaktion.
3. **Rechte werden für jeden Slice vollständig geprüft:** Bereits früher berechtigte Daten/Requests können durch 09.7-GmEpoch-, 03.2-Actor-, Source-, Session-, Membership-, History-/Audience-, Rule-/Config- und Privacywechsel unzulässig werden. PendingCommit und Fanout beachten aktuelle Fences.
4. **Ein Scope-/Versionsmodell:** Kampagnen-, Regelwerks-, Fach-/Event-, Definition-/Asset-, Audience-, Source-/GM-/Actor- und Build-/Schema-Versionen werden passend mitgeführt. Ein Modul darf keine geänderten Definitionen an bestehende Kampagnen still weiterreichen.
5. **Nachwirkungsgrenzen:** Server-Receipt/WorldRevision statt WebSocket-Ack als tatsächlicher Erfolg; Wiederverbindung ermittelt den Originalstatus statt doppelt zu würfeln, eine Tür erneut zu öffnen oder Quest-/Item-/Traktoraktionen wieder auszuführen.

## 2. Typisierter Inkrementvertrag (Arbeitsnamen)

| Arbeitsobjekt | Aufgabe und verbindliche Grenze |
|---|---|
| **FeatureSliceDefinition** | Enge fachliche Nutzerwirkung (z. B. freigegebene Bewegung oder Node-Aktion), betroffene Domänen, getrennte GM-/Player-Flows; keine pauschale „fertige Engine“-Behauptung |
| **DependencyGraph / SlicePrerequisite** | Versionsgebundene erforderliche Core-/Owner-/Rule-/Capability-/Source-/World-/Viewer-/Asset-/Migration-/Securityverträge; unzulässige Kombination blockieren |
| **DomainOwnerPort / CommandContract** | Ein zuständiger fachlicher B.4-Port mit typisierten References, Request, ExpectedRevision, OperationId, Policy- und DomainResults |
| **CurrentAuthorizationSnapshot / RevocationFence** | Für echte Reads, Writes, Realtime, Media und Reconnect neu geprüfte Session-/GM-/Actor-/Member-/Source-/History-/Fog-/Rule-/Privacy-/Quota-Grenzen |
| **WorldTransactionBoundary / OriginalReceiptContract** | B.11/B.12-konformer 14.12-Commit über genau einen 14.13-WorldWriter; keine fachliche Nebenwirkung durch bloßes UI-/Config-/Publishereignis |
| **AudienceProjection / DeliveryContract** | GM-/Player-/Handout-/Preview-/Presentation-Projektionen getrennt, nur auf aktuellem Audience-/Asset-/History-/Source-Recht und ohne GM-/NPC-/Quest-/PlayerSecrets |
| **SliceEvidence / GateOutcome** | Belege am exakten Build-/Schema-/Fixture-/RulePackstand als PASS/FAIL/NOT_RUN/BLOCKED, inklusive Browser-/Server-/DB-/OriginalReceipt-/Negativfällen |
| **IntegrationDisposition** | Getrennt von StableRelease: intern integrierbar, nachzubessern, blockiert oder zurückgenommen; eine bestandene interne Prüfung erteilt keine 14.6-/15.4-Produktivfreigabe |

Dies sind planende Dokumentations-/Typbegriffe, **keine zusätzlichen frei ausführbaren Regel- oder Build-Engines**. Konkrete Dateistruktur, Toolchain, CI, Parameter und UI werden bei tatsächlicher Implementierung gewählt.

## 3. Abhängigkeitssichere Umsetzung ohne starre Fachmodulreihenfolge

- **Voraussetzung, keine optionale Abkürzung:** Zuerst B.10-Technologiekandidaten prüfen, B.11 echten sicheren WorldCommit-/Viewer-/Revoke-/Reconnect-Spike nachweisen und B.12 selektive Übernahme/härtende Integrationsfreigabe durchführen. Solange nicht ausgeführt, verbleibt die Arbeit **in der Planung**.
- **Pro Fachinkrement:** Einen begrenzten vertikalen Nutzungsfall wählen, der bestehende Core-/Auth-/World-/Rule-/Source-Ports **wiederverwendet**. Browserhandlung und Serverwirklichkeit gemeinsam integrieren, nicht durch später anzuschließende Dummyantworten vortäuschen.
- **Fachliche Abhängigkeiten statt willkürlicher Reihenfolge:** Actor-/Scene-/Rule-/Movement-/Roll-/Turn-/Node-/Npc-/Combat-/Inventory-/Quest-Schnittstellen können sich nach belegten Voraussetzungen staffeln. Ein anstoßender Node darf nur einen passenden, vom zuständigen Fachowner akzeptierten Command vorschlagen und keine private Zweitlogik schreiben.
- **Kampagnenkonfiguration und Automatisierung:** B.3 OFF/MANUAL/GM_APPROVAL/AUTOMATIC sowie gültige Scene-/Group-/Actor-/Node-Ausnahmen wirken bei jedem Inkrement. Fehlt ein optionales Modul, wird der abhängige Pfad gesperrt oder zulässig manuell behandelt; es gibt kein stilles Auto-Enable und keine automatische WorldAction.
- **Zwei RulePack-Profile:** R1 und R2 nach B.9 müssen spätestens beim integrierten B.8-Release tatsächlich durchgehen. Bereits früher darf ein Slice keine nur für Fantasy/W20/HP/Klassen gültige Pflichtstruktur in den Kern einführen; passende Einzeltests nach Reifegrad.
- **UI, Assets und Performance:** Gemeinsame 13.x-Semantik, Source-/Viewer-Projektionen, B.6-/12.x-berechtigtes Vorladen und 12.7-Quota-/Abuse-Schutz werden nach Bedarf an echte Nutzeraktionen gebunden. Vorweggenommene Oberfläche ohne reale Vertragsprüfung zählt nicht als fertig.
- **Rückwärtsverträglichkeit:** Änderungen an gemeinsam genutzten Verträgen erfordern Betroffenheitsanalyse, versionierte Contract-/Migrationstests und erneute Prüfung der bereits integrierten Verbraucher. Produktionsdaten, gepinnte Kampagnen und 14.6/15.2-Freigaben dürfen nicht durch Entwicklungsfortschritt automatisch verändert werden.
- **Priorisierung bleibt beweglich:** Eine spätere konkrete nummerierte Reihenfolge, Aufteilung der Slices, Framework-, Testtool-, Workstream- oder Zeitplanung wird erst nach den entsprechenden Belegen und bei tatsächlichem Entwicklungsbeginn festgelegt. Dieser Beschluss ist kein verpflichtender Wasserfallplan.

## 4. Slice-Gates – Mindestnachweise für jede integrierte Fachwirkung

1. **Contract/Dependency:** Versionierte Fachreferenzen, zulässige aktivierte Capabilities und der **eine** relevante Fachowner sind geprüft. Keine unsichere „TODO-Allow“-Abkürzung.
2. **Berechtigte und unberechtigte Browser:** Getrennte aktuelle GM-/Player-Sessions; nur zulässige Felder, Ziele, Resultate und Medien. Verbotene Aktionen/Source-/Fog-/Historyabfragen geben weder Daten noch verräterische Counts/Reasons preis.
3. **Echte Fachwirkung:** Der erlaubte Command wird genau einmal autorisiert, erzeugt nur die tatsächlich gebotenen Domain-/World-/Receipt-Effekte; unzulässiger Command ohne WorldRevision-/Resource-/Quest-/NPC-/Roll-/Itemänderung.
4. **Konkurrenz/Netzfehler:** Gleiche OperationId, alte Revision, LostAck, Outbox-/WS-Gap und Disconnect führen zu nachvollziehbarem OriginalReceipt-/Audience-Reconcile, nicht doppelter Wirkung.
5. **Revocation/Ownership:** Session-, GM-, Actor-, Source-, Rule-/Config-/Membership-Änderung zwischen Read, Pending und Commit sperrt danach unzulässige Zugriffe; kein Mehr-GM oder Zweitwriter.
6. **Persistenz/Recovery:** Echte DB-/World-/Receipt-/Fence-Beharrlichkeit, Neustart und zulässige Recovery, Backup-/Migration-/Rollback-Kompatibilität soweit für den Slice berührt, ohne stille Wiederausführung.
7. **Modulgrenzen und Neutralität:** Deaktivierte Abhängigkeit bleibt tatsächlich inaktiv; sinnvolle R1-/R2-Contractchecks, keine fixen Inventarslotzahlen, Klassenpflicht oder Regeltextlizenzannahme.
8. **Belegklarheit:** PASS nur bei tatsächlich ausgeführtem und reproduzierbarem Test gegen den exakten integrierten Stand; FAIL, BLOCKED oder NOT_RUN bleiben offen. Ein grün gemockter UI-/UnitTest ersetzt keine reale Integration.

Die entsprechenden internen Gates **ergänzen**, aber ersetzen **nicht** die 12 B.8-Gesamtgates, B.9-Regelwerksneutralitätsabnahme, echten Browser-/VPS-/Backup-/Privacyprüfungen und 14.6-/15.4-Releasefreigaben.

## 5. Negative Sonderfälle und Ausschlüsse

- **Browser zeigt bereits Erfolg, Commit scheitert:** Anzeige korrigiert nach OriginalReceipt; keine neue Operation als „Reparatur“ ohne bewusste Autorisierung.
- **Inkrement besitzt einen Node-Trigger, aber Questmodul fehlt:** Kein stilles Quest-WorldEvent; Pfad bleibt blockiert oder zulässig manuell, selbst wenn ein Node-Editor schon existiert.
- **SL sieht in der eigenen Vorschau geheime Inhalte:** Ein Player- oder Zuschauerbrowser darf diese nicht über gemeinsame Deltas, Eventbezeichner, Medienpfade oder Browsercache erhalten.
- **Gruppe wechselt gültig von freier Bewegung zu Turnmodus:** 04.1-/07-/02-Owner- und Turnrechte verwenden genau einen kanonischen Weltstand und dieselben erlaubten Round/Transition-Receipts.
- **Temporäre 03.2-Kontrolle oder Spielerpause/Rückkehr:** Actor-/Membershiprechte neu prüfen; gespeicherte World-/Characterhistorie nicht pauschal kopieren oder neu auslösen.
- **WorldWriter fällt aus, Featurecode retryt:** Keine Schattenwelt, kein eigenständiger Ersatzwriter, keine neue OriginalOperationId für bereits unbekannt/erfolgreich gesendete Aktion.
- **Audio-/Plugin-/Charakterersteller als spätere optionale Fachbreite:** Architekturanschluss ist möglich, aber kein Zwang zur sofortigen vollständigen Spezialumsetzung; 15.1–15.4-VersionPins und rechtlich erlaubte Quellen gelten weiterhin.
- **Chat und Offline:** 02.118 A verbietet weiter dauerhafte ungesendete ChatDrafts/AutoSend; 14.15 A bleibt manuelle Incidentbehandlung, kein neuer Automatismus.
- **Interner Slice als vermeintlich „spielbarer“ Release:** Blockieren, solange umfassende B.2-B-/B.8-/B.9-Gates fehlen. Kein FeatureFlag, Optimistic UI oder erfolgreicher Teiltest ersetzt den StableRelease.

## 6. Umsetzungsschritte und Status

1. Dokumentierte B.11-Probe tatsächlich durchführen; getrenntes pass/fail/not-run-Ergebnis und B.10-ADRs sichern.
2. Komponenten nach B.12 gezielt härten, integrieren oder ersetzen; keine TestOnly-Identitäten als reale Zugangskontrolle einsetzen.
3. Überprüfbare gemeinschaftliche B.4-Owner-/14.12-World-/14.13-Writer-/B.5-Viewer-Ports und testbare Browser-/Server-/Persistenzpfade etablieren.
4. Ein geeignetes erstes fachliches Inkrement nach **echten** Abhängigkeiten wählen, vollständigen Nutzerpfad integrieren, inklusive Verweigerungen und Fehlerfällen.
5. Wiederholte Regression bei jeder Vertrags-, Policy-, RulePack-, Schema- oder Sourceänderung; lokale Erfolge dokumentieren, Defizite nicht ausblenden.
6. Bis zur vollständig integrierten B.2-B-Fachbreite fortfahren; B.8-/B.9-/14.6-/15.4-Gates real durchlaufen und **erst danach** gesonderte Produktfreigabe entscheiden.

**Später festzulegen:** genaue Slice-Reihenfolge, Frameworks, Datei-/Paketgrenzen, Browserframework, APIs, CI- und Testtools, Releasezielwerte, Art der Teamaufteilung, UI-Defaults und algorithmische Spezialfälle. Kein neuer produktiver Commit oder Prototyp durch diese Dokumentation.

## 7. Historische Anschlussfrage B.14 (inzwischen C beschlossen)

### B.14 – Wie werden Änderungen an bereits gemeinsam genutzten Fachverträgen während der schrittweisen Integration koordiniert?

- **A – Jedes Fachmodul passt seine Schnittstellen selbst an:** Schnell lokal, aber widersprüchliche Versionen, doppelte Fachlogik und undurchsichtige Regressionen können unbemerkt entstehen.
- **B – Alle bestehenden Schnittstellen ab dem ersten Inkrement dauerhaft einfrieren:** Stabilität auf dem Papier, aber erkannte Architektur- oder Regelwerksprobleme erzwingen riskante Umwege und Schattenmodelle.
- **C – Zentrale versionierte Contract-Änderungsprüfung mit rückwärtsverträglichen Übergängen und Verbraucherregression (Empfehlung):** Verantwortlicher DomainOwner definiert eine Änderung und deren Auswirkungen; alle betroffenen Browser-/Server-/RulePack-/Node-/Source-/History-/World-/Receipt-/Migration-Verbraucher werden im gemeinsamen Integrationsstand getestet. Inkompatibles nur nach versionierter Migration, SafePoint, aktueller Autorisierung und erforderlicher Freigabe. Alte Kampagnenpins werden nicht still umgeschrieben; echte WorldActions brauchen weiterhin ihre separaten Commits. Keine zweite Engine oder unkontrollierte Parallelmigration.
