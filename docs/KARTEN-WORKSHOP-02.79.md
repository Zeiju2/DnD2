# AdventureShift – Karten-Workshop: Beschluss 02.79 C

**Stand:** 12.10.2026 – Beschluss 02.79 C; Folgeentscheidung 02.80 C ebenfalls beschlossen, als Nächstes 02.81  
**Status:** Verbindliche Fachentscheidung mit Umsetzungsschritten und Abnahmetests; weiterhin keine Programmierung, finale API oder festes Datenbankschema.  
**Bezüge:** [Karten-Hauptworkshop](KARTEN-WORKSHOP.md) · [02.77 C](KARTEN-WORKSHOP-02.77.md) · [02.78 C](KARTEN-WORKSHOP-02.78.md) · [02.80](KARTEN-WORKSHOP-02.80.md) · [Feature-Katalog](FEATURE-WORKSHOP.md)

## 02.79 – Konfigurierbare Synchronisierung mehrerer bereits gestarteter Node-Zweige

**Verbindlich beschlossen: Variante C.** Wenn mehrere zuvor getrennt gestartete, zulässige und gegebenenfalls parallel verlaufende Zweige einer gemeinsamen Folge-Node bzw. Join-/Sammel-Node zustreben, kann die Spielleitung je **Kampagnen-/Regelprofil** sowie mit ausdrücklich markierten **Join-/Node-, Ketten-/Untergraph-, Szenen-, Zweig- und geeigneten Turn-/Rätselkontext-Ausnahmen** festlegen, **welche Teilresultate wann genügen, um den gemeinsamen Folgepfad genau einmal freizugeben**. Vorschau, geerbte Bestandsregeln und Ausnahmeschutz folgen 02.25. Die seit 02.17 bestehenden UND/ODER/NICHT-Bedingungen bleiben gültig; 02.79 behandelt *konkrete Laufzeitinstanzen und deren Abschluss*, nicht erneut die Existenz boolescher Verknüpfungen.

### 1. Konfigurierbare Join-Strategien

- **Alle erforderlichen Zweige:** Ein Join startet erst, wenn alle ausdrücklich erwarteten, noch gültigen Zweiginstanzen die jeweils zulässigen Ergebnisse geliefert haben. „Alle“ bezieht sich auf die bei diesem Vorgang festgelegte, versionierte erwartete Menge – nicht blind auf jeden irgendwann im Editor sichtbaren Port und nicht auf alte Ergebnisse anderer Auslösungen.
- **Mindestens einer (Any):** Ein einziger fachlich passender, gültiger Abschluss eines erwarteten Zweiges kann den gemeinsamen Pfad genau einmal freigeben. Nicht autorisierte Ergebnisse und bloße „gestartet“-/„wartend“-Status zählen nicht als gültiger Abschluss.
- **Ausdrücklich ausgewählte Zweige:** Nur konkret benannte erforderliche Ports/Kanten/Zweiginstanzen müssen ein zutreffendes Ergebnis liefern; andere optionale Zweige ändern die Bedingung nicht unbemerkt.
- **Mindestanzahl/Quorum:** Eine vorgegebene Anzahl **unterschiedlicher, erwarteter** Zweiginstanzen mit geeignetem tatsächlichem Resultat genügt. Ein mehrfach zugestelltes Ereignis oder wiederholter identischer Zweig zählt niemals als mehrere Stimmen. Ein konfigurierter Grenzwert muss zur erwarteten Menge passen und darf die autorisierte Ergebnisvalidierung nicht umgehen.
- **Ergebnisfilter:** Für jede Strategie können die erforderlichen Ergebnisarten/Porttypen (z. B. nur bestätigter Erfolg, bestimmte alternative Ergebnisrange, bewusst zugelassener fachlicher Misserfolg) und ggf. Kombinationen pro Zweig festgelegt werden. Ein regulärer Fehlwurf ist kein technischer Fehler; er zählt nur, wenn seine fachliche Ergebnisart ausdrücklich geeignet ist. Jackpot-/Krit-Ausgänge aus 02.77 zählen ausschließlich gemäß aktiviertem Profil.
- **Kein automatisches Ergebnis-Recycling:** Frühere erfolgreiche Zweige eines älteren Schalterereignisses zählen nicht für einen neuen Join, sofern keine spätere ausdrücklich entwickelte und berechtigte dauerhafte Zustands-/Signalbedingung statt Ereignis-Join vorliegt. Dauer-Bool-Signale aus 02.20–02.21 sind von abgeschlossenen Event-Occurrences zu trennen.

### 2. Herkunft, Status und einmalige Freigabe

1. **Eine bestimmte Join-Instanz:** Der gültige Auslöser/Fan-out aus 02.78 erhält eine eindeutige `RootEventId`/`GraphExecutionId`, daraus eine eindeutige `JoinInstanceId` (nur Entwurfsnamen), samt gültiger Kampagnen-/Graphversion, Szenen-/Turnkontext, Ursprungsereignis, Ketten-/Ziel-Node-/Portreferenzen, wirksamer Join-Policyversion und genau den erwarteten Zweig-IDs. Parallele Spielerhandlungen oder wiederkehrende Timer bekommen verschiedene Instanzen; Reconnect desselben Ereignisses benutzt dieselbe.
2. **Gezielt verknüpfte Nachfolger:** Jeder Zweig aus 02.78 meldet einen eindeutig seiner Kante/NodeInvocation/Check-ID zugeordneten fachlichen Status (etwa wartend, erfolgreich, fachlich abgelehnt, gescheitert, abgebrochen oder passend abgeschlossen). **Ausgangsport, Ergebnis und tatsächlicher Commit unterscheiden**, keine Meldung „gestartet“ als Erfolg verbuchen. Nur explizit zum aktuellen Join gehörende Ergebnis-IDs werden angenommen.
3. **Schreib-/Lese- und Zugrechte:** Vor Aufnahme eines Teilresultats und erneut vor realem gemeinsamen Folgeeffekt tatsächliche Node-/Objekt-/Figuren-/Szenen-/Turn-/Regelrechte und gültige Versionen prüfen. Ein eingehender gleichnamiger Port aus einem fremden Kontext, einer anderen Schalterbetätigung oder einer geheimen nicht erlaubten Szene darf die Join-Bedingung nicht erfüllen.
4. **Erfüllung atomar prüfen:** Erforderliche passende Resultate werden versioniert und dedupliziert gesammelt. Die Join-Transition von `pending` zu `satisfied`/\`resolved` und die berechtigte Einreihung des Folgeports sind **atomar/idempotent** – auch wenn mehrere Zweige praktisch zeitgleich beenden. Der eine gemeinsame Folgepfad wird pro gültiger Join-Instanz höchstens **einmal logisch ausgelöst**; gleiche Lieferung, Reconnect und Serverneustart zählen nicht neu.
5. **Zeitbasis und Pause:** Warten, Fristen und Timeouts verwenden explizit erlaubte Echtzeit-/aktive Spiel-/Szenen-/Kontext-/Rundenzeit aus 02.75 und gültige Kontextpausen; keine versteckte Umrechnung. Timeout ist eine fachliche Regelentscheidung, niemals von selbst ein Codefehler.
6. **Wenn Erfüllung unmöglich wird:** Ausfälle, abgebrochene required branches, nicht mehr erreichbares Quorum oder abgelaufene Fristen dürfen die Join-Node nicht unbemerkt ewig blockieren oder ungeprüft freigeben. Anwendbare, konfigurierbare 02.77-C-Fachpfade: den Join sicher beenden, in definiertem Pending halten, einen ausdrücklich geeigneten fachlichen Fehler-/Timeout-Ausgang wählen oder eine berechtigte SL-Entscheidung verlangen. Bereits erfolgte unabhängige Weltwirkungen werden dadurch nicht automatisch zurückgedreht.
7. **Was nach Freigabe mit anderen Zweigen geschieht:** Bei `any` oder erreichtem Quorum können unbenötigte Zweige noch laufen. Je gültiger Policy dürfen diese regelkonform zu Ende laufen, ausdrücklich kontrolliert abgebrochen oder bei berechtigter SL-Entscheidung gehalten werden. **Späte gültige Ergebnisse aktualisieren höchstens ihren berechtigten Verlauf/Auditstatus, niemals denselben Join erneut auslösen**, keinen bereits bestätigten Weltzustand automatisch rückgängig machen und dürfen andere vereinbarte Nebenwirkungen nicht unerlaubt stoppen. Fortsetzungs-/Abbruchschutz aus 02.74/02.77 gilt.
8. **Sichere gemeinsame Wirkung:** Selbst der erfüllte Join gibt nur eine zulässige *Anforderung* an den gemeinsamen Folgeknoten frei. Aktuellen Zielzustand, bereits geteilte Figuren-/Inventar-/Turngenerationressourcen und konkurrierende Aktionen nach 02.35/02.72–02.73/02.76 direkt vor Effect-Commit revalidieren; keine zusätzliche Gratisaktion, doppelte Auslösung oder unberechtigter Spawn-/Alarm-/Next-Player-Effekt.
9. **Systemfehler separat:** Defekte Join-/Persistenz-/Runtimeoperationen führen nicht zu einem normalen Würfel-Misserfolgport und nie automatisch zur Freigabe. Zentraler, geschützter Systemfehlerpfad aus 02.77; in berechtigter Event-/Node-Testanzeige echter Systemfehler **ganze Node rot**, normaler Testpfad nur **Rahmen**, relevant unverbundener Fachausgang **Rahmen orange**.
10. **Vertraulichkeit:** Unterdrückte/geheime Zweige, private Würfe, verdeckte NPCs und SL-internes Debug dürfen nicht über öffentliche Joinlisten, Portzahl, verzögerte Fehlermeldungen, Reconnect oder Timing-Details an andere Spieler offenbart werden. Berechtigte SL erhalten vollständige Ursachen-/Teilresultatansicht; der Spieler nur zulässige bereinigte Wirkungen.

### 3. Umsetzungsmodell und Implementierungsplan (noch nicht programmiert)

Konzeptionelle Platzhalternamen: `JoinPolicy`, `JoinInstance`, `ExpectedBranchSet`, `BranchReceipt`, `JoinOutcomeFilter`, `JoinResolution`, `JoinEffectDispatch`. Stabil und persistent vorgesehen: Quell- und Fan-out-IDs, Graph-/Regelversionen, erwartete Zweig-IDs, Anzahl/Bedingungen (alle, mindestens einer, n-aus-m, explizite Teilmenge), erlaubte Resultattypen, aktuelle gültige eindeutig verbuchte Eingänge, Warte-/Timeout-/Pausezustand, Freigabestatus, unveränderliche Effect-/Transition-ID und berechtigte Auditangaben. Keine Pflicht zu einer bestimmten Scheduler-/DB-/Queue-Bibliothek.

**Geplante Umsetzungsreihenfolge:** (1) gemeinsame stabile Join-/Branch-/Port-Identität und versionsgebundene Resultattypen mit 02.17/02.20/02.77/02.78 harmonisieren; (2) konfigurierbare Ergebnisfilter und All-/Any-/Quorum-/Subset-Evaluierung mit Typ-/Berechtigungsvalidierung; (3) persistente, atomare Einmalfreigabe und Replay-/Raceschutz; (4) Pause-/Timeout-/SL-/Abbruch- und spät eingehende Branchreceipts integrieren, inklusive sicherer Wiederaufnahme nach Serverneustart; (5) SL-Debug, einfache No-Code-Zusammenfassung und drei Graphansichten, isolierte Regressionstests nach 02.31–02.34. Konkrete Anzeigen, Schwellenwerte, Queue-/Speicherlimits und technische Datenstruktur bleiben für späteres Design.

### 4. Isolierte Abnahmefälle

| Szenario | Erwartetes fachliches Verhalten |
| --- | --- |
| Schalter startet Tür, Alarm und Licht; Join = **alle** | Erst nach drei gültigen, zur gleichen Auslösung gehörenden erforderlichen Ergebnissen einmaliger gemeinsamer Folgeimpuls |
| Derselbe Fan-out; Join = **mindestens einer** | Erstes zulässiges fachliches Ergebnis genügt; weitere Erfolge lösen den Join nicht nochmals aus |
| Join = „Alarm deaktiviert UND Tür offen“ | Licht-Zweig ist optional; er ersetzt weder Alarm- noch Türbestätigung |
| Join = „2 von 3“ | Zwei verschiedene zulässige abgeschlossene Zweige genügen; zweimal dasselbe Replayereignis zählt nur einmal |
| Ein benötigter Zweig scheitert fachlich | Nach definiertem 02.77-C-Fach-/Timeout-/SL-Pfad, kein fiktiver Erfolg und kein automatischer Rollback bestätigter anderer Weltwirkungen |
| Ein Zweig endet mit ausdrücklich erlaubt gewähltem „Misserfolg“ | Der Ergebnisfilter kann ihn als gültigen Abschluss behandeln; es ist kein Systemfehler |
| Ein Zweig ist ein geheimer Wahrnehmungscheck | Nur serverseitig oder berechtigt SL-seitig ausgewertetes Ergebnis; kein Existenz- oder Wurfleck an den Spieler |
| Zweite Schalterbetätigung vor Abschluss der ersten | Getrennte JoinInstance-/Root-IDs, keine Vermischung alter und neuer Branchresultate |
| Quorum erfüllt, anderer Zweig beendet später | Höchstens ein Folgeimpuls; anderer Zweig folgt eigener Abschluss-/Abbruchregel ohne heimliche Rückabwicklung |
| Zwei Zweige beenden in derselben Millisekunde | Atomare Status-/Versionsprüfung, nur ein Join-Commit trotz Race |
| Szene pausiert, Serverneustart während Warten | Clock-Policy/Joinstand persistiert, keine künstliche Timerfortschreibung oder Doppelaktivierung |
| Vorgeschriebene Zweige können Quorum nicht mehr erreichen | Sichere konfigurierbare Ablehnung/Timeout/SL-pending, kein endloser stiller Lock oder unerlaubte Freigabe |
| Fehlender relevanter Ergebnisausgang im Test | Nur Rahmen orange; echte technische Runtime-Störung färbt die komplette Node rot |
| Ketten in verschiedenen Turnkontexten nutzen gemeinsames Item | Keine doppelte Inventarabbuchung oder unerlaubte Next-Player-Übergabe |

### 5. Abgrenzungen und folgende Entscheidung

- **02.17** hat UND/ODER/NICHT-Bedingungen, **02.78** mehrere ausgehende Folgeaktionen bereits beschlossen. Diese Dinge werden nicht erneut zur Wahl gestellt. **02.79** klärt *eine konkrete Laufzeit-Synchronisierung* mit eindeutig korrelierten Zweiginstanzen.
- **02.77** entscheidet normale Fachfehler-/Kettenpfade; Systemfehler außerhalb des Spielgraphs. **02.35/02.73/02.76** bleiben Konflikt- und Ressourcenwächter. Das Enden einer Zwischenausführung verleiht keine neuen Spielerrechte.
- **Folgeentscheidung 02.80 C inzwischen beschlossen:** Laufende, wartende und teilwirksame Graphinstanzen dürfen nach gültiger Policy mit kontrolliert gültiger alter Version abschließen, sicher pausiert und explizit migriert oder kontrolliert abgebrochen werden. Neue Sicherheits-/Objekt-/Ressourcenrechte müssen vor späten Effekten weiterhin gelten. Siehe [02.80 C](KARTEN-WORKSHOP-02.80.md).

## Archivierte Folgefrage 02.80 – inzwischen als C beschlossen

**Beispiel:** Ein Rätsel läuft. Ein Timer ist aktiv, zwei Node-Zweige warten auf Ergebnisse und der Spielleiter bearbeitet die Verbindungen oder entfernt die noch wartende Tür-Node. Was geschieht mit diesen schon gestarteten Abläufen?

- **A – Immer bisherige Version fertiglaufen lassen:** Jeder bereits begonnene Ablauf verwendet seine beim Start gültige Graph-/Regelversion bis zum Ende, auch wenn der SL inzwischen Änderungen veröffentlicht hat.
- **B – Immer sofort aktuelle Version übernehmen:** Alle laufenden, wartenden und bereits teilweise ausgeführten Abläufe werden ungeprüft auf die neu veröffentlichte Graphversion umgestellt.
- **C – Konfigurierbar mit sicherer Versionierung (Empfehlung):** Je Kampagnen-/Regelprofil, Szene, Untergraph, Node/Aktionsart und Änderungsklasse bestimmen, ob bestehende Ausführungen auf ihrer gültigen Version kontrolliert fertiglaufen, pausiert/SL-bestätigt migriert oder sicher abgebrochen werden. Vor jeder späten tatsächlichen Weltwirkung aktuelle Rechte/Ziel-/Objekt-/Ressourcenbedingungen neu prüfen. Nicht mehr erlaubte Aktionen, entfernte Objekte, fehlende Ports oder Sicherheitsupdates dürfen durch einen alten Graph-Snapshot nicht automatisch wirksam werden; niemals doppelte Ressourcen-/Würfel-/Nodewirkungen.


**Aktueller Fortgang:** [02.80 C](KARTEN-WORKSHOP-02.80.md) ist verbindlich beschlossen. **Nächste Entscheidung 02.81:** Mehrere berechtigte Bearbeiter und kollisionssichere Zusammenarbeit am Node-Graphen.