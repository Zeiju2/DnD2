# AdventureShift – Karten-Workshop: Beschluss 02.124 A – keine integrierte Chat-Übersetzung

**Stand:** 13.10.2026 – Fachbeschlüsse 02.1 bis 02.124; nächste offene Frage 02.125
**Status:** Verbindlicher Fachbeschluss und konzeptioneller Umsetzungs-/Abnahmeplan; **noch keine Softwareimplementierung**, keine finalen API-/DB-/UI-Verträge und keine MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnenstandards und gültige markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – persönliche Notizen/Kampagnenoptionen](KARTEN-WORKSHOP-02.98.md) · [02.99 – geschützte manuelle Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – offizielle Mitteilungen und bewusste ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – integrierter Chat An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106 – Channel-/Gruppen-/DM-/SL-Rechte](KARTEN-WORKSHOP-02.106.md) · [02.107 – heutige UND historische Nachrichtensicht/Retention](KARTEN-WORKSHOP-02.107.md) · [02.108 – Edit/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – Mute/DM-Block](KARTEN-WORKSHOP-02.110.md) · [02.111 – Erwähnungen/Pings](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen/Emotes](KARTEN-WORKSHOP-02.112.md) · [02.113 – Antworten/Threads/Zitate](KARTEN-WORKSHOP-02.113.md) · [02.114 – Dateien/Links/Previews](KARTEN-WORKSHOP-02.114.md) · [02.115 – Pins/Bookmarks](KARTEN-WORKSHOP-02.115.md) · [02.116 A – keine individuellen Lesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.117 – berechtigte Chatsuche](KARTEN-WORKSHOP-02.117.md) · [02.118 A – keine gespeicherten Entwürfe](KARTEN-WORKSHOP-02.118.md) · [02.119 – Präsenz/Typing](KARTEN-WORKSHOP-02.119.md) · [02.120 – Chatumfragen](KARTEN-WORKSHOP-02.120.md) · [02.121 A – Klartext mit Absätzen](KARTEN-WORKSHOP-02.121.md) · [02.122 A – keine Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.123 A – keine Weiterleitung](KARTEN-WORKSHOP-02.123.md) · [Kommunikationsworkshop 11](FEATURE-WORKSHOP.md).

## 1. Verbindliche Entscheidung – Variante 02.124 A

**Der Projektinhaber hat ausdrücklich A gewählt: Keine integrierte automatische oder manuell anforderbare Chat-Übersetzungsfunktion in AdventureShift.** Nachrichten werden gemäß 02.121 A als **gewöhnlicher mehrzeiliger Original-Klartext** mit Zeilenumbrüchen/Absätzen übertragen, gespeichert und nur den tatsächlich berechtigten Empfängern angezeigt. Die Software plant **keine** automatische Spracherkennung, Zielspracheinstellung für Chatinhalte, `Nachricht übersetzen`-Schaltfläche, Übersetzung auf Klick, Auto-Translate beim Eingang, maschinellen Übersetzungsdienst, KI-Chatübersetzer oder übersetzten Parallelverlauf.

**02.124 A gilt für alle gewöhnlichen integrierten 02.106-Chatbereiche:** Kampagnenkanäle, berechtigte Gruppen, Einzel-/Mehrpersonen-DMs und SL-bezogene Kanäle. Auch die SL bekommt keinen 02.25-Kampagnen-/Kanal-/Rollen-Ausnahmeschalter, der die ausdrücklich ausgeschlossene Chatübersetzung wieder aktiviert. Ein späteres Übersetzungsmodul benötigt einen **neuen ausdrücklichen Fachbeschluss**.

**Beispiel:** A schreibt im berechtigten Gruppenchat auf Englisch: `The bridge is blocked.` B sieht – falls zum tatsächlichen gültigen 02.107-Empfängerkreis gehörig – **denselben englischen Originaltext**, keine von AdventureShift erzeugte deutsche Variante. B kann A um eine deutsche Formulierung bitten, im externen Voicechat nachfragen oder einen **eigenständig gewählten externen** Übersetzungsweg verwenden. Die Plattform fragt keine fremden Übersetzungs-APIs an und legt ohne bewusste neue Useraktion keine DMs bei einem fremden Anbieter offen.

**Nicht gewählt:** B (ungefragte universelle Übersetzung mit Drittweitergabe) und C (gesichert konfigurierbare Übersetzung). Das allgemeine 02.98-/02.25-Prinzip „geeignete Module bei Kampagnenerstellung schaltbar“ macht die **bewusst abgelehnte** Funktion nicht zu einer versteckten Checkbox.

## 2. Klare Grenzen und weiter zulässige Sprachvielfalt

| Bereich | Verbindliches Ziel unter 02.124 A | Keine implizite neue Funktion |
| --- | --- | --- |
| **Gewöhnliche Nachrichten** | Originalsprache, Klartext und 02.121-Absätze/Leerzeilen unverändert erhalten | Keine Autoerkennung oder automatisch ersetzte Textfassung |
| **Einzelne Nachricht übersetzen** | **Nicht** in der Chat-UI oder normalen Message-Aktionen vorgesehen | Kein Button `Übersetzen`, Kontextmenü, Slash-Command oder Tastenkürzel dafür |
| **Sprachen/Unicode** | Deutsch, Englisch und andere gemäß sicherer Texteingabe zulässige Schriften dürfen als Originaltext verwendet werden | Keine Einschränkung auf Deutsch; keine automatische „nur Standardsprache“-Umwandlung |
| **Chat-Verlauf/Historie** | Tatsächlich gesendete Originalnachrichten nach 02.107-/02.108-Rechten | Keine gespeicherten Übersetzungskopien oder Schattenhistorie |
| **Externe Übersetzung** | Spieler dürfen außerhalb von AdventureShift selbst ein Hilfsmittel wählen | Kein versteckter automatischer API-/Cloud-/Browserdienst-Aufruf durch AdventureShift |
| **Browser/OS-Erweiterungen** | Können unabhängig von der Anwendung ggf. fremde Seiten-/Auswahlübersetzung anbieten | Die App kann fremde Browserfunktionen nicht allgemein deaktivieren oder ihre Datenschutzwirkung garantieren |
| **02.117 Volltextsuche** | Sucht nur tatsächlich freigegebene Original-Nachrichtentexte/-Metadaten | Keine automatisch übersetzten Suchbegriffe, Indizes oder fremdsprachigen Kopien als zusätzliche Datenquelle |
| **02.113 Antworten/Zitate** | Anzeigen von nach eigenen Rechten geschützten Originalquellen/Revisionen | Keine eigene maschinell übersetzte Quotevorschau oder fremde Gruppen-/DM-Freigabe |
| **02.114 Dateien/Links** | Nur separat tatsächlich erlaubte Anhänge, Datei-/Textlinks und sichere Vorschauen | Kein Übersetzen von PDFs, OCR/Bildern, Linkseiten, Datei-/Audioinhalten durch Chat-A |
| **Anwendungssprache/Barrierefreiheit** | Eigenständige spätere UI-Lokalisierung und Screenreader-Unterstützung bleiben grundsätzlich offen | Kein generelles Verbot einer deutsch-/englischsprachigen Benutzeroberfläche oder unabhängig beschlossener Hilfstechniken |
| **Eigene Spielernotizen/Handouts** | Nach ihren separaten Rechten und Formaten bestehen bleiben | Kein automatischer Translations-/Transkriptionsjob der Notizen durch Chat |
| **Amtliche Notices/Acks** | Rechtmäßige getrennte System-/Kenntnisnahmepfade bleiben gültig | Chat-„Übersetzung“ darf 02.102-ACK weder ersetzen noch erzeugen |

**Keine falsche Sprach-/Geheimniszusage:** 02.124 A ist **keine automatische Schutzmaßnahme gegen bewusstes menschliches Abschreiben oder die Nutzung eines externen Translators**. Wer selbst Inhalt zu einem fremden Dienst kopiert, muss die entsprechenden Vertraulichkeits-/Nutzungsrechte und dessen Datenschutz selbst berücksichtigen. AdventureShift darf aber selbst keine versteckten Chat-/DM-/Gruppentexte zur Übersetzung exportieren. Automatische Browser-Übersetzung außerhalb des App-Einflusses kann nicht absolut verhindert oder als sichere Plattformfunktion beworben werden.

## 3. Sicherheits- und Historienrechte unverändert

1. **02.105 Chat An/Aus:** Bei Chat Aus keine regulären Chatnachrichten oder Übersetzungs-Backdoor; bei Chat An keinerlei Übersetzungs-Featureflag. Externer Voicechat, private Spielernotizen, Würfel-/Systemlog und getrennte amtliche Systemmitteilungen bleiben unabhängig.
2. **02.106/02.107 Quellrechte:** Nachrichteninhalt, Originalsprache, Sendername, Channel-/DM-/Gruppenherkunft und Historie gehören nur zu den heute **UND historisch** für diesen Betrachter tatsächlich erlaubten 02.107-Originalempfängern. Keine neue globale Übersetzungs- oder Fremd-API, die Privatnachrichten, alte Gruppeneinträge, SL-Geheimnisse oder Metadaten auf anderem Weg ausgibt.
3. **02.108 Edits/Withdraw/Retention:** Verbindlich nur tatsächlich aktuelle und nach Revisionsrechten zugängliche Originaltexte. Eine spätere Bearbeitung darf nicht durch eine im Hintergrund angelegte Übersetzung der früheren Fassung umgangen werden. Ebenso keine Schattenarchivierung durch übersetzte Snippets nach 02.107-Retentionende.
4. **02.109 Moderation:** Ein legitim eingereichter Report darf nach eigenen fallbezogenen 02.109-Regeln bearbeitet werden; daraus erwächst kein pauschales SL-Übersetzen/Lesen fremder DMs und kein freier Datentransfer an dritte Übersetzungsanbieter.
5. **02.110 DM-Block und Kanal-Mute:** Bestehende serverseitige neue Kontaktsperren/Benachrichtigungsfilter gelten weiter. Keine „Translation Request“-Nachricht als DM-Blockumgehung, kein automatisches Fremd-Ping oder Offenlegen einer Blockliste.
6. **02.111–02.115 und 02.119–02.120:** Erwähnungen, Rollenspiel-Emotes/Reaktionen, Parent-/Thread-Vorschauen, Textlinks/Dateien, Pins/Bookmarks, kurzlebige Präsenz und berechtigte Umfragen behalten eigene Rechte und Originaldaten. Keine zusätzliche Translate-Funktion über Pollbeschreibung, Linkvorschau, Quote, Suchtreffer, Reaktion oder Typingstatus.
7. **02.116 A/02.118 A/02.121 A/02.122 A/02.123 A bleiben vollständig:** Keine individuellen Lesebestätigungen, keine gespeicherten Entwürfe, einfacher Text mit Absätzen statt Rich-/Markdown/Spoiler, keine eingebauten Sprachnachrichten und keine systemseitige Chatweiterleitung. Die ausgeschlossene Chatübersetzung darf **keinen** dieser anderen negativen Beschlüsse über neue UI-/API-Umwege umgehen.
8. **02.99 und 02.101–02.104:** Eine anderssprachige Chatnachricht, manuell extern übersetzte Spielermeinung oder vermeintlich sprachlich interpretierter Code bewirken weder tatsächliche World-/NPC-/Quest-/Tür-/Node-/Turn-/Würfel-/Ressourcenaktion noch echte 02.102-Kenntnisnahmequittung. Offizielle Notices/Acks sind ein anderer unabhängiger Rechts-/Serverpfad.

## 4. Negativer Architekturentscheid und fachlicher Umsetzungsplan

**Nicht als Chatfunktion oder Modell planen:** `ChatTranslationRequest`, `ChatAutoTranslatePolicy`, `ChatTargetLanguagePreference` für Chatnachrichten, `ChatMachineTranslationResult`, `ChatTranslationCache`, `ChatTranslatedMessageRevision`, `ChatTranslationJob`, `ChatTranslationProviderBridge`, `ChatTranslationReadProjection`, `canTranslateChatMessage` und `translateMessage` als spezielle API-/WebSocket-/Offline-/Push-/Search-/Export-Capabilities. Das sind Beispiele gerade **ausgeschlossener** Funktionsfamilien, keine neuen tatsächlichen Tabellen oder APIs.

**Technisches Ziel:** Originalnachrichten sicher als Text mit gültiger Original-Zeilenstruktur und erlaubtem Unicode speichern/darstellen, ohne ungefragte Sprachanalyse oder Drittanbietertransfer. Das beinhaltet keine Festlegung auf ein bestimmtes Browser-/Unicode-/Storage-Framework. Bereits beschlossene 02.114-Linkvorschauen unterliegen ihren eigenständigen SSRF-/Datenschutzregeln, aber verarbeiten keinen Inhalt allein zum Zweck automatischer Übersetzung.

**Geplante Schritte nach Abschluss des Workshops:**
1. **Feature-/Settingsinventar:** 02.124 A als **ausgeschlossenen Chat-Übersetzungsdienst** verzeichnen; im 02.25-/02.105-Kampagnenassistenten kein `Translate An`-Modul, keinen Kanal-/SL-Rollen-Override anbieten. UI-Lokalisierung und Notiz-/Handoutmodule fachlich separat lassen.
2. **Composer/Transport/History:** 02.121-Klartext mit Absätzen und zulässigen Originalschriften ohne Sprachkonvertierung weiterleiten und 02.107-historisch empfängergebunden speichern; 02.108-Revisionen/Withdraw/02.109-Moderation unverändert. Keine neue gespeicherte übersetzte Fassungs- oder Cachekopie.
3. **Sichere Projektionspfade:** Originaltexte/Quotes/Threads/Search-Snippets/Export/Realtime/Reconnect ausschließlich für tatsächlich heutige UND historische Empfänger, ohne Übersetzungs-Cloudendpoint, ohne neue Metadatenorakel oder unbekannte Zielkanalsprache. 02.110-DM-Blocks und 02.116-Read-Receipt-Verbot bewahren.
4. **Keine Drittanbieterintegration:** Keine automatische HTTPS-Übersetzungsanfrage, KI-/LLM-Promptweitergabe, Browser-Extension-Steuerung, verstecktes Spracherkennungs-/Analytics-/Transcript-Plugin aus dem Chat. Fremde vom Menschen bewusst genutzte Werkzeuge sind nicht durch AdventureShift kontrolliert.
5. **Negativtests:** Übersetzungsbutton/Shortcut/REST/WebSocket/Backgroundjob, versteckte Settings-Flags, textbasierte Trigger, Push/Cache/Export/Moderatorpfad und 02.114-/02.117-Sonderwege auf ungefragte Translation/Datenausleitung prüfen.
6. **Geltende Sicherheitsgrenzen:** 02.105–02.123-Rechte/Retention, 02.99-Worldcommit und 02.102-Ack-Pfade testbar unverändert halten. Konkretes Frontend-Layout, App-Lokalisierung und MVP bleiben offen.

## 5. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Kampagne aktiviert 02.105 Chat An | Gewöhnlicher erlaubter mehrzeiliger Originaltext, **kein** Chat-Übersetzungsbutton/-dienst |
| Kampagne deaktiviert 02.105 Chat | Keine regulären Chat-/Translationjobs; Würfel, Welt, Notizen und amtliche Notices bleiben unabhängig |
| Spieler schreibt englische Nachricht im deutschsprachigen Team | Berechtigte Empfänger erhalten den englischen Originaltext, keine von AdventureShift erzeugte deutsche Variante |
| Spieler schreibt Deutsch, Französisch oder andere zulässige Unicode-Schriften | Text wird ohne erzwungene Sprachumwandlung sicher gespeichert/angezeigt |
| Spieler schreibt zwei Absätze nach 02.121 A | Struktur und Originalsprache der Absätze erhalten |
| SL öffnet Kampagnen-/Kanal-/Rollen-Einstellungen | Kein `Auto-Translate`-Flag oder versteckte Übersetzungsfreigabe trotz 02.25 |
| Spieler öffnet Chat-Kontextmenü, Suche, Thread oder Reply | Keine systemseitige `Translate Message`-Aktion oder übersetzte Originalvorschau |
| Manipulierter Client sendet `translateMessage`-API-/WebSocket-Aufruf | Kein nutzbarer normaler Übersetzungsdienst und keine private Textausleitung |
| Browser-Autotranslate ist als externe Funktion aktiv | Keine Behauptung, AdventureShift könne externe Browser-Erweiterungen oder ihre Datenverarbeitung absolut kontrollieren |
| Nutzer kopiert eigenen rechtmäßig sichtbaren Text freiwillig in selbst gewählten Translator | AdventureShift ruft keinen Drittservice automatisch auf; Datenschutz-/Geheimhaltungsverantwortung für manuelles Fremdtool getrennt |
| Neue Gruppenperson kennt alten geheimen Kanalbegriff | 02.106-/02.107-aktuelle UND historische Berechtigungen schützen alte Originale, kein Leak über „Sprache“/Übersetzung |
| Spieler ohne DM-ACL errät Message-ID | Keine Original-/Übersetzungs-/Sprach-/Sender-/Existenzoffenlegung |
| SL besitzt Administratorrolle, aber kein privates DM-Leserecht | Keine Übersetzungs- oder allgemeine DM-Read-API durch Admin-/Moderationsrecht |
| Nachricht wird 02.108 bearbeitet oder zurückgezogen | Keine versteckte altübersetzte Fassung aus Cache/Search/Export/History |
| 02.107-Retention einer DM endet | Keine Schattenhistorie als übersetzter Snippet/Backup/Index |
| 02.109 entfernt einen konkreten Chattext | Keine Weitergabe an Dritttranslator oder Wiederbelebung über abgelehnte Übersetzungsfunktion |
| A hat B per 02.110 als DM-Kontakt blockiert | Kein „Übersetzung anfordern“-Kontaktbypass oder Offenlegung der Blockliste |
| 02.111-`@alle`-Mention und 02.112-Reaction | Nur tatsächliche eigenen typisierten Rechte, keine Übersetzungsbedingte Ping- oder Read-Spur |
| 02.113-Quote zeigt berechtigte alte Nachricht | Ursprünglicher geschützter Quelltext, kein automatisch übersetzter Copy-/Crosspost nach 02.123 A |
| 02.114-Link und Dateianhang | Nur geschützter Link-/Dateipfad, keine ungefragte automatische Übersetzung von Website/PDF/OCR |
| 02.117-Volltextsuche | Nur berechtigte Originaltexte/Revisionen, keine automatisch übersetzten Suchindizes |
| 02.118 A kein Draftspeicher | Keine gespeicherten ungesendeten Chatübersetzungsvorlagen oder Auto-Sends |
| 02.119-Präsenz/Typing sichtbar | Kein Content-/Sprachdetektions-/Übersetzungsstatus anderer Teilnehmer |
| 02.120 Umfrage in anderer Sprache | Nur Poll nach eigener ACL, keine Übersetzung und keine automatische echte Weltaktion |
| 02.116 A schließt individuelle Read-/Delivery-Receipts aus | Keine Übersetzungsaufruf-Spur als persönlicher Lesestatus |
| Fremdsprachiger Text fordert `ACK`/`Tür öffnen` | Keine echte 02.102-Systemquittung oder 02.99-NPC-/Quest-/Door-/Node-/Turnwirkung |
| Spieler nutzt externe Voicechatsoftware für Verständigung | Weiter unabhängig, keine Chat-Voice-Transkriptions-/Übersetzungsintegration gemäß 02.122 A |
| UI-Lokalisierung wird später erwogen | 02.124 A schließt nicht automatisch deutsch-/englischsprachige Menüs aus, nur Chat-Inhaltübersetzung |

## 6. Beschlussgrenze und nächste Featurefrage

**Verbindlich beschlossen: 02.124 A – kein integrierter Chatübersetzungsdienst.** Originalsprachiger 02.121-Klartext samt Absätzen wird nur im gültigen 02.106-Kanal nach **heutigen UND historischen 02.107-/02.108-Rechten** angezeigt; keine automatische/manuell per App ausgelöste Chatübersetzung, Übersetzungs-API/Cache/Provider/Cloudweitergabe und kein 02.25-Settings-Override. Bereits beschlossene Chatrechte und Retention, 02.116 A ohne individuelle Lesebestätigungen, 02.118 A ohne gespeicherte Entwürfe, 02.122 A ohne Voice-Memos und 02.123 A ohne Forwarding gelten fort. Extern eigenständig genutzte Übersetzer und spätere eigenständige App-UI-Lokalisierung sind **andere Dinge**; die App sendet private Nachrichten nicht ungefragt an Drittanbieter. Keine reale Welt-/Quest-/Node-/Turn-/ACK-Wirkung durch fremdsprachigen Text.

**Nicht beschlossen:** Globales Verbot, verschiedene Sprachen einzugeben oder externe Übersetzungswebseiten bewusst selbst zu verwenden; neue Pflicht zu KI/Cloud; Entzug von eigenständigen bereits beschlossenen UI-/Notiz-/Datei-/Voicechatoptionen; endgültige UI-Sprachen oder andere Lokalisierung außerhalb des Chattexts. Ein späteres Chatübersetzungsfeature braucht einen neuen Nutzerbeschluss.

## Nächste Entscheidung 02.125 – Chatverlauf exportieren und drucken

**Beispiel:** Die SL oder ein Spieler möchte nach einer Session einen berechtigt einsehbaren Chatverlauf für persönliche Spielnotizen exportieren oder als Text/PDF drucken. Dabei dürfen private DMs, alte Gruppen- oder SL-Geheimnisse und abgelaufene Nachrichten nicht plötzlich im Export landen. Bereits vorhandene geschützte 02.107-/02.117-Export- und Datenschutzpfade sind dabei zu berücksichtigen.

- **A – Keine eigene Spieler-Export-/Druckfunktion:** Normale berechtigte History-/Suche bleibt, aber keine zusätzliche integrierte „Chat herunterladen/drucken“-Funktion. Gesetzlich/administrativ nötige eigene Daten-/Audit-/Backupwege sind unabhängig.
- **B – Unbegrenzte vollständige Exporte:** Jede Person exportiert/teilt alle Kampagnenchats, privaten DMs, geheime historische Nachrichten, ältere Revisionen und Dateien unabhängig von Zugriffsrechten.
- **C – Konfigurierbare berechtigte Chat-Exporte (Empfehlung):** Bei 02.105 Chat An dürfen je 02.25-Kampagnen-/Kanal-/Rollen-/Personenpolicy und gültigen Ausnahmen ausdrücklich berechtigte Spieler/SL nur **heute UND historisch gemäß 02.107** tatsächlich lesbare Nachrichten in begrenztem Zeitraum/Format exportieren oder drucken. Originaltext/02.121-Absätze, 02.108-Revisionen, 02.109-Moderation, 02.110-Personenfilter, 02.113-Quotes, 02.114-Anhänge und 02.116-A-Privatsphäre bleiben geschützt. Export ist kein universeller DM-Archiv-/Forwarding-Bypass und erzeugt keine echte Welt-/ACK-Wirkung. Dateiformate, Limits und UI später.
