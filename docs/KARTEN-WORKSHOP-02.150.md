# AdventureShift – Karten-Workshop: Beschluss 02.150 C – persönliche Reduzierung und Abschaltung rein lokaler Audioeffekte

**Stand:** 14.10.2026. Fachlich entschieden: Inventar 01.1–01.16 sowie Karten/Szenen 02.1–02.150. **Nächste offene Frage 02.151**.
**Status:** Verbindliche Fachplanung mit Umsetzungsentwurf und Abnahmetests, **noch keine Softwareimplementierung**, keine finalen UI-/API-/DB-/DSP-Verträge, Persistenzregel, Standardregler oder MVP-Einstufung.
**Bezüge:** [02.25 – Kampagnenstandards, Ausnahmen und Änderungsvorschau](KARTEN-WORKSHOP.md) · [02.49–02.51 – echte Schall-/Sensor-/Nodewelt](KARTEN-WORKSHOP.md) · [02.99 – echte autorisierte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.102 – amtliche ACKs](KARTEN-WORKSHOP-02.102.md) · [02.105 – optionaler Chat](KARTEN-WORKSHOP-02.105.md) · [02.132 C – optionales Musik-/Playlist-/Soundboardmodul](KARTEN-WORKSHOP-02.132.md) · [02.133 A – unabhängige lokale Wiedergabe](KARTEN-WORKSHOP-02.133.md) · [02.134 C – lokale Layer/Fades/Loops](KARTEN-WORKSHOP-02.134.md) · [02.135–02.136 C – geschützte Audio-Vorlagen](KARTEN-WORKSHOP-02.136.md) · [02.137 A – keine besonderen Insertparameter](KARTEN-WORKSHOP-02.137.md) · [02.138 C – lokales Ducking](KARTEN-WORKSHOP-02.138.md) · [02.139 A – keine Cue-Captions](KARTEN-WORKSHOP-02.139.md) · [02.140 A – kein privater Editor-Audio-Previewplayer](KARTEN-WORKSHOP-02.140.md) · [02.141 C – Loudness](KARTEN-WORKSHOP-02.141.md) · [02.142–02.145 C – berechtigte räumliche Audioeffekte](KARTEN-WORKSHOP-02.145.md) · [02.146 C – lokaler Hall/Echo](KARTEN-WORKSHOP-02.146.md) · [02.147 C – Szenenprofile](KARTEN-WORKSHOP-02.147.md) · [02.148 C – Profilprioritäten](KARTEN-WORKSHOP-02.148.md) · [02.149 C – sichere lokale Profilübergänge](KARTEN-WORKSHOP-02.149.md) · [VPS und geschütztes Browser-Vorladen](SITZUNGS-VORLADEN-CACHE.md).

## 1. Verbindliche Entscheidung – Variante 02.150 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Bei wirksam aktiviertem 02.132-C-Musik-/Soundboardmodul darf jeder **aktuell audio- und empfängerberechtigte Hörer** rein präsentative gerätelokale Effekte wie **Hall/Echo (02.146), zulässig vorhandene räumliche Darstellung (02.142–02.145) sowie erlaubte lokale Szenenprofilübergänge (02.149)** für seine **eigene** Wiedergabe nach wirksamer 02.25-Konfiguration **reduzieren oder abschalten**, ohne dadurch berechtigte Grundmusik-/Soundboard-Cues als solche stummzuschalten, die SL-/Szenenkonfiguration anderer zu ändern oder zusätzliche Cue-/Preset-/Positions-/Szenen-/Asset-/Lizenzrechte zu erwerben. Der bisherige persönliche Master-Mute/Lautstärkeregler bleibt unabhängig und vorrangig.

**Beispiel:** Die SL hat einer bereits zulässigen Höhlenszene ein erlaubtes abstraktes Hallprofil zugewiesen. Spieler A mag den Ambienttrack, aber nicht den Nachhall: A wählt lokal „Effekte aus“ oder eine reduzierte Intensität. Sein Browser spielt – sofern diese unverarbeitete Grundwiedergabe selbst zulässig ist – denselben erlaubten Track ohne zusätzlichen Hall. Spieler B hört den gewohnten Hall. Es verändert weder die tatsächlich serverautoritativ entschiedene Schall-/NPC-/Sensorwelt noch die Szene oder die Einstellungen der SL.

**Nicht gewählt:** A (keine persönlichen Effektoptionen zusätzlich zu Lautstärke/Mute) und B (andere Teilnehmer oder SL erzwingen auf jedem Endgerät unabhängig von Mute, Geräteleistung oder Userentscheidung identische Effektdarstellung). **C betrifft nur zulässige lokale Darstellung** und garantiert nicht, dass sich jede beliebige sicherheits-, lizenz- oder spielweltrelevante Verarbeitung deaktivieren lässt.

## 2. Berechtigungen, Konfiguration und Grenzen

1. **Wirksame Fähigkeit:** 02.132 Musik An und aktuell gültige berechtigte Quell-/Cue-/Asset-/Lizenz-/Empfängerrechte bleiben Voraussetzung. Für einen Effekt sind zusätzlich seine eigenen 02.146-/02.142–02.145-/02.149-Berechtigungen erforderlich. Persönliches Effekte-Aus darf ein deaktiviertes Modul **nicht wieder anschalten**. Die SL kann im Rahmen tatsächlich implementierter 02.25-Funktionen geeignete präsentative Unterfähigkeiten erlauben/deaktivieren; **lokale Reduzierung erhöht niemals effektive Rechte**.
2. **Eigene lokale Präferenz:** Ein Hörer kann, soweit unterstützt, zusätzliche rein lokale Hall-/Echo-, optionale Spatial-/Distanz-/Doppler- und Szenenprofil-Übergangsdarstellung **bis auf neutral/aus reduzieren**. Die endgültige Wahl zwischen Gesamtschalter, wenigen Presets und getrennten Reglern sowie konkrete Skalen bleiben für UI/MVP offen. Kein heimliches globales Abschalten von anderen Cues.
3. **Grund-Cue bleibt selbstständig:** Effektintensität und persönlicher Master-/Layer-Mute sind unterschiedlich. Effekt-Aus darf den separat erlaubten trockenen/neutralen Grund-Cue weiterhin spielen, **soweit dessen unveränderte Wiedergabe ebenfalls freigegeben und sicher ist**. Es gibt kein Recht, absichtlich gefilterte, geschützte, redigierte oder lizenzbedingt nur verarbeitete Inhalte im Original hörbar zu machen. Ist eine trockene Form nicht zulässig, gelten kontrollierter Stop/Fallback statt ungeschütztem Dry-Bypass.
4. **Spielleiter- und Mitspielerzustand unverändert:** Persönliche Auswahl verändert keine gespeicherte Szenenbindung, kein 02.148-Gewinnerprofil, keine SL-/Gruppenpräferenz und kein anderes Gerät/anderen Teilnehmer. Ein Player kann nach persönlichem Effekt-Aus weiter denselben von 02.148 rechtmäßig bestimmten Profilwinner als **bloße autorisierte Referenz** haben, ohne ihn akustisch darstellen zu müssen.
5. **Echte Welt nicht veränderbar:** 02.49–02.51 echte SoundEvents, Hindernisse, Hörreichweiten, NPCs, Schall-/Präsenz-/Bewegungsmelder, Alarme, Nodes, Türen und Licht folgen weiter ausschließlich autorisierten Spielweltregeln. Lokale Effektreduktion verändert keinen 02.99-World-/Quest-/Turn-/Würfel-/Inventarcommit, keine 02.102-ACK oder tatsächliche Sicht/Fog/Entdeckung.
6. **Persönlicher Mute und Browser gewinnen:** Kein automatisches Entmuten oder fremder Gain; bestehende 02.132/02.133-A-Musik- und persönliche Volume-/Autoplayregeln behalten Vorrang. Audio-Effektverzicht startet **keinen** Track automatisch, erzwingt kein Reconnect-Catch-up, keine gemeinsame Transportuhr und verändert weder OS- noch Voicechat-/Mikrofon-Audio anderer Apps.
7. **Getrennte Präsentationskomponenten:** Effekt-Aus reduziert nur tatsächlich als optionales Präsentationsfeature implementierte Audio-Postprocessing-Anteile. Nicht entfernt werden verpflichtende Lautheits-/Peak-/Clippingbegrenzung nach 02.141, technische Wiedergabesicherheit, Zugriffskontrolle, notwendige Lizenz-/Schutz-Filter oder reale Serverphysik. 02.134 C Musik-/Soundboard-Layer oder 02.138 C Ducking sind nicht pauschal bereits von „Effekte aus“ umfasst: ihre genaue persönliche Steuerbarkeit erfordert gesondert ausdrücklich erlaubte Implementierung und darf bestehende Beschlüsse nicht brechen.
8. **Positionale Effekte sicher reduzieren:** Wenn 02.142–02.145 separat berechtigte Richtungs-/Distanz-/Bewegungsinformationen verwendet werden dürfen, kann deren lokaler Präsentationsanteil reduziert werden, ohne dem Browser **neue** Koordinaten, Entfernungen, Geschwindigkeiten oder versteckte Quellen offenzulegen. Falls neutraler Mix/Mono-/Stereo-Fallback weitere Geheimnisse hörbar machen könnte, nur autorisierten Ersatz oder kontrollierten Abbruch verwenden.
9. **Hall/Echo und Übergänge:** Bei persönlicher Hallreduzierung müssen vorhandene lokale Hall-/Echo-Tails kontrolliert leiser oder aus werden; 02.149-Sanft-/Sofort-Profile wechseln nur noch im effektiven selbstgewählten Darstellungsumfang. Eine 02.149-Szene-/Preset-/Lizenzwiderrufsschaltung stoppt **trotz** lokal gewählter Restdauer alle inzwischen unzulässigen kontrollierbaren Tails.
10. **Aktuelle Rechte vor Datenlieferung:** VPS und Browser-Anweisungen prüfen weiter aktuelle Kampagnen-/Actor-/Rollen-/Gruppen-/Personen-/Szenen-/Fog-/Cue-/Preset-/Asset-/Lizenz-/Recipientrechte, auch wenn der Nutzer Effekte reduziert. Preference/„Effekte an“ allein veranlasst niemals Abruf bisher geheimer Presets/Assets und erteilt keine Audiofreigabe; Änderungen werden bei Revocation und Reconnect neu validiert.
11. **Privatsphäre der Präferenzen:** Persönliche Regler werden nicht als Gruppen-/Chat-/SL-Nachrichten veröffentlicht und müssen grundsätzlich keine privaten Gründe enthalten. Nur soweit technisch für Capability-/Rechte-/Fehlerbehandlung erforderlich minimale Statusdaten; andere Hörer sollen nicht erkennen können, wer Hall/Spatial abgeschaltet hat. Speicherung oder Synchronisation dieser privaten Preferences ist **noch nicht entschieden** und wird 02.151.
12. **Performance und Fallback:** Geräteschwache Browser können präsentative Effekte unter sicheren Quoten, optional automatisch abgeschalteten nicht essenziellen DSP-Pfaden und beschränkter Audioqualität reduzieren; dies ersetzt nicht die gewollte Nutzerentscheidung oder schaltet sicherheitskritische Verarbeitungen ab. Alte Jobs/Tails bei Effekt-Aus bereinigen; CPU-/RAM-/Decoder-/Gain-/Feedback-/Peak-Budgets bleiben.
13. **Sitzungsvorladen bleibt geschützt:** Audio-/Preset-Dateien nur für aktuell wirklich erlaubte, rechtmäßig lizenzierte und nach Größe/Bandbreite sinnvolle Assets bereitstellen. Wenn der Hörer präsentative Effekte deaktiviert hat, darf dies die optionale Vorladepriorität reduzieren, aber keine geheimen künftigen Szenen-/Profilmetadaten oder Cross-Campaign-Quellen offenlegen; keine Offline-Welt-Autorität.
14. **Unveränderte Negativbeschlüsse:** 02.137 A (keine Audio-Insertparameter), 02.139 A (keine besonderen Cue-Captions), 02.140 A (kein privater Editor-Sonderpreviewplayer), 02.133 A (keine gemeinsame Musikuhr), 02.116 A keine persönlichen Chat-Read-Receipts und 02.122 A keine Voice-Memos bleiben unberührt.
15. **Keine heimliche neue Regellogik:** Ein Spieler kann lokal auf Effekte verzichten, aber keine SL-Ausnahmen, NPC-Reaktionen, Sicht-/Schallregeln, tatsächliche Würfelergebnisse oder Notiz-/Chatrechte verändern. Policy-/ACL-Revisions, Reconnect- und Mehrbrowserkonsistenz sind technisch zu prüfen.

## 3. Konzeptionelles Architektur- und Lebenszyklusmodell

**Nur Arbeitsnamen, keine finalen DB-Felder oder APIs:** PersonalLocalAudioEffectsPreference, AuthorizedAudioEffectsCapabilityProjection, LocalPresentationEffectGain, LocalSpatialPresentationFallback, LocalAudioEffectsCleanupToken, EffectiveAuthorizedCueAudioGraph.

1. **Serverautorität erhalten:** VPS ermittelt nach realer Kampagnen-/Szenen-/Audio-/Preset-/Asset-/Lizenz-/Empfängerpolicy den zulässigen Cue und die optional erlaubten präsentativen Verarbeitungsschritte. Keine Übertragung privater SL- oder Fremdhörerdaten zum Zweck einer lokalen Effektentscheidung.
2. **Separater lokaler Präferenz-Layer:** Ein Player wählt für **sein eigenes Gerät** die zulässige Stärke oder das Abschalten einzelner optionaler Präsentationseffekte. Das wirkt erst **nach** serverautorisierter Cue-/Quell-/Medien-/Profilprojektion und kann diese nicht erweitern.
3. **Audio-Graph:** Rechtmäßig hörbare Quelle → erforderliche unveränderliche Lizenz-/Sicherheits-/Gain-/Limiterverarbeitung → nur aktuell erlaubte optionale Audio- und räumliche Effektpfade → vom Hörer reduzierte Präsentation → aktueller eigener Master-/Layer-Mute. Die endgültige Signalreihenfolge/Codec-/DSP-Implementierung bleibt offen und muss sicherheitsgerecht getestet werden.
4. **Widerruf/SceneSwitch:** 02.147/02.148-Profile und 02.149-Sofort-/Sanftwechsel bleiben serverberechtigt. Der Browser darf für sich optional Effektstärke herabsetzen, nie einen widerrufenen Alt-Halltail „trotzdem zum Ausklingen“ fortsetzen. Versionierung und Cancellation bei Änderungen, Doppelereignissen, Netzwerkproblemen und 02.132-/02.146-/02.142–02.145-Aus.
5. **Geräte und Kosten:** Browserunterstützung, Kopfhörer, Monoausgabe, schwache CPUs/RAM, mobiles Gerät, Cachequota, Tab-Suspend und Browser-Autoplay berücksichtigen. Lokaler FX-Aus-Fallback darf die abgesicherten Grund-Cues nicht unnötig deaktivieren, darf aber niemals geschützte unbearbeitete Inhalte freigeben.
6. **Grenze der Persistenz:** Ob ein Hörer seine Präferenz nur bis zum Tabende, kampagnenweit oder pro Gerät/Geräteverbund gespeichert erhält, ist **02.151**. Bis dahin keine feste Sync-/Cross-Device-/Cross-Campaign-Regel beschließen.
7. **Keine neuen Ereignisse:** Effektstärke, Bypass und Cleanup sind kein echter SoundEvent, Sensor-/Node-Input, neuer Cue/Playliststart, Würfel-/Door-/Quest-Commit, ACK oder Chatnachricht.

## 4. Konzeptioneller Umsetzungsplan

1. **Capability/Policy:** Trennung zwischen autorisiertem Cue-/Profil-/Medienzugriff und 02.150 rein lokalem Opt-down-Modus nach 02.25/02.132/02.146/02.142–02.149 entwerfen; verpflichtende Schutz-/Limiterpfade können nicht durch User-Preference abgeschaltet werden.
2. **Persönlicher Präsentationslayer:** Schlichte verständliche Bedienelemente für optionales Hall/Echo reduzieren/aus und nur soweit umgesetzt für Spatial-/Transition-Präsentation vorsehen; unabhängig von eigenem Mastermute und vom SL-Szenenprofil, ohne neue Geheiminformationen.
3. **Validierte Dry-/Fallbacks:** Nur erlaubte neutrale Grund-Cues statt unautorisierter Raw-Audio-Freigabe; klare serverberechtigte Medienprojektionen, 02.141-Peak-/Loudness- und 02.133-A-Autoplay-Grenzen respektieren.
4. **Audiojob-Lebenszyklus:** Reverb-/Echo-Tails, Spatial-/Transition-Gain, schnelle Effekt-An/Aus-Wechsel, Rechteentzug, SceneSwitch und 02.148-Gewinnerwechsel idempotent mit DSP-Budgets und Cleanup implementieren.
5. **Tests und Barrierefreiheit:** Splitgruppe, andere Hörer/SL unbeeinflusst, Audio ohne FX, geheimhaltungsbedingter Dry-Block, Mute/Codec/Mono/Mobil-/CPU-Fallback, Reconnect/Cache/NoWorld/NoSensor/NoACK; verständliches minimalistisches UI nach Gesamtworkshop festlegen.
6. **Offene Folgefrage:** Präferenz-Speicher- und Geräte-/Kampagnenscope als eigenständigen Beschluss **02.151** behandeln; genaue DSP- und Ressourcenwerte sowie MVP später entscheiden.

## 5. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Musik 02.132 Aus | Kein neues Abspielen oder Effektrecht durch persönliche Auswahl |
| Hall 02.146 Aus, Hörer aktiviert „Hall an“ | Kein heimliches Hall-Reaktivieren |
| Berechtigter Ambient-Cue, Hörer deaktiviert Hall | Cue bleibt bei zulässigem Dry-Audio hörbar, Hall-/Echo-Tails enden |
| Grund-Cue ist nur in geschützter verarbeiteter Form erlaubt | Kein ungeschütztes Raw-/Dry-Audio durch Effekt-Aus |
| Spieler A reduziert Hall, B nicht | Nur A hört reduzierten Hall, B und SL-Werte unverändert |
| Spieler setzt Mastermute während Effekt-Bypass | Mute bleibt vorrangig |
| Browser Autoplay blockiert Audio | Lokaler Effektschalter startet nicht von selbst |
| Berechtigter Cue enthält Spatialwirkung, die Hörer reduziert | Kein neuer Positions-/Distanz-/Velocity-/Fog-Zugriff |
| Effekte sollen NPCs/Sensoren leiser machen | Echte 02.49–02.51-Spielwelt bleibt völlig unverändert |
| Hallprofil-Szene aus 02.147 wechselt | Neuer serverautorisierter Gewinner bleibt; persönliche Stärke wirkt nur lokal |
| 02.148-Gewinner ist geheim oder nicht mehr berechtigt | Keine alternative Raw-/Preset- oder Metadatenfreigabe |
| 02.149-Sanftübergang läuft, Hörer stellt FX aus | Kontrollierbare lokale Effektjobs/Tails enden, Grund-Cue soweit erlaubt bleibt |
| Alte Szenen-Audiolizenz wird widerrufen | Kontrollierbare nun unzulässige Altteile stoppen, kein Komfort-Fade |
| 02.134 Musiklayer und 02.138 Ducking wirken | Kein ungewollter neuer Cue, kein pauschaler System-Ducking-Bypass |
| 02.141 Limiter/Peakschutz aktiv | Dieser bleibt trotz Effekte-Aus aktiv |
| Andere Person meldet sich im selben Browser an | Keine unautorisierte Nutzung fremder Audio-/Präferenz-/Cachebereiche |
| Hörer ist in Kampagne A SL, B Spieler | Effekt-Aus überträgt keine Rollen-/Szenen-/Cue-Rechte kampagnenübergreifend |
| Client manipuliert Effektgain/SourceIDs | Kein fremder Medien-/Preset-/Geheimniszugang oder Serverzustands-Commit |
| Mehrere schnelle Ein/Aus-Änderungen | Keine unkontrollierten CPU-/Speicher-/Echo-Tail-Leaks |
| Gerät ohne räumliche Audio-Engine | Sicherer berechtigter neutraler Fallback oder kontrollierter Abbruch |
| Mobilgerät mit niedriger Leistung | Optionale DSP-Reduzierung ohne Erhöhung serverautoritärer Rechte |
| Spieler verbindet nach Netzausfall erneut | Keine historischen Audio-Cue-/Transition-Catch-ups |
| Bereits berechtigtes Audio wurde vorgeladen | Nur gültige Medien; Effekte-Aus legitimiert keine Geheimassets |
| Musikeffekt-Presetname enthält „Alarm“ | Kein Schallsensor-/NPC-/Node-/Alarmevent durch FX-Schalter |
| Musikeffekt-Presetname enthält „Tür öffnen“ | Keine 02.99-Tür-/Quest-/Turn-/Inventar-/Würfelaktion |
| Amtliche 02.102-Kenntnisnahme erforderlich | Effektsteuerung bestätigt keine Notices |
| 02.137/02.139/02.140 A-Ausschlüsse | Kein Insertparameterwizard, Captionfeed oder Editor-Sonderplayer |

## 6. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen 02.150 C:** Berechtigte Hörer können optional implementierte **rein lokale** Hall-/Echo-, passende Spatial- und Szenenprofilübergangseffekte für sich selbst reduzieren oder abschalten. Eine bereits zulässige Grundmusik bleibt **nur soweit die neutrale Wiedergabe ebenfalls autorisiert ist** unabhängig hörbar; keine Rechte- oder Geheimnisumgehung, keine Veränderung von SL-/Mitspielereinstellungen oder 02.49–02.51-Echtweltphysik und keine 02.99-/02.102-Wirkung. Eigene Mute-/Gain-/Browserregeln, 02.133 A ohne globale Audiouhr, 02.141-Sicherheitspfade, 02.148-gewählte Profile sowie 02.149-Widerrufsschutz bleiben bindend.

**Nicht beschlossen:** Konkrete lokale Regler-/Preset-UI, exakte Pegel-/DSP-Kurven, Speicherung/Synchronisierung persönlicher Präferenzen, Datenbank-/API-Schemata, MVP-Umfang. Weiterhin Fachplanung, kein implementierter Code.

## Nächste Entscheidung 02.151 – Wie werden persönliche Audioeffekt-Einstellungen gespeichert?

**Beispiel:** Ein Spieler reduziert am PC für eine Kampagne den Hall. Bei der nächsten Sitzung oder auf einem anderen Gerät soll das Verhalten vorhersehbar bleiben, ohne die persönlichen Audioeinstellungen anderer Benutzer, SL-Profile oder Rechte zu überschreiben.

- **A – Nur für die aktuelle Browser-Sitzung:** Persönliche Effektreduktion wird nur flüchtig für den aktuellen Tab/Player verwendet und bei Browserneustart nicht dauerhaft gespeichert.
- **B – Erzwungener globaler Wert für alle:** Eine Person bzw. die SL setzt einen identischen Effektwert für alle Benutzer, Kampagnen und Geräte, unabhängig von deren Mute-/Zugriffsrechten.
- **C – Geschützte persönliche Präferenzen nach konfigurierbarem Scope (Empfehlung):** Bei 02.150-fähigem Audio können eigene Einstellungen optional **pro Gerät/Browser, pro Kampagne und/oder pro eigenem Profil** gespeichert und – soweit ausdrücklich erlaubt – zwischen eigenen Geräten synchronisiert werden. Nur mit gültiger Identität/ACL, ohne Offenlegung an andere Spieler, ohne neue Audio-/Szenen-/Medienrechte und ohne Vorrang vor lokalem Master-Mute, Browserregeln oder Gerätefähigkeit. Voreinstellung/Sync-/Lösch-/Kollisions-/Fallbackdetails später.
