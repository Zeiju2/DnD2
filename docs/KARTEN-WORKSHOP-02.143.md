# AdventureShift – Karten-Workshop: Beschluss 02.143 C – geschützte lokale Nachführung bewegter räumlicher Audio-Cues

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.143; nächste offene Featurefrage 02.144.
**Status:** Verbindlicher Fachbeschluss mit konzeptioneller Umsetzungsplanung und fachlichen Abnahmetests; **noch keine Softwareimplementierung**, kein finales UI/API-/DB-Schema, keine festgelegte Audio-Engine und keine MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnen-/Rollenstandards und gültige markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.49–02.51 – echte Schall-/Hörbarkeits-/Sensor-/Node-Spielwelt](KARTEN-WORKSHOP.md) · [02.54 – getrennte autorisierte NPC-Bewegung/Steuerung](KARTEN-WORKSHOP.md) · [02.99 – echte serverautorisierte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – offizielle Systemhinweise und ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106–02.107 – Chat-/History-/Empfängersicht](KARTEN-WORKSHOP-02.107.md) · [02.116 A – keine persönlichen Chatlesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.122 A – keine Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.132 C – eigenständiges optionales Musik-/Soundboardmodul](KARTEN-WORKSHOP-02.132.md) · [02.133 A – ausschließlich lokale Audio-Wiedergabe ohne gemeinsames Timing](KARTEN-WORKSHOP-02.133.md) · [02.134 C – nur lokale Loops/Fades/Layers](KARTEN-WORKSHOP-02.134.md) · [02.135–02.136 C – geschützte Audio-Vorlagen/Updates](KARTEN-WORKSHOP-02.136.md) · [02.137 A – keine Audio-Template-Insertparameter](KARTEN-WORKSHOP-02.137.md) · [02.138 C – berechtigtes lokales Ducking](KARTEN-WORKSHOP-02.138.md) · [02.139 A – keine speziellen Visual-Cue-Captions](KARTEN-WORKSHOP-02.139.md) · [02.140 A – kein privater Editor-Audio-Previewplayer](KARTEN-WORKSHOP-02.140.md) · [02.141 C – sichere lokale Lautheitsnormalisierung](KARTEN-WORKSHOP-02.141.md) · [02.142 C – statischer berechtigter lokaler Pan-/Stereo-/ggf. 3D-Cue-Snapshot](KARTEN-WORKSHOP-02.142.md).

## 1. Verbindliche Entscheidung – Variante 02.143 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Ist das **02.132-C-Musikmodul eingeschaltet** und die **02.142-C-räumliche Audio-Unterfähigkeit tatsächlich aktiviert**, darf die SL nach **02.25-Kampagnen-/Rollen-/Gruppen-/Szenen-/Personenstandards mit gültigen markierten Ausnahmen** für **ausdrücklich geeignete, für den konkreten Hörer vollständig freigegebene Cues** eine **optionale, gerätelokale und ressourcenbegrenzte Nachführung der bereits zulässigen räumlichen Präsentationsrichtung** bei Bewegungen erlauben. **Jedes relevante Positions-/Richtungsupdate erhält vor jeder tatsächlichen Zustellung erneut eine vollständige aktuelle Quell-/Cue-/Asset-/Lizenz-/Empfänger-/Szenen-/Fog-/Karten-/Positions-/Richtungsrechteprüfung.** Die **hörbare Bewegung selbst** gilt als sensible Information.

**Beispiel:** Ein für A und B tatsächlich hör- und ortungsberechtigtes Fahrzeug fährt innerhalb ihrer freigegebenen Szene von links nach rechts. Beide lokalen Spatial-Mixer können ihren **jeweils individuell erlaubten** Panwinkel entlang der für sie zulässigen Bewegung aktualisieren. C kennt das Fahrzeug nicht oder darf seine Bewegung nicht wahrnehmen: C sieht/hört weder die verfolgte Richtung noch Takt, Identität, Koordinaten, Positionsdelta, Anzahl von Updates oder ein verstecktes „Objekt bewegt sich“-Signal. Wird die Bewegung für B später geheim, darf Bs bisheriger Cue **keine** fortlaufende räumliche Spur aus den neu verborgenen Daten verraten.

**Nicht gewählt:** A (Cue behält seinen einmalig berechtigten Startwinkel während der gesamten Wiedergabe) und B (unbegrenzte weltweite Positions-/NPC-/Fog-Nachführung für jeden unabhängig von Quellrechten). C erlaubt **kein** heimliches Mithören von Voicechat, keine Rohkoordinatenübertragung, keine globale Musik-Synchronisation, keine zusätzliche echte Spielweltbewegung und keine 02.49–02.51-Schallphysik.

## 2. Aktivierung, Update-Scope und Sichtbarkeitsgrundsatz

1. **Zwei hart wirksame Voraussetzungen:** 02.132 Musik **An** **und** 02.142 Spatial-Unterfähigkeit **An**. 02.143-C-Follow-/Update-Unterfähigkeit ist **drittens** separat nach 02.25 gültigen Defaults/markierten Ausnahmen aktivierbar. Follow Aus = statischer 02.142-C-Snapshot bei weiter rechtmäßigem Cue, keine neuen Positionsupdates.
2. **Welche Quellen folgen dürfen:** Nur ausdrücklich nach gültiger Policy geeignete **bereits autorisierte Audio-Cues/Szenenkontexte** mit dazu zulässiger beweglicher Präsentationsquelle. Eine Bewegung von NPC/Token/Objekt im echten Weltgraphen ist **nicht automatisch** eine neue Audioquelle, hörbare Bewegung, Musikstart oder Spatial-Subscription.
3. **Aktueller Empfänger bei jedem Update:** Der Server prüft (a) gültige Musik-/Original-Cue-/Actor-/Asset-/Lizenz-/Session-/Empfänger-/Rollen-/Gruppen-/Kampagnenrechte **und** (b) aktuelle Karten-/Fog-/Szene-/Quellposition-/Höreranker-/Richtungs-/Geheimnisrechte. Es genügt **nicht**, dass der Cue zu Beginn einmal sichtbar war oder ein Player früher gültig auf die Szene zugreifen konnte.
4. **Nur entschärfte zulässige Präsentationsrichtung:** Ein erneuter Update-Payload enthält nur für den jeweiligen Empfänger erlaubte abstrakte Pan-/Raumrichtung; genaue verborgene Position, NPC-/Tür-/Fallen-ID, Bewegungsvektor, Entfernung, Geschwindigkeit, Zeit-/Objektspuren oder unveröffentlichte Kartenkoordinaten sind **keine** automatisch autorisierten Clientdaten. Schon die **Änderung des gehörten Winkels**, nicht nur ein Datensatzfeld, darf keine verbotenen Geheimnisse verraten.
5. **Rechte verlieren während eines Cues:** Entfällt Cue-, Audioasset-, Medien-/Lizenz- oder Empfängerrecht, enden weitere Audio-/Spatial-Zustellungen und kontrollierbare lokale Jobs. Entfällt ausschließlich Richtungs-/Positionserlaubnis, **darf kein weiteres raumbezogenes Update** erfolgen; nur nach heute erlaubten nicht-spatialen Audiorechten ist neutrale Wiedergabe zulässig, sonst Stop. Kein „letzte geheime Winkel-/Bewegungsprobe einfrieren“ als dauerhafter Secretcache.
6. **Nicht vorherige Sicht ausnutzen:** Neue Gruppenmitglieder/SL, aufgehobene Fogmasken, zurückkehrende Spieler oder geänderte ACL dürfen **nicht** rückwirkend geheime ältere Positions-/Bewegungssegmente, Cursor, Updatehäufigkeit, Tracks oder Quell-ID-Historien bekommen. Nur aktuelle tatsächlich freigegebene Orientierung für noch berechtigte Wiedergabe.
7. **Keine neuen Geräusch-Cues aus Bewegungs-Updates:** 02.143 C folgt **nur** einem bereits gültig laufenden/zugelassenen Cue. Ein Fahrzeug-/NPC-Positionsupdate startet **kein** neues Audioplayback, triggert keinen 02.138-Duckingstart, keinen 02.99-NPC-/Tür-/Quest-/Inventar-/Turncommit und keinen 02.102-ACK. Wurde der eigentliche Cue gestoppt, beendet oder ist er nicht erlaubt, existiert kein gültiges Follow-Abo.
8. **Localität und Browserhoheit:** Die Darstellung wird ausschließlich auf dem Hörergerät mit eigenem Master-/Layer-Mute, Browser-/OS-Audio-Consent, 02.134-C-Mix, 02.138-C-Ducking und 02.141-C-Gain-Normalisierung ausgeführt. Es gibt **keine** globale Audio-Uhr, kein fremdes Hardware-/Voicechat-Lautstärke-Override und keine Audioplayer-Start-/Seek-/Pause-Synchronisierung.
9. **Quotierte Updates:** Räumliche Follow-Updates für laufende berechtigte Cues dürfen Rate-/Fanout-/CPU-/Netz-/Batterie-/Speicher-/Codec- und Abo-Limits nicht überschreiten. Der konkrete Interpolationsmodus, Snapshot-/Updateintervalle, Prioritätsklassen, Fallback bei Paketverlust und Bildschirmbezug werden später technisch festgelegt.
10. **Keine neue Game-Schallautomatik:** Ein Audio-Follow-Stream ist **nicht** die physikalische 02.49–02.51-Hör-/Schall-/Sensor-/Alarm-/Node-Kette; Reichweite, Wände, Sicht und tatsächliche Weltaktionen werden ausschließlich durch ihre eigenen berechtigten Fachsysteme entschieden. 02.143 kopiert keine echten Weltkoordinaten zum Umgehen des Schall-/Fogschutzes.

## 3. Verbindliche Einordnung in bestehende Entscheidungen

| Fachgrenze | Wirkung in 02.143 C |
| --- | --- |
| **02.25 / 02.132 C** | Nach Kampagnencreation schaltbares Musikmodul und separate Follow-Fähigkeit, echte Actor-/Owner-/Asset-/Lizenz-/Szene-/Empfänger-Rechte bleiben; keine sicherheitsabschaltende Ausnahme |
| **02.142 C** | Räumliche Pan-/Stereo-/ggf. 3D-Ausgabe muss erlaubt sein; **jede Bewegung** benötigt neue heutige eigene Richtungs-/Position-/Fog-/Cue-Prüfung statt Start-Snapshot als Dauerfreigabe |
| **02.133 A** | Keine geteilte Musik-/Player-/Start-/Pause-/Seek-/Join-/Reconnectuhr; räumliche Richtungsupdates sind **keine** Audiowiedergabesynchronisation |
| **02.134 C / 02.138 C / 02.141 C** | Lokale Layer/Fades/Loops, separate nur eigene temporäre Musikabsenkung und begrenzte Loudness-Korrektur bleiben unter eigenem Mute/Browser-Consent |
| **02.49–02.51 tatsächliche Spielweltakustik** | Räumliche Darstellung ändert weder echten Game-`SoundEvent` noch Wände/Hörreichweite, NPC-Hörbarkeit, Mikrofon-/Schallsensoren, Alarme oder Nodeausgänge |
| **02.99 / 02.101–02.104** | Follow-Winkel verändert keinen wirklichen Objekt-/NPC-/Quest-/Door-/Turn-/Inventar-/Würfelzustand und quittiert keine amtlichen Notices |
| **02.135–02.136 C / 02.137 A** | Audio-Vorlagen/Revisionen/Referenzen nur nach Originalrechten; kein neues „live NPC-Track“-Inserteingabefeld beim Vorlageneinfügen |
| **02.139 A / 02.140 A** | Kein neuer Cue-Caption-/Richtungstext-/OS-Toast oder privater Probehörplayer allein durch Follow-Updates |
| **02.105 / 02.106–02.107 / 02.116 A / 02.122 A** | Chat An/Aus separat, keine versteckten DM-/Historyrechte, individuellen Chat-Receipts, Voice-Memos oder externen Mikrofon-/Voicechat-Aufnahmen |
| **Verschiedene Viewer/Fog-/Gruppenrechte** | Pro Hörer separater wirklich zulässiger Winkel-/Richtungsfeed; keine Broadcast-Rohkoordinaten, Count-/Abo-/Timegap-/Quell-Existenzlecks |
| **Geräte/Quota** | Begrenzte lokale Pan-/HRTF-/Mono-Ausgabe, Rate/Fanout/Interpolation/Abbruch statt garantierter Samplegenauigkeit oder unbegrenzter Client-Positionsrekonstruktion |

## 4. Konzeptioneller Architektur- und Lebenszyklusentwurf

1. **Modellnamen nur zur Planung:** `SpatialCueFollowCapability`, `AuthorizedSpatialFollowSource`, `SpatialCueViewerPolicy`, `SpatialCueFollowUpdate`, `SpatialCueFollowRevision`, `SpatialCueViewerSubscription`, `LocalSpatialCueInterpolator`, `SpatialFollowAbortToken` (**keine** finalen Tabellen-/API-Namen).
2. **Doppelte serverseitige Prüfgrenze je Update:** Ein echter autoritativer Welt-/Szenenbewegungsvorgang ist der einzige sachlich zulässige Bewegungsträger, aber **kein Audio-Cue-Sender an sich**. Ein getrennter streng berechtigter Audio-Projektor ermittelt für das jeweilige wirklich aktive/erlaubte Cue-Abo nach (a) Audioasset-/Cue-/Recipient-/Medien-/Lizenz-/Actor-/Policy-/Version-ACL **und** (b) gegenwärtiger Scene-/Fog-/Position-/Karten-/Richtungs-/Höreranker-/Geheimnis-ACL **einzeln je Viewer** höchstens zulässige räumliche Präsentationswinkel.
3. **Sichere Zustellidentität:** Ein erlaubtes aktives Cue-/Recipient-/Spatial-Abonnement muss konkret Kampagne, Szene, Cueversion, aktuelles Quellrecht, Client-/Hörerberechtigung, Spatial-Fähigkeit, gültige Referenzrevision und letzte heute zulässige Richtungsprojektion binden. Client kann nicht durch geratene NPC-/Token-ID oder Streamcursor beliebige versteckte Weltpositionen abfragen. Keine zusätzlichen Listen der vollständigen echten beweglichen Objekte.
4. **Datenminimierung und Timingprivacy:** Falls feinkörnige eventbezogene Live-Updates schon ihre bloße Anzahl, Geschwindigkeit, Richtung, Ende, Pausen oder Lücken als Secret preisgeben könnten, diese Informationen **nicht** an den jeweiligen Hörer liefern. Geeignete per-Hörer normalisierte/gedrosselte Präsentationsupdates nur sofern **sowohl Inhalt als auch beobachtbares Klangmuster für ihn freigegeben** sind. Kein „verborgenes NPC bewegte sich“-Badge, Abo-Count, Fehlerrückgabe oder entsprechender Panwinkel.
5. **Quell- und Aboentzug:** SceneSwitch, Fog-Neuberechnung, Gruppen-/Rollentausch, Asset-/Lizenzende, Cue-Stop, Spatial-Aus, Musik-Aus, Follow-Aus, Disconnect, Serverrevision, eigener Browser-Mute und neu fehlendes Positionsrecht entwerten bzw. beenden Followprojektoren/Caches/Client-Interpolationsjobs kontrolliert. Wenn Audio weiterhin rechtmäßig ist, räumliche Präsentation auf neutrale nach heutiger Policy erlaubte Ausgabe zurückstellen; sonst auch Audio stoppen.
6. **Interpolation ausschließlich lokaler erlaubter Werte:** Der berechtigte Client darf zwischen **für ihn bereits freigegebenen** Richtungs-Snapshots glätten, aber **keine** exakten verborgenen Weltkoordinaten, vorherigen Secret-Cuepos, Source-Geschwindigkeiten oder geheimer Quellbewegungen extrapolieren. Bei Ausfall oder ungültiger Revision abbrechen oder in neutralen zulässigen Modus wechseln; keine falsche Spielwelthörbarkeit behaupten.
7. **Keine Replay-/Join-Synchronisierung:** Bei Join/Reconnect keine historischen Positionsupdates, keine automatisch neu gestarteten Cues, keine Playbackposition/-Clock von anderen Geräten und keine Wiederherstellung alter Secret-Koordinaten. Ein eventuell neuer echter zulässiger Cue folgt dem normalen 02.132-/02.133-Pfad mit neuer unabhängiger Laufzeit und erneuter aktueller Raumfreigabe.
8. **Keine Doppelwirkung auf Quellen:** 02.99-Worldmovement kann unabhängig stattgefunden haben; Follow liest nur erlaubte Präsentation daraus. Es erzeugt keine NPC-Motion, neue Game-Schallausbreitung, 02.51-Sensortrigger, 02.138-Duckingstart, 02.102-ACK oder autoritatives neues Würfel-/Quest-/Turn-Event. Soundeffektname „Motor“ ist kein Bewegungs-/Nodekommando.
9. **Betriebs-/Auditgrenzen:** Technische Quoten für aktives Abo, Scene-/Cue-/Source-Fanout, Updatefrequenz, Rate/CPU/Netz/Decoder/OS-Latenz; idempotente monotone Revisionen statt stale/out-of-order-Winkel, per-Campaign-Isolation, sichere Serverlogs ohne unberechtigte private Positions-/Hörerlisten. Finale Grenzwerte werden später gemessen.

## 5. Konzeptioneller Umsetzungsplan

1. **Featurepolicy:** Unter 02.132-Musik **An** und 02.142-Spatial **An** getrennt erlaubbares 02.143-Follow bei 02.25-Defaults/markierten Ausnahmen; passende Rollen/Audioarten/Cues/Szene-/Hörer-Scoping ausdrücklich erfassen.
2. **Quellbewegung und Empfängerrechte:** Serverautoritative bestehende Szene-/Entitybewegungen nur als Input einer **separaten** Audio-Projektion, mit je relevantem Positionsupdate wiederholtem echten Quell-Audio-/Cue-/Lizenzrecht **UND** heutiger eigener Scene-/Fog-/Position-/Hör-Richtungs-ACL je Viewer.
3. **Private sanitisierte Followprojektion:** Nur erlaubte abstrahierte Winkel/Relativrichtungen, gültige Revision, Ziel- und Cuebindung; geheime Herkunft, IDs, Rohkoordinaten, Bewegungs-/Updatecounts, Receiverstats und historische Strecken nicht als sichtbare Eventfelder.
4. **Lokaler Renderer:** 02.142-C-Stereo-/Pan-/unterstützte 3D-Ausgabe mit bounded Interpolation ausschließlich zwischen bereits erlaubten Richtungen, persönlichem Master-/Layer-Mute, Browserentscheidung, 02.134-Mix, 02.138-Ducking, 02.141-Normalisierung und sicherem Peak-/CPU-Fallback, **kein** zentraler Player-Clock.
5. **Löschung/Revocation/Tests:** Jede Policy-/Fog-/Szene-/Quelle-/Kampagne-/Asset-/Musik-/Spatial-/Followänderung stoppt gegebenenfalls Followjob/Cache; Tests unten für sichtbar→geheim, neu berechtigte Empfänger, ID-Spoof, Reconnect, Reordering, NoWorld/NoSensor/NoACK und private Audio-/Positionsmetadaten.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Musik 02.132 C bei Erstellung Aus | Kein Cue-/Spatial-/Followplayer; Chat/Würfel/echte 02.51-Schallfunktionen unabhängig |
| Musik An, 02.142-Spatial Aus, 02.143-Follow-Einstellung An | Keine Follow-Funktion ohne wirksames Spatial-Modul |
| Musik/Spatial An, 02.143 Follow Aus | Erlaubter 02.142-Startwinkel bleibt nach seinem Snapshot ohne Bewegungsupdate |
| Musik/Spatial/Follow An, geeignetes sichtbares Fahrzeug bewegt sich | Nur im eigenen Hörergerät erlaubte Richtungsänderung ohne echte World-/Schallwirkung |
| Hörer A darf Fahrzeug hören und seine aktuelle Position sehen | Nur erlaubte pro A gefilterte Winkel zur laufenden Audioquelle |
| Hörer B darf die Tondatei hören, aber Fahrzeugposition ist geheim | Kein abgeleiteter Bewegungs-/Pan-/3D-Winkel; ggf. nur neutraler erlaubter Ton |
| Spieler C darf weder Cue noch Quelle sehen | Kein Cue, keine Follow-Existenz, Abo-/Updatecount, Fehler-/Pan-/Zeitinformation |
| Ursprünglich sichtbare NPC-Quelle wechselt in Fog | Kein Follow der jetzt verborgenen Bewegung oder altes LastAngle-Tracking |
| Sichtrecht ändert sich von Gruppe A zu B während laufendem Cue | A verliert unzulässigen Stream, B erhält keine historische Bewegungsbahn |
| Source-ACL widerrufen, Spatial-ACL noch vorhanden | Keine weitere Audio-/Positionzustellung nur aufgrund alter Spatial-Berechtigung |
| Spatial-Recht widerrufen, Audio noch gültig | Kein weiterer Panwinkel; sichere neutrale Audiowiedergabe nur falls weiterhin erlaubt |
| Musikdateilizenz läuft ab | Kein weiteres unzulässiges Medien-/Follow-/Cueplayback |
| Cue wird manuell gestoppt | Auch gültiges Followabonnement beendet; kein selbstständiger Neu-Cue |
| NPC bewegt sich ohne Audio-Cuezuordnung | Kein neuer Musik-/Soundboard-/Spatial-/World-/Nodeevent |
| SL autorisiert eine abstrakte Richtung statt Rohposition | Nur diese explizit berechtigte Präsentationsrichtung, keine geheimen NPC-Koordinaten |
| Präsentationswinkel selbst ist als Geheimnis klassifiziert | Kein hörbares Schwenken an unberechtigten Empfänger |
| Bewegung außerhalb berechtigter Kartenfläche | Keine Rückrechnung oder versteckte Ortsinformation über Pan-Update |
| Zwei Spieler haben unterschiedliche Hörer-/Kartenausrichtung | Individuelle wahrheitsgemäß berechtigte Richtungen ohne fremde Anchor-/Camera-Daten |
| Kartenrotation innerhalb nur für A erlaubtem Bereich | Kein Leak verborgener Sourceanker über Wechsel der Kamerarichtung |
| Spieler ändert Gruppe während Live-Track | Weitere Updates vollständig nach neuer Role-/Fog-/Scene-/Audio-ACL gefiltert |
| Spieler wird neu zum Moderator ernannt | Kein Rückblick auf früher nicht erlaubte Follow-Positionen |
| SL sieht NPC geheim, Spielersicht darf nur grob links hören | Spieler bekommt höchstens genehmigte Richtung, keine präzise Tracking-/Speedspur |
| Server liefert ohne gültige Positionsfreigabe einen Winkel | Kein Client- oder API-bereits sichtbares Spatial-Detail; Guard verweigert |
| Client manipuliert Entity-ID in Spatial-Subscribe | Kein NPC-/HiddenTarget-/Cue-/Empfängerlook-up mit fremden IDs |
| Client manipuliert Timestamp/Revision/Sequence | Veraltete/gefälschte Updates nicht zugestellt oder angewendet |
| Client erhält Updates in falscher Reihenfolge | Bounded Revisionsschutz, keine Rücksprünge in alte/geheime Richtungen |
| Hohe Geschwindigkeit bei 5 gleichzeitigen erlaubten Cues | Quoten-/Rate-/CPU-/Fanoutgrenzen, keine unbeschränkte Weltpositionstelemetrie |
| Langsames Netzwerk verliert Zwischenupdates | Keine Extrapolation versteckter Koordinaten, sichere Glättung/Fallback |
| Browser unterstützt kein HRTF/Spatial | Sicherer neutraler Stereo-/Mono-/Pan-Fallback nach erlaubten Daten |
| Nutzer hat persönlichen Mastermute | Kein erzwungener Ton; Followdaten nur nach eigens wirklich vorhandenen Rechten |
| Browser blockiert Autoplay | Kein Zwangsstart oder Berechtigungs-Override durch Bewegung |
| 02.134-Layer mit zwei Quellen | Jede verfolgt nur ihre eigene berechtigte Präsentation, keine Quellvermischung |
| 02.138-Ducking aktiv, Winkel ändert sich | Kein zusätzlicher Duckstart bei Positionsupdate, eigener Mute/Gain bleibt |
| 02.141-Lautheitsnormalisierung aktiv | Nur eigener zulässiger Gainfaktor, kein Pegel-/Limiter-Zwang für andere Nutzer |
| 02.133-A-LateJoin während bewegter Quelle | Kein AutoCue und kein altes Wegstück/Nachholen von Musikpositionen |
| Reconnect nach fünf Updates | Keine Wiederholung älterer Positions-/Cue-/Audioevents |
| Client wechselt Geräte | Keine globale Winkel-/MusicClock- oder private Track-/Mute-/Hörstatistik |
| Audio-Vorlage 02.135 C referenziert bewegten Cue | Keine automatische Live-Followberechtigung durch Vorlage allein |
| 02.136-C-Version einer Cuekonfiguration geändert | Keine unmittelbare Änderung schon laufender bewegter Player ohne eigene gültige Aktion |
| 02.137 A feste Audio-Vorlage eingefügt | Kein neuer Audio-Insertparameter zur NPC-Followsteuerung |
| 02.139 A keine visuellen Cue-Captions | Keine „NPC wandert nach links“-Text-/Icon-/Caption-/OS-Toast-Schicht |
| 02.140 A kein Editor-Audio-Probehörplayer | Audio-Followrecht eröffnet keinen privaten Previewstream |
| Spatial-Unterfähigkeit zur Laufzeit ausgeschaltet | Kontrollierte Stop-/Neutralfolge, keine versteckten weiteren Richtungen |
| 02.105 Chat Aus, Musik/Spatial/Follow An | Berechtigte lokale Räumlichkeit weiterhin möglich, kein Chatzwang |
| Externer Voicechat läuft | Keine Aufnahme/Voicechatlautstärke- oder Mikrofonauswertung |
| 02.49–02.51 realer Schall-/Hör-/Sensortrigger aktiv | Nur eigene originale Game-`SoundEvent`-/Nodefachlogik, nie aus LocalFollow |
| Cue heißt `Alarm` oder `Tür öffnen` | Kein 02.99-World-/NPC-/Door-/Quest-/Würfel-/Turn-/Inventarcommit |
| 02.102-ACK eines amtlichen Hinweises offen | Richtungshören/Stoppen/Follow erzeugt keine Kenntnisnahmequittung |
| Zwei Kampagnen desselben Hörers haben gleichnamige Quellen | Keine Fremdpositions-, Actor-, Cue-, Subscriber-, Audio- oder Hörerstatistik |
| SceneSwitch beim Eingang veralteten Pan-Updates | Aktuelle Scene-/Policyversion siegt, altes geheimes Richtungsupdate verworfen |
| Spieler verlässt Kampagne und hat Cue-ID im Cache | Kein weiterer berechtigter Spatial-Abo-/Medienabruf oder geheimnisverratender Status |

## 7. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.143 C – eigene schaltbare, pro Audio-/Szenen-/Fog-/Bewegungsupdate erneut nach wirklichen Empfängerrechten geprüfte gerätelokale Nachführung bereits erlaubter räumlicher Musik-/Ambient-/Soundboard-Cues.** 02.132 C Musik An, 02.142 C Spatial An und 02.25-Default-/Ausnahmescopes müssen wirksam sein. Bloße NPC-/Objektbewegung eröffnet **keinen** automatischen Audio-Cue, keine neue Welt-/Schall-/Nodeausführung und keinen Zugriff auf geheime Positionen; schon die hörbare Positionsänderung/Updatekadenz kann geheim sein. Bei Rechteentzug Follow und ggf. Audio sicher neutralisieren/stoppen. **02.133 A** keine gemeinsame Playeruhr/Join-/Reconnect-Nachholung; **02.134 C** rein lokale Layer/Fades/Loops, **02.138 C** Ducking und **02.141 C** lokale Lautheitsnormalisierung erhalten eigene Mute-/Browserpriorität. 02.135–02.136 C Vorlagen/Updates, 02.137 A keine Audio-Insertparameter, 02.139 A keine Audio-Captions und 02.140 A kein privater Editorpreview gelten uneingeschränkt. 02.49–02.51 echte Schall-/Sensor-/Nodewelt, 02.99 Weltaktionen und 02.102 offizielle ACKs sind strikt getrennt.

**Nicht beschlossen:** genaue pro-Hörer-Ursprungs-/Kamerakoordinatentransformation, Interpolation, Raten/Hz, Glättung, echte Entfernung-/Pegelabnahme, Doppler, Headtracking, DSP-Engine, Streaming, API/DB, UI oder MVP. Die zukünftige Entfernungskurve/Audiopegelberechnung ist **keine** automatisch bereits entschiedene Game-Schallausbreitung.

## Nächste Entscheidung 02.144 – Lokale entfernungsabhängige Lautstärke räumlicher Soundeffekte

**Beispiel:** Ein Spieler darf einen fahrenden Wagen in seiner Szene bereits sehen und seine Musik-/Soundboard-Cueposition nach 02.143 C hören. Beim Entfernen könnte das Geräusch in **seinem lokalen Audiomixer** allmählich leiser werden. Die Berechnung darf weder verborgene Entfernungen verraten noch entscheiden, ob ein NPC den Wagen tatsächlich hört.

- **A – Keine spezielle Entfernungsdämpfung:** Autorisierte räumliche Cues bleiben bei den üblichen eigenen Audio-/Layer-Lautstärkewerten. Richtung nach 02.142/02.143 ist möglich, aber kein automatischer Distanz-Pegelfaktor.
- **B – Physikalische globale Audio- und Weltreichweite:** Jeder Cue übernimmt alle, auch geheimen NPC-/Objektkoordinaten, bestimmt automatisch echte Schall-/Sensor-/Alarm-/Nodewirkungen und erzwingt für alle Player identische Entfernung-/Lautstärkewerte.
- **C – Konfigurierbare sichere lokale Distanzdämpfung (Empfehlung):** Nur bei aktivem 02.132-C-Musikmodul und freigegebenem 02.142-C-Spatial darf die SL nach 02.25-Rechten für geeignete wirklich hör- und distanzberechtigte Cues **eine begrenzte rein gerätelokale Entfernungs-/Pegelkurve** zulassen. Die Distanzinformation, selbst als hörbare Lautheitsänderung, muss aktuell für den Hörer wirklich freigegeben sein; andernfalls neutraler/abgewiesener Distanzmodus. Persönlicher Master-/Layer-Mute/02.141-Normalisierung/02.138-Ducking bleiben; keine 02.133-A-Globalaudio-Uhr, keine echte 02.49–02.51-Schallreichweite/Sensor-/World-/Node-/ACK-Wirkung. Kurven, Einheiten, UI und Technik später.
