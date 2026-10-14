# AdventureShift – Karten-Workshop: Beschluss 02.147 C – geschützte konfigurierbare Szenen-Audioeffektprofile

**Stand:** 14.10.2026. Fachlich beschlossen 02.1–02.147; nächste offene Featurefrage **02.148**.
**Status:** Fachplanung mit konzeptionellem Implementierungs- und Abnahmetestplan, **keine Softwareimplementierung**. Exaktes UI, Datenbank-/API-Schema, DSP, Presetbibliothek, Laufzeitgrenzen und MVP-Priorität sind nicht entschieden.
**Bezüge:** [02.25 – globale Kampagnenstandards und Ausnahmen](KARTEN-WORKSHOP.md) · [02.49–02.51 – echte Schall-/Sensor-/Nodewelt](KARTEN-WORKSHOP.md) · [02.99 – autorisierte echte Spielweltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.102 – amtliche Kenntnisnahmequittungen](KARTEN-WORKSHOP-02.102.md) · [02.105 – optionaler Chat](KARTEN-WORKSHOP-02.105.md) · [02.132 C – Musik/Playlists/Soundboard](KARTEN-WORKSHOP-02.132.md) · [02.133 A – nur lokale Wiedergabe ohne gemeinsamen Playhead](KARTEN-WORKSHOP-02.133.md) · [02.134 C – lokale Layers/Fades/Loops](KARTEN-WORKSHOP-02.134.md) · [02.135–02.136 C – Vorlagen und kontrollierte Updates](KARTEN-WORKSHOP-02.136.md) · [02.137 A – keine Audio-Insertparameter](KARTEN-WORKSHOP-02.137.md) · [02.138 C – lokales Ducking](KARTEN-WORKSHOP-02.138.md) · [02.139 A – keine Cue-Captions](KARTEN-WORKSHOP-02.139.md) · [02.140 A – kein Sonder-Editor-Previewplayer](KARTEN-WORKSHOP-02.140.md) · [02.141 C – Loudness](KARTEN-WORKSHOP-02.141.md) · [02.142–02.145 C – Spatial/Follow/Distanz/Doppler](KARTEN-WORKSHOP-02.145.md) · [02.146 C – rein lokaler Hall/Echo](KARTEN-WORKSHOP-02.146.md) · [VPS und rechtssicheres Sitzungsvorladen](SITZUNGS-VORLADEN-CACHE.md).

## 1. Verbindliche Entscheidung – Variante 02.147 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Bei tatsächlich aktiviertem **02.132-C-Musik-/Ambient-/Soundboardmodul**, wirksam aktivierter und separat freigegebener **02.146-C-Hall-/Echo-Fähigkeit** und nach **02.25-Kampagnen-/Rollen-/Gruppen-/Szenen-/Personenstandards mit gültigen markierten Ausnahmen** darf die Spielleitung abstrakte, für den jeweiligen Hörer **wirklich berechtigte Hall-/Echo-Presets** geeigneten, tatsächlich sicht-/hörberechtigten Szenen zuordnen. **Manuelle Profilwahl** und **ausdrücklich erlaubte automatische lokale Effektprofiländerung bei autorisiertem Szenenwechsel** sind **getrennt** einstellbar. Die Zuordnung erteilt weder zusätzliches Szenenwissen noch Audioasset-/Cue-/Lizenzrechte.

**Beispiel:** Eine bereits bekannte Höhlenszene bekommt ein für diese Gruppe freigegebenes abstraktes Preset „Höhle“. Die SL kann es manuell wählen oder bei einem autorisierten Szenenwechsel erlauben, dass der einzelne Browser für einen ohnehin berechtigten und tatsächlich laufenden Ambient-Cue den lokalen Hall entsprechend umstellt. Ein noch geheimer Tempel mit anderer Akustik darf dadurch weder angekündigt noch in einem Asset-/Profilmanifest verraten werden. Hall löst keinen Gegner-, Tür-, Licht-, Schall- oder Node-Effekt aus.

**Nicht gewählt:** A (überhaupt keine szenengebundenen Audioeffektprofile) und B (alle – auch verborgenen – Räume, Wände, Fog und NPCs werden automatisch in erzwungene globale Raumakustik und echte Sensor-/Node-/Weltaktionen umgerechnet). **C ist ausschließlich ein geschütztes Audiopräsentationsfeature**, keine Berechnung echter Spielweltakustik, keine globale Musiksynchronisation und kein automatischer Freibrief zur Geheimnisweitergabe.

## 2. Konfiguration, Rechte und Grenzen

1. **Effektive Abhängigkeiten:** 02.132 Musik An, 02.146 Hall/Echo An und eigenständige 02.147-Szenenprofilzuordnung An sind nötig. Eine weitere effektive Einstellung entscheidet über die SceneSwitch-Automation. Bei Aus bleibt die unabhängig erlaubte normale lokale Audiofunktion, nicht etwa ein heimlich wieder eingeschaltetes Szenenprofil. Ein endgültiger allgemeiner Kampagneneinrichtungsassistent wird erst nach allen Featurebereichen konzipiert.
2. **SL-Bearbeitung:** Berechtigte SL können einer zulässigen Szene ein bereits erlaubtes abstraktes Effektpreset zuweisen, ändern oder entfernen. Die Zuweisung selbst gewährt **keine** vorher unzugänglichen Presets, Audioquellen, Medienlizenzen, Raumpläne oder neuen Rechte für Spieler. 02.135-/02.136-Vorlagenrechte und bewusste Updates bleiben wirksam.
3. **Manuelle Steuerung:** Wer laut aktueller Kampagnenpolicy berechtigt ist, darf eine erlaubte Profilkonfiguration bewusst auswählen. Dass ein Bild/Stockwerk im Editor geöffnet ist, ist keine automatische Audioanweisung an Spieler.
4. **Automatische Aktivierung:** Nur ein **echter vom Server autorisierter und dem jeweiligen Empfänger gültig bekannt gegebener SceneSwitch** darf, wenn dies gesondert erlaubt ist, die lokale Effektkonfiguration aktualisieren. Keine implizite Audioautomation allein aus geheimem SL-Editor-Fokus, Kameraschwenk, Tokenbewegung, Sensor, Node, Alarm oder erratener Szenen-ID. Konkrete Triggerparameter/UI später.
5. **Szenen-/Empfängerscope:** SL, Gruppen, einzelne Spieler und Figuren können verschiedene aktuell berechtigte Szenen haben. Der Server liefert **pro Empfänger** ausschließlich dessen aktuell erlaubte Profilprojektion und niemals eine globale Liste versteckter Szene-Profil-Bindungen. Für eine hörbare Raumatmosphäre kann eine **eigene Präsentationsberechtigung** erforderlich sein, auch wenn eine Karte grundsätzlich bekannt ist.
6. **Laufende Rechtekontrolle:** Bei Zuordnung, Speicherung, Anzeige, Presetsuche, SceneSwitch, Eventversand, Medien-URL, Stream, Browsercache, Vorladung und tatsächlicher Effektanwendung gelten die aktuellen Kampagnen-, Rollen-, Gruppen-, Personen-, Szenen-, Fog-/Secret-, Actor-/Source-Cue-, Preset-, Asset-, Lizenz- und Empfängerrechte. Die Erlaubnis zur Szene ersetzt keine Erlaubnis zum Audiocue; die Erlaubnis zum Hallpreset ersetzt keine Erlaubnis zur Szene.
7. **Keine verdeckten Informationen:** Geheim bleiben nicht freigegebene Raum- und Szenennamen/IDs, Fog, Wände, NPC-Positionen, Raumgrößen, echte Hörweiten, private Presetnamen, Preset-/Asset-/Binding-Anzahl, Hall-/Echotiming, künftige Trigger und geschützte Medien-URLs. Auch **ein bestimmter hörbarer Hallcharakter** kann ein Geheimnis offenbaren; in diesem Fall darf das eigentlich geheime Profil nicht aus ungefilterter Geometrie oder Spielzustandsmetadaten abgeleitet werden.
8. **Kein autonomer Cue- oder Trackstart:** Eine Szene-Profil-Zuordnung bzw. -Änderung verändert **nur die zulässig angewendete lokale Effektkonfiguration**. Sie erzeugt keinen eigenständigen Musik-/Soundboard-Cue, kein automatisches Trackstarten, keinen neuen Loop, keine zweite fachliche Echonachricht und kein globales Wiedergabekommando. Spielleiterseitige echte Audiocue-Steuerung braucht weiterhin eigene 02.132-Rechte.
9. **02.133 A bindend:** Es gibt keine gemeinsame Playhead-/Seek-/Pause-/Startzeit, keinen Join-/Reconnect-Catch-up, keine automatische Audio-Transportwiederherstellung und keine erzwungene Wiedergabe. Zwei Hörer können das gleiche erlaubte Profil bekommen und unterschiedliche lokale Trackpositionen haben.
10. **Hörer-Vorrang:** Persönlicher Master-/Layer-Mute und Lautstärke, Browser-Autoplay und User-Bedienentscheidung wirken vor allen Profil-, Hall- und Echoeffekten. Niemand darf fremde Lautstärke, Systemaudio, Mikrofon oder externen Voicechat verändern.
11. **Andere Audiofeatures getrennt:** 02.134 C lokale Layers/Fades/Loops, 02.138 C lokales Ducking, 02.141 C sichere Loudness bleiben unabhängig. 02.142–02.145 C Spatial/Follow/Distanz/Doppler sind für ein abstraktes Reverb **nicht nötig**; wenn zusätzlich verwendet, brauchen sie weiterhin je eigene Sicht-/Positions-/Velocity-/Recipientrechte. 02.137 A verbietet zusätzliche Audio-Insertparameter, 02.139 A besondere Cue-Captions, 02.140 A den privaten Editor-Vorhörplayer.
12. **Änderung und Widerruf:** Rollen-, Gruppen-, Szenen-, Empfänger-, Source-/Cue-, Preset-, Asset-, Lizenz- und Capabilityrevisionen werden bei jedem neuen Vorgang erneut geprüft; alte/doppelte/verspätete SceneSwitch-Anweisungen dürfen keine veraltete Effektlage aktivieren. Kontrollierbare nicht mehr erlaubte Audioeffekte und Tails stoppen; bereits gehörte Klänge bzw. heruntergeladene Klartextbytes sind nicht garantiert rückwirkend löschbar.
13. **VPS-/Browser-Vorladen:** VPS hält die aktuelle Autorität. Jeder Browser darf nur **jetzt zulässige**, tatsächlich benötigte Medien und Presets berechtigungsgeprüft und ressourcenschonend vorladen. Ein versteckter späterer Kartenabschnitt, Geheimprofil oder geplanter SL-Szenenablauf wird **nicht** im Cache-Manifest oder über Größen/Counts verraten. Cache berechtigt nie zu späteren unautorisierten Abrufen oder einem Offline-Welt-Commit.
14. **NoWorld/NoSensor/NoACK:** Hall, Echo, Profilzuweisung und Profiländerung sind **keine** echten 02.49–02.51-Schall-/NPC-Hören-/Präsenz-/Bewegungsmelder-/Alarm-/Node-/Licht-Ereignisse, keine 02.99-Welt-/Quest-/NPC-/Door-/Turn-/Würfel-/Inventaraktionen und keine 02.102-ACKs. Ein echter autorisierter SceneSwitch darf als Spielzustandsänderung existieren; dessen zusätzliche lokale akustische Darstellung löst keine weitere Weltaktion aus.
15. **Konflikte bleiben offen:** Wie konkurrierende **berechtigte** Presets aus Szene, Gruppe, manueller Wahl und markierten persönlichen Ausnahmen eindeutig priorisiert oder abgelöst werden, wurde **noch nicht** beschlossen. Die nächste Frage **02.148** entscheidet über diesen Konflikt. Unbegrenztes Mischen oder eine konkrete Prioritätsfolge sind keine impliziten Bestandteile von 02.147.

## 3. Konzeptionelles Architektur- und Lebenszyklusmodell

**Nur vorläufige Arbeitsbegriffe, keine finalen Tabellen/Endpunkte:** SceneAudioEffectProfileBinding, EffectiveSceneProfilePolicy, AuthorizedSceneProfileProjection, SceneProfileRevision, LocalSceneProfileTransition, AuthorizedAudioPreset, LocalReverbEchoRenderer.

1. **SL-Konfiguration:** Unter 02.25-Policy erlaubte Szenenbindung an eine abstrakte aktuell zugängliche Presetreferenz mit gültigem Medien-/Lizenz-/Cue- und Scene-Scope; geänderte globale Defaults respektieren die bereits beschlossenen markierten Ausnahmen und Vorschauanforderungen.
2. **Server-Resolver:** Ermittelt aktuelle effektive Camp-/Scene-/Fog-/Group-/Person-/Actor-/Cue-/Media-/License-/Presetrechte und prüft, ob der **hörbare Klang** ein geschütztes Raumgeheimnis offenbart. Nur minimale, per Hörer berechtigte Projektionsdaten werden übertragen, keine geheime Raumgeometrie oder Playlist-/Szenengesamtliste.
3. **Manuelle bzw. autorisierte SceneSwitch-Änderung:** Nur gültige Aktion mit eigener Fähigkeit, erlaubter Szene und monoton geprüfter Revision löst die passende lokale Profilanweisung aus. Zustellung muss gegen Duplikat/Replay/stale Reihenfolge geschützt werden, ohne globale Uhr für Musik.
4. **Browserseitiger Mixer:** Für bereits wirklich erlaubte und ggf. tatsächlich laufende Cues dürfen die jeweils gültigen 02.146-Hall-/Echoeffekte unter begrenzten DSP-/Feedback-/CPU-/Speicher-/Limiter-/Tail-Budgets angewandt werden. Kein neuer Track, kein Rekursions-Echo, kein Mute-Bypass.
5. **Widerruf und Fallback:** Bei effektivem Rechteverlust Preset/Cue/Asset/Scene/Profile-Aus laufende kontrollierbare Tails beenden und Medien-/Cachezugriffe entwerten. Falls Audio-DSP oder Codec nicht unterstützt wird, nur rechtmäßige trockene Wiedergabe oder kontrollierter Abbruch; **kein geheimes Ersatzprofil**.
6. **Multi-Client:** Unterschiedliche aktive Szenen und getrennte lokale Wiedergabe pro Hörer unterstützen; Late Join/Reconnect/Browserneustart prüft neue gegenwärtige Rechte, startet aber nicht ältere Cues. Keine Erfindung einer lokalen Welt-/Würfel-/Node-Autorität bei VPS-Ausfall.
7. **Nicht im Scope:** Ungeprüfte Audio-Scene-/Fog-Geometrieerkennung, geheimer Szenen-Asset-Fingerprint, globale Musiktransportsteuerung, automatische fremde Voiceeffekte, allgemeines weltwirksames SoundEvent und beliebiger Clientscriptcode.

## 4. Geplanter Umsetzungsweg (noch keine Implementierung)

1. **Capability- und Rechtevertrag:** Effektiv schaltbare 02.147-Szenenprofilbindung, getrennte SceneSwitch-Auto-Unterfähigkeit und Berechtigungen für SL-Verwaltung, manuelle Wahl, Szenen-/Preset- und Audioempfang nach 02.25 spezifizieren. 02.132/02.146 On-Pflicht ausdrücken.
2. **Szenenbindung/Versionierung:** Abstrakte erlaubte Presetreferenzen und Scope-Ausnahmen an zulässige Szenen binden. 02.135–02.136 Vorlagen und Updates ohne automatische Rechteausweitung integrieren; kein Geheimraum-/Geometrie-Dump.
3. **Geschützte Viewerprojektion:** Vor Listen-, Editor-, SceneSwitch-, Realtime- und Media-/Cachezugriff pro Zuschauer wirksamen Resolver entwerfen, der nur wirklich erlaubte Szenen/Presets/Cue-/Assetdaten projiziert. Geschützte Manifest-/URL-/Count-/Error-Kanäle mitprüfen.
4. **Lokale Aktivierung:** Autorisierte manuelle Änderung bzw. versionierter SceneSwitch aktualisiert nur den begrenzten lokalen 02.146-Effektgraphen bereits berechtigter Cues. Eigener Mute, Browserautoplay, 02.133 A und lokale Audio-Layers haben Vorrang; keine automatische Cue-/Trackreproduktion.
5. **Lifecycle und Tests:** Szenenwechsel, Split-Gruppe, Profil-/Lizenz-/Rollenwiderruf, Tail-Ende, doppelte/alte Events, Reconnect, Late Join, Cache-Eviction, Mobile und VPS-Neustart sowie NoWorld/NoACK/Sensor/Secret-Leak testen.
6. **Spätere Festlegung:** UI-/Einstellungsassistent, Datenmodell, API/Realtime-Verträge, Preset-/Audio-DSP-Bibliotheken, Übergangskurven, Budgets und MVP nach Featureabschluss priorisieren; konkurrierende Profilpriorität gesondert als 02.148 festlegen.

## 5. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Musik 02.132 C Aus | Kein Profil-Audio; andere Spielsysteme unbeeinträchtigt |
| Musik An, Hall 02.146 Aus | Kein Reverbprofil, normale erlaubte Quellen bleiben |
| Szenenprofil An/Aus getrennt vom Hall | Keine heimliche Profilaktivierung bei Szenenprofil Aus |
| Automatischer SceneSwitch Aus | Nur separat erlaubte manuelle Profilwahl |
| Echter berechtigter Szenewechsel, Auto An | Nur lokale berechtigte Profiländerung für passende Hörer |
| SL öffnet privaten Editorraum | Kein Event/Secretprofil an Spieler ohne Szenenrecht |
| Zwei Gruppen haben unterschiedliche Szenen | Je Hörer nur eigenes erlaubtes Profil |
| Szene sichtbar, geheimes Preset nicht hörberechtigt | Keine Preset-/Raumart-/Echo-/Metadatenoffenlegung |
| Preset erlaubt, Cue oder Lizenz fehlt | Kein unberechtigter Ton/Assetabruf |
| Spieler errät Profil-ID | Keine Namen, geheimen Counts, Lizenz-, Timing- oder Error-Leaks |
| Spieler hat Track pausiert | Profiländerung startet ihn nicht selbstständig neu |
| Hörer-Mute oder Autoplayblock | Profil kann beides nicht umgehen |
| Zwei Hörer verwenden gleichen Presetnamen | Kein globaler Playhead, eigene Playerzeiten |
| Spieler verbindet später/erneut | Kein SceneSwitch-Cue-Catch-up oder ungebetener Trackstart |
| Szenenwechsel bei laufendem Nachhall | Alte unzulässige Tails werden kontrolliert gestoppt |
| Role-/Group-/Scene-/Media-/Lizenzwiderruf | Unzulässige neue Auslieferung und kontrollierbare Altjobs gesperrt |
| Zwei Events kommen vertauscht/doppelt | Versions-/Idempotenzprüfung verhindert altes Profil |
| Globaldefault geändert mit markierter Ausnahme | Effektive 02.25-Ausnahme bleibt korrekt |
| Spatial/Distance/Doppler abgeschaltet | Generischer Hall bleibt ohne geheime Bewegungs-/Positionsrechte möglich |
| Geheime Höhle in späterer Spielsitzung geplant | Kein unzulässiger Prefetch/Scene-Preset-Manifest-Hinweis |
| Profilvorlage über Kampagnen hinweg | Keine fremde Medien-/Lizenzfreigabe durch Presetverweis |
| Browser-DSP/Cache fehlt | Sicherer zulässiger trockener Ton bzw. Abbruch |
| Profil heißt „Alarm“ | Kein 02.49–02.51-Schallsensor-/NPC-/Node-/Alarmevent |
| Profil heißt „Tür öffnen“ | Kein 02.99-Tür-/Quest-/Inventar-/Turn-/Würfelcommit |
| Offizielle ACK erforderlich | Hören/Profilwechsel quittiert nichts nach 02.102 |
| 02.137/02.139/02.140 A | Kein Insertparameterwizard, keine Captions, kein Editor-Sonderpreviewplayer |
| Szene- und Personenprofil gleichzeitig gültig | Profilkonflikt bleibt **02.148**, kein ungeprüftes Mischen als beschlossen |

## 6. Beschlussgrenze und nächste Frage

**02.147 C verbindlich:** Berechtigte abstrakte Hall-/Echo-Presets dürfen nach 02.25-Defaults und gültigen markierten Ausnahmen bei aktivierter 02.132-Musik und 02.146-Hall-Fähigkeit passenden **aktuell berechtigten** Szenen/Empfängern zugeordnet werden. Berechtigte **manuelle** und **bei echtem SceneSwitch automatisch lokal ausgeführte** Profilwahl sind getrennt schaltbar. Persönlicher Mute und 02.133 A ohne globale Musikuhr, Szenen-/Preset-/Cue-/Medien-/Lizenz-/Secret-Schutz, separate Welt-Schallphysik/Nodes/ACKs und sicheres browserbasiertes Vorladen bleiben unangetastet.

**Nicht beschlossen:** Priorität konkurrierender Szenenprofile, exakte Fade-/DSP-Übergänge, Presets, Ressourcenquoten, UI, API/DB und MVP. Kein produktiver Code.

## Nächste Entscheidung 02.148 – Was passiert bei mehreren gleichzeitig passenden Szenen-Audioeffektprofilen?

**Beispiel:** Für einen erlaubten, bereits laufenden Ambient-Cue gibt es ein allgemeines Höhlenprofil und zugleich eine von der SL ausdrücklich festgelegte persönliche Ausnahme. Beide sind berechtigt. Welche lokale Effekteinstellung hat Vorrang, ohne Geheimnisse zu verraten oder Hall-Effekte unkontrolliert zu stapeln?

- **A – Rein manuelle Einzelauswahl:** Sobald mehr als ein Szenenprofil passt, ist eine bewusste Auswahl eines einzigen erlaubten Presets durch eine berechtigte SL nötig; keine automatische Prioritätsauflösung.
- **B – Alle Profile gleichzeitig mischen:** Alle globalen, szenischen, gruppen- und personenbezogenen Profile werden unabhängig von Priorität, Ressourcen und Widersprüchen parallel überlagert.
- **C – Konfigurierbare sichere Profilpriorität (Empfehlung):** Nach wirksamen 02.25-Standards und markierten Ausnahmen wird zwischen **nur tatsächlich berechtigten** Profilen eine begrenzte, nachvollziehbare, eindeutige Priorität ermittelt. Wie genau persönliche, Gruppen-, Szenen- und manuelle Einträge rangieren, wird mit diesem Beschluss festgelegt; bei unauflösbarem Konflikt sicherer neutraler Fallback. Kein Secret-Leak, kein unlimitiertes Mischen, kein Mute-/02.133-A-/World-/Sensor-/ACK-Bypass.
