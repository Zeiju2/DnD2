# AdventureShift – Karten-Workshop: Beschluss 02.125 A – kein zusätzlicher Chatverlauf-Export oder Druckmodus

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.125; nächste offene Frage 02.126
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungs- und Testplan; **noch keine Softwareimplementierung**, finale APIs, Datenbanktabellen, UI oder MVP-Einstufung.
**Bezüge:** [02.25 – Kampagnenstandards und markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – private/gezielt geteilte Spielernotizen](KARTEN-WORKSHOP-02.98.md) · [02.101–02.104 – amtliche Notices und bewusste ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106 – Chatbereiche/Empfängerrechte](KARTEN-WORKSHOP-02.106.md) · [02.107 – Historie/Retention/heutige UND historische Rechte](KARTEN-WORKSHOP-02.107.md) · [02.108 – Edits/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Moderation/fallbezogene Belege](KARTEN-WORKSHOP-02.109.md) · [02.110 – persönliche Mutes/DM-Senderblock](KARTEN-WORKSHOP-02.110.md) · [02.111 – Mentions/Pings](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen/Emotes](KARTEN-WORKSHOP-02.112.md) · [02.113 – Antworten/Zitate/Threads](KARTEN-WORKSHOP-02.113.md) · [02.114 – sichere Anhänge/Downloads/Links](KARTEN-WORKSHOP-02.114.md) · [02.115 – Pins/private Lesezeichen](KARTEN-WORKSHOP-02.115.md) · [02.116 A – keine Chat-Lesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.117 – berechtigte Suche/Filter](KARTEN-WORKSHOP-02.117.md) · [02.118 A – keine gespeicherten Chatentwürfe](KARTEN-WORKSHOP-02.118.md) · [02.119 – flüchtige Präsenz/Typing](KARTEN-WORKSHOP-02.119.md) · [02.120 – Chat-Umfragen](KARTEN-WORKSHOP-02.120.md) · [02.121 A – mehrzeiliger Klartext](KARTEN-WORKSHOP-02.121.md) · [02.122 A – keine Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.123 A – keine Weiterleitung](KARTEN-WORKSHOP-02.123.md) · [02.124 A – keine Chatübersetzung](KARTEN-WORKSHOP-02.124.md) · [Kommunikationsworkshop 11](FEATURE-WORKSHOP.md).

## 1. Verbindlicher Beschluss – Variante 02.125 A

**Der Projektinhaber wählt A: AdventureShift erhält keine zusätzliche integrierte Download-, Export- oder Druckfunktion für gewöhnliche Chatverläufe.** Ein Spieler und auch die Spielleitung finden im optionalen 02.105-Textchat **keinen** Befehl `Chatverlauf exportieren`, `Konversation herunterladen`, `Nachrichten als Text/CSV/HTML/JSON/PDF sichern` oder `Chat drucken`. Ebenso werden **keine** gespeicherten persönlichen Massenauszüge, „Transcript erzeugen“-Jobs, Chat-Archivzip-Dateien oder Batch-Medienarchive als Komfortfunktion vorgesehen.

**Wichtige positive Grenze:** Berechtigtes Lesen/Scrollen nach 02.107, die nach 02.117 C erlaubte **geschützte Volltextsuche/Filterung**, 02.115 private Lesezeichen/Kanalpins, 02.108-Versionierung, 02.109-Moderation und tatsächlich nach 02.114 gesondert berechtigte **einzelne Anhänge/Downloads** bleiben unverändert. Der normale Chatinhalt verschwindet durch diesen Beschluss nicht; allein die **gesonderte bequem ausgelöste Chatverlaufsausgabe in Dateien oder eine spezielle Druckansicht** entfällt.

**Unabhängige, eng berechtigte Datenpflichten und Administration bleiben:** Technisch nötige Backups/Restore, Datenschutz-Auskunft bzw. -Datenbereitstellung, gesetzlich oder fachlich legitimierte getrennte Datenwege sowie **02.109 fallgebundene minimale Moderationsbelege** dürfen nach ihren **eigenen** eng definierten Rollen-/Zweck-/Secret-/Retention-/Rechtsregeln behandelt werden. Sie sind **keine** Spieler-/SL-Komfortexportfunktion, kein automatischer allgemeiner „Alle DMs herunterladen“-Zugang und kein Schlupfloch für 02.125 A. Konkrete gesetzliche Anforderungen werden später im passenden Datenschutz-/Hostingworkshop geprüft, nicht vorweg festgelegt.

**Nicht gewählt:** B (universell alle privaten/geheimen Inhalte exportieren) und C (konfigurierbarer Spieler-/SL-Komfortexport). Die bei 02.25 üblichen Kampagnen-/Kanal-/Rollen-Defaults und markierten Ausnahmen **dürfen das hier bewusst ausgeschlossene Export-/Druckkomfortmodul nicht als versteckten Schalter zurückbringen**.

## 2. Abgrenzung zu Browserfunktionen und den bisherigen Export-Verweisen

| Bereich | Verbindliches Verhalten | Grenze |
| --- | --- | --- |
| **Chat-Verlauf lesen** | Tatsächlich heute UND historisch berechtigte Nachrichten nach 02.107 ansehen und, sofern vorhanden, im Verlauf navigieren | Keine automatische Massenausgabe oder Schattenhistorie |
| **02.117 Suche/Filter** | Berechtigte Volltext-/Channel-/Zeit-/Sender-/Medien-/Threadfilter und gesicherte Trefferanzeigen bleiben | **Kein** allgemeiner `Export search results`-/CSV-/Druckbutton – bisherige konditionale Exportideen in 02.117 werden durch 02.125 A **nicht freigeschaltet** |
| **02.114 Anhang herunterladen** | Nur ein einzeln wirklich berechtigtes Original/Thumbnail/zulässiger Dateidownload nach Message-/Dateirechten | Einzeldateidownload ist kein Chat-History-Bulk-Export, kein stilles ZIP aller Dateien |
| **02.115 Pins/Bookmarks** | Quellgebundene Kanalpins und eigene private Bookmarks als Navigation weiter möglich | Keine `alle gepinnten/gebuchten Originaltexte als PDF/JSON exportieren`-Sonderfunktion |
| **02.120 Polls** | Berechtigt sichtbare Pollfrage/Optionen/Tallies bei gültiger 02.120-Ergebnis-ACL | Kein Umfrage-/Stimmen-/Teilnehmer-Bulkexport über Chatverlauf-Auswahl |
| **02.113 Replies/Quotes** | Gesondert geschützte Parent-/Threadvorschauen und Quellenbezüge im erlaubten Kanal | Kein `Thread als Transkript/Printable Conversation`-Feature |
| **02.123 A Weiterleitung** | Ein Spieler darf selbst berechtigt neue Texte schreiben, ohne Forward-API | Export darf nicht als verbotener offizieller Crosspost-/Privat-DM-Repost verkleidet werden |
| **02.94 Spielernotizen** | Eigenes echtes freies Notizbuch nach separater Notiz-/Teilpolicy | Nicht automatisch aus Chatverläufen befüllen, nicht durch 02.125 A deaktivieren |
| **Administrative Backups/Datenschutzfälle** | Eigene enge System-/Betroffenen-/Wiederherstellungs- und 02.109-Evidence-Workflows bleiben planbar | Keine generelle SL-DM-Ausleseberechtigung, keine freie Kampagnen-Komfortausgabe |
| **Browser/OS-Kopieren/Drucken** | Normales Markieren, Copy/Paste, Screenshots und Browser-`Drucken` können außerhalb einer neuen AdventureShift-Exportfunktion existieren | Die App darf nicht behaupten, sämtliche vom OS/Browser angebotene Kopier-/Druckwege technisch verhindern zu können; keine eigene spezielle `Chat drucken`-Oberfläche |
| **Seiten-/App-UI-Lokalisierung** | 02.124 A verbietet nur Chatübersetzung und nicht andere UI-Anzeigen | Keine automatisch übersetzte oder neu formatierte Exportfassung |

**Wesentliche Klarstellung zu den älteren Beschlüssen:** 02.107 und 02.117 behandeln Export als **gesondert geschützten Ausgabepfad beziehungsweise als allenfalls später ausdrücklich freizuschaltende Möglichkeit**. 02.125 A trifft nun gerade die ausdrückliche **negative Produktentscheidung** gegen einen **gewöhnlichen benutzerseitigen Chat-/Suchresultatexport und eine Chat-Druckfunktion**. Wo ältere Architekturentwürfe `exportSearchResults`/`Export` als konditionale Möglichkeit nennen, gilt ab jetzt **02.125 A als fachlich vorrangiger Ausschluss dieses Komfortwegs**. Das Erfordernis, **alle tatsächlich vorhandenen administrativen/Ausgabewege ACL- und Retention-sicher zu halten**, bleibt davon unberührt.

## 3. Sicherheit, Retention und Datenprivatsphäre

1. **02.105 Chat An/Aus:** Bei Chat Aus keine regulären Verlaufs-/Such-/Export-Abfragen. Bei Chat An nur tatsächlich berechtigter Verlauf und 02.117-Suche, **kein** Export-/Druck-Menü. Offizielle 02.101–02.104-Systemnotice-/ACK- und Würfel-/Worldmodule bleiben eigenständig.
2. **02.106 Kanäle, 02.107 ursprüngliche Empfänger:** Der echte 02.107-Nachrichtentext, Autor, Kanal, Dateiinformationen und Chatmessage-/Revisionsverlauf dürfen jeweils nur bei **heute UND historisch** zutreffender individueller Quell-/Empfänger-/Fog-/Secret-/NPC-/Quest-/Notiz-/Wurf-/Retentionberechtigung angezeigt werden. Auch eigene Datenauskunft/Backup/Moderationsbelege bekommen nicht pauschal mehr Rechte allein durch ein SL- oder Adminlabel.
3. **02.108/02.109 Edits/Withdraw/Moderation:** Nachrichtenversionen und fallbezogene Moderationsbelege unterliegen weiterhin ihrem eigenständigen berechtigten Lebenszyklus. Es entstehen keine unbegrenzt wiederlesbaren Chatdruck-Spooler, CSV-/PDF-/ZIP-Snapshots oder alte Quelltextkopien im Namen eines nicht vorhandenen Exports.
4. **02.110 Mute/Block:** Persoenliche Kanalstummschaltung kann berechtigtes manuelles Lesen zulassen, echte DM-Kontaktblocks verhindern neue unerlaubte Zustellung. Keine `Ich brauche Export für blockierten Kontakt`-Bypassfunktion und keine Blocklisten-/Privatnachrichten-Metadaten in Auskunftsfehlern.
5. **02.111–02.120:** Mentions/Pings, Reaktionen/Emotes, Replies/Threads, Dateien/Thumbnails/Previews, Pins/Bookmarks, geschützte Suche/Filter, flüchtige Präsenz, berechtigte Polls und gesonderte Moderation bleiben **eigene** Rechte- und Anzeigeobjekte. `Download alle Chatbilder` oder `alle Poll-Teilnehmer drucken` darf den ausgeschlossenen Bulk-Transcriptweg nicht als Erweiterung verpacken.
6. **02.116 A und 02.118 A:** Weder lesen/suchen noch Drucken über ein Betriebssystem darf AdventureShift veranlassen, **individuelle Chat-Delivery-/Read-Receipts** oder **ungesendete gespeicherte Draftkopien** zu erzeugen.
7. **02.121/02.122/02.123/02.124 A:** Klartext mit Absätzen bleibt lesbar, keine Rich-/Spoiler-Ausgabe, kein Voice-Memo-/Transkriptarchiv, kein offizielles Forwarding und keine Translate-Copy. Eine administrative tatsächlich zulässige Datenbereitstellung erzeugt daraus keine zusätzlichen allgemein sichtbaren Chatfeatures.
8. **Menschen-/Browsergrenze:** Ein berechtigter Nutzer kann vom Bildschirm sichtbare Texte abschreiben, manuell kopieren, einen Screenshot anfertigen oder die Browser-Druckfunktion verwenden. 02.125 A **verbietet nur das neue plattformeigene Komfortexport-/Druckfeature**, nicht diese unabhängig bestehenden Möglichkeiten. Nicht versprechen, nachträglich bereits menschlich kopierte private Informationen „zurückzuholen“.

**Datenschutz-/Hostingentscheidung später:** Art, Rechtsgrund, Berechtigung und technische Sicherung gesetzlich/vertraglich verpflichtender Betroffenenauskunft, Administrations-/Backupverfahren und legaler Exportpfade müssen in Bereich 14 separat dokumentiert werden. 02.125 A darf sie nicht versehentlich verhindern, aber auch nicht zu einem pauschalen allsehenden SL-Downloadweg umdeuten.

## 4. Negativer Architekturentscheid und Umsetzung

**Nicht als normales Chatfeature planen:** `ChatHistoryExportRequest`, `ChatHistoryExportJob`, `ChatPrintableTranscript`, `ChatTranscriptDownload`, `ChatPDFTranscript`, `ChatArchiveZIP`, `ChatConversationCSV`, `ChatBulkAttachmentExport`, `canExportChatHistory` oder `canPrintChatHistory` mit zugehöriger Download-/Background-/Push-/WebSocket-/API-/UI-Komfortfunktion. Auch die zuvor unter 02.117 **nur bedingt vorgesehene** `exportSearchResults`-Option **nicht** als normale Spieler-/SL-Exportcapability implementieren. Kein 02.25-/Kanal-/Rollen-/Personentoggle, der diese verbotenen Komfortfeatures heimlich einschaltet.

**Getrennte tatsächlich erforderliche Datenwege:** `02.109 ModerationEvidence`, berechtigte datenschutzbezogene Auskunft, eng zweckgebundene Systemlogs und gesicherte 14-Backups/Restore können fachlich eigene unabhängige Modelle/Operations haben. Jeder dieser Pfade benötigt explizite authentifizierte Zweck-/Betroffenen-/Rollen-/Kanal-/Quell-/Recipient-/Retention-/Revisions-/Secretprüfung und minimale Ausgabe; **niemals** allein das „SL darf alle DMs herunterladen“ als Abkürzung. Solche Prozesse dürfen **nicht** als normale Chat-/History-/Search-Massenexportknöpfe angeboten werden. Endgültige Verfahrens-/API-/Fristdetails bleiben offen.

**Umsetzungsplan nach Abschluss des Workshops:**
1. **Featurekatalog bereinigen:** 02.125 A als ausdrücklichen Nicht-Funktionsbeschluss eintragen, frühere konditionale `Export/SearchResult`-Komfortangaben in 02.107/02.117 unter diesen Ausschluss stellen. 02.25-Settingsinventar bietet keinen Komfortexport-/Printschalter.
2. **Chat-/Search-UI-Grenzen:** Keine `Drucken/Herunterladen`-Aktion an Kanal, Verlauf, Suche, Thread, Poll, Pin oder Bookmark; keine automatisch generierte Chatdruckansicht, kein ZIP/TXT/CSV/JSON/PDF-Transkriptendpunkt. 02.114-einzelner erlaubter Datei-Download bleibt gesondert verfügbar.
3. **Berechtigungen unverändert:** Echte 02.106-Channel-/DM- und **02.107-aktuelle UND historische** Empfänger-/Quell-/Retentionprüfung für jede Text-, Such-, Quote-, Datei-, Reconnect- und individuelle ggf. administrativ berechtigte Projektion.
4. **Geschützte Eigenzweckoperationen:** Gesonderte fallgebundene 02.109-Moderationsbelege, datenschutzrechtlich legitime Auskünfte sowie technische Backups/Restore nach eigenen Kontrollen, ohne unautorisierte Spieler-/SL-Massenexports. Echte Zugriffsaudits minimal und zweckbezogen; keine Schattenhistory.
5. **Negativ- und Sicherheitsabnahme:** Manuell prüfbare Testmatrix unten einschließlich ID-Enumeration, veralteter Rollen, blockierter DMs, flüchtiger Retention, Search-/Poll-/Mediendownloadgrenzen, Browser-/OS-Druck-Unkontrollierbarkeit und No-World-/ACK-Effect.
6. **UI/Architektur-MVP später:** Keine konkrete Standarddruckmaske, PDF-Engine, Exportdateiformate oder zusätzliche Exportstatistiken ohne neuen Fachbeschluss planen.

## 5. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| SL erstellt Kampagne mit 02.105 Chat An | Berechtigte Chatverläufe verfügbar, **keine** komfortable Chat-Export-/Drucken-Schaltfläche |
| 02.105 Chat Aus | Kein gewöhnlicher neuer Chat-/Search-/Exportpfad; unabhängige Notizen, Würfel-/Systemfeeds und offizielle Notices bleiben |
| Spieler kann eigenen gespeicherten Gruppenchat heute und historisch lesen | Normale 02.107-History und 02.117-Suche funktionieren, ohne TXT-/PDF-/CSV-Massendownload |
| Spieler nutzt 02.117 erlaubte Suchfilter | Treffer/Navigation nur nach Rechten; **kein** `Exportiere Treffer`-Bulkbutton trotz früher bedingter Konzeptoption |
| SL sieht eigenen berechtigten Chat | SL hat **nicht** automatisch Komfortexport für alle anderen geheimen DMs |
| Neuer Teamspieler tritt später bei | Keine alten privaten DM-/Gruppen-/Secretmessages via Export-/Druck-API, auch keine Counts |
| Ehemaliger Chatempfänger verliert heutiges Kanalrecht | Kein unerlaubter Verlaufs-/Search-/Resultzugriff und erst recht kein Export von alten Texten |
| Spieler errät eine geheime DM-/Message-ID und ruft Export-URL auf | Kein Chat-Transcript-Endpunkt/Existenzorakel, keine Rückgabe geheimer Inhalte |
| 02.108 alte Revision entzogen/withdrawn | Kein Abholen einer alten Version via PDF-/CSV-/Druck-Schattenkopie |
| 02.109 Moderator besitzt nur fallbezogenen Belegzugriff | Nur ausdrücklich legitimer Minimalbeleg, kein allgemeines „Exportiere alle DMs“-Feature |
| 02.107 Chatverlauf flüchtig/nach Retention abgelaufen | Kein unabhängig persistenter Chatdruck-/Exportsnapshot oder neu erzeugte Chat-Historie |
| 02.114 erlaubtes Einzelbild wird heruntergeladen | Weiter nach gesonderten Medien-/Message-/Empfängerrechten möglich, **kein** kompletter Chat-Bulkdownload |
| 02.114-Medien in geheimer DM | Keine Datei-/Thumbnail-/Link-/Count-Offenlegung über fremdes Transkript |
| 02.115 persönliche Bookmarks/Kanalpins | Nur regulär zulässige Quellnavigation, keine Sammlung aller privaten Bookmarktexte als Datei |
| 02.120 Poll in Teamchat hat geheime Stimmen | Kein gebündeltes Poll-/Voter-/Tallies-Transcript mit unberechtigten Namen |
| 02.113 berechtigter Thread ist geöffnet | Normale einzelne Reply-/Quoteansicht, keine `Thread als PDF herunterladen`-Option |
| 02.123 A keine Weiterleitung | Kein Chat-Transcript-Link oder Exportjob als offizieller Crosspost-/Forwarding-Bypass |
| Spieler markiert eigenen berechtigt sichtbaren Text und nutzt Browser-Drucken | AdventureShift verspricht keine Kontrolle über alle OS-/Browserfunktionen; keine eigene Sonderdruckoberfläche |
| SL fordert legitimes gesichertes Serverbackup an | Getrennter wirklich berechtigter Administrations-/Restorepfad, kein normaler Komfortexport und kein SL-Allzugriff auf DMs |
| Berechtigte persönliche Datenauskunft wird separat gefordert | Eigenständige datenschutzgerechte Prüfung/Erfüllung bleibt möglich, nicht über Spieler-Chatbutton |
| 02.116 A verbietet individuelle Lesebestätigungen | Suche und andere Ausgaben erzeugen keine personenbezogenen Read-/Delivery-Receipts |
| 02.118 A verbietet gespeicherte Entwürfe | Kein „Export Drafts“-/Offline-Outbox-Umweg |
| 02.121 A Klartext mit Absätzen | Normales zulässiges Chatlesen bleibt mit Zeilen-/Absatzstruktur erhalten; keine neue Rich-PDF-Aufbereitung |
| 02.122 A/02.124 A schließen Voice-Memo/Chattranslation aus | Kein Audio-Transkript- oder automatisch übersetzter Chatdownload als Umweg |
| Absichtlich neuer berechtigter eigener Klartext im anderen Kanal | Gewöhnlicher `sendMessage`-Commit nach echtem Zielkanalrecht, nicht generierter Verlaufsexport |
| Chattext nennt `Tür öffnen`/`ACK` | Kein tatsächlicher 02.99-Welt-/02.102-ACK-Event durch Anzeige, Suche oder OS-Druck |
| Kampagnenadmin versucht `Export Chat An` im 02.25-Preset | Kein solcher Komfortfeature-Schalter trotz allgemeiner Modulkonfigurierbarkeit |

## 6. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.125 A – keine integrierte Spieler-/SL-Komfortfunktion für Chatverlauf-Export, Massendownload oder gesonderten Chatdruck.** Die vorher unter 02.107/02.117 erwähnten allenfalls bedingten Komfort-Exportmöglichkeiten sind **dadurch nicht freigeschaltet**, sondern für das normale Chatprodukt ausgeschlossen; reine **Berechtigungs-/Datenschutzkontrollen für tatsächlich vorhandene andersartige Datenwege** bleiben notwendig. 02.105-Chat An/Aus, 02.106-Kanäle, 02.107-heutige UND historische Empfängerrechte, Retention, 02.108–02.124 gelten unverändert. Berechtigte normale History, Suche, einzelne 02.114-Dateidownloads, berechtigt private Notizen und gesonderte rechtmäßige Backup-/Auskunfts-/Moderationsprozesse bleiben unabhängig. Kein 02.102-Ack und keine echte 02.99-Spielweltaktion durch den bloßen Chatinhalt.

**Nicht beschlossen:** Ein generelles Verbot manuellen Kopierens, von Screenshots oder Betriebssystem-/Browser-Druckfunktionen; eine Einschränkung der rechtmäßig geschuldeten personenbezogenen Auskunft, legitim fallgebundener Moderationsbeweise, Serverbackups und einzelner separat berechtigter Anhänge. Keine fertigen Datenexportformate, Fristen, Buttons, Verwaltungsverfahren oder sonstige Codeimplementation.

## Nächste Entscheidung 02.126 – Chat-Benachrichtigungen: Pop-ups, Töne und Desktop-Hinweise

**Beispiel:** Während ein Spieler die Karte betrachtet, kommt eine neue berechtigte Nachricht im Gruppenchat an. Einige Gruppen möchten einen dezenten Hinweis sehen, andere nur einen Badge oder gar keine zusätzlichen Benachrichtigungen. Persönlicher 02.110-Kanalmute und 02.111-Ping-/Block-Policy müssen Vorrang haben.

- **A – Keine zusätzlichen Chat-Pop-ups oder Töne:** Neue Nachrichten werden ausschließlich im berechtigten Chat und ggf. in schon eigenständig zulässigen passiven Unread-/Mentionansichten sichtbar; keine neue Desktop-/Ton-/Toastfunktion.
- **B – Unbegrenzte Chat-Hinweise:** Jede Nachricht löst ungefilterte Töne, Pop-ups und Desktop-Benachrichtigungen aus, auch aus fremden geheimen Gruppen, bei Mute/DM-Block oder wenn die App nicht berechtigt ist.
- **C – Konfigurierbare, geschützte Benachrichtigungen (Empfehlung):** Bei aktivem 02.105-Chat nach 02.25-Defaults und gültigen Kampagnen-/Channel-/Rollen-/Personenausnahmen optionale stille Badges, In-App-Hinweise, Sounds oder Browser-/Desktop-Notifications **je tatsächlich berechtigtem Empfänger**. 02.110-Mute-/DM-Senderblocks, 02.111-Mentionrechte, 02.107-aktuelle UND historische Message-ACL, Datenschutz bei Lock-Screen/Vorschautext und die 02.116-A-Regel ohne individuelle Lesebestätigungen bleiben. Externe OS-/Browser-Permission nur nach gesondertem Opt-in; keine automatische Spielwelt-/ACK-Wirkung. Konkretes UI später.
