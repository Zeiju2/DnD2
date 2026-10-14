# AdventureShift – Karten-Workshop: Beschluss 02.142 C – berechtigte lokale Stereo- und Raumklangpositionierung

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.142; nächste offene Entscheidung 02.143.
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungs- und Abnahmetestplan; **noch keine Softwareimplementierung**, keine finale Audio-Engine, kein endgültiges Datenbank-/API-Schema, UI oder MVP.
**Bezüge:** [02.25 – Kampagnenstandards und gültige markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.49–02.51 – eigenständige Schall-/Hörbarkeit-/Sensor-/Node-Spielwelt](KARTEN-WORKSHOP.md) · [02.99 – echte autorisierte Spielweltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – eigenständige offizielle Hinweise/ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat bei Kampagnenerstellung An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106–02.107 – Chatkanäle und aktuelle/historische Sicht](KARTEN-WORKSHOP-02.107.md) · [02.116 A – keine persönlichen Chat-Read-Receipts](KARTEN-WORKSHOP-02.116.md) · [02.122 A – keine Chat-Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.132 C – optionales Audio-/Soundboard-/Playlistmodul](KARTEN-WORKSHOP-02.132.md) · [02.133 A – nur lokale Musik und kein globaler Playhead/AutoJoin](KARTEN-WORKSHOP-02.133.md) · [02.134 C – lokale Fades, Loops und Layer](KARTEN-WORKSHOP-02.134.md) · [02.135–02.136 – rechtmäßig referenzierte/kopierte Audio-Vorlagen und gezielte Updates](KARTEN-WORKSHOP-02.136.md) · [02.137 A – keine Audio-Einfügeparameter](KARTEN-WORKSHOP-02.137.md) · [02.138 C – nur lokales Ducking](KARTEN-WORKSHOP-02.138.md) · [02.139 A – keine Audio-Cue-Captions](KARTEN-WORKSHOP-02.139.md) · [02.140 A – kein privater Editor-Previewplayer](KARTEN-WORKSHOP-02.140.md) · [02.141 C – begrenzte lokale Lautheitsnormalisierung](KARTEN-WORKSHOP-02.141.md) · [Medien/Lizenzen](LIZENZEN.md).

## 1. Verbindliche Entscheidung – Variante 02.142 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Bei tatsächlich aktiviertem **02.132-C-Musik-/Playlist-/Soundboardmodul** kann die SL nach **02.25-Kampagnen-/Rollen-/Gruppen-/Szenen-/Personenstandards mit gültigen markierten Ausnahmen** für ausdrücklich geeignete, für **den konkreten Hörer wirklich erlaubte** Musik-/Ambient-/Soundboard-Cues eine **getrennt schaltbare lokale Stereo-Pan-/Richtungs- und bei tatsächlicher Geräte-/Engineunterstützung optionale 3D-/Raumklangdarstellung** freigeben. **Nur heute sichtbar und hörbar berechtigte** Cue-/Audioquellen und **eigens berechtigte Positionen oder bewusst freigegebene Richtungsabstraktionen** dürfen zur Raumklangberechnung verwendet werden. Alle daraus erzeugten Signale werden **ausschließlich auf dem Gerät des jeweiligen Hörers** ausgegeben; weder tatsächliche Spielwelt-Schallphysik noch fremde Spielerhardware wird dadurch gesteuert.

**Beispiel:** Eine SL erlaubt einer Kampagnengruppe einen harmlosen, für die Gruppe sicht-/hörberechtigten Cue „Tür knarrt links“. Auf dem eigenen Gerät eines berechtigten Spielers kann dieser Sound nach korrekter Geräte- und Browserfreigabe nach links gepannt werden. Eine nur der SL bekannte Türposition, verborgene Falle oder ungehörte NPC-Bewegung darf **weder als geheimen Positionskoordinaten-Payload noch über den wahrnehmbaren Panwinkel oder räumliche Hörbarkeit** verraten werden. Ein anderer Spieler kann denselben erlaubten Track ohne Stereo-Hardware unverändert/mono hören, ohne dass die SL fremde Lautstärken ändert.

**Nicht gewählt:** A (prinzipiell nur Original-Stereo ohne Pan-/Raumklangfähigkeit) und B (alle Audio-Cues zwangsweise orten, obwohl Szene, Empfänger, Geheimnis, Browsergerät oder normale Schall-/Worldrechte dies nicht erlauben). **C beschließt kein automatisches Tracking bewegter Karten-/NPC-Quellen**, keinen globalen Wiedergabesync und keine 02.49–02.51-Schallkopplung. Bewegte räumliche Cues werden als **02.143** gesondert entschieden.

## 2. Konfigurierbare rein lokale Audio-Raumdarstellung

1. **Voraussetzung und echte Schalter:** 02.132-Musik **An** ist erforderlich; 02.142-Raumdarstellung kann getrennt An/Aus sein, auch bei Musik An. SL erlaubt geeignete Audio-/Cue- und Target-/Szene-/Rollen-/Gruppen-/Personenscopes gemäß 02.25-Defaults und gültigen markierten Ausnahmen. Nur fachlich tatsächlich implementierte räumliche Modi werden auswählbar; Sicherheit nie abschaltbar.
2. **Stereo und ggf. 3D:** Geeignete erlaubte Cuequellen können **lokal** zwischen linker/rechter Ausgabe gepannt oder mit optionaler, dafür unterstützter 3D-/HRTF-/Ambisonic-artiger Wiedergabe räumlich projiziert werden. Die **konkrete** DSP-Engine, Technik, HRTF-Filter, Geräteprofile, Surroundkanäle und Standardwerte sind später zu entscheiden, nicht mit C automatisch versprochen.
3. **Quell- und Positionserlaubnis in zwei Dimensionen:** Der Spieler benötigt **erstens** echte Musik-/Cue-/Audioasset-/Lizenz-/Empfängerrechte und **zweitens** die für genau diese räumliche Richtungsinformation wirksame **aktuelle** Szenen-/Fog-/Karten-/Geheimnis-/Rollen-/Gruppen-/Positionsfreigabe. Ein sichtbares Trackrecht ist **nicht automatisch** ein Recht auf versteckte Weltkoordinaten, NPCs, Schallbereiche oder Kartenobjekte.
4. **Abstrahierte Präsentationsrichtung nur explizit:** Eine SL darf als eigenständig autorisierte **Präsentationsinformation** z. B. „links“ statt echter Türkoordinaten anbieten, aber nur wenn schon diese hörbare Richtung selbst für die jeweiligen Empfänger freigegeben ist. Keine verdeckte Ableitung aus nicht erlaubten NPC-/Fallen-/Geheimszenen-Koordinaten. Falls keine gültige Richtung vorhanden ist: **sicherer neutraler Original-Stereo-/Mono-Fallback oder Ablehnung des räumlichen Modus**, nicht Herleiten verborgener Positionen.
5. **Hörerbezogener Raumbezug:** Links/rechts und optional 3D-Richtung erfordern einen sinnvoll autorisierten Hörer-/Kamera-/Szenenbezug; Kameraansicht, Kartenrotation, Schauspieler-/Tokenposition, Sicht-/Fogregion und die Ankerreferenz können für verschiedene Empfänger abweichen. **Jeder Empfänger erhält nur die für ihn entschärfte Darstellungsinformation**, niemals zentral die geheimen Quellkoordinaten. Welche Orientierungsbasis UI verwendet, wird später festgelegt.
6. **Persönliche Wahl und Gerät:** Eigene Master-/Layerlautstärke, Mute, 02.141-C-Loudnesskorrektur, 02.138-C-Ducking und Browser-/OS-Autoplayregeln bleiben **vorrangig**. Keine Aktivierung ungewollter Lautsprecherkanäle, systemweite Soundausgabe, Änderung fremder Kopfhörer oder erzwingbare Wiedergabe gegen Nutzer-/Geräteentscheidung. Nicht unterstützte 3D-/Stereo-/Monoausgabegeräte nutzen sicheren zulässigen Fallback.
7. **Keine Fernsteuerung und keine globale Uhr:** 02.133 A bleibt verbindlich. Richtung/Pan auf dem einen Player wird **nicht als gemeinsame Musikposition, Start-/Seek-/Pause-/Rundensync oder Join-/Reconnect-Catch-up** an andere Player verteilt. Jeder Track startet bei eigenem tatsächlichem Start bei Titelanfang.
8. **Audioquelle ist Präsentation, nicht physikalischer Schall:** Stereo-Pan, Hall/HRTF oder räumlicher Pegel suggerieren höchstens hörbare Richtung, **berechnen aber keine** 02.49–02.51-Schallausbreitung durch Wände, sensorische Hör-/Sicht-/NPC-/Alarmreichweiten, realen Schallsensor, Türöffnung oder Node-/Worldaktionen. **Nicht beschlossen:** Aus Kartenentfernung automatisch ableiten, wer ein Spielweltgeräusch hören darf.
9. **Statisch berechtigter Cue-Snapshot:** Bei normaler Cueausgabe wird nur die **aktuell rechtmäßig geprüfte räumliche Präsentationsangabe** für diesen Cue genutzt. Keine allein aus 02.142 C still eingeführte kontinuierliche Positionsverfolgung, Hidden-Scene-/NPC-Live-Telemetrie, überflüssige Realtime-/Profilupdates oder automatischer Pan-Neuberechnungsstream. **02.143** fragt nach einem eventuell eigenen geschützten Follow-/Update-Modus.
10. **Normalisierung, Mischen und Ducking:** 02.134-C-Layer-/Fades-/Loops, 02.138-C-temporäres Ducking und 02.141-C-begrenzte lokale Lautheitsnormalisierung dürfen nur innerhalb der bereits tatsächlich erlaubten Spuren wirken; keine höhere Verstärkung, breiterer Hörbereich oder Mute-Umgehung durch Richtungskorrektur. Finale DSP-Reihenfolge und Peak-/Clipping-/Downmix-Grenzen später prüfen.
11. **Keine neuen Editor- oder Captionkomfortmodule:** 02.137 A (keine Audio-Einfügeparameter), 02.139 A (keine zusätzlichen VisualCue-Captions) und 02.140 A (kein privater Audioeditor-Previewplayer) bleiben erhalten. Ein Positionsfeld als späteres **normales rechtlich erlaubtes Cue-/Szenen-Konfigurationsmerkmal** ist nicht automatisch ein neuer Vorlagen-Einfügeparameterdialog oder ein separater Previewplayer.

## 3. Schutz der Quell- und Spielweltberechtigungen

| Integrationsgrenze | Verbindliche Wirkung |
| --- | --- |
| **02.25 / 02.132 C** | Separate schaltbare Stereo-/Raumklang-Unterfähigkeit, echte Actor-/Owner-/Kampagnen-/Asset-/Lizenz-/Cue-/Empfängerrechte; kein globaler Mastervolume-Override |
| **Sicht-/Fog-/Szene-/Kartenrechte aus 02.1–02.51** | Auch die **akustisch wahrnehmbare Richtung** zählt als geschützte Information; Geheimquell-IDs, reale Koordinaten, Gruppen, versteckte NPC-/Tür-/Fallensektoren weder durch Position noch Panwinkel/Codec-/Preview-/Error-/Count ableitbar |
| **02.49–02.51 wirkliche Schall-/Sensor-/Nodewelt** | Raumklangausgabe erzeugt keinen Gameplay-`SoundEvent`, NPC-Hör-/Schall-/Licht-/Bewegungsmelder-/Alarm-/Nodeinput und verändert keine physikalische Spielszenen-Hörbarkeit |
| **02.99 / 02.101–02.104** | Panning erzeugt keinen Tür-/Quest-/NPC-/Würfel-/Turn-/Inventareffekt und quittiert keine offizielle 02.102-ACK-Pflicht |
| **02.133 A** | Keine globale Player-/Pan-/Track-Uhr, keine synchronisierte Seek-/Start-/Pausezeit oder Join-/Reconnect-Nachholung |
| **02.134 C / 02.138 C / 02.141 C** | Nur lokale Layer/Fades/Loops, separates begrenztes Ducking und sichere quellenbezogene Gainnormalisierung unter persönlichem Mute/Browserautoplay |
| **02.135–02.136 C / 02.137 A** | Nur autorisierte Audio-Vorlagen-/Revisionsfelder; keine Kopie geheimer Quellpositionen, kein Insertparameterdialog, keine ungefragten laufenden Positionsupdates |
| **02.139 A / 02.140 A** | Keine beim Soundboard-Cue erzeugten Text-/Symbol-/Caption-Hinweise oder Editor-Probehör-Sonderkanäle |
| **02.105 / 02.106–02.107 / 02.116 A / 02.122 A** | Chat optional, DMs/History gesondert geschützt; kein Microphone-/Voicechatmitschnitt, keine Chat-Voice-Memos, keine individuellen Receipts/wer-hörte-Pan-Statistiken |
| **Geräte-/Datenschutzgrenzen** | Keine System-/Hardware-/Fremdlautstärkeänderung, kein heimliches Headtracking, kein unautorisierter Positions-/Szenen-/Pan-/Count-/URL-/Ausgabeprofilabruf |

## 4. Konzeptionelle Architektur und Lebenszyklus

1. **Feature-/Cue-Policy:** Konzeptionelle `LocalAudioSpatialCapability`, `AudioSpatialCueEligibility`, `AuthorizedSpatialCueView`, `AudioSpatialPresentationDirection`, `LocalAudioSpatialRenderer`, `LocalAudioSpatialFallback` und `LocalAudioSpatialAbortToken` sind **Arbeitsnamen**, keine schon implementierten/API-/DB-Modelle. SL-Konfiguration nach 02.25 kann den lokalen Raumklangmodus gezielt erlauben, aber nie eigentliche Quell-/Positions-/Asset-/Secretrechte ersetzen.
2. **Strikte getrennte Autorisierung:** Serverseitig vor Cue-, Stream-, Position-, Kartenanker-, Route-/Kamera-Referenz- und Spatial-Daten-Projektion **pro Empfänger** (a) echte aktuelle Actor-/Kampagnen-/Gruppen-/Rollen-/Scene-/Asset-/Lizenz-/Medien-/Original-Cue-Rechte und (b) echte aktuelle Fog-/Geheimnis-/Position-/Karten-/Sicht-/Empfängerrechte validieren. Bereits rechtmäßig gehörte Infos sind nicht rückwirkend löschbar; neue Zustellung/Caches dagegen sperren.
3. **Projektion statt Rohkoordinaten:** Nur eigens freigegebene Präsentationsrichtung relativ zu einem erlaubten lokalen Hörerbezug, geeignetes unsensibles Cue-/Asset-Token und erlaubter Spatial-Modus an Client liefern. Keine versteckte echte Door-/NPC-/Token-/Fallentarget-ID, 3D-Position, Originalroute, Quell-/Kartenkoordinaten oder präziser Winkel, wenn diese nicht ausdrücklich zum Hörer-Scope gehören. **Auch die Klangrichtung selbst muss erlaubt sein.**
4. **Richtungs-/Playbackentscheidung lokal:** Erst nach Browser-/Hörer-Consent kann eigene Audioquelle links/rechts oder optional in einem unterstützten räumlichen Renderer ausgegeben werden. Normaler Track kann beim Start nach 02.133 A bei 0 beginnen, ohne andere Audioplayer/-Positionen zu verändern. Bei fehlender Hardware, Mono-Downmix oder nicht implementierter 3D-Engine sicher Originalton/neutraler Modus statt Audiozwang.
5. **Änderungen und Revocation:** Cue-/Quellasset-/Scene-/Fog-/Role-/Position-/Empfänger-/Kampagnen-/Lizenz-/Spatial-Unterfeaturewechsel führen zu neuer Sicht-/Richtungsberechtigungsprüfung, Invalidierung offener/gespeicherter Präsentationsparameter und kontrollierbarem Stop/Neutralfall des lokalen Spatial-Jobs. Keine unberechtigte Ortsinformation aus Cache/DeepLink/Realtime/Preview/Fehlercode.
6. **Keine Live-Entity-Telemetrie:** 02.142 autorisiert einen Cue-/Szenenkontext-Snapshot, nicht eine ständig aktualisierte Trackingquelle. Gleichzeitige Szenenwechsel, neue Spielerjoins, Browserreload, Modul-Aus, Playbackstop oder Reconnect dürfen nicht automatisch geheime Spatialwerte wiederholen. Ob erlaubte sich bewegende Quellen gerätelokal nachgeführt werden dürfen, ist **02.143 offen**.
7. **DSP-/Ressourcengrenzen:** Stereo-/Pan-/räumliche Filter, Mono-Kompatibilität, Clip/Peak-/Limiter-/CPU-/Decoder-/Batterie-/Latencybudgets; aktuelle eigene Master-/Layer-Mute-/Ducking-/Loudnessprioritäten. Keine unkontrollierten DSP-Matrixgewichte, Verfälschung von Nutzerbaselines, systemweiter Soundrouter oder unzulässige Mikrofon-/Headtrackinghardwarezugriffe.
8. **Integrität und Testbarkeit:** Serverseitige Idempotenz/Rate/Quota/Revision, getrennte reale 02.49–02.51-Schall-/Sensor-API und 02.99-World-Actions; Cue-/Spatial-Klick, Streaming oder Renderer dürfen nie eine Tür-, Quest-, NPC-, Node-, Inventar-, Würfel- oder 02.102-ACK-Aktion auslösen. Trennung von 02.132-Musikmodul-An-/Aus und Chat/Voice-Spielweise bewahren.

## 5. Konzeptioneller Umsetzungsplan (keine fertige Software)

1. **Separate Raumklangunterfähigkeit:** 02.132-Musik An mit effektiver 02.25-SL-Policy und gültigen Ausnahmen; geeignete Musik-/Ambient-/Soundboardtypen, Rollen-/Szene-/Gruppen-/Personenscopes, unterstützte lokale Pan-/3D-Modi und sichere Default-/Off-Zustände als späteres Capabilityinventar planen.
2. **Quell-/Positionssicht-Resolver:** Serverautoritative 02.132-Musik-/Cue-/Asset-/Lizenz-/Empfänger-/Scene-Rechte **UND** eigentliche 02.1–02.51-Sicht-/Fog-/Karten-/Positionsfreigabe je konkretem Hörer, vor jedem Spatial-Payload/Cache/Realtime/Link; berechtigte abstrahierte Darstellung statt fremder Rohkoordinaten.
3. **Gerätelokaler Spatial-Audioadapter:** Bei Browser-/OS-/Hardware-Eignung und freiwilligem legitimen Audio-Start Stereo-Panning, optional unterstützte 3D-Projektion, sicherer Mono-/Original-Stereo-Fallback; individueller Volume-/Mute-/02.138-Duck-/02.141-Normalisierung-/02.134-Layer-/Limiter-Vorrang, kein zentraler Audio-Playhead.
4. **Lebenszyklus und Geheimnisschutz:** Cue-/Scene-/Fog-/Rollen-/Gruppen-/Asset-/Lizenz-/Spatial-Policywechsel, Reconnect, SessionJoin, Stop, Browser-Tab und Medienrevisionen mit Redaktions-/Invalidierungs-/Abbruch-/Quota-/Rate-Grenzen; niemals stille Positionsverfolgung oder mehr Quellrechte per Audioeffekt.
5. **Abnahmetests und spätere Klärung:** Matrix unten. Konkrete 2D-/3D-Audiokomponenten, effektive räumliche Koordinatenauflösung, Mono-Hörbarkeit/Barrierefreiheit, Codec-HRTF/Audio-API, Geräte-/Kopfhörerprofil, UI und MVP erst nach vollständigem Featureworkshop spezifizieren.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Musikmodul 02.132 C bei Kampagnenerstellung Aus | Keine neue Musik-/Stereo-/Spatial-Unterfähigkeit; Chat/Würfel/02.51-Schallsystem unabhängig |
| Musik An, 02.142-Raumklang nach SL-Policy Aus | Normales rechtmäßiges Original-Stereo/Mono, kein eigenes neues Pan-/3D-Processing |
| Musik An, Spatial erlaubt, Track/Cue berechtigt | Auf eigenem Client zulässiger lokaler Pan-/Stereo-/falls unterstützt 3D-Effekt möglich |
| SL erlaubt Spatial nur für Soundboard, nicht Musik | Nur passende berechtigte Soundboard-Cues werden räumlich behandelt |
| Spieler A erhält Cue „Glocke links“ samt Sichtfreigabe | Bei gültiger Hörer- und Audio-ACL sichere linke lokale Wiedergabe, ohne neues WorldEvent |
| Spieler B ist nicht Cueempfänger | Weder Cue noch Richtung, Platzhalter, Sound, Count, Toast oder Secretmetadaten |
| B darf Audiodatei hören, aber nicht versteckte Türposition sehen | Kein aus Geheimkoordinaten abgeleiteter Pan-/3D-Winkel, neutraler sicherer Fallback oder Ablehnung |
| SL gibt abstrahiertes „links“ ausdrücklich auch für B frei | Nur bewusst berechtigte Präsentationsrichtung, keine präzisen verborgenen Türen-/NPC-Koordinaten |
| SL erlaubt keine Richtungsinformation für den versteckten Fallencue | Weder direction-label noch wahrnehmbares räumliches Geheimnis beim unberechtigten Hörer |
| Quell-Kartenposition liegt außerhalb aktuell sichtbarem Fog | Kein indirektes Entdecken durch Panwinkel oder spatial-media API |
| Audio-Asset-URL ist nur privat für SL | Keine Player-/Metrik-/URL-/Cue-/Spatial-Exfiltration an fremde Spieler |
| Spieler errät geschützte NPC-/Szenen-/Position-IDs | Kein gültiger Rohkoordinatenabruf, Count, Timing oder Error-Existenzleck |
| Spieler wechselt Kampagne | Keine Spatial-Parameter, Gruppenscopes oder Audio-Cues der anderen Kampagne |
| Spieler schaut/rotiert eigene Karte ohne entsprechende Targetfreigabe | Keine neu enthüllten versteckten Quellpositionen über Audio |
| Zwei Spieler haben unterschiedliche sichtbare Ausschnitte | Jeder bekommt ausschließlich einen für ihn berechtigten lokalen Richtungs-/Cuekontext |
| Kein sinnvoll erlaubter räumlicher Anker verfügbar | Neutraler Original-Stereo-/Mono-Fallback statt automatisch erratener Weltposition |
| Browser unterstützt kein 3D/HRTF | Regulär zulässiger Fallback, keine Behauptung garantierter 3D-Tontechnik |
| Mono-Lautsprecher oder nur ein Kopfhörerkanal | Keine zwangsgesteuerte Hardwareumstellung; nutzbarer sicherer Downmix/Originalton |
| Nutzer hat Mastermute aktiv | Kein hörbarer Pan-/3D-Ton, kein Auto-Unmute durch Spatial-Funktion |
| Nutzer verändert lokale Master-/Layerlautstärke | Seine neue Einstellung gilt, andere Spielerlautstärken bleiben unverändert |
| Browser blockiert Playback/Autoplay | Spatial-Payload allein erzwingt keinen Ton oder zusätzliche Geräteeinwilligung |
| A startet Sound jetzt, B erst später | Unterschiedliche unabhängige Playerpositionen, kein globales Spatial-/Musiksync |
| Spieler tritt später bei/reconnectet | Kein automatisches Nachspielen räumlicher Soundcues oder ursprünglicher Positionen |
| 02.134 C mehrere lokale Layer werden gemischt | Pan nur für zulässige eigene Spuren, keine neuen unberechtigten Layers oder Positionen |
| 02.138 C Glockencue löst erlaubtes Ducking aus | Nur eigener temporärer Music-Duckfaktor, keine Veränderung fremder Player/Positionsrechte |
| 02.141 C Audio-Lautheitsnormalisierung aktiv | Sichere begrenzte Sourcekorrektur, persönlicher Mute und Spatial-Peakgrenze bleiben |
| 02.137 A feste Audio-Vorlage wird eingesetzt | Kein zusätzlicher Spatial-Parameterdialog beim Einfügen |
| 02.136 C Vorlage erhält neue Quellrevision | Keine ungefragte Neupositionierung schon laufender Cues |
| 02.139 A keine VisualCue-Captions | Kein automatisch angezeigter Richtungstext/Untertitel nur wegen Cueplayback |
| 02.140 A kein privater Editorpreviewplayer | Stereo-/3D-Modus eröffnet keinen geheimen Probehörplayer |
| Soundboard-Cue heißt `Alarm` oder `Tür öffnen` | Kein echter SoundEvent-/Sensor-/Node-/Alarm-/Door-/Quest-/NPC-/Turneffekt |
| 02.51 echter Spielwelt-Schall erzeugt eigene Sicht-/Sensorwirkung | Ausschließlich unabhängige originale 02.51-Fachlogik, nie Music-Spatial-Richtung |
| Offizielle 02.102-ACK-Anforderung offen | Raumklang hören/stoppen/verändern quittiert nichts |
| SL nutzt externen Voicechat während Raumklang | Kein Mikrofonmitschnitt, Voicechat-Routing oder Fernlautstärkeänderung |
| 02.122 A Chat-Voice-Memos bleiben aus | Räumliches Audio erzeugt keine Chataufnahme-/Voice-Memo-Funktion |
| SL deaktiviert Raumklang während Cue läuft | Geordneter Abbruch/Neutralfall ohne Wiedergabe geheimer Winkel |
| Quellgruppen-/Fog-/Asset-/Lizenzrecht wird während Playback entzogen | Neue Spatial-/Medienzustellung gestoppt; Caches/Renderer redigiert, soweit kontrollierbar |
| Zwei gleichzeitig erlaubte räumliche Cues | Bounded DSP-/Rate-/CPU-/Peak-/Gainlimits statt unkontrolliertem Audio |
| Client manipuliert `spatialPosition` mit fremder Target-ID | Kein fremder Scene-/NPC-/Position-Lookup oder Quell-Audiozugang |
| SL versucht globales Live-Tracking aller NPC-Audiopositionen | 02.142 erlaubt nur zulässigen Moment-Snapshot; bewegte Quellen bleiben 02.143 offen |
| SceneSwitch und Audio-Cue-Race treffen gleichzeitig ein | Aktuelle Scene-/Policyrevision bestimmt, keine alte geheime Richtung |
| Server-/Client-Reconnect wiederholt alten Spatial-Command | Keine automatische Neu-Audiowiedergabe, kein doppelter Event-/Playheadcommit |
| 02.105 Chat bei Kampagnenerstellung Aus | Autorisierte Spatial-Musik bleibt unabhängig; keine neue Chatpflicht |
| Normale zugängliche Audio-UI ohne 02.139-Captions | Reguläre Bedienbarkeit erhalten, keine neue Cue-Caption-Schicht |
| Ausgeschiedener Spieler hat noch alte Cache-Cue-ID | Kein erneuter abgeleiteter Kartenwinkel oder Medien-/Countzugang |

## 7. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.142 C – bei aktivem 02.132-C-Audiomodul, nach 02.25 gültigen markierten Ausnahmen und echten heutigen Audio-/Szenen-/Fog-/Position-/Kampagnen-/Lizenz-/Empfängerrechten getrennt konfigurierbare ausschließlich lokale Stereo-/Pan-/falls tatsächlich unterstützte 3D-Raumklang-Präsentation.** Geheime **Richtungen selbst** dürfen nicht akustisch verraten werden, auch nicht durch sanitisierte, aber nicht freigegebene Panwinkel. Eigenes Master-/Layer-Mute, Browser und Hardware bleiben maßgeblich; 02.133 A ohne globale Player-Uhr, 02.134 C lokales Layer-Mixing, 02.138 C Ducking und 02.141 C begrenzte Gainnormalisierung bleiben. 02.135-/02.136-C Audio-Vorlagen/Updates, 02.137 A ohne Audio-Einfügeparameter, 02.139 A ohne Cue-Captions und 02.140 A ohne Editor-Probehören bleiben. Kein 02.49–02.51-Spielszenen-SoundEvent-/Sensor-/Node-/Alarmbetrieb, kein 02.99-Weltcommit oder 02.102-ACK aus räumlicher Präsentation.

**Nicht beschlossen:** finale Pan-/3D-DSP-Engine, HRTF/Headtracking, tatsächliche Karte↔Hörer-Orientierungsreferenz, dynamisches Nachführen bewegter Quellobjekte, Entfernung/Dämpfung, Formate/Codec, UI/DB/API/MVP. **02.143** entscheidet gesondert, ob bereits erlaubte Raumklangquellen bei Bewegungen aktualisiert werden dürfen; 02.142 enthält nur einen derzeit berechtigt geprüften Präsentations-Snapshot.

## Nächste Entscheidung 02.143 – Räumliche Musik-/Soundboard-Cues bei Bewegung nachführen

**Beispiel:** Eine schon freigegebene Raumklangquelle steht zu Beginn links vom Spieler und bewegt sich später innerhalb eines für ihn tatsächlich sichtbaren/erlaubten Bereichs. Soll der lokale Panwinkel fortlaufend dem echten **berechtigten** Szenenkontext folgen? Das ist eine reine Darstellung; es darf weder ungehörte NPC-Positionen verraten noch echte Spielszenen-Schall-/Sensordaten erzeugen.

- **A – Räumliche Position bleibt statisch:** Ein berechtigter Audio-Cue verwendet nur seine zum Start zulässige links/rechts-/3D-Position. Spätere Bewegung führt den bestehenden Cue nicht automatisch nach; für neue Position ist ein neuer bewusster berechtigter Cue nötig.
- **B – Alle Positionen jederzeit verfolgen:** Alle Musik-/Soundboard-Cues verfolgen unbegrenzt sämtliche NPC-/Token-/Szenenbewegungen, unabhängig von Fog, Secrets, Kampagnenrechten, persönlichem Mute oder Playberechtigung, und geben die Bewegungsdaten an jeden Client weiter.
- **C – Konfigurierbare geschützte lokale Nachführung (Empfehlung):** Bei aktivem 02.132-Musik- und tatsächlich aktiviertem 02.142-Raumklangmodul kann die SL nach 02.25-Policy für **ausdrücklich geeignete** Cues ein ressourcenbegrenztes, **pro Hörer bei jedem relevanten Update erneut sicht-/empfänger-/quellberechtigtes** Nachführen einer ohnehin rechtmäßig freigegebenen Darstellungsrichtung erlauben. Nur entschärfte wirklich erlaubte Winkel auf dem eigenen Gerät, keine verborgenen NPC-/Tür-/Fog-/3D-Rohkoordinaten, keine 02.133-A-Globalaudio-Uhr, keine World-/02.51-Schall-/Sensor-/Node-/ACK-Wirkung; UI/technische Frequenz später.
