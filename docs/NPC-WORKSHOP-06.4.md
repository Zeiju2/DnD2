# AdventureShift – NPC-/Gegner-Workshop: Beschluss 06.4 C – sichere Handlungs- und Verhaltensprofile

**Stand:** 17.10.2026. **06.4 C vom Projektinhaber verbindlich beschlossen.**
**Status:** Fach- und Architekturplanung mit Umsetzungsablauf und Grundtests; **noch keine implementierte Software**.
**Ausdrücklich später festzulegen:** Konkrete KI-Algorithmen, Verhaltens-/Handlungsprioritäten, Patrouillenrouten, Dialog-/Kampfautomatik, Aktionswerte, Timings, Standardprofile, API/DB, Oberflächen, Rechenlimits und MVP-Reihenfolge.
**Nächste grundlegende Featurefrage:** **06.5 – NPC-Gespräche und soziale Interaktionen** als eigener optionaler Strukturbaustein, nicht erneute Wahl der Steuerungsmodi.
**Bezüge:** [06.1 C NPC-Vorlagen und eigene Instanzen](NPC-WORKSHOP-06.1.md) · [06.2 C Lebenszyklus/Aktivität/Szenentransfer](NPC-WORKSHOP-06.2.md) · [06.3 C Gruppen/Fraktionen/Relationen](NPC-WORKSHOP-06.3.md) · [02.54 C bereits beschlossene NPC-Steuerung, 02.55 Wachsamkeit, 02.53–02.63 Wahrnehmung, Kommunikation, Wissen und Tarnung, 02.13/02.48 Nodes/Alarm, 02.19 inaktive Szenen und 02.25 Defaults/Overrides](KARTEN-WORKSHOP.md) · [02.99 manuelle/SL-bestätigte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [03.2 Steuerrechte](CHARAKTER-WORKSHOP-03.2.md) · [03.7 RulePacks](CHARAKTER-WORKSHOP-03.7.md) · [03.8 Status/Effekte](CHARAKTER-WORKSHOP-03.8.md) · [04.1–04.5 Bewegung](BEWEGUNG-WORKSHOP-04.1.md) · [05.1–05.3 Würfel und Wurfketten](WUERFEL-WORKSHOP-05.3.md) · [Planungsstandard](PLANUNGSSTANDARD.md).

## 1. Verbindlicher Grundbeschluss

**Option C:** AdventureShift bietet **optionale, versionierte, regelwerksneutrale NPC-Handlungs-/Verhaltensprofile**, die ausschließlich tatsächlich unterstützte, typisierte Auslöser, Bedingungen, zugelassene Aktionsreferenzen und begrenzte Zustandsübergänge verbinden. Profile sind innerhalb zulässiger Kampagnen-, RulePack-, NPC-Vorlagen-, Gruppen-, Szenen- und Instanzgrenzen wiederverwendbar. Keine Verpflichtung zu künstlicher Intelligenz, vordefinierten Fantasyaktionen, frei ausführbarem Regelcode oder globaler Simulation.

**Unverändert aus 02.54 C:** Ob und durch wen ein geeigneter NPC handelt, bestimmen **manuelle SL-Steuerung**, **SL-Bestätigung eines Vorschlags** oder **automatisches servergeprüftes Verhalten** nach der geltenden echten Policy. 06.4 spezifiziert die **referenzierbaren Handlungstypen und die Abfolge von Trigger, Vorschlag, Prüfung und realem Fachaktionscommit**. Es ändert weder die Steuerungswahl noch die Geheimnis- und NPC-Wissensgrenzen.

**Nicht gewählt:** A – ausschließlich handgesteuerte NPCs ohne verlässliches allgemeines Handlungsmodell als Plattformkern; B – fest programmiertes universelles Standardset für Angriff, Flucht, Patrouille usw. Freie manuelle NPCs und Voicechat-first-Kampagnen bleiben vollständig möglich.

## 2. Fachobjekte und Schnittstellen

1. **NpcActionDefinition / ActionCapabilityRef (Arbeitsnamen):** Versionierte, deklarative und typisierte Verweise auf **bereits fachlich zulässige** Aktionstypen wie 04-Bewegung, 02-Node-/Sensor-/Alarm- und 02.56-Nachrichtenaktion, 05-Wurf/Check, 01-Item-/Inventaraktion, 03-Status/Effekt sowie spätere 07-Kampf-/06.5-Dialogaktionen. Voraussetzung, Eingabe-/Ausgabetyp, Ziel-/Quell-/Szenen-/Turn-/Ressourcen- und Controllerrechte sind fachlich validierbar. Eine Aktionsdefinition ist **keine** echte Handlung.
2. **NpcBehaviorProfile / BehaviorProfileVersion:** Berechtigt erstellte, bearbeitete und veröffentlicht geprüfte Kombination erlaubter **Trigger-/Bedingungs-/Aktionsreferenzen**. Sichere regel-/typgeprüfte Bedingungstypen können beispielsweise auf einen wirklich wahrgenommenen Reiz, Status, aktuelle gültige Ziele, bestehende Beziehung oder Turnkontext Bezug nehmen; welche Bedingungen und Aktionsarten in einer konkreten ersten Implementierung vorliegen, wird später entschieden. Keine beliebigen Nutzer-Skripte, generative KI-Entscheidungen oder unendliche Eventrekursion.
3. **NpcBehaviorAssignment:** Echte 06.1-NPC-Instanzen beziehen ihre wirksame versionierte Verhaltenspolicy nach 02.25 und 02.54 aus erlaubten Kampagnen-/RulePack-/Vorlagen-/Gruppen-/Szenen- und ausdrücklich gekennzeichneten Einzel-Ausnahmen. Vorlagenedit/Publikation verändern bestehende Instanzen **nicht still**; kontrollierte Übernahme nur über passende freigegebene Versionsänderung.
4. **NpcBehaviorRuntimeState:** Je tatsächlich aktivierter NPC-Instanz nur benötigte Zustandsreferenzen wie wirksame Profilversion, Ablauf-/Event- oder Proposal-IDs, aktuelle Revision und ggf. echte zulässige Timer/Pausen. **Nicht identisch** mit NPC-Lebenszyklus 06.2, Wachsamkeitszustand 02.55, eigenem Gedächtnis 02.61, Turnengine oder Objekt-/Tokenidentität. Serverneustart/Reconnect dürfen abgelaufene Trigger nicht erneut wirksam machen.
5. **BehaviorTriggerEvent:** Ursächliches, wirklich gültiges 02-/03-/04-/05-/06-/Quest-/Turn-/Node-/Sensor-/SL-Ereignis mit stabiler Quell- und Korrelations-ID. Browser dürfen keine intern gültige NPC-Wahrnehmung oder ein Alarm-/Node-Ereignis vortäuschen. Eine bloße Preview, Animation, Chatnachricht oder lokale Geräuscheinblendung löst keine echte NPC-Automatik aus.
6. **NPC-Wissen als ausdrücklich begrenzter Kontext:** Gültige 02.53–02.63-Perception-/Memory-/Trust-/Verständnis-/Wiedererkennungs- und 06.3-Beziehungsdaten dürfen die Handlungsprüfung beeinflussen. Ein NPC kennt **nicht** automatisch die wahre Identität einer getarnten Figur, geheime Räume, nicht wahrgenommene Gegner, andere NPC-Erinnerungen oder die perfekte Spielerposition, nur weil der VPS diese Daten besitzt. Eine wahrgenommene ungefähre Richtung ist keine genaue Angriffserlaubnis.
7. **NpcActionIntent / ActionProposal:** Aus real zulässigen Ereignissen und Bedingungen abgeleiteter, identifizierbarer, zunächst **weltwirkungsfreier** Handlungswunsch mit NPC-ID, konkreter unterstützter ActionDefinition, erlaubten Zielen, Ursprung, Profilversion, Context-/Revision-/Controlgeneration und Sichtbarkeitsklasse. Er würfelt nicht, bewegt niemanden, bucht keine Ressourcen, gibt kein Item aus und erzeugt keine Weltzustandsänderung oder NPC-Gedächtniswirkung.
8. **Manuell / SL-bestätigt / automatisch ausschließlich gemäß 02.54 C:** In manuell gesteuerten Kampagnen handelt der NPC nur aufgrund einer aktuellen berechtigten menschlichen Aktion, optionale Hinweise bleiben unverbindlich. Im Bestätigungsmodus kann eine gültige Handlung zur Zustimmung/Ablehnung oder ausdrücklich neu validierten Änderung vorgelegt werden. Im automatischen Modus darf nur **die ausdrücklich zugelassene** Fachaktion nach vollständiger VPS-Prüfung tatsächlich ausgeführt werden. Fehlender/abwesender SL gibt niemals eine automatische Ersatzfreigabe.
9. **NpcActionExecution und echte Fachoperation:** Ein berechtigter Intent darf ausschließlich den **bestehenden** 01-/02-/03-/04-/05-/06- und später 07-Serveraktionspfad nutzen. Vor dem echten Commit prüft der VPS erneut die aktuelle NPC-Identität, Aktivität 06.2, Controller-/Status-/Regelrechte 03.2/03.8, aktuelles Ziel, Szene/Fog, Turn/Ressourcen, erlaubten Aktionsport und geltende Auslösepolicy. Genehmigung, Wurfanzeige, Storytext oder lokale NPC-Animation sind keine echte WorldAction.
10. **Konkurrenz und Steuerungsübernahme:** Wenn die SL einen automatisch gesteuerten NPC übernimmt, ein Kontrollzauber wirkt, eine Szene wechselt oder mehrere Trigger/SL-Tabs konkurrieren, benötigen Vorgang und NPC stabile Revisions-/Control-/Turn-/Operation-IDs. Veraltete Pending-Aktionen werden vor Ausführung gesperrt, konfliktfeste neue Entscheidungen sind möglich. Keine gleichzeitig konkurrierenden gültigen Bewegungen/Angriffe, keine doppelt verbuchten Ressourcen oder freie NPC-Züge.
11. **Begrenzung von Verhalten und Triggerfolgen:** Kombinierbare Ereignisse dürfen nicht zu unbegrenzten Node-/Spawn-/NPC-/Würfel-/Alarm-/Status-Schleifen führen. Endliche technische Grenzen, Deduplikation und sichere Fehler-/Stoppzustände sind **grundsätzlich Pflicht**, während genaue Budgets, Tick-/Timer-Intervalle, KI-Prioritäten, Aktionsauswahl und Konfliktstrategien später festgelegt werden. Kein Pflicht-Tick für jeden NPC im Hintergrund.
12. **Inaktive Szenen und Ruhen:** 02.19 und 06.2 legen getrennt fest, wann ein NPC überhaupt aktiv handeln darf. Ein ruhender, transferierter, archivierter oder in inaktiver Szene befindlicher NPC startet **nicht** ungefragt vollständige Dauer-KI; nur ausdrücklich erlaubt begrenzte Ausnahmen für Node-/Quest-/Timerregeln. Echtzeit und Spielrunden bleiben fachlich getrennte Zeitarten.
13. **Sicht, Gruppen und Nachrichtenaustausch:** Gruppenzugehörigkeit aus 06.3 darf erlaubte Bedingungen/Zielgruppen auswählen, **nicht** ohne eigene gültige 02.56–02.60-Kommunikation Informationen an alle Fraktionsmitglieder kopieren. 02.48-Alarme, 04.3-Gruppenbewegungen, gemeinsame Ressourcen und 07-Kampfaktionen benötigen eigene aktuelle Rechte und WorldCommits. Getrennte Rechte für tatsächliche Benutzer-/Charakter-/NPC-Steuerung bleiben bindend.
14. **Secret- und Multi-Browser-Schutz:** Unberechtigte Spieler erhalten weder unsichtbare NPCs noch geheime Handlungsabsichten, gewählte Ziele, interne Pendingqueues, Fraktions-/NPC-Profilinhalte, Nodeursachen, Animationen, Log-/API-/Socket-/Asset- und Cache-/Reconnect-Spuren. SL-Audit/Diagnose und Spielerinformationen werden getrennt nach aktueller ACL projiziert.
15. **Persistenz, Versionen und Bibliothek:** Gültige Profil-/RulePackversionen, aktive echte Zustände und einmal ausgeführte Action-IDs bleiben nachvollziehbar. Neu publizierte Profile überschreiben nicht automatisch laufende NPCs; 02.25-Schutz mit Vorschau und gekennzeichneten individuellen Ausnahmen bleibt verbindlich. Unbekannte Operatoren, unzulässige Actionports, fehlende Versionen oder Lizenzen erzeugen Blocker, keine erfundenen automatischen Aktionen.

## 3. Konzeptioneller Umsetzungsplan

1. Auf 06.1-NpcInstance/NpcTemplateVersion und 06.2-Lebenszyklus dieselben 02.54-Control- und 02.25-Overrideprüfungen aufsetzen, ohne zweiten NPC-/Turn-/Würfelmotor.
2. Versionierte, sicher typisierte Profildefinitionen mit begrenzten Bedingungen/Triggern und Referenzen auf tatsächlich zulässige Fachaktionsklassen entwerfen. Keine frei ausführbaren RulePack-Skripte.
3. Pro NPC ausschließlich legitim erworbene Wahrnehmung, Verständnis, Erinnerung, Beziehungen und Status-/Szenen-/Turninformationen in Auslöser-/Bedingungsprüfungen verwenden; kein heimliches VPS-Allwissen.
4. Weltwirkungsfreie ActionIntents/SL-Proposals mit Pending/Approval/Abbruch und action-spezifischem Commit getrennt persistieren. Vor echtem VPS-Commit immer aktuelle Rechte/Status/Turn/Version/Quellereignis erneut prüfen.
5. Einen deduplizierten, gegen Konkurrenz/Loops begrenzten fachlichen Actionpfad zu 01-Inventar, 02-Nodes/Alarm, 03-Status/Controller, 04-Bewegung, 05-Würfel und später 07-Kampf einplanen.
6. Geheimnisse und aktuell wirksame Empfängerrechte über API, WebSocket, Logs, Asset-Vorladen, Join/Reconnect und Browser-Animationen prüfen. Regel-/Profiländerungen nur mit 02.25-Vorschau/Bestands-/Ausnahmeschutz übernehmen.
7. Konkrete Behavior-Kataloge, Prioritäten, NPC-KI-Auswahl, Patrouillen- und Kampf-/Dialogalgorithmen, Fristen, Werte, technische APIs/DB und MVP bewusst **erst** bei Detailplanung festlegen. Nächster grundlegender Schnitt: 06.5 Dialog-/Interaktionszustände.

## 4. Fachliche Abnahmetests

| Fall | Erwartung |
| --- | --- |
| Manuell gespielte Händlerin | Keine eigenständige NPC-Aktion trotz vorhandener Profildefinition |
| Regelautomatisch aktive Wache | Ausschließlich valide, tatsächlich implementierte und aktuell erlaubte Aktionen |
| SL-bestätigter Untersuchungsvorschlag | Pending hat keine Bewegung, keinen RNG, keine Item-/Alarm-/Weltwirkung |
| SL lehnt ab oder Zustimmung veraltet | Kein heimlicher NPC-Commit; erneute aktuelle Prüfung |
| SL übernimmt zuvor automatischen Gegner | Alte Automatik darf nicht parallel einen zweiten Move/Angriff ausführen |
| Wache kennt nur grobe Geräuschrichtung | Keine automatisch exakte verborgene Spielerposition als Zielwissen |
| Zwei Wachen derselben Fraktion | Individuelles Wissen und Kontrolle bleiben getrennt |
| Gruppensignal soll Alarm auslösen | Nur gesonderte zulässige 02.48-/02.56-Ereignisse/Empfänger statt Fraktionstelepathie |
| Zwei Browser, doppeltes Sensor-/Nodeevent, Reconnect | Gleiche ActionOperation höchstens einmal wirksam |
| NPC in inaktiver Szene | Keine unbeschlossene permanente KI-/Patrouillen-Simulation |
| Veraltetes Profil, unzulässige Bedingung oder fehlender Actiontyp | Kontrollierte Verweigerung ohne Weltwirkung |
| Fehlende Turn-/Ressourcen-/Kollisionsrechte | Eigener 04-/07-Validator blockiert die Aktion |
| Profil erzeugt Triggerloop | Begrenzter sicherer Stopp, keine unendliche Aktion-/Wurfkaskade |
| Versteckter NPC plant Angriff | Kein Spieler-Event/Log/Queue/Preload über geheime NPC-Existenz |
| Browser fälscht NPC-interne Wahrnehmung | Kein echter berechtigter Trigger, RNG- oder WorldCommit |
| Neues veröffentlichtes Verhaltensprofil | Bestehende NPC-Zustände werden nicht still überschrieben |
| Fehler bei einem echten ActionStep | Kein fingierter Würfelpatzer/Erfolg und keine bereits geschehene Weltwirkung doppelt |
| Voicechat-first-Kampagne ohne NPC-Automatik | Normal per SL steuerbar ohne KI-Pflicht |

## 5. Beschlussgrenze und nächste Frage

**06.4 C verbindlich:** Versionierte optionale NPC-Handlungs-/Verhaltensprofile mit typisierten ActionCapabilities, echten berechtigten Events/Wissens-/Statusbedingungen, weltwirkungsfreien Vorschlägen und **separaten, erneut geprüften action-spezifischen VPS-WorldCommits**. Die 02.54-C-Wege manuell/SL-bestätigt/automatisch werden nicht neu definiert. Kein Server-Allwissen als NPC-Wissen, keine generativen Skripte, kein automatischer gemeinsamer Fraktionsalarm, keine ungeschützte KI-Schleife.

**Konkrete KI, Prioritäten, Patrouillen-/Kampf-/Dialogroutinen, Aktionswerte und technische UI/API/DB/MVP-Entscheidungen werden wie vom Nutzer gewünscht erst später festgelegt.** Bisher ausschließlich Planung, nicht Softwareimplementierung.

### 06.5 – Wie sollen NPC-Gespräche und soziale Interaktionen modelliert werden?

**Beispiel:** Ein Spieler spricht frei mit einer SL-gesteuerten Händlerin. Ein Sicherheitsroboter kann optional Antworten anbieten und einen passenden Code/Skill-Check anfordern. Ein Wachmann kann eine Information ausschließlich aufgrund seines tatsächlichen NPC-Wissens preisgeben.

- **A – Nur freie Gespräche/SL-Notizen:** Gespräche per Voicechat/Freitext ohne eigenständige systemseitige Dialog-/Interaktionszustände; bestehende 02-Kommunikations-/Node-Funktionen bleiben erhalten.
- **B – Einheitlicher fest programmierter Dialogbaum:** Standarddialogoptionen und Gesprächsabläufe im Plattformkern für alle NPCs und Spielsysteme, nur begrenzte Erweiterbarkeit; freie Gespräche laufen außerhalb dieser Logik.
- **C – Optionale typisierte Dialog-/Interaktionsmodelle (Empfehlung):** Freie SL-/Voicechat-Gespräche bleiben vollständig möglich. Zusätzlich können passende RulePacks/NPC-Vorlagen **versionierte, berechtigte Gespräche und konkrete Interaktionssitzungen** samt zulässigen Teilnehmern, Antwort-/SL-Freigabe-/Check-/Node-/Quest- und Resultatbezügen unterstützen. Storytext und Antwortvorschau ändern keine Spielwelt; dazu braucht es einen eigenen tatsächlichen autorisierten WorldCommit. Bestehende 02.56–02.63-Sprach-/Wissens-/Vertrauensregeln, 01-Code-/Itemrechte sowie 02.105-Chat An/Aus bleiben getrennt. Keine Pflicht für generative Dialog-KI, Transkription oder bestimmte Dialogtexte; genaue Gesprächs-/Antwortoptionen und UI später.

