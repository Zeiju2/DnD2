# AdventureShift – Karten-Workshop: Beschluss 02.100 C

**Stand:** 13.10.2026 – Beschluss 02.100 C; Folgeentscheidungen 02.101–02.105 C beschlossen, nächste offene Frage 02.109  
**Status:** Verbindlicher Fachbeschluss und konzeptioneller Umsetzungs-/Abnahmeplan, **keine implementierte Software**, keine finale API/Datenbankstruktur, keine abschließende globale Kampagnen-Einstellungsführung oder MVP-Freigabe.  
**Bezüge:** [02.25 Defaults und markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.51 optionale Akustik](KARTEN-WORKSHOP.md) · [02.54 NPC manuell/assistiert/automatisch](KARTEN-WORKSHOP.md) · [02.59 wirkliche Codeprüfungen](KARTEN-WORKSHOP.md) · [02.65–02.67 geheime/echte Würfe](KARTEN-WORKSHOP.md) · [02.77–02.82 Graph-/Node-/Eventversionen](KARTEN-WORKSHOP-02.82.md) · [02.83/02.84 Szene-/Editbestand](KARTEN-WORKSHOP-02.84.md) · [02.92 Questabhängigkeiten](KARTEN-WORKSHOP-02.92.md) · [02.93/02.94 optionaler Generator und manuelle Quests/Notizen](KARTEN-WORKSHOP-02.94.md) · [02.95–02.98 Notizen, Marker und Kampagnen-Automatisierungsgrade](KARTEN-WORKSHOP-02.98.md) · [02.99 C Antrag, Direktbuchung und Freigabe](KARTEN-WORKSHOP-02.99.md).

## 1. Entscheidung 02.100 – Variante C verbindlich

**Vom Projektinhaber gewählt: C – Berechtigte, protokollierte Korrektur mit Folgeprüfungen.** Hat eine nach **02.99 C** rechtmäßig in den echten Spielzustand gebuchte **manuelle Entscheidung** ein falsches oder unerwünschtes Ergebnis erzeugt, darf sie unter aktueller Kampagnen-/Regel-/Event-/Rollen-/Zielpolicy **bewusst korrigiert** werden. Die SL legt pro geeignetem Bereich mit **02.25-Defaults und expliziten Ausnahmen** fest, wer **Korrekturen beantragen**, **Korrekturvorschläge einsehen**, **deren Ausführung genehmigen** bzw. **einen klar eingegrenzten Korrekturtyp direkt durchführen** darf. Die tatsächliche Korrektur ist ein **neuer, prüfbarer und historisch verknüpfter Vorgang**, niemals das heimliche Überschreiben/Löschen des ursprünglichen realen Ereignisses.

**Kernunterscheidung:** Ein Antrag oder die Vorschau einer Korrektur verändert **nichts**. Nur eine aktuell gültige berechtigte Aktion auf einem zulässigen Korrekturpfad und – wo so konfiguriert – nach ausdrücklicher aktueller Freigabe erzeugt **einmalig** neue Welt-/Quest-/NPC-/Ressourcenwirkungen. Die vergangene tatsächlich gebuchte Aktion, ihre damalige Version, ihre Wirkung und die Entscheidung bleiben im getrennt geschützten Audit erkennbar.

**Beispiele:**
- SL setzt den Wachmann nach Voicechat versehentlich auf „freundlich“. Nach Prüfung kann ein neuer berechtigter Korrekturvorgang den **jetzt zulässigen NPC-Zustand** auf „misstrauisch“ setzen. Das frühere Ergebnis bleibt als Vorgängerbeleg protokolliert.
- Ein manuell verbuchter Questabschluss hat eine Belohnung ausgezahlt und möglicherweise eine Tür geöffnet. Eine Korrektur am Queststatus **zieht nicht blind die Belohnung zurück und schließt nicht heimlich die Tür**. Sie ermittelt die tatsächlich stattgefundenen abhängigen Effekte und lässt nur ausdrücklich freigegebene und aktuell zulässige Folgekompensationen zu.
- Eine Ressource wurde aus Versehen abgezogen. Erstattung erfolgt höchstens nach geprüften tatsächlichen Buchungen, aktueller Bestands-/Besitz-/Regelpolicy und einmaliger Transaktion. Nicht „negative Ausgaben“, doppelte Einzahlungen oder widerrechtliche Item-Rücktransfers erzeugen.
- Ein geheimer Wahrnehmungswurf, der in der Zwischenzeit tatsächlich stattgefunden hat, bleibt als echter RNG-Wurf unverändert; höchstens ein davon getrennt erlaubter narrativer Status kann unter eigenen Rechten korrigiert werden.

Die früheren Varianten **A** (keine gezielten Korrekturen) und **B** (unprotokolliertes rückwirkendes Überschreiben) werden **nicht übernommen**.

## 2. Rechte, Scope und Grenze von Korrekturen

| Fähigkeit | Fachliche Grenze |
| --- | --- |
| **Korrektur beantragen** | Recht, einen zulässigen Korrekturtyp mit Referenz auf tatsächlich bekanntes, korrekt sichtbar gemachtes Ausgangsereignis vorzuschlagen; kein Effekt |
| **Vorschau lesen / Folgen prüfen** | Nur aktuell sichtbare Ziele und entsprechend bereinigte Auswirkungen; geheime Auswirkungen nicht an unberechtigte Antragsteller ausleiten |
| **Korrektur genehmigen / ablehnen** | Eigenes Entscheidungrecht pro Eventklasse/Ziel/Szene/Gruppe/Rolle und Änderungsumfang; nicht automatisch wegen Antragsrecht |
| **Direkte Korrektur ausführen** | Separat ausdrücklich erlaubte, typisierte Korrekturaktion ohne zusätzlichen Freigabeschritt; weiterhin alle Sach-, Ressourcen- und Autorisierungsprüfungen |
| **Folgekompensation genehmigen** | Eigenständige aktuelle Berechtigung für jeden zusätzlich betroffenen Gegenstand, Quest, NPC, Timer, Alarm, Graph/Node oder andere Subsysteme; keine Pauschalvollmacht aus der Ursprungskorrektur |
| **Korrekturpolicy ändern / Audit lesen** | Getrennte Verwaltungs- und Sichtrechte; keine automatische Offenlegung aller fremden/geheimen Spieler- oder SL-Informationen |

**Rechteauflösung:** Kampagne/Regelprofil → wirksamer 02.98-Modus und tatsächlich unterstützte Korrekturtypen → Ereignisklasse und Ausgangsbeleg → Rollen/Gruppe/Benutzer → betroffene Ziele/Quest/NPC/Ressource/Szene/Graph/Turn → explizite 02.25-Ausnahmen → aktuelle Policies, Mitgliedschaft, Sicht-/Fog-/Secret-Regeln. Das ursprüngliche Recht, eine manuelle Entscheidung zu treffen oder zu genehmigen, gewährt **kein automatisches Recht**, diese später korrigieren oder bereits an Dritte übertragene Güter zurückbuchen zu dürfen.

**Selbstfreigabe:** Wer lediglich einen Korrekturantrag stellen darf, kann sich nicht selbst die Genehmigung erteilen. Eine direkte Korrektur bzw. ausdrücklich zugelassene Selbstfreigabe ist nur nach bewusst vergebener wirksamer Policy möglich. Bei besonders riskanten Konsequenzen kann die Konfiguration eine zusätzliche berechtigte Bestätigung verlangen. Keine frei zugänglichen allgemeinen „Set-Any-State“- oder Administrator-Bypass-Kommandos.

**Kampagnenmodi:** Eine manuell geführte Voicechat-first-Kampagne benötigt weiterhin weder KI, Voiceaufnahme noch Generator. Ein optional deaktivierter Korrektur-/Automatik-Unterpfad darf keine neue Wirkung erzeugen; bereits real geschehene Ereignisse bleiben historisch erhalten. Grundschutz wie Auth, serverautoritative gültige Aktionen, Datensicherheit und Event-Einmaligkeit ist nicht deaktivierbar.

## 3. Historie und Modellkandidaten (noch keine finale API)

Konzeptionelle fachliche Datentypen: `CorrectionPolicy`, `CorrectionRequest`, `CorrectionTargetRef`, `CorrectionRevision`, `CorrectionDependencySnapshot`, `CorrectionImpactPlan`, `CorrectionPlanStep`, `CorrectionDecision`, `CorrectionCommand`, `CorrectionCommitReceipt`, `CorrectionCompensation`, `CorrectionAuditLink`, `CorrectionAccessProjection` und `CorrectionConflict`. Namen sind **reine Entwurfsbezeichnungen**, nicht implementierte Tabellen/Routes/Klassen.

Eine Korrektur referenziert per stabiler ID **mindestens ein tatsächlich gebuchtes Ursprungsereignis/einen konkreten ursprünglichen Effekt** und spezifiziert die ausdrücklich beabsichtigte neue Zustandsänderung; nicht nur das sichtbare Freitextlabel. Versioniert zu binden: aktuelle Kampagnen-/Regel-/Feature-Policy, Eventtyp und effektiver Scope, Ursprungsversion und vorheriger/nachheriger Effekt, aktuelle Zielobjekt-/Ressourcen-/Quest-/NPC- und ggf. Szenen-/Graph-/Turn-/Timergeneration, Korrekturantrag/-revision, Entscheider, geprüfter Impactplan, freigegebener Ausführungsumfang, Operations-/Korrelations-/Idempotenz-IDs und finale Commit-/Fehlerstatus.

**Historie immer append-only bzw. manipulationsgeschützt nachvollziehbar:** Ursprung und Korrektur enthalten die **tatsächlichen Buchungszeiten** und bleiben korreliert. Ein eventuell erzählerisch gemeinter Rückbezug („das galt schon vor fünf Minuten“) ist **kein rückdatiertes serverseitiges Event** und sortiert echte historische Effektketten, Turnwechsel, Würfel und Rechte nicht rückwirkend um. Historische fachliche Korrekturen werden als neue Fakten mit Verweis auf die frühere Entscheidung modelliert.

**Mehrere Korrekturen:** Eine spätere Korrektur kann auf eine frühere Korrektur folgen, aber mit eindeutigen Versionen/Verweisen; bereits aufgehobene Ausgleichsschritte werden niemals per Retry oder erneuter Genehmigung doppelt ausgeführt. Kein zyklisches selbstaktivierendes Korrekturverfahren. Originale und Belege bleiben auch dann lesbar, wenn sich die aktuelle NPC-/Quest-/Objektprojektion verändert.

## 4. Abhängigkeitsprüfung statt unsicherem Welt-Rollback

Vor einer echten Korrektur erstellt der Server für den **ausgewählten überprüfbaren Korrekturscope** eine **rein lesende, effectfreie Impact-/Abhängigkeitsvorschau**. Sie berücksichtigt **wirklich protokollierte** kausale Effekte und relevante aktuelle Abhängigkeiten, nicht vermeintliche Rückverfolgbarkeit bloßer Texte, Voice-Aussagen, Spielerhypothesen oder Notizen.

| Mögliche Folge | Korrekturregel |
| --- | --- |
| **Questfortschritt, Voraussetzungen, Achievements, Belohnungen** | Prüfen, welche zulässigen Schritte wirklich geschrieben/vergeben wurden; nur gezielt autorisierte, aktuelle Kompensation oder Kennzeichnung als nicht automatisch rücknehmbar |
| **Inventar, Geld, Ressourcen, Besitz-/Handelsketten** | Tatsächliche Ledger-/Ownership-/Transferkette und heutigen Bestand prüfen; keine negative/duplizierte Buchung, kein heimlicher Entzug eines inzwischen legal übertragenen Items |
| **NPC-Status, Beziehungen und Positionen** | Aktuelle NPC-/Wissens-/Sichtpolicy und Folgereaktionen prüfen; niemals automatisch andere NPCs oder Spielerwissen ungeschehen machen |
| **Türen, Schalter, Licht, Alarm, Sensoren, Geräusch, Timer** | Nur ausdrücklich zugelassenen aktuellen Objekt-/Eventzustand ändern; keine automatische Wiederholung vergangener Trigger, keine rekursive Alarm-/Sound-/Node-Schleife |
| **Node-Graph, Fan-out/Join, Next-Player und Turngeneration** | 02.77–02.82 versionierte tatsächliche Effektkette berücksichtigen; vergangene Pulse/Timer/Join-Freigaben und Zugwechsel nicht rückwirkend löschen, umwerten oder erneut ausführen |
| **Karte, Szene, Fog, Erkundung und freigegebene Geheimnisse** | Bestehende Sicht-/Szenen-/Marker-ACLs schützen; Wissen, das Menschen bereits erhalten haben, lässt sich nicht zurücknehmen |
| **Echte Würfel und Checks** | RNG/Originalwürfe/ursprüngliche Erfolgsberechnungen bleiben echt und unverändert; neue eigenständige Aktionen können nur bei separat gültiger Regel freigegeben werden |
| **Spätere unabhängige Spielhandlungen** | Nicht blind rückgängig machen. Wo Folgen nicht sicher separierbar sind: Konflikt anzeigen, ggf. pausieren oder neuen manuellen Ausgleich beantragen |

**Keine implizite volle Transaktions-Rückabwicklung:** Ein manueller Eintrag kann viele downstream Spielereignisse angestoßen haben. Eine rückwirkende Gesamtrücksetzung könnte von Spielern getroffene Entscheidungen, ausgeführte echte Würfe, bereits konsumierte Ressourcen oder entdeckte Geheimnisse verfälschen. **Deshalb niemals ganze Szenen-/Kampagnen-Snapshots kommentarlos wiederherstellen oder historische Events löschen**. Stattdessen pro aktuellem Ziel einen gültigen **Korrektur-/Kompensations-Eventtyp** mit begrenzter Wirkung benutzen und Auswirkungen ausdrücklich beurteilen.

**Unbekannte Folgen nicht wegbehaupten:** Der Impactplan unterscheidet belegte direkt rücknehmbare Effekte, verknüpfte aber gesondert zu behandelnde Effekte, bereits irreversible/offene Konsequenzen und noch nicht sicher prüfbare Abhängigkeiten. Fehlen Kausalverknüpfungen, heißt das „nicht sicher automatisch rücknehmbar“, nicht „keine Folgewirkung“.

## 5. Geschützter Ablauf und Failure-Semantik

1. **Ausgang auswählen:** Berechtigt sichtbaren tatsächlich committed Originalbeleg (02.99 C) auswählen, beabsichtigten typisierten korrigierten Zustand nennen und minimal erforderliche Begründung optional erfassen. Ein Antrag bleibt effectfrei.
2. **Autorisierte Preflight-/Vorschau:** Serverseitig aktuelle Rollen, Policy, Sicht/Fog, Ursprung, erlaubten Korrekturtyp, Zielversionen, tatsächliche bereits gebuchte Effekte und verfügbare Kompensationsarten prüfen. Ergebnis beschreibt den **möglichen** Zielzustand, Kosten, Risiken, Abhängigkeiten und bereits irreversible Folgen; keine echte Wirkung.
3. **Freigabe:** Policy bestimmt Direktrecht oder nötige ausdrückliche Entscheider. Zustands-/Impactplanversion, betroffene Ziele, Umfang und Folgeaktionen werden konkret zur Freigabe gebunden. Bloßes „okay“ im Voicechat und ein Klick auf eine bloße Vorschau sind keine stillen Weltbefehle.
4. **Unmittelbarer Commit-Check:** Beim Commit *alle* aktuellen Berechtigungen, Ziel-/Ressourcen-/Inventar-/Quest-/Node-/Scene-/Turn-/Timer-/Graph-/Policyversionen und neu eingetretene Folgewirkungen erneut prüfen. Abweichende Grundlage = kein ungeprüfter Commit, sondern veraltete Vorlage, Neubewertung/Neufreigabe oder sachliche Ablehnung.
5. **Einmalige tatsächliche Buchung:** Ein gültiger **einzelner oder als fachlich atomare Einheit tatsächlich unterstützter** Korrektureffekt mit eindeutigem Effektbeleg/Idempotenzschlüssel transaktional gegen denselben persistenten Event-/EffectLedger-Pfad buchen. Einträge/Entscheidungen/Belege und betroffene fachliche Daten kohärent halten.
6. **Mehrschritt-/Mehrsubsystem-Folgen:** Nur dann eine einheitlich atomare Korrektur behaupten, wenn die tatsächlichen Transaktionsgrenzen dies erlauben. Sonst **getrennte freigegebene kompensierende Schritte mit Reihenfolge, stabilen Step-/Idempotenz-IDs, Fortschritt und Wiederaufnahme nach Ausfall**; Teilerfolg **klar kennzeichnen und sicher anhalten**, nie automatisch „alles fertig“ melden oder durch Retry doppeln.
7. **Ergebnis:** Berechtigt gefiltert „beantragt / wartet / abgelehnt / veraltet / teilweise ausgeglichen / abgeschlossen / nicht sicher kompensierbar“ anzeigen. Ein bloß genehmigter, beim Commit fehlgeschlagener Antrag darf nicht als korrigierter Weltzustand erscheinen.

**Race-Sicherheit:** Gleichzeitig eintreffende Entscheidung, Gegenbuchung, Ressourcennutzung, Node-Event oder zweiter Korrekturantrag auf denselben Ursprung benötigen gemeinsame Versions-/Sperr-/CAS- oder transaktional äquivalente Konfliktkontrolle. Zwei Bestätigungen derselben Revision erzeugen maximal **eine** Buchung, keine erneute Belohnung. Unterschiedliche legitime Korrekturen werden nach aktuellem Zustand neu geprüft, nicht per Last-Writer-Wins still zusammengeführt.

**Widerruf/Moduswechsel:** Wird ein Recht entzogen, eine Gruppe verlassen, ein Ziel verborgen/unpublished/gelöscht, eine Policy geändert oder das Modul deaktiviert, müssen wartende Vorschläge und schon freigegebene, noch nicht gebuchte Aktionen vor jedem weiteren Commit erneut aktuell autorisiert und ggf. gehalten/verworfen werden. Veraltete Genehmigungen dienen nicht als zeitlich unbegrenzte Rechte.

## 6. Geheimnisse, Anzeigen, Notizen und Audit

- Ursprungs- und Korrekturbelege sowie technische Dependency-/Impactdetails sind **nicht automatisch global sichtbar**. Anfrageansicht, Status/Zähler, Diff/Vorschau, Änderungsgrund, Empfängerliste, Suche, Benachrichtigung, Realtime, Export, Offline-/Browsercache und SL-Debugausgabe nach **jeweils aktuellem** Secret-/Fog-/NPC-/Quest-/Roll-/Spieler-/Feldzugriff serverseitig filtern.
- Nicht erlaubt: Aus dem Korrekturantrag erfahren, dass ein unbekannter NPC existiert, welcher geheime Check stattfand, welche Tür bei unsichtbarer Szene ausgelöst wurde, welche Spielerin eine private Notiz führte oder wer eine nicht freigegebene Quest löste. Niemals geheime Würfel, echte früher geheim gehaltene Ergebnisse oder Bearbeiteridentitäten allein durch Korrekturmetadaten veröffentlichen.
- Unveränderliche/sicher protokollierte fachliche Verknüpfungen zwischen Ausgangsbuchung, Korrekturantrag, Entscheidungs-/Impactplanstand und tatsächlich gebuchten Kompensationsschritten; die verfügbare **Spieler-, SL- und interne Serveraudit-Ansicht** folgt verschiedenen Rechten aus 02.65–02.67/02.95. Aufbewahrungs-/Datenschutzdetails und UI werden später festgelegt.
- Spieler können weiterhin eigene subjektive Notizen, Codes und Marker haben. **Einträge in solchen persönlichen Texten sind weder Beweis für eine Korrektur noch automatisch offizielle Daten**. Der vollständig optionale Missionsgenerator aus 02.93/02.94 wird nicht benötigt.
- **02.101 C** hat die konfigurierbare, feld-/empfängerberechtigungsgefilterte Mitteilung (keine / bereinigte Kurzfassung / tatsächlich berechtigte Details) zu wirklich gebuchten Korrekturwirkungen inzwischen beschlossen [Detail](KARTEN-WORKSHOP-02.101.md). Unabhängig davon müssen aktuell berechtigte Clients den **tatsächlich gültigen neuen sichtbaren Zustand** konsistent synchronisiert bekommen und dürfen nicht absichtlich auf einer inzwischen falschen alten Weltprojektion gehalten werden.

## 7. Konzeptioneller Umsetzungsplan – keine Implementierung

1. **Typisierten Korrekturkatalog aus 02.99-Ereignissen ableiten:** Für unterstützte reale Ereignisse explizite, validierbare und begrenzte Korrektur-/Kompensationstypen mit betroffenen Ressourcen und Grenzen festlegen; keine allgemeine historische Patch-/Rollback-API.
2. **Policy-Resolver erweitern:** Getrennte Beantragen/Prüfen/Freigeben/Direktkorrigieren/Schrittkompensieren/Audit-Rechte mit Kampagnenstandard, Regelprofil, Ziel/Rolle, 02.25-Ausnahme und 02.98-Modus; Secret-/Fog-/Owner-/Gruppe-Filter überall.
3. **Provenienz der ursprünglichen Events nutzen:** Bestehenden Event-/EffectLedger, echte Node-/Timer-/Turn-/Quest-/Inventory-Korrelationen, Versionen und tatsächlich stattgefundene Folgen als Basis nehmen; bei fehlender Information sichere Nicht-Automatisierbarkeit kennzeichnen.
4. **Impactplan und Berechtigtenfreigabe entwerfen:** Effektfreie Berechnung mit echten Abhängigkeiten, Revisions-/Ablauf-/Target-/Policybindung, explizit ausgewähltem Korrekturscope und getrennt zu autorisierenden Folgekompensationen.
5. **Ausführungskoordinator planen:** Einmalige transaktionale Buchungen, effektbezogene idempotente Step-Ausführung, safe pause/retry/reconnect, Nachvollziehbarkeit von Teilfehlern und feste Grenzen der Atomarität. Bei Risiko/Unentscheidbarkeit neu vorlegen statt blind rückabwickeln.
6. **UI nur als Fachablauf skizzieren:** Ausgangsbeleg → beabsichtigte Korrektur → Impact und irreversible Folgen → ausdrückliche Genehmigung/Ausführung → gefilterte Bestätigung. Detailliertes Einstellungsmenü, globaler Assistent, Modulliste und MVP-Umfang erst nach vollständigem Featureworkshop.
7. **Regressionen definieren:** Echte RNG-/Code-/Item-/NPC-/Node-/Alarm-/Timer-/Turnwirkungen, mehrstufige Ressourcenketten, geheime Felder, Race-/Reconnect-/Replay-, Fog-/Gruppen-/Policywechsel, Genehmigungen, Korrektur-Teilzustände und bereits abgeschlossene/irreversible Ereignisse testen.

## 8. Abnahmetests

| Fall | Erwartetes Ergebnis |
| --- | --- |
| Rechtmäßig gebuchter NPC-Status ist falsch | Berechtigt beantragbar; neuer Status erst nach wirklichem erlaubten Korrektur-Commit, Originalbeleg bleibt |
| Spieler darf nur beantragen | Weder direkt korrigieren noch selbst genehmigen ohne ausdrücklich zusätzliche Rechte |
| SL darf für NPC direkt korrigieren, aber nicht Inventar ändern | NPC-Event nach Serverprüfung erlaubt; Ressourcentransfer-/Inventarkorrektur abgewiesen |
| Korrektur wird abgelehnt, zurückgezogen oder nur angezeigt | Keine echte Welt-/NPC-/Quest-/Node-/Ressourcenänderung |
| Zwei SL bestätigen denselben Korrekturantrag gleichzeitig | Maximal ein echter Effekt und ein dazugehöriger Commitbeleg |
| Antrag wird nach Reconnect mehrfach gesendet | Stabile IDs, kein zweiter Ausgleich/keine Doppelgutschrift |
| Queststatus wird nach Belohnung korrigiert | Quest und bereits real ausgezahlte Belohnung **nicht blind gekoppelt**; Wirkung nur nach geprüfter expliziter Kompensation |
| Gegenstand wurde nach falscher Belohnung an anderen Charakter gehandelt | Kein heimlicher unberechtigter Besitzentzug; separater autorisierter Ausgleich oder offener Konflikt |
| Tür/Alarm wurde durch das Ursprungsevent wirklich ausgelöst | Kein automatisches Rückspulen; nur ausdrücklich aktuell gültige, separat geprüfte Änderung |
| Seit Ursprung trat ein echter Wurf oder Next-Player-Zugwechsel ein | Originalwürfe/Turngeneration bleiben; keine historische Neu-Würfelung/erneute Node-Ausführung |
| Spieler hat bereits geheime Identität erfahren | Korrektur kann dieses reale Wissen nicht aus Menschenköpfen entfernen |
| Korrekturvorschau hat Geheimziel in Abhängigkeit | Unberechtigter Antragsteller sieht weder Name, Koordinaten, Anzahl/Count, Questziel noch geheime Würfe |
| Gruppen-/Rollenrecht entzogen vor Freigabe | Kein Commit mittels alter Antrags- oder Genehmigungsrechte |
| NPC-/Quest-/Graphversion ändert sich nach Vorschau | Stale Impactplan nicht ausgeführt; aktuelle Neuprüfung und ggf. erneute Freigabe |
| Zweite Korrektur greift auf denselben schon kompensierten Effekt zu | Keine Wiederholung einer Ausgleichsbuchung; gültige neue Änderung nur nach eigener neuer Prüfung |
| Kompensation braucht zwei Schritte, zweiter schlägt fehl | Kein vorgetäuschter Gesamterfolg; erster Schritt eindeutig nachvollziehbar, zweiter sicher wartend/nicht doppelt |
| Manuelle Voicechat-first-Kampagne ohne Missionsgenerator | Korrekturen erlaubter manueller Ereignisse funktionieren nach Rechten ohne Audioaufzeichnung/KI |
| Korrektur-Feature/Modul ist für neue Aktionen deaktiviert | Kein heimlicher Korrektur-Trigger, historische legale Belege bleiben erhalten |
| Client manipuliert Kommentar, Ziel-ID oder Payload | Kein untypisiertes freies Welt-Patching, kein Überspringen von Origin-/Rechte-/Ressourcenprüfungen |
| Korrektur hat keinen sicher nachvollziehbaren Effektpfad | Kein automatisches „alles rückgängig“; als nicht sicher kompensierbar kennzeichnen |

## 9. Beschlussgrenze und Folgefrage

**Festgelegt:** Variante 02.100 C für **berechtigte, nachvollziehbare Korrektur-/Kompensationsevents** zu bereits real gebuchten manuellen Ergebnissen nach 02.99 C; separate Beantrag-/Freigabe-/Ausführungsrechte; aktuelle serverseitige Wirkungskontrolle mit echtem Ledger, Versionen, Abhängigkeiten und Schutz vor Replay, Geheimnisleaks und unbeabsichtigtem Rollback. Erzählfreiheit, Voicechat-first, optionale Automatisierung und echtes Spielwissen bleiben erhalten.

**Nicht festgelegt:** Endgültige Programmierschnittstelle, konkrete UI-Ordnung, exakte Korrekturkatalog-Eventtypen für alle Genres, globaler Kampagnenassistent, konkrete Nachrichtentransport-/UI-Ausführung, Speicherfristen oder MVP-Rangfolge. Keine vollständige automatische Rückabwicklung komplexer Historie versprochen.

## Archivierte Folgefrage 02.101 – inzwischen als C beschlossen

**Beispiel:** Die Spielleitung korrigiert einen NPC-Status, weil die frühere Entscheidung falsch eingetragen wurde. Einige Spieler haben den NPC tatsächlich gesehen; andere kennen ihn nicht, und die korrigierte Aktion enthielt möglicherweise geheime Würfe, Hintergrundpläne oder private Details. Wie sollen Mitteilungen zur Korrektur gestaltet werden?

- **A – Keine gesonderte Korrekturmitteilung:** Die aktuell berechtigten Spieler sehen nur den künftig richtigen Spielzustand, aber keinen Hinweis darauf, dass ein früherer Wert korrigiert wurde.
- **B – Immer öffentliche Komplettmeldung:** Jede Korrektur mit Begründung, allen betroffenen NPCs/Quests/Effekten und ihrer kompletten Historie geht an alle Kampagnenmitglieder, auch wenn Details geheim waren.
- **C – Konfigurierbare, berechtigungsgefilterte Korrekturmitteilungen (Empfehlung):** SL legt nach Kampagnenstandard und zulässigen Ausnahmen fest, **ob und für wen** eine Korrekturmeldung, eine bereinigte Kurzfassung und/oder der detaillierte Beleg sichtbar wird; betroffene Spieler erhalten keine unberechtigten SL-Geheimnisse, fremden Notizen oder versteckten NPCs. Der echte aktuell berechtigt sichtbare Spielzustand wird unabhängig von optionalen Mitteilungen immer korrekt synchronisiert. Die vollständige interne Historie bleibt geschützt nachvollziehbar.

**Aktueller Fortgang:** [02.101 C](KARTEN-WORKSHOP-02.101.md) ist verbindlich mit getrennten Benachrichtigungsgraden, aktuellen Empfänger-/Feld-/Sichtrechten und geschütztem Audit dokumentiert. **Der tatsächliche, erlaubt sichtbare neue Weltzustand bleibt unabhängig von Hinweisen korrekt synchronisiert.** **02.102 C** hat konfigurierbare aktive Kenntnisnahmequittungen für berechtigte wichtige Korrekturhinweise beschlossen [Detail](KARTEN-WORKSHOP-02.102.md). **02.103 C** regelt jetzt optionale, rechtsgefilterte Erinnerungen und SL-Eskalation ausstehender gültiger Quittierungen ohne pauschalen Spielstopp [Detail](KARTEN-WORKSHOP-02.103.md). **02.104 C** hat gesondertes berechtigtes Verwaltungsabschließen/Erlassen nicht sinnvoll erfüllbarer Ackpflichten mit eigenem Audit statt vorgetäuschtem Spieler-Ack beschlossen [Detail](KARTEN-WORKSHOP-02.104.md). **02.105 C** erlaubt eine bewusst berechtigt initiierte eigenständige neue Kenntnisnahmeanforderung nach erneut gültigen Empfänger-/Notice-Rechten [Detail](KARTEN-WORKSHOP-02.105.md); integrierter Chat bei Erstellung separat An/Aus, **02.106 C** hat berechtigte Chatkanaltypen bei Chat An/Aus beschlossen [Detail](KARTEN-WORKSHOP-02.106.md); **02.107 C** hat flüchtige/gespeicherte Chatverläufe und historische ACL/Retention beschlossen [Detail](KARTEN-WORKSHOP-02.107.md); **02.108 C** hat kontrollierte Chatnachrichtenbearbeitung/-Zurücknahme beschlossen [Detail](KARTEN-WORKSHOP-02.108.md); **02.109** folgt mit Melden/Moderation.
