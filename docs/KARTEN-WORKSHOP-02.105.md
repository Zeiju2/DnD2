# AdventureShift – Karten-Workshop: Beschluss 02.105 C und zusätzlicher optionaler Kampagnenchat

**Stand:** 13.10.2026 – Beschluss 02.105 C einschließlich Chat-An/Aus; Folgeentscheidung 02.106 C zu Chattypen beschlossen, nächste offene Frage 02.111  
**Status:** Verbindlicher Fachbeschluss und konzeptioneller Umsetzungs-/Testplan, **keine implementierte Software**, finale API/Datenbankstruktur, endgültige Chat-UI oder MVP-Priorisierung.  
**Bezüge:** [02.25 Kampagnenstandards/Ausnahmen](KARTEN-WORKSHOP.md) · [02.5 Fog/Sicht, 02.54–02.64 NPC-/Wissensrechte, 02.65–02.67 Würfelaudit](KARTEN-WORKSHOP.md) · [02.98 C Funktionsmodule an/aus und manuell/assistiert/automatisch](KARTEN-WORKSHOP-02.98.md) · [02.99 C Ergebnisübernahme](KARTEN-WORKSHOP-02.99.md) · [02.100 C echte Korrekturen](KARTEN-WORKSHOP-02.100.md) · [02.101 C sichtgeschützte Mitteilungen](KARTEN-WORKSHOP-02.101.md) · [02.102 C persönliche Kenntnisnahme](KARTEN-WORKSHOP-02.102.md) · [02.103 C Erinnerungen/Eskalation](KARTEN-WORKSHOP-02.103.md) · [02.104 C administrativer Erlass/Abschluss](KARTEN-WORKSHOP-02.104.md) · [Featurebereich 11 Kommunikation](FEATURE-WORKSHOP.md).

**Nachfolgender Beschluss 13.4 C:** [Optionale persönliche, echt source- und recipientgeschützte Aufgaben-/Hinweisliste](UI-WORKSHOP-13.4.md) darf 02.105-bestehende bestätigungspflichtige Quellversionen oder nach eigener Policy erneute Notice-/Ackanforderungen nur tatsächlich legitim anzeigen; eine neue SourceNotice, wiederholte persönliche Quittierung oder Chat-/Worldaktion wird durch die Listenansicht niemals erzeugt. V1 ein SL, konkrete Kategorien/Fristen/UI später.


## 1. Verbindlicher Beschluss 02.105 C – Berechtigte kontrollierte Neuanforderung

**Vom Projektinhaber gewählt: Variante C.** Wurde eine persönliche 02.102-Kenntnisnahmeanforderung für einen Spieler nach 02.104 C **rechtmäßig separat administrativ geschlossen/erlassen**, darf eine **aktuell dazu berechtigte Spielleitung oder Verwaltungsrolle** unter gültiger Kampagnen-/Regel-/Notice-/Event-/Ziel-/Rollen-/Gruppen-/Personenpolicy samt **02.25-Defaults und expliziten Ausnahmen** eine **neue eigenständige, versionierte Kenntnisnahmeanforderung** für denselben realen Spieler **bewusst** schaffen, wenn die zugrunde liegende Korrekturmitteilung heute nach **02.101 C für diese Person tatsächlich berechtigt sichtbar** und fachlich noch relevant ist. Es handelt sich **nicht** um das Wiederaufmachen, Umschreiben oder rückwirkende Umdeuten des alten terminalen Belegs.

**Unverhandelbar:** Die frühere 02.104-administrative Schließung bleibt historisch wahr und nach ihren damaligen Rechten protokolliert. Es wird weder daraus ein vermeintliches `Spieler hat damals quittiert` gemacht noch ein früheres echtes Spieler-Ack gelöscht; eine **neue** Erfordernis erhält eine **neue Requirement-ID/Revision mit Ursache, verantwortlichem Actor, gültiger aktueller Notice-Projektion, ausgewählter aktueller Policy und Verweis auf den alten Abschluss**. Erst nach der neuen bewussten 02.102-Quittierung gilt sie persönlich als bestätigt. Keine automatische Wiederöffnungsflut bei Login, Gruppenwechsel, Fog-Aufdeckung oder Reconnect.

**Beispiel:** Die alte NPC-Korrekturmitteilung für Spieler A wurde beim Gruppenaustritt nach 02.104 administrativ als `nicht persönlich quittiert / geschlossen` archiviert. A kehrt Wochen später rechtmäßig zurück, kennt den NPC aktuell und die korrigierte Information ist weiterhin relevant. Eine **heute dafür berechtigte SL** prüft die zulässige **heutige bereinigte Meldung**, entscheidet bewusst über eine **neue** Anforderung und kann diese einzeln freigeben. Der alte Abschluss wird in der getrennt geschützten Historie **nicht überschrieben**; nur das neue Ack darf später als echte persönliche Kenntnisnahme zählen.

## 2. Voraussetzungen und getrennte Rechte

| Voraussetzung / Capability | Fachliche Regel |
| --- | --- |
| **Ursprung** | Tatsächlicher, identifizierbarer 02.100-Korrektur-/Kompensations-Commit, frühere 02.101-Notice und realer nach 02.104 berechtigt administrativ geschlossener Requirementbeleg |
| **Zielperson** | Dieselbe konkrete reale Kampagnen-/Spieleridentität; neue Gruppenmitgliedschaft allein erzeugt keinen anderen Empfänger und keine automatisch geerbte alte Pflicht |
| **Heutige Sicht** | 02.101-Quell-/Ziel-/Fog-/NPC-Identitäts-/Quest-/Secret-/Wurf-/Notiz-/Gruppen-/Rollenrechte erlauben dieser Person heute die **ausdrücklich gewählte aktuell bereinigte Notice-Revision** |
| **Heutige Pflichtpolicy** | Nur wenn 02.102 heute für diese Art wichtiger tatsächlich sichtbarer Notice eine persönliche Kenntnisnahme zulässt/verlangt und keine vorrangige heutige Abschaltung/Ausnahme entgegensteht |
| **Relevanz** | Ursprungskorrektur ist weiterhin sachlich sinnvoll mitzuteilen; bereits aufgehobene/revidierte/irrelevante Informationen nicht ungeprüft als aktuelle Realität vorlegen |
| **Entscheidungsrecht** | `requestNewAcknowledgement` ist eine **separate aktuell geprüfte** SL-/Verwaltungs-Capability und folgt 02.25-Kampagnen-/Regel-/Event-/Ziel-/Szene-/Rollen-/Gruppen-/Personen-Standards |
| **Leserecht der Verwaltung** | Ein administratives Recht zur Neuanforderung gewährt nicht automatisch Leserecht an privaten Spielernotizen, SL-Geheimwürfen oder allen betroffenen verborgenen NPCs |
| **Wirkung** | Eine neue **nichtweltwirksame organisatorische Pflicht** mit eigener Version, nicht die Freigabe einer Quest-/NPC-/Inventar-/Tür-/Node-/Timer-/Turnänderung |

**Gerade nicht erlaubt:** Einer ganzen Gruppe pauschal alle alten geschlossenen Korrekturen erneut schicken; einer inzwischen nicht mehr für NPC/Quest sichtberechtigten Person Details preisgeben; der SL durch `force-reopen` ein persönliches Ack im Namen eines Spielers ausstellen; einen inzwischen fachlich falschen alten NPC-Status ohne neue zulässige Projektion anzeigen.

## 3. Typisierter Neuanforderungsablauf

1. **Berechtigten Altfallscope auswählen:** Nur erlaubte minimale Verwaltungsprojektion des tatsächlich administrativ geschlossenen alten 02.104-Requirements (ggf. neutraler Fall ohne geheimen Ursprungsinhalt); zugehörige ursprüngliche Correction-/Notice-Version bleibt unverändert.
2. **Heute prüfen und neu projizieren:** Server validiert aktuelle Auth/Policy/Role/Group/Campaign/Fog/Quest/NPC/Wurf-/Notiz-/Zielrechte **für Verwaltung und Zielperson getrennt**, fachliche Relevanz des Korrekturstatus und neue erlaubte Feldprojektion. Falls heute keine zulässige Nachricht besteht, keine neue Pflicht; kein geheimes Existenz-/Count-/Timing-Leak.
3. **Effectfreie Vorschau:** Welche heute zulässige Notice-Fassung gezeigt werden darf, welches neue eigenständige Ack verlangt würde und ob 02.103-Reminder nach aktueller Policy überhaupt zulässig wären. Preview ändert weder alte Verwaltungsakte noch World-State, Notification oder Ack.
4. **Bewusste Freigabe:** Tatsächlich berechtigter Actor wählt ausdrücklich eine neue Anforderung, ggf. separat aktuell berechtigter Mitfreigabe bei kritisch konfiguriertem Fall. Ein Login oder Rollen-/Rechtewechsel allein ist niemals diese Erklärung.
5. **Neuprüfung unmittelbar beim Commit:** Aktuelle Quell-/Notice-/Empfänger-/Requirement-/Ziel-/Policy-/Versionsrechte, alter Abschlussbeleg und laufende konkurrierende Neuanforderungen/Neuevents; keine Ausführung auf veraltetem Snapshot.
6. **Einmaliger neuer Requirementbeleg:** Eigene stabile neue ID/Revision, neuer Zeitpunkt, berechtigt gewählte aktuelle Notice-Revision, verantwortlicher Actor, Grund/Bezug zu alter Schließung; serverseitig transaktional/idempotent, kein Update des vorherigen terminalen `administrativ geschlossen` oder vorgetäuschtes Alt-Ack.
7. **Optionales eigenes Reminderleben:** Nur für den **neuen** heute gültigen 02.102-Requirement-/Recipient-/Notice-Scope darf – falls ausdrücklich aktiv – die 02.103-Reminder-/Eskalationspolicy anlaufen. Nie historische schon gestoppte Reminder beliebig replayen.
8. **Neue persönliche Kenntnisnahme:** Erforderliche neue 02.102-Quittung ausschließlich durch bewusste eigene Aktion des nun aktuell berechtigten Empfängers; die 02.104-Abschluss-, 02.102-Ack- und neue Requirementhistorie bleiben getrennt auswertbar.

## 4. Versionen, parallele Fälle und Sicherheit

**Entwurfsobjekte, keine API/DB-Festlegung:** `AcknowledgementReissuePolicy`, `AcknowledgementReissueRequest`, `AcknowledgementReissueDecision`, `AcknowledgementReissueImpactPreview`, `AcknowledgementReissueReceipt`, `AcknowledgementRequirementLink`, `ReissueConflict`, `ReissueAccessProjection`, `ReissueOperationId`.

**Stabile technische Korrelation:** Kampagnen-ID, tatsächlicher Spieler, ursprünglicher 02.100-Commit, früherer 02.101-Notice-/Revision-Scope, alter 02.102-Requirementbeleg und 02.104-Resolutionbeleg, **neue** Notice-/Ack-Requirement-/Policyversion und neue Operation-/Actor-/Audit-IDs. Eine alte Requirement-ID darf **nicht wiederverwendet** werden.

**Doppel-/Raceresistenz:** Zwei SL-Anforderungen gleichzeitig, Reconnect, erneutes Senden, Mehrgerätebetrieb, verspätete 02.103-Reminder oder ein zwischenzeitlicher NPC-/Quest-/Fog-/Gruppenwechsel dürfen nicht zwei unkontrolliert identische neue offene Pflichten, geheime Notify-Events, doppelte SL-Eskalationen oder ein fingiertes Ack erzeugen. Bei gleichzeitigen fachlich identischen zulässigen Neuanforderungen nur **ein** wirksames neues Requirement oder explizit bestätigten neuen Kontext; CAS/Versions-/Idempotenzprüfung pro Originalbeleg/Empfänger/Notice-Revision. Bei irrelevanter oder stale neuer Notice keine automatische Fallback-Freigabe der älteren Secret-Revision.

**Abschluss bleibt historisch:** Eine nachträgliche `erneut erforderlich`-Information gehört auf den **neuen** Requirement-/Auditbeleg. Der alte beendete Fall erhält allenfalls einen nach aktueller Auditpolicy berechtigten **Rückverweis**, keine Änderung seines damaligen Rechts-/Erledigungs- oder persönlich-quittiert-Status.

**Wissen und Daten bleiben geschützt:** Bereits einmal reale bekannte Sachverhalte lassen sich nicht aus menschlicher Erinnerung entfernen; erneute UI-Exposition ist jedoch immer eine **neue** Serverantwort und daher **an heutige** Rechte gebunden. Alte Offline-/Cache-/Realtime-/Inbox-/Search-/Badge-/Count-Quellen und Export dürfen nicht als Erlaubnis dienen, vergangene geheime Daten unberechtigt zuzustellen. Rollen-/Gruppenänderung vor Zustellung/Quittierung stoppt weitere illegitime Antworten.

## 5. Zusatz des Projektinhabers – Chat („rchat“) als separat schaltbares Kampagnenmodul

**Verbindlich mit 02.105 C ausdrücklich mitgeplant:** AdventureShift soll einen **integrierten Chat** vorsehen, der **bei der Kampagnenerstellung** von der SL **wirksam AN oder AUS geschaltet** werden kann. Der Ausdruck „rchat“ wird hier mangels genauerer Spezifikation vorläufig als **spielinterner Text-/Rollenspielchat** verstanden, **nicht** als Auftrag, einen bestimmten fremden Dienst/„RChat“-Anbieter einzubinden. Kampagnen-/Gruppen-/Direkt-/SL-bezogene Chattypen mit eigenen aktuellen Kanal-/Empfänger-/Gruppen-/Rollenrechten sind durch **02.106 C** beschlossen [Detail](KARTEN-WORKSHOP-02.106.md); Formatierung/Moderation und Verlauf/Retention werden im Kommunikationsbereich **11** bzw. 02.107 weiter entschieden. Aus „rchat“ folgt **keine** Pflicht zur Voicechataufnahme, Transkription, KI-Analyse oder zum integrierten Sprachdienst.

**Bei Kampagnenerstellung sichtbar wirksame Option (bereits jetzt Fachvorgabe):**
- **Chat: An** – Nur nach korrekter Kampagnen-/Rollen-/Mitgliedschafts- und künftig ausdrücklich beschlossener Kanal-/Empfängerberechtigung dürfen zugehörige Chatfunktionen nutzbar sein. Es wird kein pauschal öffentlicher Kanal für geheime SL-/NPC-/Gruppeninformationen vorab festgelegt.
- **Chat: Aus** – Der optionale Chatpfad darf **serverseitig weder neue Chatnachrichten senden/publizieren noch unberechtigte Chatabos/alten Nachrichteninhalt ausgeben**, auch nicht via manipuliertem Client. UI ausgeblendet/deaktiviert allein genügt nicht. **Bestehende rechtmäßig gespeicherte Chats bei späterem Moduswechsel geschützt behandeln**, nicht automatisch ohne abgesprochene Aufbewahrungs-/Bestandsregel löschen oder öffentlich machen.
- **Unabhängige Grundfunktionen:** Authentifizierung, SL-/Spieler-Sichtschutz, tatsächlicher World-State, Karten, Würfel-/Serverereignisprotokoll, Inventar, 02.94–02.97-Spielernotizbuch, 02.101-Korrekturhinweise, 02.102-Acks und 02.103-Reminder funktionieren nach ihren jeweiligen Policies **auch mit Chat Aus**. Der Chat-Schalter ist keine globale Benachrichtigungs-/Rechte- oder Notiz-Deaktivierung.
- **Kein Weltkommando aus Chattext:** Ein geschriebenes Rätselwort, NPC-Dialog, Code, Würfelbefehl, freiwilliger Rollenspieltext oder „Quest erledigt“ löst **ohne den jeweils eigens autorisierten 02.99-/Objekt-/Event-/Würfelpfad** niemals echte Quest-/NPC-/Türen-/Inventar-/Node-/Sensor-/Alarm-/Timer-/Next-Player-Weltwirkung aus. Chatinhalt ist unvertrauenswürdiger Freitext, niemals freier Scriptcode.
- **Serverautorität/Datenschutz:** Die serverseitige Chat-Capability berücksichtigt 02.25-Defaults/markierte Ausnahmen und spätere geregelte Änderungen mit Bestandsschutz; Nachrichten-/Empfänger-/Gruppen-/Privat-ACLs, Schutz vor Injection/HTML-Ausführung, Spam/Rate-Limits, Missbrauch und unbefugten Realtime-/Reconnect-/Such-/Exportzugriff gehören in den Implementierungsplan. **Keine** Annahme, dass Chattexte automatisch für die SL oder alle Kampagnenmitglieder freigegeben sind.

**Wichtig für die spätere Kampagnenerstellung:** Die bereits in 02.98 C beschlossene Freiheit, Technik- und Automatisierungsgrad pro geeigneter Funktion zu wählen, schließt den **separaten Chat-An/Aus-Schalter** nun ausdrücklich ein. Die **genaue Gestaltung** des Kampagnenerstellungsassistenten, eine vollständige Übersicht anderer Module/Abhängigkeiten und die endgültige Priorisierung kommen weiterhin erst **nach allen Featurebereichen**, wie zuvor vom Projektinhaber gewünscht.

## 6. Konzeptioneller Umsetzungsplan (keine Implementierung)

1. **02.105-Resolver:** Rechte `closedAck.reissue`, Origin-/Notice-/Ack-/Closure-Referenzen, aktuelle 02.25-Policy, echte Sicht-/NPC-/Quest-/Fog-/Gruppen- und heutige 02.101-/02.102-Feldprojektion mit fachlicher Relevanz getrennt prüfbar planen.
2. **Neues Version-/Antragsobjekt:** Reissue-Preview, bewusster berechtigter Commit, neue ID, alter Closurelink, Actor/Grund, einmalige persistente Erstellung und Kollisionserkennung; niemals historische Abschlüsse/Acks umetikettieren.
3. **Mitteilungs- und Reminder-Verbindung:** Neue heute berechtigte Notice-Fassung statt alter Secret-Nachricht als Quelle, 02.101 für Zustellung/Realtime/Inbox/Search/Export, 02.103 nur für den neuen tatsächlich offenen persönlichen Anforderungsscope.
4. **Chat-Policy-Capability ergänzen:** `CampaignChatPolicy` / `ChatCapabilityEnabled` als **konzeptionelle** Featureflag; wirksamer Kampagnen-An-/Aus-Check beim Erstellen/Schreiben/Abonnieren/Lesen gemäß spätere Kanalpolitik, mit revisions-/bestandsgeschützter Umschaltung. Keine finale API/DB- oder UI-Definition.
5. **Modulgrenzen:** Chat-Senden unabhängig von Welt-/Würfel-/Inventar-/Node-/Quest-/02.99-Aktions- und 02.101-Notice-/02.102-Ack-Pfaden; nur tatsächliche autorisierte Benutzeraktionen verändern Weltzustand. Eigene Notizen/SL-Geheimnisse dürfen nicht über Chat durchsickern.
6. **Tests vorbereiten:** Reissue-Auth und geheime NPCs, mehrfacher Reissue-Request, Race/Group-Change, alte Closure-/Ackhistorie, gestopptes Reminder-Replay, Chat-On/Off bei Neuerstellung/manipuliertem Client, alte Nachrichten bei Umschaltung, Secret-/Private-/Multigroup-Projektion, No-World-Effect und Voicechat-first ohne Chat.
7. **Spätere UX/Komponenten:** Die durch 02.106 C beschlossenen berechtigten Kanaltypen/Empfängerscopes berücksichtigen. Verlauf/Retention folgen 02.107, konkrete Chat-UI und Moderation im Kommunikationsbereich 11. Kampagnen-Erstellungsdialog und Modul-Inventar erst im gemeinsamen nachgelagerten Einstellungs-Workshop finalisieren.

## 7. Fachliche Abnahmetests

| Fall | Erwartung |
| --- | --- |
| Alte Ackpflicht wurde nach 02.104 administrativ geschlossen | Alter Closurebeleg bleibt terminal und darf nicht in „persönlich quittiert“ umetikettiert werden |
| Spieler kehrt mit gültiger Kampagnen-/NPC-/Notice-Sicht zurück | Berechtigte SL kann **bewusst** eine neue eigene Anforderung für eine heute erlaubte relevante Nachricht erstellen |
| Spieler meldet sich nur an oder Gruppe wird verändert | **Kein** ungeprüftes automatisches Wiederöffnen alter Anforderungen |
| Alter Hinweis ist heute geheim oder fachlich irrelevant | Keine Neuanforderung, kein verstecktes Ack-/Notice-/NPC-Existenzleck |
| Neue aktuelle Notice enthält weniger freigegebene Details als alte | Nur heute rechtmäßig projizierte minimal erlaubte Felder zeigen |
| Zwei berechtigte SL stellen identische Neuanforderung gleichzeitig | Maximal eine effektive neue zulässige Requirement-/Revisions-Instanz, kein Reminder-/Count-Duplikat |
| Browser schickt alten Closurebeleg als „persönlich bestätigt“ | Serverseitig abgewiesen; echter Spieler-Ack unverändert |
| Neue Anforderung wurde erstellt, Empfänger verliert Zugriff | Vor Inbox, Realtime, Quittierung und Reminder erneut aktuelle Rechte prüfen; unberechtigte Zustellung stoppen |
| Neue Anforderung wird vom berechtigten Spieler ausdrücklich quittiert | Neuer echter 02.102-Ackbeleg **für den neuen Scope**, alte administrative Schließung bleibt |
| 02.103-Reminder vor alter Schließung wird replayt | Keine wiederbelebte alte Reminderkette, neue fällige Mitteilungen nur unter aktueller neuer 02.103-Policy |
| Kampagne wird mit „Chat Aus“ erstellt | Kein neuer Chat-Nachrichten-/Abo-Pfad serverseitig möglich; UI deaktiviert; Würfel, Karten, Notes, 02.101-Hinweise unabhängig |
| Kampagne mit „Chat An“ und berechtigtem Benutzer | Erlaubte Chat-Nachricht nutzbar, ohne automatisch allen Spielern/SL oder versteckten Gruppen bekannt zu werden |
| Manipulierter Client sendet trotz Chat Aus | Server verweigert wirkliche Chat-Send-/Subscribe-Operation, kein World-/Node- oder Secret-Effekt |
| Chat wurde später ausgeschaltet | Alte rechtmäßige Chatdaten nach definierter Bestands-/Aufbewahrungs-/ACL-Policy geschützt, keine heimliche Veröffentlichung/Löschung |
| Chattext lautet „Türcode 1234“ oder „NPC ist tot“ | Kein echter Code-/Quest-/NPC-/Door-/Inventory-/Check-/Turn-/Nodeeffekt allein durch Nachricht |
| Spieler hat private Notiz, aber Chatmodul ist aktiv | Notiz wird weder automatisch im Chat geteilt noch dadurch für SL oder Gruppe lesbar |
| Komplette Kampagne Voicechat-first mit Chat Aus | Externes Sprechen, manuelle SL-UI-Aktionen und andere konfigurierte Module funktionieren weiter |
| Nutzer wünscht integrierte Voice-/Aufnahmefunktion | **Noch nicht** Bestandteil dieses Chat-Grundsatzes; separat zu entscheiden, kein stiller Mikrophon- oder KI-Zwang |

## 8. Beschlussgrenze und nächste Frage

**Beschlossen:** 02.105 C erlaubt eine aktuell berechtigte, bewusst autorisierte **neue, versionierte** 02.102-Kenntnisnahmeanforderung nach früherem 02.104-Abschluss, mit erneut gefilterter 02.101-Notice und unabhängigem 02.103-Reminderpfad. Die Historie bleibt vollständig, keine automatische Reopen-Flut, keine Weltwirkung. **Zusätzlich verbindlicher Nutzerwunsch:** Bei Kampagnenerstellung ist ein **eigenständiger wirksamer Chat-An/Aus-Schalter** vorzusehen; ein Chat ist optional und niemals verpflichtende Voraussetzung für Voicechat, Notizen, Würfel oder Spielweltfunktionen.

**Nicht beschlossen:** Finale Chat-Kanaltypen, -UI, Retention, Moderationsrollen, integrationsspezifische Voice-Funktionen, konkrete globale Settings-UI, endgültige API/DB-Struktur oder MVP-Umfang. „rchat“ bleibt bis zu weiterer Präzisierung als integrierter Text-/Rollenspielchat verstanden.

## Archivierte Folgefrage 02.106 – inzwischen als C beschlossen

**Beispiel:** Eine Kampagne hat das Chat-Modul bei der Erstellung aktiviert. Spieler möchten manchmal an alle schreiben, gelegentlich vertraulich in ihrer Gruppe beraten oder eine Nachricht nur an die Spielleitung senden. Was soll prinzipiell möglich sein? Der Chat darf niemals bereits beschlossene Geheimnis- und Rollenrechte umgehen.

- **A – Nur ein gemeinsamer Kampagnenchat:** Bei aktiviertem Chat gibt es ausschließlich einen einzigen für alle berechtigten Mitglieder sichtbaren Textkanal, keine individuellen/privaten Unterhaltungen.
- **B – Alles automatisch öffentlich:** Sämtliche Gruppen-/Privat-/SL-Nachrichten und frühere Chatverläufe werden unabhängig von Gruppen- oder Geheimnisrechten allen angezeigt.
- **C – Konfigurierbare berechtigte Chatkanäle (Empfehlung):** Je Kampagnen-/Regel-/Gruppen-/Rollenstandards mit markierten 02.25-Ausnahmen erlaubt die SL nur die gewünschten passenden **Kampagnen-, Gruppen-, direkt adressierten und ggf. SL-spezifischen Chatbereiche**. Nachrichten/Verläufe und Metadaten werden ausschließlich an tatsächlich berechtigte Empfänger geliefert; der gesamte Chat bleibt als Modul bei der Erstellung an-/abschaltbar. Details zu Verlauf, Moderation und UI bleiben für Kommunikationsbereich 11.

**Aktueller Fortgang:** [02.106 C](KARTEN-WORKSHOP-02.106.md) hat getrennt konfigurierbare berechtigte **Kampagnen-, Gruppen-, direkte Einzel-/Mehrpersonen- und SL-bezogene Chatbereiche** beschlossen. Der gesamte Chat bleibt wie ausdrücklich in **02.105** festgelegt **bei Kampagnenerstellung wirksam An/Aus schaltbar**. **02.107 C** hat konfigurierbar flüchtige oder gespeicherte Chatverläufe samt aktuellem UND historischem Empfängerschutz und Retention beschlossen [Detail](KARTEN-WORKSHOP-02.107.md). **02.108 C** hat konfigurierbare eigene Edits/Zurücknahmen und gezielt berechtigte Moderationsentfernung bei unveränderten Kanal-/Historienrechten beschlossen [Detail](KARTEN-WORKSHOP-02.108.md). **02.109 C** hat berechtigte, datensparsame Meldungen und begrenzte Moderation beschlossen [Detail](KARTEN-WORKSHOP-02.109.md). **Chat An/Aus bei Kampagnenerstellung bleibt verbindlich.** **02.110 C** hat persönliche berechtigt konfigurierbare Kanal-Mutes und wirksame serverseitige eigene DM-Senderblocks beschlossen, ohne amtliche Notices, Chat-Historienrechte oder echten World-State zu verändern [Detail](KARTEN-WORKSHOP-02.110.md). **02.111** fragt nach berechtigten Chat-Erwähnungen und optionalen Pings.
