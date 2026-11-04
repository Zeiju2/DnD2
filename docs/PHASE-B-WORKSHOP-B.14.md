# AdventureShift – Phase B, Beschluss B.14 C: zentrale versionierte Fachvertragsänderungen mit Verbraucherregression

**Nachfolgender Beschluss B.19 C (04.11.2026):** [Zweistufiger echter B.11-Techniktest: zuerst reproduzierbarer synthetischer LOCAL_DEV-Vertikalschnitt, dann gleicher geprüfter Teststand auf 14.8-isolierter Einzel-VPS-/Staging-Umgebung](PHASE-B-WORKSHOP-B.19.md). Eigene Environment-/Session-/World-/Receipt-/Key-/Media-/Backup-/Network-Sicherheitsgrenzen, aktuelle GM-/Actor-/Source-/History-/Privacyrechte, reale WriterFence-/Duplicate-/LostAck-/Revoke-/Reconnect-/Restart-/Outbox-Negativprüfungen und getrennte Build-/DB-/Browser-Evidenz in beiden Stufen. **Kein VPS-Test ohne wirksame Isolation; lokale PASS-Ergebnisse belegen keine Staging-Erfüllung. B.17-Readiness und B.11-Tests sind weiterhin nicht ausgeführt, B.18-Kandidaten nicht bewertet; keine Produktionsfreigabe.** **Nächste Grundfrage B.20: identische reproduzierbare Artefakte und sichere Umgebungskonfiguration.**

**Nachfolgender Beschluss B.18 C (04.11.2026):** [Kleine risikogebundene Technik-Shortlist und ein primärer isolierter B.11-P1/P2/P3-Testpfad mit nur gezielt nötigen Alternativproben und versionierten B.10-ADRs](PHASE-B-WORKSHOP-B.18.md). Serverautorität, 14.12-WorldTransaction-/OriginalReceipt, 14.13-SingleWriter/Fence, aktuelle Auth-/GM-/Actor-/Source-/History-/Privacy-/Viewerrechte, SingleVPS, Lizenz, Wartung und Recovery sind verbindliche Eignungsgrenzen. **Noch keine Kandidaten recherchiert, kein Stack final gewählt, B.17-Readiness nicht ausgeführt, B.11-Spike NOT_RUN, B.12-/B.13-Produktion nicht freigegeben.** Keine parallelen vollständigen Full-Stacks und kein B.2-/B.8-/B.9-/14.6-/15.4-Release durch Spikeerfolg. **Nächste Grundfrage B.19: getrennte lokale und VPS-/Staging-Testausführung.**

**Nachfolgender Beschluss B.17 C (04.11.2026):** [Begrenzter Architektur-/Sicherheits-Readiness-Check vor der ersten echten B.11-P1/P2/P3-Technikprobe](PHASE-B-WORKSHOP-B.17.md). Testscope, B.10–B.16-Verträge, 14.8-synthetische Isolation, Kandidaten, echte WorldWriter-/CurrentACL-/OriginalReceipt-/Audience-/Revoke-/Reconnect-/Recovery-Positiv-/Negativkriterien und redigierte Evidenz vor Testbeginn prüfen. **Preflight nur geplant, nicht ausgeführt; B.11 weiterhin NOT_RUN, B.12 nicht gehärtet, kein Stack und kein B.2-Spielrelease freigegeben.** Keine Vollplanung aller UI-/RulePack-Feindetails und keine produktiven Testdaten. **Nächste Grundfrage B.18: begrenzte Auswahl und Prüfung der Technik-Kandidaten.**

**Nachfolgender Beschluss B.16 C (04.11.2026):** [Gezielte versionierte Prüfung und begrenzte Sperre bei Beschlusswidersprüchen, widerlegten technischen Annahmen oder sicherheitskritischen Vertragslücken](PHASE-B-WORKSHOP-B.16.md). Bestehende Entscheidungen bleiben bindend; materielle Abweichungen brauchen eine ausdrücklich zuständige Fachentscheidung sowie gegebenenfalls B.14-Impact-/Migration-/ConsumerRegression. Unabhängige sichere B.13-/B.15-Arbeiten dürfen fortfahren. Keine globale neue Incident-/WorldEngine, keine zusätzlichen GM-/Actor-/Source-/Privacyrechte und keine Worldaktion durch Konfliktstatus. **B.11 weiterhin nur geplant, B.12 ungehärtet, B.13–B.15 nicht implementiert; B.2-/B.8-/B.9-/14.6-/15.4-Gates bleiben Pflicht.** **Nächste Grundfrage B.17: Readiness-Grenzen vor dem ersten echten Technikspike.**

**Nachfolgender Beschluss B.15 C (04.11.2026):** [Kleine versionierte, an bestehende Beschlüsse gebundene Entwicklungsaufträge mit B.4-/B.14-Owner-/Contractversion, Abhängigkeiten, Rechten, fachlichen Positiv-/Negativtests und tatsächlicher Evidenz](PHASE-B-WORKSHOP-B.15.md). Umsetzungsdetails nur bei anstehendem B.13-Inkrement festlegen; keine unabhängigen Schatten-To-dos und keine vorzeitige vollständige UI-/Regel-Feinplanung. **B.11-Spike ist ungetestet, B.12 nicht gehärtet, B.13/B.14 nur geplant.** Ein VERIFIED-Auftrag ist kein B.2-B-Release; B.8-/B.9-/14.6-/15.4-Gates und alle bisherigen Sicherheits-/Privacyrechte bleiben Pflicht. **Nächste Grundfrage B.16: Umgang mit entdeckten Widersprüchen und technisch nicht tragfähigen Annahmen.**

**Stand:** 04.11.2026. **B.14 C vom Projektinhaber ausdrücklich beschlossen.**
**Status:** Verbindliche Grundstruktur für das koordinierte Ändern bereits integrierter oder künftig gemeinsam genutzter Fachverträge. **Nur Architekturplanung:** Noch keine B.11-Technikprobe ausgeführt, keine B.12-Produktionshärtung, kein finaler Stack, keine implementierten B.13-Slices und keine spielbare Produktversion.
**Entscheidung C:** Änderungen an getypten Referenzen, Commands, Events, Receipts, Domänen-, Projektions-, RulePack-, Source-, Speicher- und Modulverträgen durchlaufen **eine gemeinsame versionierte Impact-/Kompatibilitäts-/Sicherheitsprüfung**. Der für den Fachvertrag zuständige DomainOwner beschreibt die Änderung, die betroffenen Konsumenten, Übergangsstrategie und Nachweise; vor der Integration werden deren tatsächliche Browser-/Server-/WorldWriter-/Rule-/Node-/NPC-/Inventory-/Quest-/History-/Media-/Migration-Anwendungsfälle regressionsgeprüft. Kein unkontrolliertes unabhängiges Schnittstellenmanagement je Modul und kein lebenslanges Einfrieren der Erstversion.
**Unverändert:** Vollständig eigener VPS, getrennte SL-/Spielerbrowser, eine kanonische CampaignWorld, **genau ein aktiver Spielleiter je Kampagne** und genau eine autorisierte 14.13-WorldWriter-Generation. Keine zweite DomainEngine oder frei beschreibbare globale Welt. Verträge und Tests ersetzen keine aktuellen Auth-/GM-/Actor-/Source-/Owner-/History-/Privacyrechte und keine echten Domaincommits.
**Geltende Verweise:** [B.1](PHASE-B-WORKSHOP-B.1.md) · [B.2](PHASE-B-WORKSHOP-B.2.md) · [B.3](PHASE-B-WORKSHOP-B.3.md) · [B.4](PHASE-B-WORKSHOP-B.4.md) · [B.5](PHASE-B-WORKSHOP-B.5.md) · [B.7](PHASE-B-WORKSHOP-B.7.md) · [B.8](PHASE-B-WORKSHOP-B.8.md) · [B.9](PHASE-B-WORKSHOP-B.9.md) · [B.10](PHASE-B-WORKSHOP-B.10.md) · [B.11](PHASE-B-WORKSHOP-B.11.md) · [B.12](PHASE-B-WORKSHOP-B.12.md) · [B.13](PHASE-B-WORKSHOP-B.13.md); [14.1](SICHERHEIT-WORKSHOP-14.1.md) · [14.2](SICHERHEIT-WORKSHOP-14.2.md) · [14.6](SICHERHEIT-WORKSHOP-14.6.md) · [14.8](SICHERHEIT-WORKSHOP-14.8.md) · [14.12](SICHERHEIT-WORKSHOP-14.12.md) · [14.13](SICHERHEIT-WORKSHOP-14.13.md) · [15.2](ERWEITERUNGEN-WORKSHOP-15.2.md) · [15.4](ERWEITERUNGEN-WORKSHOP-15.4.md).

## 1. Fachowner, Änderungsvorschlag und zentrale Durchsicht

1. **Ein fachlich zuständiger Owner:** Der in B.4 zuständige Besitzer eines Domain-/Command-/Event-/Receiptvertrags definiert zulässige Invarianten. Gemeinsame Architektur- und Security-/Privacy-Grenzen werden bei der Änderung zentral nachgewiesen; eine technische Review-Freigabe erteilt weder einen GM-/Playergrant noch einen WorldCommit.
2. **Änderung als ausdrücklicher Vorschlag:** Ausgangsversion und Zielversion, Anlass, geänderte Feld-/Operation-/Semantik-/Policyteile, beanspruchte Scope-/Source-/History-/Rule-/Ownerrechte, Betroffene und Annahmen dokumentieren. Keine stillschweigende Neubedeutung bestehender OperationKinds.
3. **Verbrauchergraph statt bloßer Suche:** Abhängige DomainOwner, API-/WS-/Subscription-Verbraucher, Viewerprojektionen, RulePacks R1/R2, Node-/Trigger-/ActionProposal-Definitionen, NPC-/Combat-/Inventory-/Quest-/Turn-/Actor-/Character-Adapter, DefinitionPackages, Medienzugriffe, Persistenz/Outbox, Backup/Restore, Jobs, Debug-/Testwerkzeuge und bestehende Kampagnenpins erfassen, soweit tatsächlich betroffen.
4. **Änderungsklassen:** (i) nachweislich rückwärtsverträgliche Ergänzung, (ii) Verhalten/Sicherheitswirkung verändernde Änderung, (iii) Breaking Change mit nötigen Versions-/Migrationsgrenzen, (iv) dringliche Sicherheitskorrektur mit explizitem Revoke-/Compatibility-/Serviceverfahren. „Optionales Feld“ ist nicht automatisch semantisch oder sicherheitstechnisch rückwärtsverträglich.
5. **Centrale Entscheidungsstelle ohne Privilegienerhöhung:** Versionierter Contract-Review verbindet verantwortliche Fachowner mit Architektur-, Security-/Privacy- und Release-Gates, wo berührt. Das ist ein technischer Entwicklungsprozess, keine separate WorldOwner-Rolle und keine pauschale Host-/Support-/GM-Impersonation.

## 2. Getypte Planungsobjekte (Arbeitsnamen)

| Objekt | Bedeutung |
|---|---|
| **ContractIdentity / ContractRevision** | Stabile ID des B.4-Fachvertrags, verantwortlicher DomainOwner und unveränderliche Revision; Referenztypen und historische Bedeutungen nicht still umdeuten |
| **ContractChangeProposal / ChangeClass** | Ziel, Version, fachliche Änderung, neue/entfernte Capabilities und Einstufung ADDITIVE/BEHAVIORAL/BREAKING/SECURITY |
| **ConsumerImpactGraph** | Versionierte tatsächliche Producer-/Consumer-/RulePack-/UI-/Node-/World-/Source-/History-/Storage-/Extension-/Migration-Abhängigkeiten |
| **CompatibilityProfile / VersionWindow** | Deklarierte und geprüfte zulässige Writer-/Reader-/Client-/Schema-/RulePack-/Event-/Projection-Kombinationen, inklusive ausdrücklich verweigerter Mischstände |
| **MigrationPlan / SafePoint / RollbackEligibility** | Selektive berechtigte Umstellung mit Preflight, Testdatenisolierung, aktuellen Rechten, erwarteten Revisionen, Wiederaufnahme-/Abbruchgrenzen und Rückwärtskompatibilitätsbeleg |
| **ContractRegressionEvidence** | Positiv-/Negativ-/Mehrbrowser-/Restart-/Revoke-/Idempotenz-/History-/Privacy-/R1-/R2-Belege am exakten Build/Schema/RulePack als PASS/FAIL/NOT_RUN/BLOCKED |
| **ContractAcceptanceDecision** | Entwicklungstechnische Annahme, Nacharbeit, Sperrung oder Ablehnung mit nachweisbaren Prüfbelegen; **weder** DomainWorldReceipt **noch** ProductReleaseReceipt |

Diese Begriffe sind eine **Dokumentations- und Vertragsebene**. Sie benötigen keine neue allgemeine Workflow-, Migration-, Rule- oder WorldEngine und bestimmen keine endgültige API-/DB-/CI-Implementierung.

## 3. Kompatibilität und Versionen ohne Schattenwelt

- **Stabile Semantik:** Existing Command-/Event-/OperationId-/OriginalOperationReceipt-/WorldRevision-Werte dürfen nicht nachträglich anders interpretiert oder überschrieben werden; ein neues ContractVersion-Label repariert keine alte WorldAction. Legitime Korrekturen erfolgen ausschließlich über vorhandene fachliche 02.100-/14.12-Grenzen.
- **Rückwärtsverträgliche Erweiterung bevorzugt:** Geeignete additive, explizit versionierte Felder/Capabilities werden durch überprüfte Reader-/Writer-Kompatibilität und sichere neutrale Defaults eingeführt. Fehlt eine sichere Standardbehandlung, wird die Kombination abgelehnt, nicht im Browser erraten.
- **Breaking Changes:** Eigenständige Version, Migrationsplanung, gültiger Aktivierungspunkt, angemessene parallele **Lesekompatibilität** nur bei nachgewiesenen Rechten; kein unkontrolliertes DualWrite und kein zweiter CampaignWorld-/WorldWriter-Pfad. Alte und neue Vertragsstände werden nicht ohne Prüfung über dasselbe Event- oder RulePack-Profil gemischt.
- **Bestehende Kampagnen bleiben fixiert:** 15.2-/B.3-VersionPins von Campaign/RulePack/Extension/Definition und deren Source-/Lizenz-/Securityfences gelten fort. Technischer Buildwechsel migriert weder LiveCharacter-/Quest-/Item-/Turn-/NPC-/Traktorzustand noch GM-/Actor-/Playerrechte automatisch.
- **Historie und Audience:** Historische Events und OriginalReceipts bleiben mit ihrer ursprünglichen Provenienz/Version lesbar, soweit heute rechtlich und fachlich erlaubt. Ein neuer Serializer darf HistoryACL, Fog, KnownFacts, GM-/NPC-/QuestSecrets, private PlayerDMs oder SourceAudience nicht neu öffnen.
- **Fehlergrenze:** Nicht unterstützte Versionskombinationen und unzulässige Migrationszustände werden fail-closed, mit redigierten, nicht verräterischen Fehlresultaten abgewehrt; kein Deserialisierungsfallback auf globale ReadAll-/WorldWrite- oder unsichere FakeAuth-Modi.

## 4. Pflichtablauf einer gemeinsamen Vertragsänderung

1. **Basiskontrakt/Änderung identifizieren:** Autoritativer Owner und belegter Ausgangsstand einschließlich Live-/Test-/Pinned-Verbrauchern.
2. **Impact und Gefahr abbilden:** Getypte Reads/Writes, Auth-/Session-/GM-/Actor-/Owner-/Source-/Fog-/History-/Privacy-/Quota-Rechte, betroffene Rule-/Node-/World-/Receipt-/Outbox-/Asset-/Backup-/Migrationpfade.
3. **Verhalten und kompatible Versionen festlegen:** Additiv oder Breaking, zulässige Mischstände, Übergangsverträge/Adapter, Abschalt-/Revoke-/Rollbackgrenzen. Keine angenommene generelle Rückwärtskompatibilität ohne echte Tests.
4. **Isolierte Testmigration:** 14.8-synthetische Daten und berechtigte, ggf. redigierte Fixtures; keine unberechtigte Produktionsextraktion. Preflight und 14.6-/15.2-SafePoint-/Pinregeln bei betroffenen Bestandskampagnen.
5. **Owner- und Verbraucherregression:** Nicht nur die ändernde Komponente, sondern alle im Graphen betroffenen echten Domänen-/Browser-/WS-/DB-/Job-/RulePack-/Security-Konsumenten gegen denselben geprüften Revisionstand testen.
6. **Technische Annahme oder Blockade:** Nur beim nachweislich erfüllten Vertrag in die gemeinsame B.13-Entwicklungsbasis integrieren; offene FAIL/NOT_RUN/BLOCKED oder ungeschützte Secrets werden nicht als PASS umbenannt.
7. **Reale Produktivfreigabe separat:** 14.6-Deployment und tatsächliche 15.4-StableRelease-/08.3-/08.5-/B.8-/B.9-Gates gelten eigenständig. Kein ContractReview aktiviert LiveSession, RulePack, Extension, Handout, WorldAction, WorldRestore oder CampaignMigration.

## 5. Verbindliche Negativ- und Integrationstests

| Szenario | Gefordertes Verhalten |
|---|---|
| Neues Character-/Inventoryfeld verändert Node-/Questverbraucher | Jeder betroffene Verbraucher erhält geprüfte Version/Adapter; andernfalls Integrationssperre |
| Regelprofil R1 besteht, strukturell anderes R2 scheitert | R2-Negativbefund bleibt sichtbar; kein pauschaler Nachweis der Genre-/RuleNeutralität |
| Alter und neuer Browser empfangen unterschiedlichen Schema-/ProjectionStand | Nur deklarierte geprüfte VersionWindow-Kombination, kein Secret-Leak oder interpretiertes Fantasieereignis |
| Bestehende Kampagne mit altem gepinntem RulePack | Kein stilles Upgrade oder Daten-/Owner-/WorldUpdate; ggf. kontrollierte separate Aktivierung |
| Bereits committed WorldAction erhält neue Eventsemantik | Ursprüngliche WorldRevision/OriginalReceipt/History bleiben unverändert, kein erneuter Commit |
| Breaking Change während aktiver Session oder offener Operation | Berechtigter SafePoint/VersionFence und OriginalReceipt-Reconciliation; kein DoubleSubmit oder zweiter Writer |
| Entzogene Actor-/GM-/Session-/Sourceberechtigung trifft alten Reader | Neue Reads/Pushs/Writes sofort nach tatsächlich wirksamem Revoke sperren, auch bei alter ContractVersion |
| CrossStore-/Outbox-/Job-Verbraucher beim Schemawechsel nicht verfügbar | Keine fiktive globale Atomicity; späteres berechtigtes Delivery/Reconcile, keine wiederholte Domainwirkung |
| Rollback eines Builds bei bereits migrierten Daten nicht sicher | RollbackEligibility verweigern; kontrollierte Recovery statt erzwungenem Rückschreiben |
| Neuer Typ enthält geheime NPC-/Quest-/DM-Felder | Ohne aktuelle konkrete Source-/History-/AudienceACL keine Browser-/Cache-/Support-/Audit-Ausgabe |
| Test/CI auf Mock grün, echter Mehrbrowser-/VPS-Test offen | NOT_RUN/BLOCKED, keine technische oder produktive Gesamtfreigabe |
| Zwei Fachmodule beanspruchen dieselbe Weltaktion als Owner | Vertrag ablehnen, eindeutigen bestehenden DomainOwner/WorldWriter durchsetzen |

## 6. Abgrenzung und Ausführungsstatus

- **B.13 C** bleibt die schrittweise tatsächlich vollständig integrierte Entwicklung; B.14 koordiniert **Änderungen an gemeinsamen Verträgen**, nicht die Reihenfolge aller Features.
- **B.2 B** verlangt weiterhin eine vollautomatisiert integrierte erste Spielversion. Eine interne Contractversion oder Regression allein erfüllt weder die 12 B.8-Releasegates noch die R1-/R2-B.9-Prüfungen.
- **14.1–14.15, 09.7, 03.2, 12.x, 13.x und 15.1–15.4** behalten ihre separaten Fachrechte, Datenschutz-, Test-/Prod-, Key-, Chat-/Support-, Asset-/Media-, Source-, Steam-/Session-, GM- und Actorgrenzen. 14.15 A bleibt manuelle Incidentbehandlung; 02.118 A verbietet weiterhin persistente ungesendete ChatDrafts.
- **Kein automatisch freigegebener LiveChange:** Review, Schema-/Codegeneration, DryRun, Green CI, ADR und ContractAcceptanceDecision sind für sich keine World-, Roll-, Quest-, NPC-, Item-, Traktor-, Publish-, RulePack-/Pluginaktivierung oder LiveDeployment.
- **Noch offen für den Umsetzungsbeginn:** genaue Contract-/Schema-/Eventencodingformate, Versionssyntax, Kompatibilitätsfenster, Migrationstools, Latenz- und Testlimits, konkreter Reviewerprozess und CI-/Git-Verfahren. Die Grundstruktur ist verbindlich, nicht implementiert.

## 7. Historische Anschlussfrage B.15 (inzwischen C beschlossen)

### B.15 – Wie werden die bereits beschlossenen Architektur- und Fachanforderungen in tatsächlich umsetzbare, nachweisbar vollständige Entwicklungsaufträge überführt?

- **A – Entwicklungsaufträge frei und je Modul unabhängig beschreiben:** Schnell angelegt, aber Sicherheits-/World-/Owner-/RulePack-/Releasekriterien aus bestehenden Beschlüssen können fehlen oder sich widersprechen.
- **B – Vor dem ersten Code den gesamten Projektumfang bis zu allen UI-Details einfrieren:** Vollständige Planungsillusion, aber hoher Vorabaufwand, kein Raum für Ergebnisse der B.11-Technikprobe und spätere fachliche Konfiguration.
- **C – Kleine versionierte, beschlussverknüpfte Build-Aufträge mit Abhängigkeiten und echten Abnahmeevidenzen (Empfehlung):** Jede tatsächlich anstehende B.13-Implementierungsaufgabe referenziert ihre verbindlichen Fachbeschlüsse, B.4-/B.14-Owner-/Contractversionen, Security-/Privacy-/World-/Receiptgrenzen, Blocker, End-to-End-Positiv-/Negativtests und den separaten Freigabestatus. Nur unmittelbar nötige Umsetzungsdetails vor dem jeweiligen Schritt konkretisieren. Kein neues paralleles Fachmodell, keine vorgetäuschte B.2-Freigabe und keine unendliche Vorabfeinplanung.
