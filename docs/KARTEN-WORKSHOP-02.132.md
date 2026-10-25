# AdventureShift – Karten-Workshop: Beschluss 02.132 C – konfigurierbare Session-Musik, Playlists und Soundboards

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.132; nächste offene Frage 02.133
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungs- und Abnahmetestplan; **noch keine Softwareimplementierung**, keine fertigen APIs, DB-Verträge, UI oder MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnenstandards/markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.49–02.51 – eigenständige akustische Spielwelt-, Schall-/Sensorregeln](KARTEN-WORKSHOP.md) · [02.54 – manuelle/SL-bestätigte/automatische NPC-Steuerung](KARTEN-WORKSHOP.md) · [02.93–02.98 – optionaler Generator, manuelles Rätsellösen und Spielernotizen](KARTEN-WORKSHOP-02.98.md) · [02.99 – autorisierte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – offizielle Notices/ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106–02.107 – Channel-/Historienrechte](KARTEN-WORKSHOP-02.107.md) · [02.110 – Chat-Mute/DM-Block](KARTEN-WORKSHOP-02.110.md) · [02.114 – geschützte Dateianhänge](KARTEN-WORKSHOP-02.114.md) · [02.116 A – keine Chatlesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.122 A – keine Chat-Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.126 C – Chatnotifications](KARTEN-WORKSHOP-02.126.md) · [02.130–02.131 – geschützter Chat-Sammelfeed/Spielereignisreferenzen](KARTEN-WORKSHOP-02.131.md) · [Assets, Lizenzen und Bibliothek](LIZENZEN.md).

**Nachfolgender Beschluss 12.5 C:** [Eigene optional sichere AudioAssetDerived-/Variant-/Format-/License-/ListenerDeliverydomäne](ASSETS-WORKSHOP-12.5.md) betrifft ausschließlich rechtmäßig erzeugte Browserfassungen/Quellmedien. Sie aktiviert **nicht** 02.132-Musik bei Chat/Musik Aus, startet keine Cues, erzwingt keinen 02.133-Playhead-Sync und erzeugt keine 02.49–02.51-Weltakustik/Sensor-/Alarm-/Nodeaktion. Hörer-/Source-/Owner-/Lizenz-/Scene-/Fog-/PersonalMute-Rechte bleiben getrennt. V1 ein SL, Audioformate/Transcoding später.

**Nachfolgender Beschluss 12.6 A:** [Musik-/Playlist-/Soundboard-Assets nicht als direkte FremdURL-Hotlinks/RemoteStreams](ASSETS-WORKSHOP-12.6.md). Gültige Audioquellen müssen nach 12.1/12.4/12.5 eigene rechtmäßig angenommene VPS-Source-/VariantRevisions sein; 02.132-Musik An/Aus, persönliche Listenerrechte, 02.133-A-NoSync sowie Trennung von 02.49–02.51-Weltakustik bleiben erhalten. Externe Voicechats und 02.114-Textlinks sind weiterhin eigenständige Tätigkeiten. V1 ein SL, konkrete Audioformate/UI später.

**Nachfolgender Beschluss 12.7 C:** [Versionierte Host-/Owner-/Library-/Campaign-/AudioAsset-/MediaWorker-/Traffic-/Cache-Kontingente](ASSETS-WORKSHOP-12.7.md) berücksichtigen rechtmäßige 02.132-Musik-/SoundboardOriginale und 12.5-AudioDerivedVarianten getrennt, ohne Hörer-/Source-/Lizenz-/Mute-/02.133-A-NoSharedPlayhead- oder 02.51-NoWorldSoundrechte zu ändern. Budgeterschöpfung verursacht keine echte Alarm-/Npc-/Sensor-/Nodeaktion. V1 ein SL; konkrete Limits und UI später.

## 1. Verbindliche Entscheidung – Variante 02.132 C

**Der Projektinhaber hat ausdrücklich C gewählt:** AdventureShift soll eine **eigenständige, bei Kampagnenerstellung effektiv An/Aus schaltbare Musik-, Playlist- und Soundboardfähigkeit** erhalten. Nach **02.25-Kampagnen-/Rollen-/Gruppen-/Szenen-/Personenstandards und gültigen markierten Ausnahmen** kann die Spielleitung festlegen, wer welche erlaubten Tracks/Playlists/Cues auswählen, abspielen, stoppen, pausieren, wechseln oder für andere vorschlagen darf und ob für passende Szenen-/Sitzungsereignisse **manuelle**, **SL-bestätigte** oder **ausdrücklich erlaubte automatisierte** Musiksteuerung verfügbar sein soll. **Jeder berechtigte Hörer behält eigene Lautstärke- und Stummschaltmöglichkeiten.**

**Beispiel:** Eine SL aktiviert Musik für ihre Kampagne und erlaubt dem Moderator, die Tavernenszene musikalisch zu begleiten. Spieler A darf die Musik leiser stellen; Spieler B schaltet sie für sich aus. Ein Szenenwechsel kann – nur bei dafür aktiviertem zulässigem Automatismus – den nächsten Track auslösen. **Weder Musikstart noch Playlistwechsel erzeugt automatisch Schallwellen, Sensoralarme, Türöffnungen, NPC-Reaktionen oder Node-Ausgänge in der Spielwelt.**

**Nicht gewählt:** A (ausschließlich externe Musik-/Soundboardprogramme) und B (jeder kann ohne Berechtigung alle Hörer beschallen, fremde Assets einsehen und globale Titel/Playlists verändern). **C ist kein Audio-Streamingdienstversprechen, keine Lizenz zum Veröffentlichen von Musik und kein automatisches Einschalten des 02.49–02.51-Schallsystems.**

## 2. Funktionale Grenzen und Konfiguration

1. **Eigenes Modul, unabhängig vom Chat:** Sessionmusik/Soundboard ist bei Kampagnenerstellung **separat von 02.105 Chat An/Aus** schaltbar. „Chat Aus“ verhindert weder das rechtmäßig aktivierte Musikmodul noch externe Voicechats, eigenständige Szenensounds, manuelles SL-Spiel oder Würfel-/Systemprotokolle. „Musik Aus“ stoppt neue Musiksteuer-/Zustellvorgänge, nicht den Rest der Kampagne.
2. **Passende Fähigkeiten, kein Universalrecht:** Kampagnenstandards und gültige markierte Ausnahmen für Anlegen/Verwalten eigener Playlists, Assetzuordnung, Cueauswahl, Sessionstart/-stop/-pause, Änderungen am gemeinsamen Wiedergabeplan, begrenzte Rollensteuerung, Empfängerscope und ausdrückliche SL-Bestätigung getrennt planen. Rechte der einzelnen Quelle und Empfänger werden bei jeder Operation **serverseitig aktuell geprüft**.
3. **Drei Steuerungswege nur soweit implementiert:** **Manuell**: berechtigter Mensch startet/stoppt bewusst. **Assistiert**: berechtigter Spieler stellt Vorschlag/Antrag, autorisierte SL bestätigt gegen gültigen Zustand. **Automatisch**: nur vorher erlaubte, eng begrenzte Szenen-/Session-/Regelereignisse dürfen nach Policy geprüfte Musik-Cues auslösen. Ohne passende Aktivierung gilt **kein** stilles Autoplay aus Welt-/Chat-/Spielererignissen.
4. **Playlists und Soundboards:** Benennbare Sammlungen rechtmäßig referenzierbarer Audioassets und einzelne manuell/regelberechtigt ausgelöste **hörbare Audio-Cues** vorsehen. Welche Medienformate, Quellen, Playlistfunktionen, Schleifen, Fades, Lautstärkekurven, gleichzeitige Layer oder Musiktransitions unterstützt werden, wird später gesondert spezifiziert; **nicht** als fertig vorhanden ausgeben.
5. **Hörersteuerung:** Pro Empfänger mindestens eigene Lautstärke/Mute als Fachziel, unabhängig von fremdem Session-Control-Recht. Der gemeinsame Sessionsteuerbefehl darf individuelle Mutes nicht aufheben und keine Hardware-/Betriebssystem-Lautstärke global verändern. Browser-/Geräteautoplay- und Nutzerzustimmungsgrenzen ehrlich beachten; kein technisch versprochener Ton gegen Browser- oder Userentscheidung.
6. **Szenen und Empfängerscopes:** Zulässige Zielgruppen können ganze Kampagnensitzungen, wirklich autorisierte Gruppen, Szenen oder angemessene einzelne Hörer sein – nur sofern jeweilige Modul- und Gruppen-/Szenen-/Secret-/Fog-/Assetrechte das erlauben. Eine hidden Szene oder Playlist verrät weder durch Tracktitel noch Audio-URL, Badge, Eventliste oder gespeicherten Cue, dass sie existiert.
7. **Audioinhalte, Rechte und Datenschutz:** Nur passende selbst geschaffene/lizenzierte oder rechtmäßig nutzbare Inhalte. Separater Asset-Upload, Metadaten/Quelle, Veröffentlichung/Streaming, Wiedergaberecht, Weitergabe, Dateiformat, Größe, Quota, Viren-/Dateiprüfung, DRM/Plattformbedingungen **müssen** vor konkreter Anbindung geprüft werden. **Keine** stillschweigende öffentliche Freigabe, Fremdprovideranbindung, DRM-Umgehung oder Zulassung beliebiger Internet-Streams beschlossen.
8. **Keine Voice-/Chataufnahme:** Wiedergabefunktion ist nicht automatisch Mikrofon, Sprachchat, Sprachmemo, Mithören, Transkript, Aufnahme oder Weiterleitung. **02.122 A schließt Voice-Memos im Chat weiterhin aus.** Externe Voicechats funktionieren unabhängig; kein Abgreifen fremder Voiceaudioquellen ohne gesonderte Entscheidung.

## 3. Strikte Trennung vom akustischen Spielweltmodell

| System/Funktion | Wirkung von 02.132 C |
| --- | --- |
| **02.49 sichtbare Schallhinweise** | Musikplayer aktiviert keine Karten-Schallgrafik und verrät keine verborgenen Hör-/Geräuschzonen |
| **02.50/02.51 Schall, Reichweiten, Wände, Hörbarkeit** | Hintergrundmusik/Soundboard-Cue ist **nicht** automatisch ein berechnetes Game-SoundEvent; Musik-Aus und Akustik-Aus sind getrennte echte Konfigurationen |
| **02.48–02.51 Mikrofon-/Schall-/Präsenz-/Bewegungssensoren, Alarm-/Nodekette** | Audio-Wiedergabe löst **keine** automatischen Akustik-Sensoren, Licht-/Tür-/Alarm-/NPC-/Nodeeffekte aus |
| **02.54 und 02.99 echte Welt-/NPC-/Quest-/Türaktionen** | Nur eigene autorisierte Weltaktion, nie Musiktext, Tracktitel oder Playbacklistener |
| **02.105–02.131 optionaler Chat/Notifications** | Musik bleibt bei Chat Aus eigenständig; Chat-Nachrichtentext, 02.131-Würfelreferenz oder 02.126-Toast ist kein unbeschränkter Musik-Control-Trigger |
| **02.101–02.104 offizielle Hinweise/ACKs** | Musikton/Playliststart quittiert keine amtliche Kenntnisnahme oder Korrektur, blockiert keine gesamte Session |
| **02.114 Dateien/02.122 A Voice-Memo-Ausschluss** | Eigenes geprüftes Audioasset ist nicht ohne separate Berechtigung ein neuer Chat-Sprachnachrichtpfad |
| **12 Assets/Bibliothek** | Musikrechte und Datei-/Metadatenzugang brauchen eigene Quell-ACL und rechtmäßige Nutzung; kein Umgehen geheimer Bibliotheksordner |
| **Individuelle Audio-Einstellungen** | Persönliches Muting/Volume ersetzt nicht 02.110-Chat-Kanalmute und hebt auch 02.110-DM-Block nicht auf |

**Grenze für spätere Integrationen:** Falls künftig ausdrücklich zwischen hörbarer Audiokulisse und einem 02.51-wirksamen echten Schall-/Nodeevent gekoppelt werden soll, braucht es eine **getrennte, eigens freigegebene, serverautoritativ geprüfte Spielweltaktion**. Diese Kopplung wird **durch 02.132 C nicht bereits beschlossen oder aktiviert**.

## 4. Berechtigungen, Sessionzustand und Technikgrenzen

1. **Serverautoritative Steuerung:** Echte Kampagnen-/Rollen-/Szenen-/Gruppen-/Asset-/Personenrechte, gültige Policyversion und aktuelle Wiedergabe-Sessionversion vor Playlist-/Cue-/Start-/Stop-/Pause-/Skip-/Auto-Triggeroperation prüfen. Ein Client darf weder SL-Aktionen durch falsche User-ID noch heimlich andere Kampagnen steuern.
2. **Zugriffsgefilterte Musikmetadaten:** Tracktitel, Playlistnamen, Dateipfade/-URLs, Artwork, interne Taglisten, Queueplätze, Cuezeitpunkte, „hörte X“, versteckte Szenen, Anzahl/Teilnehmer und Playback-Projektionen erst **pro berechtigtem Betrachter** ableiten. Direktes Media-URL-Raten, Cache/History/Realtime/Search/Export muss Original-Assetrecht beachten.
3. **Sessionversion, Race/Replay:** Gleichzeitiges „Skip“, „Pause“ und automatischer Cue oder SL-Approval sollen konsistent, dedupliziert und idempotent verarbeitet werden; keine veralteten alten Szenen-/Asset-/Permission-Cues nach SceneSwitch/Reconnect/Serverrestart. Wiedergabe-Timeline ist konzeptionell und kein garantiert perfekt synchrones Audiostreaming.
4. **Geräte und Late-Join:** Reconnect, Gerätewechsel oder nachträglicher Beitritt dürfen nur **aktuell freigegebene** Audio-/Playlist-/Szenenmetadaten und den gültigen Sessionzustand erhalten; keine Wiederherstellung verlorener privater Titel oder heimliche Audio-Autoplayzusage. Detailfragen zu Wiedergabesynchronisation, Weiterlaufen bei Join/Reconnect und Browser-Autoplay werden **in 02.133** entschieden.
5. **Hörerpräferenzen:** Persönliche Lautstärke/Mute ist nur für den eigenen Account/die berechtigte Clientinstanz wirksam; weder Playliständerung noch Rollentausch darf diese still überschreiben. Speicherung/Sync der Präferenzen, Standards, Mix aus Soundboard/Musik und Betriebsmodi später präzisieren.
6. **Sichere Audiodateien:** Medienvalidierung, Content-Type-/Codec-/Größen-/Quota-/Ratelimits, Schadsoftware-/SSRF-/Redirect-/Lizenzprüfung, rechtmäßig kontrollierte Zugriffs-URLs und begrenzte Cache-Aufbewahrung; kein unberechtigter Download durch identifizierbare Streaming-URL, kein Zwang zu Drittanbieter-Accounts oder Mikrofon.
7. **Fehler und Redaktionen:** Bei Rechteentzug, Assetlöschung, Playlistpolicywechsel, Sessionende oder Musik Aus hören Zielzustellungen auf; eventuell bereits lokal dekodiertes/abgespieltes Audio kann **nicht rückwirkend aus menschlichem Wissen gelöscht** werden. Keine geheimen Tracknamen/Fehlergründe an neue/entzogene Empfänger ausgeben.
8. **Klare Betriebskosten:** Mehrere Zuhörer, Datei-/Streambandbreite, Latenz und simultane Loops verursachen Ressourcenbedarf. Konkrete Streaming-/Cachingstrategie, Kosten, Lastgrenzen und automatische Qualitätsreduktion sind noch **nicht** entschieden und müssen gemessen werden.

## 5. Konzeptioneller Umsetzungsplan

1. **02.25-/Kampagnen-Featureinventar:** Eigenständiger schaltbarer `SessionAudioCapability`-Scope, getrennt vom 02.105-Chat und 02.51-Schall. Unterfähigkeiten Playlist verwalten, Cue initiieren, shared Player steuern, begrenzte Vorschlags-/SL-Freigabe und eventabhängiges Auto-Playback nur im ausdrücklich erlaubten Modus.
2. **Quell- und Lizenzresolver:** Konzeptionell `AudioAssetEligibility` / `AudioPlaylistSourceRef` für wirklich freigegebene Audioreferenzen mit Asset-/Lizenz-/Quoten-/Quell-ACL; keine neue beliebige Audio-Provider-Bridge als stiller Bestandteil.
3. **Autorisierte Sitzungskontrolle:** Konzeptionell `SessionAudioPolicy`, `SessionAudioCommand`, `SessionAudioState`, `SessionAudioApprovalRequest`, `SessionAudioCueRule` und `SessionAudioRevision` (keine finalen DB-/API-Namen). Policy-/Actor-/Target-/ExpectedRevision-/Idempotenz-/Auditprüfung je eigenem echten Control-Befehl.
4. **Individuelle Projektion:** Konzeptionell `AudioRecipientView` und `AudioOwnVolumeMutePreference`: serverseitige Empfänger-/Szenen-/Assetgeheimnisprüfung, anschließend lokale eigene stumme/leise Wiedergabe. Inklusive Wiedergabeverweigerung/Browser-Autoplay-Respekt; keine fremden Hardwarelautstärke- oder Chat-Mute-Eingriffe.
5. **Trennung echter Weltreaktionen:** Musik-/Soundboard-Output darf weder `SoundEvent`/02.51-Hörbarkeitslogik noch Alarm-/Door-/NPC-/Quest-/Node-Turn-Commit oder 02.102-ACK erzeugen. Reale Spielweltaktionen bleiben eigenständig geschützt.
6. **Abnahme und spätere Details:** Fachtestmatrix unten. Präzise Playlistbearbeitung, Cue-Fade-/Loop-/Layering, Multiuser-Synchronisierung, tatsächliche Codec-/Deliverytechnologie, UI, Medienanbieter, Speicher-/Ablaufzeiten und MVP nach Feature-Workshop entscheiden.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Bei Erstellung Musik Aus, Chat An | Chat funktioniert unabhängig, keine neue Sessionmusikoperation oder Playbackprojektion |
| Musik An, Chat Aus | Freigegebene Musik-/Soundboardsteuerung funktioniert, ohne dass Chat aktiviert wird |
| Musik Aus, 02.51 Schall aktiv | Bereits beschlossene echte Schall-/Sensor-/Spielweltfunktionen bleiben unabhängig |
| Musik An, 02.51 Schall Aus | Musik hörbar nur nach Browser-/Hörerentscheidung; keine reale Schallsimulation wird eingeschaltet |
| Berechtigte SL startet Tavernentrack | Nur tatsächlich freigegebene Hörer/Assets/Szenen erhalten erlaubte Musik |
| Spieler ohne Sessionsteuerrecht schickt gefälschten Skip | Serverseitig abgelehnt; Playlist und andere Teilnehmer bleiben unverändert |
| SL delegiert begrenzte Soundboard-Cues an Moderator | Nur gültige eigene Cue-/Ziel-/Asset-/Szenenrechte wirken |
| Berechtigter Spieler beantragt Trackwechsel | Ohne erforderliche SL-Freigabe noch **keine** wirkliche Wiedergabeänderung |
| Genehmigung trifft nach SceneSwitch ein | Veraltete Scene-/Policy-/Sessionrevision verhindert ungeprüfte späte Wiedergabe |
| Automatische Musikregel für Szenenwechsel deaktiviert | Kein automatischer Trackstart; manuelle Steuerung separat möglich |
| Automatische Regel aktiv, erlaubte Szene gewechselt | Nur explizit erlaubte Musikcue nach aktueller ACL/Policy, kein Welt-/Sensortrigger |
| Spielleiter lädt beliebigen Fremdstream ohne Rechte | Keine automatische Fremdprovider-/DRM-/Urheberrechtsfreigabe |
| Nicht berechtigter Nutzer errät geheime Audioasset-ID | Keine URL, Datei, Tracktitel, Playlist, Artwork oder Count an Unberechtigte |
| Spieler in geheimem Gruppenbereich hört andere Musik | Keine Leaks der verborgenen Szene oder Playlist an Außenstehende |
| Spieler stellt eigene Musik leiser | Nur eigene Wiedergabe ändert sich, nicht gemeinsame Trackauswahl oder Lautstärke anderer |
| Spieler schaltet eigene Musik stumm | Sessionautorität kann diese persönliche Wahl nicht unerlaubt übergehen |
| Browser blockiert automatisches Playback | Keine Behauptung garantierter Wiedergabe gegen Browser-Policy, kein erzwungenes Mikrofon |
| Neuer Spieler tritt später bei | Nur aktuell berechtigte Session-/Trackinfos, kein Zugriff auf alte private geheime Audiofiles |
| Rolle/Gruppe/Scene-ACL wird entzogen | Zukünftige Audiozustellung und private Metadaten gestoppt, keine Restfreigabe durch Reconnect |
| SL entfernt ein Audioasset aus Playlist | Keine neue Nutzung/URL ohne Quellenrecht; Cache und Freigaben überprüft |
| Zwei Clients schicken gleichzeitig Skip/Stop | Version-/Idempotenzschutz entscheidet konsistent ohne doppelten Cue |
| Session verliert Internetverbindung und reconnectet | Keine ungewollte Wiederholung schon verworfener Wiedergabebefehle |
| Music-Cue enthält Text „Tür öffnen“ | Keine Tür-/Quest-/NPC-/Würfel-/Inventar-/Node-/Turnaktion |
| Soundboard spielt Alarm-Sounddatei ab | **Kein** echtes Alarmsensor-/Schall-/Bewegungs-/Node-/Door-Event |
| Eigenständiger echter 02.51-Schallalarm ertönt | Richtige Sensor-/Weltlogik ausschließlich über eigene fachliche Sound-Event-Quelle |
| Musikplayer neben 02.126 Chat-Benachrichtigungen | Keine Verwechslung von Chat-Tönen, Musikcues und echten Szenensounds |
| Offizielle 02.102-Korrektur-ACK erforderlich | Musik abspielen/stummschalten bestätigt keine Kenntnisnahme |
| Chat 02.122 A verbietet Voice-Memos | Musikmodul liefert keinen neuen Mikrofon-/Chat-Sprachnachrichten-/Aufnahmeweg |
| Zwei Kampagnen desselben Accounts | Keine unberechtigte Playlist, Musiksteuerung oder Audiodatei der anderen Kampagne |
| Rollenwechsel und persönliche Mutepräferenz | Fremder Role-/Playlistwechsel schaltet eigene Stummschaltung nicht heimlich ab |
| Zu viele Cues/Dateien/Requests | Serverseitige Quoten, Rate-/Abuse-/Asset-/Transport-/Lizenz-/ACL-Schutz |
| Externer Voicechat läuft gleichzeitig | Keine automatische Aufnahme/Mithör-/Transkriptionspflicht durch integrierte Musik |

## 7. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.132 C – optionales, konfigurierbares Musik-/Playlist-/Soundboardmodul bei Kampagnenerstellung**, mit Berechtigungen nach 02.25 gültigen markierten Ausnahmen, nur konkret erlaubten Rollen-/Kampagnen-/Szenen-/Empfängerscopes, geeigneter manueller, SL-bestätigter oder freigegebener automatischer Steuerung und **eigenem Volume/Mute pro Hörer**. Es ist **unabhängig von 02.105-Chat und 02.49–02.51-Schall-/Sensor-/Node-/Alarm-/Worldeffekten**, braucht echte Audioasset-/Lizenz-/Quell-ACL, erlaubt kein unberechtigtes Cross-Kampagnen-/Secret-Metadatenleck, verspricht kein Streaming gegen Browser-/Plattform-/Urheberrecht und triggert keine 02.99-Weltaktionen/02.102-ACKs. Die unverändert negativen Chatbeschlüsse 02.116 A keine Lesebestätigungen, 02.118 A keine Drafts, 02.122 A keine Chat-Voice-Memos, 02.123 A kein Forwarding, 02.125 A keine Chatkomfortexporte, 02.127 A kein Slowmode und 02.128 A kein per-Message-Hide bleiben vollständig bestehen.

**Nicht beschlossen:** konkretes UI, vollständiges Feature-/Presetinventar, Codec-/Audio-/Streamingbibliotheken, Drittanbieterprovider, Lizenzmodelle, Kosten-/Skalierungswerte, Fade/Loop/Playback-Synchronisation und Join/Reconnect-Verhalten, exakte DB/API-Felder oder MVP. Die Entscheidung ist Fachplanung, keine fertige Software.

## Nächste Entscheidung 02.133 – Gemeinsame Musiksynchronisation und Verhalten bei späterem Beitritt

**Beispiel:** Während die SL gerade einen Song laufen lässt, tritt eine Spielerin neu bei oder verbindet sich nach einem Abbruch erneut. Die Gruppe will vielleicht denselben Titel an ähnlicher Stelle hören, aber die Spielerin hat ihre Musik bewusst stummgeschaltet oder ihr Browser verweigert automatisches Abspielen.

- **A – Ausschließlich lokale Wiedergabe:** Jede Person startet selbstständige Musik immer bei Titelanfang; Session-Position, Start-/Pausenstatus und Wiedergabe beim Beitritt werden nie gemeinsam geplant.
- **B – Erzwungener automatischer Gleichklang:** Jeder Client muss bei Join/Reconnect Musik sofort mit exakt identischer Position/Lautstärke wiedergeben – auch gegen persönliche Stummschaltung, Browser-/Betriebssystemregeln oder fehlende Rechte.
- **C – Konfigurierbare synchronisierte Sitzung mit Hörerautonomie (Empfehlung):** Bei aktiviertem 02.132-Musikmodul kann die SL nach 02.25-Policy eine autoritative **gemeinsame Track-/Queue-/Transportposition** für wirklich berechtigte Empfänger führen und passende Join-/Reconnect-/Szenenwechsel-Verfahren wählen. Clients dürfen erst nach echter Quell-/Szenen-/Empfängerautorisation und ihren eigenen Volume-/Mute-/Browser-Playbackentscheidungen einsteigen; individuelle Geräte-/Browser-Latenz bedeutet keinen garantiert samplegenauen Gleichklang. Keine World-/Schall-/Node-/ACK-Wirkung, kein Play-Zwang, konkrete UI/Algorithmen später.
