# AdventureShift – Karten-Workshop: Beschluss 02.118 A – keine gespeicherten Chat-Entwürfe

**Stand:** 13.10.2026 – Fachbeschlüsse 02.1 bis 02.118; nächste offene Frage 02.119
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungsplan und Abnahmetests; **noch keine Softwareimplementierung**, kein finaler API-/Datenbankvertrag, keine fertige Oberfläche und keine endgültige MVP-Einstufung.
**Bezüge:** [02.25 – Kampagnenstandards/markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – eigenes Spielernotizbuch und technisch/manuell konfigurierbare Kampagnen](KARTEN-WORKSHOP-02.98.md) · [02.101–02.104 – unabhängige Systemmitteilungen/Acks](KARTEN-WORKSHOP-02.104.md) · [02.105 – integrierter Chat An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106 – Kanäle/DM-/Gruppenrechte](KARTEN-WORKSHOP-02.106.md) · [02.107 – aktuelle/historische Chat-Historie/Retention](KARTEN-WORKSHOP-02.107.md) · [02.108 – Edit/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Chatmoderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – Mutes/DM-Blocks](KARTEN-WORKSHOP-02.110.md) · [02.111 – Erwähnungen/Pings](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen/Emotes](KARTEN-WORKSHOP-02.112.md) · [02.113 – Replies/Zitate/Threads](KARTEN-WORKSHOP-02.113.md) · [02.114 – Anhänge/Previews](KARTEN-WORKSHOP-02.114.md) · [02.115 – Kanalpins/Bookmarks](KARTEN-WORKSHOP-02.115.md) · [02.116 A – keine Chat-Read-/Delivery-Receipts](KARTEN-WORKSHOP-02.116.md) · [02.117 – berechtigte Chatsuche](KARTEN-WORKSHOP-02.117.md) · [Kommunikationsworkshop 11](FEATURE-WORKSHOP.md).

**Nachfolgender Beschluss 13.7 C:** [Getypte feld-/quell-/edit-/validierungs-/saveberechtigte Formulare](UI-WORKSHOP-13.7.md) **dürfen niemals** 02.118-A-verbotene persistente/gerätesynchronisierte ChatDrafts, ChatAutoSave, ChatRestore oder ReconnectAutoSend über einen generischen FachEditor erzeugen. Ungesendeter Chattext bleibt höchstens flüchtig im aktuellen Feld; erlaubte persönliche Notizen und SL-SzenenDrafte sind andere echte Fachobjekte. V1 ein aktiver SL; Formular-/UI-Details später.

**Nachfolgender Beschluss 13.8 C:** [Geräteneutrale 13.5-Action-/13.7-Input-/13.3-Statuswege](UI-WORKSHOP-13.8.md) dürfen **keine** 02.118-A-verbotene ChatDraft-Persistenz, Keyboard-/AssistiveFocus-AutoSend, ungebetene TouchSend-/Reconnect-Wirkung aktivieren. Ungesendeter Chattext bleibt maximal flüchtig im aktuellen Eingabefeld, andere bewusst gespeicherte eigene SpielerNotizen bleiben eigene Fachobjekte. V1 ein SL, UI-Details später.

**Nachfolgender Beschluss 13.9 C:** [Optionale HelpTopics/Lernfortschritt](UI-WORKSHOP-13.9.md) umgehen **nicht** das 02.118-A-Verbot persistenter ChatDrafts und Reconnect-AutoSends. TutorialHelp zu Chat/DM darf ausschließlich heute wirklich berechtigte, abgeschlossene oder flüchtig dargestellte zulässige UI-Funktionen zeigen; kein ungesendeter Nachrichtentext im LearningProgress/Telemetry/Auditcache. V1 ein SL, Hilfetexte später.

**Nachfolgender Beschluss 13.12 C:** [Sicher revalidierte optionale UI-/Pane-Wiederaufnahme](UI-WORKSHOP-13.12.md) **ändert nicht** die hier beschlossene negative ChatDraft-Regel: ungesendeter MessageText bleibt höchstens flüchtig im aktuellen Feld; keine Local-/Server-/ServiceWorker-/Account-/BrowserResume-Persistenz, kein ChatAutoSend nach Neuverbinden. Echte gespeicherte Notizen sind eigene DomainRevisions, kein getarnter ChatDraft. V1 ein SL, TTL/UI später.

**Nachfolgender Beschluss 14.2 C:** [BrowserSessionLogout/Reauth/Revoke/Deviceverwaltung](SICHERHEIT-WORKSHOP-14.2.md) führt keine Ausnahme von **02.118 A** ein: ungesendete Chattexte bleiben nicht persistent/geräteübergreifend synchronisiert und werden weder bei Reconnect noch nach neuer SteamAnmeldung automatisch abgesendet. Andere berechtigte bereits gesendete ChatMessages haben weiterhin eigenständige Source-/History-ACL. V1 ein SL, UI später.

## 1. Verbindliche Entscheidung – Variante 02.118 A

**Der Projektinhaber hat ausdrücklich A gewählt: AdventureShift bietet keine dauerhaft oder kontogebunden gespeicherten, später wiederherstellbaren Chat-Entwürfe.** Ungesendeter Nachrichtentext ist höchstens **flüchtiger Inhalt im aktuell geöffneten Chat-Eingabefeld**. Die Anwendung plant weder serverseitige oder lokale Draft-Persistenz noch geräteübergreifende Entwurfs-Synchronisation, gespeicherte Entwurfsversionen oder ein eigenes Draft-Archiv. Ein Browser-/Seitenneuladen, Schließen, Wechsel aus der Eingabemaske oder App-Neustart bietet **keinen von AdventureShift garantierten Entwurfs-Restore**.

**A ist kein versteckter C-Modus:** Die generelle 02.98-Anforderung „die meisten geeigneten Funktionen schaltbar“ gilt weiterhin, **aber diese ausdrücklich abgelehnte Draft-Speicherfunktion darf nicht durch 02.25-Kampagnen-, Rollen- oder Kanalausnahmen still aktiviert werden**. Keine Entwurfs-Autosave-/Restore-Einstellung bei Kampagnenerstellung anbieten. Eine spätere Einführung wäre eine neue fachliche Entscheidung.

**Beispiel:** A tippt in einem erlaubten Gruppenchat eine Nachricht. Während der Browser mit demselben Eingabefeld geöffnet bleibt, kann dieser Text noch im Arbeitsspeicher der aktuellen Oberfläche stehen – auch bei kurzem Netzwerkabbruch. Nach einem Reload oder neuem Login gibt es jedoch keine eigens durch AdventureShift gesicherte Wiederherstellung auf einem anderen Gerät. **Nur die bewusste Sendeaktion** kann nach erneuter aktueller serverseitiger Berechtigungsprüfung eine echte Chatnachricht erzeugen; Reconnect allein sendet nichts.

**Nicht gewählt:** B (ungeprüfte Entwurfsspeicherung mit Autosenden nach Reconnect) und C (konfigurierbare lokale/Server-/Mehrgeräte-Draft-Persistenz). Die unabhängigen **frei selbst verfassten Spielernotizen nach 02.94–02.97** bleiben unverändert gespeichert und nutzbar. Ein Spieler darf Hinweise absichtlich dort notieren, statt eine ungesendete Chatnachricht als Notizarchiv zu verwenden.

## 2. Fachliche Grenzen: Was existiert und was nicht

| Bereich | Gemäß 02.118 A | Keine stillschweigende Zusatzfunktion |
| --- | --- | --- |
| **Offenes Texteingabefeld** | Der aktuell getippte, noch ungesendete Text kann flüchtig in dieser UI existieren | Kein eigenständiger dauerhafter Entwurfsdatensatz |
| **Lokale Browser-Speicherung** | Anwendung legt keinen Draft in localStorage, sessionStorage, IndexedDB, Cache Storage oder vergleichbarer eigener Persistenz ab | Kein „letzten Entwurf wiederherstellen“, keine versteckten Service-Worker-Outboxes |
| **Backend/Konto** | Kein Entwurfs-Upload, Draft-Read-/Write-Endpunkt und keine Entwurfstabelle für gewöhnliche Chats | Keine Cloud-/Gerätesynchronisation, kein SL-Draft-Dashboard |
| **Offline-Verbindung** | Solange dieselbe Eingabemaske offen ist, kann Text flüchtig stehen bleiben; tatsächliche Sendung erfordert Verbindung und heutigen Sendeguard | Kein offline gespeicherter Versandauftrag, kein automatischer Retry nach Reconnect |
| **Verlauf/Chat-Suche** | Nur wirklich gesendete und zulässig verfügbare 02.107-Nachrichten sind Chatverlaufs-/02.117-Suchobjekte | Ungesendeter Text darf nicht heimlich im Historyindex, Export oder Search auftauchen |
| **Medien/Anhänge** | 02.114-zulässiges temporäres Quarantäne-Staging ist eine eigene begrenzte Uploadphase, keine Draft-Speicherung | Nicht gesendete Stagingmedien nicht als wiederherstellbare Entwürfe/Handouts umwidmen |
| **Notizen und Systembelege** | 02.94–02.98 persönliche Notizen sowie 02.101–02.104 amtliche Notices/Acks bleiben eigenständige Daten | Keine Löschung dieser echten Daten durch Draft-Aus |
| **Nachrichtenverarbeitung** | Eindeutig bewusst gesendeter Inhalt kann als neue berechtigte Nachricht verarbeitet werden | Entwurf ist nicht „bereits gesendet“, nicht zugestellt/gelesen und kein World-Event |

**Browsergrenze ehrlich behandeln:** Browser, Betriebssystem, Eingabemethoden oder Erweiterungen könnten außerhalb des von AdventureShift gesteuerten Speichers eigene Formulardaten halten. 02.118 A garantiert daher **keine durch AdventureShift angebotene oder angelegte Draft-Persistenz**, nicht die technische Unmöglichkeit externer Browser-Wiederherstellung. App-kontrollierte Formular-/Cache-/Service-Worker-Restorepfade sind auf unerwünschte Speicherung zu prüfen.

## 3. Senden, Verbindungsabbruch und Rechtewechsel

1. **Nur expliziter Versand:** Ein tatsächlicher 02.106-Chat-Sendebefehl entsteht erst durch bewusstes Auslösen durch den Nutzer. Weder Verbindung zurück, neuer Browser-Tab, Wiederanmeldung, Wechsel in die Szene, Aufwachen eines Geräts noch alte Eingabe-/Attachment-/Quote-/Mentionreferenzen dürfen automatisch eine Chatnachricht anstoßen.
2. **Prüfung beim konkreten Send-Commit:** Auch wenn der Text vor dem Disconnect bereits im aktuellen Eingabefeld stand, prüft der autoritative Server unmittelbar beim späteren bewussten Senden **02.105 Chat An**, die reale Account-/Kampagnen-/Kanal-/Empfänger-/Gruppen-/Rollenrechte aus 02.106, 02.109-Sendrestriktionen, 02.110-DM-Blocks sowie tatsächlich einschlägige 02.111–02.114-Mention-/Emote-/Quote-/Mediarechte samt aktuellen Policy-/Nachrichtenversionen. Eine frühere Freigabe ist keine spätere Sendegenehmigung.
3. **Chat-/Kanalwechsel:** Beim verlassenen oder geschützten Chatbereich flüchtige Eingabe nicht unbeabsichtigt in einen anderen Channel, eine andere Kampagne oder an eine neu gewählte DM-Person übernehmen. Kein geheimer Inhalt als vermeintlich neuer Draft in fremdem Chat, Kanal-Autocomplete, Logs oder Analytics. Dass Eingaben beim Wechsel verloren gehen können, ist eine bewusste Folge von A; genaue UI-Hinweise werden später entschieden.
4. **In-flight-Send ist kein Draft:** Wurde die Sendetaste **vor** dem Disconnect betätigt, kann die echte Operation am Server angenommen worden sein, auch wenn der Client noch kein Ergebnis sah. Für diesen Fall nach 02.105–02.110 die autoritative Sendestatus-/OperationId-/Idempotenzkontrolle verwenden; **kein stilles nochmaliges Senden** bei Reconnect und keine wahrheitswidrige Behauptung „wurde garantiert nicht versendet“. Nötigenfalls eigenen technischen Status abgleichen oder eine bewusste erneute Sendeentscheidung treffen.
5. **02.116 A gilt fort:** Wahrheitsgemäße eigene technische Serverannahme/Ablehnung ist kein individueller 02.116-Recipient-Delivery-/Read-Receipt. Ob eine fremde Person geöffnet/gelesen hat, bleibt ebenso unbekannt wie zuvor; keine neue Lesestatusspur aus ungesendeter Eingabe.
6. **Keine Daten aus Freitext ableiten:** Eingabefeld, Erwähnung, Emote, mitgetippter Code, vorbereitete URL oder Text „Tür öffnen“ sind bis zur wirksam autorisierten typisierten Aktion ohne echte NPC-/Quest-/Würfel-/Inventar-/Tür-/Alarm-/Node-/Timer-/Next-Player-/Turnwirkung. Auch eine gesendete Chatnachricht ist ohne gesonderten 02.99-Servercommit kein Spielmechanikbefehl.

## 4. Anhänge, Replies, persönliche Filter und bestehende Rechte

**02.114-Medienstaging:** Ein noch nicht an eine tatsächlich berechtigt gesendete Nachricht gebundener Upload kann vorübergehend in sicherer 02.114-Quarantäne stehen. Er ist **kein** gespeicherter Draft; ein abgebrochener Upload wird nach eigener begrenzter Staging-/Quoten-/Cleanup-Policy entfernt und nicht per anderer Kanal-/Kampagnen-ID wiederverwendet. Nur ein echter erneuter Chat-Send-Commit bindet eine geprüfte Datei an eine berechtigte Nachricht. Nicht automatisch ein zuvor stagingberechtigtes Asset öffentlich machen oder eine bereits wirklich gebundene/gesendete Datei wegen 02.118 A löschen.

**02.111-/02.113-Kontexte:** Flüchtige noch nicht versendete `@Person`-/`@Gruppe`-Erwähnungen, Antworten, Parent-/Threadlinks und Quote-Previews garantieren keinerlei spätere Ziel-/Gruppen-/Root-/Empfängerrechte. Beim bewussten Senden müssen 02.111-/02.113-Scopes und bei tatsächlichen verknüpften Medien 02.114-Scopes vollständig neu geprüft werden. Keine gespeicherte Empfänger-/Quote-/Mentionliste als verstecktes Draft-Backend.

**02.108/02.107-Lebenszyklus:** Ein Text im Eingabefeld ist **keine** gesendete Message-Revision. Erst nach bewusstem gültigem Senden können eine Chat-Message-ID, echte 02.107-historische Recipientbindung, konfigurierbare Retention, 02.108-Edit-/Withdrawrechte und 02.117-Suche entstehen. Alte gültige Chatnachrichten bleiben nach bisherigen heutigen **UND historischen** Quell-/Empfänger-/Geheimnisrechten lesbar; A ändert daran nichts.

**02.109-/02.110-Schutz:** Moderation und Kanal-/Personensendrestriktionen gelten vor dem späteren Senden. Persönliche Kanal-Stummschaltung oder DM-Kontaktblockierung wird nicht durch flüchtigen Text oder vorher gespeicherte Empfängervorschläge umgangen. Keine private Blockliste oder geheime Channel-/Actor-Zugehörigkeit durch Verbindungs-/Sendefehler offenlegen.

**Unabhängige Arbeit:** Eigene Spielernotizen, Kartenmarker, Würfel-/Systemlog, die bei Kampagnenerstellung separat optionalen Missionen und externe Voicechat-Gespräche funktionieren auch ohne Chat oder trotz verlorenen Eingabetexts weiter. 02.102 ausdrücklich persönlich quittierte wichtige **offizielle** Notices sind weiterhin getrennt; keine Quittierung durch getippten, verworfenen oder gesendeten Chattext.

## 5. Architekturentscheidung und Umsetzungsplan – noch kein Code

**Negativer Architekturentscheid:** **Keine** neuen produktseitigen `ChatDraft`-, `ChatDraftHistory`-, `ChatDraftSync`-, `ChatDraftAutosave`-, `ChatPendingOfflineOutbox`- oder `ChatDraftRestore`-Services, Backendtabellen, APIs, Offline-Queues oder lokalen Persistenzadapter für ungesendete Chatnachrichten vorsehen. Eine rein flüchtige `ChatComposerState`-Komponente kann während der aktuellen Eingabe existieren; sie ist kein fachlich persistentes Datenobjekt. 02.114-`ChatMediaStagingObject` sowie tatsächlich eingereichte `ChatSendOperation` und legitime System-/Transportbelege sind getrennt zu modellieren.

**Umsetzungsplan:**
1. **Funktion abgrenzen:** 02.118 A als bewusstes Nicht-Feature im 02.25-/02.105-Settingsinventar und Kommunikations-Backlog festhalten; kein konfigurierbarer Draft-Toggle trotz allgemeinem Prinzip konfigurierbarer Komfortmodule.
2. **Ephemeren Composer entwerfen:** Eingabe nur in aktuellem Chat-/Kanal-/Rollen-/UI-Kontext halten; bei Reload/Logout/Tababschluss keine von der App bereitgestellte gespeicherte Rekonstruktion. Keine Speicherung in Browserstorage, Web-Persistenz, Service-Worker-Queue, Server, Telemetrie oder History.
3. **Explizite Sendegrenze:** Einheitliche autoritative 02.106-/02.109-/02.110-/02.111–02.114-Guards beim tatsächlichen Senden; keine Reconnect-Auto-Sends, keine Retargeting- oder Draft-to-World-Aktionen.
4. **Race-/Disconnect-Schutz:** Bereits ausgelöste echte Sendoperation per idempotenter OperationId und sicheren eigenen Serverannahmebelegen verfolgen, ohne zu behaupten, die Nachricht sei beim Empfänger angekommen oder gelesen (02.116 A). Ein ungesendeter Composertext ist dagegen niemals eine automatisch wiederaufgenommene Sendewarteschlange.
5. **Staging-/Datenschutzkontrolle:** 02.114-quarantänisierte ungebundene Uploads begrenzt bereinigen; beim Chatwechsel, Rollenentzug, Restart, Multi-Device und Clientcache keine vertrauliche Eingabe in falschen Channel oder fremde Kontoansicht übertragen.
6. **Abnahmetests und UI später:** Fälle aus Abschnitt 6 prüfen; etwaige Warnung „ungesendeter Text geht beim Wechsel verloren“ ist eine spätere UI-Entscheidung, kein versteckter Draft-Store. Keine neue MVP-/DB-/API-/UX-Festlegung ohne Gesamtworkshop.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Chat An, Spieler schreibt ohne Senden | Text bleibt nur im aktuell geöffneten Eingabefeld, ist keine Server-Message |
| Seite neu laden oder Browser schließen | Keine von AdventureShift gespeicherte Nachricht als Draft wiederherstellbar |
| Spieler meldet sich auf Zweitgerät an | Kein geräteübergreifender Draft aus erstem Eingabefeld |
| Offline während Eingabe, UI bleibt geöffnet | Text darf flüchtig im Eingabefeld stehen bleiben, aber keine automatische Sendung/History |
| Reconnect nach Offline-Text | Ohne erneute bewusste Sendetaste **keine** neue Chatnachricht |
| Benutzer hat Sendetaste kurz vor Netzabbruch betätigt | Serverseitige OperationId korrekt abgleichen, keine unbeabsichtigte Doppelsendung; Empfänger-Lesestatus bleibt unbekannt |
| Spieler wechselt während Eingabe die Kampagne/Gruppe | Text wird nicht unerkannt als Nachricht in anderem Kontext übernommen oder dort als Draft gespeichert |
| SL deaktiviert `Chat` bei Kampagnenänderung | Keine normalen neuen Send-/Draft-/Historypfade, ungesendeter Eingabetext verursacht keine Veröffentlichung |
| Ehemals erlaubter Chat-Sender verliert Senderecht | Bewusstes späteres Senden serverseitig nach aktuellem Recht abgewiesen, keine Draft-Freigabe |
| B blockiert As neue DMs zwischen Tippen und Senden | DM-Senderblock greift auch bei altem Composertext, keine falsche Zustellzusage/Blocklistenoffenlegung |
| Alte eingegebene `@Gruppe`-Erwähnung nach Gruppenwechsel | Kein unberechtigter Ping und keine geheimen Gruppendaten, heutige 02.111-Targetberechtigung nötig |
| Antwort-/Threadreferenz beim Tippen zulässig, später Parent entzogen | Aktuelle UND historische 02.113-Parent-ACL erneut prüfen, kein Quell-/Quote-Leak |
| Datei im 02.114-Staging angelegt, Senden abgebrochen | Sicheres begrenztes Staging-Cleanup statt gespeicherter Draft-Datei oder öffentliches Asset |
| Datei bereits rechtmäßig in echte gesendete Message gebunden | 02.118 A löscht sie nicht als vermeintlichen Entwurf, 02.107-/02.114-Rechte unverändert |
| Nicht gesendeter Text enthält Suchbegriff | Kein Ergebnis in 02.117-Chat-Suche, Index, Export, Unread-Count oder Realtime |
| Eigene 02.94-Freitextnotiz wurde gespeichert | Diese Notiz bleibt unabhängig verfügbar; Chat-Draft-A betrifft sie nicht |
| Bereits echt gesendeter Text hat gültige 02.107-History | Gewöhnliche erlaubte Historien-/Retentionrechte bleiben, keine rückwirkende Chatlöschung |
| Serverseitige 02.109-Moderationssperre greift | Kein Senden über alte Eingabe, Reconnect, Quote/Emote oder Attachment-Umweg |
| Reconnect erhält eigenen `server angenommen`-Beleg | 02.116 A weiterhin kein `B zugestellt/gelesen`-Tracking |
| Benutzer öffnet, tippt und schließt einen Chat | Keine durch die App gespeicherte Composer-History in Browserlocalstorage/IndexedDB/Service-Worker |
| Spieler schreibt `/me öffnet Tür` oder Code im Eingabefeld | Kein NPC-/Quest-/Tür-/Node-/Turn-/Würfel-/Inventareffekt |
| Echte 02.101-Mitteilung erfordert 02.102-ACK | Keine automatische Quittierung durch Eingabe, Disconnect, Reconnect oder Chatnachricht |
| Chat ist dauerhaft Aus, Gruppe spielt Voicechat-first | Private Notizen, SL-Aktionen, Würfel und echte Systemprotokolle unabhängig vorhanden |

## 7. Beschlussgrenze und nächste Featurefrage

**Verbindlich beschlossen: 02.118 A – keine gespeicherten Entwürfe.** Nicht versendeter Chatinhalt existiert höchstens flüchtig im aktuellen UI, ohne von AdventureShift gewährleistete Wiederherstellung, kontogebundene Draft-Daten, Offline-Outbox oder geräteübergreifenden Entwurfsabgleich; insbesondere **kein automatisches Senden beim Reconnect**. Nur eine bewusste Chat-Sendeaktion nach frischer serverseitiger 02.105-/02.106-/02.109-/02.110-/02.111–02.114-Prüfung darf eine wirkliche 02.107-Nachricht erzeugen. 02.115-Bookmarks, 02.116 A ohne individuelle Chat-Lesebestätigungen und berechtigte Suche gemäß 02.117 C bleiben unverändert. 02.94-Freitextnotizen und offizielle 02.101–02.104-ACKs sind unabhängige Module.

**Nicht beschlossen:** Ein optionaler lokaler Draft-Store, Wiederherstellen nach Reload, Draft-Autosave, Mehrgeräte-Synchronisierung, automatische Offline-Sendqueue, feste UI-Verlustwarnungen, neue dauerhafte Chat-Logs oder finaler MVP-/DB-/API-Entwurf. Allgemeine Sicherheit und Rechteprüfung sind keine deaktivierbaren Optionen.

## Nächste Entscheidung 02.119 – Schreibindikatoren und Online-/Anwesenheitsanzeigen

**Beispiel:** Spieler A tippt eine Gruppenchatnachricht. Die anderen könnten „A schreibt …“ oder eine Online-Markierung sehen. Andere Spieler möchten ihre Anwesenheit jedoch nicht verraten, insbesondere nicht in fremden DMs, geheimen Gruppen oder trotz 02.110-Kontaktblock.

- **A – Keine Anwesenheits-/Schreibindikatoren:** Keine `tippt gerade`-, `online`- oder `zuletzt aktiv`-Anzeige für andere Teilnehmer im integrierten Chat.
- **B – Unbegrenzte Präsenzanzeige:** Jeder kann jederzeit alle Teilnehmer, Aktivitäten, Tippen und persönliche Zeiten auch außerhalb berechtigter Kanäle oder bei blockierten Kontakten sehen.
- **C – Konfigurierbare berechtigte und datensparsame Präsenz (Empfehlung):** Optional nur in aktivem 02.105-Chat und wirklich erlaubten 02.106-Kanälen, mit 02.25-Defaults/markierten Ausnahmen und eigenen Privatsphäre-/02.110-Block-/Mutegrenzen. Keine geheimen Gruppen-/DM-/Empfängeridentitäten, keine Aufbewahrung persönlicher Tipp-/Aktivitätszeitlinien, **keine 02.116-A-Read-/Delivery-Receipts** und keine automatische Nachricht oder Weltwirkung; genaue UI später.
