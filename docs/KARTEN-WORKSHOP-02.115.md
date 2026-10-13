# AdventureShift – Karten-Workshop: Beschluss 02.115 C – berechtigte Kanal-Pins und persönliche Chat-Lesezeichen

**Stand:** 13.10.2026 – Fachbeschlüsse 02.1 bis 02.115; nächste offene Frage 02.116
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungsplan und Abnahmetests; **noch keine Softwareimplementierung**, keine finalen API-/Datenbankverträge, Einstellungen-UI, Standard-Pinlimits, Retentionfristen oder MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnenstandards und markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – private Spielernotizen, Kartenmarker und schaltbare Funktionen](KARTEN-WORKSHOP-02.98.md) · [02.101–02.104 – unabhängige Systemkorrekturen und Quittungen](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus bei Kampagnenerstellung](KARTEN-WORKSHOP-02.105.md) · [02.106 – berechtigte Kampagnen-/Gruppen-/DM-/SL-Kanäle](KARTEN-WORKSHOP-02.106.md) · [02.107 – heutige UND historische Empfängerrechte, flüchtige Chats und Retention](KARTEN-WORKSHOP-02.107.md) · [02.108 – Textrevisionen/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Meldungen und Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – Kanal-Mutes und DM-Kontaktblocks](KARTEN-WORKSHOP-02.110.md) · [02.111 – Erwähnungen/Pings](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen/Emotes](KARTEN-WORKSHOP-02.112.md) · [02.113 – Antworten/Zitate/Threads](KARTEN-WORKSHOP-02.113.md) · [02.114 – geschützte Anhänge/Links/Previews](KARTEN-WORKSHOP-02.114.md) · [Kommunikationsworkshop 11](FEATURE-WORKSHOP.md).

## 1. Verbindliche Entscheidung – Variante 02.115 C

**Vom Projektinhaber ausdrücklich gewählt: C – getrennt konfigurierbare berechtigte Kanal-Pins und persönliche private Lesezeichen.** Bei **aktivem, bei Kampagnenerstellung wirksam An/Aus schaltbarem 02.105-Chat** dürfen nach 02.25-Kampagnen-/Regel-/Kanaltyp-/Kanal-/Gruppen-/Rollen-/Personenstandards samt fachlich gültigen markierten Ausnahmen berechtigte Personen **einzelne ihnen tatsächlich heute UND historisch lesbare Nachrichten** für den erlaubten Chatbereich anpinnen und/oder nur **für sich selbst** als Lesezeichen merken. Die SL kann Kanalpins, eigene Bookmarks und entsprechende Benutzer-/Moderationsrechte jeweils unabhängig erlauben, begrenzen oder deaktivieren.

**Fachlich zwei getrennte Funktionen:**
- **Kanal-Pin:** Eine berechtigt gesetzte, auf eine konkrete 02.107-Message-ID im selben 02.106-Kanal bezogene Hervorhebung. Sie ist als Kanalorganisation prinzipiell für **heute UND zur Ursprungsnachricht berechtigte Empfänger individuell gefiltert sichtbar**, nicht automatisch für alle späteren Mitglieder. Wer Pin setzen, ändern, lösen oder gezielt moderieren darf, ist eine eigene 02.25-Kanal-/Rollen-/Personenfähigkeit.
- **Persönliches Lesezeichen:** Ein einzelner authentifizierter Nutzer merkt sich in **seiner privaten Liste** eine aktuell und historisch zulässig lesbare Nachricht; weder andere Spieler, der ursprüngliche Absender noch die SL bekommen allein deswegen Zugriff auf fremde Bookmarks. Eigene Bookmarks lassen sich selbst wieder entfernen; ein Bookmark ist **kein öffentliches Pin, keine Nachrichtenteilung und keine dauerhafte Kopie**.

**Beispiel:** In einer berechtigten Gruppe wird eine Nachricht mit Treffpunkt durch eine dazu ermächtigte Person angepinnt. Teilnehmer B sieht sie im Pinbereich, solange B die konkrete Nachricht **heute und historisch** lesen darf. C tritt später bei und bekommt den alten Pin/Originaltext nicht allein wegen seiner neuen Mitgliedschaft. D setzt auf eine andere Nachricht ein **eigenes privates Lesezeichen**: Niemand sonst erhält daraus einen Hinweis, dass D dieses Lesezeichen besitzt. Ein abgelaufener oder zurückgezogener Text bleibt durch Pin/Bookmark nicht wieder abrufbar.

**Nicht gewählt:** A (gar keine speziellen Merkhilfen) und B (jeder pinnt beliebig dauerhaft für alle ohne Quell-/Historienrechte). Die Auswahl von C erlaubt ausdrücklich das bewusste Ausschalten bestimmter Teilfunktionen beim Kampagnenstart.

## 2. Berechtigungen, Sicht- und Verwaltungsregeln

| Teilfunktion | Konfigurierbares Soll | Feste Grenze |
| --- | --- | --- |
| **Kanal-Pins An/Aus** | Nach tatsächlichem 02.106-Channel-/Rollen-/Personenrecht zulassen, ggf. Zahl/Priorität begrenzen | Pin erweitert weder Nachrichtenempfänger noch Kanalmitgliedschaft/History |
| **Kanal-Pin setzen** | Separate `pinChannelMessage`-Fähigkeit, Ziel aktuell UND historisch lesbar, zulässiger Kanal/Messagezustand | Keine Pins fremder verborgener DMs, anderer Kanäle oder nur erratener Nachrichten-IDs |
| **Kanal-Pin lösen/verwalten** | `unpinOwnChannelMessage`/`manageChannelPins` nach Policy und dokumentierter konkreter Befugnis | Andere Pins nicht heimlich überschreiben; SL-Verwaltungsrolle kein pauschales DM-Leserecht |
| **Private Lesezeichen** | `addOwnBookmark`/`removeOwnBookmark`/`listOwnBookmarks` pro echtem Nutzer und zulässiger Kampagne | Keine automatischen Teamlisten, SL-Reports oder fremden Bookmark-Autocomplete |
| **Pinned-/Bookmark-Ansicht** | Nur je empfangender Person **heute UND historisch** lesbare Messages/Revisionen samt zulässigen Metadaten | Keine Hinweise auf verborgene Namen, Counts, Teilnehmer, Kanal-IDs, Anhänge oder Zeitstempel |
| **Sortieren/Suchen/Anspringen** | Optional erlaubte Filter, persönliche Ordnung und Navigationslinks auf regulär lesbare Quelle | Navigation ist keine Quell-/Original-Nachricht-Freigabe; kein Schattenarchiv |
| **Notizen und Kartenmarker** | 02.94–02.98 bleiben unabhängig; freiwillig nur nach gesonderten echten Rechten verlinken | Ein Chatbookmark ist keine Inventar-Keycard, keine Kartenentdeckung und kein Questbeweis |

**Unabhängige Zustände:** Das Anheften durch einen hierzu befugten Nutzer ist **keine** Moderationsentfernung und keine persönliche Mitteilung an alle; ein fremder Chatpin kann eine eigene Bookmarkliste nicht verändern. Die SL kann eigene Admin-/Moderationsoperationen je Kanal erlauben, ohne automatisch die privaten Lesezeichen oder privaten 02.107-DMs zu sehen. Die Zuordnung bleibt an echten Nutzer- und Kanal-IDs gebunden, nicht an veränderbare Charakternamen.

**Konkrete Standardeinstellungen offen:** Maximale Anzahl Pins/Lesezeichen, Sortierung, Mehrfachpins, Ablauf-/Pinned-by-Labels, Erinnerungszeiten, Benachrichtigungen und genaue Bedienoberfläche/MVP werden später festgelegt. Der Beschluss erzwingt jetzt keine festen Standardzahlen oder UI.

## 3. Heutige und historische Leserechte – auch bei geheimer Gruppe

1. **Vor jedem Pin-/Bookmark-Commit:** Server prüft 02.105 Chat An, echten Actor, `pinChannelMessage` oder `addOwnBookmark`, aktuellen 02.25-Kampagnen-/Kanal-/Rollen-/Personenstandard, 02.106-Channel-/DM-/Gruppen-/SL-Mitgliedschaft sowie **heutige UND historische** 02.107-Empfänger-/Quell-/Fog-/Secret-/NPC-/Quest-/Notiz-/Wurf-/Retentionrechte und 02.108-Nachrichtenstatus/Revision. Ein unbekannter, verborgener oder unberechtigter Message-Key ist **kein gültiger Pin-/Bookmark-Kandidat**; Antwort verrät nicht, ob das geheime Objekt existiert.
2. **Kanalpin ist KEINE öffentliche Kopie:** Serverseitige Pinobjekte können kanalgebunden existieren, aber **pro Betrachter** nur dann im Kanalpin-Verzeichnis erscheinen, wenn die Zielnachricht für diesen **zum damaligen Empfängerkreis gehörte UND heute noch sichtbar ist**. Reines Channel-Adminrecht oder spätere Teammitgliedschaft genügt nicht. Gesonderte berechtigte Verwaltungslisten dürfen keine unzugänglichen geheimen Quelltexte als allgemeine Pins anzeigen.
3. **Eigenes Bookmark bleibt privat UND quellengebunden:** Eigene Bookmarkabfragen sind an tatsächliche Accountidentität und aktuellen zulässigen Kampagnen-/Quellzugriff gebunden. Beim späteren Rechteentzug kein Text, Preview, Autor, Dateianhang, Count oder erratbares Hidden-Channel-Metadatum; technisch nötige vertrauliche Tombstones dürfen nur in einem berechtigten administrativen Datenschutzpfad bleiben, nicht in einer Spieler-Schattenliste.
4. **Neue/wechselnde Gruppenmitglieder:** Ein später beigetretener Spieler sieht Pins nur zu den Nachrichten, die er **historisch** überhaupt empfangen durfte. Umgekehrt kann ein früherer Empfänger nach Wegfall aktueller Rechte keine ursprüngliche Nachricht über einen gespeicherten Pin oder ein Mehrgerät wieder abrufen. Rechtmäßig früher menschlich gesehenes Wissen lässt sich nicht zurückholen.
5. **Statusprojektionen:** `pinned`-Marker an einer Nachricht, Pinreihenfolge, Pinned-by-Angaben, Badge/Count, persönliche Bookmarkmarkierungen, Suche, Export und Reconnect sind individuell nach gültigen 02.106-/02.107-/02.108- und 02.114-Quell-/Attachmentrechten zu filtern. Keine pauschale Reveal-Antwort mit geheimen Gruppentiteln oder Existenzcounts.
6. **Unabhängige Rollen-/Moderation:** `manageChannelPins` darf organisatorische Kanalaktionen erlauben, **nicht automatisch** fremde 02.107-Historie freischalten. 02.109-Moderation erhält nur ausdrücklich fallbezogene, eng legitime Belege; ein Pin kann niemals eine fremde DM in eine allgemeine SL-Dashboard-Liste umleiten.

## 4. Änderungen, Aufbewahrung und Datenschutz

**02.108-Edits:** Kanalpin und eigenes Bookmark referenzieren eine **stabile echte Message-ID** – keinen fest eingefrorenen, jedermann lesbaren Text. Wird der Inhalt nach 02.108 editiert, zeigt ein berechtigter Aufruf nur die nach aktueller und historischer Revisionspolicy zulässige Textfassung. Der Pin beweist nicht, dass jemand die neue Fassung schon gelesen oder gutgeheißen hat; alte Versionen ausschließlich mit **eigenständig zulässigem Revisionszugriff**. Alte Snippets, Thumbnails oder Zitatcaches werden nicht als „angeheftete Originalversion“ heimlich weiter öffentlich bereitgestellt.

**Withdraw/Moderation/Retention:** Wird eine Nachricht 02.108-zurückgezogen, 02.109-unterdrückt/entfernt, die Mitgliedschaft widerrufen oder die 02.107-Aufbewahrungsfrist erreicht, müssen alle **neuen unberechtigten** Pin-/Bookmark-Read-/Search-/Badge-/Push-/Export-/Realtime-/Reconnect-/Assetzugriffe entfallen. Pinobjekt und private Referenz werden entsprechend Daten- und Retentionpolicy entfernt oder in nicht einsehbare, rechtmäßig begrenzte administrative Belege überführt; eine eigenständige unendliche Pin-Schattenhistorie ist **nicht** erlaubt. Ein Kanalpin oder Lesezeichen verlängert Chat-Retention **niemals automatisch**. Keine falsche Behauptung, dass schon von Menschen gesehene Inhalte rückwirkend verschwinden.

**Flüchtige Chatverläufe:** Bei 02.107-flüchtiger Kommunikation können Pins/Bookmarks nur auf eine noch zulässig verfügbare Message verweisen. Sie versprechen **keine persistente Text-/Anhangswiederherstellung** nach Offline/Restart/Expiry. Ob kurzfristige flüchtige Verweise praktisch angeboten werden, richtet sich nach der tatsächlichen Speicher-/Retentionfähigkeit; keine versteckte neue Dauerhistorie als Nebenwirkung.

**02.114-Anhänge:** Bild/Datei/Preview einer angepinnten bzw. gemerkten Nachricht bleibt **pro Original/Thumbnail/Linkvorschau/Download an dieselbe heutige UND historische 02.107-/02.114-ACL gebunden**. Kein dauerhafter öffentlicher Downloadlink oder universelles Vorschaubild als Pinbeigabe, auch nicht über Suche/Export. Lizenz-/Assetbibliotheksrecht separat.

**Concurrent Events/Mehrgerät:** Pin-/Unpin, Bookmark-Set/Unset, Message-Edit/Withdraw, User-/Group-Rollentausch, Chat-An/Aus und Echtzeit/Offline-Reconnect versionssicher/idempotent behandeln. Kein Doppelklick erzeugt mehrfach denselben Kanalpin, keine verlorenen Updates/negative Counts, kein Replay von entzogenen Quell-/Pinrechten; sichtbare Änderungen rechtzeitig mit individueller Projektion neu berechnen. Bestandsschutz heißt, geschützte Daten bei deaktivierter Teilfunktion nicht **heimlich** als öffentlich oder physisch gelöscht behandeln.

## 5. Aufmerksamkeit, Spam und Welttrennung

**02.110-Mutes/DM-Blocks:** Kanalpins und Bookmarks sind **Organisationsfunktionen**, keine neue Kontaktzustellung. Ein persönlich stummgeschalteter Kanal bleibt bei gültigem Zugriff bewusst lesbar, aber das Setzen/Aufheben eines Pins erzeugt nicht automatisch neue optionale Sounds/Pushes an den Stummgeschalteten. Ein echter 02.110-DM-Senderblock darf nicht durch Kanalpin, Bookmarklink oder „angepinnt“-Push als neue blockierte Direktkontakt-Benachrichtigung umgangen werden; berechtigter geteilter Gruppeninhalt wird dadurch nicht für andere gelöscht. Blocklisten bleiben privat.

**02.111-Mentions:** Ein Pin sendet **kein** implizites `@alle`/`@Gruppe`/`@SL`; explizite Mentionbenachrichtigungen folgen ausschließlich den bereits separat berechtigten 02.111-Sende-/Empfänger-/Rate-/Mute-/Blockregeln. Keine automatische Benachrichtigung aller früheren Leser beim Umordnen.

**02.112/02.113:** Reaktionen/Emotes und Replies/Quotes/Threads behalten ihre **eigenen** Quell-/Revision-/Historienrechte. Ein Thread-Root-Pin zieht **nicht** automatisch sämtliche Unterantworten und noch weniger geheime DM-Quellen in die Kanalpinliste. Ein Quote-Pin kann keine für den Empfänger unlesbare Quelle freischalten.

**02.101–02.103 und 02.109:** Pin/Bookmark setzen, geöffnet sehen oder entfernen erzeugt **keine** tatsächliche persönliche 02.102-Kenntnisnahmequittung und ersetzt keine wirksam berechtigte 02.109-Moderationsmaßnahme. Echte System-/Sicherheits-/Korrekturinformationen folgen weiter ihrer **eigenen** geschützten Notice-/Ack-/Reminderpolicy, nicht einem frei getippten „Wichtig“-Pin.

**Keine Weltwirkung:** Pinned/Bookmarked-Status, Pin-Reihenfolge, Lesezeichenliste oder Push-/Suchereignis lösen **niemals** automatisch NPC-/Quest-/Inventar-/Geld-/Tür-/Alarm-/Sensor-/Würfel-/Node-/Timer-/Next-Player-/Turnwirkungen aus. Ein in einem Chatpin notierter Code wird nicht automatisch am Terminal ausprobiert. 02.94–02.98 freies Spielernotizbuch, optionaler Missionsgenerator, erlaubte manuelle Aktionen und externer Voicechat bleiben unabhängig.

**Missbrauchsgrenzen:** Kanalpinänderungen, Pin-/Bookmarkanzahl, verteilte Updates, Lookup-/Search-/Export- und eventuelle Benachrichtigungsraten serverseitig begrenzen, unabhängige 02.109-Chatmoderationsrestriktionen beachten. Nicht autorisierte Person darf keine fremden Pins/Bookmarks manipulieren oder über Rückgabecodes ausspähen. Konkrete Schwellenwerte und UI bewusst später festlegen.

## 6. Konzeptionelle Architektur und Umsetzungsplan

**Modellkandidaten – keine freigegebenen Tabellen/APIs:** `CampaignChatPinPolicy`, `ChatChannelPinGrant`, `ChatChannelPin`, `ChatChannelPinRevision`, `ChatChannelPinProjection`, `ChatPersonalBookmarkPolicy`, `ChatPersonalBookmark`, `ChatBookmarkOwnerScope`, `ChatPinSourceMessageBinding`, `ChatPinVisibilityDecision`, `ChatPinOperationId`, `ChatPinAuditReceipt`. Fachliche Referenzen: Kampagne, 02.106-Kanal/Gruppe/DM, authentifizierte Actor- bzw. Bookmark-Owner-ID, 02.107-Quellmessage/ursprünglicher Empfängersnapshot und Aufbewahrung, 02.108-Revision, 02.109-Maßnahme, 02.110-Filter, 02.25-EffectivePolicy- und Quell-/Zielversionen. Private Lesezeichen-Owner-Verknüpfung **nicht** pauschal als Kanalmetadatum publizieren.

**Geplante Umsetzungsschritte:**
1. **02.25-Policy-/Capabilitymatrix** für Kanal-Pin-Set/Unpin/Manage, eigene Bookmark-Set/Unset/List sowie berechtigte Pin-Read-/Search-/Export-/Navigationsrechte definieren; 02.105 Chat-An/Off serverseitig als vorrangigen Guard behalten.
2. **Geschützter Message-Resolver**: nur echte stabile Message-/Channel-IDs, 02.106-Role-/Channel-/DM-Rechte und **02.107-aktuelle UND historische Quell-/Empfänger-/Retentionchecks**, 02.108-Nachrichten-/Revisionsstatus und 02.109-Restrictions vor jedem Set/Unset/Manage-Commit neu prüfen.
3. **Getrennte Datenpfade**: Kanalpins organisatorisch kanalgebunden aber pro Leser gefiltert; persönliche Bookmarks exklusiv eigentümergebunden, ohne fremdes Nutzer-/SL-Leserecht oder neue Recipient-Historie. Unset/Moderation als eigene berechtigte, idempotente, versionierte Aktionen.
4. **Projektions- und Cachingregeln**: Pin-/Bookmarklisten, Text-/Autor-/Revision-Snippets, Counts, Threadverweise, 02.114-Bilder, Suche/Export/Realtime/Offline/Reconnect nur mit heute **und historisch** zulässigen Quell-/Anhangsrechten. Keine Leaks aus Cache, Index oder Metadaten.
5. **Lifecycle und Datenschutz**: 02.108-Edit/Withdraw, 02.109-Remove, Rollenentzug, 02.107-Retention/Flüchtigmodus und Chat-Off ohne künstlich verlängerte Chatdaten; individuell sichtbare Tombstone-/Cleanupregeln und geschützte Audits, nicht grenzenlose Archivkopien.
6. **Race-/Abuse-/Abnahmetests**: Version/CAS/Idempotenz, doppelte Aktionen, Moderator vs. eigene Entfernung, Gruppentransfers, Multi-Device/Queue/Push/Mute/DM-Block/No-World-Effect testen; UI, Grenzwerte und MVP erst nach Abschluss aller Featurefragen ausarbeiten.

## 7. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| 02.105 bei Erstellung `Chat Aus` | Keine neuen normalen Chat-Pins/-Bookmarks/-History-/Count-/Subscribeaktionen; System-/Würfel-/Notiz-/Weltmodule unabhängig |
| Chat An, Kanalpins Aus, persönliche Bookmarks An | Zulässiger Spieler kann nur eigenes Bookmark setzen, keinen Kanalpin erzeugen |
| Chat An, Kanalpins An, private Bookmarks Aus | Berechtigter Kanalverwalter darf Pin setzen, Nutzer hat keinen Bookmark-Schreibweg |
| Person ohne Kanal-Pin-Recht sendet normale Chatnachricht | Senderecht gibt kein automatisches `pinChannelMessage`-Recht |
| Berechtigter A pinnt sichtbar empfangene 02.107-Nachricht | Pin wird im erlaubten Kanal erstellt; nur berechtigte historische/heutige Leser bekommen Pintext |
| C tritt nach alter gepinnter Teamnachricht erst später bei | Keine alte Nachricht/Pintext/Original-Attachment/secret Count für C ohne historischen Empfängernachweis |
| Früherer Empfänger verliert heute Gruppen-/DM-/Fog-/Quellrecht | Kein weiterer Pin-/Bookmark-Read/Search/Export/Reconnect aus altem Recht |
| B speichert private Lesezeichen auf eigene sichtbare DM | Nur B kann seine Bookmarkliste sehen; keine SL- oder andere Spieler-Liste allein wegen Verwaltung |
| A errät Message-/Bookmark-ID eines fremden geheimen Chats | Kein Pin-/Bookmark-Read oder Änderung, keine Existenz-/Autor-/Kanalmetadaten-Leaks |
| Unterschiedliche Charaktere desselben echten Accounts | Berechtigung und Bookmark-Owner über echte authentifizierte Identität, nicht kopierbaren Nickname |
| Ein anderer Spieler entfernt As Bookmark | Verweigert; nur Eigentümer oder separat autorisierte rechtmäßige Datenschutzprozesse |
| Pin-Manager ohne DM-Leserecht verwaltet Kanal | Keine allgemeine Archiv-/DM-Einsicht, nur genau zuständige zulässige Verwaltungsaktion |
| 02.108 bearbeitet zuvor angepinnte Nachricht | Zeige nur aktuell zulässige Textrevision; alte geheime Fassung nicht durch Pin-Snapshot reaktiviert |
| 02.108 Withdraw / 02.109 Removal / 02.107-Retentionende | Keine unberechtigten Pin-/Bookmark-Snippets/Previews/Counts, keine künstlich verlängerte History |
| 02.107 flüchtige Nachricht nicht mehr vorhanden | Kein behauptetes dauerhaftes persönliches Backup im Lesezeichen oder Kanalpin |
| 02.114-Bild oder Link aus privater DM gepinnt | Download/Thumbnail/Link-Preview weiterhin unter Quellmessage-/Medienrechten, nicht öffentlich durch Pin |
| Kanalpin auf 02.113-Threadroot | Keine automatisch zugänglichen fremden Kinderantworten, Zitate oder geheime Parentinhalte |
| A hat Kanal nach 02.110 stumm und B setzt Pin | Zulässige manuelle Pin-Ansicht möglich, keine zusätzlichen aufdringlichen Ping-/Pushhinweise an A |
| A blockiert B als DM-Sender; B versucht Pin-/Lesezeichenkontakt | Keine neue direkte DM- oder zielgerichtete Pingzustellung an A, Sperrgrund bleibt privat |
| Ein Pintext enthält `@alle` oder Code „Tür 1234“ | Kein unberechtigter 02.111-Ping und keine automatisch ausgelöste Tür-/Quest-/Node-/Turnaktion |
| Spieler pinnt wichtige 02.101-Korrektur als freien Chattext | Chatpin erzeugt niemals echte 02.102-Ack-Quittierung oder gesetzlich offizielle Pflichtmitteilung |
| Gleichzeitiges Unpin/Pin, Edit/Withdraw, Multi-Device oder Reconnect | Serverseitig gültiger, deduplizierter Version-/ACL-/Retentionstand; keine Doppel-/Negativcounts |
| Kampagne deaktiviert Pins nach früherer Nutzung | Keine neuen Pins und keine ungefragte Veröffentlichung/Löschung des weiterhin geschützten Bestands |
| 02.94 persönliche Notiz oder Kartenmarker existiert | Bleibt unabhängig; keine automatische Kopie oder weltwirksame Markerverknüpfung durch Chatbookmark |
| Spam mit massenhaft Pin-/Bookmark-IDs | Serverseitige Limits, Rate-/Audit-/Fehlerdatenschutz, keine Ausleitung von versteckten Chatinhalten |

## 8. Beschlussgrenze und nächste Featurefrage

**Verbindlich beschlossen: 02.115 C** – Bei wirksamem 02.105-Chat An sind **berechtigt verwaltete Kanal-Pins** und **private persönliche Lesezeichen** getrennt nach 02.25-Defaults und zulässigen markierten Ausnahmen schaltbar. Kanalpins und persönliche Bookmarkreferenzen verleihen keine zusätzlichen 02.106-/02.107-Quell-/Empfängerrechte, benötigen **heutige UND historische** Message-/Channel-/Retentionberechtigung bei Aktion und Projektion und respektieren 02.108-Edits/Withdraw, 02.109-Moderation, 02.110-Mute/DM-Block, 02.111-Mentions, 02.112-Reaktionen, 02.113-Threads und 02.114-Medienrechte. Keine permanente Kopie, kein automatisch offizieller Systemhinweis/ACK und keinerlei reale Spielweltaktion.

**Nicht beschlossen:** Feste Pin-/Bookmarklimits, Sortier-/Navigations-/Such-UI, genaue Stummschalt-/Benachrichtigungsdetails, feste Aufbewahrungs-/Wiedervorlagezeiten, neue generische Lese-/Lieferbestätigungen, endgültiges Tabellen-/API-Schema und MVP-Einstufung. Der vollständige Settingsassistent folgt nach den Featureentscheidungen.

## Nächste Entscheidung 02.116 – Chat-Zustellstatus, Lesestatus und optionale Lesebestätigungen

**Beispiel:** Spieler A schickt B eine wichtige Gruppenchat-Nachricht und fragt sich, ob sie technisch zugestellt oder tatsächlich gelesen wurde. B möchte vielleicht gerade **keine** persönliche Lesebestätigung offenlegen. Außerdem dürfen 02.110-Blocklisten, geheime Gruppen und 02.102-verbindliche ACKs nicht mit gewöhnlichem Chatstatus verwechselt werden.

- **A – Keine individuellen Chatstatus:** Chat sendet nach echten Kanalrechten, aber zeigt generell keinen individuellen Zustell- oder Lesestatus.
- **B – Unbegrenzte Lesestatus-Transparenz:** Jeder kann für beliebige Nachrichten und Gruppen alle Teilnehmer, deren Online-/Lesezeiten und private Block-/Zustellursachen abfragen, auch bei fehlendem Message-/Historienrecht.
- **C – Konfigurierbare berechtigte und datensparsame Statusanzeigen (Empfehlung):** Die SL legt nach 02.25-Defaults und gültigen Ausnahmen getrennt fest, ob reine technische Sendestatus, empfängerberechtigte Zustellinfos und ausdrücklich erlaubte persönliche Lesebestätigungen angeboten werden. Pro Empfänger müssen aktuelle UND historische 02.106-/02.107-Sicht, 02.108-/02.109-Maßnahmen und 02.110-Mute-/Block-Privatsphäre geschützt bleiben. Zustellung, geöffnet, gelesen und bewusstes 02.102-ACK bleiben strikt unterschiedliche Vorgänge. Keine versteckten Gruppen-/DM-/Offline-/Blockinformationen über Counts oder Zeitstempel und keine Weltwirkung; UI später.
