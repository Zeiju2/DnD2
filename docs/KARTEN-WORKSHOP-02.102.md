# AdventureShift – Karten-Workshop: Beschluss 02.102 C

**Stand:** 13.10.2026 – Beschluss 02.102 C; Folgeentscheidungen 02.103 C bis 02.105 C beschlossen, nächste offene Frage 02.108  
**Status:** Verbindlicher fachlicher Beschluss und konzeptioneller Umsetzungs-/Testplan; **noch keine Softwareimplementierung**, endgültige API, Datenbankstruktur, globale Kampagnen-Einstellungsführung oder finale MVP-Einstufung.  
**Bezüge:** [02.25 globale Kampagnenstandards und markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.5 Fog/Sicht](KARTEN-WORKSHOP.md) · [02.54–02.64 NPC-Identität/Wissen](KARTEN-WORKSHOP.md) · [02.65–02.67 geheime Würfe und Audits](KARTEN-WORKSHOP.md) · [02.77–02.82 Node-/Graph-/Timer-/Turnfolgen](KARTEN-WORKSHOP-02.82.md) · [02.93–02.98 optionaler Generator, Notizen/Marker und kampagnenweites Voicechat-first/Technikprofil](KARTEN-WORKSHOP-02.98.md) · [02.99 C Ergebnisanträge und Freigaben](KARTEN-WORKSHOP-02.99.md) · [02.100 C Korrektur und Kompensation](KARTEN-WORKSHOP-02.100.md) · [02.101 C berechtigte Korrekturmitteilungen](KARTEN-WORKSHOP-02.101.md).

## 1. Verbindliche Entscheidung 02.102 – Variante C

**Vom Projektinhaber beschlossen: C – Konfigurierbare Lesebestätigung für berechtigt adressierte wichtige Korrekturhinweise.** Für ausgewählte, tatsächlich **nach 02.100 C wirksam gebuchte** und **nach 02.101 C für den konkreten Empfänger berechtigt mitteilbare** Korrekturereignisse kann die Spielleitung mit wirksamen **Kampagnen-/Regelprofil-/Ereignis-/Ziel-/Rollen-/Gruppen-/Szenen-/Personenstandards und markierten 02.25-Ausnahmen** festlegen, ob die Kenntnisnahme **ausdrücklich vom berechtigten Empfänger bestätigt werden soll**. Unwichtige Hinweise dürfen ohne Bestätigung angezeigt oder ganz stumm geschaltet werden. Ein Empfänger, dem das Ereignis nach aktueller Geheimnis-/Fog-/NPC-/Quest-/Notiz-/Wurf-Policy nicht sichtbar gemacht werden darf, wird **nicht** durch eine Bestätigungspflicht zur Offenlegung gezwungen.

**Grundsatz:** **Zugestellt ≠ angezeigt ≠ gelesen ≠ ausdrücklich quittiert.** Ein technischer Transport-Erfolg oder das bloße Öffnen einer Meldung gelten **nicht automatisch** als ausdrückliche Kenntnisnahme. Erst eine bewusste UI-Aktion der aktuell berechtigten Person, beispielsweise „Zur Kenntnis genommen“, erzeugt einen **eigenständigen nichtweltwirksamen Quittierungsbeleg**. Diese Quittung bedeutet *Kenntnisnahme einer spezifischen berechtigten Fassung*, **keine Zustimmung** zur Richtigkeit der Korrektur, keine Freigabe nach 02.99/02.100, keinen Würfel- oder Questbeweis und **keine** Änderung von Spielzustand, NPC, Inventar, Alarm, Tür, Node, Timer oder Zug.

**Keine generelle Spielsperre:** Die Wahl von C bedeutet **nicht**, dass grundsätzlich jede Meldung quittiert werden muss oder die Kampagne wegen offline befindlicher, ausgeschiedener bzw. nicht berechtigter Spieler automatisch angehalten wird. **Wie mit länger ausstehenden Quittungen (Erinnerungen, SL-Hinweise, Fristen, Eskalation, mögliche lokale Maßnahmen) umzugehen ist, ist die gesonderte nächste Frage 02.103.** Ohne deren Beschluss keine globalen Turn-, Quest-, Welt- oder Session-Blocker einplanen.

## 2. Konfigurierbarkeit, Geltungsbereich und Berechtigung

| Aspekt | Verbindliches fachliches Ziel |
| --- | --- |
| **Pflichtstufe für geeignete Mitteilungsklasse** | Normaler Hinweis ohne Quittung **oder** ausdrücklich anzuerkennender wichtiger Hinweis, soweit 02.101-Sichtbarkeit den Empfänger tatsächlich zulässt |
| **Scope/Defaults** | Kampagne, Regelprofil, Korrekturereignisklasse, konkreter Ziel-/NPC-/Quest-/Charakterkontext, Szene, Rolle, Gruppe oder gezielt berechtigter Empfänger mit erkennbarer 02.25-Ausnahme |
| **Adressat** | Nur die aktuell echte berechtigte Person, der mindestens eine fachlich ausreichende **bereinigte** Mitteilung überhaupt offenbart werden darf |
| **Rechte** | Mitteilung lesen, eigenen Empfangs-/Lesestatus sehen, eigene Kenntnisnahme ausdrücklich quittieren und den berechtigten Quittierungsstand verwalten/prüfen sind getrennte Capabilities |
| **Nicht automatisch erteilt** | Antrags- oder Korrekturausführungsrecht, private Notizleserechte, Zugriff auf geheime Würfel, fremde Quittungen oder SL-/Server-Originalaudit |
| **Keine sichtbare Nachricht / keine Berechtigung** | Keine Pflichterzeugung für den geheimen Sachverhalt, kein „Du musst unbekannte Information bestätigen“-Hinweis, kein verstecktes Count/Badge |

**Policy-Auflösung:** Zuerst echte 02.100-Commit-/Eventklasse, dann das 02.101-erlaubte **konkrete Feld-/Empfängerprojektionsrecht** und tatsächliche aktuelle 02.25-Kampagnen-/Regel-/Objekt-/Gruppen-/Rollen-/Personenpolicy; erst darauf darf 02.102 die tatsächlich zulässige Quittierungsanforderung anwenden. Ein „kritisch“-Label der SL darf **nie** die Quell-ACL überschreiben. Die Meldung kann eine bereinigte neutrale Fassung besitzen; zur Kenntnisnahme kann nur genau diese autorisierte sichtbare Fassung, **nicht** ein verborgenes Original-/Würfel-/Questdetail, verbindlich angeboten werden.

**Konfigurationsänderungen:** Bei Rollen-/Gruppen-/Kampagnen-/Fog-/Wissens-/Sicht-/Noticepolicywechsel den wirksamen Umfang und die Rechtmäßigkeit noch ausstehender Anforderungen neu bestimmen. Bestehende Quittungsbelege bleiben als historischer Beweis der **damals ausdrücklich quittierten zugelassenen Fassung** erhalten, aber bei späterem Berechtigungsentzug nicht weiter über bisherige Such-/Inbox-/Realtime-/Exportprojektionen herausgeben. Es ist kein „widerrufe bereits gehörtes Wissen“ möglich.

## 3. Zustände und präzise Semantik

**Konzeptionelle Status-/Feldtrennung, keine bereits implementierte Zustandsmaschine:**

1. **Notice candidate / berechtigte Veröffentlichung:** Ein tatsächlich gebuchtes Korrektur-/Kompensationsevent nach 02.100 hat potenziellen Mitteilungsanlass. Ob die Person eine Nachricht erhalten darf, legt allein 02.101 mit aktuellen Source-/Target-/Fieldrechten fest.
2. **Quittierung anforderbar:** 02.102-Policy fordert für den berechtigten Empfänger und die konkrete **sichtbare Notice-Fassung/Revision** eine ausdrückliche Bestätigung. Stumme oder für ihn unberechtigte Mitteilungen erzeugen keine sichtbare/abzuzählende offene Pflicht.
3. **Zustellung versucht / ausgeliefert:** Technisches Senden/Zustellen, etwa via Realtime oder nach Reconnect, ist separat. Ein erfolgreiches Server-Publish beweist **nicht**, dass die Person die Nachricht gesehen oder verstanden hat.
4. **Angezeigt / geöffnet / gelesen (soweit tatsächlich feststellbar):** Ein geeigneter erlaubter Client kann einen eigenen Lesezustand dokumentieren. Dieser kann helfen, aber **wird nicht automatisch zur ausdrücklichen Bestätigung hochgestuft**. Reine Hintergrundsynchronisierung, Tab-Fokus oder Push-Vorschau sind kein sicherer Lesebeweis.
5. **Ausdrücklich quittiert:** Berechtigter Empfänger betätigt eine eindeutig beschriftete UI-Aktion zur spezifischen sichtbaren Revision. Der Server prüft Auth/Teilnehmer/Sichtrechte, aktuelle Anforderung, Policy-/Notice-Version und den **konkreten Empfänger**, erstellt genau einmal einen geschützten Beleg; gleicher Reconnect-/Retry-Schlüssel liefert denselben Beleg, nicht weitere Quittungen.
6. **Ausstehend / veraltet / entfallen / durch neue Version ersetzt:** Wird die reale Korrektur ergänzt, der Hinweis wesentlich geändert, ein Empfänger abgemeldet oder seine Berechtigung widerrufen, müssen offene Einträge anhand aktueller Policy sicher neu bewertet werden; **keine** veraltete Quittierungsanforderung für ein neues Geheimnis oder eine inzwischen andere Notice-Fassung. Eine bereits gegebene Quittung gilt **nicht automatisch für eine neue fachlich wesentliche Revision**.

**„Gesehen“ ist kein semantischer Vertrag:** Ob der Empfänger die Aussage geistig verstanden oder mündlich akzeptiert hat, kann die Software nicht beweisen. Die Funktion protokolliert ausschließlich eine **bewusste Bedienhandlung** mit Kenntnisnahmeerklärung für den ausdrücklich sichtbaren Hinweis. Eine Quittung ist weder Rechtsunterschrift noch Zustimmung zur Spielleiterentscheidung.

**Datenschutz und Identität:** Verknüpfte Korrektur-/Notice-/Personen-/Kampagnen-/Revisions-IDs, serverseitiger tatsächlicher Zeitstempel und erlaubter Kenntnisnahmestatus als Minimalbeleg vorsehen; ursprüngliche privaten Notes, geheime Würfel und komplette SL-Begründungen **nicht** ungefiltert als Quittierungstext speichern. Anzeige anderer Spieler-Quittungen, aggregierter Zahlen und Detailbelege nur bei aktuellem spezifischem Verwaltungsrecht, nie als ungeschützte globale Lobbyliste.

## 4. Architekturkandidaten (unverbindliche Namen)

Mögliche fachliche Objekte: `CorrectionNoticeAcknowledgementPolicy`, `AcknowledgementRequirement`, `AcknowledgementRecipientScope`, `AcknowledgementNoticeRevision`, `AcknowledgementReceipt`, `AcknowledgementStatusProjection`, `AcknowledgementPolicyVersion`, `AcknowledgementAccessPolicy`, `AcknowledgementOperationId`, `AcknowledgementAuditLink`, `AcknowledgementRevocationEvent`. **Keine freigegebene API, Datenbank, Klassen- oder Endpunktdefinition.**

Erforderliche stabile Identitäten als Architekturentwurf: Kampagne und ggf. Regel-/Szene-/Rollen-/Gruppenpolicy, autoritatives **Correction-/Compensation-Commit** aus 02.100, Notice-ID/autorisiert projizierte fachliche Revision aus 02.101, tatsächlicher Empfänger (Spieleridentität, nicht nur eine wechselnde Gruppenzugehörigkeit), Notice-/Request-/Receipt-/Operation-ID, aktueller Scope-/Access-/Policy-Stand, idempotenter Ack-Key sowie für getrennte Auditprojektionen die jeweilige Quell-Event-/Korrekturkorrelation.

**Kein mandanten-/kampagnenübergreifendes Vermischen:** Eine Spieleridentität mit Rechten in Kampagne A kann nicht über globale Acklisten Nachrichten/Events aus B sehen. Wenn mehrere Geräte desselben Spielers verbunden sind, stellt die autorisierte Quittung **einmal pro erforderlich bestätigtem Notice-/Empfänger-/Revision-Scope** aus, synchronisiert diesen Status sicher an die anderen aktuell autorisierten Geräte und erzeugt nicht mehrere unabhängige „ja“-Wirkungen.

## 5. Berechtigungs- und Reconnect-Sicherheit

- **Alle Reads nach aktuellem 02.101-Scope:** Offen-Counts, Notifications, Detailansicht, Suchtreffer, Badge, Push- und Realtime-Subskription, Statuslisten, Verwaltungsreport, Verlauf und Export filtern getrennt nach aktuellem Empfänger-/Fog-/NPC-Identitäts-/Quest-/Secret-/Wurf-/Notiz-/Rollenrecht, inklusive revokter Grants.
- **Keine Existence-Leaks:** Die Zahl offener geheimer Quittungen, unbekannte Zielnamen, Gruppen-/Rollenmitglieder, Korrekturgrund oder Timer des Auslösers dürfen nicht indirekt über Anzeige, leere Fehlermeldung, Timing, Pagination oder SL-Status an unberechtigte Spieler gelangen. Auch „Bitte quittiere einen geheimen NPC“ ist verboten.
- **Ausstehende Aufforderungen bei Entzug:** Wenn Empfänger vor dem Empfang sein gültiges Recht verliert oder die relevante Notice inzwischen stumm/versteckt wurde, die Pflicht in seiner Projektion als nicht mehr anforderbar ausblenden/aussetzen bzw. mit gültiger Policy schließen; keinen Client mit einer unmöglich rechtmäßig einsehbaren Pflicht belasten.
- **Offline:** Offen gebliebene, aktuell legitime Anforderungen können bei berechtigtem Reconnect erneut sichtbar werden und dann bewusst quittiert werden. Offline selbst ist **keine** Verweigerung oder gültige Quittung. Noch keine automatischen Reminder-/Fristen-/Esklationsregeln aus 02.103 vorwegnehmen.
- **Mehrere Geräte, Wiederholung, Race:** Dieselbe Ack-Operation max. einmal buchen, doppelte Klicks/Replays/Reconnects deduplizieren; falls zwischen Darstellung und Klick Permission, Notice-Revision oder Policy wechselt, neu validieren, nicht mit altem Berechtigungs-Snapshot quittieren.
- **Korrektur überarbeitet:** Wurde derselbe NPC-Wert nach einer zweiten echten Korrektur nochmals verändert, ist zu prüfen, ob eine neue fachlich relevante sichtbare Nachricht/Revision nach 02.101 existiert und eine neue Ackpflicht **erst nach gültiger aktueller Policy** entsteht; alte Quittungen nicht unverändert als Zustimmung zum neueren Status ausgeben.
- **Benachrichtigungsunterdrückung:** Kein Ack bei einer per 02.101 abgeschalteten oder nur geheim vorhandenen Mitteilung. Das getrennte unveränderliche interne Correction-Audit bleibt trotzdem bestehen und darf nicht als Spieler-Inbox verwendet werden.

## 6. Wirkungslosigkeit für die Spielwelt

**Quittieren ≠ Freigeben:** Ein Spieler klickt „Zur Kenntnis genommen“. Das ändert nur seine berechtigte Informations-/Quittierungsprojektion; es **genehmigt weder den ursprünglich mündlichen Ausgang nach 02.99 noch eine Korrektur/Kompensation nach 02.100**. Auch das Entfernen, Wiedervorlegen, Exportieren, Lesen oder automatische Zustellen eines Hinweises führt zu **keiner** Ausführung von:
- Quest-/Inventar-/Item-/Geld-/Ressourcen-/NPC-/Figuren-/Statusänderungen,
- Türen, Sensoren, Licht, Alarm, Geräuschen, Node-Graphen, Script-/Portimpulsen,
- Würfeln/Checks, Zeitereignissen/Timern, Next-Player-/Turn-/Initiativewechseln,
- Fog-Freigaben, Spielerwissen oder eigentlich privaten Notiz-/Markerrechten.

**Sichtbarer gültiger Weltzustand immer unabhängig:** Ein erlaubter korrigierter NPC-Wert erscheint beim berechtigten Spieler, selbst wenn er den dazugehörigen optional als „wichtig“ markierten Hinweis noch nicht quittiert hat. Eine notwendige Quittung ist **keine Transaktionsvorbedingung für das bereits bestehende korrigierte Ereignis** und kein Mechanismus, bestehende korrekte World-State-Realtime-Projektionen zu verzögern. Sicherheitschecks sind nie abschaltbar, Quittierungsfunktion und Missionsgenerator bleiben optional.

## 7. Fachlicher Umsetzungsplan – keine Programmierung

1. **Feld-/Recipient-/Ack-Policy modellieren:** Die bestehende 02.101-Noticeprojektionslogik als zwingende Obergrenze benutzen; 02.25-Kampagnen-/Regel-/Ereignis-/Rollen-/Ziel-/Einzelausnahmen und „Ack nötig: ja/nein“ für berechtigte kritische Notice-Klassen beschreiben. Kein Zwang für stumme/geheime Meldungen.
2. **Notice-Revision und Ackidentität definieren:** Geeignete stabile Correction-/Notice-/Person-/Revision-/Operation-IDs, explizite Benutzeraktion, idempotente serverseitige Belege und Policyversionsbindung. Transport-, Anzeige-, Lese- und ausdrückliche Quittierungszustände getrennt persistierbar/ableitbar vorsehen.
3. **Server-Ack-Gateway isoliert planen:** Autorisierte aktuelle Recipient-/Secret-/Fog-/Group-/Quest-/Notice-/Revision-/Policyprüfung; Retry-/Race-/Replay-/Reconnectschutz, keine direkte oder indirekte Schnittstelle zum World-/Node-/Würfel-/Korrektur-Commit-Gateway. Minimale Auditbelege, keine privaten Notiz-/Geheimwurfpayloads.
4. **Client-Ansichten später spezifizieren:** Berechtigter Spieler sieht eine klar verständliche sachlich bereinigte Meldung und, wenn nötig, einen ausdrücklich beschrifteten Quittierungsakt; SL kann nur gemäß eigenen Verwaltungs-/Feldrechten den relevanten Kenntnisnahmestand beurteilen. Detailmenüs, globale Assistenten und MVP-Reihenfolge weiterhin erst nach Gesamtworkshop.
5. **Revocation und Revision berücksichtigen:** Rechteentzug, Gruppenaustritt, Fog-Änderung, News-Versionierung, mehrere Geräte, Offline und unbekannte/geheime Ziele mit Schutz vor alter, unerlaubter Ackpflicht oder alter Zustimmung.
6. **Rückmeldung/Auswertung testen:** Feldgefilterte SL-Reports, berechtigte eigene Quittungen, keine geheimen Badge-/Count-/Index-Leaks, korrekt synchrone Weltzustände ohne Ack und Schutz vor Spielereignissen durch UI-Nachricht.
7. **Folgeentscheidung 02.103 C integriert:** Optionales Erinnern/SL-Eskalation nur für tatsächlich berechtigt sichtbare und aktive Ackanforderungen nach konfigurierbarem Zeit-/Retry-/Unterbrechungsschema vorsehen, aber keine erzwungene Automatik oder Sessionblockade [Details](KARTEN-WORKSHOP-02.103.md). Über mögliche separate administrative Befreiung entscheidet 02.104.

## 8. Abnahmetests

| Fall | Erwartetes Ergebnis |
| --- | --- |
| Normale Korrekturmeldung, Ackfunktion nicht nötig | Spieler kann lesen/ignorieren; kein zusätzlicher Quittierungszwang |
| Als wichtig markierte sichtbare NPC-Korrektur | Aktuell berechtigter Empfänger erhält passende bereinigte Nachricht plus bewusste „Zur Kenntnis genommen“-Option |
| Mitteilung wurde per Server versandt, Benutzer ist offline | Transport-/Deliveryzustand kann geführt werden, aber **keine** vorgetäuschte gelesene oder quittierte Kenntnisnahme |
| Spieler öffnet oder scrollt Hinweis, klickt nicht „Zur Kenntnis genommen“ | Bei unterstützter Messbarkeit evtl. geöffnet/gelesen, aber **nicht quittiert** |
| Spieler bestätigt zulässige aktuelle Mitteilung aktiv | Genau ein serverseitig autorisierter Ackbeleg für diese Empfänger-/Noticerevision |
| Spieler doppelklickt oder reconnectet | Kein doppelter Ackbeleg, kein neues Welt- oder Kompensationsereignis |
| Derselbe Spieler nutzt PC und Tablet | Nach legaler Quittung konsistenter Status auf aktuell berechtigten Geräten, kein doppelter Pflichtfall |
| Spieler gehört nicht zum berechtigten Personenkreis | Kein Noticeinhalt, kein offen/ungelesen-Badge, keine Ackpflicht/Quittierungs-API |
| Korrektur betrifft geheimen NPC oder geheimen Wurf | Unberechtigter sieht weder „bitte bestätigen“, Count, unbekanntes Ziel, Ursprung noch Wurf |
| SL markiert Meldung „kritisch“, Ziel ist für Spieler geheim | Flag hebelt die Fog-/NPC-/Quest-/Secret-Rechte nicht aus; für diesen Empfänger kein legaler Ackzwang |
| SL schaltet Korrekturmeldung nach 02.101 stumm | Neue Ackpflicht für diesen stummen Hinweis kann nicht wirksam ausgeliefert werden |
| Gruppenrolle wird zwischen Zustellung und Klick entzogen | Server prüft Rechte erneut; Klick wird nicht unberechtigt quittiert, alte Notice nicht nochmals vom Server abrufbar |
| Korrekturmeldung erfährt wesentliche neue Revision | Alte Quittung gilt nur für alte erlaubte Revision; neue Anforderung nur bei eigener aktuellen Berechtigung/Policy |
| SL sieht Quittierungsübersicht | Nur berechtigte Empfänger-/Status- und Zielangaben, keine geheimen Namen oder privaten Spielernotizen durch Report/Count |
| Spieler hat Hinweis nicht quittiert | Tatsächlich korrigierter, für ihn sichtbarer NPC-/Quest-/Charakterzustand ist **trotzdem** richtig und aktuell |
| Kampagne ist Voicechat-first ohne KI, Generator oder integrierten Voicechat | Manuelle Berechtigtenhinweise und optionale Quittierungen funktionieren unabhängig |
| Benutzer klickt „Zur Kenntnis genommen“ | Keine Quest-/NPC-/Item-/Ressourcen-/Tür-/Alarm-/Node-/Würfel-/Timer-/Next-Player-Wirkung |
| SL will 02.99-C-Genehmigung über Lesebestätigung ersetzen | Abgelehnt: Ack ist weder Antrag noch autorisierte Weltfreigabe |
| Mehrere alte offene Ackpflichten nach Berechtigungsentzug | Keine unberechtigte Wiederzustellung/offenen Zähler; internes Audit bleibt geschützt |
| Browser manipuliert Notice-/Empfänger-/Policyversions-ID | Keine fremde Quittung, keine Geheimdaten und kein Erfolg ohne aktuelles Recht |
| Ganze Gruppe offline, eine Nachricht verlangt Ack | **Kein** automatisches globales Blockieren von Session, Zugfolge oder World-Sync |
| SL fragt nach Erinnerungs-/Eskalations-/Fristverhalten | Noch **offen als 02.103**, nicht stillschweigend automatisch implementieren |

## 9. Grenze der Entscheidung und nächste offene Frage

**Festgelegt:** Variante **C**: Die SL kann je geeigneter Korrekturmitteilung, Kampagne, Rolle und erlaubter Ausnahme für **aktuell tatsächlich berechtigte Empfänger** eine ausdrückliche Quittierung verlangen oder weglassen. Anzeige-/Lese-/Transport-/Ackzustände sind getrennt, ein Ack ist eine bewusste idempotente, auditiert geschützte und weltwirkungsfreie UI-Aktion für die **zugelassene Fassung**. Rechte, Fog, geheime Würfe, NPC-/Questwissen und private Spielernotizen behalten Vorrang; tatsächliche berechtigte Weltprojektion und 02.100-Korrekturaudit werden nicht von der Quittierung abhängig.

**Nicht beschlossen:** Finale UI-/DB-/API-Namen, konkrete Standardzeiten und Kanäle für die inzwischen unter 02.103 C beschlossenen **optional** aktivierbaren Erinnerungs-/Eskalationsfunktionen, Quittierungspflicht für alle Meldungen, automatische Session-/Turn-Blockaden, Push-/E-Mail-/Voicepflicht, MVP-Reihenfolge oder ein abschließender Kampagnenassistent.

## Archivierte Folgefrage 02.103 – inzwischen als C beschlossen

**Beispiel:** Ein Spieler erhielt einen für ihn berechtigt sichtbaren Hinweis, dass seine Ausrüstung nach einer fehlerhaften Buchung korrigiert wurde. Die SL hat nach **02.102 C** für diese Klasse ausdrücklich eine Kenntnisnahmebestätigung angefordert. Der Spieler war längere Zeit offline oder hat die Mitteilung noch nicht bestätigt. Wie soll die Software damit umgehen?

- **A – Nur dauerhaft offen halten:** Ausstehende erlaubte Quittierungen bleiben als unbestätigt erkennbar. Keine automatischen Erinnerungen, Übersichten oder Hinweise für die SL.
- **B – Session automatisch sperren:** Eine einzige ausstehende Quittung hält ohne aktuelle Kontext-, Rechte- oder Offlineprüfung die gesamte Kampagne/alle Spieler/den Turn an, bis der jeweilige Benutzer bestätigt.
- **C – Optionales Erinnern und berechtigte SL-Eskalation ohne pauschale Spielsperre (Empfehlung):** Für tatsächlich relevante und weiterhin aktuell berechtigte Quittierungsanforderungen kann die SL nach gültigem Kampagnen-/Rollen-/Ereignis-/Empfängerstandard passende **Erinnerungs- und Eskalationsregeln** vorsehen. Ausstehende Status werden der berechtigten SL nach Secret- und Fogschutz angezeigt; einzelne Spieler können konfigurierbar erinnert werden. Ohne explizit eigene rechtmäßige spätere Spielentscheidung **kein** globaler automatischer Quest-/Zug-/Sessionblock durch offline oder inzwischen unberechtigte Mitspieler. Häufigkeit, Fristen, Ausnahmen und Abbruch bei Revocation würden erst mit Annahme von 02.103 geplant.

**Aktueller Fortgang:** [02.103 C](KARTEN-WORKSHOP-02.103.md) ist beschlossen: gezielt konfigurierbare Erinnerungsfristen/Intervalle, Empfänger- und SL-Scope-Rechte, Wiederholungsgrenzen, Stop bei Quittung/Revocation/Revision und keine globale Spielsperre. **02.104 C** hat den eigenen berechtigten und protokollierten administrativen Erlass/Abschluss nicht mehr sinnvoll anforderbarer Quittungen ausdrücklich **anders als eine persönliche Spielerkenntnisnahme** beschlossen [Detail](KARTEN-WORKSHOP-02.104.md). **02.105 C** hat eine neue bewusst berechtigte Ackanforderung nach wieder gültiger Sicht-/Empfängerpolicy unter Erhalt des alten Abschlussbelegs beschlossen [Detail](KARTEN-WORKSHOP-02.105.md). Zusatz: Integrierter Chat separat bei Kampagnenerstellung An/Aus. **02.106 C** hat konfigurierbare berechtigte Kampagnen-/Gruppen-/DM-/SL-Chats bei vorrangigem Chat An/Aus beschlossen [Detail](KARTEN-WORKSHOP-02.106.md); **02.107 C** hat historische Leserechte für gespeicherte/flüchtige Chatverläufe und Aufbewahrung geregelt [Detail](KARTEN-WORKSHOP-02.107.md); **02.108** fragt nach Nachrichtenedits.
