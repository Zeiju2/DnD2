# AdventureShift – Karten-Workshop: Beschluss 02.140 A – kein gesondertes privates Audio-Probehören im Editor

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.140; nächste offene Entscheidung 02.141.
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungs-/Negativtestplan; **noch keine Softwareimplementierung**, kein fertiges UI, keine endgültigen API-/DB-Verträge oder MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnen-/Rollenstandards und markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.49–02.51 – eigenständiger Spielszenenschall, Sensoren und Nodes](KARTEN-WORKSHOP.md) · [02.99 – echte Spielweltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – offizielle Korrekturhinweise/ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – optionaler Chat](KARTEN-WORKSHOP-02.105.md) · [02.110 – Chatmutes und DM-Senderblock](KARTEN-WORKSHOP-02.110.md) · [02.116 A – keine individuellen Chatlesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.122 A – keine Chat-Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.126 C – Chat-Benachrichtigungen](KARTEN-WORKSHOP-02.126.md) · [02.132 C – optionales berechtigtes Musik-/Playlist-/Soundboardmodul](KARTEN-WORKSHOP-02.132.md) · [02.133 A – ausschließlich lokale Wiedergabe ohne Sync/Join-Catch-up](KARTEN-WORKSHOP-02.133.md) · [02.134 C – lokale Loops/Fades/Soundboard-Layer](KARTEN-WORKSHOP-02.134.md) · [02.135 C – geschützte Audio-Playlist-/Soundboardvorlagen](KARTEN-WORKSHOP-02.135.md) · [02.136 C – kontrollierte Vorlagenupdates](KARTEN-WORKSHOP-02.136.md) · [02.137 A – feste Audio-Vorlagen](KARTEN-WORKSHOP-02.137.md) · [02.138 C – lokales Cue-Ducking](KARTEN-WORKSHOP-02.138.md) · [02.139 A – keine speziellen visuellen Cue-Captions](KARTEN-WORKSHOP-02.139.md).

## 1. Verbindliche Entscheidung – Variante 02.140 A

**Der Projektinhaber hat ausdrücklich A gewählt:** AdventureShift plant **keinen eigenständigen privaten Probehör-/Preview-Player im Musik-/Soundboardeditor**. Tracks und Cues werden ausschließlich durch die **bereits unter 02.132 C zulässigen normalen, separat autorisierten Wiedergabe-, Auswahl- und Bearbeitungswege** verwendet beziehungsweise praktisch ausprobiert. Es gibt **keinen** zusätzlich zum regulären Player eingebauten Editor-Knopf „Privat probehören“, keinen gesonderten Vorab-Stream nur für SL/Redakteure, keinen Schatten-Preview-Kanal und **keine** eigene Probehör-Berechtigung oder deren 02.25-Ausnahmeschalter.

**Beispiel:** Die SL bearbeitet eine geschützte Tavernenplaylist und möchte die Regen-Datei hören. In der Planungsentscheidung 02.140 gibt es **keinen separaten Preview-Player im Editor**, der dieses Asset außerhalb der normalen 02.132-Musik-/Audioasset-Rechte spielt. Die SL darf nur einen bereits regulär zulässigen Audio-/Bearbeitungsweg nutzen. Eine Editoransicht oder Titelvorschau **erteilt keine** zusätzlichen Audio- oder Geheimnisrechte. Ob ein normal autorisierter lokaler Player für einen konkreten Sound ohne andere Zuschauer nutzbar ist, bestimmt ausschließlich seine **bereits bestehende** berechtigte Ziel-/Hörer-/Browser-/Szenen-Policy – **kein neuer Vorschau-Sondermodus**.

**Nicht gewählt:** B (automatisches Testaudio für alle inklusive versteckter Medien) und C (eigenständiger, durch Rollen/Kampagne gesondert schaltbarer privater Editor-Preview-Player). **A verbietet nicht** gewöhnliche, schon beschlossene lokale Musik-/Soundboardwiedergabe und deren persönliche Lautstärke/Mute, sondern **nur** ein zusätzliches spezielles Probehör-/Vorschau-Feature.

## 2. Abgrenzung zu bestehenden Audio- und Editorfunktionen

1. **Keine editorinterne Wiedergabeerweiterung:** Audioeditor/Bibliotheksansicht darf berechtigte Track-/Playlist-/Cueinformationen und normale Bearbeitungsaktionen anzeigen; der bloße Editor-/Asset-Fokus löst **keine** Preview, kein automatisches Abspielen, keinen geheimen „Play Sample“-Befehl und keinen neuen Player an anderer Audio-Medien-Endpunktberechtigung aus.
2. **02.132 C bleibt gültig:** Das Musik-/Playlist-/Soundboardmodul ist nach 02.25 bei Kampagnenerstellung An/Aus schaltbar und erlaubt nach echten Kampagnen-/Rollen-/Gruppen-/Szenen-/Asset-/Lizenz-/Empfängerrechten rechtmäßig ausgewählte manuelle, SL-bestätigte oder freigegebene automatisierte **reguläre** Cue-/Musikvorgänge. 02.140 A schafft dabei **keine** neue Ausgangs-/Zielgruppe.
3. **Kein versteckter Privilegienpfad:** Ein Editor-Owner, Rollenwechsel, SL-Mitglied oder Template-Verwalter darf nicht durch „Preview“ ein fremdes Track-/URL-/Datei-/Secret-/DM-/Szenenrecht umgehen. Auch direkte Audio-/HTTP-/CDN-/Blobabrufe, Manipulation von Client-/APIflags, Caches, Indexsuche und Browser-Navigationslinks behalten 02.132-C-Quell-/Medien-/Lizenzprüfungen.
4. **Keine neue öffentliche Wiedergabe:** Der Ausschluss eines separaten privaten Players heißt **nicht**, dass beim Bearbeiten automatisch alle Soundboard-Cues an Spieler zugestellt werden. Ein **regulärer** Wiedergabeaufruf benötigt stets echten 02.132-C-Actor-/Ziel-/Empfänger-/Szenen-/Asset-/Lizenzschutz. B bleibt ausdrücklich abgewählt.
5. **Lokale Hörerentscheidungen:** 02.133 A erlaubt nur unabhängige Wiedergabe, jeder echte neue Track beginnt bei **0**. Keine gemeinsame Musikposition, kein globales Seek-/Pause-/Join-/Reconnect-Catch-up. Eigener Master-/Layer-Mute, lokale Lautstärke und Browserautoplay bleiben **auch beim normalen Test über den regulären Player** unantastbar.
6. **Lokale Audiomischung:** 02.134-C-Loop-/Crossfade-/Layer und 02.138-C-reduzierendes eigenes Cue-Ducking bleiben bei **wirklich regulär abgespieltem und autorisiertem** Audio möglich; Editorfokus schaltet keine neue Overlap-/Ducking-/Mix-Funktion ein.
7. **Vorlagen und Updates:** 02.135-C-referenzierte oder kopierte Audio-Konfigurationsvorlagen, kontrollierte 02.136-C-Versionen und 02.137-A-feste Vorlagenwerte ohne Insertparameter bleiben; weder der Vorlageneditor noch Versionsdiff erhalten ein neues Probehör-Sonderrecht für verbotene Tracks oder eine implizite Medienlizenz.
8. **Keine neuen Audio-Captions:** 02.139 A schließt besondere beim Cue ausgelöste Texthinweise weiter aus. Gewöhnliche bereits berechtigte Tracknamen, normale Editorbedienbarkeit und allgemeine Barrierefreiheit bleiben möglich.
9. **Externe Tools nicht automatisiert:** 02.140 A verpflichtet weder zu externen Probehörprogrammen noch zu Drittanbieter-Streaming, Upload, Kopie, Download, Voicechatmitschnitt oder Weiterleitung an Teilnehmer. Ob rechtmäßig bereits lokal vorhandene Dateien außerhalb von AdventureShift genutzt werden, liegt außerhalb dieses Beschlusses; keinerlei Rechte entstehen dadurch in der Anwendung.

## 3. Unverändert gültige Fachgrenzen

| Bestehender Beschluss | Folge für 02.140 A |
| --- | --- |
| **02.25 / 02.132 C** | Keine AudioEditorPreviewCapability und keine Kampagnen-/Rollen-/Personenausnahme; vorhandene gültige normale Musik-/Asset-/Empfänger-ACL bestehen |
| **02.133 A** | Nur lokale neue Trackstarts am Anfang, kein globaler Playhead oder Join-/Reconnect-Sync – auch kein Preview-Catch-up |
| **02.134 C / 02.138 C** | Nur regulär berechtigte lokale Loops/Fades/Layers und optionales Ducking bleiben; kein spezieller Editor-Preview-Mixkanal |
| **02.135-/02.136 C / 02.137 A** | Vorlagen-/Update-/Kopier-/Editrechte verleihen keinen neuen Audio-Preview-Stream; beim Einfügen bleibt die Vorlage fest |
| **02.139 A** | Kein Preview-ausgelöster Cue-Text/Untertitel oder visuelles Zusatzprotokoll |
| **02.49–02.51** | Reale Schall-/Hörbarkeit-/Sensor-/Node-Funktion unabhängig; Audio-Test erzeugt keinen echten `SoundEvent` |
| **02.99 / 02.101–02.104** | Kein Door-/Quest-/NPC-/Turn-/Würfel-/Inventareffekt oder automatischer 02.102-ACK aus Editor-/Playerinteraktion |
| **02.105 / 02.110 / 02.126** | Chat/DM-/Mute-/Notifications unabhängig; kein automatisch versendeter Chat-/OS-Preview-Badge oder Audio-Cue-Weiterleitung |
| **02.116 A / 02.122 A** | Keine individuellen Lese-/Zustellbestätigungen, keine Chat-Voice-Memos, keine Mikrofon-/Sprachtranskription durch Editor |
| **Allgemeine Medien-/Lizenzrechte** | Weder Previewwunsch noch Player-/Editorzugang erlaubt neue Medienstream-URLs, DRM-/Lizenzübertragung oder geheime Asset-Downloads |

## 4. Konzeptioneller Negativvertrag und technische Grenzen

1. **Nicht zu planende Spezialmodelle:** `EditorAudioPrivatePreview`, `AudioAssetPreviewPlayer`, `AudioEditorPreviewSession`, `PrivateAudioPreviewGrant`, `PreviewOnlyStreamingUrl`, `AudioEditorSamplePlayback` sind **ausgeschlossene Funktionsideen**, keine finalen Klassen-/Tabellennamen. Kein versteckter 02.25-Default zur Reaktivierung.
2. **Normale Audioquellen bleiben autoritativ:** Jeder tatsächliche Track-/Cueabruf benötigt nach 02.132-C-Musik-An-Status gültige Actor-/User-/Rollen-/Ziel-/Empfänger-/Szenen-/Audioasset-/Lizenz-/Medien-/Geheimnis-/Policy-/Revision-Berechtigung. Editor-Read kann diese nicht ersetzen oder den ganzen Medieninhalt freischalten. Server prüft erneut bei Medien-, Stream-, Download-, Cue-, Subscribe-, Reconnect-, Cache-/URL- oder Linkzugriff.
3. **Player- und Editor-Zustand trennen:** Editoröffnung, Datei-/Waveform-/Metadatenwahl, Vorlagen-/Revisionsdiff und Fokuswechsel sind **keine** Musikspielbefehle. Es gibt keinen per-Editor heimlichen Teststream, der reguläre Playlist-/Audioasset-/Cue-Counter oder Quoten bypassed.
4. **Keine unbeabsichtigte Zuschauerzustellung:** Normale 02.132-C-Spielaktionen erfordern einen ausdrücklich rechtmäßig gewählten Ziels-/Empfängerscope. Der negative Previewentscheid darf **nicht** als Begründung dienen, jede Editorbearbeitung standardmäßig allen Teilnehmern vorzuspielen.
5. **Sicherheits-/Abusegrenzen:** Bereits bestehende sichere Medienreferenzen/Signaturen, Source-/Target-/Owner-/Asset-/Lizenz-/Secret-ACL, Upload/SSRF/Redirect-/Datei-/Rate-/Quota-/Retention-/Cache-Prüfung bleiben. Geheime Track-, Cuenamen, Dateipfade, Streaming-URLs, Playerstatus, Hörerlisten und Fehler-/Existenzunterschiede dürfen nicht über vermeintliche Preview-Requests ausgeleitet werden.
6. **NoWorld-/NoACK-Grenze:** Weder Editorinteraktion noch rechtmäßig normal abgespielte Musik liefert von selbst 02.49–02.51-Game-SoundEvent-/Sensor-/Alarm-/Node-/Tür-/NPC-/Quest-Wirkung, 02.99-Spielweltzustandsänderung oder 02.102-amtliche Kenntnisnahme.
7. **UX-/MVP-Abgrenzung:** Normale Bibliotheks-/Player-/Editorbedienbarkeit ist später zu gestalten; dabei darf kein gesonderter „privat probehören“-Button/Workflow eingeführt werden. Wie ein erlaubter regulärer Player im Layout erreichbar ist, wird **nicht** jetzt entschieden.

## 5. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| SL öffnet Audioeditor und wählt einen Track | Keine automatische Wiedergabe, kein eigener Preview-Playbutton |
| SL klickt möglichen Endpunkt `/audio/editor/preview` | Keine fachlich zulässige neue Private-Preview-API/Berechtigung |
| Entwickler aktiviert versteckten `previewEnabled`-Schalter | Kein 02.25-Override oder neues PreviewFeature gegen A |
| Musikmodul 02.132 C ist Aus | Keine aktive Audioeditor-/Preview-Musikwiedergabe; Würfel, Chat, Schall unabhängig |
| Audioeditor zeigt normal berechtigten Tracknamen | Reguläre erlaubte Metadatenanzeige möglich, aber kein neuer Probehörstream |
| SL besitzt Audio-Asset-Metadatenleserecht, aber keine Medienlizenz | Kein vollständiger Dateistream nur wegen Editor-Previewwunsch |
| Benutzer errät geheime Musikdatei-ID | Kein geheimer Trackabruf, Metadaten-/Error-/Count-Leak über Editor |
| SL sieht fremde Gruppen-Soundboardvorlage ohne Quellrecht nicht | Kein Title-/Cue-/URL-/Szenen-/Preview-Zugang über erratene Referenzen |
| SL bearbeitet erlaubte Playlist ohne echten Cue-Start | Keine neue Musikzustellung an Spieler, kein heimliches Preview |
| SL führt bewusst reguläre und gültig berechtigte 02.132-C-Musikaktion aus | Normaler Audio-/Empfänger-/Actor-/Lizenzpfad; kein besonderes Preview-Bypass |
| Spieler ohne Cue-/Steuerrecht versucht Editor-Test | Keine Erlaubnis auf fremde Teilnehmer oder Secret-Assets |
| Ein normaler Audioaufruf ist gemäß bestehenden Rechten lokal zulässig | Normale unabhängige Wiedergabe bleibt erlaubt, kein neuer privater Sonderplayer erforderlich |
| Benutzer beginnt Musik lokal | Track startet bei 0, kein 02.133-A-SharedClock-/Seek-/Join-Sync |
| B tritt spät bei einer Kampagne bei | Keine private Vorhör-Nachzustellung oder automatische Musik-Catch-up |
| A hat Musikmaster stummgeschaltet | Normaler Musik- oder Cueaufruf kann Mute nicht übergehen |
| Browser lehnt normalen Musikstart ab | Kein editorinterner Preview-Bypass gegen Browser-Autoplay |
| 02.134-C-Layer/Fades sind für Hörer erlaubt | Funktionieren nur bei normalem berechtigtem Playback, nicht durch Editorfokus |
| 02.138-C-Ducking bei regulärem berechtigtem Soundboard-Cue | Darf eigenen Mix senken, ohne eigenen Preview-Channel zu erfinden |
| SL ändert Vorlagenkonfiguration 02.135 C | Keine automatische Vorhörwiedergabe aus Vorlage oder Kopie |
| 02.136-C-Update-Diff enthält privaten Track | Kein Preview-Stream/URL/Snippet zur Umgehung von Geheimnis-ACL |
| 02.137-A-feste Vorlage wird eingesetzt | Kein Insert-Parameter oder neuer Audioeditor-Vorhörschritt |
| 02.139-A-visuelle Cue-Captions ausgeschlossen | Editor-/Player-Test erstellt keine neuen Cue-Untertitel oder Caption-History |
| Eigene reguläre Player-/Volume-/Mute-Buttons per Screenreader erreichbar | Allgemeine UI-Zugänglichkeit bleibt planbar, A verbietet keine regulären Labels |
| Chat 02.105 ist Aus, Musik 02.132 C ist An | Berechtigte normale Musikaktionen möglich ohne Chat/Previewmodul |
| Editor-Testwunsch enthält Text `/roll 20` oder `Tür öffnen` | Kein echter Würfel-/Door-/Quest-/Node-/Turn-/Inventareffekt |
| Soundboard-Cue heißt `Alarm` und wird regulär abgespielt | Kein 02.49–02.51-Schallsensor-/Alarm-/GameSoundEvent nur durch Playback |
| Offizielle 02.102-Korrektur muss bewusst bestätigt werden | Musikstart, Editorbedienung oder Stoppen quittiert nicht amtlich |
| 02.122 A keine Chat-Voice-Memos | Audioeditor erstellt keinen Mikrofon-/Sprachnachrichten-/Mithörpfad |
| Sl versucht `sendPreviewToAll` oder `listenSecretPreview` | Kein eigenes Previewbroadcast-/Geheim-Sonderrecht |
| Zwei Kampagnen mit derselben rechtmäßig verfügbaren Datei | Kein CrossCampaign-Asset-/Cue-/Teilnehmer-/Preview-Leak |
| Quell-Assetlizenz läuft zwischen Editoröffnung und normalem Playerstart ab | Neuer Source-/Medien-ACL-Check verweigert unerlaubte Wiedergabe |
| Browser neu geladen, Editor bleibt offen | Keine wiederaufgenommene Preview-Sitzung, kein globaler Playhead, kein stiller Neustart |
| SL editiert unter laufender anderer Spieler-Musik | Kein durch Editierung ausgelöster weltweiter Stop-/Start-/Preview-Cue |
| Audioeditor-Dienst verursacht Fehler | Keine heimliche World-/Node-/System-/ACK-Auswirkung |
| Benutzer fordert allgemeine Barrierefreiheit im Audioeditor | Gewöhnliche zugängliche UI bleibt möglich ohne neues Vorhörmodul |
| Normale Playliste wird nach Rechtewechsel aufgerufen | Neueste Rechte gelten; alter Editorcache kann Audiofreigabe nicht erhalten |
| Musiksystem technisch offline, separates Schallmodul online | Echte SoundEvents/Sensoren bleiben unabhängig; kein Editorpreview |
| Benutzer versucht 10000 Preview-IDs | Kein neuer Rate-/Existenzbypass, 02.132-Medien-/ACL-/Quota-Grenzen gelten |

## 6. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.140 A – kein eigener privater Audio-Probehörplayer, keine speziellen Editor-Preview-URLs, Berechtigungen, Einstellungen, Realtime-/Cue-Streams oder Audio-Vorschau-Workflows.** Reguläre, 02.132-C-autorisiert zulässige Musik-/Soundboardaktionen und gewöhnliche Editor-/Asset-Metadaten bleiben bestehen; Editorberechtigung gewährt keine gesonderten Streaming-/Geheimnismedienrechte. Fortgeltend 02.133 A lokale Musik ohne Sync/AutoJoin, 02.134 C lokale Fades/Loops/Layers, 02.135-/02.136 C sichere Audio-Vorlagen/Updates, 02.137 A keine Insertparameter, 02.138 C nur lokales Ducking und 02.139 A keine Audio-Cue-Captions. Allgemeine UI-A11y, echte 02.49–02.51-Spielwelt-Schall-/Sensor-/Nodefunktionen, 02.99-Worldactions und amtliche 02.101–02.104-Notices/ACKs bleiben fachlich unabhängig.

**Nicht beschlossen:** finales Editorlayout, normaler Player-/Assetbrowser, Audioformat-/Medien-/Lizenzprovider, technische Audio-Engine/API/DB, MVP. Fachplanung, keine Softwareimplementierung.

## Nächste Entscheidung 02.141 – Lokale Lautheitsanpassung zwischen Musik- und Soundboarddateien

**Beispiel:** Eine SL besitzt rechtmäßig zwei verschiedene Musikdateien. Eine wurde sehr leise, die andere sehr laut aufgenommen. Die Gruppe soll nicht bei jedem lokalen Trackwechsel erschrecken oder dauernd die eigene Lautstärke nachregeln müssen; die Entscheidung 02.138 C zum **kurzen Ducking bei erlaubten Cues** ist davon getrennt.

- **A – Keine automatische Lautheitsanpassung:** Unterschiedlich laute Audioquellen bleiben in ihrer originalen relativen Lautheit. Jeder Hörer kann über die bereits erlaubten eigenen Lautstärke-/Layerregler manuell nachjustieren.
- **B – Globale erzwungene Normalisierung:** Jede Audioquelle setzt automatisch dieselbe Lautstärke für alle Teilnehmer und übergeht persönliche Mutes, Geräteeinstellungen, Quell-/Lizenzrechte oder die bereits ausgeschlossene 02.133-A-Synchronisierungsgrenze.
- **C – Konfigurierbare nur lokale Lautheitsnormalisierung (Empfehlung):** Bei aktivem 02.132-C-Musikmodul kann die SL nach 02.25-Defaults/markierten Ausnahmen für **wirklich berechtigte** Musik-/Ambient-/Soundboard-Quellen eine *rein lokale* und sicher begrenzte Wiedergabe-Lautheitsanpassung erlauben. Ziel ist konsistentere empfundene Lautheit innerhalb zulässiger eigener Spuren, **ohne** persönliche Master-/Layer-Lautstärke, Mute oder Browserautoplay zu überschreiben. 02.138-C-Ducking bleibt als temporär zusätzlicher lokaler Faktor, 02.133 A ohne gemeinsame Musikuhr, keine externen Voicechat-/Systemaudioeingriffe und keine 02.49–02.51-Schall-/Sensor-/World-/ACK-Wirkung. Algorithmus/Metadaten/Player später.
