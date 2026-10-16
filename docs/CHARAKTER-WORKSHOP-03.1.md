# AdventureShift – Charakter-Workshop: Beschluss 03.1 C – versionierbare, typisierte und regelwerksunabhängige Charakterbögen

**Stand:** 15.10.2026 · **Status:** Verbindlicher Fachbeschluss und Architekturplanung, **keine Softwareimplementierung**. Nächste strukturelle Frage **03.2 – Charakterzuordnung und Steuerrechte**.
**Planungstiefe:** [Grundstruktur jetzt, genaue Zahlen/UI später](PLANUNGSSTANDARD.md).
**Bezüge:** [Feature-Workshop](FEATURE-WORKSHOP.md) · [Features AS-07/AS-08](FEATURES.md) · [Architektur](ARCHITEKTUR.md) · [Projektplan](PROJEKTPLAN.md) · [Inventar-Workshop 01](FEATURE-WORKSHOP.md) · [Sprachen als Skills 02.60](FEATURE-WORKSHOP.md) · [Würfel-/Check-/Node-Beschlüsse](KARTEN-WORKSHOP.md).

## 1. Verbindliche Entscheidung – Variante 03.1 C

**Der Projektinhaber hat C gewählt.** Charakterbögen werden nicht je Regelwerk hardcodiert. Es gibt **datengetriebene, regelwerksneutrale, versionierte Charaktervorlagen** mit typisierten Felddefinitionen und daraus erzeugte **konkrete Charakterinstanzen**, deren eigene Daten unabhängig von Vorlagen und Darstellung erhalten bleiben. Der SL bzw. später berechtigten Vorlagenbearbeitern stehen konfigurierbare Feldtypen, Vorgaben und geregelte Verbindungen zu Modulen zur Verfügung, ohne dass der Kern feste Werte wie Stärke, Trefferpunkte, Mana, Skill-Limits oder D&D-Klassen voraussetzt.

**Beispiel:** Eine Fantasykampagne verwendet Kraft, Lebenspunkte und Zauberressourcen; eine Cyberpunkkampagne Technik, Energie, Schutz und Schießfertigkeit. Beide verwenden dieselbe Engine und können eigene Felder und Würfelaktionen definieren. Ein neues Regelwerksprofil braucht neue Daten/Vorlagen und geeignete Regeladapter, **keine** fest in den Plattformkern einprogrammierten Fantasyattribute.

**Nicht gewählt:** A – starre, per Regelwerk in der Software programmierte Charakterblätter; B – ausschließlich unstrukturierter Freitext ohne verlässlich typisierte Werte/Verknüpfungen. **C bedeutet kein uneingeschränkt ausführbares Skripting, keine fertige Regelwerksautomation und keinen heute festgelegten Standardbogen.**

## 2. Grundlegendes Datenmodell

1. **Charakterbogen-Vorlage:** Stabile Vorlagen-ID, fachliche Zugehörigkeit/Verfügbarkeit, Version, Benennung und typisierte Felddefinitionen. Welche Person Vorlagen erstellen, freigeben und ändern darf, wird über tatsächlich wirksame Server-ACL geregelt; genaue Kollaborations- und Bibliotheksrechte später gesondert.
2. **Vorlagenversion:** Veröffentlichte Definitionen dürfen nicht unkontrolliert unter derselben Versionsreferenz verändert werden. Neue Felder/Typen oder strukturelle Änderungen erzeugen eine neue definierte Version oder kontrollierten Entwurfszustand. Der Datensatz eines bestehenden Charakters referenziert seine **gültige zugrundeliegende Version**, nicht blind das aktuellste Schema.
3. **Felddefinition:** Stabile maschinenlesbare Feldkennung **getrennt vom angezeigten Namen**, Datentyp, zulässiger Wertbereich/Validierung, optionaler Startwert und geeignete Sicht-/Bearbeitungsrechte. Konzeptionelle Typfamilien: Text/Beschreibung, Zahl, Ja/Nein, Auswahl, Ressource mit gegenwärtigem/zulässigem Maximum, Fertigkeit/Skill sowie ausdrücklich erlaubte Aktions-/Referenzfelder. Konkretes Typinventar, Einheiten und Formularbedienung später; kein Feldtyp darf ungeprüften Code ausführen.
4. **Charakterinstanz:** Eigene eindeutige Charakter-ID, Kampagnenbindung, gültige Vorlagenversionsreferenz und **eigene** Feldwerte/Zustände. Kein Wert wird nur durch die UI repräsentiert. Zwei Charaktere aus derselben Vorlage können völlig verschiedene Fertigkeiten, Ressourcen und Gegenstände besitzen.
5. **Entwurf vs Instanz:** Änderungen einer Vorlage verändern bestehende Instanzen nicht automatisch. Neue Vorlagenversion und etwaige Migration existierender Charaktere erfordern später explizite fachliche Entscheidung, typsichere Zuordnung und Rechte-/Werteprüfung. Stabile IDs dürfen nicht ohne kontrollierte Migration neu vergeben werden.
6. **Feldwerte und Ressourcen:** Aktuelle Ressourcenwerte und zugelassene Grenzen getrennt von der Felddefinition speichern. Abgeleitete Modifikatoren aus Items/Regeln sind **keine dauerhafte Änderung des gespeicherten Basiswerts**; Inventar 01 und optionale Regelmodule behalten eigene fachliche Autorität.
7. **Verweise auf andere Module:** Charakter-ID ist nicht automatisch SteamID, Spielerprofil-ID, Token-ID, Inventarcontainer-ID oder NPC-ID. Die Plattform braucht stabile explizite **Relationen** zu Kampagnenmitgliedschaften/Steuerrechten, Kartentokens, Inventar/Iteminstanzen, Fertigkeiten, Würfelaktionen und optionalen Regelprofilen. Wie viele Charaktere ein Benutzer verwaltet und ob mehrere Benutzer dieselbe Figur steuern dürfen, ist die nächste Grundsatzfrage **03.2**.
8. **Sprachen/Skills (02.60):** Kampagnenweit definierte Sprachen werden als erlernbare/verbesserbare Fertigkeiten oder freigegebene Verweise modellierbar, ohne hartcodierte globale Sprachenliste. Gleichartige Skills für NPCs/Figuren benötigen stabile, nach jeweiligen Rechten zugängliche Referenzen; welche Steigerungsformeln benutzt werden, ist **nicht** Teil von 03.1.
9. **Freitext bleibt möglich:** C schließt frei bearbeitbare beschreibende Text-/Notizfelder nicht aus. Sie sind ausdrücklich typisierte bzw. als Freitext gekennzeichnete Felder, nicht anstelle des strukturierten Bogenmodells.
10. **Größen/Defaults offen:** Anzahl von Feldzeilen, Reitern, Slots, Ressourcenkategorien, Startattributen, Klassen/Rassen und Detaildarstellungen wird später aus Vorlage/Setting bestimmt. Keine solche Zahl darf in der Engine fest vorgegeben werden.

## 3. Rechte, Datenfluss und verbindliche Grenzen

1. **VPS autoritativ:** Eine erlaubte Feldänderung wird serverseitig gegen Identität, Kampagne, konkrete Charakterinstanz, aktuelle Vorlagenversion, Feldtyp, Wertgrenzen, ACL und gegebenenfalls aktives Regelprofil geprüft, persistent übernommen und erst danach als wirksame Änderung in andere berechtigte Browser projiziert.
2. **Differenzierte Rechte vorsehen:** Mindestens Vorlagen bearbeiten, Charakterinstanz sehen, Feldwert sehen, Feldwert ändern, SL-/Systemkorrektur und ggf. Aktionen auslösen fachlich getrennt halten. Ob ein Nutzer einen oder mehrere Charaktere verwalten darf, ob Delegation möglich ist und welche SL-/Spielerrollen gelten, wird in **03.2** entschieden. Verdeckte SL-Felder dürfen auch nicht durch Listen, Fehlermeldungen oder Realtime-Payloads verraten werden.
3. **Schema- und Laufzeitkonflikte:** Zwei Browser, unterschiedliche Tabstände, Reconnect und gleichzeitige Updates benötigen stabile Feldreferenzen, Version/Revision und nachvollziehbaren Umgang mit Konflikten. Ein veralteter Client darf weder ein neueres Schema noch fremde Werte überschreiben.
4. **Regelaktionen statt freiem Code:** Ein Feld darf von einem geeigneten berechtigten Regel-/Würfelmodul referenziert werden. Eine Aktion erzeugt nur über den **autorisierten Server-/Würfel-/Regelpfad** einen echten Effekt – nicht allein durch einen unvalidierten Button, HTML-Formelausdruck, manipuliertes Browser-JSON oder Vorlage.
5. **Inventar-Integration:** Gegenstand/Slot/Container und deren Besitzer/Ausrüstung aus 01 behalten eigene IDs und Rechte. Charakterwerte können davon abhängig sein; daraus abgeleitete Modifikatoren dürfen keine stillen dauerhaften Basiswertüberschreibungen, Itemduplikate oder unberechtigten Inventartransfers erzeugen.
6. **Token-/Karten-Integration:** Figurenposition, Fog/Sicht, Bewegung, Tür-/Node-Weltzustand und mögliche mehrere Tokens sind getrennt vom Charakterbogen zu verwalten. Ein Charakterbogen-Edit ist kein automatisch autorisierter Token-Move, NPC-Alarm, Tür-Trigger oder Zugwechsel.
7. **VPS/Browser und Vorladen:** Browser laden nur heute berechtigte Charakter-/Feld-/Portrait-/Assetdaten. Unsichtbare SL-Notizen, fremde Charakterwerte und versteckte Fertigkeiten werden nicht zur bloßen Frontend-Ausblendung übertragen. Datenbank/Backend auf VPS, individuelle Spielersicht im eigenen Browser.
8. **Kein ungewolltes Tracking/Autonomie:** Keine automatisch festgelegten KI-Figurenaktionen, freien Nutzerprogramme, unlizenzierte Regeltexte oder Übernahme von Medien-/Kampagnenrechten durch den Import eines Bogens. Import und Vorlagenbibliothek werden später strukturell geprüft.

## 4. Konzeptioneller Umsetzungsplan

1. **Kernobjekte definieren:** Vorlagen, unveränderlich referenzierbare Vorlagenversionen, typisierte Felddefinitionen, Charakterinstanzen, getypte Werte, Rechte- und Änderungsrevisionen modellieren; konkrete DB-/API-Namen später entscheiden.
2. **Feldtyp-Registry und Validierung:** Erlaubte Basistypen, Wertebereiche, optionale Ressourcen, Referenz-/Aktionsdeskriptoren und notwendige SL-/Spieler-Sicht-/Bearbeitungspolicies ohne fest codierte D&D-Attribute. Vorsicht bei abgeleiteten Werten und unzulässiger Arbitrary-Code-Ausführung.
3. **Charakter aus Vorlage erstellen:** Kampagnenscope, gewählte gültige Vorlagenversion, individuelle Anfangswerte und explizite Charakteridentität persistent anlegen. Keine festen Feldanzahlen, keine automatische Spieler↔Charakter↔Token-1:1-Beziehung unterstellen.
4. **Änderungen und Ereignisse:** Serverseitig validierte Feld-Updates, getrennte Sicht-/Edit-Freigaben und minimale nur berechtigte Realtime-Änderungsprojektionen; Idempotenz, Konfliktbehandlung, Reset/Reload/Mehrbrowser.
5. **Schnittstellen prüfen:** Charakterwerte als typsichere Quellen für optionales Würfel-/Regelmodul und Inventareffekte; bestehende Item- und Token-/Karten-Autorität unangetastet. Sprachen-/Skills aus 02.60 als mögliches Templatefeld und stabile Referenz.
6. **Versionierung/Migration:** Schemaentwurf vs verwendete Instanzen trennen, vollständige kontrollierte Migrationsmöglichkeiten für später planen; kein heimliches Löschen alter Charakterdaten beim Template-Edit.
7. **Späteres Detaildesign:** Exakte Standard-Feldliste, Layout, Anzahl Skills, Formeln, Sprachenlernkurven, UI-Fenster, Defaultwerte und MVP-Einstufung beim entsprechenden Entwicklungsschritt. 03.2 klärt zuerst die Character-Zuordnung/Steuerrechte.

## 5. Fachliche Abnahmetests

| Test | Erwartung |
| --- | --- |
| SL erstellt Fantasy- und Cyberpunk-Vorlage | Verschiedene Feldschemata ohne Programmänderung |
| Zwei Charaktere nutzen dieselbe Vorlage | Individuelle Feldwerte und Ressourcen bleiben getrennt |
| Feld „Technik“ wird umbenannt | Stabile Feld-ID und Daten-/Aktionreferenzen bleiben gültig |
| Neues Pflichtfeld kommt in Vorlagenversion | Bestehende Figurenwerte nicht ungeprüft überschreiben oder löschen |
| Ressource wird außerhalb des zulässigen Bereichs geändert | Serverseitige Typ-/Grenzvalidierung verweigert oder behandelt nach gültiger Policy |
| SL-sichtbares Feld, fremder Spieler | Kein Feldwert in der Spielerprojektion, auch nicht in der Realtime-Payload |
| Manipulierter Browser sendet unberechtigten Edit | VPS lehnt Änderung ohne fremden Datenleak ab |
| Spieler A und Spieler B bearbeiten konkurrierend | Stale-/Versionskonflikt wird konsistent behandelt |
| Browser reconnect oder VPS-Neustart | Zugelassene Charakterinstanzwerte sind persistent |
| Item-Bonus wirkt auf numerisches Attribut | Abgeleiteter Bonus darf Basiswert nicht dauerhaft korrumpieren |
| Charakterbogen wird mit Würfelaktion verknüpft | Aktiver autorisierter Würfelpfad, nicht durch unvalidierten Client |
| Sprachen aus 02.60 | Als konfigurierbare Skills/Feldreferenzen modellierbar |
| Charakter wird einem Kartentoken zugeordnet | Explizite gesicherte Beziehung, Charakterbogen ist keine Kartenposition |
| Alter Char erhält neue Vorlage | Keine stille Feld- oder Secret-Migration ohne geprüften Prozess |
| Feldanzahl 2 statt 4 in zwei Vorlagen | Datenmodell funktioniert ohne Schema-/Codeänderung |
| Charakter und NPC besitzen ähnliche Felder | Keine automatische Fremdberechtigung; geeignete gemeinsame Typkonzepte möglich |
| Geheime NPC-/SL-Felder werden vorab geladen | Verweigert; nur aktuell autorisierte Daten an Browser |

**Nachträgliche bestätigte strukturelle Ergänzung (16.10.2026):** Als weiteres, bei Kampagnenerstellung **optionales Modul** sollen Spieler Charaktere künftig per erlaubter **Klassenwahl, Fähigkeiten-/Fertigkeitswahl und Punkteverteilung** erschaffen können. Dafür 03.1-Felddefinitionen/Charakterinstanzen und versionierte Schablonen verwenden; Erstellungsentwurf und budgetsichere Servervalidierung bei Abschluss getrennt halten. Kein hardcodiertes Regelwerk und keine jetzt zu entscheidenden Standardpunktzahlen oder Klassenlisten. [Beschluss und Ablaufplanung 03.3 C](CHARAKTER-WORKSHOP-03.3.md); 03.4 klärt die modulare Klassen-/Fähigkeitsstruktur. Bestehender 03.1-Beschluss bleibt gültig.

## 6. Beschlussgrenze und nächste Strukturfrage

**Verbindlich: 03.1 C** – Versionierte, typisierte Charaktervorlagen und konkrete unabhängige Charakterinstanzen mit stabilen Feld-IDs und erlaubten Erweiterungsschnittstellen. Ohne festes Regelwerk oder hardcodierte Slot-/Feldanzahlen. Template-Edits dürfen alte Charakterwerte nicht unkontrolliert ändern; Identität, ACL, Speichern und Realtime-Sicherheit sind serverautoritativ.

**Offen:** Wer wie viele Charaktere anlegen, besitzen, bearbeiten oder steuern darf; Mehrspieler-/SL-Delegation; NPC-Wiederverwendung; konkrete Feld-/Formel-/Layoutdetails. Erste dieser Fragen ist **03.2**.

## Nächste Entscheidung 03.2 – Zuordnung und Steuerrechte von Charakteren

**Beispiel:** Ein Spieler spielt zwei Charaktere in derselben Kampagne, die Spielleitung verwaltet NSCs, oder eine Gruppe möchte vorübergehend die Steuerung eines gemeinsam verwendeten Charakters übernehmen. Die Datenstruktur soll diese Fälle ermöglichen oder ausdrücklich ausschließen.

- **A – Starre Eins-zu-eins-Zuordnung:** Pro Kampagne genau ein Charakter pro Spieler, genau ein Spieler pro Charakter, Charakterbesitz dauerhaft an sein Konto gebunden; Sonderfälle nur mit technischem Umbau.
- **B – Alle dürfen alles steuern:** Jeder Teilnehmer kann ohne weitere Rechte jeden Charakter ansehen, verändern oder für ihn handeln.
- **C – Konfigurierbare serverseitige Charakterrechte (Empfehlung):** Eine Kampagne kann unter SL-/Rollen-/Gruppen-/Charakterpolicy eine oder mehrere Figuren pro berechtigtem Benutzer, gesonderte Sicht-/Bearbeitungs-/Steuerbefugnisse und bewusst freigegebene Delegationen vorsehen. Steam-Konto, Charakterinstanz, NPC und Token bleiben getrennte Entitäten; keine fremden Charakterdaten oder Aktionen ohne aktuelle Autorisierung. Exakte Standardlimits und UI erst später.
