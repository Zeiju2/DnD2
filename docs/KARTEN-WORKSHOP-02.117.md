# AdventureShift – Karten-Workshop: Beschluss 02.117 C – konfigurierbare berechtigte Chat-Suche und Filter

**Stand:** 13.10.2026 – Fachbeschlüsse 02.1 bis 02.117; nächste offene Frage 02.118
**Status:** Verbindlicher Fachbeschluss und konzeptioneller Umsetzungs-/Abnahmeplan; **noch keine Softwareimplementierung**, finalen API-/DB-Verträge, festen Suchlimits, konkreten Such-UI-Layouts oder finale MVP-Priorisierung.
**Bezüge:** [02.25 – globale Standards und markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – private Spielernotizen und schaltbare Kampagnenfunktionen](KARTEN-WORKSHOP-02.98.md) · [02.101–02.104 – amtliche Notices und bewusste ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat bei Kampagnenerstellung An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106 – Kanal-/Gruppen-/DM-/SL-Rechte](KARTEN-WORKSHOP-02.106.md) · [02.107 – aktuelle UND historische Empfängersicht, flüchtige Historie, Retention](KARTEN-WORKSHOP-02.107.md) · [02.108 – Edit/Withdraw/Revisionen](KARTEN-WORKSHOP-02.108.md) · [02.109 – Meldung/Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – Channel-Mute und DM-Senderblock](KARTEN-WORKSHOP-02.110.md) · [02.111 – Mentions/Pings](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen und Emotes](KARTEN-WORKSHOP-02.112.md) · [02.113 – Antworten/Zitate/Threads](KARTEN-WORKSHOP-02.113.md) · [02.114 – Anhänge/Medien/Linkvorschau](KARTEN-WORKSHOP-02.114.md) · [02.115 – Kanalpins und private Lesezeichen](KARTEN-WORKSHOP-02.115.md) · [02.116 A – keine individuellen Lesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [Kommunikationsworkshop 11](FEATURE-WORKSHOP.md).

## 1. Verbindlicher Beschluss – Variante 02.117 C

**Der Projektinhaber hat C gewählt: konfigurierbare, serverseitig berechtigungsgefilterte Chat-Suche mit Volltext- und optionalen strukturierten Filtern.** Die SL kann bei Kampagnenerstellung für den **02.105 Chat An/Aus** nach 02.25-Kampagnen-/Regelprofil-/Kanaltyp-/Kanal-/Rollen-/Gruppen-/Empfängerstandards und zulässigen markierten Ausnahmen festlegen, **welche tatsächlich unterstützten Sucharten** in welchen berechtigten Chats verfügbar sind. Die Funktion erweitert die unter 02.107 bereits verbindlich beschlossenen sicheren Suchpfade; sie **hebt keine einzige bestehende Authentifizierungs-, Kanal-, Nachrichten-, Historien- oder Quellenberechtigung auf**.

**Erlaubbare Sucharten:** Volltextsuche nach gewöhnlich berechtigt sichtbarem Nachrichtentext, Filter nach tatsächlich erlaubtem Kanal/Team, berechtigtem echten Absender, Zeitraum, ggf. Nachrichtentyp/Emote, eigener Erwähnung (ohne andere Empfängerdaten), zulässig sichtbarem Thread/Reply sowie **nur nach gesonderten 02.114-Datei-/Metadatenrechten** Bildern, Anhängen oder Linkvorschauen. Für gespeicherte Chatverläufe ist auch die Kombination mehrerer zulässiger Filter konzeptionell vorgesehen. Einzelne Filterarten können in einer Kampagne vollständig Aus sein; allgemeines `Chat Aus` blockiert serverseitig alle regulären Suchoperationen.

**Beispiel:** Spieler A sucht „Generator“ in seinem früheren Teamchat. Er findet die Nachricht nur, wenn sie für A **zum damaligen Zeitpunkt** tatsächlich adressiert war, heute noch rechtmäßig lesbar ist und nicht abgelaufen, gesperrt oder entfernt wurde. Ein inzwischen neuer Teamkollege C erhält dadurch keine Suchtreffer aus der alten Team-Epoche. Auch die Ergebnisanzahl und Filtervorschläge dürfen C die Existenz früherer geheimer Beiträge nicht verraten.

**Nicht gewählt:** A (keine zusätzlichen Such-/Filterfähigkeiten über einfache Verlaufnavigation) und B (unberechtigte kampagnenweite Volltextsuche über alle DMs, Secrets und alten Fassungen). Ein kampagnenweit deaktivierter Suchkomfort ist unter C dennoch eine zulässige Konfiguration; die darunterliegenden 02.107-ACL-/Retentionschutzpflichten bleiben.

## 2. Konfiguration, Filter und zulässiger Umfang

| Such-/Filterfunktion | Bei gültiger 02.25-/02.105–02.107-Berechtigung möglich | Verbindliche Grenze |
| --- | --- | --- |
| **Volltext** | Suchbegriff/Phrase in **heute und historisch zugänglichen** Textnachrichten und zulässigen aktuellen 02.108-Revisionen | Keine fremden DMs, unbekannten Secrets, alten zurückgezogenen oder bereits abgelaufenen Fassungen |
| **Kanal/Gruppe/DM** | Suche im einzelnen aktuell zugänglichen Kanal oder bewusst freigegebene kombinierte Suche | Keine Anzeige von verborgenen Kanalnamen, Teammitgliedschaften oder fremden DM-Beziehungen im Filter/Autocomplete |
| **Absender** | Nach tatsächlich berechtigt sichtbaren Verfassern filtern, mit servergebundener echter Senderidentität | Keine globale Personen-/NPC-/SL-Identitätsauflösung anhand erratener IDs oder bloßem Nickname |
| **Zeitraum/Sortierung** | Rechtmäßig verfügbare Nachrichten nach Sendezeit/zulässiger Reihenfolge eingrenzen | Keine versteckten Aktivitätsfenster, Lesezeitpunkte oder Zeitstempel als Such-Orakel |
| **Antwort/Thread** | Nur berechtigt lesbare eigene 02.113-Parent-/Root-/Childnachrichten finden bzw. filtern | Treffer öffnet keinen geheimen Parent, keine fremde Childantwort und keine fremden Thread-Counts |
| **Nachrichtentyp/Emote/Erwähnung** | Unterstützte 02.111-/02.112-Informationen nur im wirklich berechtigten Message-/Actor-/Recipient-Scope filtern | Keine Anzeige geheimer Mentiontargets, privater Blockbeziehungen, Reaktionsautorlisten oder versteckter Gruppen |
| **Bilder/Anhänge/Links** | Optional nach zulässigem Medienvorhandensein/Typ oder dafür lesbaren Dateimetadaten filtern | 02.114-Original-/Thumbnail-/Download-/Previewrechte zusätzlich prüfen, nie Dateiname/URL als Nebenkanal ausleiten |
| **Eigene Pins/Lesezeichen** | Berechtigte 02.115-Channel-Pins oder nur eigene Bookmarks als Suchumfang einbeziehen | Private Bookmarks anderer sind keine fremde Filterliste; Pin kopiert keine abgelaufenen Chatinhalte |
| **Exporte/Hervorhebung** | Nur zulässigen Treffertext und begrenzte sichere Hervorhebung/Navigationslinks zeigen | Ausgeleitete Snippets, Count-/Facetdaten und Export benötigen denselben aktuellen/historischen Quellschutz wie der Treffer |

**Rechte getrennt betrachten:** Konzeptionell `searchChat`, `searchAcrossOwnedChannels`, `filterChatBySender`, `filterChatByMedia`, `readSearchPreview`, `navigateToChatMessage` und eine ggf. rechtmäßig freigegebene `exportSearchResults`-Fähigkeit; nicht jede Suchberechtigung ist automatisch ein Dateidownload-, DM-Export-, Quellrevisions- oder Moderationsrecht. Die SL kann unterstützte Filter erlauben/einschränken, **nicht** historische 02.107-Zugriffe beliebig überschreiben. Exakte Reihenfolge der UI, unterstützte Volltextoperatoren, Indizierungsverfahren, Sprachen und Suchkontingente bleiben späteren Implementierungsentscheidungen vorbehalten.

## 3. Doppelte Rechteprüfung: heute UND historisch

1. **Vor jeder Suchanfrage:** Echte Accountidentität, aktive Kampagnenmitgliedschaft, 02.105-Chat-An, erlaubte Suchfähigkeit und 02.25-Ausnahmen, heutige 02.106-Kanal-/DM-/Gruppen-/SL-Rechte und aktuelle 02.109-Einschränkungen prüfen. Ein Client darf weder per freiem Filter noch durch manipulierte Channel-/Sender-/Message-IDs beliebige verborgene Datensätze durchsuchen.
2. **Pro möglichem Ergebnis:** Die Nachricht muss nach 02.107 **an den Suchenden zum ursprünglichen Zeitpunkt historisch berechtigt adressiert** worden sein **UND heute mit aktuell gültigen Quell-/Empfänger-/Gruppe-/Kanal-/Fog-/NPC-/Quest-/Notiz-/Wurf-/Secretrechten** lesbar sein; zulässige 02.108-Version/Withdraw und 02.109-Moderationsstatus sowie 02.107-Retention müssen stimmen. Alte Gruppenmitgliedschaft alleine oder SL-/Moderatorstatus alleine ist nicht hinreichend.
3. **Der Index ist kein Rechteentscheid:** Selbst wenn eine interne Suchdatenstruktur technisch verschiedene erlaubte Texte enthält, dürfen Suche, Zählung, Snippet, Filterfacet, Wortvorschlag, Relevanz, Pagination-Cursor, Ergebnis-Reihenfolge, Export oder Realtime/Retry **nur** nach aktueller individueller und historischer Rechteprojektion Informationen preisgeben. Indexpartitionierung/geschützte Indexfelder, Sicherheitsfilterung **vor** der sichtbaren Aggregation und revalidierte Page-Cursor sind einzuplanen.
4. **Nur zulässige Revisionen indexieren/projizieren:** 02.108-Edit darf nicht über alte Suchbegriffe, Highlight-Snippets, Dateinamen oder Indexcache eine ehemals sichtbare, heute unzulässige Originalversion offenbaren. Sicht auf alte Revisionen bedarf eigener aktueller UND historischer Revisionsrechte; gewöhnliche Suche zeigt nur die gerade hierfür autorisierte Fassung. Withdraw/Moderationssuppression sperren reguläre Treffer.
5. **Keine Existenzorakel:** Verborgenes Channel-/DM-/Gruppeziel, fremder Autor, privater Attachmenttyp, geheimer NPC-/Questbegriff, interner Message-Key oder Reaktions-/Threadbezug dürfen über „0 Treffer vs. Zugriff verweigert“, Suchvorschläge, Ergebnis-IDs, Facet-Anzahl, Timing und Pagination keine unnötigen Details offenlegen. Fachlich neutrale und gleichartig geschützte Auskünfte vorsehen.
6. **Navigation ist keine neue Freigabe:** Klick auf Treffer ruft die reguläre aktuell UND historisch autorisierte 02.107-Messagelesung auf, einschließlich 02.113-Parent-/Thread- und 02.114-Attachment-Rechten; beim Rechteverlust zwischen Suche und Navigation muss der Quellaufruf abgewiesen werden.
7. **02.110-Mute/DM-Senderblock:** Channel-Mute verändert **nur optionale Benachrichtigungen**, nicht eigenmächtig das rechtmäßige Durchsuchen weiterhin zulässig lesbarer Texte. Ein persönlicher DM-Block sperrt neue private Direktzustellungen dieses echten Senders, **löscht aber frühere rechtmäßige 02.107-DM-Historie nicht pauschal**. Suche darf jedoch keinen neuen DM-Kontakt oder gerichteten Ping als Block-Bypass auslösen und keine fremde Blockliste offenlegen.

## 4. Speicher- und Index-Lebenszyklus

**Gespeicherte 02.107-Verläufe:** Die Suche arbeitet nur innerhalb der zulässig gespeicherten und noch gültig aufbewahrten Nachrichten. Ein Suchindex, Tokenstamm, Wörterbuch, Previewcache, Facetaggregat, Export, Pager oder Backup darf **keine unabhängige dauerhafte Schattenhistorie** schaffen. Änderungen an Retention-/Index-/Backup-/Restore-/Schutz-Policies benötigen einen fachlich nachvollziehbaren Rebuild/Prune/Invalidierungsweg. Replikat- und Snapshotdaten bleiben mindestens gleich geschützt wie die Originaltexte, ohne die physische sofortige Entfernung jeder Menschenkopie zu versprechen.

**Flüchtige 02.107-Verläufe:** Keine garantierte rückwirkende Volltextsuche und kein dauerhafter Suchindex für nach Chat-/Restart-/Offline-Ende verschwundene flüchtige Nachrichten. Soweit vorhandene flüchtige Live-Nachrichten rechtmäßig in einer aktuellen Ansicht gefiltert werden können, ist das **kein** Versprechen einer späteren History, Push-Retry oder gespeicherten Suchkopie. Chat Aus beendet gewöhnliche Suchoperationen, nicht rechtmäßig bestehende Datenschutz-/Retentionarbeit.

**Edit/Withdraw/Moderation:** Neu veröffentlichte 02.108-Revision, gültiger Withdraw-/Removalbeleg aus 02.108/02.109, Rollenentzug, Gruppenwechsel, Ablaufdatum und Policyänderung müssen sichtbare Such-/Autocomplete-/Snippet-/Count-/Export-/Realtime- und Reconnect-Projektionen unverzüglich unter den neuen Rechten sperren. Technisches Index-Reindexing ist versioniert/idempotent; ein verspätetes Worker-Update darf alten Text nicht erneut in autorisierte Treffer hochspülen. Gezielte eigene Audit-/Moderationsbelege bleiben nur nach ihrem **eigenen** Fall-/Datenrecht, nicht über normale Chatsucheinträge.

**02.114-Medien:** Bild-/Dateinamen, Linkziele, Thumbnails, MIME- und Typfilter dürfen niemals den ursprünglichen Attachment-/Chat-Recipient-/Downloader-ACL umgehen. Text aus Dateien, OCR, PDF-Indexierung oder externe Website-Inhalte werden durch 02.117 C **nicht automatisch als bereits beschlossene Volltext-Suchquelle** freigeschaltet; dies benötigte später ausdrücklich geprüfte Format-/Datenschutz-/Leistungs-/Sicherheitsregeln. Medienfilter ist kein impliziter Freigabe- oder Parserauftrag.

**02.113-Threads, 02.115-Bookmarks:** Suchbarkeit von Parent-/Root-/Reply oder Channelpin/Bookmark setzt für die konkrete Nachricht echte heute und historische Berechtigung voraus. Ein Suchtreffer aus einer erlaubten eigenen Nachricht darf nicht automatisch Inhalte aus unberechtigter Eltern-DM, früherem Thread oder anderem gebookmarkten Kanal in eine Vorschau ziehen.

## 5. Datenschutz, Rate- und Anti-Leak-Schutz

- **02.116 A bleibt verbindlich:** Die Suchfunktion erzeugt **keine individuellen „hat gelesen“-/„zugestellt“-Bestätigungen, Lesetimestamps, Empfängerstatistiken oder an SL/Sender ausleitbare Such-/Lese-Verlaufskontrollen**. Erlaubte eigene Suchinteraktion ist kein 02.102-Ack. Eigene Unread- oder private Bookmarknavigation bleibt unter ihren getrennten Rechten.
- **02.109 Moderation:** Normale Kampagnen-Suche ist keine universelle Moderations-/Fallrecherche in fremden DMs; ein ausdrücklich berechtigtes, fallgebundenes Evidence-Lookup ist ein anderer enger und protokollierter 02.109-Pfad. Kein Chatmoderator erhält allein durch Such-Adminfähigkeit Zugriff auf alte geschützte Chatinhalte.
- **02.111 Erwähnungen/02.112 Reaktionen:** Erwähnte Accounts/Teams und Reactionautoren dürfen nur bei wirklich separaten Rechten als Filteroption auftauchen. Die Suche selbst pingt **niemanden** und erzeugt keine Welt-/Systemaktion.
- **Missbrauchsgrenzen:** Mindestlängen/Querykosten, Timeout/Rate-/Parallelitäts-/Ergebnis-/Exportlimit, stabile Pagingversionen, Schutz gegen aufwendige Wildcards/Regex/Enumeration sowie eingangsvalidierte Querysyntax konzipieren. User-Input bleibt untrusted; weder SQL-/Suchparser-Injektion, HTML-Snippet-Ausführung, ReDoS noch Dateipfad-/Node-/Weltbefehle zulassen. Konkrete Suchoperatoren und Zahlen erst nach Abschluss des Featureworkshops.
- **Sicht nur an der richtigen Stelle:** Cache-Keys und Index-/Suchantworten nach tatsächlichem Account/Kampagne/Kanal-/ACL-/Policy-/Retentionversionsbezug trennen. Keine versehentliche Veröffentlichung durch globalen Cache, Worker-Queue, Push, URL-Share, Audit-, Debug- oder Adminoberfläche. Zugriffe mit Session-/Policywechsel neu prüfen.
- **Technische Analyse ohne Verhaltensüberwachung:** Rechtmäßige minimale Betriebs-/Missbrauchsdaten können getrennt nach eigenem Audit-/Retentionrecht nötig sein; die C-Suchfunktion begründet **keinen** frei lesbaren persönlichen Suchverlauf, keine neue Anwesenheits-/Lesestatistik und kein Tracking-Feature.

## 6. Architektur und Umsetzungsplan – noch kein Code

**Fachliche Datenmodellkandidaten (keine finalen API-/Tabellenverträge):** `CampaignChatSearchPolicy`, `ChatSearchCapability`, `ChatSearchQueryScope`, `ChatSearchFilterExpression`, `ChatSearchIndexEntry`, `ChatSearchIndexRevision`, `ChatSearchAccessProjection`, `ChatSearchResultProjection`, `ChatSearchSnippetGuard`, `ChatSearchCursorVersion`, `ChatSearchRetentionJob`, `ChatSearchOperationId` und `ChatSearchRateBudget`. Wichtige Bezüge: echter Account/Kampagne, konkrete 02.106-Kanal-/Gruppen-/DM-/SL-ID, ursprünglicher 02.107-Message-/Recipient-/Access-Epoch-Snapshot, 02.108-Revision/Withdraw, 02.109-Fall-/Suppressionpolicy, 02.110-Filter, 02.113-Thread/02.114-Asset und aktuelle ACL-/Policy-/Index-/Retentionversion.

**Fachlicher Umsetzungsplan:**
1. **Einstellungen und Fähigkeiten:** 02.105-Chat-An/Off plus 02.25-Defaults/markierte Ausnahmen für Volltext, Kanäle, echte sichtbare Sender, Zeitraum, zulässige Typen, Thread und geschützte Medienfilter; nur unterstützte Modi anbieten, keine globalen Sicherheits-Overrides.
2. **Suchdatenquelle und Retention:** Für 02.107-persistierte Nachrichtentexte passende begrenzte Indexe/Filterquellen, korrekte 02.108-Revisions-/Edit-/Withdraw-/02.109-Moderation- und Aufbewahrungsinvalidierung; flüchtigen Modus niemals in eine dauerhafte Schattenhistory umwandeln.
3. **Serverseitige Query- und Trefferautorisierung:** Eingabe-/Kanal-/Filterberechtigung zuerst prüfen, dann jede Kandidaten-Message nach **heutiger UND historischer** 02.107-/02.108-Berechtigung filtern, **vor** snippet/count/aggregation/facet; Kanal-/Sender-/Thread-/Attachment-IDs nicht als Orakel behandeln.
4. **Individuelle Projektionen:** Gesicherte Treffertexte/Highlights/Navigationslinks/Counts, eigens berechtigte Media-/Thread-Felder, Search Export und Cursor-/Reconnect-/Cache-/Realtimepfade; alle erneut prüfen, falls Rechte zwischen Query und Anzeige/Navigieren geändert werden.
5. **Missbrauch und Systemtrennung:** Query-Raten, teure Suchen, Injektionen, Limitierungen, blockierte persönliche Ping-Bypässe, 02.116-A-Receipt-Ausschluss und echte amtliche 02.101–02.103-/02.109-Pfade abgrenzen.
6. **Abnahmetests und spätere UI:** Testfälle unten, relevante Policywechsel-/Multi-Device-/Race-/Backup-/Expiry-/Index-Rebuild-Matrizen vorbereiten; exakte Operatoren, Filterlayout, Performanceziele, Standard-On/Off und MVP-Reihenfolge erst nach vollständigem Gesamtworkshop festlegen.

## 7. Fachliche Abnahmetests

| Fall | Erwartetes Ergebnis |
| --- | --- |
| `Chat Aus` bei Kampagnenerstellung | Keine neue normale Chatsuchein-/Facet-/Search-/Export-/Autocomplete-Operation; Notizen, Würfel, Welt und rechtmäßige amtliche Notices bleiben |
| Chat An, Volltext Aus, Kanalsuche/Zeitraum erlaubt | Nur wirklich freigegebene Filter funktionieren; `Volltext` ist trotz Clientmanipulation gesperrt |
| A sucht `Generator` in historisch eigener gespeicherter Teamnachricht | Treffer und korrekt autorisierter Snippet nur bei **heutiger UND ursprünglicher historischer** Empfängerberechtigung |
| C wird nach Nachricht ins Team aufgenommen | Alter Teamtext, Ergebniszahl und Suchvorschläge bleiben für C unsichtbar |
| A verliert heutiges Team-/Kanal-/Quellrecht | Früher sichtbare Texte fehlen nun in Search/Count/Export/Navigate/Reconnect trotz früherer Mitgliedschaft |
| Spieler errät fremde DM-ID, Sender-ID oder verborgenen Kanal | Kein Text, kein Filterfacet, kein Autocomplete-/Count-/Timing-Existenzorakel |
| A ist SL ohne konkretes privates DM-Leserecht | Keine automatische Suche aller Spieler-DMs aufgrund der SL-Rolle |
| Suchergebnisse enthalten 02.108-bearbeitete Nachricht | Nur berechtigte sichtbare aktuelle Revision, keine verlorene alte Originalfassung über Highlight oder Indexcache |
| Nachricht wird 02.108-zurückgezogen oder 02.109-entfernt | Normale Suche/Facet/Snippet/Export/Count liefert weder Original noch geheimen Status |
| 02.107-Retention endet zwischen Query und Navigation | Navigieren/Download und erneute Suche werden verweigert, keine alte Fassung aus Pager-/Index-/Cache |
| 02.107-flüchtiger Chat nach Restart | Keine versprochene wiederabrufbare alte Volltext-/Index-Historie |
| 02.110-Kanal ist persönlich stumm | Berechtigter alter Text kann bewusst gesucht werden, kein automatischer Ping/Read-Receipt |
| A blockiert B für neue DMs; eigene alte B-DM war historisch berechtigt | Keine neue Zustellung/Blocklisteninfo, frühere nach Policy lesbare History wird nicht automatisch physisch gelöscht oder willkürlich unlesbar |
| Suchtreffer verweist auf 02.113-Thread | Nur eigenständig sichtbare Parent-/Root-/Childtexte, keine private fremde Parent-Zitatvorschau |
| Suche nach Nachrichten `mit Bild` | Treffer/Dateiname/Thumbnail nur gemäß 02.114-Message-/Asset-/Downloadrechten, keine fremden geheimen Medien |
| 02.114-Datei als PDF mit enthaltenem Geheimtext | Kein automatisches Volltext-Extrahieren fremder PDF-/OCR-Texte als neues implizites Feature |
| Eigene 02.115-Bookmarks und fremde Bookmarks | Eigene legal sichtbare Merkliste ggf. eigener Filter; fremde private Bookmarkliste bleibt geheim |
| 02.111 erwähnt Geheimgruppe; 02.112 reagiert heimlich | Kein `@Gruppe`-/Reaction-Actor-/Empfängerlisten-Orakel durch Suchfacets |
| B sucht/öffnet eine alte Nachricht | **02.116 A:** A bekommt keine individuelle `B hat gelesen/gesucht`-Bestätigung oder Read-Zeitstatistik |
| Suchtext enthält JavaScript/SQL-/Regex-/Node-Befehle | Keine Code-/Queryinjektion, ReDoS oder tatsächliche NPC-/Quest-/Tür-/Node-/Turnwirkung |
| Viele parallele Suchanfragen/Wildcards | Serverseitige Kosten-/Rate-/Paging-/Quota-Grenzen, keine unlimitierte Belastung |
| Berechtigter 02.101-Hinweis benötigt 02.102-Ack | Chat-Suche/Navigieren erzeugt nie diese echte amtliche persönliche Quittierung |
| Suche auf Tablet, Rechte wechseln während Offline/Queue | Beim Abruf/Navigation aktuelle Permission-/Message-/Retentionversion prüfen, keinen unberechtigten Cache zeigen |
| 02.109-Moderator benötigt fallgebundenen Beleg | Eigener enger autorisierter Moderationspfad statt öffentlicher normaler Chatsucheinträge |
| Chat-Aus-/Rollenswitch nach existierenden Indizes | Keine Freigabe oder unberechtigte Projektion, Retention/Datenschutz bei gültigen geschützten Beständen bleibt |

## 8. Beschlussgrenze und nächste Featurefrage

**Verbindlich beschlossen: 02.117 C.** Konfigurierbare berechtigte Chat-Suche und Filterarten bei 02.105 Chat An nach 02.25-Defaults/markierten Ausnahmen. Jede Antwort inklusive Treffertext, Ausschnitt, Counts, Facets, Suchvorschlägen, Navigationslinks, Thumbnails, Exports und Indexcaches ist nach **heutigen UND historischen** 02.106-/02.107-/02.108-Nachrichten-/Recipient-/Secret-/Retentionrechten zu schützen. 02.109-Moderation, 02.110-Mutes/DM-Blocks, 02.111–02.115-Chatfunktionen und **02.116 A ohne individuelle Lesebestätigungen** bleiben bindend. Kein automatisches Transkript-, Übersetzungs-, Datei-OCR-, Welt-/System-/Notice-/Ack-Feature.

**Nicht beschlossen:** Konkrete Suchsyntax/Operatoren, Indextechnologie, Querylimits, Volltext in PDF/Bild/Voice, Search-Abo, gespeicherte Suchen, finale Suchoberfläche/MVP-Umsetzung oder Datenbank-API. Wie die meisten geeigneten Komfortmodule ist Suchfunktion an-/abschaltbar; Auth-/Secret-/Retentionchecks nie.

## Nächste Entscheidung 02.118 – Private Chat-Entwürfe und sicheres Offline-Verfassen

**Beispiel:** Ein Spieler formuliert eine längere Chatnachricht, bevor der Browser geschlossen oder die Verbindung verloren wird. Er möchte den noch nicht gesendeten Text eventuell auf einem zweiten Gerät wiederfinden. Dabei darf ein Entwurf nicht automatisch versendet werden, wenn die Gruppe gewechselt oder der Kanal inzwischen gesperrt ist.

- **A – Keine gespeicherten Entwürfe:** Ungesendeter Text bleibt höchstens solange im aktuellen Eingabefeld vorhanden; keine persistente Wiederherstellung.
- **B – Ungeschützte Auto-Sends:** Entwürfe auf jedem Gerät und in jedem Kanal ohne aktuelle Auth-/Kanal-/Block-/Policyprüfung speichern und bei Reconnect automatisch senden, selbst wenn der Empfänger gewechselt oder Chat Aus ist.
- **C – Konfigurierbare private Entwürfe mit erneuter Sendefreigabe (Empfehlung):** Bei 02.105 Chat An und gültiger 02.25-Policy nur **eigene private** Entwürfe für berechtigte Kanäle lokal oder ggf. geschützt kontogebunden speichern, mit Retention-/Mehrgeräte-/Widerrufsschutz. Offline-Verfassen erlaubt, aber **kein automatisches Senden allein durch Reconnect**; beim ausdrücklichen Senden heutige 02.106-/02.109-/02.110-/02.111–02.117-Rechte, echte Empfänger-/Gruppen-/Attachment-/Quote-/Mention-Kontexte serverseitig neu prüfen. Eigene Entwürfe sind keine Chatverlaufseinträge und erzeugen keine Welt-/Ack-Wirkung. Konkrete UI/Speicherfristen später.
