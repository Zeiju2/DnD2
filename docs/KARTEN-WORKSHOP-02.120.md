# AdventureShift – Karten-Workshop: Beschluss 02.120 C – konfigurierbare berechtigte Chat-Umfragen und Abstimmungen

**Stand:** 13.10.2026 – Fachbeschlüsse 02.1 bis 02.120; nächste offene Frage 02.121
**Status:** Verbindlicher fachlicher Beschluss mit konzeptionellem Umsetzungs- und Testplan; **noch keine Softwareimplementierung**, keine finalen API-/Datenbankverträge, festen Limits, UI- oder MVP-Entscheidungen.
**Bezüge:** [02.25 – Kampagnenstandards und gültige markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – Spielernotizen/konfigurierbare Technik](KARTEN-WORKSHOP-02.98.md) · [02.99–02.104 – manuell autorisierte Weltaktionen, echte System-Notices und bewusste ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat bei Kampagnenerstellung An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106 – Kanal-/Gruppen-/DM-/SL-Berechtigungen](KARTEN-WORKSHOP-02.106.md) · [02.107 – heutige UND historische Empfänger-/Retentionrechte](KARTEN-WORKSHOP-02.107.md) · [02.108 – Edits und Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Meldung/Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – persönliche Mutes/DM-Blocks](KARTEN-WORKSHOP-02.110.md) · [02.111 – Erwähnungen/Pings](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen/Emotes](KARTEN-WORKSHOP-02.112.md) · [02.113 – Replies/Threads](KARTEN-WORKSHOP-02.113.md) · [02.114 – Anhänge/Links](KARTEN-WORKSHOP-02.114.md) · [02.115 – Pins/Bookmarks](KARTEN-WORKSHOP-02.115.md) · [02.116 A – keine individuellen Chat-Lesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.117 – berechtigte Suche/Filter](KARTEN-WORKSHOP-02.117.md) · [02.118 A – keine gespeicherten Entwürfe](KARTEN-WORKSHOP-02.118.md) · [02.119 – flüchtige Typing-/Präsenzindikatoren](KARTEN-WORKSHOP-02.119.md) · [Kommunikationsworkshop 11](FEATURE-WORKSHOP.md).

## 1. Verbindlicher Beschluss – Variante 02.120 C

**Der Projektinhaber wählt C: Im optionalen integrierten Chat kann die SL nach gültiger 02.25-Kampagnen-/Regel-/Kanaltyp-/Kanal-/Gruppen-/Rollen-/Personenpolicy sowie fachlich markierten Ausnahmen Umfragen/Abstimmungen einzeln freigeben oder abschalten.** Bei **02.105 Chat An** darf nur eine aktuell autorisierte Person eine Umfrage im konkret zulässigen 02.106-Chatbereich erstellen; eigene Fähigkeiten regeln getrennt **Erstellen, Abstimmen, eigene Stimme ändern/zurücknehmen, Lesen, vorzeitig schließen, Ergebnisse einsehen, Moderieren** und zulässiges Verwalten. **Weder Umfrage noch Stimmen erweitern Chat-/DM-/Gruppen-/SL-Historienrechte.**

**Verbindliches Ziel:** Die Umfrage ist eine **Chat- und Planungsfunktion**, kein verbindlicher Beschluss der Spielmechanik. Die Spieler können im Voicechat oder Tischgespräch weiterhin selbst beraten und entscheiden; ein nicht genutzter oder abgeschalteter Poll behindert manuelle SL-Aktionen, Würfel, Notizen und Kampagnenablauf nicht. Ergebnis und Mehrheitsmeinung erzeugen **niemals automatisch** eine Quest-/NPC-/Tür-/Node-/Timer-/Turn-/Inventar-/Geld-/Reise-/Kampfaktion. Wenn eine Spielleitung ein im Chat/Voicechat besprochenes Ergebnis übernehmen will, bleiben ausschließlich die **berechtigte bewusste 02.99-Serveraktion/SL-Freigabe** und die echten World-/Effectledger-Guards maßgeblich. Auch eine `Ja`-Stimme ist **keine** echte persönliche 02.102-Korrekturquittung.

**Beispiel:** Spieler A erstellt im aktiven Teamkanal eine Umfrage „Welche Route?“ mit „Wald“, „Pass“, „Fluss“. Nur wirklich berechtigte Teammitglieder können die Pollkarte und entsprechend ihrer Stimmberechtigung Wahlmöglichkeiten sehen und abstimmen. Später hinzugekommene Teammitglieder erhalten nicht automatisch Zugriff auf alte Polls, Stimmen oder Resultate. Das Ergebnis „Pass gewinnt“ setzt kein Token in Bewegung, dreht keinen Schalter und beendet keinen Zug.

**Nicht gewählt:** A (grundsätzlich keine integrierten Polls) und B (beliebige globale, offene Abstimmungen mit automatischen Wirkungen). Unter C darf eine Kampagne **Umfragen Aus** wählen, ohne die übrigen Chatmodule zu verlieren.

## 2. Konfiguration und differenzierte Berechtigungen

| Konfigurierbarer Umfang | Fachliches Sollverhalten | Unverhandelbare Grenze |
| --- | --- | --- |
| **Umfragen An/Aus** | Aktivierung bei Kampagnenerstellung, gültige 02.25-Channel-/Rollen-/Gruppen-/Personenausnahmen | Bei 02.105 Chat Aus kein reguläres Create/Vote/Result/Subscribe |
| **Poll erstellen** | Getrennt autorisierte Rollen/Accounts dürfen eine Umfrage **im eigenen berechtigten Kanal** veröffentlichen | Kein heimlicher Poll an fremde DMs, Gruppen oder SL-Kanäle |
| **Poll beantworten** | Nur heute zum konkreten Channel gehörende, **historisch zur Ursprungsumfrage berechtigte** und gemäß Policy stimmberechtigte echte Personen | Keinen anonymen Charakterwechsel, geteilten Link oder fremde Account-ID als Doppelstimme zulassen |
| **Frage/Optionen** | Geeignete, begrenzte Auswahl-/ggf. Mehrfachantworttypen als spätere Policywahl; geprüfte Textlängen/Optionenanzahl | Keine Skriptausführung, freien Code oder automatische Node-/Worldwirkung |
| **Stimme korrigieren/entfernen** | Nur eigene gültige Stimme bei gesonderter aktueller Berechtigung und offenem Poll | Fremde Stimmen nicht ohne eng berechtigte Fall-/Datenschutzmaßnahme ändern |
| **Schließen/Fristen** | Autorisiertes bewusstes Schließen, optionaler Endzeitpunkt oder separat zugelassene Fristen | Frist/Timer schließt **nur** Chatpoll, löst keine World-/Next-Player-Node aus |
| **Ergebnisse** | Pro Poll getrennte Sicht von Frage/Optionen, laufenden Ergebnissen, Endauswertung und ggf. namentlichen Stimmen | Keine standardmäßig globale Stimmliste, keine geheimen Gruppen-/DM-/Identitätsleaks |
| **Stimmprivatsphäre** | Als **separate** Option offenes oder eingeschränktes Ergebnis-/Voter-Sichtmodell; ggf. datensparsame anonyme Anzeige | Keine fälschlich behauptete echte Anonymität bei identifizierbaren Kleinpopulationen oder Admin-/Auditbelegen |
| **Laufende Benachrichtigungen** | Falls gesondert zulässig, nur optionale Kanal-/Poll-Aktivitätshinweise | 02.110-Mute-/DM-Block, 02.111-Pingrechte und 02.116-A-Privatsphäre gelten |
| **Moderation/Entfernen** | Ggf. 02.109-fallberechtigte spezifische Poll-/Message-Moderation | Kein Blanko-SL-Zugriff auf private DMs und alle verborgenen Stimmbelege |

**Fähigkeiten voneinander getrennt planen:** `createChatPoll`, `readChatPoll`, `castOwnPollVote`, `changeOwnPollVote`, `withdrawOwnPollVote`, `readPollTally`, `readPollVoterDetails`, `closeChatPoll`, `moderateChatPoll`, `configurePollPolicy`. Poll-Leserecht, aktuelles Wahlrecht, Recht zur Anzeige aggregierter Resultate und Recht zur Nennung einzelner Wählender können ausdrücklich **verschieden** sein. Eine SL-/Moderatorrolle ist keine universelle Leseberechtigung aller privaten Stimmen.

**Später festzulegen:** Welche Wahltypen, konkrete Mengenlimits, Polllaufzeiten, Wahländerung/Enthaltung, Ergebnisse während der Abstimmung, eventuelle Mindestanzahl für Aggregation, Stimmabgabe nach Gruppenwechsel, Mehrgeräte-/Abstimmungs-UI und MVP-Priorität angeboten werden. Verbindlich sind dagegen die unabhängigen Rechte, Geheimhaltung, Missbrauchsgrenzen und Weltwirkungslosigkeit.

## 3. Historische Empfängerbindung, Berechtigung zur Wahl und echte Identität

1. **Beim Create-Commit:** Echte authentifizierte Actor-/Kampagnenidentität, Chat-An, `canSend`/`createChatPoll`, gegenwärtige 02.106-Channel-/Gruppen-/DM-/SL- und 02.109-Sendrechte, gültige 02.25-/Poll-/Messageversion prüfen. Umfrage als eindeutig typisierte Chatnachricht an den **damals tatsächlich gültigen Empfängerkreis** mit 02.107-History-/Retention- und 02.108-Revisionsbezug binden.
2. **Bei jedem Vote/Change/Withdraw:** Poll muss nach aktueller Policy offen und der Zieltext zulässig sein; Actor muss **heute UND zum ursprünglichen Versandzeitpunkt** eine gültige 02.107-/02.106-Membership-/Recipient-/Secret-/Quellberechtigung für genau diese Pollmessage haben. Falls ein späterer Joiner einbezogen werden soll, erfordert das **eine neue ausdrücklich berechtigt adressierte Umfrage**, nicht eine rückwirkende Erlaubnis auf alten Polls.
3. **Stimmabgabe je echte Accountidentität:** Nicht Nickname, Charakterfigur, zweites Gerät oder mehrfache Session als mehrere Personen zählen. Für ein aktives Poll pro echter, berechtigter Person nur die nach Pollmodus zulässige effektive Wahl; `vote`-OperationId, Pollrevision und CAS/Idempotenz gegen Doppel-Klick, gleichzeitige Geräte, Race, Replay und gefälschte Requests.
4. **Persönliche/ggf. anonyme Ergebnissicht:** Der Server muss gegen Doppelsendungen eindeutig prüfen können; das bedeutet **nicht**, dass der gewöhnliche Zuschauer automatisch den Account-/Optionen-Zusammenhang sehen darf. Bei „anonym für Teilnehmer“ keine Namenwahliste, Rückgabecodes/Counts mit versteckten Personen oder Pushbelege ausleiten. Privilegierte System-/Sicherheitsadministratoren bzw. zulässige Auditpfade und sehr kleine Gruppen können Rückschlüsse erlauben – daher **keine absolute Anonymität behaupten**. Bei nicht sicher anonym darstellbaren Konstellationen Ergebnis-/Anonymitätsmodus begrenzen, nicht fälschlich zusagen.
5. **Sender und Wahlberechtigte auseinanderhalten:** Die SL kann Pollcreate/Close-Recht besitzen, ohne alle eingegangenen namentlichen DM-Stimmen lesen zu dürfen. Die Wahlberechtigung ist nicht gleich dem historischen Empfängerzählwert und verrät keine geheime Gruppenliste. Keine `@alle`-Erwähnung nur aus Poll-Erstellung.
6. **Individuelle Ergebnis-/Countprojektion:** Pollfrage, Optionslabel, Endzeit, laufender Zwischenstand, Tallies, Voter-Details, Teilnahmezahlen, Identitätslabels, Icons, Search/Filter, Export, Realtime und Reconnect brauchen **eigene** autorisierte Projektion. Ergebniszahl, vorzeitige Ergebnisveränderung oder namentliche Kleinstgruppe darf keinen verborgenen Chat-/Voter-/DM-/Geheimfraktionsinhalt verraten.
7. **Keine Rechteerweiterung durch Link/Quote/Thread:** Eine Poll-ID oder URL in einem 02.113-Thread oder 02.115-Pin verleiht keine neuen Lese-/Vote-/Result-/Mediarechte. 02.114-Anhänge zu Polltexten bleiben an der Originalmessage-ACL. Keine automatische Teilnahmeberechtigung durch bloßen Besitz des Links.

## 4. Versionierung, Edit/Withdraw, Poll-Ende und Retention

**Pollversion und Optionenkatalog:** Nach bereits abgegebenen Stimmen **keine stille Bedeutungsänderung** der Frage, Wahlmöglichkeiten, Reihenfolge/Optionen-IDs, Wahlart oder Berechtigungen, die vergangene Stimmen als Antwort auf einen anderen Inhalt erscheinen lässt. Korrekturen vor erster Stimme können – bei eigener Create/Edit-Policy – als 02.108-kompatible Poll-/Message-Revision erfolgen; nach erster Stimme muss eine Änderung mindestens ausdrücklich nach neuer gesicherter Revision/SL-Freigabe ausgewiesen werden, z. B. **neuen Poll erstellen und bisherigen sauber schließen**, statt Stimmen umzubuchen. Welche konkreten Editvarianten später erlaubt sind, bleibt offen; historische Belege dürfen nicht gefälscht werden.

**Aktiver Poll und Closing:** Serverseitige Zustände `open`/`closed`/`withdrawn`/`moderated` bzw. fachlich gleichwertige typisierte Status; nur erlaubte gültige Votes im `open`-Status. Eine erlaubte automatische Ablaufzeit verarbeitet ein **begrenztes, idempotentes Schließen des Polls selbst**. Stop/Close, gleichzeitiger letzter Vote, SL-Moderation, Policywechsel und Reconnect verwenden Poll-/Option-/Actor-/Channel-/Messageversion und klare Commitreihenfolge; keine doppelt gezählten, verspätet umgebuchten Stimmen. Kein Next-Player-, Tür-, Quest-, Würfel- oder offizielles Ack-Event.

**02.108-Withdraw/02.109-Moderation:** Wird die Quell-Chatnachricht nach ihren Rechten zurückgezogen/unterdrückt, dürfen neue Votes, Result-Pushes, Search-Counts und alte Poll-Vorschauen diese Entscheidung nicht umgehen. Fallgebundene 02.109-Minimalbelege nur bei legitimem konkreten Fall- und Auditrecht, keine neue pauschale SL-Auslesbarkeit privater Polls/DMs.

**02.107 gespeicherter Verlauf:** Zulässige Pollfrage, Optionen, effektive Stimmen/Resultate und berechtigte Verwaltungsbelege unterstehen aktuellem **UND historischem** Quell-Recipient-/Retention-/Datenschutzrecht. Persistente Poll-Resultate dürfen kein unabhängiges unbegrenzt gespeichertes Schattenarchiv für abgelaufene/gelöschte Chatmessage sein. Suchindex, Badges, Exporte, Backup/Restore, Reconnect/Offline und Poll-Statistiken müssen die gleiche Quelle/Expiry respektieren.

**02.107 flüchtiger Verlauf:** Kein garantiert nachlieferbarer Poll-/Stimm-/Ergebnisverlauf nach Neustart oder Ablauf der flüchtigen Chatnachricht. Ist dauerhafte Pollzählung für den gewählten Modus technisch nötig, muss die SL eine **tatsächlich dafür erlaubte gespeicherte 02.107-Historien-/Retentionoption** nutzen oder Poll dort auslassen – nicht durch die Hintertür eine dauerhafte Schattenhistory im flüchtigen Chat einführen.

**Bestand bei Chat Aus/Roleentzug:** Chat Aus verhindert reguläre neuen Create-/Vote-/Result-/Subscriptionoperationen. Alte berechtigte Pollbestände nicht dadurch heimlich löschen oder öffentlich machen; nach wirksamem Wiederaktivieren nur nach **heutiger UND historischer** ACL/Retention zugänglich. Sende-/Wahlentzug stoppt neue Aktionen und unberechtigte Statusprojektionen; bereits gegebene Stimme wird **nicht automatisch als nie geschehen** gefälscht. Ob sie bei gültiger Wahlpolicy im Gesamtaggregat verbleibt, verlangt einen fachlich definierten Epoch-/Snapshotmodus, den der Server konsistent dokumentiert; keine rückwirkende Offenlegung einzelner Wahlidentitäten.

## 5. Persönliche Filter, Missbrauch und strikt getrennte Spielmechanik

- **02.110 Kanal-Mute und DM-Block:** Ein stummgeschalteter Kanal kann mit weiterhin geltenden Leserechten Polls bei bewusstem Öffnen zeigen; **optionale Poll-Push-/Sound-/Mentionshinweise** werden respektvoll unterdrückt. Persönlicher echter DM-Block verhindert neue Poll-DM- und gerichtete Wahlaufforderungen des blockierten Senders an den Empfänger, auch über Mehrpersonen-DMs; zulässiger gemeinsamer Gruppentext bleibt ein eigener Scope. Persönliche Blocklisten bleiben geheim.
- **02.111–02.113:** Kein automatisch erzwungener `@Gruppe`/`@alle`-Ping aus Pollstart/Close; Reply, zitierte Pollkarte, Reaktion oder Emote erzeugen keine zusätzliche Gruppe von Poll-Wählern oder automatisches Stimmrecht. Öffentliche Reaktions-Emojis sind nicht still als „Pollstimme“ zu zählen.
- **02.114-/02.115-/02.117-Medien-/Pin-/Suchrechte:** Pollbild/Link, Anhang, Pin, Bookmark, Filter nach Umfragetyp, Facet/Zählung oder Export benötigen die jeweils zulässige Chat-/Media-/Message-/Voter-Resultprojektion. Such-/Autocomplete-Index darf geheime Pollfrage, Optionsnamen, Abstimmende oder Counts nicht als Orakel ausgeben.
- **02.116 A und 02.118 A:** Abstimmungsereignisse sind **keine** persönlichen „Nachricht zugestellt/gelesen“-Receipts; keine automatische Empfangs-/Leseliste pro Chat. Polltexte sind keine gespeicherten, über Geräte wiederherstellbaren **ungesendeten Chatentwürfe**; ein begonnener, nicht abgeschickter Stimmformularstand verursacht weder Auto-Vote noch Draft-Autosave.
- **02.119 C:** Online-/Typingstatus von Chatpersonen verrät keine Abstimmungsbeteiligung. Pollkarte schafft kein neues Präsenz-/„zuletzt gewählt“-Tracking.
- **Rate-/Abuse-/Manipulationsschutz:** Begrenzte Create-/Vote-/Update-/Close-Raten, maximale Optionen/Voter-/Resultqueries nach Policy, zulässige Poll-Laufzeiten, authentifizierte echte Accounts, idempotente OperationIDs, text-/URL-/Formatvalidierung, XSS-/SQL-/Expression- und Race-Schutz. Kein fremdes unkontrolliertes JavaScript/HTML als Optionentext und keine Massennachrichten durch Poll-Updates.
- **02.99 und offizielle 02.101–02.104-Notices:** Ein Poll gilt **nie** als Spielweltentscheidungs-Commit, echtes 02.102-ACK oder SL-Korrekturfreigabe. Eine tatsächliche Spielweltänderung erfolgt nur über den dafür zuständigen und separat autorisierten bestehenden Workflow, auch wenn die Gruppe einstimmig war. Voicechat-first, freie Spielernotizen, Würfelprotokoll, Karten und optionaler Missionsgenerator bleiben unabhängig.

## 6. Konzeptionelle Architektur und Umsetzungsplan

**Modellkandidaten, keine fertigen API-/Tabellenverträge:** `CampaignChatPollPolicy`, `ChatPollCapability`, `ChatPollMessageBinding`, `ChatPollDefinition`, `ChatPollOption`, `ChatPollRevision`, `ChatPollEligibilityRule`, `ChatPollRecipientEpoch`, `ChatPollVote`, `ChatPollVoterPrivacyMode`, `ChatPollResultProjection`, `ChatPollStatusTransition`, `ChatPollCloseOperation`, `ChatPollVoteOperationId`, `ChatPollRateBudget`, `ChatPollModerationEvidence`. Fachliche Schlüssel: Kampagnen-/Kanal-/Actor-ID, echte berechtigte Wähleridentität (nicht unberechtigt angezeigt), Originalmessage/Recipient-/Policy-Epoche gemäß 02.107, OptionIDs/Pollrevision, Wahl- und Ergebnisrechte, aktueller open/closed-Status, Version/Idempotenz, Retention, 02.109-Moderation und 02.110-Filterversion.

**Vorgesehene Umsetzungsschritte:**
1. **Konfigurations- und Rechtekatalog** für Chatpoll-An/Aus, Create/View/Vote/OwnChange/OwnWithdraw/Close/Result/ActorDetails/Moderate je 02.25-Defaults und markierten gültigen Ausnahmen. Erlaubte Auswahl-/Laufzeit-/Ergebnis-/Privatsphäremodi nur soweit tatsächlich realisierbar.
2. **Geschütztes Poll-Create** als echter berechtigter 02.106-/02.107-Chat-Message-Commit, mit typisierten stabilen Poll-/OptionIDs, geprüften Texten und historischer Message-/Empfängerbindung; keine erweiterte universelle Zuschauerliste.
3. **Serverautoritatives Vote/Close** mit aktuellen UND historischen Actor-/Message-/Channel-/Voterrechten, 02.109-Restriktionen, Poll-/Option-/Actor-Epoch-/CAS-/Idempotenzschutz sowie begrenztem Ablauf/Close-Handling.
4. **Sichere Ergebnisprojektionen** für Pollfrage, Counts, Zwischen-/Endauswertung und ggf. identifizierbare Einzelstimmen strikt getrennt nach heutigen/historischen 02.107-/02.108-/02.109-Rechten und freigegebener Voter-/Count-/Resultpolicy; Kleinstgruppen-/anonyme Ergebnisorakel abwehren.
5. **Lebenszyklus und Systemtrennung:** 02.108-Edit/Withdraw, 02.109-Moderation, 02.110-Block/Mutes, 02.111–02.119-Status-/Privacyentscheidungen, 02.107-Retention/Flüchtig, Reconnect/Backups/Export und `Chat Aus` verzugsfrei konsistent behandeln; keine automatischen 02.99-/Node-/02.102-Welt-/ACK-Effekte.
6. **Tests und spätere UI:** Abnahmekatalog unten inkl. Rechtewechsel, Doppelvotes, Race/Option-Edits/Close, anonyme Kleinpopulationen, Result-Sicht, Moderationsbelege, Index-/Leakfälle und getrennte Voicechat-/Notiz-Funktion; Grenzwerte, Ergebnisanzeige, Wahlmethoden, UX und MVP erst nach vollständigem Featureworkshop festlegen.

## 7. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Kampagne bei Erstellung `Chat Aus` | Kein normaler Poll-Create-/Vote-/Result-/Subscribe-Pfad, andere System-/Würfel-/Notizfunktionen bleiben |
| Chat An, Umfragen Aus | Reguläre berechtigte Chattexte funktionieren, Pollaktionen serverseitig gesperrt |
| Poll nur in Teamkanal erlaubt | Berechtigter Teamspieler kann Poll erstellen; anderer Channel-/DM-/SL-Bereich nach eigener Policy nicht |
| Spieler darf lesen, aber nicht abstimmen | Pollfrage sichtbar nach 02.107-ACL, kein Vote-/Doppelvote-/individuelles Resultrecht |
| Spieler darf abstimmen, aber nicht Resultate sehen | Gültige eigene Wahl möglich, kein Leck über Tally/Count/Optionlisten anderer |
| Neuer Spieler tritt Team erst nach Poll-Create bei | Keine rückwirkende historische Poll-/Stimmen-/Ergebnisfreigabe oder automatische Wahlberechtigung |
| Spieler verliert heute Channelrecht | Keine weitere Poll-/Vote-/Result-/Search-/Export-/Reconnectprojektion aus früherer Mitgliedschaft |
| Erratene Poll-ID aus fremder DM/Geheimgruppe | Keine Text-/Options-/Voter-/Count-/Thread-/File-/Existenzoffenlegung |
| 02.116-A-Chat ohne Lesebestätigungen | Umfrageteilnahme erzeugt keine „hat Chatnachricht gelesen“-Technikmeldung |
| Zweiter Charakter oder Gerät votet nochmals für denselben Account | Authentifizierte echte Wähler-ID und Poll-Operation schützen vor unerlaubten mehrfachen Stimmen |
| Double click, Retry, Race auf zwei Geräten | Effektive Stimme nach Version/Idempotenz korrekt, keine doppelte Zählung |
| Eigene Voteänderung erlaubt vs. gesperrt | Nur in erlaubt offenem Modus und durch echte aktuell berechtigte Person änderbar |
| A versucht fremde Stimme zu ändern | Abgewiesen außer gesondertem exakt berechtigtem Moderations-/Datenschutzfall |
| SL editiert Poll-Option nach abgegebenen Stimmen | Kein stilles Umlabeln oder Umadressieren alter Stimmen; nur konsistent zulässiger Revisions-/Neupollweg |
| Poll läuft zeitlich ab, letzter Vote/Close parallel | Idempotenter, revisionsgesicherter Pollstatus; keine doppelten/späten Stimmen |
| SL schließt Poll | Nur Closeberechtigung; Ergebnis selbst löst keine spielmechanischen Folgen aus |
| Anonyme Ergebnisdarstellung mit nur zwei Abstimmenden | Keine fälschliche Anonymitätszusage, keine verdeckten persönlichen Kleingruppen-Rückschlüsse über Livecounts |
| Ergebnisse während Poll geheim, nach Close sichtbar | Ausschließlich nach konfiguriertem Timing-/Actor-/Result-Scope, kein Zwischenstand via WebSocket/Badge/Export |
| Moderator darf Fallbeleg sehen, nicht alle privaten DMs | Minimaler konkret fallberechtigter Beleg, keine universellen Vote-/DM-Auskunftsrechte |
| Poll-Frage wird 02.108 zurückgezogen/02.109 unterdrückt | Keine neuen Votes oder unberechtigten Ergebnis-/Such-/Realtime-Nachlieferungen |
| 02.107-Chatverlauf ist flüchtig | Kein verborgenes persistentes Pollarchiv oder garantiertes Offline-/Restart-Result |
| 02.107-Retention endet oder Gruppenrechte wechseln | Keine alte Pollfrage/Result-/Voter-/Filekopie in Index/Cache/Backup/Export |
| B hat A als echten DM-Sender geblockt, A sendet Poll-DM | 02.110-Sperre wirkt auch auf Poll-Delivery; keine Blocklistenoffenlegung |
| A mutet berechtigten Teamchat | Poll bei bewusster erlaubter Ansicht weiter nutzbar, kein zusätzlicher aufdringlicher Poll-Ping |
| Polltext enthält `@alle`, Antwort-Thread oder Medienanhang | 02.111-Ping-/02.113-Quell-/02.114-Downloadrechte nicht umgangen |
| Voting-Benachrichtigungen und 02.119 Präsenz | Keine automatische „B stimmt gerade ab“-/Typing-/Read-Receipt-Offenlegung |
| Pollergebnis „Pass: 100 %“ | Keine automatische Tokenbewegung, Quest-/Door-/Node-/Alarm-/Next-Player-/Ressourcenwirkung |
| Korrekturmeldung fordert echten 02.102-Ack | Chat-Poll-Stimme ist keine persönliche amtliche Kenntnisnahmequittung |
| Kampagne nutzt ausschließlich Voicechat-first, Polls Aus | Freie Absprachen, private Notizen, echte manuelle SL-Aktionen, Würfel-/Systemlog bleiben voll nutzbar |
| Massenspam, manipulierte Options-IDs/SQL/HTML | Kanal-/Rollen-/Rate-/Input-/Version-/Textprüfung verhindert Spam, Injektion und fremde Datenlecks |

## 8. Beschlussgrenze und nächste Featurefrage

**Verbindlich beschlossen: 02.120 C.** Die SL kann bei Erstellung einer Kampagne den optionalen Chat **02.105 An/Aus** und seine Umfragen nach **02.25-Kampagnen-/Kanal-/Rollen-/Gruppen-/Personenstandards und markierten Ausnahmen** freigeben. Berechtigte Chat-Polls besitzen getrennte Create-/View-/Vote-/Close-/Results-/Moderationsrechte und gelten **nur im jeweiligen tatsächlich autorisierten 02.106-Kanal**. Echte Accounts statt wechselnder Figuren verhindern Doppelvotes; heutige **UND historische 02.107-Nachrichten-/Recipient-/Retentionrechte** schützen Poll-/Stimmdaten und alle Results/Counts/Export/Realtime-Projektionen. 02.108-/02.109-Revisions-/Moderationsrechte, 02.110-Mutes/Blocks und 02.111–02.119-Fachbeschlüsse gelten fort, besonders **02.116 A ohne Read-Receipts**, **02.118 A ohne Draftspeicherung** sowie **02.102 nur per eigener echter Ackaktion**. Kein Pollergebnis führt ohne gesonderte berechtigte wirkliche 02.99-Weltaktion zu Quest-/NPC-/Tür-/Node-/Turn-/Inventar-/Würfeländerungen.

**Nicht beschlossen:** Genaues Poll-Layout, konkrete Auswahlformate/Limits/Zeitfenster, fixe Defaults für offene/verborgene Stimmen, absolute Anonymitätsgarantie, anonyme SL-Audits, definitive MVP-Reihenfolge oder finale DB-/API-Verträge. Die spätere Konfigurationsführung wird erst nach Abschluss des gesamten Featureworkshops entworfen.

## Nächste Entscheidung 02.121 – Chat-Textformatierung und Spoiler

**Beispiel:** Spieler möchten im erlaubten Chat wichtige Informationen fett markieren, Listen oder kurze Codeblöcke teilen und einen Hinweis optional erst nach Klick als Spoiler anzeigen. Ein Spoiler darf aber keine echten SL-Geheimnisse allein durch CSS „schützen“.

- **A – Nur einfacher Text:** Kein besonderer Formatierungseditor, keine Markdown-/Spoilerfunktion; Text bleibt gewöhnlicher Chatinhalt.
- **B – Ungefiltertes Rich-HTML und vermeintlich geheime Spoiler:** Jeder darf beliebiges HTML/Skript/Embed/Styles übertragen; mit Spoilerklasse verborgene Inhalte gelten fälschlich als vor Unberechtigten geschützt.
- **C – Konfigurierbare sichere Formatierung und freiwillige Spoiler (Empfehlung):** Nach aktivem 02.105-Chat und 02.25-Kampagnen-/Kanal-/Rollenpolicy nur unterstützte geprüfte Formatierungsarten (z. B. Fett, Kursiv, Listen, kurze Codebereiche) und optionale Spoiler-Interaktion zulassen. Serverseitig sichere Rendering-/Sanitization-/Linkregeln, bestehende 02.106–02.120-ACL und 02.108-Revision-/Retentionrechte. Spoiler ist **nur ein bewusster UX-Sichtschutz**, kein echtes Geheimnisrecht; vertrauliche Informationen nur über tatsächlich getrennt autorisierte Empfängerscopes. Exaktes UI später.
