# AdventureShift – Phase B, Beschluss B.18 C: begrenzte technische Kandidaten-Shortlist und evidenzgesteuerte Spike-Auswahl

**Nachfolgender Beschluss B.20 C (04.11.2026):** [Reproduzierbarer B.11-/B.19-Testbuild mit unveränderlicher Source-/Dependency-/Toolchain-/Schema-/Fixture-Provenienz, BuildDigest und getrennten sicheren LOCAL_DEV-/ISOLATED_VPS_STAGING-Einstellungen](PHASE-B-WORKSHOP-B.20.md). Wo zielkompatibel dasselbe Artefakt verwenden, bei Windows-/Linux-/Plattformunterschieden separate Artefakte gleicher nachweisbarer Sourcebasis mit unabhängigen Stage-/Contracttests. Geheimnisse und ProdDaten niemals im Build/Git/Testlog, kein stiller Dependency-/Schema-/SecurityConfigDrift. **Noch kein Build/Preflight/Spike real ausgeführt oder Stack festgelegt; kein automatischer WorldEffect, Codeimport oder B.2-/B.8-/B.9-/14.6-/15.4-Release.** **Nächste Grundfrage B.21: Isolierung von Technikspike-Code im Git-Entwicklungsprozess.**

**Nachfolgender Beschluss B.19 C (04.11.2026):** [Zweistufiger echter B.11-Techniktest: zuerst reproduzierbarer synthetischer LOCAL_DEV-Vertikalschnitt, dann gleicher geprüfter Teststand auf 14.8-isolierter Einzel-VPS-/Staging-Umgebung](PHASE-B-WORKSHOP-B.19.md). Eigene Environment-/Session-/World-/Receipt-/Key-/Media-/Backup-/Network-Sicherheitsgrenzen, aktuelle GM-/Actor-/Source-/History-/Privacyrechte, reale WriterFence-/Duplicate-/LostAck-/Revoke-/Reconnect-/Restart-/Outbox-Negativprüfungen und getrennte Build-/DB-/Browser-Evidenz in beiden Stufen. **Kein VPS-Test ohne wirksame Isolation; lokale PASS-Ergebnisse belegen keine Staging-Erfüllung. B.17-Readiness und B.11-Tests sind weiterhin nicht ausgeführt, B.18-Kandidaten nicht bewertet; keine Produktionsfreigabe.** **Nächste Grundfrage B.20: identische reproduzierbare Artefakte und sichere Umgebungskonfiguration.**

**Stand:** 04.11.2026. **B.18 C vom Projektinhaber ausdrücklich beschlossen.**
**Status:** Verbindliche Architektur- und Auswahlgrundstruktur, **noch keine reale Kandidatenrecherche abgeschlossen, kein Produkt oder Versionsstand bewertet, keine Technologie fest ausgewählt, kein B.17-Preflight durchgeführt, kein B.11-Spike implementiert oder ausgeführt und kein Testergebnis vorliegend**.
**Entscheidung C:** Für die erste isolierte B.11-P1/P2/P3-Kernprobe wird **eine kleine, fachlich begründete und überprüfbare Kandidaten-Shortlist** gebildet. Wir vergleichen tatsächliche Eignung für einen eigenständig auf einem VPS betreibbaren, serverautoritativen Browser-/Mehrspieler-/WorldTransaction-Kern. **Ein** plausibel führender Kandidatenpfad wird nach bestandener B.17-Readiness zuerst minimal und wirklich getestet. Gescheiterte, fehlende oder zweifelhafte kritische Nachweise lösen **gezielte Vergleichsproben** zu der betreffenden Technik- oder Architekturannahme aus, **keine verpflichtende Parallelentwicklung ganzer Full-Stacks**. Erst belastbare Resultate und versionierte B.10-ADRs erlauben eine spätere gemeinsame Technologieentscheidung.
**Bewusst keine vorgezogene Festlegung:** Das Dokument entscheidet keine konkrete Sprache, Datenbank, Frameworkversion, WebSocketbibliothek, Containerlösung, Projektstruktur oder Lizenzfreigabe. Aktuelle Releases, Lizenzen, Wartungsstatus, bekannte Sicherheitslücken und VPS-Eignung müssen **bei der wirklichen Kandidatenerhebung** extern geprüft und mit Quellen-/Versionsstand dokumentiert werden; hier werden solche Nachweise nicht vorgetäuscht.
**Unveränderte V1-Grenzen:** Selbst hostbarer Single-VPS ohne Cloud-/Clusterpflicht, getrennte echte Spielleiter-/Spielerbrowser, **genau ein aktiver Spielleiter je Kampagne**, genau eine kanonische CampaignWorld und ein autoritativer WorldWriter. Kein globaler Host-/Support-/GM-/Security-ReadAll, keine zweite Fach-/World-/RuleEngine und kein unerlaubter Zugriff auf private DMs oder GM-/NPC-/Quest-/PlayerSecrets.
**Bezüge:** [B.1](PHASE-B-WORKSHOP-B.1.md) · [B.2](PHASE-B-WORKSHOP-B.2.md) · [B.3](PHASE-B-WORKSHOP-B.3.md) · [B.4](PHASE-B-WORKSHOP-B.4.md) · [B.5](PHASE-B-WORKSHOP-B.5.md) · [B.6](PHASE-B-WORKSHOP-B.6.md) · [B.7](PHASE-B-WORKSHOP-B.7.md) · [B.8](PHASE-B-WORKSHOP-B.8.md) · [B.9](PHASE-B-WORKSHOP-B.9.md) · [B.10](PHASE-B-WORKSHOP-B.10.md) · [B.11](PHASE-B-WORKSHOP-B.11.md) · [B.12](PHASE-B-WORKSHOP-B.12.md) · [B.13](PHASE-B-WORKSHOP-B.13.md) · [B.14](PHASE-B-WORKSHOP-B.14.md) · [B.15](PHASE-B-WORKSHOP-B.15.md) · [B.16](PHASE-B-WORKSHOP-B.16.md) · [B.17](PHASE-B-WORKSHOP-B.17.md) · [14.1](SICHERHEIT-WORKSHOP-14.1.md) · [14.6](SICHERHEIT-WORKSHOP-14.6.md) · [14.8](SICHERHEIT-WORKSHOP-14.8.md) · [14.12](SICHERHEIT-WORKSHOP-14.12.md) · [14.13](SICHERHEIT-WORKSHOP-14.13.md) · [15.4](ERWEITERUNGEN-WORKSHOP-15.4.md).

## 1. Vergleichsgrenzen – was der Kandidatenpfad wirklich tragen muss

1. **Gemeinsame Serverautorität:** Authentifizierter, fachlich autorisierter B.4-CommandOwner und ein kanonischer 14.12-/14.13-WorldTransaction-/OriginalReceipt-/SingleWriter-Pfad, keine vom Browser direkt beschreibbaren Welt-/Roll-/Inventar-/Questzustände.
2. **Echte Transaktions- und Konkurrenzgarantien:** Persistente WorldRevision plus OriginalOperationReceipt, atomare relevante Fachzustandsänderungen, Conflict/CAS, idempotente OperationId, Writer-Fencing bei Restart/Lease-/Generationwechsel und zulässige Outbox-/Job-Reconciliation ohne globale CrossStore-ACID-Fiktion.
3. **Getrennte Sitzung und Rechte:** 14.1-/14.2-/09.7-/03.2-kompatible GM-/Player-/Actor-/Source-/History-/Fog-/Privacy-Checks an Request-, Commit-, Snapshot-/Delta-, Subscription-, Reconnect- und Mediengrenzen. Synthetische TestAuth darf nur als solche ausgewiesen werden.
4. **Ein selbst betriebener VPS:** Kandidat benötigt keinen externen Pflichtdienst für WorldWrites, Sessionberechtigungen, Rule-/Media-/Blob-/Secretstorage oder Wiederherstellung. Optionale spätere Skalierung bleibt möglich, aber keine Cluster-/Cloud-Voraussetzung.
5. **Kompatibler modularer Kern:** B.3-Capabilities/Automation/Exceptions, B.4-Fachowner, B.5-Viewerprojektion, B.6-Berechtigungsvorladen, B.7-Reconnect und B.9-unterschiedliche RulePacks müssen sich später ohne Zweitmotor anbinden lassen. Die erste Spike-Probe implementiert diese Fachbreite **noch nicht**.
6. **Lizenz, Wartbarkeit und Betrieb:** Plausible Pflege-/Patch-/Releasefähigkeit, dokumentierte API-/Dependency-/Lizenz- und Nutzungsrechte, nutzbare Tests/Diagnose/Backup/Recovery und VPS-kontrollierbare Konfiguration. Unbekannte oder nicht geprüfte Aussagen bleiben **UNVERIFIED**, kein stiller Freibrief.
7. **Gleichartige Messbedingungen:** Hypothese, CandidateVersion, Build/Environment/Fixture, zulässige Testidentitäten, Kommandotypen, ExpectedRevision/OperationId, Faults und Beobachtung müssen zum Vergleich **nachvollziehbar äquivalent** sein; Unterschiede und Gründe werden explizit festgehalten.

## 2. Planungsobjekte für Kandidatenauswahl und Nachweise (Arbeitsnamen)

| Arbeitsobjekt | Verpflichtende Bedeutung |
|---|---|
| **TechnologyCandidate / CandidateRevision** | Konkrete Laufzeit-/Server-/Persistenz-/Session-/Realtime-/Betriebsoption mit eindeutigem Versionsstand und Herkunft; Auswahl zunächst offen |
| **CandidateEligibilityMatrix** | Prüffelder aus B.10, B.11, B.17 und 14.x: Sicherheit, SingleVPS, World/Receipt, Viewer/Session, Lizenz, Wartung, Erweiterbarkeit; PASS/FAIL/UNKNOWN |
| **CriticalRiskHypothesis / FalsificationCase** | Zu beweisende oder widerlegende testbare Invariante; kein nur rhetorisches „sicher und skalierbar“ |
| **PrimarySpikePath / ComparisonAlternative** | Ein zunächst zulässiger enger Kandidatenpfad, dazu problembezogen definierte Ersatz-/Vergleichsmöglichkeiten, keine vollständigen parallelen Produkte |
| **TestEvidence / BuildFixtureRef** | Tatsächlich ausgeführter Fall, exakte Version/Build/Schema/Environment/OperationId/Receipt/WorldRevision und redigierte positive/negative Beobachtung |
| **ADRRecord / DecisionRevision** | Ein technischer B.10-Entscheid mit Alternativen, Gründen, nachgewiesenen Risiken, offener Unsicherheit, Entscheidungsgeltung und Rücknahmebedingungen |
| **CandidateDisposition / NextProbe** | ELIGIBLE, BLOCKED, REJECTED, TESTED_PASS, TESTED_FAIL, UNTESTED; Review allein macht keinen Kandidaten zum Produktrelease |

Diese Objekte sind **technische Planungs- und Nachweisartefakte** (z. B. später Git-Dokumente/CI-Protokolle), keine neue World-, Plugin-, Rule-, Incident- oder zentrale Produktivfreigabe-Engine.

## 3. Verbindliche Ablaufreihenfolge

1. **Anforderungen festsetzen:** B.10-, B.11-, B.17- und relevante 14.x-Sicherheits-/Quoten-/Lizenzregeln als unverhandelbare Kriterien versionieren. B.16 entdeckt und sperrt Widersprüche; keine stille Neudefinition früherer Beschlüsse.
2. **Kleine Kandidatenliste recherchieren:** Erst beim echten Technikschritt konkrete Produkte/Versionen mit öffentlich/primär nachprüfbaren technischen Dokumentationen, Lizenz-, Maintenance- und Sicherheitsständen erfassen. Nur plausibel VPS- und SingleWriter-taugliche Kandidaten aufnehmen; keine erfundene „beste“ Bibliothek.
3. **Grobe Verwerfungsfilter vor Code:** Kandidaten mit zwingender fremder Cloud, ungeklärter inkompatibler Nutzungslizenz, prinzipiell fehlendem transaktionalen WorldCommit/Receipt oder unvereinbarer Autoritäts-/SourceACL-Grenze nicht durch UI-Demos schöngerechnet freigeben.
4. **Primäre Hypothese begründen:** Einen am plausibelsten passenden Weg als **vorläufigen Ersttestpfad** festlegen; technische Unsicherheiten und Alternativen benennen. Die Auswahl ist kein endgültiger Stack-ADR.
5. **B.17-Readiness wirklich prüfen:** Isolierte 14.8-Testumgebung, synthetische separate GM-/Player-/UnauthorizedSessions, sichere Keys/Stores, positiver und negativer Command, echte Receipt-/Writer-/Viewer-/Revoke-/Restartmessung, reproduzierbarer Cleanup und Secret-Schutz müssen belegbar READY sein.
6. **B.11 minimal tatsächlich implementieren:** Nur den definierten fachneutralen vertikalen Pfad mit echter, nicht gemockter Persistenz/Fencing/ACL und unabhängigen Browseransichten testen. TestAuth-Scope/SteamIntegration-Lücke explizit kennzeichnen.
7. **Negative Fälle zwingend messen:** Zweiter aktiver GM, fremde Actor-/Source-/CampaignRefs, verbotene Audience, ConcurrentRevision, DuplicateOperation, LostAck, Disconnect, Revoke bei PendingWrite, WriterRestart/Fence und Outbox-/Delivery-Ausfall. Kein PASS ohne wirkliches Ergebnis.
8. **Gezielte Alternativprobe nur bei Bedarf:** Bei Fehltest oder offenem harten Risiko **genau die betroffene** DB-/Fencing-/Realtime-/Session-/Autorisierungs- oder Betriebsannahme mit äquivalentem Testfall vergleichen. Sicherheitslücken werden nicht aus Zeitgründen übergangen.
9. **ADR nach Evidenz:** Nachgewiesene und verbleibende Risiken, Lizenzen, Versions-/Migration-/Quoten-/SingleVPS-Betriebsfolgen dokumentieren; gewählte Technologie kann später nach B.14 geändert werden, aber nicht still in gepinnten Kampagnen.
10. **B.12 und Release strikt trennen:** Nur geeignet gehärtete Spike-Komponenten nach B.12 in die gemeinsame B.13-Entwicklungsbasis übernehmen. B.2-B-Spielumfang, B.8-/B.9-Gesamtgates und 14.6-/15.4-Freigaben bleiben vollständig unerfüllt, bis sie **separat real** bestanden wurden.

## 4. Vergleichs- und Negativfälle

| Prüffall | Auswirkung |
|---|---|
| Zwei Kandidaten haben unterschiedliche Last-/DB-Testbedingungen | Kein ungeprüftes relatives Performance-/Risikourteil; Messaufbau und Limitierungen offen dokumentieren |
| Ein Browser zeigt einen erfolgreichen Command, Server konnte keine Revision/Receipt committen | FAIL für echten WorldEffect; UI-Scheinbeleg unzulässig |
| SessionRevoke oder GMEpoch-Wechsel lässt alten PendingCommand zu | Sicherheits-FAIL und BLOCKED, auch wenn Latenz/Rendering gut aussehen |
| Zweiter Writer erzeugt konkurrierenden WorldCommit | Kandidatenpfad gesperrt, keine Reparatur durch blindes Rollback oder DuplicateReplay |
| Einziges „Auth“-Ergebnis kommt aus FakeAccounts | Begrenzt auf synthetische ContractFixture, kein Steam-/RealSession-E2E-Beleg |
| Unautorisierter Player kann Secret-Source-/NPC-/Quest-/Assetreferenzen aus Snapshot/Delta ableiten | Security-FAIL; Ansichtsausblendung ersetzt nicht B.5-Projektionsfilterung |
| Timeout nach Commit und verlorenes Ack | Derselbe OriginalOperationReceipt wird gefunden, kein neuer WorldEffect mit anderer OperationId |
| DB-Transaktion erfolgreich, Outbox/WS-Zustellung fehlgeschlagen | Kanonische Welt bleibt committed; separate berechtigte Reconciliation ohne zweiten Commit |
| Kandidat benötigt produktive DMs/GMSecrets oder ProdKeys als Testfixtures | B.17/14.8-Readiness BLOCKED, kein zulässiger Test |
| Kandidatenshortlist enthält nur Dokumentation, keine realen Tests | Status UNTESTED, kein bestätigter Technologieentscheid |
| Ein Kandidat erfüllt Kernprüfung, R1/R2-/NPC-/Quest-/Kampfbreite fehlt | B.11-Scope ggf. bestanden, B.2-/B.8-/B.9-Spielrelease ausdrücklich **nicht** |
| Fremdlizenz oder Sicherheitswartung unklar | Nicht als unbedenklich erklären; Lizenz-/Supply-Chain-Review offen und ggf. Integrationsblocker |
| Erster Kandidat scheitert | Beleg behalten, nach B.16 Risiko klären, gezielte Alternative testen; nicht sofort alles neu oder dauerhaft aufgeben |

## 5. Statusgrenzen und spätere Festlegungen

**Noch nicht getan:** Eine konkrete Kandidaten-Shortlist recherchiert oder evaluiert, ein primärer Stack ausgewählt, B.17 real READY geprüft, B.11 implementiert oder ausgeführt, echte Spikemessung/ADR dokumentiert oder Code produktiv übernommen. B.18 C entscheidet **das Verfahren**, nicht dessen spätere Ergebnisse. Konkrete Bibliotheken, Paketversionen, Testmaschinen, Performancewerte, Hostparameter, CI-Verfahren und Migrationsrouten erst im anstehenden Technikschritt bestimmen.

**Keine Erweiterung des Spielumfangs durch den Spike:** Bereits beschlossene Node-, Kampf-/Initiative-, NPC-, Inventar-, Quest-, RulePack-, Character-, Asset-, Karten-, Steam-, Privacy- und Modulrechte bleiben bestehen; reine Mock-/UI-Demos ersetzen diese nicht. Audio ist weiterhin ein **optionales späteres Modul**, kein eigener B.11-Blocker; 02.118 A untersagt weiterhin persistente ungesendete ChatDrafts und 14.15 A bleibt manuelle Sicherheitsvorfallbehandlung.

## 6. Historische Anschlussfrage B.19 (inzwischen C beschlossen)

### B.19 – In welcher tatsächlichen Umgebung und Reihenfolge soll die erste B.11-Technikprobe ausgeführt werden?

- **A – Nur lokal auf dem Entwickler-PC:** Schneller isolierter Prototyp, aber tatsächliche SingleVPS-/Netz-/Deployment-/Restart-/Browsertrennungs- und Betreibergrenzen bleiben unzureichend belegt.
- **B – Sofort auf der später produktiv genutzten VPS-Installation testen:** Reale Serverumgebung, aber hohe Gefahr einer Vermischung mit Produktivkonten, Keys, DMs, GMSecrets oder laufenden Kampagnen und Verletzung von 14.8.
- **C – Zweistufig in wirksam isolierter Entwicklungsumgebung und anschließender isolierter VPS-/Staging-Umgebung (Empfehlung):** Zuerst minimale reproduzierbare synthetische Tests lokal/auf einem getrennten Entwicklungsgerät; dann denselben revisionsgebundenen autoritativen Browser-/WorldCommit-/Security-/Reconnect-/Restart-Pfad auf einem nachweislich von Produktion getrennten einzelnen VPS/Staging-Scope ausführen. Die Ergebnisse bleiben umgebungsgetrennt, tatsächlich ausgeführt und vergleichbar. Bei fehlender sicherer VPS-Isolation keine VPS-Probe, bis diese hergestellt ist; nie automatisch in Produktion wechseln.
