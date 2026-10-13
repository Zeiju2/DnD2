# AdventureShift – Karten-Workshop: Beschluss 02.113 C – berechtigte Antworten, Zitate und Chat-Threads

**Stand:** 13.10.2026 – Fachbeschlüsse 02.1 bis 02.113; nächste offene Frage 02.114
**Status:** Verbindlicher Fachbeschluss und konzeptioneller Umsetzungs-/Testplan; **noch keine Softwareimplementierung**, keine freigegebenen API-/Datenbankverträge, endgültigen UI-Flows, Threadgrenzen, Aufbewahrungsfristen oder MVP-Prioritäten.
**Bezüge:** [02.25 – globale Standards mit markierten gültigen Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – Spielernotizen/Voicechat-first und Kampagnenmodule](KARTEN-WORKSHOP-02.98.md) · [02.101–02.104 – eigenständige amtliche Notices/Acks](KARTEN-WORKSHOP-02.104.md) · [02.105 – bei Kampagnenerstellung Chat An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106 – getrennte Kanal-/DM-/Gruppen-/SL-Rechte](KARTEN-WORKSHOP-02.106.md) · [02.107 – aktuelle und historische Empfänger-/Retentionrechte](KARTEN-WORKSHOP-02.107.md) · [02.108 – Revisionen und Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Melden/Moderieren](KARTEN-WORKSHOP-02.109.md) · [02.110 – Channel-Mutes/DM-Kontaktsperren](KARTEN-WORKSHOP-02.110.md) · [02.111 – Mentions/Pings](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen/Emotes](KARTEN-WORKSHOP-02.112.md) · [Kommunikationsworkshop 11](FEATURE-WORKSHOP.md).

## 1. Verbindliche Entscheidung – Variante 02.113 C

**Der Projektinhaber hat C gewählt: konfigurierbare, aktuell UND historisch berechtigte direkte Antworten, Nachrichtenzitate und optionale Chat-Threads.** Für den bei Kampagnenerstellung ausdrücklich **02.105 Chat An/Aus schaltbaren** integrierten Chat konfiguriert die SL je **02.25-Kampagnen-/Regelprofil-/Kanaltyp-/Kanal-/Gruppen-/Rollen-/Personen-/Empfängerscope und zulässigen markierten Ausnahmen** getrennt, ob **auf einzelne Nachrichten antworten**, **automatisch berechtigte Quellenzitate/Vorschauen** und **zusammengehörige Thread-Ansichten** möglich sind. Ein Chat mit allen drei Optionen Aus ist ein gültiger C-Modus.

**Begriffe strikt trennen:**
- **Direkte Antwort:** Eine gewöhnliche neue, separat nach heutigen Send-/Empfängerrechten zugestellte 02.106-/02.107-Chatnachricht hat einen typisierten Link auf eine **konkrete nach 02.107 berechtigt sichtbare Zielnachricht**. Der Link ist kein Leserecht auf die Ursprungsnachricht und kein Import fremder Teilnehmer.
- **Zitierte Vorschau:** Ein UI-seitig angezeigter begrenzter Ausschnitt der referenzierten Originalnachricht, **nur nach eigener aktueller UND historischer Quell-/Nachrichten-/Revisions-/Empfängerberechtigung des jeweiligen Betrachters**. Keine ungeprüften serverseitig ausgelieferten Snapshot-Kopien oder erratbaren Originalnachrichten-/Kanalnamen.
- **Thread:** Eine optionale, nach wahrer Kanal-/Empfängerpolicy separat aktivierte Gruppierung von berechtigten Nachrichten durch stabile Root-/Parent-/Threadreferenzen; **kein automatisch neu öffentlicher Chatkanal**, keine Freigabe aller Antworten an das ursprüngliche Publikum oder an nachträglich beigetretene Personen.

**Beispiel:** A antwortet auf Bs Nachricht in einem Teamchat. C kann die Antwort sehen, sofern C zum historischen Empfängerkreis der Antwort und heute zum konkreten Chat gehört. Wenn C den alten Text von B historisch nicht lesen darf, bekommt C **keinen** Originaltext und keine verräterische Originalmetadatenvorschau; die neue Antwort kann im zulässigen eigenen Umfang erscheinen, mit einem neutralen Platzhalter für den nicht zugänglichen Bezug, sofern bereits die Anzeige der Bezugsexistenz ohne Geheimnisleck möglich ist. Ein Thread erweitert diese Rechte nicht.

**Nicht gewählt:** A (niemals verknüpfte Antworten/Zitate/Threads) und B (beliebige Message-ID-/Kanal-/DM-Zitate mit Offenlegung geschützter Texte) sind keine zwingenden Standardeinstellungen.

## 2. Einstellbare Fähigkeiten und Grenzen

| Funktion | Bei gültiger separater Freigabe | Unverhandelbare Grenze |
| --- | --- | --- |
| **Direkt antworten** | Nachricht mit verifiziertem Parent-Message-Bezug im erlaubten aktuellen Chat absenden | Kein Link zu einer für den Sender heute oder historisch unlesbaren Zielnachricht |
| **Quellenvorschau/Zitat** | Gekürzten oder zulässigen Referenztext **pro Betrachter** bei aktueller Berechtigung projizieren | Keine öffentliche Snapshot-Kopie/secret Sender-/Kanal-/Gruppen-/Timestamp-Leaks |
| **Threads** | Zugehörige rechtmäßig adressierte Antworten nach Root-/Parent-Bezug gruppieren, ggf. in eigener Teilansicht | Threadzugang ist niemals zusätzliche Kanalmitgliedschaft oder pauschales DM-Leserecht |
| **Optionale Thread-Hinweise** | Berechtigte neue Aktivität im erlaubten Thread nach Empfängerpolicy signalisieren | 02.110-Mute/DM-Block, 02.111-Pinglimits und echte 02.109-Rechte haben Vorrang |
| **Referenz- und Teilnehmersuche** | Aus aktuell und historisch lesbaren Nachrichten des erlaubten Scopes antwortbare Ziele anbieten | Keine fremde Message-/DM-ID-Enumeration, kein geheimes Autocomplete |
| **Eigener Thread-Ausstieg/Follow-Status** | Allenfalls persönliche, nach konkreter Policy unterstützte Aufmerksamkeitspräferenz | Keine Rechteänderung oder neue Fremd-Subscription ohne gültige Mitgliedschaft |

**Capability-Kandidaten:** `canReply`, `canPreviewQuote`, `canCreateThread`, `canReadThread`, `canFollowThread`, `canModerateThread` und normale `canSendMessage`/`canReadMessage` ausdrücklich getrennt denken. Eine SL-Administrationsrolle darf nicht allein deshalb verborgene Spieler-DMs oder geschützte frühere Zitate öffnen. Sicherheitsrechte, Auth, Quellberechtigungen und 02.107-Retention sind **nicht abschaltbar**, die Komfortfunktionen dagegen bei Kampagnenerstellung sinnvoll an-/ausschaltbar.

**Standard für den Entwurf:** Innerhalb **desselben** tatsächlich erlaubten 02.106-Chatkanals referenzieren. Kanalübergreifendes automatisches Zitat/Verlinken ist **nicht implizit durch C freigegeben**. Wenn eine spätere Kampagnenpolicy eine kanalübergreifende Wiedergabe ausdrücklich unterstützt, benötigt sie gesonderte Quell-/Ziel-/Empfänger-Schnittrechte und darf keine unbekannten privaten Nachrichten durch Metadaten oder Text transportieren. Eine **bewusst selbst getippte oder kopierte Textaussage** ist nicht mit einer automatisch erzeugten geschützten Originalzitatvorschau zu verwechseln; bereits menschlich gesehene Inhalte sind technisch nicht rückholbar. Chat-Moderation/Sende-/Geheimnisregeln bleiben auch für neuen Freitext gültig.

## 3. Empfänger, Geheimnisse und Autorisierung

1. **Beim neuen Antwort-Commit:** Der Server prüft den realen Absender, 02.105-Chatmodus, 02.106-Kanal/Gruppe/DM/SL, 02.109-Sendrestriktionen, gültige 02.25-Antwort-/Thread-Policy, aktuelle Quelle/Sichtbarkeit sowie den **ursprünglichen, historisch berechtigten Empfängerkreis** des Parent-Texts. Ein erratener Parent-Key erhält dieselbe datensparsame ununterscheidbare Ablehnung wie jeder andere unzulässige Bezug.
2. **Neue Nachricht hat eigenes Recht:** Der zulässige Parent-Bezug bewirkt **weder neue Empfänger für die Antwort noch neue Empfänger für die alte Nachricht**. Jede neue Antwort wird nach tatsächlichem aktuellen 02.106-Channel-/DM-Zielrecht und ihrem eigenen 02.107-Recipient-/Retention-Snapshot zugestellt; keine stille Einladung in alte DMs, neue Gruppen oder SL-Unterhaltungen.
3. **Individuell berechnete Parent-Vorschau:** Beim **Anzeigen** von Quote-/Thread-Root-/Parenttext, Namen, Uhrzeit, Counts, Pfaden, Threadtiefe und Aktionen je Betrachter **aktuelle UND historische** Les-/Kanal-/Secret-/Fog-/Message-/Revisionsrechte überprüfen. Bei fehlendem Recht neutral unterdrücken oder neutrales „Bezug nicht verfügbar“ anzeigen – nur wenn der Bezugshinweis selbst keine Informationen über Geheimnisse verrät. Keine Unterscheidung „fremde geheime DM“ vs. „gelöscht“, weder in Fehlern noch in Counts oder Rendering.
4. **Alte und neue Gruppenmitglieder:** Ein später beigetretener Spieler darf nur seine wirklich für ihn historischen und heute erlaubten Threadnachrichten sehen; die Root-/Parent-/Unterantworten anderer Epochen nicht automatisch. Ein ursprünglicher Empfänger, der aktuell keine Zugriffsrechte mehr hat, verliert neue Projektionen – ohne falsche Zusage, bereits gelesene Texte beim Menschen zu löschen.
5. **SL-/Moderatorrechte:** Berechtigte 02.109-Fallarbeit darf konkrete eingeschränkte Quellen-/Threads überprüfen, wenn fall-/belegbezogen legitim; daraus folgt **kein universeller SL-Thread- oder DM-Archivzugang**. Referenzen auf NPC-/Quest-/Notiz-/Wurf-/Karten-/Fog-Geheimnisse dürfen deren eigentliche Quellrechte nicht aushebeln.
6. **Untrusted Content:** Nachrichtentext, Markdown, `> quote`, `/me`, URLs und Threadtitel bleiben Nutzereingaben. Kein serverseitiges Ausführen von Befehlen, Quellen- oder Rechteänderungen durch frei getipptes Zitat. Explizite syntaktische Kennzeichnung erzeugt **kein** privilegiertes `ChatMessageReference`-Objekt ohne gültigen Servercommit.

## 4. Edit, Withdraw, Retention und Lifecycle

**02.108-Revisionen:** Antwortreferenzen zeigen auf **stabile Message-IDs** und für geschützte Quellvorschau auf eine bewusst typisierte zulässige Text-/Revisionssicht. Ein späterer Edit des Parents darf **keine alte, nicht mehr berechtigte Textversion** durch Cache, Push, Volltextsuche, Export, Badge oder Thread-Zitat wieder sichtbar machen. Die aktuell berechtigt sichtbare Revision kann – wenn die betreffende Zitatpolicy dies so festlegt – dargestellt werden; ältere Revisionen ausschließlich mit separat aktuell **und historisch** berechtigtem Versionsleserecht. Der genaue Standard „aktuelle Revision oder geschützte Version beim Antworten“ bleibt ein späteres UI-/Policy-Detail, aber nie eine globale automatische private Kopie.

**Zurückziehen und Moderation:** Nach 02.108-Withdraw, 02.109-Removal/Sendrestriction, Rechteeinzug oder 02.107-Retention-Ende darf keine verbotene Elternvorschau oder verdeckte Metadatenprojektion bestehen bleiben. Je Thread-Recht können **bereits rechtmäßig zugestellte eigene Antworten** sichtbar bleiben, jedoch ohne ungültige Parentdetails; nicht automatisch gesamte Threads physisch löschen oder alte Antworten als neu adressiert ausgeben. Rechtmäßig beschlossene Datenschutz-/Retention-Löschungen werden separat wirksam.

**Flüchtige versus gespeicherte Chatverläufe:** Für 02.107-flüchtige Chats keine Zusage einer wiederabrufbaren Thread-/Quote-Historie, wenn die Basisnachrichten bereits entfallen sind. In gespeichertem Modus folgen Threadindex/Parent-Referenz, Volltext, Reply-Counts, Quote-Caches, Backup/Restore/Archiv den Originalnachrichten-/Empfänger-/Retention-/Revocationsregeln. Abgelaufene Nachrichten nicht durch einen Thread als Schattenarchiv unbegrenzt weiterhalten.

**Laufende, konkurrierende Operationen:** Ziel-/Quell-/Thread-/Kanal-/Policy-/Revisions-/Retentionversion unmittelbar beim Commit und vor verzögerter Zustellung prüfen; Doppelklick/Retry/Reconnect nur idempotent einmalig verarbeiten. Bei Parent-Edit/Withdraw/Rolewechsel gleichzeitig mit Reply kein stale Geheimtext oder verlorener Sicherheitsschutz. Geschützte Eventbelege statt heimlicher Umschreibung historischer Autor-/Empfänger-/Channel-Fakten. Gelöschte Parent-Referenzen dürfen nicht nachträglich auf eine andere Nachricht-ID umgebogen werden.

**Thread-Baum:** Jede neue Antwort genau einer gültigen Elternreferenz und höchstens einem gültigen Root/Thread zuordnen, mit kontrollierter Tiefe und begrenztem Umfang. Serverseitig niemals Zyklen/Quervertauschungen durch manipulierte IDs zulassen. Konkrete Thread-Tiefe, Schließ-/Archivmöglichkeiten und Grenzwerte bleiben offene spätere UI-/Policyfragen.

## 5. Persönliche Filter, Pings, Reaktionen und getrennte Systempfade

- **02.110-Kanal-Mute** unterdrückt optionale neue Reply-/Thread-Hinweise für die betroffene Person, ohne gültige eigene Nachrichtensicht zu löschen. **DM-Senderblock** verhindert neue blockierte Direktzustellungen samt Antworten/Thread-Benachrichtigungen. Ein blockierter echter Sender darf in gemeinsamen erlaubten Gruppenkanälen keine gerichteten Reply-/Thread-Hinweise als Kontakt-Bypass auslösen; normale gemäß eigener Rechte zulässige Gruppenunterhaltungen werden nicht für alle versteckt.
- **02.111-Erwähnungen/Pings:** Eine Antwort auf Nachricht von A darf **nicht automatisch** jeden alten Teilnehmer oder A anpingen. Nur eigens gültige 02.111-@Person/@Gruppe/@SL/@alle-Rechte und eventuell gesondert zulässige Thread-Follow-Hinweise begründen optionale Aufmerksamkeit. Auto-Follow, Auto-Subscribe oder Notify-All nicht aus bloßem Root-/Quote-Link ableiten.
- **02.112-Reaktionen/Emotes:** Reaction-Zähler und Reaktionsreferenzen folgen ihren eigenen Revisions- und Nachrichtenrechten, keine automatische Konvertierung von Reply in Reaction. Emote-Text mit Reply-Link ist immer noch nur Chattext ohne Node-/Quest-/Door-/Turnwirkung.
- **02.101–02.103/02.109-Systemnotices und Acks:** `Antwort erhalten`, `gesehen`, `zitiert` oder `Thread gelesen` bedeutet **nicht** persönlich quittierte Kenntnisnahme oder berechtigte SL-Entscheidung. Nur ausdrücklich autorisierte getrennte Notice-/Moderationspfade erzeugen solche Belege. Chat-An/Aus verändert keine rechtmäßigen Weltzustände, Würfel-/Serverprotokolle, Spielernotizen, Kartenmarker oder externe Voicechatgespräche.
- **Rate-/Abuse-Schutz:** Reply-/Thread-Erstellrate, Fan-out, Threadtiefe, Quote-Länge, Follow-/Count-Abfragen und optionale Benachrichtigungen begrenzen, deduplizieren und mit 02.109-Restriktionen koppeln. Keine massenhaften Reply-Pushes oder „@alle“-Ersatzmechanik. Konkrete Zahlen/UX erst nach Abschluss des Featureworkshops.

## 6. Konzeptarchitektur und geplanter Umsetzungsweg

**Fachliche Datenmodellkandidaten, keine verbindlichen Tabellen/APIs:** `CampaignReplyThreadPolicy`, `ChatReplyCapability`, `ChatMessageReference`, `ChatQuoteProjection`, `ChatThreadRoot`, `ChatThreadMembershipProjection`, `ChatThreadParticipantEpoch`, `ChatThreadMessageIndex`, `ChatThreadVisibilityGuard`, `ChatThreadNotificationDecision`, `ChatThreadFollowPreference`, `ChatReplyOperationId`, `ChatReplyCommitReceipt`. Erforderliche Scopes: Kampagnen-/Kanal-/Root-/Parent-/Child-ID, echter Actor, historische und aktuelle Absender-/Empfänger-/Gruppen-/Quellrechte, konkret sichtbare 02.108-Revision, 02.107-Retention, 02.110-Mute/Block, 02.111-Mention-/Notify-Policy, 02.109-Moderation/Sendrestriktion und effektive Versions-/Auditbelege.

**Umsetzungsplan nach Featureworkshop:**
1. **02.25-Policy-/Capability-Raster:** Reply, geschützte Zitatprojektion, Threads und Thread-Hinweise getrennt an-/auskonfigurierbar; 02.105 Chat-An/Off, 02.106-Kanal-ACL und 02.107-historische Empfängerrechte als Pflichtguards beibehalten.
2. **Typisierte Referenzprüfung:** Server nimmt nur strukturierte Parent-/Root-/Revision-IDs entgegen, verhindert Zyklen, fremde Quellen und unberechtigte Cross-Channel-Referenzen; echte 02.109-Sender-/Moderationsrechte und passende Zielversion beim Commit prüfen.
3. **Eigener neuer Message-Scope:** Reply-Message mit eigenständigem berechtigten Recipient-Snapshot und auditierter Parent-Referenz senden. Keine Nachricht oder Gruppe durch das Vorhandensein von Thread-Rechten „öffnen“.
4. **Pro Betrachter neu gefilterte Read-Projektion:** Root-/Quote-/Replies-/Members-/Thread-Counts und Suche/Export/Reconnect/Offline/Push nur nach heutigen und historischen Source-/Parent-/Child-/Revision-/Retentionrechten ausliefern, inkl. datensparsamer neutraler Fallbacks.
5. **Lebenszyklus-/Benachrichtigungs-Gateway:** 02.108-Edits/Withdraw, 02.109-Moderation, 02.110-Personenfilter, 02.111-Pinglimits und 02.112-Emotes/Reaktionen entlang derselben versionierten, idempotenten Serverpipeline; Race-/Deduplikationsschutz.
6. **Tests/UX-Abgrenzung:** Privatchat-/Geheimnis-/History-/Retention-/Rolechange-/Mehrgeräte-/Spam-/No-World-Effect-Tests vorbereiten; konkrete Quote-Darstellung, Threadtiefe, Hotkeys, Limits und MVP erst im vollständigen UI-/Featureworkshop festlegen.

## 7. Fachliche Abnahmetests

| Fall | Erwartetes Ergebnis |
| --- | --- |
| `Chat Aus` bei Kampagnenerstellung | Kein neuer Reply-/Quote-/Thread-Send-/Subscribe-/Count-/History-Pfad; Welt, Würfel-/Systemlog, Notizen, amtliche Notices und Voicechat bleiben unabhängig |
| `Chat An`, Reply erlaubt, Threads/Zitate Aus | Berechtigte verlinkte Antwort ohne automatisch öffentliches Zitat und ohne neue Thread-Teilnehmersicht; normale Texte bleiben möglich |
| Zitate erlaubt, Threads gesperrt | Nur aktuell/historisch berechtigte individuelle Originalvorschau; keine automatische Threadbildung |
| Threadfunktion erlaubt, Reply für Kanal/Rolle untersagt | Keine Reply-Operation über Thread-Sonder-API, nur eigene tatsächlich noch berechtigte Threadsicht |
| A antwortet auf im selben Kanal aktuell und historisch sichtbaren B-Text | Serverseitiger gültiger Parentbezug und separat nach realem neuen Recipientrecht gesendete Antwort |
| A errät private DM-/geheime Nachricht-ID | Kein Parent-/Root-Leak, kein Quelltext, keine fremden Sender/Teilnehmer/Counts, generischer unaufklärender Fehler |
| B darf die Antwort, aber nicht den Parent lesen | Nur gültiger Antworttext; keine verbotene Quellvorschau/Metadaten, ggf. neutraler nicht verräterischer Platzhalter |
| Neue Gruppenmitglieder öffnen alten Thread | Nur historisch berechtigte eigene Antworten, keine automatische frühere Root-/Parent-/Reply-Freigabe |
| Spieler verliert Gruppen-/Channel-/Fog-/Secretrecht | Keine neue Quote-/Thread-/Search-/Push-/Reconnect-Projektion aus ehemaligem Recht |
| SL will ohne spezifische Berechtigung fremde DM-Threads lesen | Verweigert, kein pauschales SL-Leserecht |
| In anderem Kanal wird geheime Parent-ID verlinkt | Kein automatischer kanalübergreifender Quellimport; neue Empfänger erhalten keinen Parenttext |
| Parenttext wird 02.108 nach Versand bearbeitet | Kein über Cache ausgelieferter unberechtigter alter Text; zulässige Revision je Betrachter korrekt |
| Parent wird zurückgezogen oder 02.109 gesperrt | Parentvorschau verschwindet, fremde Antworten nur mit eigenständiger echter Berechtigung; keine Schattenkopie |
| 02.107-Retention für Parent endet | Keine neue Parent-Quote/-Suche/-Count; abgelaufene Inhalte nicht über Threadarchiv wiederherstellbar |
| Flüchtige Nachricht nach Reconnect verloren | Kein erfundener historischer Chat-/Threadinhalt, keine garantierte Offline-Nachlieferung |
| A mutet Threadkanal und erhält Antwort | Kein zusätzlicher optionaler Reply-/Threadhinweis; bewusste berechtigte Chatansicht bleibt nutzbar |
| A blockiert B als DM-Kontakt, B schreibt in alter Direktunterhaltung | Serverseitig keine neue blockierte DM-Reply-/Thread-Zustellung oder versteckter Benachrichtigungs-Bypass |
| A und B im gleichen Gruppenchat trotz DM-Block | Regulär erlaubter Gruppentext bleibt für berechtigte Personen sichtbar; kein gezielter Reply-Ping von B an A |
| B antwortet auf Text von A ohne `@A` | Kein frei erfundener 02.111-Erwähnungsping nur wegen Parentlink |
| Quote enthält `/me öffnet Tür` oder `@alle` | Kein echter Tür-/Node-/NPC-/Quest-/Würfel-/Turneffekt und keine Ping-Umgehung durch Zitattext |
| Threadantwort wird mit `👍` quittiert | 02.112-Reaktionsrechte gelten; kein 02.102-Ack, keine echte Storyentscheidung |
| Parallel: Parent-Edit/Withdraw, Rollenwechsel, Send/Retry | Stale Parent/Versions-/Recipientdaten abgelehnt oder berechtigt neu projiziert; keine Doppelantwort oder Datenfreigabe |
| Bösartige Parent-ID erzeugt Threadzyklus / unendlichen Fan-out | Serverseitige Typsicherheit, Depth-/Rate-/Cycle-Grenze, keine unendliche Queue |
| Gespeicherte Nachricht exportiert/gesucht; Autor hatte damals keine Parent-Sicht | Keine Parent-/Originalinhaltseinblendung oder geheime History-/Count-Auskunft |
| Reale 02.101-Korrektur benötigt persönliche Ackquittung | Nur separate autorisierte 02.102-Aktion erzeugt Ack; Chatantwort/Quote/Thread kann sie nicht ersetzen |

## 8. Beschlussgrenze und nächste Frage

**Verbindlich beschlossen: 02.113 C.** Direktantworten, serverseitig **pro Empfänger berechtigt projizierte** Quellzitate und optionale Chat-Threads sind **bei 02.105 Chat An/Aus** und nach **02.25-Defaults/markierten Ausnahmen** getrennt konfigurierbar. **Keine** globale Zitat-/DM-/Gruppen-/Historienfreigabe, keine unberechtigten Root-/Parent-/Replycounts, keine heimlichen Textkopien durch Cache/Archiv, kein erzwungener Ping, kein tatsächlicher Welt-/System-/Ack-Effekt. Alle bisherigen 02.106–02.112-Rechte und Fristen gelten fort.

**Nicht beschlossen:** Standardtiefe/Threadarchivierung, Thread-Stummschalter als zusätzliche individuelle Detailfunktion, cross-channel Quoting als automatisches Feature, visuelle Thread-/Quote-/Inline-Darstellung, feste Fristen/Limits, MVP-Reihenfolge, finales Datenbankschema und API. Diese bleiben für den späteren Gesamtworkshop offen.

## Nächste Entscheidung 02.114 – Chat-Anhänge, Bilder und Link-Vorschauen

**Beispiel:** Ein Spieler möchte im aktivierten Gruppenchat eine selbst gezeichnete Skizze oder einen Bildhinweis teilen; jemand postet einen Weblink. Sollen Anhänge, Bilder und automatisch geladene Vorschauen Teil des optionalen Chats sein?

- **A – Nur Textlinks:** Keine direkt in AdventureShift gespeicherten oder angezeigten Chatanhänge; normale Links sind lediglich Text.
- **B – Unbegrenzter Upload und automatische Vorschau:** Jeder darf beliebige Dateien und URLs hochladen oder automatisch extern abrufen lassen; Content, private IPs, Geheimnisse und Dateigrößen werden nicht gesondert geschützt.
- **C – Konfigurierbare sichere Medien/Anhänge (Empfehlung):** Bei 02.105 Chat An erlaubte Dateitypen, Upload-/Link-/Preview-Funktionen und Rechte pro Kampagne/Kanal/Rolle konfigurieren; verifizierte Größen-/Inhalts-/Asset-/Urheber-/Malware-/SSRF-Schutzprüfung, datensparsame Metadaten und **aktuelle UND historische 02.107-Recipient-/Retentionrechte** für Download/Thumbnail/Linkvorschau. 02.108–02.113-Edit/Moderation/Mute/Block/Threads gelten mit; kein ungefragtes Ausleiten von Linkabfragen an Dritte oder automatischer Welttrigger. Detail-UI später.
