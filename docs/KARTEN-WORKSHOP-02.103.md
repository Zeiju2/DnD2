# AdventureShift – Karten-Workshop: Beschluss 02.103 C

**Stand:** 13.10.2026 – Beschluss 02.103 C; 02.104 C und 02.105 C inzwischen beschlossen, nächste offene Frage 02.110  
**Status:** Verbindlicher fachlicher Beschluss und konzeptioneller Umsetzungs-/Testplan; **noch keine implementierte Software**, finalen APIs, Datenbanktabellen, vollständig spezifizierte Kampagnen-Einstellungsoberfläche, MVP-Einstufung oder ausgeführte Erinnerung.  
**Bezüge:** [02.25 Kampagnenstandards/markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.5 Fog/Sicht, 02.54–02.64 NPC-Wissen, 02.65–02.67 geheime Würfe/Audit](KARTEN-WORKSHOP.md) · [02.77–02.82 Node-/Graph-/Eventkontrolle](KARTEN-WORKSHOP-02.82.md) · [02.93–02.98 optionaler Missionsgenerator, private Spielernotizen/Marker und konfigurierbarer Automatisierungsgrad](KARTEN-WORKSHOP-02.98.md) · [02.99 C manuelle Ergebnisse](KARTEN-WORKSHOP-02.99.md) · [02.100 C Korrekturen/Kompensationen](KARTEN-WORKSHOP-02.100.md) · [02.101 C berechtigte Korrekturmitteilungen](KARTEN-WORKSHOP-02.101.md) · [02.102 C bewusste Quittierung](KARTEN-WORKSHOP-02.102.md).

## 1. Verbindliche Entscheidung 02.103 – Variante C

**Vom Projektinhaber gewählt: C – optionale, konfigurierbare Erinnerungen und berechtigte SL-Eskalation ohne pauschale Spielsperre.** Sind nach **02.102 C** ausdrücklich anzuerkennende wichtige Korrekturmitteilungen trotz einer **wirklich aktuell zulässigen, dem konkreten Empfänger sichtbaren Mitteilung nach 02.101 C** noch nicht aktiv quittiert, darf die Spielleitung nach **gültigen Kampagnen-/Regelprofil-/Ereignis-/Ziel-/Szenen-/Gruppen-/Rollen-/Personenstandards und markierten 02.25-Ausnahmen** eine geeignete Erinnerungs- und Eskalationsstrategie festlegen. Optional werden einzelne noch berechtigte Empfänger erinnert oder berechtigte SL-/Verantwortliche erhalten **nur nach ihren eigenen aktuellen Informationsrechten** einen Hinweis auf relevante offene Kenntnisnahmebestätigungen. Die Funktion darf ganz deaktiviert werden und ist **kein erzwungener Automatismus für alle Ereignisse**.

**Keine globale automatische Sperre:** Ein fehlendes Ack, offline befindlicher Spieler oder später entzogene Leseberechtigung darf **niemals als pauschale Regel alle Spieler, die Kampagne, den nächsten Zug, Türen, Quests oder die Weltzustandssynchronisierung blockieren**. Erinnerungen und Eskalationen sind nur Information/Organisation; ob eine Leitung im Einzelfall nach bestehenden ausdrücklich gültigen Rechten eine **separate bewusste Spielentscheidung** trifft, wird nicht durch einen Reminder legitimiert. Der rechtmäßig korrigierte, für die Person sichtbare Weltzustand aus **02.100/02.101** bleibt unabhängig von Quittierungen, Remindern und SL-Eskalationen korrekt.

**Beispiel:** Ein Charakter besitzt nach einer korrigierten Buchung weniger Munition. Die SL hatte für diese tatsächlich erlaubte Kurzmeldung eine explizite Kenntnisnahme festgelegt. Der Spieler ist mehrere Tage offline. Nach passenden konfigurierten Voraussetzungen kann beim nächsten berechtigten Zugriff ein unaufdringlicher In-App-Hinweis erscheinen; eventuell sieht eine hierfür berechtigte SL, dass **eine erlaubte** Bestätigung aussteht. **Kein anderer Spieler muss deshalb warten.** Der Spieler bestätigt persönlich erst durch eigenen bewussten 02.102-Ack-Klick. Falls die Ausrüstungsmitteilung mittlerweile geheim oder für ihn nicht mehr zulässig ist, dürfen keine neuen Erinnerungen oder auffällige Restzähler mehr ausgeliefert werden.

**Nicht beschlossen:** A („nur offen, nie Erinnerungen/Eskalation“) als einziger Modus und B („eine offene Bestätigung sperrt immer alles“) werden verworfen. Stilles Offenhalten bleibt als **konfigurierbare** Option möglich.

## 2. Konfigurierbare Parameter und sinnvolle Grenzen

| Parameter | Konzeptionelle Regel |
| --- | --- |
| **Erinnern** | Pro geeigneter 02.102-Ackklasse aus/an; manuell durch berechtigte SL oder, sofern explizit aktiviert, nach gültigen Frist-/Intervallregeln automatisiert; keine automatische Pflicht für alle Notices |
| **Beginn der Frist** | Nur aus einer zulässig bestehenden sichtbaren Ackanforderung und dafür eindeutig dokumentiertem Startbezug, z. B. erlaubte Nachricht verfügbar/zustellbar oder berechtigter nächster Login – **nicht** allein aus verborgenem Eventzeitpunkt für nicht erreichbare Adressaten |
| **Häufigkeit/Maximalzahl** | SL konfiguriert zulässige Mindestabstände, Wiederholung, Höchstversuche, Ruhezeiten oder Stopps passend zum Kampagnenprofil; **keine willkürlich bereits verbindlichen Zeitwerte** |
| **Empfänger** | Ausschließlich der konkrete noch berechtigte Spieler, gegebenenfalls persönlich berechtigte SL-/Moderatorrolle als Eskalationsadressat; Gruppenscope berechtigt nicht zur ungeprüften Offenlegung aller Details |
| **SL-Eskalation** | Getrennt an-/abschaltbar; erst nach gültigem alters-/zustandsbasiertem Schwellenwert und unter eigener Statuslese-/Secretpolicy, ggf. nur neutraler Hinweis „eine für dich berechtigt verwaltbare Bestätigung ist ausstehend“ |
| **Fristüberschreitung** | Status „überfällig“ ist Organisationsmetadatum, **kein** fälschliches „abgelehnt“, „bewusst verweigert“ oder „quittiert“ und kein Welt-Ereignis |
| **Unterbrechen/Abbrechen** | Erfolgreiche eigene Quittung, Widerruf/Entzug der aktuellen Quellrechte, deaktivierte Notice/Ack/Reminder-Policy, relevante neue Revision, Gruppenwechsel, Kampagnenende oder ausdrücklich erlaubtes Pausieren stoppen/neu prüfen geplante Zustellungen |
| **Kanäle** | Fachlich nur berechtigtes In-App/SL-Dashboard als Basispfad vorsehen; Push/E-Mail/Voice/Drittdienste **nicht voraussetzen** und nur später bei eigener Kanal-/Einwilligungs-/Sicherheitsentscheidung |
| **Preset/Ausnahme** | Erzählfokus: typischerweise keine automatischen Erinnerungen; andere Profile können Assistenz anbieten, aber verbindlich nur, was SL explizit als tatsächliche wirksame Policy wählt; 02.25-Defaults/Ausnahmen bleiben |

**Wichtig:** Die konkrete UX aller Kampagnenschalter, finalen Standardintervalle, minimale/zulässige Grenzen und MVP-Prioritäten werden – wie bisher beschlossen – **nach Abschluss des gesamten Featureworkshops** festgelegt. 02.103 genehmigt den **konfigurierbaren Funktionsumfang**, keine fertig implementierte Timerplattform oder konkrete Minutenfrequenz.

## 3. Berechtigung und Wiedervorlage

Eine offene Erinnerung darf überhaupt nur existieren, wenn zum betrachteten Zeitpunkt sämtliche Bedingungen **gleichzeitig** erfüllt sind:

1. Es gab ein echtes korrigiertes/kompensiertes Event nach 02.100 C, nicht lediglich einen vorgeschlagenen oder abgelehnten Antrag.
2. Für den bestimmten Empfänger gibt es eine **aktuell erlaubte** sichtbare und sachlich noch gültige Mitteilungsfassung nach 02.101 C.
3. Für genau diese Empfänger-/Notice-Revision ist nach 02.102 C eine **noch aktive und rechtmäßig ausstehende** ausdrückliche Kenntnisnahme verlangt; reine Transport-/Lesestatus sind nicht „quittiert“.
4. Der Empfänger besitzt heute noch die passende Identität, Kampagnenmitgliedschaft, Gruppen-/Rollen-, NPC-/Quest-/Objekt-/Fog-/Notiz-/Wurf-/Secret-Berechtigung; der tatsächliche Empfänger ist nicht anhand einer früheren Gruppe still zu einem anderen Spieler umgebogen.
5. Erinnerungsmodul und konkrete Regel sind aktuell aktiv, nicht pausiert, bereits erreicht, veraltet oder durch Rechte-/Policy-/Notice-Revisionswechsel widerrufen.
6. Für SL-Eskalation ist **zusätzlich** zu prüfen, ob die jeweilige SL/Verantwortliche den ausstehenden Status, betroffene Person und ggf. die erlaubte Ziel-/Korrekturdarstellung sehen darf. SL-Campaignadministration allein verleiht keine Lesevollmacht für fremde private Spielernotizen.

**Rechteprüfung nicht nur beim Planen:** Bei jeder Terminermittlung, Fälligkeit, Empfängerauflösung, Aufbereitung einer Erinnerung, Outbox-Veröffentlichung, Inbox-/Count-/Suche-/Realtime-/Reconnect-Abfrage und tatsächlichem Öffnen die **aktuellen** Rechte und Quell-Revisionen erneut validieren. Auch ein vor Wochen berechtigter Reminder darf bei heute geheimem NPC **weder Text noch verräterische Existenz, Zähler, Zeitpunkt oder einen generischen „Du hast unbekannte Aufgaben“-Badge** ausliefern.

**Offline und Unzustellbarkeit:** Ein noch nicht erreichbarer Spieler wird nicht als verweigernd bewertet. Wie mögliche Schwellwerte ab **nachweisbar bereitgestellter, zugänglicher** Nachricht oder nach dem nächsten Login berechnet werden, bleibt pro unterstützter Policy transparent; ein bloßer unsicherer Versandversuch bedeutet keine Kenntnisnahme. Eine SL kann die organisatorische Abwesenheit erkennen, wenn separat berechtigt, aber keine erfundene Zustell- oder Lesebestätigung erhalten.

## 4. Statusmodell und fachliche Ereignisgrenzen

Konzeptioneller, **noch nicht implementierter** Erinnerungs-/Eskalationsablauf:

- **Nicht fällig / pausiert:** Eine reale Ackanforderung ist nach aktueller Policy sichtbar und offen, aber noch kein aktueller Termin oder ein bewusster Pausegrund liegt vor.
- **Fällig:** Ein rechtmäßig offener Fall erfüllt eine **konkret aktive** Erinnerungspolicy. In diesem Zustand wird zunächst **effectfrei** geplant; ohne aktuelle Berechtigung keine Sendung.
- **Ausgeliefert / erneut fällig:** Die minimal gefilterte Information wird via später festgelegtem tatsächlich erlaubtem Kanal ausgeliefert. Technische Zustellversuche und Wiederholungen haben eigene idempotente Datensätze; „gesendet“ ist nicht „gelesen“ oder „quittiert“.
- **Überfällig / berechtigt eskaliert:** Nur nach konkretem Schwellenwert, aktueller SL-/Adressatenpolicy und neuer Rechteprüfung wird eine **getrennte** minimal gefilterte Anzeige für die SL erstellt; dieser Status erzeugt kein automatisches negatives Spielereignis.
- **Quittiert / kein Bedarf mehr / abgebrochen / neu zu bewerten:** Gültiges aktives Ack, ausgeschaltete Regel, weggefallene Berechtigung, geänderte Notice-Version oder manuell rechtmäßig gestoppte offene Anforderung beendet ältere Folgetermine. Bereits rechtmäßig protokollierte Erinnerungsversuche können im **geschützten** Audit bleiben, sind ohne aktuelle Berechtigung aber nicht weiter abrufbar.

**Mehrere betroffene Spieler:** Jeder Notice-/Revision-/Empfänger-Scope erhält einen **eigenen** Ack- und Reminder-Lebenszyklus. Eine neue Gruppe oder geänderte Mitgliedschaft darf nicht sämtliche früheren Reminder identisch an neue Gruppenmitglieder verschicken. Eine eventuelle SL-Zusammenfassung enthält nur nach aktuellen eigenen Rechten erlaubte Felder und Counts, niemals eine rohe globale Liste aller offenen Korrektur-IDs.

**Quittiert != genehmigt:** Erinnerung, Eskalation, SL-Aufruf, „als dringend markieren“, Deadline oder ein Klick auf „Erinnerung gesehen“ erfüllen nicht das ausdrückliche persönliche 02.102-Ack. Sie genehmigen weder 02.99-Spielevents noch 02.100-Korrekturen/Kompensationen.

## 5. Konzeptuelles Datenmodell und Zuverlässigkeit

Fachliche Platzhalternamen: `AcknowledgementReminderPolicy`, `AcknowledgementReminderRule`, `AcknowledgementReminderSchedule`, `AcknowledgementReminderOccurrence`, `ReminderDeliveryAttempt`, `ReminderDeliveryCursor`, `ReminderEscalationPolicy`, `ReminderEscalationRecord`, `ReminderRecipientProjection`, `ReminderSuppressionReason`, `ReminderDeduplicationKey`, `ReminderAuditEntry`. **Keine fertigen Klassen, Datenbanktabellen oder HTTP-/Realtime-Routen.**

Mögliche verknüpfte Identitäten: `campaignId`, tatsächliche `correctionCommitId`/`compensationStepId` aus 02.100, `noticeId`/`noticeRevision` aus 02.101, `ackRequirementId`/`recipientId` aus 02.102, aktuelle `policyVersion`/`scopeRevision`/`groupMembershipRevision`, `occurrenceId`, Fälligkeits-/Versuchs-/Statuszeiten, Kanal-/Escalation-Adressat und stabiler `operationId`/`deliveryDedupKey`. **Keine** frei vom Client glaubwürdig gesetzten „Reminder war jetzt fällig“-Timer oder Eskalationsrechte.

**Serverautoritative Berechnung:** Fälligkeit aus versionierter Regel, dem wirklich persistierten und rechtmäßig wirksamen Ausgangsstatus und der ausgewählten Zeitsemantik bestimmen; geplante Occurrences **idempotent** erstellen/claimen/abschließen. Konkurrierende Scheduler/Server-Reconnects dürfen für denselben Anspruch keine Spamlawine erzeugen; gesicherte Zustellversuche und wiederholte Outbox-Verarbeitung **mindestens einmal transportierbar, aber fachlich dedupliziert**. Rate-Limit, Ruhezeiten, maximale Wiederholungen und Abbruch bei Änderungs-/Rollen-/Fog-/Ackstand vor der tatsächlichen Zustellung berücksichtigen.

**Keine künstliche globale Echtzeitsperre:** Timer-/Scheduler-Events des Reminders liegen in einem eigenen **nichtweltwirksamen Kommunikations-Subsystem**. Sie dürfen **nicht** den aus 02.48/02.77–02.82 bekannten Alarm-/Sensor-/Node-Graphen, Player-Turn-Scheduler oder Quest-/Ressourcenledger triggern. Darf die SL eine Szene oder Sitzung nach allgemeiner dafür konzipierter Berechtigung manuell pausieren, ist das ein **separater** bewusster Spielbefehl und kein versteckter Automatikeffekt von 02.103 C.

## 6. Geheimnisse, Datenschutz und Spam-Schutz

- **Inhalt minimieren:** Reminder an Spieler nur den nach aktuellen 02.101-Rechten sichtbaren bereinigten Nachrichtenteil und die eigenständig berechtigte Ackanforderung mitteilen. Niemals versteckte NPC-Identität, private Spielernotiz, secret Roll, verborgene Questphase, SL-Hintergrund oder frühere nicht autorisierte Werte verraten.
- **SL-Eskalation separat filtern:** „SL“ ist keine Generalvollmacht, persönliche Notizen, geheime Spielerwürfe oder fremde Campaign-Informationen zu lesen. Statuszählung, Betroffenenliste, Reminderzeit, Begründung und Korrekturursprung nach aktueller SL-/Rollen-/Ziel-/Auditberechtigung beschneiden.
- **Zähler/Timing/Meta-Leaks:** Ungelesene Anzahl, überfällige Reminderanzahl, externe Push-Vorschau, Suchindizes, Filter, Sortierung, Benachrichtigungszeitpunkte, Zustellfehler und geschützte Debug-Ausgabe dürfen keine verborgenen Ereignisse nach außen verraten.
- **Policy-Wechsel/Revocation:** Wenn ein Ziel verborgen, Quest unpubliziert, Spieler aus Gruppe entfernt, Notice/Ack deaktiviert oder Korrektur durch neue Revision ersetzt wird, fällige nicht gesendete Reminder abbrechen bzw. nur nach bewusster gültiger neuer Policy neu bestimmen. Frühere rechtmäßig ausgesprochene Information kann nicht aus menschlicher Erinnerung gelöscht werden.
- **Keine Flut:** Konfigurierbare Mindestabstände, max. Versuche, Stummschaltung/Pausierung, mögliche Gruppierung nur über Empfänger-seitig erlaubte Informationen; gesonderte Berechtigung für eskalierenden SL-Zugriff. Kein automatisches wiederholtes Mailing oder Dauer-Ping an offline/ungeprüft erreichbare Spieler.
- **Sichtbares Feedback:** Wenn die SL einen rechtmäßig sichtbaren Überfälligstatus sieht, muss er als **ausstehend** und nicht als vorsätzliche Verweigerung oder bereits als „benachrichtigt/gelesen/bestätigt“ etikettiert sein. Explizite Kenntnisnahme bleibt Sache des echten Empfängers.
- **Unveränderliche Belege:** Tatsächlich verschickte/unterdrückte/eskalierte Vorgänge auditierbar mit aktuellen Schutzrechten; serverseitige Fehler nicht als erfolgreich zugestellt verbuchen. Aufbewahrungsfristen und konkrete Kommunikationskanäle werden später übergreifend festgelegt.

## 7. Umsetzungsschritte (nur Plan)

1. **Policy-Inventar erweitern:** Auf 02.25-/02.98-Mode-, 02.101-Notice- und 02.102-Ackresolver aufbauend zulässige inaktive/manuelle/regelgestützte Reminder- und SL-Eskalationsmodi, Wiederholungsbegrenzungen, Ruhezeiten, Schwellen und priorisierte Ausnahmen definieren.
2. **Bereitstellung/Fälligkeit sauber modellieren:** Tatsächliche Notice-Verfügbarkeit, konfigurierbaren Beginn, aktuelle Berechtigung, Offset/Zeitzone/Sitzungskontext, ggf. Pausen, Policyrevision und effektive Zeitregel getrennt speichern/ableiten. Noch keine fixen Defaultstunden beschließen.
3. **Revalidierenden fachlichen Scheduler/Outbox planen:** Einen berechtigt offenen Ackfall maximal einmal pro Occurrence markieren, vor Versand/SL-Eskalation neu prüfen, atomare Status-/Zustellversuchprotokolle, Retry mit Backoff, Dedup und Rate-Limits vorsehen; Reconnect/Serverneustart und konkurrierende Worker testen.
4. **Empfängerfeldprojektion einsetzen:** Reminder- und SL-Eskalationstexte aus den wirklich für diesen Empfänger aktuell zulässigen Notice-/Ack-Feldern zusammensetzen, nicht alte vollen Correction-/Secret-Payloads laden und ungefiltert durch Push/Realtime weiterleiten.
5. **Minimalen Fach-UI-Ablauf vormerken:** SL konfiguriert später angemessene Erinnerung/Eskalation, darf nach tatsächlichen administrativen Rechten offene Fälle ohne geheime Zielinformationen sehen. Spieler sieht bei berechtigtem Zugriff seinen eigenen noch ausstehenden Hinweis und bestätigt weiterhin nur nach 02.102.
6. **Kein World-/Turn-Trigger:** Reminder-Events aus Notification-/Ack-Domain streng außerhalb von Node-, Quests-, Waffen-/Inventar-, Sensor-, Alarm-, Würfel- und Turn-Aktionen halten. Sessionstatus und World-State bleiben auch bei offenen Pflicht-Acks korrekt.
7. **Regressions- und Abuse-Tests:** Geheime/entzogene Notices, Offline/Rejoin, Rotationen der SL-/Gruppenrolle, neue wichtige Revision, Doppelexecution, Rate-Limit, Zeit-/Sommerzeit, Suppression-Caches, Multi-Device und Empfänger-/SL-Feldfilter absichern.

## 8. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Kampagne konfiguriert „keine Erinnerungen“ | Gültiger noch nicht quittierter Hinweis kann offen bleiben; kein automatischer Reminder/keine Eskalation |
| Berechtigter Spieler hat nach Policy eine fällige Quittung offen | Ein sachlich korrekter, minimal bereinigter Reminder höchstens in konfiguriertem Rhythmus, ohne zusätzliche Weltwirkung |
| Spieler ist offline vor zugänglicher Zustellung | Kein vorgetäuschtes Gelesen/Quittiert/Verweigert; je aktivem Modus ggf. nächste geeignete Bereitstellung/Frist |
| Normale 02.101-Kurzmeldung ohne 02.102-Ackpflicht | Keinen Reminder durch 02.103 erzeugen |
| Geheimer NPC/Quest/Wurf verursacht ursprünglich ein Event | Unberechtigter erhält keine Remindertexte, Ackcounts, Escalationhinweise oder geheime Badges |
| Spieler hat inzwischen NPC-/Quest-/Gruppenrecht verloren | Pending Reminders abbrechen/nicht erneut zustellen; keine neuen unberechtigten Ackpflichten |
| SL hat Escalationrecht, aber nicht Zugriff auf geheimen Korrekturgrund | SL sieht höchstens erlaubten neutralen Status, keine geheimen Origin-/Notiz-/Wurffelder |
| SL hat kein Recht, Quittierungsstatus dieses Empfängers zu lesen | Keine Empfängeridentität, Overdue-/Count-/Timeline-Information über entsprechende Reports oder Realtime |
| Quittierung wurde schon erfolgreich durch bewussten Klick gespeichert | Erinnerungen/Eskalation enden gemäß gültiger aktuellen Policy, kein weiteres fälliges Ereignis |
| Zwei Scheduler holen dieselbe fällige Occurrence ab | Ein logischer Reminderfall und höchstens einmal als neu dargestellte Nachricht, keine Spamduplikate |
| Server startet während einer Zustellung neu | Konsistente Retry-/Attempt-Historie, keine behauptete Erfolgsmeldung ohne Erfolg und kein doppelter World-State-Effekt |
| Zeit-/DST-Übergang und abweichende Zeitzonen | Effektive Fälligkeits-/Ruhezeitregeln nachvollziehbar ohne ungeprüfte Doppel-/Früherinnerung |
| Neuer fachlich wesentlicher Korrekturhinweis ersetzt alte Version | Frühere fällige Occurrences veralten; neue Ackpflicht nur für aktuell berechtigte neue Notice-Revision |
| Gruppenwechsel einer offenen Nachricht | Kein automatisches Neuverteilen früherer Empfänger-Nachricht an jetzt andere Gruppenmitglieder |
| Betroffener ist mehrere Tage offline | Andere Spieler können weiterspielen; keine automatische globale Session-, Quest- oder Turn-Sperre |
| SL klickt „Erinnerung senden“ | Kein tatsächliches ursprüngliches Ack, kein automatisch genehmigter Korrektur-/Questzustand |
| SL wird über ausstehende Quittung informiert | Nur erlaubte minimale Statusinformation; kein SL-Bypass privater Spieler-Notizen |
| Zwei Korrekturschritte sind teils erfolgreich | Erinnerung verweist nur auf tatsächlich gebuchte und sichtbare relevante Notice-/Ack-Revision, kein falscher Gesamterfolg |
| Akustiksimulation, Missionsgenerator und Voicechatintegration ausgeschaltet | Reminder-Konzept bleibt unabhängig; kein Mikrofonmithören oder KI erforderlich |
| Berechtigter Spieler klickt nach Reminder „Zur Kenntnis genommen“ | Genau ein gültiger persönlicher Ackbeleg nach 02.102, kein Quest-/NPC-/Alarm-/Node-/Würfel-/Turn-Effekt |
| Reminderpolicy wird während wartender Zustellung deaktiviert | Neue/fällige Aktionen vor dem Ausliefern erneut prüfen und stoppen; historische echte Korrektur bleibt unverändert |
| Browser manipuliert Deadline, Policyversion oder Empfänger-ID | Server lehnt unberechtigten Reminder-/Ack-/Escalation-Effekt ohne geheime Fehlermetadaten ab |

## 9. Abgrenzung und nächste offene Frage

**Verbindlich 02.103 C:** Die SL soll für **zulässige offen gebliebene Kenntnisnahmeanforderungen aus 02.102** optionale, gegen Missbrauch begrenzte **Empfängererinnerungen und gezielte, rechtegefilterte SL-Eskalation** anhand von Kampagnen-/Event-/Rollen-/Empfängerdefaults mit markierten 02.25-Ausnahmen konfigurieren können. Zeitbezug, Fristen/Intervalle, Pausen, Abschaltung, Retry, Dubletten, Revocation und Offline-Handling gehören in den Umsetzungsplan. **Kein** heimliches Freigeben von echten Welt-/Korrekturevents, keine automatische globale Spielsperre, kein Offenlegen unbekannter Korrektur-/NPC-/Notiz-/Wurfdaten.

**Noch offen:** Exaktes UI, konkrete Defaultfristen, unterstützte externe Zustellkanäle, Aufbewahrungsfristen, endgültige Datenbank-/API-Struktur, MVP-Einstufung und **02.105** mögliche kontrollierte Neuanforderung nach 02.104 C-Verwaltungsabschluss. **Der prinzipielle kontrollierte administrative Abschluss/Erlass ist in 02.104 C inzwischen beschlossen** [Detail](KARTEN-WORKSHOP-02.104.md).

## Archivierte Folgefrage 02.104 – inzwischen als C beschlossen

**Beispiel:** Ein Spieler verlässt dauerhaft die Gruppe, verliert einen rechtmäßig früher sichtbaren NPC-Zugang oder kann aus praktischen Gründen eine alte, noch offene wichtige Korrekturmitteilung nicht mehr ausdrücklich bestätigen. Die SL möchte die offene Organisationsaufgabe bereinigen, ohne fälschlich zu behaupten, dieser Spieler habe die Meldung selbst gelesen oder ihr zugestimmt.

- **A – Nur persönlich quittierbar:** Eine Anforderung kann niemals administrativ beendet werden; auch dauerhaft abwesende oder heute nicht mehr berechtigte Empfänger bleiben als endlos unerfüllte Pflicht offen.
- **B – SL bestätigt heimlich im Namen des Spielers:** Berechtigte oder unberechtigte Leitungen dürfen jederzeit ohne eigene Historie die persönliche Lesebestätigung fälschen und so tun, als habe der Spieler selbst die Mitteilung zur Kenntnis genommen.
- **C – Konfigurierbares, nachvollziehbares Erlassen oder Schließen durch Berechtigte (Empfehlung):** Für nicht mehr sinnvoll anforderbare, stornierte oder anderweitig gelöste Ackpflichten kann eine **eigens aktuell berechtigte SL/Verwaltungsrolle** nach Scope-/Grund-/Regelpolicy einen **separaten protokollierten Erledigungs-/Befreiungsstatus** vergeben, die zugehörigen Reminder beenden und ggf. eine rechtmäßig neue persönliche Quittierung getrennt verlangen. Das erzeugt **niemals** den falschen Beleg „Spieler hat selbst quittiert“, enthüllt keine Geheimdaten und verändert keinen Spiel-/Quest-/NPC-/Turn-/Inventarzustand. Exakte Grundregeln wurden mit 02.104 C beschlossen [Details](KARTEN-WORKSHOP-02.104.md).

**Aktueller Fortgang:** [02.104 C](KARTEN-WORKSHOP-02.104.md) erlaubt einen separat autorisierten, begründeten und auditierten Verwaltungsabschluss nicht mehr sinnvoll erfüllbarer oder zulässig erlassbarer Ackpflichten, **ohne eine persönliche Quittierung des Spielers vorzutäuschen**. Nur zugehörige künftige Reminder stoppen, echte ursprüngliche Events und Quittungen unangetastet lassen. **02.105 C** erlaubt aktuell berechtigt freigegebene **neue** persönlich adressierte Ackanforderungen nach heutiger Sicht-/Noticeprüfung, ohne alte administrative Abschlüsse zu reaktivieren [Detail](KARTEN-WORKSHOP-02.105.md). **Zusatz:** Integrierter Kampagnenchat bei Erstellung separat An/Aus. **02.106 C** hat getrennt aktivierbare, aktuell berechtigte Chatkanäle bei Chat An/Aus beschlossen [Detail](KARTEN-WORKSHOP-02.106.md); **02.107 C** hat flüchtige oder gespeicherte Chatverläufe samt historischem Empfängerschutz entschieden [Detail](KARTEN-WORKSHOP-02.107.md); **02.108 C** hat differenziert berechtigte versionierte Edits/Zurücknahmen beschlossen [Detail](KARTEN-WORKSHOP-02.108.md); **02.109 C** hat datensparsame, fallgebundene Chatmeldungen und geschützte Moderationsentscheidungen beschlossen [Detail](KARTEN-WORKSHOP-02.109.md). **02.110** behandelt persönliche Chatfilter.
