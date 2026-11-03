# AdventureShift – Phase B, Beschluss B.6 C: gestuftes, aktuell berechtigtes Browser-Vorladen und Caching

**Nachfolgender Beschluss B.10 C (03.11.2026):** [Gemeinsame architekturgebundene Technologieentscheidung mit begrenzten isolierten Risikoproben und versionierten ADRs](PHASE-B-WORKSHOP-B.10.md); bestehende SingleVPS-/WorldWriter-/GM-/Source-/Privacy-/Rule-/Asset-/Releasegrenzen bleiben maßgeblich. Es wurde **noch kein** Framework, Datenbanksystem oder echter Technik-Spike ausgewählt/ausgeführt. **Nächste Grundfrage B.11 – erste technische Risikoprobe.**

**Nachfolgender Beschluss B.9 C (03.11.2026):** [Zwei rechtmäßig eigens konstruierte verschiedenartige RulePack-/Roll-/Turn-/Ressourcen-Referenzfälle](PHASE-B-WORKSHOP-B.9.md) sind im B.8-Gesamt-Releasegate zu prüfen. Ein passender numerischer 02.63-/02.64-Check und ein andersartiger 05.1-Pool-/SymbolCheck nutzen denselben B.3–B.8-/14.12-/14.13-Fachowner-/WorldWriter-/ACL-/OriginalReceiptvertrag; keine universelle Fantasy-/W20-/HP-/Klassenpflicht. **B.10 C inzwischen beschlossen; B.11 ist die nächste Grundfrage.**

**Nachfolgender Beschluss B.8 C (03.11.2026):** [Reproduzierbare 14.8-isolierte genreunabhängige Referenzkampagne und B.2-B-Gesamtfreigabe-Gates](PHASE-B-WORKSHOP-B.8.md) mit echten getrennten Browsern, B.3–B.7-Fach-/Source-/Privacy-/WorldWriter-/OriginalReceipt-/Reconnect-/Backup-Nachweisen und Negativfällen. Kein Green-CI-/Mock-Ersatz für echte integrierte Spielbarkeit. **B.9 C inzwischen beschlossen; B.10 ist die nächste Grundfrage.**

**Nachfolgender Beschluss B.7 C (03.11.2026):** [Fachlich zulässige lokale Offline-Entwürfe, StaleReadViews, OriginalOperationReceipt-Reconciliation und bewusstes frisches Submit](PHASE-B-WORKSHOP-B.7.md) ohne lokale Roll-/Quest-/NPC-/Item-/Turn-/WorldEngine. 02.118 A verbietet ChatDraft-Persistenz/AutoSend weiter; Auth-/GM-/Actor-/Source-/Fog-/Current+HistoricalAudience-/Turn-/Rule-/Worldrechte müssen nach Reconnect neu gelten. **B.8 C inzwischen beschlossen; nächste Grundfrage B.9 – RulePack-Konformität und Genreunabhängigkeit.**

**Stand:** 03.11.2026. **B.6 C vom Projektinhaber ausdrücklich beschlossen.**
**Status:** Verbindliche fachliche Grundstruktur, Daten-/Rechte-/Schnittstellenmodell, Umsetzungsfolge und Abnahmetests; **keine implementierte Software**, keine konkrete Browsercache-, Service-Worker-, HTTP-/WS-, Storage-, CDN- oder Datenbanktechnologie festgelegt.
**Kernentscheidung:** Der VPS stellt für jeden aktuellen Viewer einen **eigenen, priorisierten, versions- und rechtegebundenen Ladeplan** zusammen: kleine gegenwärtig benötigte Inhalte zuerst, weitere bereits ausdrücklich zulässige Inhalte im Hintergrund, neu freigegebene Geheimnisse **erst nach tatsächlicher Freigabe**. Sicherheits-/Lizenz-/Medienrechte und Ressourcenlimits gelten bei Planung **und** jeder erneuten tatsächlichen Auslieferung.
**Unveränderte V1-Grenzen:** Eigener VPS, getrennte SL-/Spielerbrowser, **genau ein aktiver Spielleiter und eine kanonische CampaignWorld je Kampagne**. B.1–B.5 bleiben verbindlich; Vorladen ist kein GM-/Actor-/WorldWrite-, Roll-, Quest-, Traktor- oder Veröffentlichungsrecht.
**Bezüge:** [Planungsstandard](PLANUNGSSTANDARD.md) · [B.1 – Entwicklungsschritte](PHASE-B-WORKSHOP-B.1.md) · [B.2 – breite erste spielbare Version](PHASE-B-WORKSHOP-B.2.md) · [B.3 – Kampagnenkonfiguration](PHASE-B-WORKSHOP-B.3.md) · [B.4 – Fachowner/DomainEvents](PHASE-B-WORKSHOP-B.4.md) · [B.5 – Viewerprojektionen/Realtime](PHASE-B-WORKSHOP-B.5.md) · [bestehender Stage-0–4-Vorladevertrag](SITZUNGS-VORLADEN-CACHE.md) · [02 Karten/Fog/Nodes](KARTEN-WORKSHOP.md) · [03.7 RulePack/Quickstart](CHARAKTER-WORKSHOP-03.7.md) · [08.1 GM-/Player-/Preview](SL-WERKZEUGE-WORKSHOP-08.1.md) · [09.2 Mitgliedschaft/Pause/Rejoin](KAMPAGNEN-WORKSHOP-09.2.md) · [09.4 Gruppen/HistoricalAudience](KAMPAGNEN-WORKSHOP-09.4.md) · [09.7 eine aktive Spielleitung](KAMPAGNEN-WORKSHOP-09.7.md) · [09.9 eine CampaignWorld](KAMPAGNEN-WORKSHOP-09.9.md) · [12.1 Assets/Owner/License](ASSETS-WORKSHOP-12.1.md) · [12.2 AssetVersionPins](ASSETS-WORKSHOP-12.2.md) · [12.3 Revoke/Erasure](ASSETS-WORKSHOP-12.3.md) · [12.5 MediaVariants](ASSETS-WORKSHOP-12.5.md) · [12.6 kein externes URLAssetImport](ASSETS-WORKSHOP-12.6.md) · [12.7 Quotas](ASSETS-WORKSHOP-12.7.md) · [13.2 Pane-/ViewerScopes](UI-WORKSHOP-13.2.md) · [13.3 OriginalReceipts](UI-WORKSHOP-13.3.md) · [13.12 sichere Workspace-Wiederaufnahme](UI-WORKSHOP-13.12.md) · [14.1 Auth/SourceACL](SICHERHEIT-WORKSHOP-14.1.md) · [14.2 SessionRevoke](SICHERHEIT-WORKSHOP-14.2.md) · [14.7 Job-/OutboxRecovery](SICHERHEIT-WORKSHOP-14.7.md) · [14.9 Requestschutz](SICHERHEIT-WORKSHOP-14.9.md) · [14.12 WorldTransactions](SICHERHEIT-WORKSHOP-14.12.md) · [15.4 Releases/Beta](ERWEITERUNGEN-WORKSHOP-15.4.md).

## 1. Verbindlicher Beschluss – Option C

**Ziel:** Möglichst flüssiges Kartenspiel, Szenenwechsel, Token-/Würfel-/Regel- und zulässiges MediaRendering bei üblicher VPS-/Browserverbindung. Ein Spielerbrowser darf deshalb notwendige **gegenwärtig erlaubte** Assets und voraussichtlich bald nötige **bereits erlaubte** Varianten vorausschauend beziehen. **Nicht bekannt oder nicht freigegeben heißt nicht vorladbar.** Es gibt keinen legitimen Geheimkarten-Gesamtdownload oder einen hinter CSS verborgenen NPC-/Quest-/Node-/GM-Blob.

**Bestehende Stufen 0–4 werden weiterverwendet, nicht neu erfunden.** Die ursprüngliche [Vorladegrundstruktur](SITZUNGS-VORLADEN-CACHE.md) ist verbindlich. B.6 C verbindet sie mit B.3-C-CampaignCapabilities, B.4-C-Fachowner-/DefinitionRef-/AssetUse-Grenzen, B.5-C-Viewer-Projections und 12.x-Media-/14.x-Request-/Privacy-/Quota-Fences. Das ist **kein zweiter unabhängiger Asset-/Permission-/Downloadmotor**.

**Geheimnisse:** Eine vorhersehbare zukünftige Szene, ein kommender NPC, eine Questbelohnung oder eine noch unbekannte Falle wird nicht allein deshalb im Spielerbrowser gecacht, weil eine SL sie vorbereitet, ein Generator sie erstellt, ein späterer Trigger möglich ist oder der VPS ihre Datei kennt. Selbst verschlüsselte nicht berechtigte Rohinhalte im Playerbrowser wären hier kein zulässiger Ersatz für serverseitiges Zurückhalten. Auch Dateinamen, Größen, Zähler, URLs, Kartenkoordinaten, Hashes, Downloadzeiten, Katalogtreffer und Fehler dürfen keine Secrets offenlegen.

**Leistungsziel ohne falsche Garantien:** Die Engine priorisiert LiveSpiel, autorisierte Bewegungs-/Turn-/Roll-/Quest-/NPC-/WorldEvents, Realtime-Reconnect und aktuell sichtbar benötigte Medien gegenüber Hintergrundtranscodes und spekulativem Preload. Weil zuvor geheime Inhalte erst nach legitimer Freigabe übertragen werden dürfen und Clients/Netzwerke begrenzt sind, werden **keine garantiert ladefreien Szenenwechsel, 100-%-Offline-Verfügbarkeit oder geheimnisfreie Zukunftsdownloads vor Freigabe** behauptet.

## 2. Stufen 0–4: bestehende Semantik und B.6-Ergänzung

| Stufe | Zulässige Aufgaben | Schutz-/Priorisierungsgrenze |
|---|---|---|
| **0 – App-Basis** | Versionierte benötigte öffentliche Anwendungsteile, freigegebene allgemeine UI-/Sprach-/Theme-Ressourcen | Keine geschützten Campaign-/Player-/GM-/NPC-/Quest-/AssetRohdaten allein durch AppShell |
| **1 – Sitzung vorbereiten** | Nach Auth-/Member-/GM-/Actor-/Sourceprüfung sichtbare Einstiegsszene, erlaubte Kartenkacheln, eigene Token-/Charakterdaten, benötigte kompatible RulePack-/UI-/Medienvarianten | Pro tatsächlichem Viewer und Startscope; keine komplette noch geheime Campaigndefinition |
| **2 – bereits zulässige nächste Bereiche** | Schon rechtmäßig bekannte anschließende Szene/Teilkachel, sichtbare NPC-/Item-/Handout-/regelgebundene Medien und Versionsreferenzen | Bloße wahrscheinliche Story-/Node-/Questnachfolge **ohne** aktuelle Erlaubnis bleibt unsichtbar und nicht vorladbar |
| **3 – opportunistischer Hintergrund** | Zusätzliche zulässige Assets nach verfügbarem Budget, Browser-/VPS-/Netzkapazität, ohne wichtiges LiveGameplay zu beeinträchtigen | Kann ohne Wahrheits-/Rechteänderung pausieren, gedrosselt werden oder ausfallen |
| **4 – echte neue Freigabe / JIT** | Nach berechtigter LivePublikation, Fog-/Known-/History-/Group-/Scene-/Item-/Questfreigabe erstmals benötigte sichere Assets laden | Vor Freigabe keinerlei Playerbytes/URL/Manifest; unumgängliche Nachladezeit nach Freigabe ist korrekt |

**SL und Player nicht gleichsetzen:** Die berechtigte Spielleitung darf unter eigenen heutigen GM-/Quellrechten vorbereitete Inhalte für ihren Arbeitsplatz vorladen. Diese Daten bleiben in GM-eigenen Viewer-/Cache-/MediaScopes und werden weder in read-only PlayerPreview noch über den einzigen GM-Account in Spielerbrowser gespiegelt. Der SL hat ebenfalls kein generelles Recht auf private Spieler-DMs, Notizen, Host-/Key- oder fremde Secretdaten.

## 3. Fachobjekte und Version-/Zugriffsverträge (Arbeitsnamen)

1. **PreloadContext / ViewerSession / CampaignId / PaneScope / AudienceScope:** Tatsächlicher Account-/Session-/Campaign-/Pane-/GM-/Actor-/Group-/Presenter-/HistoryScope statt bloßer Geräte-ID. Rechte sind vor Manifest-/AssetServe-Abgabe aktuell zu prüfen.
2. **ViewerEligibleContent / CurrentDisclosureDecision / KnownFogFence:** Eine vom Original-Fachowner/B.5-Projektionsvertrag heute geprüfte erlaubte Menge. Die PreloadPlanung erfindet keine Informationsfreigabe und darf nicht ungefilterte künftige World-/Node-/NPC-/QuestQuellen lesen.
3. **PreloadManifest / ManifestRevision / ManifestDigest / EnvironmentScope:** Nur zulässige konkrete AssetUse-/Variant-/Rule-/UI-Referenzen mit begrenztem Empfänger-/Versions-/Umgebungsscope; kein autorisierendes dauerndes DownloadAll-Ticket.
4. **PriorityBand / Stage / RequiredForCurrentView / EstimatedCost:** Reihenfolge nach tatsächlicher aktueller UX-Notwendigkeit und Budget; priorisierbar, aber kein Sicherheitsrecht, einen geheimen Kandidaten zu erwähnen.
5. **AssetSourceRef / AssetUseBinding / VariantVersion / LicenseGrant:** 12.1-/12.2-/12.5-Originalrechte, freigegebene Varianten und tatsächlich legitim verwendete Revisionen. Identische Bytes/Hashes bei unterschiedlichen Besitzern erlauben keine fremde Lizenz oder Lieferung.
6. **RulePackReleasePin / ModuleCapabilityRevision / DependencyLock:** Nur wirklich veröffentlichte, mit B.3 kompatible und heute nutzbare Rules/Modules laden. Beta-/PreRelease-Pakete nur im ausdrücklich getrennten 14.8-Testscope.
7. **ScopedCacheEntry / ViewerCacheNamespace / CacheVersion / DisclosureEpoch:** Client- und ggf. VPS-Zwischenspeicher nach tatsächlich genehmigter Quelle, Variante, Viewer, Environment und aktueller Berechtigungsbindung. Sharing von Render-/Blobbytes setzt erneut legitime ACL-/LicenseUse-Rechte voraus.
8. **ServeAuthorization / MediaServeFence / ExpiringDeliveryGrant:** Jeder neue Download, RangeRequest, Resume, Refresh oder URL-/Tokenausgabe benötigt aktuelle Session-/Source-/Target-/Audience-/Asset-/License-/Privacy-/Revokeprüfung; eine bereits bekannte URL/ETag ist kein neues Recht.
9. **ManifestInvalidation / CacheEpoch / ScopeRevoke:** GM-/Actor-/Member-/Group-/Fog-/Scene-/Source-/Asset-/License-/Privacy-/Consent-/Session-/ConfigÄnderungen sperren neue unberechtigte Angebote und markieren betroffene Client-/ServiceWorker-/InMemory-Projektionen als ungültig.
10. **AllowedPrefetchNext / CandidateEvidence / NoFutureSecret:** Kandidaten entstehen nur aus **bereits aktuell offenbarten** Quellen; private GM-Vorbereitungen, unerlaubte künftige Szenenfolge und geheime Node-Targets werden selbst als Kandidatenmetadaten nicht an Playersessions übermittelt.
11. **VpsGlobalQuota / CampaignQuota / OwnerQuota / BrowserBudget / PriorityFence:** 12.7-/14.9-Host-/Campaign-/Owner-/Traffic-/Cache-/Media-/Workerbudgets werden angewandt; Hintergrundvorladen darf keine LiveActions/Realtime/NowVisible-Assets verhungern lassen.
12. **DownloadWorkItem / SchedulerLease / CancellationFence / RetryEligibility:** Drosselbarer und abbrechbarer Hintergrundauftrag. Ein geplanter Download darf beim späteren Start nach Widerruf nicht ohne frischen Rechtecheck fortgesetzt werden.
13. **VariantSelection / QualityTier / NetworkHint / ViewportNeed:** Geeignete bereits legitime Medienauflösung/TileRange passend zu aktueller Szene, Gerät und verfügbarem Budget; kein vollständiger Geheimlayer, nur weil ein großer Bildblob einfach zu cachen ist.
14. **CacheHitEligibility / ConditionalRequest / ValidationReceipt:** Auch 304/ETag/Range/SharedCache- und Refresh-Pfade dürfen heute verbotenen neuen Zugriff nicht fortsetzen; unveränderte legal berechtigte Dateien sind nach frischer aktueller Prüfung wiederverwendbar.
15. **PreloadProgressProjection / AuthorizedFailure / Redaction:** Nur für den konkreten Empfänger zulässige Stufen-/Bereitschafts-/Fortschrittsinformationen. Keine geheimen Filecounts, Titel, Bytes, Quota-/Ownerdaten oder Dauer-Hinweise auf verborgene Ereignisse.
16. **DisconnectResume / OfflineReadScope / PendingIntentBoundary:** Bereits gültig gecachte erlaubte Lesedaten können kurzfristig lokal angezeigt werden, soweit Schutz/Clientzustand das erlaubt; ein Offlinecache wird **nie** zur WorldTruth oder zum automatischen WorldCommand. Ob/offline Intents gesichert werden, ist die nächste B.7-Grundfrage.
17. **Reconciliation / RestoreFence / RevocationHighWatermark:** Nach Reconnect/Restore neu autorisierte Manifest-/Version-/AssetSource-/AudiencePrüfung. Ein älteres Backup, Cache oder signierter Link reaktiviert widerrufene Geheimnisse nicht.
18. **AuditTrace / PrivacyRetention / NoRetrospectiveDeletionClaim:** Getrennte datensparsame Auslieferungs-/Abweisungsbelege für Security/Diagnose. Der VPS kann neue Lieferung unterbinden und eigene kontrollierbare Caches bereinigen, aber bereits extern gesicherte, einst legal empfangene Kopien nicht zuverlässig rückwirkend vernichten.

## 4. Grundablauf des intelligenten Vorladens

1. **VPS erstellt pro echter Viewer-/Pane-Session den erlaubten Einstieg:** B.5-C-Snapshot/CurrentACL, B.3-C-Config/RuleReleasePins und 12.x-Media-/LicenseScopes werden bei Bedarf aus ihren zuständigen Fachownern geprüft. Nur freigegebene Kandidaten gehen in den PreloadPlan.
2. **Initiale Startfähigkeit vor Vollständigkeit:** Öffentliche AppShell und die zum gegenwärtigen Betreten nötigen Viewer-/Scene-/Token-/Rule-/Map-Varianten (Stufe 0/1) haben Vorrang; ein optionales Großmedium blockiert nicht grundsätzlich die sichere Lobby-/Spielsitzungsbereitschaft.
3. **Berechtigte Vorausschau:** Weitere bereits sicht- und abrufberechtigte angrenzende Tiles, Szenenobjekte, NPC-/Handout-/Item-/Regelvarianten werden nach Kosten, Browserbudget und B.3-C-Modulabhängigkeiten in Stufe 2/3 priorisiert. Keine Server-GM-Planungsinformationen an Spieler liefern.
4. **Download mit erneuter Schutzprüfung:** Unmittelbar beim tatsächlichen Serve/Refresh/Range/Resume wird die heutige Permission-/License-/Source-/Revoke-Fence geprüft. Ein zum Planungszeitpunkt legitimer Kandidat kann vor der Auslieferung unzulässig werden.
5. **Render und Cache:** Browser verwenden nur die legitim ausgegebenen Varianten innerhalb des gültigen Viewer-/Source-/VersionScopes; aus dieser lokalen Lesedarstellung entstehen keine Actor-/Quest-/Roll-/NPC-/WorldEffects.
6. **Neue Freigabe:** Freigegebene vorher geheime Inhalte sind erst nach echter eigenständiger Scene-/Fog-/Known-/Handout-/Quest-/SL- oder DomainWorldAction für den entsprechenden Empfänger Stufe-4-JIT-fähig; zuvor dürfen keine URLs, Bytes oder Metadaten ausgesendet werden.
7. **Widerruf oder Kontextwechsel:** Logout, Pausieren/Austritt, GM-/Actor-/Group-/Fog-/Asset-/License-/Privacywechsel beendet neue unberechtigte Deliveries, entwertet betroffene Manifeste/URLs und fordert Client-/Server-CacheInvalidation für kontrollierbare Stores an.
8. **Reconnect/Recovery:** Session und Viewer-Kontext neu prüfen; B.5-C-Snapshot-/Delta-Cursor, B.3-C-Config und 12.x-AssetVersionPins revalidieren; legitime identische Assets bei frischen Grants wiederverwenden, unzulässige nie automatisch nachladen.
9. **VPS-Überlast/Client-Engpass:** Quota-/Backpressure-/Schedulervertrag reduziert zuerst Hintergrundpfade. Kritische Fachwrites und notwendige neue aktuell sichtbare Daten bleiben nach tatsächlicher Capacity- und AdmissionPolicy vorrangig; keine erfundene Null-Latenz-Garantie.

## 5. Umfang und sichere Ausnahmen

| Anwendungsfall | Vorladen zulässig | Vorladen unzulässig |
|---|---|---|
| Spieler steht vor bereits geöffnetem Raum | Bekanntes Kartenstück, erlaubte Tile-/Door-/Token-/AudioVariant, heute freigegebene UI-/RuleDaten | Die komplette Karte inklusive noch verdeckter Gegner, Fallen und Geheimräume |
| Gegner wird erst künftig entdeckt | Bereits bekannte allgemeine Spielregeldaten | Vorab versteckte NPC-Position, Portrait/Status, EncounterName, geheimer Roll-/Initiativehinweis |
| SL bereitet nächste Szene vor | In ihrem tatsächlich berechtigten GM-Arbeitskontext vorbereitete Ressourcen | Kopie dieser Daten in Player-/Preview-/Presenter-Cache ohne AudienceGrant |
| Handout/Quest wird neu freigegeben | Ab tatsächlich erlaubter Freigabe das adressierte Handout/RewardImage per Stufe 4 | Vorzeitiges geheimes PDF, Titel, Anzahl offener Quests oder geheime Bild-/Audiohashes |
| Spieler kehrt nach Pause zurück | Bei neu gültiger Session-/Member-/Actor-/Group-/Fog-/History-/LicenseACL aktuelle erlaubte Assets | Blindes Wiederverwenden alter Gruppen-/GM-/NPC-/Chat-/Questrechte |
| Modulpaket/RulePack erhält neues Release | Der von der Kampagne weiterhin gepinnte berechtigte stabile Release und kompatible Varianten | Automatisches Download-/ActivationUpgrade, produktive Beta-/Testdaten |
| Audio-/Chat-/Missionsgenerator-Modul aus | Erforderliche andere erlaubte Spielressourcen | Versteckte Pflichtdownloads des deaktivierten Moduls |
| Gleicher Blob in mehreren Medienbibliotheken | Bytewiederverwendung nur bei jeweils frischer legaler Use-/Owner-/Audienceberechtigung | Freigabe fremder Besitzerquellen durch Hash-/Cachegleichheit |

## 6. Umsetzungsplanung und Grundstruktur-Abnahmetests

**Reihenfolge:** (1) Ein einziges PreloadManifest-/Stage-/Audience-/AssetUse-/Variant-Kontraktmodell aus dem vorhandenen 12.x-Vorladeplan; (2) B.5-C-viewergefilterter Kandidatenresolver ohne Zukunftsgeheimnisse; (3) Stufen-/Quota-/Backpressure-/Cancellation-Scheduler; (4) frische MediaServe-, ETag-, Range-, URLRefresh- und Manifestrechte; (5) Revoke-/Reconnect-/CacheInvalidation/Restore-Reconciliation; (6) B.2-B-End-to-End-Abnahme in mehreren Browsern mit echten Map-/Rule-/NPC-/Node-/Inventory-/Quest-/Handout- und geheimen Medien.

| Prüfkonstellation | Erwartetes Verhalten |
|---|---|
| Spieler loggt sich zur Sitzungsvorbereitung ein | Stufe-0/1-App-/Scene-/Token-/Rule-/Assetdaten nur nach heutiger Session-/Member-/SourceACL |
| Aktueller Sichtbereich ist klein, dahinter geheime große Karte | Nur heute legale Tiles/Varianten; keine Vollkarte, Hash-/Size-/URL-/Count-Lecks |
| SL hat geheimen zukünftigen Boss/NPC geplant | Kein PlayerManifest, kein vorab ausgeliefertes Portrait, kein Hinweis durch Prefetch-Fortschritt |
| Bereits bekannte angrenzende Szene ist offen | Zulässige Stage-2/3-Prefetch mit Prioritäten/Quota und Abbruchmöglichkeit |
| Vorbereitetes Quest-/Handout-Asset wird erst jetzt freigegeben | Vor Freigabe keine Bytes; nach Freigabe Stage-4-JIT mit aktueller Recipient-/History-/LicenseACL |
| Ein legal eingeplantes Bild wird vor Download widerrufen | Erneuter ServeCheck verweigert und entwertet neuen Refresh/Range/Download |
| Gleicher Inhalt wird unter zwei Ownern referenziert | Identischer Blobhash gibt keinen übergreifenden fremden Read-/UseGrant |
| 304/ETag-, Range-/URLRefresh oder CacheHit nach Revoke | Kein neuer unberechtigter MediaServe; kontrollierbare betroffene Caches invalidieren |
| Player wechselt die Gruppe, pausiert oder kehrt zurück | Aktuelle Rechte/History erneut prüfen; keine automatische Alt-Audience-Auslieferung |
| GM-Arbeitsfläche und PlayerPreview im selben Browser | Getrennte Viewer-/Pane-/Asset-/CacheScopes, keine GMOriginale in PlayerProjection |
| Tab-Reconnect mit alten Session-/Source-/Fog-Marken | Neu autorisierter B.5-Snapshot/Manifest; keine automatische Wiederherstellung widerrufener Grants |
| Audio/Chat/Generator ausgeschaltet | Kein versteckter Pflicht-Preload oder WorldEffect für das deaktivierte optionale Modul |
| Neue Bibliotheksrevision oder Beta erscheint | Kein stiller CampaignPin-Wechsel; Beta nie im normalen Produktivprefetch |
| Viel gleichzeitiger Live-Kampf, WS und Medien-Download | Angemessene Quota-/Backpressure-Priorisierung für Fachaktionen und sichtbar benötigte Ressourcen |
| Background-Downloader nach VPS-/Worker-Neustart | Frische Job-/Source-/License-/Quota-/Session-/RevokeEligibility vor Fortsetzen |
| Spieler hat früher legal empfangenes Asset extern kopiert | Keine fälschliche Zusage, eine externe Kopie rückwirkend zu löschen; künftige Ausgaben blockieren |
| Mobilgerät mit wenig Speicher/Bandbreite | Angepasste bereits zulässige Variant-/Tile-/Cachepriorität, keine geheime Ersatz-Komplettdatei |
| Clientcache behauptet Tür-/Item-/Queständerung | Keine Kanonizität; nur 14.12-/14.13-WorldAction mit OriginalReceipt verändert Welt |
| Aufwändige Szene lädt aus dem Internet nach | Kein garantierter Null-Ladezeit-Anspruch; Unfreigegebenes bleibt serverseitig zurückgehalten |
| Multi-Browser-B.2-B-Gesamtrunde | Korrekte erlaubte Vorlade-/Medien-/Realtime- und Widerrufsabwicklung für Karten, Nodes, NPC, Rule/Combat, Inventar, Quests |

## 7. Beschlussgrenze und nächste Grundfrage

**B.6 C beschlossen:** Der **bestehende Stage-0–4-Vorladevertrag** erhält eine einheitliche pro Viewer berechtigte Manifest-/Prioritäten-/Version-/Quota-/MediaServe-/Revocation-Verzahnung mit B.3 C, B.4 C und B.5 C. Für Spieler keine unveröffentlichten künftigen Geheimnisse im Cache; korrekte einmalige Spielweltwirkungen bleiben ausschließlich bei bestehenden Fachactions.

**Später festlegen:** konkrete Mengen-/Performance-/Netzwerk-/ClientSpeicherbudgets, Ladeprioritäten und Fairness, Cache-/CDN-/ServiceWorker-Technik, Tile-/Variantformate, URLs/TTL/ETag/Rangeverfahren, UI-Bereitschaftsanzeigen, Geräteparameter und Media-Scheduling; keine unbegründete Garantie vollständiger Ladefreiheit.

### B.7 – Wie werden unterbrochene Browser-/Netzverbindungen bei lokalen Eingaben behandelt?

**Historische Entscheidungsfrage – B.7 C wurde nachfolgend verbindlich beschlossen; siehe [B.7-C-Fachentwurf](PHASE-B-WORKSHOP-B.7.md).**

- **A – Während Offline strikt keine Eingaben:** Nur aktuelle Verbindung erlaubt Aktionen oder Entwürfe; einfach, aber unterbrochene Runden können unnötig Arbeitsfortschritt verlieren.
- **B – Browser schreibt offline eine eigenständige lokale Spielwelt und synchronisiert später alles automatisch:** Flüssig, aber widerspricht einer einzigen serverautoritativen CampaignWorld, echten Würfeln, aktuellen Actor-/GM-/Turn-/Fog- und OriginalOperationReceipt-Rechten.
- **C – Sichere lokale Entwürfe und ausdrücklich ausstehende Intents (Empfehlung):** Bereits erlaubte Daten können als klar gekennzeichnete veraltbare Lesesicht dienen. Spieler dürfen begrenzte lokale Form-/Notiz-/Aktionseingaben als **unbestätigte Entwürfe** vorbereiten, soweit die Fach-/Privacy-Policy das zulässt. Nach Wiederverbindung werden nur ausdrücklich zur Übertragung freigegebene, noch gültige Intents unter **heutiger** Account-/Session-/Actor-/GM-/Turn-/Resource-/Source-/WorldRevision-/B.3-Policy erneut serverseitig geprüft. Kein lokaler Roll-/Quest-/Item-/NPC-/WorldCommit, keine stillen doppelten Handlungen, keine Rückwirkung alter Zug-/Sichtrechte. Konkrete Offline-UX und Speicherfristen später.
