# AdventureShift – Karten-Workshop: Beschluss 02.134 C – konfigurierbare lokale Musiküberblendungen, Wiederholung und Soundboard-Mischung

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.134; nächste offene Frage 02.135
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungs-/Abnahmetestplan; **keine Softwareimplementierung**, kein endgültiges UI, keine finalen Audio-Engines, Datenbank-/API-Verträge oder MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnenstandards und gültige Ausnahmen](KARTEN-WORKSHOP.md) · [02.49–02.51 – echte Akustik-/Sensor-/Schallweltereignisse](KARTEN-WORKSHOP.md) · [02.99 – sichere reale Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – amtliche Hinweise/ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.110 – Kanal-Mute/DM-Senderblock](KARTEN-WORKSHOP-02.110.md) · [02.114 – geschützte Chatanhänge](KARTEN-WORKSHOP-02.114.md) · [02.116 A – keine individuellen Lese-/Zustellbestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.122 A – keine Chat-Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.126 – Chatbenachrichtigungen](KARTEN-WORKSHOP-02.126.md) · [02.132 C – eigenständige optionale Sessionmusik/Playlists/Soundboard](KARTEN-WORKSHOP-02.132.md) · [02.133 A – kein globaler Playhead/Sync/Join-Catch-up](KARTEN-WORKSHOP-02.133.md) · [Lizenzen und Assets](LIZENZEN.md).

## 1. Verbindliche Entscheidung – Variante 02.134 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Das nach **02.132 C eigenständig bei Kampagnenerstellung An/Aus schaltbare Musik-/Playlist-/Soundboardmodul** darf nach gültigen **02.25-Kampagnen-/Rollen-/Gruppen-/Szenen-/Personen-Defaults und markierten Ausnahmen** geeignete, je nach Implementierungsstand konfigurierbare **lokale Playlist-Wiederholungen, Fade-in/Fade-out, Überblendungen/Crossfades sowie gleichzeitig hörbare Musik-, Atmosphäre- und Soundboard-Cue-Layer** unterstützen. Alle Misch-/Timingvorgänge werden **im jeweiligen rechtmäßig berechtigten Hörergerät** ausgeführt. Persönliche Lautstärke/Mute, tatsächliche Asset-/Szenen-/Empfängerrechte und Browser-/OS-Audioeinschränkungen sind zwingend.

**Beispiel:** Ein Spieler hört eine zugelassene Tavernentrack-Wiederholung in seinem Browser. Er startet nach eigener Zustimmung einen Kampftrack: Die Audio-Engine kann seine lokale Taverne aus- und Kampfmusik einblenden, während ein berechtigter Glockenton in einem eigenen lokalen Soundboard-Layer erklingt. Eine andere Spielerin hört möglicherweise einen ganz anderen Zeitpunkt, pausiert oder hat das gesamte Modul stummgeschaltet. **Niemand wird zum Zeit- oder Lautstärkestand des anderen synchronisiert.**

**Nicht gewählt:** A (nur ein Klang gleichzeitig, ohne diese optionalen Mischfunktionen) oder B (unbegrenzter unberechtigter Mehrfachstart und erzwungene Lautstärke für fremde Hörer). **C hebt ausdrücklich nicht 02.133 A auf:** kein globaler Abspielposition-/Transport-/Pause-/Seek-Sync, kein automatisches Starten beim Join/Reconnect und keine 02.25-Ausnahme zur Wiederaktivierung einer abgelehnten gemeinsamen Musikuhr.

## 2. Konfigurierbare lokale Audiofunktionen

1. **Voraussetzung:** 02.132-Musik **An** und jeweils wirksam erlaubte 02.25-Unterfähigkeit für lokale Wiedergabe/Mixing. Bei Musik **Aus** kein neuer Misch-/Cue-/Audio-Pfad. 02.105-Chat An/Aus, 02.49–02.51-Akustik An/Aus und 02.132-Musik bleiben **unabhängig**.
2. **Loop-/Playlist-Replay:** Sofern eigens erlaubt, kann der **lokale Player** ein für ihn freigegebenes Trackasset nach regulärem Ende wieder bei **0** beginnen oder eine zugelassene Playlist lokal fortsetzen. Keine globale Wiederholungsuhr, kein Server-Offset, keine automatische historische Cue-Nachholung. Playlist-Advance/Repeat ist kein erzwungenes Live-Join-Playback.
3. **Fade-in/Fade-out/Crossfade:** Nur technisch unterstützte, individuell konfigurierbare lokale Pegelkurven für zulässige Audioquellen. Beim lokalen Start eines **neuen** Tracks beginnt dessen Quelle bei **Titelanfang (02.133 A)**; eine parallele Übergangsdauer und zwei hörbare Quellen beim Crossfade ergeben **keine** gemeinsame synchronisierte Position. Dauer, Kurven, Grenzen und Defaultpresets erst später bestimmen.
4. **Musik-/Ambient-/Soundboard-Layer:** Eigene *lokale* Kategorien für zulässig gleichzeitig laufende Tracks/Cues vorsehen, jeweils mit getrennter Quellfreigabe. Auch ein Soundeffekt darf über Musik gelegt werden, soweit Policy, Browser und Ressourcen es ermöglichen. Keine automatische 02.49–02.51-Welt-Schall-/Sensor-/Alarm-/Node-Simulation aus der Audiowiedergabe.
5. **Hörerautonomie und sichere Pegel:** Jede Person behält eigenen Master-Lautstärke-/Mutezustand nach 02.132 C und den Start-/Pause-/Stopzustand nach 02.133 A. Ein optionaler eigener Layer-/Musik-/Effektpegel darf diese **nur für sich selbst** weiter verringern/anpassen. Zulässige maximale Anzahl gleichzeitiger Layer, Quoten, Pegelbegrenzer/Clipping-/Hörschutz und Ressourcengrenzen im Technikdesign definieren; keine unbegrenzte Überlagerung oder unkontrolliertes gegenseitiges Beschallen.
6. **Manuell, Approval oder Auto-Cue:** 02.132-C-Actor-/Rollen-/Gruppen-/Szenenrechte für Auswahl, Vorschlag, gültige SL-Freigabe oder ausdrücklich erlaubte automatische Cue-Auswahl bleiben. Eine gemeinsame Playlist- oder Cue-Auswahl kann zulässig adressiert werden, aber **die Audioausführung und Übergangskurve sind gerätelokal**, nur bei tatsächlicher Hörer-/Browserfreigabe und niemals als verordneter globaler Playbackstand. Normale Cue-Empfängerrechte gelten vor jedem Start.
7. **Lokale Kollisionen/Races:** Wenn Trackwechsel, neuer Cue, Fadeende, Mute, Szene-/Rechtewechsel oder lokaler Stop gleichzeitig eintreffen, muss der Client veraltete lokale Quelljobs abbrechen/revidieren statt alte verborgene Audioquellen erneut zu starten. Sicherheits-/Policygrenzen vom Server sind vorrangig, lokale Audioautomation nur Komfort.
8. **Keine Aufnahme und kein Fremdplayerzugriff:** Mixing ist reine Audioausgabe, keine Mikrofonaufnahme, keine Voicechat-Integration, kein 02.122-A-Chat-Voice-Memo, keine automatische Speicherung gemischter Audiodateien oder Extraktion fremder Audio-/Systemlautstärken. Keine SL-Fernbedienung fremder Browserlautstärke.
9. **Settings-Grenze:** 02.25-C-Defaults und gültige Ausnahmen schalten nur fachlich unterstützte **lokale** Fades/Loops/Layers ein; **kein** globaler Playhead, gemeinsame Positionsverfolgung, Join-/Reconnect-Backfill, ungefilterte Massen-Cues oder sicherheitskritisch abschaltbare Lizenz-/ACL-/Browserkontrolle.

## 3. Geschützte Quellen und strikte Systemtrennung

| Bestehende Grenze | Bedeutung für 02.134 C |
| --- | --- |
| **02.132 C Musikmodul An/Aus und Asset-/Cue-/Steuerrechte** | Nur erlaubte Playlists, Track-/Cuequellen, Schauspieler, Gruppen/Szenen, Empfänger und Lizenzrechte dürfen lokale Mixaufgaben erzeugen |
| **02.133 A rein lokale Wiedergabe** | Kein per-Server `sharedPlayhead`, `musicServerStartAt`, `globalSeek`, `syncCrossfade` oder globaler Fade-/Loop-Zeitanker, selbst bei automatischen Cueangeboten |
| **02.25 markierte Ausnahmen** | Passende LocalLoop/LocalFade/LocalLayer-Unterfähigkeiten, **nie** Ausnahme zur Sync-/Secret-/Lizenz-/Autoplayumgehung |
| **02.105 Chat und 02.122 A Voice-Memo-Ausschluss** | Musik/Mixing funktioniert bei Chat Aus; kein Chat-Audioaufnahme-/Sprachnachrichten-/Transkriptionspfad |
| **02.49–02.51 Akustik, Hörbarkeit und Nodes** | Soundboard-Glocke, Explosion oder Alarmton **nur hörbare Präsentation**, kein Game-SoundEvent, Schallsensor, Alarm-, Licht-, Door-, NPC-, Quest- oder Node-Trigger |
| **02.99 autorisierte Weltaktionen / 02.101–02.104 amtliche ACKs** | Lokale Audioeffekte ändern weder Würfel, Türen, Timer, Turn, Inventar oder Queststatus noch quittieren sie amtliche Systemmeldungen |
| **02.110/02.126 Chatmutes/Benachrichtigungen** | Persönlicher Audiomute getrennt von Chatmute; Toast-/OS-Ton nicht heimlich Teil von Musikmixing, Pflichtsystemhinweise bleiben |
| **Rechte und geheime Assets** | Verborgene Playlist-/Track-/Scene-/Cue-Metadaten, Medien-URL, Cover, Loopzeiten, Anzahl oder Mixstatus sind für Unberechtigte nicht verfügbar |
| **Browser-/Plattformregeln** | Keine Garantie simultaner Ausgabe, Autoplay gegen Nutzersignal, exakten Crossfades auf jedem Gerät, lizenzwidriger Streams oder verfügbarer Audiohardware |

**Keine World-Kopplung durch Tonnamen:** Ein Dateiname `alarm.mp3`, ein gespielter Schuss oder eine Audioautomation mit Szenenetikett `Tür öffnen` darf **nicht** als direkter Schall-, Sensor-, Node-, Quest- oder NPC-Aktionsinput interpretiert werden. Falls später eine echte Weltaktion **gesondert autorisiert** werden sollte, benötigt sie ihre **eigene 02.99-/02.51-Eventprüfung**; 02.134 C beschließt keinen solchen Trigger.

## 4. Konzeptionelles Lebenszyklus- und Architekturmodell

1. **Vorrang serverseitiger Quellenrechte:** Vor Playlist-/Track-/Soundboard-/Cue-Freigabe und Media-URL-Laden aktuelle Kampagnen-/Szenen-/Actor-/Rollen-/Empfänger-/Audioasset-/Lizenz-/Secret-ACL und 02.132-/02.134-Featurepolicy prüfen. Playback-Mixing darf nicht durch erratene Asset-IDs, alte signierte URLs, Reconnect, Cache oder öffentlich vorhersagbare Layerreferenzen ein Geheimnis enthüllen.
2. **Lokale Mischprojektion:** Konzeptionelle Arbeitsnamen `LocalAudioMixCapability`, `LocalAudioMixPolicy`, `LocalAudioLayer`, `LocalAudioTransition`, `LocalAudioLoopMode`, `LocalAudioGainPreference`, `LocalAudioVoiceBudget`. Solche Clientzustände sind **keine** globale Server-Playhead-/Hörtelemetriedatenbank. Finale Audio-Engine/DB/API/UX erst später.
3. **Lokaler Mixgraph:** Bei erlaubtem Cue eigener Audio-Quellhandler, optional mehrere kategoriale Layer, Gain-/Mutehierarchie (eigener Mastermute vor lokalen Layerpegeln), optional Fade-/Crossfade-/Loopjobs und resource-bounded Mixdown. Nur die aktuell berechtigt zugelassene Quelle darf dabei tatsächlich dekodiert/abgespielt werden; kein verstecktes Hintergrundprefetching fremder Secrets.
4. **Policy-/Assetwechsel:** Rechte-/Lizenz-/Szenen-/Gruppen-/Rollen-/Kampagnenwechsel, Musik Aus, Entfernen eines Tracks oder Widerruf eines Cues müssen neue und noch kontrollierbare lokale Audiojobs sicher blockieren/beenden. Bereits physisch gehörte Töne und exportierte externe Kopien können nicht rückwirkend ungehört gemacht werden.
5. **Timing und Idempotenz:** Lokal zwei überblendete Quellen erlauben, ohne die 02.133-A-Regel `neuer Titel bei 0` zu verletzen. Keine Server-Trackzeit, die alle Clients nachkorrigiert. Deduplizierte berechtigte 02.132-C-Cue-Vorschläge/Approval-/Actor-Operationen sowie lokale Abort-/Replacement-Token verhindern Doppel-Layer, endlose Loops bei Reconnect und Race-/Replay-Missbrauch.
6. **Browser-/Audio-Hardwaregrenzen:** Autoplay-/Usergesture-, Decoder-/Codec-/Hardwarelimit, suspendierte Tabs und schlechte Verbindung müssen als technische Grenzen respektiert werden. Keine Zusage für Samplegenauigkeit, Streamingqualität, permanente Playbackfortsetzung oder Umgehen persönlicher Mutes.
7. **Sicherheit und Ressourcen:** Serverseitige Cue-/Media-/Request-/Quota-/Ratebegrenzungen und clientseitige gleichzeitige Quellen-/Lautheits-/CPU-/Speicherbudgets, Fehlerabfang und Ausstieg aus blockierten Cueketten. Auch erlaubt konfigurierte Mehrfach-Layer sind **nicht** unbegrenzt.
8. **Beobachtbarkeit nur im richtigen Scope:** Diagnose von Fehlern nur in berechtigt zugänglichen Logs, keine Teilnehmerlisten „wer hörte/pausierte/spulte“, keine Vor-/Nachrichten-/Mischstatuscounts von unberechtigten Personen oder versteckten Szenen. Keine persönlichen Chat-Lesebestätigungen durch Audioevents (02.116 A).

## 5. Umsetzungsplan (noch keine Software)

1. **Policy-/Capability-Vertrag:** Im 02.132-C-Modul die Unterfunktionen `loopLocal`, `fadeLocal`, `crossfadeLocal`, `mixLocalLayers` und lokal getrennte Musik-/Soundboard-Busse nach geeigneten 02.25-Defaults/Ausnahmen abbilden; 02.133-A-Sync-Funktionen ausdrücklich **nicht** anbieten.
2. **Echte Audioquellen/Assets:** Lizenz-/Medien-/Secret-/Empfänger-/Scene-/Rollen-/ACL-Resolver und aktuell validierte, zeitlich begrenzte Audioquellen für erlaubte Layer definieren. Keine heimliche Dropbox-/Streaming-/Voiceprovider-Brücke.
3. **Local-Player-Audioadapter:** Bei freigegebenen Quellen und tatsächlicher Browser-/Hörerentscheidung eine bounded Audio-Mixengine mit eigene Master/Layer-Volume/Mute, optionalen Kurven, Wiederholung und mehreren Cues konzipieren. Neue Trackquelle stets bei 0; Cue darf bei späterem Join nicht heimlich nachlaufen.
4. **Fehler-/Revisionswege:** Wiederholte Cue-Aktionen, gleichzeitige lokale Mixupdates, Szenen-/Policy-/Asset-/Rechtewechsel, Tab-Suspend/Resume, Musik Aus und Reconnect müssen alte Jobs stoppen, ohne neue ungefragte Wiedergabe auszulösen. Keine globale Wiedergabeuhr, kein automatischer Catch-up.
5. **Test- und Sicherheitsmatrix:** Fachfälle unten. Soundeffekt-/UI-/Fade-/Loop-/Crossfade-Grenzen, Defaultpresets, Equalizer, Ducking und tatsächliche Codec-/Player-/Streamingtechnik sind nach Featuresammlung separat zu entscheiden; ebenso Priorisierung/MVP.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Musik 02.132 C bei Kampagnenerstellung Aus | Kein LocalMix-Cue, Loop, Fade oder Layerstart; Würfel-/Chat-/02.51-Weltmodule unabhängig |
| Musik An, Chat 02.105 Aus | Berechtigte lokale Mixfunktionen funktionieren ohne integrierten Chat |
| SL erlaubt lokale Loops, verbietet Multi-Layer | Track darf lokal wiederholen, aber nicht unbegrenzt weitere Layer erzeugen |
| Kampagne erlaubt lokale Überblendungen | Zwei autorisierte Titel können **nur auf dem jeweiligen Client** zeitweise gleichzeitig erklingen |
| Spieler A startet Kampftrack beim Crossfade | Neuer Track startet lokal bei Titelanfang, vorhandener Track kann nur bei A ausgeblendet werden |
| Spieler B beginnt denselben Track später | B beginnt bei 0, **kein** Gleichziehen mit As Position oder Befehl an A |
| Spieler A pausiert, B läuft weiter | Keine globale Pause-/Seek-/Driftkorrektur über 02.133 A |
| Spieler wiederholt Track | Neustart am lokalen Titelanfang, keine zentrale Playlist-Wiederholungsuhr |
| Später beigetretener Spieler mit erlaubten Musikrechten | Kein Autoplay/Catch-up, eigene freiwillige Startposition 0 |
| Reconnect während lokaler Überblendung | Kein automatisches Replay/Crossfade-Backfill oder wiederhergestellter globaler Playhead |
| SL aktiviert 02.25-Sync-Ausnahme zusätzlich zu LocalMix | Nicht zulässig: 02.133-A-Verbot bleibt ohne Override |
| Lokale Mixingfunktion für konkrete Gruppe Aus | Kein Start zusätzlicher Mixebene durch heimlichen Clientflag trotz aktivem Musikmodul |
| Gültige SL-Freigabe eines Trackwechsels | Erlaubte neue Cue-Auswahl, **kein** Zwangsseek/Verstellen fremder Player |
| Autorisierte automatische Szenenregel sendet Cue-Angebot | Nur nach Policy/Asset-/Empfängerrechten, lokale Hörer-/Browserentscheidung bleibt |
| Playlist-/Assetreferenz in nicht freigegebener Szene | Kein Tracktitel, URL, Cover, Cue, Bytezugang, Layername oder Preview für Unberechtigte |
| Rollen-/Gruppenrecht entzogen, während Loop läuft | Neue Aufrufe/Wiedergabe kontrollierbar stoppen, keine Secret-Kopie oder Streamverlängerung |
| Assetlizenz-/Medienrecht abgelaufen | Neue Nutzung/Layerstarts verboten und kontrollierbare Wiedergabe beenden |
| Spieler stellt eigenen Master-Mute ein | **Alle** eigenen Layer bleiben stumm; SL kann den Mute nicht überschreiben |
| Spieler reduziert nur eigenen Soundeffektpegel | Musik anderer Teilnehmer und deren Soundboardpegel unverändert |
| Browser blockiert Audio-Autoplay | Keine erzwingbare Wiedergabe; Fade-/Layer-Engine darf Browserblock nicht umgehen |
| SL versucht globale `syncCrossfadeAt`-API | Keine solche fachlich zulässige Synctimeline-/Remote-Seek-Funktion |
| Soundboard spielt Glocke über Hintergrundmusik | Für Berechtigte lokaler Audioeffekt, kein Game-SoundEvent oder akustischer Sensortrigger |
| Soundboard spielt einen Alarmton | Kein echter 02.51-Alarm-/Node-/Door-/NPC-/Quest-/Würfeleffekt |
| Cue-Name lautet `Tür öffnen` | Keine 02.99-Door-/Quest-/Inventar-/Turnaktion |
| Zwei lokale Crossfades werden schnell hintereinander gestartet | Version/Abort/Idempotenz vermeidet verwaiste Endlosschleifen und unzulässige alte Layer |
| Viele gleichzeitige Cues und Loops | Eigene Clip-/Rate-/Memory-/CPU-/Gainlimits wirken, keine unbegrenzte Überlagerung |
| Tab wird pausiert und später fortgesetzt | Kein garantierter samplegenauer Audiofortschritt, kein Server-Backfill oder Zwangsstart |
| Browser unterstützt bestimmten Audiocodec nicht | Sichere lokal erkennbare Fehlersituation, keine Aussage garantierter Formatunterstützung |
| Zwei Geräte desselben Nutzers spielen Titel | Ihre Playheads/Fades/Loops bleiben separat; kein durch Account veranlasster globaler Sync |
| Eine andere Kampagne benutzt dasselbe Musikasset | Kein Cross-Campaign-Zugriff auf geheime Playlist-/Scene-/Mixstatistiken |
| 02.110-Chatkanal-Mute aktiv | Musik-Mute bleibt unabhängig, keine stillen Änderungen an Chatberechtigungen/Benachrichtigungen |
| 02.122 A kein Chat-Voice-Memo | Lokales Mixing eröffnet kein Mikrofon-/Voiceaufnahme-/Transkriptionsmodul |
| Offizieller Hinweis nach 02.102 muss aktiv quittiert werden | Audiohören, Looping, Fade und Mute erzeugen kein ACK |
| Echte 02.49–02.51-Schallsimulation separat aktiv | Ihre Hörbarkeits-/Sensor-/Alarm-/Node-/Weltaktionen nur über eigenen geprüften Originalpfad |
| Nicht berechtigter Client errät Track-/Layer-ID | Kein Medienstream/Audio-Metadaten-/Fehlertext-Existenzleck über Mix-API |
| Szenenwechsel während verzögertem Cue | Veralteter Cue wird nach aktueller ACL-/Policyversion verworfen, kein geheimer Loop |
| Mixfunktion bei laufender Sitzung deaktiviert | Keine neuen Mixjobs; kontrollierbare lokale alte Layer rechtmäßig beenden, persönliche Mastermuteinstellung respektieren |

## 7. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.134 C – getrennt konfigurierbare und wirklich berechtigte lokale Loops, Fades/Crossfades und Musik-/Soundboard-Layer**, verfügbar nur bei aktivem 02.132-C-Musikmodul und gültigen 02.25-Defaults/markierten Ausnahmen, pro Hörergerät nach echten Audioasset-/Lizenz-/Rollen-/Szenen-/Gruppen-/Empfängerrechten und unter persönlicher Volume-/Mute-/Browserautonomie. **02.133 A bleibt absolut:** kein globaler Playhead, keine Positions-/Start-/Pause-/Seek-Synchronisation, kein AutoJoin/AutoReconnect-Catch-up, keine heimliche C-Sync-Ausnahme. Keinerlei direkte Schall-/Sensor-/Alarm-/Node-/NPC-/Quest-/Door-/Würfel-/Turn-/Inventar-/02.99-Weltaktion oder amtliches 02.102-ACK; Chatmodule einschließlich 02.122 A Voice-Memo-Ausschluss bleiben unabhängig.

**Nicht beschlossen:** vollständiger Kampagnen-Konfigurationsassistent, konkrete UI/Playerengine/Codec-/Media-/Streamingprovider, Pegel-/Layer-/Fade-/Loop-Limits, genaue Übergangskurven, konkretes Ducking/Equalizerverhalten, endgültige DB/API/Retentionsstruktur, MVP. Solche Entscheidungen folgen erst nach der Featuresammlung.

## Nächste Entscheidung 02.135 – Audio-Playlist- und Soundboardvorlagen kampagnenübergreifend wiederverwenden

**Beispiel:** Eine Spielleitung hat für mehrere Settings eigene Tavernensounds, Kampfmusik und Soundboard-Kategorien organisiert. Sie möchte passende Playlists als eigene Vorlagen für eine andere Kampagne verwenden, ohne automatisch alle Dateien, Rechte oder geheimen Szenen anderer Kampagnen freizugeben.

- **A – Nur innerhalb derselben Kampagne:** Audio-Playlists und Soundboard-Sammlungen werden nicht als eigene Vorlagen/Referenzen zwischen Kampagnen wiederverwendet; bestehende eigene Audioassetverwaltung bleibt.
- **B – Alle Inhalte global für jeden:** Sämtliche Playlists, Titel, Dateilinks und privaten Szenen-Audiorechte aller Kampagnen werden automatisch für alle Konten verfügbar und bearbeitbar.
- **C – Berechtigte wiederverwendbare Audio-Vorlagen (Empfehlung):** Bei aktivem 02.132-Musikmodul kann die SL nach 02.25 und tatsächlichen Besitzer-/Asset-/Lizenz-/Kampagnenrechten **ausdrücklich freigegebene** Playlist-/Soundboard-Konfigurationen als Vorlagen referenzieren oder zulässig kopieren. Audioassetzugriff, gültige Zielrechte, Geheimnisse, Revisionen und Lizenzen bei jeder Nutzung prüfen; keine automatische Offenlegung fremder Kampagnen oder globale Trackfreigabe. 02.133 A lokale Wiedergabe und 02.134 C lokales Mixing bleiben, allgemeines Assetimport-/Exportdesign folgt getrennt in Bereich 12.
