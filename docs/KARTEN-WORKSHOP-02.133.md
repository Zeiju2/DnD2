# AdventureShift – Karten-Workshop: Beschluss 02.133 A – nur lokale Musikwiedergabe ohne gemeinsame Synchronisation

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.133; nächste offene Frage 02.134
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungs- und Abnahmetestplan; **keine Softwareimplementierung**, kein finales UI, kein verbindliches Datenbankschema/API und keine MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnenstandards/markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.49–02.51 – unabhängiges Schall-/Sensor-/Node-Modell](KARTEN-WORKSHOP.md) · [02.99 – echte autorisierte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – amtliche Notices/ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.110 – Channel-Mute/DM-Block](KARTEN-WORKSHOP-02.110.md) · [02.114 – geschützte Dateien](KARTEN-WORKSHOP-02.114.md) · [02.116 A – keine individuellen Chatlesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.122 A – keine integrierten Chat-Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.126 – Chatbenachrichtigungen](KARTEN-WORKSHOP-02.126.md) · [02.131 C – Quell-Würfel-/Systemevent-Referenzen](KARTEN-WORKSHOP-02.131.md) · [02.132 C – optionales Musik-/Playlist-/Soundboardmodul](KARTEN-WORKSHOP-02.132.md) · [Lizenz-/Assetfragen](LIZENZEN.md).

## 1. Verbindliche Entscheidung – Variante 02.133 A

**Der Projektinhaber hat ausdrücklich A gewählt:** Es gibt **keine gemeinsame, synchronisierte Wiedergabeposition, keinen globalen Play-/Pause-/Seek-Fortschritt, keinen Wiedergabe-Catch-up und keinen automatischen Musikeinstieg bei Join oder Reconnect**. Jede berechtigte Person spielt Audio auf ihrem eigenen Gerät eigenständig ab; **jeder eigenständig gestartete Track beginnt am Titelanfang**. Unterschiedliche Spieler dürfen absichtlich unterschiedliche Positionen erreichen, unabhängig pausieren, früher aufhören oder Musik völlig stummschalten.

**Beispiel:** Die SL hat eine berechtigte Tavernenplaylist zur Verfügung gestellt. A beginnt Track 1 lokal um 19:00 Uhr, B startet denselben Track zehn Minuten später und hört ihn von Beginn an. C tritt noch später bei: C erhält nur aktuell berechtigte Musikauswahl und darf selbstständig starten, wird **nicht** in As oder Bs Zeitposition hineingezogen. Ein Reconnect übernimmt keine zentrale Trackposition und löst kein unbemerktes Neu- oder Weiterspielen aus.

**Nicht gewählt:** B (erzwungene exakt synchrone Wiedergabe selbst gegen private Mutes/Browserregeln) und C (konfigurierbarer gemeinsamer Sessiontransport mit Track-/Queue-/Abspielposition für Late-Join). A ist **keine** abwählbare 02.25-C-Variante: Es gibt keinen versteckten SL-/Kanal-/Personenmodus, der globales Playback-Seeking oder einen Session-Clock-Sync wieder freischaltet.

## 2. Abgrenzung zu 02.132 C – Musikverwaltung bleibt, Transport ist lokal

1. **Musikmodul bleibt optional:** 02.132 C ist weiterhin verbindlich: Bei Kampagnenerstellung Musik-/Playlist-/Soundboardfunktion wirklich **An/Aus**, getrennt von 02.105-Chat und 02.49–02.51-Schall. Nicht jeder Spieler muss den Player verwenden.
2. **Gemeinsame Organisation ja, gemeinsame Abspieluhr nein:** Zulässige SL-/Rollenbefugnisse zur Auswahl, Pflege und Freigabe von Playlists, Trackempfehlungen und Soundboard-Cues bleiben. Konzeptionell werden **berechtigte Musikauswahl-/Cue-Angebote** oder rechtmäßige Steuerabsichten kommuniziert, **nicht** ein verbindlicher globaler `currentlyPlayingOffset`-/`sharedTransportPosition`-/`syncedPlayhead`-Zustand gespeichert oder übertragen.
3. **Manuell/SL-bestätigt/automatisch:** Die 02.132-C-Betriebsmodi betreffen nur **wer welche Musik/Cues auswählen, vorschlagen, freigeben oder für einen rechtmäßig eingeschalteten lokalen Player als neuen Start-Cue anbieten darf**. Ein erlaubtes Szenenereignis kann eine für den Empfänger erlaubte Trackauswahl signalisieren. Es erzeugt **keinen** global synchronisierten Startzeitpunkt und **keinen** Join-/Reconnect-Nachhol-Cue. Wenn nach gesonderter gültiger Audio-/Browser-/Nutzerfreigabe ein aktueller lokaler Cue startet, beginnt der Titel bei **0**, niemals bei einer errechneten Position anderer Hörer.
4. **Hörerautonomie:** Persönliche Volume-/Mute-/Play-/Pause-/Stop-Entscheidungen bleiben lokal. Bereits entschiedene SL-Rechte, Audioquellzugang oder Playlistorganisation berechtigen **nicht**, den Browser zu übersteuern, andere Geräte unbemerkt zu starten oder persönliche Hardwarelautstärke zu manipulieren.
5. **Kein globaler Transportstatus:** Ein optionaler technischer Steuerungs-/Berechtigungszustand (z. B. welche Playlist im Szenenkontext ausgewählt oder ob ein Asset noch erlaubt ist) ist **nicht** gleichbedeutend mit `playing`, `paused`, `positionMs`, `startedAtServerTime` oder einem fortlaufenden Server-Zeitanker. Play/Pause/Seek jedes Empfängers sind lokale Gerätezustände, kein für andere berechtigter Live-Telemetriefeed.
6. **Kein Trackende über gemeinsame Uhr:** Automatische lokale Weitergabe/Loop/Überblendung ist, falls später beschlossen, eine **geräteindividuelle** Funktion. Andere Player werden nicht durch Ende oder Fortschritt eines Hörers mitgezogen. Umfang/Fades/Mixing unter 02.134 separat klären.
7. **Begrenzung rückwirkender Änderungen:** Eine Änderung der zulässigen Playlist/Scene/Audioassets erfordert künftig neue Autorisierungsprüfungen; sie darf aber nicht unter dem Vorwand einer Sessionuhr alle Player an eine gemeinsame Zeit springen lassen. Rechteentzug stoppt neue unzulässige Zustellung und gebotene lokale Wiedergabe, soweit tatsächlich technisch durchsetzbar; bereits gehörte Klänge sind nicht rückwirkend löschbar.

## 3. Join, Reconnect, Szenenwechsel und Rechte

| Situation | Verbindliches Verhalten |
| --- | --- |
| Spieler betritt Kampagne spät | Nur jetzt berechtigte Track-/Playlistinfos; **kein** Start von selbst und keine Position anderer Hörer |
| Neuer Hörer startet freiwillig erlaubten Track | Beginnt lokal bei Titelanfang, auch wenn die SL oder andere schon weiter sind |
| Browser-Neuladen/Reconnect | Kein serverseitiger Offset, kein Nachholen verpasster Start-/Pause-/Seek-Events, kein erzwungenes Autoplay |
| Verbindungsabbruch während eigener Wiedergabe | Ob ein bereits lokaler Player technisch weiterlaufen kann, hängt vom Gerät/Assetzugriff ab; **keine** versprochene gemeinsame Fortsetzung |
| Zwei berechtigte Spieler hören denselben Track | Zeitliche Abweichungen sind zulässig; keine gemeinsame Clock-/Driftkorrektur |
| SL legt andere Szene/Playlist fest | Berechtigte neue Auswahl/Cues möglich; kein automatischer gemeinsamer Seek oder Backfill für Offline-Spieler |
| Hörer hat eigene Volume-/Mutepräferenz | Bleibt unter eigener Kontrolle, unabhängig von SL-Playback-/Playlistrechten |
| Browser blockiert Playback | Keine Zwangswiedergabe oder Umgehung von Autoplay-/Audio-Zustimmung |
| Geschützte Asset-/Szenenrechte werden entzogen | Kein zukünftiger verbotener Assetstream/Playlist-/Tracktitel/Artwork; kein Position-/Cuecache als Rechteumgehung |
| Kampagnenchat ist Aus | Eigenständig erlaubtes 02.132-Musikmodul kann weiter funktionieren |
| Musikmodul ist Aus | Kein neuer Musik-/Cue-Clientpfad; Chat, Würfel, Notizen, 02.51-Schall/Systemfeed unabhängig |
| 02.49–02.51-Akustik/Alarm/Sensor aktiviert | Audioplayer ist kein echter Game-SoundEvent-/Hörbarkeits-/Node-/Alarm-Auslöser |
| 02.102 amtliche Bestätigung offen | Playerstart, Stop, Pause und Reconnect erzeugen kein offizielles ACK |

## 4. Konzeptionelle Architekturentscheidung

- **Negativer Syncvertrag:** Kein `CampaignSharedMusicPlayhead`, `GlobalAudioPlaybackClock`, `SessionPlaybackOffset`, `SharedTransportPlayingState`, `AutoJoinAtLiveOffset`, `ResumeSyncedMusicOnReconnect`, `forceSyncToSessionMusic`, Client-Driftkorrektur-, per-SL-/per-Personen-Playbackzwang oder globale Seek-/Pause-/Resume-Synchronisierungsfähigkeit als Teil von 02.133. Auch kein 02.25-Override, der das explizit abgewählte Modul wieder einführt.
- **Erlaubter Kontrollbereich aus 02.132 C:** Serverautoritative Kampagnen-/Rollen-/Gruppen-/Szenen-/Asset-/Lizenz-/Empfänger-Policy für verfügbare Playlists, Tracks, Cue-Angebote, rechtmäßige Auswahl-/Freigabe-/Anfrageentscheidungen und zugelassenen aktuellen Szenenkontext. Ein Event darf **nicht** als „alle bei Position 02:15 beginnen“ transportiert werden.
- **Lokaler Audiozustand:** Konzeptionell `LocalAudioPlayerState` mit geräteindividueller, **nicht an andere synchronisierter** Wiedergabeentscheidung und Position; `AudioOwnVolumeMutePreference` aus 02.132 C bleibt eigenständig. Kein anderer Teilnehmer muss die persönliche Playposition kennen. Ob lokale Zustände nach Browserreload überhaupt gespeichert werden, wird **nicht** als Feature zugesichert.
- **Quell-/Szenenschutz vor jedem Cue:** Nur gültige 02.25-/02.132-Kampagnen-/Actor-/Target-/Gruppen-/Szenen-/Asset-/Lizenz-/Secret-/Medienrechte erlauben Metadata, Download/Streaming, Vorschlag, lokale Aktivierung und Cue. Rechtewechsel invalidieren ggf. autorisierte Auswahl/Quelle, aber erzeugen keinen gemeinsamen Musiktransport.
- **Geräte-/Transportrealität:** Unterschiedliche Pufferraten, Browser, Netzverfügbarkeit, Autoplay-Policies und lokale Pausen sind zulässige, **nicht zu korrigierende** Differenzen. Es wird keine garantierte simultane Audioausgabe oder zeitgenau synchronisierte Musikwiedergabe behauptet.
- **Sicherheits-/Datenschutzgrenze:** Keine persönlichen Playhead-/Hörlisten-/Online-/Mute-/Block-Statistiken, versteckten Track-/Scene-IDs, fremden Audio-URLs, Zeitanker, Queuepositionen oder Soundeffekt-Counts über öffentliche APIs, Realtime, Cache, Logs, Chat-Notifications oder Favoriten veruntreuen. Technische Serverlogs dienen nur berechtigten Diagnose-/Abusezwecken.
- **Kein Chat-/Welt-/ACK-Nebeneffekt:** 02.122-A-Chat-Voice-Memo-Ausschluss bleibt. Musik-Cue ist kein Chatmessage-Forward, keine 02.131-Würfel-/Systemreferenz, kein 02.102-Korrektur-Ack, kein 02.99-Spielwelt-/NPC-/Quest-/Door-/Turn-/Inventarevent und kein 02.49–02.51-Schall-/Sensor-/Node-/Alarmereignis.
- **Umsetzungsschritte:** (1) Negativ-Capability für globalen Audio-Sync; (2) 02.132-Policy und Audioquell-/Lizenzberechtigungen; (3) nur autorisierte Track-/Playlist-/Cue-Auswahl ohne globalen Offset; (4) lokale Browser-/Mute-/Volume-/Playbackautonomie und Fehlergrenzen; (5) Join-/Reconnect-/Scene-/Chat-Aus-/Musik-Aus-/NoWorld-/NoSensor-/NoACK-/Geheimnis- und MultiDevice-Abnahmetests. Finale UI, Playback-Engine, API-/DB-Namen, lokale Wiedergabespeicherung und MVP später.

## 5. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| SL wählt erlaubte Taverne-Playlist, A und B starten zeitversetzt | Beide Player beginnen jeweils lokal bei 0, B wird nicht an As Offset gesetzt |
| A pausiert eigenen Track, B hört weiter | Bs Player läuft unverändert weiter, keine globale Pause-/Seek-Eventübertragung |
| B startet Track, nachdem A bereits beendet hat | Bs Track beginnt lokal am Anfang, kein globaler Track-Ende-Catch-up |
| C kommt erst mitten im Stück in die Kampagne | Kein automatischer Musikstart; nur berechtigte Trackwahl, Start von 0 nach eigener Entscheidung |
| C reconnectet nach Netzverlust | Kein globaler Offset-/Pause-/Resume-Backfill und kein ungewolltes Autosenden von Audio-Cues |
| Browser-Reload während Playback | Keine gemeinsame Transport-Wiederherstellung zugesichert; kein unfreiwilliges Autoplay |
| SL versucht `forceSyncToSessionMusic` | Kein gültiger regulärer Feature-/API-/Policy-Pfad zur globalen Zeitsynchronisierung |
| Manipulierter Client sendet globalen `seekAll(120000)`-Wunsch | Kein eigener Rechtspfad und keine Positionsänderung fremder Geräte |
| 02.25-Ausnahme für Person mit „Sync erlaubt“ | Kein heimliches Wiedereinschalten der ausdrücklich abgewählten gemeinsamen Wiedergabeuhr |
| Musikmodul 02.132 C bei Kampagnenerstellung Aus | Keine neuen Musikbefehle; Chat, Würfel, 02.51-Schall unabhängig |
| Musikmodul An, integrierter Chat Aus | Audioasset-/Playlist-/Cuefunktionen nur nach eigenen Rechten, kein Chatzwang |
| SL gibt Spielleiter-/Moderatorplaylist frei | Berechtigte Empfänger können Trackwahl sehen und lokal starten, keine Zwangsynchronisierung |
| Spieler ohne Playlist-/Cue-Recht versucht globales Skip | Keine erlaubte Steuerung fremder Playlist/Empfänger; lokale Fremdposition bleibt unverändert |
| Spieler beantragt gemäß 02.132 C Trackwechsel | Antrag ist kein eigener globaler Audio-Playbackzustand oder vorgezogener Trackstart |
| SL bestätigt zu spät nach SceneSwitch | Nur noch aktuelle Scene-/Cue-/Asset-/Policyrechte gelten, kein alter gecachter Cue zum Einspielen |
| Erlaubte automatisierte Szenen-Cue-Regel aktiv | Nur neue aktuell autorisierte Cue-Auswahl für lokale Playbackfähigkeit, keine gemeinsame Transportposition |
| Hörer erlaubt lokalen Cue nach Browserzustimmung | Track startet bei 0, nicht nach Serverstartzeit anderer |
| Hörer lehnt automatisches Abspielen ab | Kein Browser-Bypass, keine Audioerzwangsausgabe |
| A hat Musik stummgeschaltet | Jeder Cue respektiert eigenen Mute; kein SL-Override auf A |
| A ändert persönliche Lautstärke | B und SL behalten unabhängige Lautstärke und Playposition |
| Spielersicht verliert Zugriff auf geheime Szene | Keine neue Track-ID, Playlist, Cover, Audio-URL, Cuezeit, Schattenqueue oder Position |
| Reconnect mit veralteter signierter Assetadresse | Erneute Berechtigungsprüfung, keine Verlängerung verfallener Quellrechte |
| Später neu zur Gruppe gehörender Spieler | Nur heute berechtigter Audiozugriff, kein automatisches Erben historischer Geheimassets |
| Zwei Kampagnen unter demselben Account | Keine fremden Audioassets, Playlisten, Mute-/Sessionmetadaten oder globales Clock-Mixing |
| Ein Client spielt lokalen Soundboard-Cue | Andere Player werden nicht durch dessen Playerposition oder Cue-Ende gesynct |
| Musiktitel lautet „Tür öffnen“ | Kein echtes Door-/Node-/NPC-/Quest-/Turn-/Würfel-/Inventarevent |
| Soundboard spielt Alarmton | Kein zusätzliches 02.49–02.51-Spielwelt-Schall-/Sensor-/Alarm-/Node-Event |
| 02.51 echter Spielweltgeräuschauslöser | Akustische Game-ACL und Sensorlogik bleiben unabhängig von lokaler Musik |
| 02.101-Korrektur braucht 02.102-ACK | Hören, Skip, Starten, Stoppen oder Mute quittiert nicht |
| 02.110-Chatmute aktiviert | Kein Einfluss auf persönlichen Musikmute; Pflicht-Systemhinweise separat |
| 02.122 A verbietet Chat-Voice-Memos | Keine Sprachaufnahme/Transkription durch Musikplayer |
| Browser/Netz verzögert lokalen Start von B | Keine behauptete garantierte Gleichzeitigkeit oder automatische Driftkorrektur |
| Viele wiederholte/gefälschte Cueangebote | 02.132-Rate-/Quota-/Replay-/Idempotenz-/Actor-/Assetschutz bleibt wirksam |
| Zwei Geräte desselben Hörers sind verbunden | Jedes Gerät hat unabhängigen Playhead, keine Session-Clock oder Zwangswiedergabe |

## 6. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.133 A – ausschließlich selbstständige lokale Audiowiedergabe, jeder Start bei Titelanfang; kein gemeinsamer Trackfortschritt, kein synchronisierter Start-/Pause-/Seekstatus, kein Late-Join-/Reconnect-Catch-up.** Die ausdrücklich abgelehnte C-Synchronisierung wird **nicht** durch 02.25-Defaults, Ausnahmen oder 02.132-C-Modi heimlich reaktiviert. **02.132 C bleibt bestehen:** optionales Musik-/Playlist-/Soundboardmodul, sinnvolle manuelle/SL-bestätigte/automatische **Berechtigungen für Track-/Playlist-/Cue-Auswahl**, rechtmäßige Audioassets, eigene Lautstärke/Mute sowie unabhängiger Chat und separate 02.49–02.51-Schall-/Sensor-/Nodewelt. Keine neuen 02.99-Weltwirkungen oder 02.102-ACKs; keinerlei garantierte Streaming- oder Geräte-Autoplay-Leistung.

**Nicht beschlossen:** fertiges UI, endgültige Playlistfortschritts-/lokale Bookmark-/Audio-Speicherung, Codec-/Provider-/Streamingtechnik, Cuelayer/Fades/Mixing/Looping, rechtliche Lizenzmodelle, endgültige DB-/API-Namen, Performancezahlen oder MVP. Der Beschluss ist konzeptionelle Fachplanung.

## Nächste Entscheidung 02.134 – Musiküberblendungen, Wiederholung und Soundboard-Mixing

**Beispiel:** Die SL hat eine Tavernenplaylist und möchte beim Kampf die Stimmung wechseln, während gelegentlich ein Glockenton ertönt. Da 02.133 A **keinen global synchronen Playhead** vorsieht, können Überblendungen, Looping und gleichzeitige Cues höchstens an den jeweiligen lokalen Player gebunden sein.

- **A – Schlichte Einzelwiedergabe:** Pro lokalem Player nur ein Musikstück oder Sound-Cue zur Zeit, manuelle Stop-/Startwahl, keine speziellen Fade-/Crossfade-/Loop-/Multi-Layer-Mischfunktionen.
- **B – Alle Klänge unbegrenzt erzwingen:** Jeder darf beliebig viele Tracks/Cues überlagern, alle Lautstärken aller Empfänger ändern und ihre Browser-Mutes übergehen, ohne Asset-/Rollen-/Szenen-/Empfängerrechte.
- **C – Konfigurierbares lokales Sound-Mixing (Empfehlung):** Die SL darf bei aktiviertem 02.132-Musikmodul nach 02.25-Defaults und markierten Ausnahmen geeignete **pro Hörer lokal ausgeführte** Playlist-Loops, Überblendungen/Crossfades, Musik- und Soundboard-Layer sowie Audio-Cue-Übergänge freigeben, soweit technisch unterstützt. Gültige Actor-/Audioasset-/Empfänger-/Szenenrechte und eigene Hörerlautstärke/Mute/Browserentscheidungen bleiben. **Kein** globaler 02.133-A-Sync, kein 02.49–02.51-Game-SoundEvent, kein automatisches Node-/Alarm-/World-/ACK-Ereignis; UI, Grenzwerte und Mixformate später.
