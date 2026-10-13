# AdventureShift – Karten-Workshop: Beschluss 02.116 A – keine individuellen Chat-Zustell- oder Lesebestätigungen

**Stand:** 13.10.2026 – Fachbeschlüsse 02.1 bis 02.116; nächste offene Frage 02.117
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungs- und Testplan; **noch keine Softwareimplementierung**, keine finalen API-/Datenbankverträge, abschließende UI-/MVP-Entscheidung oder festen technischen Loggingfristen.
**Bezüge:** [02.25 – Kampagnenstandards und gültige markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – Spieler-Notizen/konfigurierbare Automatisierung](KARTEN-WORKSHOP-02.98.md) · [02.101–02.104 – offizielle Mitteilungen, bewusste Acks und Reminder](KARTEN-WORKSHOP-02.104.md) · [02.105 – optionaler Chat bei Kampagnenerstellung](KARTEN-WORKSHOP-02.105.md) · [02.106 – Channel-/Gruppen-/DM-/SL-Rechte](KARTEN-WORKSHOP-02.106.md) · [02.107 – heutige/historische Empfängerrechte und Aufbewahrung](KARTEN-WORKSHOP-02.107.md) · [02.108 – Edits/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Meldungen/Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – persönliche Mutes und DM-Kontaktblock](KARTEN-WORKSHOP-02.110.md) · [02.111 – Mentions/Pings](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen/Emotes](KARTEN-WORKSHOP-02.112.md) · [02.113 – Antworten/Zitate/Threads](KARTEN-WORKSHOP-02.113.md) · [02.114 – Anhänge/Linkvorschauen](KARTEN-WORKSHOP-02.114.md) · [02.115 – Kanal-Pins/private Bookmarks](KARTEN-WORKSHOP-02.115.md) · [Bereich 11 Kommunikation](FEATURE-WORKSHOP.md).

## 1. Verbindliche Entscheidung – Variante 02.116 A

**Der Projektinhaber hat ausdrücklich Variante A gewählt: Im gewöhnlichen integrierten Chat gibt es KEINE individuellen Zustellstatus, Lesestatus oder persönlichen Lesebestätigungen.** Dies gilt bei aktiviertem 02.105-Chat für Kampagnen-, Gruppen-/Team-, Einzel-/Mehrpersonen-DM- und SL-bezogene 02.106-Kanäle gleichermaßen. Kein Absender, Mitspieler, Kanalmoderator oder SL bekommt aus einem normalen Chatvorgang den technischen Zustand „an Person X zugestellt“, „Person Y hat geöffnet/gelesen“ oder entsprechende persönliche Zeitpunkte.

**02.116 A ist kein versteckter C-Konfigurationsmodus:** Die Entscheidung lautet ausdrücklich *diese Funktionen nicht anbieten*. 02.25-Defaults oder Kanalausnahmen erzeugen **keinen Schalter**, mit dem gewöhnliche individuelle Chat-Zustell-/Lesebestätigungen nachträglich wieder freigeschaltet werden. Eine andersartige ausdrückliche spätere fachliche Entscheidung wäre nötig, um daran etwas zu ändern.

**Beispiel:** A sendet im erlaubten Gruppenchat eine Nachricht. Der Server nimmt sie rechtmäßig an und stellt sie nach den bestehenden Kanal- und Empfängerrechten bereit; A sieht aber **nicht**, ob B oder C die Nachricht bereits auf einem Gerät erhalten, geöffnet oder gelesen haben. Ebenso zeigt ein privater DM-Chat keine persönlichen Zustellhäkchen, Lesemarkierungen oder „zuletzt gelesen“-Zeiten. B muss keinen Lesestatus aktiv verweigern, weil die Funktion im gewöhnlichen Chat nicht existiert.

**Unbedingt getrennt:** Wirklich autorisierte offizielle 02.101–02.103-Korrektur-/Systemhinweise können **nach deren eigener Policy** weiterhin eine bewusst durch die betreffende Person ausgelöste **02.102-Kenntnisnahmequittung** verlangen. Ein solches ausdrücklich bestätigtes amtliches Ereignis ist **keine normale Chat-Lesebestätigung** und wird durch 02.116 A nicht deaktiviert. 02.109-eigens berechtigte Moderations-/Fallstatusinformationen behalten ebenso ihre getrennten Rechte, ohne normales Chat-Tracking zu legitimieren.

## 2. Was nicht angezeigt oder als Chatfunktion bereitgestellt wird

| Nicht vorgesehene Funktion | Fachliche Grenze |
| --- | --- |
| **Zugestellt pro Empfänger** | Keine persönlichen Chat-Delivery-Häkchen, Zeitstempel, Empfängerzustellungslisten oder recipientgenauen Zustellreports |
| **Geöffnet/gelesen pro Empfänger** | Keine persönlichen „gesehen“, „gelesen um“, Lesebestätigungs-Ticks, „zuletzt gelesen von“, Read-At- oder Opened-At-Auskunft |
| **Gruppen-/Thread-Übersichten** | Keine Liste, wer eine Message/einen Thread gelesen hat, keine individuellen Read-Counts oder geheimen Teilnehmer-/Receipt-Aufschlüsselungen |
| **Downloads/Medien als Lesestatus** | Öffnen eines 02.114-Anhangs, Thumbnail, Linkpreview oder Downloads erzeugen keinen für Sender sichtbaren Chat-Lesebeleg |
| **Reaktionen/Antworten als Tracking** | 02.112-Reaktion, 02.113-Antwort oder 02.115-Bookmark wird nicht zu einem maschinellen `readReceipt` oder `deliveryReceipt` umgedeutet |
| **Admin-/SL-Sonderzugang** | Chatverwaltung oder Moderation schafft keine allgemeine persönliche Lesetimeline anderer Teilnehmer, insbesondere fremder DMs |
| **API/Realtime/Export** | Nicht nur UI verstecken: normale Chat-Endpunkte, WebSocket-Nachrichten, Push, Badge/Count, History, Suche, Export, Debug- und Reconnectprojektion liefern keine individuellen Zustell-/Lesestatus aus |

**Kein falscher Umkehrschluss:** Die freiwillige sichtbare Antwort/Reaktion eines Spielers kann menschlich nahelegen, dass er einen Text gesehen hat. Das ist ein **eigenständiger erlaubter Chatbeitrag**, keine technische Bestätigung darüber, ob/zu welchem Zeitpunkt eine beliebige vorherige Nachricht ausgeliefert oder gelesen wurde. Die Software ermittelt daraus keinen neuen personenbezogenen Read-Receipt-Datensatz.

**Eigene ungelesene Ansicht ist separat:** Bereits in 02.106/02.107 vorgesehene **nur für den jeweiligen berechtigten Teilnehmer selbst** mögliche Unread-Badges und persönliche Chatnavigation dürfen bleiben, soweit korrekt geschützt und tatsächlich später vorgesehen. Dafür ggf. minimal benötigte eigene Anzeige-/Positionsmetadaten dürfen **niemals** an Absender, andere Mitglieder oder SL als „B hat Nachricht X gelesen“ ausgeleitet werden. 02.116 A verlangt kein zusätzliches individuelles Chat-Lesestatussystem und kein personenbezogenes Quittierungsarchiv.

## 3. Technischer Versand darf trotzdem korrekt funktionieren

**Wichtig: eigener Sendefehler ist keine Empfänger-Lesebestätigung.** Für robuste Nachrichtenübermittlung braucht der Client die Unterscheidung, ob **sein eigener Sendebefehl** lokal aussteht, vom **Server gültig angenommen** oder serverseitig **abgelehnt/fehlgeschlagen** ist. Solche eng auf den eigenen Operationserfolg begrenzten Rückmeldungen sind zulässig, sollen aber sprachlich **nicht** als „Empfänger zugestellt“ oder „Empfänger gelesen“ dargestellt werden. Auch bei einer berechtigten angenommenen Nachricht kann eine andere Person offline sein; der Serverannahmebeleg behauptet nicht deren tatsächliche Kenntnisnahme.

**Keine irreführende Erfolgsmeldung:** Nach 02.110 blockierte neue DMs, widerrufene 02.106-Senderechte oder 02.109-Sendbeschränkungen werden serverseitig wirksam durchgesetzt. Hat ein Sendeversuch keine zulässige Zustellung, darf die Software **nicht unwahr** „zugestellt“ melden. Generische, fachlich zutreffende Fehler wie „Nachricht an den gewählten Empfänger nicht zustellbar“ dürfen erscheinen, ohne den geheimen Blockgrund, Mitgliedsstatus, Gruppenrechte oder Account-Details zu verraten. Bei Mehrpersonen-DMs keine falsche pauschale Komplettzustellzusage; eine notwendige eigene Operationsergebnisanzeige bleibt ohne recipientgenaue intime Zustellhistorie.

**Interne Betriebsdiagnose:** Serverseitige Transport-Acks, Fehlerbehandlung, Deduplikation, Queue-/Idempotenzbelege und sparsame Sicherheits-/Auditprotokolle bleiben für korrekte technische Verarbeitung und nötige Nachvollziehbarkeit zulässig. Sie sind **keine vom Benutzer abfragbare Chat-Read-/Delivery-Receipt-Funktion**. Datensparsamkeit, Zugriffsschutz, getrennte erforderliche Audit-Rechte und noch festzulegende zulässige Retention gehören zum technischen Plan; weder ein allsehendes SL-Dashboard noch frei durchsuchbare personenbezogene Transportlogs daraus ableiten. Insbesondere muss keine neue Nachrichtenöffnung „aus Gründen des Acks“ an den Sender publiziert werden.

## 4. Vereinbarkeit mit den bereits beschlossenen Modulen

- **02.105 Chat An/Aus:** Bei Chat Aus keine regulären neuen Chat-Send-/Subscribe-/Verlaufsvorgänge. Chat An schaltet **nicht** heimlich die durch A abgelehnten Lesebestätigungen frei; 02.101–02.104-Notices/Quittungen und das Würfel-/Systemlog bleiben unabhängig.
- **02.106 Kanäle und 02.107 Historie:** Chat-Nachrichten dürfen weiterhin nur ihren wirklich berechtigten heutigen **UND historischen** Empfängern übermittelt werden. Diese serverseitige ACL-/Zustellprüfung ist nötig, um Datenschutz und Sicherheit zu gewährleisten, erzeugt aber keinen sichtbaren „B empfangen“-/„B gelesen“-Status für A. Flüchtig/persistiert und Retention bleiben konfigurierbar.
- **02.108 Bearbeitung/Withdraw:** Eigene Nachrichtenänderung, Rücknahme und Revisionen bleiben rechtmäßig; keine neue Liste, welche Teilnehmer die Originalfassung vor dem Edit gesehen haben. Was Menschen bereits gelesen haben könnten, lässt sich nicht rückwirkend löschen, wird aber von AdventureShift nicht als garantierter Status behauptet.
- **02.109 Melden/Moderation:** Ein bewusst eingereichter, rechtmäßig berechtigter Report bzw. ein fallbezogenes Moderator-Entscheidungs-/Action-Audit bleibt möglich. Das ist keine allgemeine Chat-Lesestatistik. Kein allgemeiner SL-Zugriff auf fremde private DM-Read-/Delivery-Informationen.
- **02.110 Kanal-Mutes und DM-Senderblocks:** Der eigene Mute löst keine Lesebestätigung aus. Blockierte DM-Empfänger erhalten keinen normalen neuen Senderkontakt, während Absender keine privaten Blocklisten oder persönliches Zustelltracking einsehen können. Bei erlaubtem Gruppenchat werden die normalen Nachrichtenrechte nicht verändert.
- **02.111 Mentions/Pings:** Ein berechtigter Hinweis ist nur eine zulässige optionale Benachrichtigung, **kein** Nachweis des Empfangs oder der Kenntnisnahme. Keine individuellen Ping-Read-Quittungen und kein Umgehen von Mute/Block.
- **02.112 Reaktionen/Emotes und 02.113 Antworten/Threads:** Wer selbst reagiert oder antwortet, führt eine eigene, nach ihren bestehenden Rechten sichtbare Chataktion aus. Daraus niemals heimlich recipientbezogene „gelesen“-Daten oder Teilnehmer-Readlisten für den Quellthread generieren.
- **02.114 Medien:** Anzeige eines Bildes, Erzeugung einer Linkvorschau oder Download einer Datei gilt nicht als Chat-Lesebeleg für andere Benutzer. Die echte Medien-/Message-/Retention-ACL bleibt vollständig erhalten.
- **02.115 Kanalpins/private Lesezeichen:** Setzen/Lesen/Entfernen von Pins und Bookmarks ist **kein** „gelesen“-Status; persönliche Bookmarks bleiben privat, und ein Pin verrät keine versteckte Empfängerhistorie.
- **Offizielle 02.101–02.103/02.109-Systempfade:** Tatsächlich autorisierte wichtige Korrekturen und Sicherheits-/Moderationshinweise folgen ihren eigenen Sicht-/Mitteilungs-/Auditrechten. Bei ausdrücklich geltender 02.102-Pflicht ist **nur eine bewusste persönliche Quittierungsaktion** der verlangte Ackbeleg; einfache Zustellung, automatisches Lesen, Chatnachricht, Reaktion, Pin oder Medienaufruf erfüllen ihn nicht.
- **Keine Weltwirkung:** Chatversand, technischer Sendebeleg, Clientanzeige oder Weglassen von Read-/Delivery-Status löst keine Würfel-/Quest-/NPC-/Inventar-/Tür-/Alarm-/Sensor-/Node-/Timer-/Next-Player-/Turnwirkung aus. Freie private Notizen und externe Voicechat-Absprachen funktionieren auch ohne integrierten Chat.

## 5. Konzeptionelle Architektur und Implementierungsgrenze

**Dies ist ausdrücklich eine Entscheidung gegen neue Recipient-/Read-Receipt-Datenmodelle.** Keine normalen `ChatDeliveryReceipt`, `ChatReadReceipt`, `ChatRecipientReadTime` oder `ChatReadActorList` als vom Absender/SL abrufbare Chat-Features planen. Bereits fachlich geplante 02.107-`ChatMessageRecipientSnapshot`-Daten beschreiben, **wer historisch berechtigt war**, nicht, ob dieser Empfänger eine Nachricht tatsächlich empfangen/gelesen hat. 02.102-`AcknowledgementReceipt` gehört ausschließlich zum gesondert berechtigten offiziellen Notice-/Ack-System.

**Technische Entwurfsbegriffe nur für korrektes Senden:** `ChatSendOperation`, `ChatServerAcceptance`, `ChatSendRejection`, `ChatTransportError`, `ChatAccessProjection` und ggf. `ChatOwnUnreadProjection` (keine fertigen API-/DB-Verträge). Eigener Sendebefehl, serverseitiges Autorisierungsresultat und unterdrückte individuelle Statusprojektion bleiben semantisch getrennt. Keine universell lesbaren privaten 02.110-Recipientblockgründe in Sendefehlern/Debugs; keine Absender-/Moderator-Abfrage von individuellen Read-/Received-Zeitstempeln. Für Systempflichtmeldungen werden die bestehenden 02.101–02.104-Objekte statt eines künstlichen Chat-Receipt-Workarounds genutzt.

**Umsetzungsplan (nach Abschluss des Featureworkshops):**
1. **Keine Receipt-Capabilities:** In der Chat-Policy für 02.116 **keinen** `showReadReceipts`/`showRecipientDeliveryStatus`-Schalter, keine personenbezogenen Abfrage-/Export-/Subscribe-Endpunkte anbieten; auch SL-/Adminausnahmen nicht als stillen Ersatz einführen.
2. **Sendetransport korrekt spezifizieren:** Eigene pending/angenommen/abgelehnt/failure-Information ohne Versprechen einer Empfängerzustellung; 02.105-Chatmode, 02.106-Kanal-, 02.107-Empfängerrechte und 02.109-Sendrestriktionen am tatsächlichen Servercommit prüfen. 02.110-Blocks und Teilzustellung korrekt, generisch und ohne private Ursache behandeln.
3. **Sicht-/Leak-Audit:** WebSocket/Realtime, Suche/History, Query/Count/Badges, Debug-/Log-, Export-/Archive-, Offline-/Push-/Reconnect- und SL-/Moderator-Projektionen auf unerlaubte persönliche Delivered-/Read-/LastRead-Felder oder daraus abgeleitete Informationen prüfen. Eigene Unread-Navigation, falls vorhanden, bleibt nur für den jeweiligen Besitzer.
4. **02.102-Notice-Ack strikt getrennt:** Gesonderte echte offizielle Notice-Anforderung, explizite menschliche Ackhandlung und darauf beschränkte eigene Recipient-/Role-/Statussicht ohne Zugriff durch gewöhnliche Chatnachrichten oder Chatreaktionen.
5. **Idempotenz, Datenschutz, Tests:** Offline-/Reconnect-/Mehrpersonen-DM-/Block-/Mute-/Rolewechsel-/Edit-/Retention-/Moderations- und Voicechat-first-Fälle prüfen; reine technische Operationsbelege auf minimalen berechtigten Zweck beschränken, keine neue ungefragte Trackingfunktion.
6. **UI nach Workshop:** Formulierungen eigener Sendefehler und der schon beschlossenen eigenständigen Unread-Navigation benutzerverständlich festlegen, ohne individuelle Liefer-/Lesestatus als Feature einzuführen. Implementierungs-/MVP-Prioritäten bleiben bis zum Gesamtplan offen.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Aktivierte Kampagne, A sendet B eine berechtigte DM | B kann die Nachricht nach 02.106-/02.107-Recht erhalten, A sieht **keinen** individuellen Zustell- oder Lesestatus von B |
| Berechtigter Gruppenchat mit A, B und C | Keine personenbezogene „B gelesen / C ungelesen“-Liste, kein personalisierter Zustell-Count, kein Read-Time |
| Server nimmt As Sendeoperation korrekt an | Eigene technische Annahme darf gezeigt werden, aber **nicht** „B zugestellt“ oder „B gelesen“ |
| Sendeoperation scheitert an eigener Berechtigung oder Transport | A erhält zutreffenden generischen eigenen Fehler, kein gefälschter Empfänger-Delivery-Erfolg |
| A blockiert B als DM-Sender | B kann aus Fehlschlag/Status keine persönliche Blockliste abfragen; keine falsche Zustellzusage |
| Mehrpersonen-DM hat unterschiedlich zulässige Empfänger | Serverseitige Filterung bleibt; keine Empfänger-Einzeldelivery-/Readliste und kein falscher vollständiger Zustellerfolg |
| B ist offline, empfängt später über Reconnect | A bekommt keine individuelle „offline/gelesen/zugestellt um“-Rückmeldung; aktueller/historischer Recipient-Schutz bleibt |
| B öffnet einen Gruppenkanal oder scrollt zum Text | Kein an Absender/Sonder-SL gepushtes `readAt`-/`openedAt`-Event |
| A besitzt nur eigenes Chat-Unread-Badge | Eigener Counter kann nach eigener gültiger Policy funktionieren; andere Teilnehmer sehen daraus keinen Read-Status |
| A ist SL und administriert Chatkanäle | Kein universeller Kanal-/DM-Read-/Delivery-Überblick durch bloße SL-Rolle |
| Neue Gruppe betritt alten Kanal, alte historische ACL fehlt | Weder alte Nachricht noch individuell abgeleitete Read-/Delivery-Metadaten erscheinen |
| Nachricht wird bearbeitet oder zurückgezogen | Keine persönliche „wer las Originalrevision“-Auswertung, bestehende 02.108-Revisionsrechte bleiben |
| 02.109-Moderationsfall ist offen | Berechtigter Fallstatus ist nur eigens legitim sichtbar, kein pauschales Lesen-/Empfangen-Tracking der DM |
| 02.111-`@Person`-Ping kommt an | Ping bleibt ein optionaler Hinweis, keine empfängerbezogene Lesebestätigung |
| B reagiert `👍` oder antwortet A im Thread | Eigene berechtigte Interaktion bleibt sichtbar, aber kein generiertes `ChatReadReceipt` zu früheren Texten |
| B lädt 02.114-Anhang herunter | A sieht keine persönliche Medien-/Chat-Lesebestätigung, tatsächliche Anhangsrechte bleiben |
| A setzt Kanalpin, B setzt eigenes Lesezeichen | Keine automatische Lesequittung und keine fremde Lesezeichenoffenlegung |
| Echte offizielle 02.101-Nachricht verlangt 02.102-ACK | Nur ausdrücklich berechtigter bewusster Ack erzeugt amtlichen Kenntnisnahmebeleg; 02.116 A schaltet ihn **nicht** aus |
| Gewöhnliche Chatnachricht lautet „Bitte bestätige mit gelesen“ | Freitext kann eine menschliche Antwort auslösen, aber keinen technischen, offiziellen 02.102-Ack oder Read-Receipt |
| Chat ist bei Kampagnenerstellung `Aus` | Keine normalen Chatoperationen, aber Notizen, Würfel-/Systemlog, Welt und amtliche Notices/Acks bleiben unabhängig |
| Code fragt versteckte `readReceipt`-/`deliveryReceipt`-API an | Keine für gewöhnlichen Chat nutzbare persönliche Receipt-API, WebSocket-, Export- oder Debug-Veröffentlichung |
| Änderung von 02.25-Kampagnen-/Kanalstandards | Keine still freigeschalteten individuellen Read-/Delivery-Anzeigen, da Variante A verbindlich gilt |
| Nachricht enthält angeblich „Quest erledigt“ oder „Tür öffnen“ | Weder Sendestatus noch Chattext ändern echte NPC-/Quest-/Tür-/Node-/Turn-/Würfelzustände |

## 7. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.116 A – keine individuellen Chat-Zustell-, Öffnungs- oder Lesestatus, keine Lesebestätigungen, keine personenbezogenen Empfänger-Zeitlisten.** Diese Funktionen gehören nicht in die normale Chat-UI oder deren API/Realtime/Export/SL-Ansichten. Technisch notwendige eigene Sendefehler/Serverannahme dürfen wahrheitsgemäß und datensparsam angezeigt werden, **ohne** eine Empfängerzustellung zu behaupten. Ein 02.110-DM-Block oder eine verborgene Gruppe darf daraus nicht auslesbar sein. Alle 02.105–02.115-Chat-/Quell-/Retention-/Sicherheitsentscheidungen gelten fort; insbesondere bleibt **02.102 bewusste Quittierung wichtiger offizieller Mitteilungen** ein unabhängiger berechtigter Systempfad.

**Nicht beschlossen:** Irgendeine C-Konfiguration individueller Read-Receipts, neue globale Online-/Typing-Statusanzeigen oder allgemeine Anwesenheitsauswertungen; kein endgültiges UI/MVP, keine konkreten technischen Logfristen, keine Softwareimplementierung. Funktionen außerhalb gewöhnlicher Chatlesebestätigung benötigen eine eigene spätere Featureentscheidung.

## Nächste Entscheidung 02.117 – Chat-Suche und Filter in berechtigten Verläufen

**Beispiel:** Ein Spieler möchte einen zuvor besprochenen Begriff, einen Ort oder einen selbst geschriebenen Text im Chat suchen. Die Suche darf weder fremde DMs noch ältere Gruppennachrichten anzeigen, für die ihm die damaligen und heutigen Rechte fehlen. Bereits in 02.107 beschlossene geschützte Suchpfade werden durch 02.117 hinsichtlich konkreter Filterfunktionen präzisiert.

- **A – Nur einfache Verlaufnavigation:** Keine eigene erweiterte Chat-Such-/Filteroberfläche; normal zugelassene Verlaufnavigation und zwingende 02.107-Sicherheitschecks bleiben erhalten.
- **B – Ungefilterte kampagnenweite Suche:** Jede Person kann alle Nachrichten, ehemaligen Gruppen, DMs und alten Versionen samt privaten Dateinamen durchsuchen, unabhängig von aktuellen oder historischen Rechten.
- **C – Konfigurierbare berechtigte Chat-Suche (Empfehlung):** Nach 02.25-Kampagnen-/Kanal-/Rollenstandards mit gültigen markierten Ausnahmen wählbare Volltext-, Absender-, Kanal-, Zeitraum-, Medien- und ggf. Threadfilter **nur für tatsächlich heute UND historisch lesbare 02.107-Nachrichten und 02.108-Revisionen**. Kein verborgenes Resultat/Count/Autocomplete, keine Retention-/Moderations-/Mute-/DM-Block- oder 02.116-A-Umgehung. Reine Navigation ohne Weltwirkung, UX später.
