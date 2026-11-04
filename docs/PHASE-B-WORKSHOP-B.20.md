# AdventureShift – Phase B, Beschluss B.20 C: reproduzierbare Testbuilds und strikt getrennte Umgebungskonfiguration

**Nachfolgender Beschluss B.22 C (04.11.2026):** [Später technisch geschützter Git-Hauptzweig mit scopegerechten Pflichtprüfungen und berechtigter B.12-/B.14-/B.15-Owner-/Security-/Contract-/Migration-/B.13-Reviewabnahme](PHASE-B-WORKSHOP-B.22.md). Kritische FAIL-/BLOCKED-/NOT_RUN-Gates sperren Codeintegration; Prüf- und CI-Schutzänderungen dürfen nicht unbemerkt eigene Kontrollen ausschalten. **Noch kein GitHub-Ruleset/Branchschutz/CI tatsächlich eingerichtet, keine B.11-/B.17-/B.18-/B.19-/B.20-Technikprobe ausgeführt.** Intern geprüfter Merge ist keine WorldAction und keine B.2-B-/B.8-/B.9-/14.6-/15.4-Produktivfreigabe. **Nächste Grundfrage B.23: Abschluss der Grundsatzplanung und Übergang zur echten isolierten technischen Umsetzung.**

**Nachfolgender Beschluss B.21 C (04.11.2026):** [Isolierter Git-Branch/Worktree für B.11-/B.19-Technikspikes, ohne ungehärteten FakeAuth-/TestOnly-/WorldWriter-Code auf `main`; selektive Übernahme nur nach B.12-/B.14-/B.15-Härtung und echten Tests](PHASE-B-WORKSHOP-B.21.md). B.20-Build-/B.19-Stage-/B.10-ADR-Evidenz bleibt versionsgebunden; Worktree/Branch ist **keine** 14.8-Daten-/Secret-/VPS-Sicherheitsisolation. **Noch kein Experimentzweig angelegt und kein B.11-/B.17-/B.18-/B.19-/B.20-Test tatsächlich durchgeführt.** Git-Merge ist kein 14.6-/15.4-Release und kein B.2-B-/B.8-/B.9-Gesamtnachweis. **Nächste Grundfrage B.22: überprüfbare Schutz- und Integrationsgates für `main`.**

**Stand:** 04.11.2026. **B.20 C vom Projektinhaber ausdrücklich beschlossen.**
**Status:** Verbindliche technische Grundstruktur für künftige B.11-/B.19-Testartefakte. **Noch kein Build erzeugt, kein Build-/Digestvergleich ausgeführt, keine B.17-Readiness festgestellt, keine B.18-Kandidaten technisch bewertet, keine lokale oder VPS-Probe durchgeführt, keine finale Technologie und kein StableRelease gewählt.**
**Entscheidung C:** LOCAL_DEV und ISOLATED_VPS_STAGING verwenden **dieselbe überprüfte und versionsgebundene Anwendungsrevision**, reproduzierbare Build-Eingaben, dokumentierte Abhängigkeiten und überprüfbare Artefaktidentitäten. Innerhalb gleicher Zielplattform/Architektur wird nach Möglichkeit **dasselbe unveränderliche Buildartefakt** per Prüfsumme/Digest wiederverwendet; bei verschiedenen Betriebssystem-/CPU-/Runtimezielen werden die nötigen separaten zielgebundenen Artefakte nachvollziehbar aus **derselben Source-/Dependency-/Toolchain-Revision** erstellt und durch Compatibility-/Parity-Nachweise verglichen. Geheimnisse und zulässige Laufzeiteinstellungen sind **getrennt je Umgebung**, nicht eingebaut und nicht aus Produktion kopiert. Abweichungen im Programm-, Schema-, Toolchain- oder Sicherheitskonfigurationsstand verlangen konkrete erneute Prüfungen. Ein Testbuild bleibt **Nicht-Produktionscode** ohne automatische B.12-/14.6-/15.4-Freigabe.
**Unverändert:** Selbst betreibbarer Einzel-VPS, SL und Spieler in eigenen Browsern, **genau ein aktiver Spielleiter je Campaign**, eine CampaignWorld und eine gültige WorldWriter-Autorität. Session-/GM-/Actor-/Owner-/Source-/History-/Fog-/Privacy-/Key-/Media-/Host-/Support-/Securityrechte bleiben getrennt; kein zweiter WorldWriter durch parallele Build-/Deployvorgänge.
**Bezüge:** [B.1](PHASE-B-WORKSHOP-B.1.md) · [B.2](PHASE-B-WORKSHOP-B.2.md) · [B.3](PHASE-B-WORKSHOP-B.3.md) · [B.4](PHASE-B-WORKSHOP-B.4.md) · [B.5](PHASE-B-WORKSHOP-B.5.md) · [B.7](PHASE-B-WORKSHOP-B.7.md) · [B.8](PHASE-B-WORKSHOP-B.8.md) · [B.9](PHASE-B-WORKSHOP-B.9.md) · [B.10](PHASE-B-WORKSHOP-B.10.md) · [B.11](PHASE-B-WORKSHOP-B.11.md) · [B.12](PHASE-B-WORKSHOP-B.12.md) · [B.13](PHASE-B-WORKSHOP-B.13.md) · [B.14](PHASE-B-WORKSHOP-B.14.md) · [B.15](PHASE-B-WORKSHOP-B.15.md) · [B.16](PHASE-B-WORKSHOP-B.16.md) · [B.17](PHASE-B-WORKSHOP-B.17.md) · [B.18](PHASE-B-WORKSHOP-B.18.md) · [B.19](PHASE-B-WORKSHOP-B.19.md); [14.1](SICHERHEIT-WORKSHOP-14.1.md) · [14.2](SICHERHEIT-WORKSHOP-14.2.md) · [14.5](SICHERHEIT-WORKSHOP-14.5.md) · [14.6](SICHERHEIT-WORKSHOP-14.6.md) · [14.7](SICHERHEIT-WORKSHOP-14.7.md) · [14.8](SICHERHEIT-WORKSHOP-14.8.md) · [14.9](SICHERHEIT-WORKSHOP-14.9.md) · [14.12](SICHERHEIT-WORKSHOP-14.12.md) · [14.13](SICHERHEIT-WORKSHOP-14.13.md) · [15.4](ERWEITERUNGEN-WORKSHOP-15.4.md).

## 1. Gemeinsame unveränderliche Build-Basis

1. **Quellrevision fixieren:** Eindeutiger Git-Commit/SourceTree und zulässiger Testscope, keine ungeprüften Dateien oder ein sich zwischen Tests verändernder Hauptbranch. TestOnly-Funktionen und synthetische Fixtures werden gekennzeichnet und später vor Produktionsübernahme nach B.12 entfernt oder strikt isoliert.
2. **Abhängigkeiten fixieren:** Direkte und transitive Libraries, Build-/Runtime-/Testtools, Lockdateien, zulässige Paketquellen, Buildscripts, Zielplattform und Lizenz-/Wartungsstände soweit für den konkreten Spike nötig dokumentieren. Keine unkontrollierte „latest“-Auflösung beim Staging-Start.
3. **Artefakt bauen und identifizieren:** BuildDigest/Manifest über das *tatsächlich* zu startende Artefakt, Zielplattform, relevante Runtime-/Toolchain-/Schema-/Fixtureversion und Verifikationsweg festhalten. Ein Hash behauptet keine Sicherheit, sondern nur überprüfbare Identität.
4. **Gleiche Zielumgebung, gleiches Artefakt:** Wo technisch lauffähig, bereits lokal geprüftes unveränderliches Artefakt nach Verifikation auf der Staging-VPS einsetzen; kein stiller Neu-Build dort. Äquivalente Umgebungen können passende eigene Testdaten/Secrets verwenden.
5. **Verschiedene Zielplattformen:** Falls etwa Windows-PC und Linux-VPS keine gemeinsame Binär-/Container-Laufzeit besitzen, getrennte Zielartefakte derselben definierten Source-/Dependencybasis erzeugen. Solche Artefakte sind **nicht byteidentisch**; Versions-/Konfigurations-/Contractvergleich und jeweils real ausgeführte Tests belegen die fachliche Gleichwertigkeit nur für den geprüften Umfang.
6. **Schema-/Vertragsbindung:** B.4-/B.14-Owner-/Event-/Receipt-/World-/Viewer-/Security-/RulePack-/FeatureVersionen und passende 14.6-Migrationsstände werden explizit mit der Testversion gekoppelt. Unzulässige Mischstände verweigern die Testausführung, nicht still mit „best effort“ umdeuten.
7. **Keine versteckten Seiteneffekte:** Build, Artefaktkopie, Konfigurationswechsel, Deployment ins isolierte Staging und Teststart dürfen keine reale CampaignWorld-, Roll-, Quest-, NPC-, Item-, Traktor-, ActorControl- oder GM-Rechteänderung auslösen.

## 2. Getypte Planungs- und Nachweisobjekte (Arbeitsnamen)

| Objekt | Zweck und Grenze |
|---|---|
| **SourceRevision / DependencyLockRevision** | Exakter Quell-/Abhängigkeits-/Buildscripteingang, inklusive zulässiger Paketquelle und Versionsstand |
| **ToolchainTarget / PlatformCompatibility** | Relevante Compiler-/Runtime-/OS-/CPU-/Buildparameter und belegte Zielkompatibilität; keine unbelegte plattformübergreifende Byteidentität |
| **BuildArtifact / ImmutableArtifactDigest** | Tatsächlich erzeugtes und später gestartetes artefaktspezifisches Hash-/Provenienzmerkmal, gegen Manipulation/Verwechslung prüfbar |
| **BuildProvenance / CandidateManifest** | Herkunft, Buildpipeline, Testkandidat, TestOnly-Kennzeichen, gelaufene Checks und eventuell noch offene Supply-Chain-/Lizenzfragen |
| **EnvironmentConfigProfile / SecretRef** | Versionierte zulässige nichtgeheime Einstellungen und getrennte SecretReferenzen für LOCAL_DEV und ISOLATED_VPS_STAGING, niemals Secretbytes im Git-/Build-/Testbericht |
| **SchemaCompatibility / FixtureRevision** | TestWorld-/DB-/Event-/Receipt-/Projectionversion mit explizit zulässigen Migrations- und Fixturekombinationen |
| **StageRunEvidence / RuntimeIdentity** | In der echten Stage gestarteter BuildDigest, Source-/Schema-/Configversion, redigierte aktuelle Laufzeitinformationen, tatsächlich gemessene Tests |
| **DriftFinding / ReverificationDecision** | Abweichung, betroffene B.11-/B.17-/B.19-Tests, erneute Ausführung, PASS/FAIL/BLOCKED/NOT_RUN; keine automatische Bestätigung |
| **TestArtifactDisposition / NoProdReleaseFence** | Nur Testartefakt, mit ausdrücklich getrennter B.12-Härtung und B.8-/B.9-/14.6-/15.4-StableReleasefreigabe |

Die Begriffe definieren **Dokumentations- und Buildverträge**, keine neue allgemeine CI-/Cloud-/Deployment-/WorldEngine. Die konkrete Buildtechnologie, Prüfsummen-/Signaturlösung, Registry und Paketform wird bei B.18-Kandidatenbewertung festgelegt.

## 3. Sicherer Umgang mit umgebungsspezifischen Einstellungen

- **Erlaubt unterschiedlich:** Isolierte Serviceadressen, Testports/Hostnamen, Test-DB-/Blob-/Queue-/Media-/Backup-Namespaces, lokale vs. VPS-kompatible Pfade, TestAccounts, getrennte Session-/Key-/Tokenmaterialien, Monitoringziele und innerhalb der Fachverträge zulässige Last-/Log-/Timeoutwerte.
- **Nicht als nebensächliche Configdrift behandeln:** Abschalten von CurrentACL/Source-/History-/Privacychecks, fehlende WriterFence-/OriginalReceipt-Persistenz, TestAdmin/ReadAll, ungeschützte CORS-/WS-/Mediafreigaben, permissive Security-/RateGrenzen, andere Command-/Event-/Schema-/Rule-/Ownersemantik oder abweichendes Authmodell. Solche Unterschiede verlangen eigene Analyse und blockieren bei kritischer Unverträglichkeit den Vergleich.
- **Nur Referenzen, niemals Secretrohwerte:** Vertrauliche Konfiguration außerhalb von Git, Artefakten und unredigierten CI-/Buildlogs; keine Kopie produktiver Keys, SteamSessions, privater DMs oder GM-/NPC-/Quest-/PlayerSecret-Quellen nach Staging.
- **Beim Start erneut prüfen:** BuildDigest, erlaubte EnvironmentId, DB-/Schema-/World-/Receipt-/Source-/Secret-/Key-/WS-/Media-Fences, sichere Betriebsparameter und B.17-Readiness. Unbekannter oder nicht zulässiger Build-/Config-/SchemaMix führt zu BLOCKED statt zu produktivem oder still degradiertem Betrieb.
- **Keine automatische Promotion:** Ein erfolgreicher Testbranch/Build im Staging bleibt in 14.8-Testscope. Veröffentlichung, Migration, World-/Rule-/Extensionänderung und produktives Deployment erfordern ihre vorhandenen getrennten Fach-/Releasefreigaben.

## 4. Ablauf von lokaler Prüfung zu Staging und zurück zu Evidenz

1. **Ausgangslage prüfen:** B.18-Kandidatenpfad und tatsächlich abgelegter B.17-Readiness-Nachweis, isolierte Testumgebung und erforderliche B.11-Testmatrix vorhanden; fehlende Voraussetzungen nicht als „READY“ deklarieren.
2. **Testbuild festhalten:** Source-/Dependency-/Toolchain-/Target-/Schema-/FixtureVersion fixieren, TestOnly-Provenienz vermerken, unveränderliches Artefakt erzeugen und Digest **wirklich** berechnen.
3. **LOCAL_DEV-Run:** Unabhängige GM-/Player-Browser und TestServices mit ausschließlich synthetischen Accounts/Secrets/Worlds starten; gestarteten ArtefaktDigest und zulässige ConfigRevision mit getesteter DB-/SchemaRevision erfassen. B.11-Positiv-/Negativtests ausführen und Observations dokumentieren.
4. **Vor Stagingtransfer:** Transferprüfung desselben Artefakt-Digest, sofern zielkompatibel; andernfalls getrennte Zielartefakte mit verifizierter gemeinsamer Source-/Dependency-/Toolchain-Provenienz und ausdrücklich begrenzter Gleichwertigkeitsaussage. Keine Änderungen unter demselben Buildnamen.
5. **ISOLATED_VPS_STAGING-Run:** Eigenständige B.17-/14.8-ScopeReadiness, getrennte Testkeys/IDs/Stores und CurrentACL nachweisen. Gestartete Artefakt-/Config-/Schema-/Runtimeidentität messen, B.19-VPS-/Network-/MultiBrowser-/Writer-/Reconnect-/Revoke-/Restart-/Outboxfälle tatsächlich ausführen.
6. **Drift und Fehler:** Digest-/Config-/Contract-/Dependency-/Schemaabweichungen oder neue Sicherheitsfehler dokumentieren, betroffene Stage-/B.11-Nachweise auf NOT_RUN/BLOCKED/FAIL setzen und nach Korrektur wiederholen. Unveränderte alte Belege können historisch erhalten bleiben, gelten jedoch nicht für den neuen Build.
7. **Archivierung/Weitergabe:** Redigierte, unveränderlich referenzierbare Testevidenz und B.10-ADRInput behalten. B.12 erlaubt nur einzeln gehärtete Codeübernahme, kein automatisches Merge-/Release-/ProdDeploy aus einem positiven Test.
8. **Aufräumen:** Synthetische Sessions, Schlüssel, Testdaten, temporäre Artefakte und Staging-Stores gemäß 14.8-/14.5-/14.6-Retention-/Cleanupregeln behandeln; keine echte Spielwelt zurücksetzen oder in Teststände verwandeln.

## 5. Verbindliche Negativfälle

| Konstellation | Erforderliche Reaktion |
|---|---|
| Git-HEAD ist gleich, transitive Abhängigkeit oder Toolchain wurde neu aufgelöst | Buildidentität verändert oder nicht belegbar: passende Tests erneut; kein pauschales „identisch“ |
| Lokal auf Windows und VPS auf Linux entstehen verschiedene Binärdateien | Unterschiedliche Digests sind erwartbar; gleiche Source-/Dependencyrevision und Target-/Contract-Parität **tatsächlich** nachweisen |
| Container-/Paketname bleibt, Bytes/Digest ändern sich | Neue Artefaktidentität, keine Übernahme des alten Testergebnisses |
| Gleicher ArtefaktDigest, aber andere DB-/Schema-/WorldWriter-/SourceACL-Config | Umgebungsspezifischen Impact/Compatibility und betroffene Sicherheits-/Worldtests neu prüfen |
| Secret versehentlich in Artefakt/Buildlog | Testfreigabe blockieren, Material gemäß 14.5/14.8 sicher behandeln; bloßer Hash schützt nicht vor Secret-Leak |
| Test-/DebugAuth im vermeintlichen Produktionsbuild erreichbar | B.12-Härtungs-/14.6-Releasegate BLOCKED; synthetisches Bestehen keine Authfreigabe |
| VPS lädt eine neue Libraryversion beim Start nach | Unfixierte RuntimeDependencies: Staging-Nachweis nicht mit lokalem gleichsetzen |
| Neuere SchemaVersion wird auf alte WorldRevision/OriginalReceipts ohne Kompatibilitätsprüfung angewandt | Verweigern, B.14-/14.6-Schema-/Migration- und WorldReceipt-Schutz einhalten |
| Lokaler B.11-Test PASS, Staging-Run mit anderem Artifact oder Config bleibt ungetestet | Staging NOT_RUN oder BLOCKED; keine VPS-Gesamtbehauptung |
| Staging-Artefakt erhält trotz erfolgreichem B.11-Einzeltest einen ProductReleaseTag | Kein tatsächliches 14.6-/15.4-Release; echte B.2-B-/B.8-/B.9-Gates weiterhin offen |
| Neuaufbau nach Korrektur des WriterFence/ACL-Codes | Neuen Digest erzeugen und passende Konkurrenz-/Revoke-/Receipt-/Recovery-Gates wiederholen |
| Umgebungseinstellungen ändern zulässige Testkapazität | Daten-/Performancevergleich nur bei dokumentierten Bedingungen und Quotas; keine erfundenen VPS-Leistungswerte |

## 6. Historische Anschlussfrage B.21 (inzwischen C beschlossen)

**B.20 C ist beschlossen, aber nicht implementiert.** Weder eine Buildpipeline, ArtifactRegistry, Containerlösung, Programmiersprache, reproduzierbares Paket, synthetische Testwelt noch ein konkreter B.11-Testlauf wurden dadurch erstellt. B.2-B-Fachbreite, B.8-/B.9-Releasegates und 14.6-/15.4-Freigaben bleiben unverändert Pflicht.

### B.21 – Wie schützen wir die offizielle Entwicklungsbasis vor ungehärtetem Technikspike-Code?

- **A – Den B.11-Spike direkt auf dem Hauptbranch entwickeln:** Einfache Versionsverwaltung, aber TestOnly-/FakeAuth-/Experimentcode kann unbemerkt als reguläre Architekturgrundlage gelten.
- **B – Die Probe in einem völlig getrennten, nicht verbundenen Repository erstellen:** Starke räumliche Trennung, aber nachweisbare Source-/Contract-/Evidenzverknüpfung, geprüfte Übernahme und Regression können unnötig erschwert werden.
- **C – Isolierter Spike-Branch/Worktree mit gezielten Qualitäts- und Übernahmegates (Empfehlung):** Die B.11-/B.19-Tests werden mit synthetischen Fixtures und explizitem NoProd-Testprofil in getrenntem Entwicklungszweig oder Worktree versioniert. Der offizielle gemeinsame Basiszweig bleibt vom ungehärteten Testcode getrennt; Build-/Evidence-/ADR-Bezüge bleiben erhalten. Erst nach wirklich bestandenen B.17-/B.11-Gates und B.12-Sicherheits-/Lizenz-/Owner-/Contract-/Recovery-Härtung dürfen **geeignete** Komponenten selektiv nach B.14-/B.15-Review übernommen werden. Kein pauschales Zusammenführen, kein automatisches Deployment und keine Freigabe durch Branchwechsel allein.
