# AdventureShift – Karten-Workshop: Beschluss 02.141 C – konfigurierbare, ausschließlich lokale Lautheitsnormalisierung

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.141; nächste offene Entscheidung 02.142.
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungs-/Abnahmetestplan; **noch keine Softwareimplementierung**, keine endgültige DSP-Engine, API, Datenbank, Oberfläche oder MVP-Einstufung.
**Bezüge:** [02.25 – Kampagnen-/Rollenstandards und gültige markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.49–02.51 – eigenständige Schall-, Sensor- und Node-Spielweltfunktionen](KARTEN-WORKSHOP.md) · [02.99 – ausschließlich berechtigte echte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – offizielle Notices und bewusste ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – optionaler Chat](KARTEN-WORKSHOP-02.105.md) · [02.110 – Chat-Mutes/DM-Blocks](KARTEN-WORKSHOP-02.110.md) · [02.122 A – keine Chat-Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.132 C – optionales Musik-/Playlist-/Soundboardmodul](KARTEN-WORKSHOP-02.132.md) · [02.133 A – nur lokale Audiowiedergabe, ohne gemeinsame Musikuhr](KARTEN-WORKSHOP-02.133.md) · [02.134 C – rein lokale Fades/Loops/Layers](KARTEN-WORKSHOP-02.134.md) · [02.135 C – geschützte Audio-Vorlagen](KARTEN-WORKSHOP-02.135.md) · [02.136 C – kontrollierte Audio-Vorlagenrevisionen](KARTEN-WORKSHOP-02.136.md) · [02.137 A – keine Einfügeparameter für Audio-Vorlagen](KARTEN-WORKSHOP-02.137.md) · [02.138 C – nur lokales Soundboard-Ducking](KARTEN-WORKSHOP-02.138.md) · [02.139 A – keine besonderen visuellen Audio-Cue-Captions](KARTEN-WORKSHOP-02.139.md) · [02.140 A – kein privater Editor-Probehörplayer](KARTEN-WORKSHOP-02.140.md) · [Medien/Lizenzen](LIZENZEN.md).

## 1. Verbindliche Entscheidung – Variante 02.141 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Bei wirksam aktiviertem **02.132-C-Musik-/Playlist-/Soundboardmodul** kann die SL nach **02.25-Kampagnen-/Rollen-/Gruppen-/Szenen-/Personenstandards und gültigen markierten Ausnahmen** für geeignete, dem Hörer tatsächlich erlaubte Musik-, Ambient- und Soundboard-Audioquellen eine **optionale, sicher begrenzte, ausschließlich auf dem jeweiligen Hörergerät wirksame Lautheitsangleichung** aktivieren. Ziel ist es, erhebliche Lautheitsunterschiede zwischen rechtmäßig zugänglichen Audiodateien abzufedern, **ohne** die persönlich eingestellte Master-/Layerlautstärke, Stummschaltung, Browser-/OS-Autoplayregeln, andere Geräte, laufende Voicechats oder den Originaldateiinhalt umzuschreiben.

**Beispiel:** A hört rechtmäßig ein leises Tavernenstück und danach einen wesentlich lauter gemasterten Kampftrack. Wenn die Normalisierung für As wirklich autorisierten eigenen Player wirksam ist, kann dieser **auf eigener Ausgabeseite** für beide Quellen geeignete begrenzte Wiedergabekorrekturen vornehmen. B hört die Titel zu selbst gewählten anderen Zeiten oder hat die Musik stumm; weder As Wiedergabestand noch Bs persönlicher Masterpegel wird fremdgesteuert. Ein späterer berechtigter Glockenton kann nach **02.138 C** zusätzlich kurzzeitig die eigenen Musik-/Ambient-Layer absenken; Normalisierung und Ducking sind **verschiedene** lokale DSP-Funktionen.

**Nicht gewählt:** A (keine automatische Angleichung zwischen Audiodateien) und B (erzwungene einheitliche Lautheit für alle mit Übersteuerung persönlicher Regler/Mutes). **C ist keine Zusage identischer tatsächlich wahrgenommener Lautstärke**, keine systemweite Audioverstärkung und kein globaler 02.133-A-Wiedergabesync.

## 2. Eigene Schalter und Wahrung der Hörerhoheit

1. **Kampagne/Unterfähigkeit:** Musikmodul 02.132 An ist erforderlich; die **02.141-Lautheitsnormalisierung kann separat An/Aus** nach tatsächlich geeigneter 02.25-Policy konfiguriert werden, einschließlich gültiger markierter Ausnahmen. Bei Musik Aus entfällt jeder neue Modul-Audio-/Normalisierungspfad. Bei Normalisierung Aus gelten normale rechtmäßige Trackpegel und bisherige Master-/Layerregler.
2. **Quellen und Zielspuren:** Nur Audioquellen/Cues, auf die der jeweilige Empfänger nach **aktuellen** Kampagnen-/Actor-/Rollen-/Gruppen-/Szenen-/Asset-/Lizenz-/Geheimnis-/Medienrechten Zugriff hat; Audioarten Musik, Ambient, Soundboard getrennt einstellbar, soweit technisch unterstützt. Nicht rechtmäßige Quelle darf auch **nicht zum Zweck einer Lautheitsanalyse** ohne eigenes Recht gelesen werden.
3. **Keine SL-Fernlautstärke:** Kampagnen-Policy darf eine lokale Normalisierungsmöglichkeit erlauben oder einschränken, sie berechtigt aber **nicht zum Setzen/Überschreiben** persönlicher Masterlautstärke, persönlicher Layer-Lautstärke, Mutes, Browser-/OS-Hardwarelautstärke oder externer Voice-Audiopegel. Bestehende persönliche Audiosteuerung behält Vorrang.
4. **Nur Wiedergabekorrektur:** Fachziel ist eine dynamische oder aus geeigneten zulässig gewonnenen Quellinformationen berechnete, **pro Hörer lokal angewendete** Gain-Korrektur; Originaldatei, Album/Track-Metadaten und Lizenz bleiben unverändert. Keine obligatorische Normalisierung sämtlicher gespeicherter Musikdateien, kein automatischer Dateireencode, kein erzwungenes Upload-/Cloudaudioanalyseverfahren.
5. **Begrenzte Korrektur:** Gewünschte Lautheitszielbereiche, maximale negative/positive Korrekturen, True-Peak-/Clipping-/Limiter-Schutz, Umgang mit Stille/sehr kurzen Cue-Peaks und bevorzugte Quellenkategorien **später technisch definieren und testen**. C erlaubt keinesfalls unbeschränkte Verstärkung, Gehörschutzgefährdung oder immer lautere Endlosschleifen.
6. **Wahrnehmungsrealität:** Lautheitsmetriken/Analysedaten können stark von Wiedergabegerät, Dynamic Range, Tracklänge und tatsächlichem Audiosignal abhängen. Keine Behauptung, dass jeder Hörer dieselbe wahrgenommene Lautheit erhält oder leise Dialoge in Musik garantiert verständlich sind.
7. **Fehlende/fehlerhafte Analyse:** Bei nicht verfügbaren/inkompatiblen oder nicht hinreichend vertrauenswürdigen Quell-Metadaten darf der Player keine willkürliche unbeschränkte Gainkorrektur ansetzen; sichere begrenzte Standardwiedergabe bzw. kontrollierte Nichtanwendung der Korrektur ohne Geheimnis-/Medien-Existenzleck. Fallback und genaue Analysealgorithmik erst später.
8. **Personen-/Geräteautonomie:** Jeder Nutzer kann eigene Master-/Layer-Pegel und Mute ändern; Browser, OS, Decoder, Gerät und Hörbereitschaft entscheiden über tatsächliche Wiedergabe. Mute vor oder während Korrektur bleibt Mute und wird niemals nach Trackwechsel aufgehoben. Mehrere Geräte desselben Accounts dürfen unterschiedliche Ausgangspegel haben.
9. **Kein unverlangtes Mithören/Tracking:** Normalisierung erfordert **keine Mikrofonfreigabe**, keine Sprach-/Voicechat-Erkennung, keine Lautheitsmessung von Drittanwendungen und keine Aufzeichnung/Ausgabe fremder Hörerpegel, Cue-Listen oder Hörzeiten. 02.122-A-Chat-Voice-Memos und unabhängige Voicechatlösung bleiben.

## 3. Reihenfolge und Unabhängigkeit von Audio-Ducking, Crossfades und Spielwelt

| Teilfunktion | Verbindlicher Schutz von 02.141 C |
| --- | --- |
| **02.132 C normale Wiedergabe** | Weiter nur bei echter Actor-/Quelle-/Asset-/Lizenz-/Szenen-/Empfängerberechtigung und browserseitig zulässiger Wiedergabe |
| **02.133 A unabhängige lokale Wiedergabe** | Kein serverseitiger Playhead/Trackfortschritt/Seek/Pause-Sync, kein LateJoin-/Reconnect-Catch-up, keine globale „alle auf gleichem Pegel“-Anordnung |
| **02.134 C Fades/Loops/Layers** | Korrektur nur für eigene zulässige Track-/Layer-Ausgabe; Loop und Crossfade behalten lokale Zeitbasis und sichere Peak-/Mixgrenzen |
| **02.138 C Cue-Ducking** | Normalisierung ist **quellenbezogene Lautheitskorrektur** und Ducking **nur temporäre Absenkung eigener Musik-/Ambientbusse durch erlaubten Soundboard-Cue**; Faktor und persönliche Mutes sauber getrennt |
| **Persönliche Lautstärke/Mute** | Persönlicher Master-/Layer-Gain und Mute haben Vorrang; Normalizer darf seine Berechnung nicht als neuen User-Pegel zurückspeichern |
| **02.135-/02.136 C Vorlagen/Updates** | Template darf nur freigegebene Audio-Konfiguration referenzieren; keine automatische Roh-Audio-/Analyse-/Lizenz-/Assetfreigabe oder globale Änderung laufender Player |
| **02.137 A feste Audio-Vorlagen** | Kein zusätzlicher Normalisierungsparameterdialog beim Einfügen; zulässige Quell-/Zielkonfiguration nur nach eigenem bestehenden Edit-/Updatepfad |
| **02.139 A / 02.140 A** | Kein neuer visueller Sound-Caption-Toast und kein privater Editor-Audio-Probehörplayer durch Analyse oder Playbacknormalisierung |
| **02.49–02.51 Gameplay-Schall** | Normalisieren von Soundboarddatei oder Musik verändert **nicht** tatsächliche Welt-Hörbarkeit, Schallausbreitung, Lärmeradius, Sensor-/Alarm-/Nodeeingänge |
| **02.99 / 02.101–02.104** | Audio-Gain-Korrektur ist keine Weltaktion, Tür-/Quest-/NPC-/Würfel-/Turn-/Inventarwirkung und keine bewusste 02.102-ACK-Quittierung |
| **02.105, 02.110, 02.126** | Chat An/Aus, persönlicher Chatmute, unabhängige offizielle/Chatnotifications und Channelrechte bleiben von Normalisierung getrennt |

**Konzeptionelle Gainhierarchie:** Ein geeigneter lokaler Ausgabefaktor könnte aus `ownMasterGain × ownLayerGain × boundedSourceNormalizationFactor × authorizedDuckFactor` entstehen, unter absolutem persönlichem Mute, Audioautoplay und sicheren Peak-/Outputbegrenzern. **Das ist keine endgültige DSP-Formel/Implementation**: Quellen-/Mixer-/Limiter-Reihenfolge muss später unter anderem bei gleichzeitigen Layern, Attack-/Releasekurven und Clipping getestet werden. Normalisierung kann eine Quelle bis zu einem sicheren Limit anheben, während **Ducking nie verstärken** darf.

## 4. Sicherheits-, Daten- und Lebenszyklusmodell

1. **Rechte an Quellanalyse und Metadaten:** Nur rechtmäßig zugängliche Audiodateien/Streams und zugehörige freigegebene Analysewerte. Wenn die Quell-Metrik auf einem Server in erlaubtem Rahmen einmal berechnet/gespeichert werden sollte, ist das **keine** generelle Veröffentlichung der Datei, Waveform, Tracklänge, Musikquelle, Peak-/Loudnessmetadaten oder privaten Playlisten. Serverseitig aktuelle Owner-/Kampagnen-/Asset-/Lizenz-/Geheimnis-/Empfänger-/Medienrechte und Originalretention vor Abruf prüfen.
2. **Keine neue Schattenbibliothek:** Vorhandene Quell-Asset-/Lizenz-/Cache-/Retention-/CDN-/Mediengrenzen gelten; keine stillen neuen Vollkopien, durchgängigen Track-Transkripte, normalen Audio-Dumps oder DRM-Umgehungen durch Normalisierung. Analysemetadaten sind je Quelle/Version wirksam berechtigt und bei Rechteentzug für nicht Berechtigte zu invalidieren.
3. **Konfigurationsversion und Revisionsschutz:** Kampagnenfeature, gültige markierte 02.25-Ausnahmen, betroffene Cuekategorie/Layer, Quellasset/-revision und lokale Hörerpräferenz kontrollieren, ob und wie eine Korrektur im Moment wirken darf. Änderungen nach SceneSwitch, Role-/Gruppen-/Musik-Aus, Lizenzende, Quelllöschung oder neuen Rechten dürfen keinen alten geheimen Normalisierungsjob reaktivieren.
4. **Lokale Zustandsmaschinen:** Konzeptnamen `LocalAudioNormalizationCapability`, `AudioLoudnessEligibility`, `AuthorizedAudioLoudnessMetadata`, `LocalAudioNormalizationGain`, `LocalAudioGainComposition`, `LocalAudioPeakGuard`, `LocalAudioNormalizationAbortToken` (nur Arbeitsnamen). Keine globalen per-Teilnehmer-Lautheitslisten, Player-Timeline oder ferngesteuerten Gainoperationen.
5. **Cue-/Mix-Race und Fehlersicherheit:** Bei Trackwechsel, Layer-/Cue-Erzeugung, Crossfade, Duckstart/-ende, Mute, lokalem Playerstop, Tab-Suspend/-Resume, Gerätewechsel, Streamfehler oder Reconnect alte Gain-/Analyse-Tasks versioniert abbrechen bzw. im zulässigen eigenen neuen lokalen Zustand berechnen. Kein Double-Gain durch mehrfachen Cue-Event/Retry.
6. **Gültiger Outputschutz:** Bei sehr lauten oder mehrfach überlagerten Quellen maximal zulässige sichere Pegel/Peak-Begrenzung, bevor Ausgabe erfolgt; keine unkontrollierte kumulative Hochregelung durch wiederholte Normalisierung oder Looping. Persönlich niedriger gewählte Lautstärke bleibt maßgeblich, keine Zwangswiedergabe.
7. **Audiodaten und Datenschutz:** Kein Zugriff auf Audio anderer Apps/Voicechat, keine Mikrofonaufnahme oder Höreranalyse. Metriken über geheimen Titel dürfen nicht über Suchvorschauen, Error-Strings, Facets, Gesamtstatistiken, Realtime-/Chat-/Push-/Zähler-/OS-Lockscreen oder globale Template-Vorschau offengelegt werden.
8. **Technologiewahl offen:** Integrated-Loudness-/Peakmessung, RMS/EBU-R128/ReplayGain-artige Standards, adaptive On-the-fly-Berechnung versus geprüfte Metadaten, Offline-/Selfhosting-Budgets, Codec-/Laufzeitunterstützung, genaue Limiter und UX/Presets werden **erst später technisch verglichen**, nicht als beschlossen oder umgesetzt ausgegeben.

## 5. Konzeptioneller Umsetzungsplan

1. **Feature-/Policyvertrag:** Eigenes `LocalAudioNormalizationCapability` in 02.132-Musik An/Aus nach 02.25-Defaults/markierten Ausnahmen; relevante Musik-/Ambient-/Soundboard-Scopes und Berechtigungen definieren. Persönliches Master-/Layer-Mute ist keine veränderbare Serverpolicy.
2. **Freigegebene Quellmetrik:** Aktuelle Quell-/Owner-/Lizenz-/Asset-/Scene-/Empfänger-/Medien-ACL und versionsgebundene nur berechtigte Loudness-/Peakdaten; sichere Unterstützung fehlender/inkompatibler Metriken, ohne unrechtmäßigen Transcoding-/Streaming-/Dateiexport.
3. **Lokale Gainkomposition:** Audioplayer-/Mixeradapter mit begrenztem quellenbezogenem Normalisierungsfaktor, 02.134-C-Layer/Fade-/Loop-Pegel, 02.138-C-temporärem Duckfaktor, persönlichem Master-/Layer-Mute sowie Peak-/Clipping-/Browserautoplaygrenze. Keine gemeinsame Clock oder Fremdgerätsteuerung.
4. **Races/Revocation/Sicherheit:** Szenen-/Rollen-/Asset-/Policy-/Lizenz-/Musik-/Normalizer-Aus, Cuewechsel, Crossfade, mehrere Layer, Reconnect und Tab-Suspend behandeln; Mute/Nutzergainänderung hat Vorrang, alte Prozesse/Metadaten invalidieren, keine unberechtigte Dateidaten- oder Metadatenleckage.
5. **Abnahmetests und spätere Details:** Fachmatrix unten; Normalisierungsmetrik, Lautheitsziel-/Gain-/Peak-/Latenz-/CPU-/Quota-Limits, tatsächliche Medienbibliotheken, UI, DB/API und MVP später gemeinsam planen.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Musik 02.132 C bei Kampagnenerstellung Aus | Keine Normalisierungsanwendung, Chat/Würfel/02.51-Schallsystem unabhängig |
| Musik An, 02.141-Lautheitsnormalisierung nach 02.25 Aus | Kein neuer Normalisierungsfaktor; eigene Player-/Layerlautstärke bleibt |
| Musik An, Normalisierung für Musik An und zulässige Tracks | Sichere, nur lokale Angleichung erlaubter Track-Lautheit möglich |
| Musiknormalisierung erlaubt, Soundboard-Normalisierung verboten | Nur erlaubte Musikkategorie wird normalisiert |
| A hört leisen Track, B sehr lauten anderen Track | Beide individuell autorisierten lokalen Normalisierungen; keine zentrale Pegel-/Trackgleichschaltung |
| B startet denselben Track zehn Minuten später | Start lokal bei 0, keine 02.133-A-Playhead-/Loudness-Synchronisation |
| A stellt Masterpegel 20 Prozent ein | Normalisierung ersetzt diesen persönlichen Wert nicht und kann den Masterpegel nicht erzwingen |
| A mutet eigene Musik vor Trackstart | Audio bleibt stumm, normalisierter Gain entmutet niemals |
| A verändert eigene Lautstärke während Normalisierung | Neue eigene Einstellung gilt unmittelbar; kein Rücksprung zu altem Nutzer-Gain |
| Browser verweigert Audio-Autoplay | Kein Umgehen der Browser-/Nutzerzustimmung und kein Zwangsabspielen durch Gain |
| Source-Audioanalyse ergibt fehlenden Wert | Sicherer limitierter Fallback, keine unbegrenzte Verstärkung |
| Source-Asset enthält lange Stille und ein sehr lautes Geräusch | Limiter-/Peakschutz verhindert unkontrolliertes Aufdrehen auf gefährliche Pegel |
| Musik enthält extrem große Dynamiksprünge | Keine Garantie perfekter Wahrnehmungsgleichheit; sichere Outputgrenze bleibt |
| Trackquelle sehr laut gemastert | Lokal sicherer Normalizer darf eigenen Track begrenzt reduzieren |
| Trackquelle sehr leise gemastert | Nur innerhalb definierter Peak-/Gain-Sicherheitsgrenzen lokal anheben |
| Spieler besitzt keine Asset-/Lizenzberechtigung | Weder Audiosignal noch ausgelesene geheime Peak-/Loudnessdaten oder URL |
| Geheime SL-Playlist wird von Spieler erraten | Keine Track-/Cue-/Album-/Lautheitsmetadaten-/Count-/Existenzantwort |
| Quelle gehört privater anderer Kampagne | Kein CrossCampaign-Medien-/Analyse-/Listen-/Statistikleck |
| Assetlizenz wird während Wiedergabe entzogen | Neue Nutzung/Analysedaten gesperrt, beherrschbare lokale Ausgabe gestoppt |
| Source-Track wird gelöscht oder ersetzt | Alte Metrik nicht unberechtigt auf neue Assetversion anwenden |
| SL ändert Szene während laufender normalisierter Musik | ACL-/Scene-/Policyrevision gewinnt, kein versteckter alter Audiojob |
| A startet Crossfade zwischen zwei freigegebenen Tracks | Nur auf A lokal zwei Quellen mit sicherer individueller Korrektur, keine Fremdzeitbasis |
| Zwei Ambient-/Musiklayer werden gleichzeitig wiedergegeben | Kein unbegrenztes Stapeln hoher Gains oder systemweites Peak-/Clippingproblem |
| Lokaler Loop wiederholt lautheitskorrigierte Musik | Kein exponentielles Hochregeln durch jede neue Wiederholung |
| Soundboard-Glocke löst 02.138-C-Ducking aus | Ducking senkt eigene Musik **vorübergehend zusätzlich**, Normalisierung bleibt quellenbezogen |
| Ducking endet während A sein Mastergain verändert | Nur Duckfaktor wird beendet; der neue persönliche Pegel bleibt |
| Spieler ist stumm und Ducking endet | Weder Normalisierung noch Ende des Duckfaktors erzeugt hörbare Audioausgabe |
| Soundboard-Cue ist nicht berechtigt | Keine Audioquelle, keine Analyse-/Normalizer-/Ducking-Nebenwirkung |
| Browser-Tab suspendiert und reconnectet | Keine alte Musikposition, kein Normalisierungs-Catch-up, kein doppeltes Gain |
| Zwei Endgeräte desselben Nutzers | Keine globalen Lautheits-/Mute-/Playbackzustände, persönliche Geräte bleiben unabhängig |
| SL schaltet Normalisierung mitten in Sitzung Aus | Kontrollierter Rückgang zum gültigen lokalen Basis-/Layerpegel, ohne Nutzerwerte zu überschreiben |
| Quell- und Playlistvorlage 02.135 C geteilt | Nicht automatisch neue Audiofile-/Loudnessanalyse-/Lizenzrechte an Zielkampagne |
| 02.136 C neuer Vorlagenstand übernommen | Keine automatische Aktualisierung bereits laufender Medien/Normalisierungstasks |
| 02.137 A fest eingefügte Audiovorlage | Kein zusätzlicher Audio-Normalisierungsparameterwizard beim Einfügen |
| 02.139 A keine besonderen Cue-Captions | Normalizer erzeugt keinen neuen Text-/Symbol-/Untertitel-Hinweis |
| 02.140 A kein Audioeditor-Probehörplayer | Analyseoption eröffnet keinen neuen geheimen Editor-Previewstream |
| Audio heißt `alarm.mp3` oder `Tür öffnen` | Keine 02.49–02.51-Sensor-/Node-/Door-/Quest-/NPC-/Würfel-/Turnaktion aus Gain |
| Offizielles 02.102-ACK steht aus | Musik-/Gainkorrektur ist keine Bestätigung |
| Externer Voicechat läuft gleichzeitig | Voice-/Systemaudiopegel nicht verändert, keine Aufnahme/Lautheitsmessung dieser App |
| 02.122 A keine Chat-Voice-Memos | Normalisierungsanalyse eröffnet keine Mikrofon-/Voicecapture- oder Transkriptionspipeline |
| Music An, Chat 02.105 Aus | Rechtmäßig aktivierte lokale Normalisierung ohne Chat möglich |
| Mehrfacher Trackwechsel/Quick-Skip | Kein mehrfach gestarteter Gain-Job oder verwaister Normalizer pro Quelle |
| Sehr viele Media-/Metrik-Abfragen | Rate-/Quota-/ACL-/Cache-/SSRF-/Codec-/CPU-Schutz |
| Spieler sendet manipulierten Ziel-Gain und fremden Actor | Kein fremdes Lautstärke-Override oder Berechtigungsanstieg |
| Spieler besitzt 02.110-Chatmute | Eigene Music-Gain/-Mute-Einstellung bleibt unabhängig von Chat-/DM-/Systemnotifications |
| Vorhandene echte 02.51-Szenenschallvisualisierung | Behält eigene wahrheitsgemäße Hörbarkeits-/Sensorrechte unabhängig von Audio-Normalisierung |

## 7. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.141 C – getrennt schaltbare, quellen-/hörtatsächlich-berechtigte, sichere Lautheitsangleichung nur innerhalb des lokalen Musik-/Ambient-/Soundboard-Audioausgabepfads**, nach 02.132-Musik-An und wirksamer 02.25-Policy. Persönlicher Master-/Layer-Gain, Mute und Browserautoplay bleiben übergeordnet; 02.133 A ohne globale Play-/Seek-/Pause-/Join-Synchronisierung, 02.134 C nur lokale Fades/Loops/Layers, 02.138 C unabhängiger temporärer Duckingfaktor, 02.135-/02.136-C-Vorlagenrecht/Updates, 02.137 A keine Insertparameter, 02.139 A keine Audio-Captions und 02.140 A kein Editor-Probehörplayer bleiben ausdrücklich erhalten. Keine Dateiumschreibung, keine Audio-/Secret-/Lizenzfreigabe, kein OS-/Voicechat-/Mikrofoneingriff, kein 02.49–02.51-Game-SoundEvent-/Sensor-/Node-Effekt, keine 02.99-Spielweltänderung und kein 02.102-ACK.

**Nicht beschlossen:** exakte DSP-/Loudness-Messmethode, genormte Ziel-LUFS-/Peakwerte, Verstärkungs-/Limiter-/Hörschutzgrenzen, Latenzen, Codecs, zentrale/Client-Analysestrategie, tatsächliche UI/DB/API, MVP; alles folgt später als konkrete technische Entscheidung.

## Nächste Entscheidung 02.142 – Stereo-/Raumklangpositionierung von Musik- und Soundboard-Cues

**Beispiel:** Eine SL möchte bei einer Szene einen autorisierten Soundboard-Cue „knarrende Tür“ eher aus dem linken Kopfhörer hören lassen oder einer freigegebenen Umgebungsmusik eine räumliche Richtung geben. Das tatsächliche 02.49–02.51-Spielwelt-Schallmodell darf dadurch nicht versehentlich umgangen oder realer Sensor-/NPC-/Door-/Nodezustand geändert werden.

- **A – Keine besondere räumliche Audiopositionierung:** Musik-/Soundboarddateien spielen mit ihrem normalen Original-Stereosignal und persönlichen Lautstärkereglern. Keine eigene Pan-/3D-/Raumklanglogik.
- **B – Unbegrenzte zwangsgesteuerte Raumklangsimulation:** Jeder Audio-Cue erhält global eine Position und darf geheime Kartenkoordinaten/Hörzonen, fremde Kopfhörer-/Systemlautstärke und tatsächliche Schall-/Node-/NPC-/Alarmzustände ohne Rechte beeinflussen.
- **C – Optionale berechtigte lokale Audiopositionierung (Empfehlung):** Bei 02.132-Musik An kann die SL nach 02.25-Defaults/markierten Ausnahmen für ausdrücklich geeignete erlaubte Audio-Cues und Szenenkontexte rein lokale Pan-/Stereo-/ggf. 3D-Wiedergabeoptionen freigeben. **Nur** dem konkreten Hörer erlaubte Positionen/Audiosignale werden verwendet; persönliches Master-/Layer-Mute, Browser/OS und unterstützte Geräte bleiben maßgeblich. Keine globale 02.133-A-Musikuhr, keine automatische Offenlegung verborgener Szeneecken, keine 02.49–02.51-Game-SoundEvent-/Sensor-/Node-/NPC-/World-/ACK-Wirkung. Formate/UX später.
