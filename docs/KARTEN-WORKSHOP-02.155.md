# AdventureShift – Karten-Workshop: Beschluss 02.155 C und Abschluss der Audio-Unterfragen

**Stand:** 14.10.2026. Karten-/Szenenplanung 02.1 bis **02.155**. **Status:** Verbindliche Fachplanung, keine Softwareimplementierung.
**Nächster Workshop:** **03.1 Charakterbögen**, keine weitere Audio-Unterfrage in dieser Planungsrunde.
**Neue Arbeitsweise:** [Planungsstandard](PLANUNGSSTANDARD.md) – Grundarchitektur jetzt, konkrete Parameter/UI/DSP später.

## Verbindlicher Beschluss 02.155 C

Der Projektinhaber hat ausdrücklich **C** gewählt: Bei aktiviertem 02.132-Musik-/Audio-Modul und nach wirksamer 02.25-Kampagnen-/Rollen-/Gruppen-/Personen-/Szenenpolicy sowie gültiger 02.150-Berechtigung zur **eigenen lokalen Audioeffektreduktion** kann der Hörer für seine freiwilligen FX-Änderungen entscheiden:

- **Sofort lokal:** Ein bereits unabhängig gestarteter, weiterhin wirklich berechtigter Cue übernimmt eine geänderte lokale Effektstärke zeitnah und unter begrenzten DSP-/CPU-/Gain-/Tail-Ressourcen, soweit unterstützt.
- **Ab nächstem legalen Cuestart:** Ein bereits laufender, weiterhin berechtigter Cue behält seine bisherige erlaubte Effektpräsentation. Erst ein neuer, **anderweitig tatsächlich autorisierter** Start eines passenden Cues übernimmt den neu eingestellten Effektwert. Dieser Modus startet nicht selbst neue Musik.

Beide Verhaltensweisen erfolgen **ausschließlich für den eigenen Browser-Player** und über die normalen persönlichen Einstellungen, wie mit **02.154 A** beschlossen. Ein separater InGame-FX-Schnellzugriff wird nicht wieder eingeführt.

**Nicht gewählt:** A (freiwillige Änderungen immer erst beim nächsten Start) und B (weltweite sofortige Änderung aller Hörer einschließlich Mute-/Rechteumgehung). Variante C schafft keinen gemeinsamen Audiotransport.

## Unveränderliche Architekturgrenzen

1. **Aktuelle Rechte:** Vor Audio-/Preset-/Cue-/Medien-/Asset-/Lizenz-/Szenen-/Empfängerausgabe sowie bei lokaler Anwendung gültige Rechte prüfen. Kein Zugriff auf geheime Quellen oder auf ungeschützte Raw-/Dry-Audiodaten.
2. **Rechteentzug schlägt jede Verzögerung:** Wenn Szene, Quelle, Asset, Lizenz oder Audio-Capability widerrufen wird, müssen kontrollierbare unzulässige lokale Effektjobs und alte Tails **unverzüglich nach wirksamer Widerrufsmeldung** enden. Ein gewählter „nächster Cue“-Modus darf diesen Abbruch nie aufschieben.
3. **Persönliche Hörerautonomie:** Eigenes Master-/Layer-Mute, Gain, Browserautoplay, verpflichtende 02.141-Limiter-/Peak-Sicherheit und die bereits gewählte Wiedergabe gewinnen immer. Keine automatische Cue-Erzeugung oder Entstummung.
4. **02.133 A:** Kein globaler Playhead, kein Gruppen-Seek/Pause, keine Join-/Reconnect-Musiknachholung, kein samplegenauer gemeinsamer Fade-Start.
5. **02.146–02.149:** Effektfähigkeit, geschützte Szenenprofile, eindeutiger serverautorisierter Profilgewinner und Rechteentzug bei sanften Übergängen bleiben mit eigenen Berechtigungen erhalten. Sofortiges lokales Opt-down braucht keine zusätzliche Sensor-/Worldwirkung.
6. **02.151–02.153:** Geschützte eigene Einstellungsspeicherung und optionaler Eigengeräte-Sync bleiben, letzter gültiger Save gewinnt, keine besondere History-/Undo-Funktion.
7. **Kein Weltbefehl:** Persönliche Audioeffektänderung löst keine echten 02.49–02.51-Spielwelt-Schall-/Sensor-/Nodeereignisse, 02.99-Türen-/Würfel-/Inventar-/Questaktionen oder 02.102-ACKs aus.
8. **VPS/Browser und Vorladen:** Der Server autorisiert Daten und Spielwelt, der Browser berechnet erlaubte Effekte lokal. Kein Vorladen noch geheimer späterer Szenen/Assets, nur um die „Sofort“-Option zu beschleunigen.
9. **Umsetzungsparameter später:** Exakte Fade-/DSP-Kurven, Effektparameter, Audio-Bibliothek, UI-Platzierung, Gerätebudgets und MVP erst beim tatsächlichen Entwickeln des Audio-Moduls bestimmen.

## Konzeptioneller Umsetzungsplan

1. Eine persönlich wirksame Auswahl **Sofort oder ab nächstem regulär gestarteten erlaubten Cue** als konfigurierbaren Präsentationsmodus neben 02.150 modellieren.
2. Nur gegenwärtig autorisierte Quell-/Cue-/Szenen-/Preset-/Asset-/Empfängerscopes auf dem VPS erlauben und minimal an den Browser liefern.
3. Der lokale Audio-Renderer aktualisiert bei „Sofort“ nur vorhandene erlaubte Effekte; bei „nächster Cue“ merkt er den neuen Wert bis zum nächsten **unabhängig regulär gestarteten** Cue. Kein neuer Track, kein automatischer Cue und kein geheimer Presetdownload.
4. Versionen, schnelle Änderungen, Reconnect, browserseitige Beschränkungen und Rechteentzug sicher abfangen.
5. Audio-Implementierung nach Priorisierung, nicht jetzt weiter in einzelne DSP-/Interfacefragen zerlegen.

## Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Berechtigter laufender Ambient-Cue, persönlicher Modus „Sofort“ | Nur eigener lokaler FX-Wert ändert sich ohne Cue-Neustart |
| Berechtigter laufender Cue, Modus „nächster Cue“ | Aktueller weiterhin zulässiger Effekt bleibt; erst nächster separat berechtigter Start übernimmt neuen FX-Wert |
| Es erfolgt kein neuer Cuestart | Keine künstliche Playback-Aktion |
| Anderer Spieler hört denselben Track | Sein eigener Effekt/Mute wird nicht verändert |
| Browserautoplay blockiert bzw. persönliches Mute aktiv | Kein Autostart, kein Auto-Unmute |
| Nicht mehr erlaubter Halltail bei gewähltem „nächster Cue“ | Abbruch des kontrollierbaren Alt-Tails nach wirksamer Revocation |
| 02.154 A normale Audioeinstellungen | Kein zusätzlicher FX-Schnellzugriff |
| Geheime Scene, Cue/Asset ohne Lizenz oder fremde Pref | Kein Leak und keine neue Medienberechtigung |
| DSP/Quota/CPU des Browsers unzureichend | Zulässiger sicherer Fallback statt unkontrollierter Effektschleife |
| Neue FX-Einstellung wird gespeichert | 02.151–02.153-Policy unverändert, keine gemeinsame Musikuhr |
| „Alarm“-Sound oder „Tür auf“-Effekt | Kein echtes Node-/Schallsensor-/World-/ACK-Ereignis |

## Abschluss des Audio-Unterworkshops

**02.155 C ist als Architekturentscheidung dokumentiert.** Zusätzliche Audiofeinfragen werden zurückgestellt, nicht als implizit beschlossen oder implementiert ausgegeben. Die Audiofähigkeit bleibt optional und auf eine spätere Projektphase verschiebbar.

**Nächste strukturelle Entscheidung 03.1 – Charakterbogen-Vorlagendatenmodell:**

- **A – Feste Regelwerk-Charakterbögen:** Charakterfeldstrukturen sind im Programm fest vorgegeben; für weitere Systeme ist neue Implementierung nötig.
- **B – Vollständiger Freitextbogen:** Alles als unstrukturierter Text, keine zuverlässig typisierten Würfel-, Ressourcen-, Regel- oder Inventarverknüpfungen.
- **C – Typisierte, versionierbare, regelwerksneutrale Charaktervorlagen (Empfehlung):** Vorlage/Instanz getrennt, dynamische definierte Feldtypen, stabile Feldreferenzen, geschützte Bearbeitungsrechte und spätere optionale Regel-/Würfel-/Inventarverknüpfungen. Konkrete Feldanzahlen und grafisches Blattlayout später.
