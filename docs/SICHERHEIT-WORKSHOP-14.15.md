# AdventureShift – Sicherheit-/Hosting-Workshop: Beschluss 14.15 A – manuelle Sicherheitsvorfallbehandlung

**Stand:** 27.10.2026. **14.15 A verbindlich beschlossen**; dreimal identisch gesendete Auswahl wird nur einmal übernommen.
**Status:** Fachliche Grundstruktur für manuelles Vorgehen und Wiederverwendung der bereits beschlossenen Sicherheitsfunktionen. **Keine Softwareimplementierung.**
**V1:** Ein aktiver Spielleiter, eine kanonische CampaignWorld je Kampagne, vollständiger Betrieb auf einem eigenen VPS.
**Später:** Betreiber-Runbooks, Notfallfristen, tatsächliche Alarmschwellen, Meldungen, manuelle Verfahren, CLI/UI/API/DB und konkrete technische Details.
**Planungsfolge:** **Block 14 abgeschlossen; nächste Grundfrage 15.1 – Erweiterbarkeit und optionale Plugins.**

**Bezüge:** [14.1 Account- und Steamidentität](SICHERHEIT-WORKSHOP-14.1.md) · [14.2 Sessions/SecurityHold](SICHERHEIT-WORKSHOP-14.2.md) · [14.3 AccountRecovery](SICHERHEIT-WORKSHOP-14.3.md) · [14.4 SecurityAudit](SICHERHEIT-WORKSHOP-14.4.md) · [14.5 Key-/SecretLifecycle](SICHERHEIT-WORKSHOP-14.5.md) · [14.6 Deployment/Restore](SICHERHEIT-WORKSHOP-14.6.md) · [14.7 Service-/JobRecovery](SICHERHEIT-WORKSHOP-14.7.md) · [14.8 Test-/Prod-Isolation](SICHERHEIT-WORKSHOP-14.8.md) · [14.9 Rate-/WS-/Uploadschutz](SICHERHEIT-WORKSHOP-14.9.md) · [14.10 einmaliger Bootstrap](SICHERHEIT-WORKSHOP-14.10.md) · [14.11 HostConfig](SICHERHEIT-WORKSHOP-14.11.md) · [14.12 DomainStores/WorldTransaction](SICHERHEIT-WORKSHOP-14.12.md) · [14.13 SingleVPS/WorldWriter](SICHERHEIT-WORKSHOP-14.13.md) · [14.14 geschützter Support](SICHERHEIT-WORKSHOP-14.14.md) · [09.6 echte Backups](KAMPAGNEN-WORKSHOP-09.6.md) · [09.7 eine GM-Epoch](KAMPAGNEN-WORKSHOP-09.7.md) · [09.8 Privacy/Erasure](KAMPAGNEN-WORKSHOP-09.8.md) · [09.9 eine World](KAMPAGNEN-WORKSHOP-09.9.md) · [02.99 WorldActions](KARTEN-WORKSHOP-02.99.md) · [02.107 private DMs](KARTEN-WORKSHOP-02.107.md) · [03.2 ActorControl](CHARAKTER-WORKSHOP-03.2.md) · [05.1 Würfelbelege](WUERFEL-WORKSHOP-05.1.md) · [12.3 AssetRevocation](ASSETS-WORKSHOP-12.3.md) · [12.7 Quotas](ASSETS-WORKSHOP-12.7.md) · [13.3 OriginalActionReceipts](UI-WORKSHOP-13.3.md) · [13.12 WorkspaceReconnect](UI-WORKSHOP-13.12.md) · [Sabotage und Traktor](FEATURE-VORMERKUNG-SABOTAGE-TRAKTOR.md).

## 1. Verbindliche Wahl – ausdrücklich A, nicht C

**Sicherheitsvorfälle werden durch tatsächlich berechtigte VPS-Betreiber manuell einzeln untersucht.** Es wird **keine eigenständige automatische SecurityIncident-/Severity-/ContainmentIntent-/Evidence-/IncidentApproval-/SafeReopen-/Notification-Domäne** als verbindliche Grundstruktur angelegt.

Ein Verdacht, ein Prüfhinweis, ein manuell ausgelöster Sicherheitsvorgang und dessen tatsächlich wirksames Ergebnis sind unterschiedliche Sachverhalte. Der Betreiber nutzt hierzu die bereits getrennt **versionierten** Schutzfunktionen aus 14.1–14.14. Die im Nutzerauftrag genannten getrennten Rechte und Revisionsprüfungen bleiben erhalten, aber sie begründen **keinen** versteckten Incident-Orchestrator.

**Maßnahmen werden nur über die bestehende zuständige Fachdomäne wirksam:** eine legitime Session-Sperre über 14.2, verifizierte OwnerRecovery über 14.3, redigierte tatsächliche Sicherheitsbelege über 14.4, KeyRotation über 14.5, MediaRevocation über 12.3, Servicequiesce über 14.7, Requestschutz über 14.9, zulässige HostConfig-Änderungen über 14.11 und eigene Backups/Restores über 09.6. Die bestehenden Owner-/SecurityOperator-/Source-/GM-/Actor-/Privacy-/ExpectedRevision-/OriginalOperationReceipt-Grenzen bleiben unverändert.

**Nicht gewählt:** B – pauschale globale Notfallsperre; C – gesonderter automatisierter Incident-/Containment-/Recovery-/Reopen-Workflow. A schafft auch keinen pauschalen Host-/GM-/Support-/Player-Impersonation-Zugang und keine eigenständige World-/Roll-/Quest-/Traktoraktion.

## 2. Zu berücksichtigende bestehende Fachgrenzen

1. **ManualObservation:** Meldung oder Verdacht ist weder bewiesener Angriff noch tatsächlicher SecurityCommit.
2. **SecurityAudit 14.4:** Autorisierte redigierte Audit-/Causation-/ActualOutcome-Information statt universellem Rohlog.
3. **IndependentSecurityOperator:** Host-/Security-/Account-/Key-/DataOwner und die aktive SL besitzen jeweils unterschiedliche Rechte.
4. **SessionRevoke 14.2:** Einzelne/alle eigene bzw. ausdrücklich berechtigte andere BrowserSessions nur über echten Revoke-/SecurityEpoch-Commit.
5. **AccountRecovery 14.3:** Steam-/UserAccount-Verknüpfung niemals allein wegen manuell gemeldeter Gefahr übernehmen.
6. **KeyUse/Rotation 14.5:** Keine RawKeys im Supportlog; erforderliche Rotate-/Revoke-/BackupCompatibility bleibt eigener Commit.
7. **MediaServeFence 12.3:** Bereits widerrufene GM-/NPC-/Quest-/Fog-/Handout-/Assetvarianten nicht erneut ausliefern.
8. **ServiceReadiness 14.7:** Technischer Worker-/DB-/WS-/Key-/Backupstatus getrennt von bestätigter Kompromittierung.
9. **RequestAdmission 14.9:** PreAuth-/Rate-/Abuse-/Origin-/Quota-Sicherheit auch ohne eigene IncidentEngine.
10. **HostConfig 14.11:** Wirklich berechtigte Konfigurationsänderung mit eigenem Preflight, ActiveRevision und RollbackEligibility.
11. **Deploy/Restore 14.6/09.6:** Recovery nur bei gültigem Archive-/Owner-/Key-/World-/Asset-/Privacy-/Compatibility-Check.
12. **Test/ProdIsolation 14.8:** Vorfalltests möglichst synthetisch; kein allgemeines Kopieren echter privater Daten und Secrets.
13. **Support 14.14:** Purpose-/Consent-/ReadOnly-Einsicht ersetzt keine Account-/Key-/GM-/WorldOperationCapability.
14. **Owner-/Actor-/HistoricalAudience 03.2/09.4:** Kein fremdes CharacterControl, keine gruppenfremden DMs/Quests/GMSecrets.
15. **SingleGM 09.7:** Kein zweiter aktiver Spielleiter und keine Reaktivierung alter GM-Epochs.
16. **SingleWorld 09.9/14.12:** Kein zweiter WorldRoot, keine ungesicherte Bearbeitung von Game-/Npc-/Item-/Quest-/Traktorzuständen.
17. **OriginalOperationReceipt 13.3:** Vor einer Wiederholung nach Timeout den wirklich einmalig ausgeführten World-/Roll-/Quest-/Tür-/TraktorCommit prüfen.
18. **Privacy/Retention/Erasure 09.8:** Verdachtsdokumentation ist keine unbefristete Erlaubnis zur Aufbewahrung privater Rohdaten.
19. **Source-/SecretRedaction:** Keine SteamGuard-/Session-/Recovery-/DB-/Signing-/BackupKeys, unbekannten NPC-/Quest-/GM-/Spielerinhalte in allgemeine Diagnosen kopieren.
20. **ManualScopeSelection:** Nur tatsächlich notwendige, eigens berechtigte vorhandene Sperre/Wartung; keine aus A abgeleitete globale automatische AllUsersSperre.
21. **ActualOutcome:** Ein Logeintrag „gesperrt“ beweist keinen tatsächlich erfolgten DomainRevoke.
22. **SafeNewAccess:** Vor neuen WebSocket-/Media-/Account-/World-Reads und Commits heutige Security-/GM-/Key-/Owner-/Source-/Privacy-/Service-Revisionsrechte prüfen.
23. **NoIncidentAggregate:** Keine neue IncidentCase-/Severity-/Containment-/Evidence-/Notification-/Reopen-Datenbank oder unabhängige Berechtigungsengine.
24. **ManualRunbookLater:** Menschliche Ablauftexte, Beweissicherung, Fristen, Warnschwellen und Supportkontakte später festlegen.
25. **V1:** Eigenbetrieb auf einem VPS, genau ein aktiver SL, eine kanonische World je Kampagne.

## 3. Konzeptioneller Umsetzungsplan

1. **Keine neue Incident-Engine** implementieren; bestehende getrennte Sicherheits- und Privacy-Domänen in der Architektur wiederverwenden.
2. Redigierte, berechtigte bestehende 14.4-/14.7-/14.14-Diagnosebelege nach ihrer heutigen Source-/Purpose-/Owner-ACL lesen.
3. Tatsächlich notwendige 14.2-/14.3-/14.5-/12.3-/14.6-/14.9-/14.11-/09.6-Maßnahmen nur als eigene rechtmäßig autorisierte Fachoperationen durchführen.
4. Originalbelege und tatsächliche wirksame Zustände kontrollieren; Pending/Unknown nicht als erfolgreich ausgeben.
5. Bei weiterer Nutzung aktuelle BrowserSession-/GM-/Actor-/Asset-/Key-/Media-/Privacy-/Service-Grants vor neuen Ausgaben revalidieren.
6. Manuelle Betreiberanleitung sowie konkrete UI-/CLI-/Protokoll-/Fristen-/MFA-/Alarmdetails später spezifizieren.

## 4. Grundstruktur-Abnahmetests

| Szenario | Erwartetes Verhalten |
|---|---|
| Verdächtiger Login wird gemeldet | Manuelle berechtigte Prüfung, kein automatischer Fremdkontozugriff |
| Ein AccountOwner widerruft eigenes verlorenes Gerät | Tatsächlicher 14.2-RevokeReceipt, kein Incident-Flag als Ersatz |
| GM möchte fremdes Spielergerät sperren | Ohne eigene SecurityAuthority kein fremdes Accountrecht |
| Steam-/AccountLink soll aus Notfall geändert werden | 14.3-OriginalOwner-/Proof-/Approval-Prüfung zwingend |
| SigningKey ist möglicherweise gestohlen | 14.5-Key-/Backup-/Session-/Operatorrechte prüfen; kein RawSecret in Logs |
| KeyRotation wurde abgelehnt oder ist pending | Kein vorgetäuschter KeyRevoke-/Ready-Erfolg |
| Versehentlich geheime Karte ausgeliefert | 12.3-Media-/14.2-SessionFences verhindern neue unzulässige Downloads |
| Spieler hatte Bild zuvor rechtmäßig gespeichert | Kein falsches Versprechen der Rücknahme externer Kopien |
| MediaWorker ist ausgefallen | 14.7-Service-/Jobstatus statt unbelegter IncidentSeverity |
| Login-/WS-Anfragen werden geflutet | 14.9-PreAuth-/Rate-/Quota-Grenzen ohne neue globale BanEngine |
| Betreiber verlangt globale Alle-Sperrung | A erteilt keine pauschale Sperrerlaubnis ohne bestehende jeweilige Berechtigung |
| Frühere SL öffnet alten Browser | Heutige 09.7-GMEpoch und 14.2-Sessionrechte bleiben maßgeblich |
| Supporter liest Quota-/Workerstatus | Keine fremden PlayerDM-/GM-/NPC-/Quest-/Key-ReadAll-Rechte |
| Spieler wechselt geheime Gruppe | Alte History-/Fog-/Quest-/Chat-Grants gelten nicht automatisch neu |
| Verdacht wird in Testumgebung reproduziert | 14.8-Isolation, kein produktiver World-/Roll-/Quest-/TraktorEffect |
| Backup enthält alte Sessioncookies | Kein Reaktivieren der Account-/GM-/Assetrechte nach Restore |
| Personendaten wurden rechtmäßig gelöscht | 09.8-Retention-/Erasuregrenzen bleiben auch bei Incidentnotiz wirksam |
| Echter HostConfig-Fehler wird korrigiert | 14.11-eigener Activation-/Audit-/OriginalReceipt-Prozess |
| WorldAction wurde vor Timeout tatsächlich committed | Nur OriginalReceipt, keine zweite Tür-/Npc-/Quest-/Item-Aktion |
| Würfel wurde bereits autoritativ erzeugt | Kein zweiter 05-RollRecord nach Support-/ServerRetry |
| Traktor wurde bereits bewegt | Kein erneutes Fahren, Reparieren oder Sabotieren durch Incidentstatus |
| Kein Beleg einer tatsächlichen AccountSperre liegt vor | Manuelle Notiz wird nicht als gültiger Revoke ausgegeben |
| Betreiber möchte Dienst wieder freigeben | Nur die heutigen 14.2-/14.5-/14.7-/Owner-/Privacy-/Source-Rechte |
| V1 hat genau einen GM und eine World | Sicherheitsoperator erhält keine weitere GM-/WorldAuthority |
| Technische Notfallfristen noch offen | Manuelle Variante bleibt ohne neue IncidentEngine und mit bestehenden Schutzrechten umsetzbar |

## 5. Beschlussgrenze und nächste Grundfrage

**14.15 A abgeschlossen:** Manuelle Einzelfallreaktion mit bereits getrennten, versionierten und berechtigten Sicherheitsfunktionen. **Keine zusätzliche Incident-/Containment-/Reopen-Engine, keine pauschale globale Notfallsperre und keine neue World-/GM-/Account-Impersonation.** Block 14 Speichern, Sicherheit & Hosting grundstrukturell abgeschlossen.

### 15.1 – Wie sollen eigene Erweiterungen und Plugins eingebunden werden?

**Beispiel:** Ein SL möchte neue RulePack-Vorlagen, besondere NPC-/Node-Bausteine oder später optionale Zusatzmodule nutzen.

- **A – Nur Hauptsoftwareupdates:** Neue Funktionen durch Softwareupdates; bestehende RulePack-/Node-/Templatekonfiguration bleibt, aber kein eigener Pluginvertrag.
- **B – Frei ausführbare Skripte/Plugins:** Erweiterungen mit weitreichendem Server-/DB-/Gamezugriff ohne verbindliche Sandbox-/Source-/World-/Privacy-Grenzen.
- **C – Optionaler sicherer Erweiterungsvertrag (Empfehlung):** Versionierte ExtensionManifest-/Kind-/InstallAuthority-/AllowedCapability-/Sandbox-/Source-/Owner-/CampaignScope-/Quota-/Actor-/GM-/DataAccess-/ActionProposal-/WorldCommit-/License-/Update-/Revoke-Grenzen. Importierter Code besitzt keine freie Root-/Key-/DB-/GM-/WorldWriter-Fähigkeit. **V1 braucht keinen Pluginmarktplatz und keine freie ScriptingEngine**; konkrete APIs, Programmiersprachen, Sandbox und UI später.
