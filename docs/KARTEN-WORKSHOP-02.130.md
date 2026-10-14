# AdventureShift – Karten-Workshop: Beschluss 02.130 C – berechtigte persönliche kanalübergreifende Chat-Sammelansicht

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.130; nächste offene Frage 02.131
**Status:** Verbindlicher Fachbeschluss, konzeptioneller Umsetzungs- und Abnahmetestplan; **noch keine Softwareimplementierung**, kein finales UI, keine API-/DB-Verträge oder MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnenstandards/markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – private Spielernotizen](KARTEN-WORKSHOP-02.98.md) · [02.99 – echte autorisierte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – offizielle Notices/ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106 – Channel-/DM-/Gruppen-/SL-Rechte](KARTEN-WORKSHOP-02.106.md) · [02.107 – heutige und historische Empfänger-/History-/Retentionrechte](KARTEN-WORKSHOP-02.107.md) · [02.108 – Edits/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – Mutes/DM-Blocks](KARTEN-WORKSHOP-02.110.md) · [02.111 – Pings](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen](KARTEN-WORKSHOP-02.112.md) · [02.113 – Replies/Threads](KARTEN-WORKSHOP-02.113.md) · [02.114 – Medien](KARTEN-WORKSHOP-02.114.md) · [02.115 – Pins/Bookmarks](KARTEN-WORKSHOP-02.115.md) · [02.116 A – keine individuellen Lese-/Zustellbestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.117 C – Suche/Filter](KARTEN-WORKSHOP-02.117.md) · [02.118 A – keine Draftspeicherung](KARTEN-WORKSHOP-02.118.md) · [02.120 C – Umfragen](KARTEN-WORKSHOP-02.120.md) · [02.121 A – absatztreuer Klartext](KARTEN-WORKSHOP-02.121.md) · [02.122–02.125 A – abgewählte Chat-Komfortmodule](KARTEN-WORKSHOP-02.125.md) · [02.126 C – Benachrichtigungen](KARTEN-WORKSHOP-02.126.md) · [02.127 A – kein Slowmode](KARTEN-WORKSHOP-02.127.md) · [02.128 A – kein persönliches Einzelmessage-Hide](KARTEN-WORKSHOP-02.128.md) · [02.129 C – persönliche Kanalorganisation](KARTEN-WORKSHOP-02.129.md).

## 1. Verbindliche Entscheidung – Variante 02.130 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Bei wirksamem **02.105 Chat An** kann die SL gemäß **02.25-Defaults und gültigen markierten Ausnahmen** eine **persönliche, kanalübergreifende Sammelansicht** aktivieren. Sie führt für die betrachtende Person ausschließlich die **heute UND historisch nach 02.106/02.107 tatsächlich erlaubten und noch verfügbaren** Nachrichten aus berechtigten Kampagnen-, Gruppen-, DM-/Mehrpersonen- und gegebenenfalls SL-bezogenen Kanälen zusammen. Nutzer dürfen innerhalb der freigegebenen Kanaltypen/Scopes ihre eigene Anzeigeauswahl und temporären Filter wählen. Jede Nachricht bleibt ihrem tatsächlichen Quellkanal zugeordnet.

**Beispiel:** Spielerin A ist heute Mitglied von „Kampagne“, „Späher“ und einer erlaubten DM mit B. Sie wählt in der Sammelansicht Kampagnen- und Spähernachrichten. A sieht nur wirklich ursprünglich an sie adressierte, aktuell noch erlaubte Inhalte; alte Spähernachrichten vor ihrem Gruppeneintritt werden nicht durch die gemeinsame Ansicht zugänglich. B und die SL behalten ihre eigenen Berechtigungen und getrennten persönlichen Ansichten.

**Nicht gewählt:** A (keine gemeinsame Ansicht) und B (unberechtigter kampagnenweiter Vollfeed auch aus fremden Gruppen, geheimen SL-Kanälen und DMs). **C ist kein „alle Kampagnennachrichten abrufen“-Recht**, keine neue Speicherkopie und kein separates Channelmitgliedschaftsmodell.

## 2. Konfiguration, persönlicher Umfang und Grundverhalten

1. **Harte Chat-Grenze:** Wenn der integrierte 02.105-Chat wirksam **Aus** ist, gibt es keine aktive Sammelansicht, keine daraus gestartete Chatabfrage und keinen Feed-Realtime-Subscriber. Unabhängige Spielwelt-/Würfel-/Systemereignisse, offizielle Notices/ACKs und eigene Notizen funktionieren gemäß ihren bestehenden Regeln weiter.
2. **02.25-Policy:** Zulässige Aktivierung pro Kampagne und für geeignete Kanaltypen, Gruppen, Rollen oder Personen gemäß begründeten markierten Ausnahmen; eine Ausnahme kann höchstens eine **Ansichtsfähigkeit**, niemals ein ansonsten verbotenes 02.106-/02.107-Leserecht gewähren. Wird die Fähigkeit entzogen, stoppen sämtliche neuen Feed-Abrufe/Pushes.
3. **Individuelle Anzeigeauswahl:** A kann aus **nur aktuell berechtigten** Kanaltypen/Channel-Referenzen wählen und die eigene Anzeige temporär eingrenzen. Es gibt keine globale SL-erzwungene Änderung fremder eigener Feedlisten allein durch persönliche Filter. Ob persönliche Filter-Defaults synchronisiert/gespeichert werden, ist später zu spezifizieren; keine neuen dauerhaften Textkopien oder fremden Teilnehmerlisten.
4. **Zusammenführen statt Kopieren:** Der Server erzeugt eine **pro Betrachter dynamisch autorisierte Projektion** der Originalnachrichten inklusive tatsächlicher erlaubter Kanalzuordnung, keine neue, neu adressierte Sammel-Message. Reihenfolge/Navigationsfenster können über sicheren Cursor oder Pagination bestimmt werden. Weder flüchtige Nachrichten noch abgelaufene History entstehen neu.
5. **Nur Lesen und Navigieren als Feed-Eigenschaft:** Gewöhnliche Channelantworten, Reaktionen, Dateiöffnungen, Umfrageaktionen oder Senden sind weiterhin nur durch **separaten aktuellen Quellkanal-/Message-Action-Guard** erlaubt. Die gemeinsame Ansicht hat **keinen „in alle Kanäle senden“-/Crosspost-/Weiterleitungsbefehl** (02.123 A). Normale Eingabe muss ein bestimmtes, autorisiertes Ziel haben.
6. **Abgrenzung zur Suche:** Anzeigeauswahl und einfache Feednavigation können Bestandteil von 02.130 sein, ohne dadurch unzulässige **02.117-C-Such-/Volltext-/Sender-/Medienfilter** zu erzwingen. Erweitertes kanalübergreifendes Suchen gibt es nur, soweit 02.117 mit eigener effektiver Policy eingeschaltet und pro Fundstelle autorisiert ist.
7. **Keine zusätzlichen Privilegien durch UI:** Die 02.129-C-Kanalfavoriten und Einklappbereiche können Navigationshilfen bleiben, geben der Sammelansicht aber keinen weiteren Empfängerscope. Das 02.128-A-Verbot des persönlichen Ausblendens einzelner regulär berechtigter Nachrichten bleibt; die private Auswahl von *Kanälen für eine Teilansicht* ist nicht Message-Hide-/Unhide.

## 3. Sicherheits- und Berechtigungsgrenzen

| Quelle/Feature | Unveränderliche Grenze für den Sammelfeed |
| --- | --- |
| **02.105 / 02.25** | Chat und Sammelfeedfähigkeit müssen aktuell aktiv sein; getrennte Kanal-/Rollen-/Personen-Ausnahmen sind **keine** generelle Quellfreigabe |
| **02.106** | Pro aktuellem Betrachter nur erlaubte Kampagnen, Kanäle, Gruppen, SL-Scopes, DMs und echte Kanal-/Sender-/Metaangaben; keine fremden Kanalnamen/IDs/Member |
| **02.107** | **Je einzelner Message** muss ursprüngliche historische Empfängerbindung **UND heutiges Kanal-/Quell-/Secret-/Fog-/Retentionrecht** passen; kein Backfill bei spätem Join oder späterer SL-Rolle |
| **02.108 / 02.109** | Nur tatsächlich zulässige aktuelle Revision/Withdraw-/Suppression-/Moderationsprojektion; keine alten Originale in Feed-/Zitat-/Thumbnail-/Cache-Snapshots |
| **02.110** | Kanal-Mute ändert eigene Notifications, nicht allein historische Leserechte. Echter DM-Senderblock verhindert unzulässige neue DMs; zuvor legitime Historie wird nicht pauschal vernichtet |
| **02.111 / 02.126** | Favorite, Feedöffnung oder Kanalaggregation lösen nicht automatisch Ping, Sound, Push oder doppelte Badges aus; Mute/QuietHours/Lockscreen-Privacy gelten weiter |
| **02.112–02.115 / 02.120** | Reaktionen, Thread-/Quote-Referenzen, Medien, Kanalpins, private Bookmarks und Poll-/Wählerdaten nur nach **je eigenem** Quell-, Objekt-, Versions- und Empfängerrecht |
| **02.116 A** | Kein individueller „wer hat welche Nachricht gelesen“-/Zustell-/Öffnungsstatus durch Feednavigation oder private Selektion |
| **02.117 C** | Suche und Filter bleiben getrennt schaltbar; keine Treffer-/Facet-/Autocomplete-/Count-/Excerpt-Leaks über ausgeblendete/ungültige Quellen |
| **02.118 A / 02.121 A** | Keine Draftspeicherung/Autosend und keine Rich-Text-/Markdown-/Spoiler-Funktion durch Feed; normale Nachrichten bleiben schlichter Absatztext |
| **02.122–02.125 A / 02.127 A** | Keine integrierten Voice-Memos, systemseitiges Forwarding, automatische Übersetzung, Komfortexport/-druck oder Gameplay-Slowmode; technischer Abuse-Schutz bleibt |
| **02.128 A / 02.129 C** | Feedfilter sind kein individuelles Message-Hide-Archiv; nur private Kanal-Favoriten/Sortierung, keine Fremdorganisation |
| **02.101–02.104 / 02.99** | Offizielle Systemkorrekturen und bewusstes ACK unabhängig; Sammelfeedtext erzeugt niemals echte NPC-/Quest-/Door-/Würfel-/Node-/Turn-/Inventaraktionen |

**Seitenkanal-Prinzip:** Der Server darf keine verbotene Kanalexistenz, geheimen Nachrichtentext, Nachrichtenzahl, Thread-Kindmenge, DM-Teilnehmer, verborgene Zeitreihe, Suchfacet, Sprungmarke oder Fehlermeldungsdifferenz über den Feed verraten. Globale Quell-IDs und interne Lücken in Cursor/Index sind keine für Clients ungefiltert auszugebenden Navigationseinträge.

## 4. Lebenszyklus, Reihenfolge, Reconnect und Grenzen

1. **Kontext pro Leser/Request:** Autorisierung vor jeder Batchabfrage und vor jeder Realtimezustellung; bei Deep Link, Pagination, Filterwechsel, Reaction, Attachment und Reply wird das jeweilige Ziel **erneut** geprüft. Nicht vertrauenswürdig: Client-Channel-IDs, Kanaltyp-Listen, alte Cursor, lokale Suchindizes, Cache-/Offline-Blobs.
2. **Chronologie:** Für berechtigte Quellen stabil nach tatsächlicher geeigneter Nachrichtenreihenfolge zusammenführen; Gleichstände deterministisch behandeln. Ein Client bekommt **keine** ungefilterten Rohpositionen, Nachrichtenzähler, Time-Gaps oder Token, aus denen versteckte Nachrichten/Kanäle ableitbar sind. Cursor an Viewer/Kampagne/Featurepolicy/ACL-/Querykontext binden und begrenzen.
3. **Änderung und Entzug:** Gruppenaustritt, Rollenwechsel, Widerruf geheimer Informationen, DM-/Kanaländerung, Retentionablauf, Edit/Withdraw und Moderation entziehen Inhalte **auch aus offenen Feed-/Realtime-/Search-/Cache-/Notificationansichten**. Spätere Berechtigung ersetzt keine fehlenden ursprünglichen Empfängerrechte.
4. **Flüchtige History:** Nur noch tatsächlich verfügbare 02.107-Nachrichten anzeigen; keine versprochene rückwirkende Speicherung. Ein Live-Feed kann vor Reconnect vorhandene, nicht mehr persistierte Nachrichten nicht neu laden.
5. **Mute/Block/Personalität:** Mute reduziert nach 02.110/02.126 Hinweise, nicht automatisiert die durch C erlaubte eigene History. Ein optionaler persönlicher „stumme Kanäle nicht anzeigen“-Filter verändert ausschließlich die eigene vorübergehende Navigation. Private Block-/Favoritenlisten anderer dürfen aus Feedposition/Filtertreffer/Unread nicht erkennbar sein.
6. **Massenabruf und Multi-Device:** Grenze für Seitenlängen, Fan-in, Abfragen/Filter, Realtime-Backpressure, Indexzugriffe und DOS-/Abuseversuche; idempotentes Reconnect, kein doppelt gerendertes Messageevent. Ein Synchronisierungszustand darf nicht die ursprünglich erlaubte Retention/Quellzugriffe verlängern.
7. **Kampagnengrenzen:** Ein 02.130-Feed ist an den konkret autorisierten Kampagnenscope gebunden; andere Kampagnen, selbst beim selben Account, werden nicht heimlich mit eingemischt. Ob später eine übergreifende Kampagnen-Inbox erlaubt wird, ist **nicht beschlossen**.

## 5. Konzeptioneller Umsetzungsplan

1. **Feature- und Policyvertrag:** 02.130-Sammelfeed als optionales eigenes 02.25-Untermodul nur bei 02.105 Chat An; effektive Kampagnen-/Kanaltyp-/Gruppen-/Rollen-/Personenstandards und gültige markierte Ausnahmen prüfen. Keine Sicherheitsprüfung deaktivierbar.
2. **Berechtigte Quellmenge:** Eigene 02.106-Channel-/DM-/Group-/SL-ACL zuerst auflösbar machen, danach **je Message** 02.107-Originalrecipient, heutige Quell-/Fog-/Secret-/Retention-ACL und 02.108-/02.109-Version/Moderation prüfen. Nicht freigegebene Quellen nicht für Zähl-/Sortier-/Facet-Projektionen verwenden.
3. **Nur virtuelle Feedprojektion:** Konzeptionell `ChatAuthorizedAggregateView`, `ChatAggregateViewPolicy`, `ChatAggregateViewerFilter`, `ChatAggregatePageCursor` und `ChatAggregateRecipientProjection` als **unverbindliche** Namen. Keine eigene neue Nachrichten-/Media-/DM-Historytabelle oder Snapshot-Kopie; Quellnachrichten behalten Original-Channel-ID und Quelle.
4. **Sichere Pagination/Realtimelogik:** Geschützte Quellunion, deterministische sichtbare Reihenfolge, begrenzter vorab autorisierter Ausschnitt, viewer-/policygebundene Cursor, Cache-Invalidierung bei Rechten/Retention/Revisionen, Reconnect unter aktueller erneuter Prüfung. Keine verdeckten IDs, Zeit-/Message-Lücken oder falsche Counts als Leck.
5. **Getrennte Aktionen und Präferenzen:** Optionen zur Auswahl berechtigter Channeltypen/Channel-IDs nur für die eigene Ansicht; kein neues Senderrecht oder 02.123-Forward. Weiterführende 02.117-Suche, 02.113-Replies, 02.114-Medien, 02.120-Polls und 02.126-Benachrichtigungen gesondert validieren. Ob und wie eigene Filter gespeichert werden, später datenschutzgerecht entscheiden.
6. **Abnahme und offene Umsetzung:** ACL-/Historienscope-/Edit-/Moderation-/Mutation-/Mehrgeräte-/Mute-/Block-/Cursor-/Timing-/DM-/Search-/Privacy-/No-ACK-/No-World-Tests unten. UI-Auswahl, konkrete Indizes/DB-Typen, Persistenzregeln, Skalierungsgrenzen, Clientnavigation und MVP/Release nur im späteren Architektur-/UI-Workshop finalisieren.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| 02.105 Chat Aus von Beginn an | Keine Feed-/Realtime-Chatoperation; Würfel-/Systemfeed, offizielle Korrekturen, Spieler-Notizen unabhängig |
| Chat An, 02.130-Policy Aus | Gewöhnliche autorisierte einzelne Kanäle bleiben, **keine** Sammelansicht oder Feed-API |
| Chat An, C für bestimmte Kanaltypen freigegeben | Nur tatsächlich nach 02.106/02.107 berechtigte Nachrichten aus zulässigen Typen |
| A wählt zulässigen Gruppen- und Kampagnenkanal | Beide zusammen, jede Nachricht im eigenen richtigen Quellkanal verlinkbar |
| Später neu beigetretener Spieler | Kein Backfill historisch nicht ursprünglich adressierter Gruppenbeiträge |
| Ehemaliger Nutzer mit widerrufenem aktuellen Gruppenrecht | Kein alter Text, kein Gruppenname/Count/Preview trotz früherer persönlicher Filterauswahl |
| Neugewonnene SL-Rolle ohne private DM-Empfängerbindung | Keine automatisch hinzugekommenen fremden Spieler-DMs oder Texte |
| A errät geheimen Kanal-/DM-/Message-Identifier | Keine Unterscheidung durch Treffer, Count, Cursor, Errorcode oder Existenzschnipsel |
| A versucht alle Kampagnen-Channel-IDs manuell anzufordern | Server begrenzt auf aktuelle Autorisierung und effektive 02.25-Policy |
| B nutzt manipulierte Feedfilter als A | Kein Lesen/Schreiben As privater Kanal-/Filterwahl ohne legitimes Recht |
| Geheim- oder Fog-Recht eines Messages wird entzogen | Message und alle Caches/Previews/Realtime/Deep Links unmittelbar unzulässig |
| 02.108 Edit/Revisionswechsel | Nur die jetzt zulässige Fassung; kein alter Volltext im Feedindex |
| 02.108 Withdraw / 02.109 Moderationsentfernung | Geänderte/entfernte Quellen gemäß tatsächlicher Policy; keine alte Kopie im Sammelfeed |
| 02.107 History ist flüchtig/abgelaufen | Keine rekonstruierten alten Texte nach Reconnect/Restart |
| 02.110-A Kanalmute | Mute macht aufdringliche Feed-Notifications stumm, löscht nicht automatisch zulässigen Gruppenchat |
| 02.110 DM-Senderblock | Keine neue verbotene DM; vorher rechtmäßig lesbare History nur nach eigenen Originalrechten |
| 02.126 Ruhezeit/Lockscreen/OS-Permission | Kein zusätzlicher Push, kein geheimnisverratender OS-Text durch Feed |
| 02.111 Mention in anderem berechtigten Kanal | Ein normaler ggf. erlaubter Ping, keine zusätzliche Feed-Doppelbenachrichtigung |
| 02.116 A ohne persönliche Lesebestätigungen | Feed öffnen/scrollen setzt keinerlei Sender-Read-/Delivery-Receipt |
| 02.117-Suche für A deaktiviert | Feedansicht schaltet nicht unerlaubt Volltext-/Filter-/Querysuche frei |
| 02.113 Thread oder Zitat verweist auf geheimes Parent | Erlaubte sichtbare Kindnachricht, aber keine verbotenen Parent-/DM-/Historydetails |
| 02.114 Attachment-Thumbnail zu entzogener Nachricht | Kein Datei-/Miniatur-/Preview-/Linkzugriff über den Feed |
| 02.120 Poll im Channel | Ergebnisse und Wähler nur nach eigener 02.120-/02.107-Berechtigung |
| 02.115 privater Bookmark / 02.129 Kanalfavorit | Ändert keine Feed-Quellrechte, fremden Listen oder Nachrichtenzustände |
| 02.128 A Kein persönliches Message-Hide | Temporäre Channel-Filter sind keine gespeicherte versteckte Einzel-Message-History |
| 02.123 A Keine Weiterleitung | Kein Bulk-Forward/Crosspost aus dem Feed, Senden nur gezielt in erlaubtem Kanal |
| 02.125 A Kein Chat-Komfortexport | Keine „gesamte Sammelansicht exportieren/ausdrucken“-Sonderfunktion |
| Tausende Nachrichten, gleiche Timestamps, konkurrierende Änderungen | Stabile zulässige Reihenfolge/Pagination ohne Secret-Lücken- oder Duplicate-Leaks |
| Reconnect mit altem Cursor und alten Gruppenrechten | Neuer Server-ACL-/Policy-/Revisioncheck; kein Cache-Bypass |
| Mehrere Kampagnen desselben Accounts | Keine Vermischung fremder Kampagneninhalte |
| Text `/roll`, `Tür öffnen` oder `Quest erledigt` im Feed | Keine reale 02.99-Würfel-/Door-/Quest-/NPC-/Node-/Turn-/Inventarwirkung |
| Wichtige 02.101-Korrektur/02.102-ACK | Kein automatisches amtliches ACK durch Feednavigation; separates Notice-/ACK-System |

## 7. Beschlussgrenze und nächste Frage

**Verbindlich beschlossen: 02.130 C – optional schaltbare rein persönliche kanalübergreifende Sammelansicht ausschließlich der je Betrachter heute UND historisch nach 02.106-/02.107-Rechten wirklich zugänglichen Nachrichten.** Sie ist eine **virtuelle Lesesicht** auf Originalkanäle und muss 02.105 Chat An, 02.25 gültige markierte Ausnahmen, 02.108-/02.109-Nachrichtenstatus, 02.110-Mutes/Blocks, 02.116 A keine individuellen Read-/Delivery-Receipts, 02.117-C-Suchgrenzen, 02.118 A keine Drafts/Autosend, 02.123 A keine Weiterleitung, 02.125 A kein Chat-Komfortexport, 02.126-C-Notificationprivacy, 02.127 A kein spielerischer Slowmode, 02.128 A kein individuelles Message-Hide und 02.129-C-eigene Kanalorganisation unverändert einhalten. Die Sammelansicht verleiht weder neue Channel-/DM-/Historienrechte noch erzeugt sie echte Spielwelt- oder offizielle ACK-Aktionen.

**Nicht beschlossen:** finales UI, neue per Account dauerhafte Filter-/Favoriten-Historypflicht, endgültige Sortier-/Pagegrößen, Indizes/API-/DB-/Caching-Verträge, Chat-MVP, kanalübergreifende Kampagnen-Inbox oder Würfel-/Systemfeed-Verhalten. All das bleibt gesonderte Fach-/Implementierungsarbeit.

## Nächste Entscheidung 02.131 – Würfel- und Systemereignisse im Chat anzeigen

**Beispiel:** Eine Gruppe nutzt externen Voicechat. Der Würfelwurf wird unabhängig vom optionalen Textchat als echtes autorisiertes Spielereignis gespeichert bzw. angezeigt. Optional könnte eine Chatansicht auf den bereits freigegebenen Würfelwurf oder auf einen Systemhinweis **nur verweisen**, ohne neue Geheimnisse zu enthüllen oder bei „Chat Aus“ den Wurf zu verlieren.

- **A – Strikt getrennte Ansichten:** Würfe, Initiative, Systemereignisse und amtliche Notices erscheinen nur in ihren eigenständigen erlaubten Protokollen, niemals als zusätzliche Einträge in einer Chatkanal-/Sammelansicht.
- **B – Alles als ungefilterte Chatnachricht:** Jeder Würfel-/System-/SL-Geheimeintrag wird allen Chatteilnehmern als normalen Text gezeigt; bei Chat Aus gäbe es keinen eigenen Wurf-/Systemfeed mehr.
- **C – Konfigurierbare geschützte Anzeigeverknüpfung (Empfehlung):** Bei 02.105 Chat An kann die SL nach 02.25-Policy und gültigen Ausnahmen entscheiden, ob **nur jeweils tatsächlich berechtigte** Würfel-/Systemhinweise in dafür vorgesehenen Chatansichten als **reine read-only Referenzen auf Originalereignisse** erscheinen. Originalprotokoll, geheime Würfe, Quell-/Empfänger-/Fog-/Retentionrechte, 02.116-Receipt-Verbot und 02.102-Acks bleiben vollständig unabhängig; 02.105 Chat Aus sperrt niemals Würfeln oder amtliche Systemhinweise. Genaue Ereignistypen und UI später.
