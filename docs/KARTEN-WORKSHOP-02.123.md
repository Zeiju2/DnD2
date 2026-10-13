# AdventureShift – Karten-Workshop: Beschluss 02.123 A – keine integrierte Weiterleitung von Chatnachrichten

**Stand:** 13.10.2026 – Fachbeschlüsse 02.1 bis 02.123; nächste offene Frage 02.124
**Status:** Verbindlicher Fachbeschluss und konzeptioneller Umsetzungs-/Abnahmeplan; **noch keine Softwareimplementierung**, keine finalen API-/DB-/UI-Verträge, keine MVP- oder Grenzwertfestlegung.
**Bezüge:** [02.25 – Kampagnenstandards und gültige markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – private/gezielt geteilte Notizen und Kampagnenoptionen](KARTEN-WORKSHOP-02.98.md) · [02.99 – manuelle echte Welt-/Regelaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – amtliche Hinweise/ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106 – geschützte Chatbereiche](KARTEN-WORKSHOP-02.106.md) · [02.107 – aktuelle/historische Nachrichtensicht und Retention](KARTEN-WORKSHOP-02.107.md) · [02.108 – Edit/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – Mutes/DM-Blocks](KARTEN-WORKSHOP-02.110.md) · [02.111 – Mentions/Pings](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen/Emotes](KARTEN-WORKSHOP-02.112.md) · [02.113 – berechtigte Antworten/Threads/Quotes](KARTEN-WORKSHOP-02.113.md) · [02.114 – sichere Dateien/Links/Previews](KARTEN-WORKSHOP-02.114.md) · [02.115 – Pins/Bookmarks](KARTEN-WORKSHOP-02.115.md) · [02.116 A – keine Read-/Delivery-Receipts](KARTEN-WORKSHOP-02.116.md) · [02.117 – geschützte Chat-Suche/Filter](KARTEN-WORKSHOP-02.117.md) · [02.118 A – keine gespeicherten Entwürfe](KARTEN-WORKSHOP-02.118.md) · [02.119 – flüchtige Typing-/Präsenzanzeigen](KARTEN-WORKSHOP-02.119.md) · [02.120 – Chat-Polls](KARTEN-WORKSHOP-02.120.md) · [02.121 A – einfacher mehrzeiliger Chattext](KARTEN-WORKSHOP-02.121.md) · [02.122 A – keine Chat-Sprachnachrichten](KARTEN-WORKSHOP-02.122.md) · [Bereich 11 Kommunikation](FEATURE-WORKSHOP.md).

## 1. Verbindliche Entscheidung – Variante 02.123 A

**Der Projektinhaber hat ausdrücklich A gewählt: Keine systemseitige Weiterleitungsfunktion für Chatnachrichten.** AdventureShift bekommt im optionalen, bei Kampagnenerstellung gemäß **02.105** aktivierbaren Chat **keine Nachricht-weiterleiten-Schaltfläche, kein Forward-to-Channel-Menü, keine „in andere Gruppe teilen“-Aktion und keine technische Erzeugung einer neuen Nachricht aus einer alten vollständigen Chatnachricht samt Autoren-, Zeit-, Kanal-, Empfänger-, Datei-, Poll- oder Secret-Metadaten**. Weder bestehende DMs noch Gruppen-, Kampagnen- oder SL-Chatbeiträge dürfen dadurch automatisch anders adressiert werden.

**Kein versteckter C-Modus:** 02.25-Kampagnen-/Channel-/Rollen-Defaults und markierte Ausnahmen aktivieren diese **bewusst ausgeschlossene** Komfortfunktion nicht. Die SL erhält keinen `AllowMessageForwarding`-Schalter, und weder Client, API, Adminansicht, Suchergebnis noch Realtime-Schnittstelle schafft heimlich einen gleichwertigen Forwarding-Bypass. Eine spätere Einführung verlangt eine neue ausdrückliche Fachentscheidung.

**Erlaubt bleibt gewöhnliche menschliche Kommunikation:** Eine Person kann Informationen, die sie tatsächlich kennt, im erlaubten Zielchat **bewusst in eigenen Worten** oder als selbst neu getippten **02.121-A-Klartext mit Absätzen** formulieren und nach gültiger aktueller **02.106-/02.109-/02.110-Sendeberechtigung** absenden. Das ist eine **eigene neue Nachricht des tatsächlichen Absenders** mit neuem 02.107-Nachrichten-/Empfänger-/Historienkontext, **keine automatisch legitimierte Weitergabe** der ursprünglichen Nachricht. Das System kann bereits bekannt gewordenes menschliches Wissen oder manuelles Kopieren in fremde Programme nicht technisch „ungeschehen“ machen; es darf aber **keinen eigenen UI-/API-Helfer** zum automatischen Überführen fremder geschützter Inhalte einführen.

**Beispiel:** A liest eine für A rechtmäßig sichtbare Teamnachricht und möchte einen Treffpunkt in einem anderen Team diskutieren. A kann dort – falls zum neuen Team überhaupt schreibberechtigt und nicht 02.109-/02.110-gesperrt – einen eigenen Text schicken. AdventureShift bietet **kein „Originalnachricht weiterleiten“** an und kopiert weder den echten Ursprungsautor B noch eine damalige Empfängerliste, private DM, alte Revision, Dateianhang oder Pollabstimmung in den neuen Kanal.

**Nicht gewählt:** B (ungeprüfte universelle Weiterleitungen) und C (konfigurierbare abgesicherte Weiterleitung). Unter A wird **nicht** die technisch bereits beschlossene 02.113-Antwortfunktion innerhalb des tatsächlich erlaubten Kanalkontexts beseitigt.

## 2. Abgrenzung zu bereits beschlossenen Chatfunktionen

| Vorhandene Funktion | Weiterhin erlaubt nach eigenen Rechten | Durch 02.123 A ausdrücklich nicht erlaubt |
| --- | --- | --- |
| **02.121-Klartext schreiben** | Eigene, bewusst gesendete Nachrichten mit Absätzen im aktuell autorisierten Chat | One-Click-Reposting samt Originalautoren-/Quellenmetadaten |
| **02.113 direkte Antworten/Zitate** | Nur die bei 02.113 tatsächlich autorisierten **same-channel** Parent-/Quote-/Thread-Referenzen und pro Leser geschützte Vorschau | Weiterleiten einer Nachricht in einen anderen Kanal unter dem Deckmantel von „Antworten“ |
| **02.114 Anhänge/Bilder/Links** | Nur nach separat erlaubtem Dateityp, Quell-/Ziel-/Message-/Asset-/Downloadrecht und sicherer Uploadpipeline | Automatisches Kopieren privater Bilder/Dateien aus alten DMs durch Forward-ID oder Text-/Anhangslink |
| **02.115 Kanalpins/Lesezeichen** | Berechtigt sichtbare Nachrichten im ursprünglichen Kanal anheften oder für sich merken | Pin/Bookmark als „Crosspost“ in fremde Gruppe oder neue dauerhafte Originalkopie |
| **02.117 Suche/Filter/Exports** | Heute UND historisch rechtmäßig lesbare Textsuche und etwaige ausdrücklich erlaubte Datenansichten | Suchresultat-/Exportaktion „Weiterleiten nach …“ mit Quelltext, Resultcount, geheimem Kanalnamen oder Anhang |
| **02.120 Umfragen** | Umfragen und Stimmen in ihrem tatsächlichen berechtigten ursprünglichen Chat | Crosspost desselben Poll-/Voter-/Resultobjekts mitsamt alten Empfängern |
| **02.111 Mentions, 02.112 Reaktionen** | Berechtigte Erwähnungen, eigenständige Reaktions- oder Emoteaktionen | Eine Erwähnung oder Reaktion als verdeckte Cross-Channel-Messageforward-Aktion |
| **02.108 Edits/Withdraw, 02.109 Moderation** | Vorhandene originale Nachrichten und Fälle mit ihren unveränderten Version-/Quell-/Falldaten schützen | Moderations- oder Bearbeitungsrecht als universelle Weiterleitungs-/Privat-DM-Kopierberechtigung |
| **02.94–02.98 eigenes Notizbuch** | Eigene Notizen privat oder bewusst nach eigenen **separaten** Berechtigungen teilen | Automatisches Spiegeln privater Originalchats in geteilte Notizen ohne eigenständige Entscheidung |
| **02.122 Voicechat/Audio** | Externe Voicechatgespräche, ggf. eigens erlaubte 02.114-Dateien und 02.51-Szenensound bleiben eigenständig | Abgewähltes Audio-Voice-Memo- oder Chatweiterleitungsmodul als Audio-Workaround |

**Begriffsabgrenzung:** „Neue eigene Textnachricht schreiben“ und „systemseitig die originale Chatnachricht weiterleiten“ sind **verschiedene Vorgänge**. Ein Spieler darf nicht die Originalabsenderidentität fälschen oder eine im Ursprungs-DM vorhandene Chatquelle durch einen erratenen `MessageId`-Referenzcode automatisch im Zielraum lesbar machen. Bei Freitext können Wörter wie „B sagte ...“ stehen; das ist **kein** serverbestätigtes Originalzitat oder dokumentiertes Approval durch B.

## 3. Geschützte Daten, Senderidentität und Rechte bei bewusst neu verfasstem Text

1. **02.105 Chat An/Aus:** Bei ausgeschaltetem Chat existieren weder reguläre neue Message-Sends noch ein versteckter Forward-/Crosspost-Endpunkt. Offizielle 02.101–02.104-Mitteilungen, Würfel/Systemlog, eigene 02.94-Notizen und externer Voicechat bleiben unabhängig.
2. **02.106 neuer Zielchat:** Ein selbst geschriebener Text muss die **heute gültige** echte Kampagnen-, Kanal-, Rollen-, Gruppenzugehörigkeits- und DM-Empfänger-Sendeberechtigung des wirklichen Accounts erfüllen, einschließlich 02.109-Moderationsrestriktionen und 02.110-DM-Kontaktsperren. Nachricht ist neu und hat einen **eigenen** 02.107-Ursprungs-Recipient-Snapshot; der originale alte Kanal bekommt dadurch keine neue Mitgliedschaft und der neue Kanal kein Recht auf den alten Chat.
3. **02.107 Quell-/Historiengeheimnisse:** Die App darf alte Texte nur nach **heutigen UND historischen** ursprünglichen Message-/Empfänger-/Fog-/Secret-/Gruppenrechten zeigen, suchen, zitieren oder herunterladen. Ein Nutzer darf niemals durch Kenntnis einer ID, eines URL-Tokens, einer alten Exportzeile oder eines neuen Kanals **automatisch** geschützte Originaldaten auslesen. Die Tatsache, dass Menschen sich legale Beobachtungen erzählen können, macht die appseitige Quell-ACL nicht optional.
4. **Echte Autoren-/Zeit-/Kanalmetadaten:** Das System darf fremde Originalautoren, Nachrichtenversionen, vertrauliche Gruppenlabels, Zeitstempel, Umfrageoptionen, Abstimmendenlisten oder Empfängerlisten **nicht** als „offiziell weitergeleitet“ an einen neuen Text binden. Der neue Text trägt den wirklichen aktuellen Autor; eigene eingegebene Zitate sind nicht kryptographisch oder serverseitig als Originalsiegel zu behandeln.
5. **02.108-/02.109-Revision/Withdraw/Moderation:** Zurückgezogene, abgelaufene oder konkret gesperrte Originalnachrichten werden über normale 02.107-/02.108-/02.109-Rechte nicht erneut lesbar, suchbar oder als automatischer Forward-Snapshot veröffentlicht. Ein menschlich früher gesehener Text kann nach eigenem zulässigem Neuschreiben vom neuen Autor stammen; das erzeugt **keinen** wieder gültigen alten Quellenbeleg und keine automatische Erlaubnis zur Veröffentlichung vertraulicher Materialien.
6. **02.114 Anhänge:** Wer ein Bild wirklich neu teilen möchte, müsste **gesondert** das nötige Recht auf die ursprüngliche Datei, das neue Upload-/Ziel-/Empfängerrecht, Datenschutz und ggf. Lizenz-/Assetbibliotheksregeln nach 02.114 erfüllen. Keine alte private Anhang-ID einfach in andere Kanäle einfügen, um signierte Downloads/Thumbnails/Linkvorschauen oder historische Retention zu umgehen.
7. **02.113 Quoterechte:** Weiterhin gültig bleiben lediglich tatsächlich berechtigte Quellen-/Parent-/Threadbezüge **im erlaubten Chatkontext**; kein uneingeschränkter kanalübergreifender „verwandte Nachricht“-Referenzpfad durch 02.123.
8. **02.25 macht kein Verbots-Override:** Eine mit Kampagnen-Defaults/markierten Ausnahmen eingerichtete 02.111-Mention, 02.114-Media-, 02.115-Pin- oder 02.117-Suchfähigkeit ist kein Forwardingrecht. Sicherheits-/ACL-/Secret-/Retention-/Moderationskontrollen bleiben verpflichtend.

## 4. Datenmodell und Abnahmegrenzen – negativer Architekturentscheid

**Nicht als Chat-Feature planen:** `ChatMessageForward`, `ChatForwardDestinationPicker`, `ForwardOriginalAuthorMetadata`, `CrossChannelForwardCommit`, `ForwardOriginalAttachmentBinding`, `ForwardMessageSubscription`, `ForwardHistoricalRecipientSnapshot` und allgemeine `canForwardMessage`-/`canForwardPrivateDM`-Capabilities oder eine universelle `POST /chat/messages/{id}/forward`-API. Keine „Weiterleiten“, „Forward“, „Crosspost“ oder „in anderem Chat teilen“-Schaltfläche an Nachrichten, in Searchhits, Pins, Quotes, Moderationsfallansichten oder Pollkarten. Ein gewöhnlicher 02.106-Message-Send bleibt ein eigenständiges Feature und darf keine unbekannten Originalreferenzen serverseitig auflösen.

**Nichts rückwirkend entfernen:** Bestehende, zuvor fachlich beschlossene 02.113-Quote-/Reply-/Threadrechte, 02.114-Messagebound-Media-/Linkanzeigen, 02.115-Bookmarks/Channelpins und 02.107-Autorisierung bleiben unverändert. 02.121 A einfacher Text mit Absätzen statt Rich-/Markdown-/Spoiler, 02.122 A kein Voice-Memo-Modul, 02.118 A kein Draft-Store/Autosend sowie 02.116 A keine individuellen Read-/Delivery-Receipts sind weiterhin harte Ausschlüsse.

**Neue Nachricht ist eigenes Event:** Wird ein Ergebnis aus Tischgespräch, Voicechat oder eigener Erinnerung manuell in neuem erlaubtem Text mitgeteilt, gilt die heute echte Account-/Kanal-/Senderechtprüfung, 02.107 neuer eigener Recipient-/Retentionkontext und eindeutige Commit-/OperationId. Doppelklicks/Retries dürfen keine falschen Mehrfachsendungen erzeugen. Das Quellchatlog wird nicht rückwirkend verändert, ursprüngliche Send-/Editbelege bleiben echt, und es wird **keine** vermeintliche originale „weitergeleitet von B“-Autorisierung erzeugt.

**Kein technisches Geheimhaltungsversprechen über menschliches Wissen:** Die Plattform kann erlaubterweise gezeigten Text nicht aus menschlicher Erinnerung oder aus systemunabhängigen Browser-/OS-Funktionen löschen und soll nicht behaupten, manuelles Kopieren und Abtippen sei unmöglich. Sie darf aber nicht selbst ein leicht missbrauchbares Quellnachrichten-/DM-/Medien-Kopier-API bereitstellen oder fremde alte Nachrichten an neue Empfänger ausleiten.

**Unabhängige Spielmechanik und amtliche Mitteilung:** Chatweiterleitungsverbot verhindert oder erzeugt keine tatsächlichen World-/Quest-/NPC-/Tür-/Node-/Turn-/Inventar-/Würfel-/Alarm-Ereignisse. Eine neue erlaubte Textnachricht ist **kein** echtes 02.99-World-Commit und auch keine gesonderte 02.102-Kenntnisnahmequittung; amtliche 02.101–02.104-/02.109-Sicherheitshinweise verbleiben auf ihren eigenen verlässlichen Berechtigungswegen.

## 5. Konzeptioneller Umsetzungsplan

1. **Negativen Funktionsumfang dokumentieren:** Im 02.25-Settingsinventar und im optionalen 02.105-Chat ausdrücklich **kein Forwardingmodul/Schalter**, keine `canForward`-Sonderberechtigung oder private-channel-zu-public Kopieraktion. Gültige 02.106–02.122-Grenzen übernehmen, ohne deren unabhängige Funktionen still abzuschalten.
2. **UI-/API-Flächen kontrollieren:** Kein Forwardmenü oder direktes „an anderen Channel senden“ an Message, Reply, Poll, Medienanhang, Searchhit, Bookmark, Channelpin, Desktop-Kontextmenü oder Admin-/Moderationsliste; keine verdeckte Message-ID-/Attachment-ID-zu-Crosspost-REST-/WebSocketaktion.
3. **Gewöhnliches Senden hart abgrenzen:** Bei jeder selbst neu verfassten 02.121-Klartextnachricht echte aktuelle 02.105-/02.106-Kanal-/Account-/Empfänger-/02.109-Sendrestriktions- und 02.110-DM-Block-Policy prüfen. Keine frei eingesetzten Originalauthor-/Originalchannel-/Recipient-/Forward-Felder als vertrauenswürdige Messageattribute übernehmen.
4. **Quellenrechte weiter schützen:** Bei 02.107-Read/Search/Export, 02.113-Quotes/Thread-Bezügen und 02.114-Anhängen heutige **und historische** Quell-/Empfänger-/Revision-/Retentionrechte serverseitig validieren. Bewusst neues legales Datei-/Linkteilen nur im wirklich separat zugelassenen 02.114-Zielscope und nach gültigen Eigentums-/Nutzungsrechten, kein Originalattachment-ID-Bindungs-Bypass.
5. **Lebenszyklus/Datenschutz:** 02.108-Edit/Withdraw, 02.109-Moderation, 02.110-Block, 02.107-Retention, 02.116-A-no-receipts, 02.118-A-no-drafts und 02.122-A-no-voice-memo-Guards für Query, Cache, Export, Realtime, Reconnect und Sendstatus unverändert behalten. Keine neue dauerhafte Crosspost-/Forwarding-Schattenhistory.
6. **Abnahmetests/UX später:** Die unten aufgeführten Negativtests vorbereiten; konkrete Composer-/Copy-/Paste-/Info-UI erst nach Gesamtworkshop festlegen. Kein Funktionierender-Forwarder-Prototyp und keine Softwareimplementierung wird durch diesen Beschluss behauptet.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Chat An bei Kampagnenerstellung | Gewöhnliche zulässige Nachrichten möglich, **kein** Forward-/Crosspost-Menü |
| Chat Aus | Keine neue normale Chat-Send- oder versteckte Weiterleitungsoperation, unabhängige Notizen/Systemnachrichten bleiben |
| SL aktiviert alle unterstützten 02.25-Chat-Komfortmodule | Trotz Defaults/markierter Ausnahmen **kein** Forward-Feature/`AllowForward`-Schalter |
| Spieler klickt auf berechtigte private DM-Nachricht | Kein `Weiterleiten an Team`-Button oder automatischer Copy-to-Channel-Pfad |
| Spieler will Teamtreffpunkt in anderem Team besprechen | Muss im neuen gültig berechtigten Kanal **eigene** Nachricht bewusst formulieren/senden |
| Neues Teammitglied darf alten Quellchat nicht historisch lesen | Keine alten Message-/Author-/DM-/Count-/Anhang-/Secretinfos durch neue eigene Nachricht automatisiert auslesbar |
| Autorwechsel: A schreibt eigenen Text zu Bs alter Aussage | Neuer Message-Author ist echt A, keine gefälschte `original von B weitergeleitet`-Kennung |
| A errät alte private Message-ID und baut Forwardrequest | Keine autorisierte Forward-API, kein Auskunfts-/Existenz-/Kanalorakel |
| 02.113 Antwort im selben wirklich berechtigten Kanal | Weiterhin möglich nach 02.113-Quote-/Parent-/Threadrechten |
| 02.113 Reply in anderer Gruppe mit geheimer Parent-ID | Kein Cross-Channel-Forwarding oder automatischer Import des Parenttexts |
| 02.114 privates DM-Bild wird in neue Gruppe „weitergeleitet“ | Kein Kopieren per alter Asset-ID; neue zulässige Übernahme nur über eigene echte Datei-/Ziel-/Lizenzrechte |
| 02.114 erlaubter gewöhnlicher Link als neuer Text | Linktext kann nach eigenem Chat-/Linkrecht geschrieben werden, kein automatisches Weiterleitungszitat |
| Kanalpin/Bookmark/Searchresult eines alten Texts | Nur erlaubte Quellansicht/Navigation, keine Spezialaktion `Forward to Group` |
| 02.120 Poll mit geheimen Voter-Details | Kein Crosspost samt Poll-/Option-/Voter-/Resultobjekt in anderen Kanal |
| Original wurde 02.108-editiert/withdrawn oder 02.109-moderiert | Alte berechtigte Original-Such-/Read-/Exportpfade geben keine verbotene alte Fassung per Forward frei |
| Blockierter DM-Sender versucht Spezialweiterleitung | Keine neue Kontaktzustellung; 02.110-DM-Block und normale Sendeguards bleiben |
| Neue eigene Nachricht in anderem Team trotz 02.109-Sendsperre | Server weist sie ab, kein Umgehen durch Copy-/Reply-/Anhangstrick |
| Zwei Geräte/Offline/Retry beim eigenen Textversand | Nur absichtlich ausgelöste echte idempotente 02.106-Send-Operationen, kein Forward-/Autosend bei Reconnect |
| 02.116 A verbietet Lesestatus | Kein persönliches `B erhielt/gelesen die Weiterleitung`-Tracking, das abgewählte Feature existiert nicht |
| 02.118 A verbietet gespeicherte Entwürfe | Kein automatisches Forward-Draft-/Outbox-Speichern oder erneutes Senden |
| 02.121 A erlaubt Absätze | Eigener mehrzeiliger Text bleibt absatztreu, kein heimlicher Rich-/Originalquote-Renderer |
| 02.122 A kein Chat-Voice-Memo | Kein Audio-Forwarder oder Voice-Clip-Reupload als Sonderfunktion |
| Rechtmäßig persönliche 02.94-Notiz | Kann eigenständig privat/gezielt nach Notizrechten bestehen; Chat übernimmt sie nicht automatisch |
| Normale Chatnachricht behauptet „Tür öffnen“ oder „ACK“ | Kein echter 02.99-Welt-/02.102-Ack-Effekt durch eigene Chatworte |
| Mensch erinnert sich an alte zulässig gesehene Information | System verspricht keine unmögliche technische Löschung menschlicher Erinnerung, bietet aber keinen Quell-Forward-API |

## 7. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.123 A – keine systemseitige Chatnachrichten-Weiterleitung.** Es gibt keinen auf 02.25-/02.105-Defaults oder Ausnahmen beruhenden Forwarding-Schalter, keine Cross-Channel-Weiterleitungsrechte, kein neues Quellautoren-/Quell-DM-/Attachment-/Poll-Snapshot-Reposting und keine Spezial-API. Selbst neu verfasste Nachrichten in einem tatsächlich erlaubten neuen 02.106-Kanal bleiben mit eigenem echten Autor und **neuem eigenen 02.107-Empfängerkontext** möglich, sofern die heutigen Sendeberechtigungen gelten. 02.107-Read/Search/Quote/Attachment-Zugriffe prüfen weiterhin **heutige UND historische Originalberechtigungen**; 02.113-geschützte Same-Channel-Replies und 02.114-separat zugelassene Dateien bleiben unverändert. 02.116 A ohne individuelle Chatlesebestätigungen, 02.118 A ohne gespeicherte Entwürfe, 02.121 A mit einfachem absatzfähigem Chattext und 02.122 A ohne Voice-Memos gelten fort. Keine offizielle 02.102-Ack- oder echte 02.99-Weltwirkung durch Text.

**Nicht beschlossen:** Allgemeines Verbot, eigene Worte zu schreiben, menschliche Erinnerungen zu erzählen oder systemunabhängige Betriebssystem-Kopieraktionen zu verwenden; kein Entzug zuvor gewährter berechtigter 02.113-Quote-/Reply-Rechte, keine zusätzlichen pauschalen 02.114-Dateitypverbote. Eine spätere systemseitige Weiterleitungsfunktion würde einen neuen Beschluss brauchen.

## Nächste Entscheidung 02.124 – Automatische Chat-Übersetzung

**Beispiel:** Ein Spieler schreibt in einer anderen Sprache. Ein Mitspieler möchte den Text in seiner eigenen Sprache lesen, ohne dass geheime DMs und geschützte Kampagnennachrichten ungefragt an fremde Übersetzungsdienste geschickt werden.

- **A – Keine integrierte Übersetzung:** Spieler lesen den ursprünglichen Text und übersetzen selbst mit eigenen Mitteln; AdventureShift bietet keinen Übersetzungsdienst im Chat.
- **B – Universelle Fremdübersetzung:** Jede Nachricht – auch geheime DMs und früher verborgene Texte – wird ohne Einwilligung automatisch an beliebige externe Übersetzungsanbieter übertragen und für alle angezeigt.
- **C – Konfigurierbare berechtigte und datensparsame Übersetzung (Empfehlung):** Bei 02.105 Chat An erlaubt die SL nach 02.25-Policy und markierten Ausnahmen nur für jeweils **heute UND historisch** lesbare Nachrichten optionale angefragte Übersetzung. Eigene Autor-/Empfänger-/Kanalrechte, 02.107-History/Retention, 02.108-Revision, 02.109-Moderation, 02.110-Block/Mute und 02.121-Klartext gelten. Externe Anbieter/Datenschutz und Speicherung sind nur nach gesonderter Berechtigung/Transparenz möglich; niemals automatisch Welt-/Node-/Quest-/ACK-Rechte oder versteckte Gruppen-/Originaltexte freigeben. Genaues UI und Sprachen später.
