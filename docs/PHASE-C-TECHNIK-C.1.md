# AdventureShift – Phase C.1: erste reale Technik-Kandidatenerhebung (vorläufig, nicht freigegeben)

**Erhebungsdatum:** 04.11.2026. **Status:** `RESEARCH_PARTIAL` – überprüfte offizielle Veröffentlichungs-/Support-/Lizenzquellen und schreibgeschützte Entwickler-PC-Bestandsaufnahme; **kein** Code-, Lizenzgesamt-, Vulnerability-, Leistungs-, B.17-Readiness- oder B.11-Spike-PASS. **B.23 C** [beendet den allgemeinen Grundsatzfrageblock](PHASE-B-WORKSHOP-B.23.md). Die technische Auswahl bleibt nach [B.18 C](PHASE-B-WORKSHOP-B.18.md) und [B.10 C](PHASE-B-WORKSHOP-B.10.md) evidenzgesteuert.

## 1. Maßgebliche fachliche Grenzen

- Ein eigener Single-VPS mit separaten GM-/Player-Browsern, **genau ein aktiver GM je V1-Kampagne**, **eine** kanonische CampaignWorld und **eine** aktuelle gefencete WorldWriter-Autorität.
- Serverseitige CurrentACL-/CampaignMembership-/ActorControl-/Source-/History-/Fog-/Privacy-/Media-Rechte **an jedem relevanten Request, Commit und Fanout**, keine Browser-WorldTruth oder pauschalen ReadAll-/Impersonation-Pfade.
- Eine persistente, transaktional wirksame DomainAction mit WorldRevision, eindeutigem OriginalOperationReceipt, OperationId-Deduplizierung, ExpectedRevision-Konflikterkennung, Crash-/LostAck-/Restart-/Outbox-/Reconnect-Sicherheit. **PostgreSQL allein liefert diese Anwendungsgarantien nicht; sie müssen implementiert und mit negativen Tests belegt werden.**
- Lokale und isolierte VPS-/Staging-Testumgebungen gemäß B.19/B.20 und 14.8, niemals LiveSecrets/-World/-Backups/-Accounts für synthetische Techniktests.
- Lizenzen auch transitiver Dependencies, aktueller Securitystatus, Wartung, Updatepfad und portable Single-VPS-Betriebsmittel prüfen. Kein Technologie- oder UI-Framework darf eine zweite World-, Rule-, Turn-, Owner- oder ACL-Engine einführen.

## 2. Aktuell geprüfte Basistechnologien

| Technologie | Offiziell überprüfte Angabe am 04.11.2026 | Vorläufiges Ergebnis |
| --- | --- | --- |
| **Node.js 26.x** | Node Release WG: **26.x Active LTS**, EOL 30.04.2029; Node selbst unter MIT, eingebaute Drittlizenzen gesondert | Geeignete Laufzeithypothese, nicht Security-/Production-PASS |
| **Fastify 5.x** | Offizieller LTS-Plan nennt Node 20/22/24/26; **5.12.8** als neuestes sichtbares 5.x-Release vom 02.11.2026 **mit Securityfix**; MIT, Dependencies separat | Geeignete HTTP-/API-Hypothese; Paket-/Advisory-Review vor echter Nutzung |
| **PostgreSQL 18.6** | 18.x unterstützt, **18.6** aktueller veröffentlichter Minor-Stand (13.08.2026), PostgreSQL-Lizenz; **19 derzeit nur RC**, nicht als produktionsreife Baseline wählen | Gemeinsamer Datenbankkandidat für alle drei Backends; reale Atomizität/CAS/Receipt-Fences erst beweisen |
| **Go 1.27.3** | Offizielle Go-Releasehistorie: 1.27.3 vom 19.10.2026; Go-Compiler/Standardbibliothek unter BSD-artiger Lizenz | Ernstzunehmender kleiner Serverkandidat, konkrete WebSocket-/DB-Dependencies offen |
| **.NET 10 LTS** | Microsoft: .NET 10 LTS, Support bis November 2028, 10.0.14 als angezeigter Patchstand; Runtime-/ASP.NET-Core-Quellen überwiegend MIT mit distributionsabhängigen Zusatzbedingungen | Ernstzunehmender Serverkandidat, konkrete Npgsql-/WebSocket-/ASP.NET-Pakete offen |

**Quellenliste (abrufbar am 04.11.2026):**
- [Node.js Release WG – Lifecycle](https://github.com/nodejs/Release/blob/main/README.md)
- [Node.js – Lizenz](https://github.com/nodejs/node/blob/main/LICENSE)
- [Fastify – offizielle LTS-Versionen](https://github.com/fastify/fastify/blob/main/docs/Reference/LTS.md)
- [Fastify – Releases/Securityfix](https://github.com/fastify/fastify/releases)
- [Fastify – Lizenz](https://github.com/fastify/fastify)
- [PostgreSQL – Versionierungs-/Supportpolicy](https://www.postgresql.org/support/versioning/)
- [PostgreSQL – 18.6 Release Notes](https://www.postgresql.org/docs/release/18.6/)
- [PostgreSQL – Lizenz](https://www.postgresql.org/about/licence/)
- [PostgreSQL – 19 RC (noch kein GA)](https://www.postgresql.org/)
- [Go – Releasehistorie](https://go.dev/doc/devel/release)
- [Go – Lizenz](https://go.dev/doc/install/source)
- [.NET – Supportpolicy](https://dotnet.microsoft.com/en-us/platform/support/policy)
- [.NET – Lizenzhinweise](https://github.com/dotnet/core/blob/main/license-information.md)

**Quellenstatus:** Offizielle Angaben sind Versions-/Lizenzevidenz, **kein vollständiger Auditscan**. Einzelversionen und Securityadvisories sind vor Installations-/Testbeginn erneut nach Repo-/Package-Registry-/Herstellerstand zu prüfen. Insbesondere Fastify Securityfixes und PostgreSQL-Securityhinweise sind nicht durch bloße Major-Versionsnummern abgegolten.

## 3. Drei eng begrenzte technische Kandidatenpfade

| Pfad | Aufbau nur als B.11-/B.19-Testhypothese | Begründung und offen bleibendes Risiko |
| --- | --- | --- |
| **K1 – führende Erstprobe** | **TypeScript/Node 26 LTS + Fastify 5.x (mind. geprüfter Sicherheits-Patchstand) + PostgreSQL 18.x**; minimale getrennte Browserseiten und streng versionierter API-/WebSocket-Vertrag, Bibliotheken für DB-/Realtime erst nach Licence-/Securityprüfung konkret festlegen | Browser-/Backend-Typen lassen sich geteilt prüfen; auf dem Entwickler-PC ist Node 26 bereits vorhanden. Risiko: Realtime-/ACL-/Race-/Worker-Sicherheit und zuverlässige WorldWriter-/Receipt-Transaktionen **nicht durch Framework garantiert**. |
| **K2 – gezielte Alternative** | **Go 1.27.x + PostgreSQL 18.x**, Web/API-/Realtime-Libraries erst bei gezielter Ersatzprobe wählen | Kompakter Einprozess-VPS-Pfad möglich. Risiko: zusätzlicher Sprach-/Contract-/Buildpfad; kein lokales Go installiert; dasselbe World-/Securitymodell bleibt echte Implementierungsarbeit. |
| **K3 – gezielte Alternative** | **ASP.NET Core auf .NET 10 LTS + PostgreSQL 18.x**, Npgsql-/Realtime-Bibliotheken nach echtem Dependencyreview | Gut wartbarer Serverpfad möglich, .NET-10-SDK am PC vorhanden. Risiko: zusätzlicher Sprach-/Contractpfad und konkrete DB-/SignalR-/Securityintegration noch nicht geprüft. |

**Vorrang als Hypothese:** `K1` ist der **einzige primär geplante P1–P3-Minimaltestpfad**, weil lokal bereits ein passender aktiver LTS-Runtimepfad und Git/Docker verfügbar sind und TypeScript-Browser-/Serververträge ohne zweifache Fachmodellimplementierung verglichen werden können. Das ist **noch keine endgültige Technologie-ADR/Freigabe**. `K2` und `K3` sind nur **gezielt** zu prüfen, falls ein konkretes K1-Risiko mit Nachweis scheitert. Kein paralleler Komplettbau von drei Systemen.

**Nicht vorzeitig entschieden:** Produktions-Frontend, Kartenrendering, State-Management, Auth-/Steam-Adapter, WebSocket-/ORM-/Migration-/Job-/Queue-/Cache-/Reverse-Proxy-/Container-Framework, Plugin-/RulePack-Sandbox, endgültige Packageversionen oder Single-VPS-Größe. Für B.11 dürfen einfache getrennte Browseransichten reichen; spätere UI-/Widgetregeln bleiben erhalten.

## 4. Lokal beobachtete Werkzeuglage (TM-PC, schreibgeschützt abgefragt)

- Windows 11 Pro; Git vorhanden. Lokaler Arbeitsklon `C:\Users\muell\source\repos\DnD2` war beim Lesetest **sauber** auf `main` mit HEAD `aee148e` (**vor** den danach über GitHub geschriebenen B.23-Dokumentationscommits).
- Node `v26.10.0` vorhanden; .NET-SDKs `9.0.316` und `10.0.401` vorhanden; Docker Client und Server `29.8.0` antworten. `pnpm`, `go` und `psql` wurden nicht im PATH gefunden.
- Dieser reine Bestandscheck hat **keine Container, Datenbanken, Nutzer, Keys, Netzfreigaben, Branchregeln, Testsoftware oder Services** angelegt und kann **keine** 14.8-Isolation beweisen. Versionsabfragen sind keine B.17-Readiness.

## 5. Reale Negativprüfungen für eine später zulässige K1-Erstprobe

1. Test-only GM-/Player-SessionScopes vor Setup; ausschließlich synthetische Campaign/Account/Actor/Source/World-Daten; keine Produktions-Credentials.
2. Ein `ALLOW`-B.4-DomainCommand ergibt genau eine kanonische WorldRevision und sein persistentes `OriginalOperationReceipt`; ein `DENY`-Command ergibt null Änderungen und null Secrets.
3. Duplicate `operationId`, verlorene Antwort, Retry, konkurrierende `expectedWorldRevision`, abgelaufene WriterGeneration und Restart dürfen weder doppelte Wirkung noch zweite Writerautorität verursachen.
4. Reconnect-/WebSocket-/Snapshot-/Delta-Projektion berücksichtigt **aktuelle** Mitgliedschaft, GM-/Actor-/Source-/History-/Fog-/Privacyrechte; nach Revoke keine weiteren unberechtigten Daten-/Medienausgaben.
5. Traces/Logs/Outbox/JobRecovery enthalten keine Secret-/DM-/GM-/Player-ReadAll-Leaks und erzeugen keine automatische WorldAction über das Originalreceipt hinaus.
6. Identisch fachlicher Buildkandidat, aber jeweils isolierte Daten/Keys/Sessions/Backups auf LOCAL_DEV und ISOLATED_VPS_STAGING; separate PASS-/FAIL-Nachweise. Keine Stagingausführung ohne C.2/B.17-/14.8-Gate.

## 6. Nächste Eintrittsschranke und offener Arbeitsstand

- **C.1 – technische Primärhypothese dokumentiert, aber nur `RESEARCH_PARTIAL`**: genaue DB-/WS-/Schema-/CLI-/Buildbibliotheken, TransitiveLicense-/Advisory-/Maintenanceprüfung und versionsgebundene B.10-ADR/Dependency-Lock noch offen.
- **C.2 – noch `NOT_RUN`:** gezielter B.16-/B.17-/14.8-Preflight inklusive realer lokaler Testisolation und unberührter VPS-Produktionsgrenzen; bei fehlendem Beleg `BLOCKED`, nicht `PASS`.
- **C.3 – noch `NOT_RUN`:** B.21-Experimentzweig und tatsächlich wirksame B.22-Git-/CI-/Secret-/PR-Gates vor risikoreichem Test-/Übernahmecode.
- **C.4/C.5 – noch `NOT_RUN`:** keine B.11-P1/P2/P3-Software oder Tests, keine lokale oder VPS-WorldTransaction-/Securityevidenz.
- **C.6/C.7 – noch `NOT_RUN`:** kein gehärteter Produktivcode oder B.2-B-/B.8-/B.9-/14.6-/15.4-Release.

**Fazit:** Aus offiziellen Quellen und lokalem Inventar ist `K1` als **prüfbare erste technische Hypothese** vertretbar. Ob K1 die Sicherheit, Atomizität, WorldFence-/Receipt- und Reconnectinvarianten erfüllt, lässt sich **nur durch echte Tests** beantworten. Bis dahin keine Stack-Freigabe und keine Behauptung eines lauffähigen AdventureShift.
