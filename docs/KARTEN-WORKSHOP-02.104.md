# AdventureShift – Karten-Workshop: Beschluss 02.104 C

**Stand:** 13.10.2026 – Fachbeschlüsse 02.1 bis 02.104; nächste offene Frage 02.105  
**Status:** Verbindlicher fachlicher Beschluss und konzeptioneller Umsetzungs-/Testplan; **keine Softwareimplementierung**, keine endgültigen API-/Datenbankverträge, kein fertiger globaler Kampagnenassistent und keine finale MVP-Priorisierung.  
**Bezüge:** [02.25 Kampagnenstandards und markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.5 Fog/Sicht, 02.54–02.64 NPC-Wissen, 02.65–02.67 geheime Würfe/Audit](KARTEN-WORKSHOP.md) · [02.77–02.82 Node-/Graph-/Eventkontrolle](KARTEN-WORKSHOP-02.82.md) · [02.93–02.98 optionaler Generator, private Notizen/Marker und Kampagnen-Automatisierung](KARTEN-WORKSHOP-02.98.md) · [02.99 C manuelle Ergebnisse/Freigaben](KARTEN-WORKSHOP-02.99.md) · [02.100 C Korrektur/Kompensation](KARTEN-WORKSHOP-02.100.md) · [02.101 C Mitteilungs-Sichtrechte](KARTEN-WORKSHOP-02.101.md) · [02.102 C persönliche Kenntnisnahme](KARTEN-WORKSHOP-02.102.md) · [02.103 C Erinnerungen/SL-Eskalation](KARTEN-WORKSHOP-02.103.md).

## 1. Verbindliche Entscheidung 02.104 – Variante C

**Vom Projektinhaber gewählt: C – kontrollierter administrativer Abschluss bzw. Erlass einer nicht mehr sinnvoll erfüllbaren Kenntnisnahmeanforderung.** Für eine nach 02.102 C ursprünglich tatsächlich gültige, aber mittlerweile **nicht mehr sinnvoll anforderbare, gegenstandslose oder nach ausdrücklich gültiger Policy erlassbare** persönliche Quittierung darf eine **aktuell eigens berechtigte Spielleitung/Verwaltungsrolle** einen **separaten, begründeten und nachvollziehbar protokollierten Verwaltungsabschluss** ausführen. Er beendet die zugehörigen offenen Erinnerungen/Eskalationen aus 02.103 C, **ohne eine persönliche Quittierung vorzutäuschen** oder echte zuvor gebuchte Ereignisse nach 02.99/02.100 zu manipulieren. Der Grund und die verantwortliche berechtigte Person werden als geschützt abrufbarer eigener Verwaltungsbeleg gespeichert.

**Unverhandelbare Unterscheidung:** `persönlich bestätigt` / `vom Empfänger selbst quittiert` ist ein einzig durch 02.102 C zulässig ausgelöstes persönliches Ack-Ereignis. `administrativ geschlossen`, `erlassen`, `gegenstandslos`, `storniert` oder `durch neuere Notice ersetzt` ist **niemals gleichbedeutend** mit `persönlich gelesen`, `quittiert`, `verstanden`, `akzeptiert` oder `zugestimmt`. Auch ein beliebiger SL-/Admin-Button darf keine alte Quittungs-ID im Namen des Spielers erzeugen. In Ansichten/Auswertungen zählen persönliche Quittungen und administrativ erledigte Anforderungen **getrennt**.

**Beispiel:** Spieler A hat die Gruppe endgültig verlassen und darf die alte NPC-Mitteilung inzwischen nicht mehr einsehen. Eine berechtigte SL kann – **ohne geheime früher sichtbare Inhalte neu offenzulegen** – die offen gebliebene Anforderung mit zulässigem Grund `Gruppenaustritt` administrativ schließen. Status: „administrativ erledigt, nicht persönlich bestätigt“. Weitere Reminder an A und entsprechende neue Eskalationen enden. Die ursprünglich tatsächlich erfolgte Korrektur, ihr Audit, ihre Sicht-/Gruppenrechte und alle aktuellen Weltzustände bleiben unverändert.

**Beschlussgrenze:** Diese Variante genehmigt das **prinzipielle Recht** zur gesonderten Schließung/Befreiung mit aktueller fachlicher Policy. Die genaue UI, finalen Grundcodes, Rollendefinitionen, Genehmigungsstaffeln, Retention und Reaktivierungsstrategie werden später spezifiziert; insbesondere ist **02.105** die nächste Frage zur möglicherweise kontrollierten Wiederaufnahme bereits administrativ geschlossener Anforderungen.

## 2. Fachlicher Scope, Gründe und Befugnisse

| Fachaspekt | Geplantes Verhalten und Grenze |
| --- | --- |
| **Betroffene Anforderung** | Eindeutig benannte tatsächlich bestehende 02.102-Ack-Anforderung mit Kampagne, erlaubter 02.101-Notice-Revision, ursprünglichem Empfänger und noch nicht anderweitig abgeschlossener wirksamer Version |
| **Zulässige Gründe (Kandidaten)** | Gruppen-/Kampagnenaustritt, dauerhaft nicht erreichbarer Empfänger, Entfall des rechtmäßigen Sicht-/Notice-/Ackrechts, zurückgezogene/ersetzte Notice, korrigiertes Ziel nicht mehr relevant, ausdrücklich regelgerecht erlassene Pflicht, andere dokumentierte fachlich zulässige Gründe |
| **Administrative Befreiung** | Eine noch sichtbare, prinzipiell erfüllbare Pflicht darf nur dann bewusst erlassen werden, wenn die aktuelle Policy genau dafür eine erforderliche Berechtigung und einen begründeten Ermessensentscheid vorsieht; `offline` allein erzeugt keine automatische Befreiung |
| **Schließung wegen Wegfall** | Bei nicht mehr gültiger Notice-/Empfängerberechtigung darf das System eine Verpflichtung nach fachlich gesicherter Policy als nicht mehr anforderbar markieren; ein zusätzlicher berechtigter Verwaltungsabschluss darf organisatorische Altfälle sauber beenden |
| **Eigene Abschlussberechtigung** | `close/waive acknowledgement requirement` getrennt von `notice lesen`, `persönlich quittieren`, `Reminder konfigurieren`, `Reminder-Eskalation sehen`, `Korrektur freigeben` und `historisches Audit einsehen` |
| **Entscheider-/Schutzpolicy** | Bei fachlich besonders kritischen Anforderungen darf eine ausdrücklich konfigurierte zusätzliche Berechtigtenfreigabe erforderlich sein; ein solcher Antrag/Preview ist selbst effectfrei bis zum gültigen administrativen Commit |
| **Benachrichtigung über Abschluss** | Abschluss ist kein Zwang zur Veröffentlichung alter geheimer Notice-Daten. Ein erlaubter organisatorischer Hinweis an SL/Empfänger kann nur über eigene passende, nach 02.101 begrenzte Mitteilungsrechte erfolgen; keine pauschale Fremdinformation |
| **Historische Auswertung** | Separate Kategorien: `persönlich quittiert`, `offen`, `administrativ erlassen/geschlossen`, `gegenstandslos/ersetzt`, ggf. `Konflikt/Neubewertung nötig`; kein Vermischen zu „100 % Spieler haben bestätigt“ |

**Vereinbarkeit mit 02.25:** Kampagne/Regelprofil → Ereignis-/Korrekturtyp und sichtbare 02.101-Notice → Ackpflicht/Empfängerscope 02.102 → aktuelle 02.103-Erinnerungs-/Eskalationspolicy → zulässige Abschlussart/Begründung/Verwaltungsrolle → markierte Szenen-/Objekt-/Gruppen-/Personenausnahmen. **Eigene Authentifizierung, echte Rechte, Serverintegrität, Daten- und Secret-Schutz bleiben zwingend** und können weder durch globale Voreinstellung noch Einzelausnahme ausgeschaltet werden.

**Nur mit zulässigem Kontext:** Eine verwaltende Rolle, die zwar den neutralen offenen Verwaltungsfall behandeln darf, aber keinen Zugriff auf die private Ursprungsnotiz oder einen geheimen NPC besitzt, soll nur die **minimal notwendigen, selbst zulässigen Verwaltungsfelder** sehen. Ein generischer Hinweis `nicht mehr anforderbar` darf bei Bedarf den eigentlichen Geheimnisgrund gerade **nicht** verraten. Ohne dafür passende echte Befugnis darf auch eine SL keinen fremden/anderen Kampagnenfall abschließen.

## 3. Statusmodell ohne gefälschte Spielerquittung

Fachlich getrennte Achsen, keine fertige Datenbank:

1. **Persönliche Kenntnisnahme (02.102):** Persönlich quittiert nur durch bewusstes, autorisiertes Ack des wirklichen Empfängers für die konkret berechtigt sichtbare Notice-Revision. Ein nachträglicher Verwaltungsabschluss kann einen vorhandenen echten Ackbeleg nicht rückwirkend ausradieren oder durch fremden Ack ersetzen.
2. **Organisatorische Pflicht (02.104):** `offen`, `administrativ erlassen`, `administrativ geschlossen – derzeit nicht anforderbar`, `gegenstandslos/storniert` oder `durch gültige neue Fassung ersetzt`. Die genaue Benennung kann später verfeinert werden; die Trennung zur persönlichen Quittung ist verbindlich.
3. **Erinnerungs-/Eskalationspfad (02.103):** Nach effektivem organisatorischem Abschluss darf für **dieselbe Anforderung/Revision** kein weiterer neuer Reminder bzw. keine neue offene SL-Eskalation ausgehen. Eventuell schon wirklich protokollierte frühere Reminder bleiben im geschützten Verlauf erhalten.
4. **Originalereignis und korrigierte Welt (02.99–02.101):** Bleiben vollständig unverändert und unabhängig vom Verwaltungsabschluss. Kein Rücksetzen von Belohnung, Quest, Türen, NPCs, Alarm, Würfen, Nodes, Timern, Next-Player oder Turngenerationen.

**Ablauf (Entwurf):** Berechtigt sichtbaren aktuellen Verwaltungsfall auswählen → angebotene zulässige Abschlussart und Grund wählen → aktuelle sichere Status-/Folgenvorschau, einschließlich offener Reminder, ohne Weltwirkung → nach Policy gesondert bestätigen/freigeben → **serverseitig unmittelbar beim Commit** Berechtigung, gültige Ack-/Notice-/Revision-/Gruppen-/Ziel-/Secret-/Policyversion und Zustandskollision erneut prüfen → genau **einen** neuen organisatorischen Abschlussbeleg erfassen → weitere zulässige Reminder für denselben Scope stoppen. Ein fehlgeschlagener/veralteter/ungeprüfter Abschluss wird **nicht** als durchgeführt ausgewiesen.

**Wirksamkeit bei ursprünglichem Rechteentzug:** Bei inzwischen geheim gewordener alten Notice muss die Verwaltungs-API nur berechtigte minimale Fallmetadaten akzeptieren, keine clientseitig erfundene Original-Secret-ID als Zugriffsschlüssel. Die Anzeige und eigentliche Bearbeitbarkeit einer „verwaisten“ Pflicht ist eigenständig zu prüfen; ein berechtigt verwaltbarer, intern referenzierter Fall kann abgeschlossen werden, **ohne dem Spieler das Geheimnis wieder zu verraten**.

**Wiederaufnahme bleibt getrennt:** Ein alter administrativer Abschluss darf nicht automatisch durch Gruppenrückkehr, Login, Fog-Wechsel, Policy- oder Notice-Neurevision in `Spieler hat persönlich quittiert` umgewandelt werden. Ob und wie eine neue persönliche Kenntnisnahmeanforderung nach späterer Wiederberechtigung erstellt werden kann, wird in **02.105** gesondert entschieden.

## 4. Architekturentwurf – keine implementierte API

Konzeptionelle Fachobjekte: `AcknowledgementResolutionPolicy`, `AcknowledgementAdministrativeResolution`, `AcknowledgementResolutionReason`, `AcknowledgementResolutionRequest`, `AcknowledgementResolutionDecision`, `AcknowledgementResolutionReceipt`, `AcknowledgementResolutionStatusProjection`, `AcknowledgementResolutionAuditLink`, `AcknowledgementResolutionConflict`, `AcknowledgementResolutionOperationId`, `ReminderCancellationLink`. Die Namen sind **Platzhalter**, keine verbindlichen Klassen-/Tabellen-/Routenbezeichnungen.

**Erforderliche Scope-/Korrelationsfelder (vorläufig):** Kampagne, Original-/Correction-Commit aus 02.100, zulässiger Notice-/Revisionseintrag aus 02.101, tatsächlicher Empfänger und 02.102-`ackRequirementId`, aktueller Status, Policy-/Mitgliedschafts-/Sicht-/Zielrevision, Verwaltungsactor und getrennte Rollenberechtigung, Abschlussart und erlaubter Grund, mögliche unabhängige Entscheidungsperson, serverseitiger Zeit-/Operations-/Idempotenzbeleg, Link zu stornierten 02.103-Reminder-/Escalation-Occurrences. Grundtext, wenn erlaubt, ist **untrusted** Nutzereingabe, kein ausführbarer Node-Code, kein Beweis für echte Spielerkenntnis und kein automatischer Weltzustand.

**Atomare Einmaligkeit:** Effektiver Statuswechsel und geschützter Resolution-Auditbeleg bilden eine wohldefinierte, transaktionale Änderung; parallel oder verzögert arbeitender Scheduler muss aufgrund aktueller terminaler Requirement-Version **vor jedem weiteren Versand** erkennen, dass die Pflicht beendet ist. Eine organisatorische Schließung garantiert nicht das Zurückholen einer **bereits wirklich** zugestellten Nachricht. Retry, Doppelklick, Browserreconnect und parallele SL-Schließung dürfen **maximal einen wirksamen Abschluss** pro zulässiger Requirement-/Revisions-/Operations-Kombination erzeugen.

**Race mit echtem Spieler-Ack:** Trifft während des administrativen Schließens die echte autorisierte persönliche Quittierung ein, darf es **keinen gleichzeitig widersprüchlichen terminalen Zustand** für denselben Anforderungsstand geben. Die Operationen serialisieren/versionieren; bereits erfolgreich gebuchter persönlicher Ack bleibt wahr, der konkurrierende administrative Abschluss darf nicht als zusätzliche persönliche Bestätigung erscheinen und muss sich an den nun aktuellen Stand anpassen bzw. fachlich abgewiesen werden. Umgekehrt darf eine nach dem effektiven administrativen Abschluss verspätete Alt-Quittung **nicht still als rechtzeitig gültiges Ack** einer bereits beendeten Pflicht verbucht werden; neueste Rechte und Requirement-Revision entscheiden.

**Administrative Schließung ist kein dauerhafter Blankoscheck:** Mehrere zeitlich getrennte Altfälle desselben Spielers, derselben NPC-Quest oder derselben Kampagne sind unabhängig. Eine Abschlussberechtigung für ein spezifisches Ack ist **keine** pauschale Vollmacht, private Spielerkommunikation zu lesen, eigene alte Nutzeraktionen zu fälschen oder alle künftigen Quittungen dieses Spielers zu erlassen.

## 5. Datenschutz, Sichtbarkeit und Audit

- **Quellrechte bleiben vorrangig:** NPC-Identität, Questfeld, Fog, Gruppenwissen, geheime Würfel und private geteilte Spielernotizen aus 02.94–02.102 werden weiterhin **pro Quellfeld und aktuellem Empfänger** geprüft. Abschlussgrund, Korrekturursprung, betroffener Spieler, frühere Empfängerlisten oder historisch geheim gewordene Ziele dürfen nicht ungeprüft in SL-/Spieler-/Gruppenansichten auftauchen.
- **Statuszählungen trennen:** `offen`, `persönlich quittiert`, `administrativ erlassen/geschlossen`, `gegenstandslos` dürfen aggregiert nur nach tatsächlich erlaubtem Scope erscheinen; `alle quittiert` ist falsch, wenn einige nur administrativ abgeschlossen wurden.
- **Keine indirekten Existenzlecks:** Inbox-, Badge-, Suche-, Count-, Autocomplete-, Export-, Realtime-, Push-/Webhook- (falls später separat beschlossen), SL-Dashboard- und Fehlermeldungsprojektionen dürfen weder verborgene NPCs/Quests noch fremde geschlossene Acks indirekt verraten.
- **Prüfung beim Abruf:** Rechteentzug, Gruppenaustritt, Rollenwechsel und neue Notice-/Policyversion erfordern aktuelle serverseitige Filterung auch für den Verwaltungsbeleg; kein bloßes CSS-Verstecken von bereits an Spielerbrowsern gesendeten Secret-DTOs.
- **Nachvollziehbarer Grund:** Audit enthält tatsächlich getroffene Verwaltungsentscheidung und minimal notwendige Identitäten/Revisionen; **keine nachträgliche Löschung oder Mutation des ursprünglichen 02.102-Acks** und keine heimliche Überschreibung der 02.99-/02.100-Origin-/Correction-/EffectLedger-Historie.
- **Keine Fake-Replay-Quittung:** Ein persönlicher `AcknowledgementReceipt` aus 02.102 entsteht nur bei der eigenen autorisierten Aktion. SL/Server können nur den klar anders typisierten Administrationsbeleg erzeugen.
- **Abgeschlossene Pflicht ≠ zusätzlich veröffentlichte Nachricht:** Aus einer Schließung darf keine Pflicht folgen, bisher verborgene Correction-/Notice-Inhalte nachträglich an Gruppen auszuleiten. Falls organisatorische Abschlussanzeigen erlaubt sind, nur aktueller minimaler Status.
- **Datenintegrität immer an:** Optionale Komfortmodule dürfen ausschaltbar sein, nicht aber Auth, Vertraulichkeit, Record-Integrität, serverseitige Policy- und Versionprüfung.

## 6. Umsetzungsplan (Fachplanung, keine Programmierung)

1. **02.102-Statusdefinition erweitern:** Ack durch Empfänger, optional administrativ geschlossen/erlassen/gegenstandslos/ersetzt sowie „offen“ als getrennte Fachzustände und klare Erfolgsauswertungen modellieren; bestehende echte historische Acks unverändert lassen.
2. **Policy-Resolver konzipieren:** Separate Administrator-/SL-Rechte und etwaige notwendige Mitfreigabe je Kampagne, Regel, Event, Ziel, Szene, Empfänger, Grund und markierter 02.25-Ausnahme; Berechtigung auf Verwaltungsmetadaten von voller Quell-Secret-Leseberechtigung trennen.
3. **Geschütztes Admin-Preflight/Commit-Modell:** Eindeutige Requirement-/Notice-/Recipient-/Versionsreferenzen, valide Gründe und erlaubte Statusübergänge, effectfreie Vorschau, dann autorisierter atomarer Abschlussbeleg. Keine untypisierte universelle `setAcknowledged=true`-Schnittstelle.
4. **02.103-Scheduler anbinden:** Bei terminalem Verwaltungsabschluss offene künftige Reminder/Eskalationen gezielt invalidieren, Worker vor Versand nochmals prüfen, deduplizierte Cancel-/Ack-/Resolution-/Delivery-Korrelation und Crash-/Reconnect-Retry-Fälle behandeln.
5. **Views/Reports planen:** Abgegrenzte eigene/SL-Ansichten für `persönlich bestätigt` vs. `administrativ erledigt` und offen; keine geheime NPC-, Quest-, Spieler-Notiz- oder Wurfprojektion, berechtigte Summen statt allgegenwärtiger globaler Zähler.
6. **Änderungs-/Ausnahmetests:** Gruppen-/Fog-/NPC-/Quest-Rechteverlust, langzeitoffline Benutzer, erneuter Login, neues Ereignis, mehrfacher Adminabschluss, Doppel-Klick, konkurrierender echter Spieler-Ack, späteres Policy-Update, versteckte Quell-IDs und ursprünglich schon zustellte Reminder prüfen.
7. **Spätere Arbeit trennen:** Alle Modul-/Kampagnensettings und UI-Flows erst nach Abschluss des Gesamtworkshops konsolidieren; **02.105** soll mögliche Reaktivierung/Neuanforderung eines administrativ abgeschlossenen Falls bei wieder bestehendem Recht eigenständig entscheiden.

## 7. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Spieler verlässt Kampagne mit offener Quittung | Berechtigte Verwaltung kann konkret zulässigen Fall als `administrativ geschlossen – nicht persönlich quittiert` erledigen, ohne alte Secret-Notice erneut an Spieler zu senden |
| Spieler war lange offline, ist aber weiterhin berechtigt | Keine automatische Erlassbuchung allein aufgrund der Offlinezeit; eine eigens erlaubte bewusste Befreiung nur nach gültiger Policy und Grund |
| Administrator klickt Schließen | Separater nachvollziehbarer Resolution-Beleg mit actor, Grund, Scope und Version, **kein 02.102-Spieler-Ack** |
| Administrator versucht „als vom Spieler gelesen“ zu markieren | Serverseitig abweisen; kein gefälschter `AcknowledgementReceipt` |
| Adminrecht reicht für neutralen Fall, aber nicht für geheime NPC-Daten | Abschluss allenfalls anhand explizit erlaubter Minimalmetadaten; kein NPC-Name/Position/Quest-/Wurfinhalt |
| Spieler-/SL-Account ohne `close/waive`-Recht sendet manipulierten Request | Abgewiesen; weder fremde Fälle noch Secret-IDs/Counts offenlegen |
| Zwei SL schließen dieselbe Anforderung parallel | Maximal ein effektiver terminaler Abschluss mit idempotentem Beleg; zweiter erkennt den aktuellen Zustand |
| Spieler quittiert unmittelbar vor administrativer Schließung | Persönliche Quittung bleibt echt; spätere Schließung darf sie nicht überschreiben/fälschen |
| Admin schließt, während Spieler alte Notice offen hat | Verspäteter Quittierungsversuch wird anhand aktueller Requirement-/Noticeversion geprüft; keine rückwirkende Fake-Quittung |
| Abschluss greift, Reminder liegt bereits beim Scheduler | Vor tatsächlicher Zustellung erneut prüfen, weitere noch nicht gelieferte Reminder stoppen; bereits erfolgte Zustellungen historisch korrekt |
| Empfänger war wegen Rollenverlust nicht mehr noticeberechtigt | Keine neue Offenlegung bei Abschluss, keine offenen Ack-/Reminder-Counts bei unberechtigtem Empfänger |
| Gruppen-/NPC-/Fogrechte ändern sich zwischen Vorschau und Abschluss | Neue Prüfung, ggf. veralteter Vorgang wird abgewiesen oder ausdrücklich neu vorbereitet |
| Betroffener kehrt zurück oder erhält alte NPC-Sicht neu | Kein stilles Verwandeln administrativer Schließung in Spieler-Ack, keine automatische ungeprüfte Neuanforderung; **02.105 noch offen** |
| SL-Report zählt persönliche Quittungen | Administrativ erlassene Fälle werden separat ausgewiesen, nicht als persönliches Ack mitgezählt |
| SL stornierte zulässige Ackpflicht nach Notice-Aktualisierung | Alte offene Pflicht nur mit passender 02.104-Policy schließen/als ersetzt führen; neue Notice-Anforderung nach ihrer eigenen 02.102-Policy |
| Adminabschluss mit optionalem Grundtext „öffnet Tür“ | Nur untrusted Begründung; keine Tür-/Node-/Quest-/Ressourcen-/Timer-/Turnwirkung |
| Interner Event-/Korrekturaudit wird erneut geprüft | Ursprüngliche Weltaktion, spätere 02.100-Korrektur, 02.102 echte Acks und 02.104 administrative Belege bleiben korrekt getrennt nachvollziehbar |
| Reconnect, Serverneustart und Retry beim Abschluss | Keine doppelten Resolution-/Reminder-Cancel-Effekte, konsistenter terminaler Status |
| Kampagne nutzt vollständig manuelle Spielweise ohne Generator oder Voice-App | Berechtigte administrative Befreiung funktioniert unabhängig von KI, Missionsgenerator, Mikrofon oder Sprachaufzeichnung |
| Abschalten optionaler Reminder/Quittierungs-Komfortfunktion | Bereits legale Originalevents bleiben bestehen; historisches Audit wird nicht gelöscht; neue Aktionen nur nach tatsächlicher aktueller Policy |
| Offline-Spieler kann nie mehr quittieren | Keine globale automatische Quest-/Turn-/Sessionblockade für andere Mitspieler |

## 8. Grenze des Beschlusses

**Verbindlich beschlossen:** Eine tatsächlich berechtigte SL-/Verwaltungsrolle darf nach gültigen Kampagnen-/Ereignis-/Rollen-/Empfänger-Defaults mit 02.25-Ausnahmen eine ungeeignete oder ausdrücklich erlassbare alte Quittierungsanforderung **transparent und auditierbar administrativ abschließen**, mit eigenem Status und Grund, **niemals unter Identität einer vermeintlich zustimmenden Person**. Zu dieser Anforderung gehörende neue 02.103-Remindervorgänge enden; wahre persönlich quittierte Meldungen, historische Korrekturen, echte Würfel, Notizrechte und World-State bleiben unverändert.

**Nicht beschlossen:** Finale Verwaltungsoberfläche, exakte Kategorien/Defaults/Fristen, API-/DB-Namen, Bestätigungsstaffeln, automatische spätere Wiederaufnahme eines geschlossenen Falls, erzwungene externe E-Mail-/Voice-Nachrichten oder endgültige MVP-Priorität. Die vollständige UI-/Konfigurationsplanung bleibt für nach Abschluss aller Featurethemen vorbehalten.

## Nächste Entscheidung 02.105 – Wiederaufnahme einer administrativ geschlossenen Kenntnisnahmeanforderung

**Beispiel:** Eine Quittierung wurde nach 02.104 C beim Ausscheiden von Spieler A korrekt als `administrativ geschlossen – nicht vom Spieler bestätigt` archiviert. Wochen später kehrt A zurück und hat erneut berechtigten Zugriff auf einen inhaltlich weiterhin wichtigen, für ihn sichtbaren korrigierten Gegenstand/NPC-Status. Wie soll AdventureShift damit umgehen?

- **A – Geschlossen bleibt immer geschlossen:** Einmal administrativ beendete Kenntnisnahmeanforderungen können unter keinen Umständen erneut als aktuell zu quittierende Information vorgelegt werden, auch nicht nach neu erlangtem Zugriffsrecht.
- **B – Alle alten Fälle automatisch wieder öffnen:** Jeder Login, Gruppenwechsel oder neues Sichtrecht lässt ungeprüft alle früheren persönlichen, heute womöglich geheimen/irrelevanten Korrekturhinweise mitsamt Reminderpflicht wieder auftauchen.
- **C – Berechtigte kontrollierte Neuanforderung als neuer Status (Empfehlung):** Die SL oder eine nach Kampagnen-/Notice-/Rollen-/Zielpolicy berechtigte Verwaltung kann **bewusst und nachvollziehbar** eine alte administrativ geschlossene Anforderung anhand aktueller 02.101-Sicht-/Geheimnis-/Notice- und 02.102-Quittierungspolicy **neu anfordern**, sofern die relevante zugelassene Mitteilung noch sinnvoll ist. Dafür wird ein **neuer, versionierter, separat sichtbarer Requirement-/Auditbeleg** mit Bezug auf den alten Abschluss geschaffen, statt die ursprüngliche persönliche Quittung oder Abschlussgeschichte umzuschreiben; neue Reminder nur nach aktueller 02.103-Policy. Keine automatische Wiederöffnungsflut, kein geheimes Wissen und keine Spielweltwirkung.
