# AdventureShift – Karten-Workshop: Beschluss 02.76 C

**Stand:** 12.10.2026 – Beschluss 02.76 C; nachfolgende 02.77 C beschlossen, nächste offene 02.78  
**Status:** Verbindliche fachliche Entscheidung und Umsetzungsplanung, keine implementierte Funktion, keine finale API oder Datenbankmigration.  
**Bezüge:** [Karten-Hauptworkshop](KARTEN-WORKSHOP.md) · [Beschluss 02.74](KARTEN-WORKSHOP-02.74.md) · [Beschluss 02.75](KARTEN-WORKSHOP-02.75.md) · [Feature-Katalog](FEATURE-WORKSHOP.md)

**Nachfolgender Beschluss 14.7 C:** [Idempotente Job-/TimerDue-/WorldEffect-Recovery](SICHERHEIT-WORKSHOP-14.7.md) erhält die 02.76-Priorität/Occurrence-/Order-/WorldResource-Konfliktregel für gleichzeitig oder lange überfällige Fälligkeiten. WorkerRestart oder doppelte Queuezustellung darf keine weitere legitime Explosion, NPC-/ItemSpawn, Alarm-/Quest-/NextPlayerwirkung allein aus Prozesszeit erzeugen. V1 ein SL, konkrete Schedulerwerte später.

## 02.76 – Konfigurierbare, konfliktgesicherte Verarbeitung gleichzeitig fälliger Timer- und Node-Ereignisse

**Verbindlich beschlossen: Variante C.** Zeitgleich oder nahezu zeitgleich serverseitig fällige Timer, wiederkehrende Occurrences, Node-Impulse und zulässige verzögerte Folgeaktionen dürfen nicht pauschal alle seriell oder alle unkoordiniert parallel ausgeführt werden. Die Spielleitung kann **Kampagnen-/Regelprofilstandards** und ausdrücklich gekennzeichnete **Ausnahmen je Aktions-/Timer-/Node-Typ, Szene, Region, Zielobjekt und Turn-/Rätselkontext** definieren. Die jeweilige Regel bestimmt Ausführungsreihenfolge, Priorität und bei echter Kollision eine sichere Konfliktstrategie. Globale Änderungen und Bestandsschutz folgen 02.25. Die Konfiguration darf niemals Sicherheits-/Szenen-/Figurenrechte umgehen.

### 1. Konfigurierbare Verarbeitung

- **Nachweislich unabhängig parallel:** Timer-/Node-Effekte mit disjunkten und spielregelkonform kompatiblen Schreib-/Ressourcen-/Figuren-/Objektzuständen dürfen nebenläufig wirksam werden. Zwei räumlich getrennte Lampen in unterschiedlichen Szenen können gleichzeitig geschaltet werden. Eine andere Zugfolge allein beweist aber keine Unabhängigkeit, wenn dieselbe Tür, Figur, Munition, Inventarressource oder Alarm-/Queststatus gemeinsam betroffen ist.
- **Geordnet/serialisiert:** Ereignisse mit gemeinsamen exklusiven Zielzuständen werden nach wirksamer Priorität und stabil bestimmter Reihenfolge nacheinander **mit erneuter Prüfung unmittelbar vor dem Commit** verarbeitet. Die eingangs zuerst gemeldete Aktion garantiert keinen späteren Erfolg. Kein globaler Lock, der unabhängige Timer über alle Kampagnen oder Szenen unnötig anhält.
- **Priorität:** Regelprofile können definierte Kategorien bzw. Gewichtungen verwenden (beispielsweise sicherheitskritisches Türschließen, SL-Entscheidung oder gewöhnlicher Mechanismus). Der Grund für die Priorität muss nachvollziehbar sein; gültige Empfängerrechte, Objekt-/Sicherheitsbedingungen und bereits bestehende zwingende Regeln stehen oberhalb bloßer zeitlicher Reihenfolge. Eine niedrige Priorität darf nicht ohne zulässige Policy unbegrenzt verhungern.
- **Gleichstand:** Eine explizite, für den betroffenen Geltungsbereich gültige Tie-Break-Policy entscheidet stabil, z. B. über serverseitig dauerhaft zugewiesene Auslösungssequenz und eindeutige Ereignis-/Occurrence-ID. Client-Zeitstempel oder Netzwerkankunft allein sind keine vertrauenswürdige Autorität. Eine absichtlich zufällige Entscheidung käme nur nach gesondert gültiger Regel mit nachvollziehbarer, einmalig protokollierter Auswahl infrage; keine ungeprüften spontanen Neuversuche.
- **Konfliktfolgen:** Je gültiger Policy kollidierende Aufträge nach Neuprüfung ausführen, geordnet warten, sicher ablehnen, kontrolliert verwerfen oder SL-pending setzen. Ein Wartestatus erzeugt **noch keine** neue Türbewegung, Alarmwirkung, Würfelprobe, Ressourcenkosten, Spawnaktion oder Next-Player-Übergabe. Bei ausstehender SL-Freigabe aktuelle Situation erneut prüfen.
- **Typisierte Node-Signale:** Ereignisimpulse, anliegende boolesche Werte, Datensignale und Aktionsbefehle aus 02.17/02.20/02.21 dürfen nicht als gleichwertige konkurrierende Befehle behandelt werden. Ein gültiges Dauersignal wird nach seinem wirklichen Halt/Zustand beurteilt; Impulse müssen über eindeutige Occurrence-IDs verarbeitet werden; erlaubte Signalzusammenführung nur durch ausdrückliche kompatible Regel.
- **Wiederholende/überfällige Timer:** 02.16/02.75 entscheiden, *welche* konkreten Occurrences nach Pause/Neustart existieren und noch gültig sind. **02.76** priorisiert nur diese bereits legitim fälligen Occurrences; keine unbegrenzte Menge alter Ticks oder gratis neu erzeugte Events. Prioritäts-/Backlog- und Wiederholungsgrenzen bleiben konfigurierbar und sicher begrenzt, genaue Grenzwerte später.

### 2. Vollständiger konzeptioneller Prüfpfad

1. **Fälligkeit feststellen:** Der serverautoritativ gespeicherte Timer/Node-Trigger aus 02.15–02.16 und die wirksame Zeitbasis aus 02.75 erzeugen einen berechtigten Ausführungsauftrag mit Quell-/Trigger-/Occurrence-ID, Kampagnen-/Szenen-/Node-/Turnkontextbindung, Policyversion, Zielreferenzen und status-/turngenerationgebundenen Bedingungen. Gleiche erneute Zustellung derselben Occurrence erstellt keinen zweiten gültigen Auftrag.
2. **Schutz und Typvalidierung:** Existenz, aktive Regel-/Node-/Graphversion, Porttypen, Szenenrechte, zulässiger Quell-/Zielkontext und berechtigter Action-/Character-Owner werden zuerst geprüft. Nicht autorisierte Aufträge gelangen nicht durch eine hohe Priorität in die Ausführung.
3. **Konflikt- und Unabhängigkeitsgruppe:** Abhängigkeiten der betroffenen *echten* Weltobjekte, Figurenposition, Inventar-/Aktionsbudgets, Zustandslese-/Schreibzugriffe und Turngenerationen feststellen. Gemeinsame Ressource oder nicht beweisbare sichere Unabhängigkeit erfordern konfliktgesicherte Verarbeitung statt unkontrollierter Parallelität. Unabhängige Gruppen dürfen gemeinsam laufen.
4. **Effektive Priorität und Gleichstand:** Regel- und Overrideherkunft dokumentieren; nur für tatsächlich konkurrierende Aufträge einen nachvollziehbaren, stabilen Konfliktentscheid treffen. Eine gleichzeitige Fälligkeit ist kein automatisches Gleichrangigkeitsrecht und keine automatische Löschung einer zweiten Aktion.
5. **Pending ohne Weltwirkung:** Bei Warteschlange, SL-Freigabe oder Kontextpause geprüften Status/Fristen sichern. Zulässige Reservierungen bedürfen eigener geprüfter Regel; keine heimliche vorzeitige Tür-/Objektänderung oder Itemverbrauch. Wie ein fehlgeschlagener *Folgeschritt* einer mehrstufigen Node-Kette behandelt wird, entscheiden wir erst in 02.77.
6. **Unmittelbar vor Commit revalidieren:** Aktuelle Zielobjekt-/Tür-/Schloss-/Alarm-/Nodeversion, Spieler-/Figurenkontrolle, Szene und Position, aktiver Zugkontext/Turngeneration, Policy- und Ressourcenzustand prüfen. Auch nach serieller Wartezeit oder SL-Bestätigung darf ein veralteter Tür-/Next-Player-Befehl nicht blind wirken.
7. **Atomar und höchstens einmalig:** Gemeinsamen Spielweltzustand transaktional korrekt verändern und exakt *eine logisch gültige Wirkung je eindeutiger Occurrence/Effekt-ID* anerkennen, mit Deduplikation/versionsgebundenem Commit nach 02.35, 02.72–02.75. Folge-Node-/Alarm-/Spawn-/Turn-Ereignisse erst nach real bestätigter Quellwirkung und mit eindeutigem Ursprung ausgeben. Für externe Nachrichten/Transporte idempotente Empfänger-/Outbox-Semantik vorsehen: Kein pauschales Versprechen physisch genau einmaliger Netzwerkzustellung.
8. **Begrenzter Wiederanlauf:** Bei temporärem Versionskonflikt ein regelkonformer, begrenzter Retry mit neuen Zustands-/Rechteprüfungen oder definierter Warte-/SL-Entscheidung; keine endlosen Retries, unlimitierten Folge-Events, Priority-Starvation oder Node-Loops. Abgebrochene/veraltete Aufträge lösen keine späten Folgewirkungen aus.
9. **Sichtbarkeit/SL-Debug:** Vollständige Prioritäts-/Konflikt-/Abhängigkeits-/Versionierungs- und Fehlgründe nur für berechtigte SL; Spielerclients erhalten lediglich freigegebene Effekte und bereinigte Status. Keine Rückschlüsse auf geheime Timer, NPCs, Fallen, Rätsel, Würfelproben oder verborgene Szenen über Queueposition, Fehlermeldungen oder Reconnect.
10. **Simulierbarkeit:** Die drei Node-Ansichten und der einfache Regelassistent aus 02.14/02.27 benutzen dieselben Regeldefinitionen. SL-Debug aus 02.31 und isolierte Test-/Freigaberegeln aus 02.32–02.34 zeigen nachvollziehbar fällige Aufträge, Konfliktgruppen, effektive Policy, Gewinner/Verlierer, Replaystatus und tatsächliche Effekte. Tests verändern keine echte Welt, Zeitbasis oder Turngeneration.

### 3. Daten- und Implementierungsplanung (noch nicht programmiert)

**Konzeptionelle Platzhalternamen:** `DueEvent`/ `EventOccurrence`, `ExecutionPolicy`, `ConflictGroup`, `PendingEffect`, `EffectCommitRecord` und `EffectDispatch`. Die finalen Datentabellen, Locks, Serialisierungsalgorithmen, Scheduler, APIs, Zahlwerte und Infrastruktur werden erst beim technischen Design verbindlich ausgewählt.

Notwendige fachliche Angaben je Auftrag: unveränderliche Quell-/Event-/Occurrence-ID, Eigentümer-/Kampagnen-/Szenen-/Turnkontext, Fälligkeitsclock aus 02.75, Policy-ID und wirksame Policyversion, Ziel- und Ressourcenzustandsversionen, betroffene typisierte Ports, serverseitige Ordnungskennung, ggf. Prioritätsklasse/Tie-Break-Ergebnis, Status (fällig, wartend, SL-pending, verarbeitet, abgelehnt, verworfen), deduplizierbarer Wirkungsschlüssel und berechtigte Audit-Daten. Sensible Felder niemals vollständig an unberechtigte Clients übertragen.

**Vorgesehene Umsetzungsschritte:** (1) Gemeinsames fachliches Event-/Effekt- und Rechte-/Prioritätsmodell mit 02.35/02.73/02.75 vereinbaren; (2) Konfliktanalyse und atomare Einmalwirkung implementieren, inklusive typisierter Graphports und unabhängig paralleler Kontexte; (3) Pending-/SL-/Timeout-/Retry- und Neustartpfad integrieren, wobei 02.77-Folgeschrittregeln offen bleiben; (4) SL-Vorschau/Diagnose/Simulator und automatisierte deterministische Race-/Replay-/Sicherheits-/Lasttests erstellen. Die Reihenfolge ist Planungsgrundlage, noch keine MVP-Freigabe.

### 4. Abnahmefälle

| Szenario | Erwartete Wirkung |
| --- | --- |
| Tür-Öffnen und Tür-Schließen gleichzeitig durch zwei Timer | Nur gültiger, konfliktgesichert priorisierter/serialisierter Effekt mit aktueller Objektprüfung wirkt; finale Türversion und eventuelle Folgeports passen zusammen |
| Unabhängiger Alarmtimer gleichzeitig mit derselben Tür-Kollision | Alarm darf unabhängig ablaufen, sofern er wirklich keine exklusiven Zustände/Ressourcen mit dem Türkonflikt teilt |
| Zwei Ereignisse mit exakt gleicher Priorität | Dokumentierte stabile Tie-Break-Regel oder ausdrücklich gültiger SL-/Wartepfad; weder Client-Uhr noch zufälliger Netzwerk-Replay entscheiden |
| Zwei Szenen mit je unabhängiger Tür und Timer | Parallele gültige Effekte ohne unnötige kampagnenweite Blockade |
| Zwei Timer verbrauchen dieselbe letzte Itemladung oder verändern dieselbe Figur | Keine Doppelabbuchung oder zwei widersprüchliche bestätigte Figurenpositionen |
| Fälliger Next-Player-Impuls trifft nach anderem Zugwechsel ein | Turngeneration neu geprüft; keine zweite unberechtigte Übergabe |
| Timer nach Serverneustart doppelt zugestellt | Gleiche Occurrence höchstens einmal logisch wirksam; ältere ungültige Ereignisse nach 02.75 kontrolliert verworfen oder zurückgestellt |
| Dauerwert eines gehaltenen Tasters und gleichzeitiger Türimpuls | Typisierte Signale und physisch gültiger Haltezustand nach 02.21–02.22/02.74 geprüft; keine willkürliche Impuls-/Boolean-Vermischung |
| Wartende Aktion verliert Zielberechtigung oder SL-Freigabe wird spät erteilt | Keine Ausführung ohne frische Rechte-/Objekt-/Ressourcenvalidierung |
| Geheimes Fallenereignis verliert die Priorität | Unberechtigte Spieler erfahren nicht, dass ein versteckter Timer/Fallen-Node konkurriert hat |
| Loop/100-fach aufgeholter wiederkehrender Timer | Schutz gegen Event-Sturm, deterministische begrenzte Wiederanlaufpolicy, keine unlimitierten Spawn-/Alarm- oder Wiederholungsnebenwirkungen |
| Isolierte SL-Simulation mit drei parallelen Effekten | Deterministisch erklärbarer Ablauf, tatsächlicher Serverzustand bleibt unverändert |

### 5. Grenzen und spätere Entscheidungen

- **02.35 bleibt gültig:** Objektbezogene Konfliktstrategien sind bereits beschlossen; 02.76 spezifiziert zusätzlich *fällige Zeit-/Node-Occurrences, konkurrierende Ausführung und Wiederanlauf*, ohne eine zweite widersprüchliche Regelwelt zu erzeugen.
- **02.75 bleibt gültig:** Sie entscheidet Zeitbasis und Zulässigkeit aufgelaufener Timer-Occurrences; 02.76 verarbeitet nur bereits legitim eingereihte Fälligkeiten.
- **02.74 bleibt gültig:** Ein ausstehender Timer kann eine verbotene Figurenaktion nach Zugende nicht reaktivieren.
- **Nicht vorwegnehmen:** Numerische Prioritätsstufen, Fairnessgrenzen, Backoff-Fristen, Ressourcenreservierungen und kampfspezifische Kosten/Initiative folgen technischen bzw. Fach-Detailrunden (03/05/07). Allgemeiner Kampagnenassistent und generelle Modulabschaltungen erst nach allen Featurethemen; ausdrücklich beschlossene Akustik-Option 02.51 bleibt.
- **Folgeentscheidung 02.77 C inzwischen beschlossen:** Konfigurierbare Fach-Erfolgs-/Misserfolgs-/Folgepfade und sichere Teilwirkungen in verbundenen Node-Ketten; zentrale technische Systemfehler außerhalb des Graphen. Siehe [02.77 C](KARTEN-WORKSHOP-02.77.md). Nächste offene Frage: **02.78**.

## Archivierte Folgefrage 02.77 – inzwischen beschlossen: C

**Verbindliche Teilvorgaben inzwischen ergänzt:** Check-Nodes besitzen reguläre Erfolg-/Misserfolg-Ausgänge; bei optional aktiviertem erweitertem Ergebnismodus sind frei benannte Würfelbereiche/mehrere Ports einschließlich möglichem Jackpot erlaubt. Natural-20-/kritische Sonderfälle werden nur bei ausdrücklich aktiviertem Regelprofil verarbeitet. Systemfehler bleiben außerhalb regulärer Ergebnisports. **Testdarstellung:** orangefarbener Rahmen für relevanten nicht angeschlossenen Ausgang, normale Testpfade nur am Rahmen, bei echtem technischen Systemfehler die komplette Node rot. Siehe [02.77 Teilvorgaben](KARTEN-WORKSHOP-02.77-TEILBESCHLUESSE.md). **Die nachfolgende historische A/B/C-Auswahl wurde inzwischen durch Beschluss [02.77 C](KARTEN-WORKSHOP-02.77.md) verbindlich entschieden.**

**Beispiel:** Tür öffnen → Alarm zurücksetzen → Licht aktivieren. Die Türöffnung funktioniert, aber der Alarm lässt sich wegen fehlender Berechtigung nicht zurücksetzen.

- **A – Immer gesamte Kette stoppen:** Jeder Fehler beendet sofort die restliche Node-Kette; bereits wirksame vorherige Schritte werden nicht ohne eigene Regel rückgängig gemacht.
- **B – Immer weitere Schritte versuchen:** Fehler einzelner Schritte werden ignoriert, alle folgenden Nodes laufen weiter – auch wenn ihr benötigter Eingangserfolg fehlt.
- **C – Konfigurierbare Fehler-/Folgepfade (Empfehlung):** Pro Kampagne, Regelprofil, Kette, Node und geeigneter Aktion definierbar: bei Erfolg weiter, bei Fehler stoppen, expliziten Fehlerzweig auslösen, regelkonform erneut versuchen, auf SL warten oder – bei ausdrücklich vorbereiteter und sicher möglicher Rückabwicklung – geeignete Teilaktionen kompensieren. Bereits endgültig wirksame Welt-/Ressourcen-/Würfel-/Zugeffekte dürfen nicht automatisch oder heimlich rückgängig gemacht werden.
