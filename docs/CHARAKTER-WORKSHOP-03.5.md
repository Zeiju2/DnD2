# AdventureShift – Charakter-Workshop: Beschluss 03.5 C – optionales, konfigurierbares Fortschrittssystem

**Stand:** 16.10.2026. Verbindlich beschlossen **03.5 C**, auf Basis von [03.1 – Charaktervorlagen](CHARAKTER-WORKSHOP-03.1.md), [03.2 – Zuordnung und Steuerrechte](CHARAKTER-WORKSHOP-03.2.md), [03.3 – optionale Charaktererstellung](CHARAKTER-WORKSHOP-03.3.md) und [03.4 – Klassen, Fähigkeiten und Skills](CHARAKTER-WORKSHOP-03.4.md). **Nächste Grundstrukturfrage: 03.6 – kontrollierte Migration bestehender Figuren bei Vorlagen-/Regeländerungen.**
**Status:** Fachliche Architekturplanung mit Umsetzungsfolgen und Abnahmetests, **keine implementierte Software**. Standardzahlen, XP-/Rangtabellen, Formeln, UI, API-/DB-Verträge und MVP später. [Verbindlicher Planungsstandard](PLANUNGSSTANDARD.md).

**Nachfolgender Beschluss 10.4 C:** [Getrennte alternative Questresultate, Consequences und Rewards](JOURNAL-WORKSHOP-10.4.md) dürfen nur als **legitime Award-Quelle** für die hier festgelegten 03.5-CharacterProgression-/XP-/Meilenstein-/Punktecommits dienen, niemals als unautorisiertes direktes Verändern von XP oder Charakterwerten. Ein Questresultat oder eine Handoutfreigabe ist noch kein XP-Award; wirklicher Empfänger, Scope, RuleVersion, Fortschrittsquelle, Doppelbuchungsschutz und spätere genaue Rewardformeln folgen den gültigen Fachrechten. V1 weiterhin ein aktiver SL; konkrete XP-/Formel-/UI-Details später.

## 1. Verbindlicher Beschluss – Variante C

Der Projektinhaber wählt **C – ein optionales, regelwerksabhängig konfigurierbares Charakterfortschrittssystem**. Die Entwicklung einer bestehenden Charakterinstanz kann – wenn das betreffende Modul einer Kampagne aktiviert und zulässig ist – **XP/Erfahrung, verteilbare Steigerungspunkte, Meilensteine, Level, Ränge, Fertigkeits- und Attributsteigerungen, neue Fähigkeiten und Klassenoptionen sowie gegebenenfalls regelgesteuerte Umschulung** unterstützen. Die tatsächlichen Auswirkungen werden versioniert und **serverseitig autorisiert und validiert**.

Ein anderes Regelwerk darf ohne Level, mit freien Punkten oder nur SL-vergebenen Meilensteinen funktionieren; eine Kampagne darf das Fortschrittsmodul **ganz abschalten** und stattdessen berechtigte manuelle Bogenänderungen verwenden. Das System erzwingt keine eingebauten D&D-Klassen oder festen XP-/Punktewerte.

**Nicht gewählt:** A – keinerlei strukturierte Entwicklungsfähigkeit außer manuellen Feldänderungen – und B – identische festprogrammierte XP-/Levelmechanik für alle Kampagnen. Variante C ist **keine** Zusage, dass alle denkbaren Aufstiegsregeln oder Regelsysteme bei Start bereits automatisiert sind.

## 2. Architektur: unabhängige Grundobjekte

1. **Regelprofil und Fortschrittsdefinition:** Eine versionierte ProgressionRuleVersion (Arbeitsname) beschreibt für eine Kampagne, **ob** und **welche** Fortschrittsarten verfügbar sind: XP, Punkte, Rang/Level, Meilensteine, Skills oder freigegebene andere Mechaniken. Typisierte IDs verweisen auf veröffentlichte Charakterbogenfelder und Klassen-/Fähigkeitsdefinitionen aus 03.1/03.4. Kein für jede Figur verpflichtendes Level-Feld.
2. **Charakterzustand:** CharacterProgressionState gehört zu einer existierenden **CharacterInstance**, behält deren Identität, Vorlagenversion, Charakterzuordnung und aktuell rechtmäßige Feld-/Inventarbeziehungen. Er kann Fortschrittswährungen, zulässige Rang-/Meilensteinstände und erworbene Qualifikations-/Abilityreferenzen enthalten; nur soweit das Regelprofil sie benötigt.
3. **Währungsarten trennen:** Gesammelte Erfahrung, verfügbare Steigerungspunkte, bereits ausgegebene Punkte, Klassenstufen und Aktionsressourcen werden **nicht automatisch gleichgesetzt**. Konvertierungen, Kosten, Grenzen und bedingte Auszahlungen ergeben sich aus dem tatsächlich erlaubten Regelprofil; konkrete Zahlen und Formeln später.
4. **Legitime Fortschrittsquelle:** Award/ProgressionEvent referenziert Charakter-ID, tatsächlichen Auslöser, berechtigten Initiator, betroffene Regelversion, Ereignis-/Operation-ID und fachliches Ergebnis. Mögliche Quellen sind berechtigte SL-Vergabe, validiertes Quest-/Meilenstein-/Regelereignis oder ausdrücklich aktivierte Automation. Ein manipulierbarer Browserbutton allein vergibt **keine XP**.
5. **Entwurf und Commit getrennt:** Eine berechtigte Person darf mögliche Verbesserungen als AdvancementDraft wählen. Der Draft verändert **noch keine** spielweltwirksamen CharacterInstance-Werte, Ressourcen, Klassen-/Abilityrechte oder Inventargegenstände. Erst ein separat gültiger AdvancementCommit kann diese Zustände tatsächlich verändern.
6. **Optionaler Freigabeschritt:** Der Kampagnen-/Regelmodus kann SL-Bestätigung oder passende Freigaben durch berechtigte Gruppen/Rollen verlangen. **Punkte vergeben**, **Entwicklung beantragen**, **Entwurf bearbeiten**, **genehmigen**, **anwenden** und **Umschulen/Korrigieren** sind unterschiedliche Kompetenzen nach 02.25 und 03.2; ein temporärer Charaktercontroller durch Verhexung/Übernahme erhält nicht automatisch das Recht, fremde Punkte auszugeben oder aufzusteigen.
7. **Dauerhafter vs. abgeleiteter Wert:** Gewonnene Attribut-/Skill-/Abilityverbesserungen werden im legalen Figurenzustand nachvollziehbar gespeichert. Klassen-, Item- und temporäre Modifikatoren bleiben **getrennte Ableitungsquellen** nach 03.4 und 01. Keine stillen Basiswertüberschreibungen durch UI-Berechnung.
8. **Version und Fortschrittsregeln:** Anwendung referenziert die tatsächlich gültige veröffentlichte Regel-/Charakter-/Klassenfassung. Neue Regelversionen ändern alte Charakterentscheidungen nicht im Hintergrund; eine kontrollierte Übernahme späterer Versionen folgt **03.6**.
9. **Entwicklung ist kein Charakterneustart:** Ein Levelup oder Skillzuwachs verändert gezielt dieselbe CharacterInstance. Zuordnung/Steamidentität, Tokenposition, Inventar, Quest- und Würfelhistorie werden nicht ersetzt oder neu angelegt.
10. **Optionale Umschulung/Respec:** Nur bei berechtigter Regel-/SL-Policy dürfen bereits gewählte Skills/Punkte/Klassenoptionen geändert werden; dabei vollständige aktuelle Budget-/Voraussetzungs-/Abhängigkeitsprüfung. Umschulung **rollt keine** realen Würfel, verbrauchten Items, NPC-Aktionen, Türen, Questbelohnungen oder Runden rückwirkend zurück.
11. **NPC-/Kampagnenneutralität:** NPCs, Sonderfiguren und gemeinsam betreute Charaktere können passende Progressionsmechanik erhalten, müssen aber weder XP noch Levels verwenden. Jede Regelwerkskampagne darf eigene Typen/Listen hinterlegen und die Module einzeln deaktivieren.
12. **Geheimhaltung:** SL-geheime Meilensteine, NPC-Fähigkeiten, noch nicht freigeschaltete Klassen oder verborgene Voraussetzungen gehören nicht in unberechtigte Browserprojektionen. Keine verdeckten Daten als nur ausgeblendetes JSON/WebSocket-Payload oder vorab geladener Zukunftscontent.
13. **Ohne freie Skriptruntime:** Fortschrittsregeln bestehen aus autorisiert unterstützten **typisierten** Voraussetzungen, Feldern, Kosten- und Ereignisverweisen. Arbiträrer ausführbarer Regelwerkscode ist durch den Beschluss nicht erlaubt.
14. **Exakte Zahlen später:** Levelanzahl, XP-Tabelle, Steigerungskosten, Skillgrenzen, Klassennamen, Prestigegrade, Trainingsdauer, Menüaufbau und konkrete Autoevent-Konfiguration bleiben zu bestimmen, wenn das System implementiert wird.

## 3. Berechtigungen und serverseitige Abläufe

**Vergabe:** Ein vom Server geprüftes berechtigtes Quest-/SL-/Regelereignis gibt nur der konkreten Figur die nach dem aktiven Profil zulässige Ressource oder den Meilenstein. Identische Event-/Operation-IDs dürfen kein zweites Mal vergeben, Ressourcengrenzen nicht überschritten und heimliche SL-Quellen nicht an unbefugte Empfänger projiziert werden.

**Entwicklungsentwurf:** Berechtigte Figurbetreuer wählen aus **aktuell erlaubten** Feldern, Klassenmodulen, Skills und Fähigkeiten eine mögliche Verbesserung mit kontrolliert berechneten Kosten. Ein unbestätigter oder ungültiger Entwurf ist keine tatsächlich erlernte Fähigkeit und erlaubt keine Aktion.

**Genehmigung:** Ist die Option aktiv, muss ein gesondert berechtigter SL/Actor genehmigen. Ablehnung/Widerruf ändert keine echte Fähigkeit und verbraucht nicht bereits dauerhaft das Budget.

**Commit:** Vor Anwendung werden Anmeldung, Kampagne, CharacterInstance, 03.2-Steuer-/Edit-/Fortschrittsrechte, 03.1-Vorlagen-/Feldversion, 03.4-Klassen-/Skilldefinition, gültiger 07-Regelpfad, heute verfügbare Punkte, Voraussetzungen, ggf. die erforderliche SL-Bestätigung und frühere Operationen **erneut** serverseitig geprüft. Die erlaubte Änderung wird atomar **genau einmal** auf die konkrete CharacterInstance angewandt; aktuelle erlaubte Realtimeprojektionen folgen.

**Rücknahme/Korrektur:** Berechtigte Korrektur ist eine explizite neue fachliche Aktion nach Regeln, keine technische Replay-/Rollbackfunktion für alte echte Weltzustände. Bestehende Inventare, Ressourcenverbräuche und Würfelhistorien bleiben sicher.

**VPS und getrennte Browser:** Server ist autoritativ für Punktevergabe, Genehmigung und tatsächliche Entwicklung. Browser dürfen Entwürfe anzeigen und senden, aber nicht autonom den Spielzustand festschreiben. Reconnect, zwei Browser, parallele Bearbeitung und Netzwerk-Retry erfordern Revisionen, Event-ID/Operation-ID und klare Konfliktprüfung.

## 4. Konzeptioneller Umsetzungsplan

1. Versionierte optionale ProgressionRules und eigene, nicht notwendigerweise vorhandene XP-/Punkte-/Meilenstein-/Rang-Daten pro CharacterInstance definieren.
2. Authentifizierte, eindeutig ausgelöste ProgressionAwards und fachlich getrennte Ausgabe-/Meilenstein-/Advance-Ereignisse mit revisions- und idempotenzsicherer Persistenz planen.
3. Berechtigungen für Vergabe, Entwurf, SL-/Gruppenbestätigung, Anwendung, optional Respec und Sichtbarkeit in 02.25-/03.2-ACL und Ruleprofil auflösen.
4. Typsichere Referenzen von 03.1-Feldern auf 03.4-Klassen-/Skill-/Abilitymodule, Budget-/Grenz-/Voraussetzungsprüfung und getrennte Inventar-/Klassenmodifikatoren festlegen.
5. Atomares Server-Commit nur nach erneuter heutiger Berechtigungs-, Versions- und Budgetprüfung; keine Doppelvorgänge durch Wiederholen/Reload/gleichzeitige Tabs.
6. Sichere Schnittstellen zu Quest-/Node-/Würfel-/NPC-/Inventarereignissen ohne ungewollte echte Weltaktionen. Nur aktuell sichtbare Progressionsdaten und Medien an berechtigte Spielerbrowser übertragen.
7. UI, genaue Punktzahlen/Regelformeln/Progressionstabellen, tatsächliche Speicherung/API/DB und MVP später im Implementierungsplan spezifizieren. **03.6** klärt vorher die grundlegende kompatible Schema-/RulePack-Migration.

## 5. Fachliche Abnahmetests

| Test | Erwartung |
| --- | --- |
| Progressionsmodul ist aus | Keine Level-/XP-Pflicht; gültige Figuren und manuelle erlaubte Werte bleiben |
| Fantasy hat XP/Level, Cyberpunk Skillpunkte | Unterschiedliche Konfiguration ohne Plattformcodeänderung |
| SL gewährt XP | Serverseitig echte Berechtigung und Character-ID geprüft |
| Quest-/Node-Ereignis gibt XP | Nur bei tatsächlich gültiger Quelle und einmaliger Event-ID |
| Doppelte XP-Zustellung | Höchstens eine tatsächliche Gutschrift |
| XP und Steigerungspunkte getrennt | Keine stillschweigende automatische Gleichsetzung |
| Spieler beantragt Skillsteigerung | Draft allein verändert keine CharacterInstance |
| SL-Freigabe ist aktiviert | Aufstieg ohne Freigabe nicht wirksam |
| Spielmodus erlaubt selbstständige Steigerung | Rechtmäßig selbst autorisierter Progressionspfad funktioniert |
| Voraussetzungen oder Budget fehlen | Commit verweigert, keine unzulässige negative Punktebilanz |
| Zwei Tabs steigern gleichzeitig | Atomare Ausgabe, keine Doppelpunkte oder doppelte Ability |
| Figur wird temporär beherrscht/verhext | Controller bekommt nicht automatisch XP-/Respec-/Adminrechte |
| Klassenaufstieg verleiht neue Fähigkeit | Gültige veröffentlichte 03.4-Version und Figure-/Regelrechte nötig |
| Itembonus und Levelbonus wirken gleichzeitig | Getrennte abgeleitete Quellen, Basiswert korrekt |
| Spieler versucht fremde Figur zu steigern | Keine Charakter- oder Kontenumgehung |
| Reconnect während eines Aufstiegs | Aktueller Zustand wird geladen, kein zweiter Commit |
| Regel- oder Charaktervorlage geändert | Kein automatischer Altfiguren-Update; späterer Verfahren 03.6 |
| Geheimer NPC-/SL-Meilenstein | Keine geheimen Daten im Spieler-Cache/WebSocket |
| Respec nach tatsächlichem Itemverbrauch | Kein automatisches Zurückgeben des Items oder Rollback der Welt |
| Sprachskill nach 02.60 wird erlernt | Typsichere kampagnengebundene Skillreferenz |
| Normale Character-ID bleibt nach Levelup | Dieselbe CharacterInstance, keine Token-/Inventarduplizierung |
| XP-/Skillkosten im Client manipuliert | VPS verwendet gültige Regeln, nicht Browserwerte |

**Nachfolgender Beschluss 03.6 C (16.10.2026):** Vorhandene Figuren behalten bestehende gültige Bogen-/RulePack-/Class-/Progressionsfassungen, bis sie gesondert berechtigt und explizit nach Feld-/Skill-/Punkte-/Ressourcen-/Klassenmapping-Preview atomar auf eine gültige Zielversion migriert werden. Keine stille Löschung, Secretfreigabe, doppelte XP-/Item-/Würfel-/Weltaktion. [Beschluss und Tests 03.6 C](CHARAKTER-WORKSHOP-03.6.md). **Nächste Strukturfrage 03.7:** berechnete Charakterwerte. Die nachfolgende 03.6-Frage bleibt der frühere Entscheidungsnachweis.

## 6. Beschlussgrenze und nächste Frage

**Verbindlich beschlossen: 03.5 C.** Optionales, versioniertes und regelwerkskonfigurierbares Fortschrittssystem für bereits bestehende Charakterinstanzen – mit erlaubter Vergabe, vorbereiteten Änderungen, freigabepflichtigen oder erlaubten selbstständigen Aufstiegen, serverautoritativ einmaliger Anwendung und ggf. ausdrücklich erlaubter Umschulung. Keine Pflicht zu einer festen XP-/Levelmechanik, keine Daten- oder Inventarverluste durch automatisches Ersetzen von Charakteren.

**Offen für später:** XP-/Kosten-/Levelzahlen, konkrete Skill-/Regelkataloge, exakte UI, API-/DB-Datenfelder und MVP.

## Nächste Entscheidung 03.6 – Umgang mit aktualisierten Vorlagen und Regeln bei vorhandenen Charakteren

**Beispiel:** Nach mehreren Spielsitzungen wird eine neue Version eines Charakterbogens oder Klassenregelwerks veröffentlicht. Darin werden Felder umbenannt oder ersetzt, Fähigkeiten verändert oder andere Punktkosten festgelegt. Die bereits gespielten Figuren besitzen alte Werte und erworbene Skills.

- **A – Sofort ungeprüft für alle:** Jede neue Vorlage/Regelversion wird automatisch auf alle Figuren angewandt, auch wenn Felder/Werte/Skillreferenzen dabei verloren gehen.
- **B – Niemals migrieren:** Bestehende Figuren bleiben immer bei ihren alten Definitionen; ein gezielter Wechsel zu einer späteren Version ist nicht vorgesehen.
- **C – Kontrollierte, selektive Versionmigration (Empfehlung):** Bestehende Figuren behalten ihren alten gültigen Zustand, bis eine dazu berechtigte Person eine neue Version mit Vorschau, Feld-/Skill-/Klassen-/Punktemapping und Sicherheitsprüfung **für ausgewählte Figuren ausdrücklich anwendet**. Kein unkontrollierter Werteverlust, kein mehrfacher Fortschritt oder Itemgewinn, keine automatische Rechteausweitung. Exakte Dialoge und numerische Migrationsregeln erst später.
