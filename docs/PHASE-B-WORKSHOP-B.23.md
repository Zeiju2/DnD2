# AdventureShift – Phase B, Beschluss B.23 C: Abschluss der Grundsatzplanung und kontrollierter Übergang in die echte Technikvorbereitung

**Stand:** 04.11.2026. **Entscheidung:** Der Projektinhaber hat **B.23 – Variante C** ausdrücklich gewählt.
**Geltung:** Dieser Beschluss **schließt die grundsätzliche Phase-B-Entscheidungsrunde B.1–B.23 ab** und gibt den Übergang zu beschlussgebundener, überprüfbarer technischer Vorbereitung frei. Er **gibt weder eine konkrete Technologie noch einen Implementierungs-, Staging- oder Produktivstand frei**.
**Tatsächlicher Status bei Beschluss:** B.18-Kandidatenrecherche noch nicht durchgeführt; B.17-/14.8-Readiness noch nicht bestanden; B.21-Experimentzweig, B.22-Branchschutz-/CI-Regeln und B.20-Build noch nicht tatsächlich eingerichtet; B.11-P1/P2/P3-Spike nicht implementiert oder ausgeführt; B.12-Härtung, B.13-Fachintegration und B.2-/B.8-/B.9-/14.6-/15.4-Releaseprüfungen nicht erledigt. **Ein Planungscommit ist kein technischer Testbeleg.**

## 1. Beschlussumfang und Vorrang bestehender Entscheidungen

1. **Keine weitere Vollausplanung aller Module vor dem ersten Code.** Die Grundsatzdokumentation B.1–B.22 und die Fachworkshops sind verbindliche Ausgangsbasis. Präzise Feldwerte, UI-Verhalten, Inventargrößen, RulePack-Formeln, Layouts, Audio- und andere Moduldetails werden **erst bei ihrem konkreten B.15-Entwicklungsauftrag** fachlich entschieden und versioniert; relevante bereits beschlossene Regelungen bleiben unangetastet.
2. **Gezielter Abgleich vor Implementierung:** B.16 prüft am betroffenen Arbeitspaket und an den betroffenen Fachvertragsgrenzen auf echte Widersprüche, fehlende Owner, technische Widerlegungen und kritische Security-/Privacy-/World-Lücken. Nur tatsächlich betroffene Arbeit blockieren; keine unbelegte Behauptung einer vollständigen, bereits abgeschlossenen projektweiten Konfliktprüfung. Materielle Fachentscheidungen sind explizit neu zu beschließen und nach B.14 auf Consumer, Migration, Quellen, Rechte, Audit und Regression zu prüfen.
3. **Inkrementeller Weg gemäß B.1/B.13/B.15:** Zuerst ein prüfbarer technischer Kern, dann nach B.12-Härtung nur geeignete Teile gezielt integrieren, anschließend die breite Fachintegration für die erste **B.2 B**-Spielversion. Ein einzelner grüner Spike, eine Demo oder ein grünes CI/PR ist keine spielfertige AdventureShift-Version.
4. **V1-Grenzen unverändert:** Selbsthostbarer **Single-VPS** ohne verpflichtende externe Cloud/Cluster; GM und Player in eigenen Browsern, **genau ein aktiver Spielleiter je Kampagne**, genau **eine** kanonische CampaignWorld und **eine** autorisierte aktuelle 14.13-WorldWriterGeneration. Spätere Mehrfach-GM-/Co-SL-Möglichkeiten aus 08.2 sind **keine V1-Freigabe**.
5. **Fachrechte unverändert:** 14.1–14.15 und alle bestehenden GM-/Account-/Session-/Actor-/DomainOwner-/Source-/Fog-/History-/Viewer-/Privacy-/Media-/Secret-/Host-/Support-/Recoverygrenzen; keine generelle Host-/Support-/GM-/Player-Impersonation, keine private DM-/NPC-/Quest-/GM-/PlayerSecret-ReadAll-Ausnahme und keine neue Neben-World-/Regel-/Quest-Engine.
6. **Explizite ältere Festlegungen bleiben:** 02.118 A – keine persistierten ungesendeten Chatentwürfe/kein Reconnect-AutoSend; 14.15 A – manuelle Sicherheitsvorfallbehandlung, keine neue automatische globale IncidentCase-/Containment-Engine. Audio als späteres optionales Modul; konfigurierbare Kampagnenmodule und Automationsstufen sowie reale Voicechat-/manuelle Spielmöglichkeiten bleiben erhalten.
7. **Keine Wirkung durch Entwicklungsstatus:** Ein Beschluss-, Git-, Spike-, Test-, CI-, Deployment- oder Releasestatus führt für sich weder WorldReset, Roll-/Quest-/Item-/NPC-/Traktor-/02.99-WorldEffect noch SessionGrant, SecretFreigabe, Migration oder Kampagnenaktivierung aus.

## 2. Konkret geordneter Start in die Technikphase

Die Reihenfolge ist ein **Abhängigkeitsplan**, kein bereits ausgeführter Workflow. Für jeden Nachweis gelten exakte Commit-/Build-/Schema-/Config-/Fixture-/Environment-IDs und klare Ergebnisse `PASS`, `FAIL`, `BLOCKED`, `NOT_RUN` oder begründetes `NOT_APPLICABLE`.

| Schritt | Konkrete Arbeitsleistung / Eintrittsbedingung | Anfangsstatus |
| --- | --- | --- |
| **C.1 – Technikkandidaten aufnehmen** | B.18: kleine reale, aktuell quellengestützte Shortlist für serverautoritativen, transaktionalen Browser-/Single-VPS-Mehrspieler-Kern; Versionen, Lizenz, Wartung, Security, SingleWriter/Receipt, Realtime, Reconnect, Recovery prüfen; erste B.10-ADR als **vorläufige Hypothese**, kein finaler Stack | `NOT_RUN` |
| **C.2 – Kritischen Beschluss-/Sicherheitsabgleich durchführen** | Betroffene B.4-/B.10–B.16-Verträge, 14.8-Isolation, 14.12-WorldTransaction/OriginalReceipt, 14.13-WriterFence, aktuelle Viewer-/Source-/GM-/Actor-/History-/Privacyrechte und B.17-Readiness am begrenzten B.11-P1/P2/P3-Scope wirklich prüfen; Konflikte lokal sperren und referenzieren | `NOT_RUN` |
| **C.3 – Entwicklungs- und Git-Grenzen einrichten** | B.21 isolierter Experimentzweig/Worktree ohne Produktiv-Keys/-Daten; B.22 **tatsächlich wirksame** Git-/CI-/Review-/Secret-/Änderungsschutz-Gates, bevor risikoreicher Code integriert wird; keine irreführende Branchschutzbehauptung anhand von Dokumentation | `NOT_RUN` |
| **C.4 – Minimalen lokalen B.11-Technikspike bauen und testen** | B.19 LOCAL_DEV mit B.20 reproduzierbarem Stand: getrennte synthetische GM-/Player-Sessions, CurrentACL, ein erlaubter und ein verbotener typisierter Command, persistente WorldRevision, atomarer 14.12-Commit/OriginalOperationReceipt, 14.13-Fencing, gefilterte B.5-Projektion; echte Negative für Duplicate, LostAck, Revoke, ConcurrentRevision, Restart, Reconnect, Outbox | `NOT_RUN` |
| **C.5 – Isolierten Single-VPS-/Staging-Nachweis führen** | Erst nach separatem realem 14.8-/B.17-Preflight: B.19 ISOLATED_VPS_STAGING mit überprüfbar entsprechendem B.20-Source-/Buildstand, ohne SharedSecrets/-World/-DB/-Queue/-Backup; reale Browser-/Netz-/Security-/World-/Recoverytests unabhängig bewerten | `NOT_RUN` |
| **C.6 – ADR und selektive Härtung** | Messergebnisse bewerten, technische Architekturentscheidung in B.10-ADRs dokumentieren, ggf. gezielte Alternativprobe; nur durch B.12-/B.14-/B.15-/B.13-Gates gehärtete Komponenten kontrolliert über B.22 in die Entwicklungsbasis übernehmen | `NOT_RUN` |
| **C.7 – Fachliche Vertikalslices für B.2 B** | Erst anschließend inkrementell Charakter/Actor, Szenen/Nodes, Bewegung/Kampf/Initiative, Würfel, NPC, Regelpakete, Inventar, Quests, Sources/Media/Privacy und die vom Kampagnenkonfigurator erlaubten Modi integrieren; reale R1-/R2- und B.8-Releasegates später **vollständig** nachweisen | `NOT_RUN` |

Die Schrittbezeichnungen C.1–C.7 sind organisatorische Arbeitsabschnitte und **keine neuen Fachengines oder zusätzlichen Rollen**. Die vorläufige Reihenfolge darf für unabhängige ungefährliche Teilaufgaben angepasst werden; der echte Sicherheits-/VPS-/WorldWrite-Gate-Vorrang nicht.

## 3. Erster minimaler fachlicher Prüfvertrag

1. **Testidentitäten:** Zwei eigenständige synthetische Sessionkontexte (GM und Player) mit ausdrücklich gesetzten CampaignMembership-, GM-/Actor-/Source-/Historyrechten; keine echten Steam-/Liveaccounts, keine allgemeine GM-/Player-Impersonation. Ein synthetischer Auth-Vertrag ist kein Nachweis der späteren produktiven Steam-Authentifizierung.
2. **Positive Aktion:** Ein berechtigter fachlicher TestCommand mit `operationId`, `expectedWorldRevision`, zuständigem B.4-DomainOwner und gültigen aktuellen Rechten führt genau **einen** atomaren kanonischen WorldCommit aus; das `OriginalOperationReceipt` ist persistent und eindeutig.
3. **Verweigerte Aktion:** Ein unberechtigter, veralteter oder widerrufener Player-/GM-/Actor-/Source-/Historyzugriff verursacht **keinen** WorldEffect und verrät keine verdeckten GM-/NPC-/Quest-/PlayerSecrets über Response, WebSocket, Reconnect, Snapshot, Delta, Media oder Logs.
4. **Wiederholung/Konkurrenz:** Duplicate und verlorenes Ack liefern dieselbe ursprüngliche Operationserkenntnis ohne erneute Wirkung; RevisionConflict/WriterFence verhindern zweiten Writer oder konkurrierenden ungeprüften Commit, inklusive Neustart/Recovery und begrenzter Outbox-/Job-Reconciliation.
5. **Begrenztes Ziel:** Der Spike testet **nur** diese sicherheits-/transaktionskritische technische Hypothese. Er verlangt noch keine vollständige UI, Kartenwelt, RulePacks, 3D, Audio, Würfel-/NPC-/Questautomatik oder B.2-B-Fachbreite; nichts davon wird durch die Probe gestrichen.

## 4. Abgleichsregister und nicht zu verwechselnde Freigaben

| Bestehender Beschluss | Abzugrenzender verbindlicher Vertrag |
| --- | --- |
| B.1/B.2/B.8/B.9 | Überprüfbare Inkremente, breite erste Spielversion gemäß B.2 B, reale modulübergreifende Referenzkampagne und zwei unterschiedliche R1/R2-RulePack-Nachweise bleiben getrennt von B.11-Spike/CI. |
| B.3–B.7 | Kampagnenkonfiguration/Automationsstufen, einheitliche Fachreferenzen und Owner, sichere Zuschauerprojektionen, gefiltertes Vorladen, ausdrückliche Reconnect-Aktionen; keine ClientWorldTruth. |
| B.10–B.12/B.17–B.22 | Evidenzbasierte Stackentscheidung, echter isolierter P1–P3-Kern, begrenzte Readiness, selektive Härtung, lokale/VPS-Trennung, reproduzierbare Builds, isolierter Zweig und nachweisbare Integrationsgates. |
| B.13–B.16 | Vertikale Fachintegration, versionierte fachliche Vertragspflege, konkrete beschlussgebundene WorkItems und begrenzte Prüfung materieller Abweichungen; keine globale undokumentierte Neuentwicklung. |
| 14.8/14.12/14.13 | Wirksame unabhängige Testisolation, kanonische atomare WorldTransactions und OriginalReceipts, genau eine gefencete WorldWriter-Autorität, ohne unzulässige globale CrossStore-ACID-Annahme. |
| 14.1–14.15, 09.x, 12.x, 15.4 | Auth-/Data-/Source-/Recovery-/Service-/Media-/Security-/Privacy-/Retention-/Supportrechte und echte Deployment-/Releasegates behalten Vorrang. |

**Abgleichsergebnis zum Zeitpunkt dieses Dokuments:** Die oben genannten **bekannten** Grenzen wurden beim Übergangsplan berücksichtigt. Eine vollständige automatische/verifizierte Analyse **aller** historischen Fachworkshoptexte und aller technischen Folgewirkungen wurde **nicht** durchgeführt; einzelne B.16-Konfliktprüfungen bleiben als reale C.2-Arbeit offen. Daher keine pauschale Freigabe aufgrund dieser Tabelle.

## 5. Sofortiger nächster Arbeitsauftrag und Statusdisziplin

**Nächster konkreter Auftrag C.1:** Aktuelle technische Kandidaten und ihre Quellen/Versionen/Lizenzen/Wartungsstände erheben, dann eine kleine Hypothesen-Shortlist für den B.11-/B.19-/B.20-Minimalpfad gegen die oben genannten Hardgates prüfen. Danach B.17-/14.8-Readiness und tatsächlichen Git-/CI-Schutz **getrennt** belegen, bevor gefährdende Tests oder Produktivintegration erfolgen. Konkrete Technologie-, VPS-, Sicherheits- und Deployentscheidungen benötigen dokumentierte echte Nachweise; sie wurden **durch B.23 C nicht bereits getroffen**.

**Kein weiterer allgemeiner Grundsatzfrageblock erforderlich.** Neue Fragen nur für tatsächlich offene, fachlich wesentliche Entscheidungen, die sich im konkreten WorkItem nicht sicher aus bestehenden Beschlüssen ableiten lassen. Fachliche Module bleiben über B.14/B.15 änderbar. Ein späteres Produktrelease folgt ausschließlich den unverändert geltenden B.2-/B.8-/B.9-/14.6-/15.4-Freigaben.
