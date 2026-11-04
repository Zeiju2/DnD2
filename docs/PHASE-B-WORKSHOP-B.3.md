# AdventureShift – Phase B, Beschluss B.3 C: zentral geprüfte Kampagnenmodule und Automatisierung

**Nachfolgender Beschluss B.12 C (04.11.2026):** [Selektive Übernahme nur nach tatsächlichem Spike-Nachweis, Produktionshärtung, Security-/Source-/Owner-/Lizenz-/Auth-/Service-/Migration-/Backup-/Testreviews und erneuten Integrationsprüfungen](PHASE-B-WORKSHOP-B.12.md). Geeignete Komponenten dürfen in die gemeinsame Entwicklungsbasis, ungeeignete Teile werden ersetzt; **keine unveränderte Spike-Übernahme, keine TestOnly-/FakeAuth-/AllRead-Pfade in Produktion, keine automatische Stack-, Kampagnen- oder Releasefreigabe.** B.11 bleibt **geplant, nicht ausgeführt**; B.2-B-Spielrelease und B.8-/B.9-Gesamtgates bleiben Pflicht. **Nächste Grundfrage B.13: Integrationsreihenfolge der Fachmodule.**

**Nachfolgender Beschluss B.11 C (04.11.2026):** [Erste isolierte echte GM-/Player-/SingleWorld-/WorldTransaction-/OriginalOperationReceipt-/Revoke-/Reconnect-Risikoprobe](PHASE-B-WORKSHOP-B.11.md). Noch **kein** Prototyp ausgeführt, kein Techstack final gewählt und keine B.2-B-Spielbarkeit freigegeben; B.1–B.10 samt Sicherheitsrechten unverändert. **Nächste Grundfrage B.12: Code des Spikes kontrolliert weiterverwenden oder ersetzen.**

**Nachfolgender Beschluss B.10 C (03.11.2026):** [Gemeinsame architekturgebundene Technologieentscheidung mit begrenzten isolierten Risikoproben und versionierten ADRs](PHASE-B-WORKSHOP-B.10.md); bestehende SingleVPS-/WorldWriter-/GM-/Source-/Privacy-/Rule-/Asset-/Releasegrenzen bleiben maßgeblich. Es wurde **noch kein** Framework, Datenbanksystem oder echter Technik-Spike ausgewählt/ausgeführt. **B.11 C inzwischen beschlossen; nächste Frage B.12.**

**Nachfolgender Beschluss B.9 C (03.11.2026):** [Zwei rechtmäßig eigens konstruierte verschiedenartige RulePack-/Roll-/Turn-/Ressourcen-Referenzfälle](PHASE-B-WORKSHOP-B.9.md) sind im B.8-Gesamt-Releasegate zu prüfen. Ein passender numerischer 02.63-/02.64-Check und ein andersartiger 05.1-Pool-/SymbolCheck nutzen denselben B.3–B.8-/14.12-/14.13-Fachowner-/WorldWriter-/ACL-/OriginalReceiptvertrag; keine universelle Fantasy-/W20-/HP-/Klassenpflicht. **B.10 C inzwischen beschlossen; B.11 ist die nächste Grundfrage.**

**Nachfolgender Beschluss B.8 C (03.11.2026):** [Reproduzierbare 14.8-isolierte genreunabhängige Referenzkampagne und B.2-B-Gesamtfreigabe-Gates](PHASE-B-WORKSHOP-B.8.md) mit echten getrennten Browsern, B.3–B.7-Fach-/Source-/Privacy-/WorldWriter-/OriginalReceipt-/Reconnect-/Backup-Nachweisen und Negativfällen. Kein Green-CI-/Mock-Ersatz für echte integrierte Spielbarkeit. **B.9 C inzwischen beschlossen; B.10 ist die nächste Grundfrage.**

**Nachfolgender Beschluss B.4 C (03.11.2026):** [Einheitliche versionierte typisierte Fachowner-/Ref-/Command-/Event-/Result-/OriginalReceipt-/ACL-Verträge](PHASE-B-WORKSHOP-B.4.md) ohne ShadowWorld, ShadowInventory, ShadowQuest oder direkten Modul-WorldWrite. B.3 C bleibt der Konfigurations-/Automationvertrag, 14.12/14.13 der WorldCommit-/SingleWriter-Vertrag. **B.5 C nachfolgend beschlossen:** [viewerbezogener Projection-/Realtime-/Reconnect-Vertrag](PHASE-B-WORKSHOP-B.5.md). **B.6 C nachfolgend beschlossen:** [per Viewer/Capability freigegebene Stage-0–4-Medien und CacheScopes](PHASE-B-WORKSHOP-B.6.md). **B.7 C nachfolgend beschlossen:** [Offline nur mit erneuter aktueller B.3-Policy-Fachprüfung](PHASE-B-WORKSHOP-B.7.md). **B.8 C inzwischen beschlossen; nächste Grundfrage B.9 – RulePack-Konformität und Genreunabhängigkeit.**

**Stand:** 03.11.2026. **B.3 C vom Projektinhaber ausdrücklich beschlossen.**
**Status:** Verbindliche fachliche Grundstruktur und Umsetzungs-/Abnahmetestplan; **keine Softwareimplementierung**, kein endgültiger UI-, API-, DB- oder Techstackbeschluss.
**Geltung:** Kampagnenspezifische, versionierte RulePack-/Modul-/Automationskonfiguration mit geprüften Dependencies und zulässigen Szenen-/Gruppen-/Figuren-/Aktionsausnahmen. Keine stillen Weltwirkungen.
**Unverändert:** [B.1 C – inkrementelle Entwicklung](PHASE-B-WORKSHOP-B.1.md) und [B.2 B – breit automatisierter erster spielbarer Release](PHASE-B-WORKSHOP-B.2.md). V1 eigener VPS, getrennte SL-/Spielerbrowser, **genau ein aktiver SL** und **genau eine kanonische CampaignWorld** je Kampagne.
**Bezüge:** [Planungsstandard](PLANUNGSSTANDARD.md) · [02.25 Kampagnenstandards/Ausnahmen; 02.48 optionale Features; Nodes](KARTEN-WORKSHOP.md) · [02.99 WorldActions](KARTEN-WORKSHOP-02.99.md) · [03.2 Actor-Control](CHARAKTER-WORKSHOP-03.2.md) · [03.7 RulePacks](CHARAKTER-WORKSHOP-03.7.md) · [04.1 Bewegung](BEWEGUNG-WORKSHOP-04.1.md) · [05.2 Würfelsteuerung](WUERFEL-WORKSHOP-05.2.md) · [06.4 NPC-Handlungen](NPC-WORKSHOP-06.4.md) · [07.3 Kampfaktionen](KAMPF-WORKSHOP-07.3.md) · [08.3 Draft/Test/Publish/Live](SL-WERKZEUGE-WORKSHOP-08.3.md) · [09.7 aktive GM-Autorität](KAMPAGNEN-WORKSHOP-09.7.md) · [09.9 eine World](KAMPAGNEN-WORKSHOP-09.9.md) · [10.4 Questfolgen](JOURNAL-WORKSHOP-10.4.md) · [12.7 Quotas](ASSETS-WORKSHOP-12.7.md) · [13.3 ActionReceipts](UI-WORKSHOP-13.3.md) · [14.8 Testisolierung](SICHERHEIT-WORKSHOP-14.8.md) · [14.12 Domain-/WorldTransactions](SICHERHEIT-WORKSHOP-14.12.md) · [14.13 WorldWriter](SICHERHEIT-WORKSHOP-14.13.md) · [15.2 Kampagnen-Pins](ERWEITERUNGEN-WORKSHOP-15.2.md) · [15.4 Release/Beta](ERWEITERUNGEN-WORKSHOP-15.4.md).

## 1. Verbindlicher Fachbeschluss – Variante C

Jede Kampagne erhält **eine verbindliche, versionierte, zentral aufgelöste Konfiguration** für aktivierte Module, konkrete zulässige Releases, RulePacks, Automationsfähigkeiten und deren Abhängigkeiten. Ein zentraler **deklarativer Validator** weist fehlende, unvereinbare, zyklische oder unberechtigte Kombinationen vor tatsächlicher Aktivierung nachweisbar zurück. Er ist **keine zweite Regel-/Action-/WorldWriter-Engine**.

**Automationsstufen:** Pro geeigneter Fachaktion kann – soweit der jeweilige Fachvertrag es zulässt – deaktiviert, manuell, SL-bestätigt oder regelautomatisch gewählt werden. Bereits geplante Kampagnenstandards und explizit zulässige Ausnahmen für Szene, Gruppe, Figur, NPC, Node oder einzelne Action werden über einen einzigen nachvollziehbaren Policy-Auflösungsvertrag geprüft. **Nicht jede Stufe ist in jeder Fachdomäne zulässig.**

**Sicherheitsregeln bleiben Pflicht:** Steam-/Account-/Session-/Campaign-/GM-/Actor-/Owner-/Source-/Fog-/HistoricalAudience-/Asset-/License-/Privacy-/Quota-/WorldWriter-/OriginalOperationReceipt-/Backup- und Auditgrenzen dürfen **niemals** über einen Modulschalter, eine Vorlage oder Ausnahme deaktiviert oder erweitert werden. Ein SL besitzt deshalb nicht automatisch fremde private Chat-/Notizrechte; eine Vorlagenaktivierung gewährt weder Host-/Support-/Key-/Secret- noch fremde World-/Figurenrechte.

**Fehlende Abhängigkeit:** Ein deaktiviertes Node-/Quest-/Door-/Turn-/Rule-/NPC-/Inventory-Modul wird **nicht still automatisch wieder eingeschaltet**. Der betroffene Automatikpfad wird kontrolliert gesperrt oder – nur bei tatsächlich vorhandener berechtigter Fachalternative – explizit im zugelassenen manuellen/SL-Bestätigungsmodus ausgeführt. Andere unabhängige Spielhandlungen können weiter funktionieren.

**Nicht gewählt:** A – ausschließlich unflexible Gesamtprofile. B – beliebige, voneinander unabhängige Schalter ohne Compatibility-/Version-/Dependencyprüfung. Wiederverwendbare Presets und Quickstart-Regelpakete bleiben **Vorbelegungen**, keine Sonder-Engines und keine zusätzlichen Rechte.

## 2. Gemeinsame Konfigurations- und Schnittstellenobjekte (Arbeitsnamen)

1. **CampaignConfiguration / CampaignConfigRevision / ActiveConfigEpoch:** Ein kampagneneigener versionierter Konfigurationszustand mit getrenntem Entwurf, geprüftem Kandidaten und tatsächlicher Aktivierung. Veraltete Browser- oder Backuprevisionen werden nicht unbemerkt wieder maßgeblich.
2. **ModuleDefinition / ModuleId / CapabilityDeclaration / CapabilityVersion:** Typisierte deklarierte Fachfunktionen, Eingänge, Ereignisse, Konfigurationen und Grenzen. Installiertes Paket oder bekannter Port ist kein effektives Use-/Read-/Write-/Actor-/GM-Recht.
3. **InstalledVersion / StableRelease / CampaignModuleBinding / DependencyLock:** Auf dem VPS vorhandene Version, wirklich freigegebene Release-Fassung und gewählte kampagnenbezogene Bindung sind getrennt. Nur gültige stabile Releases im Normalbetrieb; Beta nur in ausdrücklich isolierten 08.3-/14.8-Tests.
4. **RequiredDependency / OptionalIntegration / ConflictConstraint / VersionConstraint:** Typisierte gerichtete Anforderungen und Inkompatibilitäten je Capability/Action. Pflichtabhängigkeiten werden kompatibel aufgelöst, optionale fehlen ggf. ohne unerlaubte Weltwirkung.
5. **DependencyGraph / EffectiveCapabilityPlan / PlanDigest:** Zentrale begrenzt auswertbare und versionierte Ableitung mit reproduzierbarer Auflösungsfolge. Fehlende Pakete, Abhängigkeitszyklen, ungültige Quell-/Lizenz-/Schema-/Securityrechte und mehrdeutige Konflikte führen zur kontrollierten Ablehnung.
6. **ModuleEnablement / AutomationPolicy / ActionMode:** Fachlich zulässige Zustände OFF, MANUAL, GM_APPROVAL, AUTOMATIC; klar getrennt von einer nicht installierten, inkompatiblen, widerrufenen oder nicht berechtigten Capability. SLApproval ist noch keine WorldAction.
7. **CampaignDefault / RulePackPolicy / ScopedOverride / OverrideAuthority / PolicyProvenance:** Nach 02.25 gelten globale Vorbelegungen und ausdrücklich begrenzte Ausnahmen, die Scope, Owner, Revision, Herkunft, Fachberechtigung und gegebenenfalls Ablauf dokumentieren. Kein pauschaler „letzter Override gewinnt“-Bypass für Schutzrechte.
8. **EffectivePolicy / ConstraintIntersection / ResolutionReason:** Der Server ermittelt das tatsächliche Ergebnis aus gültiger Modul-/Rule-/Action-/Scoped-Policy und allen unabhängigen heutigen Pflichtrechten. Sicherheitsgrenzen können durch explizite Ausnahmen nicht aufgeweicht werden. Widersprüche werden fachlich nachvollziehbar abgewiesen.
9. **ConfigChangeIntent / ExpectedConfigRevision / ImpactPreview / ValidationResult:** Berechtigte Änderungen liefern eine gefilterte Vorschau auf Abhängigkeiten, World-/Session-/Rule-/NPC-/Quest-/Item-/Turn-/Node-Folgen, aktivierte Automation, inkompatible VersionPins und sichere Migrationsanforderungen. Preview und Save sind keine Weltwirkung.
10. **ActivationAuthority / SafePoint / ConfigActivation / ActivationReceipt / Audit:** Getrennte Berechtigungen zum Ansehen, Bearbeiten, Testen, Freigeben und Aktivieren. Der fachlich geprüfte Konfigurationscommit geschieht atomar innerhalb seines ConfigOwners; er öffnet **keine** GM-/Actor-/NPC-/World-/Key-/Hostrechte, braucht in V1 keine zweite SL und löst keine Roll-/Quest-/Item-/Tür-/WorldAction aus.
11. **ActionConfigBinding / PendingIntent / Revalidation / OriginalOperationId:** Offene Auto-/Node-/Würfel-/NPC-/Quest-/Turn-Intents werden vor echter Ausführung erneut gegen aktuelle ConfigEpoch, Rechte, Rule-/Source-/Actor-/Turn-/Resourcezustände geprüft. Bei Wechsel der Konfiguration folgt sicheres Fortsetzen, Halten oder Ablehnen nach vorhandenen Fachregeln; **keine** doppelte Ausführung und kein Semantikwechsel mitten im Commit.
12. **DisabledOrSuspendedModule / PersistedDomainState / RetentionFence:** Deaktivierung, Lizenz-/Securitywiderruf oder inkompatible Versionen sperren neue unzulässige Operationen, **löschen aber nicht** rechtmäßige gespeicherte Charakter-, NPC-, Roll-, Quest-, Inventar-, Turn- oder WorldHistorie. Deaktivierte Quellen werden weiterhin nur nach heutigen Leserechten sichtbar.
13. **VersionUpdateIntent / Eligibility / MigrationBoundary / PinReceipt:** Neue StableReleases ersetzen keine RulePack-/Extension-/Asset-/DefinitionPins still. Eine kompatibilitäts-/source-/owner-/license-/privacygeprüfte Umstellung darf keine unangemeldete Character-/Quest-/Worldmigration erzeugen.
14. **AuthorizedCatalog / SafeConfigProjection / BrowserCacheFence:** Katalog, Preview, WS, Search, Logs und Preload enthalten nur die tatsächlich für den Viewer berechtigten Modul-/Regel-/Fehler- und Quellmetadaten. Verborgene NPC-/Quest-/GM-/PlayerGeheimnisse dürfen auch über Abhängigkeitsdiagnosen nicht erscheinen.
15. **DependencyQuota / EvaluationBound / FailClosed:** Typ-, Graph-, Rekursions-, Mengen-, Request-, CPU-/Worker-/Trigger- und Quota-Grenzen werden fachlich zentral durch bestehende Quota-/Abusepolicies begrenzt. Es gibt keine Endlosschleifen, keine unkontrollierte Rekursion und keine direkte Drittcodeausführung.

## 3. Ausführung und Berechtigungsfolge

**Erstellen:** Ein berechtigter Kampagnenersteller wählt ein gültiges eigenes oder mitgeliefertes RulePack/Quickstart-Preset. Es entsteht ein **Konfigurationsentwurf**, kein automatisch publik gemachtes Spiel und keine ungefragte Aktivierung aller Features. Zusätzliche Source-/Owner-/Lizenzrechte müssen separat vorliegen.

**Konfigurieren:** Die SL stellt Module, zulässige Fachaktionen, gewünschte Automationsstufen und erforderliche Ausnahmen ein. Der zentrale Validator zeigt – gefiltert nach berechtigten Daten – an, welche Pfade möglich, unzulässig, inkompatibel oder abhängig von einer weiteren bewusst gewählten Funktion sind. Er aktiviert niemals selbst einen als OFF gewählten Dienst.

**Aktivieren:** Nur nach berechtigtem Commit, aktueller erwarteter Revision, kompatiblen VersionPins, bestätigter Auswirkung und ggf. fachlich gültigem SafePoint wird die neue ConfigEpoch aktiv. Publish von Szenen, Rule-/CharacterMigration und echte DomainWorldActions bleiben getrennt.

**Im Spiel:** Zulässiger Browser-/Node-/NPC-/Rule-Intent → aktuelle Account-/Session-/GM-/Actor-/Member-/Owner-/Source-/Fog-/History-/Asset-/License-/Privacy-/Quota-ACL → gültiger EffectiveCapabilityPlan → originäre fachliche Rule-/Resource-/Turn-/ActionPolicy → ggf. separate SL-Bestätigung → genau ein autoritativer 14.12-/14.13-Domain-/WorldCommit mit OriginalReceipt → gefilterte Benachrichtigung/WS-Projektion. Konfigurationsschalter, Preview, RuleEvaluation und SLApproval sind keine Weltcommits.

**Abschalten und laufende Aktionen:** Inaktive Pflichtabhängigkeit stoppt die davon abhängige Action, nicht pauschal alle übrigen Module. Noch offene Vorgänge müssen unter aktuellen Rechten erneut geprüft werden. Ein bereits rechtmäßig abgeschlossener Kampf-, Wurf-, Quest-, Item- oder Türzustand bleibt kanonisch und wird weder zurückgerollt noch wegen eines neuen ConfigPins wiederholt.

**Beispiel:** Eine Kampagne aktiviert manuelle Bewegung, automatische NPC-Wahrnehmung und SL-bestätigte Türaktionen. Ein Sensor-/NodeEreignis erzeugt nur einen **gültigen Vorschlag**. Erst nach aktueller SL-Freigabe, Tür-/GM-/Actor-/Scene-/Turn-/World-Prüfung und echtem OriginalWorldCommit öffnet die Tür. Wenn die Türfähigkeit deaktiviert wird, kann der Node sie nicht heimlich wieder einschalten oder alte Ereignisse nachträglich erneut ausführen.

## 4. Betrieb, Ausnahmen und Grenzfälle

- **Fachpflicht und Kampagnenoptionen sind getrennt:** Breite automatisierte Spielsysteme müssen für die B.2-B-Erstfreigabe wirklich implementiert sein; einzelne Kampagnen dürfen sie gemäß gültigem CapabilityPlan trotzdem teilweise deaktivieren oder manuell betreiben. Optionales Audio, integrierter Chat, Missiongenerator und Tutorials werden nicht durch die erste Spielrunde zur Pflicht.
- **Gezielte Ausnahmen:** Ein globaler Kampagnenstandard kann nach berechtigter Fachpolicy je Szene, Gruppe, Actor oder Node sinnvoll angepasst werden. OverrideScope, erlaubte Variante, Quelle und effektive Berechtigung müssen explizit sein. Bei unklarer Kombination gilt „keine unberechtigte Erweiterung“.
- **Authentische Live-Grenzen:** Eine GMPreview, isolierter Test, Beta, ein alter BrowserCache oder ein Plugin-Installationsstatus erzeugt keine aktive CampaignConfiguration und keinen gültigen WorldCommit.
- **Echte Rechteentzüge:** SessionRevoke, Key-/Asset-/License-/Source-/Privacyänderungen bleiben auch gegen bereits gespeicherte ConfigRevisionen und VersionPins sofort zu prüfen. Kein ReadAll-Zugang für Host, Support, GM oder Plugins.
- **Session/Realtime/Persistenz:** Der Konfigurationsstand ist wiederherstellbar und getrennt versioniert; WS-/Browserprojektionen revalidieren aktuelle ACL, Session und Konfiguration. Ein erfolgreicher Preview/Cache/Frontendzustand ist nie der alleinige Nachweis eines WorldWrites.
- **Transaktionsgrenzen:** DomainStore/WorldTransaction/OriginalReceipt/Outbox aus 14.12 und genau ein WorldWriter aus 14.13 bleiben maßgeblich; kein zweiter Kampf-/Quest-/NPC-/Inventar-/Node-/Turnmotor.
- **Abwärtskompatibilität:** Bestehende berechtigte CampaignWorld/Actor-/Item-/NPC-/Questzustände und Ergebnisse bleiben nach einer Config-Änderung erhalten. Exakte Migration braucht die heute gültigen spezialisierten 03.6-/14.6-/15.2-Fachoperationen.

## 5. Umsetzungsreihenfolge – als Architekturplan, kein bereits geschriebener Code

1. Gemeinsame Versionen und typisierte Capability-/Dependency-/Automation-Registrierung mit eindeutigem Modul- und Fachowner für RulePack, Node, Bewegung, Kampf/Turn, NPC, Würfel, Inventar, Quest und Handout.
2. Ein deklarativer Resolver mit Version-/Constraint-/Zyklus-/Konflikt-/Owner-/Source-/License-/Quota-/Privacyprüfung, nachvollziehbarem effektiven Plan und striktem Fail-Closed-Verhalten.
3. Geschützter ConfigDraft-/Preview-/ExpectedRevision-/SafePoint-/ActivationReceipt-Prozess ohne WorldSideEffects.
4. Laufzeitintegration: Jede fachliche Action benutzt den aktiven Plan **zusätzlich** zu ihren eigenen Actor-/GM-/Rule-/Target-/Resource-/Source-/WorldWriterrechten und OriginalReceipts.
5. Gefilterte Config-/Fehler-/Abhängigkeitsprojektion und sichere Caches, Test-/Preview-/Release-/Reconnect-/VPS-/Backupabläufe.
6. Umfangreicher B.2-B-End-to-End-Test mit gemischter automatischer/manueller/SL-bestätigter Steuerung. Die breite erste Produktfreigabe bleibt ein gesondertes Releasegate; interne Implementierung erfolgt nach B.1 in überprüfbaren Schritten.

## 6. Verbindliche Grundstruktur-Abnahmetests

| Test | Erwartetes Ergebnis |
|---|---|
| Gültige RulePack-Schnellstartvorlage | Erzeugt kompatiblen überprüfbaren Entwurf, keine ungewollten Zwangsmodule oder fremden Berechtigungen |
| Pflicht-Quest-/Door-/Rule-Capability deaktiviert | Abhängige Node-/NPC-/Questaktion blockiert; keine stille Aktivierung oder Weltwirkung |
| Optionale Audio-/Chat-/NPC-Integration fehlt | Unabhängige zulässige Gameplaypfade bleiben funktionsfähig |
| Konflikt, fehlender Release oder Versionsbereich nicht erfüllbar | Klarer ValidationResult; ungültige Konfiguration wird nicht aktiviert |
| Zyklische Module-Dependencies | Endliche, nachvollziehbare Ablehnung, kein Resolver-/Worker-Loop |
| Globale Automation mit enger Szene-/Figurenausnahme | Nur im rechtmäßig erlaubten fachlichen Scope wirksam |
| Override will fremden Actor, GMSecret oder privaten Spielerchat freigeben | Abweisung ohne Daten-/Metadatenleck |
| Manuel/SL-bestätigt/automatisch gemischt | Nur wirklich erlaubte Fachaktionen folgen dem jeweiligen Modus |
| SL freigibt noch offenen Antrag | Aktuelle Berechtigungen werden vor WorldEffect erneut geprüft |
| Gleichzeitig zwei ConfigÄnderungen | ExpectedRevision-/CAS-Grenze verhindert verlorenes Update |
| NPC-/Turn-/NodeIntent während ConfigWechsel | Keine Teilwirkung und keine doppelte oder semantisch veränderte Buchung |
| Modul in laufendem Kampf deaktiviert | Fachlich gültiger SafePoint oder sichere Ablehnung, keine rückwirkende Statusänderung |
| Neues Release erscheint | Kein stilles Update von alten gültigen CampaignVersionPins |
| Beta vorhanden | Nur expliziter isolierter Test; niemals in normaler Prod-Katalog-/Dependency-Auswahl |
| Quota erschöpft | Kein neuer unberechtigter AutoAction-/Retry-/WorldCommit |
| Lizenz-/Source-/Sessionrecht widerrufen | Neue Reads/Actions auch bei gepinnten oder gecachten Altversionen verweigert |
| Versteckter GM-/NPC-/Questmodulzustand im Katalog | Spieler sehen weder geheime Inhalte noch Labels, Counts oder DiagnosticLeaks |
| Doppelte WS-/Workeranfrage | Bestehendes OriginalReceipt, keine zweite Roll-/Item-/Quest-/NPC-/Worldwirkung |
| BackupRestore mit alter Config | Heutige gültige Rechte, Revocations und Versionskompatibilität bleiben durchgesetzt |
| Mehrere aktive GM oder direkter Nodezugang auf WorldWriter | Server blockiert unerlaubte zweite Autorität bzw. Direktwirkung |
| ConfigSave/Preview | Kein WorldReset, Roll-/Quest-/Traktor-/Item-/NPC-/WorldEffect |
| Durchgängiges B.2-B-Spiel mit wechselnden Automationsstufen | Alle vereinbarten automatischen Kernfamilien verfügbar; manuelle Wege nur nach gültiger Fachpolicy |

## 7. Entscheidungsgrenze und nächste Grundfrage

**B.3 C beschlossen:** Eine zentrale, versionierte Konfigurations- und Abhängigkeitsprüfung für individuell aktivierbare Module und pro Fachkontext zulässige Automationsstufen. Keine stillen Änderungen, keine zweite World-/Regel-/BerechtigungsEngine und keine geheimnis- oder rechteerweiternde Ausnahme.

**Später festlegen:** technische API-/DB-Formate, genaue Versionierungsnotation, konkrete Presets, UI der Kampagnenerstellung, Spezial-Overrides, Defaultwerte, Zahlen/Quotas, genaue SafePoint-Regeln, Performance-Limits und Migrationsabläufe. Bereits beschlossene OriginalDomainAction-/Source-/GM-/Privacy-/SingleWriter-Grenzen dürfen nicht später durch Konfigurationskomfort umgangen werden.

### B.4 – Wie werden die Daten- und Ereignis-Schnittstellen aller Fachmodule verbindlich zusammengeführt?

**Historische Entscheidungsfrage: B.4 wurde nachfolgend als C beschlossen; siehe [verbindlichen B.4-C-Plan](PHASE-B-WORKSHOP-B.4.md).**

- **A – Ein einziges unmittelbar von allen Modulen bearbeitbares Welt-Datenobjekt:** Einfacher Start, aber starke Kopplung, Sicherheits- und Migrationsrisiken.
- **B – Jedes Modul verwaltet Referenzen und Schnittstellen völlig eigenständig:** Wenig gemeinsame Kernarbeit, jedoch unkoordinierte Kopien von Character-/Item-/Quest-/Turn-/Actor-/ACL- und Worldlogik.
- **C – Gemeinsame typisierte Fachowner- und Referenzverträge (Empfehlung):** Zentrales, versioniertes ID-/Command-/Event-/Receipt-/ACL-Schema mit eindeutig zuständigen Fachstores und einziger kanonischer 14.12-/14.13-WorldWriter-Grenze. Andere Module verwenden erlaubte Referenzen statt Schatten-Weltzustände. Konkrete DB-/API-Feldlisten später.
