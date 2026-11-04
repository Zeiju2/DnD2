# AdventureShift – Phase B, Beschluss B.15 C: beschlussverknüpfte, überprüfbare Entwicklungsaufträge

**Nachfolgender Beschluss B.18 C (04.11.2026):** [Kleine risikogebundene Technik-Shortlist und ein primärer isolierter B.11-P1/P2/P3-Testpfad mit nur gezielt nötigen Alternativproben und versionierten B.10-ADRs](PHASE-B-WORKSHOP-B.18.md). Serverautorität, 14.12-WorldTransaction-/OriginalReceipt, 14.13-SingleWriter/Fence, aktuelle Auth-/GM-/Actor-/Source-/History-/Privacy-/Viewerrechte, SingleVPS, Lizenz, Wartung und Recovery sind verbindliche Eignungsgrenzen. **Noch keine Kandidaten recherchiert, kein Stack final gewählt, B.17-Readiness nicht ausgeführt, B.11-Spike NOT_RUN, B.12-/B.13-Produktion nicht freigegeben.** Keine parallelen vollständigen Full-Stacks und kein B.2-/B.8-/B.9-/14.6-/15.4-Release durch Spikeerfolg. **Nächste Grundfrage B.19: getrennte lokale und VPS-/Staging-Testausführung.**

**Nachfolgender Beschluss B.17 C (04.11.2026):** [Begrenzter Architektur-/Sicherheits-Readiness-Check vor der ersten echten B.11-P1/P2/P3-Technikprobe](PHASE-B-WORKSHOP-B.17.md). Testscope, B.10–B.16-Verträge, 14.8-synthetische Isolation, Kandidaten, echte WorldWriter-/CurrentACL-/OriginalReceipt-/Audience-/Revoke-/Reconnect-/Recovery-Positiv-/Negativkriterien und redigierte Evidenz vor Testbeginn prüfen. **Preflight nur geplant, nicht ausgeführt; B.11 weiterhin NOT_RUN, B.12 nicht gehärtet, kein Stack und kein B.2-Spielrelease freigegeben.** Keine Vollplanung aller UI-/RulePack-Feindetails und keine produktiven Testdaten. **Nächste Grundfrage B.18: begrenzte Auswahl und Prüfung der Technik-Kandidaten.**

**Nachfolgender Beschluss B.16 C (04.11.2026):** [Gezielte versionierte Prüfung und begrenzte Sperre bei Beschlusswidersprüchen, widerlegten technischen Annahmen oder sicherheitskritischen Vertragslücken](PHASE-B-WORKSHOP-B.16.md). Bestehende Entscheidungen bleiben bindend; materielle Abweichungen brauchen eine ausdrücklich zuständige Fachentscheidung sowie gegebenenfalls B.14-Impact-/Migration-/ConsumerRegression. Unabhängige sichere B.13-/B.15-Arbeiten dürfen fortfahren. Keine globale neue Incident-/WorldEngine, keine zusätzlichen GM-/Actor-/Source-/Privacyrechte und keine Worldaktion durch Konfliktstatus. **B.11 weiterhin nur geplant, B.12 ungehärtet, B.13–B.15 nicht implementiert; B.2-/B.8-/B.9-/14.6-/15.4-Gates bleiben Pflicht.** **Nächste Grundfrage B.17: Readiness-Grenzen vor dem ersten echten Technikspike.**

**Stand:** 04.11.2026. **B.15 C vom Projektinhaber ausdrücklich beschlossen.**
**Status:** Verbindliche Planungs- und Umsetzungsgrundstruktur; **noch keine Implementierung, keine ausgeführte B.11-Probe, kein gehärteter B.12-Kern, keine bestandenen B.13-Slices, keine endgültige Stackwahl und kein spielbarer Release.**
**Entscheidung C:** Die umfangreiche Fach- und Sicherheitsplanung wird beim Entwicklungsbeginn in **kleine, versionierte, nachvollziehbare und jeweils end-to-end überprüfbare Entwicklungsaufträge** übersetzt. Jeder Auftrag referenziert die geltenden Beschlüsse, den maßgeblichen DomainOwner und B.4-/B.14-Contractstand, fachliche und technische Abhängigkeiten, die betroffenen GM-/Player-/Actor-/Source-/History-/Privacy-/World-/RulePackrechte, konkrete Positiv-/Negativnachweise und den tatsächlich erreichten Status. Einzelheiten werden **für den unmittelbar anstehenden Schritt** präzisiert, nicht unbegrenzt im Voraus.
**Nicht beschlossen:** Kein vollständiges Einfrieren sämtlicher UI-/Regel-/Algorithmusdetails vor dem ersten Code und keine unabhängigen „Modul-to-do“-Listen ohne Querverträge. Ein dokumentierter Auftrag, ein Git-Commit, ein Mock-Test, eine grüne CI-Prüfung oder ein intern bestandener Vertikalschnitt ist **keine** fachliche WorldAction und **keine** B.2-B-Spielreleasefreigabe.
**V1-Grenzen:** Ein selbst betriebener VPS, unterschiedliche Spielleiter-/Spielerbrowser, **genau ein aktiver Spielleiter und genau eine kanonische CampaignWorld je Kampagne**, ein autorisierter WorldWriter. Modulare regelwerksneutrale Konzepte und optionale Kampagneneinstellungen, keine zweite Fachengine, kein pauschaler GM-/Support-/Host-/Security-ReadAll-Zugriff.
**Verweise:** [Planungsstandard](PLANUNGSSTANDARD.md) · [B.1](PHASE-B-WORKSHOP-B.1.md) · [B.2](PHASE-B-WORKSHOP-B.2.md) · [B.3](PHASE-B-WORKSHOP-B.3.md) · [B.4](PHASE-B-WORKSHOP-B.4.md) · [B.5](PHASE-B-WORKSHOP-B.5.md) · [B.7](PHASE-B-WORKSHOP-B.7.md) · [B.8](PHASE-B-WORKSHOP-B.8.md) · [B.9](PHASE-B-WORKSHOP-B.9.md) · [B.10](PHASE-B-WORKSHOP-B.10.md) · [B.11](PHASE-B-WORKSHOP-B.11.md) · [B.12](PHASE-B-WORKSHOP-B.12.md) · [B.13](PHASE-B-WORKSHOP-B.13.md) · [B.14](PHASE-B-WORKSHOP-B.14.md); [14.1](SICHERHEIT-WORKSHOP-14.1.md) · [14.2](SICHERHEIT-WORKSHOP-14.2.md) · [14.6](SICHERHEIT-WORKSHOP-14.6.md) · [14.8](SICHERHEIT-WORKSHOP-14.8.md) · [14.9](SICHERHEIT-WORKSHOP-14.9.md) · [14.12](SICHERHEIT-WORKSHOP-14.12.md) · [14.13](SICHERHEIT-WORKSHOP-14.13.md) · [15.2](ERWEITERUNGEN-WORKSHOP-15.2.md) · [15.4](ERWEITERUNGEN-WORKSHOP-15.4.md).

## 1. Was ein Entwicklungsauftrag verbindlich festhält

1. **Identität und fachlicher Zweck:** Stabile WorkItemId, überprüfbarer vertikaler Benutzungsfall, Nicht-Ziele, geplantes Entwicklungsinkrement und identifizierte betroffene Fachdomänen. Ein Auftrag darf mehrere Verbraucher umfassen, muss aber klein genug für tatsächliche End-to-End-Abnahme bleiben.
2. **Verbindliche Beschlussherkunft:** Konkrete nummerierte bisherige Fach-/Sicherheits-/UI-/Rule-/Kampagnenbeschlüsse samt gewählter Variante und ausdrücklich **abgewählten** Alternativen. Kein lokaler Auftrag darf einen Beschluss still durch eine bequemere Implementierung ersetzen.
3. **Owner und Contractstände:** Die B.4-DomainOwner, B.14-ContractRevisionen, VersionPins/RulePack-/Source-/Audienceversionen und betroffene Producer/Consumer; neue Daten- oder Befehlsgrenzen gehen gegebenenfalls zuerst durch B.14, nicht als heimlicher Zweitwriter.
4. **Prerequisites und Blocker:** Benötigte B.10-ADR, echte B.11-Risikoprobe, B.12-Übernahme-/Härtungsfreigabe, B.13-gemeinsame Ports, andere Fachaufträge, Umgebung/Security-, Daten-, Lizenz- oder Migrationsnachweise. Nicht erfüllte Blocker bleiben **BLOCKED**, nicht künstlich bestanden.
5. **Rechte und unerlaubte Pfade:** Aktuelle Steam-/Account-/Session-/GM-/Actor-/Campaign-/Group-/Owner-/Source-/Fog-/History-/Privacy-/Rule-/Asset-/Media-/Quota-/Securityrechtsschranken sowohl für Lesen, Vorladen, Anzeigen, Editieren, Publizieren als auch für tatsächliche WorldCommits.
6. **Vorgesehene fachliche Wirkungen:** Authentifizierter ActionIntent, eindeutig zulässiger DomainCommand, ExpectedRevision/OriginalOperationId, jeweils genau ein 14.12-/14.13-OriginalWorldCommit bei tatsächlich weltwirksamem Vorgang, dauerhaftes OriginalReceipt und getrennte B.5-Audienceprojektionen/Delivery; UI- oder Config-/Preview-Schritt selbst löst keine WorldAction aus.
7. **Akzeptanzbelege:** Positive und negative Ausführungsszenarien für zwei tatsächliche berechtigte oder unberechtigte Browser, getypte Owner-/RulePack-/Version-/Source-Grenzen, Konkurrenz, Dedupe/LostAck, Revoke, Reconnect, Restart, Recovery und beteiligte Domänen. Nicht berührte Testfamilien als begründet **NOT_APPLICABLE**, niemals heimlich als PASS.
8. **Betrieb und Releasegrenzen:** 14.8-Test-/Prod-Isolation, 14.6-Deployment-/Migrations-/Backup-/Rollbackfähigkeit, 12.7-/14.9-Schutz und 15.4-StableRelease-Pins sowie referenzierte B.8-/B.9-Gates. Nur anfallende Spezialdetails konkretisieren, den Releaseumfang B.2 B aber nicht reduzieren.

## 2. Versionierte Planungsobjekte (Arbeitsnamen)

| Objekt | Zweck |
|---|---|
| **DevelopmentWorkItem / WorkItemRevision** | Unveränderlich verknüpfbarer fachlicher Auftrag mit Version, Scope und tatsächlichem Status, kein Domain-/WorldRecord |
| **DecisionTrace / RequirementCoverage** | Verweise auf verpflichtende Entscheidungen, An/Aus-/Ausnahme-/Ausschlussanforderungen und explizite Nachweisabdeckung |
| **WorkDependency / BlockerEvidence** | Versionierter benötigter Vorläufer, negativer/fehlender Beleg und zulässige Entblockungsbedingung |
| **OwnerContractBinding / ConsumerMap** | Zuständiger B.4-Fachowner, B.14-ContractRevisionen und betroffene UI-/API-/WS-/Rule-/Node-/World-/Media-/Migration-Verbraucher |
| **SecurityAcceptanceMatrix** | Positive/negative echte CurrentACL-/GM-/Actor-/Source-/History-/Privacy-/Receipt-/Revocation-/Quota-Testbedingungen |
| **ImplementationEvidence / VerificationOutcome** | Exakter Git-/Build-/Schema-/Fixture-/RulePack-/Teststand mit PASS/FAIL/BLOCKED/NOT_RUN/NOT_APPLICABLE und realer Beobachtung |
| **WorkItemDisposition** | Technischer Status: PLANNED, READY, IN_PROGRESS, BLOCKED, VERIFIED oder REWORK; VERIFIED gilt nur für den konkret abgenommenen Auftrag |
| **ReleaseCoverageReference** | Getrennter Nachweisbezug auf den vollständigen B.2-B-Funktionsumfang, 12 B.8-Gates, R1/R2-B.9, 14.6-/15.4-Produktfreigabe |

Dies ist ein **Planungs-/Entwicklungsnachweis**, keine neue LiveGame-, Rollen-, Rechte-, Issue-, Audit- oder World-Workflow-Engine. Ob Git-Dateien, Issues, Tracker oder CI verwendet werden, bleibt offen; es gibt keine Verpflichtung auf einen bestimmten externen Cloud-Dienst.

## 3. Arbeitsablauf von Beschluss zu geprüfter Implementierung

1. **Bedarf identifizieren:** Ein konkretes funktionsorientiertes B.13-Inkrement auswählen, ohne die späteren B.2-B-Pflichtdomänen durch Reihenfolgenwahl auszuschließen.
2. **Beschluss- und Abhängigkeitskette verbinden:** Exakte bisherige Beschlüsse, Verbote, B.4-/B.14-Ownerverträge und offene B.10-/B.11-/B.12-Nachweise ermitteln; für dringende Konflikte keine stillen Ersatzentscheidungen treffen.
3. **Nur erforderliche Details präzisieren:** Felder, Testfixtures, API, UI, Quota, Lizenz-/RulePack- und Datenformate **erst für diesen Schritt** entsprechend Planungsstandard konkret festlegen. Beliebige Klassen-/W20-/HP-/Slot-/UI-Defaults nicht in den generischen Kern hardcoden.
4. **Vor Umsetzung Eintritt prüfen:** Echte technische Voraussetzungen, isolierte Umgebung, Testdaten, Rechte-/Source-/Security-Contracts, Daten-/Migrationseignung und messbare Akzeptanzkriterien müssen vorhanden oder ausdrücklich BLOCKED sein.
5. **Eine vertikale Funktion bauen:** Eigener GM-/Player-Browserfluss → B.5-viewergefilterte API/Realtimedaten → B.4-FachOwner/Rules → zulässiger 14.12-/14.13-WorldCommit und OriginalReceipt → Reconnect/Recovery; keine UI-Dummywelt und keine gesonderte Schattenfachlogik.
6. **Belege am exakten Stand ausführen:** Positiv- und Negativfälle mit realen getrennten Sitzungen, Source-/Fog-/Privacy-/GmEpoch-/Actor-/Revision-/Duplicate-/Failure-/Recovery-Schranken; Testframework-Mocks allein nicht ausreichend, wenn echte Integration gefordert ist.
7. **Ergebnis getrennt festhalten:** Auftrag nur VERIFIED, wenn für seine Kriterien tatsächliche Belege vorliegen. FAIL/BLOCKED/NOT_RUN oder ungeklärter RulePack-/Lizenz-/Privacyfall bleiben sichtbar; ein „grüner“ technischer Schritt wird nicht zum Spielrelease erklärt.
8. **Rückwirkungen kontrollieren:** Gemeinsamer Vertragswechsel geht durch B.14-Impact/Consumer-/Migrationsprüfung und Regression bereits integrierter Aufgaben. Nicht kompatible aktive Kampagnen/VersionPins werden nicht still aktualisiert.
9. **Umfang des fertigen Produkts separat prüfen:** B.2-B-Fachumfang sowie B.8-/B.9-/14.6-/15.4-Gates müssen später **als Gesamtheit tatsächlich** bestehen. Kein einzelner VERIFIED-Auftrag, erfolgreicher ADR oder Code-Merge kann die Freigabe ersetzen.

## 4. Verbindliche Beispiel-Auftragsfamilien – noch keine ausgeführten Aufgaben

| Auftragsfamilie | Untergrenze für spätere Abnahme |
|---|---|
| **B.11-P1/P2/P3-Spike** | Isolierter echter SingleWorld-/WorldWriter-/OriginalReceipt-/GM-/Player-/Source-/Reconnect-/Revoke-Nachweis; kein FakeAuth-Test als geprüfter Steam-End-to-End-Nachweis |
| **B.12-Produktionshärtung** | Einzeln geprüfte Übernahme oder Ersatz von Komponenten; Auth-/ACL-/Privacy-/Recovery-/Security-/Lizenz-/Servicekontrolle und Wiederholung der Tests nach Umbau |
| **B.13-Fachinkrement, etwa erlaubte Tokenbewegung** | Tatsächlicher Actor-/Turn-/Node-/Fog-geprüfter WorldEffect; verbotene Bewegung ohne Änderung; OriginalReceipt, getrennte Viewer, Neustart, Konflikt und Reconnect |
| **Regelwerk-/Automationsintegration** | B.3 OFF/MANUAL/GM_APPROVAL/AUTOMATIC, erlaubte Exceptions; R1 numerische passende Checks und R2 andere zulässige Pools/Symbole ohne globale W20-/Klassen-/HP-Pflicht |
| **Node-/NPC-/Combat-/Inventory-/Quest-Integration** | Jeder betroffen zuständige Fachowner, getrennte ActionProposal-/DomainCommand-/WorldCommit-Rechte und kein mehrfacher Roll-/Quest-/Item-/Traktor-Effekt |
| **UI-/Editor-/Media-/Chat-Anschluss** | Einheitliche semantische 13.x-Rechte und B.5-/B.6-/12.x-Projektionen, editierte Drafts ≠ Publish ≠ LiveWorldAction; 02.118 A weiterhin keine gespeicherten ungesendeten ChatDrafts |
| **Release-Abnahme** | Echte 14.8-isolierte Referenzkampagne, zwölf B.8-Gates, zwei unterschiedlich strukturierte B.9-RulePacks, umfassende B.2-B-Fachbreite und separate 14.6-/15.4-Freigabe |

Diese Tabelle ordnet **Arten** künftiger Aufträge, keine verbindliche Implementierungsreihenfolge und keine Behauptung abgeschlossener Arbeit. Optionales Audio, freie Dritt-Plugin-Laufzeit oder fein ausgebauter Charakterersteller bleiben gemäß bisherigen Beschlüssen als späterer Umfang vorbereitet, soweit nicht für die konkrete erste B.2-B-Spielbreite verpflichtend.

## 5. Abnahme- und Negativfälle für die Auftragssteuerung

- **Auftrag ohne Source-/History-/Actor-Negativtest:** Nicht READY oder VERIFIED, solange betroffene Zugriffsrechte offen sind.
- **Zwei Module führen denselben WorldEffect aus:** B.4/B.14-Ownergrenze verletzt, Arbeit gesperrt; keine zweite WorldEngine zulassen.
- **„Fertig“ trotz nur Mock-/UI-Demo:** Nicht VERIFIED; B.13-Integration benötigt reale aktuelle Authorization/World-/OriginalReceipt-/Browsernachweise.
- **Test grün, aber falsche RulePack-Annahme:** R2-/B.9-Lücke als FAIL/BLOCKED kennzeichnen; nicht alle Regeln auf W20-/HP-/Fantasystruktur zwingen.
- **Produktionsupgrade verändert Kampagnenpins/Charakterstände still:** Verboten; B.14-/14.6-/15.2-Kontrollen und autorisierte Fach-/WorldMigration separat.
- **Offene Operation und Browser-Ack verloren:** OriginalOperationReceipt abgleichen; kein automatisch erneutes Würfeln, Node-/Quest-/Traktorereignis oder neues OriginalOperationId-Replay.
- **Neuer Auftrag setzt inaktiviertes Modul voraus:** Blockiert oder unter tatsächlich erlaubtem manuellem Verfahren; kein stilles Aktivieren.
- **Sicherheitsfix oder Änderung erzeugt Vertragsbruch:** B.14-Revisions-/Consumerprüfung und gezielte Revoke-/Deployment-/Recovery-Kontrolle, keine allgemeine Ausnahme von Auth und Privacy.
- **V1-Plan deckt zwar alle Aufträge ab, aber integrierte B.8-End-to-End-Gates fehlen:** Keine erste Spielreleasefreigabe.
- **Historisch abgewählte Option erscheint durch Implementierungsbequemlichkeit wieder:** Beschlusskollision offen kennzeichnen, nicht als erledigtes Arbeitspaket verschleiern.
- **Verifizierter Auftrag ohne tatsächlich dokumentierten Testlauf/Build:** Status zurück auf prüfbedürftig, bis Evidenz reproduzierbar vorliegt.

## 6. Bewusst später und ausdrücklich nicht durch B.15 bewirkt

Konkrete Aufgaben-IDs, Team-/Reviewerrollen, Statusanzeige, Git-Projektstruktur, CI-/Issue-/Ticket-/Dashboardtools, Testsprachen, Feldformate, UI-Defaults, Aufwandsschätzungen und Zeitpläne werden erst bei realem Entwicklungsbeginn festgelegt. Diese B.15-Planung führt **keine** echte B.11-Probe aus, wählt keinen Stack, implementiert keinen Code, erstellt keine laufende Kampagne, vergibt keine GM-/Actor-/Hostberechtigung und verändert keine World-, Roll-, Quest-, Item-, NPC-, Character- oder Traktorwirkung.

## 7. Historische Anschlussfrage B.16 (inzwischen C beschlossen)

### B.16 – Was geschieht, wenn während der Implementierung bisher übersehene Widersprüche oder technisch nicht tragfähige Fachannahmen entdeckt werden?

- **A – Umsetzende Entwickler entscheiden je Aufgabe nach eigenem Ermessen:** Schnell, aber Beschlüsse, Rechte und Module können unbemerkt auseinanderlaufen; wenig nachvollziehbare Abweichungen.
- **B – Bei jeder offenen Einzelheit die gesamte Entwicklung einfrieren, bis alles vollständig neu geplant ist:** Verhindert spontane Abweichungen, macht aber risikoarmes Weiterarbeiten an unabhängigen Bereichen unverhältnismäßig schwer.
- **C – Gezielter Konflikt-/Abweichungsnachweis mit sicherem Blocker, maßgeblicher Fachentscheidung und B.14-Änderungsprüfung (Empfehlung):** Betroffenen Entwicklungspfad begrenzt sperren, Ursache, bestehende Beschlüsse, Auswirkungen, zulässige Lösungsvarianten und Tests offen dokumentieren; echte sicherheits-/fachkritische Abweichungen erst nach gesonderter berechtigter Entscheidung und versioniertem Contract-/Migration-/Release-Recheck zulassen. Unabhängige sichere Arbeit darf weitergehen. Keine stillen Anforderungenänderungen, keine zweite World-/Regelengine und keine ungeprüfte produktive Freigabe.
