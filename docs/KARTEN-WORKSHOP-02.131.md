# AdventureShift – Karten-Workshop: Beschluss 02.131 C – geschützte Würfel-/Systemereignis-Referenzen im Chat

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.131; nächste offene Frage 02.132
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungs- und Abnahmetestplan; **noch keine Softwareimplementierung**, keine finalen APIs, DB-Verträge, UI oder MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnenstandards und gültige markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.49–02.51 – akustische Spielweltfunktionen](KARTEN-WORKSHOP.md) · [02.94–02.98 – eigenständige Spielernotizen](KARTEN-WORKSHOP-02.98.md) · [02.99 – autorisierte echte Spielweltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.100 – Korrekturen](KARTEN-WORKSHOP-02.100.md) · [02.101–02.104 – offizielle Korrekturhinweise/ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106 – Kampagnen-/Gruppen-/DM-/SL-Kanäle](KARTEN-WORKSHOP-02.106.md) · [02.107 – heutige und historische Empfänger-/History-/Retentionrechte](KARTEN-WORKSHOP-02.107.md) · [02.108 – Nachrichtenedits/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – Mutes/DM-Senderblock](KARTEN-WORKSHOP-02.110.md) · [02.111 – Mentions/Pings](KARTEN-WORKSHOP-02.111.md) · [02.113 – Replies/Threads](KARTEN-WORKSHOP-02.113.md) · [02.114 – geschützte Medien](KARTEN-WORKSHOP-02.114.md) · [02.115 – Pins/Bookmarks](KARTEN-WORKSHOP-02.115.md) · [02.116 A – keine individuellen Lesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.117 C – Suche/Filter](KARTEN-WORKSHOP-02.117.md) · [02.118 A – keine Draftspeicherung](KARTEN-WORKSHOP-02.118.md) · [02.120 C – Umfragen](KARTEN-WORKSHOP-02.120.md) · [02.121 A – Klartext mit Absätzen](KARTEN-WORKSHOP-02.121.md) · [02.122–02.125 A – abgewählte Chatkomfortmodule](KARTEN-WORKSHOP-02.125.md) · [02.126 C – Notifications](KARTEN-WORKSHOP-02.126.md) · [02.127 A – kein Gameplay-Slowmode](KARTEN-WORKSHOP-02.127.md) · [02.128 A – kein persönliches Message-Hide](KARTEN-WORKSHOP-02.128.md) · [02.129 C – private Kanalorganisation](KARTEN-WORKSHOP-02.129.md) · [02.130 C – persönlicher kanalübergreifender Chatfeed](KARTEN-WORKSHOP-02.130.md).

## 1. Verbindliche Entscheidung – Variante 02.131 C

**Der Projektinhaber hat C gewählt:** Bei tatsächlich aktiviertem **02.105 Chat** darf die SL im Rahmen von **02.25-Kampagnen-/Ereignistyp-/Kanaltyp-/Gruppen-/Rollen-/Personenstandards sowie gültigen markierten Ausnahmen** bestimmen, ob geeignete, für die jeweilige Person wirklich freigegebene **Würfel- und Systemereignisse zusätzlich als reine, read-only Referenzprojektion in erlaubten Chatkanälen und optional der 02.130-Sammelansicht** erscheinen. Das echte Originalereignis und sein eigener autoritativer Verlauf bleiben unabhängig vom Chat bestehen; dessen Rechte, Inhalt, Wurfwert und Wirkung werden nicht durch Chattext verändert.

**Beispiel:** Spieler A führt einen öffentlichen Würfelwurf aus. Das serverautoritative Würfelergebnis ist für die Mitglieder der Kampagnengruppe freigegeben und kann nach wirksamer Chat-/Projektionspolicy in deren Kanal als referenzierter, autorisierter Würfelhinweis sichtbar sein. Ein nur an die SL adressierter Geheimwurf wird **nicht** durch denselben Kanal, eine Badgezahl, einen Zeitstempel, eine Vorschau oder die Sammelansicht gegenüber Spielern verraten. Chat Aus bedeutet **nicht**, dass die Würfel oder der eigene Systemfeed abgeschaltet werden.

**Nicht gewählt:** A (niemals zusätzliche Chatreferenzen) und B (alles ungefiltert in Chat, ohne eigene Protokolle). Variante C ist **keine** Umstellung der Spielereignisse auf normale, editierbare Chatnachrichten; kein automatisches Offenlegen aller Würfe/SL-Geheimnisse und keine neue globale Kanalmitgliedschaft.

## 2. Aktivierung, fachlicher Umfang und Zielansichten

1. **Vorrang der unabhängigen Quelle:** Würfel-RNG, Ergebnis-/Audit-/Spielereignis-Commit, zugelassene Systemmeldungen und offizielle 02.101–02.104-Notice-/ACK-Flows liegen in **eigenen fachlichen Protokollen/Modulen**. Eine Chatprojektion kann weder Quelle noch tatsächlichen Zustand ändern, stornieren, freigeben oder noch einmal ausführen. Auch bei Chat Aus bleibt die autorisierte Originalanzeige und -funktion gemäß eigener Aktivierung/Policy möglich.
2. **Separate Schaltbarkeit:** Chat An ist notwendige, aber nicht hinreichende Bedingung. Die SL kann die zusätzlichen Chat-Anzeigeverknüpfungen **nach geeigneten Ereignistypen und Zielkanal-/Empfänger-Scopes** mittels 02.25-Defaults und gültigen markierten Ausnahmen zulassen oder sperren. Rechteprüfungen sind **nicht** optional. Welche konkreten Eventkategorien, Zielkanäle, Presets, Anzeigeformen und UI-Schalter unterstützt werden, folgt nach Abschluss der Featureentscheidungen.
3. **Geeignete Quellkategorien:** Nur tatsächlich bestehende, freigabefähige **Würfel- und Systemereignisse**, z. B. autorisiert sichtbare Würfelergebnisse, Runden-/Initiative-/Sitzungsstatus oder erlaubte Regel-/Systemhinweise, *sofern* eine passende Quelle, tatsächliche eigene Sichtbarkeit und freigegebene Zielprojektion existieren. Keine automatische Behauptung, dass jeder dieser Eventtypen bereits technisch implementiert ist oder stets dieselben Retentionsrechte besitzt.
4. **Nur Referenz statt neue Nachricht:** Ein read-only **typisierter Verweis auf Quellereignis-ID/Version** kann in einer autorisierten Channelansicht angezeigt werden. Der Server löst erlaubte Anzeigeinhalte bei jeder Projektion aus der maßgeblichen Quelle neu auf. Kein Umwandeln in 02.121-freien Chattext, keine manipulativ editierbare Ersatzkopie des Würfels oder SL-Geheimnisses und kein dauerhafter doppelter Text-/Attachment-/Event-Store in der Chathistory.
5. **Zielkanäle und gemeinsame Ansicht:** Eine Projektion darf nur einen **effektiv erlaubten** 02.106-Kanal beziehungsweise eine bereits autorisierte 02.130-Sammelansicht erreichen. Der Kanal muss nicht allen Teilnehmern das Ereignis zeigen: pro Betrachter gilt die Schnittmenge aus wirklichem **heutigem** Kanalrecht, für den Ereigniszeitpunkt relevantem **historischem** Empfänger-/Historyrecht und **Quellereignisrecht**. Nicht Berechtigte sehen auch keinen Platzhalter, Unread, Count, Existenzhinweis, Sender-/Wurftyp oder Eventzeitpunkt.
6. **Keine unerlaubte Nachzustellung:** Chat-, Kanal-, Feature- oder Ereignisfreigaben führen nicht allein zu rückwirkender Freigabe früherer Geheimwürfe oder historischer privater Nachrichten. Original-Event- und Chat-Retention/Archivgrenzen bleiben unabhängig: Ein Chatverweis **verlängert keine** Aufbewahrung; die Projektion ist nur verfügbar, solange alle für sie erforderlichen Quellen/Ansichten zulässig existieren.
7. **Keine zusätzlichen Chataktionen:** Anklicken eines berechtigten Eventverweises öffnet höchstens die **eigenständig erneut autorisierte** Originalanzeige, niemals 02.99-Spielweltaktionen, Würfel-Neuwürfe, 02.102-ACKs oder eine improvisierte Chat-Antwort im Namen des Originalevents. Gewöhnliche Reply/Reaction/Bookmark/Suche kann nur nach ihren **separaten** 02.113-/02.112-/02.115-/02.117-Fähigkeiten und Quellenrechten konzipiert werden; kein neuer Default durch C.

## 3. Berechtigungen und bereits entschiedene Grenzen

| Grenze | Konsequenz für 02.131 C |
| --- | --- |
| **02.105 Chat An/Aus und 02.25 Defaults/Ausnahmen** | Keine Chatreferenz, Chat-Abo, Suchprojektion oder neue Feed-Aktion bei Chat Aus; eventeigene Protokolle bleiben |
| **02.106 / 02.107 Kanal-/Historyrechte** | Channel-/DM-/Gruppen-/SL-Membership und **heutige UND historische** Empfänger-/Retentionrechte je Betrachter; keine fremden Empfänger-/Kanal-Existenzdaten |
| **Autoritative Würfel-/Systemereignisse** | Originalausgabe/Originalrecipients/Geheimwurf-/Fog-/Quest-/NPC-/SL-/Eventversion-/Retentionrechte gelten zusätzlich; Chat ist nie Wurf- oder Systemdatenquelle |
| **02.108 / 02.109 Chatbearbeitung/Moderation** | Chatmeldung/Moderation oder normale Nachrichtenedits dürfen Originalereignis **nicht** verändern; wenn Projektion nach Policy unterdrückt wird, bleibt eigener geschützter Quellzustand unberührt |
| **02.100 / 02.101–02.104 Korrekturen und amtliche Hinweise** | Offizielle Notice/ACK/Reminder bleiben rechtlich/fachlich eigene Zustände. Referenz ist kein neues amtliches Pflichtzustellmedium und kein bewusstes ACK |
| **02.110 Mutes/DM-Blocks, 02.111 Mentions und 02.126 Notifications** | Zusätzlicher Chateintrag respektiert eigene Mute-/Block-/Ping-/QuietHours-/OS-Privacy; keine Doppelnotification zum eigentlichen Ereignis und keine Aushebelung gesondert erforderlicher Systemhinweise |
| **02.112–02.115, 02.117 und 02.120** | Keine automatischen Reaktions-, Reply-, Thread-, Upload-, Pin-, Such- oder Pollrechte durch eingeblendeten Quellverweis |
| **02.116 A** | Keine individuellen Read-/Delivery-Receipts, wann Spieler den Wurfhinweis gesehen oder geöffnet haben |
| **02.118 A, 02.121 A** | Keine Chatdrafts, Autosend oder neues Rich-Text-Markup; Eventkarte ist strukturierte *Systemdarstellung*, nicht ein HTML-/Markdown-Chattext |
| **02.122–02.125 A, 02.127 A** | Keine Chat-Voice-Memos, Weiterleitung, Übersetzung, Komfortexport/-druck oder spielerischer Slowmode durch diese Anzeige; technischer Flood-/Abuse-Schutz bleibt |
| **02.128 A / 02.129 C / 02.130 C** | Keine persistente persönliche Einzelmessage-Hideliste; private Kanal-Favoriten und virtuelle Sammelansicht eröffnen weder neue Quell-/Historyrechte noch Fremdstatistiken |
| **02.49–02.51 Akustik** | Würfel-/Systemreferenz erzeugt **keinen** tatsächlichen Szenensound, Schallsensoralarm, Nodeoutput oder regionalen Hörbarkeitszustand; akustische Gameplay-Systeme bleiben eigenständig |

**Geheimnisregel:** Ein geheimer Wurf darf selbst dann nicht als „Geheimer Wurf geschah“ in unberechtigten Channelcounts/Badge-/Sound-/Lockscreen-Nachrichten auftauchen, wenn seine Würfelaugen verborgen bleiben. Gleiches gilt für SL-only-Systemereignisse, NPC-Positionen, versteckte Quests, Würfel-Formeln und spätere korrigierte/entzogene Originalinformationen.

## 4. Lebenszyklus, Realtime und Integritätsmodell

1. **Quelle zuerst:** Der autoritative Würfel-/System-/Noticehandler commitet ein Event **einmal** nach seinem fachlichen Recht. Ein optionaler Projektor darf dieses Ereignis nur referenzieren; er darf keine zusätzliche RNG-, Würfel-, Loot-, Tür-, Alarm-, Quest-, NPC- oder Turn-Transition auslösen.
2. **Rechte pro Empfänger und Zeitpunkt:** Vor Channelprojektion, Realtime-Push, Badge, Preview, Such-/Sammelansicht, Navigationslink, Reconnect oder Wiederholung **je Betrachter** gültige Source-Event-Recipient-/Originalsicht UND aktuelle Quell-/Fog-/Secret-/Retentionrechte, 02.106-/02.107-Channel-ACL und wirksame 02.25-/02.105-Anzeige-Policy prüfen.
3. **Typisierte Herkunft und Versionsbindung:** Konzeptionelle Eventreferenz trägt mindestens Quelltyp, interne Event-/Revisionsidentität, Ziel-/Kontextreferenz und gültigen Projektionszustand. Client darf diese nicht verwenden, um beliebige fremde Event-IDs abzurufen oder durch generierten Chattext das Original zu ersetzen.
4. **Widerruf/Korrektur:** Quell-ACL-/Fog-/Geheimnis-/Rollentausch, Eventrevision, echter Widerruf oder offizielle 02.100-Korrektur führen bei nächsten Projektionen zu gegenwärtig berechtigter Darstellung/entfallendem Hinweis, nicht zu einem dauerhaften alten Cachetext. Bereits menschlich gesehene Informationen lassen sich nicht rückwirkend aus Erinnerungen löschen; keine falschen Garantien.
5. **Channel-/Featurewechsel:** Abschalten des integrierten Chats oder der 02.131-Anzeige stoppt neue Chatreferenzen und aktive projektionseigene Feeds, ohne Würfel-/System-/Notice-Ledger zu löschen. Reaktivierung ist kein automatisches Backfill abgelaufener oder nie an Empfänger freigegebener Events.
6. **Dedup/Ordnung:** Dasselbe Event in Originalfeed, ggf. mehreren erlaubten Chatanzeigen und 02.130-Feed bleibt **dasselbe** Originalereignis. Anzeigen referenzieren per stabiler projektionsgebundener Identität, unterbinden Reconnect-Duplikate, doppelte Unread-/Toast-/Sound-/ACK-Zählung und falsch aufaddierte Quellereignisse. Zeit-/Cursorinformationen nur aus bereits autorisierter Projektion.
7. **Quoten und Fehlersicherheit:** Fehlende Events, abgelaufene Retention, ungültige Zielkanal-IDs oder fremde Quell-IDs ergeben keine Geheimtext-/Existenz-/Member-/Recipient-Offenlegung; Batch-/Rate-/Queue-/Fanout-/Replay-/Cache-Schutz, eventeigene Idempotenz und sichere Logs/Audits.

## 5. Konzeptioneller Umsetzungsplan

1. **Capability-Policy:** Bei 02.105 Chat An nach 02.25 schaltbare **Würfel-/System-Referenzprojektion**, getrennt nach zulässigen Event-/Kanal-/Recipient-/Rollen-/Ausnahmescopes, ohne der Quelle oder dem Nutzer mehr Rechte zu verleihen. Chat Aus sperrt nur Chatprojektion.
2. **Quellprüfer:** Konzeptionell `AuthorizedGameEventView` mit echt ursprünglichem Empfängerkreis, aktuellem Quell-/Secret-/Fog-/Retention-/Versionzustand sowie ggf. getrennten 02.101–02.104-Notice-/ACK-Rechten; in jedem Render-/Realtime-/Linkpfad serverseitig prüfen.
3. **Channelprojektion:** Konzeptionell `ChatEventReferencePolicy`, `ChatEventViewProjection`, `ChatEventRecipientResolution` und `ChatEventProjectionKey` (nur Arbeitsnamen); referenzieren statt Quellwürfel-/Systemereignisse als gewöhnliche Chatautorenmessages zu kopieren. 02.106-/02.107-Channel-/Historienberechtigung zusätzlich, keine versteckte Existenzlecks.
4. **Anzeige/Klick/Feed:** Typisierte, read-only Ereigniskarte nach aktueller Feldsicht; nur bei separater aktueller Quelle/Channelberechtigung navigierbar. Optionales Einsortieren in 02.130-Aggregation mit einem einzigen Original-/Dedup-Schlüssel; getrennte Event- und Chat-Notification-Pipelines mit persönlicher 02.110-/02.126-Priorität.
5. **Änderungs- und Retentionsschutz:** ACL-/Korrektur-/Quellrevision-/Secret-/Eventrettention-/Chatpolicy-Wechsel entwerten Caches, Cursor, Snippets, Badges und Realtimeprojections; niemals neue Shadowhistory durch Kopieren, echten Wurf neu committen oder offiziellen ACK automatisch erzeugen.
6. **Tests und spätere Entscheidungen:** Fälle unten durchlaufen; konkrete fachlich unterstützte Eventtypen, UI-Darstellung, Sound-/Anzeigeoptionen, Performancebudgets, Datenmodell/API und MVP erst im anschließenden Gesamt-Settings-/Architektur-/UX-Workshop finalisieren.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| 02.105 Chat Aus bei Kampagnenerstellung | Würfel-/Systemquelle funktioniert nach eigenem Recht; keine Chatprojektion, kein Chat-Abo |
| Chat An, 02.131-Anzeige Aus | Gewöhnliche Chatnachrichten normal, Würfel/System nur in eigenen Protokollen |
| Chat An, SL erlaubt freigegebene Würfe im Kampagnenkanal | Ein echter autoritativer Originalwurf, zusätzlich nur berechtigte read-only Referenz |
| SL führt geheimen Würfelwurf aus | Spieler sehen weder Würfelzahl/Formel noch Existenz, Channelcount, Toast oder Dummykarte |
| Öffentlicher Wurf für Gruppe A, Spieler aus Gruppe B | Kein fremder Wurfreferenztext, Link, Badge, Zeitstempel oder Gruppenname |
| Gruppe erhält neues Mitglied | Keine automatische alte private Spielereignis-/Chat-Historie durch Eintritt |
| Ehemaliger Empfänger verliert heutiges Quell-/Kanalrecht | Kein Zugriff auf Eventreferenz, Link, Originalwurf oder Cache trotz vorheriger Berechtigung |
| SL besitzt Kampagnenverwaltung, aber kein DM-/Geheimwurfleserecht | Kein automatischer Zugriff auf private fremde Würfe über Adminstatus |
| Chat An und Würfel-/Systemmodul im eigenen Modus | Chat spiegelt Quelle, schaltet sie nicht ein/aus oder um |
| Realtime-Event in zwei zulässigen Ansichten | Keine doppelte Quelle, doppelte Notification/Unread/ACK oder zusätzlicher echter Wurf |
| Spieler klickt einen gültigen Eventverweis | Nur erneut berechtigte originale Eventansicht; keine Änderung/Neuwurf |
| Spieler manipuliert Event- oder Kanal-ID | Kein fremder Datenabruf und keine Secret-Existenz-/Fehlertextausleitung |
| Normaler Chattext enthält `/roll 20` oder `Tür öffnen` | Kein echter Dice-/Door-/Node-/Quest-/Turn-/Inventareffekt |
| Angreifer sendet gefälschte Eventkarte als Nachricht | Keine Autoritäts-/System-/Würfelberechtigung durch Chattext oder Clientpayload |
| Berechtigter Würfelbericht wird nach Quellpolicy verborgen | Referenz und sämtliche Caches/Previews/Toasts/Unread neu redigiert bzw. weg |
| 02.100-/02.101-Korrektur eines Events | Original und eigene Korrekturhistorie bleiben wahr; Referenz zeigt nur aktuell zulässigen Stand |
| 02.102-ACK erforderlich | Chatkarte lesen, wegklicken oder Favorit setzen quittiert **nicht** automatisch |
| 02.103-Reminder während Chat Aus | Offizielle Reminder weiterhin nach eigener Berechtigung/Policy, nicht durch Chatschalter verloren |
| 02.110 Kanal stummgeschaltet | Keine unzulässigen Chat-Töne/Pushes; unabhängige verpflichtende Systemhinweise bleiben |
| 02.110 DM-Senderblock | Keine neue unberechtigte DM durch Eventprojektion; alte rechtmäßige History getrennt |
| 02.116 A persönliche Lesebestätigungen ausgeschaltet | Kein „Person X hat Wurfbericht gesehen“ durch Klick/Scroll |
| 02.117-Suche nicht erlaubt | Eventreferenzen aktivieren keine unberechtigte neue Chat-Volltextsuche |
| 02.118 A keine Chat-Entwürfe | Eventprojektionen speichern keine Composerentwürfe und versenden nichts automatisch |
| 02.123 A Weiterleiten ausgeschlossen | Kein Eventforward/-Crosspost-Knopf, keine Kopie in fremdem Channel |
| 02.125 A kein Chatkomfortexport | Kein „Würfel-/Systemevents aus Chat exportieren“-Sonderweg |
| 02.128 A keine Einzelmessage-Ausblendung | Referenzen sind keine eigene neue Hide-/Restore-Funktion |
| 02.129 private Kanalreihenfolge und 02.130-Sammelansicht | Nur zusätzliche **berechtigte** Anzeige, keine fremde Kanal-/Event-Sicht |
| 02.107-History flüchtig, Quelle nicht mehr verfügbar | Reconnect verspricht keinen gespeicherten eventbasierten Chatschatten |
| 02.126 OS-Lockscreen ohne Textfreigabe | Keine geheime Würfel-/NPC-/Eventinformation oder Quelle über Push |
| Viele gleichzeitige Events/Reconnect/Doppelsend | Quellereignisse und Projektionen dedupliziert, Fanout/Quoten begrenzt |
| Zwei Kampagnen desselben Accounts | Keine fremden Event-IDs, Chat-Referenzen, History oder Notification-Counts |
| 02.49–02.51 Akustik aktiv | Chatwürfelkarte erzeugt keinen zweiten echten Szenensound oder Sensor-/Alarm-/Nodeeffekt |

## 7. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.131 C – konfigurierbare, berechtigungssichere read-only Referenzanzeige erlaubter Würfel-/Systemereignisse in aktiviertem Chat und ggf. autorisierter 02.130-Sammelansicht.** Quelle, Würfelprotokoll, Systemfeed, Originalrechte, geheime Würfe, 02.101–02.104-Notices/ACKs und 02.99-Spielweltwirkungen bleiben **unabhängig**; ein Chatschalter oder Empfänger-/Channel-Override darf keine Quell-, History- oder Geheimnisrechte erweitern. Fortgeltend 02.105 Chat An/Aus, 02.106-/02.107 aktuelle UND historische Channel-/Message-/Recipient-/Retentionrechte, 02.108-/02.109-Revision/Moderation, 02.110-Mutes/DM-Blocks, 02.116 A keine persönlichen Receipts, 02.118 A keine Drafts, 02.123 A keine Weiterleitung, 02.125 A kein Chatkomfortexport, 02.126-C-Notificationprivacy, 02.127 A kein Spiel-Slowmode, 02.128 A kein Message-Hide und 02.129-/02.130-C-Personalisierung ohne Quellfreigabe.

**Nicht beschlossen:** feste Eventtypen, Default-Ereigniskanäle, konkretes UI/Detaillevel, Event-/Chat-Aufbewahrungsfristen, Payload-/Cursor-/DB-/API-Entwurf, Performancezahlen, MVP oder eine direkte Würfelsteuerung aus Chat.

## Nächste Entscheidung 02.132 – Musik-Playlists und Soundboard für Spielsitzungen

**Beispiel:** Eine SL möchte bei einer Taverne Hintergrundmusik starten und beim Kampf einen anderen Track abspielen. Manche Gruppen lösen Musik lieber manuell im externen Voicechat; andere möchten Musik/Umgebungsgeräusche passend zur Szene automatisieren. Die bereits beschlossenen **akustischen Spielwelt-/Schall-/Sensorfunktionen 02.49–02.51** dürfen durch einen reinen Musikplayer weder heimlich aktiviert noch simuliert werden.

- **A – Keine integrierte Musik-/Soundboardfunktion:** Hintergrundmusik, Soundboards und Playlists werden außerhalb der Anwendung organisiert; die vorhandenen eigenständigen Szenen-/Akustikfunktionen bleiben nach früheren Beschlüssen bestehen.
- **B – Jeder steuert weltweit alles:** Jeder Kampagnenteilnehmer kann ohne Rollen-/Asset-/Lautstärke-/Geheimnisrechte beliebige Musik oder Töne für alle Teilnehmer erzwingen und dabei auch verborgene Szenen/Dateien auslesen.
- **C – Konfigurierbare, berechtigte Session-Musik/Soundboards (Empfehlung):** Die SL kann bei Kampagnenerstellung nach 02.25-Defaults/markierten Ausnahmen eine **eigenständige** Musik-/Playlist-/Soundboardfähigkeit aktivieren und für geeignete Rollen, Szenen, Empfängerbereiche und Musik-/Cue-Aktionen manuelle, SL-bestätigte oder unterstützte automatisierte Steuerung erlauben. Audiodateien/Playlists nur nach Asset-/Lizenz-/Medien-/Geheimnisrechten; eigene Lautstärke-/Muteoptionen pro Hörer. Der Musikplayer ist **nicht** automatisch das 02.49–02.51-Schallmodell, kein Sensor-/Node-/Alarm-Trigger, kein Chatzwang und kein Mithören externer Voicechats; technisches Playback/UI und konkrete Eventintegration später.
