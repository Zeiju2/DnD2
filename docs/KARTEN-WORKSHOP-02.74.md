# AdventureShift – Verbindlicher Beschluss 02.74 C (Ergänzung)

Diese Ergänzung dokumentiert Entscheidung **02.74 C** nach dem früheren Stand in [KARTEN-WORKSHOP.md](KARTEN-WORKSHOP.md). Die dort noch als offen bezeichnete Frage 02.74 ist damit **beschlossen**; als Nächstes folgt **02.75**.

## 02.74 – Laufende und ausstehende Aktionen beim Zugende (12.10.2026)

**Verbindlich beschlossen: Variante C.** AdventureShift behandelt beim gültigen Zugende jede bereits gestartete, haltende, zeitbasierte oder noch wartende Handlung gemäß einer konfigurierbaren Policy. Kampagnen-/Regelprofilstandard mit markierten Ausnahmen für Figuren, Aktionsarten, Szenen, Nodes und Turn-Kontexte nach 02.25. Ein Zugende ist weder pauschal der Abbruch aller laufenden Vorgänge noch eine unkontrollierte Erlaubnis für alle verspäteten Aktionen. Keine Implementierung oder finale API.

### 1. Zulässige Folgen eines Zugendes

- **Regelgerecht abschließen:** Eine zulässige, schon begonnene Handlung darf nach aktiver Regel begrenzt *vor* dem Zugwechsel fertig werden. Ungültige Aktionen oder endloses Blockieren einer Zugübergabe sind nicht erlaubt.
- **Fortsetzen:** Ausdrücklich autorisierte bestehende Handlungen oder ihre bereits ausgelösten Weltwirkungen dürfen auch nach dem Zugende weiterlaufen. Daraus entsteht weder ein neuer Zug noch ein zusätzlicher Angriff oder kostenloses Aktions-/Bewegungs-/Inventarbudget.
- **Pausieren:** Der Zwischenstand bleibt versioniert und nachvollziehbar ohne weitere unberechtigte Weltwirkung erhalten; Wiederaufnahme benötigt gültigen Auslöser und erneute aktuelle Prüfung.
- **Kontrolliert abbrechen:** Noch nicht wirksame Teile und Folgeports werden gestoppt, zulässige Reservierungen nach ihrer Regel freigegeben. Bereits rechtmäßig abgeschlossene Teilwirkungen werden nicht blind rückgängig gemacht oder erneut ausgeführt.
- **Auf SL-Freigabe warten:** Nur ausdrücklich berechtigte Spielleiter dürfen eine Aktion freigeben oder ablehnen. Freigabe ersetzt weder neue Zustands-/Rechteprüfung noch Ressourcenvalidierung.
- **Kein sicher definierter Fall:** Ohne anwendbare gültige Regel darf der Server alte Aktionen nicht blind weiterverarbeiten; sicher halten/ablehnen und im geschützten SL-Debug erklären.

Dies gilt für Zugende per Spieler, autorisierter SL-Aktion, gültiger Next-Player-Node 02.67–02.70, Ausfall-Fallback 02.69 oder berechtigtem Kontextwechsel 02.71. Aktionen bleiben dem richtigen Turn-Kontext, dessen Turngeneration und dem ursprünglichen Ereignis zugeordnet. Die Next-Player-Node bewegt nicht automatisch einen Token oder ändert ohne Transferpolicy andere Kontexte.

### 2. Halteaktionen, Timer und verzögerte Nodes

- **Schalter gedrückt halten:** Physisches Halten über das Zugende hinweg setzt nachweislich gültige fortdauernde Halte-/Präsenz-/Positionsbedingungen und eine erlaubende Regel voraus. Fehlt dies, endet der Halt mit definierter Freigabe oder Stopwirkung. Keine unbeabsichtigten „Geisterhände“.
- **Angestoßene Mechanismen:** Ein durch eine gültige Handlung ausgelöster autonomer Mechanismus (z. B. Alarmtimer, verzögerte Tür oder Countdown) kann nach einer *eigenen* gültigen Effektpolicy weiterlaufen, auch wenn der Zug des Auslösers endete. Ein Timerende allein legalisiert keine inzwischen verbotene Folgeaktion.
- **Ausstehende Interaktionen:** Queue-, Pause- und SL-Pending-Status bedeuten noch keine wirksame Tür-, Alarm-, Spawn-, Next-Player-, Würfel- oder Ressourcenaktion; reale Wirkung erst nach gültigem Commit.
- **Würfelproben:** Bestätigte Würfelchecks aus 02.63–02.65 behalten ihre Check-ID und ihr Resultat. Eine Pause oder Wiederaufnahme ist kein kostenloser neuer Wurf. Geheime Wahrnehmungsprüfungen und SL-Informationen bleiben gemäß 02.66 serverseitig geschützt.
- **Zeitberechnung:** Welche Timer bei Spielpause, Offline-Zeit oder Serverneustart weiterlaufen bzw. eingefroren werden, ist die *nächste* eigene Entscheidung 02.75; 02.74 trifft darüber keinen universellen Vorgriff.

### 3. Zustands-, Rechte- und Einmalwirkungsschutz

Konzeptionell versionierte ActionTurnEndPolicy und ActionLifecycle-Datensätze mit Aktion-/Trigger-/Figur-/Kontext-/Turngenerations-ID, Policyquelle/Override, Status und betroffenen Objekt-/Ressourcen-/Check-/Effekt-IDs; dies sind Platzhalter, kein festgelegtes Datenbankmodell. Mögliche Statusgruppen: angefragt, aktiv/haltend, pausiert, SL-pending, abgeschlossen oder abgebrochen/fehlgeschlagen.

Bei jedem späteren Effekt oder einer Wiederaufnahme **direkt vor der Wirkung** aktuelle Figurenkontrolle, Szenen-/Positionslage, ausdrücklich zulässige Handlungen nach Zugende, Node-/Turn-/Regelrechte, Objektversion und gemeinsame bzw. ausdrücklich kontextspezifische Ressourcen erneut serverseitig prüfen. Ein inzwischen abgelaufener Turn wird nicht durch einen älteren Auftrag wieder gültig; ein regelkonformer, ausdrücklich nachwirkender Effekt kann dagegen ohne neuen Spielerzug bestehen.

Echte Ressourcenbuchung und Weltwirkung bleiben atomar und höchstens einmalig (02.35, 02.72, 02.73): keine doppelte letzte Patrone, doppelte Itemladung, doppeltes Würfelresultat, zweiter Türimpuls oder wiederholter Next-Player-Wechsel bei Retry/Reconnect/Node-Schleife. Mehrere unabhängige Kontexte behalten ihre Zugfolgen; nur tatsächliche geteilte Figuren-/Weltobjekt-/Ressourcenkonflikte verknüpfen sie. Serverneustart oder nachträgliche SL-Freigabe sind keine Erlaubnis, veraltete Aktionen blind zu starten.

### 4. SL-Diagnose und isolierte Abnahmefälle

- Spieler 1 hält einen Druckschalter, sein Zug endet: je erlaubter Haltepolicy echtes Halten fortführen oder mit definierter Freigabe beenden, ohne imaginäre Präsenz.
- Zulässiger Countdown wird durch Spieler 1 ausgelöst, Spieler 2 ist danach am Zug: Nur seine ausdrücklich erlaubte Weltwirkung läuft weiter; kein zusätzlicher Zug für Spieler 1.
- Pausierter Türbefehl: Ist die Figur inzwischen weg oder das Schloss geändert, keine späte Türenöffnung/Spawn-/Alarm-/Zugübergabe.
- SL gibt eine wartende Handlung nach Ressourcenänderung frei: Erneut prüfen; weder Gegenstandskosten noch Würfelchecks doppelt ausgeben.
- Zwei unabhängige Rätsel-/Turnkontexte in derselben Szene: Zugende in A ändert B nicht ohne tatsächlichen gemeinsamen Weltzustandskonflikt.
- Reconnect, doppeltes Node-Event, veraltete Turngeneration und Serverneustart führen nicht zu doppelter Wirkung. Isolierter SL-Test nach 02.31–02.34 verändert keine echten Daten oder geheimen Spieleransichten.

**Noch offen:** 02.75 entscheidet reale vs. Spiel-/Turnzeit, Pausen und Timer-Wiederanlauf. Exakte Queue-Reihenfolgen, Timeouts, Reservierungen, Kampf-/Skillkosten sowie konkrete UI folgen später in 03/05/07. Der globale Einstellungsassistent und die generelle Abschaltbarkeit anderer Module bleiben nach Abschluss des gesamten Featureworkshops; die ausdrücklich beschlossene Akustik-Ausnahme 02.51 gilt weiterhin.

## Nächste Entscheidung 02.75 – Wie verhalten sich Timer bei Pausen, Offline-Zeit und Serverneustart?

- **A – Immer Echtzeit:** Jeder Countdown misst ununterbrochen vergangene reale Zeit, auch wenn Kampagne, Szene oder Zug pausiert oder ein Spieler offline ist.
- **B – Immer Spielzeit:** Jeder Timer friert bei Unterbrechung ein und läuft erst weiter, wenn seine Spielrunde/Szene wieder aktiv ist.
- **C – Konfigurierbar (Empfehlung):** Je Kampagnen-/Regelprofil, Timer-/Aktionsklasse, Szene, Node und Turn-Kontext lässt sich die maßgebliche Zeitbasis und das Pausen-/Wiederanlaufverhalten festlegen, mit erkennbaren Standards und Ausnahmen. Abgelaufene Ereignisse werden nach Neustart nur bei aktueller Rechte-/Zustandsprüfung und höchstens einmal ausgelöst; keine ungeprüfte Nachhol-Lawine.
