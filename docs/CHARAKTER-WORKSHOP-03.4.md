# AdventureShift – Charakter-Workshop: Beschluss 03.4 C – modulare Klassen, Fertigkeiten und Fähigkeiten

**Stand:** 16.10.2026. Beschlossen: **03.4 C**. **Nächste Strukturfrage: 03.5 – Charakterentwicklung nach der Erstellung**.
**Status:** Fachliche Architekturplanung mit Datenmodell, Schnittstellen, Sicherheit und Abnahmetests; **keine Softwareimplementierung**. Exakte Klassen-/Skilllisten, Punkte-/XP-Zahlen, Formeln, UI, APIs, DB und MVP später.
**Bezüge:** [03.1 C typisierte versionierte Charakterbögen](CHARAKTER-WORKSHOP-03.1.md) · [03.2 C Charakterzuordnung/temporäre Kontrolle](CHARAKTER-WORKSHOP-03.2.md) · [03.3 C Vorlagen-Publikation/optionale Charaktererstellung](CHARAKTER-WORKSHOP-03.3.md) · [Inventar 01, Karten/Nodes 02, Sprachen 02.60, Würfel 05, Regeln 07](FEATURE-WORKSHOP.md) · [Planungsstandard](PLANUNGSSTANDARD.md).

## 1. Verbindlicher Beschluss – Variante C

Der Projektinhaber hat ausdrücklich **C** gewählt. **Klassen, Berufe, Archetypen, Fertigkeiten und Fähigkeiten werden als typisierte, regelwerksneutrale und versionierte Datenbausteine** mit stabilen technischen IDs und überprüften Beziehungen zu 03.1-Charakterfeldern, Skills, Ressourcen, erlaubten Aktionen, Voraussetzungen und optionalen Punktebudgets modelliert. Der Plattformkern muss keine feste D&D-Klasse, Fantasyattribute, Stufenanzahl, Klassen-/Skillzahl oder spezielle Würfelmechanik voraussetzen.

**Beispiel:** Ein „Techniker“ kann die Option auf Reparaturfertigkeiten, ein weiteres berechtigtes Skillfeld, passende Startfähigkeiten und eine zulässige Regelaktionsreferenz erhalten. Ein „Soldat“ hat andere Auswahlmöglichkeiten. Die tatsächliche Reparatur-/Kampfaktion muss jedoch separat über einen gültigen Regel-/Würfel-/Inventar-Pfad autorisiert und geprüft werden.

**Nicht gewählt:** A (Klasse nur als Text/Label ohne strukturierte Regelbeziehung) und B (fest programmierte Klassenschemata, die den gesamten vorhandenen Charakterbogen oder seine Werte ungeprüft ersetzen). C begründet weder grenzenloses Multiclassing noch beliebig ausführbaren Nutzercode.

## 2. Zwingende Datenstruktur

1. **Bogenbasis:** Die 03.1-Charakterinstanz referenziert weiterhin eine zulässige veröffentlichte Charaktervorlagenversion mit stabilen Feld-IDs und dauerhaft gespeicherten eigenen Werten. Klassen sind zusätzliche Definitionen/zugeordnete Bausteine, **keine neue CharacterInstance-ID** und keine neue Steam-/Token-/NPC-Identität.
2. **Definitionen:** Versionierte ClassModuleDefinition, AbilityDefinition und SkillDefinition (**Arbeitsnamen, keine finalen DB-Felder**) haben technische IDs, Typkategorie, Gültigkeits-/Kampagnen-/RulePack-/Bibliotheks-Scope und Veröffentlichungsstatus. Anzeigenamen sind austauschbar und niemals Berechtigungs-ID.
3. **Instanzielle Wahl:** Eine Klasse/Fähigkeit/Fertigkeit wird als **berechtigte erworbene/ausgewählte Referenz samt zugrunde gelegter veröffentlichter Modulrevision** an einer konkreten Figur gespeichert. Die zwei Charaktere mit derselben Klasse behalten unterschiedliche eigene Basiswerte, Budgetentscheidungen, Ressourcen, Iteminstanzen und Zustände.
4. **Typisierte Feldbezüge:** Klassenbausteine referenzieren nur echte kompatible stabile Attribut-/Ressourcen-/Skill-IDs. Fehlendes Feld, falscher Feldtyp oder ungültige Vorlagenversion führen zu geprüfter Kompatibilitätsentscheidung, nicht zu einem still erzeugten Feld mit zufällig passendem Namen.
5. **Auswahl und Kosten:** Daten können erlaubte Startfertigkeiten, bei Bedarf freischaltbare Fähigkeiten, auswählbare Varianten, Mindest-/Maximalwerte, gegenseitige Ausschlüsse, Kosten-/Punktbudget-Regeln und passende Voraussetzungen beschreiben. Die **konkreten** Beträge, Kurven, Startklassen und Tabellen werden später festgelegt.
6. **Voraussetzungen:** Regelkriterien dürfen sich nur auf gültige Feld-/Skill-/Klassen-/Statusreferenzen beziehen. Zyklen, nicht auflösbare Abhängigkeiten und unzulässige Klassen-/Fähigkeitsreferenzen werden vor Veröffentlichung oder Anwendung erkannt. Kein ungeprüfter rekursiver Bewertungsgraph.
7. **Regelwirkung:** Ein Baustein kann kontrollierte **typisierte** Effektdeskriptoren beisteuern: etwa Auswahl freigeben, einen Skill definieren, eine abgeleitete Zahl modifizieren oder eine RuleAction-Referenz zulassen. Das ist eine deklarative Schnittstelle zu späteren Regeladaptern, kein beliebiges JavaScript/SQL/externes Skript und kein sofortiger Spielwelt-Commit.
8. **Basiswert und Ableitung trennen:** Permanent vom Spieler gespeicherte Attribute/Punkte, Itemboni, Klassenmodifikatoren und temporäre Effekte aus Zuständen werden getrennt mit Herkunft/Quelle referenziert. Klassen- und Inventareffekte dürfen **abgeleitete** Werte verändern, nicht beim Anzeigen oder Umschalten unkontrolliert gespeicherte Basiswerte überschreiben.
9. **Mehrere erlaubte Bausteine:** Eine Figur kann strukturell mehrere berechtigte Modultypen wie Klasse, Hintergrund, Skill und Fähigkeit referenzieren. Ob tatsächlich mehrere Hauptklassen oder bestimmte Kombinationen erlaubt sind, entscheidet das spätere Regelprofil; kein automatisches Multiclassing ohne validierte Kampagnen-/Regelkonfiguration.
10. **Versionierung:** 03.3-konform gibt es gesonderte Bearbeitungs- und Veröffentlichungsrechte. Neu publizierte Klassen-/Fähigkeitsrevisionen dürfen vorhandene Figuren, bereits verteilte Punkte, aktuelle Ressourcen, Iteminstanzen oder Fähigkeiten **nicht** automatisch migrieren, löschen oder rückabwickeln. Bestandsmigration benötigt einen getrennten geprüften explizit autorisierten Prozess.
11. **Klasselose Systeme:** Die Klassenfähigkeit ist innerhalb einer Kampagne optional. Eine rein manuelle oder klassenlose Charaktervorlage und deren Instanzen bleiben zulässig, ohne leere Pflichtklassen- oder automatische Levelfelder.
12. **Rechte:** Klassen-/Skill-/Aktions- und Feldwerte werden unter aktueller 02.25-/03.1-/03.2-/03.3-/Regel-/Kampagnen-/Asset-/Lizenz-/Empfänger-ACL serverautoritativ geprüft. Bei zeitweiliger Verhexung oder Charakterübernahme nach 03.2 geht **nicht** automatisch das Klassenverwaltungs-/Punkteausgabe-/Vorlagenveröffentlichungsrecht an den Controller über.
13. **Geheimnisse:** Verborgene SL-/NPC-Klassen, geheime Fähigkeiten/Regeln/Optionen, nicht lizenzierte Module oder versteckte Voraussetzungen dürfen nicht durch WebSocket, Cache, Profilzählungen, Preview oder Fehlertexte an unberechtigte Browser geliefert werden.
14. **Regel- und Weltgrenze:** Klasse/Skill kann definierte Würfel-/Regel-/Inventar-/Tokenfähigkeiten anbieten; ihr Vorhandensein allein ist kein eigener Würfelwurf, keine Tür-/NPC-/Node-/Questaktion und kein Inventartransfer. Echte Aktionen müssen eigene Rechtegrenzen und einmalige serverseitige Durchführung erfüllen.
15. **Mehrbrowser:** Doppelklick, zwei Tabs, parallele Auswahl, Verbindungsabbruch, veraltete Vorlage und Cache-Reconnect benötigen Versionen und Operation-IDs. Punkte dürfen nicht zweimal ausgegeben, Startitems nicht dupliziert und alte RuleActions nicht ohne neue ACL abgesetzt werden.
16. **Sprachen als Skills:** Die nach 02.60 kampagnenweit angelegten Sprachen bleiben als definierte Skills/Fähigkeitsreferenzen abbildbar, keine hartcodierte Liste. Erlernen/Steigern folgt passenden späteren Regelmodulen.
17. **Feinwerte auf später verschieben:** Standardklassen, Auswahl-Listen, genaue Regelformeln, Punktekosten, Skillgruppen, Lernstufen, UI-Schritte, Lizenzpakete, DB/API-Feldnamen, genaue MVP-Reihenfolge und Performancebudgets noch nicht endgültig beschließen.

## 3. Konzeptioneller Ablauf

**Vorlagen-/Modulentwurf:** Berechtigter Editor ändert einen gültigen Entwurf und referenziert erlaubte Klassen-/Ability-/Skilldefinitionen. Publikation nach 03.3 prüft gültige Ziel-Feldtypen, Berechtigungen, vererbte Abhängigkeiten, ggf. Punktbudgets und Lizenzscopes. Ein veröffentlichter Stand ist versioniert und gilt nicht automatisch für bestehende Charaktere.

**Optionale Charaktererstellung:** Wenn der 03.3-Erstellungsmodus tatsächlich eingeschaltet und der Spieler zum Erstellen berechtigt ist, kann er aus **heute freigegebenen** Klassen/Fähigkeiten/Fertigkeiten wählen und erlaubte Punkte verteilen. Ein Draft bleibt nichtweltwirksam. Der VPS prüft beim Abschluss aktuelle Charaktervorlage, Class-/Ability-/Skillrevisionen, Budget, Voraussetzungen, Charakteranzahl nach 03.2 und Actor-/Kampagnenrechte; die Erzeugung der CharacterInstance ist transaktional und idempotent.

**Laufender Charakter:** Gültig erworbene Fähigkeiten wirken über definierte Rule-/Stat-Adapter mit separater Provenienz. Beim Wegfall/Wechsel einer Berechtigung oder Klasse werden zukünftig zulässige abgeleitete Wirkungen neu ermittelt, ohne alte Würfel-/Item-/Ressourcenereignisse zu replizieren oder dauerhaft gespeicherte Basiswerte zu beschädigen. Konkrete Aufstiegs-/Umlernverfahren sind **03.5**.

**VPS/Browser:** Server verwaltet Besitz, Zustand, Regeln und echte Aktionen; getrennte Browser zeigen und verändern nur aktuell erlaubte Klassen-/Charakterinformationen. Keine vollständigen geheimen Pakete vorladen, auch nicht hinter einer versteckten UI-Klasse.

## 4. Konzeptioneller Umsetzungsplan

1. Versionierte, typisierte Class-/Ability-/Skilldefinitionen mit stabilen IDs, aktuellem Scope und separaten 03.3-Entwurfs-/Publishrechten strukturieren.
2. Feld-/Skill-/RuleAction-Kompatibilität und versionierte Voraussetzungen, erlaubte Wahlräume und optionales Punktemodell strikt deklarativ validieren; Zyklen und ungültige Referenzen zurückweisen.
3. Auf einer CharacterInstance gewählte/erworbene Modulversionen getrennt von echten Basiswerten und 01-Inventar-/02-Token-IDs referenzieren; Quellen von abgeleiteten Werten kenntlich machen.
4. Optionalen CharacterCreationDraft aus 03.3 integrieren; serverautoritativ die erlaubte Budgetausgabe, Voraussetzungen und einmaligen Abschluss prüfen, nie Clientkosten blind übernehmen.
5. Echte Spielaktionen nur über geschützte 05-Würfel-/07-Regel-/01-Item-/02-Tokenadapter erlauben; temporäre 03.2-Steuerung verleiht keine Vorlagen- oder Skilladministration.
6. Vorlagen-/Klassenpublikation und Bestandsmigration voneinander trennen; alte Figuren nicht ungeprüft aktualisieren, Version-/Replay-/Reconnect-/Secretfälle testen.
7. Finale Listen, Wertzahlen, UI/API/DB/DSP und MVP erst bei tatsächlicher Umsetzung bestimmen. **03.5** entscheidet die Struktur der Weiterentwicklung nach der Ersterstellung.

## 5. Fachliche Abnahmetests

| Fall | Erwartetes Verhalten |
| --- | --- |
| Techniker statt Soldat aus derselben Bogen-Vorlage | Andere erlaubte Skills/Fähigkeiten, keine hartcodierten Bogenkopien |
| Fantasyklasse und Cyberpunkberuf | Beide per Daten/Ruleprofile ohne Programmänderung darstellbar |
| Kampagne ohne Klassenmodul | Charakterinstanzen und manuelles Spiel weiterhin möglich |
| Zwei Charaktere mit derselben Klasse | Eigene getrennte Attributwerte, Skillstände, Iteminstanzen und Punkte |
| Klasse referenziert umbenanntes Feld | Stabile Feld-ID erhält gültige Verknüpfung |
| Klasse referenziert inkompatiblen Feldtyp | Veröffentlichung oder Anwendung scheitert sicher |
| Voraussetzung fehlt oder hängt zyklisch von sich selbst ab | Server weist unzulässigen Auswahl-/Publikationszustand zurück |
| Punktkosten im Client manipuliert | Serverseitige Budgetprüfung statt Clientvertrauen |
| Doppelte Charaktererstellung/mehrere Tabs | Höchstens ein autorisierter Abschluss und keine Doppelpunkt-/Itemvergabe |
| Klasse verleiht zulässigen Ressourcenbonus | Als Quellenreferenz abgeleitet, kein stilles Überschreiben des Basiswerts |
| Item- und Klassenbonus wirken auf denselben Wert | Nur regelprofileigene legale Kombination, kein unlimitiertes oder zufälliges Stacking |
| Publizierte Klassenversion wird geändert | Alter Charakter behält explizit verwendete Version und Werte bis zur kontrollierten Migration |
| Controller ist zeitweilig verhext/beherrscht | Nur ausdrücklich erlaubte Handlungen, keine Klasse-/Punkte-Adminrechte |
| Unberechtigter Spieler errät Geheimklasse/NPC-ID | Kein Name, Count, Regeltext oder private Feldwerte per Realtime |
| Klasse verspricht eine Reparaturaktion | Noch keine echte Welt-/Würfel-/Inventarwirkung ohne gesondert erlaubte Aktion |
| Klassenbeschreibung verleiht Startausrüstung | Keine Items aus UI-Replay; echter Inventarvorgang mit ACL und Idempotenz erforderlich |
| Sprachskill wird gewählt | Nach 02.60 definierte Kampagnensprache als typisierte Skillreferenz |
| Browsercache kennt Klasse aus fremder Kampagne | Keine CrossCampaign-/Lizenz-/Secretfreigabe |
| Bereits existierender Charakter verliert Klassenoption | Nicht automatisch Vorlagenbasis/Charakterwerte löschen |

## 6. Beschlussgrenze und nächste Frage

**Fest beschlossen: 03.4 C.** Datengetriebene, versionierbare, regelwerksneutrale und typisierte Klassen-, Fertigkeits- und Fähigkeitsbausteine mit geprüften Feld-, Skill-, Voraussetzungs-, Budget- und Aktionsbezügen. Keine Hardcoding-Klassenvorlagen, keine ungeprüften Bestandswertüberschreibungen und kein unautorisiertes Nutzerskripting.

**Noch offen:** konkrete Klassenlisten, Fähigkeitstabellen, Budgetzahlen, Multiclass-/Stackingformeln, finale UI/API/DB/MVP und die nächste strukturelle Frage **Charakterentwicklung nach der Ersterstellung**.

## Nächste Entscheidung 03.5 – Wie entwickeln sich Charaktere nach ihrer Erstellung weiter?

**Beispiel:** Eine Figur hat ihren Anfangscharakter fertig. Später erhält sie nach den Kampagnenregeln Erfahrung, Punkte oder einen Meilenstein und darf dadurch eine Fertigkeit steigern, neue Klassenoptionen auswählen oder einen Rang aufsteigen. Wir entscheiden zunächst die Struktur, nicht die genaue XP-Tabelle.

- **A – Nur manuell Werte ändern:** Keine eigene Fortschritts-/Level-/Punkte-Struktur. Berechtigte SL/Spieler passen den Bogen direkt an, wenn ihr Regelwerk es erfordert.
- **B – Für alle erzwungenes festes XP-/Level-System:** Jede Kampagne verwendet dieselbe hartcodierte Aufstiegsmechanik und Klassenstufen, ungeachtet des Regelwerks.
- **C – Optionales konfigurierbares Fortschrittsmodell (Empfehlung):** Versionierte Regeln für passende **XP-/Punkte-/Meilenstein-/Rang-/Level-/Skill-Entwicklung** als getrennte, servergeprüfte Zustandswechsel einer bestehenden Figur. Optionale SL-Freigabe, Voraussetzungen, Budgets, einzelne erlaubte Verbesserungen und spätere Umschulung können modelliert werden, ohne feste Zahlen, Levelkosten oder UI jetzt zu bestimmen. Regelwerksfreie Kampagnen können das Modul ausschalten.
