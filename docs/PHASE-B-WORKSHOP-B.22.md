# AdventureShift – Phase B, Beschluss B.22 C: geschützter Git-Hauptzweig mit nachweisbaren Integrationsgates

**Stand:** 04.11.2026. **B.22 C vom Projektinhaber ausdrücklich beschlossen.**
**Status:** Verbindlicher Architektur- und Prozessvertrag für die spätere Implementierung; **noch keine GitHub-Branchschutz-/Ruleset-Konfiguration aktiviert, keine CI-Pipeline eingerichtet, kein B.11-Spike implementiert oder ausgeführt und keine produktive Spielsoftware freigegeben.** Dieser Dokumentationscommit bleibt eine Planungsänderung.
**Entscheidung C:** Der spätere offizielle Integrationszweig `main` wird gegen unkontrollierte Codeänderungen **mit technisch wirksamen Branchschutz-/Merge-Gates**, zum betroffenen Entwicklungsauftrag passenden automatischen Checks sowie einer nachvollziehbaren zuständigen Fach-/Sicherheits-/Architekturprüfung geschützt. **Fehlende, fehlerhafte, nicht ausgeführte oder umgangene Pflichtgates zählen nicht als PASS.** Getrennte Experimente nach B.21 bleiben möglich; aus ihnen wird nur nach B.12-Härtung, B.14-Contract-/Consumerprüfung und B.15-beschlussgebundenem Acceptance-Nachweis selektiv übernommen. Ein erfolgreiches internes Merge ist niemals automatische Produktivfreigabe nach B.2/B.8/B.9/14.6/15.4.
**V1-Grenzen:** Auf einem eigenen VPS vollständig betreibbare GM-/Player-Browser, **genau ein aktiver Spielleiter je Kampagne**, eine kanonische CampaignWorld und eine fachlich autorisierte WorldWriter-Generation; keine ShadowEngine, kein technischer Reviewer mit allgemeinem GM-/Actor-/Source-/History-/Privacy-/Host-/Support-Zugriff.
**Bezüge:** [Planungsstandard](PLANUNGSSTANDARD.md) · [B.1](PHASE-B-WORKSHOP-B.1.md) · [B.2](PHASE-B-WORKSHOP-B.2.md) · [B.3](PHASE-B-WORKSHOP-B.3.md) · [B.4](PHASE-B-WORKSHOP-B.4.md) · [B.5](PHASE-B-WORKSHOP-B.5.md) · [B.8](PHASE-B-WORKSHOP-B.8.md) · [B.9](PHASE-B-WORKSHOP-B.9.md) · [B.10](PHASE-B-WORKSHOP-B.10.md) · [B.11](PHASE-B-WORKSHOP-B.11.md) · [B.12](PHASE-B-WORKSHOP-B.12.md) · [B.13](PHASE-B-WORKSHOP-B.13.md) · [B.14](PHASE-B-WORKSHOP-B.14.md) · [B.15](PHASE-B-WORKSHOP-B.15.md) · [B.16](PHASE-B-WORKSHOP-B.16.md) · [B.17](PHASE-B-WORKSHOP-B.17.md) · [B.18](PHASE-B-WORKSHOP-B.18.md) · [B.19](PHASE-B-WORKSHOP-B.19.md) · [B.20](PHASE-B-WORKSHOP-B.20.md) · [B.21](PHASE-B-WORKSHOP-B.21.md) · [14.1](SICHERHEIT-WORKSHOP-14.1.md) · [14.6](SICHERHEIT-WORKSHOP-14.6.md) · [14.8](SICHERHEIT-WORKSHOP-14.8.md) · [14.9](SICHERHEIT-WORKSHOP-14.9.md) · [14.12](SICHERHEIT-WORKSHOP-14.12.md) · [14.13](SICHERHEIT-WORKSHOP-14.13.md) · [15.4](ERWEITERUNGEN-WORKSHOP-15.4.md).

## 1. Grundlegende Schutz- und Integrationsregeln

1. **Geschütztes `main` für Implementierung:** Produktrelevante Code-/Schema-/Security-/Buildänderungen erfolgen über nachvollziehbare Review-Änderungen mit erforderlichen Statusprüfungen statt unbemerkten Direktwrites. Geeignete technische Einstellungen und Berechtigungen werden **beim tatsächlichen Implementierungsbeginn** nachgewiesen; sie werden durch diesen Beschluss nicht automatisch aktiviert.
2. **Review an der Änderung:** Verlinkter B.15-DevelopmentWorkItem, relevante gewählte Fachentscheidungen, B.4-Owner, B.14-ContractRevision, B.16-offene Blocker, B.20-Source-/Dependency-/Buildstand, Risiken und Positiv-/Negativ-Ergebnisse. Kein Review-„Approved“ ohne einschlägige Beleglage.
3. **Kontrollierter Prüfumfang:** Kleine reine Dokumentationsänderung braucht keinen funktionslosen Spiel-E2E-Run; Domain-/World-/Security-/Schema-/Auth-/Source-/Privacy-/Rule-/Media-/Migrationänderungen brauchen **betroffene** Contract-/Unit-/Integration-/Mehrbrowser-/Recovery- und ggf. B.9-R1-/R2-Regression. Keine pauschale Pflicht, vor jeder Codeintegration die komplette B.2-B-Spielfreigabe erneut auszuführen.
4. **Pflichtgates technisch durchsetzen:** Tatsächlich ausgeführte Build-/Linter-/Test-/Dependency-/Lizenz-/Secret-/Security-/Schema-/Compatibility-/Contractprüfungen und B.13-Regressionsfälle gemäß Impact-Matrix. Für kritische geänderte Rechte, Daten und WorldEffects gehören berechtigte und unberechtigte, positive und negative Testfälle dazu.
5. **Keine Selbstbefreiung durch Prüfcode:** Änderungen an CI-/Ruleset-/Workflow-/GitHooks-/Auth-/Secret-/Environment-/WorldWriter-/SecurityTest-Dateien sind **schutzrelevant**. Geänderter Prüfcode darf eigene Schutzauflagen nicht ohne gesonderte autorisierte, versionierte Review-/Regressionsevidenz abschalten. Unvertrauenswürdige Pull-Request-Ausführung erhält keine produktiven Secrets oder Schreib-/Deploymentrechte.
6. **Nachweis an exakter Revision:** Gateergebnisse gelten nur für den geprüften Commit-/Build-/Dependency-/Schema-/Contract-/Fixture-/Environmentstand. Geänderte Commits oder Merge-Basis, sicherheitsrelevante Configänderungen und neu eingeführte Abhängigkeiten erfordern die jeweils passenden Rechecks.
7. **Klare Ergebniszustände:** `PASS` nur nach echtem erfolgreichen Test. `FAIL`, `BLOCKED`, `NOT_RUN`, abgebrochene oder uneindeutige Sicherheits-/World-/Privacy-Prüfungen dürfen nicht als erfolgreich integriert gelten. Nicht betroffene Tests werden nachvollziehbar `NOT_APPLICABLE` dokumentiert, nicht fälschlich `PASS`.
8. **Keine Releasewirkung durch Merge:** `main`, Review, CI-Erfolg, Commit/Tag oder Staging-Deployment erzeugen keine WorldAction, keine GM-/Actor-/Source-/HistoryGrant, keine RulePack-/Pluginaktivierung und keinen B.2-/14.6-/15.4-StableRelease. Freigabeumfang und zwölf B.8-/B.9-Gates bleiben eigenständig.

## 2. Typisierte Entwicklungs- und Integrationsnachweise (Arbeitsnamen)

| Arbeitsobjekt | Verantwortliche Wirkung |
|---|---|
| **ProtectedBranchPolicy / RulesetRevision** | Versionierte beabsichtigte `main`-Schutzregeln, erforderliche Checkgruppen und technische Wirksamkeitskontrolle, noch nicht aktiviert |
| **ChangeScope / WorkItemBinding** | B.15-Auftrag, betroffene Fachdomänen, B.4-Owner, B.14-Revision und B.16-Konflikte sowie ausdrücklich nicht berührte Pfade |
| **RequiredGateMatrix / CheckEvidence** | Für den Change erforderliche automatische und reale Positiv-/Negativtests mit `PASS/FAIL/BLOCKED/NOT_RUN/NOT_APPLICABLE` am exakten Stand |
| **SecureReviewDecision** | Sachlich zuständige technische/fachliche/Privacy-/Security-Beurteilung, keine neue laufende Spielrolle und kein World-/Host-/Supportrecht |
| **BuildProvenance / ArtifactDigest** | B.20-Version und überprüfbarer Änderungs-/Artefakt-/Dependency-/Schema-/Fixturebezug, keine Aussage durch Namen allein |
| **SpikePromotionTrace / HardeningEvidence** | B.21-Experimentprovenienz, B.12-Reviews, selektive gehärtete Komponenten und erneute B.13-/B.14-/B.15-Regressionsnachweise |
| **MergeEligibility / IntegrationReceipt** | Nur technisches Integrationsresultat: zulässig, blockiert oder nachzubessern; kein `OriginalOperationReceipt` und keine produktive Freigabe |
| **ExceptionAndRecoveryRecord** | Eng begrenzte technische Notfall-/Repository-Wiederherstellung nur mit berechtigter, protokollierter Entscheidung und Nachprüfung; kein stiller Dauerbypass |

Die Arbeitsbegriffe sind Nachweise der **Softwareentwicklung**, keine neue Engine für WorldCommit, SecurityIncident, UserIdentity, Release, Quest oder Kampagnenrechte. Konkrete GitHub-/CI-/Branchschutzfunktionen, Rollen und Toolprodukte folgen bei realer Einrichtung.

## 3. Integrationsablauf und Qualitätsmatrix

1. **Änderungsauftrag und Scope:** Beschlüsse/Quellen nach B.15 referenzieren; B.16-Blocker und B.14-Contractänderungen vorher klären. Ein B.11-Experiment bleibt nach B.21 getrennt, bis B.12-Sicherheits-/Lizenz-/Auth-/Owner-/Recovery-Härtung tatsächlich geprüft wurde.
2. **Früh und eng testen:** Syntax/Lint, Build-/Dependencylock-/Lizenz-/Secret-Checks für passende Dateien; bei API-/Schema-/Rule-/Auth-/World-/Source-/Vieweränderungen Contract-/Migrations-/Privacy-/Negative-/E2E-Tests zu allen wirklich betroffenen Verbrauchern.
3. **Echte World-/Session-Sicherheit:** Positiv/Negativ für GmAuthorityEpoch, ActorControl, CampaignMembership, DomainOwner, CurrentACL, Source-/HistoricalAudience, Fog, MediaServe, SingleWorldWriter/WriterFence, atomaren 14.12-Commit/OriginalOperationReceipt, Duplicate/LostAck/Revoke/Restart/Outbox. Nur in isolierten 14.8-Testscopes.
4. **Review und technische Schutzregel:** Zuständiger Review bestätigt die wirklich gelaufenen Gates, die offenen Risiken und das Fehlen unautorisierter TestOnly-/FakeAuth-/ReadAll-/ProductionSecret-Pfade. Dies darf auch in einem kleinen Team nachvollziehbar organisiert werden, ohne automatisch eine zweite aktive V1-Spielleitung oder ein vorgeschriebenes Entwicklerteam einzuführen.
5. **Gesonderte Schutzänderung:** Änderung an der Prüfinfrastruktur, Secret-/Deploymentrechte, Branchrules, Testauswahl oder Skip-Logik benötigt einen unabhängigen fachlich berechtigten Änderungsnachweis (im Sinne einer separaten sachlichen Prüfung, **nicht** eine erfundene neue Produktionsrolle). Keine automatische `admin`-Umgehung durch testenden Code.
6. **Integration ausschließlich des geprüften Stands:** Erst wenn alle Pflichtgates der konkreten Änderung technisch bestanden und die erforderlichen sachlichen Entscheidungen dokumentiert sind. Konflikt, FAIL, BLOCKED, NOT_RUN oder nachträgliche kritische Codeänderung verhindern den unkontrollierten Merge.
7. **Nach Integration Regression:** Betroffene gemeinsame B.13-Verbraucher und B.14-Versionen auf der Integrationsbasis nachprüfen. Fehlender Nachweis blockiert weitere abhängige Arbeiten; bereits existierende Kampagnenzustände und Release-Pins bleiben unverändert.
8. **Freigabe strikt eigenständig:** B.2-B-Fachbreite, B.8 modulübergreifende echte GM-/Player-/VPS-Gates, B.9 R1-/R2-RuleNeutralität und 14.6-/15.4-Produktionsfreigabe werden **nicht** aus einem grünen internen Merge abgeleitet.

## 4. Negative Sonderfälle und Grenzen

| Konstellation | Korrektes Ergebnis |
|---|---|
| CI ist nicht vorhanden, obwohl Branchschutz schon „geplant“ ist | Technischer Schutz **nicht aktiv/nicht bewiesen**; Planungsdokument kein Schutzbeleg |
| CI meldet Erfolg nach ausschließlich gemocktem WorldReceipt | Echte World-/Receipt-/Browser-Anforderungen `NOT_RUN`; kritische Integration nicht freigeben |
| Entwickler entfernt Tests im selben Patch, um zu bestehen | Eigenständiges Schutzänderungsreview, keine automatische Übernahme eines grün gewordenen Fehlchecks |
| Testworkflow läuft mit Produktivdeployment-Token aus nicht vertrauenswürdigem PR | Security-Gate BLOCKED und Zugriffsgrenzen korrigieren, keine Secrets in Logs/PR-Forks |
| Code enthält GM-/NPC-/Quest-/PrivateDM-ReadAll-Abkürzung | Sicherheits-FAIL, auch wenn UnitTests erfolgreich sind |
| Änderung an Commit-/Receipt-/WriterFence mit veralteter B.11-Evidenz | B.12-/B.13-/B.14-Risiko- und Negativtests am neuen gehärteten Build wiederholen |
| Zwei Module beanspruchen denselben WorldEffect | Owner-/14.12-/14.13-Gate BLOCKED, kein Schattenwriter |
| Git-Hauptbranch hat neuen Commit nach Prüfungsabschluss | Prüfrelevante Baselineänderung bewerten, bei Impact aktuelle Merge-Revision erneut prüfen |
| Kritischer Notfall verlangt kurzfristige Repositoryreparatur | Zeitlich/inhaltlich begrenzte autorisierte Ausnahme mit redigiertem Nachweis, Nachtests und Sicherheitsreview, niemals verdeckter Dauer-Bypass |
| PR mit nur redaktioneller Dokumentationsänderung | Schlanke dokumentationsgerechte Checks statt fingierter vollständiger Spieltests |
| Geprüfter Einzel-Slice wird nach Merge als fertiges Spiel beworben | Verweigern, B.2-B-/B.8-/B.9-/14.6-/15.4-Releasegates weiterhin offen |
| Branchschutzkonfiguration ist noch nicht real geprüft | Keine Behauptung, `main` sei bereits gegen direkte Pushs oder Administrator-Bypass abgesichert |

## 5. Abschlussstatus und nächste grundlegende Entscheidung B.23

**B.22 C ist beschlossen und dokumentiert; eine Branchschutzkonfiguration, CI-/Checkpipeline oder tatsächliche Reviewautomatisierung wurde nicht eingerichtet.** B.17-Preflight, B.18-Techkandidatenprüfung und B.11-/B.19-Testimplementierung bleiben `NOT_RUN`, B.12 nicht gehärtet, B.13–B.15 nur geplant. `main` wird durch diesen reinen Planungscommit nicht technisch geschützt. **Keine neue produktive Wirkung**, kein erneutes Roll-/Quest-/Item-/NPC-/Traktorereignis durch Merge oder Teststatus.

### B.23 – Wann schließen wir die Grundsatzplanungsphase ab und beginnen die tatsächliche technische Umsetzung?

- **A – Weitere detaillierte Grundsatzfragen zu allen Modulen vor jedem Code:** Mehr Vorabunterlagen, aber widerspricht B.1/B.13/B.15 und verzögert die echte B.11-Risikoprobe ohne entsprechenden Architekturgewinn.
- **B – Sofort irgendeinen Prototyp bauen, ohne B.17-/14.8-/B.21-/B.22-Eintrittsbedingungen zu prüfen:** Schneller Code, aber Gefahr ungeschützter Testumgebungen, unklarer Auth-/World-/Receipt-/Git-Grenzen und unbrauchbarer Nachweise.
- **C – Phase B mit Beschlussabgleich abschließen und in die konkrete, isolierte Implementierungsvorbereitung übergehen (Empfehlung):** Bestehende verbindliche Architekturentscheidungen samt B.16-Blockern konsolidieren, nur tatsächlich kritische Widersprüche vorab klären; danach **B.18-Technikkandidaten konkret prüfen, B.17-/14.8-Readiness tatsächlich durchführen, B.21-/B.22-Git-/Testschutz wirksam einrichten und B.11-P1/P2/P3-Probe nach B.19/B.20 wirklich bauen und testen**. Detailfragen zu späteren UI-/Regeln/Nodes nur bei den jeweiligen B.15-Entwicklungsaufträgen. Kein „bereit“ ohne echte Nachweise und keine vorzeitige B.2-B-Freigabe.
