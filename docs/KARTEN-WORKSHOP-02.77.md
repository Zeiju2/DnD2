# AdventureShift – Karten-Workshop: Beschluss 02.77 C

**Stand:** 12.10.2026 – Beschluss 02.77 C; inzwischen auch 02.78 C beschlossen, als Nächstes 02.79  
**Status:** Verbindlich beschlossene Fachfunktion und Umsetzungsplanung. Noch keine Softwareimplementierung, endgültige API oder Datenbankmigration.  
**Bezüge:** [Hauptworkshop](KARTEN-WORKSHOP.md) · [02.76](KARTEN-WORKSHOP-02.76.md) · [02.77 Teilbeschlüsse](KARTEN-WORKSHOP-02.77-TEILBESCHLUESSE.md) · [02.78 C](KARTEN-WORKSHOP-02.78.md) · [Feature-Katalog](FEATURE-WORKSHOP.md)

## 02.77 – Fachliche Fehler- und Folgepfade in mehrstufigen Node-Ketten

**Verbindlich beschlossen: Variante C.** Wenn in einem bereits teilweise ausgeführten Node-Graphen ein fachlicher Teilschritt fehlschlägt oder eine Check-Node einen regulären Misserfolg ausgibt, kann dessen Fortsetzung abhängig von der wirksamen **Kampagnen-/Regelprofil-, Ketten-/Untergraph-, Szenen-, Node- und Aktionspolicy** konfiguriert werden. Möglich sind: anhalten; nur über den tatsächlich gewählten, typisierten Ergebnisport weiterleiten; erlaubte alternative Folgeaktionen auslösen; eine ausdrücklich erlaubte, begrenzte Wiederholung versuchen; auf eine berechtigte SL-Entscheidung warten; oder nur ausdrücklich vorbereitete und aktuell sichere Kompensationsaktionen ausführen. Kampagnenstandard, markierte Ausnahmen sowie Vorschau und Bestandsschutz nach 02.25 gelten. Die Optionen dürfen keine Spiel-/Serverrechte umgehen.

### 1. Fachliche Ausgänge, Krit-Ergebnisse und Systemstörungen trennen

- **Normale Checks:** `Erfolg` und `Misserfolg` sind die beiden Standard-Ergebnisausgänge von Check-Nodes. Der zu niedrige Würfelwurf ist ein **reguläres Spielergebnis**, kein technischer Fehler. Die echte Probe folgt weiterhin 02.63–02.66 (gültiger Würfel-/Skillwert plus numerischer Mindestwurf, Gleichstand Erfolg) und verwendet stabile serverseitige Check-/Wurf-IDs.
- **Optionale Ergebnisbereiche:** Der Spielleiter aktiviert per gesondertem Häkchen an der geeigneten Check-/Zufalls-Node mehrere frei benennbare Ergebnis-Ranges und passende Ports. Beispiel Glücksspielautomat: Niete, Kleingewinn, Großgewinn oder Jackpot; die tatsächlichen Würfelbereiche legt das Regelprofil selbst fest. Ob Rohwurf, Gesamtwert oder Differenz zur Schwierigkeit gilt, wird ausdrücklich gespeichert. Eine reine Zufalls-/Gewinn-Node braucht keinen vorgeschriebenen Skillcheck.
- **Kritische Sonderfälle:** Natural 20, kritischer Erfolg, kritischer Misserfolg oder andere besondere Würfelwerte gelten **nur bei ausdrücklich aktiviertem, geeigneten regelabhängigen Krit-Profil**. Kein allgemeiner W20-Zwang, keine automatische Jackpot-, Erfolg- oder Patzerregel. Überlappende Ranges und Krit-Vorrang vor Aktivierung eindeutig validieren.
- **Fachliche Ablehnung:** Eine nicht erfüllte Bedingung, blockierte Tür, fehlende Reichweite, falsche Aktionsvoraussetzung oder unzulässige Figurenzughandlung kann ein vorgesehener typisierter fachlicher Status sein. Fachliche Ablehnung wird nicht als kritischer Würfelfehlschlag ausgegeben; nur die zulässigen, ausdrücklich verkabelten Status-/Alternativports wirken.
- **Echte Systemfehler außerhalb der Spiel-Nodes:** Code-Ausnahmen, beschädigter interner Zustand und technische Persistenz-/Runtime-Fehler werden zentral ausfallsicher behandelt, nicht über gewöhnliche `Misserfolg`-, `kritisch`, `Niete`- oder `Jackpot`-Ports geroutet. Kein automatisches Gratis-Neuwürfeln, doppelte Ausgabe oder unbeabsichtigter Node-Folgeeffekt durch technischen Retry.

### 2. Fortsetzungsregeln einer fachlich fehlgeschlagenen Kette

1. **Nur bestätigte Resultate verzweigen:** Ein Port `Tür geöffnet` wird erst bei einem wirklich erfolgreichen, autorisierten Türzustandswechsel aktiviert. Die bloße Anfrage oder ihre spätere Ablehnung ist kein Öffnungserfolg. Gleiches gilt für Alarm-, Item-, Skill- und Next-Player-Wirkungen.
2. **Kette stoppen:** Die wirksame Regel darf bei einem bestimmten Fachausgang den restlichen Pfad beenden. Ein nicht verbundener Ausgang beendet nur den betroffenen Zweig und wird im Test orange am **Rahmen** markiert; er ist nicht automatisch ein Codefehler.
3. **Alternativen:** Misserfolgs-, Jackpot-, Teil-Erfolgs- oder andere benannte Fachports dürfen ihre eigenen, kompatiblen Folge-Nodes auslösen. Ein gescheiterter Schritt macht nicht automatisch alle anderen bedingungsunabhängigen Schritte ungültig. Es entstehen keine unberechtigten positiven Ausgangssignale.
4. **Begrenzte Wiederholung:** Wiederzustellung derselben technischen Aktion referenziert dieselbe Check-/Occurrence-/Effekt-ID und führt nicht zu einem neuen Wurf oder Kostenverbrauch. Ein **wirklich neuer Spielversuch** mit erneutem Würfeln darf nur durch eine neue, ausdrücklich berechtigte Spieler-/Regelaktion mit eigenen gültigen Kosten und Rechten entstehen. Retryzahl, Gültigkeitsdauer und Schleifenschutz müssen begrenzt sein; Zahlenwerte später.
5. **SL-Freigabe:** Pending-Zustand speichert gültige Kampagnen-/Figuren-/Ketten-/Node-/Regel-/Turn-/Objektversionen, hat aber selbst **keine** reale Wirkung. Eine nachträgliche Freigabe benötigt aktuelle Spieler-/SL-, Szenen-/Objekt-/Ressourcen-/Turnrechte und eine erneute Zielprüfung.
6. **Teilerfolge:** Ein bereits bestätigter Schritt darf nicht stillschweigend unwirksam geschrieben werden, wenn ein späterer fachlicher Schritt scheitert. In verteilten Graphketten über Szenen, NPCs, Items und Turn-Kontexte existiert kein magischer pauschaler Komplett-Rollback.
7. **Explizite Kompensation:** Nur für dafür geeignete vorherige Effekte kann ein bewusst konfigurierter Folgepfad eine **neue**, berechtigte und aktuelle umkehrende Aktion ausführen, z. B. eine offen gebliebene Tür erneut schließen, sofern dabei niemand gefährdet oder eingeschlossen wird. Bereits geschehene Würfe, verbrauchte Ressourcen, offengelegte Informationen, ausgelöste Nachrichten oder bereits abgeschlossene Zugwechsel nicht rückwirkend aus der Historie entfernen. Nicht kompensierbare Teilwirkungen bleiben sichtbar als Teilwirkung dokumentiert.
8. **Rechte/Versionen/Einmalwirkung:** Jede spätere Wirkung gegen aktuelle Figurenkontrolle, Sichtbarkeit, Ziel-/Objektzustand, Turngeneration, Ressourcen, gültige Node-/Kanten-/Porttypen und wirksame Policy unmittelbar vor Commit serverautoritativ revalidieren. Eindeutige GraphExecution-/NodeInvocation-/Check-/Branch-/Effect-IDs (nur Entwurfsbegriffe), idempotente Events und atomare bestätigte Effekte nach 02.35/02.72–02.76. Geheime NPCs und Wahrnehmungschecks bleiben vor unberechtigten Spielerclients vollständig verborgen.

### 3. Diagnose und Darstellung

Die zuvor ausdrücklich festgelegte Testdiagnose bleibt verbindlich und gilt einheitlich für die drei Node-Ansichten (02.27) sowie isolierte Event-/Node-Tests (02.31–02.34):

| Befund | Darstellung |
| --- | --- |
| Regulärer Spiel-Erfolg, Misserfolg, Jackpot oder anderer fachlicher Ergebniszweig | Bei Testhervorhebung **nur Node-Rahmen** einfärben; normale Füllung |
| Im Test relevanter, nicht verbundener Fachausgang | **Orangefarbener Rahmen**, normale Füllung, konkret benannten Ausgang anzeigen |
| Echter technischer Systemfehler | **Ganze Node rot einfärben**, einschließlich Füllfläche; Rot hat Vorrang vor Orange; technische Details nur berechtigt |

Farben werden durch klare Texte/Icons ergänzt; Porttypenfarben (02.20) nicht umdeuten. Vollflächig rote Nodes behalten ausreichenden Textkontrast. Fachliche Misserfolge sind **niemals** rote technische Fehler. Durch geheime Nodes, vertrauliche Checks und die Fehlermeldung darf kein Spieler unberechtigte Informationen erhalten.

### 4. Implementierungsplanung (noch kein Code)

- **Daten-/Regelmodell:** Versionierte, stabile typisierte Ausgangsports, Check-/Result-/Range-/Crit-Profil und Ketten-/Folgepolicy aus bisherigen Entscheidungen zusammenführen, inklusive Herkunft geerbter Standards und individueller Ausnahmen. Einfacher Regelassistent (02.14) und visueller Node-Editor benutzen dasselbe Modell.
- **Ausführung:** Pro realer Check-ID kanonisches einmaliges RNG-/Skill-/Mindestwurf-Ergebnis auswerten, genau einen eindeutigen fachlichen Port wählen; unabhängige Graphzweige und konkurrierende Ressourcen nach 02.35/02.73/02.76 behandeln. Sichere begrenzte Pending-, Retry-, Abbruch-, Alternativ- und ausdrücklich zulässige Kompensationspfade.
- **Zentrale Technikstörungen:** Systemfehler separat abfangen und mit sauberem Audit, Transaktionsschutz und Debugstatus versehen; keine regulären Spielports und keine kostenlose Wiederholung einer verbrauchten Probe. Für externe Side Effects idempotente Effect-Dispatch-/Outbox-Semantik statt unbelegtem absolutem Exactly-once-Netzwerkversprechen.
- **SL-Tests/Abnahme:** In isolierter Simulation prüfen: Wurf unter/gleich/über Mindestwurf, Jackpot aus freier Range, ausgeschaltete/eingeschaltete Krit-Sonderfälle, nicht verbundener Ausgang mit **orangefarbenem Rahmen**, echter Code-/DB-Fehler mit **vollständig roter Node**, Erfolg vor späterem fachlichen Fehlschritt, zulässiger Alternativzweig, fehlende Rechte bei spätem SL-Approval, vermeintlicher Rollback irreversibler Wirkung, Retry/Duplikat mit nur einer Check-/Effekt-ID, geheimen Wahrnehmungscheck und parallele Ketten. Kein Test ändert reale Türen, Figuren, Inventare, Würfel oder Turngenerationen.

### 5. Abnahmebeispiele

**A – Tür und Alarm:** `Tür öffnen → Alarm zurücksetzen → Licht einschalten`. Tür öffnet tatsächlich, Alarm-Reset wird fachlich wegen fehlender Berechtigung abgelehnt. Je wirksamer **02.77 C-Kettenpolicy** wird der betroffene Zweig beendet, der geeignete fachliche Ablehnungszweig ausgelöst oder nach SL-Freigabe korrekt erneut geprüft. **Die geöffnete Tür bleibt offen**, sofern kein ausdrücklich erlaubter, frisch geprüfter Kompensationsschritt sie wieder schließen darf. Das Licht erhält keinen fiktiven Erfolgsimpuls vom fehlgeschlagenen Alarm-Reset.

**B – Glücksspielautomat:** Bei optional aktiviertem Mehrfach-Ergebnismodus wird abhängig vom echten, serverseitigen Würfelrohwert genau `Niete`, `Kleingewinn`, `Großgewinn` oder `Jackpot` ausgewählt. Jackpot nur nach konfigurierter Range/Kritregel, kein automatischer Natural-20-Bonus; exakt eine echte Gewinnbuchung je Check-/Occurrence-ID.

**C – Technikstörung:** Eine Node wirft intern eine Ausnahme. Die regulären Spielausgänge feuern nicht, die betroffene Node ist im berechtigten Event-/Node-Test **vollflächig rot**. Audit und sichere Isolierung statt eines Misserfolgports oder einer unbeabsichtigten neuen Würfelprobe.

**D – Nicht verkabelter Fachausgang:** Eine gültige `Misserfolg`-Node führt nirgendwohin. Beim Test wird **nur der Rahmen orange**; die Node-Füllung bleibt normal und das Ereignis ist kein Programmfehler.

**Beschlussgrenze:** Damit sind die bislang dokumentierten Teilvorgaben und die **Hauptentscheidung 02.77 C abgeschlossen**. Weitere Detaillierung der Zahlwerte, Queues, UI und technischen APIs folgt in der späteren Umsetzung. Insbesondere werden **nicht** alle fachlichen Misserfolge als zentrale Systemexceptions behandelt.

## Archivierte Folgefrage 02.78 – inzwischen als C beschlossen

**Mehrere Reaktionen pro Auslöser sind bereits seit 02.13 beschlossen; ob sie grundsätzlich möglich sind, stand nicht erneut zur Wahl.** Die damals offene Frage, *wie* mehrere verbundene Folge-Nodes desselben gültigen Ausgangs gemeinsam starten und fortschreiten, wurde inzwischen als **02.78 C** verbindlich beschlossen und in [KARTEN-WORKSHOP-02.78.md](KARTEN-WORKSHOP-02.78.md) dokumentiert. Die nachfolgenden A/B/C-Optionen sind ein historischer Fragenstand.

**Beispiel:** Ein erfolgreicher Schalter-Impuls soll gleichzeitig die Beleuchtung einschalten, einen Alarm deaktivieren und eine Tür öffnen.

- **A – Immer streng nacheinander:** Alle Nachfolger eines Ausgangs werden ungeachtet der Unabhängigkeit in einer festen Reihenfolge gestartet.
- **B – Immer gleichzeitig:** Alle Nachfolger beginnen sofort ungeordnet parallel, selbst wenn sie dieselben Ressourcen oder Zielobjekte berühren.
- **C – Konfigurierbare Verzweigungs-/Ausführungsstrategie (Empfehlung):** Je Kampagnen-/Regelprofil, Node-/Port-/Untergraph und Szene wählbar: geeignete unabhängige Nachfolger parallel; definierte Reihenfolge/Abhängigkeiten; ggf. ausdrücklich gewählte alternative Ziele. Gemeinsame Weltobjekt-/Ressourcenkonflikte nach 02.35/02.73/02.76 atomar behandeln und bei fachlichen Fehlern der Nachfolger die beschlossene 02.77-C-Policy anwenden. Ursprungsevent und Nachfolger-IDs deduplizieren, keine Folge-Nodes mehrfach aktivieren.

**Aktuelle Fortsetzung:** **02.78 C** ist beschlossen; als Nächstes folgt **02.79**, die Synchronisierung mehrerer bereits gestarteter, auf eine gemeinsame Folge-Node zulaufender Zweige. Siehe [02.78 C](KARTEN-WORKSHOP-02.78.md).
