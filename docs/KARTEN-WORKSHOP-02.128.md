# AdventureShift – Karten-Workshop: Beschluss 02.128 A – kein persönliches Ausblenden einzelner Chatnachrichten

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.128; nächste offene Frage 02.129
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungs- und Abnahmetestplan; **noch keine Softwareimplementierung**, keine finalen APIs, Datenbankverträge, UI oder MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnenstandards und gültige Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – private Notizen und optionale Funktionen](KARTEN-WORKSHOP-02.98.md) · [02.99 – autorisierte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – offizielle Notices und ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106 – Kanal-/Gruppen-/DM-/SL-Rechte](KARTEN-WORKSHOP-02.106.md) · [02.107 – heutige und historische Empfängerrechte, flüchtige History und Retention](KARTEN-WORKSHOP-02.107.md) · [02.108 – eigene Edits/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – fallbezogene Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – Kanal-Mutes/DM-Senderblocks](KARTEN-WORKSHOP-02.110.md) · [02.111 – Mentions/Pings](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen/Emotes](KARTEN-WORKSHOP-02.112.md) · [02.113 – Replies/Zitate/Threads](KARTEN-WORKSHOP-02.113.md) · [02.114 – Medien/Links](KARTEN-WORKSHOP-02.114.md) · [02.115 – private Lesezeichen/Kanalpins](KARTEN-WORKSHOP-02.115.md) · [02.116 A – keine individuellen Lesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.117 C – berechtigte Suche/Filter](KARTEN-WORKSHOP-02.117.md) · [02.118 A – keine gespeicherten Chatentwürfe](KARTEN-WORKSHOP-02.118.md) · [02.119 C – kurzlebige Präsenz/Typing](KARTEN-WORKSHOP-02.119.md) · [02.120 C – berechtigte Umfragen](KARTEN-WORKSHOP-02.120.md) · [02.121 A – schlichter mehrzeiliger Text](KARTEN-WORKSHOP-02.121.md) · [02.122–02.125 A – kein Voice-Memo, Forwarding, Übersetzung oder Komfortexport](KARTEN-WORKSHOP-02.125.md) · [02.126 C – geschützte Benachrichtigungen](KARTEN-WORKSHOP-02.126.md) · [02.127 A – kein Slowmode, dennoch Spamabwehr](KARTEN-WORKSHOP-02.127.md).

## 1. Verbindliche Entscheidung – Variante 02.128 A

**Der Projektinhaber hat ausdrücklich A gewählt: AdventureShift erhält keine zusätzliche, nutzerbezogene „Diese einzelne Chatnachricht nur für mich ausblenden“-Funktion.** Wer eine 02.107-gültige Nachricht **heute UND historisch** sehen darf und für wen sie noch gemäß erlaubter Retention verfügbar ist, kann sie im normal berechtigten Verlauf weiterhin wiederfinden. Es gibt **keinen** persönlichen Hide-/Unhide-Knopf, keine pro Account verborgene Message-ID-Liste, kein `Nachricht ignorieren`-Tombstonearchiv und keine eigene persönliche „Alle ausgeblendeten Nachrichten“-Wiederherstellungsansicht.

**A ist kein konfigurierbarer C-Modus:** Die allgemeine 02.25-Kampagnen-/Kanal-/Rollen-/Personen-Konfiguration und markierte Ausnahmen schalten **keine** dieser ausdrücklich abgewählten Funktionen heimlich wieder ein. Die SL erhält auch keinen beliebigen „blende diese eine Nachricht für Spieler X aus“-Komfortweg außerhalb bereits beschlossener wirklicher 02.106-/02.107-/02.108-/02.109-Rechte- bzw. Moderationsoperationen.

**Beispiel:** A hat einen alten, weiterhin rechtmäßig gespeicherten Gruppenbeitrag gelesen. A kann den Kanal nach 02.110 stummschalten, innerhalb der wirklich erlaubten 02.117-Suche/Filter navigieren oder 02.115 private Lesezeichen auf wichtige andere Nachrichten setzen. A kann **nicht** eine einzelne regulär sichtbare Nachricht per Klick **nur aus As persönlicher History verschwinden lassen**, während das Original für alle anderen unverändert stehen bleibt.

**Nicht gewählt:** B (jeder löscht beliebige fremde Nachrichten global ohne Moderationsbefugnis) und C (getrennt konfigurierbare private persönliche Hide-/Restore-Markierungen). Das Fehlen von C ist kein Widerruf der bereits berechtigten 02.108-Withdraw-/02.109-Moderations- oder 02.107-Retentionmaßnahmen.

## 2. Abgrenzung zu bereits beschlossenen Funktionen

| Bestehende Funktion | Bleibt gemäß eigenem Beschluss möglich | Kein durch 02.128 A neu erlaubter Weg |
| --- | --- | --- |
| **02.107 berechtigter Verlauf** | Regulär heute UND historisch lesbare, nicht abgelaufene/verbotene Nachrichten nach gespeichertem/flüchtigem Modus anzeigen | Keine nutzerspezifische Liste dauerhaft ausgeblendeter einzelner Message-IDs |
| **02.108 eigene Edit-/Withdraw-Rechte** | Eigenen Beitrag unter gültiger Version-/Withdraw-Policy wirklich ändern oder zurückziehen | `Für mich verstecken` als geheimer Ersatz einer gesonderten zulässigen Quellenoperation |
| **02.109 echte Moderation** | Eng berechtigt Meldung/Entfernung/Suppression nach legitimer Fall-/Kanalpolicy | Beliebiges globales Löschen durch normale Spieler oder pauschale private DM-SL-Sicht |
| **02.110 Channel-Mute/DM-Senderblock** | Persönliche Benachrichtigungen stummschalten und neue gesperrte Direktkontakte unterbinden | Mute löscht nicht automatisch einzelne historische Gruppennachrichten; DM-Block löscht frühere rechtmäßige DM-History nicht pauschal |
| **02.117 Suche/Filter** | Nach tatsächlich freigegebenen Kanal-/Zeit-/Sender-/Volltext-/Threadkriterien temporär Treffer eingrenzen | Suchfilter ist keine persistente persönliche Message-Hideliste oder universelle Quellenlöschung |
| **02.115 Channelpins/private Bookmarks** | Zulässig lesbare Nachricht hervorheben bzw. privat für spätere Navigation merken | Bookmark-/Unbookmark-Operation darf alte normale Message aus dem Verlauf nicht automatisch ausblenden |
| **02.113 Replies/Zitate/Threads** | Nach eigenen gültigen Quell-/Eltern-/Kindrechten anzeigen und navigieren | Verborgene Quell-IDs oder Threadkinder nicht mittels anderer UI-Tombstones einsehen |
| **02.114 Medien** | Berechtigte Nachrichtenanhänge nur mit heutiger UND historischer Datei-/Message-ACL laden | Kein `nur für mich Text ausblenden, Datei aber unbegrenzt behalten`-Backdoor |
| **02.126 Benachrichtigungen** | Individuell zugelassene Töne/Toasts/Badges/OS-Hinweise, QuietHours und Mutes verwenden | Wegklicken eines Pop-ups ist kein `Originalnachricht dauerhaft für mich ausblenden` |
| **02.125 A kein Export/Druck** | Gewöhnliche berechtigte History und einzelne erlaubte Dateidownloads bleiben | Keine versteckte persönliche Archiv-/Restore-Datei durch ein abgewähltes Hidefeature |
| **Persönliche Notizen** | 02.94–02.98 bewusst selbst geführte Notizen bleiben eigenständig | Keine automatische Umwandlung normaler Nachrichten in versteckte Notizen |

**Kein Zwang, alle alten Inhalte sofort auf einmal zu laden:** Normale Pagination, virtueller Scrollbereich, Fensterzustand und temporäre Navigationsfilter können aus Performance-/UX-Gründen zulässig sein. Entscheidend ist, dass eine weiterhin rechtmäßig lesbare Nachricht **nicht als neue persistente persönliche Hide-Ausnahme** aus der eigentlichen autorisierten History entfernt wird. Für flüchtige oder abgelaufene 02.107-History wird **keine** Wiederherstellung versprochen.

## 3. Heutige UND historische Berechtigungen und Retention

1. **Chat An/Aus:** Bei 02.105-Chat Aus keine normalen neuen Chat-/History-/Hide-Operationen; unabhängige System-/Würfel-/Notizmodule bleiben. Bei Chat An gibt es keinen neuen Hide-Endpunkt.
2. **Pro Betrachter:** Der Server autorisiert die reguläre 02.107-History nach tatsächlicher 02.106-Kampagnen-/Kanal-/Gruppen-/DM-/SL-/Personenmitgliedschaft, **ursprünglicher historischer Empfängerbindung UND heutiger Quell-/Fog-/Secret-/Retentionberechtigung**. 02.128 A ist kein pauschales `Jeder sieht alles`-Programm.
3. **Keine automatische neue Freigabe:** Ein neu zur Gruppe gehörender Spieler erhält nicht rückwirkend alte geheim adressierte Nachrichten, nur weil keine zusätzliche persönliche Hidefunktion existiert. Ein früherer Leser verliert den Zugriff bei tatsächlich widerrufenen aktuellen Quellrechten. Es entsteht kein persönliches Schattenarchiv.
4. **02.108-/02.109-Lifecycle:** Echte Edit-/Withdraw-/Fallmoderation kann eine Nachricht entsprechend ihren **eigenen** Autor-/Role-/Case-Rechten ändern, unterdrücken, rechtmäßig als Auditbeleg halten oder entfernen. Das ist keine neue „jeder versteckt nur für sich“-Funktion. Die vorher erlaubte Version/alte Quelltexte dürfen nicht durch Cache/Quotes wieder unberechtigt sichtbar werden.
5. **02.110-Kanal-Mute vs. DM-Block:** Mute schützt Aufmerksamkeit/Notifications, nicht automatisch den historischen Gruppenlesezugriff. Eine echte DM-Senderblockierung verhindert neue Kontakte, löscht aber den zuvor rechtmäßig verfügbaren Chatverlauf nicht automatisch. Die private Blockliste darf auch nicht über Counts, versteckte Nachrichten oder neue per-user Hidezustände verraten werden.
6. **Such-, Pin-, Realtime-/Exportprojektionen:** Reguläre 02.117-Suche, 02.115-Pins/Bookmarks, 02.113-Threads, 02.114-Thumbnails, 02.120-Umfragen und 02.126-Badges/Notificationnavigation benutzen alle ihre bestehenden Nachricht-/Empfänger-/Revisions-/Retentionguards. Kein neuer Hidden-Messages-Count, Recovery-Index, fremder Hideaktor oder persönliche Hidden-Message-Suchoption als Seitenkanal.

## 4. Architekturentscheidung und planbare Umsetzung

**Negativer Feature-/Datenvertrag:** `ChatPersonalMessageHide`, `ChatHiddenMessageList`, `ChatHiddenMessageTombstone`, `ChatMessageHidePreference`, `ChatRestoreHiddenMessage`, `canHideOwnViewMessage`, `setMessageHiddenForMe` und `listMyHiddenMessages` gehören **nicht** als zusätzliche gewöhnliche Chat-UI-/REST-/WebSocket-/DB-/Cache-/Offline-/Export-Funktionen in den Plan. Der Ausschluss ist ein ausdrücklicher Nutzerbeschluss; keine 02.25-/Channel-/Role-/Personenausnahme soll ihn umgehen.

**Wichtige Grenzen:** Das durch 02.108-/02.109 bereits konzeptionell beschlossene wirklich berechtigte Bearbeiten, Zurückziehen, fallweise Entfernen und berechtigtes Datenschutzhandeln gehört zu **eigenen typisierten Nachricht-/Fall-Lebenszyklen**, nicht zu `persönlich ausgeblendet`. Eine per 02.107 abgelaufene Nachricht wird nicht weiter durch `Unhide` wieder abrufbar; ein 02.110-Mute ist keine Chatarchiv-Löschung. Der Server muss normale Nachrichtenrechte auch dann prüfen, wenn eine UI-Ansicht nur eine Teilmenge darstellt.

**Konzeptioneller Umsetzungsplan:**
1. **Featurekatalog/Settings:** Die Variante 02.128 A bei 02.25/02.105 als bewusst **nicht anzubietenden** persönlichen Message-Hide-/Restore-Komfort verankern. Keine verdeckten Settings-Flags oder per-SL-/per-User-Ausnahmen.
2. **Normaler Verlaufsresolver:** Bereits beschlossene 02.106-/02.107-Channel-/Historien-/Retention-/Secret-/Personenrechte, 02.108-Nachrichtenversionen und 02.109-Moderation **unverändert** pro tatsächlichem Viewer anwenden; normale History nicht nach einem neuen Hide-Flag filtern.
3. **Ausnahmen funktional getrennt:** 02.110-Channelmute/DM-Block als Benachrichtigungs- bzw. neuer Kontaktfilter; 02.117-Suche/Navigation temporär; 02.115-Bookmarks/Pins als sichere Referenzen; 02.108-/02.109-Edit/Withdraw/Moderation als echte Nachrichtenzustandsänderungen.
4. **Keine versteckte per-user-Historie:** Kein `hideMessageForMe` in Realtime/Cache/Offline/Export, kein Schattenindex persönlicher versteckter Text-IDs. Keine Chat-Quellenkopie, die nach Ablauf von 02.107-Retention auf `Wieder einblenden` wartet.
5. **Spamschutz und Notices weiterhin:** 02.111-/02.127-A-Spam-/Abuse-/Sendeguards, 02.126-C-Mute-/Notification-/QuietHoursschutz und unabhängige offizielle 02.101–02.104-Notices/02.102-Acks nicht durch fehlenden Hidekomfort deaktivieren.
6. **Abnahme/MVP später:** UI-Performance/Pagination, History-/Search-/Moderations-/Block-/Notification-/Secret-/Cache-/Mehrgeräte-/Retentiontestmatrix prüfen. Aussehen, Scrolling, Limits und MVP-Priorisierung erst nach vollständigem Workshop festlegen.

## 5. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| 02.105 Chat Aus bei Erstellung | Kein normaler Chat-/Hide-Pfad; Notizen, Würfel-/Systemlog und amtliche Notices unabhängig |
| Berechtigter Spieler öffnet regulär gespeicherten alten Gruppenchat | Noch rechtmäßig sichtbare Chatnachrichten sind nach 02.107-History zugänglich |
| Spieler öffnet Kontextmenü einer fremden berechtigten Nachricht | **Kein** `Nur für mich ausblenden`/`Wieder einblenden`-Knopf |
| Spieler ruft `setMessageHiddenForMe` mit bekannter Message-ID auf | Kein solcher autorisierter gewöhnlicher Chat-Endpunkt/Feature-Toggle |
| SL sucht nach versteckter Hide-Policy im 02.25-Assistenten | Keine Kampagnen-/Rollen-/Personen-Ausnahme für das abgewählte Modul |
| Neuer Spieler tritt Gruppe nach alten Geheimnachrichten bei | Keine alte Nachricht, Quell-ID, Hidden-Count oder Media aus fehlendem historischen Recht |
| Ehemaliger Spieler verliert heutiges Channelrecht | Keine alten Texte oder Hide-/Restore-Nebenkopien trotz ehemaliger Mitgliedschaft |
| Nachricht läuft gemäß 02.107-Retention aus | Normale History/Quellen nicht mehr abrufbar, kein persönliches Unhide-Archiv |
| Flüchtige 02.107-Nachricht ist nach Restart verloren | Keine zugesicherte `Wieder einblenden`-Kopie |
| Spieler ändert eigenen Text gemäß 02.108 | Echte autorisierte Revision gilt, kein fremder persönlicher Hidezustand |
| Autor zieht eine Message 02.108-berechtigt zurück | Tatsächliche nach Revision und Recipientrecht gültige Withdrawprojektion, keine persönliche Ersatzkopie |
| 02.109-Moderator entfernt Nachricht fallberechtigt | Echte gezielte Moderation nach gesonderten Scope-/Auditrechten; kein universal erlaubtes Löschen durch andere |
| A hat Kanal stummgeschaltet gemäß 02.110 | Zulässige History bleibt, optionale 02.126-Notifications sind stumm, Message nicht heimlich verborgen |
| A blockiert B als DM-Sender | Neue Blockkontakte gesperrt; früher rechtmäßig verfügbare History nicht automatisch vernichtet |
| A setzt privates Bookmark nach 02.115 | Nur eigene private Merkhilfe; Entfernen des Bookmarks löscht den normalen Originalchat nicht |
| A nutzt 02.117-Filter für einen Absender oder Zeitraum | Erlaubte Trefferprojektion gefiltert, keine persistente `diese Message verstecken`-Liste |
| A öffnet/verlässt einen 02.113-Thread | Autorisierte Parent-/Reply-Navigation ohne dauerhaftes Verbergen der Originalmessage |
| 02.114-Dateianhang einer Message ist für A zulässig | Dateizugriff unter eigenem Original-/Assetrecht; keine `hidden`-Backdoor zu fremder Datei |
| 02.120-Poll nach Berechtigung geschlossen | Pollsicht nach eigener History-/Resultpolicy, kein fremdes Voter-/Hidden-Count-Leak |
| 02.126-Toast wird vom Empfänger weggeklickt | Nur Hinweis weg, nicht die zugrundeliegende erlaubte Chatnachricht aus History verschwunden |
| 02.116 A ohne persönliche Lesebestätigungen | Weder Anzeigen noch Navigation erzeugt ein `hat gelesen/ausgeblendet`-Signal an den Sender |
| 02.118 A verbietet Drafts/Autosend | Kein Draft-Hide-/Unhide-Mechanismus oder wiederaufgenommener Offline-Send |
| 02.125 A verbietet Chat-Komfortexport | Kein Datenexport der tatsächlich nicht vorhandenen persönlichen Versteckliste |
| Echte amtliche 02.101-Korrektur verlangt 02.102-ACK | Hidefunktion steht nicht zur Verfügung; Notice und bewusste ACKs folgen eigenem Berechtigungspfad |
| Chattext behauptet `Tür öffnen` | Keine tatsächliche 02.99-Quest-/NPC-/Door-/Würfel-/Node-/Turnaktion |
| Mehrere Geräte, Reconnect und Rechtewechsel | Alle zeigen jeweils nur aktuell UND historisch erlaubte Messages; keine inkonsistenten Hidden-Flags |

## 6. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.128 A – kein persönliches Ausblenden einzelner Chatnachrichten.** Es gibt weder eine normale per Account gespeicherte Versteck-/Wiederherstellungsliste noch einen 02.25-Kampagnen-/Channel-/Rollen-/Personen-Schalter dafür. Die wirklich **heute UND historisch** nach 02.106-/02.107-/02.108-/02.109-Policy berechtigten und verfügbaren Nachrichten bleiben in der regulären History zugänglich. **Unverändert:** 02.108 tatsächliche Edits/Withdraw, 02.109 fallbezogene Moderation, 02.110 Mute/DM-Block, 02.115 private Lesezeichen, 02.117 C Suche/Filter, 02.126 C Notificationpräferenzen, 02.127 A kein Slowmode aber zwingende Spamabwehr; sämtliche vorherigen A-Entscheidungen wie **02.116 A ohne Read-/Delivery-Receipts** und **02.118 A ohne gespeicherte Drafts** bleiben. Eine Nachricht ist kein durch persönlichen Hide versteckter, unbegrenzt gespeicherter Ghosttext und erzeugt keine echten 02.102-ACK-/02.99-Spielweltwirkungen. Externer Voicechat, Spieler-Notizen und eigenständige Weltaktionen bleiben unabhängig.

**Nicht beschlossen:** Eine per-Person-Hideliste, globale Löschung durch beliebige Spieler, neue künstliche Aufbewahrung, konkretes UI-/Pagination-/Virtualisierungsverhalten, finale Datenbank-/API-Entwürfe oder MVP. Es werden **keine** zusätzlichen individuellen Rechte zum Lesen fremder Chatgruppen eröffnet.

## Nächste Entscheidung 02.129 – Chatkanäle persönlich sortieren und favorisieren

**Beispiel:** Ein Spieler ist in mehreren berechtigten Gruppen- und DM-Kanälen. Die wichtigsten möchte er in seiner eigenen Kanalliste nach oben setzen, ohne dass andere Teilnehmer dadurch deren Sicht oder Rechte verändern.

- **A – Feste Kanalübersicht:** Die Anwendung zeigt berechtigte Chatkanäle in einer vom System festgelegten Ordnung; keine eigenen Favoriten oder Sortierlisten.
- **B – Jeder ändert alle Listen:** Jeder Teilnehmer kann globale Kanalreihenfolge, Sichtbarkeit und Favoriten auch für andere ändern, selbst ohne Kanal- oder Teamrecht.
- **C – Konfigurierbare private Kanalorganisation (Empfehlung):** Bei 02.105 Chat An erlaubt 02.25-Policy mit gültigen markierten Ausnahmen persönliche Favoriten, eine eigene Sortierung und optional eingeklappte Bereiche **nur für die eigene Kanalübersicht**. Sichtbarkeit hängt weiterhin ausschließlich von echten heutigen 02.106-Kanal-/DM-/Gruppen-/SL-Rechten ab; private DM-/Teamnamen, 02.107-History, 02.110-Mutes/Blocks, 02.111-Pings und 02.126-Notifications werden nicht durch eine Favoritenliste offengelegt oder automatisch umsortiert. Kein personenbezogenes „A hat dich favorisiert“-Signal, keine 02.116-Lesebestätigung, kein World-/ACK-Effekt; genaue UI später.
