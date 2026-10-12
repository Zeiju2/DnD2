# AdventureShift – Karten-Workshop: Beschluss 02.75 C

**Stand:** 12.10.2026 – Beschluss 02.75 C; Folgeentscheidung 02.76 C ebenfalls dokumentiert, als Nächstes 02.77  
**Status:** Verbindliche fachliche Entscheidung, Architektur- und Testplanung. Keine Softwareimplementierung, kein finales Datenbankschema.  
**Anschluss:** [Hauptworkshop](KARTEN-WORKSHOP.md) · [Beschluss 02.74](KARTEN-WORKSHOP-02.74.md) · [Beschluss 02.76](KARTEN-WORKSHOP-02.76.md) · [Feature-Katalog](FEATURE-WORKSHOP.md)

## 02.75 – Konfigurierbare Zeitbasis und sichere Timer bei Pause, Offline-Zeit und Neustart (12.10.2026)

**Verbindlich beschlossen: Variante C.** Zeitbasierte und runden-/ereignisbasierte Vorgänge erhalten eine ausdrückliche, versionierte wirksame Zeitregel. Die Spielleitung definiert fachliche Kampagnen-/Regelprofilstandards mit erkennbar markierten Ausnahmen für geeignete Szenen, Regionen, Gruppen, Zugkontexte, Aktions-/Timerklassen, konkrete Timer und Nodes (Vererbungs-/Bestandsregeln 02.25). Dies betrifft unter anderem Tür-/Schloss-/Keycardfristen (01.11–01.16), zeitliche Itemeffekte (01.7), Zeit- und Wiederholungs-Nodes (02.15–02.16), Szenen-/Cross-Scene-Ereignisse (02.18–02.20), NPC-Nachrichten/Gedächtnis/Wachsamkeit (02.55–02.61), ausstehende Zugübergaben (02.67–02.74) und autonome Rätselmechanismen. Die genauen Zeitwerte und UI-Einstellungsführung bleiben für spätere Planung offen.

### 1. Ausdrückliche Zeitbasen – keine stille Umrechnung

- **Echtzeit / verstrichene Zeit:** Countdown wird anhand serverautoritativ gespeicherter Zeitanker berechnet; eine konfigurierte Echtzeituhr darf auch während Spiel-/Szenenpause, Offline-Zeit einzelner Spieler und Serverstillstand fortschreiten. Solange der Server nicht läuft, werden aber keine realen Nodes ausgeführt: Nach Neustart wird die Fälligkeit anhand der gespeicherten Basis *geprüft*, nicht rückwirkend eine unkontrollierte Effektkette simuliert.
- **Aktive Kampagnen-/Spielzeit:** Nur validierte Zeitabschnitte zählen, während der zugehörige Kampagnen-Zeitkontext laut Regel aktiv ist. Pausierte Abschnitte, für die keine aktive Zeit gebucht wird, verlängern keine fällige Aktion; ein einzelner Offline-Spieler pausiert nicht automatisch alle anderen.
- **Aktive Szenen-/Kontextzeit:** Nur Zeit im ausdrücklich zugeordneten aktiven Szenen-, Gruppen- oder Turn-Kontext zählt. Zwei Szenen oder Rätsel können parallel verschiedene Zeitstände besitzen. Inaktive/geladene/unsichtbare Szenen haben nicht automatisch denselben Zeitstatus; ein anderer laufender Bereich setzt ihren Timer nicht unbeabsichtigt fort.
- **Runden-/Zugzeit:** Fortschritt ausschließlich durch gültige, eindeutig identifizierte Turn-/Rundenereignisse der richtigen Zugfolge und Generation (02.67–02.74). Sekunden, Minuten und Zug-/Rundenanzahl werden **nicht automatisch ineinander umgerechnet**. Auch parallele Turn-Kontexte verändern einander nicht ohne ausdrückliche, autorisierte Verknüpfung.
- **Ereignis-/Node-gesteuerte Zeit:** Ausdrücklich typisierte gültige Node-/Storyereignisse dürfen den Fortschritt, das Fälligwerden oder den Reset auslösen. Doppelt zugestellte oder nicht berechtigte Trigger gelten nicht als neue Zeit.
- **Kombinationen nur ausdrücklich:** Ein Timer darf nur dann mehrere Clock-Grenzen oder kombinierte Bedingungen verwenden, wenn das gültige Regelprofil genaue Bedeutung und Abschlussbedingung festlegt; keine implizite Ableitung aus Client-Zeit, Tageszeit, anderen Spieler-Sessions oder Szenenwechseln.

### 2. Pause, Unterbrechungen und Wiederanlauf

- **Hierarchisch und begrenzt:** Kampagnen-, Szenen-, Turn-/Rätsel- und ausdrücklich definierte Aktionspausen wirken nur auf zugewiesene Timer-Zeitbasen. Pause-Grund, Scope, Beginn, Ende, verantwortliche berechtigte Quelle und Regelversion sind nachvollziehbar. Ein übergeordnet pausierter Clock-Scope kann nicht durch eine unberechtigte untergeordnete Wiederaufnahme umgangen werden.
- **Spieler offline / Reconnect:** Die Abwesenheit eines einzelnen Spielers bedeutet nicht automatisch Stillstand der Kampagne. Der Timer folgt ausschließlich seiner wirksamen Policy; Aktionen, die eine bestimmte Figur erfordern, prüfen deren Verfügbarkeit und Rechte beim tatsächlichen Effekt erneut. Ausfall-/Ersatzzugregeln 02.69 bleiben eigenständig.
- **Serverneustart / Ausfall:** Persistierte Fälligkeit, bereits gezählte aktive Dauer, Scope-Pausen, Aktions-/Timerstatus und Versionen rekonstruieren; Reconnect darf einen Countdown nicht ein zweites Mal erzeugen. Für Echtzeit kann eine Frist inzwischen abgelaufen sein, für ausschließlich aktive Spiel-/Szenenzeit zählt nicht laufende Serverzeit nicht als simulierte Spielaktivität.
- **Überfällige Timer:** Die gewählte Policy bestimmt, ob eine noch gültige Fälligkeit bei Wiederaufnahme *einmal kontrolliert* nachgeholt, übersprungen/verworfen, zeitlich fortgeschrieben oder bis zur SL-Entscheidung angehalten wird. Es werden keine verbotenen, mehrfachen Explosionen, Spawns, Schadensereignisse, Alarme oder Zugwechsel aus einer langen Offline-Zeit erzeugt. Wiederkehrende Timer (02.16) benötigen eine begrenzte, eindeutige Fälligkeits-/Occurrence-Behandlung; die genaue Priorisierung gleichzeitig fälliger Ereignisse ist inzwischen als **02.76 C** beschlossen (siehe [02.76](KARTEN-WORKSHOP-02.76.md)).
- **Stop/Reset/Neustart einzelner Timer:** Nur ein ausdrücklich gültiger SL-/Regel-/Node-Auslöser darf sie unter kontrollierter Versionierung ändern. Zeit verschieben, pausieren und zurücksetzen sind eigenständige Vorgänge; eine rückwirkende Änderung löst nicht ohne zusätzliche Berechtigung alte Folgewirkungen neu aus.
- **Bestehende Instanzen bei Policyänderung:** Regeln aus 02.25 gelten auch hier: Vorschau betroffener vorhandener Timer; Änderungen nur an neuen Instanzen oder ausdrücklich an zulässigen nicht überschriebenen Bestandsinstanzen, mit bewusster Migration von Start-/Rest-/Fälligkeitswerten. Aktive Timer behalten keine ungeprüft veränderten Restfristen, und individuelle Ausnahmen werden nicht überschrieben.

### 3. Konzeptionelle Zustands- und technische Schutzregeln

**Vorläufige Modellbegriffe, nicht als finale API beschlossen:** `TimerClockPolicy`, `TimerInstance`, `ClockScope`, `PauseInterval`, `TimerOccurrence`, `TimerEffectDispatch`. Jeder konkrete Timer referenziert Kampagne/Szene/Turnkontext/Node oder anderes zulässiges Besitzerobjekt, die wirksame Zeitbasis samt Policy-/Overrideversion, unverwechselbare Timerinstanz-ID, den autorisierten Startauslöser, persistierte Zeitanker oder bereits verbuchte aktive Dauer, Fälligkeit bzw. ausstehende Ereignis-/Rundenzahl, wiederkehrende Occurrence-ID und aktuellen Zustand.

1. **Serverautoritativ:** Clients können lokal höchstens eine geschätzte Restzeit anzeigen; der tatsächliche Zeitstand, Pausen und die wirksame Fälligkeit werden serverseitig bestimmt. UTC-Zeitanker und geeignete monotone Prozesszeit für laufende Intervalle trennen; Systemuhrsprünge und Drift müssen kontrolliert erkannt und sicher behandelt werden. Keine Zeitzonen-/Sommerzeitverschiebung darf aus einer Dauerfrist ungewollt eine zweite Auslösung machen.
2. **Persistenz und Wiederherstellung:** Dauerhaft registrierte Timer und ihre Ausführungszustände transaktional speichern, bevor relevante Wirkung bestätigt ist. Nach Absturz/Neustart Fälligkeit gegen unveränderte Timer-/Regel-/Objektversion und aktuelle Aktionsrechte erneut prüfen. Kein bloßer Client-Countdown und keine ungeschützte `setTimeout`-Annahme als einzige Wahrheit.
3. **Einmalige Wirkungsfolge:** Je Timerinstanz und konkreter Occurrence stabile deduplizierbare IDs; Effektstatus inklusive wirksam/abgelehnt/ausstehend, idempotenter Node-Dispatch und ggf. transaktionaler Outbox-Ansatz für Ereignisse. Interne Wiederholungsversuche dürfen dieselbe echte Tür-, Alarm-, Spawn-, NPC-Wissens-, Inventar- oder Turnwirkung nicht doppeln. Sicherheit gilt auch bei zwei Serverarbeitern, Retry, Reconnect und Graphschleifen (02.35).
4. **Rechte neu validieren:** Das Ablaufen einer Zeit rechtfertigt nicht automatisch eine Weltwirkung: Kampagnen-/Szenen-/Graph-/Nodeberechtigung, gültige Regelversion, Zielobjekt-/Türzustand, aktuelle Turngeneration, reale Figur-/Inventarressourcen und inaktive Szenenpolicy direkt vor Effect-Commit prüfen. Eine nur pausierte/ausstehende Aktion aus 02.74 ist nicht bereits wirksam.
5. **Sichtbarkeit & Geheimnisse:** Countdown, Fälligkeitszeit, pausierter Zustand, verborgenes Ziel, Fehlergründe und Verlauf an Spieler nur gemäß Serverberechtigung projizieren. Geheime Fallen/SL-Nodes und unbemerkte Proben bleiben auch über Timeranzeigen, Reconnect, Fehlermeldungen und Telemetrie verborgen; vollständige Gründe nur im berechtigten SL-Debug.
6. **Keine globale Blocksperre:** Unabhängige Kampagnen/Szenen/Turnkontexte dürfen parallel Zeit führen. Bei gemeinsamem echten Weltobjekt konkurrierende Timereffekte nach 02.35/02.73 konfliktprüfen und atomar revalidieren. Cross-Scene-Nodes benötigen weiterhin gültige typisierte Kanten und Rechte aus 02.18–02.20.
7. **Bedienung und isolierte Simulation:** SL kann wirksame Zeitbasis, Erbquelle, Pausenursache, gespeicherte Fälligkeit, Status und möglichen Wiederanlauf im Debug nachvollziehen und konfigurationsgemäß übersteuern. Vorschau und isolierte Tests aus 02.31–02.34 müssen ohne echte Timerfortschritte, Spielzeitbuchung, Ressourcenänderung oder Folgewirkungen funktionieren.

### 4. Abnahmefälle für die spätere Implementierung

| Fall | Erwartetes fachliches Ergebnis |
| --- | --- |
| Bombe: 60 Sekunden Echtzeit, fünf Minuten Kampagnenpause | Echtzeit-Frist läuft entsprechend ihrer konfigurierten Policy ab; reales Ereignis nur nach gültiger Zustands-/Rechteprüfung und höchstens einmal |
| Dieselbe Bombe: 60 Sekunden aktive Spielzeit | Während einer für sie gültigen Spielpause verbraucht der Countdown keine Spielzeit; nach Wiederaufnahme mit korrekter Restzeit fortsetzen |
| Szene A pausiert, Szene B aktiv | Timer mit `scene_A`-Clock stehen entsprechend ihrer Policy; berechtigt unabhängige B-Timer laufen weiter |
| Zwei unabhängige Rätsel-Zugfolgen | Eine Runde in Kontext B verändert den rundenbasierten Timer A nicht |
| Einzelner Spieler offline, andere spielen weiter | Nur die wirksame Clock-/Fallbackpolicy entscheidet; kein pauschaler globaler Zeitstopp |
| Server nach Ablauf einer Echtzeitfrist wieder verfügbar | Fälligkeit wird einmalig klassifiziert, gegen aktuelle Rechte und Objektversion geprüft; keine blinde Folgeeffekt-/Replay-Lawine |
| Wiederkehrender Alarmtimer nach langem Serverausfall | Keine unbegrenzte Folge von Nachholalarmsignalen; zulässige Occurrences anhand Wiederanlaufpolicy begrenzen/deduplizieren |
| Timeränderung während des Countdowns | Bestandsschutz bzw. berechtigte Migration nach 02.25, mit Vorschau; weder Überraschungsreset noch rückwirkender Doppeleffekt |
| Reconnect oder zweimaliges Node-Ereignis | Derselbe Timer/Occurrence wird nicht mehrfach erzeugt bzw. ausgelöst |
| Geheime Falle mit Countdown | Unberechtigte Clients erhalten weder geheime Timerdaten noch Ziel-/SL-Metadaten |

**Abgrenzung:** Dies ist eine fachliche Architekturplanung, kein beschlossenes konkretes Scheduler-Framework, kein zwingender Echtzeitstandard für alle Timer und keine abschließende Definition sämtlicher Wiederholungs-/Queue-Grenzwerte. Bestehende Produktregel zur Akustiksimulation (02.51) bleibt unverändert; generelle modulare Deaktivierung und gesamte Kampagnen-Einstellungsführung weiterhin später.

## Archivierte Folgefrage 02.76 – inzwischen beschlossen: C

- **A – Immer strikt seriell:** Ein globaler Ausführungsstrom arbeitet sämtliche gleichzeitig fälligen Timer nacheinander nach einer festen Reihenfolge ab – auch bei unabhängigen Szenen.
- **B – Immer parallel:** Alle fälligen Timer lösen sofort gleichzeitig aus, ohne Konfliktkoordination zwischen gemeinsamen Objekten oder Ressourcen.
- **C – Konfigurierbare, konfliktgesicherte Verarbeitung (Empfehlung):** Pro Kampagnen-/Regelprofil, Timer-/Node-Typ, Szene und Kontext lässt sich die Verarbeitung ordnen bzw. priorisieren. Nachweislich unabhängige Effekte dürfen parallel ausgeführt werden; gemeinsame Figuren-/Objekt-/Ressourcenwirkungen werden atomar, versionsgesichert und vor Commit erneut geprüft. Bei Gleichstand oder Kollision greifen definierte Warte-/Ablehnungs-/SL-Policies, ohne Endlosschleifen oder unbeabsichtigte Offenlegung geheimer Events.

**Aktueller Fortgang:** **02.76 C** ist in [KARTEN-WORKSHOP-02.76.md](KARTEN-WORKSHOP-02.76.md) verbindlich geplant. **Als Nächstes 02.77:** Fehler- und Teilerfolgsfolgen mehrstufiger Node-Ketten.
