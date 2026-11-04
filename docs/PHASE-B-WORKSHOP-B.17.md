# AdventureShift – Phase B, Beschluss B.17 C: begrenzter Architektur- und Sicherheits-Readiness-Check vor der ersten echten Technikprobe

**Nachfolgender Beschluss B.20 C (04.11.2026):** [Reproduzierbarer B.11-/B.19-Testbuild mit unveränderlicher Source-/Dependency-/Toolchain-/Schema-/Fixture-Provenienz, BuildDigest und getrennten sicheren LOCAL_DEV-/ISOLATED_VPS_STAGING-Einstellungen](PHASE-B-WORKSHOP-B.20.md). Wo zielkompatibel dasselbe Artefakt verwenden, bei Windows-/Linux-/Plattformunterschieden separate Artefakte gleicher nachweisbarer Sourcebasis mit unabhängigen Stage-/Contracttests. Geheimnisse und ProdDaten niemals im Build/Git/Testlog, kein stiller Dependency-/Schema-/SecurityConfigDrift. **Noch kein Build/Preflight/Spike real ausgeführt oder Stack festgelegt; kein automatischer WorldEffect, Codeimport oder B.2-/B.8-/B.9-/14.6-/15.4-Release.** **Nächste Grundfrage B.21: Isolierung von Technikspike-Code im Git-Entwicklungsprozess.**

**Nachfolgender Beschluss B.19 C (04.11.2026):** [Zweistufiger echter B.11-Techniktest: zuerst reproduzierbarer synthetischer LOCAL_DEV-Vertikalschnitt, dann gleicher geprüfter Teststand auf 14.8-isolierter Einzel-VPS-/Staging-Umgebung](PHASE-B-WORKSHOP-B.19.md). Eigene Environment-/Session-/World-/Receipt-/Key-/Media-/Backup-/Network-Sicherheitsgrenzen, aktuelle GM-/Actor-/Source-/History-/Privacyrechte, reale WriterFence-/Duplicate-/LostAck-/Revoke-/Reconnect-/Restart-/Outbox-Negativprüfungen und getrennte Build-/DB-/Browser-Evidenz in beiden Stufen. **Kein VPS-Test ohne wirksame Isolation; lokale PASS-Ergebnisse belegen keine Staging-Erfüllung. B.17-Readiness und B.11-Tests sind weiterhin nicht ausgeführt, B.18-Kandidaten nicht bewertet; keine Produktionsfreigabe.** **Nächste Grundfrage B.20: identische reproduzierbare Artefakte und sichere Umgebungskonfiguration.**

**Nachfolgender Beschluss B.18 C (04.11.2026):** [Kleine risikogebundene Technik-Shortlist und ein primärer isolierter B.11-P1/P2/P3-Testpfad mit nur gezielt nötigen Alternativproben und versionierten B.10-ADRs](PHASE-B-WORKSHOP-B.18.md). Serverautorität, 14.12-WorldTransaction-/OriginalReceipt, 14.13-SingleWriter/Fence, aktuelle Auth-/GM-/Actor-/Source-/History-/Privacy-/Viewerrechte, SingleVPS, Lizenz, Wartung und Recovery sind verbindliche Eignungsgrenzen. **Noch keine Kandidaten recherchiert, kein Stack final gewählt, B.17-Readiness nicht ausgeführt, B.11-Spike NOT_RUN, B.12-/B.13-Produktion nicht freigegeben.** Keine parallelen vollständigen Full-Stacks und kein B.2-/B.8-/B.9-/14.6-/15.4-Release durch Spikeerfolg. **Nächste Grundfrage B.19: getrennte lokale und VPS-/Staging-Testausführung.**

**Stand:** 04.11.2026. **B.17 C vom Projektinhaber ausdrücklich beschlossen.**
**Status:** Verbindliche **Planung der Startvoraussetzungen**, keine ausgeführte Readiness-Prüfung. Die erste B.11-P1/P2/P3-Technikprobe ist **nicht implementiert und nicht ausgeführt**; weder ein Stack noch ein produktionsgehärteter B.12-Kern, ein B.13-Vertikalschnitt oder eine spielbare B.2-B-Version sind nachgewiesen.
**Entscheidung C:** Vor dem ersten echten isolierten Mehrbrowser-/WorldWriter-/WorldTransaction-/OriginalReceipt-Test wird ein **eng begrenzter, nachvollziehbarer Preflight** durchgeführt. Er kontrolliert die vorhandenen Architektur-/Sicherheitsbeschlüsse B.10–B.16, den testbaren Minimalumfang, Kandidaten-/Dependency-/Versionsnachweise, synthetische 14.8-Umgebung, CurrentACL-/GM-/Actor-/Source-/Viewer-/Revoke-/Recovery-Grenzen und die tatsächlichen Pass-/Fail-/NotRun-Kriterien. Erst ein belegter erfolgreicher Preflight erlaubt die **isolierte Testimplementierung**, weder direktes Produktivdeployment noch eine endgültige Technologieentscheidung. Keine Pflicht, vorher vollständige UI-/Regel-/Audio-/Spezialmechanikdetails zu planen.
**Unverändert für V1:** Vollständig selbst hostbarer Single-VPS, Spieler und SL im jeweils eigenen Browser, **genau ein aktiver Spielleiter** und **genau eine kanonische CampaignWorld** pro Kampagne, ein tatsächlich berechtigter 14.13-WorldWriter. Keine pauschale Host-/Security-/Support-/GM-/Player-Impersonation, keine Offenlegung privater DMs oder GM-/NPC-/Quest-/PlayerSecrets.
**Geltende Beschlüsse:** [B.1](PHASE-B-WORKSHOP-B.1.md) · [B.2](PHASE-B-WORKSHOP-B.2.md) · [B.3](PHASE-B-WORKSHOP-B.3.md) · [B.4](PHASE-B-WORKSHOP-B.4.md) · [B.5](PHASE-B-WORKSHOP-B.5.md) · [B.6](PHASE-B-WORKSHOP-B.6.md) · [B.7](PHASE-B-WORKSHOP-B.7.md) · [B.8](PHASE-B-WORKSHOP-B.8.md) · [B.9](PHASE-B-WORKSHOP-B.9.md) · [B.10](PHASE-B-WORKSHOP-B.10.md) · [B.11](PHASE-B-WORKSHOP-B.11.md) · [B.12](PHASE-B-WORKSHOP-B.12.md) · [B.13](PHASE-B-WORKSHOP-B.13.md) · [B.14](PHASE-B-WORKSHOP-B.14.md) · [B.15](PHASE-B-WORKSHOP-B.15.md) · [B.16](PHASE-B-WORKSHOP-B.16.md); [14.1](SICHERHEIT-WORKSHOP-14.1.md) · [14.2](SICHERHEIT-WORKSHOP-14.2.md) · [14.5](SICHERHEIT-WORKSHOP-14.5.md) · [14.6](SICHERHEIT-WORKSHOP-14.6.md) · [14.7](SICHERHEIT-WORKSHOP-14.7.md) · [14.8](SICHERHEIT-WORKSHOP-14.8.md) · [14.9](SICHERHEIT-WORKSHOP-14.9.md) · [14.12](SICHERHEIT-WORKSHOP-14.12.md) · [14.13](SICHERHEIT-WORKSHOP-14.13.md) · [15.4](ERWEITERUNGEN-WORKSHOP-15.4.md).

## 1. Was vor dem Start tatsächlich geklärt sein muss

1. **Konkrete Testfrage und Nichtziele:** B.11 C bleibt die erste Probe: unabhängige synthetische GM-/Player-Sessions, eine TestCampaign, ein Writer, ein berechtigter und ein verweigerter getypter Command, aktuelle Source-/Actor-/GmAuthorityACL, echte WorldRevision + OriginalOperationReceipt, berechtigte Viewerprojektionen, Duplicate/Disconnect/Revoke/Restart-Negativfälle. Keine vollständige NPC-/Combat-/Quest-/Inventar-/Map-/UI-Engine für diesen Beleg.
2. **Architekturkontrakte und Blocker:** B.3–B.7/B.10–B.16-Dependencies und zu prüfende Hypothesen versionieren. Unbekannte oder widersprüchliche Fachowner-/World-/Session-/Sourceverträge nach B.16 gezielt als BLOCKED behandeln, nicht im Testcode „vorläufig erlauben“.
3. **Isolierte 14.8-Umgebung:** Eigenständiger Entwicklungs-/Testscope, synthetische Testidentitäten, GM-/PlayerSessions, WorldRoot, Domain-/Receipt-/Audit-/Queue-/MediaStores, Secrets/Keys und Backups; kein produktiver Schreib-/Leseweg, kein importiertes privates ProductionWorld-/Chat-/DM-/Quest-/NPC-Material. Ein einzelner VPS genügt nur bei **tatsächlich wirksamer** Trennung.
4. **Kandidaten und technische Machbarkeit:** Eingrenzbare B.10-Server-/DB-/Session-/Realtime-/Deploymentkandidaten samt Versions-/Lizenz-/VPS-/Maintenance-/ADR-Hypothesen. Der Preflight wählt **keinen ungeprüften endgültigen Stack**. Unbekannte Kosten/Quotas und produktive Annahmen werden nicht verschwiegen.
5. **Echte statt simulierte Invarianten:** B.11-SingleWorld-/SingleWriter-/Fencing-, 14.12-atomare WorldTransaction-/Receiptpersistenz und B.5-CurrentAuthorization-/Audienceprojektionen müssen im anschließenden Experiment **real** geprüft werden. Synthetische Identitäten sind nur ausdrücklich begrenzte ContractFixtures; FakeAuth-Test ersetzt keinen 14.1-Steam-/Account-/Session-End-to-End-Beleg.
6. **Sicherheitsgrenzen pro Zugriffsweg:** Identität ≠ GM-/Actor-/Owner-/Campaign-/Source-/Historygrant; aktueller Entzug wirkt auf API, WebSocket, Outbox-Fanout, Reconnect sowie betroffene MediaServe-Pfade. Keine geheimen Referenzen/Counts/AssetURLs in Playerantworten, Testreports oder Logs.
7. **Reproduzierbare Prüfinstrumente:** Nachvollziehbare Test-OperationIds, Versions-/Build-/Schema-/Fixture-/Environmentkennzeichen, ExpectedWorldRevision, autorisierte/abgelehnte Requests, echte persistente Revisionen und OriginalOperationReceipts, redigierte Beobachtungen und ein kontrollierter Reconnect-/Crash-/Revoke-Ablauf. Keine Pflicht zu einer bereits final gewählten Testtoolchain.
8. **Entscheidbare Stop-/Go-Grenzen:** Explizite Erwartungen für PASS, FAIL, NOT_RUN und BLOCKED. Tatsächlich nicht nachweisbare Sicherheits-/WorldWriter-/Datenisolationspflichten lassen den Preflight **nicht bestehen**; optionale Folgefunktionen dürfen als begründete B.11-Nichtziele markiert sein.

## 2. Geplante Planungs- und Nachweisobjekte (keine neue Produktengine)

| Arbeitsname | Verbindliche Bedeutung |
|---|---|
| **ReadinessScope / ReadinessRevision** | Exakter B.11-Spike, gewählte zu prüfende Architekturhypothesen, Build-/Environment-/Fixture-/Kandidatenreferenzen und dokumentierte Nichtziele |
| **PreflightDependencyMatrix** | Versionierte B.3–B.16-/14.x-Anforderungen, bekannte Konflikte, echte Voraussetzungen und verantwortliche Contract-/Security-Owner |
| **IsolationEvidence / NoProductionFence** | Trennung von Identität, GM-/Player-/Source-/World-/Key-/Audit-/Media-/Backupdaten; tatsächlich überprüfte Write-/Read-Grenzen |
| **TestIdentityCapabilityFixture** | Eng gefasste synthetische Sessions, CampaignMembership, eine GmAuthorityEpoch, ActorController, Owner-/Source-/HistoryACL und mindestens eine unberechtigte Rolle |
| **InvariantTestPlan / NegativeCaseCatalog** | Positiv-/Negativkriterien zu SingleWriter, Revoke, Duplicate, LostAck, stale Revision, AudienceSecret, Crash/Restart und OriginalReceipt |
| **EvidenceCaptureContract** | Prüfevidenz am exakten Code-/Test-/DB-/Browserstand, OriginalWorldRevision/Receipt, redigierte Logs und reproduzierbare Ausführung, ohne Secretrohwerte |
| **ReadinessGateDecision** | Dokumentierte technische Startentscheidung READY, BLOCKED oder NOT_CHECKED. **READY ist keine gelaufene oder bestandene B.11-Probe.** |
| **CleanupAndRollbackPlan** | Testdaten-/Testkey-/Session-/Store-Bereinigung und sichere Wiederholung ausschließlich im isolierten Scope; kein WorldReset echter Kampagnen |

Es handelt sich um Entwicklungsdokumentation und technische Testverträge, **nicht** um einen neuen produktiven Readiness-/Incident-/World-/Deployment-Dienst. Konkrete CI-, Datei-, Container-, DB-, API- und UI-Implementierungen werden erst bei der realen Probe festgelegt.

## 3. Minimaler B.17-Readiness-Ablauf vor B.11

1. **Anwendbare Beschlüsse fixieren:** Alle für den B.11-Vertikalschnitt maßgeblichen Owner-/GM-/Actor-/World-/Receipt-/Privacy-/Test-/Prod-Regeln und deren Versionen als B.15-Auftrag referenzieren.
2. **B.10-Risiken abgrenzen:** Kandidatenvergleich und ADR-Fragen mit Hypothesen, echten Betriebsannahmen und Lizenzen festhalten; keine weitere Großmodulplanung als Voraussetzung erfinden.
3. **14.8-Testscope validieren:** Synthetische Accounts, getrennte BrowserSessions, World-/Receipt-/Media-/KeyStores und Deny-by-default-Ausgabe; keine Testwelt mit echter Produktionsidentität, produktiven Secrets oder kopierten privaten DMs.
4. **Kleinsten echten Prüfpfad definieren:** GM und Player unabhängig verbunden; erlaubter Command -> persistierter SingleWriter-WorldCommit und OriginalReceipt -> nur berechtigt gefiltertes Snapshot/Delta. Verbotener Command -> nachweislich kein WorldEffect.
5. **Negativ- und Wiederanlaufpfad festschreiben:** Doppelrequest, konkurrierende Revision, verlorenes Ack, Disconnection, Session-/GM-/Actor-/Source-Revoke, altes WriterFencing, Server-/DB-Wiederaufnahme und Outbox-/WS-Ausfall nach echtem Commit.
6. **Beleg- und Erfolgskriterien vorbereiten:** Für jede Invariante beobachtbare Persistenz-/Response-/Audience-/Security-/Recoveryergebnisse, Redaktionsschutz und Status PASS/FAIL/NOT_RUN/BLOCKED festlegen. Ansehen einer UI-Animation ist kein Commitbeweis.
7. **Technische Startentscheidung treffen:** READY nur bei **tatsächlich geprüften** Startvoraussetzungen; bei relevanter Lücke BLOCKED und B.16-Konflikt-/Abweichungsverfahren. Diese Entscheidung startet keine automatische Software-, World- oder Deploymentaktion.
8. **Erst dann isoliert implementieren und ausführen:** Die echte B.11-Probe läuft als eigener nicht produktiver Testschritt. Ihre Ausführung/Ergebnisse/ADRs werden gesondert gemessen; anschließende Codeübernahme erst nach B.12-Härtung.

## 4. Readiness- und Testabgrenzung: falsche Positivmeldungen verhindern

| Feststellung | Korrekte Konsequenz |
|---|---|
| Architektur und Preflight sind nur dokumentiert | NOT_CHECKED; **nicht** „READY“, keine ausgeführte B.11-Probe |
| Kandidat hat nur UI-Demo oder FakeAuth | Kein Beleg für echte 14.1-SteamAuth oder persistente SingleWriter-/SourceACL-Sicherheit |
| GM-/Player-/Session-/TestWorld-Daten können Produktion erreichen | Readiness BLOCKED; 14.8-Isolation vor jedem Test herstellen |
| Testmatrix enthält nur erlaubte Aktionen | Readiness BLOCKED; verbindliche B.11-Revoke-/Duplicate-/Denied-/Recovery-Negativfälle fehlen |
| Keine Möglichkeit, OriginalReceipt und DB-WorldRevision zu beobachten | Readiness BLOCKED; hübsches Browserbild beweist den Commit nicht |
| Ein B.16-Konflikt betrifft WriterAuthority oder SecretProjection | Nur betroffenen Spike-Teilpfad BLOCKED; keine Ausnahme von Sicherheitsinvarianten |
| Preflight READY, eigentlicher Spike nicht ausgeführt | Readinessstatus positiv, B.11-Ergebnis bleibt **NOT_RUN**, kein bestätigter Stack/Release |
| B.11-Test besteht auf synthetischen Accounts, SteamAuth fehlt | Begrenzter Contractnachweis, echter Steam-/Session-E2E-Nachweis bleibt offen |
| Einzelner Spike besteht, B.2-B-/B.8-/B.9-Gates fehlen | Keine erste offiziell spielbare AdventureShift-Version |
| Tests erzeugen Roll-/Quest-/Item-/Traktorwirkungen in echter CampaignWorld | Verboten; Testscope-/WorldIsolation verletzt, kein gültiger isolierter Nachweis |

## 5. Unveränderte Grenzen und nächste Grundfrage

B.17 C beschließt **nur den minimalen, risikogerechten Preflight**. Kein vollständiges UI-, RulePack-, NPC- oder Audio-Feindesign als Voraussetzung, keine künstliche Unendlichkeit weiterer Planungsfragen. 14.15 A bleibt manuelle Incidentbehandlung; 02.118 A untersagt persistente ungesendete ChatDrafts. Readiness ist weder 14.6-StableDeployment noch 15.4-Release, weder 08.3-Publish noch eine 02.99-/14.12-WorldAction, kein Erlaubnisschein für Support-/GM-/Player-Impersonation.

**Noch nicht durchgeführt:** Kandidatenauswahl, tatsächlicher Readiness-Check, Testimplementierung, B.11-Positiv-/Negativläufe und B.12-Produktionshärtung. Was genau an Bibliotheken, DB, Frameworks und Testmethoden verwendet wird, entscheidet der nachfolgende eng begrenzte Kandidaten-/Technikschritt anhand B.10.

## 6. Historische Anschlussfrage B.18 (inzwischen C beschlossen)

### B.18 – Wie wählen und vergleichen wir die technischen Kandidaten für den ersten isolierten B.11-Spike, ohne bereits den späteren Gesamtstack festzuschreiben?

- **A – Einen vertrauten Stack sofort verbindlich setzen und nur damit die Probe bauen:** Schnell, aber B.10-Risiken und alternative DB-/Realtime-/Fencing-/Betriebsansätze werden ohne Evidenz ausgeschlossen.
- **B – Mehrere komplette konkurrierende Full-Stacks parallel umsetzen:** Breite Vergleichbarkeit, aber unnötig teure Doppelentwicklung weit über den begrenzten B.11-Sicherheitskern hinaus.
- **C – Kleine begründete Kandidaten-Shortlist mit primärem isolierten Spike und gezielten Alternativnachweisen (Empfehlung):** B.10-Eignung, Lizenz, Wartbarkeit, VPS-Betrieb, Auth-/ACL-/WorldTransaction-/OriginalReceipt-/WriterFence-/Viewer-/Recovery-Risiken vergleichen. Einen minimalen Kandidaten zuerst tatsächlich prüfen, bei unbewiesenen/fehlgeschlagenen Invarianten gezielt alternative Implementierungswege testen. Alle Befunde versionsgebunden in ADRs erhalten; erst echte Evidenz erlaubt die spätere zusammenhängende Stackentscheidung. Keine verpflichtende parallele Full-Stack-/UI-Entwicklung, kein automatischer Produktionsimport.
