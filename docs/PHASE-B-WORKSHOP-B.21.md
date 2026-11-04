# AdventureShift – Phase B, Beschluss B.21 C: isolierter Technikspike-Zweig mit selektiver geprüfter Codeübernahme

**Nachfolgender Beschluss B.22 C (04.11.2026):** [Später technisch geschützter Git-Hauptzweig mit scopegerechten Pflichtprüfungen und berechtigter B.12-/B.14-/B.15-Owner-/Security-/Contract-/Migration-/B.13-Reviewabnahme](PHASE-B-WORKSHOP-B.22.md). Kritische FAIL-/BLOCKED-/NOT_RUN-Gates sperren Codeintegration; Prüf- und CI-Schutzänderungen dürfen nicht unbemerkt eigene Kontrollen ausschalten. **Noch kein GitHub-Ruleset/Branchschutz/CI tatsächlich eingerichtet, keine B.11-/B.17-/B.18-/B.19-/B.20-Technikprobe ausgeführt.** Intern geprüfter Merge ist keine WorldAction und keine B.2-B-/B.8-/B.9-/14.6-/15.4-Produktivfreigabe. **Nächste Grundfrage B.23: Abschluss der Grundsatzplanung und Übergang zur echten isolierten technischen Umsetzung.**

**Stand:** 04.11.2026. **B.21 C vom Projektinhaber ausdrücklich beschlossen.**
**Status:** Verbindliche Grundstruktur für die spätere Git- und Entwicklungsorganisation. **Noch kein Spike-Branch oder Worktree angelegt, keine Buildpipeline/Branchschutzregel konfiguriert, keine B.17-Readiness real geprüft, kein B.11-Spike implementiert oder ausgeführt, keine B.12-Härtung, keine endgültige Stackentscheidung oder spielbare Version.**
**Entscheidung C:** Ungehärteter B.11-/B.19-Technikspike-Code entsteht auf einem **gezielt getrennten Experiment-Branch beziehungsweise eigenem Git-Worktree** und wird eindeutig als nur synthetisch und nicht produktionsfähig gekennzeichnet. Der gemeinsame Hauptbranch `main` bleibt die maßgebliche Beschluss-/Entwicklungsbasis, ohne pauschale Übernahme unvalidierter TestAuth-/FakeACL-/Fixture-/Debug-/WorldWriter-Abkürzungen. Die ursprünglichen Testbelege bleiben auf ihre exakten Commits, B.20-Builds und B.19-Testumgebungen rückführbar. **Nur einzeln geprüfte und nach B.12 gehärtete Komponenten** dürfen nach fachowner- und vertragsgebundener B.14-/B.15-Prüfung gezielt in die reguläre Entwicklungsbasis übernommen werden. Die Übernahme ist weder ProductRelease noch Migration oder echte WorldAction.
**Unveränderte V1-Grenzen:** Vollständig eigenständig auf einem VPS betreibbar; Spieler und SL in getrennten Browsern; **genau ein aktiver Spielleiter und eine kanonische CampaignWorld pro Kampagne**; genau eine autorisierte 14.13-WorldWriterAuthority. Browser, Branch, Git-Merge, Testoperator und VPS-Host erhalten keine zusätzlichen GM-/Actor-/Owner-/Source-/History-/Privacy-/World-/Securityrechte.
**Verweise:** [B.1](PHASE-B-WORKSHOP-B.1.md) · [B.2](PHASE-B-WORKSHOP-B.2.md) · [B.3](PHASE-B-WORKSHOP-B.3.md) · [B.4](PHASE-B-WORKSHOP-B.4.md) · [B.5](PHASE-B-WORKSHOP-B.5.md) · [B.8](PHASE-B-WORKSHOP-B.8.md) · [B.9](PHASE-B-WORKSHOP-B.9.md) · [B.10](PHASE-B-WORKSHOP-B.10.md) · [B.11](PHASE-B-WORKSHOP-B.11.md) · [B.12](PHASE-B-WORKSHOP-B.12.md) · [B.13](PHASE-B-WORKSHOP-B.13.md) · [B.14](PHASE-B-WORKSHOP-B.14.md) · [B.15](PHASE-B-WORKSHOP-B.15.md) · [B.16](PHASE-B-WORKSHOP-B.16.md) · [B.17](PHASE-B-WORKSHOP-B.17.md) · [B.18](PHASE-B-WORKSHOP-B.18.md) · [B.19](PHASE-B-WORKSHOP-B.19.md) · [B.20](PHASE-B-WORKSHOP-B.20.md); [14.1](SICHERHEIT-WORKSHOP-14.1.md) · [14.2](SICHERHEIT-WORKSHOP-14.2.md) · [14.5](SICHERHEIT-WORKSHOP-14.5.md) · [14.6](SICHERHEIT-WORKSHOP-14.6.md) · [14.8](SICHERHEIT-WORKSHOP-14.8.md) · [14.9](SICHERHEIT-WORKSHOP-14.9.md) · [14.12](SICHERHEIT-WORKSHOP-14.12.md) · [14.13](SICHERHEIT-WORKSHOP-14.13.md) · [15.4](ERWEITERUNGEN-WORKSHOP-15.4.md).

## 1. Welche Trennung ist wirklich verbindlich?

1. **Getrennter Entwicklungsstand:** B.11-Probecode, synthetische Testhilfen, begrenzte experimentelle Session-/Source-/World-Fakes und riskante technische Alternativen dürfen auf einem verknüpften, aber klar getrennten Spike-Zweig erarbeitet werden. `main` muss sich ohne diese unausgereiften Teile weiterplanen und entwickeln lassen.
2. **Worktree ist keine Sicherheitsgrenze:** Ein eigener Git-Worktree oder Branch trennt Arbeitsstände, **nicht** automatisch Datenbanken, Secrets, Steamkonten, VPS-Zugänge, Kampagnenwelten, Netzwerkdienste oder Berechtigungen. B.17-/14.8-Isolation und B.19-Lokal-/Staging-Trennung sind weiterhin separat nachzuweisen.
3. **Keine ungeprüfte Auslieferung:** Der Experiment-Zweig darf keinen produktiven Deploymentkanal, keine automatische LiveCampaign-Migration und keine Berechtigung zum `main`-Release durch bloßen Branch-Namen oder grünen Mock-Test erhalten. CI-/Deploy-Token, StagingCredentials und Produktivschlüssel bleiben geschützt und fachlich getrennt.
4. **Versionierte Belege statt Branchgefühl:** Spike-Hypothese, B.10-ADR-Kandidat, Commit-/Tree- und B.20-Artifact-/BuildDigest, Schema-/Fixture-/Dependency- und B.19-Stage-Evidence müssen exakt miteinander verbunden bleiben. Ein nachträglich verschobener BranchHead ändert die geprüfte Vergangenheit nicht.
5. **Keine pauschale Branch-Übernahme:** Ein erfolgreicher B.11-Spike beweist nur die tatsächlich geprüften Risiken; es wird **nicht** der gesamte Spike-Branch ungeprüft nach `main` gemergt. Geprüfte Codeteile, Contracts, Tests und redigierte technische Belege können **selektiv** nach B.12/B.14/B.15 übernommen werden.
6. **Unveränderte Entscheiderrechte:** Ein technischer Reviewer darf nach geltendem Entwicklungsprozess Code beurteilen, erwirbt dadurch aber keinen GM-/Host-/Actor-/Privacy-/Support-ContentRead oder 02.99-/14.12-WorldWrite. Fachliche Beschlussänderungen folgen B.16 und gegebenenfalls B.14.

## 2. Planungsobjekte für Zweig, Evidenz und Übernahme (Arbeitsnamen)

| Arbeitsobjekt | Zweck / Trennlinie |
|---|---|
| **SpikeBranchScope / WorktreeBinding** | Zuordnung des isolierten Experimentzweigs zu B.11-Hypothese, B.18-Kandidatenpfad und B.17-/14.8-Testscope; noch keine tatsächliche Branchanlage |
| **SpikeCommitRef / BuildArtifactEvidence** | Unveränderlich verweisbarer GitCommit, getesteter B.20-Build-/Schema-/Fixturestand und echte B.19-L-/V-Testbelege |
| **TestOnlyBoundary / NoProdPolicy** | Kennzeichnung synthetischer Account-/GM-/Actor-/Source-/World-/Key-/Media-/Fixture-/Debugpfade und Sperre produktiver Secret-/Worldzugriffe |
| **ComponentPromotionCandidate** | Ein klar abgegrenztes geeignetes Code-/Contract-/Teststück mit überprüfbarer Herkunft; nie pauschal der komplette Branch |
| **HardeningAndAcceptanceMatrix** | B.12-Security-/Auth-/Source-/Owner-/Privacy-/License-/World-/Receipt-/Recovery-/Maintenance-Prüfungen plus B.14-/B.15-Consumer-/End-to-End-Gates |
| **ReviewDisposition / IntegrationEvidence** | `REJECT`, `REWORK`, `ACCEPT_HARDENED` oder `BLOCKED`; konkrete positive/negative Prüfungen zum übernommenen Code und getrennte technische Reviewnachweise |
| **MainBaseline / PromotionTrace** | Nachvollziehbarer Übergang der tatsächlich akzeptierten einzelnen Dateien/Änderungen auf den offiziellen Git-Stand, mit Revisions-, Reviewer- und Regressionsevidenz |
| **ExperimentCleanupRecord** | Sicheres Entfernen synthetischer Testdaten/Keys/Sessions/Jobs gemäß 14.8; historische redigierte Nachweise bleiben zulässig aufbewahrt, kein LiveWorldReset |

Die Begriffe sind **Git-/Entwicklungsartefakte**. B.21 verlangt weder jetzt ein neues Repository, noch eine zusätzliche World-, Incident-, Build- oder Plugin-Engine. Konkrete Branchbezeichnungen, GitHub-Schutzregeln, CI-Werkzeuge und Reviewerzahlen werden erst beim tatsächlichen Umsetzungsbeginn festgelegt.

## 3. Späterer sicherer Ablauf

1. **Noch vor Branchanlage:** B.18-Kandidaten-Shortlist tatsächlich prüfen, B.17-Readiness ehrlich bewerten, B.11-Minimalplan und B.19-/14.8-Umgebungsisolation festlegen. Dokumentation auf `main` bleibt unabhängig davon weiterhin möglich.
2. **Isolierten Zweig für die Probe anlegen:** Von einer bekannten, eindeutigen Baseline starten, ausschließlich künstliche Testidentitäten und getrennte Store-/Session-/Source-/World-/Media-/Key-Bezüge verwenden. Debug-/TestOnly-Grenzen explizit kennzeichnen, keine Produktiv-Credentials.
3. **Minimalen sicheren Kern tatsächlich bauen:** Getrennter GM-/Player-Browser, CurrentACL, erlaubter/verbotener DomainCommand, eine echte CampaignTestWorld mit 14.12-/14.13-WorldTransaction, OriginalOperationReceipt, Viewerprojektion, Reconnect und alle B.11-Negativfälle.
4. **Lokal und VPS separat messen:** B.19-Stufen mit unveränderlicher B.20-Build-Provenienz, getrennten synthetischen Fixtures, tatsächlichen L-/V-Ergebnissen, Revoke-/WriterFence-/Restart-/Duplicate-/LostAck-/Outbox-Testevidenz.
5. **Befund und ggf. Alternativprobe fixieren:** PASS, FAIL, NOT_RUN und BLOCKED an exakte Versionsstände binden; B.10-ADRs nur mit tatsächlichen Ergebnissen, B.16 bei untragfähigen Verträgen. Keine „grüne“ Autorität allein durch einen PR-Status.
6. **Selektive Härtung:** Geeignete Komponenten nach B.12 auf produktionsfähige Auth-/Session-/Source-/Owner-/Privacy-/World-/Receipt-/License-/Error-/Service-/Monitoringverträge bringen. TestOnly-Bypasses dürfen nicht über Standardwege in Produktivbuilds erreichbar sein.
7. **Vertrag und Verbraucher erneut testen:** B.14-Versionen, B.15-Beschlussabdeckung, B.13-Vertikalschnitt, konkrete positive und negative Tests **am gehärteten Integrationskandidaten**; Spike-Evidenz ersetzt keine neue Übernahmeprüfung nach Codeänderung.
8. **Gezielt in `main` aufnehmen:** Nur technisch freigegebene Inhalte über nachweisbaren Review-/Merge- oder Patchprozess. Ein Code-Merge ist **kein** B.2-B-Spielrelease, keine LiveMigration, keine RulePack-/Pluginaktivierung und keine 14.6-/15.4-Deploymentfreigabe.
9. **Experiment separat schließen/aufbewahren:** Temporäre Fixtures/Keys/Stores nach 14.8-/14.5-Policies bereinigen, sinnvolle redigierte Prüfbelege/ADRs versioniert erhalten. Nicht geeignetes Experiment muss nicht in `main` umbenannt oder integriert werden.

## 4. Negative Nachweise für die spätere Git-/Integrationsprüfung

| Konstellation | Erforderliche Folge |
|---|---|
| Worktree benutzt dieselbe produktive Datenbank oder Secretdatei wie der Hauptzweig | **BLOCKED**; Branch-/Worktree-Trennung ist keine Sicherheitsisolation |
| Spike-Branch enthält FakeAuth-AllRead und wird vollständig in `main` gemergt | Übernahme verweigern; nur gehärtete, eigens geprüfte Teile übernehmen |
| Lokal grüner Mock-Test, aber B.11-WorldRevision/OriginalReceipt nie real gemessen | `NOT_RUN`/Blocker, kein gehärteter Kern und keine Testfreigabe |
| Positiver B.11-Teststand, nach Härtung änderte sich ACL- oder WriterFence-Code | Neue Buildidentität und Pflichtregression; ursprüngliches PASS gilt nicht pauschal für den Umbau |
| Merge enthält neue API-/Schema-/RulePack-/Eventsemantik ohne B.14-Folgenprüfung | Contract-/Consumer-/Migration-Gate blockiert die Übernahme |
| Staging-Deployment startet versehentlich einen produktiven WorldWriter oder kopiert Session-/Keys | Sicherheitsverstoß, 14.8-Stage blockieren; keine LiveWorld-Wirkung durch Test |
| Browsercache zeigt GM-/NPC-/Quest-/PlayerSecrets an unberechtigte Player | B.5-/14.x-Security-FAIL, unabhängig von der Git-Branch- oder CI-Meldung |
| Verlorener Ack erzeugt beim Reconnect zweite WorldAction | B.11-/14.12-FAIL, keine Freigabe über alternative Teststatuswerte |
| Ein Entwickler ändert fachliche Vorgaben im Merge ohne neue B.16-Entscheidung | Entscheidung offen, Merge fachlich blockiert |
| Experiment-Code ist geprüft, R1/R2-/NPC-/Combat-/Inventory-/Quest-Breite fehlt | Intern begrenzte B.11-Evidenz möglich; **keine** B.2-B-/B.8-/B.9-Spielreleasefreigabe |
| Branchbezeichnung oder Git-Tag behauptet `stable` | Keine tatsächliche 14.6-/15.4-Produktivfreigabe ohne separate echte Gates |

## 5. Historische Anschlussfrage B.22 (inzwischen C beschlossen)

**B.21 C ist beschlossen und dokumentiert; es wurde dadurch noch kein separater Spike-Branch erzeugt und keine technische Schutzregel tatsächlich aktiviert.** B.11/B.17/B.18/B.19/B.20 bleiben ohne ausgeführte Proben beziehungsweise Builds. B.12 C verlangt weiterhin tatsächliche Produktionshärtung vor selektiver Codeübernahme, B.2 B die umfassende erste Spielversion und B.8/B.9 die realen Release-Gesamtgates. Es wird kein neuer Zweitwriter, keine verpflichtende externe Cloud, kein dauerhafter ChatDraft entgegen 02.118 A und keine neue automatische IncidentCase-Engine entgegen 14.15 A eingeführt.

### B.22 – Wie wird der offizielle Git-Hauptzweig gegen fehlerhafte Integrationen geschützt, wenn die ersten echten Implementierungsaufträge beginnen?

- **A – Manueller Merge ohne feste Pflichtnachweise:** Entwickler prüfen nach eigenem Ermessen. Schnell, aber B.12-/B.14-/B.15-Fach- und Sicherheitsgates lassen sich leicht übersehen.
- **B – Hauptzweig bis zur vollständigen B.2-B-Spielversion generell für jede Codeänderung sperren:** Verhindert frühe Integrationen, widerspricht aber der unter B.1/B.13 beschlossenen schrittweisen geprüften Entwicklung und führt zu großen risikoreichen Zusammenführungen.
- **C – Geschützter Hauptzweig mit passenden verpflichtenden automatischen Prüfungen und begründeter fachlicher Reviewfreigabe (Empfehlung):** Ein B.15-Entwicklungsauftrag darf nur nach zum Änderungsumfang passenden Build-/Lint-/Test-/Security-/License-/Contract-/Migration-/B.13-Regression-Nachweisen und zuständiger Reviewentscheidung integriert werden. Kritische FAIL/BLOCKED/NOT_RUN werden nicht als PASS behandelt; technische Schutzmaßnahmen können nicht heimlich mit dem zu prüfenden Code abgeschaltet werden. Gleichzeitig darf ein interner Merge ausdrücklich **kein** B.2-B-/B.8-/B.9-/14.6-/15.4-StableRelease sein. Konkrete CI-Tools und Branch-Schutzoptionen beim Implementierungsbeginn festlegen.
