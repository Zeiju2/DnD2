# AdventureShift – Karten-Workshop: Beschluss 02.149 C – sichere lokale Hall-/Echo-Profilübergänge

**Stand:** 14.10.2026. Fachbeschlüsse Inventar 01.1–01.16, Karten/Szenen 02.1–02.149. **Nächste offene Frage 02.150**.
**Status:** Verbindliche Fachplanung mit Umsetzungsentwurf und Abnahmetests, **keine Softwareimplementierung**; konkrete DSP-/Audio-/Codec-Bibliothek, API/DB, UI, Werte für Fade-/Tail-/CPU-Budgets und MVP noch offen.
**Bezüge:** [02.25 – Kampagnen-Defaults/markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.49–02.51 – echte Schall-/Sensor-/Nodewelt](KARTEN-WORKSHOP.md) · [02.99 Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.102 amtliche ACKs](KARTEN-WORKSHOP-02.102.md) · [02.105 optionaler Chat](KARTEN-WORKSHOP-02.105.md) · [02.132 C Musik/Playlists/Soundboard](KARTEN-WORKSHOP-02.132.md) · [02.133 A – lokale Wiedergabe ohne gemeinsame Audiozeit](KARTEN-WORKSHOP-02.133.md) · [02.134 C – Fades/Layers/Loops](KARTEN-WORKSHOP-02.134.md) · [02.135–02.136 C Audio-Vorlagen/Updates](KARTEN-WORKSHOP-02.136.md) · [02.137 A keine Audio-Insertparameter](KARTEN-WORKSHOP-02.137.md) · [02.138 C Ducking](KARTEN-WORKSHOP-02.138.md) · [02.139 A keine zusätzlichen Audio-Captions](KARTEN-WORKSHOP-02.139.md) · [02.140 A kein Editor-Vorhörplayer](KARTEN-WORKSHOP-02.140.md) · [02.141 C Loudness](KARTEN-WORKSHOP-02.141.md) · [02.142–02.145 C räumliche Audiopräsentation](KARTEN-WORKSHOP-02.145.md) · [02.146 C – lokaler Hall/Echo](KARTEN-WORKSHOP-02.146.md) · [02.147 C – geschützte Szenenprofile](KARTEN-WORKSHOP-02.147.md) · [02.148 C – sichere Profilpriorität](KARTEN-WORKSHOP-02.148.md) · [VPS/Browser-Vorladen](SITZUNGS-VORLADEN-CACHE.md).

## 1. Verbindliche Entscheidung – 02.149 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Die SL kann bei aktivierter **02.132-C-Musik-/Ambient-/Soundboardfähigkeit**, separat erlaubter **02.146-C-Hall-/Echo-Fähigkeit** und wirksamer **02.147-C-Szenenprofilfunktion** nach **02.25-Kampagnen-/Rollen-/Gruppen-/Szenen-/Personen-Defaults und gültigen markierten Ausnahmen** einen von **02.148 C** eindeutig autorisierten Profilwechsel im jeweiligen Hörerbrowser **sofort** oder **sanft und streng ressourcenbegrenzt** durchführen lassen. Eine sanfte Überblendung zwischen zwei lokalen Hall-/Echoeffektzuständen ist ausschließlich erlaubt, solange **beide** zugrundeliegenden Szenen-/Profil-/Cue-/Medien-/Lizenz-/Empfängerrechte während dieser Phase tatsächlich bestehen. **Wird eine Berechtigung entzogen, muss der betroffene Effekt mit kontrollierbaren Tails umgehend nach wirksamem Widerruf gestoppt werden**, selbst wenn das hörbar abrupt ist.

**Beispiel:** Die Spielergruppe wechselt von einer freigegebenen Höhle in eine freigegebene kleine Kammer. Beide rechtmäßig gehörten Klangcharaktere sind für den konkreten Hörer im Übergang erlaubt: sein eigener Browser kann den alten Hall kurz aus- und den neuen einblenden. Falls die bisherige Höhlenszene sofort ihre Audioberechtigung verliert, wird deren Hall **nicht** für einen komfortablen Übergang fortgesetzt. Die Musik selbst wird deswegen weder neugestartet noch gruppenweit synchronisiert.

**Nicht gewählt:** A – immer nur sofortiger harter Profilwechsel; B – erzwungene global synchronisierte Überblendung einschließlich inzwischen verbotener Hall-/Echo-Tails. **C betrifft nur lokale Darstellung**, keine globale Musikuhr, keine echten SoundEvents/Nodeaktionen und keine zusätzliche Szenenfreigabe.

## 2. Verbindliche Grenzen und Konfiguration

1. **Getrennt schaltbar:** Wirksame 02.132-Musik-, 02.146-Hall-, 02.147-Szenenprofilrechte sind Voraussetzung. 02.148 bestimmt den aktuell autorisierten Gewinner. Eigene 02.149-Übergangsoption „Sofort“ oder „Sanft“, jeweils nur bei gültiger 02.25-Policy und Ausnahmen. Der spätere Gesamtkampagnen-Assistent wird **erst nach dem Featureworkshop** ausgestaltet.
2. **Genau ein policywirksames Profil:** 02.148 wählt je Hörer-/Scene-/Cue-Scope **ein** aktuelles Profil oder sicheres neutrales Ergebnis. Zwei kurzzeitige lokale DSP-Zweige während eines erlaubten Übergangs erzeugen **kein** zweites policywirksames Gewinnerprofil und gewähren kein beliebiges Profilmischen.
3. **Sofortiger Wechsel:** Bei gültiger Auswahl und entsprechend wirksamer Einstellung endet die alte lokale Reverb-/Echo-Konfiguration und die neue rechtmäßige wird unmittelbar benutzt; der eventuell bereits erlaubte Grundtrack muss nicht neu starten.
4. **Sanfter Wechsel:** Nur wenn **alter und neuer Zustand fortdauernd** nach Kampagne/Rolle/Gruppe/Person/Szene/Fog/SourceCue/Preset/Asset/Lizenz/Empfänger zulässig sind und Ressourcen reichen, ist ein kurzer gerätelokaler Fade der reinen Hall-/Echo-Wirkung erlaubt. Noch keine verbindlichen DSP-/Wet-/Dry-/Fade-Formeln oder Sekundenwerte.
5. **Widerruf hat Vorrang:** Alte Quellen/Presets/Tails mit inzwischen abgelaufenen Rechten nicht für Klangkomfort künstlich weiterleben lassen. Aktuell bereits hörbare frühere Schallwellen können nicht rückwirkend aus dem Gedächtnis gelöscht werden. Asynchron eintreffende Rechteänderungen sollen schnellstmöglich zu kontrolliertem Abbruch führen; Netzwerkzustellung ist nicht garantiert verzögerungsfrei.
6. **Nur vorhandene berechtigte Cues:** Profilwechsel selbst erzeugt **keinen** neuen Track, Soundboard-Cue, Musikstart oder Playback-Seek. Er manipuliert ausschließlich die auf schon für den Hörer zulässige Cues angewandte Effektpräsentation und benötigt weiterhin Browser-Autoplay-/Nutzerfreigabe.
7. **Persönlicher Mute/Gain und Browser gehen vor:** Alle alten/neuen Effektzweige und Echo-Tails respektieren aktuelle eigene Master-/Layer-Stummschaltung und Lautstärke; kein automatisches Entmuten, kein globaler Gain und kein Mikrofon-/externes Voicechat-/OS-Audio.
8. **02.133 A unverändert:** Kein Session-Playhead, keine gemeinsame Crossfade-Uhr, kein erzwungener identischer Start-/Pause-/Seek-Zeitpunkt, kein historischer Join-/Reconnect-Musikeinstieg. Zwei Spieler können dasselbe erlaubte Effektprofil zeitversetzt und unterschiedlich hören.
9. **Audio-Subsysteme getrennt:** 02.134 lokale Musik-Layers/Fades/Loops und 02.138 eigenes Ducking werden durch 02.149 nicht ungeprüft doppelt gestartet; 02.141 Loudness, Peak/Clipping, 02.142–02.145 Spatial-/Follow-/Distanz-/Dopplerrechte bleiben eigenständig. Abstrakter Hall erfordert keine zusätzlichen geheimen Raum-/Positions-/Geschwindigkeitsdaten.
10. **Audioeffektressourcen begrenzen:** Maximaldauer, maximale parallele zulässige Übergangspfade, Echo-/Hall-Feedback, Tail-Länge, Lautstärke/Peak, CPU, Speicher, Decoderanzahl und Realtime-Rate nach Messung hart begrenzen. Kein unendliches Echo-Feedback und kein unkontrolliertes erneutes Ducking durch Tail-/Fadeereignisse.
11. **Rechte vor allen Daten:** Der VPS prüft effektive 02.25-/02.132-/02.146-/02.147-/02.148-/02.149-Capabilities sowie Scene-/Fog-/Role-/Group-/Person-/Cue-/Preset-/Media-/License-/Recipient-ACL **vor neuer Projektion, Übergang, Realtime-Anweisung, neuen URLs und Downloads**. Der Browser erhält minimal benötigte Werte, keine konkurrierenden, geheimen oder künftigen Profilkataloge.
12. **Geheimnis-/Metadatenschutz:** Nicht erlaubte Szenen, Wände, Raumarten, NPC-Positionen, Cue-/Presetnamen, URLs, alte Verliererprofile, Counts, Timestamps, Echo-Tail-Dauer, Download-Warteschlange und Fehlermeldungen dürfen keine unberechtigten Informationen verraten. Ein hörbarer Effekt kann bereits Geheimwissen sein.
13. **Version und Race-Guards:** Szene/Profil/Asset-/Lizenz-/Rollenscope/Playerstate/Transitionpolicy revisionieren; verspätete/doppelte/gefälschte manuelle oder SceneSwitch-Events nicht als gültigen neuen Fade ausführen. Bei A→B→C-Schnellwechseln alte kontrollierbare Jobs aufräumen und zum **neuesten heute berechtigten Ergebnis** konvergieren, ohne eine große Effektkette wachsen zu lassen.
14. **Reconnect/Offline:** Bei Join/Reconnect keine vergangene Fade-Sequenz nachholen und keinen Track selbstständig abspielen; nur aktuelle Freigabe/Profil/Playerzustand beachten. Browsercache ist keine eigenmächtige NPC-/Node-/Würfel-/Welt-Autorität während VPS-Störung.
15. **Vorladen und Fallback:** Für beide Übergangseffekte ausschließlich **heute erlaubte** Musik-/Preset-/Lizenz-Assets vorbereiten; niemals heimlich geheime spätere Karten/Scenes oder Profile nur wegen Crossfade-Komfort übertragen. Bei fehlender Engine, Asset-, Quota- oder Codecfähigkeit rechtmäßiger direkter Wechsel, neutral/dry Ton oder kontrollierter Abbruch.
16. **Vorlagen/UI-Ausschlüsse bleiben:** 02.135/02.136-C-Quell-/Lizenz-/Vorlagenrechte, 02.137 A ohne Insertparameterdialog, 02.139 A ohne besondere Audio-Cue-Captions und 02.140 A ohne privaten Editorpreviewplayer gelten weiter.
17. **Keine Spielweltwirkung:** Hallübergänge und Effekt-Tails sind **keine** 02.49–02.51-Schall-/NPC-Hör-/Schallsensor-/Bewegungsmelder-/Alarm-/Licht-/Nodewelt, keine 02.99-Quest-/Door-/NPC-/Turn-/Würfel-/Inventaränderung und keine 02.102-Kenntnisnahme.
18. **Noch offen:** DSP-Kurven, Ressourcen- und Zeitlimits, API/DB, UI/MVP und optionale persönliche Effect-Intensity-/Reduction-Settings werden nicht still als implementiert ausgegeben; letzter Punkt wird **02.150**.

## 3. Konzeptionelle Architektur

**Arbeitsbegriffe – keine realen Schemata oder Endpunkte:** LocalSceneAudioTransitionPolicy, AuthorizedProfileTransitionProjection, SceneProfileTransitionRevision, BoundedLocalReverbCrossfade, LocalAudioTransitionAbortToken, AudioTransitionBudget.

1. **Autoritativer Ausgangszustand:** 02.148 C berechnet pro Hörer/Scene/Cue einen aktuell erlaubten neuen Gewinner (oder neutral/dry), 02.149 prüft danach separat wirksamen Sofort-/Sanftmodus und **beiderseitige** alte/neue Rechte für jede zulässige Übergangsphase.
2. **Minimale Projektion:** VPS sendet nur die für aktuellen Empfänger nötige versionierte rechtmäßige Profil-/Transition-Anweisung; keine SL-Geometrien, konkurrierenden oder geheimen Kandidatenlisten. Mediensuche und Browser-Vorladen prüfen dieselben heutigen Rechte.
3. **Gerätelokaler Effektpfad:** Rechtmäßig gestarteter Cue → separater erlaubter Mix/Source → nur berechtigte 02.146-Alt-/Neu-Reverb-/Echoeffekte mit höchstens zeitlich begrenztem 02.149-Übergang → persönlich kontrollierter Master-/Layer-Mute, Lautheits-/Peak-/CPU-Schutz. Endgültige DSP-Reihenfolge ist noch zu evaluieren.
4. **Schneller Widerruf:** Bei wirksamem Rechteentzug betroffenen alten Zweig/Tail vollständig aus dem steuerbaren lokalen Mix entfernen und künftige Streams/Caches entwerten. Unberechtigte alte Tails dürfen auch nicht wegen CPU-/Netzwerk- oder Fadekomfort weiterlaufen.
5. **Event-Lifecycle:** SceneSwitch-/Manual-/Policy-Revisions, Retry/Duplicate/OutOfOrder, Logout/Login, Splitgruppen, Browser-Refresh, Tab-Suspend, Reconnect und VPS-Neustart idempotent und bounded behandeln. Keine globale 02.133-Uhr, kein Audio-Backfill.
6. **NoWorld-Schranke:** Crossfade ist kein neuer fachlicher Cue, kein wiederholtes Game-SoundEvent, kein Door-/Quest-/NPC-/Würfel-/ACK-Ereignis und kein Mikrofon-/Fremdvoice-Transform.

## 4. Konzeptioneller Umsetzungsplan

1. Eigene 02.149-Fähigkeit/Policy mit zulässigen Modi „Sofort“ und „Sanft“ nach 02.25-Defaults/Ausnahmen, bei echter Aktivierung von 02.132/146/147 und gültigem 02.148-Gewinner.
2. Serverseitigen aktuellen Übergangsresolver für alten und neuen Scene-/Preset-/Cue-/Asset-/Lizenz-/Recipient-Scope spezifizieren; geheimer/entzogener Altzustand darf kein erlaubtes Crossfadeziel werden.
3. Revisionsgebundene minimale Realtime-Anweisung und idempotentes Abbrechen bei Race/Replay/Reconnect; SL-/Player-Rechte und persönliche Mute-/Autoplayregeln separat prüfen.
4. Bounded lokalen 02.146-DSP-Reverb-/Echo-Übergang mit Schutz gegen mehrfache parallele Tails, Feedback, CPU/Gain/Clipping/RAM; direktes Umschalten bzw. zulässigen neutralen Fallback unterstützen.
5. Szenenwechsel, Gruppen-/Rollenwechsel, Rights-Loss, AudioAus, Mute, Assetrevocation, sehr schnelle A→B→C-Änderungen, späte Joiner, Browser-/Mobil-Fallback, SecretCache und NoWorld/NoACK intensiv testen.
6. Nach Abschluss aller Featurebereiche API/DB, DSP, UI/UX, Testzahlen, Browserplattformen und MVP-Priorität festlegen. Persönliche Effektoptionen in 02.150 gesondert entscheiden.

## 5. Fachliche Abnahmetests

| Szenario | Erwartung |
| --- | --- |
| 02.132 Musik Aus / 02.146 Hall Aus / 02.147 Szeneprofil Aus | Kein eigenständiger 02.149-Fade oder neue Audioberechtigung |
| 02.148 liefert kein autorisiertes Profil | Sicheres neutral/dry Verhalten statt geheimem Wechsel |
| Sofort-Modus mit zwei gültigen Profilen | Direkte lokale Änderung ohne speziellen Fade |
| Sanft-Modus mit zwei fortdauernd gültigen Profilen | Kurzer begrenzter lokaler Hall-/Echo-Übergang |
| Altes Preset wird beim SceneSwitch verboten | Kontrollierbare Alt-Tails abbrechen, selbst wenn der Cut hart klingt |
| Neues Preset/Quelle/Lizenz nicht erlaubt | Kein neuer unberechtigter Medientransfer oder Audioeffekt |
| Gruppen A und B erhalten verschiedene Scopes | Nur jeweils autorisierte lokale Profile, keine fremden Szenennamen |
| Zwei Spieler spielen Musik zeitversetzt | Kein synchroner Fadestart oder globaler Playhead |
| Browser blockiert Autoplay | Fade startet keinen neuen Track |
| Mastermute mitten im Fade | Alter und neuer Effektzweig bleiben stumm |
| Player ändert persönlichen Gain mitten im Echo | Keine fremde Gain-Rücksetzung oder Auto-Unmute |
| Audio-Aus/Scene-/Preset-/Medienrecht entzogen | Kontrollierbare Jobs sofort nach wirksamer Revocation beenden |
| A→B→C in kurzer Folge | Nur aktuelle zulässige Revision, begrenzte CPU-/Tail-/Jobanzahl |
| Replay/OutOfOrder/dupliziertes SceneSwitch | Kein alter Audiojob, keine Track-Wiederholung |
| Late Join oder Reconnect während Transition | Kein historischer Fade-/Cue-Catch-up |
| SL-Editor öffnet versteckte Höhle | Keine verborgenen Profile oder Audio-/Asset-Metadaten |
| Preset wird nur für Crossfade-Vorladen angefordert | Kein Zugriff, solange es für den Empfänger noch geheim ist |
| Browser-Engine fehlt/Cache voll/Codec fehlt | Sicherer direkter Wechsel, legaler trockener Ton oder Abbruch |
| Hohe CPU/Peak/Echo-Feedbacklast | Budget/Peak-/Tail-Grenzen wirken, kein unendlicher Effekt |
| 02.134 Layers, 02.138 Ducking, 02.141 Loudness aktiv | Kein doppelter fachlicher Cue, kein unnötiges Ducking oder Clipping |
| 02.142–02.145 Spatial aus | Kein geheimes Richtungs-/Distance-/Velocity-Leak durch Fade |
| Zwei Kampagnen mit gleichen Presetnamen | Keine fremden Audio-/Medienrechte |
| Externer Voicechat läuft | Keine Mikrofon-/OS-/Fremdapp-Reverbwirkung |
| Audioeffekt heißt „Alarm“ | Kein Sensor-/NPC-/Node-/Schall-Weltevent |
| Audioeffekt heißt „Tür öffnen“ | Kein echter Tür-/Quest-/Würfel-/Turn-/Inventar-Commit |
| 02.102 amtliches ACK verlangt | Fade/Hören ist keine Quittierung |
| 02.137/139/140-Ausschlüsse | Kein Insertparameterdialog, Cue-Captionfeed oder Sondervorhörplayer |

## 6. Beschlussgrenze und nächste Frage

**02.149 C verbindlich:** Konfigurierbare lokale Sofort- oder begrenzte sanfte Hall-/Echo-Profilübergänge bei aktuell gültigem 02.148-Gewinner und nur bei fortdauernder beidseitiger Berechtigung; Widerruf stoppt steuerbare Alt-Tails ohne garantierte nachträgliche Löschung bereits gehörter Signale. Kein neuer Track, keine 02.133-A-Globaluhr, kein Mute-/Autoplay-Bypass, keine geheime Prefetch-Freigabe, keine 02.49–02.51-Welt-/Sensor-/Node-, 02.99-World- oder 02.102-ACK-Wirkung.

**Nicht beschlossen:** finale DSP-Kurve, Crossfade-Dauer, Preset-/CPU-Budgets, UI/API/DB/Codec, MVP und persönliche Intensitätsregler. Fachplanung, keine lauffähige Software.

## Nächste Entscheidung 02.150 – Persönliche Reduzierung oder Abschaltung reiner Audioeffekte

**Beispiel:** Die Spielleitung aktiviert in einer Höhle berechtigten Hall und bei Szenenwechsel kurze Effekte. Ein Spieler möchte die Musik weiterhin hören, die lokale Hall-/Spatial-/Echoverarbeitung aber wegen Kopfhörern, persönlicher Vorliebe oder Geräteleistung reduzieren oder abschalten, ohne die Weltaktionen oder andere Spieler zu beeinflussen.

- **A – Keine gesonderten persönlichen Effektoptionen:** Der Hörer behält nur die bereits geplanten persönlichen Mute-/Lautstärkeregelungen, aber keinen eigenen Effekte-reduzieren/aus-Modus.
- **B – Gleiche Effektintensität für alle erzwingen:** SL oder andere Teilnehmer können die volle Effektverarbeitung ungeachtet der eigenen Stummschaltung, Browserfähigkeit und Ressourcen auch auf fremden Geräten erzwingen.
- **C – Geschützte persönliche lokale Effektreduktion (Empfehlung):** Berechtigte Hörer dürfen rein präsentative Hall-/Echo-/gegebenenfalls Spatial-/Übergangseffekte lokal abschwächen oder abschalten, ohne den ohnehin erlaubten Grund-Cue/Track oder andere Hörer zu beeinflussen. Keine zusätzlichen Cue-/Preset-/Scene-/Asset-/Lizenzrechte; echter 02.49–02.51-Spielszenenschall/Sensor-/Node-/Weltzustand bleibt unabhängig. Genaues UI, Einzeleffektregler, Speicher- und Defaultverhalten später.
