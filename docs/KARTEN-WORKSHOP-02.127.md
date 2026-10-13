# AdventureShift – Karten-Workshop: Beschluss 02.127 A – kein spielerischer Chat-Slowmode

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.127; nächste offene Frage 02.128
**Status:** Verbindlicher Fachbeschluss und konzeptioneller Umsetzungs-/Abnahmeplan; **noch keine Softwareimplementierung**, keine finalen APIs, Datenbank-, UI- oder MVP-Festlegungen.
**Bezüge:** [02.25 – Kampagnenstandards und gültige markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – Spielernotizen/konfigurierbare Kampagnenfunktionen](KARTEN-WORKSHOP-02.98.md) · [02.99 – Weltaktionen und Serverautorisierung](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – amtliche Notices/ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106 – Kanäle/DMs/Gruppen/SL](KARTEN-WORKSHOP-02.106.md) · [02.107 – aktuelle und historische Empfänger-/Retentionrechte](KARTEN-WORKSHOP-02.107.md) · [02.108 – Bearbeiten/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Meldung/Moderation/Missbrauch](KARTEN-WORKSHOP-02.109.md) · [02.110 – Kanal-Mutes/DM-Kontaktblock](KARTEN-WORKSHOP-02.110.md) · [02.111 – Mentions/Ping-Spamschutz](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen/Emotes](KARTEN-WORKSHOP-02.112.md) · [02.113 – Antworten/Threads](KARTEN-WORKSHOP-02.113.md) · [02.114 – sichere Anhänge/Links](KARTEN-WORKSHOP-02.114.md) · [02.115 – Kanalpins/Bookmarks](KARTEN-WORKSHOP-02.115.md) · [02.116 A – keine individuellen Read-/Delivery-Receipts](KARTEN-WORKSHOP-02.116.md) · [02.117 – Suche/Filter](KARTEN-WORKSHOP-02.117.md) · [02.118 A – keine gespeicherten Entwürfe](KARTEN-WORKSHOP-02.118.md) · [02.119 – flüchtige Präsenz/Typing](KARTEN-WORKSHOP-02.119.md) · [02.120 – Umfragen](KARTEN-WORKSHOP-02.120.md) · [02.121 A – Absatz-Klartext](KARTEN-WORKSHOP-02.121.md) · [02.122 A – keine Sprachnachrichten](KARTEN-WORKSHOP-02.122.md) · [02.123 A – kein Weiterleiten](KARTEN-WORKSHOP-02.123.md) · [02.124 A – keine Übersetzung](KARTEN-WORKSHOP-02.124.md) · [02.125 A – keine Chat-Exporte](KARTEN-WORKSHOP-02.125.md) · [02.126 C – berechtigte Benachrichtigungen](KARTEN-WORKSHOP-02.126.md).

## 1. Verbindliche Entscheidung – Variante 02.127 A

**Der Projektinhaber hat ausdrücklich A gewählt: Im integrierten Chat wird kein zusätzliches spielerisches Slowmode- oder Nachrichtenabstandsmodul angeboten.** Bei aktiviertem 02.105-Chat darf eine nach 02.106/02.109/02.110 aktuell schreibberechtigte Person **ohne eine vom SL-Kampagnenmodus festgelegte Wartezeit** mehrere gewöhnliche Nachrichten hintereinander senden. Ein gesendeter Text erzeugt keinen automatischen personenbezogenen „Du darfst erst in X Sekunden wieder schreiben“-Cooldown.

**Kein versteckter C-Modus:** Weder 02.25-Kampagnen-/Regel-/Kanaltyp-/Rollen-/Personen-Defaults noch gültig markierte Ausnahmen bekommen einen `Slowmode An`-Schalter, eine Cooldown-Sekundenzahl pro Kanal oder automatische SL-/Moderator-Ratensperren als Gameplay-Einstellung. Die Wahl A lässt sich nicht durch ein Preset zu B (starrer Slowmode) oder C (konfigurierbarer Slowmode) umdeuten. Eine spätere Einführung wäre ein eigener neuer Fachbeschluss.

**Verbindlich ebenfalls:** Allgemeine serverseitige **Missbrauchs-, Spam-, Sicherheits-, Ressourcen-, Transport- und Datenschutzgrenzen aus 02.109/02.111** bleiben ausdrücklich aktiv. „Kein Slowmode“ heißt **nicht**: unendlich viele Nachrichten/HTTP-/WebSocket-Aufrufe, ungefilterte @alle-Pings oder das Recht, 02.109-Moderationssperren, 02.110-DM-Blocks und reale 02.106-Kanalrechte zu umgehen. Eine technische Notbremse gegen Spam, Bot-Angriffe oder Serverüberlastung ist **kein** dauerhaftes pro-Spielfigur einstellbares Chat-Slowmode-Modul.

**Beispiel:** A sendet im erlaubten Gruppenchat nacheinander drei Absätze als drei bewusst versendete Nachrichten. Ohne aktivierte Spam-Abwehrmaßnahme müssen sie nicht künstlich 5, 15 oder 30 Sekunden auseinanderliegen. Sendet A hingegen in einem Bot-/Flut-Angriff massenhaft Nachrichten oder unberechtigte Mentions, greifen die bisherigen serverseitigen Schutzmechanismen; die App darf das nicht mit „Slowmode grundsätzlich verboten“ verwechseln.

**Nicht gewählt:** B (immer und überall dieselbe starre Wartezeit) und C (Kampagnen-/Kanal-/Rollen-/SL-gesteuerter Chat-Cooldown). Externer Voicechat, Notizen und die tatsächliche 02.99-Spielweltmechanik bleiben unabhängig.

## 2. Unterscheidung: verbotener Slowmode und weiterhin verpflichtende Schutzmaßnahmen

| Bereich | Gemäß 02.127 A | Unveränderliche Grenze |
| --- | --- | --- |
| **Spielerischer Mindestabstand zwischen normalen Nachrichten** | **Nicht vorgesehen:** keine „erst wieder nach X Sekunden“-Chatregel | Kein 02.25-/02.105-/Kanal-/Role-Cooldownfeature |
| **Normales manuelles Senden** | Mehrere bewusst abgesendete zulässige 02.121-Klartextnachrichten können unmittelbar folgen | Jede Message benötigt erneut echte 02.106-/02.109-/02.110-Sendeberechtigung |
| **Sicherheits-Rate-Limits/Backpressure** | Gegen technische Überlastung, Bots, Replay, Abuse, Nachrichtengrößen, Spam und ID-Enumeration **weiterhin nötig** | Interne Grenzwerte kein Kampagnenspiel-Slowmode; fehlerhafte Überlastzustellung nicht als Erfolg ausgeben |
| **02.109 Moderator-Eingriff** | Fallbezogene Sendbeschränkung/Entfernung nach gesonderter echter Berechtigung bleibt möglich | Eine legitim begründete Moderationssperre ist keine frei verstellbare Pause für alle Spieler |
| **02.110 persönlicher Mute** | Einzelne Kanal-Notifications/Töne/Toasts dürfen stummgeschaltet werden | Mute ist kein neuer Sendecooldown für alle und kein willkürlicher Historyzugriffsentzug |
| **02.110 echter DM-Senderblock** | Unerlaubte neue private Kontaktzustellung wird serverseitig verhindert | Kein `Cooldown abwarten, dann trotz Block senden` |
| **02.111 Mentions/Pings** | Permission-/Recipient-/Abuse-/Massenping-Limits unverändert | Normale Textsendefreiheit gibt nicht unbegrenzte `@alle`-Rechte |
| **02.112/02.120 Reaktionen/Umfragen** | Eigene Rate-/Idempotenz-/Berechtigungsregeln für Reaction/Vote/Close | Diese Operationen nicht ungefragt als neue normale Chatnachrichten zählen oder unbegrenzt spammen lassen |
| **02.114 Medien** | Upload-/Malware-/MIME-/Speicher-/Quota-/Trafficlimits unabhängig | Kein Dateispeicher ohne Quote wegen abgewähltem Slowmode |
| **02.126 Benachrichtigungen** | Individuelle Mutes, QuietHours, Deduplikation, Rate-/Push-Filter weiter aktiv | `Kein Slowmode` erzwingt keine Sounds oder ungebremste Desktop-Pushwellen |
| **02.101–02.104 Pflichtmitteilungen** | Rechtmäßige separate Systemhinweise/Reminders/ACKs unabhängig | Kein Chat-Cooldown, der amtliche Ack-/Sicherheitskanäle blockiert |

**Keine Zahlen festgelegt:** Sicherheitsschutzbudgets, Bot- und DDoS-Schwellen, Größen-/Bandbreitenlimits, Burst-/Backpressure-Verhalten und Moderationstrigger werden in späteren Sicherheits-/Hostingdetails begrenzt und abgenommen. Sie sind **nicht** eine versteckte SL-Konfiguration „Nachricht alle 10 Sekunden“, sondern zweckgebundene notwendige Schutzkontrollen mit nachvollziehbarem Fehlermanagement.

## 3. Servertransport, Reconnect und effektive Rechte

1. **02.105 Chat An/Aus:** Ein deaktiverter Chat bleibt tatsächlich Aus – kein normaler neuer `sendMessage`-Commit. Bei Chat An kein zusätzliches pro-Kanal-Gametime-Cooldown. Die 02.25-Optionen für andere bereits erlaubte Module bleiben gültig, können aber nicht das ausdrücklich ausgeschlossene Slowmode wiederherstellen.
2. **Jeder Send-Commit einzeln serverseitig geschützt:** Echter authentifizierter Actor, aktueller 02.106-Kanal-/Gruppen-/DM-/SL-/Kampagnen-/Rollen-/Empfängerscope sowie 02.109-Sendrestriktionen und 02.110-DM-Senderblock beim tatsächlichen Commit prüfen. Kein „gestern durfte ich senden, also heute wieder“ oder „ich habe die Wartezeit abgewartet, also darf ich blockierten B kontaktieren“.
3. **Bei Rate-/Transportfehlern wahrheitsgemäß:** Zulässige eigene `pending/accepted/rejected`-Information nach 02.116 A: Serverannahme darf angezeigt werden, **keine** Behauptung, dass ein bestimmter Empfänger den Text erhalten/gelesen hat. Technische Missbrauchsabwehr darf den Sendversuch korrekt und sparsam ablehnen, ohne private Blocklisten, geheime Gruppen oder interne Erkennungsdetails preiszugeben.
4. **02.118 A – Keine Offline-Outbox/Autosend:** Ein beim Verbindungsabbruch nicht bewusst gesendeter Composertext ist kein automatisch später geplanter Sendeauftrag. Ein bereits **bewusst** eingereichter echter Send-Commit braucht 02.105-/02.106-OperationId-/Idempotenz-/Reconnect-/Doppelclickschutz, damit „kein Slowmode“ nicht Doppelzustellung oder ungeprüftes Replay bedeutet.
5. **02.107-/02.108-/02.109-Lifecycle:** Tatsächlich gesendete Nachrichten unterliegen weiterhin heute UND historisch gültigen Channel-/Empfänger-/Quell-/Secret-/Retention- und Edit-/Withdraw-/Moderationsrechten. Die Entscheidung A macht keine verborgenen DMs zugänglich, speichert keine abgelaufenen Daten länger und erzeugt keine neue permanente Nachrichtenschattenhistorie.
6. **02.111-/02.112-/02.113-/02.114-/02.115-/02.120-Scoped Effects:** Mentions, Reaktionen/Emotes, Replies/Threads/Quotes, Dateien, Pins/Bookmarks und berechtigte Umfragen behalten getrennte Capabilities und technische Quoten. Ein mit hoher Häufigkeit getippter `/me`-Text, Poll-Option oder `@Gruppe`-Mention erzeugt keine unberechtigten eigenen Ressourcen-/Node-/Alarm-/Worldevents.

## 4. Zusammenspiel mit Benutzeroberfläche, Datenschutz und Welt

**Chatbenachrichtigungen unabhängig:** 02.126 C kann trotz 02.127 A Sounds/Toasts/Badges pro Empfänger und Kategorie drosseln, bündeln oder per 02.110 stummschalten. **Benachrichtigungs-Ratebegrenzung ist nicht Chat-Slowmode.** Ein schneller Chat darf nicht als Recht interpretiert werden, mehrere private Lock-Screen-Vorschauen/DM-Metadaten an Unberechtigte oder blockierte Empfänger zu schicken. 02.116 A – keine individuellen Chat-Read-/Delivery-Receipts – bleibt unabhängig von Versandtempo und Notification-Anzeige.

**Schon ausgeschlossene Module:** 02.118 A bedeutet kein gespeicherter Entwurf oder Auto-Resend; 02.121 A normaler mehrzeiliger Klartext statt Rich-/Markdown-/Spoilereditor; 02.122 A keine Voice-Memos; 02.123 A keine Nachrichtweiterleitung; 02.124 A keine Chatübersetzung; 02.125 A keine Chat-History-/Search-Komfort-Exporte. Kein früher ausgeschlossener Komfort wird wegen 02.127 A neu aktiviert.

**Moderation:** 02.109 C bleibt fallbezogen. Ohne Slowmode kann die SL im rechtmäßigen Moderationsscope gegen Spam vorgehen, aber erhält durch 02.127 A weder allgemeine Einsicht in fremde private DMs noch einen heimlich universell aktivierten Timer zum Steuern aller normalen Nachrichten. Gegen Bots/Spam notwendige technisch begrenzte Schutzchecks lassen sich nicht über persönliche Ausnahmen aushebeln.

**Unabhängige amtliche Notices und Spielwelt:** Echte 02.101–02.104-Sicherheits-/Korrekturmitteilungen, Quittungen und Reminder haben ihre eigenen Rollen-/Empfänger-/Ack-/Lebenszyklusregeln. Normaler Text `Tür öffnen`, die Sendefrequenz, technische Rateabwehr oder das Weglassen eines Cooldowns löst **niemals** automatisch 02.99-World-/NPC-/Quest-/Tür-/Würfel-/Node-/Timer-/Next-Player-/Turn-Effekte aus. Der externe Voicechat, private Notizen, SL-Handlungen und der optionale Missionsgenerator bleiben außerhalb des Chat-Slowmode-Kontexts.

## 5. Negativer Architekturentscheid und Umsetzungsplan

**Nicht als Chat-Komfortfeature planen:** `CampaignChatSlowmodePolicy`, `ChatSlowmodeInterval`, `ChatSlowmodeOverride`, `ChannelSlowmodeConfig`, `UserSlowmodeCooldown`, `canSetSlowmode`, `nextAllowedChatSendAt` oder eine normale `setSlowmode`-REST-/WebSocket-/Admin-/UI-Aktion. Es gibt **keinen** Chat-Nachrichten-Mindestabstand, keine effektive spielerische Cooldownfrist und keine 02.25-Rollen-/Personenausnahmen für einen abgewählten Slowmode.

**Bestehende getrennte Sicherheitsmodelle bleiben:** 02.109-echt autorisierte `ChatModerationRestriction` und zweckgebundene technische `ChatAbuseRateBudget`/`ChatTransportBackpressure`/`ChatSendOperationId`-Konzepte können für Transport- und Schutzfunktionen nötig sein. Sie sind kein `Slowmode`-Feature und dürfen nicht als versteckte normale Kampagnen-Spielregel etikettiert werden. Konkrete Namen, API-/DB-Verträge, Speicherfristen, Quoten und UI-Fehlermeldungen werden erst in späterer technischer Umsetzung entschieden.

**Umsetzung nach Abschluss des Featureworkshops:**
1. **Negative Feature-/Settingsentscheidung festhalten:** Kein Chat-Slowmode-/Intervall-/Role-Ausnahmeschalter im 02.25-/02.105-Konfigurationsassistenten; keine implizite 02.127-A-Wartezeit aus Channel-/Userpresets.
2. **Normales manuelles Senden:** Authentifizierte gültige 02.106-/02.109-/02.110-Nachrichtenoperation ohne künstliche Cooldown-Regel, aber sicher bei jeder Sendung geprüft, einschließlich Message-/Reaction-/Poll-/Mention-/Attachment-Spezialrechte und aktueller ACL.
3. **Missbrauchsschutz unabhängig:** Serverbudget, Quoten, Rate-/Spam-/Flood-/Replay-/Ressourcenschutz gegen echte Abuses sowie 02.109-Befugnisse und 02.111-Massenmentionlimits erhalten; keine pauschale Gameplay-Sendeabklingzeit als vermeintlich nötige Sicherheit.
4. **Transport/Mehrgeräte/Offline:** Idempotenz, CAS/Operation-ID, Reconnect/Retry-/Mehrgeräteprüfung ohne 02.118-A-gespeicherte ungesendete Draftoutbox oder automatische Nachsendung; technische Fehlerrückmeldung ohne 02.116-A-Recipientstatus/Privacy-Leak.
5. **Privacy/Spam/Benachrichtigungen testen:** 02.107-heutige UND historische Message-/Recipient-/Retentionrechte, 02.110-Mutes/Blocks, 02.111-Pings, 02.126-C-Notification-Dedupe/QuietHours/OS-Opt-in, Moderation und 02.102-ACK-Trennung testbar sicher halten.
6. **UI und MVP später:** Kein Slowmode-Timer/Cooldown-Count oder `warte noch X Sekunden` als Spielregel. Allgemeine Spam-/Transportfehler verständlich und nicht als normaler Nachrichtenerfolg zeigen. Konkrete Abusegrenzen, UI und MVP nach Gesamtworkshop planen.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Kampagne mit 02.105 Chat An | Berechtigter normaler Chat ohne zusätzliche Spiel-Slowmode-Regel |
| Kampagne mit Chat Aus | Kein reguläres `sendMessage` oder neuer Sende-/Slowmodepfad, amtliche Notices und Notizen unabhängig |
| Spieler sendet zwei eigene zulässige Klartextnachrichten nacheinander | Kein künstlicher einstellbarer Mindestabstand zwischen normalen Nachrichten |
| Spieler sendet mehrere 02.121-Absätze als eine Nachricht | Ein bewusst gesendeter Message-Commit mit Absätzen, keine künstlichen Cooldownabzüge pro Absatz |
| SL sucht in 02.25-Kampagnen-/Kanal-/Role-Settings Slowmode | Kein solcher optionaler Game-Intervallschalter trotz genereller Konfigurierbarkeit |
| Manipulierter Client versucht `setSlowmode` oder `nextAllowedChatSendAt` | Kein freigeschalteter Chat-Slowmode-Featurepfad oder gefälschte Wartefrist |
| Technisch massenhafte Bot-/Flood-Nachrichten | Serverseitige Missbrauchs-/Rate-/Ressourcengrenzen schützen weiter, ohne Gameplay-Slowmode |
| 02.109 legitim moderierte Person versucht erneut zu senden | Tatsächliche Moderator-Sendsperre greift unabhängig von abgelehntem Slowmode |
| A hat B nach 02.110 für neue DMs blockiert | A empfängt keine neue unerlaubte DM; `kein Slowmode` hebt Block nicht auf |
| A schaltet persönlichen Gruppenkanal-Mute ein | 02.126-optional Toasts/Sounds aus, aber kein Slowmode-/Kanal-Senderecht für andere verändert |
| A pingt tausendmal `@alle` | 02.111-Sender-/Target-/Abuseratebegrenzung bleibt wirksam trotz normaler Sendefrequenz |
| 02.112-Reaktion oder 02.120-Pollvote in schneller Folge | Eigene Rate-/Idempotenz-/Voter-/Message-ACL bleibt; keine künstliche normale Chatabklingzeit |
| 02.114-Datei-Massen-Upload während schnellen Chats | MIME-/Quota-/Malware-/Netz-/Speicherlimits weiter aktiv |
| B erhält viele berechtigte Teamnachrichten und hat Desktop-Toast erlaubt | 02.126-eigene Deduplikation/Rate/Privatsphäre und 02.110-Mute können Notificationflut begrenzen |
| A sendet vor Netzverlust bewusst, quittierendes Clientpaket geht verloren | Echte Sendung nur idempotent, kein ungewollter Doppelcommit beim Reconnect |
| A schreibt nur offline im 02.118-A-Eingabefeld | Kein Auto-Senden oder persistente Offline-Outbox bei Verbindung zurück |
| SL/Moderator ohne DM-Leserecht prüft Spamprotokoll | Kein pauschaler Blick in private fremde DMs; 02.109-berechtigte Fälle getrennt |
| Unberechtigte Person errät alte Gruppen-/DM-/Message-ID | 02.106-/02.107-aktuelle UND historische ACL, Revision und Retention geschützt |
| 02.108-Withdraw oder 02.109-Removal nach Versand | Kein wieder öffentliches Original durch Spamcheck, Count, Cache oder Reconnect |
| 02.116 A verbietet individuelle Lesebestätigungen | Schnell gesendete und angezeigte Nachricht erzeugt keinen Sender-Read-/Delivery-Receipt |
| Echte 02.101-Systemkorrektur erfordert 02.102-ACK | Keine Chat-Slowmodewartezeit, keine automatische amtliche Quittierung |
| Spieler schreibt `Tür öffnen` zehnmal hintereinander | Keine echte 02.99-NPC-/Quest-/Door-/Node-/Turn-/Würfelwirkung |
| Voicechat-first-Kampagne mit Chat Aus | Voicechat, selbstständige Spielernotizen, Würfel-/Systemfeed und manuelle SL-Aktionen unverändert |

## 7. Beschlussgrenze und nächste Featurefrage

**Verbindlich beschlossen: 02.127 A – kein zusätzlicher spielerischer oder konfigurierbarer Chat-Slowmode.** Keine im 02.25-/02.105-Settingsinventar festlegbaren Mindestabstände, keine kanal-/rollen-/personenbezogenen Sendeabklingzeiten oder normale Slowmode-API. Technisch notwendige serverseitige **Spam-/Missbrauchs-/Rate-/DDoS-/Transport-/Ressourcenschutzgrenzen** nach 02.109/02.111 bleiben ausdrücklich gültig; ebenso sämtliche 02.106-/02.107-aktuellen UND historischen Kanal-/Empfänger-/Retention- und 02.110-DM-Block-/Mute-Regeln. **02.126 C konfigurierbare Benachrichtigungen** einschließlich Deduplizierung/QuietHours sind unabhängig. 02.116 A (keine persönlichen Chat-Lesebestätigungen), 02.118 A (keine Draftspeicherung), 02.121 A (einfacher Absatztext), 02.122 A (keine Voice-Memos), 02.123 A (kein Weiterleiten), 02.124 A (keine Übersetzung) und 02.125 A (keine Chat-Exporte) gelten fort. Keine echte World-/System-Ack-Wirkung durch Chat-Sendefrequenz.

**Nicht beschlossen:** Feste allgemeine Server-Ratezahlen, Bot-Erkennungsalgorithmen, technische Quoten, fertig spezifizierte Fehlertexte oder MVP-Reihenfolge. Die ausdrücklich abgelehnte Gameplay-Cooldown-Funktion darf nicht als angeblich erforderliches 02.25-Preset eingeführt werden.

## Nächste Entscheidung 02.128 – Eigene Ansicht: Chatnachrichten persönlich ausblenden

**Beispiel:** Spieler A hat eine für ihn berechtigt sichtbare, aber inzwischen irrelevante Chatnachricht. Er möchte sie vielleicht nur in seiner eigenen Ansicht verstecken, ohne den ursprünglichen Text für alle zu löschen, während SL-Moderation und 02.107-Historienrechte unverändert bleiben.

- **A – Kein persönliches Nachrichtenausblenden:** Alle heute UND historisch berechtigt sichtbaren und regulär gespeicherten Chatnachrichten bleiben nach 02.107-Policy in der eigenen Chatansicht; nur bestehendes 02.110-Kanalmute und die 02.117-Suche/Filter ändern die Navigation.
- **B – Universelles Entfernen per Klick:** Jeder kann beliebige eigene/fremde Chatnachrichten für alle Teilnehmer global verschwinden lassen, auch ohne 02.108-/02.109-Rechte.
- **C – Konfigurierbares rein persönliches Ausblenden (Empfehlung):** Bei 02.105 Chat An nach 02.25-Kampagnen-/Kanal-/Rollen-/Personenpolicy darf jeder hierzu Berechtigte einzelne heute UND historisch erlaubte Nachrichten nur in **seiner eigenen privaten Ansicht** ausblenden und ggf. wieder sichtbar machen. Kein physisches Original-Löschen, keine neue Moderations-/DM-/Quellenfreigabe, keine fremde „A hat ausgeblendet“-Anzeige oder Chat-Read-Receipt (02.116 A). 02.107-Retention, 02.108-/02.109-Edit/Withdraw/Moderation, 02.110-Mute/Blocks und 02.115-Bookmarks bleiben geschützt; UI/Retentionlimits später.
