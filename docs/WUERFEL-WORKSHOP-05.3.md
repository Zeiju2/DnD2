# AdventureShift – Würfel-Workshop: Beschluss 05.3 C – sichere optionale Würfelketten

**Stand:** 17.10.2026. **05.3 C verbindlich beschlossen.** Dies ist ein **Fach- und Umsetzungsplan, keine Implementierung**.
**Ausdrücklicher Zusatz des Projektinhabers:** Die **konkreten Würfelmechaniken** – beispielsweise Neuwurfbedingungen, zusätzliche Würfel, Explosions-/Sonderwürfel, Keep/Drop und konkrete Grenzen – werden **erst in der späteren detaillierten Würfel-Planung** festgelegt. Jetzt nur die architekturtragende Grundstruktur.
**Status:** Block 05 für die Grundstrukturrunde abgeschlossen; nächster Hauptblock **06 NPCs/Gegner**, Frage **06.1**.
**Verbindliche Vorentscheidungen:** [05.1 Würfelmodelle und echte VPS-RollRecords](WUERFEL-WORKSHOP-05.1.md) · [05.2 manuelle, SL-bestätigte und automatische Auslöser](WUERFEL-WORKSHOP-05.2.md) · [02.63–02.67 aktive Checks, Adv/Disadv, vollständige Geheimwahrnehmung, Sichtbarkeit und Logs](KARTEN-WORKSHOP.md) · [02.77 Check-/Krit-/Fehlerausgänge](KARTEN-WORKSHOP-02.77.md) · [03.7 Regelwerksvorlagen](CHARAKTER-WORKSHOP-03.7.md) · [Planungsstandard](PLANUNGSSTANDARD.md).

## 1. Verbindlicher Grundbeschluss – C

AdventureShift erlaubt, für dazu geeignete RulePacks **optionale, versionierte, datengetriebene und typsichere mehrstufige Wurfvorgänge** zu definieren. Sie können bei entsprechender **später tatsächlich implementierter** Operatorunterstützung etwa bedingte Folgewürfe, wiederholte Würfe, zusätzliche Würfel und Ergebnisverzweigungen darstellen. Jeder **wirklich neue** logische Wurf bleibt ein eigenes, serverseitig gültiges, mit seiner Ursache verbundenes Würfelereignis. Die Reihenfolge, das wirkliche Regelresultat und die eventuellen Weltfolgen müssen sicher getrennt bleiben. Spieler dürfen weiterhin ohne Sequenzen frei würfeln oder eine Partie ganz manuell betreiben.

**Nicht gewählt:** A als ausschließliche Architektur aus unverbundenen Einzelwürfen; B als universell fest eincodierte Liste weniger Würfelketten. **Keine freie Ausführung** von JavaScript, SQL oder beliebigem Regelcode; **keine unendlichen Würfel-/Nodeketten**. Das heutige Modell ist **keine** Zusage, schon jede mögliche Regel eines Fremdsystems unterstützen zu können.

## 2. Grundlegendes Modell

1. **RollSequenceDefinition / RuleSequenceVersion (Arbeitsnamen):** Versionierte, publizierte, referenzierte Ablaufdefinition mit zulässigen typisierten Schritt-/Bedingungs-/Ausgangsarten, eindeutigen IDs, passenden 05.1-Dice-/Roll-/Evaluation-Versionen und prüfenbaren Abhängigkeiten. Ein Entwurf oder eine Vorschau ist nie ein echter Wurf.
2. **RollSequenceInstance / StepExecution:** Ein konkreter Ablauf besitzt stabile Root-, Ursprung-/Aktions-, Versions- und Schritt-/Occurrence-IDs, zulässige Figur-/NPC-/Ziel-/Szenen-/Turnbezüge sowie gültige Statusübergänge. Echte Einzelwürfe und ausgeführte Folgeschritte sind eindeutig auf ihre zugrunde liegende Ursache zurückführbar.
3. **Ein eigener 05.1-RollRecord pro echtem neuen logischen Schritt:** Der VPS zieht genau einmal den für diesen neuen Wurf zulässigen Zufall. **Neuwurf ≠ technischer Request-Retry**: Ein bewusst erlaubter Reroll erzeugt einen neuen, korrelierten RollRecord und **überschreibt nicht** den historischen Rohwurf. Die spätere gültige Evaluation entscheidet ausdrücklich, welcher tatsächlich vorhandene Wurf für ein Ergebnis zählt; keine willkürliche Clientauswahl.
4. **Grenze zur bisherigen 02.64-Regel:** Ein Advantage-/Disadvantage-Check mit zwei echten Rohwürfen innerhalb einer **einzigen** logischen Fertigkeitsprobe bleibt nach 02.64 gültig; höher/niedrigerer Wert, passender Skill **einmal**, Vergleich mit numerischem Mindestwurf, Gleichstand Erfolg. 05.3 ändert dies **nicht** in zwei willkürlich freie Proben.
5. **Auslöse- und Rechteprüfung pro Schritt:** 05.2-Policy legt fest, ob ein Folgeschritt manuell, nach geschützter SL-Freigabe oder automatisch beginnen darf. Ein Pending-Approval enthält noch keinen echten Folgewurf. Vor tatsächlicher Ausführung aktuelle Actor-/Controller-/RulePack-/Figuren-/Skill-/Status-/Turn-/Ziel-/Szenenrechte sowie Sicht- und Geheimnisklasse erneut prüfen; stale/abgelehnte Schritte sicher abbrechen oder pausieren.
6. **Bedingungen und Typen:** Nur ausdrücklich unterstützte, korrekt versionierte, validierte Ergebnis- und Bedingungstypen lösen weitere Schritte aus. Technische Fehler sind keine zufälligen Patzer oder gültigen Misserfolge. Die 02.77-Porttypen und typisierten Node-Ergebnisse bleiben verbindlich.
7. **Grenzwerte und Schleifenschutz:** Jeder Regelablauf muss technisch **sicher begrenzbar** sein (Wurfanzahl, Verschachtelungen, Übergänge, Auswertung, Triggerloops, Ressourcen). Konkrete Zahlen/Operatoren später. Idempotente Root-/Step-/Operation-IDs verhindern doppelte Würfe/Kosten durch Mehrbrowser, Reconnect, erneute Nodeevents oder Transport-Retry.
8. **Kosten und Spielweltwirkung getrennt:** Nur passende wirklich bestätigte Fachaktionen können Turn-/Ressourcen-/Kampf-/Inventar-/Tür-/Status-/XP-/Alarmfolgen auslösen. Würfel-Ergebnis, Animation, Freigabe und Simulation sind keine eigenständigen WorldCommits. Zeitpunkt der Kosten bestimmt die spätere Regelmechanik; reine Anträge und Previews verbrauchen nichts. Bereits tatsächlich verbuchte Aktionen bleiben historisch echt; spätere Korrekturen verwenden separate autorisierte Korrekturereignisse.
9. **Sichtbarkeits- und Geheimnisschutz:** Die vier 02.65-Modi wirken auf Root, Schritte, Würfe und deren Logs **empfängerspezifisch**. Zwingend servergeheime unbemerkte Wahrnehmungswürfe dürfen **keine** Spieler-Metadaten hinterlassen (existierende Sequenz/Step, Zahl, Timing, Pending, Socket, Cache, IDs, Animation, Verlauf); 02.66 kann solche geheimen Würfe auch nachträglich **nicht** offenlegen.
10. **Version/Abbruch/Neustart:** Eine laufende Instanz hält ihre ursprüngliche Definition nachvollziehbar, ohne das aktuelle Sicherheitsrecht zu umgehen. Bei geänderten Regeln, entzogenen Rechten, ungültigem Ziel oder Turn-/Szenenwechsel ist ein erneuter aktueller Check nötig. Ein verspäteter Folgewurf darf keine alten Spielzustände ausnutzen. VPS-Neustart/Browser-Reconnect darf bereits gezogene Zufallswerte oder Weltwirkungen nicht neu auslösen.
11. **Integration statt Doppelarchitektur:** Die Sequenz verbindet bestehende 01-Inventar-, 02-Node-/Sensor-/Fog-, 03-Charakter-/RulePack-/Status-, 04-Bewegungs- und später 06-NPC-/07-Kampf-Verträge. Es entsteht kein zweiter versteckter RNG-, Turn-, Node- oder Rechtemotor.

## 3. Konzeptioneller Umsetzungsplan

1. Eine versionierte Sequenzdefinition und laufende Sequenzinstanz mit eindeutigen Step-/Resultat-/Roll-/Ursprungsreferenzen auf den bestehenden 05.1-/05.2-Kern modellieren.
2. Typgeprüfte Übergänge, echte vs. geplante Ausführung und gespeicherte Laufzeit-/Freigabezustände unterscheiden.
3. Bei jedem gültigen Schritt genau den gemeinsamen VPS-RNG-/RollRecord-Pfad verwenden, idempotent mit fachlicher Step-Operation-ID; keine Doppelwürfe.
4. Rechte-/Geheimnis-/Turn-/Kontroll-/Statusprüfungen vor jeder Fortsetzung durchführen und nur gesondert autorisierte WorldActions anschließen.
5. Schutz gegen endlose Folgen, konkurrierende Auslöser, technische Fehler, abgelaufene Freigaben und Versionenkonflikte sowie geschützte per-Empfänger-Projektionen einplanen.
6. **Bewusst erst später** im detaillierten Würfelteil konkretisieren: mögliche Reroll-/Explosion-/Keep-/Drop-/Zusatzoperatoren, Resultat-Kombinationslogik, max. Würfel, Formelsyntax, konkrete RulePacks, Fristen, Zahlen, Bedienung, 3D-Animation, API/DB und MVP-Priorisierung.

## 4. Grundstruktur-Abnahmetests

| Fall | Muss gelten |
| --- | --- |
| Einfacher Wurf ohne Sequenz | Bleibt ohne Kettenmodul zulässig |
| Trefferwurf gefolgt von möglichem Schadenswurf | Eigene echte Roll-IDs nur bei gültiger Regel/Trigger; Ereignisse korreliert |
| Zulässiger Neuwurf | Alter echter Wert unverändert, neuer echter VPS-Wert mit eigenem RollRecord |
| 02.64 Vorteil/Nachteil | Zwei echte Rohwerte einer logischen Probe, Skill einmal, nicht zwei frei erfundene Schritte |
| SL-Freigabe ausstehend oder abgelehnt | Kein vorgezogener Zusatzwurf und keine Wirkung |
| Berechtigung, Figur oder Szene ändert sich | Neuer Schritt erst nach aktueller Prüfung; sonst sicher anhalten |
| Konkurrierende Browser/SL, doppeltes Nodeevent, Reconnect | Kein zusätzlicher RNG-/WorldCommit derselben fachlichen Operation |
| Geheimwahrnehmung als Folge | Weder Existenz noch Step-/Pending-/Rohwert-/Zeitspur für Spieler |
| Typfehler, unbekannter Operator oder unbegrenzte Loop | Kontrolliert blockiert, kein unendlicher Wurf |
| Technischer Fehler in Folgeaktion | Kein spielerischer Patzer/Misserfolg, frühere echte Würfe bleiben erhalten |
| Schadens-/Inventar-/Tür-Folge | Nur über separate Rechte- und Idempotenzprüfung einer echten WorldAction |
| Serverneustart bei laufender Sequenz | Kein erneuter alter Wurf und keine unberechtigte Weiterführung |

## 5. Beschlussgrenze und nächstes Hauptmodul

**05.3 C ist verbindlich auf Grundstrukturebene entschieden.** Die ausdrückliche Vertagung der detaillierten Würfelmechanik bleibt Teil dieses Beschlusses; spätere Detailentscheidungen dürfen die sichere Identitäts-, ACL-, Geheimnis-, RNG- und WorldAction-Trennung nicht unterlaufen.

**Block 05 Würfelsystem ist damit für die aktuelle Grundstrukturrunde vorläufig abgeschlossen. Nächster Block 06: NPCs & Gegner.**

### Nächste Frage 06.1 – Wie werden NPC-/Gegnervorlagen und konkrete NPC-Instanzen modelliert?

**Beispiel:** Der Spielleiter speichert eine Wächtervorlage und platziert sie dreimal. Jede Wache besitzt anschließend eigene Werte, Inventar, Zustände, Tokenposition und ggf. einen anderen Steuerungsmodus.

- **A – Token mit Notizen:** Ein NPC ist im Wesentlichen ein Karten-Token/Objekt mit freien Notizen, ohne eigene versionierte NPC-Instanzstruktur.
- **B – Festes NPC-Schema:** Ein festes plattformweites Gegner-/NPC-Formular bildet alle Instanzen ab, mit nur begrenzter Erweiterbarkeit für unterschiedliche Regelsysteme.
- **C – Versionierte Vorlagen und separate Instanzen (Empfehlung):** Wiederverwendbare, genre-/regelwerksabhängige NPC-Vorlagen und gesonderte konkrete NPCs mit eigener Identität, Werten, Ressourcen, Status, Inventar, Token-, Rechte- und Steuerbezügen. Geeignete typisierte Teile des 03-Charakter-/RulePackmodells dürfen wiederverwendet werden, **ohne NPC-ID, Spielercharakter-ID, Token-ID oder Steam-Konto gleichzusetzen**. Die schon gültigen **02.54-C-Modi** manuell, SL-bestätigt und automatisch bleiben wählbar; keine verpflichtende KI. Genaue Werte und Felder später.

