# AdventureShift – Karten-Workshop: Beschluss 02.138 C – berechtigtes lokales Soundboard-Cue-Ducking

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.138; nächste offene Featurefrage 02.139.
**Status:** Verbindlicher Fachbeschluss und konzeptioneller Umsetzungs-/Abnahmetestplan; **noch keine Softwareimplementierung**, keine endgültigen Audio-API-/DB-/UI-Verträge oder MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnen-/Rollenstandards und markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.49–02.51 – unabhängige Szenenschall-/Sensor-/Nodewelt](KARTEN-WORKSHOP.md) · [02.99 – echte berechtigte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – amtliche Hinweise und ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – optionaler Chat](KARTEN-WORKSHOP-02.105.md) · [02.110 – Chatmutes/DM-Blocks](KARTEN-WORKSHOP-02.110.md) · [02.116 A – keine individuellen Chatlesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.122 A – keine Chat-Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.126 C – berechtigte Chatbenachrichtigungen](KARTEN-WORKSHOP-02.126.md) · [02.132 C – konfigurierbare Sessionmusik/Playlists/Soundboard](KARTEN-WORKSHOP-02.132.md) · [02.133 A – kein gemeinsamer Musikplayhead/AutoJoin](KARTEN-WORKSHOP-02.133.md) · [02.134 C – lokal konfigurierbare Musik-/Soundboard-Layer und Fades](KARTEN-WORKSHOP-02.134.md) · [02.135 C – geschützte Audio-Vorlagen](KARTEN-WORKSHOP-02.135.md) · [02.136 C – kontrollierte Vorlagenupdates](KARTEN-WORKSHOP-02.136.md) · [02.137 A – feste Audio-Vorlagen ohne Einfügeparameter](KARTEN-WORKSHOP-02.137.md).

## 1. Verbindliche Entscheidung – Variante 02.138 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Bei wirksam aktiviertem **02.132-C-Musikmodul** und nach **02.25-Kampagnen-/Rollen-/Gruppen-/Szenen-/Personenstandards mit gültigen markierten Ausnahmen** kann die SL eine **eigenständige optionale lokale Audio-Cue-Prioritäts-/Duckingfähigkeit** freigeben. Nur ein **für genau diesen Hörer und das Audioasset tatsächlich berechtigter** Soundboard-Cue darf auf dessen **eigenem Gerät** geeignete **eigene Musik-/Ambient-Layer vorübergehend relativ zu deren momentanen lokalen Basispegel absenken**; anschließend wird die Absenkung wieder zurückgenommen und höchstens auf den **inzwischen gültigen eigenen** Pegel zurückgeführt. **Weder persönliche Stummschaltung noch Browser-/Betriebssystem-Audiorechte werden übergangen.**

**Beispiel:** A hört auf dem eigenen Computer erlaubte Tavernenmusik mit selbst gewählter Lautstärke. Ein für A berechtigter SL-Glockencue wird nach gültiger Audio-/Hörerfreigabe lokal abgespielt; die **nur bei A** laufende Tavernenspur wird vorübergehend leiser und danach zu As aktuellem gewählten Pegel zurückgeführt. B kann den Glockenton lokal anders spät hören, Musik komplett stumm haben oder Ducking in der eigenen effektiven Fähigkeit nicht aktiviert haben; B wird **nicht** aus As Player mitgesteuert. Ein Audio-Cue wird dabei **niemals** in einen 02.51-Schall-, Sensor-, Alarm- oder Nodeeffekt umgewandelt.

**Nicht gewählt:** A (gar keine automatische lokale Musikabsenkung) und B (jeder Cue kann ohne Rechte fremde Musik, Voicechat, Systemlautstärke oder Mutes übersteuern). C erlaubt **keine** Live-Voice-Erkennung, Mikrofonaufnahme, systemweite Lautstärkemanipulation, globale Wiedergabeposition oder globale Synchronisation.

## 2. Konfiguration und funktionale Grenzen

1. **Getrennter wirksamer Schalter:** 02.138-Ducking als **optionale Unterfähigkeit** nur bei 02.132-C-Musik **An**; es kann je gültiger 02.25-Policy auch bei aktivem Musik-/02.134-Mischmodul **Aus** sein. Ohne wirksame Duckingfähigkeit gibt es ausschließlich normales rechtmäßig erlaubtes Playback/Fades/Layers – kein versteckter Gain-Eingriff.
2. **Priorisierte Soundboard-Cues:** Nur unterstützte, tatsächlich berechtigte Audio-Cue-Arten mit eigener zulässiger Zuordnung zu lokalen Ziel-Layern dürfen eine befristete Absenkung auslösen. Ob und wie Prioritätsklassen, Cue-Gruppen, Zielbusse oder kampagnenspezifische Presets gestaltet werden, bleibt späterer UI-/Technikplanung vorbehalten; **keine** Umgehung von 02.132-Actor-/Cue-/Target-/Assetrechten.
3. **Nur passender eigener Mixbus:** Ducking wirkt **ausschließlich innerhalb des integrierten, lokalen 02.134-C-Mixers** auf freigegebene **eigene Musik-/Ambient-Spuren**, niemals auf Voicechat anderer Anwendungen, System-/Betriebssystem-/Hardwarelautstärke, Mikrofoneingabe, fremde Geräte, Pflichtsystemhinweise oder reale Spielszenenschallwerte nach 02.49–02.51.
4. **Pegelhierarchie und persönliche Souveränität:** Persönlicher Mastermute/Browserblock und selbst gewähltes Master- sowie Musik-/Ambient-Layer-Gain haben Vorrang; Ducking ist ein **nur reduzierender temporärer Faktor**, kein „set volume“-Befehl gegen den Nutzer. Nach Duckingende wird ausschließlich die **Absenkung entfernt**, nicht ein alter absolute Basispegel wieder hineingeschrieben.
5. **Lokales Timing:** Angriff, Haltephase, Freigabe/Erholung und mögliche kurze Fades nur auf dem **jeweiligen Hörergerät** und für den tatsächlich dort zulässig gestarteten Soundboard-Cue. Keine garantierte globale Gleichzeitigkeit und kein vom Server verbreiteter Musikstart-/Seek-/Pause-/Fadestand. **02.133 A bleibt vollständig bestehen**.
6. **Hörerautonomie/Consent:** Der berechtigte Cue selbst darf nur nach 02.132-C-Actor-/Asset-/Empfänger-/Szenenpolicy und tatsächlicher Browser-/Nutzerentscheidung lokal hörbar werden. Ein verworfener/gesperrter/nicht gestarteter Cue darf **nicht als Trick** fremde oder eigene Musik herunterregeln.
7. **Überlappende Cues:** Mehrere legitime lokale Prioritäts-Cues dürfen nur nach einer begrenzten, sicheren, deterministischen eigenen Mixregel die Absenkung **zusammenfassen**, **nicht** mehrere unkontrollierte Faktoren stapeln, permanent Mutes manipulieren oder nach dem letzten Cue im abgesenkten Zustand hängen bleiben. Konkrete mathematische Kombination und Limitwerte erst später festlegen.
8. **Änderung des Basispegels während Ducking:** Ändert A während der Glocke selbst Musik-Lautstärke/Mute, gilt sofort sein neuer Pegel. Beim Ende der Glocke kehrt Musik zu **diesem aktuell gewählten** Wert zurück, nicht zur zuvor gespeicherten Lautstärke und insbesondere niemals aus Mute wieder in Ton.
9. **Laufzeitwechsel:** Stop, Pause, Ducking-Schalter Aus, Musikmodul Aus, Szenen-/Gruppen-/Rollen-/Assetrechtwiderruf, Cueabbruch, Browser-Tab-Suspend, Audio-Fehler und Reconnect führen zu geordnetem Beenden/Invalidieren eines nur lokal zulässigen Gain-Absenkungsjobs; **kein** globales Cue-/Ducking-Replay oder automatisches Nachholen vergangener Sounds.
10. **Optional trotz Voicechat-first:** 02.105-Chat und externe Voicechats bleiben unabhängig. Keine Mikrofon-, Audiolautheits-, Voicechat-/Spracherkennungs-, Transkriptions- oder 02.122-A-Chat-Voice-Memo-Pipeline; Ducking basiert **ausschließlich auf zulässigen eigenen Audio-Cue-Ereignissen**.
11. **Keine versteckte Weltfunktion:** Ein benannter „Alarm“- oder „Tür öffnen“-Soundboard-Cue ist **nur Audiowiedergabe**. Keine automatische echte 02.49–02.51-Hörbarkeit, 02.99-Worldaction, NPC-/Quest-/Door-/Turn-/Inventar-/Node-/Schallsensor-Trigger und keine offizielle 02.102-ACK-Quittierung.

## 3. Berechtigungs-/Integrationsgrenzen

| Existierender Beschluss | Unveränderliche Auswirkung |
| --- | --- |
| **02.25 / 02.132 C** | Kampagnen-/Rollen-/Gruppen-/Szenen-/Personen-Capabilities sowie Owner-/Asset-/Lizenz-/Empfängerrechte vor Audio-Cue, Duckingangebot und lokaler Ausführung |
| **02.133 A** | Keine gemeinsame Musikzeit, kein Serverplayhead, kein synchronisierter Duckingstart/-fade, kein AutoJoin/AutoReconnect oder auf globalen Timestamp gestütztes „Aufholen“ |
| **02.134 C** | Bestehende rein lokale Crossfade-/Loop-/Musik-/Soundboard-Layer bleiben; Ducking ist eine zusätzliche **optional schaltbare** lokale Busfunktion, keine Pflicht für die lokale Mischfunktion |
| **02.135 C / 02.136 C / 02.137 A** | Freigegebene Audio-Vorlagen/Updates unverändert berechtigt; beim Audio-Vorlagen-Einfügen **keine** neuen Parameterdialoge, ein entsprechender Duckingwert nur als zulässig gespeicherte Konfiguration oder nach separatem Ziel-Edit |
| **02.49–02.51 Szenenschall/Sensor/Nodes** | Virtuelle Audioabsenkung verändert niemals Schallphysik, Lärmereignisse, Präsenz-/Bewegungs-/Mikrofon-/Schallsensoren oder Alarmschaltungen |
| **02.99 reale Spielwelt / 02.101–02.104 ACKs** | Cue-/Duckingnavigation erzeugt keine Quest-/NPC-/Door-/Würfel-/Turn-/Inventaraktion und bestätigt keine amtliche Kenntnisnahme |
| **02.105 / 02.110 / 02.126** | Chatmodul, persönliche Chat-Kanalmutes/-DM-Blocks, Chat-Badges/Toasts/OS-Notifications bleiben unabhängig vom eigenen Musik-/Duckingpegel |
| **02.116 A / 02.122 A** | Weder individuelles wer-hört-was-Tracking als Lese-Receipt noch Chat-Sprachnachrichten-/Voice-Memo-/Mikrofonaufnahme |
| **Browser/OS/Hardware/Datenschutz** | Persönliches Mute/Consent bleibt, kein Zugriff auf Fremd-/System-/Voicechatlautstärken, keine geheimen Cue-/Album-/Szene-/Track-/Empfängerstatistiken |
| **Mediensicherheit/Quelllizenz** | Ducking begründet kein neues Recht auf andere Audioassets, DRM-/Streamingprovider, Medien-URLs oder unberechtigte Vorschau |

## 4. Konzeptionelle Architektur und Lebenszyklus

1. **Policy und Quellzulässigkeit:** Serverseitig wirksame 02.132-Musik-An-/02.138-Ducking-Capability mit geeigneten 02.25-Defaults und markierten Ausnahmen; vor jedem Cueangebot echte Account-/Actor-/Rollen-/Kampagnen-/Gruppe-/Szene-/Asset-/Lizenz-/Geheimnis-/Recipient-/Cue-Rechte einschließlich aktueller Policy-/Quellrevision prüfen. Geheime Cue-Namen, Zielgruppen und Verfügbarkeit dürfen auch nicht über Ducking-Metadaten/Fehler-/Count-/Telemetry-Signale verraten werden.
2. **Nur gerätelokaler Audioeffekt:** Entwurfsnamen `LocalAudioDuckingCapability`, `AuthorizedLocalAudioCue`, `LocalAudioDuckTargetBus`, `LocalAudioDuckingGainEnvelope`, `LocalAudioDuckActiveSet`, `LocalAudioUserGainBaseline`, `LocalAudioDuckAbortToken` (**keine finalen Klassen/API-/DB-Namen**). Persönlicher Mixer führt aktuell erlaubte Zielspur und Duckingfaktor unabhängig von persistenten Spielerpräferenzen.
3. **Gainkomposition:** Konzeptionell `effectiveLocalGain = ownMasterGain × ownLayerGain × authorizedDuckFactor`, wobei der Duckingfaktor **höchstens 1** sein darf. Mastermute/Layer-Mute oder Browserblock setzt hörbare Ausgabe stets auf null. Keine Speicherung des temporär reduzierten Pegels **als** neuer Nutzerwert; nach Ende der Cue-Absenkung nur Duckfaktor entfernen.
4. **Beginn nur bei realem Cue:** Der Zielclient aktiviert einen begrenzten Duckingjob nur für einen **tatsächlich freigegebenen und lokal zugelassenen bzw. begonnenen** Cue. Nicht autorisierte, durch Browser blockierte, entfernte oder bei 02.133 A nicht nachzuholende Cues dürfen kein Ducking auslösen.
5. **Ende und Racekontrolle:** Kurzlebige Tokens/Revisionen für Start/Stop/Ende, konkurrierende, überlappende Cues, Mute-/Gainwechsel, Szenen-/Rechteentzug, Musik-Aus, Ducking-Aus, Reconnect und Ressourcenfehler; deterministischer bounded-failure-safe Rückweg auf **aktuellen** eigenen Basispegel. Kein Wiederabspielen früherer Cues nach Reconnect.
6. **Keine globalen Transportdaten:** Andere Spieler und die SL erhalten keine privaten individuellen Gain-/Duck-/Playhead-/Muted-/Cue-gehört-Angaben allein durch diese Funktion. Keine gemeinsame Server-Audio-Fade-Uhr; Reconnect führt vor potenzieller neuer Cuezulassung zu frischer Rechteprüfung.
7. **Belastbarkeit/Hörschutz:** Schutz gegen zu viele überlappende Cues, zu lange Absenkung, laute Soundeffekte, Rate-/Quota-/CPU-/Decoder-/Gain-/Clippingprobleme; eventuelle Prioritäten/Abklingkurven/Timebounds und maximale Absenkung erst im Gesamtsettings-/Audiodesign konkretisieren.
8. **Keine Welt- oder ACK-Schicht:** Ducking hat **ausschließlich lokal hörbare** Musik-/Ambientbuswirkung, nicht Spielwelt-Schallausbreitung, Alarmierung, Sensorinput, echten 02.99-Worldstate oder 02.102-Ack-/Reminderpfad. Fehler in der Audio-Engine dürfen nicht als normale World-/Node-Events propagieren.

## 5. Umsetzungsplan – nur Fachplanung

1. **Eigene schaltbare Fähigkeit:** 02.138-Ducking unter 02.132-Musik nur bei gültigen 02.25-Defaults/Ausnahmen, echte Actor-/Cue-/Targetbus-/Lizenz-/Secret-/Empfängerprüfungen; kein Zwang für reine 02.134-Mischfunktion.
2. **Berechtigter Cue-Resolver:** Nur bereits rechtmäßig nutzbare Soundboard-Cue-Identität/Version, Source-/Asset-/Scene-/Role-/Recipientrechte, Mute-/Browser-/Duckingfeatureeffekt pro tatsächlich abspielendem Gerät; kein eigener ungeschützter Websocket-Broadcast.
3. **LocalAudio-Mixeradapter:** Getrennter eigener Master-/Layer-Basispegel und temporärer bounded-Duck-Faktor mit Gain-Hierarchie/Mute, lokaler Kurve und ggf. zulässiger Busauswahl; keine Mikrofon-/externen Voice- oder OS-System-Audio-APIs.
4. **Revisions-/Abort-Grenzen:** Mehrere Cues sicher kombinieren, nach letzten gültigen Cues nur Duckingfaktor entfernen, aktuellen persönlichen Baselinepegel nicht überschreiben; Quell-/Rollen-/Szenen-/Modulwiderruf, Browser-/Reconnect-/Tabpause sicher behandeln.
5. **Abnahme und offene Implementierung:** Testmatrix unten; finale konkrete Cuekategorien, Kurven/Dauern, UI, Benutzerpräferenzen, Audioengine, Datenmodelle, technische Lastgrenzen und MVP in der späteren technischen/UX-Planung festlegen.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| 02.132-Musik An, 02.138-Ducking nach Policy Aus | 02.134-Layer und Fades funktionieren; Soundboard-Cue senkt Musik nicht automatisch |
| Musik Aus, Chat An, Soundboard-Cue angefordert | Kein neuer Audio- oder Duckingvorgang; unabhängiger Chat/Systemfeed ungestört |
| Musik An, Chat Aus, Ducking erlaubt | Lokaler berechtigter Glockencue darf eigene Musik absenken, ohne Chat zu aktivieren |
| SL-Cue gilt für A, nicht B | Nur A bekommt berechtigten Cue samt möglichem lokalem Ducking; B keine Cue-/Secret-/Count-Details |
| A und B spielen Track zeitversetzt | Keine gemeinsame Musikposition/Start-/Pause-/Duck-Zeit; Ducking nur am jeweiligen lokalen Player |
| Spieler A hat eigenen Musikmaster auf niedrige Lautstärke | Ducking reduziert höchstens darunter und kehrt zu As aktuellem eigenen Wert zurück |
| A schaltet Mastermute vor Cue ein | Alle eigenen Layer bleiben stumm; kein späteres automatisches Entmuten |
| A verändert eigene Musiklautstärke während Cue | Nach Cue endet nur Duckingfaktor; der **neu gewählte** persönliche Wert bleibt |
| A mutet mitten in der Absenkung | Kein Wiederanheben nach Duckingende gegen Mute |
| Browser verbietet Cue-Autoplay | Kein Cue-/Duckingzwang, keine OS-/Hardware-Audioumgehung |
| 02.134-Layer: Musik und Regen-Ambient zulässig | Nur freigegebene eigene Zielbusse temporär absenkbar, nicht pauschal andere Quellen |
| SL erlaubt Ducking nur für Musik, nicht Ambient | Ambientpegel bleibt nach eigenen Einstellungen unverändert |
| Cue wird wegen Asset-/Lizenzrechten abgewiesen | Kein Sound und kein Ducking; keine Daten zum geheimen Track |
| Client errät eine geheime Soundboardcue-ID | Keine Aktivierung, kein Player-/Duckingcount, kein Existenz-/Fehlertextleck |
| Cueziel gewechselt, während Cue ansteht | Revalidierung vor lokaler Aktivierung; alte Berechtigungs-/Zielinformationen ungültig |
| SL versucht fremde Musiklautstärke per Ducking zu ändern | Kein Remote-/globale-OS-Lautstärkezugriff; B verwaltet nur Bs eigenen Player |
| SL versucht Voicechat-App-Lautstärke zu reduzieren | Externe Voice-/Systemlautstärke liegt außerhalb Duckingmodul und bleibt unverändert |
| Mikrofonberechtigung fehlt | Funktion benötigt keine Mikrofonaufnahme, Lautheitserkennung, Sprachaufnahme oder Transkription |
| 02.122 A keine Chat-Voice-Memos | Ducking erzeugt keinen Chat-Sprachnachrichten-/Aufzeichnungspfad |
| Zwei rechtmäßig gestartete lokale Cues überlappen | Begrenzte deterministische Absenkung; nach Ende des letzten Cues normaler **aktueller** Baselinepegel |
| Erster Cue endet, zweiter läuft noch | Keine vorzeitige volle Rückkehr und keine kumulierte unbegrenzte Absenkung |
| Cues werden rasch mehrfach gestartet/gestoppt | Token-/Versions-/Idempotenzschutz gegen hängen gebliebene Gain-Jobs |
| Mute, Cuestop und Rechteentzug gleichzeitig | Persönlicher Mute und gültige neueste Policy gewinnen; kontrollierte Jobabbruchlogik |
| Musik-/Duckingunterfunktion wird während laufendem Cue deaktiviert | Kontrolliertes Ende der Duckingjobs; kein heimlicher neuer Audioauftrag |
| Browser-Tab suspendiert/Resume | Keine neue Cuespielung per Sync-/Reconnect-Catch-up; Zustand nach aktuell gültigen Rechten sicher |
| A reconnectet mitten in fremdem Cue | Kein Nachholen oder globales Ducking-/Trackpositionssync nach 02.133 A |
| Zwei Geräte von A haben unterschiedliche eigene Pegel | Keine gegenseitige Gain-Übertragung oder zentrale Hörer-/Duckingtelemetrie |
| Spieler startet regulären Loop/Crossfade aus 02.134 C | LocalMix bleibt; 02.138 ist separat und optional, keine neue globale Timeline |
| Playlist-/Soundboardvorlage 02.135 C gespeichert | Keine Audioasset-/Lizenz-/Duckingrechte durch Vorlage allein |
| 02.136 C erlaubt Versionierung von Vorlagen | Neue Cuepriorität/-konfiguration aktualisiert keine laufenden Player automatisch |
| 02.137 A feste Audio-Vorlage wird eingefügt | Kein zusätzlicher Ducking-Prioritätsparameterdialog bei Vorlageninsert |
| Vorlage referenziert unzulässiges Album-/Audioasset | Keine Medien-/Preview-/Cover-Freigabe durch Ducking-Metadaten |
| Soundboardcue heißt `Alarm` | Kein echter Spielwelt-SoundEvent-/Sensor-/Alarmausgang |
| Soundboardcue heißt `Tür öffnen` | Kein 02.99-Tür-/Quest-/NPC-/Node-/Würfel-/Turn-/Inventareffekt |
| 02.49–02.51-Spielweltgeräusch aktiviert Sensor | Nur originaler geprüfter SoundEvent-Pfad, nie lokales Musikpegel-Ducking |
| 02.101-Korrektur/02.102-ACK wartet | Glocke hören, Ducking, Stoppen oder Mute quittiert nichts amtlich |
| Spieler besitzt 02.110-Chat-Kanalmute | Kein Umschalten des unabhängigen Musikmute und keine Änderung offizieller Hinweise |
| 02.126-Push während Hintergrundmusik | Pflicht-/Chat-Hinweis wird nicht von Ducking als Mikrofon-/OS-Audioquelle abgefangen |
| Cue-Storm mit vielen IDs und langen Haltezeiten | Server-/Client-Quota-/Rate-/Dauer-/CPU-/Lautheitsgrenzen greifen, keine Endlosabsenkung |
| Quellrolle verliert Cue-Sendeberechtigung | Neue Cues abgelehnt, laufende kontrollierbare Cues/Jobs nach gültiger Policy beendet |
| Mehrere Kampagnen auf einem Hörergerät | Kein Audio-Cue-/Ducking-/Secret-/Template-Übergreifen auf fremde Kampagnenscopes |

## 7. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.138 C – getrennt schaltbare, nur durch tatsächlich erlaubte Soundboard-Cues ausgelöste, zeitlich begrenzte lokale Absenkung ausschließlich eigener Musik-/Ambient-Layer mit Rückkehr zum aktuell gewählten eigenen Basispegel.** 02.132-C-Kampagnenmusik/Berechtigungen und 02.25-Defaults/Ausnahmen gelten, 02.133 A **kein globaler Playhead/Sync/Join-Catch-up**, 02.134 C optionales **lokales** Layer-/Fade-/Loop-Mixing, 02.135-/02.136-C-Vorlagenrechte/Updates und 02.137 A **keine Audio-Vorlagen-Insertparameter** bleiben. Persönlicher Master-/Layer-Mute, Browserautoplay und Quell-/Asset-/Lizenz-/Scene-/Recipientrechte gewinnen. Keine externen Voicechat-/Systemlautstärkeeingriffe, Aufnahme, Chat-Voice-Memos, 02.49–02.51-Spielwelt-Schall-/Sensor-/Node-/Alarmwirkung, 02.99-Weltaktion oder amtliche 02.102-ACK-Quittierung.

**Nicht beschlossen:** konkrete Cue-Prioritätsstufen, Ducking-Kurven, Attack-/Release-/Haltedauern, genaue kombinierte Pegelabsenkung, Hörschutz-Limits, API/DB/UI, MVP. Dieser Beschluss ist technische Fachplanung, keine fertige Implementierung.

## Nächste Entscheidung 02.139 – Barrierefreie visuelle Hinweise zu Soundboard- und Musik-Cues

**Beispiel:** Eine Spielerin hat Ton deaktiviert oder kann bestimmte Geräusche nicht hören. Sie könnte optional eine kurze sichtbare Beschreibung **nur für Audio-Cues erhalten, die für sie tatsächlich freigegeben sind** – etwa „Glocke läutet“ – ohne dass eine geheime Falle, fremde Szene oder private Audio-Datei sichtbar wird.

- **A – Keine besonderen visuellen Audiohinweise:** Musik und Soundboard bleiben rein akustisch; Barrierefreiheit erfolgt nur über die allgemeinen UI-Einstellungen und manuelle SL-Kommunikation.
- **B – Alle Audiodaten für alle als Text:** Jeder bekommt jeden Track-, Geräusch-, Szenen- und Geheim-Cue als öffentlichen Text samt Eventzeiten/Dateinamen, auch ohne Hör-/Kanal-/Szenen-/Empfängerrechte.
- **C – Optionale berechtigte visuelle Audiohinweise (Empfehlung):** Bei aktivem 02.132-Musikmodul kann die SL nach 02.25-Defaults/markierten Ausnahmen ergänzende **redaktionell kontrollierte kurze Text-/Symbolhinweise** für tatsächlich autorisierte Musik-/Soundboard-Cues freigeben. Die hörende Person darf die Darstellung persönlich nutzen/ausblenden; keine Offenlegung geheimer Tracktitel, SL-only-Cues, fremder Kampagnen oder versteckter Szenen durch Count, Text, Toast oder Cache. Keine automatische Sprachtranskription, keine 02.122-Voice-Memos, kein 02.133-A-Sync und kein 02.49–02.51-Schall-/Sensor-/Welt-/ACK-Effekt; UI später.
