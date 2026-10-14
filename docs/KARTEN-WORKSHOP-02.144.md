# AdventureShift – Karten-Workshop: Beschluss 02.144 C – sichere ausschließlich lokale Distanz-Pegeldämpfung für räumliche Audio-Cues

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.144; nächste offene Featurefrage 02.145.
**Status:** Verbindlicher Fachbeschluss mit konzeptioneller Umsetzung und fachlichen Abnahmetests; **noch keine Softwareimplementierung**, keine endgültige Audio-Engine, API-/DB-Verträge, UI oder MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnen-/Rollenstandards und gültige markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.49–02.51 – echte Schall-/Wand-/Sensor-/Node-Spielwelt](KARTEN-WORKSHOP.md) · [02.99 – echte autorisierte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – unabhängige offizielle Hinweise/ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – optionaler Chat](KARTEN-WORKSHOP-02.105.md) · [02.110 – Chatmutes/DM-Senderblock](KARTEN-WORKSHOP-02.110.md) · [02.116 A – keine individuellen Lesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.122 A – keine Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.132 C – optionales Musik-/Playlist-/Soundboardmodul](KARTEN-WORKSHOP-02.132.md) · [02.133 A – nur lokales Playback, ohne gemeinsame Musikzeit](KARTEN-WORKSHOP-02.133.md) · [02.134 C – lokale Loops/Fades/Layers](KARTEN-WORKSHOP-02.134.md) · [02.135-/02.136 C – geschützte Vorlagen/Versionsupdates](KARTEN-WORKSHOP-02.136.md) · [02.137 A – keine Audio-Insertparameter](KARTEN-WORKSHOP-02.137.md) · [02.138 C – begrenztes lokales Ducking](KARTEN-WORKSHOP-02.138.md) · [02.139 A – keine Audio-Cue-Captions](KARTEN-WORKSHOP-02.139.md) · [02.140 A – kein Editor-Previewplayer](KARTEN-WORKSHOP-02.140.md) · [02.141 C – sichere lokale Lautheitsnormalisierung](KARTEN-WORKSHOP-02.141.md) · [02.142 C – berechtigte räumliche Stereo-/Pan-/3D-Cues](KARTEN-WORKSHOP-02.142.md) · [02.143 C – optionales pro Update berechtigtes Nachführen bewegter Cues](KARTEN-WORKSHOP-02.143.md).

## 1. Verbindliche Entscheidung – Variante 02.144 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Wenn das **02.132-C-Musikmodul aktiviert** ist und die **02.142-C-räumliche Audiofähigkeit tatsächlich aktiviert** ist, darf die SL nach 02.25-Kampagnen-/Rollen-/Gruppen-/Szenen-/Personenstandards mit gültigen markierten Ausnahmen für **ausdrücklich geeignete, jeweils tatsächlich hör- UND distanzberechtigte Cues** eine **separat schaltbare, begrenzte, rein gerätelokale Entfernungs-/Lautstärkedämpfung** vorsehen. Die eigene Musik-/Ambient-/Soundboardquelle kann bei für diesen konkreten Hörer erlaubter Entfernung **lediglich innerhalb sicherer Grenzen leiser** gemischt werden. Die wahrnehmbare Distanz-/Lautheitsänderung selbst ist eine **geschützte Information** und darf weder einen verborgenen NPC noch eine geheime Quelle, Szene oder Strecke verraten.

**Beispiel:** Ein Spieler darf einen Wagen sehen, sein Motoraudio tatsächlich hören und seinen Abstand kennen. Der Wagen fährt weg; bei optional eingeschalteter **02.143-C-Followfähigkeit** und erneuter Berechtigungsprüfung kann der eigene lokale Player für diesen Cue einen geringeren Dämpfungsfaktor verwenden. Ein anderer Spieler ohne Distanzfreigabe erhält weder diesen Pegelverlauf noch die Quelle-/Objekt-/Entfernungsdaten. Sein normaler Player darf nur dann einen neutralen räumlichen bzw. nicht-räumlichen Audiomodus verwenden, wenn sein **Audio-Recht unabhängig davon weiterbesteht**.

**Nicht gewählt:** A (überhaupt keine spezielle lokale Distanzdämpfung) und B (automatische gemeinsame physikalische Reichweite, globale Spielerpegel und Schall-/Sensor-/NPC-/Alarm-/Nodewelt aus Audiowiedergabe). C **ändert keine Spielwelt-Hörbarkeit** und verspricht keine konkrete realistische Ausbreitungsformel oder perfekte Wahrnehmungskonsistenz.

## 2. Aktivierung, Distanzsicht und lokale Pegelregeln

1. **Drei unabhängige Schaltergrenzen:** 02.132 Musik **An**, 02.142 Spatial **An** und 02.144-Distanzdämpfung **separat An** nach 02.25 wirksamen Defaults/markierten Ausnahmen. Ohne diese Kombination keine neue Distanz-Gainoperation. **02.143 Follow An** ist *zusätzlich* erforderlich, wenn sich die einmal erlaubte Entfernung **während** des laufenden Cues fortlaufend ändern soll; mit Follow Aus bleibt nur ein einmalig rechtmäßig zulässiger Distanz-Snapshot am Cue-Start.
2. **Nur zugelassene Cues:** SL wählt ggf. geeignete Rollen/Szenen/Personen/Cuetypen für Distanzpräsentation. Die Fähigkeit gibt weder neuen Audioasset-/Cue-/Lizenz-/Empfängerzugang noch irgendein Recht auf genaue Karten-/NPC-/Tür-/Fallen- oder Fogpositionen. Die konkrete Audioquelle muss bereits nach 02.132 und 02.142 wirklich zulässig sein.
3. **Zwei getrennte Auth-Ebenen plus Distanzrecht:** Vor der jeweiligen Quell-/Dämpfungsprojektion echte (a) Actor-/Campaign-/Cue-/Asset-/Medien-/Lizenz-/Recipientrechte und (b) gegenwärtige Karten-/Szene-/Fog-/Höreranker-/Quellpositions-/Secretrechte **und ausdrücklich die für den Viewer zulässige Entfernungsinformation** prüfen. Eine erlaubte Richtung **ist kein Distanzrecht**. Entfernung in Rohmetern ist nicht erforderlich, wenn nur **explizit freigegebene** geeignete grobe Distanz-/Pegelstufen als Präsentation zulässig sind.
4. **Hörbare Distanz ist selbst ein Secret:** Ein monoton leiser werdender Motor kann eine Bewegung, Entfernung, Geschwindigkeit, Annäherung, Eintritt/Austritt aus Fog und Anwesenheit implizieren. Der Server muss **nicht nur den Datenpayload**, sondern auch den daraus wahrnehmbaren lokalen Pegelverlauf anhand der tatsächlich freigegebenen Infos schützen. Keine differenzierten Gainupdates/Counts/Cursor/Lücken/Fehler/Subscriptionstatus an Unberechtigte.
5. **Sanitisierte Projektionswerte:** Client erhält höchstens eine **für ihn heute freigegebene abstrahierte Audio-Dämpfungsinformation** (z. B. begrenzter normierter Faktor oder rechtmäßige grobe Stufe), nicht ungeprüfte exakte Entity-/NPC-/Door-/Fallentarget-IDs, 3D-Rohkoordinaten, Entfernungen oder Quellgeschwindigkeiten. Keine Ableitung neuer Präzision durch wiederholte Queries/Pan-/Distance-Probes.
6. **Distanzfaktor nur dämpfend:** Konzeptionell `authorizedDistanceGain` im sicheren Bereich **0 bis 1**. 02.144 hebt weder persönliche Master-/Layer-Lautstärke, 02.141-C-quellenbezogenen begrenzten Normalisierungsfaktor noch 02.138-C-temporäre Duckingkurven an. Ohne gültige Distanzberechtigung **kein** versteckter Distanz-Gain: neutraler zulässiger Modus nur bei unabhängig weiter bestehender Cue-/Audioberechtigung, andernfalls Stop/Abbruch.
7. **Gainhierarchie ohne Masterüberschreibung:** Konzeptionell `localOutput = ownMasterGain × ownLayerGain × boundedNormalizationGain × authorizedDuckGain × authorizedDistanceGain`, mit absolutem Master-/Layer-Mute, Browser-/OS-Autoplay- und Peak-/Clipping-/Limiter-Schutz. **Nicht finale DSP-Formel.** Der Distanzfaktor verändert **keine gespeicherte** eigene Lautstärkepräferenz.
8. **Distanzberechnung ist nicht Hörbarkeitsrecht:** Der Distanzfaktor entscheidet **nur über die lokale Wiedergabe einer bereits erlaubten Quelle**, nicht darüber, ob ein echter NPC ein Geräusch hören kann, Wände Schall schlucken, ein Schallsensor auslöst oder ein Licht-/Tür-/Alarm-/Nodeoutput entsteht. **02.49–02.51** bleiben die maßgebliche **unabhängige Spielweltlogik**.
9. **Dynamic nur bei 02.143 C:** Eine bewegte Audioquelle darf nur dann laufende Distanz-Dämpfungsupdates erzeugen, wenn die eigenständige **02.143-Followpolicy** aktiv ist und **jedes Update** heute erneut echte Cue-/Recipient-/Scene-/Fog-/Entfernungsrechte erfüllt. Ein statischer 02.142-Snapshot allein ist keine Erlaubnis zum Live-Tracking.
10. **Bei Rechteverlust sicher stoppen/neutralisieren:** Cueende, Gruppentausch, Rollenwechsel, Sicht-/Fog-/Distanzrechtentzug, Source-/Asset-/Lizenzrevocation, Spatial-/Distance-/Follow-/Musik-Aus, SceneSwitch, Browser-Tabpause oder Reconnect invalidieren alle künftig unberechtigten Dämpfungs-/Medien-/Abo-/LocalDSPjobs. **Kein** Weiterverarbeiten des letzten geheim gewordenen Distanzfaktors; bereits gehörte Geräusche können menschlich nicht rückwirkend ungehört werden.
11. **Keine Positions-/Entfernungs-Historie:** Keine automatische Track-/Distanz-/Pan-Replay-History, keine an neue Mitglieder gelieferte private Distanzspur, keine exakten Spieler- oder NPC-Pfade in Playlist-/Vorlagen-/Revisionsmetadaten, Cache-/Search-/OS-Notifications oder technischen Diagnosen unberechtigter Personen. Distanznormalisierung ist **kein** weiteres Trackingfeature.
12. **Ressourcen und Hörschutz:** Eingrenzung von Pegelkurven, maximaler Dämpfung/Blendzeiten, Updatehäufigkeit, Zahl gleichzeitiger Spatialquellen, Codec/CPU/Peak/Ratelimits; konkrete mathematische Distanzkurve, Einheiten, Dämpfungsradius, Subjekt-/Kameraanker und Hörergeräte-UX werden **später** festgelegt.
13. **Unabhängig von Voice/Chat/Notices:** Kein Mikrofonmitschnitt, Voicechat-/Hardware-/OS-Lautstärkeeingriff, Audio-Caption-/Toast-Erzeugung oder Auto-ACK. Externer Voicechat und deaktivierbarer 02.105-Chat bleiben unabhängig; 02.116 A, 02.122 A, 02.139 A und 02.140 A bleiben unverändert.

## 3. Einordnung in bestehende Features

| Beschluss | Zwingende Grenze |
| --- | --- |
| **02.25 / 02.132 C** | Music An, separat erlaubte Distanzunterfähigkeit, gültige SL-Standards/Ausnahmen, tatsächliche Actor-/Audioasset-/Lizenz-/Recipientrechte |
| **02.142 C** | Spatial An mit aktuell erlaubter Richtung; **zusätzlich separat** tatsächliches Distanzrecht, kein stilles Extrahieren geheimer Weltkoordinaten |
| **02.143 C** | Laufende Distanzänderungen nur bei erlaubtem Follow, für **jedes neue Bewegungs-/Distanzupdate** erneute wirklich gültige Quell-/Fog-/Szenen-/Entfernungsrechte |
| **02.133 A** | Jeder Track startet lokal bei 0, kein gemeinsamer Musikplayhead/-Sync, kein AutoJoin/AutoReconnect-Catch-up; Distanzupdates sind keine Audiotransportuhr |
| **02.134 C / 02.138 C / 02.141 C** | Lokale Fades/Loops/Layers, temporärer **nur reduzierender** Duckfaktor und quellenbezogene sichere Lautheitsnormalisierung bleiben getrennt vom neuen **nur reduzierenden** Distanzfaktor |
| **02.135-/02.136 C / 02.137 A** | Audio-Vorlagen/Versionsupdates kopieren keine geheimen Positions-/Distanzrechte, Einfügen erfolgt ohne eigenen Parameterwizard |
| **02.139 A / 02.140 A** | Keine zusätzlichen VisualCue-Captions oder Editor-Sonderprobehörstreams durch Entfernung/Gain |
| **02.49–02.51 tatsächliche Akustik** | Keine neue echte SoundEvent-/Wand-/NPC-Hörbarkeits-/Schall-/Bewegungssensor-/Alarm-/Nodewirkung aus lokaler Entfernungs-Gainkurve |
| **02.99 / 02.101–02.104** | Kein Quest-/NPC-/Door-/Würfel-/Turn-/Inventarcommit oder amtliches 02.102-ACK bei Distanzänderung |
| **02.105 / 02.110 / 02.116 A / 02.122 A** | Kein Chatzwang, kein Auslesen fremder Hör-/Mutes, keine Chat-Receipts/Voice-Memos, kein Mikrofon-/Voicechat-Audiozugriff |
| **Browser/OS/Privatsphäre** | Persönlicher Master-/Layer-Mute gewinnt, Hardware-Mono- und Wiedergabebeschränkungen respektieren, keine fremde systemweite Lautstärkesteuerung |

## 4. Konzeptionelle Architektur und Lifecycle

1. **Fachmodelle nur als Entwurf:** `LocalAudioDistanceCapability`, `AudioDistancePresentationEligibility`, `AuthorizedCueDistanceProjection`, `LocalAudioDistanceGain`, `LocalAudioDistanceEnvelope`, `AudioDistanceRecipientDecision`, `LocalAudioDistanceAbortToken`; **keine** endgültigen DB-/API-Namen.
2. **Quelle bleibt echte Weltbewegung:** Ein bereits autoritativ existierender Szenen-/Entitypositionsstand kann **read-only** in eine räumliche Audiopräsentation einfließen. Weder dessen Quellbewegung noch eine daraus abgeleitete Entfernung erzeugt ein neues WorldEvent, Würfel-, Node-, Schall-, Alarm- oder NPC-Aktionskommando.
3. **Pro Hörer doppelt/trippelt geprüft:** Vor statischer und bei 02.143 erlaubter dynamischer Distanzpräsentation Quellcue-/Actor-/Asset-/Lizenz-/Recipient-ACL, Karten-/Fog-/Szene-/Position-/Richtungs-ACL und die eigenständige **Distanzpräsentationsfreigabe** serverseitig neu prüfen. Ausgabe nur zulässiger **minimierter Distanz-/Gainstufe**; keine Rohzielposition oder geheimen Quellobjektbezug vorhersagbar im Clientstream.
4. **Sicherer Distanzwert statt physikalische Wahrheit:** Angezeigte Hörpegel/ggf. abstrahierte Entfernungsrelation haben nur den Status der **für den Hörer freigegebenen Audiopräsentation**, niemals eines 02.51-SoundEvent-Hörbarkeitsprädikats. Gleiche Weltquelle kann zwei unterschiedlich berechtigte Presentergebnisse liefern, ohne tatsächliche Weltregeln zu verändern.
5. **Client nur sichere Gainberechnung:** Eigener bounded `distanceGain <= 1`, unabhängig von `normalizationGain` und `duckGain`, unter persönlich gewähltem Master-/Layergain und Mute. Optionale 02.134-C-Fades/Loops/Layers bleiben Gerätelokal; kein globales Gain-/Time-/Playheadcommand an die Gruppe.
6. **Updates/Abort:** Nur bei 02.143-Follow An, erlaubter fortlaufender Cue und gültigem Distanzrecht revisionsgebundene neue Gainprojektion. Cue-Stop, Rolle/Fog/Distanzrecht, Audio-Lizenz, Szene, Musik-/Spatial-/Distance-/Follow-Aus invalidieren Updatejobs/Caches. Out-of-order-/Replay-/Retry-/Multidevice-Requests, Rate-/Abo-/Quota-/Peak-/CPU-Guards.
7. **Falling back ohne Geheimnisleck:** Fehlt gültige Distanzinformation, darf nicht anhand verborgener Koordinaten ein „ungefähr nah“-Gain geschätzt werden. Stattdessen keine weitere Distanzprojektion, ggf. neutrale, ohnehin berechtigte Audioquelle oder Abbruch; keine versteckte letzte Distanz/Hörerbewegung aus alten Daten einfrieren, kein Count-/Error-/Timing-Hinweis.
8. **Keine neue Medien-/Positionstelemetrie:** Weder SL noch andere Spieler erhalten aus dieser Funktion fremde individuell gewählte Lautstärken, Hörstatistiken, NPC-Koordinaten, Distanzverläufe, Playbackzeit, Abozählung oder eine neue gemeinsame MusicClock. Technische Audits dürfen Zugriffe sichern, nicht als unberechtigte Benutzerberichte offenlegen.
9. **MVP-/Technikgrenze:** Konkrete Radius-/Einheiten-/Meter-/Grid-/Höreranker-/Dämpfungskurve, Grenz-/Clippingwerte, Szenenkoordinatensystem, Audio-Engine-/DSP-/Latenz-/Glättungsdetails, UI/DB/API/MVP werden später entschieden. 02.144 C wählt das **Fachverhalten**, nicht seine Formel.

## 5. Konzeptioneller Umsetzungsplan (noch keine Software)

1. **Capability-/Policy-Trennung:** 02.132 Music An + 02.142 Spatial An + separat 02.144 Distance On mit wirksamem 02.25-Actor-/Scene-/Cue-/Rollen-/Gruppen-/Hörerscope; laufende Folgebewegung nur bei 02.143 Follow An.
2. **Echte Quell-/Distanzfreigabe:** Serverresolver für wirkliche Original-Cue-/Asset-/Lizenz-/Medien-/Empfängerrechte, aktuelle Karte-/Fog-/Quell-/Hörerposition-/Richtungserlaubnis sowie **eigene heutige Distanzpräsentationsfreigabe**. Bei der Projektionsausgabe nicht auf Clientautorisation vertrauen.
3. **Minimierte Distanzprojektion:** Nur für den Viewer erlaubte Distanzklasse/relative Gainstufe statt echter Quell-/Hörer-/Weltkoordinaten. Bei unberechtigter oder nicht verfügbarer Entfernung neutraler zulässiger Modus/Abbruch statt Shadow-Quelle oder Positionsprobe.
4. **Eigener lokaler DSP-Faktor:** Sicher begrenzte Distanzdämpfung zusätzlich zu 02.141-Normalisierung, 02.138-Ducking, 02.134-Layer/Fades/Loops und eigenem Master-/Layermute; Browser/OS/Hardware/Hörbereitschaft maßgeblich. Distanzfaktor niemals zur lokalen *Verstärkung* oder globalen Spielwelt-Hörregel umdeuten.
5. **Revocation-/Ressourcentests:** Distanz-Cue-Revisions-/Fog-/Scene-/Role-/Policy-/Asset-/Cue-/Follow-/Distance-Aus-/Join-/Reconnect-/Race-/Rate-/Quota-/Peak-/Privacy-/NoWorld-/NoSensor-/NoACK-/NoSync-Abnahmetests; konkrete DSP-/Einstellungs-/MVP-Entscheidungen zurückstellen.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Musikmodul 02.132 C bei Erstellung Aus | Keine Audio-/Distanzdämpfung; Chat, Würfel und echte 02.51-Schallfunktion unabhängig |
| Musik An, 02.142 Spatial Aus, Distance An | Keine Distanzdämpfung ohne wirkliche Spatial-Fähigkeit |
| Musik/Spatial An, Distance Aus | Normaler berechtigter räumlicher Cue ohne eigenen Distanzpegel |
| Musik/Spatial/Distance An, statischer erlaubter Wagen | Nur anfänglich vollständig erlaubter Distanz-Snapshot, kein Live-Tracking bei 02.143 Follow Aus |
| Musik/Spatial/Distance/Follow An, erlaubter Wagen fährt weg | Nur pro Hörer erneut autorisierte, lokal begrenzte Dämpfung bei erlaubtem Bewegungsupdate |
| Spieler A kennt Wagen und Entfernung | A kann berechtigten Distanzgain auf eigenem Audio hören |
| Spieler B darf Wagen hören und Richtung kennen, aber Abstand ist geheim | Kein Distanzgain aus geheimem Abstand, keine distanzabhängige hörbare Spur |
| Spieler C kennt weder Wagen noch Cue | Kein Audio, Pegelupdate, Existenz-, Count-, Zeit- oder Abohinweis |
| Quelle ist hinter Fog und der Abstand ist geheim | Weder rohe Meter noch akustisch entfernungsabhängige Foglecks |
| SL erlaubt grobe Ferne/Nähe, verbietet exakte Meter | Nur genehmigte grobe Präsentationsklasse, keine genaue Distanzableitung |
| Cue-Anfang war erlaubt, Bewegung wird später geheim | Kein weiterer Distanz-/Pegelverlauf aus der neuen versteckten Position |
| Audio bleibt erlaubt, Distanzrecht wird entzogen | Neutraler zulässiger Audiomodus oder Distanzfunktion aus, kein LastDistance-Shadowcache |
| Audio-/Asset-/Lizenzrecht wird entzogen, Distanzrecht bleibt | Kein weiterer unzulässiger Audio-/Gain-/Medienabruf |
| Spieler erhält Rechte erst nach spätem Eintritt | Keine frühere Positions-/Distanzhistorie und kein Audio-AutoJoin nach 02.133 A |
| Spieler reconnectet bei fahrendem Wagen | Keine alten Pegelupdates, Cue-/Player-Neustart oder gemeinsame Zeit |
| Spieler wechselt Kampagne | Keine fremden Distanz-/Audio-/Welt-/Empfänger-/Playerdaten |
| Spieler errät NPC-ID und fragt Distanzquelle ab | Kein Rohkoordinaten-/Name-/Entfernung-/Count-/Fehlertextleck |
| Client sendet manipulierte `distanceMeters`-/Actor-ID | Keine Datenfreigabe/realer Worldstate-Change oder globaler Audiopegel |
| Szene rotiert/Kamera wird bewegt | Nur wirklich erlaubter räumlicher/Distanzbezug, keine zusätzliche Entity-Aufklärung |
| Hörerposition ist geheim vor dieser Gruppe | Kein fremder Standort oder Precise-Höreranker im Spatial-Stream |
| Dämpfung bei großer erlaubter Distanz | Faktor höchstens 1, eigener Track wird nur leiser, kein Zwangsmute anderer |
| Quelle kommt wieder näher und Abstand ist weiterhin erlaubt | Maximal bis zum rechtmäßigen aktuellen eigenen Basispegel, nicht darüber |
| Mastermute während Positionsänderung aktiv | Bleibt absolut stumm, kein Auto-Unmute durch Near-/Far-Wechsel |
| Spieler ändert eigene Masterlautstärke während Dämpfung | Aktuelle eigene Einstellung gilt; kein Rückschreiben alten Basispegels |
| Browser verweigert Audio-Autoplay | Distanzregel erzwingt keine Wiedergabe und umgeht Browserregeln nicht |
| 02.141-C-Normalisierung aktiv | Korrigiert sichere Quelllautheit getrennt; Entfernung bleibt nur reduzierender Faktor |
| 02.138-C-Ducking während Glockencue aktiv | Temporäre Musicabsenkung und Entfernungsabsenkung getrennt, keine Doppelverstärkung |
| 02.134-C-Crossfade zweier räumlicher Cues | Je eigener erlaubter Quelle bounded DistanceGain, keine fremden Layer-/Weltrechte |
| 02.143 Follow Aus, Quelle bewegt sich | Keine dynamischen Distanzupdates nur durch 02.144; Snapshot bleibt nach 02.142-Recht |
| 02.143 Follow An, aber Cue bereits beendet | Keine Distanz-Gain-Events und kein neuer Cue auf Bewegung |
| Unterbrechung/SceneSwitch bei ausstehendem Update | Revision-/Actor-/Fog-/Scene-ACL gewinnt, veraltete Distanz verworfen |
| Client erhält Updates out-of-order | Kein Rückfall auf alte/geheime Distance-Caches oder duplizierte Gainjobs |
| Viele erlaubte Audio-Cues folgen gleichzeitig | Fanout-/Rate-/CPU-/Quota-/Limitergrenzen statt unendlicher Berechnung |
| 02.135-/02.136-C-Audio-Vorlagen verwendet | Keine Übertragung privater Positions-/Distanz-/Track-/Lizenzrechte durch Vorlage |
| 02.137 A feste Vorlagen werden eingefügt | Kein neuer Distanz-Einfügeparameterwizard oder privater Source-Koordinateneditor |
| 02.139 A keine Audio-Cue-Captions | Keine automatisch eingeblendeten „Wagen wird leiser“-Texte oder Symbole |
| 02.140 A kein Editor-Audio-Previewplayer | Distanzfunktion führt keinen verborgenen Probehörstream ein |
| Soundboard-Cue heißt `Alarm` | Kein echter Schallsensor-/Alarm-/Node-/NPC-/Door-/Quest-/Würfel-/Turn-Effekt |
| Echte 02.51-Schallausbreitung durch Wände | Wird ausschließlich durch eigenes Game-`SoundEvent`-/Hörbarkeitsmodell geregelt, nicht DistanceGain |
| NPC bewegt sich ohne berechtigten Soundboard-Cue | Kein neuer Musik-, Alarm-, Sensor- oder Nodeausgang durch Entfernung |
| 02.99-Weltaktion versucht durch Distanz-Cue | Kein echter Quest-/NPC-/Door-/Turn-/Inventar-/Würfelcommit |
| Amtlicher Hinweis benötigt 02.102-ACK | Lauter/leiser/hören/stoppen erzeugt keine Quittierung |
| Voicechat läuft und Spieler mutet Musik | Kein Eingriff in externe Voice-/OS-/Systemlautstärke, keine Aufnahme |
| 02.105 Chat Aus, Musik/Spatial/Distance An | Zulässige Distanzdämpfung lokal ohne integrierten Chat |
| Stereo-/3D-Hardware fehlt, Mono-Fallback aktiv | Nur rechtmäßig erlaubtes neutrales Audio, keine geheime Distanzoffenlegung |
| Entfernungskurve enthält ungültige Zahlen oder extreme Werte | Sichere Bounds/Fallback, kein Clipping, exponentielles Verstärken oder CPU-Abuse |
| Medien-/Lizenzrechte werden nach Browsercache widerrufen | Kein neuer Audio-/Distanz-Medienzugriff trotz alter signierter Quelle |
| Räumlicher Gain wird per DeepLink oder Suche abgefragt | Keine unberechtigte Weltposition, Höreranker oder Distanzhistorie |
| Hörer hat persönliche Lautstärke auf sehr geringem Wert | DistanceGain kann nur zusätzlich absenken, persönlicher Pegel bleibt maßgeblich |
| Spieler erhält lokalen Cue erst später als SL | Beginn weiterhin individuell bei 0, kein globaler Musik- oder Distanz-Timer |

## 7. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.144 C – eine eigenständige optionale, sichere und nur lokal wirksame Entfernungs-/Pegelabsenkung für bereits wirklich erlaubte räumliche Audio-Cues.** 02.132 Music An, 02.142 Spatial An und separat aktivierte 02.25-Distancefähigkeit sowie **heutige echte Audio-, Asset-, Lizenz-, Empfänger-, Fog-, Szenen-, Positions- und Distanzfreigabe** sind zwingend. Fortlaufende Entfernungsänderungen nur bei zusätzlich tatsächlich aktivem und je Update neu autorisiertem **02.143 C Follow**. Das hörbar leiser/lautere Muster darf keine Secretentfernung verraten; Distanzdämpfung **verstärkt nie über den persönlichen Basispegel** und beeinflusst nie das echte 02.49–02.51-Schall-/Sensor-/Node-Modell. 02.133 A keine gemeinsame Playback-Uhr, 02.134 C lokale Layer-/Fades-/Loops, 02.138 C nur temporäres Ducking, 02.141 C gesicherte Lautheitsnormalisierung und 02.135-/02.136 C Audio-Vorlagen/Updates bleiben; 02.137 A keine Audio-Insertparameter, 02.139 A keine Cue-Captions, 02.140 A kein Editorpreview bleiben negativ. Keine 02.99-Worldeffects und keine 02.102-ACKs durch reine lokale Dämpfung.

**Nicht beschlossen:** exakte Meter-/Grid-/Entfernungskurve, min/max-Distanz, Radius/Reichweiten, Interpolation, Pegelgrenzen, Headtracking, Doppler-/Wandfilter, Audiobibliothek, APIs/DB/UI/MVP. Nur Fachplanung, kein implementierter Code.

## Nächste Entscheidung 02.145 – Doppler-Effekt für berechtigte bewegte räumliche Soundeffekte

**Beispiel:** Ein bereits erlaubter Fahrzeug-Sound fährt am Spieler vorbei. Ein optionaler lokal berechneter, sicher begrenzter Doppler-Effekt könnte den Ton beim Näherkommen und Entfernen etwas verändern. Die dafür benötigte Bewegungsgeschwindigkeit oder -richtung kann selbst geheim sein.

- **A – Kein spezieller Doppler-Effekt:** Tonhöhe/Frequenz von Musik-/Soundboard-Cues bleibt wie in der freigegebenen Originaldatei, auch bei 02.142–02.144-Raumdarstellung.
- **B – Alle Weltbewegungen zwangsbeschallen:** Sämtliche NPC-/Fahrzeug-/Geheimquellbewegungen erzeugen ungefilterte Doppler-/3D-/Soundinformationen für alle und wirken auf echte Schall-/Sensor-/Alarm-/Node-/Questzustände.
- **C – Optionale sichere nur lokale Doppler-Präsentation (Empfehlung):** Bei aktivem 02.132-Musikmodul und zulässigen 02.142-/02.143-Spatialbewegungs-Cues kann die SL nach 02.25-Policy nur ausdrücklich passende **heute tatsächlich audio-, bewegungs- und geschwindigkeitsberechtigte** Quellen lokal mit begrenzter Doppler-/Pitch-Veränderung präsentieren. Geheime Geschwindigkeiten, NPCs, Richtungen oder Cue-Existenz bleiben auch akustisch verborgen. Eigene Mutes, Browser, 02.133-A-NoSync, 02.138-Ducking, 02.141-Loudness und 02.144-Distance-Attenuation bleiben; kein neuer Game-`SoundEvent`-/Node-/World-/ACK-Effekt. Formeln, Limits, Geräte-/Codec-Unterstützung später.
