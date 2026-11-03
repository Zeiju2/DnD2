# AdventureShift – Phase B, Beschluss B.7 C: sichere lokale Entwürfe und ausdrücklich kontrollierte Wiederaufnahme nach Netzunterbrechung

**Nachfolgender Beschluss B.9 C (03.11.2026):** [Zwei rechtmäßig eigens konstruierte verschiedenartige RulePack-/Roll-/Turn-/Ressourcen-Referenzfälle](PHASE-B-WORKSHOP-B.9.md) sind im B.8-Gesamt-Releasegate zu prüfen. Ein passender numerischer 02.63-/02.64-Check und ein andersartiger 05.1-Pool-/SymbolCheck nutzen denselben B.3–B.8-/14.12-/14.13-Fachowner-/WorldWriter-/ACL-/OriginalReceiptvertrag; keine universelle Fantasy-/W20-/HP-/Klassenpflicht. **Nächste Grundfrage B.10 – technische Basis nach Risikoprüfung wählen.**

**Nachfolgender Beschluss B.8 C (03.11.2026):** [Reproduzierbare 14.8-isolierte genreunabhängige Referenzkampagne und B.2-B-Gesamtfreigabe-Gates](PHASE-B-WORKSHOP-B.8.md) mit echten getrennten Browsern, B.3–B.7-Fach-/Source-/Privacy-/WorldWriter-/OriginalReceipt-/Reconnect-/Backup-Nachweisen und Negativfällen. Kein Green-CI-/Mock-Ersatz für echte integrierte Spielbarkeit. **B.9 C inzwischen beschlossen; B.10 ist die nächste Grundfrage.**

**Stand:** 03.11.2026. **B.7 C vom Projektinhaber ausdrücklich gewählt.**
**Status:** Verbindlicher Fach- und Architekturgrundbeschluss mit Daten-/Rechte-/Ablauf-/Fehler-/Testgrenzen; **keine Softwareimplementierung**, kein endgültiger Browserstorage-, API-, Offline-UI- oder Synchronisationsalgorithmus.
**Entscheidung:** Bei zeitweiliger Offline-/VPS-/WebSocket-Unterbrechung dürfen bereits legitim empfangene Inhalte nur als möglicherweise veraltbare **Lesesicht** dienen. Zulässige lokale Eingaben können als klar unbestätigte **Entwürfe** vorbereitet werden. Eine tatsächliche Übertragung oder Ausführung erfolgt **nicht blind**, sondern nur nach expliziter fachlicher Sendefreigabe und erneuter aktueller Serverprüfung, ggf. nach vorgängigem Abgleich eines unbekannten bisherigen Operationsergebnisses.
**V1:** Ein selbst betriebener VPS, je eigene Spieler-/SL-Browser, genau **ein aktiver Spielleiter pro Kampagne** und genau **eine kanonische CampaignWorld**. Keine clientseitige Welt-/Würfel-/Roll-/Quest-/NPC-/Inventory-/TurnEngine und keine zusätzliche GM-/Actor-/Owner-/Source-/Privacyautorität.
**Unverändert:** [B.1 C – überprüfbare Entwicklungsinkremente](PHASE-B-WORKSHOP-B.1.md) · [B.2 B – breite erste spielbare Freigabe](PHASE-B-WORKSHOP-B.2.md) · [B.3 C – Module und Automations-Policies](PHASE-B-WORKSHOP-B.3.md) · [B.4 C – Fachowner und typisierte Aktionen](PHASE-B-WORKSHOP-B.4.md) · [B.5 C – aktuelle Viewer-/Realtime-Projektionen](PHASE-B-WORKSHOP-B.5.md) · [B.6 C – berechtigtes Vorladen](PHASE-B-WORKSHOP-B.6.md).
**Weitere Bezüge:** [02.118 A – kein gespeicherter ungesendeter Chatentwurf](KARTEN-WORKSHOP-02.118.md) · [02.99 originale WorldActions](KARTEN-WORKSHOP-02.99.md) · [03.2 Figuren-/ControlGrant](CHARAKTER-WORKSHOP-03.2.md) · [05.1 echte VPS-Würfel](WUERFEL-WORKSHOP-05.1.md) · [08.3 Draft/Test/Publish/Live getrennt](SL-WERKZEUGE-WORKSHOP-08.3.md) · [09.2 Join/Pause/Rejoin](KAMPAGNEN-WORKSHOP-09.2.md) · [09.7 SingleGM](KAMPAGNEN-WORKSHOP-09.7.md) · [09.9 SingleWorld](KAMPAGNEN-WORKSHOP-09.9.md) · [09.8 Privacy/Erasure](KAMPAGNEN-WORKSHOP-09.8.md) · [13.3 Status/OriginalReceipt](UI-WORKSHOP-13.3.md) · [13.7 getypte Feld-/Draft-/Savegrenzen](UI-WORKSHOP-13.7.md) · [13.12 WorkspaceResume](UI-WORKSHOP-13.12.md) · [14.1 Auth-/Session-/Actor-/SourceACL](SICHERHEIT-WORKSHOP-14.1.md) · [14.2 Revoke/Logout](SICHERHEIT-WORKSHOP-14.2.md) · [14.7 Jobs/Recovery](SICHERHEIT-WORKSHOP-14.7.md) · [14.9 Requestschutz](SICHERHEIT-WORKSHOP-14.9.md) · [14.12 echte WorldTransaction-/OriginalOperationReceipts](SICHERHEIT-WORKSHOP-14.12.md) · [14.13 SingleWriter](SICHERHEIT-WORKSHOP-14.13.md) · [Betriebliches Vorladen](SITZUNGS-VORLADEN-CACHE.md).

## 1. Verbindlicher Fachbeschluss – C

**Offline ist kein eigener Spielmodus mit selbstständiger Welt:** Der Browser darf eine zuvor berechtigt empfangene Karte, einen Text oder ein eigenes Formular vorläufig darstellen und editieren. Diese Ansicht kann inzwischen veraltet oder widerrufen sein. Ihre lokalen Änderungen sind **keine** WorldAction, RuleEvaluation, RollRecord, Quest-/Item-/NPC-/TurnMutation, Charaktersteuerung oder neue historische Freigabe.

**Entwurf und verbindliche Operation getrennt:** Ein erlaubter Spieler kann einen Notiztext, Formularwert, eine beabsichtigte Zug-/Aktionswahl oder eine zulässige SL-Editoränderung vorbereiten, soweit **die jeweilige Fachdomäne** einen lokalen Entwurf überhaupt erlaubt. Der gemeinsame Offlinevertrag führt **keine allgemeine ChatDraft-, Autosave-, Recovery-, PlayerImpersonation- oder ActionQueue-Funktion** ein. Es ist nicht für jeden Command eine Offlinevorbereitung zulässig.

**02.118 A ist eine ausdrückliche Ausnahme ohne Aufweichung:** Ungesendete Chat-/DM-Nachrichten bleiben höchstens flüchtig im aktuellen Eingabefeld. Kein lokaler persistenter ChatDraft, Geräte-/Accountsynchronisation, Browser-/ServiceWorker-ChatRestore oder automatische ChatSend-Warteschlange beim Reconnect. Zulässige **echte eigene Spielernotizen** nach 02.94–02.97 oder SL-Entwürfe sind eigenständige Fachobjekte, keine umetikettierten Chatentwürfe.

**Explizites Senden und aktuelle Fachprüfung:** Nach Rückkehr der Verbindung reicht ein lokaler Entwurf allein nicht. Er wird fachlich validiert, dem Nutzer als noch unverbindlich angezeigt und darf nur bei aktivem gültigem Konto-/Session-/Campaign-/GM-/Actor-/Source-/Turn-/Resource-/B.3-Config-/WorldRevision-/Policykontext sowie einer zum Fachcommand gehörenden **bewussten Sendeentscheidung** ausgeführt werden. Wo eine automatische DomainSave-Policy ausdrücklich bereits vorher zugelassen wurde, bleibt ihre Fach-/EditAuthorization maßgeblich; niemals automatisch World-/Roll-/Quest-/Item-/Npc-/ChatAction durch bloßen Reconnect.

**Unbekanntes Ergebnis darf nicht verdoppelt werden:** Verbindungsabbruch **nach** dem Senden ist nicht gleichbedeutend mit „nie angekommen“. Vor jeder Wiederholung prüft der Client/Server den ursprünglichen fachlich authentischen OriginalOperationId-/Receipt-/Pending-/Unknown-Status. Eine nötige erneut zulässige Übermittlung verwendet die **identische** Idempotency-/Operation-Identität; erfolgreiche Weltwirkung wird nicht ein zweites Mal committed. Fehlt ein sicher nachweisbarer Status, bleibt die Handlung als *unklar* markiert, statt Erfolg oder Misserfolg zu erfinden.

**Kein unerlaubtes Wiederaufleben:** Ein historisch erlaubter Zug, verlorener ControlGrant, veränderte Fog-/Source-/Group-/GM-AuthorityEpoch, Ablauf einer Session oder alte ResourceRevision berechtigt nicht zu späterer Nachholung. Veraltete Actions können verworfen oder gezielt neu formuliert werden; keine nachträglichen Bonusaktionen oder Roll-/Quest-/Door-/Item-/Traktorwirkungen.

**Nicht gewählt:** A – grundsätzlich keine lokale Vorbereitung von geeigneten Eingaben. B – unabhängige Offline-World mit automatischem späterem Konflikt-Merge und replayten Würfel-/Spielweltwirkungen.

## 2. Fachobjekte, Zustands- und Schnittstellenverträge (Arbeitsnamen)

1. **ConnectivityState / TransportHealth / ServiceReadiness:** Online, instabil, offline und wiederverbindend sind **Client-/Serviceindikatoren**, kein echter GM-/Actor-/World- oder Sessionmitgliedschaftszustand; ein Ping beweist nicht die Wirkung einer Aktion.
2. **ViewerReadSnapshot / ReadRevision / StaleDisclosure:** B.5-/B.6-berechtigt empfangene ReadOnlyProjektion mit ursprünglicher Source-/Viewer-/Campaign-/Scene-/Fog-/License-/HistoricalAudience-Bindung. Offline stets möglicherweise veraltet; keine Rechtegewährung durch Cachebesitz.
3. **LocalInputBuffer / DraftKind / FieldPolicy:** Nur nach 13.7 tatsächlich geeignete lokale Formular-/Notiz-/Editor-/ActionIntent-Entwürfe. Typ-/Feld-/Owner-/Source-/Retention-/Privacyregeln kommen vom zuständigen Fachowner, nicht von allgemeinem OfflineStorage.
4. **DraftPersistenceEligibility / SensitiveDataClass / ClientLifecycleFence:** Ob ein Entwurf überhaupt lokal gespeichert werden darf, ist gesondert fachlich legitimiert; geeignete Schutzmaßnahmen, begrenzte Lebensdauer/Größe und Löschung bei Logout/SessionRevoke/Accountwechsel. **02.118-A-ChatDrafts sind ausdrücklich nicht persistierbar.**
5. **DraftContextBinding / AccountId / SessionId / CampaignId / ActorId / GmEpoch / PaneScope:** Ein Eingabepuffer darf nicht still auf einen anderen User, Figur, Gruppe, aktiven SL, Kampagne, Tab oder SourceOwner übertragen werden.
6. **DraftBaseRevision / ExpectedRevision / TargetRef / ConfigEpoch:** Lokale Änderung merkt sich die ursprünglich berechtigt gesehene Basis, ohne daraus alte Commitrechte zu konservieren. Bei Veränderung sind aktuelle Domain-/World-/Rule-/Ownerstände neu aufzulösen.
7. **PreparedIntent / CommandKind / ExplicitSubmissionConsent:** Ein Entwurf einer echten Action ist erst ein unbestätigter **Vorschlag**. Die tatsächliche, einzeln bewusste Sendefreigabe erfordert aktuelle Entscheidung und gültige Domänenerlaubnis.
8. **InFlightOperation / OriginalOperationId / IdempotencyKey / ReceiptLookup:** Eine womöglich bereits gesendete Aktion trägt eine unveränderte Original-Identität; Ergebnisabgleich erfolgt **vor** einer erneuten Übermittlung. Neue Aktion braucht neue ausdrückliche Absicht und gültigen eigenen Operationbezug.
9. **OfflineQueuePolicy / AllowedCommandKinds / NoAutoReplay:** Keine generische unbeschränkte Weltaktionswarteschlange. Nur explizit erlaubte Fachcommand-Arten können als vorbereitete, nicht gesendete Entwürfe existieren; automatisches Senden beim Reconnect ist für LiveWorld-/Roll-/Chatwirkung ausgeschlossen.
10. **ReconnectHandshake / FreshAuthentication / SecurityEpoch / SessionRevokeFence:** Tatsächlich neue Auth-/Session-/Membership-/GM-/Actor-/Source-/Fog-/Privacy-/Asset-/History-/Key-/License-/Envprüfung, unabhängig vom vorherigen Cache oder einem alten signierten Token.
11. **RevalidationResult / EligibilityPreview / ConflictReason:** Jede geplante Operation erhält eine neue servergeprüfte und quellengefilterte Zulässigkeits-/Konfliktvorschau. Auch Ablehnungen dürfen keine fremden NPC-/GM-/Quest-/Inventar-/Historygeheimnisse verraten.
12. **CommitIntent / DomainOwner / WorldWriterFence / OriginalReceipt:** Nur die jeweiligen 02.99-/03–10-/14.12-/14.13-Fachowner dürfen echte Domain-/WorldCommits einmalig auslösen; weder OfflineDraftSave noch ClientVorschau ist ein WorldEffect.
13. **PendingOrUnknownAction / Confirmation / SafeRetry:** Geprüfte Pending-/Unknown-/Rejected-/Conflict-/Committed-Stati nach 13.3 C statt optimistisch „durchgeführt“. Bei ungewisser Antwort kein blindes Replay, weder Server- noch Client-Seitenwirkung durch bloßes UI-Fortsetzen.
14. **ClientDraftReconciliation / Discard / RebaseSuggestion:** Nutzer kann geeignete Entwürfe bewusst verwerfen oder nach eigener Entscheidung auf neue Fachrevision umarbeiten. Kein automatisches Force-Overwrite, von alten Geheimnissen abgeleitete Werte nicht ungeprüft rebasen.
15. **PrivacyScope / Retention / EraseOnLogout / UserSwitchFence:** Lokale personenbezogene Eingaben und gespeicherte erlaubte Notizen folgen getrennten Source-/Retention-/Erasure-/Privacygrenzen. Ein gemeinsames Gerät oder Browserprofil darf keine stillschweigende Übernahme durch eine andere Anmeldung bewirken.
16. **BackgroundSyncRestriction / ServiceWorkerFence / PreviewRestriction:** Hintergrund-Push/Sync, Offline-Preview und SL-ReadOnlyPlayerView erhalten keine unbemerkten Send-, Weltaktions-, Publish- oder echten PlayerImpersonationrechte.
17. **DeliveryReceipt / ReconnectCursor / AuthorizedProjection:** Nach echtem Ergebnis liefert B.5 C nur aktuell zulässige Snapshot-/Delta-/Receiptprojektionen. Die lokale Entwurfsanzeige wird nie als bestätigte WorldTruth interpretiert.
18. **Quota / SizeBound / RetryBound / AbuseProtection:** Begrenzte und kontrollierte Entwurfsgrößen, Wiederverbindungsversuche und zulässige Operationen nach 12.7/14.9. Wiederholung/Backpressure darf keine Quota-/GM-/Actor-/WorldWriter-Schranken umgehen.

## 3. Trennung der Eingabeklassen

| Eingabe | Während offline erlaubt | Nach Verbindung |
|---|---|---|
| Bereits rechtmäßig sichtbare Karte, Charakter-/Quest-/Inventaransicht | Lokal nur als klar möglicherweise veraltete Lesesicht, ohne neue Secret-/Worldrechte | Frische aktuelle B.5-Reprojektion; entzogene Daten in kontrollierbaren Caches invalidieren |
| Geeignetes eigenes Formular, eigene echte Notiz | Flüchtiger Entwurf, optional nur bei fachlich ausdrücklich erlaubter sicherer Persistenz | Revalidierter eigenständiger Field-/NoteSave mit CurrentACL/ExpectedRevision; keine implizite ChatMessage |
| SL-Szene-/Node-/Regel-Entwurf | Nur für berechtigte Owner-/GM-/DraftScopes; keine Test-/Publish-/Livewirkung | Source-/Owner-/Version-/Conflictprüfung und ggf. eigener DraftSave, Publish separat |
| Ungesendete Chat-/DM-Nachricht | **Nur flüchtig im aktuellen Eingabefeld**, keine gespeicherte Offlinewarteschlange | 02.118 A: kein AutoSend/ChatRestore; tatsächlicher Send nur nach eigener bewusster Aktion und aktuellem Channel-/DM-Recht |
| Geplante Move-/Turn-/Angriffs-/Roll-/Door-/NPC-/Quest-/Itemaktion | Allenfalls explizit zulässige, klar unbestätigte Absicht, keine verbindliche Simulation/Verbrauch/Würfelwerte | Nach LiveSync/Turn-/Actor-/Resource-/Rule-/Source-/WorldRevisionprüfung ausdrücklich neu freigeben; OriginalReceipt vor Retry abgleichen |
| Formell bereits abgesendete Action, Ack verloren | **Pending/Unknown**, nicht als „nie versendet“ behandeln und nicht zweite Absicht erzeugen | Zuerst OriginalOperationId-/OriginalReceiptabgleich; idempotenter SafeRetry nur nach gültiger Domainpolicy |
| Inaktive/alte GM-/Actor-/Membership-/Fog-/QuestBerechtigung | Keine legitime Autorität durch vorhandene lokale Daten oder Cache | Heutiger Grant entscheidet; ungültige Actions ablehnen, illegitime Datenzugriffe sperren |

## 4. Gesicherter Ablauf

1. **Netzabbruch erkennen:** App stellt betroffene Sendewege als instabil/offline dar; laufende Eingaben bleiben nur als für ihren Fachbereich erlaubte Entwürfe erhalten. Ungewisse bereits gesendete Commands werden als Pending/Unknown geführt.
2. **Nur erlaubt anzeigen:** Browser darf zuvor legitim erhaltene Inhalte lokal begrenzt als veraltbar darstellen, erhält aber keine neuen Geheimnisse. Keine lokale Würfel-/Quest-/World- oder NPC-Realaktion, kein neuer Actor-/GM-Grant.
3. **Entwurf vorbereiten:** Gegebenenfalls fachspezifische Felder oder Aktionen lokal aufnehmen; DomainPolicy bestimmt Speicherung, TTL, Privatsphäre und ob nur Flüchtigkeit erlaubt ist. Chat-/DM-Text nur flüchtig ohne Restore.
4. **Wiederverbindung:** Zuerst echte Auth-/Session-/Campaign-/GmEpoch-/Actor-/Group-/Source-/History-/Rule-/Config-/Turn-/Resource-/WorldRevision-Revalidierung und B.5-/B.6-sicherer neuer Snapshot/Delta-Abgleich. Ein ResumeCursor oder Token ist kein aktuelles Recht.
5. **Unsichere alte Ergebnisse klären:** Für vor Disconnect bereits versandte Operationen OriginalOperationId-/Receiptstatus abfragen. Kein neues WorldEffect bei erfolgreichem altem Commit; Pending/Unknown bleibt entsprechend gekennzeichnet.
6. **Entwürfe getrennt prüfen:** Für noch nie versandte Eingaben aktuelle Fach-/Schema-/Source-/Field-/Quota-/ExpectedRevisionprüfung; bei Konflikt/abgelaufenen Zugrechten klare Ablehnung oder nur nach bewusster neuer Bearbeitung aktualisierte Absicht.
7. **Bewusster Fachcommit:** Erst die explizit gesendete, aktuell erlaubte Operation durch ursprünglichen Fachowner/WorldWriter erzeugt einen echten einmaligen Commit. Zulässige reine Formular- oder Notizspeicherung bleibt getrennt von Spielaktionen.
8. **Berechtigtes Ergebnis anzeigen:** OriginalReceipt und aktuelle adressatengerechte B.5-Projektion bestimmen Committed/Pending/Rejected. Auch mehrere Tabs oder wiederholte WS-Events erzeugen keine doppelten Effekte.
9. **Logout, Privacyentzug oder Besitzerwechsel:** Nicht mehr erlaubte Cliententwürfe und kontrollierbare Caches werden gemäß ihrem gültigen Fach-/Retention-/SessionFence verworfen; bereits extern kopierte früher sichtbare Daten lassen sich nicht rückwirkend garantiert entfernen.

## 5. Implementierungsfolge und Abnahmekriterien

**Umsetzung nach B.1 C:** (1) explizite Klassifikation von fachlich überhaupt offline vorbereitbaren Eingaben; (2) lokale Lesesicht-/Entwurfs-/Privacygrenze mit besonderer 02.118-A-Verweigerung; (3) gemeinsame Reconnect-/FreshACL-/Cursor-/Snapshot-/DraftRevalidation; (4) OriginalOperationId-/Receipt-Abgleich der während des Abbruchs ungewissen Aktionen; (5) kontrollierte individuelle Submit-/Conflict-/Discard- und ggf. sichere DraftSave-Wege; (6) Multi-Tab-/Revocation-/Worker-/Backpressure-/VPSRecovery-/CrossSourceNegativtests; (7) B.2-B-Releasegate der tatsächlichen umfassenden NPC-/Combat-/Node-/Inventory-/Quest-/Roll-/Worldaktionen auch bei abruptem Disconnect.

| Fall | Erwartetes Verhalten |
|---|---|
| Spieler schreibt eigenes Notizfeld offline | Erlaubter lokaler Entwurf nur gemäß NoteOwner-/Field-/Retentionpolicy; erst aktueller fachlicher Save wird verbindlich |
| Spieler tippt Chattext offline | Nur flüchtiger Input; kein lokaler persistierter ChatDraft/AutoSend/AccountSync |
| Browser wird mit ungesendeter Chatnachricht neu geladen | Kein versteckter 02.118-A-ChatDraftRestore |
| Browser-Antwort nach Angriffs-/Würfelcommand geht verloren | OriginalOperationReceipt vor Retry; kein zweiter Angriff/Wurf/ResourceSpend |
| Move-Entwurf aus altem Turn wird später abgesendet | Aktuelle Turn-/Actor-/World-/RuleRevisionprüfung verweigert veralteten Zug ohne Gratisaktion |
| Gegner wird während Offlinezeit entdeckt oder versteckt | Kein altes Fog-/Known-/NPC-Leserecht; frische berechtigte Projektion |
| Spieler wurde aus Gruppe entfernt oder pausiert | Kein altes Member-/Party-/HistoricalAudience-Recht durch Offlinecache/Entwurf |
| GM wird gewechselt, alter SL-Tab besitzt Szeneentwurf | Kein GmEpoch-/Publish-/LiveWrite durch alten Tab; nach CurrentACL auflösen oder blockieren |
| Spieler wechselt Account auf gemeinsamem Browser | Fremde Entwürfe/Cache-/Source-/ActorDaten dürfen nicht in neue Session übernommen werden |
| SL-Preview bereitet eine WorldAction vor | ReadOnly-Grenze verweigert wirksames Senden; keine Player-Impersonation |
| NPC-/Quest-/Door-/Traktor-/Item-Automation will bei Reconnect alte Trigger nachholen | Keine unautorisierte Nachholung oder DoubleReplay; nur originäre aktuelle Fachpolicies |
| Server erhält zwei identische OperationIds | Nur der originale zulässige Commit-/Receiptstatus, nicht zwei WorldEffects |
| Alte Operation hat Status UNKNOWN und ist nicht klärbar | Nicht als Erfolg/Misserfolg ausgeben, nicht blind mit neuer OperationId erneut ausführen |
| Offline-Formular basiert auf fremder inzwischen gesperrter Source | Neue Field-/Source-/Ownerprüfung verweigert neue Saves und verdeckte Metadaten |
| Wiederverbindung nach ServiceRestart oder BackupRestore | Aktuelle Revocation-/Privacy-/Source-/Versionfences und kanonischer World-/Receiptzustand |
| Client erzeugt eigenen Würfelrohwert oder lokalen QuestReward | Kein wirksamer Domain-/WorldCommit, keine autoritative Roll-/RewardHistorie |
| Viele Offline-Entwürfe/Retryversuche | Fach-/Quota-/Requestschutz, keine ungebremste Sendewarteschlange |
| B.2-B-Kampagne überlebt reale Unterbrechung | Eine gemeinsame World, konsistente Character-/Actor-/Turn-/NPC-/Item-/Quest-/Roll-/Nodezustände, korrekte sichtbare Resultate |

## 6. Was später festgelegt wird und nächste Grundfrage

**B.7 C beschlossen:** Sichere lokale, fachlich tatsächlich zulässige Entwürfe; alte Offline-Anzeigen bleiben Lesesichten; wirksame Aktionen, Würfel, Quest-/NPC-/Item-/Turn-/Worldzustände und originale Receipts kommen nur vom VPS. **Keine** persistente Chatentwurfs-/AutoSend-Ausnahme; **kein** Offline-WorldFork, keine automatische Replay-/Wiederholungswelt.

**Später:** konkrete ClientStorage-Technik, Draft-Lebensdauern, Speicherung/Opt-in pro Fachmodul, UI/UX, Konfliktdialoge, konkrete Queue-/Retry-/Timeoutwerte, Eventfelder, unterstützte Offline-FieldKinds, Performance-/Quotabudgets, technische Implementierung und reale Tests. Eine generische universelle Offline-Sendqueue ist ausdrücklich nicht still erlaubt.

### B.8 – Wie wird der große erste B.2-B-Release fachlich nachweisbar abgenommen?

**Historische Entscheidungsfrage: B.8 wurde danach als C beschlossen; maßgeblich ist [der neue B.8-C-Fachentwurf](PHASE-B-WORKSHOP-B.8.md).**

- **A – Nur Unit-/Modultests mit grüner CI:** Prüft einzelne Komponenten, ist aber kein belastbarer Nachweis dafür, dass eine vollständige Spielrunde über mehrere Browser und Sicherheitsgrenzen funktioniert.
- **B – Erst in echten Spielrunden Fehler entdecken und fortlaufend korrigieren:** Verzichtet auf eine gemeinsame reproduzierbare Integrationsabnahme vor der ersten Freigabe und lässt Sicherheits-/World-/Reconnect-Regressionen schwer überprüfbar.
- **C – Versionierte genreunabhängige Referenzkampagne und modulübergreifende Release-Gates (Empfehlung):** Reproduzierbarer isolierter End-to-End-Spielablauf mit echten Kampagnen-/Actor-/Rule-/Node-/Combat-/NPC-/Roll-/Inventory-/Quest-/Fog-/History-/Reconnect-/Backup-Aktionen. Für erlaubte und abgewiesene Vorgänge OriginalReceipts, ein WorldWriter und Source-/Privacy-/Viewer-/Revocationprüfungen belegen. Zusätzliche passende RulePack-Varianten ohne Spezialcode möglich. Erst die belegte B.2-B-Gesamtstrecke darf als spielbare Freigabe gelten; konkrete Testszenen und CI-Technik später.
