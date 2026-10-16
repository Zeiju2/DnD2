# AdventureShift – Charakter-Workshop: Beschluss 03.3 C – geschützte Entwürfe und Freigabe von Charaktervorlagen

**Stand:** 16.10.2026. Fachbeschlüsse 03.1 C (typisierte Charaktervorlagen), 03.2 C (konfigurierbare Zuordnung und temporäre Steuerung), **03.3 C** (separat autorisierte Vorlagenverwaltung).
**Status:** Verbindliche Fachplanung und konzeptionelle Tests, **keine Softwareimplementierung**. Finale UI, konkrete Feld-/Punktzahlen, Regelwerksdaten, technische API-/DB-Schemata und MVP werden später bestimmt.
**Nächste Strukturfrage:** **03.4 – Technische Verknüpfung von Charakterklassen, Fähigkeiten und Punkteregeln.**
**Verknüpfungen:** [03.1 Vorlagen- und Instanzmodell](CHARAKTER-WORKSHOP-03.1.md) · [03.2 Zuordnung/Steuerrechte](CHARAKTER-WORKSHOP-03.2.md) · [Projektplan](PROJEKTPLAN.md) · [Architektur](ARCHITEKTUR.md) · [Planungstiefe](PLANUNGSSTANDARD.md).

## 1. Beschluss 03.3 C

Der Projektinhaber hat **Variante C** gewählt: Vorlagen für Charakterbögen dürfen unter wirksamen Kampagnen-/Rollen-/Gruppen-/Personen-/Objektstandards und gültigen markierten Ausnahmen von **ausdrücklich berechtigten SL, Co-SL und ggf. delegierten Vorlagenbearbeitern** erstellt und verändert werden. **Entwurf bearbeiten**, **publizierte Version freigeben** und **Rechte an weitere Benutzer delegieren** sind getrennte Befugnisse. Ein Editieren eines Entwurfs ist weder eine Veröffentlichung noch eine nachträgliche Änderung existierender Charakterinstanzen.

**Beispiel:** Ein Co-SL erstellt in einer Cyberpunkkampagne einen neuen Bogen mit Technik- und Energiefeldern. Er darf mit der ihm erlaubten Editorrolle einen neuen Entwurf bearbeiten; erst ein gesondert dazu Berechtigter kann eine gültige geprüfte Version veröffentlichen. Spieler mit bereits existierenden Charakteren bekommen dadurch nicht ungefragt neue Attribute oder geänderte Ressourcen.

**Nicht gewählt:** A, wonach allein eine feste Haupt-SL ohne delegierbare Einzelrechte alle Vorlagen betreuen dürfte; B, wonach jedes Mitglied ohne Rechtekontrolle und ohne getrennte Veröffentlichung bestehende Charaktervorlagen verändert.

## 2. Vorlage, Entwurf, Veröffentlichung und Instanz

1. **Charaktervorlagen-Identität:** Stabile Template-ID und fachlicher Scope (etwa Kampagne bzw. berechtigte Vorlagenbibliothek); Metadaten nur nach geltender Leseberechtigung. Ein Vorlagentitel ist keine sichere technische ID.
2. **Entwurfszustand:** Eine oder mehrere zulässige Draft-Revisionen enthalten Felddefinitionen, Typ-/Werte-/Aktionsreferenzen, optionale Erstellungsregeln und spätere Anzeigevorgaben. Entwurfsänderungen dürfen keine bislang veröffentlichte Version direkt überschreiben.
3. **Veröffentlichte Version:** Bewusst autorisierter Publikationsvorgang erzeugt bzw. aktiviert einen validierten, versionsstabilen und wiederauffindbaren Vorlagenstand. Bereits erzeugte Charaktere behalten ihre eigene konkrete Dateninstanz und ihren gültigen Schemabezugsstand.
4. **Auswirkungen vor Veröffentlichung:** Berechtigte SL können Änderungen an Typen, Feld-IDs, Referenzen, Ressourcen, Skills, möglichen Klassenoptionen und Regelmodulanschlüssen vor Publikation gegen aktuelle Vorlagen- und Szenenberechtigungen prüfen. Keine Veröffentlichung mit ungültigen Pflichtfeldern, unauflösbaren Referenzen oder unberechtigter Medien-/Rule-Pack-Abhängigkeit.
5. **Keine automatische Datenmigration:** Veröffentlichung aktualisiert vorhandene Charakterinstanzen nicht im Hintergrund. Sollen bereits bestehende Charaktere später eine andere Schema-Version erhalten, benötigt es eine **eigene berechtigte, typsichere und kontrollierte Migration** mit gesicherter Feldzuordnung, Bestandswert-/Inventar-/Regelscope-Prüfung. Die Details der Migrationsbedienung sind eine spätere strukturrelevante eigene Prüfung, kein impliziter 03.3-Automatismus.
6. **Entwurfsrechte und Publikationsrechte:** Mindestens eigene getrennte Permissions für Anlegen, Lesen/Preview, Ändern, Verwerfen, Versionen einsehen, Freigeben/Veröffentlichen, gegebenenfalls Vorlagen anderen zuweisen und spätere Instanzmigration. Wer eine Vorlage bearbeiten darf, erhält weder automatisch Publish-/Adminrechte noch Rechte an fremden Charakterwerten.
7. **SL-/Co-SL-/Gruppenrollen:** Effektive Rechte nach 02.25-Defaults und markierten gültigen Ausnahmen. Ein Co-SL kann ausdrücklich Publikationsrechte erhalten, ein delegierter Spieler etwa nur Entwurfsrechte. Rechteentzug wirkt auf neue Änderungen und neue Freigaben unmittelbar.
8. **Vorlagen sind keine Spielweltaktion:** Bearbeiten/Publizieren erzeugt keinen echten Würfelwurf, Itemtransfer, NPC-Entscheid, Tokenmove, Tür-/Node-Signal oder verdeckte Szenenfreigabe.
9. **Mehrbrowser-Konflikte:** Ein Entwurf mit zwei parallel aktiven Bearbeitern braucht Revisionen und gültige Konflikt-/Editierberechtigungen; die konkrete Sperr- oder Merge-Strategie später. Veraltete Editorzustände dürfen keine neueren veröffentlichten Definitionen still überschreiben.
10. **Unterschiedliche Kampagnen und Genres:** Regeln für Vorlagebibliotheken und Wiederverwendung bleiben nach Scope-/Lizenz- und Rollenrechten abgesichert. Eine Vorlage aus einer anderen Kampagne gibt weder deren SL-Notizen noch Charaktersicht-/Inventarrechte frei.

## 3. Verbindliche Zusatzanforderung: optionale Charaktererstellung

Der Projektinhaber möchte **später ausdrücklich eine optionale Charaktererstellung**, in der Spieler **Klassen wählen, Fähigkeiten/Fertigkeiten auswählen und Punkte verteilen** können. Dieses System soll **datengetrieben und regelwerkskonfigurierbar** auf 03.1-Vorlagen und 03.2-Charakterrechte aufsetzen und darf nicht als verpflichtende Mechanik in den Plattformkern eingebaut werden.

**Der grundlegende Ablauf wird jetzt eingeplant**, ohne bereits Klassenlisten, Punktwerte, Start-Level, Bildschirmseiten oder die Würfel- und Rechenformeln eines bestimmten Rollenspiels zu fixieren.

1. **Modusschalter bei Kampagnenerstellung:** Eine Kampagne oder geeignete Vorlagenart kann die regelgestützte Spieler-Charaktererstellung aktivieren oder deaktivieren. Alternativ kann die SL Charaktere manuell über erlaubte 03.1-Instanz- und Editierrechte anlegen. Kein Spieler wird ohne Modulfreigabe zu einer Regel-/Punkteverteilung gezwungen.
2. **Regel-/Vorlagengebundene Auswahl:** Eine veröffentlichte, für den aktuellen Spieler und die Kampagne berechtigte Charaktervorlagenversion referenziert optionale **Erstellungsschritte** wie Grundwerte, Archetyp/Klasse, Fähigkeit, Fertigkeit, Hintergrund/Varianten und die Anzahl zu verteilender Punkte. Auswahlkategorien sind **Daten/Regelkonfiguration** statt hardcodierter D&D-Klassen.
3. **Stabile Baukastenreferenzen:** Klassen-, Skill-, Fähigkeits- und Punkteregeldefinitionen benötigen prinzipiell stabile, versionierbare IDs und echte erlaubte Referenzen zu Feldern/Regelmoduldefinitionen. Ob Klassen als wiederverwendbare Modulpakete zusätzliche Felder, Skills oder Aktionen bereitstellen und in welcher Vererbung/Komposition, bleibt als **nächste strukturelle Frage 03.4**.
4. **Konfigurierbare Budgets und Validierung:** Punktpool, erlaubte Verteilung, Minimal-/Maximalwerte, Kosten, Voraussetzungen, gegenseitige Ausschlüsse und Pflichtentscheidungen sind **bei Bedarf als validierbare Regel-/Vorlagendaten** modellierbar. Exakte Zahlen und Formeln später. Der VPS bestätigt, dass dieselben Punkte nicht mehrfach ausgegeben, Voraussetzungen nicht umgangen und Optionen aktuell erlaubt sind.
5. **Erstellungsentwurf:** Der Spieler darf einen erlaubten, nicht endgültig angelegten Charakterentwurf mit vorläufigen Auswahlwerten bearbeiten, soweit die Kampagnenpolicy es vorsieht. Ein solcher Wizard-Draft ist kein schon gültiger Kampagnen-Charakter, kein kostenloses Inventar und keine Berechtigung, Token-/Weltaktionen auszulösen.
6. **Validierter Abschluss:** Erst nach erfolgreicher aktueller Server-Validierung (Account, Kampagne, Erstellungs-/Vorlagen-/Klassenrechte, Budget, Voraussetzungen, Feldtypen, Charakteranzahl nach 03.2, Referenzversion) wird daraus eine **konkrete Charakterinstanz** mit dauerhaft gespeichertem gültigem Ausgangszustand. Der Abschluss erfolgt logisch einmalig/idempotent, auch bei Doppel-Klick, Browser-Reconnect oder zwei Tabs.
7. **Manuell vs. Spieler-Wizard:** SL kann bei berechtigter Kampagnenkonfiguration Charaktere vorbereiten oder zulässige Schritte freigeben; ob ein einzelner Spieler Werte später ändern, Punkte neu verteilen, Klassen wechseln oder aufsteigen darf, folgt eigenen echten Regel-/Charakter-ACL und ist mit diesem Grundbeschluss **nicht pauschal erlaubt**.
8. **Keine Rechteerweiterung durch eine Klasse:** Eine Klasse/Fähigkeit kann nach geltendem Regelprofil Spielwerte und erlaubte Aktionen beeinflussen, aber niemals Steamkontozugriff, SL-Rolle, fremde Charakter-/Inventar-/Chatrechte oder geheime Inhalte verleihen. Regelwirksame Würfel-/Item-/Skill-Aktionen gehen über etablierte autorisierte Systeme.
9. **NPCs und Sonderfiguren:** Dieselbe Grundvorlagenarchitektur soll für passende Spieler- und NPC-/Sonderfigurenwerte verwendbar bleiben; NPC müssen nicht zwingend durch einen Spieler-Wizard erstellt werden. Besitzer, aktuell wirksamer Controller und Charakterinstanz bleiben getrennt (03.2).
10. **Feinplanung aufgeschoben:** Konkrete Klassen, Punktekosten, Standardwerte, Fertigkeitskataloge, Stufen-/Levelprogression, Benutzerführung/Seitenfolge, kosmetische Auswahl, Individualisierung und Regelwerkslizenzpakete erst bei passender späterer Implementierung bzw. wenn ihre strukturelle Schnittstelle geklärt wird.

## 4. Serverseitiges Grunddaten- und Ereignismodell

**Nur Arbeitsbegriffe, keine existierenden Datenbanktabellen oder APIs:** CharacterSheetTemplate, CharacterTemplateDraftRevision, PublishedCharacterTemplateVersion, TemplateEditorGrant, TemplatePublisherGrant, CharacterCreationOptionDefinition, CharacterCreationRuleSet, CharacterCreationDraft, CharacterCreationValidationResult, CharacterInstance.

1. **Draft ändern:** Actor, Kampagne, Vorlagen-/Entwurfs-ID und gültiges Editierrecht serverseitig prüfen; neue getypte Feld-/Erstellungsdefinitionen gegen aktuelle Version und referenzierte, berechtigte Ressourcen prüfen.
2. **Veröffentlichen:** Separat aktuelles Publikationsrecht, Vorlagenscope, referenzierte Optionstypen, Regelpakete, stabile IDs, Geheimnis-/Lizenzstatus und Entwurfsrevision validieren. Die publizierte Version bleibt für bestehende Charaktere unveränderliche Bezugsgröße.
3. **Erstellungs-Wizard (nur wenn aktiviert):** Ein berechtigter Spieler lädt nur erlaubte veröffentlichte Vorlage und Auswahloptionen, pflegt eigenen Entwurf, erhält unverbindliche erlaubte Validierungshinweise, sendet einen Abschlusswunsch. Der VPS prüft den vollständigen aktuellen Zustand gegen Budget, Voraussetzungen und Charakter-/Kampagnengrenzen und legt höchstens eine legitime Instanz an.
4. **Datenfluss nach Abschluss:** Charakterwerte und Ressourcen sind CharacterInstance-State nach 03.1, die 03.2-Zuordnung/Delegation separat, Inventar-Item-Instanzen und Tokens separat. Erstellungsoptionen erzeugen keine unbegründeten Inventarobjekte oder Würfelwürfe.
5. **Widerruf und Änderungen:** Entzug von Edit-/Publish-/Creationrechten stoppt neue Operationen. Alte Browserformulare, Draft-Versionen, nicht mehr verfügbare Klassen/Pakete oder veränderte Kampagnenstandards können keine alten, unautorisierten Veröffentlichungen oder unzulässigen Charaktere erzeugen.
6. **Rechtegefilterte Realtimeprojektion:** Spieler sehen nur heute zugelassene Vorlagen, Klassen-/Fertigkeitsoptionen und jeweils berechtigte eigene Charakterentwürfe. Geheime SL-Entwürfe, verbotene Klassen und private Bogenfelder werden nicht als „nur ausgeblendet“ an den Client geschickt.

## 5. Konzeptioneller Umsetzungsplan

1. **ACL-/Templateobjekte:** Vorlagenidentität, Autor-/Editor-/Publisher-Scopes, Entwurfsrevisionen und veröffentlichte Versionen mit stabilen IDs konzipieren.
2. **Publish-Pipeline:** Erlaubte Typen, Felder, Options-/Regelreferenzen, Lizenz-/Assetrechte und kompatible Charakterinstanzversionen prüfen; keine automatische Bestandsmigration.
3. **Optionale Creation-Engine als separates Modul:** Generische definierbare Auswahl-/Budget-/Voraussetzungsregeln und einen versionierten, nichtweltwirksamen Erstellungsentwurf vorsehen. Spielerwahl und serverseitigen Abschluss klar trennen.
4. **Gegenwartsrechte und Multi-Client:** Authentifizierte Rollen/Scopes/Charakterlimits, Race-/Replay-/Reconnect-/Idempotenzschutz und Secret-Projektion für Editieren, Publizieren und Erstellen planen.
5. **Schnittstellen:** 03.1 CharacterInstance, 03.2 CharacterAssignment/Controller, Inventar 01, Tokens/Scene 02, Würfel/Regeln 05/07 und Skills/Sprachen 02.60 typsicher anbinden.
6. **Späteres Feindesign:** Konkrete Vorlagenauswahl, Klickwege, Klassenkataloge, Zauber-/Skill-/Stufenregeln, Zahlen, DB/API/UI und MVP erst beim zugehörigen Entwicklungsschritt. Zuerst **03.4** die strukturelle Verbindung von Klassen/Skills/Fähigkeiten entscheiden.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Berechtigte Co-SL erstellt einen Entwurf | Erlaubtes Editieren; keine automatische Veröffentlichung |
| Spieler hat Draft-Recht, aber kein Publish-Recht | Kein Veröffentlichungs-Commit möglich |
| SL veröffentlicht zulässige Revision | Neue eigenständig referenzierbare, geprüfte Vorlagenversion |
| Spieler besitzt ältere Charakterinstanz | Ihre Feldwerte werden nicht ungeprüft auf neue Version migriert |
| Zwei Editoren verändern denselben Draft | Stale-/Konfliktschutz, keine stillen Änderungen anderer Personen überschreiben |
| Erratene Vorlagen-ID einer anderen Kampagne | Kein Lese-/Edit-/Publishrecht oder Datenleck |
| Creation-Modul deaktiviert | Spieler wird nicht zu Klassen-/Punktwahl gezwungen; erlaubte manuelle Erstellung bleibt möglich |
| Creation-Modul aktiviert, Spieler wählt Fantasyklasse | Nur erlaubte Klassenoptionen und Felder dieser gültigen Vorlage sichtbar |
| Cyberpunk-Vorlage enthält andere Skills als Fantasy | Gleiche Engine, keine hardcodierte Regelwerksklasse |
| Spieler verteilt erlaubte Punkte über mehrere Attribute | Serverseitig geprüfte Summe/Kosten/Grenzen vor Charakterabschluss |
| Spieler versucht dieselben Punkte doppelt auszugeben | Abgelehnt; Budget nicht umgehbar |
| Fähigkeit benötigt Voraussetzung | Auswahl/Abschluss ohne diese Voraussetzung abgelehnt oder gemäß aktuellem Regelprofil behandelt |
| Geheime/gesperrte Klasse existiert | Kein Leck ihrer Bezeichnung/Count/Metadaten in Spieler-Wizard |
| Spieler manipuliert Feldtyp oder Budget im Browser | VPS validiert und lehnt unberechtigte Werte ab |
| Spieler darf maximal N Charaktere besitzen | Aktuelle konfigurierbare 03.2-Policy wird beim Abschluss durchgesetzt |
| Browser schickt zweimal „Charakter erstellen“ | Höchstens eine konkrete gültige Instanz pro logischem Abschluss |
| Wizard-Draft vorhanden, aber nicht freigegeben | Kein autorisiertes Token/Inventar, keine echte Weltaktion |
| Klassenoption ist nach Draft-Beginn widerrufen | Abschluss neu prüfen; kein illegaler Charakter durch veralteten Client |
| Vorlagen-Editor ändert veröffentlichte Feld-ID | Keine unkontrollierte Löschung alter CharacterInstance-Werte |
| Spieler wählt eine Verhexungsfähigkeit | Kein sofortiger Fremdcontroller; spätere legitime 03.2-Regelaktion erforderlich |
| Spieler wählt eine Waffe als Startoption | Keine unautorisierten kopierten Item-Instanzen; nur korrekter späterer Inventarpfad |
| Späterer Klassen-/Levelwechsel | Keine pauschal erlaubte nachträgliche Änderung aus bloßem Creation-Wizard-Recht |

**Nachfolgender Beschluss 03.4 C (16.10.2026):** Klassen, Fähigkeiten und Skills sind versionierte, typen- und rechtegeprüfte Datenmodule mit stabilen Referenzen auf Vorlagenfelder, Fertigkeiten, Regelaktionen, Voraussetzungen und optionale Punktebudgets. Die Klasse ist weder nur Text noch ein hartcodierter Ersatz des ganzen Bogens. Bereits bestehende Instanz-Basiswerte bleiben unabhängig; Klassen- und Itemeffekte werden kontrolliert als eigene Quellen abgeleitet. [03.4 C mit Umsetzungsplan und Tests](CHARAKTER-WORKSHOP-03.4.md). **Nächste Frage 03.5 – Fortschritt vorhandener Figuren.** Die nachfolgende ursprüngliche 03.4-Fragestellung bleibt als historischer Entscheidungsnachweis bestehen.

## 7. Beschlussgrenze und nächste Frage

**Fest beschlossen: 03.3 C.** Getrennte Berechtigungen für Erstellen/Bearbeiten von Vorlagen-Entwürfen und gesondert autorisierte Freigabe/Publikation unveränderlich referenzierbarer Vorlagenversionen; keine ungeprüfte automatische Migration bestehender Charakterinstanzen.

**Zusätzlich verbindlich als Wunsch/Grundanforderung aufgenommen:** Eine **optionale** charakterbasierte Erstellung mit **Klassenwahl, Fertigkeits-/Fähigkeitswahl und Punkteverteilung** als datengetriebener, kampagnenkonfigurierbarer Ablauf. Der VPS prüft bei Abschluss Budgets, Voraussetzungen, Rechte und gültige Vorlage; einzelne Punktzahlen, Klassen und das endgültige Wizard-Layout bleiben später zu entscheiden.

## Nächste Entscheidung 03.4 – Wie beeinflussen Klassen und Fähigkeiten den Charakterbogen strukturell?

**Beispiel:** Ein Spieler wählt die Klasse „Techniker“ statt „Soldat“. Die Klasse könnte unterschiedliche Startfertigkeiten, zusätzliche Fähigkeiten, verfügbare Aktionen oder andere erlaubte Punkteregeln anbieten, ohne das Charakterbogen-Schema neu programmieren zu müssen.

- **A – Klassen als bloße Beschriftung:** Klassenwahl wird nur als Text/Auswahl gespeichert, ohne strukturierte Effekte, Voraussetzungen oder Verbindungen zu Fertigkeiten und Punkten.
- **B – Feste Klasse überschreibt den gesamten Bogen:** Für jede Klasse gibt es eine hardcodierte vollständige Charakterfeldstruktur, die bei Wahl andere Werte/Slots ungeprüft überschreibt und nur per Programmänderung erweitert werden kann.
- **C – Versionierbare modulare Klassen-/Fähigkeitsbausteine (Empfehlung):** Klassen und Auswahloptionen sind berechtigte, versionierte Datenmodule mit typisierten Voraussetzungen, erlaubten Feld-/Skill-/Aktionsverweisen und bei Bedarf konfigurierbaren Punktbudgets. Sie erweitern bzw. beeinflussen eine gemeinsame 03.1-Vorlage über definierte geprüfte Regeln, **ohne** ungeprüften Bestandswertüberschreibungen. Konkrete Klassenkataloge, Preise und UI später.
