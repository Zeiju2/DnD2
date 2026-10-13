# AdventureShift – Karten-Workshop: Beschluss 02.112 C – konfigurierbare Chatreaktionen und Rollenspiel-Emotes

**Stand:** 13.10.2026 – Fachbeschlüsse 02.1 bis 02.112; nächste offene Frage 02.113
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungsplan und Abnahmetests; **noch keine Softwareimplementierung** und keine finalen API-, Datenbank-, UI-, Emoji-Paket-, Grenzwert- oder MVP-Festlegungen.
**Bezüge:** [02.25 – Kampagnenstandards/markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – freie Notizen und Kampagnenmodi](KARTEN-WORKSHOP-02.98.md) · [02.101–02.104 – getrennte amtliche Hinweise und Acks](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106 – geschützte Chatbereiche](KARTEN-WORKSHOP-02.106.md) · [02.107 – Historie/Retention/Empfänger](KARTEN-WORKSHOP-02.107.md) · [02.108 – Nachrichtenversionen/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – persönliche Mutes/DM-Blocks](KARTEN-WORKSHOP-02.110.md) · [02.111 – Erwähnungen/Pings](KARTEN-WORKSHOP-02.111.md) · [Kommunikationsworkshop 11](FEATURE-WORKSHOP.md).

## 1. Verbindlicher Beschluss – Variante 02.112 C

**Der Projektinhaber wählt C – konfigurierbare, berechtigungsgebundene Chatreaktionen und Rollenspiel-Emotes.** Bei **02.105 Chat An** darf die Spielleitung nach den **02.25-Kampagnen-/Regelprofil-/Kanaltyp-/Kanal-/Gruppen-/Rollen-/Empfängerstandards mit gültigen markierten Ausnahmen** **Reaktionen auf Nachrichten** und **textuelle Rollenspiel-Emotes** unabhängig freigeben, sperren und auf unterstützte Arten einschränken. Auch eine Kampagne mit eingeschaltetem Textchat, aber deaktivierten Reaktionen/Emotes ist zulässig.

**Zwei bewusst verschiedene Bedienungen:**
- **Reaktion:** Ein tatsächlich autorisierter Teilnehmer kann eine erlaubte Emoji-/Symbolreaktion auf eine **bestimmte, für ihn heute UND zum Nachrichtenzeitpunkt berechtigt sichtbare 02.107-Nachricht bzw. deren zulässige 02.108-Revision** setzen oder **seine eigene** Reaktion entfernen. Eine Reaktion ersetzt oder verändert die ursprüngliche Nachricht nicht. Eine Reaktion ist keine neue Chat-Adressierung, kein `@Person`-Ping, keine Ackquittung und kein spielwirksamer Befehl.
- **Rollenspiel-Emote:** Ein Spieler kann bei vorhandener entsprechender 02.106-Sendeberechtigung und gesonderter Emote-Freigabe eine **als Handlung/Atmosphäre formatierte Textnachricht** in genau diesem berechtigten Kanal senden, z. B. `*A legt die Karte auf den Tisch*` oder, wenn als späterer Eingabemodus freigegeben, `/me nickt`. Diese Emote-Nachricht bleibt **Chatinhalt**, nicht tatsächliche Bewegung, ein Skillwurf, eine NPC-Aktion, eine Inventaroperation oder ein 02.99-verifiziertes Welt-Event. Die Anzeige verwendet eine servergebundene echte Autorenidentität; freie Figuren-/Nickname-Strings können sie nicht ersetzen.

**Beispiel:** In einem erlaubten Gruppenchat stimmt B durch einmaliges Setzen einer erlaubten Reaktion an As Plan zu. C schreibt eine als Rollenspiel-Emote erkennbare Beschreibung. Beides ist nur für die betreffenden aktuellen **und** historischen Kanal-/Nachrichtenempfänger sichtbar; weder werden fremde DMs geöffnet noch wird aufgrund von `👍` oder `/me öffnet die Tür` irgendein Weltzustand verändert.

**Nicht gewählt:** A (nie gesonderte Reaktionen) und B (unbegrenzt auf fremde/unsichtbare Nachrichten reagierbar, ungeschützte öffentliche Zähler und Reaktionslisten). Unter C können einzelne Arten bewusst deaktiviert sein.

## 2. Konfigurierbarkeit, Rechte und Arten

| Teilfunktion | Fachliches Sollverhalten | Zwingende Grenze |
| --- | --- | --- |
| **Reaktionen An/Aus** | Pro zulässigem Kampagnen-/Kanal-/Rollen-/Personenscope ein- oder ausschalten | 02.105 Chat Aus und aktuelle 02.106–02.109-ACL immer vorrangig |
| **Erlaubte Reaktionsarten** | Versionierte erlaubte Menge von Emoji-/Symbol-IDs statt beliebig ausführbarem Inhalt; auswählbare Reaktionsarten je Policy | Keine pauschale Freigabe selbst hochgeladener GIFs, Bilder, Animationen oder Skripte |
| **Reaktion hinzufügen/entfernen** | Nur bei separatem Recht, aktueller realer Accountidentität und sichtbarer zulässiger Zielnachricht; eigene Reaktion bewusst rücknehmbar | Kein stilles Entfernen oder Fälschen fremder Reaktionen ohne konkret geregelte 02.109-Moderationsbefugnis |
| **Text-Emotes An/Aus** | Bei gesondertem erlaubtem Emote-/Senderecht als typisierte Chat-Nachricht darstellen | Keine freie Fälschung des Originalabsenders oder Sonderstatus als offizielles Systemereignis |
| **Optionale Benachrichtigungen** | Gesondert erlaubte harmlose Hinweise, z. B. auf Reaktionen zu eigenen Nachrichten | 02.110-Mute/Block und 02.111-Ping-/Massenbenachrichtigungsschutz; keine ungefragten `@alle`-Pings |
| **Zähler und Namen** | Nur für berechtigt einsehbare Zielnachrichten und jeweils erlaubte Reaktionsdetails aggregieren | Keine Reaction-Existenz-, Geheimgruppen-, Absenderlisten- oder Private-DM-Leaks |

**Rechte fachlich trennen:** `canSendMessage`, `canSendEmote`, `canReact`, `canRemoveOwnReaction`, `canReadReactionSummary`, `canReadReactionActors` und eigens fall-/nachrichtenbezogene `canModerateReaction`-Fähigkeiten sind nicht automatisch deckungsgleich. `canReadReactionActors` ist **kein** generelles Spieler-/SL-Verzeichnis. Die SL kann Reaktionen z. B. nur für Teamkanäle, nur mit einem zulässigen Symbolsatz oder für einzelne Gruppen erlauben; die letztgültigen 02.25-Ausnahmen und 02.106-Kanalrechte beschränken sämtliche Fähigkeiten.

**Konkrete Einstellungsoberfläche, Default-Emojis, Reaktionsmenge je Spieler/Nachricht, maximale Textlänge, Emoji-Paketgröße, Ruhezeiten und MVP-Reihenfolge bleiben offen.** Sicherheits-, Auth-, Rate- und Datenintegritätsprüfungen sind dagegen nicht optional.

## 3. Nachrichtensicht, Herkunft und Geheimnisschutz

- **Zielnachricht existiert und ist wirklich lesbar:** Vor jedem Reaktions-Commit prüft der Server authentifizierten Akteur, 02.105 Chat An, konkrete 02.106-Channel-/Gruppen-/DM-Mitgliedschaft, aktuelle Quell-/Fog-/Secret-/NPC-/Quest-/Notiz-/Wurfrechte und **historische 02.107-Empfängerberechtigung** der Zielnachricht. Eine erratene Message-ID oder Revisions-ID darf keine Existenz verraten.
- **Kein neues Chat-/Historienrecht:** Das Reagieren öffnet keine private DM, macht keine verschwundene Nachricht wieder abrufbar und verschafft neu eingetretenen Gruppenmitgliedern keinen alten Reaktionsverlauf. Ein Reaktionszähler/Badge/Realtime-Event kann keine frühere Nachrichtensicht umgehen.
- **Aktuelle Projektion statt globaler Counts:** Ob eine Reaktion oder deren Aggregat gezeigt werden darf, hängt an heute **und historisch** berechtigter Sicht auf Zielnachricht und ggf. deren Version. Eine optionale Liste der reagierenden Teilnehmer erfordert **zusätzliche** Actor-Detailrechte; berechtigte Summen dürfen nicht über Hidden-Channel-/DM-/geheime Gruppen- oder blockierte Kontaktstatus zusätzliche Informationen enthüllen.
- **Echte Identität und Anzeigeidentität:** Server speichert den wirklichen Account als Reaktionsautor. Sichtbare Rollenspielfiguren/Charakter- oder Nicknamen können nach tatsächlichen Kampagnenrechten formatiert werden, schaffen aber weder freie Senderwahl noch Umgehung einer 02.110-Sperre. Kein Spieler darf allein durch Zeichenfolgen einen anderen reagieren lassen.
- **Erlaubte Symbole und sichere Darstellung:** Nur geprüfte, nicht ausführbare Darstellungskennungen. Text-Emotes werden sicher als Text bzw. erlaubtes Rendering behandelt, niemals als HTML, SQL, Browsercode, Shellkommando oder Node-Expression. Eventuelle später per Assetbibliothek (Bereich 12) angebotene eigene Symbole benötigen separate Upload-/Lizenz-/MIME-/Größen-/Sichtrechte; durch C noch nicht automatisch freigegeben.

## 4. Verlauf, Versionen, Bearbeitung und Aufbewahrung

**Reaktionsbezug auf eine Message-Revision:** Die konkrete Reaktion referenziert die **bei ihrer Erstellung sichtbare zulässige Nachrichtenrevision**. Wird der Nachrichtentext nach 02.108 später bearbeitet, gilt die alte Reaktion **nicht automatisch als Zustimmung zum neuen Text**: Sie wird nicht ungeprüft als aktuelle Reaktion auf die neue Fassung übernommen. Ob ein berechtigter Leser alte Reaktionen in einer zulässigen Versionshistorie sehen darf, folgt den jeweils gültigen **02.107-/02.108-Revisions-/Historienrechten**. Bestehende ursprüngliche Event-/Bearbeitungsbelege werden nicht still umgeschrieben. Neue Reaktionen auf die neue Revision müssen eigens zulässig gesetzt werden.

**Zurückziehen/Entfernen:** Bei 02.108-Withdraw/zulässiger Entfernung, 02.109-Moderationsunterdrückung, abgelaufener 02.107-Retention oder Widerruf der Ziel-/Kanalrechte keine neue Reaktion, kein neuer Reaktionshinweis und keine unzulässige alte Count-/Actor-/Search-/Export-/Reconnect-Projektion. Zuvor tatsächlich gesehenes menschliches Wissen kann nicht rückwirkend ausgelöscht werden. Erforderliche eng berechtigte Moderations-/Revisionsbelege und rechtmäßige Datenschutzlöschung bleiben eigene Prozesse, **keine unbegrenzte Reaktionsschattenhistorie**.

**Flüchtige Nachrichten:** Bei 02.107-Kommunikation ohne gespeicherten abrufbaren Verlauf werden Reaktionen höchstens so lange angeboten, wie die konkrete Zielnachricht im zulässigen **flüchtigen** Kanalkontext existiert und referenzierbar ist. Kein implizites Wiederherstellen nach Offline/Neustart, kein dauerhafter Suchindex oder Push-Nachrichtenarchiv. Bei persistierten Nachrichten richten sich Reaktionsdaten, Aggregate, Indexe, Archive, Backups und Löschgrenzen nach der geltenden Zielnachrichten-/Retention-/Datenschutzpolicy; keine selbstständige unbegrenzte Aufbewahrungszusage.

**Eigene Reaktion zurücknehmen:** Eigener Unset ist eine **neue kontrollierte Aktion**, die den effektiven aggregierten Stand anpasst; sie behauptet nicht, andere hätten die Reaktion nie gesehen. Serverseitige Idempotenz, eindeutiger effektiver Actor-/Nachricht-/Revision-/Reaktionstyp-Schlüssel und Vergleich aktueller Versionsstände verhindern Doppelklick-Spam, negative Zähler und Add-vs-Remove-Races. Fremde Reaktionen sind nur mit ausdrücklich passender 02.109-beschränkter Moderation änderbar.

## 5. Persönliche Filter, Missbrauchsschutz und unabhängige Systeme

**02.110 Channel-Mute:** Eine stummgeschaltete Unterhaltung kann ihre nach echter 02.107-Policy zulässigen Reaktionen/Emotes beim Öffnen weiterhin zeigen, aber **optionale Reaktionssounds, Pushes oder intrusive Benachrichtigungen** werden für diese Person nicht ausgelöst. Weder Reaction-Count noch gelesene Nachricht behaupten automatisch ein 02.102-Ack.

**02.110 DM-Kontaktblock:** Ein blockierter echter Absender darf seine Sperre **nicht durch eine neue Reaktion auf frühere DM-Nachrichten oder einen zusätzlichen Reaktionsping als neue Kontaktzustellung an die blockierende Person umgehen**. In Mehrpersonen-DMs wird die neue persönliche Reaktions-/Benachrichtigungsprojektion empfängergenau geschützt, statt andere berechtigte Teilnehmer pauschal auszuschließen oder falschen Komplett-Delivery-Erfolg zu behaupten. In gemeinsam berechtigten Gruppenkanälen bleiben rechtmäßig sichtbare Reaktionen/Emotes grundsätzlich mögliche Gruppeninhalte; ein **gezielter neuer Reaktionshinweis** des blockierten Accounts an die blockierende Person wird unterdrückt, ohne globale Gruppenkommunikation automatisch zu löschen. Private Blocklisten, Ursachen und individuelle Zustellstatus sind nicht über Reaction-Counts oder Fehlermeldungen ausleitbar.

**02.111 Pings:** Eine Reaktion ist **kein `@Person`-/`@Gruppe`-/`@alle`-Ping**. Text-Emotes folgen denselben 02.111-Erwähnungsrechten wie gewöhnliche Nachrichten, soweit der Inhalt tatsächlich eine erlaubte, strukturierte Erwähnung enthält. Präfixe wie `/me`, `*handelt*` oder ein Emoji verleihen keine Sonder-Broadcast-, Prioritäts- oder Benachrichtigungsrechte.

**02.109 Moderation/Anti-Spam:** Separat begrenzte Reaktionsart-/Actor-/Message-/Channel-Raten, Anti-Deduplikation und atomar begrenzte Aktualisierungen, um Reaction-Stürme, Bot-/Replay-Spam und unlimitierte Group-Mentions zu verhindern. Bestehende 02.109-Send- oder konkrete Kanalrestriktionen dürfen nicht über Reaktionsaktionen/Emotes umgangen werden. Eine eigens legitimierte, nachrichten-/fallbezogene Reaction-Entfernung kann vorgesehen werden; sie ist **kein allgemeines Recht**, fremde DMs/Reaction-Historien zu lesen, und erzeugt keine automatische Schuldentscheidung. Geschütztes Audit muss sparsam und nach aktueller Fall-/Quell-/Datenschutzberechtigung erfolgen.

**Amtliche Notices und Welt bleiben getrennt:** Eine positive Reaktion (z. B. `👍`, `✅`) ist **niemals** eine 02.102-Personenquittung, 02.99-Freigabe, Türcodeeingabe, tatsächliche Würfelprobe, Next-Player-Node, NPC-Kommunikation, Quest-Erfüllung oder Inventartransaktion. Ein textuelles `/me öffnet Tür` bewegt keine Figur, ändert keine Tür, alarmiert keine Sensoren und startet keine Nodes. Tatsächlich berechtigte 02.101–02.103-/02.109-System-/Sicherheitsinformationen bleiben auf ihrem getrennten serverseitigen Noticepfad und folgen ausschließlich dessen Konfiguration. Voicechat-first, eigenes Spielernotizbuch und Würfel-/Systemlog benötigen den optionalen Chat nicht.

## 6. Konzeptionelle Architektur und Umsetzungsplan

**Modellkandidaten (keine verbindlichen API-/Tabellennamen):** `CampaignChatReactionPolicy`, `ChatReactionType`, `ChatReactionTypeCatalog`, `ChatReactionGrant`, `ChatMessageReaction`, `ChatReactionRevisionBinding`, `ChatReactionActorScope`, `ChatReactionProjection`, `ChatReactionAggregate`, `ChatReactionOperationId`, `ChatReactionRateBudget`, `ChatReactionModerationReceipt`, `CampaignChatEmotePolicy` und `ChatEmoteMessagePresentation`. Kontexte: Kampagne, Chat-/Gruppenkontext, reale Actor-ID, konkrete 02.107-Nachricht und 02.108-Revision, tatsächlich historisch und heute zulässige Empfänger, 02.25-/02.109-/02.110-/02.111-Policyversionen, idempotente Operation, zulässige Aggregat-/Notification-Projektion und ggf. gesondert berechtigtes Moderationsaudit.

**Geplante Arbeitsschritte:**
1. **Abhängigkeiten/Policy** festlegen: 02.105 Chat An/Aus; 02.106-Sende-/Lese-/Channelrechte; 02.107 historische Retention; 02.108 Revision/Withdraw; 02.109 Moderation; 02.110 persönliche Filter; 02.111 strukturierte Mentions; getrennte Reaktions-/Emote-/Actor-Detail- und Moderations-Capabilities nach 02.25.
2. **Typisierung der Darstellungen:** Erlaubten Emoji-/Reaktionstypenkatalog versionieren, geprüfte sichere Renderingrepräsentationen vorsehen, Rollenspiel-Emote als normale typisierte Chatnachricht mit echter Autorenkennung planen; keine Ausführung von Nutzereingaben und keine implizite Asset-/Codefreigabe.
3. **Commit-/Target-Guards:** Beim Set/Unset validen Akteur, Nachricht, konkrete Revision, Channel, aktuelle **und historische** Sicht, Rolle, Retention, Send-/React-/Moderate-Policy, Quellrechte sowie wirksame Anti-Spam-Limits prüfen; echtes atomar-idempotentes Ergebnis statt clientseitig editierter Counts.
4. **Empfängerprojektion und Optionale Hinweise:** Aggregat-/Actor-/Message-/Emote-/Realtime-/Badge-/Search-/Exportansichten jeweils nach Quell-/ACL-/Historien-/Versionsrecht filtrieren; Notifications empfängerbezogen hinter 02.110-Mute-/Block-Guards, 02.111-Pinggrenzen und 02.109-Schutz legen; Sicherheits-/Korrektursystempfade eigenständig lassen.
5. **Lebenszyklus:** 02.108-Edit/Withdraw und 02.109-Suppression nicht rückwirkend als Zustimmung zu neuem Text darstellen; abgelaufene 02.107-Nachrichten, Offline-/Reconnect-/Queue-/Backup-/Lösch- und Moderationsfälle ohne unerlaubtes Schattenarchiv behandeln; CAS/Idempotenz für Add/Remove/Kollisionen.
6. **Abnahmetests/UX später:** Testfälle aus Abschnitt 7 automatisiert vorbereiten; konkrete Emoji-Palette, Zähler-/Actor-Anzeige, Tastatur, Dialoge, Fristen, Grenzwerte, Rollenspiel-Darstellung und MVP erst im abschließenden UI-/Featureworkshop entscheiden.

## 7. Fachliche Abnahmetests

| Fall | Erwartetes Ergebnis |
| --- | --- |
| Bei Kampagnenerstellung `Chat Aus` | Keine regulären neuen Reaktionen, Emotes, Reaction-Counts/-Events oder neuen Historyabrufe; geschützte Altbestände bleiben geschützt; Würfel, Notizen, Welt, amtliche Notices funktionieren |
| Chat An, Kanalreactions Aus, Text-Emotes An | Berechtigte neue Emote-Chattexte möglich, aber keine Reaction-Operation für den Kanal |
| Kanalreactions An, Emotes Aus | Berechtigte Reaktion möglich, kein typisierter Emote-Sendebefehl; normaler erlaubter Text bleibt getrennt |
| Nur bestimmte Emoji-Typen/Personen erlaubt | Ungültige bzw. nicht autorisierte Reaktion wird serverseitig abgewiesen; Clientmanipulation ändert daran nichts |
| A reagiert auf B zulässig sichtbare Nachricht | Einmaliger, nach Scope sichtbarer korrekter Reaction-Stand; keine Veränderung von Bs Originaltext |
| A verwendet dieselbe Reaktion mehrfach | Idempotenter effektiver Actor-/Ziel-/Typzustand, kein mehrfach hochgezählter Count |
| A entfernt eigene Reaktion, versucht fremde zu entfernen | Eigener Status korrekt aktualisiert; fremde Aktion ohne konkret berechtigte Moderation abgewiesen |
| A erlangt Nachricht-ID aus fremder geheimer DM | Keine Reaktion, kein erratbarer Count, kein Existenz-/Channel-/Teilnehmer-Orakel |
| Neue Gruppe tritt später bei, alter Verlauf nicht freigegeben | Alte Reactions/Actorlisten bleiben ebenso geschützt wie ursprünglicher Nachrichtentext |
| Zielnachricht wird 02.108 bearbeitet | Alte Reaktion gilt nicht automatisch für neue Textrevision; legitime alte Version allenfalls nach Revisionsrecht |
| Zielnachricht ist zurückgezogen, moderiert oder abgelaufen | Kein neuer Reaction-Commit und keine unerlaubte Count-/Search-/Reconnect-/Pushprojektion |
| 02.107 flüchtige Nachricht existiert nicht mehr | Kein neuer Reaction-Aufruf, keine automatische Archivkopie oder garantiertes Offline-Nachholen |
| A mutet einen Gruppenchat, B reagiert auf As Text | Berechtigter Reaction-Stand bei aktivem Öffnen möglich; kein zusätzlicher optionaler Notification-Ping an A |
| A blockiert B als DM-Kontakt, B reagiert auf alte Direktnachricht | Keine neue Reaktions-/Zustellungsumgehung zu A; kein verräterischer Blockgrund an B |
| B reagiert im gemeinsamen Gruppenchat; A hat B blockiert | Bestehendes Recht für Gruppentext/-reaktionen bleibt, aber kein zielgerichteter neuer Reaktionshinweis von B an A |
| Gruppen-/Mehrpersonen-DM mit individuell blockiertem Sender | Empfängergebundene Darstellung/Zustellung, keine pauschale Sperre für andere und kein falscher Komplettstatus |
| Unberechtigter Spieler nutzt `@alle` in Text-Emote | 02.111 erwähnt niemanden mit zusätzlichem Ping; Emote-Präfix kann Pings nicht freischalten |
| `/me zaubert Feuerball`, `✅` oder `👍` | Keine echten Würfel, Zauber, Quest-, Door-, NPC-, Alarm-, Sensor-, Node-, Turn- oder Inventareffekte |
| 02.102 persönlich zu quittierende Korrektur | Reaction bzw. Emote gilt nie als Ack; offizielle Quittierung bleibt getrennt |
| 02.109 Chat-Send-/Moderationsrestriktion greift | Keine Umgehung über Reaktionen/Emotes und keine universelle SL-Einsicht in fremde DMs |
| Doppelklick, Multi-Device, Add-vs-Unset-Race, Reconnect | Serverseitig atomarer, deduplizierter aktueller Zustand ohne negative/gefälschte Zähler oder Mehrfachhinweise |
| Massenspam/ungültige eigene Emoji-/Asset-URL | Rechte-, Typ-, Rate-/Sicherheitskontrolle lehnt ab, keine ausführbaren Inhalte und keine unkontrollierte Pushflut |
| Chatmodule ausgeschaltet, Gruppe nutzt Voicechat-first | Rollenspiel, private Notizen, manuelle SL-Entscheidungen und rechtmäßiges Spielprotokoll unverändert nutzbar |

## 8. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen:** **02.112 C** – Reaktionen und textuelle Rollenspiel-Emotes im optionalen 02.105-Chat sind nach **02.25-Defaults/markierten Ausnahmen** getrennt konfigurierbar, hängen an den aktuellen **und historischen** 02.106-/02.107-Chat-/Nachrichten-/Empfängerrechten und respektieren 02.108-Revisions-/Withdraw-/Retentiongrenzen, 02.109-Moderation, 02.110-Mute-/DM-Kontaktfilter und 02.111-Mentions-/Pingrechte. Originalautor, Nachricht, Reaktionsautor und echte Weltaktionen bleiben strikt getrennt. Reaktions-Aggregate/Actorlisten/Benachrichtigungen dürfen keine privaten Inhalte oder Identitäten ausleiten; Rate, Deduplikation und Idempotenz sind Pflicht.

**Nicht beschlossen:** Bestimmtes Emoji-Set, frei hochladbare Sticker/GIFs, eigene Zeichencodes und Sound/Animationen, konkrete Limits, Reaktionszeiten, UI/Shortcuts, definitive MVP-Priorität, Datenbank/API sowie automatische Welt-/Kampfsystemrelevanz von Emotes. Diese Punkte dürfen nicht ohne spätere Entscheidung als umgesetzt gelten.

## Nächste Frage 02.113 – Antworten, Zitate und Chat-Threads

**Beispiel:** In einem langen Gruppenchat möchte Spieler A auf eine konkrete ältere Nachricht von B antworten; optional sollen verwandte Antworten in einem Thread erscheinen. Gleichzeitig darf eine Antwort nicht den Text einer inzwischen verborgenen privaten Nachricht anderen Spielern zeigen.

- **A – Kein Nachrichtenbezug:** Antworten erscheinen als gewöhnliche Nachrichten ohne verknüpftes Ziel, Zitatvorschau oder Thread.
- **B – Unbegrenzte Zitate und Threads:** Jeder kann jede beliebige Message-ID referenzieren oder deren Text in andere Kanäle kopieren; alte/geheime Nachrichten können dadurch unerlaubt offenbart werden.
- **C – Konfigurierbare berechtigte Antworten/Zitate und optionale Threads (Empfehlung):** Nach Kampagnen-/Kanal-/Rollenpolicy und 02.25-Ausnahmen darf ein berechtigter Teilnehmer ausschließlich auf **für ihn tatsächlich aktuell und historisch lesbare Nachrichten** reagieren/antworten, deren zulässiger Referenztext nur berechtigten Empfängern gezeigt wird. Threads und Querverweise bleiben mit 02.107-/02.108-/02.109-/02.110-/02.111-/02.112-Rechten, Revocation und Retention vereinbar; keine automatische Geheimnis-, DM-, Ping- oder Weltfreigabe. Konkrete Oberfläche später.
