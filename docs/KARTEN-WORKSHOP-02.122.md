# AdventureShift – Karten-Workshop: Beschluss 02.122 A – keine integrierten Chat-Sprachnachrichten

**Stand:** 13.10.2026 – Fachbeschlüsse 02.1 bis 02.122; nächste offene Frage 02.123
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungs- und Abnahmeplan; **noch keine Softwareimplementierung**. Keine fertigen API-/DB-/UI-/MVP-Verträge.
**Bezüge:** [02.25 – Kampagnenstandards und gültige markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.51 – Akustiksimulation](FEATURE-WORKSHOP.md) · [02.94–02.98 – Spielernotizen und optionale Kampagnentechnik](KARTEN-WORKSHOP-02.98.md) · [02.101–02.104 – amtliche Mitteilungen und echte ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus bei Kampagnenerstellung](KARTEN-WORKSHOP-02.105.md) · [02.106 – getrennte Kanal-/DM-/Gruppen-/SL-Rechte](KARTEN-WORKSHOP-02.106.md) · [02.107 – aktuelle/historische Leserechte und Retention](KARTEN-WORKSHOP-02.107.md) · [02.108 – Nachrichtenedits/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Meldung/Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – Channel-Mutes und DM-Blocks](KARTEN-WORKSHOP-02.110.md) · [02.111 – Mentions/Pings](KARTEN-WORKSHOP-02.111.md) · [02.112 – Reaktionen/Emotes](KARTEN-WORKSHOP-02.112.md) · [02.113 – Antworten/Threads](KARTEN-WORKSHOP-02.113.md) · [02.114 – geschützte Dateien/Bilder/Links](KARTEN-WORKSHOP-02.114.md) · [02.115 – Pins/Bookmarks](KARTEN-WORKSHOP-02.115.md) · [02.116 A – keine Lesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.117 – Chat-Suche](KARTEN-WORKSHOP-02.117.md) · [02.118 A – keine Entwurfsspeicherung](KARTEN-WORKSHOP-02.118.md) · [02.119 – Typing/Präsenz](KARTEN-WORKSHOP-02.119.md) · [02.120 – Chatpolls](KARTEN-WORKSHOP-02.120.md) · [02.121 A – Klartext mit Absätzen](KARTEN-WORKSHOP-02.121.md).

## 1. Verbindlicher Beschluss – Variante 02.122 A

**Der Projektinhaber hat ausdrücklich A gewählt: AdventureShift bekommt kein eingebautes Modul für Chat-Sprachnachrichten, Mikrofonaufnahme, Sprachclipversand oder spezielle Audio-Nachrichtenwiedergabe.** Spieler können im bei Kampagnenerstellung gemäß 02.105 optionalen Chat weiter berechtigten normalen Text mit Absätzen schreiben (02.121 A), erwähnen, antworten und die jeweils freigeschalteten übrigen Chatfunktionen nutzen. **Externe Voicechat-Programme** bleiben wie bisher der vorgesehene Weg für Sprachgespräche. Nichts an 02.122 A verlangt externen Voicechat, automatische Mithörfunktionen, KI, Transkript oder Sprachaufzeichnung.

**Keine versteckte C-Konfiguration:** Die 02.25-Defaults/markierten Ausnahmen und die übergreifende Vorgabe „die meisten geeigneten Funktionen bei Kampagnenerstellung an-/ausschaltbar“ bedeuten **nicht**, dass ein ausdrücklich abgewähltes Chat-Sprachnachrichtenmodul als versteckter Kanal-/SL-/Rollen-Schalter vorhanden sein soll. Keine Schaltfläche „Sprachnachricht“, keine Chat-Record-/Voice-Clip-API, kein Mikrofonzugriff für Voice-Memos und keine darauf zugeschnittene Nachrichtenart/Abspieloberfläche. Eine spätere Einführung benötigt eine neue ausdrückliche Entscheidung.

**Beispiel:** A möchte im Teamchat einen mündlichen Hinweis geben. Statt in AdventureShift auf „Aufnehmen“ zu klicken, kann A ihn im externen Voicechat erzählen oder als **Klartextnachricht mit Absätzen** nach 02.121 A aufschreiben. Abenteuerregeln, NPCs, Würfel, eigene Spielernotizen und die sichere manuelle 02.99-SL-Übernahme bleiben wie beschlossen separat verwendbar.

**Nicht gewählt:** B (beliebiges Aufnehmen/Autoplay ohne Rechte/Datenschutz) und C (optional konfigurierbares Audioaufnahme-/Sprachnachrichten-Feature).

## 2. Präzise Abgrenzung zu bestehenden Dateianhängen und anderen Audiomodulen

| Bereich | Wirkung von 02.122 A | Grenze |
| --- | --- | --- |
| **Mikrofon/Voice-Memo im Chat** | **Nicht vorgesehen**: keine Chat-Aufnahmetaste, Mikrofonberechtigung dafür, Recording-Session oder Record-/Stop-/Send-Audio-Flow | Kein unbemerkter, impliziter oder expliziter Mikrofonzugriff durch das Chatmodul |
| **Audio-Chatnachricht/Sprachcliptyp** | **Nicht vorgesehen**: keine typisierte `voiceMessage`-Nachricht, keine Waveform- oder Voice-Memo-Abspielfunktion | Keine versteckte Kanal-/Adminausnahme für das ausgeschlossene Modul |
| **Autoplay/Transkription** | Kein Chat-Sprachnachrichten-Autoplay, keine automatische Sprach-zu-Text-Transkription und keine Aufnahmeauswertung als Nebenfunktion | Kein stilles Aufnehmen, Abhören, Speech-to-Text- oder KI-Zwang |
| **Externer Voicechat** | **Weiter erlaubt und unabhängig**; geschieht außerhalb des integrierten Textchatmoduls | Nicht als von AdventureShift kontrollierter, heimlich aufgezeichneter Audiokanal behandeln |
| **02.114 generische Dateianhänge** | Die bereits separat beschlossenen **berechtigten Uploads/Downloads für ausdrücklich zugelassene Dateitypen** bleiben bestehen | 02.122 A erlaubt **nicht automatisch Audio-Dateitypen**; ob generische Audiodateien überhaupt als 02.114-Datei zulässig sind, bestimmt ausschließlich eine spätere Dateityp-Policy. Kein neuer Voice-Memo-Player oder Sprachclip-Capture durch eine gewöhnliche Datei |
| **02.51 Sound-/Akustiksimulation** | Szenensounds, Alarme, Sensoreffekte und manuelle SL-Soundcues aus früheren Beschlüssen bleiben unabhängig | Akustiksimulation ist kein Chat-Sprachnachrichtendienst |
| **Spielernotizen, Handouts, Würfel/Systemlog** | Separate, gemäß bestehenden Rechten nutzbare Module | 02.122 A löscht, verändert oder entsperrt diese Daten nicht |
| **02.121 Klartextchat** | Normaler mehrzeiliger Text mit Leerzeilen/Absätzen statt Voice-Chatfunktion | 02.121 A schließt Rich-Text/Markdown/Spoiler ebenfalls weiter aus |

**Wichtige Unterscheidung:** Ein eventuell in Zukunft separat als generische 02.114-Datei erlaubter Audiocontainer ist **kein Freibrief für ein integriertes Voice-Memo-Aufnahme-, Versand- oder Spezialwiedergabemodul**. Das Nutzer-A bezieht sich auf **Sprachnachrichten und Audio-Clips als Chatfeature**, nicht auf ein allgemeines Verbot von Weltgeräuschen, Musik/Soundeffekten oder sonstigen unter eigenständiger fachlicher Zustimmung nutzbaren Assets. Die 02.114-Dateitypfreigabe darf keine implizite Chat-Speech-Funktion aktivieren.

## 3. Negative Produkt-/Datenmodellentscheidung und Sicherheitsgrenzen

**Nicht als Feature planen:** `ChatVoiceMessage`, `ChatVoiceRecorder`, `ChatAudioCaptureSession`, `ChatVoiceClipPlayback`, `ChatVoiceMessageTranscription`, `ChatVoiceMessageDuration`, `ChatVoiceRecordingPermission`, `ChatVoiceWaveform` oder `ChatVoiceMessageAutoplay` als spezielle Chat-Nachrichten-/Dienst-/UI-Datenmodelle. Keine Chat-WebSocket-Events oder API-Routen `voiceMessageCreate`/`voiceMessageStartRecording`/`voiceMessageStopRecording`/`voiceMessageAutoplay`, keine Voice-Upload-Queue, keine zugehörige Speicherung, Suche, Reconnect-Synchronisation, Soundbenachrichtigung oder Moderationskopie. Fachbegriffe sind nur Beispiele ausgeschlossener Capabilities, keine Vorgabe tatsächlicher finaler API-Namen.

**Keine Mikrofonanfrage vom Chat:** Das integrierte Chatmodul soll den Nutzer **nicht** um Browser-/OS-Mikrofonrechte bitten, nur weil er einen Gruppenchat oder Schreibindikator öffnet, eine Umfrage erstellt, eine Nachricht senden möchte oder auf Reconnect wartet. Die 02.119-Kanalpräsenz/Typing sendet keinen Sprach-/Text-/Composerinhalt, 02.118 A speichert keine ungesendeten Chatentwürfe. Mögliche spätere ganz andere Mikrofonanwendungen benötigten eigene getrennte Beschlüsse/Einwilligung und dürfen 02.122 A nicht rückwirkend uminterpretieren.

**02.105 Chat Off:** Wenn die SL den normalen Chat bei Kampagnenerstellung deaktiviert, existiert natürlich auch **keine** versteckte Voice-Memo-Komponente oder deren Cache-/Subscribe-/Offline-Funktion. Die zuvor beschlossenen externen Voicechatmöglichkeiten und amtlich berechtigten 02.101–02.104-Systemnotices/Acks bleiben davon unabhängig.

**Authentifizierung, DM-/Historyschutz:** 02.106-Kanal-/Gruppen-/Direktnachrichtenrechte und 02.107-heutige **UND historische** Empfänger-/Retention-/Fog-/Secret-/NPC-/Quest-/Notiz-/Wurfrechte gelten unverändert für echte Texte/zugelassene 02.114-Dateien. Kein `voiceMessage`-Sonderpfad kann Blocklisten, 02.108-Withdraw, 02.109-Moderations- oder 02.110-Channel-Mute-/DM-Senderblock-Regeln umgehen. Keine ursprüngliche private Sprachnachrichtenhistorie konstruieren, keine neue versteckte Empfängerkennung, keine pauschalen SL-DM-Rechte.

**02.116 A, 02.118 A und 02.121 A fortgeltend:** Keine personenbezogenen Chat-Read-/Delivery-Receipts, kein gespeicherter ungesendeter Draft, keine Rich-Text-/Markdown-/Spoileroberfläche. Kein Sprachnachrichtenfeature als Workaround für diese ausgeschlossenen Chatkomfortfunktionen. Ein vom Nutzer selbst geschriebener Hinweis oder ein vorhandener mehrzeiliger Klartext bleibt gewöhnliche Chatnachricht, keine automatisiert transkribierte Voice-Aufnahme.

**Untrusted externe Inhalte:** Ein extern geposteter Link/Dateianhang nach 02.114 kann auf fremde Audioinhalte zeigen; daraus folgt weder automatisches Abspielen, Drittseitenabruf, Mikrofonzugriff noch ein durch AdventureShift erzeugter Voiceclip. URLs/Dateien bleiben unter 02.114-MIME-/Inhalts-/SSRF-/ACL-/Retentionkontrollen. Der externe Anbieter kontrolliert seine eigene Verarbeitung, nicht die Chat-Voice-Memo-Funktion von AdventureShift.

## 4. Andere Spiel- und Kommunikationsentscheidungen bleiben unabhängig

- **02.111 Mentions, 02.112 Emotes, 02.113 Replies, 02.120 Umfragen:** Spieler dürfen weiterhin bei jeweilig gültiger Kanal-/Rollen-/Personenpolicy Text erwähnen, Rollenspielhandlungen als **Text** formulieren, auf erlaubte Nachrichten antworten, in Threads diskutieren und berechtigt Umfragen erstellen/abstimmen. Keine dieser Aktionen verlangt einen Audiochat-Record-Button.
- **02.114 Anhänge und 02.115 Pins:** Eine erlaubte Textlinkvorschau oder ein berechtigter Dateianhang bleibt unter seiner echten Message-/Empfängerberechtigung; Pin/Bookmark macht nichts öffentlich und führt kein Voice-Modul ein.
- **02.117 Suche:** Kein Audio-Transkript, versteckter Voice-Memo-Index oder Durchsuchung nicht vorhandener Aufnahmen. Tatsächlich gesendete, zulässig gespeicherte Klartexte bleiben nach aktuellen **UND historischen** 02.107-Rechten suchbar.
- **02.119 Präsenz:** Sichtbar berechtigte `A schreibt`-Indikatoren oder grobe Onlineanzeige erhalten keinen neuen `A spricht gerade`-/Mikrofon-/Tonpegelstatus aus dem hier abgelehnten Voice-Memo-Modul.
- **02.101–02.104 System und 02.99 World-Commit:** Gesprochenes im externen Voicechat und gewöhnlich im Chat getippte Äußerungen sind weder persönliche 02.102-ACKs noch automatisch verbindliche SL-Genehmigungen. Nur tatsächlich autorisierte separate Server-World-/Node-/Quest-/Würfel-/Tür-/Turnaktionen haben Spielwirkung. Ein etwaiges späteres allgemeines Sprachmodul darf diese Rechte nicht durch vorgespiegelte „Sprachbefehle“ umgehen.
- **Manueller/Voicechat-first-Betrieb:** Die Gruppe kann Rätsel und Pläne mündlich klären, private Notizen schreiben und Entscheidungen freiwillig im geschützten Chat dokumentieren. Kein Missionsgenerator, automatisches Mithören, Speech-to-Text oder KI-System ist notwendig.

## 5. Konzeptioneller Umsetzungsplan – keine Softwareimplementierung

1. **Negativer Featurevertrag:** 02.122 A im Chatmodul-Inventar und globalem 02.25-Settingsassistenten als **bewusst ausgeschlossene** Aufnahme-/Voice-Clip-/Wiedergabefunktion dokumentieren. Weder Aufnahme-Button noch versteckter Featureflag, keine Teilmodul-Mikrofonberechtigung.
2. **Chattypen/Backend begrenzen:** Bereits beschlossene echte Message-/Kanal-/Anhangtypen unterstützen, aber **keinen neuen Voice-Message-Objekttyp, keine Voice-Upload-/Autoplay-/Transkriptions-API und keine eigenständige Voice-Datenbank** planen.
3. **Modulgrenzen beweisen:** Externe Voicechatnutzung, optional eigenständige 02.51-Akustik/SL-Cues, Spielernotizen und eventuelle nach 02.114 separat erlaubte generische Dateien bleiben nutzbar, jedoch ohne Voice-Memo-Bypass. Dateitypen sind keine automatische Funktionsfreigabe.
4. **Sicherheits-/Privacytests:** Überzeugend prüfen, dass Chat-An, Typing-An, Mention, Dateiupload, Offline-/Reconnect, SL-Modus und Rollentausch keinerlei Chat-Mikrofonaufnahme, Audio-Autoplay, Voice-Transcript oder öffentliche geheime Audio-Metadaten anstoßen.
5. **Bestehende Rechte testen:** 02.106-/02.107-Empfängerschutz, 02.108-/02.109-Moderation, 02.110-Mutes/DM-Blocks, 02.116-A-Read-Receipt-Verbot und 02.118-A-Draft-Verbot werden nicht durch einen Audio-Sonderpfad umgangen.
6. **UI/MVP später:** Die generelle Chat-/Mediendarstellung wird im späteren UI-Workshop entschieden. Dort keine eingeschlossene Chat-Sprachnachrichtenaufnahme vortäuschen. Dieser Beschluss ist fachlich fixiert; noch keine Implementierung.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| SL erstellt Kampagne mit 02.105 Chat An | Normaler berechtigter Chat möglich; keine integrierte Sprachnachrichtentaste oder Voice-Memo-Option |
| SL schaltet den Chat vollständig Aus | Keine normale Chat-/Voice-Memo-Bedienung, externe Voicechatnutzung und offizielle Notices/Acks bleiben eigenständig |
| Spieler öffnet DM, Gruppen- oder SL-Chat | Keine Chat-Mikrofonberechtigungsanfrage/Audio-Capture-Session |
| Spieler sucht `Sprachnachricht aufnehmen` | Kein versteckter Recorder, kein Voice-Clip-Editor oder Aufnahmestart über Hotkey |
| Spieler schreibt normal mit zwei Absätzen | 02.121 A: mehrzeiliger Klartext mit Leerzeile, keine Voice-Message-Sendestufe |
| Externer Voicechat funktioniert | Der Chat-Beschluss deaktiviert kein externes Gespräch |
| SL nutzt 02.51-Sound- oder Alarm-Node | Welt-/Szenensound unabhängig nutzbar; keine Aufzeichnung einer Chatstimme |
| Spieler erstellt berechtigte Umfrage (02.120) | Poll wie geplant, keine Audioaufnahme, kein Soundautoplay |
| Spieler aktiviert 02.119-Schreibindikator | Keine Mikrofonanfrage, keine Audiolevels oder Voice-Speaker-Status |
| 02.114 erlaubt ein generisches Dateiformat | Nur individuell zugelassener und geprüfter Datei-/Linkpfad, kein automatischer Voice-Memo-Record-/Player-/Transcribe-Bypass |
| 02.114 erlaubt keine Audiodateien | Kein Audio-Dateiupload allein durch abgeleitetes 02.122-A-Recht |
| Audio-URL wird als Text geteilt | Nur reguläre sichere 02.114-Linkberechtigung, kein ungefragtes Audio-Autoplay |
| Client sendet gefälschten `voiceMessageCreate`-Aufruf | Kein solcher Chat-Featureweg wirksam, kein Server-Record-/Audioarchiv |
| Spieler verwendet zwei Geräte/unterbricht Verbindung | Kein Voice-Clip-Entwurf, kein Auto-Reconnect-Audiosenden, 02.118 A bleibt |
| Blockierter DM-Sender will Voice-Memo als Umgehung verwenden | Keine neue Umgehungszustellung, reguläre 02.110-Blockrechte gelten |
| Neue Gruppenperson errät alte private Datei-/DM-ID | Keine Audio-/Message-/Datei-/Member-Leaks über Chat-Sonderweg |
| 02.108-Edit/02.109-Moderation an bestehendem erlaubtem Text | Gewöhnliche Rechte und Revisionen gültig, keine geheime Audio-Version |
| 02.117-Volltextsuche nach Voice-Memo-Transkript | Kein automatisch erzeugtes/transkribiertes Voice-Memo-Datenobjekt |
| 02.116 A schließt individuelle Lesebestätigungen aus | Kein Delivery-/Read-Receipt bei Text und kein Voice-Playback-Tracking |
| Rechtmäßige 02.101-Korrektur benötigt bewussten 02.102-Ack | Weiter eigener amtlicher Ackprozess, nicht durch externe Sprachnachricht ersetzbar |
| Spieler spricht `Tür öffnen` extern oder teilt nur Text | Keine automatisch echte Door-/NPC-/Node-/Quest-/Würfel-/Turnwirkung |
| Kampagnenpreset versucht `Voice-Memo An` zu setzen | Keine solche Kampagnen-/Kanal-/Rollenfreigabe trotz 02.25-Ausnahmen |
| Rückkehr aus externer Voiceanwendung in Chat | Kein Mikrofonaktivitäts-/Transkript-/Aufnahmezustand wird von AdventureShift gespeichert |

## 7. Beschlussgrenze und nächste Featurefrage

**Verbindlich beschlossen: 02.122 A – keine integrierten Chat-Sprachnachrichten oder speziellen Audio-Clips.** Kein Voice-Memo-Aufnehmen/Senden/Abspielen, keine Chat-Mikrofonberechtigung, Voice-Transkription, Autoplay, Sprachclip-Historie oder entsprechender 02.25-Teilmodulschalter. Externer Voicechat, 02.51-Sound-/Szenenmodule, tatsächlich genehmigte 02.114-Dateien und die Text-/System-/Notizfunktionen bleiben **unabhängig**. Alle 02.105–02.121-ACL-/Retention-/Secret-/Moderationsentscheidungen gelten weiter, insbesondere **02.116 A ohne persönliche Chat-Read-/Delivery-Receipts**, **02.118 A ohne gespeicherte Entwürfe** und **02.121 A mit einfacher Absatztext-Eingabe**. Kein Voice-Memo-Modul kann echte 02.102-ACKs oder 02.99-Spielweltaktionen ersetzen.

**Nicht beschlossen:** Ein globales Verbot sämtlicher Audio-Dateiformate oder aller Weltgeräusche; zusätzliche Einschränkungen gegenüber dem bereits separat konfigurierbaren 02.114-Anhangmodul; universelle Mikrofonregeln für fremde externe Anwendungen; neue Auth-/Hosting-/MVP-/UI-Verträge. Eine spätere Chat-Voice-Memo-Funktion benötigt einen neuen Beschluss.

## Nächste Entscheidung 02.123 – Chatnachrichten weiterleiten und bewusst in anderen Kanälen teilen

**Beispiel:** Ein Spieler will eine frühere Gruppenchat-Nachricht offiziell in einen anderen berechtigten Teamkanal weiterleiten. Dabei darf eine geheime private DM weder samt Absender noch ihren Bildern/Dateien unbemerkt in einen öffentlichen Kanal kopiert werden.

- **A – Keine systemseitige Weiterleitung:** Keine „Weiterleiten“-Funktion für Nachrichten. Spieler können berechtigt lesbare Inhalte höchstens selbst als gewöhnlichen Text neu schreiben; 02.106-/02.107-Chat- und Moderationsrechte bleiben.
- **B – Unbegrenztes Weiterleiten:** Jeder darf beliebige Nachrichten, DMs, Autoren, History, Polls und Anhänge ungeprüft in andere Bereiche kopieren, selbst bei fehlenden Quell-/Empfängerrechten.
- **C – Konfigurierbares, geschütztes Weiterleiten (Empfehlung):** Bei 02.105 Chat An kann die SL nach 02.25-Kampagnen-/Kanal-/Rollen-/Personenstandards und gültigen Ausnahmen eine echte Weiterleitungsfunktion zulassen, nur wenn der Sender den Originaltext **heute UND historisch nach 02.107** lesen darf und im neuen Zielkanal wirklich 02.106-senden darf. Ziel- und Quellenempfänger, 02.108-Revisionen, 02.109-Moderation, 02.110-Blocks, 02.113-Quote-/Thread- und 02.114-Medien-/Assetrechte werden separat geprüft. Fremde private DMs, Autoren-, Rechte- oder Anhangsmetadaten werden nicht versehentlich veröffentlicht; neue Weiterleitung ist ein eigener expliziter neuer berechtigter Send-Commit ohne Welt-/ACK-Wirkung. UI später.
