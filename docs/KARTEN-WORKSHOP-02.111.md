# AdventureShift – Karten-Workshop: Beschluss 02.111 C – berechtigte Chat-Erwähnungen und persönliche Pings

**Stand:** 13.10.2026 – Fachbeschlüsse 02.1 bis 02.111; nächste offene Frage 02.112
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungsplan und Abnahmetests; **keine Softwareimplementierung**, keine finalen API-/Datenbankverträge, keine festgelegten Ping-Limits oder fertige UI-/MVP-Priorisierung.
**Bezüge:** [02.25 Kampagnenstandards und markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 Spielernotizen, Marker und schaltbare Kampagnenfunktionen](KARTEN-WORKSHOP-02.98.md) · [02.101–02.104 amtliche Mitteilungen und Acks](KARTEN-WORKSHOP-02.104.md) · [02.105 Chat An/Aus bei Kampagnenerstellung](KARTEN-WORKSHOP-02.105.md) · [02.106 Channel-/Rollen-/Gruppen-/DM-Scope](KARTEN-WORKSHOP-02.106.md) · [02.107 aktuelle und historische Rechte/Retention](KARTEN-WORKSHOP-02.107.md) · [02.108 Edit/Withdraw/Revision](KARTEN-WORKSHOP-02.108.md) · [02.109 Melden/Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 persönliche Mutes/DM-Senderblocks](KARTEN-WORKSHOP-02.110.md) · [Kommunikationsworkshop 11](FEATURE-WORKSHOP.md).

## 1. Verbindliche Entscheidung – Variante 02.111 C

**Vom Projektinhaber ausdrücklich gewählt: C – konfigurierbare, tatsächlich berechtigte und persönliche Filter respektierende Erwähnungen/Pings.** Nur wenn der **integrierte Chat bei Kampagnenerstellung nach 02.105 aktiviert** und ein konkreter 02.106-Kanal für Sender und Ziel aktuell erlaubt ist, können ausdrücklich dafür berechtigte Teilnehmer erlaubte **`@Person`-, `@Gruppe`-, `@SL`- und gegebenenfalls `@alle`-Erwähnungen** benutzen. Die SL konfiguriert nach 02.25 **Kampagnen-/Regel-/Kanaltyp-/Kanal-/Gruppen-/Rollen-/Empfängerstandards und zulässigen markierten Ausnahmen**, welche Erwähnungsarten und Senderrechte unterstützt und aktiv sind. Nicht jede Kampagne und nicht jeder Chatbereich muss Pings anbieten.

**Zwei Ebenen strikt trennen:** Ein **Chattext** bzw. eine 02.108-Revision ist eine Nachricht an den durch 02.106–02.107 berechtigten Empfängerkreis; eine **optionale Pingbenachrichtigung** ist eine zusätzlich durch Rechte und persönliche 02.110-Filter begrenzte Aufmerksamkeitsfunktion an einzelne tatsächlich berechtigte Personen. Eine Erwähnung erweitert **niemals** Kanalsicht, Gruppenmitgliedschaft, Empfängerhistorie, Nachrichten-Leserecht oder DM-Zustellbarkeit.

**Beispiel:** Spieler A schreibt im für beide tatsächlich sichtbaren Gruppenchat `@B, prüfst du die Tür?`. Nur wenn A berechtigt erwähnen darf, B zum konkreten Kanal gehört, diese konkrete Erwähnung erlaubt ist und Bs persönliche Stummschaltung/Blockierung keinen Ping ausschließt, erhält B den optionalen Hinweis. Der Chattext bleibt nur nach normalen Gruppenrechten lesbar. `@Geheimteam` oder `@alle` darf keine versteckten Mitglieder aufdecken oder unberechtigt Massenhinweise erzeugen.

**Nicht gewählt:** A (Erwähnungen grundsätzlich ohne Funktion) und B (beliebige unbeschränkte Pings einschließlich stummgeschalteter, blockierter und geheimer Empfänger) sind keine zwingenden Verhaltensweisen. Eine Kampagne ohne aktivierte Ping-Arten ist eine zulässige C-Konfiguration.

## 2. Konfiguration: Erwähnungsarten, Senderrechte und Empfängergrenzen

| Erwähnungsart | Zulässiges Verhalten bei aktivierter Policy | Grenze |
| --- | --- | --- |
| **`@Person`** | Eine konkrete authentifizierte, im aktuellen Kanal tatsächlich ansprechbare Person adressieren, sofern Sender dafür berechtigt ist | Keine Suche in fremden/verborgenen Account-, Kanal-, Gruppen- oder DM-Teilnehmerlisten; kein alleiniger Nickname-Beweis |
| **`@Gruppe`** | Bei gesonderter Berechtigung berechtigte Mitglieder einer im **selben Kanal** zulässig erwähnbaren Gruppe adressieren | Keine kampagnenweite Gruppenauflösung, kein Offenlegen geheimer Mitgliedschaften oder Weiterleiten in fremde Chats |
| **`@SL`** | Nur erlaubte, für den konkreten Kanal tatsächlich adressierbare SL-Rolle/-Empfänger erreichen | Keine Pflichtzustellung; keine Offenlegung verborgener SL-Accounts, kein Allzugriff der SL auf fremde DMs |
| **`@alle` / Channel-Ping** | Optional nur bei ausdrücklich dafür erteilter Fähigkeit für den **jeweiligen Kanal** und unter separaten Massenpinggrenzen | Kein Default-Superrecht, keine Pings an Mitglieder außerhalb aktueller/historisch zulässiger Empfängerbindung |
| **Unaufgelöstes `@Wort`** | Bleibt harmloser gewöhnlicher Chattext, nicht als privilegierter Ping wirksam | Kein Erraten versteckter Identitäten durch Fehlermeldungen, Autocomplete oder Unterschiede in Counts |

**Getrennte Capabilities planen:** Ein echtes Nachrichtensenderecht ist **nicht** automatisch ein Recht auf `@Gruppe`/`@SL`/`@alle`. Erwähnungen pro unterstütztem Typ ausdrücklich konfigurieren; 02.109-Sendbeschränkungen und aktuelle Kampagnen-, Kanal-, Rollen-, Personen- und Gruppenrechte bleiben vorrangig. Bei **Chat Aus** kann keine neue normale Erwähnung ausgelöst oder wiederholt werden; die Welt- und Systemfunktionen bleiben unabhängig aktiv.

**Keine abschließenden Standardzahlen:** Die genauen Pingmengen, Zeitfenster, Ruhezeiten, Popup-/Soundtypen und die Settings-UI werden nach Abschluss des gesamten Featureworkshops festgelegt. Das fachliche **Mindestprinzip** begrenzter Missbrauchsmöglichkeiten und vollständig wirksamer Rechte ist bereits verbindlich.

## 3. Berechtigte Auflösung ohne Geheimnis- oder Gruppenleaks

- **Strukturierte Zielreferenz:** Der Editor darf nach tatsächlicher Les-/Ansprechberechtigung eine Erwähnung auf stabile, serverseitig gebundene Account-/Rollen-/Gruppen- oder Kanal-Scope-IDs beziehen. Sichtbarer Name ist Darstellung, keine Berechtigungsgrundlage; gleichnamige Charaktere, Nickname-Wechsel und frei getippte Strings erlauben keine Umgehung.
- **Autocomplete/Suche und Vorschau:** Nur derzeit **in diesem Chat** wirklich erwähnbare Identitäten und Kategorien anbieten; keine geheimen Gruppen, versteckten SL-/NPC-/Quest-/Charakterzuordnungen, Personenlisten oder betroffenen Count-Metadaten per Autocomplete, Eingabevalidierung, Ladezeiten, Suchvorschlägen oder Tooltip verraten. Generische, datensparsame Ablehnung, kein Target-Existenzorakel.
- **Serverautoritatives Senden:** Bei jedem Send-Commit Chat-An/Off, echte Absenderidentität, Kanal/Gruppe/DM/Empfänger, `canSend`, spezifisches `canMentionType`, 02.109-Restriktionen, aktuelle 02.25-Policy-/Mitgliedschafts-/Geheimnisversion und Größe der tatsächlichen Zielmenge validieren. Der Client liefert keine vertrauenswürdige Empfängerliste.
- **Einzelne Zielprojektion:** Der Server ermittelt nur den Schnitt aus erlaubtem Kanalempfängerkreis, zulässiger konkreter Erwähnungsart und tatsächlichen aktuellen/bei ursprünglicher Nachricht gültigen Berechtigungen. Gruppenmentions werden nicht über Kanalgrenzen hinweg zu neuen DMs. Keine automatische Freigabe des Chattexts durch die Erwähnung.
- **Ereigniszeit versus Nachlieferung:** Die beim gültigen Senden berechtigt angesprochene Gruppe und Version dürfen für Deduplikation/Belege festgehalten werden; **später** neu beigetretene Gruppenmitglieder erhalten nicht rückwirkend alte Hinweise, und vor einer verzögerten Zustellung werden heutige Rechte und 02.110-Filter erneut geprüft.
- **Sonderfall Direct/Mehrpersonen-DM:** Erwähnungen ersetzen keine adressierten DM-Empfänger und umgehen niemals einen serverseitigen 02.110-Block neuer DMs; mehrere legitime Empfänger werden unabhängig behandelt. Ein Teilnehmer darf nicht durch `@Dritter` aus einer privaten Unterhaltung unbemerkt eine neue DM an Dritte erzeugen.

## 4. Persönliche Mutes, DM-Kontaktblocks und offizielle Systemhinweise

**02.110-Kanal-Mute:** Bei wirksamer persönlicher Stummschaltung entstehen für diesen Spieler **keine optionalen zusätzlichen Ping-Sounds, Pushes oder aufdringlichen In-App-Hinweise aus dem stummgeschalteten Kanal**. Der weiterhin zulässige Chattext kann nach tatsächlichem heutigem und historischem Recht bewusst geöffnet werden; ein Mute ist keine Löschung und keine automatische Lese-/Ackquittung. Etwaige spätere feinere persönliche Ausnahmen wären eine gesonderte bewusst erlaubte Einstellung und sind hier nicht implizit aktiviert.

**02.110-DM-Senderblock:** Neue private DMs des blockierten echten Senderaccounts werden wie beschlossen serverseitig dem blockierenden Empfänger nicht zugestellt. Darüber hinaus darf derselbe Sender einen Block **nicht durch optionalen `@Person`-/`@Gruppe`-Ping in einem ansonsten zulässigen gemeinsamen Kanal als Benachrichtigungs-Bypass benutzen**: Sein zielgerichteter Zusatzhinweis an die blockierende Person entfällt; ein nach bestehenden Gruppenrechten lesbarer Gruppenchatbeitrag wird dadurch **nicht** universell versteckt oder gelöscht. Keine Information über die persönliche Blockbeziehung an Sender, SL ohne eigenes Recht oder andere Empfänger.

**Keine Privilegien durch Text:** `@SL`, `@Admin`, `@Wichtig`, `@System` oder frei formatierte Texte sind **niemals** eine offizielle, dem Mute/Block übergeordnete Systemzustellung. Nur tatsächlich typisierte und separat autorisierte 02.101–02.103-Notice-/Ack-/Reminder- und 02.109-Safety-/Moderationspfade folgen ihren **eigenen** Rechten und Konfigurationen. Ein Chatping ist keine Korrekturkenntnisnahme und kein echtes 02.102-Ack.

**Keine Weltwirkung:** Erwähnung, Zustellung, Mute, blockierter Ping, Ping-Retry, Mention-Count und eine etwaige Mention-Hervorhebung dürfen nie eigenständig NPC-/Quest-/Inventar-/Door-/Alarm-/Sensor-/Node-/Würfel-/Timer-/Turn-/Next-Player-Effekte auslösen. Sprach-/Voicechat und freie Spielernotizen bleiben separat.

## 5. Versand, Bearbeitung, Reconnect und Aufbewahrung

1. **Nachricht vor Ping:** Normale Message-ACL aus 02.105–02.107 und 02.109-Sendrechte zuerst prüfen. Erst eine rechtmäßig angenommene Nachricht/Revision bildet die Grundlage optionaler Mention-Entscheidungen. Kein Mention-Datensatz ist ein alternativer öffentlicher Nachrichtenkanal.
2. **Empfängerbezogene Notification-Guards:** Unmittelbar vor Anzeige/Realtime/Push/Offline-Queue/Badge/Counter/In-App-Postfach/erneutem Reconnect aktuelle Rechte, Source-Visibility, Empfänger-/Kanalstatus, 02.110-Personen- und Kanalfilter prüfen. Eine ehemals zulässige Pinganforderung garantiert **keine** spätere Zustellung. Bei geheimen Chats kein Nachrichten-Vorschautext oder ausleitender Name in ungeschützten externen Push-Payloads.
3. **02.107-Historie:** Erwähnte Personen erhalten durch Mention weder alte Chatnachrichten noch Archivzugriff. Ein eigener Mention-Filter/-Zähler/-Suchindex benötigt die heutigen **UND historischen** Message-/Recipient-/Retentionrechte; abgelaufene oder bei flüchtigem Chat entfallene Nachrichten dürfen nicht als Schattenhistorie fortleben.
4. **02.108-Edits und Withdraw:** Ein Edit verändert den ursprünglichen, schon versendeten Ping nicht rückwirkend. Erwähnungen auf überarbeiteten Texten dürfen **keine automatische Neu-Ping-Flut** oder Wiederbelebung entfernter Nachrichten verursachen; falls später ein ausdrücklich berechtigter Edit-Ping-Modus angeboten wird, ist er separat zu autorisieren, versionieren und zu deduplizieren. Noch ausstehende Hinweise zu entzogenen, nicht mehr aktuell erlaubten Nachrichten sind zu unterdrücken; bereits gesehene menschliche Inhalte sind nicht rückholbar.
5. **02.109-Moderation und Race:** Schreibsperren, gesperrte Nachrichten, Moderationsentfernung und Rechteentzug müssen künftige optionalen Pingzustellungen verhindern. Send-/Edit-/Withdraw-/Role-/Group-/Mute-/Block-/Chat-Off-Konflikte versioniert prüfen; kein stale Target, keine heimliche Shadowqueue, kein Wiederholungsping per Doppelklick/Replay.
6. **Keine irreführenden Zustellbestätigungen:** Erfolg beim Nachrichtensenden ist nicht identisch mit individuellem Pingempfang. Der Sender erhält keinen unzulässigen Bericht darüber, wer gemutet, blockiert, offline, in geheimen Gruppen oder adressierbar ist. Unzustellbarkeit generisch und korrekt darstellen.
7. **Rate/Abuse:** Serverseitige Limits für Erwähnungen pro Nachricht, pro Absender/Ziel/Kanal und Zeitfenster, besonders für `@alle`/Gruppenpings; Entdoppelung wiederholter Ziele, sichere Queue-/Backpressure-/Retry-Steuerung und 02.109-Melde-/Moderationsschutz. Konkrete Schwellwerte später bestimmen.

## 6. Konzeptionelle Architektur und Umsetzung

**Modellkandidaten, keine API-/Tabellenfestlegung:** `CampaignMentionPolicy`, `ChatMentionType`, `ChatMentionCapability`, `ChatMentionTargetRef`, `ChatMentionResolution`, `ChatMentionRecipientSnapshot`, `ChatMentionNotificationDecision`, `ChatMentionDeliveryReceipt`, `ChatMentionRateBucket`, `ChatMentionOperationId`, `ChatMentionAccessProjection`. Fachlicher Scope: Kampagne, 02.106-Kanal, reale Sender-/Empfängeridentität, optionales Gruppentarget, konkrete 02.107-Nachricht-/02.108-Revisions-ID, heutige und historische Recipient-/Role-/Group-/Policyversion, 02.110-Filterversion, Zustellstatus und geschützte Sichtprojektion.

**Umsetzungsplan (nach Workshop/MVP-Entscheidung):**
1. **Kampagnen- und Capability-Modell** der einzelnen Mentiontypen mit 02.25-Defaults/markierten Ausnahmen, wirksamem 02.105-Chat-Gate und Vorrang der 02.106–02.110-Rechte entwerfen.
2. **Sichere Target-Auflösung** mit strukturierten echten IDs, kanalbezogen gefilterten Vorschlägen und generischen Fehlern; keine Berechtigung allein aus `@Text`.
3. **Serverseitige Nachricht-/Mentions-Validierung** am Commit einschließlich Gruppenschnitt, konfigurierter @alle-Befugnis und Absender-/Moderator-Restriktionen; keine implizite DM-/Gruppenrechtserweiterung.
4. **Empfängerbezogene optionale Notification-Pipeline** hinter Message-/History-ACL mit 02.110-Mute-/Blockguard vor jedem tatsächlichen Publish und unabhängigem System-/Noticekanal.
5. **Versions-/Lifecycle-/Abuse-Schutz** für Edit/Withdraw/Retention/Queue/Realtime/Mehrgerät/Race/Deduplikation/Rate; Datenschutz für alle Query-/Count-/Autocomplete-/Push-/Export-Sichten.
6. **Rechtstests und UI später:** Einfache sichtbar berechtigte `@Person`-Auswahl, ggf. Gruppe/SL/alle nach Policy; Testmatrix und die endgültige Darstellung/Benachrichtigungskonfiguration erst nach vollständigem Featureworkshop spezifizieren.

## 7. Fachliche Abnahmetests

| Test | Erwartetes Ergebnis |
| --- | --- |
| Kampagne bei Erstellung `Chat Aus` | Keine neue normale Nachricht, Mentionauflösung, Pingzustellung, Mentionbadge oder Replayfunktion; Notizen, Welt, Würfel und rechtmäßige offizielle Notices bleiben |
| Nur `@Person` erlaubt, kein `@Gruppe`/`@alle` | Berechtigte einzelne Person darf erwähnt werden; Gruppen-/Massenping hat keine Benachrichtigungswirkung |
| `@B` im für A und B berechtigten aktiven Kanal | Nur B erhält bei gültiger individueller Policy einen optionalen Ping; keine neuen Leserechte für B |
| Gleicher Name bei zwei Spielern/Charakteren | Stabile eindeutige Identitätswahl, keine unklare automatische Ping-Adressierung per Freitext |
| Sender versucht `@Geheimgruppe` zu erraten | Keine Zielmember-/Count-/Autocomplete-/Error-/Latency-orientierte Secret-Auskunft, kein Ping an Unberechtigte |
| `@Gruppe` mit teils geheimen oder nicht kanalberechtigten Mitgliedern | Nur zulässige Empfänger im konkreten Kanal; keine Zielgruppenliste offenlegen |
| `@alle` von berechtigtem SL und unberechtigtem Spieler | Nur ausdrücklich berechtigter und limitierter Channel-Massenping möglich, nie universeller Bypass |
| A mutet den Kanal; B erwähnt A | Kein zusätzlicher optionaler Ping an A, berechtigter Chattext bleibt beim bewussten Öffnen normal lesbar |
| A blockiert B als echten DM-Sender; B erwähnt A im Gruppenchat | Kein zielgerichteter Ping von B an A; normale gemeinsame Chatberechtigung und Gruppentext bleiben unabhängig bestehen |
| Blockierter B wechselt Charaktername oder Gerät | Kein Umgehen durch Nickname, Token oder Geräte-/Reconnectwechsel |
| B versucht A durch neue private DM mit Mention zu erreichen | 02.110-Recipientblock verhindert neue DM-Zustellung samt Mentionnotification |
| `@SL` als angebliche Warnung oder `@System` als Freitext | Keine amtliche Pflichtnachricht, kein Bypass von 02.101–02.103-/02.109-Systempolicy |
| A erhält echte autorisierte 02.101-Notice mit eigener ACK-Pflicht | Getrennter rechtmäßiger Notice-/Ackweg ohne durch Chatping gefälschte Quittung |
| Spieler tritt Gruppe erst nach Ping bei oder verliert Kanalrechte | Kein alter Gruppenping für Neue; ausstehender Ping bei Entzug nicht nachgeliefert |
| Chatnachricht editiert / zurückgezogen / 02.109-entfernt | Keine automatische unlimitierte Pingwiederholung, keine späteren unberechtigten Hinweise zu nicht mehr sichtbarer Nachricht |
| 02.107 flüchtiger/abgelaufener oder historisch fremder Text | Mention-Search/Unread/Badge/Export/Reconnect verrät weder Inhalt noch heimlichen Existenz-Count |
| Gruppenping parallel zu Mute-/Block-/Role-/Chat-Off-Änderung | Aktuelle effektive Version vor Zustellung, kein Rennen mit ungültigen Pings/Queues |
| Wiederholter Klick, Replay, Massenerwähnung | Deduplikation, getrennte Rechte, Limits, kein Spam oder fremdes Status-Orakel |
| Pingtext behauptet `öffne Tür`, `Quest geschafft` oder `Next Player` | Keinerlei Welt-/Door-/NPC-/Node-/Ressourcen-/Würfel-/Turnwirkung |
| Voicechat-first ohne integrierten Chat | Mündliche Absprachen, eigene Notizen, manuelle SL-Aktionen, Würfel-/Systemlog weiter funktionsfähig |

## 8. Beschlussgrenze und nächste Frage

**Verbindlich beschlossen:** **02.111 C**. Erwähnungs- und Pingarten sind bei aktiviertem 02.105-Chat **einzeln konfigurierbar**, können nur innerhalb **tatsächlich berechtigter** 02.106-Channel-/Personen-/Gruppen-/SL-Sicht auf aktuell zugelassene Empfänger wirken und respektieren **02.107 aktuelle/historische Empfänger-/Retentionrechte**, **02.108 revisionssichere Messageänderungen**, **02.109 berechtigte Moderation und Anti-Spam** sowie **02.110 persönliche Channel-Mutes und DM-Senderblocks**. Keine verborgenen Gruppen/Accountdetails preisgeben; keine Umgehung durch `@alle` oder `@System`, kein echtes System-/Welt-/ACK-Ereignis. 02.25-Defaults und Ausnahmen bleiben.

**Nicht beschlossen:** Konkrete Limits/Fristen/Notification-Sounds/Push-Provider, Reaktions-Emojis, Voice/Video, finale Auto-Complete-/UI-Gestaltung, Editor-Hotkeys, finale Priorität, Datenbankschema/API. Diese Grenzen gelten für die Fachplanung; noch kein Code.

## Nächste Entscheidung 02.112 – Chatreaktionen und Emotes

**Beispiel:** Spieler B bestätigt einen Plan mit einer kleinen Reaktion auf As Chatnachricht statt eine neue Nachricht zu schreiben. Andere möchten Rollenspiel-Emotes als Text benutzen. Soll AdventureShift Nachrichtenreaktionen und Emotes anbieten?

- **A – Keine gesonderten Reaktionen:** Chat nur mit gewöhnlichen Textnachrichten; Emotes höchstens als normaler Text, ohne Reaktionszähler.
- **B – Unbegrenzte offene Reaktionen:** Jeder kann auf beliebige Nachrichten unbeschränkt reagieren, auch wenn ihm Chat, Verlauf oder Nachricht gar nicht zustehen, und die Reaktionen sind universell sichtbar.
- **C – Konfigurierbare berechtigte Reaktionen/Emotes (Empfehlung):** Pro aktivem Chat/Kanal/Rolle und 02.25-Ausnahmen festlegen, ob und welche Reaktionen und Text-Emotes erlaubt sind; serverseitig nur für aktuell und historisch zulässig sichtbare Nachrichten und Empfänger, mit 02.107-/02.108-/02.109-/02.110-Rechten, Spamgrenzen, echten Identitäten und ohne Weltwirkung. Anzeige und optionale Hinweise respektieren persönliche Filter; finale UI später.
