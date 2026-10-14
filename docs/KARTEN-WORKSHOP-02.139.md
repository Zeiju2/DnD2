# AdventureShift – Karten-Workshop: Beschluss 02.139 A – keine besonderen visuellen Audio-Cue-Hinweise

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.139; nächste offene Entscheidung 02.140.
**Status:** Verbindlicher Fachbeschluss mit konzeptioneller Umsetzungs-/Negativtestplanung; **noch keine Softwareimplementierung**, keine finalen APIs, DB-Schemata, UI oder MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnenstandards und gültige markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.49–02.51 – unabhängig geregelte sichtbare Schall-/Hörbarkeits- und Sensorfunktionen](KARTEN-WORKSHOP.md) · [02.99 – echte autorisierte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – amtliche Systemhinweise und bewusste ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – optionaler Chat](KARTEN-WORKSHOP-02.105.md) · [02.106–02.107 – Chat-/Empfänger-/Historyschutz](KARTEN-WORKSHOP-02.107.md) · [02.116 A – keine Chatlesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.122 A – keine Chat-Sprachnachrichten](KARTEN-WORKSHOP-02.122.md) · [02.126 C – separate Chat-Benachrichtigungen](KARTEN-WORKSHOP-02.126.md) · [02.132 C – optionales Musik-/Playlist-/Soundboardmodul](KARTEN-WORKSHOP-02.132.md) · [02.133 A – nur lokaler Player, kein globaler Musik-Sync](KARTEN-WORKSHOP-02.133.md) · [02.134 C – lokal konfigurierbare Fades/Loops/Layer](KARTEN-WORKSHOP-02.134.md) · [02.135 C – berechtigte Audio-Vorlagen](KARTEN-WORKSHOP-02.135.md) · [02.136 C – kontrollierte Vorlagenrevisionen](KARTEN-WORKSHOP-02.136.md) · [02.137 A – feste Audio-Vorlagen](KARTEN-WORKSHOP-02.137.md) · [02.138 C – optionales lokales Soundboard-Ducking](KARTEN-WORKSHOP-02.138.md).

## 1. Verbindliche Entscheidung – Variante 02.139 A

**Der Projektinhaber hat ausdrücklich A gewählt:** Für Musik-/Playlist-/Soundboard-Wiedergabe wird **kein spezielles visuelles Audio-Cue-Hinweis-/Caption-/Icon-/Untertitel-/Toast-Modul** vorgesehen. Der Player zeigt **nicht zusätzlich aufgrund eines gerade ausgelösten Soundboard-/Musik-Cues** Hinweise wie „Glocke läutet“, automatisch erscheinende Audiosymbole, eine gesonderte Geräuschereignisliste, visuelle Takt-/Soundlabels oder eine nach Audioereignissen generierte barrierefreie Caption-Inbox an. **Kein 02.25-Default, keine Rollen-/Gruppen-/Personenausnahme und kein individueller Anzeige-Opt-in** schaltet diese ausdrücklich abgewählte Cue-spezifische Komfortfunktion verborgen wieder ein.

**Beispiel:** Die SL löst im separaten optionalen 02.132-Musik-/Soundboardmodul einen berechtigten Glocken-Cue aus. Berechtigte Hörer können ihn nach ihren lokalen Player-/Mute-/Browserregeln hören. Stummgeschaltete Personen erhalten **keinen besonderen neu eingeblendeten „Glocke läutet“-Audiohinweis**. Wenn diese Information spielerisch wichtig ist, kann die SL bewusst einen bereits vorhandenen erlaubten Kommunikations-/Szenen-/Systemweg verwenden – ohne dass die Audiodatei oder ihr Titel dadurch automatisch zum Text- oder Welt-Event wird.

**Nicht gewählt:** B (alle geheimen Cues und Tracks unberechtigt als Text) und C (konfigurierbare zusätzliche berechtigte Cue-Captions). **A ist kein Verbot allgemeiner Barrierefreiheit oder der getrennten, bereits beschlossen geregelten visuellen 02.49–02.51-Schall- und Systemanzeigen.**

## 2. Abgrenzung: kein Audio-Captionmodul, bestehende Informationswege bleiben

1. **Ausgeschlossene Sonderfunktion:** Kein `AudioCueCaption`, `SoundboardVisualCueOverlay`, `AudioEventSubtitle`, `AudioCaptionNotification`, `AudioCueVisualAccessibilityFeed` oder vergleichbares neues Audio-spezifisches API-/Realtime-/DB-/Settings-Modul. Dies sind konzeptionelle **nicht zu implementierende** Typen, keine endgültigen API-Namen.
2. **Normale bestehende UI-Metadaten bleiben:** Die **bei bestehendem 02.132-C-Recht** bereits erlaubte Anzeige von Playlist-/Tracknamen, Auswahl, erlaubten Audioasset-/Lizenzangaben, eigenen Mute-/Lautstärkereglern und gewöhnlichen Bedienelementen wird durch A nicht abgeschafft. Sie stellt **keinen zusätzlich beim Abspielen erzeugten Texthinweis** über ein Geräusch dar. Nicht berechtigte erhalten auch über normale UI keine geheimen Audioinformationen.
3. **Allgemeine Barrierefreiheit bleibt:** Gewöhnlich bedienbare UI, Tastatur-/Screenreader-Zugänglichkeit regulärer bereits berechtigter Bedienelemente, Kontrast, Lesbarkeit und die getrennte spätere UI-Barrierefreiheitsplanung bleiben zulässig. **Kein** verstecktes durch den Audio-Cue ausgelöstes Text-/Icon-Signal allein unter dem Deckmantel dieser allgemeinen Anforderungen.
4. **Bereits beschlossene visuelle 02.49–02.51-Schallhinweise:** Ein regelkonform autorisiertes **echtes Spielwelt-Schall-/Szenenereignis** darf weiterhin gemäß den früheren eigenständigen Sicht-/Schallbeschlüssen grafisch dargestellt werden, auch wenn das Musikmodul Aus ist. **02.139 A** betrifft nur **zusätzliche Audio-/Soundboard-Cue-Captions** aus dem 02.132-Musikplayer; ein Playback-Cue wird **nicht** zu einem echten 02.51-`SoundEvent`.
5. **Würfel-/Systemfeed und offizielle Notices:** Wirkliche 02.101–02.104-Systemhinweise, ACKs/Reminder sowie autorisierte Würfel-/Spielsystemereignisse bestehen unabhängig, selbst wenn Musik/Chat Aus sind. Kein Ersatz durch automatisch generierte Musik-Captions, kein verlustiges Zusammenlegen dieser Informationswege.
6. **SL kommuniziert bewusst:** Die Spielleitung kann Informationen weiter über **selbst autorisiert getätigte** normale manuelle Spiel-/Journal-/Chat-/Kartenaktionen oder Voicechat vermitteln; bei 02.105 Chat Aus bleibt Voicechat-first und manuelle SL-Kommunikation möglich. Dies ist eine **neue bewusste Aktion**, keine automatische Weiterleitung, kein aus Musiktext erzeugter 02.99-Welteffekt und kein neuer privilegierter Chat-/DM-/Historyzugang.
7. **Keine Audio-Transkription:** Keine Mikrofon-/Voicechataufnahme, Tonanalyse, KI-Transkription, automatisch erzeugten Track-/Cue-Beschreibungen oder Chat-Voice-Memo-Funktionen. 02.122 A bleibt negativ; es gibt keinen heimlichen zusätzlichen externen Anbieter, Mikrofonrecht oder Audioüberwachungsdienst.
8. **Echte Geheimnissperren bleiben:** Auch die **ausgeschlossene** Cue-Caption-Funktion darf nicht als Platzhalter über Count, unread, Toast, Push, A11y-Live-Region, Suchfacet, automatisch zugefügtes Icon, Tooltip, Timestamplücke, Hörerstatus oder Cache für geheime Cues auftauchen. Asset-/Scene-/Empfänger-/Actor-/Lizenz-/Retentionrechte aus 02.132 und 02.25 bleiben gültig.

## 3. Integrationsgrenzen der vorherigen Beschlüsse

| Frühere Entscheidung | Unveränderliche Wirkung |
| --- | --- |
| **02.25 / 02.132 C** | Musik-/Playlist-/Soundboard-An-/Aus und gültige Cue-/Owner-/Asset-/Lizenz-/Recipient-Rechte; **keine** zusätzliche 02.139-Option „visuelle Cue-Hinweise an“ |
| **02.133 A** | Jeder Hörer startet Musik lokal von vorn; **keine** Cue-Captionzeitstempel als verdeckte gemeinsame Wiedergabeuhr, kein Join-/Reconnect-Catch-up |
| **02.134 C** | Erlaubte lokale Fade-/Loop-/Musik-/Soundboard-Layer funktionieren weiterhin ohne gekoppelte Cue-Untertitel |
| **02.138 C** | Eigener berechtigter Cue kann weiterhin eigene Musik-/Ambient-Layer vorübergehend absenken; **keine** automatisch erzeugte „Cue spielt“-Kachel/Captions |
| **02.135-/02.136-C und 02.137 A** | Audio-Vorlagen/Revisionen/feste Einfügung bleiben; keine visuelle Cue-Caption als neues Audio-Einfügefeld oder Vorlagenupdatezwang |
| **02.49–02.51 / 02.99** | Echte getrennt autorisierte sichtbare Schall-/Node-/Weltaktionen sind nicht betroffen. Abspielen von Soundboard-„Alarm“ erzeugt niemals selbst neue Spielwelt-Schallgrafik, Sensor-/Node-/Alarm- oder Door-/Quest-Wirkung |
| **02.101–02.104** | Offizielle Notices/Reminder/ACKs bleiben voll funktionsfähig; Audio-Cue-Hören erzeugt keine bewusste 02.102-Kenntnisnahme |
| **02.105-/02.106-/02.107-Chat** | Chat bei Erstellung separat An/Aus; manuelle zulässige Texte brauchen normale heutige **UND historische** Channel-/Empfängerrechte, kein automatisch erzeugter Chat-Cue |
| **02.116 A / 02.122 A / 02.126 C** | Keine persönlichen Chat-Read-/Delivery-Receipts, keine Chat-Voice-Memos und keine neuen Cue-Caption-OS-Pushes aus Chat-Benachrichtigungen |
| **Allgemeines UI/A11y** | Reguläre zugängliche Musiksteuerung und separat geregelte allgemeine Zugänglichkeits- und Spielerhinweisfunktionen bleiben; kein neues Cue-spezifisches Untertitelmodul |

## 4. Konzeptioneller Umsetzungsausschluss

1. **Negativer Capability-Vertrag:** Die 02.132-C-/02.25-Musikmodulliste enthält **keine** `audioVisualCueHints`, `autoCueCaptions`, `soundboardSubtitleFeed`, `captionOnMute` oder ähnliche freischaltbare 02.139-Unterfunktion. Es gibt kein gesondertes per-Kampagne-/Personen-Cue-Caption-Preferenceobjekt, das die Funktion durch Ausnahme doch ausführt.
2. **Keine zweite Message-/Eventquelle:** Reines Musik-/Soundboard-Abspielen und 02.138-C-Ducking publizieren **keine** eigenen Chatmessage-/journal-/systemnotice-/systemfeed-/szenen-/Screenreader-Live-Region-/OS-Notification-Captionereignisse. Nur getrennte, fachlich ausdrücklich berechtigte Spielwelt-/System-/SL-Aktionen benutzen ihre eigenen ursprünglichen Quellen.
3. **Datenmodell-/Transporttrennung:** Kein besonderer CueCaption-Datensatz, keine Caption-Unreadzähler, visuelle Audioeventhistorie, Caption-Realtime-Abonnements, Caption-Suche/Export oder unberechtigter Cache. Normale bereits notwendige sichere Audioasset-/Track-/Cue-Metadaten sind nur nach tatsächlicher 02.132-ACL aufzulösen.
4. **Keine fremde Feature-Uminterpretation:** Weder 02.49 visuelle Szenenschallmarker, 02.51-Schallphysik, 02.126-Chatbenachrichtigung noch 02.131-Systemevent-Chatreferenz darf **allein wegen** einer 02.132-Musik-/Soundboard-Abspielaktion zur versteckten 02.139-Captionschicht werden.
5. **Hörerprivatsphäre und Persistenz:** Ein selbst stummgeschalteter Nutzer gibt dadurch **keine** Berechtigung frei, die gehörten/nichtgehörten Cues als Text für sich oder andere zu protokollieren. Es gibt keine individuelle wer-hat-Cue-gelesen-/gesehen-Historie. Bestehende echte Audio-/Lizenz-/Kampagnen-/Empfängerrechtsprüfung bleibt serverautoritativ.
6. **Technische Arbeit später:** Normale Bedienelement-Zugänglichkeit, lizenzkonforme Audiofiles, Browser-/Betriebssystem-Consent, UI-Layouts, MVP und Medien-/Szenen-Sichtbarkeit bleiben gesonderte Planungsthemen. 02.139 A ist kein pauschaler Ausschluss allgemeiner Barrierefreiheit und keine neue technische Umsetzung eines Screenreader-Sound-Deskriptors.

## 5. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| 02.132-Musik An, SL startet berechtigten Glockenton | Hörer darf ihn lokal hören, **kein** automatisch eingeblendeter Cue-Text „Glocke läutet“ |
| Hörer hat Musik bewusst stummgeschaltet | Keine ersatzweise automatisch erzeugte Caption, kein neuer Cue-Hinweisfeed |
| 02.25-Ausnahme „Audio-Captions für Gruppe A“ versucht | Keine solche 02.139-Unterfunktion; A ist verbindlich und nicht per Ausnahme umgehbar |
| Client sendet manipuliertes `soundboardSubtitleFeed=true` | Keine Freischaltung, kein Caption-Endpoint/Realtime-Abo |
| SL gibt manuellen Text im normal berechtigten Chat frei | Normale 02.105–02.107-Nachricht nur nach echten Chatrechten möglich, kein automatischer Audio-Cue-Forward |
| Chat bei Kampagnenerstellung Aus, Musik An | Rechtmäßiges Music-Playback weiterhin; keine versteckte Aktivierung von Chat oder Caption-Toast |
| Musik Aus, echtes 02.51-Schallereignis sichtbar freigegeben | Eigenständige vorher beschlossene Spielwelt-Schallvisualisierung bleibt erlaubt |
| Musik An, 02.51-Spielszenenschall Aus | Audiowiedergabe erzeugt keine neue Schallwellen-/Sensoranzeige |
| Audiofile heißt `alarm.mp3` | Kein echter 02.49–02.51-Sensor-/Alarm-/Node-/Tür-/NPC-/Quest-Effekt |
| SL nutzt vorhandene berechtigte manuelle Karten-/Szenenanzeige | Vorhandenes separat autorisiertes Kartenfeedback bleibt; kein Zwangscaption aus Cue |
| Offizielle 02.101-Korrektur erfordert ACK | Notice/ACK/Reminder bleiben unabhängig, Hören/Stoppen/Mute quittiert nicht |
| Echte Würfel-/Systemevents werden zusätzlich im Chat angezeigt (02.131 C) | Nur bereits eigenständig autorisierte Ereignisreferenzen; kein Audio-Cue-Captionbypass |
| Playlistliste enthält erlaubten Tracknamen | Reguläre berechtigte Player-/Auswahlmetadaten weiterhin möglich, **kein** zusätzlicher Ereignis-Unteritel bei Start |
| Geheimer Track von fremder Gruppe | Kein Titel, Preview, Count, A11y-Caption, OS-Toast oder Zeitstempel-/Existenzleck |
| Audio-Cue ist durch Berechtigungsentzug unzulässig | Kein Mediaabruf und keine Text-/Icon-/Unread-/Push-Schattenbenachrichtigung |
| 02.138-C-Ducking senkt eigene Musik kurz ab | Ducking wirkt lokal, ohne zusätzliche visuelle Absenkungs-Caption |
| 02.134-C-Crossfade läuft zwischen zwei berechtigten Tracks | Lokale Mischung funktioniert ohne Untertitel-/Captionlayer |
| Spieler startet Track später oder reconnectet | Kein globaler Playhead/AutoJoin nach 02.133 A und kein Caption-Catch-up |
| Soundboardvorlage wird nach 02.135 C rechtmäßig kopiert | Keine automatisch neue Caption-Konfiguration, kein fremder Medienzugriff |
| Source-Template erhält geprüftes Update nach 02.136 C | Keine automatische Wiedergabe, Textcaption oder Änderung einer Zielplaylist |
| Feste Audiovorlage aus 02.137 A eingesetzt | Keine zusätzlichen Audio-Caption-/Untertitel-Insertparameter |
| Allgemeines UI mit Tastatur/Screenreader bedient | Reguläre berechtigte Musik-/Mute-/Volume-Regler bleiben zugänglich |
| Screenreader fokussiert berechtigten Play-Button | Standard-Accessible-Name für Steuerelement möglich, aber keine automatisch generierte Cue-„Glocke läutet“-Live-Nachricht |
| Externer Voicechat wird genutzt | Kein Audio-Sampling/Voice-/Mikrofonmitschnitt oder automatische Sprache-zu-Text-Pipeline |
| 02.122 A keine Chat-Voice-Memos | 02.139 A erschafft keinen neuen Audio-/Chat-Sprachnachrichtenpfad |
| 02.116 A keine individuellen Chat-Lesebestätigungen | Auch keine Audio-Cue-„gelesen“-/„gesehen“-Records |
| 02.126-C-Chat-Notifications eingeschaltet | Nur vorhandene berechtigte Chatmessages benachrichtigen; keine Musikcaption-Badge-/Toast-Erweiterung |
| Besondere Textnotiz durch berechtigte SL nach manuellem Spielereignis | Die SL-Notiz folgt eigenen Notiz-/Empfänger-/Sichtbarkeitsrechten, nicht automatischem Musiktext |
| Audio-Cue-Name enthält `Tür öffnen` | Kein 02.99-Welt-/Node-/Quest-/Door-/Turn-/Inventareffekt und kein automatisch vorgerendertes Audio-Cue-Label |
| Spieler aus Kampagne B errät Audioszenen-ID aus A | Kein Audio-/Titel-/Cue-Caption-/Metadaten-/Fehlertextzugriff über Kampagnengrenze |
| Audio-Cue per Link in fremdem DM erwähnt | Keine automatische Freigabe von Audio-Datei-/DM-/Historienrechten |
| Musikliste aktualisiert berechtigt ausgewähltes Asset | Gewöhnliche Playerliste/Assetberechtigungen bleiben, keine neu erzeugte Sound-Caption-History |
| Temporärer Browser-Tab suspendiert/fortgesetzt | Kein nachgeholter visueller Cue-Feed, kein automatische neue Musik-Synchronisation |
| Musikdatei wurde nach Lizenzende unzugänglich | Keine neue Auslieferung über Musikplayer oder visuelle Cue-Captions |
| Client fragt systematisch nach nicht erlaubten Audio-Cue-IDs | Kein zusätzlicher Such-/Count-/Existenzkanal; serverseitige Music-ACL gilt |
| Hörer hat persönliche Lautstärke gering eingestellt | Keine fremde Lautstärkeänderung und kein automatisches visuelles „leise“-Cue-Feedbackmodul |
| Allgemeine UI-Barrierefreiheitsplanung erfolgt später | Keine Beschädigung regulärer A11y-Bedienbarkeit; A schließt ausschließlich spezielle Cue-Captions aus |

## 6. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.139 A – keine zusätzlichen visuellen, beim Musik-/Soundboard-Cue automatisch erzeugten Text-/Symbol-/Untertitel-/Caption-/Toast-Hinweise.** Weder Modulschalter, persönliche Auswahl noch 02.25-Ausnahmen dürfen diese Audio-Cue-spezifische Funktion wieder einführen. Allgemeine zugängliche reguläre UI-Bedienelemente, rechtmäßig sichtbare Playlistmetadaten, SL-bewusst gesendete Hinweise, echte 02.49–02.51-Schallvisualisierungen und amtliche 02.101–02.104-Notices/ACKs bleiben bestehen. 02.132 C Musikmodul optional, 02.133 A keine Synchronisation, 02.134 C lokales Mixing, 02.135-/02.136 C sichere Audio-Vorlagen/Updates, 02.137 A feste Audio-Insertwerte und 02.138 C gerätelokales Ducking werden **nicht** eingeschränkt. Keine neuen World-/Sensor-/Node-/Quest-/ACK-Wirkungen aus Musikplayback.

**Nicht beschlossen:** abschließende allgemeine UI-Barrierefreiheits- und Lesbarkeitsstandards, Playerengine/Codec-/Audiozulieferer, konkreter regulärer Playerbildschirm, finale API/DB-/MVP-Priorisierung. Es bleibt Fachplanung, keine fertige Software.

## Nächste Entscheidung 02.140 – Privates Probehören von Musik- und Soundboarddateien im Editor

**Beispiel:** Die SL möchte in der Audioverwaltung vor dem Einsatz prüfen, ob ein rechtmäßig verfügbares Regen- oder Glocken-Audio zu einer Szene passt. Andere Spieler sollen weder den Testton hören noch dadurch von einer geheimen Szene, einem verborgenen Cue oder einer privaten Audiodatei erfahren. Probehören soll keine echten Spielwelt-SoundEvents oder Chat-Nachrichten erzeugen.

- **A – Kein integriertes Probehören:** Tracks und Cues werden ausschließlich über normale berechtigte Wiedergabe-/Bearbeitungswege getestet; kein eigener privater Vorschauplayer im Editor.
- **B – Jede Vorschau für alle:** Alle Benutzer dürfen jedes geheime Audioasset hören, und ein Probeton wird allen Teilnehmern auch ohne Asset-/Rollen-/Szenenrechte zugestellt.
- **C – Konfigurierbares privates Probehören (Empfehlung):** Bei aktivem 02.132-Musikmodul darf die SL nach 02.25-Defaults/markierten Ausnahmen geeigneten Rollen und Personen eine **nur auf ihrem eigenen Gerät hörbare Vorschau auf tatsächlich lizenz-/asset-/szene-/empfängerberechtigte Musik-/Soundboarddateien** im Editor gestatten. Keine neue öffentliche Cue-/Kampagnennachricht, keine Zuschauer-/Hörerstatistik, kein globaler 02.133-A-Sync, kein Voicechatmitschnitt, kein 02.49–02.51-SoundEvent-/Node-/Alarm-/World-/ACK-Effekt; 02.139 A weiterhin ohne zusätzliche visuelle Audio-Captions. Konkrete UI/Playbackgrenzen später.
