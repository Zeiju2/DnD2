# AdventureShift – Karten-Workshop: Beschluss 02.126 C – geschützte, konfigurierbare Chat-Benachrichtigungen

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.126; nächste offene Frage 02.127
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungs-/Abnahmeplan; **noch keine Softwareimplementierung**, keine finalen APIs, Datenbankverträge, UI, Standardzeiten, Sounds oder MVP-Einstufung.
**Bezüge:** [02.25 – Kampagnenstandards/markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – freie Notizen/optionale Kampagnentechnik](KARTEN-WORKSHOP-02.98.md) · [02.101–02.104 – offizielle Mitteilungen, bewusste ACKs, Reminder](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus bei Kampagnenerstellung](KARTEN-WORKSHOP-02.105.md) · [02.106 – Kanal-/DM-/Gruppen-/SL-Rechte](KARTEN-WORKSHOP-02.106.md) · [02.107 – heutige UND historische Empfängersicht/Retention/Unread](KARTEN-WORKSHOP-02.107.md) · [02.108 – Edits/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – Kanal-Mutes/DM-Senderblocks](KARTEN-WORKSHOP-02.110.md) · [02.111 – berechtigte Mentions/Pings](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen/Emotes](KARTEN-WORKSHOP-02.112.md) · [02.113 – Replies/Threads](KARTEN-WORKSHOP-02.113.md) · [02.114 – Medien/Textlinks](KARTEN-WORKSHOP-02.114.md) · [02.115 – Pins/private Lesezeichen](KARTEN-WORKSHOP-02.115.md) · [02.116 A – keine Lesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.117 – Chat-Suche](KARTEN-WORKSHOP-02.117.md) · [02.118 A – keine gespeicherten Drafts](KARTEN-WORKSHOP-02.118.md) · [02.119 – kurzlebige Präsenz/Typing](KARTEN-WORKSHOP-02.119.md) · [02.120 – Umfragen](KARTEN-WORKSHOP-02.120.md) · [02.121 A – Klartext mit Absätzen](KARTEN-WORKSHOP-02.121.md) · [02.122 A – keine Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.123 A – keine Weiterleitung](KARTEN-WORKSHOP-02.123.md) · [02.124 A – keine Übersetzung](KARTEN-WORKSHOP-02.124.md) · [02.125 A – keine Chat-Exporte/Druckansicht](KARTEN-WORKSHOP-02.125.md) · [Kommunikationsworkshop 11](FEATURE-WORKSHOP.md).

**Nachfolgender Beschluss 13.3 C:** [Read-only projizierter DomainAction-/Receipt-/Pendingstatus](UI-WORKSHOP-13.3.md) ist keine zusätzliche 02.126-Chatbenachrichtigungsquelle und ändert keine Channel-/DM-/Recipient-/History-/Read-/Mute-Rechte. Wenn die Chatbenachrichtigung berechtigt auf eine Fachaktion verweist, gelten bei LinkOpen aktuelle Source-/Action-/Actor-/Recipient-/Historyrechte, keine Fremd-Secret-/Counts. V1 ein SL, UI später.


## 1. Verbindlicher Beschluss – Variante 02.126 C

**Der Projektinhaber wählt C: Die SL kann beim Erstellen einer Kampagne die vom 02.105-Chat unabhängigen, zusätzlich schaltbaren Chat-Benachrichtigungsarten nach 02.25-Kampagnen-/Regel-/Kanaltyp-/Kanal-/Gruppen-/Rollen-/Personenstandards und fachlich gültigen markierten Ausnahmen konfigurieren.** Spieler dürfen innerhalb dieser tatsächlich verfügbaren Funktionen ihre **eigenen** Pop-up-, Ton-, Desktop-/Browser-, Kanal- und Erwähnungspräferenzen verwalten. Eine persönliche Präferenz darf aber weder geheime Inhalte freigeben noch 02.110-Mute-/DM-Block-/Empfängerrechte übersteuern.

**Mögliche voneinander getrennte, optional zuschaltbare Kanäle:** stille persönliche Unread-/Mention-Badges, dezente In-App-Toasts beim Kartenspiel, eigenständige Benachrichtigungstöne und Browser-/Desktop-/OS-Hinweise. Bereits existierende nach 02.107/02.111 rechtmäßige passive Zähler und Mentionpfade bleiben eigenständig; 02.126 ergänzt bei aktivem Chat die konkrete **Benachrichtigungszustellung**, nicht automatisch neue Nachrichteinsichts-/Lesestatusrechte.

**Beispiel:** A spielt auf der Karte. In einem für A wirklich aktuell UND historisch zulässigen Teamkanal schreibt B eine Nachricht. Falls Kampagne/Kanal und As persönliche Einstellungen In-App-Hinweise erlauben und der Kanal nicht stummgeschaltet ist, kann A einen kurzen Hinweis erhalten. Falls A nur stille Badges möchte, bleibt der Toast aus. Falls die neue Nachricht eine aktuell berechtigte 02.111-Erwähnung enthält, kann dafür eine **separat erlaubte** Benachrichtigungsart gelten. Ein Spieler C ohne historische Empfängerberechtigung erhält weder Vorschautext noch Nachrichtenzahl/Autor/Channel-Metadatum.

**Nicht gewählt:** A (über die bisherigen passiven Anzeigen hinaus gar keine Benachrichtigungen) und B (ungefilterte Zustellung aller Nachrichten trotz Geheimnissen/Mute/Blocks). Unter C dürfen Kampagnen und Nutzer **alle zusätzlichen Chat-Pop-ups/Töne/Desktop-Hinweise deaktivieren**. Das bereits ausdrücklich beschlossene **02.116 A – keine individuellen Read-/Delivery-Receipts** bleibt ebenso wie **02.118 A – keine Draftspeicherung** unangetastet.

## 2. Granulare Konfiguration und wirkliche Berechtigungen

| Einstellbarer Bereich | Fachliche Option unter 02.25/02.105 | Verbindliche Sicherheitsgrenze |
| --- | --- | --- |
| **Chat-Benachrichtigungen An/Aus** | Kampagnenstandard sowie gültige konkrete Kanal-/Gruppen-/Rollen-/Personenausnahmen | 02.105 Chat Aus schaltet normale Chatbenachrichtigungen tatsächlich ab |
| **Stiller Badge / eigene Unreads** | Eigene erlaubte, ggf. schon 02.107/02.111-vorhandene Zähler getrennt von Sounds/Pop-ups | Nur selbst berechtigte Nachrichten zählen; kein fremder DM-/Secret-/Voter-Count |
| **In-App-Toast** | Optional bei neuer berechtigter Nachricht im anderen geöffneten Chat oder bei Kartenansicht | Nur aktueller für diese Person zulässiger Absender-/Channel-/Textausschnitt |
| **Ton** | Separat erlaubter dezenter lokaler Hinweiston, ggf. pro Kanal/Kategorie unterschiedlich | Nicht 02.51-Szenensound oder Welt-/NPC-/Sensor-/Alarmnode auslösen |
| **Browser-/Desktop-/OS-Hinweis** | Nur bei angebotener Plattformunterstützung und **eigener ausdrücklicher Benutzerfreigabe** | Kein automatisch erzwungener OS-Permissionprompt, Lock-Screen-/Multidevice-Privacy schützen |
| **Ereignistypen** | Neue Kanal-/Gruppen-/DM-Nachricht, berechtigte 02.111-Mention, ggf. ausdrücklich optierte 02.112-Reaktion, 02.113-Reply, 02.115-Pin und 02.120-Poll getrennt | Kein `@alle`-/Massen-Ping ohne 02.111-Send-/Empfängerrecht; 02.119-Typing/Online erzeugt kein stilles Tracking |
| **Individuelle Präferenzen** | Persönlich Ton/Toast/Desktop/Preview, erlaubte Kanalarten, optional Ruhezeiten/„Nicht stören“ wählen | Persönliches Opt-in kann Kampagnenverbot, tatsächliche Quellrechte oder Mute/Block **niemals** übersteuern |
| **Vorschautext / Absender / Kanal** | Nur wenn bewusst erlaubt und zum Zustellzeitpunkt heute UND historisch sichtbar; möglichst sparsame Vorschau | Standardkonzept für externe/Lock-Screen-Hinweise ist neutraler Text ohne private Namen/Geheimnisse |
| **Ruhezeiten / Bündelung** | Optional Benachrichtigungen während Ruhezeiten unterdrücken, drosseln oder aggregieren | Keine Secret-Leaks durch Aggregate, spätere Nachlieferung oder Beschriftung |
| **Sicherheits-/Systemmeldungen** | Normale Chatpräferenzen nicht als Universalfilter für gesonderte 02.101–02.104-Notices missbrauchen | Amtliche ACK-/Reminder-/Moderationsrechte sind unabhängig, nie automatische Chat-Lesebestätigung |

**Konzeptionelle Rechte:** `configureCampaignChatNotifications`, `setOwnChatNotificationPreferences`, `receiveAllowedChatBadge`, `receiveAllowedChatToast`, `receiveAllowedChatSound`, `receiveAllowedDesktopNotification` und `viewAllowedChatNotificationPreview`. Ein Kanalbesitzer/SL darf nicht schlicht `notifyAnyUserAboutAnyDM` erhalten. Einstellungen an Kanal, Rolle und Empfänger sind als **effektive Policy** zu berechnen; eigene Nutzerpräferenzen verengen die individuell angebotene optionale Zustellung.

## 3. Serverautorisierung, Mutes und Geheimnisschutz

1. **Vor Nachricht-/Eventannahme:** Es gelten alle tatsächlichen 02.105-/02.106-Sende-/Rollen-/Gruppen-/DM-/SL-/02.109-Moderations- und 02.110-Senderblockregeln; ein abgewiesener Sendebefehl erzeugt keine falsche „Neue Nachricht“-Zustellung.
2. **Vor jeder optionalen Empfängerzustellung:** Echten Account, Kampagnen-/Channel-/Personen-Policy, 02.110-Mute/Block, 02.111-Mention-/Gruppen-/`@alle`-Rechte, 02.107-**ursprüngliche historische UND aktuell gültige** Recipient-/Message-/Fog-/Secret-/NPC-/Quest-/Notiz-/Wurf-/Retentionrechte sowie 02.108-Revision/Withdraw und 02.109-Suppression/Restriktionen erneut prüfen. Keine unberechtigten Altgruppenbenachrichtigungen für Neubeigetretene.
3. **Bei Klick/Aufruf erneut prüfen:** Ein Toast oder ein OS-Hinweis ist **keine** Leseberechtigung und kein dauerhafter Downloadlink; Navigation zur Message/02.113-Thread-/02.114-Dateiquelle erfordert die **heutige UND historische** 02.107-Quellberechtigung zum tatsächlichen Öffnungszeitpunkt.
4. **Mute und DM-Block vorrangig:** Persönlicher 02.110-Kanalmute unterdrückt optionale Töne/Toasts/Desktopzustellung und entsprechende Pings, ohne zulässige History-/Search-/passive eigenen Unreadanzeigen automatisch zu löschen. Echte DM-Senderblockierung verhindert **neue** Chat-/Mention-/Reaktions-/Poll-/Pinbenachrichtigungen als gerichtete Umgehung; persönliche Blocklisten und konkrete Gründe bleiben privat. Der berechtigte gemeinsame Gruppenchat hat eigene Empfängerrechte, wird aber nicht zu einem heimlichen DM-Kanal.
5. **Private Inhalte und OS-Lock-Screens:** Externe OS-/Desktop-Notifications können auch bei gesperrtem Bildschirm oder in anderen Nutzerkontexten sichtbar werden. Default ohne Absender-/Channel-/Text-/Dateinamen-/Thumbnail-/Polloption-/Secret-Vorschau; nur eigens zugelassene feinere Vorschauen nach realer ACL. Für riskante Inhalte neutrale `Neue Nachricht`-Formulierung und optional vollständige Unterdrückung; keine pauschale Übertragung fremder DMs an Notification-Drittanbieter.
6. **Counts/Metadaten schützen:** Zähler, Stacks, Vorschau, Icons, Autor, Sendername, Gruppentitel, DM-Teilnehmer, `B reagierte`, Pollvote/-Result, `geheime Gruppe hat 3 neue Nachrichten` oder Push-Timing dürfen für Unberechtigte **keine Existenzorakel** sein. Aggregation nur über zuvor pro Empfänger autorisierte Ereignisse.
7. **Keine zusätzlichen personenbezogenen Receipts:** Eine ausgelieferte, angezeigte, stummgeschaltete oder weggeklickte Benachrichtigung erzeugt **keinen** individuellen 02.116-A-`received/read/opened`-Status an den Absender und **keinen** 02.102-ACK. Betriebstechnische Zustellfehler sind keine persönliche Bestätigung tatsächlicher Kenntnisnahme.
8. **Offizielle Notices unabhängig:** Bereits ausdrücklich berechtigte 02.101-/02.102-/02.103-/02.104-Pflichtmitteilungen, Erinnerungen und gesetzlich legitime 02.109-Sicherheitsinformationen behalten ihre eigenen Empfänger-/Hinweis-/ACKrechte; normale Chat-Mutes und Komfort-Schalter unterdrücken sie nicht pauschal. Sie sind aber **keine** frei nutzbaren SL-Chat-Massenping-Bypässe.

## 4. OS-Berechtigungen, Offline, Datenschutz und Eventlebenszyklus

**Browser-/OS-Benachrichtigung:** Plattformbezogene Permission nur nach bewusstem Benutzer-Opt-in erfragen. Wenn der OS-Status verweigert/entzogen oder die Plattform nicht unterstützt ist, darf AdventureShift keine Desktopbenachrichtigung behaupten; In-App-/Badge- und andere wirklich erlaubte Varianten bleiben eigenständig. Kein heimliches Aktivieren von OS-Tönen/Permission bei Kampagnenerstellung durch die SL. Desktopbenachrichtigung ist eine zustellbare Komfortnachricht, **keine garantierte Aufmerksamkeit oder Lesebestätigung**.

**Reconnect / Offline / Warteschlangen:** Bei kurzzeitigen Verbindungsproblemen dürfen höchstens zweckgebundene, begrenzte und geheimnisgeschützte Benachrichtigungsreferenzen für eine tatsächlich unterstützte Nachzustellung existieren. **Vor jedem Retry erneut die vollständige aktuelle UND historische 02.107-Message-/Recipient-/Retention-/02.108-/02.109-/02.110-Policy prüfen**; bei widerrufenem Recht, expired Message, Chat Aus, deaktivierter Präferenz oder Kanal-Mute keine Nachlieferung. Keine unabhängige dauerhafte Chattext-/Attachment-Schattenkopie als Notification-Queue. Gewisse einmal bereits an einen OS-Notification-Dienst übermittelte/auf einem fremden Gerät gezeigte Vorschauen lassen sich technisch nicht rückwirkend zurückholen – deshalb minimaler Payload und Privacy-by-Default.

**Mehrgeräte/Mehrfachzustellung:** Ein einzelner Account mit mehreren Sitzungen darf kein neues Multiplayer-Recipientrecht und keine automatische Lesebestätigung erhalten. Wenn möglich Geräte-/Session-bezogene Entkopplung bzw. Deduplikation, stabile Event-/Message-/Revision-/Recipient-ID, Rate-/Spamgrenzen, Bündelung, stale Timer/Retry und versionssichere Änderungen an Mutes/Blöcken/Präferenzen; keine mehrfachen überlauten akustischen Ereignisse durch konkurrierende Reconnects. Konkrete Maximalraten, Expiry-/Ruhezeitintervalle und Gruppierungsregeln werden später bestimmt.

**Proaktive Hinweiskategorien:** Reaktionen/Emotes nach 02.112, Thread-Reply nach 02.113, Pinänderung nach 02.115, 02.120-Pollstart oder -Schluss nur dann als eigene zusätzliche Kategorie zustellen, wenn Kampagnenpolicy und Nutzer dies **ausdrücklich** erlauben. Keine impliziten neuen Pings aus `@alle`/geheimer Gruppenliste. Keine 02.119-Typing-/Online-Anwesenheits-Historien-Notification und keine 02.125-Export-/Druckeinträge.

**Spielwelt/Voicechat:** Lokaler optionaler Nachrichtenton ist **nicht** die 02.51-Szenensound-/Alarm-/Sensor-Engine und löst keine Tür, Quest, NPC-, Würfel-, Node-, Ressource-, Timer-, Turn- oder Next-Player-Wirkung aus. Ein empfangener Hinweis kann niemals eine echte 02.99-Spielweltaktion oder bewusstes offizielles 02.102-ACK ersetzen. Der externe Voicechat, eigene freien Spielernotizen und optionaler Missionsgenerator bleiben davon unabhängig.

## 5. Konzeptionelle Architektur und Umsetzungsplan

**Fachliche Modellkandidaten (keine finalen APIs/Tabellen):** `CampaignChatNotificationPolicy`, `ChatNotificationCapability`, `ChatNotificationChannelScope`, `ChatNotificationOwnPreference`, `ChatNotificationEventCategory`, `ChatNotificationRecipientProjection`, `ChatNotificationPreviewPolicy`, `ChatNotificationDeliveryAttempt`, `ChatNotificationDedupKey`, `ChatNotificationRateBudget`, `ChatNotificationDeviceConsent`, `ChatNotificationMuteDecision` und `ChatNotificationExpiryGuard`. Eine Notification referenziert die bestehende echte 02.107-Message-/Kanal-/Recipient-/Revisions-ID – **keine neue frei lesbare Kopie**. Effektive Policyversionsbindung an 02.25, 02.105–02.110 und individuelle Privatsphärewahl; Minimalbetriebs-/Audits nur nach eigenem engen Recht.

**Umsetzungsplan nach Abschluss aller Featureentscheidungen:**
1. **02.25-Policy-/Präferenzmatrix** für getrennte passive Badge-, In-App-Toast-, Sound-, Browser-/Desktop- und Eventkategorie-Funktionen definieren. Echte Chat-An/Off-, Channel-/Role-/Personen-, Nutzer-Privacy-, 02.110-Mute-/Block- und 02.111-Mention-Guards mit klarer Vorrangregel.
2. **Serverseitiger Recipient-Resolver:** Für jedes zugestellte Chat-/Reply-/Reaction-/Poll-/Mention-/Pinereignis originäre **historische UND heutige** 02.107-Leserechte, 02.108-/02.109-Lifecycle und weitere spezifische Medienscopes prüfen; Filter **vor** Count/Preview/Push/Caching/Subscription anwenden.
3. **Sichere Render-/Permission-Schicht:** Einfacher 02.121-A-Klartext mit erlaubter Absatzstruktur, sichere Kurzvorschauen und neutrale externe Lock-Screen-Notifications; keine 02.114-geheimen Medien, 02.120-privaten Stimmen oder Gruppen-/Sendernamen außerhalb expliziter Rechte.
4. **OS-/Browser-Grenze:** Permission nur nach eigenständigem Opt-in, zugestimmt/abgelehnt/entzogen korrekt handhaben; nur unterstützte Plattformen, keine erzwungenen Desktop-Pushes und keine irreführende Empfangs-/Kenntnisnahmebehauptung.
5. **Lifecycle/Anti-Spam:** Stale-Reconnect-/Offline-/Multi-Device-/Expiry-/Rolechange-/Block-/Mute-/QuietHours-/DuplicateEvent-/RateLimit-/Render-Race-Tests. Keinen 02.107-retentionswidrigen Notification-Schattenstore.
6. **Abnahme und UI später:** Untenstehende Tests, sinnvolle Opt-in-Defaults, Vorschautextstufen, Frequenz/QuietHours, Sounds und Icons erst bei späterem Gesamt-Settings-/UI-/MVP-Plan konkretisieren. Unabhängige offizielle 02.101–02.104-ACK-/Reminderkanäle und 02.116-A-Verbot erhalten.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Kampagne erstellt mit `Chat Aus` | Keine regulären Chat-Toast-/Ton-/OS-Push-/Unread-Subscriptions; amtliche Notices/Würfel/Notizen unabhängig |
| Chat An, Benachrichtigungen vollständig Aus | Berechtigter Chatverlauf/02.117-Suche nutzbar; keine zusätzlichen Töne/Toasts/Desktop-Pushes |
| SL erlaubt nur stille persönliche Badges | Nur pro Nutzer berechtigte Zähler, kein Popup/Ton |
| SL erlaubt Toast/Ton, Spieler deaktiviert eigenen Kanalton | Individuelle Unterdrückung wirkt; SL-Präferenz hebt Nutzer-Mute nicht auf |
| Spieler A erhält berechtigte Gruppenchat-Nachricht beim Kartenblick | Nur im autorisierten Kanal/Kampagnen-/persönlichen Scope ein zulässiger Toast |
| Neue Person C tritt erst nach früherer geheimer Nachricht bei | Kein historisch unberechtigter Ping/Count/Preview/Absender/Channelname |
| Alte berechtigte Person verliert heutiges Kanalrecht | Keine neue Notification/Navigation/Offline-Nachlieferung zu den alten Quellmessages |
| A mutet Teamkanal nach 02.110 | Optionale Benachrichtigungen unterdrückt; berechtigtes manuelles Lesen bleibt nach eigener Policy |
| A hat B als DM-Sender blockiert | Keine neue direkte DM-/Poll-/Reaction-/Mention-/Pin-Notification von B an A oder Blockursachen-Leak |
| B ist SL, hat aber kein Leserecht für As private DM | Kein automatischer SL-Desktop-Push/Preview/DM-Count |
| Berechtigtes `@Person` vs. gefälschtes `@alle` | Nur echte 02.111-permissionierte Erwähnung kann gesondertes Pingereignis auslösen |
| Neues Reply/Reaktion/Poll/Pin bei zugelassenen Eventtypen | Nur konkret erlaubte Kategorien und Original-/Recipientrechte, kein unautorisierter Massensound |
| Spieler deaktiviert Vorschautext für Desktop/Lock-Screen | Nur neutraler `Neue Nachricht`-Hinweis ohne Namen, Text, Gruppen-/DM-/Attachmentdetails |
| OS-Permission verweigert oder zurückgezogen | Kein Desktopnotification-Versprechen; bestehende andere tatsächlich erlaubte Anzeigen getrennt |
| Spieler hat OS-/Desktop-Hinweise nie erlaubt | Keine automatisch ausgelöste Browser-/OS-Permission oder Pushzustellung |
| Nachricht nach 02.108-Edit/Withdraw und 02.109-Remove | Keine verbotene alte Fassung in neuem Push/Queue/Cache/Preview |
| 02.107-Retention endet oder Chat wird flüchtig | Keine dauerhafte Notification-Schattenkopie und kein nachträglich unzulässiger Push |
| A klickt eine bereits gezeigte veraltete Notification nach Rights-Revocation | Navigation prüft erneut aktuell UND historisch und verweigert unberechtigten Message-/Anhangszugriff |
| Zwei Geräte/Reconnect/Retry | Deduplikation/Rate-/Privacy-/ACL-Checks, keine mehrfachen unkontrollierten Sound-Pings |
| 02.119 Typing/Online kommt an | Kein impliziter neuer globaler Aktivitätsalarm, kein Read-/Delivery-Tracking |
| 02.116 A ohne Lesestatus | Push angezeigt/weggeklickt erzeugt nie `B hat gelesen/empfangen`-Receipt |
| 02.118 A ohne Entwurfsspeicher | Notification-Reconnect erstellt keine gespeicherte Draft-/Autosendqueue |
| 02.121 A-Klartext mit Absätzen im Hinweis | Sicherer Klartextausschnitt ohne aktives Markdown/HTML, ggf. neutrale Darstellung |
| 02.114 geheimes Bild/Dateiname in DM | Kein Thumbnail-/Download-/URL-/Dateiname-Leak auf Lock-Screen oder unter fremdem Account |
| 02.120 Poll enthält geheime Abstimmende/Livevotes | Keine unberechtigte Voter-/Resultzahl in Notification-Vorschau/Count |
| 02.125 A kein Chat-Export | Keine neue History-/Notification-Bulkdownloadfunktion aus der Push-/Alert-Liste |
| Amtliche Korrektur gemäß 02.101–02.104 verlangt echten Ack | Chat-Mute hebelt official Notice nicht aus; Toast/Sound ersetzt niemals bewusste 02.102-Quittung |
| Ein Signal enthält behauptete `Tür öffnen`-Aktion | Keine echte NPC-/Quest-/Door-/Würfel-/Node-/Timer-/Turnwirkung durch Sound/Toast |
| Geheimgruppe sendet Nachricht; fremder Account prüft Badge/Push/Autocomplete | Keine Gruppenexistenz, Senderliste oder Aktivitätsmetadaten als Nebenkanal |

## 7. Beschlussgrenze und nächste Featurefrage

**Verbindlich beschlossen: 02.126 C.** Die SL darf bei Kampagnenerstellung zusätzlich zum wirksamen 02.105-Chat nach 02.25-Defaults/zulässigen markierten Ausnahmen **stille Badges, In-App-Toasts, Töne und Browser-/Desktop-Hinweise** samt Kategorie-/Kanal-/Rollen-/Personenrechte konfigurierbar anbieten. Spieler können innerhalb dessen eigene Präferenzen, Mutes und ggf. Ruhezeiten nutzen. Vor jeder optionalen Benachrichtigung/Preview/Count/Retry und erneut beim Öffnen gelten **heutige UND historische 02.107-Message-/Recipient-/Retentionrechte**, 02.106-Channel-/DM-Rechte, 02.108-/02.109-Lifecycle, **02.110-Mutes/DM-Blocks** und 02.111-Mentionrechte. Externe Notifications nur nach eigenem OS-/Browser-Opt-in, datensparsame Lock-Screen-Vorschauen. **02.116 A ohne individuelle Chat-Lesebestätigungen, 02.118 A ohne Drafts, 02.121 A Klartext, 02.122 A ohne Voice-Memos, 02.123 A ohne Forwarding, 02.124 A ohne Übersetzung und 02.125 A ohne Chatverlauf-Export/Druck** bleiben. Amtliche 02.101–02.104-Systemhinweise/echte ACKs sind unabhängig; keine automatische Spielweltwirkung.

**Nicht beschlossen:** Standard-Sounds, feste Ruhezeitfenster, konkrete OS-/Browser-Integrationen, Icons/Farben, konkrete Raten/TTL, vollständige UX oder MVP. Sicherheits-/Empfänger-/Geheimnisrechte und negative A-Featuregrenzen sind keine abschaltbaren Optionen.

## Nächste Entscheidung 02.127 – Chat-Nachrichtenfrequenz und Slowmode

**Beispiel:** Während einer intensiven Spielsitzung überschüttet eine Person einen Gruppenchat mit vielen einzelnen Nachrichten. Manche Gruppen möchten nur normale Spamgrenzen, andere einen bewusst festgelegten Mindestabstand pro Nutzer und Kanal. Die normale Unterhaltung und Voicechat-first-Spielweise müssen möglich bleiben.

- **A – Kein zusätzlicher Slowmode:** Keine gezielte spielerische Sendeabklingzeit; allgemeine Missbrauchs-/Spam-/Sicherheitsgrenzen aus 02.109/02.111 bleiben jedoch bestehen.
- **B – Starrer Slowmode überall:** Jede Kampagne, jeder Kanal, jeder Nutzer und jede Rolle unterliegen ungefragt dauerhaft demselben Sendeintervall; keine individuelle Ausnahme.
- **C – Konfigurierbarer berechtigter Slowmode (Empfehlung):** Bei 02.105 Chat An kann die SL nach 02.25-Defaults und markierten gültigen Kanal-/Rollen-/Personen-Ausnahmen bestimmte Chats zeitweilig auf einen Mindestabstand zwischen **bewussten** normalen Chatnachrichten begrenzen. Serverautoritativ, mit Echtzeit-/Offline-/Reconnect-/Mehrgeräte-/Moderations- und Revisionsschutz; 02.110-Blocks/Mutes, 02.116-A-no-receipts und 02.118-A-no-autosend bleiben. Keine globale Runden-/Voicechat-/World-/02.102-Ack-Sperre; konkrete Intervalle/UI später.
