# AdventureShift – Phase B, Beschluss B.19 C: zweistufige isolierte Ausführung der ersten Technikprobe

**Stand:** 04.11.2026. **B.19 C vom Projektinhaber ausdrücklich beschlossen.**
**Status:** Verbindliche Grundstruktur für die spätere Ausführung und Bewertung des B.11-Spikes. **Noch keine lokale oder VPS-Technikprobe implementiert oder ausgeführt, keine B.17-Readiness tatsächlich bestanden, keine konkrete B.18-Kandidaten-Shortlist geprüft, kein Stack/Build ausgewählt und kein B.2-B-Spielrelease freigegeben.**
**Entscheidung C:** Die erste reale B.11-P1/P2/P3-Probe wird **zweistufig** geplant: zunächst ein minimaler, reproduzierbarer und strikt isolierter Test in einer Entwicklungsumgebung auf dem PC oder geeignetem Entwicklungsgerät; danach derselbe ausdrücklich identifizierte und unverändert fachlich relevante Teststand in einer **wirksam von Produktion isolierten** VPS-/Staging-Umgebung. Dort müssen reale Netzwerk-, Mehrbrowser-, Persistenz-, Writer-/Session-/Revocation-, Neustart- und Reconnectgrenzen gesondert nachgewiesen werden. Die zweite Stufe findet **nur** statt, wenn ihre eigenen 14.8-/B.17-Sicherheitsvoraussetzungen belegbar erfüllt sind. Weder lokale Test-Erfolge noch ein Staging-PASS bewirken Produktivfreigabe oder automatische Datenübernahme.
**V1-Rahmen:** Ein selbst betreibbarer VPS ohne vorgeschriebene Cloud oder Cluster, GM und Player in jeweils eigenen Browsern, **ein aktiver Spielleiter** und **eine** kanonische CampaignWorld je Kampagne, **eine** gültige WorldWriter-Autorität. Account-/Session-/GM-/Actor-/Owner-/Source-/Fog-/History-/Privacy-/Media-/Host-/Security-/Supportrechte bleiben getrennt, ohne pauschale Impersonation oder ReadAll.
**Verweise:** [B.1](PHASE-B-WORKSHOP-B.1.md) · [B.2](PHASE-B-WORKSHOP-B.2.md) · [B.3](PHASE-B-WORKSHOP-B.3.md) · [B.4](PHASE-B-WORKSHOP-B.4.md) · [B.5](PHASE-B-WORKSHOP-B.5.md) · [B.6](PHASE-B-WORKSHOP-B.6.md) · [B.7](PHASE-B-WORKSHOP-B.7.md) · [B.8](PHASE-B-WORKSHOP-B.8.md) · [B.9](PHASE-B-WORKSHOP-B.9.md) · [B.10](PHASE-B-WORKSHOP-B.10.md) · [B.11](PHASE-B-WORKSHOP-B.11.md) · [B.12](PHASE-B-WORKSHOP-B.12.md) · [B.13](PHASE-B-WORKSHOP-B.13.md) · [B.14](PHASE-B-WORKSHOP-B.14.md) · [B.15](PHASE-B-WORKSHOP-B.15.md) · [B.16](PHASE-B-WORKSHOP-B.16.md) · [B.17](PHASE-B-WORKSHOP-B.17.md) · [B.18](PHASE-B-WORKSHOP-B.18.md); [14.1](SICHERHEIT-WORKSHOP-14.1.md) · [14.2](SICHERHEIT-WORKSHOP-14.2.md) · [14.5](SICHERHEIT-WORKSHOP-14.5.md) · [14.6](SICHERHEIT-WORKSHOP-14.6.md) · [14.7](SICHERHEIT-WORKSHOP-14.7.md) · [14.8](SICHERHEIT-WORKSHOP-14.8.md) · [14.9](SICHERHEIT-WORKSHOP-14.9.md) · [14.12](SICHERHEIT-WORKSHOP-14.12.md) · [14.13](SICHERHEIT-WORKSHOP-14.13.md) · [15.4](ERWEITERUNGEN-WORKSHOP-15.4.md).

## 1. Beide Stufen haben getrennte Prüfzwecke

1. **Stufe L – lokale Entwicklungsprobe:** Minimalen B.11-Testpfad mit echten synthetischen getrennten GM-/PlayerSessions, enger Command-/Owner-/ACL-Prüfung, einer TestWorld, persistenter Revision/OriginalOperationReceipt und unabhängiger Browserprojektion aufbauen. Bereits lokal positive/negative Tests für unzulässige Aktionen, doppelte Zustellung, konkurrierende Revision, LostAck, Revoke, Disconnect und Neustart ausführen, soweit für die Hypothese tatsächlich nötig. Tests mit MockAuth gelten nur als **ausdrücklich begrenzte ContractFixtures**, niemals als Nachweis produktiver Steam-/Browserauthentifizierung.
2. **Stufe V – isolierte Einzel-VPS-/Staging-Probe:** Nach belegtem lokalem Teststand und eigenem 14.8-/B.17-Staging-Preflight denselben versionierten Kandidaten in realer selbst hostbarer Netzwerk-/Serverumgebung auf einer Einzel-VPS-kompatiblen Topologie untersuchen. Reale getrennte Browser-/Session-/WebSocket-/Media-/DB-/WorldWriter-/Secret-/Recovery-/Quota-Grenzen erneut ausführen. Getrennte Geräte/Browserprofile und Netzpfade sind zur E2E-Prüfung geeignet, müssen aber **eigenständige authentifizierte Sessions** und Rechte verwenden.
3. **Gleiche Testhypothese, getrennte Ergebnisse:** Fachliche B.11-Kommandotypen, erlaubte/verweigerte Operationen, ExpectedRevision, OperationId-Strategie und zu prüfende Invarianten bleiben vergleichbar. Jede Umgebung erhält **eigene** synthetische IDs, Sessions, Keys, TestCampaignWorlds, Datenbanken/Queues/Assets und OriginalReceipts; es wird **kein LiveWorldSnapshot oder Sessiongrant zwischen Umgebungen kopiert**.
4. **Staging ist nicht Produktion:** Die Test-VPS darf nur dann auf einer Maschine mit anderen Diensten liegen, wenn echte Isolation von Netzwerk-/Storage-/DB-/Keys-/Domain-/Accounts-/Queues-/Media-/Backup-/Logs nach 14.8 nachgewiesen ist. Anderenfalls separate geeignete Testressourcen verwenden oder **V-Stufe BLOCKED** lassen. Keine Behauptung, ein allgemeiner Containername oder Datenbankpräfix reiche als Beweis aus.
5. **Kein Rückschluss von L auf V:** Lokale PASS-Werte beweisen weder VPS-Neustart/Fencing, echte Remote-Netzstörungen, Proxy-/WS-/Media-Rechte noch die Staging-Deploymentgrenzen. Der gesamte für B.11 geforderte Remote-Nachweis ist erst bei **wirklich ausgeführter** Stufe V erbracht.

## 2. Planungs- und Nachweisobjekte (Arbeitsnamen)

| Objekt | Bedeutung |
|---|---|
| **ExecutionStage / EnvironmentScope** | LOCAL_DEV oder ISOLATED_VPS_STAGING mit unverwechselbarer EnvironmentId; niemals implizite Produktionsumgebung |
| **SpikeBuildIdentity / CandidateRevision** | Gültige Code-/Schema-/Dependency-/Fixture-/Testplanrevision und reproduzierbare Buildidentität, idealerweise Artefakt-Digest; keine Aussage über sicheren Build ohne reale Verifikation |
| **EnvironmentIsolationManifest** | Zugeordnete synthetische Identitäten, World-/Receipt-/Domain-/Outbox-/Media-/Secret-/Key-/Queue-/Backup-/Logbereiche, Network/Host-/Source-Fences |
| **StageReadinessEvidence** | Getrennte B.17-/14.8-Preflightbelege pro Stufe, einschließlich Deny-by-default und NoProd-Fences |
| **StageTestRun / FaultScenario** | Wirklich ausgeführte Positiv-/Negativ-/Disconnect-/Crash-/Revoke-/Duplicate-/SingleWriter-Tests pro Bühne mit Expected/Actual und PASS/FAIL/BLOCKED/NOT_RUN |
| **WorldReceiptEvidence** | Reale dauerhafte WorldRevision, OriginalOperationReceipt, WriterGeneration und korrekt berechtigte Snapshot-/Deltazustellung im jeweiligen Testscope |
| **CrossStageComparability / DriftFinding** | Abgleich derselben Hypothese und Buildversion, dokumentierte Umgebungs-/Tool-/Configabweichung und deren Einfluss; nicht unbesehen Ergebnisse zusammenfassen |
| **StageDisposition / CleanupEvidence** | Stage-spezifisches Testresultat, reproduzierbare Bereinigung und schützende Abschaltung; keine B.12-Engineering- oder 14.6-/15.4-Produktfreigabe |

Diese Begriffe kennzeichnen Entwicklungs- und Nachweisunterlagen, **keine neue World-, Incident-, Rule-, Deployment- oder Test-Orchestrierungsengine**.

## 3. Ausführungsablauf und Sicherheitsgates

1. **Voraussetzungen vor lokalem Start:** B.18-Kandidatenpfad benennen, B.17-Preflight wirklich absolvieren, B.11-invariante Negativtestmatrix und 14.8-Dev-Isolation verifizieren. Fehlt der Nachweis, bleibt L **BLOCKED/NOT_RUN**, nicht „angefangen“ oder bestanden.
2. **L-Test in synthetischem Scope:** Browserprofile mit getrennten aktuellen Session-/Member-/GM-/Actor-/Source-Scopes, TestWorld und echter persistenter Transaktion statt UI-Demo; OriginalReceipt nach DB-/Service-Neustart erhalten. Verbote vor Commit und Auslieferung durchsetzen, 14.12-/14.13-Konkurrenz und WriterFences wirklich messen.
3. **L-Evidenz sichern:** Exakte Build-/Schema-/Candidate-/FixtureVersionen, Code-/Environment-/OperationIds, Server- und Persistenzbelege, redigierte Resultate und aufgetretene FAIL/NOT_RUN/Blocking-Risiken. Weder Secrets noch echte fremde Kampagnendaten als Debugartefakte übernehmen.
4. **Explizite Staging-Eignung:** Nur nach ausreichendem lokalen Vertragsergebnis die VPS-Stufe vorbereiten; dabei Staging-Isolation, Ports/Netze, Credentials, DB-/World-/Queue-/Key-/Storage-/Backup-/WS-/Media-/Log-Fences und unabhängige GM-/Player-E2E-Zugriffe gesondert auf NoProd-Transgressions prüfen.
5. **Staging-Deployment nur in Testscope:** Dieselbe identifizierte Kandidatenrevision und vergleichbarer Testplan werden mit ausdrücklich stagebezogenen, separat geschützten Secrets/Settings bereitgestellt. Keine Wiederverwendung lokaler oder produktiver World-/Receipt-/SessionIDs, Keys, Token oder Host-/GM-/Playergrant-Daten.
6. **V-Test tatsächlich wiederholen und erweitern:** Physische/logische Deploymentrealität, Netzunterbrechung, Reconnect, WebSocket-Gap, LostAck, parallele Browseranfragen, unabhängige SessionRevoke/GmAuthorityEpoch-/Actor-/Source-Epochen, Crash/DB-Restart/WriterLease-/Fencing, Outbox-Recovery und Security-/Quota-/AssetServe-Zugriffe unter realistischer Einzel-VPS-Betriebsführung.
7. **Fehler richtig behandeln:** Lokaler oder Staging-FAIL wird samt Scope dokumentiert; niemals durch andere Stage-PASS-Werte überschreiben. B.16-Blocker, B.10-ADR-Hypothesen und B.18-gezielte Alternativprobe erst nach Risikobewertung. Änderungen an Code/Contract/Config/Schema verlangen geänderten Versionsbeleg und erneute passende Stage-Tests.
8. **Beide Stufen getrennt beurteilen:** Nur nach echten Nachweisen „local verified“ bzw. „staging verified“ für exakt den getesteten Teilumfang. Das zusammengeführte B.11-Ergebnis darf allein die **gemessenen** Invarianten stützen; FakeAuth bleibt begrenzt, R1/R2-B.9- und B.8-Gesamtgates bleiben separat.
9. **Bereinigen, nicht produktiv übernehmen:** Synthetische Sessions/Keys/Worlds/Jobs/Media/Logs/Backups nach festgelegter sicherer Test-Retention behandeln; keine LiveCampaign-Restore-/WorldReset-/Roll-/Quest-/NPC-/Item-/Traktorwirkung. Geeigneten Code erst nach B.12-Härtung und gesonderten Freigaben integrieren.

## 4. Vergleichbare Testfälle je Stage

| Testkonstellation | L – lokale Probe | V – isolierte VPS-/Staging-Probe |
|---|---|---|
| Zwei unabhängige GM-/PlayerSessions, nur eine aktive GMEpoch | Echte getrennte lokale BrowserSessions/Actorgrants | Echte Remote-Browsersessions, gleiches rechtliches Fachmodell, Netz-/Host-/Proxygrenzen |
| Erlaubte WorldAction | Tatsächliche atomare TestWorldRevision + OriginalOperationReceipt | Erneut tatsächlicher Commit/Receipt im **eigenen** VPS-Teststore |
| Verbotener fremder Actor/Source/GM/HistoryRead | Keine Mutation/Secretbytes, kein verräterischer Fehler | Dasselbe über echte HTTP-/WS-/Media-/Netzpfade |
| DuplicateId, ConcurrentRevision, LostAck | Genau ein Originalergebnis, kein zweiter Commit | Konkurrenz/Netzabbruch unter realen VPS-Verhältnissen erneut prüfen |
| Session-/Gm-/Actor-/SourceRevoke nach Read oder vor PendingCommit | Neue unzulässige Reads/Pushs/Mutationen blockiert | Auch bei veralteten Cursors/WS-/Tab-/MediaLinks und RemoteClients blockiert |
| Writer- und Prozessneustart | Persistente Fences/Receipts mit neuem Prozess | Echter VPS-Service-/DB-/WriterRecovery-Fall, alter Writer nie autoritativ |
| Outbox-/WS-Zustellung gestört | Commit bleibt, berechtigte spätere Zustellung ohne Replay | Gleiches bei Proxy-/Netz-/Worker-/Betriebsunterbrechungen |
| Umgebungsisolation/Testdaten | Synthetische LocalWorld, keine Prodkeys/DMs | Eigene StagingWorld, getrennte Host-/Storage-/Keys-/Logs-/Backups, keine Produktauswirkung |
| Ergebnisevidenz | Exakte Local-Candidate-/Build-/Fixture-/Receiptbelege | Eigene konkrete VPS-/Deployment-/Network-/Server-/Receiptbelege; Local-PASS nicht übertragen |

## 5. Verbotene Abkürzungen und Negativfälle

- **Nur lokale Tests grün:** V-Stufe bleibt NOT_RUN. **Keine** Aussage, der Test sei VPS-tauglich, zuverlässig im Internet oder produktiv freigegeben.
- **VPS-Staging verwendet Produktiv-DB, produktive SteamSessions, PrivateDMs oder KeyStore:** V-Stufe **BLOCKED**, kein Teststart; Testkonten oder Quellgrant nicht durch bloße Umgebungsvariablen als isoliert behaupten.
- **VPS hat Staging-/Prod-Prozesse auf einer Maschine:** Nur bei tatsächlich nachgewiesenen wirksamen Fences zulässig; dedizierter Test-VPS ist möglich, aber **kein allgemeiner Mehr-VPS-Zwang** für den späteren Einzel-VPS-Betrieb.
- **Client sieht GM-only-Feld nach Reconnect oder Cachewarmup:** Security-FAIL, selbst wenn ursprüngliche lokale Tests erfolgreich waren.
- **LostAck führt zu neu erzeugter OperationId und zweitem Roll-/Quest-/WorldCommit:** FAIL; OriginalReceipt-Reconciliation statt Automatik-Replay.
- **Netz- oder DB-Neustart erzeugt zweite WorldWriterAuthority:** FAIL. Keine ungesicherten Workarounds, die 14.13-WriterFence umgehen.
- **Gleicher Code, andere Schema-/Security-Config:** Getrennte Vergleichsabweichung dokumentieren und erforderliche Regression wiederholen, niemals ungeprüft „identisch“ behaupten.
- **Fixture/Teststatus wird zu echtem Kampagnenstand kopiert:** Verboten; weder B.11 noch B.19 geben einen 08.3-/08.5-/09.6-/14.6-/15.4-Publish-/Restore-/Worldcommit frei.
- **Echte Steam-Authentifizierung im produktiven Sinn fehlt:** Synthetische Session-/CurrentACL-Probe als begrenzte ContractEvidence kennzeichnen; 14.1-Steam-/Account-/Browserintegration später separat wirklich nachweisen.
- **Audio, volle Regelwerke oder komplette UI fehlen:** Für B.11 zulässige begrenzte Nichtziele; der umfassende **B.2-B-Spielrelease** bleibt trotzdem unverändert erforderlich.

## 6. Schlussstatus und nächste grundlegende Frage B.20

**B.19 C beschlossen:** Zuerst minimal und reproduzierbar lokal prüfen, danach denselben fachlichen Kandidatenpfad in einer realen, isolierten Einzel-VPS-/Staging-Umgebung gesondert prüfen; **beide** Ergebnisse versioniert, umgebungsgetrennt und mit Negativfällen. B.17-Readiness, B.18-Kandidatenauswahl und B.11-Testruns wurden noch **nicht** tatsächlich ausgeführt. Diese Dokumentation ist keine automatische Deploymentgenehmigung und kein 14.6-/15.4-Release.

### B.20 – Wie stellen wir sicher, dass bei den beiden Teststufen wirklich derselbe überprüfte Softwarestand verwendet wird?

- **A – Code und Konfiguration jeweils manuell auf die VPS kopieren:** Einfach, aber schwer reproduzierbare Abweichungen, vergessene Dateien und nicht nachvollziehbare Build-/Dependency-/Secretzustände.
- **B – Lokal und auf der VPS jeweils unabhängig aus dem aktuellen Hauptbranch bauen:** Bequem, aber neue Commits, transitive Abhängigkeiten und unterschiedliche Laufzeit-/Securitykonfigurationen können zu inhaltlich verschiedenen Testergebnissen führen.
- **C – Versionierte, reproduzierbare Buildartefakte mit getrennten sicheren Umgebungskonfigurationen und Provenienz (Empfehlung):** Genau geprüfte Quell-/Dependency-/Schema-/TestFixtureRevisionen und unveränderliche Buildidentität/Digest festhalten; denselben freigegebenen Testkandidaten in LOCAL_DEV und ISOLATED_VPS_STAGING mit ausschließlich zulässigen, ausdrücklich getrennten Secrets/RuntimeSettings ausführen. Bei Abweichungen Build-/Config-/MigrationCompatibility neu prüfen und betroffene Tests wiederholen. Ein Testartefakt wird dadurch **nicht** automatisch ein produktiver 14.6-/15.4-Release.
