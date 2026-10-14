# AdventureShift – Karten-Workshop: Beschluss 02.146 C – konfigurierbare lokale Hall-/Echoeffekte

**Stand:** 14.10.2026. Fachentscheidungen 02.1 bis 02.146, nächste offene Frage **02.147**.
**Status:** Verbindliche Fachplanung mit Umsetzungsentwurf und Tests; **noch keine Softwareimplementierung**, keine finalen DSP-Formeln, API-/DB-Schemata, UI oder MVP-Einstufung.
**Bezüge:** [02.25 Kampagneneinstellungen](KARTEN-WORKSHOP.md) · [02.49–02.51 echte Schall-/Sensor-/Nodewelt](KARTEN-WORKSHOP.md) · [02.99 echte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 amtliche Notices/ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 optionaler Chat](KARTEN-WORKSHOP-02.105.md) · [02.116 A keine Read Receipts](KARTEN-WORKSHOP-02.116.md) · [02.122 A keine Chat-Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.132 C Audio/Playlists/Soundboard](KARTEN-WORKSHOP-02.132.md) · [02.133 A rein lokale Wiedergabe](KARTEN-WORKSHOP-02.133.md) · [02.134 C lokale Layer/Fades/Loops](KARTEN-WORKSHOP-02.134.md) · [02.135–02.136 C Audio-Vorlagen und kontrollierte Updates](KARTEN-WORKSHOP-02.136.md) · [02.137 A keine Audio-Insertparameter](KARTEN-WORKSHOP-02.137.md) · [02.138 C Ducking](KARTEN-WORKSHOP-02.138.md) · [02.139 A keine Audio-Captions](KARTEN-WORKSHOP-02.139.md) · [02.140 A kein Editor-Previewplayer](KARTEN-WORKSHOP-02.140.md) · [02.141 C Loudness](KARTEN-WORKSHOP-02.141.md) · [02.142 C räumliche Audiopräsentation](KARTEN-WORKSHOP-02.142.md) · [02.143 C Bewegungsnachführung](KARTEN-WORKSHOP-02.143.md) · [02.144 C Distanzdämpfung](KARTEN-WORKSHOP-02.144.md) · [02.145 C Doppler](KARTEN-WORKSHOP-02.145.md).

## 1. Verbindliche Entscheidung – Variante 02.146 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Bei aktiviertem **02.132-C-Musikmodul** kann die SL nach **02.25-Kampagnen-/Rollen-/Gruppen-/Szenen-/Personen-Defaults und gültigen markierten Ausnahmen** für ausdrücklich geeignete, aktuell vollständig **audio-/asset-/lizenz-/szenen-/empfängerberechtigte** Musik-, Ambient- und Soundboard-Cues **getrennt aktivierbare, begrenzte ausschließlich lokale Hall- und Echoeffekte** erlauben. Zulässige abstrakte Presets können etwa „kleiner Raum“, „große Halle“ oder „Höhle“ darstellen. **Hall- und Echoeffekte sind ausschließlich hörbare Präsentation**, keine aus echter Spielweltgeometrie abgeleitete neue Schallphysik.

**Beispiel:** Eine für die Gruppe freigegebene Glocke kann im eigenen Audioplayer kurz mit einem ebenfalls zugelassenen „Große Halle“-Hall erklingen. Die SL hat daneben eine geheime Kammer – weder deren Namen, Wände, Lage noch ihre Klangverhältnisse dürfen ohne eigene Freigabe als Effektparameter oder akustisch erkennbarer Raumtyp preisgegeben werden. Der Hall öffnet keine Tür und löst keinen Sensor- oder NPC-Alarm aus.

**Nicht gewählt:** A (keine besondere Reverb-/Echo-Funktion) und B (ungefilterte automatische Hallberechnung aus sämtlichen echten/geheimen Räumen mit globaler Welt- und Sensorwirkung). **C ist kein zusätzliches Recht auf geheime Raumgeometrie, Impulsantwortdateien, Audioassets, Musik-Synchronisation, Mikrofonaufnahme oder unbegrenzte Echo-Rückkopplung.**

## 2. Konfiguration und unveränderliche Grenzen

1. **Schalter:** **02.132 Music An** und eigene nach 02.25 wirksame **02.146 Hall-/Echo-Capability An** sind erforderlich. Unterfähigkeiten für Musik, Ambient, Soundboard, passende Rollen/Personen/Szenen und erlaubte Effekttypen werden später nach gültigen markierten Ausnahmen spezifiziert. Musik Aus oder Echo Aus blockiert neue Effektjobs, ohne eigenständige Chat-, Würfel- oder echte Schallsysteme zu deaktivieren.
2. **Unabhängig von Spatial:** Stereo-/3D-Spatial nach **02.142 C** ist für abstrakten Reverb nicht zwingend. Sind Spatial/Follow/Distance/Doppler deaktiviert, darf Reverb diese Fähigkeiten nicht heimlich aktivieren oder verborgene Richtungen, NPC-Geschwindigkeiten oder Abstände auslesen.
3. **Echte Audio-/Presetrechte:** Vor Cue-/Preset-Auswahl, Realtime, Link, Medienstream, Effektstart und Cache-/Suchzugriff serverseitig Actor-/Owner-/Campaign-/Rollen-/Gruppen-/Scene-/Asset-/Lizenz-/Cue-/Recipient-/Secretrechte überprüfen. Presetname, „Höhle“-Klang, Nachhalllänge und Echomuster selbst können geheim sein; Empfänger dürfen nur ihnen **wirklich gestattete** Präsentationswerte erhalten.
4. **Keine Weltgeometrie-Ableitung:** Wände, echte Raumgröße, Türen, Fog, NPCs, versteckte Kartenpunkte, Hörbarkeit, 02.51-SoundEvent-Reichweiten und Sensorknoten sind **keine ungeschützten Audio-Reverb-Inputs**. Ein generisches freigegebenes Preset darf ohne den realen Raumkontext laufen. Eine automatische Bindung an Szenenprofile wird **erst in 02.147** separat entschieden.
5. **Effektarten nur im zulässigen Umfang:** Hallanteil, Wet/Dry-Mix, Echoverzögerung, Wiederholungsanzahl, Abklingdauer und Ausgabekanal nur falls tatsächlich technisch implementiert und durch Policy/Limit freigegeben. Konkrete Presets, Parametergrenzen, Impulsantwort-/Filter-/DSP-/Streamingtechnik, Lizenzquellen und UI **nicht** als fertig ausgeben.
6. **Persönlicher Mute hat Vorrang:** Alle Reverb-/Echo-Tails respektieren den **aktuellen** eigenen Master-/Layergain und Mute sowie Browser-/OS-Autoplay. Kein Auto-Unmute, keine Rückschreibung alter Pegel, keine Fremd- oder Systemlautstärkesteuerung. Ein nicht autorisierter oder durch den Browser nicht gestarteter Cue hat keinen spielenden Nachhall.
7. **Begrenzte Rückkopplung:** Echoausgabe darf nicht automatisch wieder als frischer Cue/Source in dieselbe Effektkette eingespeist werden. Strikte Grenzen für Echo-Frequenz, Feedback, Tail-Länge, Clipzahl, CPU, Speicher, Gain, Peak/Clipping und Quoten. Bei ungültigem Preset oder fehlender Engine sicherer gewöhnlicher berechtigter Ton oder kontrollierter Abbruch.
8. **Kontrollierter Tail nach Cueende:** Technisch erlaubtes kurzes Ausklingen ist nur bei weiterhin **gültigen** Cue-/Asset-/Lizenz-/Scene-/Empfängerrechten und innerhalb definierter Limits möglich. Widerruf, SceneSwitch, Rollenwechsel, Musik/Hall Aus, Browserstop und Audioassetlöschung invalidieren kontrollierbare Effekttails und alte Daten/Caches; bereits gehörte Töne können nicht menschlich rückwirkend gelöscht werden.
9. **Eigene Playerzeit:** Hall und Echos laufen ausschließlich im jeweiligen **lokalen** Mixer. **02.133 A** verbietet gemeinsame Start-/Seek-/Pause-/Echo-Timestamps und LateJoin-/Reconnect-Catch-up. Kein neuer Sound-Cue nur wegen Echo-Tail oder Neuverbindung.
10. **Andere Audiofeatures bleiben unabhängig:** **02.134 C** lokale Fades/Layers/Loops; **02.138 C** nur temporär reduzierendes eigenes Ducking; **02.141 C** sichere Loudness; **02.142–02.145 C** Stereo/Spatial, Follow, Entfernung und Doppler mit ihren zusätzlichen separaten Sicht-/Bewegungs-/Distanzrechten. Hall schaltet diese nicht an und erteilt keine Quell-, Welt- oder Positionsrechte.
11. **Vorlagen- und Komfortausschlüsse:** 02.135-/02.136-C-Quell-/Ziel-/Medienlizenz-/Versionrechte bleiben; **02.137 A** keine Audio-Einfügeparameter, **02.139 A** keine besonderen Cue-Captions und **02.140 A** kein privater Editor-Probehörplayer. Ein Vorlagenpreset ist niemals pauschale Medien- oder Raumfreigabe.
12. **Kein Voicechat oder echte Schallwelt:** Kein Hall auf Mikrofone, externem Voicechat oder OS-Audio, keine Aufnahme/Sprachmemo/Transkription. **02.49–02.51** physikalische Schall-/Hör-/NPC-/Sensor-/Alarm-/Nodewelt, **02.99** Weltaktionen sowie **02.101–02.104** Notices/ACKs bleiben unabhängig. Soundeffektnamen sind keine Weltkommandos.

## 3. Unveränderte Fachentscheidung und technische Trennung

| Bereich | 02.146-C-Wirkung |
| --- | --- |
| **02.25 / 02.132 C** | Getrennter tatsächlicher Effekt-Schalter, echte SL-/Cue-/Asset-/Lizenz-/Scene-/Empfängerberechtigungen |
| **02.133 A** | Keine gemeinsame Reverb-/Echo-/Musik-Uhr, kein Join-/Reconnect-Autoaudio oder globaler Seek |
| **02.134 C / 02.138 C / 02.141 C** | Eigene Mixerlayer, Lautstärke-/Mute-Vorrang, bounded Loudness, temporäres Ducking; keine globalen Gainänderungen |
| **02.142 C / 02.143 C / 02.144 C / 02.145 C** | Zusätzliche Raumrichtung, Follow, Distanz und Geschwindigkeit erfordern eigene Rechte; Hall ersetzt oder erteilt sie nicht |
| **02.135–02.136 C / 02.137 A** | Audio-Vorlagenrechte bleiben; kein Hall-Parameterdialog beim Einfügen und kein heimlicher Live-Updatezwang |
| **02.139 A / 02.140 A** | Keine visuellen Cue-Captions oder privaten Editor-Previewstreams durch Reverb |
| **02.49–02.51** | Hall-Tail ist **kein** `SoundEvent`, keine Wand-/Hörreichweite, kein Präsenz-/Schallsensor, Alarm oder Node |
| **02.99 / 02.101–02.104** | Kein Door-/NPC-/Quest-/Turn-/Würfel-/Inventareffekt, keine 02.102-ACK-Quittierung |
| **02.105 / 02.116 A / 02.122 A** | Chat unabhängig; keine persönlichen Receipts, Voice-Memos oder Mikrofonaufnahmen |
| **Sicherheit/Privacy** | Keine geheimen Raum-/Track-/Preset-/Asset-/Hörer-/Count-/Tail-Timingdaten an Unberechtigte |

## 4. Konzeptionelles Architektur- und Lebenszyklusmodell

1. **Nur konzeptionelle Arbeitsnamen:** `LocalAudioReverbCapability`, `AuthorizedAudioEffectPreset`, `AudioEffectViewerProjection`, `LocalReverbEchoRenderer`, `LocalReverbTailBudget`, `LocalEchoAbortToken`, `AudioEffectSourceRevision`. Keine endgültigen Tabellen/Endpoints.
2. **Pro-Viewer-Projektion:** Server prüft aktuelle Audio-/Cue-/Asset-/Lizenz-/Szenen-/Recipient-ACL und separate Freigabe einer etwa geschützten **Raumatmosphäre** vor Effect-/Preset-/Search-/Cache-/Realtime-/Mediazugriff. Keine rohe geheime 02.51-Wand-/Raum-/Fog-/NPC-Position oder fremder Source-/Kampagnenzugang als Effekt-Input.
3. **Lokaler bounded DSP-Graph:** Schon erlaubter Cue → nur wirklich erlaubte Presetparameter → beschränkter Wet-/Dry-/Delay-/Reverb-Mixer; kombiniert mit berechtigten 02.134-/02.138-/02.141-/02.142–02.145-Kapazitäten nur nach eigenen Regeln, zuletzt unter persönlichem Mute/Browser/Peak-/Limiter-Schutz. **Reihenfolge ist nicht als finale Implementierung festgelegt.**
4. **Kein neues Quellereignis:** Ein Delay-Echo oder Halltail wird **nicht** an den World-/Chat-/Spielsystem-/Würfel-/Nodebus als ursprünglicher neuer Cue publiziert. Keine zweite Autorität, kein erneuter RNG, keine automatischen ACKs/Notifications/Spielweltreaktionen.
5. **Version/Revocation/Tail:** Cue-/Preset-/Lizenz-/Scene-/Rollen-/Asset-/Effekt-/MusicRevision pro lokalem Effektjob, Abbruch/Entwertung kontrollierbarer Tails bei Rechteverlust; beim technischen Cueende nur strikte Restdauer und unveränderte weiterhin gültige Rechte. Keine nachträgliche Wiederholung bei LateJoin oder Reconnect.
6. **Keine verborgene Szenenprofilautomation:** Ein abstrakter Hallraum darf als normal rechtmäßig gewählter Audioeffekt zur Verfügung stehen. Ob bei Szenenwechsel ein Effektprofil manuell/automatisch nach wirklich gültigen Rechten zugeordnet wird, ist **02.147**. Keine automatische Triggerübernahme aus unbekannten Kartenräumen.
7. **Ressourcen und Datenminimierung:** Feedback-/Tail-/Ketten-/CPU-/Decoder-/Rate-/Quota-Limits, technische Logs ohne als Nutzerfeed ausgegebene geheime Hall-/Raumdynamik, keine Upload-/SSRF-/Path-/DRM-/Lizenz-Umgehung. Safe Fallback bei unsupported DSP oder Browserblock.
8. **NoWorld-Grenze:** Der lokale Echo-/Hallrenderer bleibt Präsentation; keine echte 02.49–02.51-NPC-Hörbarkeit, keine Schallsensor-/Alarm-/Nodewirkung und kein 02.99-/02.102-Effekt. Tests müssen auch zusammengesetzte Layer-/Ducking-/Doppler-/Reverbketten umfassen.

## 5. Konzeptioneller Umsetzungsplan

1. Eigene 02.146-Reverb-/Echo-Capability unter 02.132-Musik-An und wirksamer 02.25-Policy; Rollen-, Scene-, Cue- und Effektkategorien planen.
2. Nur freigegebene, versionierte und rechtmäßig lizenzierte abstrakte Presets und Audio-Cues projektieren; keine HiddenRoom-/NPC-/Geometry-/Asset-URLs aus Effektparametern oder Caches.
3. Geräterenderer mit eigenem Wet-/Dry-/Delay-/Tailbudget, Usermute, Peak/CPU/Decoder-/Feedback-Guards und sicherem normalen Wiedergabe-Fallback.
4. Cue-/Source-/Preset-/License-/Scene-/Role-/Music-Aus-Invalidierung und idempotente Replay-/Reconnect-/Stop-/Race-Guards; Hallausgabe nie als neuer Cue-/SoundEvent-/ACK-Input.
5. Fachtests unten und später technische Details zu Reverb-/Delayalgorithmik, Effektdauern, Limits, DSP-Bibliothek, UI, API/DB und MVP beschließen.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Musik 02.132 C Aus | Kein neuer Hall-/Echo-Playbackpfad, unabhängige Chat-/Würfel-/02.51-Weltfunktionen |
| Musik An und Hall-Fähigkeit Aus | Normale erlaubte Player/Layers ohne besonderen Reverb |
| SL aktiviert berechtigten Glockenhall | Nur eigene lokale, begrenzte Hallwiedergabe für berechtigten Empfänger |
| 02.142 Spatial Aus, Hall An | Generisches berechtigtes Hallpreset bleibt ohne 3D-Positionsrechte möglich |
| Reverb nur für Soundboard, nicht Ambient erlaubt | Nur rechtmäßig unterstützte Soundboard-Cues erhalten den Effekt |
| Abstraktes Hallpreset „Große Halle“ berechtigt | Entsprechender zulässiger Hall ohne geheime echte Karten-/Raumgeometrie |
| Quellraum „Geheime Höhle“ für Spieler verborgen | Kein Name, Preset, Raumprofil, Hallzeit oder hörbarer Secret-Fingerabdruck |
| Spieler darf Cue hören, aber nicht geheime Raumart | Kein aus verborgenen World-Geometriedaten abgeleiteter Hall |
| Spieler errät Secretpreset- oder Scene-ID | Keine Preset-/Track-/Raum-/Count-/URL-/Fehler-Existenzoffenlegung |
| Audioassetlizenz fehlt trotz Presetrecht | Kein Stream, Cue, Echo oder Medienzugriff |
| Spieler nicht in ursprünglichem Cue-Empfängerscope | Kein Effekt, Tail, privater Cue-Count oder geheimnisverratender Fehler |
| Browser blockiert Autoplay | Kein Effektstart/Audiozwang, kein zusätzlicher Echo-Bypass |
| Benutzer hat Mastermute aktiviert | Auch sämtliche Reverb-/Echo-Tails sind stumm |
| Nutzer ändert persönlichen Mastergain während Tail | Aktuell selbst gewählter Pegel bleibt, kein automatisches Entmuten |
| Echo-Feedback extrem hoch angefordert | Harte Feedback-/CPU-/Lautheitslimits oder sicherer Abbruch |
| Echo erzeugt irrtümlich einen zweiten CueStart | Deduplizierung; keine Recursion, kein neues Ducking oder Spielwelt-Event |
| Cue endet und erlaubter Tail klingt kurz aus | Nur innerhalb fest begrenzter Dauer und weiterhin gültiger ACL |
| Cue-/Asset-/Scene-Recht während Tail entzogen | Kontrollierbare Effekttails beendet, kein privates Secret-Nachhallreplay |
| Musik-/Reverbfähigkeit im Betrieb Aus | Halljobs stoppen kontrolliert, gewöhnliche Systeme getrennt |
| Später beitretender Spieler | Kein historischer Echo-/Musik-Join-Catch-up oder globaler Starttimestamp |
| Player reconnectet nach Cueende | Kein Echo-Replay, kein automatisch neuer Musik-Cue |
| Zwei Hörer starten Musik zeitversetzt | Eigene unterschiedliche Hallzeitlinien statt globalem Sync |
| Mono-/Browser-Hardware ohne Reverbunterstützung | Sicherer regulärer Audio-Fallback statt Codec-/Hardwarezwang |
| 02.134 C mehrere lokale Layers/Crossfade | Hall nur an zugelassenen eigenen Spuren, beschränkte Mixer-Ressourcen |
| 02.138 C Ducking aktiv | Hall erzeugt kein zusätzliches Duckingstart-Ereignis |
| 02.141 C Loudness aktiv | Kein unkontrolliertes Verstärken/Clipping aus Mix und Reverb |
| 02.142–02.145 Raum-/Distanz-/Dopplerfunktionen Aus | Hall aktiviert keine versteckte Quelle-/Velocities-/3D-/Distanzrechte |
| Spatial-Follow und Echo gleichzeitig | Beide nur nach eigenen gültigen Cue-/Szenenrechten, keine Weltgeometrie-Offenlegung |
| Geheime Raum-IR-Datei im Preset genannt | Keine pauschale neue Download-/Upload-/Lizenzfreigabe |
| Audio-Vorlage 02.135 C verwendet Hallpreset | Keine Kopie fremder Raumnamen/Secret-Medien-/Lizenzrechte |
| Vorlage 02.136 C bekommt neues Hallpreset | Keine automatische Änderung laufender Cues ohne kontrolliertes Update |
| 02.137 A feste Vorlagen | Kein Hall-Eingabeparameterwizard beim Einfügen |
| 02.139 A keine Caption | Kein visueller „Glocke hallt“-Toast oder Chat-Audio-Ereignisfeed |
| 02.140 A kein Editorpreview | Hall eröffnet keinen privaten Vorhörstream |
| Hallender Cue „Alarm“ | Kein echtes 02.49–02.51-`SoundEvent`-/NPC-/Sensor-/Node-/Alarmereignis |
| Hallender Cue „Tür öffnen“ | Kein 02.99-Tür-/Quest-/Turn-/Würfel-/Inventarcommit |
| Offizielle 02.102-ACK-Pflicht | Hören/Echo/Stoppen erzeugt keine Quittierung |
| Externer Voicechat läuft | Keine Voice-/Mikrofonaufnahme, keine Fremdapp-Reverb- oder System-Gainänderung |
| Chat 02.105 bei Erstellung Aus | Reguläre berechtigte Musik/Hallfunktion ohne integrierten Chat |
| Spieler hat 02.110-Chatmute | Eigenes Musikmute unabhängig von Chatmute |
| Browsercache nach Quell-/Szenen-/Lizenzwiderruf | Keine neue unberechtigte Hall-/Media-Zustellung |
| Viele Echotails gleichzeitig | Quota-/CPU-/Speicher-/Gain-/Peak-/Decodergrenzen und Cleanup wirken |
| Zwei Geräte desselben Nutzers | Kein gemeinsam erzwungener Echozeitanker oder Masterlautstärke |
| Client injiziert `roomGeometry` und fremde Preset-ID | Kein Secret-Raum-/NPC-/Audioassetzugriff oder Codeausführung |
| SceneSwitch während laufendem Hall | Alte Presetrechte und Tails kontrolliert invalidieren |
| Echo-Engine fällt aus | Sicherer lokaler Ton/Fallback, keine World-/System-/ACK-Nebenwirkung |

## 7. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.146 C – getrennt aktivierbare, ressourcenbegrenzte ausschließlich lokale Hall-/Echoeffekte auf tatsächlich audio-/asset-/lizenz-/szenen-/empfängerberechtigten Musik-/Ambient-/Soundboard-Cues.** Generische Hallpresets ersetzen **nie** echte 02.49–02.51-Wand-/Schall-/Sensor-/Nodewelt, eröffnen keine geheimen Raum-, Positions- oder Medienrechte und erzeugen keine 02.99-Weltaktion/02.102-ACK. Musik aus 02.132 C bleibt bei Kampagnenerstellung schaltbar; 02.133 A verbietet globale Audiozeit, 02.134 C lokale Layer/Fades/Loops, 02.138 C Ducking, 02.141 C Loudness, 02.142–02.145 C weitere eigene Spatial-/Distanz-/Dopplerrechte bleiben; 02.137/02.139/02.140 A-Ausschlüsse ebenfalls.

**Nicht beschlossen:** Effektdauer/-formel, Presetbibliothek, DSP-Engine, Impulsantwortlizenzen, automatische Szenenprofilwahl, UI/API/DB/MVP. Das ist Fachplanung, noch keine Softwareimplementierung.

## Nächste Entscheidung 02.147 – Hall-/Echo-Audioeffektprofile mit Szenen verknüpfen

**Beispiel:** Die SL verwendet für eine erlaubte Höhlenszene ein generisches Hallpreset. Sie könnte es beim Szenenwechsel manuell auswählen oder die Vorlage nur nach ausdrücklicher Erlaubnis für die richtige Szene automatisch aktivieren lassen, ohne geheime Geometrie preiszugeben.

- **A – Keine besonderen Szenenprofile:** Hall- und Echoeffekte werden ausschließlich in den gewöhnlichen berechtigten Audio-/Cue-Einstellungen ausgewählt; keine besondere Szenenverknüpfung.
- **B – Alle Szenen erzwingen Welt-Raumakustik:** Raumgrößen, Wände, Fog, NPC-Positionen und geheime Räume werden automatisch zu globalen Hallprofilen und echten Sensor-/Alarm-/Node-/Spielweltaktionen.
- **C – Konfigurierbare geschützte Szenen-Audioeffektprofile (Empfehlung):** Bei aktiviertem 02.132-Musikmodul und zulässiger 02.146-Hallfähigkeit kann die SL nach 02.25-Capability und gültigen Ausnahmen erlaubte abstrakte Hall-/Echo-Presets passenden **tatsächlich sicht-/hörberechtigten** Szenen/Empfängern zuordnen. Manuelle Wahl oder gezielte rechtmäßig autorisierte SceneSwitch-Automation sind getrennt wählbar. Kein Leak geheimer Räume/Geometrien, kein AutoJoin-/02.133-A-Globalplayhead, keine 02.49–02.51-Schall-/Sensor-/Node-/02.99-Welt-/02.102-ACK-Wirkung; UI und Triggerdetails später.
