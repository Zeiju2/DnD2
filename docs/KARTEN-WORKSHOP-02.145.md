# AdventureShift – Karten-Workshop: Beschluss 02.145 C – geschützter lokaler Doppler-Effekt für berechtigte bewegte Audio-Cues

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.145; nächste offene Featurefrage 02.146.
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Implementierungs- und Abnahmetestplan; **noch keine Softwareimplementierung**, keine endgültigen Formeln, Audio-Engines, Datenbank-/API-Verträge, Oberfläche oder MVP-Einstufung.
**Bezüge:** [02.25 – Kampagnen-/Rollenstandards mit gültigen markierten Ausnahmen](KARTEN-WORKSHOP.md) · [02.49–02.51 – unabhängig geregelte echte Spielszenenakustik, Sensoren, Alarm und Nodes](KARTEN-WORKSHOP.md) · [02.54 – echte eigenständige NPC-Steuerung](KARTEN-WORKSHOP.md) · [02.99 – autorisierte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – amtliche Hinweise und ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – separater optionaler Chat](KARTEN-WORKSHOP-02.105.md) · [02.110 – Chat-Mute-/Blockrechte](KARTEN-WORKSHOP-02.110.md) · [02.116 A – keine Chat-Lesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.122 A – keine Chat-Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.132 C – optionales Musik-/Soundboardmodul](KARTEN-WORKSHOP-02.132.md) · [02.133 A – keine gemeinsame Wiedergabeposition oder Join-Synchronisation](KARTEN-WORKSHOP-02.133.md) · [02.134 C – lokale Audio-Layers/Fades/Loops](KARTEN-WORKSHOP-02.134.md) · [02.135–02.136 C – geschützte Audiovorlagen und bewusste Updates](KARTEN-WORKSHOP-02.136.md) · [02.137 A – feste Audio-Vorlagen ohne Insertparameter](KARTEN-WORKSHOP-02.137.md) · [02.138 C – eigenes optionales lokales Ducking](KARTEN-WORKSHOP-02.138.md) · [02.139 A – keine besonderen Audio-Cue-Captions](KARTEN-WORKSHOP-02.139.md) · [02.140 A – kein besonderer Editor-Vorhörplayer](KARTEN-WORKSHOP-02.140.md) · [02.141 C – sichere lokale Lautheitsnormalisierung](KARTEN-WORKSHOP-02.141.md) · [02.142 C – berechtigte Stereo-/Pan-/ggf. 3D-Darstellung](KARTEN-WORKSHOP-02.142.md) · [02.143 C – je Update berechtigte bewegte Spatialquellen](KARTEN-WORKSHOP-02.143.md) · [02.144 C – nur lokale Distanzdämpfung](KARTEN-WORKSHOP-02.144.md).

## 1. Verbindliche Entscheidung – Variante 02.145 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Bei wirksam aktiviertem **02.132-C-Musikmodul**, **02.142-C-Spatialfähigkeit**, **02.143-C-bewegter Cue-Nachführung** und separat nach **02.25-Kampagnen-/Rollen-/Gruppen-/Szenen-/Personen-Defaults und gültigen markierten Ausnahmen** eingeschalteter Doppler-Unterfähigkeit darf die SL für geeignete, heute vollständig **audio-, quellen-, bewegungs-, richtungs- und geschwindigkeitsberechtigte** Musik-/Ambient-/Soundboard-Cues eine **sicher begrenzte Tonhöhen-/Frequenzverschiebung ausschließlich im jeweiligen eigenen Hörerplayer** vorsehen. Sie stellt nur eine **optionale Präsentation** tatsächlich zugelassener Bewegung dar – **kein** echter 02.49–02.51-Spielwelt-Schalleffekt und keine automatische Musik-/NPC-Synchronisierung.

**Beispiel:** A darf einen vorbeifahrenden Wagen sehen, seinen Motor-Cue hören und die erforderliche Annäherungs-/Entfernungsbewegung wahrnehmen. Wenn Audio, Spatial, Follow und Doppler jeweils berechtigt aktiv sind, kann As eigener Audioplayer den Motor beim Näherkommen begrenzt höher und nach dem Vorbeifahren tiefer klingen lassen. B darf zwar den Sound, aber nicht die Geschwindigkeit des Wagens erfahren: B erhält **keinen** daraus abgeleiteten Pitchverlauf; wenn normale nicht-dopplerbezogene Audiowiedergabe weiterhin zulässig ist, bleibt sie bei unveränderter Originaltonhöhe. Weder genaue Geschwindigkeitswerte noch unsichtbare NPC-/Quellkoordinaten werden B geschickt.

**Nicht gewählt:** A (überhaupt keine zusätzliche Doppler-/Pitchdarstellung) und B (ungefilterte, global erzwungene Doppler- und Game-Schall-/Sensor-/Nodeeffekte aus allen NPC-/Objektbewegungen). C ist **keine** physikalische Echtzeitausbreitungsberechnung des Spiels, keine Aufnahme externer Audiogeräte und keine Garantie perfekter Dopplerqualität auf jeder Hardware.

## 2. Aktivierung, geschützte Bewegung und Hörerhoheit

1. **Vier notwendige echte Voraussetzungen:** (a) 02.132 Musik **An**, (b) 02.142 Stereo-/Spatial **An**, (c) 02.143 sichere Bewegungsnachführung **An** und (d) 02.145-Doppler-Unterfähigkeit für diese Rolle/Szene/Cuegruppe **An**. 02.144-Distanzdämpfung darf unabhängig **An oder Aus** sein. Doppler selbst schaltet keine dieser Fähigkeiten im Hintergrund an.
2. **Nur schon zugelassene Quellen:** Ein autorisierter, tatsächlich laufender/zulässiger Cue und dessen vom Spielweltmodul getrennt freigegebene Spatial-Präsentation sind Ausgangspunkt. Bloße Bewegung, Ortswechsel oder Erscheinen eines NPC/Fahrzeugs startet **keinen** neuen Cue, keinen Musiktrack und keine Spielweltaktion.
3. **Eigenes Geschwindigkeits-/Radialbewegungsrecht:** Außer aktueller Audio-/Cue-/Audioasset-/Lizenz-/Empfänger- und Karten-/Fog-/Position-/Richtungsberechtigung braucht der konkrete Hörer **ausdrücklich die für das Pitchmuster erforderliche Annäherungs-/Entfernungs- beziehungsweise Radialgeschwindigkeitsinformation**. Ein erlaubtes Soundboard-Asset, Richtung oder Abstand aus 02.144 ist **nicht** automatisch eine Freigabe von Geschwindigkeit.
4. **Akustisches Signal selbst kann verraten:** Ein höher/tiefer werdender Ton offenbart möglicherweise Existenz, Bewegungsrichtung, Geschwindigkeitsklasse, Beschleunigung oder passierte Wegpunkte. Rechteprüfung muss **das hörbare Ergebnis**, nicht bloß einzelne Datenfelder, abdecken. Keine Dopplerwiedergabe bei unzulässiger geheimen Geschwindigkeits-/NPC-/Sourcebewegung, auch nicht durch sanitisierte, aber verräterische Zeit-/Pitchfolgen.
5. **Datensparsame serverseitige Projektion:** Nur **heute für diese Hörerperson tatsächlich freigegebene** Pitch-/Bewegungspräsentationsstufe und ggf. erlaubte abstrakte Richtung übertragen, **keine** rohen NPC-/Tür-/Fallenpositionen, 3D-Weltkoordinaten, Geschwindigkeits-/Beschleunigungsvektoren, Velocity-IDs, historischen Pfade, Hörzonen oder geheimen Quellinformationen. Selbst eine scheinbar harmlose genaue Pitchratio kann verbotene Geschwindigkeit rekonstruieren – in diesem Fall **unterdrücken/geeignet grob begrenzen** statt senden.
6. **Pro relevantem Follow-/Pitchupdate erneut prüfen:** Der frühere Cue-Startgrant und der frühere 02.143-Followgrant genügen nicht dauerhaft. Vor jeder neuen geschwindigkeits-/bewegungsbezogenen Pitchprojektion **für den konkreten Empfänger** aktuelle Source-/Cue-/Lizenz-/Kampagnen-/Actor-/Audio-/Position-/Fog-/Richtung-/Geschwindigkeitsrechte und gültige Policy-/Revisionsversion prüfen.
7. **Gerätelokal statt Gruppen-DSP:** Die tatsächliche Tonhöhen-/Frequenzänderung wird nur auf dem **eigenen Gerät** berechnet/gerendert. SL-/Kampagnen-Defaults erlauben die Fähigkeit, setzen jedoch **keinen** fremden OS-/Hardware-/Voicechat-Lautstärkepegel und erzwingen keine gemeinsame Abspielposition oder den Audio-Start.
8. **Begrenzte Tonhöhenverschiebung:** Nur ausreichend eng begrenzte, technisch für Cue und Codec geeignete Pitch-/Playbackrate-/Resampling-Effekte. Keine extremen Frequenzen, unkontrollierte Playbackgeschwindigkeit, negative Zeit, unbegrenzte Dopplerverstärkung oder Clipping/CPU-/Decoder-Überlast. Exakte Maxima, Formeln, Audioengine-Fähigkeiten und Umgang mit Musik versus Kurz-Cues später festlegen.
9. **Stille, Mute und Browserentscheidung:** Eigenes Master-/Layer-Mute und gewählte Lautstärke haben absoluten Vorrang; Browser-/OS-Autoplay und bereits gesperrte Medien sind niemals durch Doppler zu umgehen. Ein unberechtigter oder nicht gestarteter Cue darf keine Pitch-/Audio-/Positions-Tasks auslösen.
10. **Fallback bei fehlendem Recht oder Technik:** Liegt zwar weiterhin **echte reguläre Cue-/Audiofreigabe**, aber kein Geschwindigkeitsrecht oder keine Dopplerfähigkeit vor, kann der Ton **neutral in normaler zulässiger Originaltonhöhe** bleiben. Fehlt die Cuerechte-/Assetfreigabe, muss auch normales Audio gestoppt/abgewiesen werden. Kein LastKnownPitch aus zwischenzeitlich geheim gewordenen Werten.
11. **Optionale Distanz-Pegeldämpfung getrennt:** 02.144 C reduziert nur den **eigenen Audiopegel** nach *separatem Distanzrecht*; 02.145 C beeinflusst nur begrenzt Pitch/Frequenz nach *separatem Geschwindigkeits-/Bewegungsrecht*. Die eine Fähigkeit liefert **keine** fehlende Berechtigung für die andere.
12. **Keine Kopplung an echte physikalische Spielszenenakustik:** Doppler ist nur Audiopräsentation, **keine** 02.49–02.51-Schallwellen-/Wand-/Hörbereich-/Sensor-/Alarm-/Nodeberechnung. Ein Dopplerton mit Namen „Sirene“ öffnet keine Tür, verändert kein NPC-Verhalten, sendet keinen Alarm und quittiert keine offizielle Notice.

## 3. Verhältnis zu früheren Beschlüssen

| Beschluss | Verbindliche Folge für 02.145 C |
| --- | --- |
| **02.25 / 02.132 C** | Gesonderte schaltbare Doppler-Capability mit wirksamer Rollen-/Kampagnen-/Szenen-/Personenpolicy; Quell-/Cue-/Asset-/Lizenz-/Empfängerrechte bleiben zwingend |
| **02.142 C und 02.143 C** | Spatial und Follow müssen aktiv, Cue bereits tatsächlich erlaubt sein. Jedes neue Pitch-/Bewegungsupdate benötigt erneut Sicht-/Fog-/Richtungs-/Positions- **und eigenes Geschwindigkeitsrecht** |
| **02.144 C** | Entfernungsdämpfung ist eigenes, **nur reduzierendes lokales Gain-Modul** und darf Doppler nicht autorisieren; Pitchänderung ist kein Distanz-/NPC-Hörbarkeitsprädikat |
| **02.133 A** | Weiterhin kein synchronisierter Player-/MusicClock-/Seek-/Pause-/LateJoin-/Reconnectstatus; Pitchänderung ist **kein** gemeinsam synchronisierter Transport |
| **02.134 C / 02.138 C / 02.141 C** | Nur lokales Layer-/Fade-/Loop-Mixing, zeitweise nur reduzierendes Ducking und sichere quellenbezogene Lautheitsnormalisierung; persönlicher Mute/Browserautoplay gewinnt |
| **02.135-/02.136 C und 02.137 A** | Berechtigte Vorlagen/Versionsupdates kopieren keine geheimen Velocity-/Positions-/Trackinformationen und erhalten **keine** Audio-Vorlagen-Einfügeparameter |
| **02.139 A / 02.140 A** | Keine neuen visuellen „Fahrzeug kommt näher“-Cue-Captions oder privaten Editor-Previewstreams durch Doppler |
| **02.49–02.51 echte Schall-/Sensorwelt** | Kein echter SoundEvent, Sensortrigger, Wand-/NPC-Hörbarkeits-/Alarm-/Nodeoutput aus lokaler Pitchänderung |
| **02.99 / 02.101–02.104** | Keine echten Quest-/NPC-/Door-/Turn-/Würfel-/Inventaraktionen und keine bewusste amtliche 02.102-ACK-Quittierung |
| **02.105 / 02.110 / 02.116 A / 02.122 A** | Chat unabhängig An/Aus, Chatmutes keine Musicmutes, keine persönlichen Read-Receipts, Mikrofon-/Voicechat-Aufnahmen oder Chat-Sprachnachrichten |
| **Privacy, Lizenz und Geräte** | Keine fremden Hörlisten, versteckte Source-/Geschwindigkeitstelemetrie, unrechtmäßigen Stream-/Codec-/Medien-URLs oder OS-Fernpegel |

## 4. Architekturentwurf und Lebenszyklus

1. **Arbeitsnamen, keine fertigen API-Modelle:** `LocalAudioDopplerCapability`, `AuthorizedDopplerCueView`, `DopplerVelocityPresentationGrant`, `LocalDopplerPitchEnvelope`, `DopplerCueVersion`, `DopplerViewerSubscription`, `LocalDopplerAbortToken`. Der technische Daten-/Audio-/Quellvertrag wird später definiert.
2. **Serverauthoritative Quelle, getrennte Projektion:** Die bereits autoritativ stattfindende zulässige Fahrzeug-/NPC-/Token-/Szenenbewegung und ihr Fachzustand sind **nur Inputs** einer getrennten read-only Cue-/Spatial-/Doppleransicht. **Keine** neue echte Bewegung, NPC-Aktion, Game-SoundEvent, Door-/Nodeaktion, Alarmierung oder Würfelwirkung durch den Pitch-Renderer.
3. **Dreifache aktuelle per-Viewer-Prüfung:** Vor Initial- und jedem nachfolgenden Pitchereignis getrennt (a) gültige echte Originalcue-/Asset-/Actor-/Empfänger-/Medien-/Lizenzrechte, (b) 02.142-/02.143-aktueller Fog-/Karten-/Richtungs-/Position-/Hörerankerkontext und (c) die eigene **aktuelle Geschwindigkeits-/Annäherungs-/Doppler-Presentation-ACL** prüfen. Clientflags, versteckte IDs und reine SL-Rolle sind keine Ersatzberechtigung.
4. **Sanitisierter Pitchfeed ohne Rohvelocity:** Pro Hörer nur erlaubte grobe Pitch-/Dopplerpräsentation und minimale versionierte gültige Cue-/Viewerreferenz. Keine ungefilterten Radialgeschwindigkeiten, XYZ-Vektoren, geheimen Hörer-/Quellkoordinaten, anderen NPC-IDs, Cursor-/Zähldaten, Search-/Preview-/Error-/Realtime-Existenzlecks. Rate-/Timing-Muster dürfen nicht verraten, wann ein verborgenes Fahrzeug beschleunigt.
5. **Konsistente Versionierung:** Cue-/Weltpositions-/Viewer-/Fog-/Geschwindigkeits-/Lizenz-/Asset-/Scene-/Dopplerpolicyrevision, monoton autorisierte Abfolge, bounded Rate/Fanout/Quota und idempotente Subscribe-/Retry-/Reorder-/Reconnectbehandlung. Kein altes geheimes Velocitysegment im Browsercache nach Rollenwechsel.
6. **Widerruf und Absturzschutz:** Wird 02.132-Musik, 02.142-Spatial, 02.143-Follow oder 02.145-Doppler ausgeschaltet, Szene gewechselt, Cues gestoppt oder Quell-/Geschwindigkeits-/Lizenz-/Recipientrechte entzogen, sind Serverprojektor/Subscriptions, Clientpitchjob und Caches zu invalidieren. Sicher neutraler Originalton nur soweit Cue-/Assetrecht weiterhin gilt; sonst Audio stoppen. Keine nachträgliche Secret-Interpolation, Extrapolation oder LastKnownPitch.
7. **Lokale begrenzte Audio-DSP-Kette:** Berechtigter lokaler Renderer wendet optional bounded Pitch/Resampling/HRTF/Layer-Fades und 02.144-DistanceGain, 02.141-LoudnessGain, 02.138-DuckGain in **noch später festzulegender, technisch validierter** DSP-Reihenfolge an. Master-/Layer-Mute absolut; CPU/Decoder-/Sample-/Peak-/Clipping-/Playbackrate-/Schutzlimits. Keine garantierte physikalische Tonhöhenformel bei fehlendem Codec-/Browser-/Hardware-Support.
8. **Kein Nachholen/Aufzeichnen:** Bei Join/Reconnect kein Audio-Autoplay, keine vergangenen Pitch-/Bewegungslisten, keine SessionMusicClock und keine Hörer-/Velocity-Statistik an SL/Spieler. Falls nach Reconnect ein **neuer echter Cue** autorisiert wird, beginnt dieser gerätelokal nach 02.133 A.
9. **Audits ausschließlich rechtmäßig:** Berechtigungsentscheidungen, Ablehnung und technische Überlast können im legitimen technischen Audit erfasst werden, dürfen aber niemals als UI-/Chat-/OS-/Search-/Stats-Schnittstelle echte geheime Weltpfade, Geschwindigkeiten oder individuelle Hörmuster offenlegen. Eigene Raten-/Privatsphärengrenzen definieren.

## 5. Konzeptioneller Umsetzungsplan (noch keine Software)

1. **Featurepolicy nach 02.25:** 02.132-Musik + 02.142-Spatial + 02.143-Follow + getrennt 02.145-Doppler nur für geeignete Cues/Rollen/Empfängergruppen/Scene; 02.144-Distanzdämpfung bleibt eigener optionaler Schalter.
2. **Read-only Source-/Velocityresolver:** Vor jeder gerätelokalen Doppler-Projektion tatsächliche Actor-/Cue-/Asset-/Lizenz-/Empfänger- sowie Fog-/Richtungs-/Bewegungs-/Höreranker-/Geschwindigkeitsberechtigung; **akustische** Pitchänderung selbst als geschützte Information autorisieren.
3. **Minimierte revidierbare Datenprojektion:** Nur wirklich erlaubte abstrahierte und bounded Pitch-/Bewegungsstufe, keine exakte NPC-/Fahrzeug-/Tür-/Fallen-Position/Velocity; kein indirekter Leak durch Abo-/Fehler-/Zeit-/Cachemetadaten.
4. **Gerätelokaler sicherer Renderer:** 02.133-A-eigenständige Playeruhr, 02.134-C-Layer, 02.142-C-Spatial, 02.144-C-DistanceGain, 02.141-C-Loudness, 02.138-C-Duck, persönliche Mute-/Browserpriorität. Bounded Pitch-/Decoder-/Gainkurven, sichere Neutral-/Abbruchfälle.
5. **Revocation/Tests:** Quell-/Fog-/Velocity-/Lizenz-/Role-/Scene-/Follow-/Doppler-Aus-Invalidierung, NoCueOnMove, NoSync/NoSoundEvent/NoWorld/NoACK/NoVoiceCapture, HiddenVelocity-/Join-/Reconnect-/Rate-/CPU-/AudioCodec-/Mute-Fälle anhand der Tabelle unten. Formeln/UX/Performance/MVP nach vollständiger Featureplanung.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Musik 02.132 C bei Kampagnenerstellung Aus | Kein neuer Doppler-/Spatial-/Cue-Audioauftrag; Chat, Würfel und echte 02.51-Weltakustik unabhängig |
| Musik An, 02.142 Spatial Aus, Doppler An | Kein Doppler ohne tatsächlich eingeschaltete Spatial-Capability |
| Musik/Spatial An, 02.143 Follow Aus, Doppler An | Keine bewegungsabhängige Pitch-Nachführung ohne wirksames Follow |
| Musik/Spatial/Follow An, Doppler Aus | Bereits zulässiges Pan-/Distanzverhalten unverändert, kein Pitchshift |
| SL erlaubt Doppler nur für Motor-Cues | Andere Cues bleiben auch bei Bewegung in originaler Tonhöhe |
| A darf Fahrzeug, Cue, Richtung und Annäherungsgeschwindigkeit kennen | Bounded nur lokaler Pitchverlauf nach eigener Freigabe möglich |
| B darf Motor hören, aber Fahrzeuggeschwindigkeit bleibt geheim | Kein von geheimer Geschwindigkeit abgeleiteter Pitch, neutraler Ton nur bei weiterer Cuerechtegeltung |
| C darf das Fahrzeug und seine Cue-Existenz nicht erfahren | Weder Sound, Pitch, Count, Subscription, Zeit noch geheimnisverratender Fehler |
| SL-Cue ist erlaubt, aber Geschwindigkeit nicht | Keine automatische Geschwindigkeitsfreigabe durch Source-/Cue-Recht |
| Distanz ist durch 02.144 C erlaubt, Radialgeschwindigkeit aber nicht | Keine Doppler-Berechtigung aus bloßer Distanzberechtigung |
| Direction/Position ist erlaubt, Source-Beschleunigung wird geheim | Keine hörbar verräterische Beschleunigungs-/Tonhöhenkurve |
| Ein sichtbares Objekt bewegt sich ohne ausdrücklich zugelassenen Audio-Cue | Kein neues Musik-/Soundboard-/Doppler-/GameEvent |
| Fog verdeckt bewegtes Objekt nach zunächst erlaubtem Cue | Neue verborgene Pitch-/Velocityinformationen nicht mehr geliefert |
| Rollen-/Gruppenwechsel entzieht Velocitysicht | Projektor/Cache/Clientpitchjob entwertet; kein LastKnownPitch aus Secretphase |
| Quell-Audiolizenz läuft ab | Keine neue Medien-/Pitch-/Realtime-Zustellung |
| SL deaktiviert Musik, Spatial, Follow oder Doppler während Cue | Kontrolliert neutralisieren/stoppen, keine versteckten weiteren Pitchupdates |
| Cue endet, Quelle bewegt sich weiter | Kein weiterhin laufender Doppler-Abo-/Decoderjob |
| Spieler tritt erst nach vorbeifahrendem Wagen bei | Keine automatischen alten Pitchsegmente, Audio-Join-/Reconnect-Catch-up oder Trackstarts |
| Spieler reconnectet nach mehreren Velocityupdates | Keine historische Doppler-Nachstellung und keine fremde Playbackposition |
| Zwei Spieler mit unterschiedlichen autorisierten Sichtrechten | Getrennte Pitchprojektionen ausschließlich aus ihren jeweils zugelassenen Bewegungsdaten |
| Unberechtigter Client errät NPC-/Door-/Fallen-ID | Kein Velocity-API-/Metadaten-/Existenz-/Fehlerleck |
| Client sendet manipulierte `velocityVector`-/Actor-ID | Kein neues Quell-/Cuerrecht oder Worldmove-/NPC-Steuerbefehl |
| Quell-/Position-/Policyrevision wechselt während Stream | Nur aktuell berechtigte Pitchdaten, alte gepufferte Updates nicht mehr angewendet |
| Netzwerk liefert Updates rückwärts/out-of-order | Versionierte Verwerfung, keine Rückkehr zu früheren geheimen Tonhöhen |
| Velocity-Updatezahl/Timing verrät geheime Bewegungen | Kein entsprechender per-Viewer-Zähler, Tick-/Abo-/Tonhöhenmuster |
| Begrenzter Hörer darf nur „bewegt sich“ wissen, nicht „wie schnell“ | Keine genaue Pitchrelation, die Geschwindigkeit rekonstruiert |
| Statt roher exakter Velocity werden erlaubte grobe Pitchstufen genutzt | Nur zulässige gerätelokale Präsentation, keine Rohkoordinaten/Velocities |
| Sehr schneller erlaubter Wagen überschreitet Pitchbudget | Sicherer bounded Faktor/Neutralfall, keine Decoder-/CPU-/Clipping-Überlast |
| Codec/Browser unterstützt Pitchshift nicht | Zulässiger normaler Ton statt ungesicherter Hardware- oder Audiozwang |
| Ein Spieler hat Master-/Layer-Mute aktiv | Doppler schaltet keinen Ton ein und hebt Mute niemals auf |
| Benutzer stellt eigene Lautstärke während Doppler um | Seine neue Einstellung gilt, fremde Player bleiben unberührt |
| Browser blockiert Autoplay | Kein Cue-Start oder Pitch-Zwang durch Doppler |
| 02.133 A zwei Spieler beginnen Track zeitversetzt | Kein globaler Playhead, Start-/Seek-/Pause-/Pitch-Sync |
| 02.134 C erlaubt lokale Fades/Layers | Nur eigene zugelassene Layer, Doppler erweitert keine Cue-/Mixrechte |
| 02.138 C Glocke löst eigenes Ducking aus | Dopplerstart/Velocities erzeugen keinen zusätzlichen Ducking- oder echten Welttrigger |
| 02.141 C Loudness-Normalisierung und Doppler aktiv | Sicherer LocalDSP-/Peak-Schutz, keine Mastergain-/Limiter-Umgehung |
| 02.144 C Distanzdämpfung ist Aus | Doppler kann bei eigenen getrennten Velocityrechten zulässig sein, ohne Distanz-Modul automatisch einzuschalten |
| 02.144 C Distanzdämpfung ist An | Lokaler DistanceGain unabhängig von eigenem bounded Pitchfaktor; keine Quelle-/Secretrechteausweitung |
| 02.135–02.136 C Audio-Vorlagen/Versionen genutzt | Keine automatische Übertragung geheimer NPC-Bewegung oder Velocityrechte |
| 02.137 A feste Audio-Vorlage eingefügt | Kein neuer Audio-Template-Insertparameter für Doppler |
| 02.139 A keine Cue-Captions | Kein automatischer sichtbarer „Wagen nähert sich“-Toast/Text |
| 02.140 A kein eigener Editor-Probehörplayer | Kein geheimes Doppler-Teststreamrecht aus Editor |
| 02.49–02.51 echter NPC-Hör-/Sensorbereich | Originale SoundEvent-/Schall-/Nodewelt unverändert, Doppler hat keine Game-Schallwirkung |
| Cue „Alarm“ oder „Tür öffnen“ klingt mit Doppler | Keine Alarm-/Tür-/NPC-/Quest-/Würfel-/Turn-/Inventaraktion |
| 02.102 Korrekturmeldung erfordert persönliches ACK | Doppler hören, stoppen oder Pitchregeln ändern quittiert nicht |
| Externer Voicechat läuft während Doppler | Kein Mikrofon-/Fremdvoice-Mitschnitt und keine externe Audio-Lautstärkeänderung |
| Spieler hat 02.110-Chatkanalmute | Musicmute/Dopplerberechtigung unabhängig von Chatmutes |
| 02.105 Chat bei Kampagnenerstellung Aus | Berechtigt aktiviertes lokales Musik-/Spatial-/Doppler-Modul weiterhin eigenständig |
| Gleiche Audio-Asset-ID in zwei Kampagnen | Keine fremden Velocity-/Member-/Cue-/Hör-/Kampagneninformationen |
| Mehrere Cues mit hoher Position-Updatefrequenz | Fanout-/Rate-/CPU-/Decoder-/Quota-/Peak-Limits und Abbruch wirken |
| Gerätewechsel während Cue | Kein globales Velocity-/MusicClock-/Mute-Tracking, Wiedergabe nach eigenen Geräte-/Browserregeln |
| Szene wechselt während Pitch-Interpolation | Alte Snapshots ungültig, keine extrapolierte geheime Bewegungsbahn |
| Featurepolicy fordert Doppler, aber kein freigegebener Radialbezug | Neutraler Ton oder kein Pitchmodus, niemals Hidden-Source-Velocity-Schätzung |

## 7. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.145 C – getrennt konfigurierbare, begrenzte ausschließlich gerätelokale Doppler-/Pitchpräsentation für tatsächlich erlaubte bewegte Spatial-Cues bei aktuell vollständigen Audio-/Bewegungs-/Geschwindigkeits-/Fog-/Positionsrechten.** Wirksame 02.132-Musik-An-, 02.142-Spatial-An-, 02.143-Follow-An- und eigene 02.25-Dopplerfähigkeit sind nötig; 02.144-C-Distanceattenuation bleibt eigenständig optional. Jede akustisch wahrnehmbare Pitchänderung ist ein zu schützendes Geheimnis; keine unberechtigten Velocities, Rohkoordinaten, Takt-/History-/Countlecks. Eigene Mutes/Browserautoplay und 02.133-A-NoSync, 02.134-C-Layers, 02.138-C-Ducking und 02.141-C-Loudness bleiben. **Keine** echten 02.49–02.51-Schall-/Sensor-/Node-/Alarmwirkungen, 02.99-Weltaktionen oder 02.102-ACKs; 02.137/02.139/02.140-A-Ausschlüsse bleiben. Fachplanung, noch kein Code.

**Nicht beschlossen:** physikalische Doppler-/Schallgeschwindigkeitsformel, Cue-/Audioformatgrenzen, maximale Pitchratio und HRTF-/Playbackrateverhalten, Interpolations-/Velocitypräzision, Headtracking, genaue UI, DB/API/MVP. Ob mehrere bereits autorisierte Soundeffekte ergänzend lokale Hall-/Echo-Präsentationen erhalten können, ist eine eigenständige neue Frage.

## Nächste Entscheidung 02.146 – Lokale Hall-/Echo-Effekte für erlaubte Musik- und Soundboard-Cues

**Beispiel:** Ein bereits berechtigter Glockenton soll als akustische Stimmung eines großen Saales leicht nachhallen. Die SL möchte aber keine echten 02.49–02.51-Wand-/Sensor-/NPC-Hörbarkeitsdaten aus dem Hall ableiten lassen oder dabei geheime Raumgeometrie ausgeben.

- **A – Kein besonderes Hall-/Echo-Modul:** Nur vorhandene Track-/Stereo-/Mix-/Ducking-/Loudness-/Distanz-/ggf. Doppler-Ausgabe, keine eigene zusätzliche Raumhall-/Echo-Effektfunktion.
- **B – Weltweiten Hall aus allen geheimen Räumen ableiten:** Für alle Sounds werden ungefilterte NPC-/Geheimraum-/Wand-/Geometrieinformationen zu akustischen Raummodellen und echten Sensor-/Node-/Alarmwirkungen, unabhängig von Empfängerrechten.
- **C – Konfigurierbare rein lokale Hall-/Echo-Präsentation (Empfehlung):** Bei aktivem 02.132-Musikmodul kann die SL nach 02.25-Policy für wirklich berechtigte Audio-/Szenen-/Asset- und Empfänger-Cues **optionale begrenzte lokale Hall-/Echo-Presets** freigeben. Nur tatsächlich für den Hörer erlaubte Raumatmosphären/Parameter, keine versteckten Raumgeometrien/Schallradien/Secretpositionen, eigene Mutes/Browser-/Gainlimits bleiben. Kein globaler 02.133-A-Musiksync und kein 02.49–02.51-Spielwelt-`SoundEvent`-/Sensor-/Node-/Alarm-/World-/ACK-Effekt; Algorithmen und UI später.
