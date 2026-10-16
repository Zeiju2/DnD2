# AdventureShift – Charakter-Workshop: Beschluss 03.7 C – sichere abgeleitete Werte und wiederverwendbare Regelwerksvorlagen

**Stand:** 16.10.2026. **03.7 C beschlossen**, mit ausdrücklicher Ergänzung des Projektinhabers: **selbst anlegbare, speicherbare und mitgelieferte Regelwerksvorlagen für schnell startbare Partien**. **Nächste Strukturfrage: 03.8 – Zustände und zeitlich/ereignisgebundene Effekte an Figuren.**
**Status:** Verbindliche fachliche Grundstruktur mit Schnittstellen, Rechten, Ablauf und Abnahmetests; **keine Software implementiert**. Konkrete Presets, Regeltexte, Formeln, Zahlen, UX, API/DB, Ressourcenlimits und MVP-Reihenfolge erst später festlegen.
**Bezüge:** [03.1 typisierte Charaktervorlagen](CHARAKTER-WORKSHOP-03.1.md) · [03.2 Charakterkontrolle](CHARAKTER-WORKSHOP-03.2.md) · [03.3 Draft/Publish und optionale Charaktererstellung](CHARAKTER-WORKSHOP-03.3.md) · [03.4 Klassen/Fähigkeiten/Skills](CHARAKTER-WORKSHOP-03.4.md) · [03.5 Fortschritt](CHARAKTER-WORKSHOP-03.5.md) · [03.6 kontrollierte Migration](CHARAKTER-WORKSHOP-03.6.md) · [01 Inventar, 02 Karten/Nodes, 05 Würfel, 07 Regelprofile, 12 Bibliothek](FEATURE-WORKSHOP.md) · [Planungsstandard](PLANUNGSSTANDARD.md).

## 1. Entscheidung und Benutzerziel

**Variante C:** Ein **optionales, versionsgebundenes und sicheres System für abgeleitete/berechnete Charakterwerte** kombiniert deklarativ definierte, typisierte Quellen – etwa gespeicherten Basiswert, Klasse, Fähigkeit, Skill, Ausrüstung und temporären Zustand – zu einem aktuellen Wert wie Angriff, Verteidigung oder Traglast. Die Berechnungen laufen fachlich **serverautoritativ**; Browser dürfen erlaubte Ergebnisse darstellen, aber nicht als vertrauenswürdige Spielregel durchsetzen.

**Zusatz des Projektinhabers (gleichrangig beschlossen):** Spielleiter bzw. entsprechend Berechtigte können **Regelwerksvorlagen anlegen, speichern, erneut nutzen und weiterentwickeln**. AdventureShift soll auch **mitgelieferte, sofort auswählbare Basis-/Regelwerksvorlagen** anbieten, damit eine **schnelle Partie** mit wenigen Entscheidungen vorbereitet werden kann. Später lassen sich eigene und bereitgestellte Vorlagen nach gültigen Rechten anpassen und versionieren. Der Kern ist genre- und regelwerksneutral; weder D&D noch ein anderes System darf ein fest eingebautes Pflichtmodell sein.

**Keine Festlegung konkreter Vorlagen oder vollständiger Drittanbieter-Regelwerke:** Welche tatsächlich mitgelieferten Regelprofile, Genres, Lizenzen, Datenpakete oder Fertigstellungsstufen verfügbar sind, wird gesondert geplant; lizenzpflichtige Namen, Texte und Mechaniken werden nicht ohne passende Nutzungsrechte mitgeliefert. Eine Startervorlage muss nicht automatisch sämtliche Regeln eines externen Spielsystems abdecken.

**Nicht gewählt:** A (nur dauerhaftes manuelles Eintragen aller Ableitungen ohne Regelstruktur) und B (beliebiger ungeprüfter ausführbarer Browser-/Servercode für Formeln). Manuelles Spielen bleibt **als wählbarer Modus** erhalten und wird gerade nicht abgeschafft.

## 2. Grundlegende Daten- und Modulstruktur

1. **RuleTemplate/RulePackVersion (Arbeitsnamen):** Wiederverwendbarer, versionierbarer und veröffentlichbarer Regelprofil-Datensatz mit stabiler ID, Eigentümer/Herkunft, Scope (persönlich, Kampagne, freigegebene Bibliothek, mitgeliefert), Berechtigungen, Kompatibilität, Modulliste, geeigneten Charakterbogen-/Klassen-/Skill-/Würfel-/Fortschritts-/Inventarverweisen, sicheren Formeln und zulässigen Starteinstellungen. Ein Profil besteht aus **Referenzen und Konfiguration**, nicht aus einem unkontrolliert ausführbaren Skript.
2. **Vorlage vs. Kampagne:** Eine Kampagne referenziert bei Auswahl eine **konkrete gültige Vorlagenversion** und bildet daraus ihre gesonderte, berechtigte Kampagnenkonfiguration. Vorlagenänderungen ändern bereits laufende Kampagnen/Charaktere **nicht still**. Spätere selektive Regel-/Charaktermigration folgt 03.6 und den zukünftigen Freigabe-/Kompatibilitätsregeln; Änderungen dürfen den realen Weltzustand nicht zurückspulen.
3. **Modulare Aktivierung:** Rechenregeln, Klassen, optionale Charaktererstellung, Fortschritt, Inventarboni, Würfel-/Kampf- und andere Automatisierung haben eigenständige, kompatibilitätsgeprüfte An-/Aus- und Freigabegrenzen. Ein vorbereiteter Schnellstart bietet **Defaults, keine irreversiblen Zwangsmodule**. Eine rein manuelle Kampagne ist gültig. Die übergreifende UI-Führung bei Kampagnenerstellung wird wie 02.48 vereinbart **erst nach den Featureblöcken** ausgearbeitet.
4. **Gespeicherte vs. berechnete Daten:** CharacterInstance hält dauerhafte, autorisiert geänderte Basis-/Ressourcen-/Progressionswerte; effektive abgeleitete Werte werden aus gültigen Quelldefinitionen und aktuellen Zuständen ermittelt. Anzeige oder Neuberechnung überschreibt den gespeicherten Basiswert nicht und vergibt keine Items, Skillpunkte, XP oder World-/Würfelaktionen.
5. **TypedDerivedField/FormulaRule (Arbeitsnamen):** Regel nennt typisiertes Ergebnisfeld, Quell-IDs, erwartete Datentypen/Einheiten, erlaubte Operationen, Version, Kontext/Kompatibilität und Grenzen. Namen/Labels allein sind keine stabilen Referenzen. Fehlende, geheimhaltungsbedingt unzulässige, widersprüchliche oder inkompatible Quellen sind **definierte Fehler/Blocker**, keine willkürliche Nullsetzung.
6. **Abhängigkeitsgraph:** Der VPS prüft bei Entwurf/Publikation/Aktivierung Formeln und Abhängigkeiten auf Typen, unzulässige Referenzen, Zyklen und begrenzte Rechenkosten. Keine frei programmierbaren JavaScript-, SQL-, Shell- oder externen Code-Snippets aus RulePacks. Die tatsächlich erlaubte Ausdruckssprache, Rundung, Stacking, Grenzfälle und Performancebudgets werden **bei der Umsetzung** bestimmt.
7. **Klassen, Ausrüstung und Zustände:** Gültige 03.4-Module, 01-Item-/Ausrüstungsbeziehungen und spätere 03.8-Status-/Effektinstanzen liefern jeweils nachvollziehbare **getrennte Quellen** für Ableitungen; die konkrete Stapel-/Vorrangregel bestimmt das aktivierte Regelprofil. Doppelte oder abgelaufene Quellen dürfen sich nicht ungeprüft weiter auswirken.
8. **Revisions- und Ereignisgrenzen:** Ändert sich eine zulässige Eingabe, wird die aktuelle Ableitung für zukünftige autorisierte Aktionen neu ermittelt oder konsistent invalidiert. Lokale Zwischenspeicher sind **kein maßgeblicher Spielzustand**. Historische Würfelresultate, verbrauchte Gegenstände, gespielte Szenen und frühere Regelanwendungen bleiben unverändert.
9. **Sicht- und Berechnungsrechte:** Berechnung und Projektion werden getrennt autorisiert. Nicht nur das Ergebnis, sondern auch Quellwerte, Formeldetails, geheime SL-Fähigkeiten, versteckte NPC-Zustände und Rechteableitungen bleiben nach 02.25/03.1–03.6 gefiltert. Auch Cache, Realtime, Fehlerdetails und vorab geladene Presets dürfen keine fremden Kampagnen- oder Geheimdaten ausliefern.
10. **Vorlagenlebenszyklus:** Berechtigte Personen dürfen eine Vorlage entwerfen, speichern, eigene Entwürfe bearbeiten, freigegebene Vorlagen auswählen und ggf. **als eigene Kopie/Abzweigung** weiterentwickeln; Entwurf, Veröffentlichung, Teilen, Import und die Anwendung auf eine konkrete Kampagne sind **getrennte Rechte**. Eine freigegebene Vorlage wird nicht durch die Bearbeitung einer abgeleiteten Kopie überschrieben. Welche Bibliotheksfreigaben, Paketimporte/-exporte und Publikationswege allgemein gelten, wird mit Modul 12/15 entschieden.
11. **Mitgelieferte Vorlagen:** Es gibt ein Konzept für **nutzbare, getestete Startprofile** (z. B. einfache freie Sandbox oder eigene generische Genreprofile, sofern später bestimmt), die hinsichtlich Rechten, Assets, Format- und Regelfassungen valide sind. Ein auswählbares Startprofil kann vorbereitete Werte/Charakterfelder/Module enthalten, **ohne** geheimen Content oder nicht rechtmäßig verwendbare Fremdregeltexte auszuliefern.
12. **Schnellstart-Flow:** Berechtigter Kampagnenersteller wählt ein gültiges Startprofil → VPS prüft Profil-/Lizenz-/Asset-/Kompatibilitätsrechte → erzeugt eine **eigene Kampagnenkonfiguration mit gültigen Defaults** → SL kann erlaubte Einstellungen ändern, Module deaktivieren oder direkt zum gemeinsamen Spielraum/Lobby fortfahren. Nur für wirklich autorisierte Nutzer/Charaktere werden erforderliche Spielinstanzen erzeugt; keine automatische Vervielfältigung von Spielercharakteren, XP oder Inventargegenständen.
13. **Speichern und Wiederverwenden:** Personalisierte Vorlagen sind nach erneuter Anmeldung, anderer zulässiger Kampagne und auf Wunsch als neue Vorlage weiterverwendbar. Speichern betrifft den gültigen Vorlagensatz, nicht automatisch Geheimnisse, Besitzerrechte, laufende Charakterspeicher oder vollständige fremde Kampagnenstände. Kompatibilitäts- und Lizenzprüfung gilt auch bei Nutzung in einer späteren Kampagne.
14. **Fehler-/Konfliktverhalten:** Defekte oder nicht berechtigte Presets/Formeln werden **nicht teilweise spielweltwirksam** geladen. Sichere Diagnose nur an Berechtigte, klarer Abbruch bzw. gültiger manueller Fallback nach aktiver Entscheidung; keine stillschweigende Auswertung mit falschen Werten. Gleichzeitige Entwurfsbearbeitung braucht Revision-/Konfliktkontrolle; idempotenter Schnellstart gegen Doppelklick/Reconnect.
15. **Feingranularität später:** Bestimmte Vorlagenlisten, Anzahl an Einstellungen, Punktzahlen, Formelsyntax, konkrete Demo-Kampagnen, Defaultrollen, UI-Assistent, Installations-/Downloadoptionen, Dateiformate, DB und MVP-Zuordnung sind **bewusst keine heutigen Beschlüsse**.

## 3. Konzeptioneller Umsetzungsablauf

1. RuleTemplate- und RulePack-Versionen samt Scope/ACL, zulässigen Modulkombinationen, stabilen Referenzen und kompatiblen veröffentlichten Vorlagen-/Regelquellen definieren.
2. Serverautoritative typisierte Ableitungen auf stabile Feld-/Modul-/Item-/Statusquellen modellieren; Eingabe-/Ausgabevalidierung, Zyklen, fehlende Quellen und Ressourcenbudgets abfangen.
3. Gespeicherte Charakterbasis, aktive Status-/Itemquellen und effektiv berechnete Werte so trennen, dass keine doppelten World-/Würfel-/XP-/Inventarcommits entstehen.
4. Berechtigten Vorlagen-Entwurf, -Speichern, -Publizieren, -Kopieren und versionierte Wiederverwendung auf Basis 03.3/03.6 und der späteren Bibliotheksrechte ermöglichen.
5. Schnellstart mit Auswahl eines **berechtigten geprüften** Presets, Erstellen einer eigenen Kampagnenkonfiguration und regulärem SL-/Spielerzugang planen. Keine globale automatische Aktualisierung laufender Kampagnen.
6. Sichere Browserprojektionen und Rechte-/Lizenz-/Geheimnisprüfung auf Vorlagen, Zwischenergebnisse, Formelquellen, Reconnect und Cache testen.
7. Auswahl mitgelieferter Starterprofile, konkrete UI/API/DB, Regelmath und Release-/MVP-Umfang erst nach dem zusammenhängenden Grundstruktur-Workshop festlegen.

## 4. Fachliche Abnahmetests

| Szenario | Erwartung |
| --- | --- |
| SL startet mit mitgeliefertem berechtigtem Profil | Kampagne/Lobby erhält eigene gültige Voreinstellungen; kein Pflichtdurchlauf durch sämtliche Regeldetails |
| SL erstellt eigenes Profil, speichert und nutzt es erneut | Versionierte Vorlage bleibt verfügbar und erzeugt später wieder gültige eigene Kampagnenkonfigurationen |
| Vorlage wird kopiert und angepasst | Original/andere Kampagne bleibt unverändert |
| Neu veröffentlichte Regelversion | Ändert keinen Bestandscharakter ohne kontrollierte 03.6-Migration |
| Einfacher manueller Modus | Freie Charakterwerte und Spiel ohne Berechnungssystem möglich |
| Char-Basis + Klassenbonus + Item + Status | Typkonformer aktueller abgeleiteter Wert; gespeicherte Basis unverändert |
| Item abgelegt oder Effekt endet | Neuer effektiver Wert ist für künftige Aktionen korrekt; keine Vergangenheitsänderung |
| Formel mit Zyklus, inkompatibler Einheit oder fehlendem Feld | Veröffentlichung/Anwendung scheitert kontrolliert ohne Teilwirkung |
| Browser fälscht Ergebnis einer Ableitung | VPS verwendet nur autorisierte, gültige Definitionen/Eingaben |
| Spieler öffnet fremde oder geheime Vorlage | Keine unberechtigten Daten via UI, WebSocket, API, Cache oder Fehlermeldungen |
| Lizenz oder Profilberechtigung entzogen | Neue unberechtigte Nutzung gesperrt; keine Rechteausweitung durch Kopie |
| Vorlagen-Schnellstart doppelt gesendet | Keine doppelte Kampagne oder doppelte Figuren-/Item-Erzeugung je fachlicher Operation |
| Zwei Browser bearbeiten denselben Entwurf | Revisionkonflikt statt stillem Lost Update |
| Profil erlaubt Modul ohne gültige Abhängigkeit | Hinweis/Blocker vor Veröffentlichung oder Kampagnenaktivierung |
| Historischer Wurf nach Regelrevision | Vergangenes Würfel-/Welt-/Inventarereignis unverändert |

## 5. Beschlussgrenze und nächste Frage

**03.7 C verbindlich:** Optionales, typisiertes, serverseitig geprüftes Regelberechnungssystem mit versionierten sicheren Formeln und getrennter Speicherung echter Basiswerte. **Zusätzlich verbindlich:** Eigene anlegbare/speicherbare/wiederverwendbare Regelwerksvorlagen und Konzept für mitgelieferte Startprofile für schnelle Partien; gesicherter Kampagnenableitungs-/Kopiervorgang, keine stillen Regelupdates, freie manuelle Spielweise möglich.

**Nicht entschieden:** konkrete regelwerkspezifische Inhalte, Lizenzrechte für Drittanbieterpakete, Auswahl der Startprofile, Formeln, UX-Screens, detaillierte Datenverträge, genaue Defaultautomatisierung und MVP/Releasezuordnung.

### Nächste Strukturfrage 03.8 – Wie werden Zustände und zeitlich begrenzte Effekte an Figuren geführt?

**Beispiel:** Eine Figur wird vergiftet, erhält für drei Runden einen Schild oder wird zeitweise verzaubert. Das kann Werte, erlaubte Aktionen und die Steuerrechte beeinflussen. Was müssen wir dafür grundsätzlich planen?

- **A – Nur manuelle Notizen:** Zustände und ihre Dauer sind freie Texte/Marker; Spielleiter und Spieler aktualisieren Folgen selbst.
- **B – Festes universelles Statussystem:** Die Software erzwingt für alle Genres dieselben Zustände, Dauern und Wirkungen.
- **C – Optionales datengetriebenes Status-/Effektmodell (Empfehlung):** Versionierte, regelwerksbezogene Zustandstypen und separate konkrete Effektinstanzen mit Quelle, Ziel, Dauer-/Beendigungsbedingungen, Berechtigungen und getypten Bezügen zu 03.7-Berechnungen, 03.2-Kontrollrechten und 02-Node-/Ereignissystem. Der VPS prüft Auslösung, Änderung und Ende; rein manuelle Kampagnen können das Modul deaktivieren. Genaue Zustandslisten, Zahlen und UI später.
