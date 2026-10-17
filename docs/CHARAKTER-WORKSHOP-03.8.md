# AdventureShift – Charakter-Workshop: Beschluss 03.8 C – konfigurierbare Zustände und befristete Effekte

**Stand:** 17.10.2026. **03.8 C vom Projektinhaber beschlossen.** **04.1 C am 17.10.2026 nachfolgend beschlossen:** [flexible Bewegungsmodi mit gültiger Gegnerentdeckung als optionalem frei→rundenbasiert-Trigger](BEWEGUNG-WORKSHOP-04.1.md). **Nächste grundlegende Frage 04.2:** Token-Größe, Platzbedarf und Kollision; danach weitere Grundsatzfragen der Hauptmodule 04–15.
**Status:** Verbindliche Planung von Datenobjekten, Abläufen, Rechten, Schnittstellen und Abnahmetests; **keine Implementierung**. Konkrete Effektkataloge, Zahlen, genaue Zeit-/Stacking-Formeln, UI, technische API/DB und Priorisierung folgen später.
**Bezüge:** [03.1 Charakterinstanz/-felder](CHARAKTER-WORKSHOP-03.1.md) · [03.2 Mehrfigurensteuerung/Verhexung/Übernahme](CHARAKTER-WORKSHOP-03.2.md) · [03.3 Entwurf-/Veröffentlichungsrechte](CHARAKTER-WORKSHOP-03.3.md) · [03.4 Klassen/Fähigkeiten](CHARAKTER-WORKSHOP-03.4.md) · [03.5 Fortschritt](CHARAKTER-WORKSHOP-03.5.md) · [03.6 kontrollierte Migration](CHARAKTER-WORKSHOP-03.6.md) · [03.7 sichere abgeleitete Werte und eigene/mitgelieferte RulePacks](CHARAKTER-WORKSHOP-03.7.md) · [02.15–02.16 Trigger/Echtzeit-/Rundenzähler, 02.25 ACL, 02.67–02.73 Turns/Next Player, 01 Inventar, 05 Würfel und 07 Regelmodule](FEATURE-WORKSHOP.md) · [Planungsstandard](PLANUNGSSTANDARD.md).

## 1. Verbindlicher Beschluss: C

AdventureShift erhält eine **optional aktivierbare, daten-/regelwerksgetriebene Struktur für Figurenzustände und Effekte**. Berechtigte Autoren können Zustandstypen und Effektvorlagen definieren und über die 03.7-Regelwerksvorlagen speichern und wiederverwenden; beim wirklichen Auslösen entsteht **eine gesonderte konkrete Effektinstanz** mit eigener Lebensdauer, Herkunft, Ziel, Berechtigung und Revisionszustand.

Die Laufzeit kann – soweit vom jeweiligen veröffentlichten Regelprofil unterstützt – **dauerhaft**, **echtzeitbasiert**, **rundenbasiert** oder **durch ein definiertes Ereignis bzw. eine gültige Bedingung beendet** sein. Ein Effekt kann rein informativ/manuell oder ausdrücklich automatisiert wirken. Mögliche, niemals universell fest verdrahtete Wirkungsklassen sind typisierte Boni/Mali auf 03.7-Ableitungen, Modifikation/Blockade erlaubter Aktionen, vorübergehende Fähigkeiten und regelgesteuerte **Verhexung/Charakterkontrolle im bereits beschlossenen 03.2-Rechterahmen**.

**Beispiele, keine vordefinierten Pflichtregeln:**
- „Vergiftet“ kann als bloße Notiz gelten oder über ein passendes Regelprofil einen abgeleiteten Wert beeinflussen bzw. einen ausdrücklich autorisierten Tick-/Schadenseffekt auslösen.
- „Schild für drei Runden“ kann die Verteidigungsableitung nur während der zugrunde gelegten **konkreten** gültigen Turn-/Rundenzählerfolge beeinflussen.
- „Beherrscht bis Schalter X aktiviert wird“ kann eine begrenzte, separat autorisierte zeitweilige Kontrollwirkung vorsehen, deren Ende ein **gültiges Ereignis** aus der 02-Node-/Eventstruktur auslöst. Der Controller erhält keine Konto- oder Geheimdatenrechte.

**Nicht gewählt:** A als alleiniger Standard, bei dem Zustände technisch nur freie Notizen sein dürfen; B als für alle Kampagnen vorgeschriebenes, hartcodiertes Einheits-Statussystem. **Manuelle Kampagnen und einzeln rein beschreibende Effekte bleiben ausdrücklich erlaubt**, auch wenn eine Regelautomatik deaktiviert ist.

## 2. Grunddatenmodell und Verantwortung

1. **StatusDefinition/EffectDefinitionVersion (Arbeitsnamen):** Wiederverwendbare, versionierte, veröffentlichte Typdefinition mit stabiler ID, RulePack-/Bibliotheks-/Kampagnenscope, Besitzer/Quelle, Rechten, verständlicher Bezeichnung, möglichen Wirkungsdeskriptoren, zulässigen Zielen, Dauerarten, Beendigungs-/Entfernungsregeln, Abhängigkeits-/Kompatibilitätsverweisen und Sichtbarkeitsprofil. Eine bloße Umbenennung ändert die technische Identität nicht. Keine beliebigen Skripte.
2. **ActiveEffectInstance (Arbeitsname):** **Eigene persistente Effektinstanz** je tatsächlicher Anwendung: stabile Instanz-ID; Definition und exakte Version; Kampagnen-/Zielcharakter-/ggf. NPC-/Tokenreferenzen; erlaubte Quelle, verantwortlicher Actor und Auslöseereignis; optionaler Ausprägungsparameter; Beginn; gültige Zeitbasis oder Endbedingung; Gültigkeitsstatus; letzte Zustandsrevision; eindeutige Operation-/Event-ID; Sicht-/Bearbeitungsgrenzen. Gleichartige Effekte auf mehreren Zielen oder durch mehrere Quellen bleiben unterschiedliche Instanzen, soweit das Regelprofil das erlaubt.
3. **Definition ist nicht Wirkung:** Entwurf, Vorschau, Bibliothekskopie oder RulePack-Schnellstart aus 03.7 erzeugen **keinen** aktiven Zustand auf Spielfiguren. Die Regel-/Effektvorlage wird nicht mit ihren bereits abgelaufenen oder verbrauchten Laufzeitdaten in eine neue Kampagne übernommen.
4. **Ziele und Abgrenzung:** Aktuelle Grundzielobjekte sind 03.1-CharacterInstances einschließlich geeigneter 06-NPC-Charakterinstanzen. Beziehungen zu 02-Token/Position/Szene bleiben gesondert; **ein grafischer Marker allein** ist kein autorisierter Charakter- oder Weltzustandswechsel. Spätere Effekte auf Räume, Gegenstände oder Fahrzeuge laufen über deren eigene Modul- und Berechtigungsadapter.
5. **Manuell vs. automatisiert:** Eine Definition kann nur eine für Berechtigte sichtbare Notiz/Markierung vorsehen oder deklarative, durch den VPS prüfbare Effekte anbieten. Je Kampagne/Regelprofil und nach passender Ausnahmepolicy darf das Modul ganz aus sein bzw. nur bestimmte Automatikarten verwenden. Dann bleiben Freitextnotizen/SL-Entscheidungen möglich, aber es gibt **keinen heimlich laufenden Effektmotor**.
6. **Zeitbasis eindeutig:** Echtzeit verwendet einen persistent nachvollziehbaren Serverzeit-/Fälligkeitsbezug; Runden verwenden **benannte gültige Rundenzähler-/Turnkontexte**, nicht verstrichene Sekunden. Dauer „3 Runden“ bedeutet nie implizit „3 × 6 Sekunden“. Bei mehreren parallelen Turnkontexten (02.70–02.73) ist festgelegt, welcher Kontext welchen Effekt fortschaltet; fremde Turn-Events dürfen keine Dauer verbrauchen. Kontext-/Zugwechsel referenziert eine aktuelle Generation und keine abgelaufene.
7. **Ereignisbedingtes Ende:** Nur **typisierte, gültige Ereignisse oder geprüfte Zustandsbedingungen** aus passenden 02-Trigger-/Rule-/Quest-/Aktion-Interfaces dürfen End-/Änderungsbedingungen erfüllen. Ein frei erfundener Browser-Event oder ein namensgleicher unberechtigter Node löst keinen Effekt ab. Trigger-Ketten werden gegen Zyklen, unbeschränkte Rückkopplung und Replay abgesichert.
8. **Lebenszyklus:** Ein Effekt wird nach heutiger Identitäts-, Figuren-, RulePack-, Ziel-, Sicht-/Aktions-/Zeitscope-/SL-Policy beantragt, ggf. genehmigt und nur durch **eine** autorisierte, atomare und idempotente Anwendung aktiviert. Danach sind – je Profil – Aktualisieren, Pausieren, Erneuern, Unterdrücken, Entfernen, reguläres Ablaufen und durch Rechte-/Quellenverlust erzwungenes Ende unterscheidbare fachliche Übergänge. Ein abgelaufener Effekt wird nicht nach Reconnect erneut gestartet.
9. **Quelle und Gültigkeit:** Itemeffekte aus 01, 03.4-Fähigkeiten, 05-Würfel-/07-Regelergebnisse, 02-Node-/Szenenevents oder SL-Aktionen können nur nach eigener Autorisierung einen Zustand auslösen. Quellenverlust (etwa Ausrüstung abgelegt, Token/Szene unzulässig, aktive Beherrschung aufgehoben) wird nach definierten RulePackregeln kontrolliert neu bewertet; es gibt keine stillen unbegrenzten Boni aus gelöschten Referenzen.
10. **Trennung von Basis und Ableitung:** Statusmodifikatoren liefern **geprüfte aktive Quellen** an 03.7, ohne gespeicherte Attribut-/Basis-/Fortschrittswerte zu überschreiben. Permanenter Schaden, Ressourcenverbrauch, XP-Vergabe, Würfel, Gegenstandsübergänge, Node-/Weltfolgen oder Zugwechsel sind **getrennt** zu autorisierende echte Aktionen. Eine Statusanzeige, reine Neuberechnung oder wiederholte WebSocket-Zustellung erzeugt keine zusätzlichen realen Commits.
11. **Stacking und Konflikte:** Regelprofile müssen angeben können, ob wiederholte Zustände koexistieren, sich ersetzen, erneuert werden, sich nach begrenzter Regel kombinieren oder als Konflikt abgewiesen werden. Welche konkrete Stackingformel, Vorrangzahl oder maximale Instanzanzahl gilt, wird später definiert. **Ohne eindeutig gültige Regel** keine unkontrollierte Doppelwirkung.
12. **Sicherheit und Kontrollrechte:** Wer Statusvorlagen erstellen, veröffentlichen, sehen, anwenden, ändern, beenden, genehmigen oder geheim halten darf, sind **getrennte Berechtigungen** nach 02.25 und 03.1–03.3. Temporärer Charaktercontroller (03.2) erhält keineswegs automatisch SL-/Admin-/Vorlagen-/Fremdstatusrechte. Ein Kontrollstatus darf höchstens einen explizit genehmigten, beschränkten und widerrufbaren **03.2-ControlGrant** bzw. Aktionsfilter erzeugen; niemals ein anderes Steamkonto übernehmen, fremde Charakterbögen offenlegen oder Rollenmitgliedschaften umschreiben.
13. **Sichtbarkeit und geheime Herkunft:** Wirkungen, Dauer, Quelle, Auslöser und sogar die Existenz eines Effekts können unterschiedliche 02.25-/SL-/Regel-Sichtrechte haben. Der VPS sendet an jeden Spieler nur tatsächlich freigegebene Ergebnis-/Aktionsprojektionen; **keine geheimen NPCs, verdeckten Flüche, unentdeckte Türen/Nodes oder verborgenen Rohformeln** in Browser, WebSocket, Logs für Unberechtigte oder Sitzungsvorladecache.
14. **Persistenz und Synchronisation:** Echte Statusinstanzen und relevante Timer-/Rundenzähler-/Eventreferenzen werden auf dem VPS gespeichert. Join/Reconnect, parallele Browser und Wiederanlauf berechnen ausschließlich den **aktuell gültigen** Status aus autoritativen Ereignis-/Revisionsdaten; keine doppelte Tickvergabe, kein altes Kontrollrecht, kein Clienttimer als Wahrheit. Historische Effekt-/Würfel-/Worldevents werden nicht rückwirkend neu abgespielt.
15. **Versionierung und Migration:** Das Erstellen/Veröffentlichen einer neuen Statusdefinition ändert aktive Bestandsinstanzen oder bestehende Figuren nicht ungeprüft. Gültige Definitionen und Quellversionen werden festgehalten; nötige Umstellungen folgen **03.6 mit Vorschau, gesonderten Rechten und Schutz vor Datenverlust/Neu-Ausführung**. Aktuelle Sicherheits-/Lizenz-/Geheimnisrechte können unzulässige Altverwendungen unabhängig davon sperren.
16. **Modulare Wiederverwendbarkeit:** Eigene/mitgelieferte Regelwerksvorlagen aus 03.7 dürfen Statusdefinitionen referenzieren oder – nach gültiger Bibliotheks- und Lizenzpolicy – als Teil einer berechtigten RulePack-Kopie nutzbar machen. Kein automatisch freigegebenes Geheimwissen, keine Originalvorlagenüberschreibung. Statusmodul An/Aus und abhängige Berechnungs-/Turn-/Kampfmodule müssen kompatibel validiert werden.
17. **Zeitrandfälle bewusst offen:** Offline-Fortschritt, globales Pausieren, verpasste wiederholte Echtzeit-Ticks, die genaue Bedeutung von „bis zum nächsten eigenen Zug“, Reihenfolge gleichzeitiger End-/Aktionsereignisse und effektgenaue Zeitlimits sind **noch keine Detailbeschlüsse**; hier gelten die offenen Grundlagen aus 02.15/02.16 und späteren 04/05/07-Regelentscheidungen. Die Grundarchitektur muss diese Zustände korrekt unterscheiden können.
18. **Keine festverdrahteten Statuseinträge:** Gift, Furcht, Tarnung, Betäubung oder Schild sind nur Beispiele. Ein Cyberpunk-, Horror-, Fahrzeug- oder regelwerksfreies Szenario darf andere oder keine Zustände besitzen; weder Fantasy noch ein einzelnes Kampfsystem wird durch 03.8 erzwungen.

## 3. Berechtigter Ablauf

**Vorlage erstellen/verwenden:** Berechtigter Autor definiert gültige, versionierte Status- und Wirkungsregeln bzw. wählt einen freigegebenen RulePack-Status. Ein Draft verändert keinerlei Spielfigur. Bei Veröffentlichung prüft der VPS typisierte Referenzen, Trigger, Dauergrundlagen, Kompatibilität, Sicht-, Lizenz- und Veröffentlichungsrechte.

**Status anwenden:** Ein legitimer SL-/Spieler-/Würfel-/Klassen-/Item-/Node-Akteur löst unter heutiger Kampagnen-/Ziel-/Regel-/Turn-/Quellpolicy eine definierte Anwendung aus. Server prüft aktuelle Rechte, Ziel-ID, Versionsreferenzen, Zielzustand, Stacking-/Dauerpolicy und Operation-ID; anschließend genau eine persistente Effektinstanz bzw. ein regelgemäßes Update.

**Aktiv wirken lassen:** Nur tatsächlich aktive, gültige EffectInstances liefern berechtigte Modifikatoren an 03.7 bzw. explizite Einschränkungen an 03.2 und spätere 04/05/07-Aktionen. Erforderliche zusätzliche echte Aktion (z. B. periodischer Schaden oder Alarm) benötigt einen **eigenständigen** berechtigten, einmalig gebuchten Commit. Eine bloße Animation/Anzeige ist kein weltwirksames Ereignis.

**Dauer/Ende:** Der autoritative Zeit-/Turn-/Eventdienst bestimmt das gültige Ende, setzt die Instanz revisionssicher auf beendet/erloschen und invalidiert die zulässigen Ableitungen und Steuerrechte. Ungültige oder doppelte Signale sind ohne Zweitwirkung; bei Reconnect werden nur tatsächlich aktuelle Ergebnisse ausgeliefert.

**Manuelle Kampagne:** Wird automatische Statusverarbeitung abgeschaltet, können SL/Spieler gemäß ihrer jeweiligen Berechtigung weiter einfache Zustandsnotizen oder manuell veranlasste Spielhandlungen führen; keine unsichtbare Automatik zwingt Runden- oder Kampfsysteme auf.

## 4. Grober technischer Umsetzungsplan

1. Versionierte, genreunabhängige Status-/EffectDefinition mit sicheren typisierten Wirkbeschreibungen und RulePack-/Bibliotheks-/Kampagnen-/ACL-Bezug modellieren.
2. Persistente konkrete EffectInstance als getrennte Entität mit Ziel, Quelle, Definition/Version, Lifetime-/Turn-/Event-Bindung, aktueller Wirksamkeit, Revision und Operation-/Event-ID modellieren.
3. Status-Lifecycle als serverautoritatives, atomar/idempotent prüfendes Fachmodul entwerfen; 02-Zeit-/Rundenzähler-/Eventkorrelation einbinden ohne einen zweiten konkurrierenden Scheduler oder Turnmotor zu schaffen.
4. Adapter zu 03.7 abgeleiteten Werten und zu 03.2 beschränkter Charaktersteuerung vorsehen; physische Regelaktionen in 05/07 und World-/Item-/Node-Adapter getrennt autorisieren.
5. Geschützte Template-Verwaltung, Status-An-/Aus je Kampagnenpolicy, SL-/Spieler-Aktionen und reine Freitextvariante bereitstellen; volle Kampagnenerstellungs-UI nach 02.48 später bündeln.
6. Realtime-/Reconnect-/Geheimnisprojektionen, Konflikt-/Verfallsbehandlung, sichere Versionmigration und Fehlerfälle vor Implementierung mit überprüfbaren Akzeptanztests spezifizieren.
7. Exakte Effektlisten, Formelsprache, Zeit-/Pause-/Stackingparameter, UX, API/DB, Hintergrundjobs und MVP im passenden Umsetzungsschritt ausarbeiten.

## 5. Fachliche Abnahmetests

| Fall | Erwartetes Ergebnis |
| --- | --- |
| Status per Vorlage erstellt und gespeichert | Wiederverwendbare versionierte Definition, keine aktiven Instanzen bis zur tatsächlichen Anwendung |
| Regelprofil ohne Statusmodul | Keine automatische Statuswirkung, weiterhin berechtigte manuelle Beschreibungen/Spielaktionen |
| Gift als beschreibender Marker | Nur autorisierte Anzeige; kein ungefragter Schaden, Würfel oder Ressourcencommit |
| Aktiver Schild verändert Verteidigung | Abgeleiteter Wert wird aktualisiert, gespeicherter Basiswert bleibt unverändert |
| Drei Runden in einem bestimmten Turnkontext | Nur tatsächliche gültige Runden dieses Kontexts zählen; keine Zeitumrechnung |
| Paralleler fremder Turnkontext läuft weiter | Effekt läuft nicht durch fremde Runde ab |
| Echtdauer nach Reconnect oder Neustart | Serverpersistenter Zustand entscheidet, kein erneuter Start oder zweiter Tick |
| Effekt endet bei legitimer Tür-/Quest-/Nodeaktion | Nur korrekt typisiertes gültiges Triggerereignis beendet ihn einmalig |
| Gefälschter Browser-Tick oder Node-ID | Keine Statusverlängerung/-entfernung und keine Weltwirkung |
| Übernahme/Verhexung einer Figur | Nur konkrete erlaubte Aktionen betroffen, keine Konto-/SL-/Geheimrechte übertragbar |
| ControlGrant läuft ab oder wird entzogen | Alte Steuerrechte sofort unwirksam; Reconnect gibt sie nicht zurück |
| Item wird abgelegt und dessen Statusquelle entfällt | Regelkonformes Beenden/Unterdrücken, keine Geisterboni |
| Gleicher Effekt wird erneut beantragt | Stacking-/Erneuerungs-/Konfliktpolicy entscheidet; kein ungeprüftes Doppeln |
| Doppelte Nachricht oder zwei Browser | Höchstens ein tatsächlicher Status-/Tick-/Worldcommit pro Ereignis |
| Effektziel oder Sourceversion geändert | VPS prüft aktuelle Rechte, Version, Revision und Blocker |
| Geheimer Fluch auf NPC | Nicht freigegebene Quelle/Existenz/Parameter erreichen keine Spielerbrowser |
| Neue Effektvorlage veröffentlicht | Aktive Bestandsinstanzen werden nicht still migriert oder neu ausgelöst |
| Regel-/Effektdefinition ungültig oder zyklisch | Keine Veröffentlichung/Aktivierung mit ungeprüfter Auswertung |
| Abgelaufene Wirkung würde Schaden/Tür/Quest auslösen | Nur bei eigenständig berechtigtem, idempotentem Action-/Node-Commit |
| Rundenregel in Kampagne ohne Rundenzähler | Keine irrtümliche automatische Umrechnung oder fiktives Ablaufen |

## 6. Beschlussgrenze und nächster Hauptmodulblock

**03.8 C verbindlich:** Optionales, regelwerkskonfigurierbares, persistent serverautoritäres Zustands-/Effektsystem mit versionierten Vorlagen und gesonderten aktiven Instanzen; manuelle oder geeignete automatische Wirkungen, valide Echtzeit-/Runden-/Ereignisdauer, sichere Quellen-/Ziel-/Kontroll-/Wertadapter, separate Rechte/Geheimnissicht, atomare idempotente Laufzeitänderungen. Wiederverwendung in 03.7-Regelwerksvorlagen möglich. Keine automatische Basiswertänderung und keine ohne eigenständige Autorisierung wirkenden Würfel-/World-/Itemaktionen.

**Später:** Konkrete Gift-/Schild-/Hex-/Statuslisten, exakte Dauer- und Offline-/Pause-/Ticksemantik, Stapelformeln, Rechte-Defaults, UI, Speicher-/Scheduler-/API-Implementierung und MVP.

**Der Block 03 Charakterbögen ist für die grundlegende Architektur zunächst ausreichend strukturiert.** Spezielle Charakteraktions-/Würfelentscheidungen werden in 05/07, allgemeine Vorlagen-/UI-/Serverfragen in 09/12–15 weitergeführt. Damit folgt der bereits geplante **Block 04 Tokens und Bewegung** statt einer unbegrenzten Zahl an Charakter-Unterfragen.

**Nachfolgender Beschluss 04.1 C (17.10.2026):** Regelwerks-/Szenen-/Gruppenabhängige freie, Ziel-/Wegpunkt- und rundenbasierte Bewegungsarten mit auf gültige Gegnerentdeckung/Encounter- oder SL-/Node-Ereignisse gestützter kontrollierter Modeumschaltung beschlossen [Details/Tests](BEWEGUNG-WORKSHOP-04.1.md). Die folgende ursprüngliche Frage bleibt als historischer Entscheidungsnachweis erhalten. **Nächste offene Frage: 04.2 – Token-Platzbedarf/Kollision.**

### Ursprüngliche Grundsatzfrage 04.1 – Welche Bewegungsmodi sind architektonisch möglich?

**Beispiel:** Eine Gruppe erkundet frei eine Stadt, wechselt in eine Kampfszene mit Zugreihenfolge und nutzt zwischendurch ein Rätsel mit „Next Player“-Node. Wie dürfen die Figuren auf Karte/Szene in diesen unterschiedlichen Situationen bewegt werden?

- **A – Ausschließlich freie Bewegung:** Tokens lassen sich nach Zugriffsrecht jederzeit frei bewegen. Kein technischer runden- oder aktionsbudgetbasierter Modus.
- **B – Ausschließlich feste Rundenzüge:** Jede Figur wird überall nur im selben vorgegebenen Zug-/Bewegungsmodell gesteuert; auch Erkundung ist erzwungen rundenbasiert.
- **C – Regel-/kampagnenabhängig umschaltbare Modi (Empfehlung):** Freie, ziel-/wegpunktbezogene und gegebenenfalls runden-/zug-/bewegungsbudgetbasierte Bewegungsarten können je zulässiger Kampagnen-/Szenen-/Figuren-/Bereichspolicy aktiviert werden. Der VPS prüft Kontrolle, Pfad/Ziel, Kosten und tatsächliche Szene-/Turnkontexte nach 02; 02.67–02.73-„Next Player“ und bestehende Node-/Bewegungsereignisse werden **wiederverwendet**, nicht durch einen zweiten widersprüchlichen Motor dupliziert. Konkrete Defaultgeschwindigkeiten, Wegsuche, Rasterzahlen, UI und Spezialbewegungen erst später.
