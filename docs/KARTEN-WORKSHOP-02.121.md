# AdventureShift – Karten-Workshop: Beschluss 02.121 A – einfacher Chattext mit Absätzen, ohne Rich-Text oder Spoiler

**Stand:** 13.10.2026 – Fachbeschlüsse 02.1 bis 02.121; nächste offene Frage 02.122
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungsplan und Abnahmetests; **noch keine Softwareimplementierung**, keine finalen API-/Datenbank-/Editorverträge, konkreten Zeichen-/Zeilenlimits oder abschließende UI-/MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnenstandards und zulässige markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – separates Spielernotizbuch und wählbare Kampagnenmodule](KARTEN-WORKSHOP-02.98.md) · [02.101–02.104 – amtliche Notices und bewusste ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus bei Kampagnenerstellung](KARTEN-WORKSHOP-02.105.md) · [02.106 – Kanal-/Gruppen-/DM-/SL-Rechte](KARTEN-WORKSHOP-02.106.md) · [02.107 – Historie, aktuelle UND historische Empfängerrechte, Retention](KARTEN-WORKSHOP-02.107.md) · [02.108 – Edits/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Meldung/Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – persönliche Mutes/DM-Blocks](KARTEN-WORKSHOP-02.110.md) · [02.111 – Mentions/Pings](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen/Emotes](KARTEN-WORKSHOP-02.112.md) · [02.113 – Replies/Threads](KARTEN-WORKSHOP-02.113.md) · [02.114 – Anhänge/Textlinks/Previews](KARTEN-WORKSHOP-02.114.md) · [02.115 – Kanalpins/Bookmarks](KARTEN-WORKSHOP-02.115.md) · [02.116 A – keine Lesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.117 – Chat-Suche/Filter](KARTEN-WORKSHOP-02.117.md) · [02.118 A – keine gespeicherten Entwürfe](KARTEN-WORKSHOP-02.118.md) · [02.119 – flüchtige Präsenz/Typing](KARTEN-WORKSHOP-02.119.md) · [02.120 – Umfragen](KARTEN-WORKSHOP-02.120.md) · [Kommunikationsworkshop 11](FEATURE-WORKSHOP.md).

## 1. Verbindliche Entscheidung – Variante 02.121 A mit ausdrücklicher Ergänzung

**Der Projektinhaber wählt ausdrücklich 02.121 A und ergänzt: „Absätze ja, aber nichts Ausgefallenes.“** AdventureShift plant im integrierten 02.105-Chat **gewöhnlichen, mehrzeiligen Klartext**. Spieler können **Absätze, einzelne Zeilenumbrüche und Leerzeilen** eingeben, versenden, nach tatsächlich geltenden Rechten empfangen und bei erlaubter 02.108-Bearbeitung wieder ändern. Die sichtbare Textgliederung darf beim Übertragen und Anzeigen **nicht zu einem einzigen unlesbaren Fließtext zusammenfallen**.

**Keine Rich-Text-/Markdown-/Spoilerfunktion:** Keine besondere Fett-/Kursiv-/Unterstreichen-/Schriftfarbe-/Größe-/Überschrift-/Liste-/Codeblock-Formatierung, kein HTML-Editor, keine Markdown-Interpretation, kein Spoiler- oder `erst nach Klick zeigen`-Text. Eine Zeichenfolge wie `**wichtig**`, `_leise_`, `# Überschrift`, `- erster Punkt`, `> Geheimhinweis` oder `<b>Text</b>` ist, soweit zulässig, **normaler Text mit sichtbaren Zeichen**, kein Formatierungs-/Sicherheitsbefehl. Die normalen selbst getippten Bindestriche, Nummern oder Anführungszeichen dürfen stehen bleiben, aber es entsteht daraus keine rich-formatierte Liste oder versteckte Originalquelle.

**Beispiel für eine gültige mehrzeilige Nachricht:**

    Treffpunkt: Nordtor

    Zuerst suchen wir den Schlüssel.
    Danach sprechen wir mit dem Wächter.

Dies ist **eine** gewöhnliche berechtigt versendete Chatnachricht mit zwei Absätzen und drei nichtleeren Textzeilen, keine drei Nachrichten und kein spezielles Layoutmodul. Der Text darf nicht durch automatische CSS-/HTML-Markupinterpretation willkürlich anders aussehen.

**Nicht gewählt:** B (ungefiltertes Rich-HTML) und C (konfigurierbare Formatierung/Spoiler) werden für normale Chattexte **nicht** geplant. Die generelle 02.25-Option für sinnvolle Komfortmodule berechtigt die SL **nicht**, das hier ausgeschlossene Rich-Text-/Spoilersystem als Kampagnen-/Kanal-Ausnahme still wieder einzuschalten. Bei weiterhin optionalem 02.105-Chat gibt es keinen `Rich Chat`-/`Markdown An`-/`Spoiler An`-Schalter.

## 2. Was Klartext ausdrücklich erlaubt – und was nicht

| Bereich | Verbindlicher Fachumfang | Abgrenzung |
| --- | --- | --- |
| **Absatz und Zeilenumbruch** | Nachrichten dürfen mehrzeilig sein; Leerzeilen dürfen Absätze trennen und bei Anzeige erhalten bleiben | Nicht in mehrere Nachrichten aufteilen, keine automatische Überschrift-/Listenumwandlung |
| **Normale Zeichen** | Wörter, Zahlen, übliche Satzzeichen, Unicode-Zeichen und optional einfache Emoji als Textzeichen | Emoji als Text ist keine 02.112-Emoji-**Reaktion** oder ein Rich-Text-Editor |
| **Getippte Markdown-Zeichen** | Sterne, Unterstriche, Rauten, Backticks, Bindestriche, Pfeile etc. dürfen sichtbar als Zeichen stehen | Kein interpretierter Markdown-Bold, Kursiv, Quote, Heading, Codeblock oder Spoiler |
| **HTML-/Script-Strings** | Falls als Text zulässig, sicher **escaped/als Text gerendert** | Kein HTML-/CSS-/JS-/SVG-/Iframe-/Eventhandler-Ausführen |
| **Links** | Gewöhnliche URL als Text und ggf. allein nach **02.114** aktivierter berechtigter Klick-/Previewpfad | Keine neue Markdown-Linksyntax, automatisches Embed oder ungefragtes Drittanbieter-Fetch |
| **@Mentions/Pings** | Gesondert strukturierte und nach **02.111** berechtigte Erwähnungen können weiter funktionieren | Kein Rechtegewinn oder Ping allein durch freie Text-/Markdownsyntax |
| **Emotes/Reaktionen** | 02.112-Emote ist ein **eigener typisierter Chatinhalt**, Reaktion eine separate Aktion | `*A nickt*` im gewöhnlichen Text ist nicht automatisch eine Emote-/World-Aktion; `/me` nur nach separatem 02.112-Beschluss/Parserrecht |
| **Antworten/Zitate/Threads** | 02.113-UI-seitig typisierte Parent-/Quote-/Threadreferenzen bleiben verfügbar | `>`-Text oder frei kopierter Text erzeugt nicht automatisch berechtigte Originalzitate |
| **Umfragen** | 02.120-Polls sind eigene, separat berechtigte Chatobjekte | Polloptionen werden nicht zu allgemeinem Rich-Text und nicht als Markdown-Formular aus gewöhnlichem Text erzeugt |
| **Spoiler** | **Keine Spoilertexte**, keine auf Klick aufdeckbaren Geheimtexte im normalen Chat | Wirkliche SL-Geheimnisse ausschließlich in berechtigt getrennten 02.106-Scopes |
| **Eigenständige Dokumente/Handouts** | Separates Spielernotizbuch, 02.114-Medien und Bereich 10/12 bleiben unter ihren eigenen Rechten möglich | Ein anderswo vorhandener Rich-Editor darf nicht heimlich den 02.121-Klartextchat verändern |

**Einheitliches Standardverhalten:** Kein versteckter `Markdown Auto`-Modus, keine WYSIWYG-Werkzeugleiste mit Textformatierungen, kein CSS-only-Spoiler, keine Browser-HTML-Paste als aktiver HTML-Chat. Gewöhnliche Links werden ausschließlich gemäß bereits beschlossenem 02.114-Linkmodul behandelt, nicht als neu zugelassener Formatierungsdialekt.

## 3. Eingabe, Versand, Anzeige und Bearbeitung

**Mehrzeilige Eingabe und Absätze:** Der Chatcomposer muss, **wenn der Chat aktiv und der Absender aktuell berechtigt ist**, echte Absätze mit leeren Zwischenzeilen erfassen können. Textinhalt und erlaubte Zeilenumbrüche beim Servercommit konsistent speichern und im berechtigt lesbaren Nachrichtenverlauf darstellen, auch beim 02.108-Edit und ggf. 02.107-Export. Unterschiedliche Browser-Zeilenendungen dürfen intern kanonisch z. B. auf `\n` normalisiert werden; es darf daraus kein zusätzlicher Chat-Sendebefehl entstehen. Die konkrete Tastenkombination für Zeilenumbruch vs. bewusstes Absenden (Enter, Shift+Enter, Button) ist eine **spätere UI-Entscheidung**, aber Absatz-Eingabe muss ohne versehentliches Senden möglich sein.

**Rendern als Text, nicht als Markup:** Den gespeicherten Inhalt als reine Textknoten und geprüfte Zeilenumbruchdarstellung ausgeben, z. B. mit sicherem Whitespace-/`pre-wrap`-Verhalten; niemals untrusted Message-HTML in `innerHTML`/`dangerouslySetInnerHTML` als Befehl ausführen. Rendern darf weder Markdown automatisch interpretieren noch Script-/Style-/Iframe-Inhalte einschleusen; sensible Steuer-/unsichtbare Unicodezeichen, extrem lange Wörter/Zeilen, Kopier-/Paste-Daten und ungewöhnliche Bidi-Eingaben brauchen belastbare Anzeige-/Validierungsregeln ohne unnötige Verfälschung legitimer Texte.

**Beim Einfügen:** Aus einer extern formatierten HTML-/Word-/Web-/Markdownquelle nur den **sichtbaren, nach aktueller Sendepolicy zulässigen Plain-Textinhalt** übernehmen, nicht fremde Formatierungen, aktives DOM, Fonts, eingebettete Skripte oder automatische Attachments. Enthaltene Absätze und Zeilenumbrüche so sinnvoll wie möglich erhalten. Zitat-/Mention-/Media-Features dürfen nur über ihre **eigenen** 02.111-/02.113-/02.114-Rechte und strukturierte Nutzeraktion entstehen, nicht durch versehentlichen Paste von fremdem Markup.

**Nachrichtenlimits:** Maximalgröße in Zeichen/Bytes, Zahl der Zeilen/Absätze, zulässiger Unicodebereich, Rendering-/Scrollleistung, Missbrauchs-/DoS-/Überlangen-Schutz und Leere-Text-Normalisierung werden im späteren Implementierungsplan mit Tests konkret festgelegt. Diese fachliche Entscheidung schreibt **keine** feste Limithöhe und kein willkürliches Entfernen aller Leerzeilen vor. Fehler wegen Überlänge dürfen keine fremden Geheimnis-/Blocklisteninfos verraten.

**Bearbeitung/History:** Nur wirklich gesendete Chattexte werden zu 02.107-historisch gebundenen Nachrichten. Bei 02.108-Revision/Withdraw wird die Text- und Absatzstruktur versioniert geschützt, nicht durch ein frei manipulierbares Rich-Text-DOM gespeichert; nur aktuell UND historisch berechtigte Leser sehen entsprechende zulässige Fassungen. 02.118 A verbietet weiterhin gespeicherte ungesendete Drafts oder Auto-Send nach Reconnect.

## 4. Bestehende Security-, Chat- und Spielweltrechte bleiben erhalten

- **02.105/02.106/02.107:** Chat An/Aus bei Kampagnenerstellung; echte Kampagnen-/Gruppen-/Einzel-/Mehrpersonen-DM-/SL-Kanal- und aktuelle **UND historische** Empfänger-/Retention-/Fog-/Secretrechte vorrangig. Mehrzeiliger Text aus privater DM wird durch zusätzliche Absätze nicht zu einer öffentlichen Nachricht oder einem geheimen Spoiler freigegeben.
- **02.108/02.109:** Textänderungen/Withdraw bleiben zulässige versionierte Vorgänge, einzelne Meldungen/Moderationen bedürfen separater wirklicher Berechtigung. Keine Script-/CSS-/Markdownumgehung der Moderation, keine pauschale SL-Lesehoheit über fremde Privat-DMs.
- **02.110/02.111:** Channel-Mute, echter DM-Kontaktblock und erwähnungsbezogene Benachrichtigungen behalten ihre eigenen aktuell gültigen Regeln. Text `@SL` oder `@alle` ist kein privilegierter Ping oder Pflichtnotice, solange keine echte 02.111-autorisierte strukturierte Mention vorliegt; `*fett*` darf keine Benachrichtigungen priorisieren.
- **02.112/02.113/02.114/02.115:** Typisierte Emotes/Reaktionen, Replies/Threads, geschützte Bilder/Textlinks/Previews und Kanalpins/private Bookmarks können parallel existieren, wenn gesondert aktiv. Sie geben weder CSS-/Markdown-/HTML-Formatierung noch unberechtigten Zugang zu einer älteren Nachricht. 02.114-Autopreview ist nicht durch einen frei getippten HTML-Tag oder Markdownlink erzwingbar.
- **02.116 A und 02.118 A:** Keine individuellen „B hat gelesen“-/„zugestellt“-Status, keine ungesendeten lokal/serverseitig gespeicherten Drafts; 02.119-Präsenz zeigt keinen Composertext und kein gespeichert getipptes Rich-DOM. Suchfunktion 02.117 darf nur erlaubte Klartextnachrichten/zulässige Revisionen durchsuchen, nicht fremde alte Textversionen oder Draftreste.
- **02.120 Umfragen und 02.101–02.104-Systempfade:** Ein absatzgetrennter Pollwunsch oder handgeschriebene `[x]`-Option ist **kein** echter Poll-Submit/Chatvote oder 02.102-Ack. Wirkliche Pollobjekte erfordern die 02.120-Rechte, amtliche Korrekturen/ACKs ihren eigenen serverseitig autorisierten Weg.
- **Voicechat/Notizbuch/Weltwirkung:** Spielernotizen nach 02.94–02.98, der externe Voicechat, manueller SL-Entscheid und Regel-/Würfel-/Quest-/NPC-/Tür-/Node-/Turnabläufe bleiben unabhängig. Weder Absätze, Sonderzeichen noch Formatierungstext erzeugen einen echten 02.99-Server-/World-Commit.

**Datenschutz am gesamten Ausgabepfad:** Suche/Result-Snippets, Realtime, Export, Inbox/Badges, Cache, Mobile/Browser, Reconnect, Moderationsbelege und Untertitel/Bildschirmleserprojektionen zeigen normalen berechtigten Text/Absätze und keine verbotenen Inhalte oder durch HTML/Markdown eingeschleuste Link-/Secret-/Ackoperationen. Nicht verfügbare Nachrichtenteile dürfen nicht als `Spoiler per Klick` lediglich CSS-versteckt an unberechtigte Clients ausgeliefert werden.

## 5. Architekturentwurf und Umsetzung

**Konzeptionelle Bezeichnungen (keine finalen APIs/Tabellen):** `ChatPlainTextMessageBody`, `ChatPlainTextNormalization`, `ChatMultilineComposerState`, `ChatTextRenderingPolicy`, `ChatPlainPasteNormalizer`, `ChatPlainTextValidation`, `ChatTextSecurityProjection` und bestehende 02.107-`MessageRevision`-/`RecipientSnapshot`-Referenzen. Diese Daten sind **keine Rich-Text-Dokumentbäume**, kein Markupparser, kein Draftarchiv und keine neuen Chat-Erlaubnisse.

**Umsetzungsplan nach Featureworkshop:**
1. **Fachliche Schranke festlegen:** 02.121 A als Klartext-only mit **Absätzen/Leerzeilen erlaubt**, ohne Kampagnen-/Channel-Toggle für Markdown/Rich-Text/Spoiler. 02.105-Chat Aus/An gilt weiterhin; alle 02.25-ACL-Ausnahmen haben keine Ermächtigung, ausgeschlossene Formatierung zu aktivieren.
2. **Mehrzeiligen Composer/Sendeguard planen:** Text mit Zeilenumbrüchen/Absätzen flüchtig im aktuellen Eingabefeld halten; absichtliches Senden von neuer Zeile UI-seitig unterscheidbar machen, mit frischer 02.106-/02.109-/02.110-Sendberechtigung und ohne 02.118-A-Draftpersistenz.
3. **Kanonisches Klartextmodell:** Sichere Unicode-/Zeilenendungs-/Leerzeilen-/Längennormalisierung, kein Rich-DOM, keine Markdown-/HTML-Interpretation. Paste als Plain Text, Versionierung bei 02.108, 02.107-Retention und historischer RecipientScope.
4. **Sichere pro Leser Ausgabeschicht:** escaped Textknoten mit erhaltener Zeilenstruktur in Chat, History, Reply-/Quote-/Thread-/Search-/Pin-/Moderations-/Export-/Reconnectanzeigen. Links/Mentions/Poll-/Emote-/Media-Interaktionen separat nach 02.111–02.120 typisiert und berechtigt.
5. **Abuse-/Injection-/Integrationsprüfung:** XSS/HTML/SVG/CSS/Script, Markdown-Befehle, große Pasteblöcke, zu viele Leerzeilen, Mixed CRLF/LF, Unicode/Bidi, Mobile/Screenreader/Kopieren, 02.108-Edits, 02.110-Blocks und bestehende Sicherheits-/Retentionregeln.
6. **Abnahme/UI später:** Die konkrete Taste zum Absatz/Versand, Platzhaltertext, Editorhöhe, max. Zeilenlänge und Layout erst nach Abschluss aller Featureentscheidungen festlegen. Keine Softwareimplementierung vorweg behaupten.

## 6. Fachliche Abnahmetests

| Test | Erwartetes Ergebnis |
| --- | --- |
| `Chat Aus` bei Kampagnenerstellung | Keine neuen regulären Chattexte, aber Spielernotizen, Würfel-/Systemlog, Welt und echte amtliche Notices funktionieren |
| Berechtigter Spieler schreibt zwei Absätze mit Leerzeile | **Eine** Nachricht mit erhaltener Absatzstruktur statt einer einzigen zusammengeklebten Textzeile |
| Spieler fügt mehrere Zeilen mit `CRLF`, `LF` ein | Inhalt bleibt sinnvoll mehrzeilig nach konsistenter Normalisierung, ohne unbeabsichtigten Sendevorgang |
| Text `**Hallo**` / `_leise_` / `# Notiz` | Sichtbare Zeichen, keine Fett-/Kursiv-/Überschrift-Darstellung |
| Text `- eins` und `1. zwei` | Bleibt getippter Text; kein automatisch formatierter Bullet-/Listen-Editor |
| Text `> geheime Zeile` | Kein strukturiertes 02.113-Zitat und kein verborgenes Spoilerobjekt |
| Text `||Geheimnis||` oder `<span hidden>Code</span>` | Kein Spoiler und keine unsichtbar ausgelieferte CSS-Geheimnisfreigabe |
| Text `<img src=x onerror=alert(1)>` oder `<script>…</script>` | Sicher als Text dargestellt, keine ausführbare HTML-/JS-/SVG-/CSS-Interpretation |
| HTML-/Word-Inhalt als Paste mit Absätzen | Nur sicherer Plain Text inklusive normaler Zeilenumbrüche eingefügt, keine eingebetteten aktiven Elemente |
| Chat-URL zu einer Website als gewöhnlicher Text | Nur nach separat wirksamer 02.114-Linkpolicy ggf. klickbar/previewfähig; kein neuer Markdown-/HTML-Linkbefehl |
| Berechtigtes `@Name` via 02.111 strukturierte Mention | Legitimer Ping nach echten ACL-/Mute-/Blockrechten; keine frei erfundene Mention durch Markdown |
| Reiner Text `*A nickt*` / berechtigter 02.112-Emotetyp | Normaler Freitext bleibt normal; eigenes typisiertes Emote nach 02.112 unabhängig möglich |
| Markdown `>` vs. echte 02.113-Reply-/Quote-Referenz | Nur ausdrücklich gültiger Servermessagebezug darf alte Quelle referenzieren; keine DM-/Historyfreigabe durch Text |
| Eigene 02.120-Polloption als `[ ] Fluss` geschrieben | Kein echter Pollvote und keine automatische Worldaktion |
| 02.108 bearbeitet mehrzeilige Nachricht | Zulässige Revision speichert/zeigt aktuelle berechtigte Absätze, keine unberechtigte alte Revision |
| 02.109-Moderator sieht fallberechtigtes Textbeispiel | Gleicher sicherer Text/Absatzrenderer ohne Script-, History- oder fremde DM-Leaks |
| 02.107-alte Nachricht aus früherer geheimer Gruppe | Nicht durch Copy/Paste-/Snippet-/Spoiler- oder Formatierungsmodus einem Neumitglied zugänglich |
| 02.110-DM-Block aktiviert | Plain Text umgeht nicht den neuen DM-Empfängerblock; kein versteckter Blocklistgrund |
| 02.116 A keine Lesebestätigungen | Anzeige eines formatiert aussehenden Texts erzeugt keinen Delivered-/Read-Receipt |
| 02.118 A kein Draftspeicher, 02.119 Typing aktiv | Mehrzeiliger Composer bleibt flüchtig, kein Auto-Save/Auto-Send, Typing sendet keinen Textinhalt |
| 02.117-Suche nach einem Begriff aus Absatz zwei | Nur nach tatsächlicher aktueller UND historischer 02.107-Berechtigung Treffer, normales Snippet ohne HTML-Ausführung |
| Große Nachrichten/Unicode/Bidi/übermäßige Leerzeilen | Begrenztes sicheres Rendering und gültige Zeichennormalisierung, keine Endlosschleife/DoS |
| Texte enthalten vermeintliches `@System`, `ACK` oder `Tür öffnen` | Kein offizielles Notice/Ack, kein NPC-/Quest-/Door-/Node-/Turn-/Ressourcenbefehl |

## 7. Beschlussgrenze und nächste Featurefrage

**Verbindlich beschlossen: 02.121 A mit ausdrücklicher Nutzerergänzung „Absätze ja, aber nichts Ausgefallenes“.** Chat bleibt **einfacher mehrzeiliger Klartext** mit absatztreuen einzelnen Zeilenumbrüchen/Leerzeilen, **ohne** Rich-Text-/Markdown-/HTML-Interpretation, Formatierungsleiste oder Spoiler. Die SL kann diesen ausgeschlossenen Komfortbereich **nicht** über 02.25-/Kanalpresets wieder einschalten. Separat autorisierte 02.111-Mentions, 02.112-Emotes/Reaktionen, 02.113-Replies, 02.114-Textlinks/Anhänge, 02.115-Pins und 02.120-Umfragen bleiben eigenständige typisierte Funktionen; ihre Rechte werden nicht durch Zeichenfolgen im normalen Text erzeugt. Alle 02.105–02.120-Rechte/Secret-/Retention-/Moderationsguards bleiben erhalten, insbesondere **02.116 A ohne Chat-Lesebestätigungen**, **02.118 A ohne gespeicherte Entwürfe** und bewusst quittierte 02.102-Systemnachrichten unabhängig. Kein Text- oder Absatzinhalt erzeugt echte Weltwirkung.

**Nicht beschlossen:** Konkrete Absatz-/Enter-/Senden-Tastenkombination, Chat-Editorhöhe, Maximalwerte für Zeichenzahl/Leerzeilen, Syntaxhighlighting, Markdown-Plugins, Spoilerformat, endgültige API-/Datenbankschemata oder MVP-Priorität. Inhalt und Umfang des eigenständigen Spieler-Notizbuchs sind **nicht** durch 02.121 eingeschränkt.

## Nächste Entscheidung 02.122 – Sprachnachrichten und Audio-Clips im optionalen Chat

**Beispiel:** Ein Spieler möchte einen kurzen gesprochenen Hinweis aufnehmen und im Gruppenchat teilen. Andere Gruppen verwenden bewusst ausschließlich externe Voicechat-Programme und möchten keine integrierten Audioaufnahmen speichern. Das ist von 02.114-Bildern/Dateien und 02.105-Chat An/Aus getrennt zu entscheiden.

- **A – Keine integrierten Sprachnachrichten:** Kein Aufnahme-/Wiedergabe- oder Sprachclipmodul im Chat; externe Voicechats und anderweitig erlaubte Dateien bleiben unabhängig.
- **B – Unbegrenzte Aufnahmen und Autoplay:** Jeder kann Audiodaten ohne wirksame Rechte-/Längen-/Datenschutzprüfung aufnehmen, weitergeben und allen automatisch abspielen.
- **C – Konfigurierbare geschützte Chat-Sprachnachrichten (Empfehlung):** Nur wenn der 02.105-Chat und diese Teilfunktion ausdrücklich aktiv sind, darf eine aktuell berechtigte Person nach 02.25-Kampagnen-/Kanal-/Rollen-/Personenstandards kurze Audionachrichten bewusst aufnehmen und senden. Geschützte Empfänger-/Retention-/Attachmentrechte aus 02.106-/02.107-/02.114, Mute/Block und Moderatorenscope bleiben; keine versteckte Mikrofonaufnahme, kein ungewollter Autoplay/Voice-Transkriptzwang, keine automatische Quest-/World-/ACK-Wirkung. Konkrete UI/Limits später.
