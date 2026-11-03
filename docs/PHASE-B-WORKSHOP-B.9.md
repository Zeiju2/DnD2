# AdventureShift – Phase B, Beschluss B.9 C: regelwerksneutrale Referenz-RulePacks mit unabhängigen Kompatibilitätsfällen

**Nachfolgender Beschluss B.10 C (03.11.2026):** [Architekturgebundene gemeinsame VPS-/Browser-/DB-/Realtime-/Rule-/Media-/Deploymententscheidung mit begrenzten isolierten Risikoprüfungen und versionierten ADRs](PHASE-B-WORKSHOP-B.10.md) wird vor konkreter Stackfestlegung berücksichtigt. B.9-R1/R2-Testregeln und ursprüngliche World-/GM-/Actor-/Source-/Secret-/Version-/Release-Rechte bleiben unverändert. **B.11 folgt: priorisierte technische Risikoprobe.**

**Stand:** 03.11.2026. **B.9 C vom Projektinhaber ausdrücklich beschlossen.**
**Status:** Verbindliche Fach-/Architekturentscheidung mit Test-, Rechte-, Lizenz-, Versions- und Umsetzungsgrenzen. **Noch keine implementierte Software**, keine erstellten lauffähigen RulePacks, keine ausgeführten Konformitätstests und keine Freigabe von Drittanbieterregelwerken.
**Kernentscheidung:** Mindestens **zwei bewusst strukturell verschiedene, versionierte und rechtmäßig selbst erstellte Referenz-RulePacks** prüfen vor dem ersten B.2-B-Spielrelease dieselben fachlichen Vertragsgrenzen, ohne dass ein Fantasy-/W20-/HP-/Klassen-/Initiativmodell im Kern verpflichtend wird. Beide müssen in der [B.8-C-Gesamtabnahme](PHASE-B-WORKSHOP-B.8.md) und in eigenen kontrastierenden Fachtests echte, autorisierte VPS-Aktionen und richtige Viewerprojektionen nachweisen.
**V1-Grenzen:** Eigener VPS, Spielleiter und Spieler in getrennten Browsern, genau **ein aktiver Spielleiter** je produktiver Kampagne und genau **eine kanonische CampaignWorld**; keine zweite RuleEngine, kein frei ausführbares RulePack-Scripting, keine pauschale fremde Asset-/Regel-/GM-/PlayerDM-Nutzung.
**Phase-B-Bezüge:** [B.1 C – inkrementelle Entwicklung](PHASE-B-WORKSHOP-B.1.md) · [B.2 B – breiter erster Spielrelease](PHASE-B-WORKSHOP-B.2.md) · [B.3 C – deklarative Module/Capabilities/VersionPins](PHASE-B-WORKSHOP-B.3.md) · [B.4 C – gemeinsame Fachowner/Commands/Events](PHASE-B-WORKSHOP-B.4.md) · [B.5 C – viewergefilterte Snapshots/Deltas](PHASE-B-WORKSHOP-B.5.md) · [B.6 C – aktuelles rechtmäßiges Vorladen](PHASE-B-WORKSHOP-B.6.md) · [B.7 C – Offline-Entwürfe/OriginalReceipts](PHASE-B-WORKSHOP-B.7.md) · [B.8 C – Referenzkampagne/G1–G12](PHASE-B-WORKSHOP-B.8.md).
**Weitere Bezüge:** [Planungsstandard](PLANUNGSSTANDARD.md) · [02.63/02.64 konkrete numerische Checks und zwei Rohwürfe bei Vorteil/Nachteil](KARTEN-WORKSHOP.md) · [03.1 Charaktervorlagen](CHARAKTER-WORKSHOP-03.1.md) · [03.2 Actor-/ControlGrants](CHARAKTER-WORKSHOP-03.2.md) · [03.3 Draft/Publish und optionale Charaktererstellung](CHARAKTER-WORKSHOP-03.3.md) · [03.4 Klassen, Skills und Fähigkeiten als optionale Konfiguration](CHARAKTER-WORKSHOP-03.4.md) · [03.7 eigene/mitgelieferte RulePacks](CHARAKTER-WORKSHOP-03.7.md) · [04.1 Bewegung und erlaubte Moduswechsel](BEWEGUNG-WORKSHOP-04.1.md) · [05.1 numerische, Pool- und Symbolwürfel](WUERFEL-WORKSHOP-05.1.md) · [05.2 manuelle, genehmigte und automatische Würfel](WUERFEL-WORKSHOP-05.2.md) · [05.3 optionale sichere Wurfketten](WUERFEL-WORKSHOP-05.3.md) · [06.4 NPC-Verhalten](NPC-WORKSHOP-06.4.md) · [07.1 Konfliktkontext](KAMPF-WORKSHOP-07.1.md) · [07.2 Teams/Initiative](KAMPF-WORKSHOP-07.2.md) · [07.3 Aktionsbudgets/Reaktionen](KAMPF-WORKSHOP-07.3.md) · [07.4 regelgebundene Kampfresultate](KAMPF-WORKSHOP-07.4.md) · [10.4 Quest-/Rewardfolgen](JOURNAL-WORKSHOP-10.4.md) · [15.2 kampagnenbezogene VersionPins](ERWEITERUNGEN-WORKSHOP-15.2.md) · [15.4 produktiv nur echte Releases](ERWEITERUNGEN-WORKSHOP-15.4.md) · [Lizenz-/Urheberrechtsplanung](LIZENZEN.md).

## 1. Verbindliche Entscheidung – Variante C

AdventureShift definiert **eine einzige regelwerksneutrale, serverautoritativ ausführbare Typ-/Capability-/Action-/Result-/Roll-/Effect-Schnittstellenfamilie**. Ein RulePack liefert nur gültige deklarative Definitionen und Regelverträge: welche Attribute und Proben es gibt, welche Würfelarten, Erfolgsauswertungen, Ressourcen, Aktionsfenster, Konflikt-/Initiativ-/NPC-/QuestPolicies und Ableitungen im jeweiligen System gelten. Das Paket ist nicht berechtigt, Eigenlogik als beliebigen JavaScript-/Python-/SQL-/Root-/Datenbank-/WorldWriter-Code auszuführen.

**Mindestens zwei absichtlich unterschiedliche eigene Referenzpakete** werden als eigenständige testbare Definitionen vorgesehen. Ihre Abweichungen müssen echte Architekturkonflikte aufdecken: numerischer Einzelwurf vs. Pool-/geeignetes Symbolergebnis, alternative Ressourcen-/Turn-/Initiativmodelle, verschiedene Charakter-/Fähigkeits-/Quest-/Inventarregeln. Ein einziger Test mit anderem Waffennamen oder anderem HP-Wert ist **kein** ausreichender zweiter Regelwerksnachweis.

**Bestehende 02.63/02.64-Entscheidungen bleiben gültig:** Der konkret bereits beschlossene numerische Skillcheck (echter Wurf plus Skill gegen Mindestwurf; Gleichstand ist Erfolg) und die definierte Zwei-Rohwürfe-Vorteil-/Nachteilmechanik gelten **für diesen ausdrücklich gewählten Checktyp**. Sie sind keine Pflicht, jeden Pool-, Symbol- oder anderweitig geeigneten RollTyp nachträglich zu einer numerischen W20-Probe umzudeuten. Ein RulePack wählt ausschließlich zulässige vorhandene getypte Probenarten.

**Kein offenes Versprechen beliebiger Fremdregelwerke:** B.9 C sagt nicht, dass schon im ersten Produktrelease alle Pen-&-Paper-Systeme vollständig abgedeckt sind. Konkrete auslieferbare Schnellstartpakete, urheberrechtliche Freigaben und unterstützte Sondermechaniken sind gesondert zu spezifizieren und zu implementieren. Die hier geforderten Referenzpakete sind **Testdefinitionen**, keine bereits ausgelieferten oder veröffentlichten Produktfeatures.

**Nicht gewählt:** A – eine einzelne fest eingebrannte Fantasy-/W20-Regel als technische Allgemeinlogik. B – alle existierenden, teilweise rechtlich geschützten Regelwerke vollständig vorab implementieren.

## 2. Zwei bewusst verschiedene Referenz-RulePacks (fachliche Beispiele, keine fertig definierten Werte)

| Prüfmerkmal | Referenzprofil R1: numerische Probe | Referenzprofil R2: Pool-/Symbolprobe |
|---|---|---|
| Ursprung/Lizenz | Eigene synthetische Testdefinition und eigene sichere Medien | Andere, ebenfalls eigene synthetische Testdefinition |
| Charakterwerte | Beliebig typisierte Basis-/Skill-/Optionalklassen und deklarative abgeleitete Werte | Andere Attribut-/Ressourcen-/Fähigkeitsstruktur, **keine Pflichtklasse** |
| Würfel/Check | Tatsächlich servergenerierter numerischer Wurf und ggf. 02.63-/02.64-CheckKind | Tatsächlich servergenerierter Pool oder geeignete Symbolergebnistypen nach 05.1; eigener typisierter Resolver |
| Erfolg | Für gewählten numerischen CheckKind: Wurf + Skill ≥ definierter Mindestwurf | Je R2 deklarativ typisierte Erfolge/Kosten/Sondereffekte, kein impliziter numerischer 02.63-Mindestwurf |
| Turn/Initiative | Konfigurierbare 07.2-Turn-/Prioritäts-/Aktionsregeln | Strukturell abweichende erlaubte Reihenfolge, Ressourcen und ggf. Reaktionsfenster |
| Kampf/Status | Passende getypte Ressourcen-/Result-/Statuswerte, **HP nicht als globale Enginepflicht** | Anderes zulässiges Stress-/Zustands-/Ressourcenmodell ohne Zwang zu R1-HP |
| NPC/Node | R1-Regel-/Roll-/Actor-/Questprüfungen über identische 06-/02.99-Originalowner | R2-Regel-/Roll-/Actor-/Questprüfungen über **dieselben** Fachownerschnittstellen |
| Inventar/Quest | Berechtigte R1-Item-/Objective-/RewardWorldEffects | Anders konfigurierte erlaubte Bedingungen/Ressourcen, unveränderte 14.12-WorldTransaktion |
| Viewer/Geheimnisse | R1-SecretRoll-/Fog-/GM-/History-/MediaACL | Dieselben unveränderlichen Schutzgrenzen auch bei anderen Resulttypen |
| Ergebnis | Echte OriginalOperationReceipts und Replay-/Reconnectschutz | Echte OriginalOperationReceipts und Replay-/Reconnectschutz |

**R1/R2 sind Prüfachsen, keine bestätigten Spielsysteme, veröffentlichte RulePack-Namen oder endgültigen Formeln.** Beide müssen außerdem die jeweils im Fachkatalog zulässige manuelle, SL-bestätigte und automatische Ausführung prüfen. Ein nicht aktives Kampf-/NPC-/Questmodul darf keinen versteckten Regelzwang erzeugen.

## 3. Fachobjekte, Versionen und Autoritätsgrenzen (Arbeitsnamen)

1. **RulePackDefinition / RulePackId / ImmutableRuleRevision:** Eigenständige stabile Definition mit Source-/Owner-/Attribution-/License-/Scope-/StableRelease-/TestOnly-Status; gespeichert ≠ freigegeben ≠ im CampaignWorld-State angewendet.
2. **RuleCapabilityManifest / DependencyLock / RuleVersionPin:** B.3-C-typisierte benötigte Rollen, Module, CheckKinds, Konflikt-/Turn-/Inventar-/QuestPorts und stabile Versionen; keine automatische Aktualisierung bei neuem Bibliotheksrelease.
3. **RuleSchema / CharacterValueKind / AttributeDefinition:** Getypte generische Werte/Constraints statt verpflichtenden Klassennamen, HP-/XP-Feld oder fest verdrahteten W20-Zahlen. Optionale Klassen-/Fähigkeits-/Punkteverteilung bleibt nach 03.3/03.4 möglich.
4. **RollKind / DiceProfile / PoolProfile / SymbolProfile:** Nur von 05.1/05.2/05.3 tatsächlich definierte, serverautoritativ gezogene und ausgewertete passende Würfeltypen. Rohwerte, SecretScopes und OriginalRollRecords können nicht im RulePack, Plugin oder Browser erfunden werden.
5. **CheckDefinition / ComparisonSemantics / SuccessOutcomeKind:** Regelgebundene getypte Eingaben/Ausgaben. Das konkrete 02.63-NumericSkillCheckKind behält Mindestwurf/Gleichstand und 02.64-Vorteil/Nachteil. Andere zulässige CheckKinds haben eigene geprüfte Resulttypverträge.
6. **DerivedValueExpression / TypedInputRef / EvaluationBound:** Endlich begrenzte deklarative Berechnung aus aktuellen legitimen 03.7-Werten/Ressourcen/Status/Equipment; keine unbeschränkten Formelskripte, keine Clientautorität.
7. **TurnPolicy / InitiativePolicy / ReactionPolicy / ResourceBudget:** 07.1–07.5-/02-Turn-Autorität mit rulegebundenem Reihenfolge-/Kosten-/Reaktionsvertrag; keine zweite R1-/R2-TurnEngine und keine universelle Initiativeformel.
8. **ActorControlPolicy / CharacterOrNpcCapability:** Tatsächliche 03.2-/06-Owner-/ControlGrant-/Rule-/Scene-/Member-/GM-Rechte bleiben unabhängig vom gewählten Profil; neue Fähigkeiten sind keine neue Rechtequelle.
9. **RuleWorldEffectIntent / DomainActionKind / ExpectedRevision:** Regelresultat ist vor 02.99-/14.12-Authorisierung allenfalls Proposal. Nur gültiger OriginalDomainOwner/14.13-WorldWriter committed Item-/Quest-/Door-/Conflict-/Turn-/Npc-/Movement-Effekte.
10. **RuleResult / RollReceipt / OriginalOperationReceipt / CausationId:** Typisierte, nachweisbar echte Outcomes und Kausalketten; doppelte HTTP-/WS-/Workeranfragen erzeugen keine zusätzlichen Würfe oder Belohnungen, auch wenn R1 und R2 verschiedene Ergebnisse haben.
11. **RuleVisibilityPolicy / SourceAudience / HistoricalAudience / PrivacyFence:** Wurf-/NPC-/Quest-/GM-/PlayerSecret-/Asset-/Fog-/Historyschutz wird **nicht** durch RulePackwahl ausgeschaltet. PlayerViews bekommen nur aktuelle rechtmäßige B.5-C-Projektionen, B.6-C-Prefetch nur erlaubte Quellen.
12. **RuleTestFixture / VariantConformanceCase / EvidenceReceipt:** B.8-C-versionierte erlaubte und verweigerte R1-/R2-Testschritte mit reproduzierbarer FixtureVersion, echten Browser-/VPS-/World-/Resultbelegen und separater TestOnly-RNG-Isolation.
13. **CompatibilityRevision / RuleMigrationIntent / PinUpdateReceipt:** Regel-/Formel-/Konfigurationskompatibilität nach 03.6/14.6/15.2; Wechsel oder Update verändert weder Charaktere noch laufende Quests, Items oder WorldHistory ohne aktuelle autorisierte Fachmigration.
14. **RuleBudget / QuotaScope / ExecutionFence:** Begrenzte Pools, Formeln, Folgechecks, Node-/NPC-/Combat-Rekursion, Ressourcen und WorkerBudgets; keine unbegrenzte Fanout-/Exploit-Ausführung unter neuen RulePaketen.
15. **RulePackagePublication / LibraryReleaseAuthority / BetaOnlyTest:** Erst wirklich berechtigte veröffentlichte StableRelease-Versionen produktiv auswählbar; Beta/TestOnly ausschließlich in 08.3-/14.8-isolierten Tests, keine Test-Worlds oder fremden Medien in Produktivkonten.
16. **LicenseProvenance / OriginalDefinitionRights / RedistributionEligibility:** Eigene originäre Beispieltexte/Mechaniken/Medien klar dokumentieren. Für konkrete Fremdregelwerke oder geschützte Bestandteile Nutzungs-/Weitergabe-/Bearbeitungs-/Attributions-/Lizenzrechte **je Version** prüfen; keine bloße Deklaration von „Open“ als Nachweis.

## 4. Verbindlicher Konformitäts- und Abnahmepfad

1. **Zwei strukturverschiedene Testdefinitionen:** R1 und R2 unter getrennten DefinitionIds/ImmutableRevisions mit dokumentierten Unterschieden; Synthetik/TestOnly-Provenienz und erlaubte TestAssets. Keine Kopien geschützter Spielregelbuchtexte als Testabkürzung.
2. **Gemeinsamer Rule-Validator:** Beide Profile laufen durch **denselben** B.3-C-Capability-/DependencyResolver, dieselben B.4-C-Command-/Event-/ResultKinds und denselben serverseitigen OriginalOwner-/WorldWriterpfad; keine pro Testprofil geschriebene zweite Engine.
3. **Roll- und Character-Konformität:** R1 prüft die bereits beschlossene 02.63-/02.64-Semantik im richtigen CheckKind; R2 prüft eigene geeignete 05.1-Pool-/SymbolKinds. Für beide bleiben echte ServerRollRecords und passende Actor-/GM-/Historyrechte verbindlich.
4. **Turn/Kampf/NPC-Konformität:** Je Profil eigene gültige Initiative-, Budget-, Reaktions-, NPC-/Konflikt- und Wirkungskonfiguration. Kein universeller HP-/Klassen-/XP-/W20-Zwang im gemeinsamen Speicher oder der UI-Projektion.
5. **CrossModule-Weltfolgen:** In beiden Profilen mindestens eine tatsächlich autorisierte Node-/NPC-/Combat-/Inventory-/Quest-Kausalkette mit genau einer 14.12-WorldTransaction pro Originaloperation und passender OriginalReceipt-/CrossStoreOutbox-Semantik; fehlende Module blockieren betroffene Automatik sicher.
6. **Geheimnisse/Viewer:** Bei R1 und R2 private NPC-/Quest-/GM-/PlayerDaten, geheime RollResults, unbekannte Fog-/History-/MediaSources gegen Player-/GM-/Preview-/Support-/RevokedSession prüfen. Keine Offenlegung über andere Wurf-/Resulttypen.
7. **Sichere Änderung und Reconnect:** Rule-/CampaignVersionPins bleiben stabil; Schema-/Rule-/Asset-/Licenseupdates, BrowserReconnect, OfflineDrafts, Dedupe und Restore dürfen nicht unkontrolliert neue Würfel/Weltaktionen/Charaktermigrationen verursachen.
8. **Freigabe-Gates:** R1-/R2-Konformität ist ein **zusätzlicher Pflichtnachweis** innerhalb des echten B.8-C-Gates für den konkreten B.2-B-Release. Grüne Einzeltests, Mock-Würfel oder zwei dekorative Template-Namen reichen nicht. Beide sollen ohne verpflichtenden externen Cloudserver auf dem eigenen VPS funktionieren.

## 5. Negative Konformitätsfälle

| Testfall | Erwartetes Ergebnis |
|---|---|
| R2-Regel nutzt Pool/Symbole, aber Implementierung verlangt W20 + HP | Fehlende Regelwerksneutralität: **Gate nicht bestanden** |
| R1 verwendet explizites 02.63-NumericSkillCheckKind | Echte Rohwürfe; Skill + Wurf ≥ Mindestwurf einschließlich Gleichstand; 02.64-Semantik im passenden erlaubten Advantage/Disadvantage-Kontext |
| R2 verwendet anderes zulässiges 05.1-CheckKind | Kein heimlicher R1-Mindestwurf oder R1-Vorteil/Nachteilzwang; korrekt typisiertes Result |
| R2 braucht andere Turn-/Initiativefolge | Ein original 02-/07-TurnController, keine zweite RulePack-/NPC-WorldEngine |
| RulePack lässt Klasse/HP/XP weg | Wenn im gewählten Profil optional, keine künstliche Pflichtspalte/Default oder UI-/DB-Verweigerung |
| Profil fordert nicht unterstützte Würfel-/ResultKind | Typisierter CompatibilityReject; keine zufällige W20-Ersatzsemantik |
| Zwei Regelversionen laufen in getrennten Kampagnen | Stabile CampaignPins, eindeutige OwnerScopes, keine Datenvermischung |
| Neue veröffentlichte Profilversion erscheint | Kein automatischer Rule-/Character-/Quest-/WorldMigrationscommit |
| Test-/Beta-Profil wird im regulären Produktivkatalog angezeigt | Ablehnung nach 15.4, kein stilles Beta→Stable |
| R1-/R2-NPC-Node möchte gegnerischen Actor oder private GM-/Player-Quelle auslesen | Heutige ACL/Source-/History-/Fog-/Actorprüfung; keine Secret- oder Metadatenlecks |
| Browser liefert eigene angebliche Würfelrohwerte | Kein zulässiger 05.1-RollRecord oder OriginalWorldCommit |
| Roll-/Quest-/Item-/Turn-Request wird doppelt zugestellt | Gleiches OriginalOperationReceipt statt doppelter Wirkung |
| Ungeeignete Formel oder endloser Triggergraph | Zentrale Typ-/Kompatibilitäts-/Quota-/CycleFence, keine Freicodeausführung |
| Testprofil importiert fremde Bilder oder geschützte Regeltexte ohne Rechte | Keine automatische Paketfreigabe/Weitergabe; rechtmäßige Version-/Sourceprüfung nötig |
| Nur R1 ist nachweisbar funktionstüchtig | **B.9-C-Regelneutralitätsgate nicht bestanden**, selbst wenn R1 viele UnitTests besteht |

## 6. Entwicklungsfolge und Geltungsgrenze

**Schrittfolge:** (1) deklarative gemeinsame RulePack-/Check-/Roll-/Turn-/Result-/EffectContracttypen; (2) R1 und R2 als sauber getrennte synthetische Testfixtures; (3) B.3-Dependency-/Version-/RuleValidator; (4) echte R1- und R2-ServerRoll-/Character-/Turn-/Combat-/NPC-/Node-/Inventory-/Quest-/WorldIntegrationen; (5) B.5-/B.6-/B.7-Viewer-/Reconnect-/Offline-/MediaRights-Negativtests; (6) B.8-End-to-End-Evidence und ReleaseGate für genau diese Build-/Rule-/Schema-Versionen.

**Jetzt entschieden:** Mindestens **zwei wirklich verschiedenartige, rechtmäßig eigenständig konstruierte und versionierte Test-Regelkonfigurationen** mit gemeinsamen OriginOwner-/Server-/WorldWriter-/Viewer-/Security-/Roll-/Quest-Verträgen sind für die erste umfassend spielbare Version nachweisbar kompatibel zu machen. **Kein** allumfassendes D20-/Fantasy-/Klassen-/HP-/XP-/Initiative-Pflichtmodell und **keine** unerlaubten Drittinhalte.

**Später festzulegen:** endgültige Texte, Namen, Werte, konkrete Würfelpool-/Symbolspezifikationen, zu unterstützende echte Systeme, Starterprofile, Verteil-/Lizenzverträge, UI, API/DB, Rechenalgorithmen, Kompatibilitätsmatrix und konkrete Testwerkzeuge. Diese Detailoffenheit darf die fachlichen Architektur- und Schutzgrenzen nicht rückwirkend ändern.

### B.10 – Wie legen wir den technischen Implementierungsstack vor der Programmierung fest?

**Historische Entscheidungsfrage: B.10 C wurde ausdrücklich beschlossen; maßgeblich ist [B.10-C-Fachplanung](PHASE-B-WORKSHOP-B.10.md).**

- **A – Sofort einen vollständigen Stack ohne technische Gegenprobe festschreiben:** Backend, Datenbank, Browserframework, Realtime, Storage und Deployment werden jetzt endgültig ausgewählt, selbst wenn VPS-/Auth-/Transaktions-/Sicherheitsfragen noch nicht praktisch validiert sind.
- **B – Jedes Modul wählt seinen eigenen Stack unabhängig:** Schnelle Einzelentscheidungen, aber riskante Brüche bei WorldWriter, RuleEngine, ACL, DomainStore, UI- und Betriebs-Schnittstellen.
- **C – Architekturgebundene Technologieentscheidung mit begrenzten Risikoprüfungen (Empfehlung):** Ein kohärenter Single-VPS-/Browser-Stack wird anhand der verbindlichen B.1–B.9-, 14.12/14.13- und Sicherheitsanforderungen verglichen. Vor der irreversiblen Wahl werden nur kritische Fragen mit isolierten, nicht als spielbar freigegebenen Technikproben validiert. Versionierte Architekturentscheidungen mit Begründung, Risiken, Lizenz-/Betriebsfolgen und Kompatibilität führen zu einer gemeinsamen technischen Basis; konkrete Framework-/DB-/UI-/CI-Auswahl dann anhand dieser Nachweise. Kein getrenntes Techniksystem je Modul.
