# AdventureShift – Phase B, Beschluss B.16 C: gezielte Konfliktbehandlung und sichere Beschlussabweichungen

**Nachfolgender Beschluss B.19 C (04.11.2026):** [Zweistufiger echter B.11-Techniktest: zuerst reproduzierbarer synthetischer LOCAL_DEV-Vertikalschnitt, dann gleicher geprüfter Teststand auf 14.8-isolierter Einzel-VPS-/Staging-Umgebung](PHASE-B-WORKSHOP-B.19.md). Eigene Environment-/Session-/World-/Receipt-/Key-/Media-/Backup-/Network-Sicherheitsgrenzen, aktuelle GM-/Actor-/Source-/History-/Privacyrechte, reale WriterFence-/Duplicate-/LostAck-/Revoke-/Reconnect-/Restart-/Outbox-Negativprüfungen und getrennte Build-/DB-/Browser-Evidenz in beiden Stufen. **Kein VPS-Test ohne wirksame Isolation; lokale PASS-Ergebnisse belegen keine Staging-Erfüllung. B.17-Readiness und B.11-Tests sind weiterhin nicht ausgeführt, B.18-Kandidaten nicht bewertet; keine Produktionsfreigabe.** **Nächste Grundfrage B.20: identische reproduzierbare Artefakte und sichere Umgebungskonfiguration.**

**Nachfolgender Beschluss B.18 C (04.11.2026):** [Kleine risikogebundene Technik-Shortlist und ein primärer isolierter B.11-P1/P2/P3-Testpfad mit nur gezielt nötigen Alternativproben und versionierten B.10-ADRs](PHASE-B-WORKSHOP-B.18.md). Serverautorität, 14.12-WorldTransaction-/OriginalReceipt, 14.13-SingleWriter/Fence, aktuelle Auth-/GM-/Actor-/Source-/History-/Privacy-/Viewerrechte, SingleVPS, Lizenz, Wartung und Recovery sind verbindliche Eignungsgrenzen. **Noch keine Kandidaten recherchiert, kein Stack final gewählt, B.17-Readiness nicht ausgeführt, B.11-Spike NOT_RUN, B.12-/B.13-Produktion nicht freigegeben.** Keine parallelen vollständigen Full-Stacks und kein B.2-/B.8-/B.9-/14.6-/15.4-Release durch Spikeerfolg. **Nächste Grundfrage B.19: getrennte lokale und VPS-/Staging-Testausführung.**

**Nachfolgender Beschluss B.17 C (04.11.2026):** [Begrenzter Architektur-/Sicherheits-Readiness-Check vor der ersten echten B.11-P1/P2/P3-Technikprobe](PHASE-B-WORKSHOP-B.17.md). Testscope, B.10–B.16-Verträge, 14.8-synthetische Isolation, Kandidaten, echte WorldWriter-/CurrentACL-/OriginalReceipt-/Audience-/Revoke-/Reconnect-/Recovery-Positiv-/Negativkriterien und redigierte Evidenz vor Testbeginn prüfen. **Preflight nur geplant, nicht ausgeführt; B.11 weiterhin NOT_RUN, B.12 nicht gehärtet, kein Stack und kein B.2-Spielrelease freigegeben.** Keine Vollplanung aller UI-/RulePack-Feindetails und keine produktiven Testdaten. **Nächste Grundfrage B.18: begrenzte Auswahl und Prüfung der Technik-Kandidaten.**

**Stand:** 04.11.2026. **B.16 C vom Projektinhaber ausdrücklich beschlossen.**
**Status:** Verbindliche fachliche Planungs- und Änderungsgrundstruktur, **keine Softwareimplementierung**. B.11-Technikprobe nicht ausgeführt, B.12-Code nicht produktionsgehärtet, B.13-Vertikalschnitte nicht implementiert, B.14-Änderungsprozess nicht als Software umgesetzt, B.15-Aufträge noch keine ausgeführten Entwicklungsschritte. Keine finale Technologie-/Frameworkwahl, kein spielbarer Release.
**Entscheidung C:** Bei widersprüchlichen, nicht tragfähigen oder unklaren bestehenden Anforderungen wird **gezielt der betroffene Entwicklungs-/Änderungs-/Freigabepfad blockiert**. Konkrete Fundstelle, geltende Beschlüsse einschließlich Ausschlüssen, Auswirkungen, zulässige Lösungen und nachzuweisende Tests werden versioniert nachvollziehbar dokumentiert. Fachliche oder sicherheitsrelevante Änderungen benötigen vor ihrer Verwendung eine **ausdrückliche sachlich zuständige Entscheidung** und – sofern ein gemeinsamer Vertrag betroffen ist – B.14-Impact-/Versions-/Migrations-/Verbraucherprüfung. Nicht betroffene, nachweislich sichere Entwicklungsarbeiten dürfen weitergehen. Kein stilles Überschreiben früherer Entscheidungen, keine pauschale Freigabe und keine zusätzliche Incident-/World-/RuleEngine.
**Unveränderte V1-Grenzen:** Selbst betreibbarer Single-VPS, separate Spielleiter- und Spielerbrowser, **genau ein aktiver Spielleiter pro Kampagne**, eine kanonische CampaignWorld und nur eine gültige autorisierte WorldWriter-Generation; Module und RulePacks bleiben versioniert, optional und regelwerksneutral. Fach-/Security-/Privacy-/Host-/Support-/GM-/Actor-/Source-/Historyrechte bleiben getrennt.
**Zusammenhang:** [Planungsstandard](PLANUNGSSTANDARD.md) · [B.1](PHASE-B-WORKSHOP-B.1.md) · [B.2](PHASE-B-WORKSHOP-B.2.md) · [B.3](PHASE-B-WORKSHOP-B.3.md) · [B.4](PHASE-B-WORKSHOP-B.4.md) · [B.5](PHASE-B-WORKSHOP-B.5.md) · [B.7](PHASE-B-WORKSHOP-B.7.md) · [B.8](PHASE-B-WORKSHOP-B.8.md) · [B.9](PHASE-B-WORKSHOP-B.9.md) · [B.10](PHASE-B-WORKSHOP-B.10.md) · [B.11](PHASE-B-WORKSHOP-B.11.md) · [B.12](PHASE-B-WORKSHOP-B.12.md) · [B.13](PHASE-B-WORKSHOP-B.13.md) · [B.14](PHASE-B-WORKSHOP-B.14.md) · [B.15](PHASE-B-WORKSHOP-B.15.md); [09.7](KAMPAGNEN-WORKSHOP-09.7.md), [14.1](SICHERHEIT-WORKSHOP-14.1.md), [14.2](SICHERHEIT-WORKSHOP-14.2.md), [14.6](SICHERHEIT-WORKSHOP-14.6.md), [14.8](SICHERHEIT-WORKSHOP-14.8.md), [14.12](SICHERHEIT-WORKSHOP-14.12.md), [14.13](SICHERHEIT-WORKSHOP-14.13.md), [14.15](SICHERHEIT-WORKSHOP-14.15.md), [15.2](ERWEITERUNGEN-WORKSHOP-15.2.md).

## 1. Wann eine Abweichung als Blocker gilt

1. **Widerspruch:** Zwei bindende Beschlüsse/Verbote verlangen für denselben Fall unterschiedliche Domain- oder Sicherheitswirkungen; keines wird allein aufgrund des Alters, der Codestelle oder einer allgemeinen „Empfehlung“ still verdrängt.
2. **Technisch widerlegte Annahme:** Ein reproduzierbarer realer B.10-/B.11-/B.13-/B.14-Test belegt, dass ein geforderter WorldWriter-/Receipt-/Auth-/Projection-/Rule-/VPS-Vertrag auf dem bisherigen Pfad nicht korrekt funktioniert. **Ungetestet ist nicht widerlegt und nicht bestanden.**
3. **Unklare Grundstruktur:** Fehlende Festlegung beeinflusst Fachowner, Domainreferenz, Autorisierung, History/Audience, WorldCommit, Contract-/Migrationversion oder zwingenden Releaseumfang. Feindetails wie Spacing, einzelne Zahlen, Farben oder Defaultslotzahlen sind nach Planungsstandard keine neuen Grundsatzblocker, sofern sie keine solche Wirkung haben.
4. **Security-/Privacy-/Lizenzrisiko:** Geheime GM-/NPC-/Quest-/Player-/DM-Daten, Steam-/Session-/Actor-/Source-/History-/Medienrechte, Key-/Host-/Supportprivilegien oder unklare Nutzungsrechte könnten durch eine Änderung unzulässig erweitert werden. Betroffenen Pfad nicht freischalten, bis Rechte und Quelle tatsächlich geklärt sind.
5. **Verträglichkeits-/Betriebsbruch:** Gewünschte Lösung würde alte gepinnte Kampagnen, echte WorldRevision/OriginalReceipts, 14.6-Migration/Recovery, 14.13-WriterFence oder B.2-/B.8-/B.9-Freigabekriterien still ändern.

**Keine neue globale Stoppautomatik:** Ein fachliches Konfliktdokument sperrt die betreffende Entwicklungs-/Contract-/Releaseentscheidung, erzeugt aber **keine neue laufende Produktiv-SessionSperre, SecurityIncidentEngine oder Worldmutation**. Reale bestehende Sicherheitsvorfälle bleiben 14.15 A und den jeweils tatsächlich zuständigen 14.x-Sicherheitsoperationen unterstellt.

## 2. Typisierte Planungsobjekte – keine zusätzliche Engine

| Arbeitsname | Zweck / Grenze |
|---|---|
| **ConflictFinding / EvidenceRef** | Exakter betroffener Beschluss, Code-/Contract-/Teststand, nachweisbare Beobachtung oder konkrete Unklarheit; vertrauliche Inhalte redigieren |
| **ScopeImpact / DependencyFence** | Engste betroffene B.15-Aufträge, B.13-Slices, B.14-Contracts, RulePacks, Sources, World-/Viewer-/Migration-/Releasepfade; keine globale Blockade ohne eigenen Grund |
| **ResolutionOptions / TradeoffRecord** | Fachlich zulässige Alternativen mit Sicherheits-, SingleVPS-, Regelwerksneutralitäts-, Daten-/Lizenz-/Wartbarkeitsfolgen und verworfenen Varianten |
| **DecisionAuthority / ChangeApproval** | Ausdrücklich zuständige fachliche Entscheidung bei materieller Anforderungsänderung; technisches Review allein erteilt keine GM-/World-/Security- oder Produktrechte |
| **ContractChangeLink / MigrationImpact** | Falls betroffen, B.14-Version-/Consumer-/Adapter-/Schema-/SafePoint-/Rollback- und 14.6-/15.2-Kampagnenpin-Schutz |
| **ResolutionEvidence / RegressionMatrix** | Ausgeführte positive/negative Prüfungen am genauen Build-/Schema-/RulePack-/Fixture-/Security-/Worldstand mit PASS/FAIL/NOT_RUN/BLOCKED |
| **ConflictDisposition** | OPEN, BLOCKED, DECIDED, IMPLEMENTED, VERIFIED oder REJECTED; eine dokumentierte Entscheidung ist **noch kein** bestandener technischer Test oder Release |

Diese Arbeitsbegriffe beschreiben die **Git-/Dokumentations-/Entwicklungsnachweise**, nicht einen neuen LiveGame-Status, neue automatische IncidentContainment-Logik, neue Berechtigung oder einen eigenen fachlichen Writer.

## 3. Kontrollierter Klärungs- und Umsetzungsablauf

1. **Fund dokumentieren:** Exakte Ausgangsbeschlüsse und Verbote, Versionen, betroffenes Verhalten, reproduzierbare Fehler oder ausdrücklich fehlende Evidenz erfassen. Keine hypothetische Abweichung als tatsächlich bewiesenen Fehler ausgeben.
2. **Sicherheits-/Fachrisiko einstufen:** Maßgebliche DomainOwner nach B.4/B.14, Auth-/GM-/Actor-/Source-/History-/Fog-/Privacy-/Rule-/WorldWriter-/Quota-/Asset-/License-/Retention-Grenzen und laufende Kampagnenpinstände feststellen; Unbekanntes als offen benennen.
3. **Gezielt sperren:** Nur tatsächlich betroffene B.15-Arbeitsaufträge, Releases, Migrationen oder Versionskombinationen als BLOCKED behandeln, bis zulässige Vorbedingungen bestehen. Kein verstecktes „temporär erlauben“ als Default. Abhängige Aufgaben entsprechend markieren.
4. **Alternativen prüfen:** Vorhandenen Beschluss ohne Änderung technisch korrekt erfüllen, einen zulässigen internen Adapter verwenden oder eine **ausdrücklich genehmigte** neue fachliche Entscheidung vorbereiten. Bei Widerspruch zu zwingenden Schutzgrenzen kein unsicheres Ersatzverhalten.
5. **Materielle Entscheidung nachhalten:** Produkt-/Architektur-/Rechte-/Erstspielfreigabe-/Regelneutralitätsänderungen werden nicht vom einzelnen umsetzenden Entwickler still entschieden. Bestehende Beschlüsse bleiben sichtbar; überholte Geltung, Gründe und neue Version werden ausdrücklich verlinkt. Für technische Detailentscheidungen innerhalb bindender Grenzen genügt die zuständige technische Vertragsprüfung.
6. **Betroffene Verträge prüfen:** Falls B.14-Owner-/Contract-/Consumergraph berührt, versionierte Kompatibilität, Source-/History-/Audience-/Schema-/RulePack- und 14.6-/15.2-Migrationsfolgen mit konkreten SafePoints/Verweigerungsbedingungen nachweisen; niemals blind dual schreiben oder World/Receipt rekonstruieren.
7. **Isoliert testen:** 14.8-konforme synthetische oder erlaubte redigierte Daten; tatsächlich ausgeführte MultiBrowser-/CurrentACL-/Revoke-/Duplicate-/LostAck-/Reconnect-/Restart-/R1-/R2-/Backupszenarien, soweit betroffen. Neue Builds und betroffene früher geprüfte Verbraucher erneut testen.
8. **Gezielt entsperren:** Erst nach erforderlicher Entscheidung, sicheren Änderungen und tatsächlichen Prüfungen Status VERIFIED für **diese** Konfliktlösung. Ein intern geprüfter Fix ist nicht automatisch B.2-B-Spielrelease, B.8-/B.9-Gesamtfreigabe oder 14.6-/15.4-StableRelease.
9. **Unabhängig weiterarbeiten:** Andere unverändert berechtigte, voneinander unabhängige B.13-/B.15-Entwicklungsbereiche behalten ihre eigenständigen Test- und Integrationspflichten und können voranschreiten.

## 4. Unveränderliche Schutzregeln bei einer Lösung

- **World und OriginalReceipt:** Keine pauschale Neuberechnung früherer Würfel-/Quest-/Item-/NPC-/Traktor-/Node-/Turnaktionen, keine neue WorldRevision durch Konfliktstatus und kein DuplicateCommit bei Reconnect. Korrekturen nur über bestehende fachliche 02.100-/14.12-Grenzen.
- **Authority:** Eine CampaignWorld und genau ein aktiver GM in V1; eine gültige WorldWriter-Autorität. Authentifizierte SteamIdentität, Host-/Support-/SecurityOperator und GM-/ActorControlGrant bleiben getrennt.
- **Privacy/Source/History:** Ein neues Contractfeld, Eventname, Diff, Debuglog, Testauszug oder View-Cache darf keine GM-/NPC-/Quest-/Player-/DM-Geheimnisse ausgeben; 14.4-Audit ist kein Freibrief zu ReadAll.
- **Pin-/Release-Schutz:** Bestandskampagnen, RulePack-/Extension-/Definitionpinstände und legitime Eventhistorie bleiben bestehen. Änderung, Aktivierung, Migration, Deployment und reale WorldAction bleiben getrennte aktuell berechtigte Fachoperationen.
- **B.2-B-Freigabeumfang:** Ziel bleibt die umfassende integrierte erste Spielversion mit Node-, Rule-, NPC-, Combat-/Initiative-, Inventory-, Quest- und weiteren schon zugesagten Kernmodulen, einschließlich B.8 zwölf Gesamtgates und B.9 zwei strukturell unterschiedlichen RulePacks.
- **Ausgeschlossene Funktionen:** Keine zweite Scripting-/World-/NPC-/CombatEngine, keine Cloud-/Clusterpflicht, kein 14.15-IncidentCase-Automatismus und entgegen 02.118 A keine persistenten ungesendeten ChatDrafts oder Reconnect-AutoSend.

## 5. Negative Prüfbeispiele

| Konfliktfall | Richtige Reaktion |
|---|---|
| Implementierung will aus Einfachheit jedem Player den GM-Snapshot liefern | Betroffenen Delivery-Slice blockieren; B.5-Viewer-/SourceACL bleibt zwingend |
| Zwei Fachmodule schreiben denselben Inventar-/Quest-/Traktoreffekt | B.4-Owner-/14.12-OriginalWorldWriter eindeutig halten, keine zweite Engine |
| Testkandidat kann WorldWriterFence bei Restart nicht garantieren | B.11-/B.10-Nachweis nicht bestanden; betroffene Stack-/Integrationswahl blockiert |
| R2-Regelpack benötigt andere Würfel- und Turnmechanik als R1 | Generischen Vertrag auf B.9-Konformität überprüfen, nicht heimlich W20/HP verpflichtend machen |
| Breaking ContractChange würde gepinnte Kampagnen still überschreiben | B.14-/15.2-/14.6-MigrationSafePoint und separate CurrentAuthorization verlangen |
| Testlauf unklar oder nur Mock-positiv | NOT_RUN/BLOCKED statt PASSED/VERIFIED und keine Releasebehauptung |
| Securityfix widerspricht einer alten Komfortfunktion | Konkreten Zugriff sperren; Entscheidung und B.14-/14.x-Kompatibilitäts-/Revoke-Verfahren dokumentieren, nicht global beliebige WorldActions verbieten |
| Betroffener Node-Slice ist blockiert, unabhängige Asset-Parser-Tests sind sicher | Node-Slice bleibt BLOCKED, unabhängige Arbeit darf geprüft fortfahren |
| Produktinhalt muss aus Lizenzgründen ersetzt werden | Source-/License-/Asset-Impact nach 12.x/15.x prüfen; kein unrechtmäßiger Export oder stilles neues geheimnisoffenes Mediaserve |
| Jemand erklärt ursprünglichen Plan pauschal für „überholt“ | Ohne konkrete neue zuständige Entscheidung keine Änderung des verbindlichen Beschlussstandes |

## 6. Nächster Entwicklungsschritt und Abgrenzung

B.16 C gibt **keine Erlaubnis zum Überspringen** der B.10-ADRs, des tatsächlich auszuführenden B.11-P1/P2/P3-Spikes, der B.12-Produktionshärtung und der B.13-/B.14-/B.15-Vertrags- und Abnahmepflichten. Welche technischen Review-Tools, Ticketnummern, Felder, Zuständigkeiten und Freigabeautomaten eingesetzt werden, wird erst im jeweils tatsächlich anstehenden Entwicklungsschritt entschieden. Es wurde durch diese Planungsentscheidung **nichts** implementiert, live geändert, migriert, wiederhergestellt oder freigegeben.

## 7. Historische Anschlussfrage B.17 (inzwischen C beschlossen)

### B.17 – Welche Mindestvoraussetzungen gelten für den Übergang von der Architekturplanung zur ersten echten B.11-Technikprobe?

- **A – Sofort mit einem schnellen Prototyp anfangen, fehlende Voraussetzungen später ergänzen:** Früh sichtbarer Code, aber riskante Auth-/World-/Testisolation-/OriginalReceipt-Regeln werden möglicherweise durch provisorische Abkürzungen verdrängt.
- **B – Erst jedes Fachmodul und sämtliche UI-/Regeldetails endgültig ausarbeiten:** Wenig zu Beginn offene Parameter, aber große Vorabplanung, bevor die kritischen Architekturannahmen tatsächlich überprüft sind.
- **C – Begrenzter Architektur-/Sicherheits-Readiness-Check für die erste isolierte Probe (Empfehlung):** Beschluss-/Dependency-/Scope-Check B.10–B.16, 14.8-synthetische Umgebung, eine echte WorldWriter-/Receipt-/CurrentACL-/Viewer-/Reconnect-/Revoke-Testliste, klar begrenzte Kandidaten, Testdaten/Secrets/NoProd-Grenzen, dokumentierte Pass-/Fail-/NotRun-Kriterien und technisch reproduzierbare Nachweise **vor dem Start** festlegen. Die Probe selbst bleibt die erste tatsächliche Implementation und darf den späteren B.2-B-Release oder die endgültige Stackwahl nicht vortäuschen. Keine vollständige Vorabplanung aller UI- und RulePackdetails.
