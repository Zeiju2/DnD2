# AdventureShift – Karten-Workshop: Beschluss 02.119 C – berechtigte, datensparsame Schreib- und Präsenzindikatoren

**Stand:** 13.10.2026 – Fachbeschlüsse 02.1 bis 02.119; nächste offene Frage 02.120
**Status:** Verbindlicher Fachbeschluss und konzeptioneller Umsetzungs-/Abnahmeplan. **Noch keine Softwareimplementierung**, keine finalen API-/Datenbankverträge, UI, Status-/TTL-Zeitwerte oder MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnenstandards und zulässige markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – freie Spielernotizen und konfigurierbare Funktionen](KARTEN-WORKSHOP-02.98.md) · [02.101–02.104 – getrennte Systemhinweise und bestätigte ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat bei Erstellung An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106 – Kanal-/Gruppen-/DM-/SL-ACL](KARTEN-WORKSHOP-02.106.md) · [02.107 – heutige und historische Empfänger-/Historyrechte](KARTEN-WORKSHOP-02.107.md) · [02.108 – Edits/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – persönliche Kanal-Mutes und DM-Senderblock](KARTEN-WORKSHOP-02.110.md) · [02.111 – Mentions/Pings](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen/Emotes](KARTEN-WORKSHOP-02.112.md) · [02.113 – Replies/Zitate/Threads](KARTEN-WORKSHOP-02.113.md) · [02.114 – Medien/Links](KARTEN-WORKSHOP-02.114.md) · [02.115 – Pins/Bookmarks](KARTEN-WORKSHOP-02.115.md) · [02.116 A – keine individuellen Chat-Lesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.117 – Chat-Suche/Filter](KARTEN-WORKSHOP-02.117.md) · [02.118 A – keine gespeicherten Chatentwürfe](KARTEN-WORKSHOP-02.118.md) · [Kommunikationsworkshop 11](FEATURE-WORKSHOP.md).

## 1. Verbindlicher Beschluss – Variante 02.119 C

**Der Projektinhaber wählt C – konfigurierbare, kanal- und empfängerberechtigte sowie datensparsame Online-/Anwesenheits- und Schreibindikatoren.** Bei **aktivem 02.105-Kampagnenchat** können nach wirksamen **02.25-Kampagnen-/Regelprofil-/Kanaltyp-/Kanal-/Gruppen-/Rollen-/Personenstandards samt zulässigen markierten Ausnahmen** Schreibindikatoren und der begrenzte aktuelle Präsenzstatus **getrennt** aktiviert, deaktiviert und für tatsächlich berechtigte Zuschauer freigegeben werden. Die einzelne Person darf innerhalb dieser Policy ihre eigenen optionalen Sichtbarkeits-/Privatsphäreeinstellungen vornehmen; keine erzwungene Enthüllung verborgener privater Kontakte.

**Zwei verschiedene Informationen:**
- **Schreibindikator:** In genau einem aktuell tatsächlich erlaubten Chatbereich darf bei bewusster, berechtigter Texteingabe für kurzlebige Zeit etwa `A schreibt …` angezeigt werden. **Weder Texteingabe noch Textlänge, Keystrokes, Anhänge, Erwähnungsziel, Editorinhalt, ungelesene Nachricht oder private Draft-Information** werden dabei an andere übertragen. Der Status ist flüchtig und ohne Sendung/Lesereceipt.
- **Aktuelle Präsenz:** Unter erlaubter Policy kann etwa `online` oder `abwesend/nicht verfügbar` angezeigt werden, soweit dies aus einem **tatsächlichen autorisierten, hinreichend aktuellen Chat-/Sessionverbindungszustand** belastbar ableitbar ist. Ein grüner Punkt beweist **nicht**, dass die Person vor dem Gerät sitzt, zuhört oder eine bestimmte Nachricht gelesen hat. Ein historischer `zuletzt aktiv um 18:42`-Verlauf oder rückwirkende Anwesenheitsliste wird durch C **nicht** automatisch freigegeben.

**Beispiel:** A und B gehören zu einem freigeschalteten Teamchat. A hat Statusfreigabe aktiviert und tippt im offenen Composer. B kann gemäß aktueller Gruppen-/Empfängerpolicy vorübergehend `A schreibt …` sehen. C sitzt in einer fremden, geheimen Gruppe und sieht weder den Teamnamen noch A als Schreiber. Wenn B A als echten DM-Sender blockiert, darf A B keinen neuen DM-Schreibindikator oder gezielten Kontaktstatus als Umweg zustellen. Ein bewusst erlaubter Gruppenchat ist davon als eigener Kommunikationskontext getrennt.

**Nicht gewählt:** A (generell nie Status anzeigen) und B (universelles Tracking aller Konten und Gruppen). Bei Kampagnenerstellung **Schreibindikator Aus, Präsenz Aus** zu wählen, ist eine zulässige C-Konfiguration. **02.116 A verbietet weiterhin jede individuelle Chat-Lesebestätigung, Zustellbestätigung und Read-/Delivery-Zeitleiste. 02.118 A verbietet weiterhin gespeicherte Chatentwürfe.** Keine C-Option überschreibt diese A-Beschlüsse.

## 2. Konfiguration, Rechte und persönliche Privatsphäre

| Funktion | Fachlich zulässige Konfiguration | Zwingende Grenze |
| --- | --- | --- |
| **Schreibindikatoren An/Aus** | Kampagne, Kanaltyp, konkreter Kanal, Rolle, Gruppe/Person und gültige 02.25-Ausnahme | Nur aktueller tatsächlich schreibberechtigter Kanal; kein Entwurfs- oder Textinhalt |
| **Aktuelle Präsenz An/Aus** | Separat nach erlaubtem Kanal-/Rollen-/Gruppenscope freigeben | Keine universelle Konten-, Freundes-, SL-/DM- oder Secret-Präsenzsuche |
| **Eigene Sichtbarkeit** | Soweit die Kampagnenpolicy das vorsieht persönlich verbergen/zulassen; ggf. je berechtigtem Kanal feiner steuern | Andere Teilnehmer/SL dürfen nicht still fremde Privatsphäreeinstellungen überschreiben oder auslesen |
| **Empfänger-Sichtbarkeit** | Nur aktuell berechtigten Mitspielern des **konkreten** Kanals den erlaubten Status zeigen | Kein Status aus privater Gruppe für fremden Kanal, keine alten Memberships/Recipients |
| **Verbindung/Abwesenheit** | Belangvolle temporäre Client-/Session-/Verbindungszustände, ggf. benutzergewählte Abwesenheit | Offline/Abwesenheit nicht als tatsächliche Arbeits-/Aufmerksamkeitsbehauptung oder Personenhistorie ausgeben |
| **Kanal-Mute/DM-Block** | 02.110-Personen- und Aufmerksamkeitsfilter gelten bei Status-/Eventzustellung weiterhin | Kein DM-Typing-/Presence-Bypass zum blockierenden Empfänger, keine Blocklist/Blockursache |
| **Pflicht-Systeminformationen** | 02.101–02.103/02.109 separate Serverpfade, unabhängig von Chatstatus | Keine gewöhnliche Text-/Presence-Operation ersetzt verbindliche 02.102-Ack-Quittung |

**Getrennte Rechte konzeptionell planen:** `publishOwnTyping`, `readAllowedTyping`, `publishOwnPresence`, `readAllowedPresence`, `updateOwnPresenceVisibility` sowie für echt berechtigte Kampagnenverwaltung `configureCampaignPresencePolicy`. **Keine** Fähigkeit `readAllUsersPresence` oder `inspectAllTypingHistory` für pauschale SL-/Moderatoransichten. Ein SL-Administrationsrecht allein eröffnet keine geheimen Privat-DMs oder fremde versteckte Gruppen.

**Noch offen:** Ob die Anwendung automatisch `online/abwesend` unterscheidet oder eine grobe selbstgewählte Abwesenheit unterstützt, konkrete Standard-On/Off-Policies, Zeitfenster/TTL, Farbsignale/Icons, Gerätepräferenzen, Statusformatierung und MVP-Reihenfolge. Der Sicherheitsrahmen dieser Entscheidung ist dagegen verbindlich.

## 3. Serverseitig geschützte flüchtige Statusprojektion

1. **Vor jedem Publizieren:** Echten authentifizierten Account/Steam-Mitgliedschaft, `02.105 Chat An`, konkrete 02.106-Channel-/Gruppen-/DM-/SL-Mitgliedschaft, aktive Schreib-/Präsenz-Capability, 02.25-EffectivePolicy- und persönliche Sichtbarkeitsversion sowie 02.109-Beschränkungen prüfen. Ein manipuliertes Clientevent mit fremder Actor-ID, Nickname/Token, Fake-Kanal oder heimlichem Gruppentarget ist kein echter Status.
2. **Vor jeder Zuschauerzustellung:** Aktuelle Empfängerrechte auf denselben Kanal, erlaubte Sicht auf die konkrete Person/Kanalidentität, relevante Fog-/Secret-/NPC-/Quest-/Notiz-/Wurf-/Gruppenscopes und 02.110-Kanal-/Blockfilter erneut prüfen. Ein statusbezogener `join`/`subscribe`/`read`-Pfad darf niemals weniger geschützt sein als die echte 02.106-Chatmitgliedschaft.
3. **Keine Historienempfänger aus Status ableiten:** 02.107-heutige und historische Rechte schützen weiterhin die eigentlichen Nachrichten/DM-Historien. Status ist dagegen **eine aktuelle flüchtige Konnektivitätsinformation** und kein nachträglicher Beweis, dass jemand zu einem früheren Zeitpunkt eine Message las oder damaliger Adressat war; nicht als neuen historischen Empfängerkreis speichern.
4. **02.110-Mute und DM-Senderblocks:** Kanal-Mute unterdrückt optionale aufdringliche Präsenz-/Typing-Hinweise; bei bewusst geöffnetem Kanal darf passive aktuell berechtigte Präsenz gemäß separater 02.119-Policy weiterhin sichtbar sein – Mute ist kein Entzug der Kanalmitgliedschaft. Bei neuen direkten Status- oder Typing-Events dieselben echten Account-/Empfänger-/02.110-Senderblockregeln beachten wie bei neuen DMs. Ein blockierter Sender darf weder durch Präsenzabfragen einen Block erkennen noch dem blockierenden Empfänger gerichtete DM-Typing-Events senden. Ein gemeinsamer berechtigter Gruppenchat bleibt ein eigener erlaubter Kontext, ohne universelle persönliche Kontaktrechtserweiterung.
5. **Keine Existenz-/Aktivitätsorakel:** Autocomplete, Gruppen-/Kanallisten, Presence-Counts, Teilnehmerzahl, WebSocket-Subscriptions, Fehlercodes, Zeitunterschiede, Reconnect, Debug-/SL-Dashboard, Broadcasts und Such-/Filterpfade dürfen nicht verraten, dass eine verborgene Gruppe/DM existiert oder wer sie nutzt. Sendern keine `B hat mich blockiert`-Diagnose geben.
6. **Flüchtigkeit:** Typing- und Online-Indikatoren benötigen **kurzlebige, versionierte temporäre Serverzustände mit definierbarer Ablaufregel**, werden bei tatsächlichem gültigem Stop/Timeout, Logout, Disconnect, Policy-/Role-/Channelwechsel und Rechteentzug entfernt bzw. gegenüber bisherigen Zuschauern widerrufen. Ein verspätetes Stop-/Start-/Reconnect-Event darf sie nicht fälschlich wieder aktivieren. Konkrete TTL-Sekunden bleiben offen.
7. **Mehrgeräte/Races:** Derselbe authentifizierte Account kann mit mehreren Geräten verbunden sein. Effektiven `online`-Zustand nur aus noch aktuellen legitimen Sessions ableiten; ein einzelner Device-Disconnect schaltet andere berechtigte Sessions nicht unzutreffend ab. Typing wird an tatsächlichen berechtigten Composer-/Kanal-Kontext gebunden, nicht an jede Kampagnenverbindung global. Deduplikation, Rate-Limits, Version/CAS, Sequenzen und Expiry gegen Spam oder stale Reconnect vorsehen.

## 4. Wichtige Negativgrenzen: 02.116 A, 02.118 A und Welttrennung

**02.116 A – keine Lesebestätigungen:** `online`, `A tippt`, `A hat ein Eingabefeld offen` oder ein vorübergehender Zustandswechsel beweist niemals, dass A eine konkrete Nachricht empfangen, geöffnet oder gelesen hat. Keine `readAt`/`deliveredAt`/`lastRead`-Timestampdaten, empfängerbezogenen Häkchen, persönlichen Readcounts, automatischen Empfangsquittungen oder künstlichen SL-Einsichten durch Presence-/Typing-API. Ein reines serverinternes eigenes Send-Operationsergebnis ist weiterhin getrennt.

**02.118 A – keine gespeicherten Entwürfe:** Ein Schreibindikator sendet **niemals** den bisher getippten Text, seine Länge, Eingabeänderungen, Erwähnungs- oder Quoteziele oder einen Zwischenstand als speicherbaren Draft. Kein Auto-Save, `typingText`, Keylogging, Autoversand oder persistente Offline-Outbox. Sobald das Eingabefeld verschwindet, kann die App keine verwertbare gespeicherte Entwurfsrekonstruktion aus Typingevents ableiten.

**02.107 Historie/Retention:** Nachrichtenverläufe dürfen gemäß ihrem geltenden Empfänger-/Aufbewahrungsrecht gespeichert sein, aber ein Status ist kein Chattext. **Keine** nachträglich sichtbare persönliche Online-/Typing-Timeline, letzten-Aktivitätszeitpunkte für andere, Statistikhistorie oder Accountverhaltensprofil aus dieser Komfortfunktion. Datenschutzrechtlich nötige minimale Netzwerk-/Sicherheitsdiagnostik bleibt separat, zweck- und zugriffsbeschränkt und darf nicht als Chatstatusfunktion angeboten werden.

**02.108–02.115:** Chat-Edit/Withdraw, Meldungen, Mentions, Reaktionen, Threads, Medien, Pins/Bookmarks und die berechtigte Suche bleiben ihre eigenen Funktionen. Ein `A schreibt`-Event erzeugt weder 02.108-Nachrichtenrevision noch 02.111-@Ping, 02.112-Reaktion, 02.113-Reply, 02.114-Dateianhang, 02.115-Pin oder 02.117-Suchtreffer. Status-Events werden bei 02.105 Chat Aus nicht weiter zugestellt oder als versteckte Gegenwartsspur indexiert.

**Amtliche Systemmeldungen und Spielwelt:** 02.101–02.103-/02.109-Notice-/Safety-/Falloperationen gehen ihren eigenen geschützten Serverpfad; weder Typing noch Online löst 02.102-ACK, 02.99-SL-Freigabe oder tatsächlich wirksame NPC-/Quest-/Würfel-/Tür-/Alarm-/Sensor-/Node-/Timer-/Next-Player-/Turnoperation aus. Externer Voicechat, private Spieler-Notizen, Kartenmarker und optionale Missionsautomatisierung sind unabhängig vom integrierten Textchat.

## 5. Konzeptionelle Architektur und Umsetzungsplan

**Kandidaten – keine finalen Tabellen/APIs:** `CampaignChatPresencePolicy`, `ChatTypingCapability`, `ChatPresenceCapability`, `ChatOwnPresenceVisibilityPreference`, `ChatPresenceSessionState`, `ChatTypingEphemeralState`, `ChatPresenceProjection`, `ChatPresenceRecipientGuard`, `ChatPresenceRevision`, `ChatPresenceOperationId` und `ChatPresenceRateBudget`. Nur **flüchtige** (z. B. im autoritativen Echtzeitdienst vorgehaltene) effektive Präsenz-/Typingzustände mit Kampagne/Kanal/echtem Account, Geräte-/Sessionbindung, kurzlebiger Ablauf-/Versionsmarkierung und aktuell erlaubter Zuschauerprojektion – kein gewöhnliches `lastSeen`-/`readReceipt`-Datensatzarchiv.

**Umsetzung nach dem Featureworkshop:**
1. **Policy/Capabilities:** Getrennte `Typing An/Aus`- und `Presence An/Aus`-Schalter bei Kampagnenerstellung, je 02.25-Defaults und gültigen markierten Ausnahmen, persönliche Sichtbarkeit innerhalb der Policy; 02.105 Chat Off vorrangig; 02.116 A und 02.118 A als harte Negativgrenzen.
2. **Ephemeres Eventmodell:** Typisierte `typingStart`/`typingStop`- und grobe aktuelle `presenceUpdate`-Projektionen aus echten Sessions ohne Text/Keystrokes oder Read-/Deliveryinformationen. Ratebegrenzte Signale, TTL, Reconnect-/Disconnect-/Tabclose-/Multi-Device-/Race-Verarbeitung.
3. **Serverseitiger Berechtigungsresolver:** Vor Publish aktuelle echte Sender-/Kanal-/Gruppen-/SL-/DM-/Role-/Secretrechte und 02.109-Restriktionen; vor jedem Empfänger-Push 02.106-/02.110-Scopes, konkrete Policy-/Persona-Sichtbarkeitsversion und kanalspezifische Erlaubnis neu prüfen.
4. **Datenschutzfreundliche UI-Projektion:** Zuschauer sehen nur gerade berechtigte grobe Präsenz oder kurzes `schreibt` ohne Input-Inhalt, Listen für fremde DMs/Teams, historische Zeiten, vollständige Accountsicht oder lügende Onlinegewissheit. Nach Rights-Revocation kein alter Zustand im Badge/Cache/Reconnect.
5. **Negative Endpunkt-/Persistenztests:** Kein Draft-History-Store (02.118 A), kein Chat-Read-/Delivery-Receipt (02.116 A), keine Such-/Export-/Audit-Typinghistorie, kein Auto-`@alle` oder World-/Ack-Event.
6. **Abnahme und spätere UX:** Die Testmatrix unten prüfen; erst nach Gesamtworkshop genaue Typing-Zeitfenster, Statusicons, Farb-/Sound-/Accessibilitydarstellung, Default-Privatsphäre und MVP-Kosten abwägen.

## 6. Fachliche Abnahmetests

| Test | Erwartetes Ergebnis |
| --- | --- |
| Bei Kampagnenerstellung `Chat Aus` | Kein normales Tippen-/Präsenz-Publish/Subscribe oder Status-Reconnect; Notizen, Welt, Würfel-/Systemfeed, amtliche Notices und Voicechat bleiben |
| Chat An, Typing Aus, Presence An | Nur aktuell und wirklich berechtigt zulässiger Präsenzstatus, niemals `schreibt` |
| Typing An, Presence Aus | Kurzes `schreibt` im wirklich erlaubten Kanal, keine allgemeine Online-/letzte-Aktivitätssicht |
| Kampagnenstandard Typing An, konkrete Kanal-Ausnahme Aus | Server blockiert Tippzustand im ausgenommenen Kanal; keine Client-only-Umgehung |
| Eigene Privatsphäre-Präferenz verbietet Status | Andere Teilnehmer bekommen keine persönlich entgegen der geltenden Policy unzulässige Indikatoranzeige |
| A und B im gleichen tatsächlich berechtigten Gruppenkanal | A darf vorübergehend B als Schreiber sehen, wenn beide aktuellen Freigaberechte gelten |
| C in anderem, verborgenem Kanal rät auf As Status | Kein Typing-/Presence-Zustand, kein erratbarer Channel-/Gruppen- oder Personenstatus |
| A versucht fremde Actor-ID/Nickname zu senden | Server weist fälschlich erzeugte Status-/Charakteridentität zurück |
| B hat A als echten DM-Sender blockiert | Kein gerichteter A→B-DM-Typing- oder gezielter Präsenz-Bypass, Blockstatus selbst nicht verraten |
| A und B spielen trotzdem im gemeinsamen berechtigten Gruppenchat | Regulär zulässige Kanalpräsenz separat möglich, aber keine heimliche DM-Freigabe oder Blockdiagnose |
| SL besitzt Kampagnenverwaltungsrecht, nicht aber private DM-Rechte | Keine pauschale DM-Typing-/Online-Teilnehmerliste im SL-Dashboard |
| Tab/Browser/Netzwerk plötzlich geschlossen | Indikator läuft zeitlich ab; kein dauerhaftes `schreibt` trotz Offline |
| Zwei gleichzeitige angemeldete Geräte eines Accounts | Korrekte grobe autorisierte Präsenz, einzelner Device-Disconnect verliert nicht alle Sessions |
| Gruppen-/Rollen-/Policyentzug während Typing | Neue Empfänger-/Client-/Realtime-/Cache-Projektionen sofort unberechtigt, kein stale Replay |
| Falsche oder verspätete `typingStart`-/`typingStop`-Events | Version/TTL/Deduplikation verhindert Wiederaufleben abgelaufener Zustände und Ping-Spam |
| Spieler tippt geheime Türcodes und `@Geheimgruppe` | Kein Text-/Längen-/Keystroke-/Mentionziel-Exfiltration durch Typingevent |
| Browser wird neu geladen, Composertext war ungesendet | **02.118 A:** kein von AdventureShift gespeicherter Draft oder Restore über Präsenzzustand |
| Spieler ist `online`, öffnet aber keine Nachricht | **02.116 A:** keine Lesebestätigung, kein Empfangs- oder Lesetimestamp beim Absender |
| Spieler liest Nachricht und setzt persönliches Bookmark | Präsenz/Typing kann keine Lese-/Zustellquittung oder fremde Bookmarkliste erzeugen |
| Suche/Export nach alten Typing-/Presenceereignissen | Keine über den normalen Chat zugängliche persönliche Status-/Aktivitätszeitlinie |
| 02.101-Systemhinweis erfordert bewussten 02.102-Ack | Typing/Online/Voicechat erzeugt niemals eine offizielle Kenntnisnahmequittung |
| `A schreibt: Tür öffnen` oder Onlinewechsel | Keine echte Quest-/NPC-/Door-/Node-/Würfel-/Inventar-/Alarm-/Turnwirkung |
| Rate-/Replay-Spam durch simulierte Typing-Events | Begrenzung, Versions-/Policycheck und Empfängerschutz, kein globales Status-Broadcast |
| Kampagnenchat schaltet An→Aus oder Mitgliedschaft läuft ab | Ephemere Statusprojektion bereinigt, keine ungefragte Offenlegung von Altdaten |

## 7. Beschlussgrenze und nächste Featurefrage

**Verbindlich beschlossen: 02.119 C** – Schreibindikatoren und grobe aktuelle Präsenz sind bei wirksam 02.105 Chat An und nach 02.25-Defaults/markierten Ausnahmen getrennt konfigurierbar, jeweils ausschließlich für aktuelle, wirklich berechtigte 02.106-Kanal-/Personen-/Gruppen-/DM-/SL-Zuschauer und unter wirksamen eigenen Sichtbarkeits-/02.110-Block-/Mute-Regeln. Statuszustände sind **flüchtig, kurzlebig und ohne Inhalt/Keylogging oder gespeicherte Aktivitätszeitlinie**. Kein Geheimnis- oder Gruppenmitglieds-Leak durch Suche, Counts, Realtime, Export, Reconnect oder vermeintliche Adminansichten. **02.116 A (keine individuellen Chat-Read-/Delivery-Receipts) und 02.118 A (keine gespeicherten Entwürfe/Autosend) bleiben strikt erhalten.** Echte 02.101–02.103-/02.109-Pflichthinweise, 02.102-Acks und Weltzustandsaktionen bleiben davon unabhängig.

**Nicht beschlossen:** Bestimmte TTL-Sekunden, Farben/Icons, Anwesenheitsheuristik, pauschale `zuletzt online um`-Zeitstempel, dauerhafte Präsenzarchive, universelles Steam-/Freundes-Tracking, konkretes Privatsphäre-Default, Geräte-UI, fertige API/DB oder MVP-Priorität. Einstellungen/UX werden nach den Featureentscheidungen gesamt geplant.

## Nächste Entscheidung 02.120 – Optionale Chat-Umfragen und Abstimmungen

**Beispiel:** Im Gruppenchat möchte die Gruppe schnell zwischen drei Reiserouten abstimmen. Manche Kampagnen lösen Entscheidungen jedoch lieber ausschließlich im Voicechat oder durch die Spielleitung. Die Umfrage darf nicht automatisch eine Quest, Tür, Ressourcenbuchung oder offizielle 02.102-Kenntnisnahmequittung auslösen.

- **A – Keine integrierten Umfragen:** Spieler organisieren Abstimmungen per Chat, Voicechat oder selbst verwalteten Notizen; keine Pollobjekte.
- **B – Unbegrenzte öffentliche Umfragen:** Jeder darf alle Gruppen/DMs mit globalen Umfragen und öffentlich einsehbaren Stimmen erreichen; Ergebnisse lösen ohne Prüfung tatsächliche Spielweltaktionen aus.
- **C – Konfigurierbare, berechtigte Umfragen (Empfehlung):** Die Spielleitung legt bei 02.105 Chat An nach 02.25-Kampagnen-/Kanal-/Rollenstandards und markierten Ausnahmen fest, wer Polls erzeugen, lesen, abstimmen, schließen und Ergebnisse sehen darf. Geheime Gruppen/Teilnehmer, 02.107-Historie/Retention, 02.109-Moderation, 02.110-Blocks/Mutes und 02.116-A-Privacy bleiben geschützt. Abstimmung nur Gesprächs-/Planungshilfe, keine automatische echte Welt-/Node-/Quest-/Turn- oder System-Ack-Wirkung; Einzelheiten und UI später.
