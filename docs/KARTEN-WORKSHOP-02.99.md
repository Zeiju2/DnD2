# AdventureShift – Karten-Workshop: Beschluss 02.99 C

**Stand:** 13.10.2026 – Beschluss 02.99 C; Folgeentscheidungen 02.100 C bis 02.103 C beschlossen; nächste offene Frage 02.104  
**Status:** Verbindlicher fachlicher Beschluss und konzeptioneller Umsetzungs-/Testplan. Noch keine implementierte Software, freigegebene API, endgültige Datenbankstruktur, globale Einstellungsführung oder MVP-Priorisierung.  
**Bezüge:** [Karten-Hauptworkshop, 02.25 Kampagnenstandards/Ausnahmen](KARTEN-WORKSHOP.md) · [02.54 NPC-Steuerung](KARTEN-WORKSHOP.md) · [02.59 gültige Codeeingabe](KARTEN-WORKSHOP.md) · [02.65–02.67 Sicht-/Wurfaudit](KARTEN-WORKSHOP.md) · [02.77–02.82 Node-Ereignisse/Graphversionen](KARTEN-WORKSHOP-02.82.md) · [02.83/02.84 Szenenänderungen](KARTEN-WORKSHOP-02.84.md) · [02.92 Questbedingungen](KARTEN-WORKSHOP-02.92.md) · [02.93/02.94 optionaler Generator und Spielnotizen](KARTEN-WORKSHOP-02.94.md) · [02.95–02.97 Notizschutz](KARTEN-WORKSHOP-02.97.md) · [02.98 C Spielerpins und manuell/assistiert/automatisch je Kampagne](KARTEN-WORKSHOP-02.98.md).

## 1. Verbindliche Entscheidung 02.99 – C: Konfigurierbare manuelle Ergebnisse mit Freigabe

**Vom Projektinhaber ausdrücklich gewählt: Variante C.** Nach einer Verhandlung, einem Rätsel oder einer Gruppendiskussion im Voicechat darf die Software das besprochene Ergebnis **nicht schon wegen einer mündlichen Aussage, Textchatmeldung, privaten Notiz, Kartenmarkierung oder eines bloßen Änderungsantrags** als Spielwelt-Wahrheit verbuchen. Erst eine **bewusste, aktuell berechtigte manuelle UI-Aktion**, gegebenenfalls nach der konfigurierten Bestätigung durch Spielleitung oder eine andere ausdrücklich berechtigte Rolle, darf eine **serverautoritativ geprüfte** Änderung auslösen. Bereits nach 02.98 freigegebene echte, regelautomatische Serverereignisse bleiben davon unabhängig.

Die Spielleitung soll nach Kampagnenstandard und zulässigen **markierten Ausnahmen aus 02.25** je dafür geeigneter **Kampagne, Regelprofil, Ereignisart, Zieltyp, Quest/NPC/Objekt, Szene und Rolle** einstellen können, **wer einen Änderungsantrag stellen**, **wer eine bestimmte Spielzustandsänderung direkt erfassen** und **wer einen Antrag genehmigen oder ablehnen** darf. Eine Aktion ohne Genehmigungsbedarf erfordert weiterhin gültige Schreibberechtigung und alle Sachprüfungen; eine Genehmigung ist keine Umgehung tatsächlicher Regeln und Geheimnisschutzkontrollen. Nicht jede Featureklasse muss alle Modi oder dieselben Rollen anbieten.

**Beispiele (nur wenn die jeweilige Kampagnenpolicy diese Ergebnistypen erlaubt):**
- Ein Spieler sagt im Voicechat, der Wachmann sei überzeugt. Er kann gegebenenfalls den erlaubten Antrag „Wachmann ist kooperativ“ stellen. Erst eine berechtigte SL-Freigabe oder eine für diesen NPC ausdrücklich zugelassene direkte Eintragung aktualisiert den autoritativen NPC-Zustand.
- Ein Rätsel wurde gemeinsam gelöst. Ein berechtigter Antrag darf den freigegebenen Questfortschritt vorschlagen; die Prüfung des tatsächlichen Türcodes an einem echten Terminal oder ein echtes Inventarobjekt wird dadurch **nicht simuliert oder übersprungen**.
- Nach manuell geleitetem Kampf möchte die SL eine Ressource belasten oder eine Quest abhaken. Der Server prüft nach gewählter Eventart, ob der betroffene Charakter, die Ressource, der Turn und die Voraussetzungen noch aktuell sind. Eine zweite Bestätigung kann nicht ein zweites Mal dieselbe Ressource abbuchen oder Belohnung vergeben.

## 2. Geltungsbereich und Zuständigkeiten

| Befugnis / Operation | Bedeutung und Grenze |
| --- | --- |
| **Antrag erstellen** | Spieler oder SL schlägt einen klar typisierten Effekt mit ausschließlich sichtbaren/erlaubten Zielen vor. **Keine Weltwirkung**. |
| **Antrag einsehen / kommentieren / zurückziehen** | Eigenständige, aktuelle Leserechte; Empfänger und geheime Details werden serverseitig begrenzt. Eine persönliche Notiz wird nicht dadurch freigegeben. |
| **Direkt eintragen** | Für exakt den Ereignistyp und das Ziel autorisierte Person löst die tatsächliche servergeprüfte Aktion ohne zusätzlichen Freigabeschritt aus. Nicht mit „beliebige Spielweltfelder bearbeiten“ verwechseln. |
| **Bestätigen / ablehnen** | Nur eine für diese Kombination aus Event, Ziel und Scope aktuell zur Entscheidung berechtigte Person kann einen Antrag behandeln. Bestätigung geht erst durch den **erneuten vollständigen Commit-Check** in echte Wirkung über. |
| **Policy verwalten** | Separates SL-/Kampagnenverwaltungsrecht; nicht automatisch aus dem Recht auf Eintrag, Antrag oder Bestätigung ableiten. |
| **Historie lesen** | Eigener, feldgefilterter Sicht-/Audit-Scope; weder Antragsteller noch Bestätiger erhalten automatisch alle Geheimnis-/Protokolldaten. |

**Rechteermittlung (fachlicher Resolver):** Kampagnen-/Regelprofilstandard → erlaubte Eventklassen/Zieltypen → Szenen-/Objekt-/Quest-/NPC-/Rollen-/Gruppen- und ausdrücklich markierte Ausnahmen → aktuelle Mitgliedschaft/Identität/Owner-/Sicht- und Feature-Modi. Gültigkeit jeder Zwischenebene prüfen; Ausnahmen sind keine pauschale Erlaubnis, echte Sicherheitsinvarianten zu überschreiben. Ein Spieler darf z. B. einen Quest-Antrag stellen, aber ohne eigenes Bestätigungsrecht **nicht seine eigene Bewerbung eigenmächtig freigeben**. Wenn dieselbe Person Antrag und Bestätigung ausführen soll, ist das nur bei **bewusst dafür erteilter Direkt- oder ausdrücklicher Selbstfreigabeberechtigung** zulässig; keine stillschweigende Eskalation.

**Ausschluss:** Niemals „alles, was im Voicechat behauptet wurde“, automatisch verbuchen (Variante B verworfen). Keine obligatorische Mikrofonaufnahme, Sprachüberwachung, Transkription, KI-Auswertung oder Voicechatintegration. Externe Gespräche und freiwillige Freitextnotizen bleiben nutzbar, wenn alle Automatik-/Generatorfunktionen abgeschaltet sind.

## 3. Entwurfsmodell – noch keine endgültige API

Konzeptionelle fachliche Typen: `ManualOutcomePolicy`, `ManualOutcomeEventType`, `ManualOutcomeRequest`, `ManualOutcomeRevision`, `ManualOutcomeDecision`, `ManualOutcomeCommand`, `ManualOutcomePreflight`, `ManualOutcomeCommitReceipt`, `ManualOutcomeAccessProjection`, `ManualOutcomeConflict`, `ManualOutcomeAudit`. Es handelt sich **nicht** um freigegebene Klassen, HTTP-Routen, Tabellen oder feste Feldnamen.

**Benötigte verknüpfte Identitäten/Versionen (als Entwurf):** Kampagne/Regelprofil, Anlass/Eventklasse, Zieltyp und berechtigte Zielreferenz, Szene, Gruppe/Rolle, Antragsteller, Entscheider, wirksame Policyversion, Ziel-/Ressourcen-/Quest-/NPC-Version, ggf. Turngeneration und Graph-/Szenenversion, Antrags-/Revisions-/Entscheidungs-/Operations-/Korrelations-ID, optional Ablaufzeit und expliziter Effektumfang. Subjektive Begründungen sind **Nutzereingaben, kein Beweis eines In-Game-Checks**.

Die Eventtyp-Definition beschränkt mögliche Änderungen auf **fachlich definierte, validierbare Kommandos** (etwa zulässigen Queststatus setzen, freigegebenes NPC-Attribut ändern, festgelegte Ressourcenbewegung buchen, ein Objekt per echtem erlaubten Bedienkommando ändern). Keine generische Feld-Schreib-API für untypisierte beliebige NPC-/Item-/Node-/Fog-/Würfel-/SL-Geheimniszustände und niemals vom Antrag übernommene ausführbare Skripte.

## 4. Lebenszyklus eines manuellen Ergebnisses

1. **Vorschlagen:** UI zeigt nur für diese Rolle/Ansicht erlaubte Ereignisarten und auswählbare sichtbare Ziele. Vorschlag mit beabsichtigter Änderung und optionalem Freitext erzeugen. Ein Antrag ist zunächst **effectfrei**.
2. **Einreichen:** Server prüft aktuelle Berechtigung zum Stellen, erlaubten Typ/Ziel, Policy-/Scopeversion und Eingabevalidität; versieht den Antrag mit stabiler Antrags-ID, Revisionsstand und eindeutigem Status. Antrag ist nicht gleich autoritativer Spielweltzustand.
3. **Prüfen:** Nur aktuell berechtigte Empfänger sehen die minimale zugelassene Vorschau und die erlaubten Datenfelder. Sie können nach Policy genehmigen, ablehnen oder eine Überarbeitung anfordern. Eingaben/Entscheidungen haben individuelle Idempotenz-IDs.
4. **Freigabe/Commit:** Bei Genehmigung wird **im selben kontrollierten Transaktions-/EffectLedger-Pfad** die aktuelle Rechte-, Policy-, Ziel-, Regel-, Szenen-, Turn-, Ressourcen- und Konfliktlage erneut geprüft. Nur bei Erfolg werden ein typisiertes echtes Weltkommando und der dazugehörige Commitbeleg atomar gebucht. Bestehende Event-/Wurf-/Node-Mechanismen werden nicht durch einen Frontend-Status oder Freitext ersetzt.
5. **Abschluss:** Status differenziert zwischen vorgeschlagen, wartend, zurückgegeben, abgelehnt, zurückgezogen, veraltet/abgelaufen, fehlgeschlagen und **einmalig wirksam verbucht**. Benachrichtigungen/Ansichten sind nach Empfängerrechten gefiltert; eine genehmigte, aber fachlich ungültig gewordene Aktion wird **nicht** fälschlich als erfolgreich dargestellt.
6. **Neubewerten:** Ist Ziel, Berechtigung, Policy, Turngeneration oder benötigter Zustand seit Einreichung geändert, **nicht stillschweigend auf altem Snapshot ausführen**. Sicher als veraltet behandeln; neue Prüfung und erforderlichenfalls neue Vorlage/Bestätigung. Genehmigte Anträge nicht als beliebig lange gültige „Blanko-Tickets“ wiederverwenden.

**Direkteingabe** nutzt denselben fachlichen Server-Validierungs-/Transaktionspfad wie ein genehmigter Antrag, aber mit unmittelbarer, ausdrücklich erlaubter Autorenschaft statt vorgeschaltetem Antrag. **Assistenz/Preview** kann helfen, hat vor dem Commit keinerlei Nebenwirkung. Ein Vorschlag kann zurückgezogen oder abgelehnt werden; seine Daten dürfen im separaten geschützten Audit verbleiben, ohne dass jemals eine Quest-/Weltwirkung daraus entsteht.

## 5. Echte Wirkung, Modulgrenzen und technische Sicherheit

- **Prüfung am maßgeblichen Zeitpunkt:** Auth/aktuelle Mitgliedschaft, Kampagnen-/Event-/Zielpolicy, erlaubtes Modul und Betriebsmodus (02.98), Sicht-/Fog-/Wissensrechte, Ressourcenkosten und Besitz, relevanter Spiel-/Objekt-/Turn-/Node-/Graph-/Szenenzustand. SL-Sonderrechte müssen ausdrücklich modelliert und selbst autorisiert sein, nie impliziter API-Bypass.
- **Einmaligkeit und konkurrierende Anträge:** Persistente Antrags-/Entscheidungs-/Operation-IDs; transaktionale Compare-and-Set-Versionen und EffectLedger-/Event-Korrelation; zwei nahezu gleichzeitige Genehmigungen derselben Aktion dürfen nur **ein** echtes Ergebnis liefern. Bei Kollision unabhängige gültige Kommandos neu validieren, konfliktierende Anträge zurückweisen oder ausdrücklich neu vorlegen. Kein blindes Last-Writer-Wins.
- **Mehrteilige Ergebnisse:** Bei „Quest abschließen plus Belohnung“ jedes betroffene echte Ziel und die zusammengesetzte Transaktion ausdrücklich prüfen; wenn Bündel unterstützt werden, atomar oder sicher kompensierbar mit einer eindeutigen Korrelationsgruppe. Nicht mit automatisch doppelt ausgelösten Quest-/Loot-/Sensor-/Node-Folgen vermengen. Der genaue Umfang zusammengesetzter UI-Buchungen bleibt Implementationsthema.
- **Event-/Node-Auswirkungen:** Eine manuelle Statusänderung löst weitere Node-/Timer-/Alarm-/Tür-/Next-Player-Folgen nur aus, wenn **der ausdrücklich typisierte und in diesem Modus aktive, freigegebene Eventpfad** das vorsieht. Keine unbeabsichtigten Autotrigger aus Notiz, Label, Antrag, Vorschau oder Ablehnung. Dedup, Schleifenschutz, korrekter Branch-/Graphversionsbezug gemäß 02.77–02.82.
- **Kein Würfelumschreiben:** Historische echte Würfe, verborgene Wahrnehmungschecks und ihre RNG-Werte bleiben nach 02.65–02.67 unverändert. Manuelle narrative Feststellung/SL-Override, falls als eigener Aktionstyp ausdrücklich erlaubt, ersetzt **nicht** den Nachweis einer tatsächlich stattgefundenen Würfelprobe.
- **Kein Code-/Inventar-Bypass:** Der Text „Türcode 1234“ ist kein gültiges Terminalevent. Offiziell geführte Quests, manuelle NPC-Einträge, private Notizen und Spieler-Kartenmarker dürfen keine reale Keycard, Ressource, geheime NPC-Identität oder berechtigte Tür-/Schalterbedienung vortäuschen.
- **Moduswechsel während offener Anträge:** Off/manuell/assistiert/automatisch nach 02.98 unterwirft offene Anträge aktueller Policy und geschützter Bestandsbehandlung. Deaktivierter optionaler Pfad nimmt keine neuen Aktionen an; abgeschaltete Module führen keine bereits wartenden Anträge heimlich aus. Gültige historische, tatsächlich gebuchte Zustände und deren Audit bleiben bestehen.
- **Rollen-/Gruppen-/Zieländerung:** Entzug eines Antrags-/Genehmigungsrechts wirkt vor jeder relevanten Abfrage und beim Commit; ein verschwundener/unveröffentlichter NPC oder ein nicht mehr sichtbares Questziel darf keine geheimen Targetinformationen im Fehlertext preisgeben.
- **Sicht und Datenschutz:** Detailansichten, Warteschlangen, Abzeichen/Zähler, Suche, Realtime-Events, Pushbenachrichtigungen, Exporte, Logs und Browser-Caches nach aktuell erlaubten Empfängern/Feldprojektionen trennen. Kein Leak von geheimen SL-NPCs, künftigen Questschritten, privaten Spieler-Notiztexten, versteckten Anträgen, ursprünglichen geheimen Würfeln oder fremden Spielerberechtigungen.
- **Audit/Korrekturen:** Unveränderlich nachvollziehbare fachliche Belege für Antrag, Änderungen, Entscheidung und echte Transaktion; getrennte technische und sichtbarkeitsgefilterte Spieler-/SL-Historie. Bereits gebuchte Weltaktionen nicht per Löschen der Anfrage rückgängig machen. **02.100 C** hat berechtigte, historisch verknüpfte Korrektur-/Kompensationsereignisse mit Folge-/Abhängigkeitsprüfung und erhaltenem Originalbeleg inzwischen beschlossen. [02.100 C](KARTEN-WORKSHOP-02.100.md).
- **Sicherheitsgrenze:** Authentifizierung, Autorisierung, serverautoritative Zustandsänderungen, Geheimnis-/Fogschutz, Datenintegrität und Event-Einmaligkeit sind unter keinem Kampagnenmodus abschaltbar.

## 6. Konzeptueller Umsetzungsweg (keine Implementierung)

1. **Ereigniskatalog und Policies entwerfen:** Echte, typisierte zulässige Ergebnisänderungen von nur narrativen Angaben trennen; Request/Direct/Approve/Reject/Read/Configure-Rechte mit Defaults und markierten 02.25-Ausnahmen, passende 02.98-Betriebsmodi/Regelmodule.
2. **Einheitliches serverseitiges Preflight/Commit-Gateway planen:** Autoritative Ziel-, Event-, Ressourcen-, Rollen-/Fog-, Turn-/Graphversion-/Szenenprüfung; Preview strikt ohne Auswirkungen. Vorhandene echte Objekt-/Quest-/NPC-/Inventory-/Node-Kommandos anbinden, keine freie Weltzustandspatch-API.
3. **Persistente Anträge und Entscheidungen modellieren:** Eindeutige IDs/Revisionen, geschützte Zustandsmaschine, Policy-/Targetversionsbindung, idempotente Entscheidungen, explizite Ablehnungs-/Veraltungszustände, sicheres Reconnect/Retry.
4. **Minimale rollenbezogene UI-Abläufe vorsehen:** Vorschlag aus zulässigem Kontext, bewusste Eingabe, geschützte Prüfansicht und sichtbare Bestätigung/Fehlermeldung mit freigegebenem Ergebnis. Kein endgültiger Einstellungsassistent oder Menüdesign vor Abschluss aller Featurefragen.
5. **Abhängigkeiten gegenprüfen:** 02.54 NPC manuell/SL/automatisch, 02.59 Codeprüfung, 02.65–02.67 private Würfe, 02.77–02.84 Graph-/Szenenänderung, 02.92 Questbedingungen, 02.93/02.94 vollständig optionaler Generator, 02.95–02.98 Notiz-/Marker-Rechte und Technikschalter.
6. **Tests vor Freigabe definieren:** Zulässige Ereignisklassen, jede Rollen-/Antrags-/Genehmigungskombination, geheime Daten, doppelte Freigaben, konkurrierende Ressourcen, veraltete Ziele, Policy-/Moduswechsel, Reconnect, Node-/Turn-/Ressourcen-Einmaligkeit und abgewiesene manipulierte Clientanträge.

## 7. Fachliche Abnahmetests

| Fall | Erwartetes Ergebnis |
| --- | --- |
| Spieler sagt „Wachmann überzeugt“ im Voicechat | Kein NPC-Statuswechsel allein durch Gespräch; kein Voice-Mithören nötig |
| Spieler stellt berechtigten Vorschlag für sichtbaren NPC | Antrag wird gespeichert, echter NPC bleibt bis zum gültigen Commit unverändert |
| Spieler darf nur Antrag stellen, nicht freigeben | Selbstbestätigung/Direktänderung wird serverseitig abgewiesen |
| Rolle erhält für diese NPC-Klasse ausdrücklich Direktrecht | Gültige manuelle Aktion führt nach Preflight genau einmal zur autoritativen Änderung |
| Richtiger Entscheider genehmigt ein gültiges Questziel | Einmaliger transaktionaler Fortschritt; zulässige separate Folgeeffekte nur nach Regel-Eventpolicy |
| Empfänger lehnt ab oder fordert Überarbeitung | Kein Quest-, NPC-, Item-, Node- oder Ressourcen-Effekt |
| Zwei berechtigte Personen genehmigen denselben Antrag gleichzeitig | Maximal ein Commit und ein Effekt; beide Antworten konsistent |
| Client wiederholt Antrag oder Entscheidung nach Reconnect | Wiederholungs-/Operations-IDs erzeugen keine Doppelbuchung |
| Ziel wurde seit Antrag gelöscht oder auf verborgen geändert | Antrag kann nicht auf veraltetes/geheimes Ziel committed werden; Fehler verrät keine Hidden-IDs |
| Antragsteller verliert Gruppenrolle, bevor SL genehmigt | Aktuelle Policy wird erneut ausgewertet; nicht unkontrolliert mit Altberechtigung wirksam |
| Entscheider verliert Genehmigungsrecht kurz vor Klick | Commit wird verweigert |
| Spieler versucht per Request freie Ressourcen/Belohnungen zu setzen | Nicht erlaubte Felder/Eventtypen oder unzureichende Ressourcen-/Ownerrechte werden abgewiesen |
| Manuelles Ergebnis kollidiert mit aktuellem Zug-/Node-/Questzustand | Sicheres Veralten/Neuprüfen; keine doppelte Folgereaktion |
| Automatikmodul wird ausgeschaltet, Antrag wartet noch | Kein heimlicher späterer Commit; bestehende legitime Welt- und Auditdaten bleiben |
| Private Notiz oder geteilte Spielerpin behauptet „Quest gelöst“ | Keine Weltwirkung und keine automatische Antragstellung/Quelle privater Details |
| SL ist in einer manuellen Kampagne ohne Missionsgenerator | Zulässige echte Quest-/NPC-/Objektstatusänderung nach aktueller manuell konfigurierter Policy weiterhin möglich |
| Antrag auf geheimen NPC wird unberechtigt abgefragt | Keine NPC-Namen, Koordinaten, Zähler, Snippets, Benachrichtigungs- oder Cache-Lecks |
| SL bestätigt falschen alten Code statt echter Terminaleingabe | Kein echter Terminal-Codecheck aus gesprochenem Text oder Antragskommentar |
| Bereits protokollierter geheimer Wurf steht im Kontext | Keine Manipulation/Offenlegung des ursprünglichen RNG-Ergebnisses |
| Manipulierter Browser meldet einen Antrag als genehmigt | Kein Effekt ohne echte serverseitige Authorisierung, Zustand-/Versionprüfung und Commit |

## 8. Grenze dieses Beschlusses und nächste offene Frage

**Festgelegt:** Konfigurierbare manuelle Änderungsanträge, getrennte Direkt-/Entscheidungsrechte, serverseitige echte Zustandsübernahme erst nach gültiger UI-Aktion und ggf. Bestätigung, 02.25-Defaults/Ausnahmen sowie alle 02.98-Modus-/Voicechat-first-/Geheimnisgarantien. **Nicht festgelegt:** Fertige UI, finale Datenbank/Protokolle, genaue Gesamtliste aller Eventtypen und Modi, globaler Einstellungsassistent oder MVP-Rangfolge. Ein eventuelles KI-/Voice-Modul ist nicht vorausgesetzt oder genehmigt.

## Archivierte Folgefrage 02.100 – inzwischen als C beschlossen

**Beispiel:** Die Gruppe beschließt im Voicechat, dass ein Wachmann befreundet ist. Eine berechtigte Person übernimmt dies nach 02.99 C in den offiziellen NPC-Zustand. Kurz danach stellt die SL fest, dass das Ergebnis falsch eingetragen wurde oder eine Ressource versehentlich doppelt belastet zu werden droht. **Wie darf ein bereits wirksam gebuchter manueller Spielweltzustand korrigiert werden?**

- **A – Keine Korrektur nach Commit:** Einmal tatsächlich gebuchte manuelle Entscheidungen sind grundsätzlich endgültig; zukünftige Spielaktionen können natürlich neue Situationen schaffen, aber kein gesondertes Korrekturverfahren.
- **B – Direktes Überschreiben ohne Historie:** Wer irgendwann den Zustand bearbeiten durfte, kann frühere NPC-/Quest-/Ressourcenwerte rückwirkend ohne nachvollziehbaren Änderungsbeleg überschreiben; weitere Effekte werden nicht geprüft.
- **C – Berechtigte, protokollierte Korrektur mit Folgeprüfungen (Empfehlung):** Kampagnen-/Ereignis-/Rollen-/Zielpolicy bestimmt, wer eine **explizite Korrektur anfordern, freigeben und ausführen** darf. Statt historischer Löschung/heimlichem Rollback wird nach Vorschau/aktueller Rechte-, Versions-, Ressourcen- und Abhängigkeitsprüfung ein **neuer nachvollziehbarer Korrektur-/Kompensationsvorgang** gebucht. Bereits echte Würfe, ausgelöste Nodes/Alarme, anderweitig verbrauchte Ressourcen und bekannt gewordene Geheimnisse werden nicht magisch ungeschehen gemacht; Folgen müssen separat und sicher behandelt werden. Details erst nach 02.100-Entscheidung.

**Aktueller Fortgang:** [02.100 C](KARTEN-WORKSHOP-02.100.md) ist mit neuen, nachvollziehbaren Korrektur-/Kompensationsevents, getrennten Freigaberechten, tatsächlichem Abhängigkeitsplan und erhaltenen historischen Ursprungsbelegen beschlossen. **02.101 C** regelt nun nach echten Rechten gefilterte Korrekturmitteilungen [Detail](KARTEN-WORKSHOP-02.101.md); **02.102 C** hat schaltbare bewusste Lesebestätigungen nur für aktuell berechtigte wichtige Korrekturhinweise beschlossen [Detail](KARTEN-WORKSHOP-02.102.md). **02.103 C** hat optionale, aktuell berechtigte Erinnerung/Eskalation für offene 02.102-Quittierungen ohne globale Spielblockade beschlossen [Detail](KARTEN-WORKSHOP-02.103.md). **02.104** behandelt getrennte rechtmäßige Freistellung/Schließung unlösbarer Anforderungen.
