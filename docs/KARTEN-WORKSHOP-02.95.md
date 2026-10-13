# AdventureShift – Karten-Workshop: Beschluss 02.95 C

**Stand:** 13.10.2026 – Beschluss 02.95 C; Folgeentscheidung 02.96 C ebenfalls beschlossen, nächste offene Frage 02.97  
**Status:** Verbindlicher Fachbeschluss und Umsetzungsplanung mit Abnahmetests; noch kein implementierter Code, kein finales Datenbankschema, keine abschließende UI- oder MVP-Entscheidung.  
**Bezüge:** [Karten-Hauptworkshop](KARTEN-WORKSHOP.md) · [02.25 globale Vorgaben und markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.83/02.84 Versionierung und Zusammenarbeit](KARTEN-WORKSHOP-02.84.md) · [02.85 Vorlagenordner/Volltextsuche](KARTEN-WORKSHOP-02.85.md) · [02.86 Rechte für geteilte Bibliotheken](KARTEN-WORKSHOP-02.86.md) · [02.92 Abhängigkeitsprüfung](KARTEN-WORKSHOP-02.92.md) · [02.93 optionaler Missionsgenerator ohne KI](KARTEN-WORKSHOP-02.93.md) · [02.94 Missionsketten und verbindliches Spielernotizbuch](KARTEN-WORKSHOP-02.94.md) · [02.96 Notizordner/Tags/Volltextsuche](KARTEN-WORKSHOP-02.96.md)

## 02.95 – Frei konfigurierbare private und bewusst gemeinsam genutzte Spielernotizen

**Verbindlich beschlossen: Variante C.** Jeder berechtigte Spieler besitzt weiterhin den unter **02.94 C ausdrücklich beschlossenen eigenständigen, dauerhaft verfügbaren UI-Bereich für selbst geschriebene Freitextnotizen**. Notizen sind beim Anlegen **persönlich/privat**. Für jede einzelne Notiz lässt sich nach wirksamen Kampagnen-/Gruppen-/Spieler-/Rollenstandards und ausdrücklich gekennzeichneten Ausnahmen aus 02.25 **bewusst** wählen, ob sie privat bleibt, für bestimmte berechtigte Spieler bzw. Gruppenmitglieder oder als gemeinsame Gruppennotiz sichtbar wird. **Lesen und Bearbeiten sind getrennte Berechtigungen.** Notizen werden weder automatisch für alle sichtbar, noch löst das Teilen einen Codecheck, Quest-/Wissensflag, Inventaritem oder eine Node-/Tür-/NPC-/Würfelwirkung aus. **Missionen und Missionsgeneratoren bleiben für das Notizbuch vollkommen optional.**

### 1. Sichtbarkeits- und Kollaborationsmodi

- **Privat als Standard:** Eine neue vom Spieler verfasste Notiz gehört zunächst dessen berechtigtem Spieler-/Kampagnenkontext und wird ohne bewusste Freigabe nicht an Gruppe, weitere Spieler, SL-Generator oder andere Kampagnen übermittelt. Eigener Text kann auch absichtlich falsch oder nur eine Vermutung sein; keine automatische Prüfung gegen echte Rätselcodes/SL-Geheimnisse.
- **Gezielte Empfänger:** Der Eigentümer darf bei gültiger Policy eine bestimmte Auswahl tatsächlich berechtigter Mitspieler freischalten. Für jeden geteilten Eintrag ist erkennbar, **wer lesen** und – sofern ausdrücklich erlaubt – **wer editieren** darf. „Mit Spieler B teilen“ ist nicht gleich „allen Spielern in Bs anderen Gruppen freigeben“; technische Zielidentitäten sind eindeutig und serverseitig zu prüfen.
- **Gruppennotiz:** Eine Notiz kann als bewusst für eine benannte berechtigte Gruppe freigegebene gemeinsame Notiz geführt werden. Bei Gruppenwechsel/-zusammenführung oder Neuaufnahme eines Mitglieds muss die wirksame Freigaberegel deutlich unterscheiden, ob die Notiz nur für die beim Teilen konkret ausgewählten Empfänger oder bewusst für eine **dynamische Gruppenmitgliedschaft** gilt. Keine unbemerkte automatische Erweiterung des Empfängerkreises.
- **Berechtigung zum Lesen vs. Schreiben:** Schreibberechtigung impliziert nur den für das Editieren tatsächlich notwendigen Zugriff auf die jeweilige Notiz, nicht das Recht, deren Empfängerliste zu erweitern, die Notiz in andere Kampagnen zu übertragen oder andere persönliche Texte anzusehen. Ein nur leseberechtigtes Gruppenmitglied darf nicht bearbeiten/löschen/weiterteilen.
- **Freigabehoheit und Ausnahmen:** Notizeigentümer, berechtigt definierte Gruppennotizverantwortliche und gegebenenfalls ausdrücklich rechtlich/technisch zuständige Adminrollen sind getrennt von normalen Lesenden/Editoren zu modellieren. Was passiert, wenn ein Eigentümer die Kampagne verlässt oder eine Gruppennotiz verwaist, benötigt eine berechtigte Übernahme-/Archiv-/Löschpolicy statt pauschaler Öffentlichkeit.
- **Kein impliziter SL-Zugriff auf Rätselgedanken:** Eine Spielleiterrolle darf ihre berechtigten Szenen- und Questdefinitionen verwalten, bekommt aber **nicht allein wegen dieser Rolle automatisch sämtliche privaten Überlegungen der Spieler in einem Generator-Preview oder Suchindex**. Etwaige ausdrücklich nötige administrative Zugriffsfälle müssen eng begründet, rollen-/kontextgeschützt, protokolliert und in der späteren Rechteausarbeitung klar dargestellt werden.

### 2. Freigabevorgang, Widerruf und Wahrung der Spielerentscheidung

1. **Konkrete einzelne Notiz auswählen:** Benutzer entscheidet gezielt für eine vorhandene Notiz; keine globale automatische Offenlegung bereits notierter Codes durch Aktivieren einer Gruppensicht oder einer Mission.
2. **Freigabevorschau:** Vor Bestätigung den tatsächlichen Titel/Textumfang, den Zielkreis und die zu gewährenden Rechte **lesen** bzw. **bearbeiten** anzeigen. Bei dynamischer Gruppe deren Reichweite und mögliche künftige berechtigte Mitglieder erkennbar machen, ohne fremde vertrauliche Daten zu offenbaren.
3. **Aktuellen Gruppen-/Kampagnenkontext prüfen:** Jede Freigabe, Synchronisierung und Bearbeitung auf gültige Identität, Kampagne, Gruppen-/Mitgliedschaft, Empfängerrolle und Notizregel mit aktueller Policyversion serverseitig prüfen. Ein früheres Login, erratbare Notiz-ID oder fremde Einladungs-URL erteilt kein Recht.
4. **Geteilte Notiz bleibt menschlicher Text:** Beispiel „Vielleicht lautet der Code 4739“ darf eine andere berechtigte Person lesen und bei Schreibrecht als Hypothese kommentarlos berichtigen. **Die tatsächliche Weltcodeprüfung findet erst durch explizite Eingabe am berechtigt bedienbaren Schloss/Terminal/Container statt** (01.10/02.59). Das Freigeben, Kopieren, Übernehmen oder Bearbeiten im Notizbuch vergibt weder Keycard-/Itemrechte noch Mission-/Quest-/NPC-Wissen oder SL-„richtiger Code“-Hinweise.
5. **Widerrufen oder Empfängerliste ändern:** Berechtigter Besitzer kann nach wirksamer Policy Les-/Schreibfreigaben zurücknehmen oder vermindern. Danach dürfen Serverabfragen, Realtime-Ereignisse, neue Such-/Vorschau-/Exportvorgänge und weitere Editoperationen **keine aktuell unberechtigten Inhalte mehr ausliefern**. Veraltete Browser-Caches/Subscriptions berechtigungsbewusst invalidieren. **Bereits vorher bewusst mitgeteiltes Wissen kann faktisch nicht aus Erinnerungen oder eigenhändig angefertigten Kopien anderer Personen entfernt werden**; keinen technisch unmöglichen Geheimnis-Rückruf versprechen.
6. **Kein automatisches Weiterteilen:** Empfänger mit Lese- oder Bearbeitungsrecht können die ursprüngliche Notiz nicht allein durch dieses Recht für weitere Spieler/größere Gruppen offiziell weiterfreigeben; gesondertes explizites Share-/Owner-/Adminrecht erforderlich.
7. **Inhalt und Eigentum getrennt:** Eine gemeinsame Notiz darf nach Bearbeitungsregel mehrere Autorenbeiträge haben; der ursprüngliche Besitzer-/Gruppenverantwortungsbezug bleibt eindeutig. Aus einer privaten Notiz eine Gruppennotiz zu machen ist kein automatische Übertragung der gesamten persönlichen Notizsammlung.
8. **Generator-unabhängig:** Notiz erstellen, privat behalten, selektiv teilen, gemeinsam bearbeiten und wieder privat machen bleibt auch in Kampagnen ohne aktive Questkette, ohne Missionsgenerator und ohne jegliche KI verfügbar.

### 3. Konfliktsichere Echtzeitbearbeitung

- **Gemeinsamer aktueller Stand:** Geteilte Notizen dürfen bei gültigem Editrecht von mehreren Berechtigten bearbeitet werden. Jede Änderung referenziert eine unverwechselbare Notiz-ID, zugrunde liegende Revision, Bearbeiter-/Kampagnen-/Gruppenberechtigung und eindeutige Edit-/Sync-Operations-ID.
- **Keine fremden Änderungen still überschreiben:** Bearbeiten zwei Personen nahezu gleichzeitig denselben Textabschnitt, muss der Server Versionskonflikte erkennen und einen geschützten Vergleich/Neuabgleich bzw. bewusste Entscheidung anbieten; nicht pauschal „letzte Speicherung gewinnt“. Nachweislich unabhängige kompatible Änderungen dürfen kontrolliert zusammengeführt werden. Ein geeignetes OT-/CRDT-/Lock-/Transaktionsframework ist erst später auszuwählen.
- **Offline-/Reconnect-Schutz:** Auf einen zwischenzeitlich widerrufenen Empfängerscope bezogene Offlineänderungen werden beim Wiederverbinden **nicht mehr ungeprüft in die geteilte Notiz übernommen**; aktuelle Schreibrechte, freigegebener Sichtumfang und Revisionsstand gelten. Wiederholte Editoperation mit identischer ID darf keine doppelte Änderung oder falschen Löschvorgang erzeugen.
- **Löschen und Revisionen:** Berechtigter Eigentümer/Editor kann nach wirksamer Policy den Text editieren; vollständiges Löschen/Archivieren, Freigabeverwaltung und etwaige Wiederherstellung älterer Notizfassungen müssen von einfachen Schreibrechten unterscheidbar sein. Aufbewahrung/Versions-UX wird in der späteren UI-/Datenschutzplanung konkretisiert; geheime ältere Versionen dürfen nach Rechteentzug nicht über Diff/Audit hervorscheinen.
- **Sicherer Text:** Eingaben ausschließlich als nicht vertrauenswürdige Daten behandeln. Keine Ausführung von HTML-/JS-/SQL-/Node-Code aus Freitext; Größen-/Speicher-/Rategrenzen vorsehen, bei späteren Formatanforderungen geeignete sichere Darstellung. Kein automatisches Pushen persönlicher Notizen an NPC-/Missions-/KI-Modelle.
- **Audits ohne Preisgabe:** Für berechtigte Verantwortliche relevante Teilungs-/Edit-/Konflikt-/Widerrufsvorgänge nachvollziehbar machen, aber fremde Notiztexte, Autoren oder Empfängerlisten nicht über allgemeines Spielprotokoll, Fehlermeldung oder Such-Snippet enthüllen.

### 4. Bewusst getrennte Daten und Berechtigungen

| Bereich | Verbindliche Grenze |
| --- | --- |
| **Private Notiz** | Freitext/Vermutung eines Spielers, standardmäßig nur persönlicher Notizbereich |
| **Geteilte Notiz** | Genau bewusst erteilte Les-/Bearbeitungs-/Gruppenzugriffe, keine neuen Spielweltrechte |
| **Questfortschritt** | Ausschließlich gültige tatsächlich eingetretene Mission-/Quest-/Node-/SL-Ereignisse, nicht Noteinträge |
| **Schlüssel/Keycard-Item** | Echte Inventar-/Objektinstanz mit tatsächlichem Besitz und Nutzungsregeln; Notiz darüber erzeugt keinen Besitz |
| **Codeeingabe** | Wirkliche aktive Tür-/Terminal-/Containerinteraktion mit aktueller Authentisierung, Versuchs-/Typ-/Rechteprüfung |
| **SL-/NPC-Geheimnis** | Serverseitig nach wirklichen Objekt-/Wissen-/Szenenrechten gefiltert; nicht allein durch Gruppennotiz-Berechtigung offenlegbar |
| **Mission-/Kartengenerator** | Vollkommen optional; erzeugt keinen Notiztext automatisch als kanonisches Weltwissen und darf ohne explizite gültige Freigabe keine privaten Notizen lesen |

### 5. Datenmodell und Umsetzungsplanung – kein Code

**Konzeptionelle Platzhalter:** `PlayerCampaignNotebook`, `PlayerNoteEntry`, `PlayerNoteRevision`, `PlayerNoteShareGrant`, `NoteRecipientScope`, `NoteEditPermission`, `SharedNoteEditOperation`, `NoteMergeConflict`, `NoteAccessPolicy`, `NoteSharingAudit`. Stabile Notiz-/Spieler-/Kampagnen-/Gruppe-/Empfänger-/Freigabe-/Revisions-/Operation-/Rollen-/Policyversions-IDs sowie klar getrennte Besitzer-, Editor-, Leser- und Freigabe-/Löschrollen. Noch keine Pflicht zu einem bestimmten Speicherformat, CRDT, Editorkomponente oder Synchronisierungsprotokoll.

**Umsetzungsschritte:** (1) Persönliches persistentes Spielernotizbuch aus 02.94 mit dem effektiven Kampagnen-/Gruppen-/Rollen-/Einzelnotizrechte-Modell aus 02.25 verbinden; (2) Freigabedialog für bewusst einzelne Einträge und private/gezielte/gruppenbezogene Empfänger mit getrennten Lese-/Edit-/Share-/Deleteaktionen, sicherer Gruppenmitgliedschaftsänderung und Widerruf konzipieren; (3) sichere rechtegefilterte Spieleransichten/Subscriptions und revisions-/operationsgebundene gemeinsame Bearbeitung samt Konflikt-/Offline-/Reconnectbehandlung; (4) Textsicherheit, persistenter Speicher/Audit/Retention- und Gruppen-Transfer-/Verwaisungsregeln sowie isolierte Tests; (5) unabhängige reale Codeeingabe und Missions-/Inventar-/NPC-/Node-/Questtrennung als Regression abnehmen. Konkrete gesamte UI-Menüführung und allgemeine Modulabschaltungen wie zuvor erst nach Featureworkshop abschließend planen.

### 6. Abnahmeszenarien

| Test | Erwartetes Ergebnis |
| --- | --- |
| Spieler A erstellt neue Notiz „Vielleicht Code 4739“ | Standardmäßig nur für A sichtbar, kein neuer Schlüssel/Questflag |
| A gibt diese Notiz für B nur zum Lesen frei | B darf sie sehen, nicht editieren, löschen oder weiterteilen |
| A gewährt B ausdrücklich Bearbeitungsrecht | B darf nach aktueller Scope-/Revisionprüfung ändern; C ohne Freigabe sieht nichts |
| A teilt eine einzelne Notiz mit seiner Gruppe | Nur der gültig bestimmte berechtigte Empfängerkreis sieht diesen Eintrag, nicht As gesamte private Sammlung |
| Neue Person tritt einer Gruppe bei | Keine unbemerkte Historienfreigabe bei nur für bisherige Empfänger erteilter Notiz; bei bewusst dynamischem Gruppenscope sichtbare Policy beachten |
| A widerruft Bs Zugriff vor dessen Reconnect | B bekommt keine neuen Notizdaten; alte offline erfasste Edits werden serverseitig ohne aktuellen Rechtsnachweis abgelehnt |
| Zwei berechtigte Editoren ändern dieselbe Zeile | Konflikt/Merge-/Rebaseentscheidung, keine unbemerkte Last-Writer-Wins-Überschreibung |
| Zwei kompatible unabhängige Änderungen | Gültige kontrollierte Zusammenführung mit nachvollziehbarer Revisions-ID |
| Gleiche Editoperation wird nach Netzwerkfehler doppelt übertragen | Idempotenz: einmalige logische Änderung, kein doppelter Eintrag |
| Spieler A notiert falschen Code | Notiz bleibt freie Vermutung; kein Richtig-/Falschhinweis oder automatische Aufgabe |
| Spieler B liest geteilten Code und tippt ihn am Terminal | Nur dort serverseitige echte Code- und Zugriffsprüfung; durch Noteilung kein zusätzliches Item/Spielrecht |
| Missionsgenerator/KI wird überhaupt nicht benutzt | Privates und erlaubtes Gruppennotizbuch weiterhin funktionsfähig |
| Ein geteiltes Dokument enthält HTML-/JS-artigen Text | Sicher als Text darstellen, keine Codeausführung |
| Unberechtigter Nutzer errät fremde Notiz-ID | Keine Text-, Metadaten-, Revision-, Autoren-, Empfänger- oder Existenzdetails ausliefern |
| Gruppennotiz-Inhaber verlässt Kampagne | Berechtigte Übernahme-/Archivpolicy anwenden, keine automatische Öffentlichkeit |
| SL ruft allgemeine Generator-/Diagnosevorschau auf | Keine fremden privaten Spielernotizen als unberechtigte Datenquelle |
| Eigene Notiz wird nach Reconnect wieder geöffnet | Persistente eigene berechtigte Version bleibt erhalten, fremde Geheimnisse nicht synchronisiert |

### 7. Abgrenzung und nächste Entscheidung

- **02.94 C** hat das persönliche, frei verwendbare Spielernotizbuch und die völlige Freiwilligkeit des Missionsgenerators **bereits verbindlich beschlossen**. **02.95 C** legt ausschließlich **bewusste Teilung, Gruppenscopes, getrennte Lese-/Schreibrechte und sicheren kollaborativen Betrieb** von Spielernotizen fest.
- **Folgeentscheidung 02.96 C inzwischen beschlossen:** Berechtigte Spieler dürfen Notizen in **selbst erstellten, frei benennbaren und verschachtelbaren Ordnern** organisieren, **Tags/Kategorien**, Sortierung/Filter nutzen und eine **echte berechtigungsgefilterte Volltextsuche über Titel, Notiztext und erlaubte textuelle Metadaten** betreiben. Persönliche Ordner-/Tagzuordnung geteilter Notizen überträgt keine fremden Eigentümer-/Edit-/Share-Rechte; Suche, Trefferzahl, Snippets, Autocomplete und Ordnerpfade bleiben geheimnisgeschützt nach 02.95. [02.96 C](KARTEN-WORKSHOP-02.96.md). **02.97** fragt separat nach bewussten Verknüpfungen von Notizen mit sichtbar erlaubten Karten-/NPC-/Questobjekten.
- **02.97 noch offen:** Spieler könnten ihre Notizen bewusst mit bereits berechtigt sichtbaren Kartenmarkern/Orten, bekannten NPCs oder freigegebenen Questanzeigen verknüpfen, ohne geheime Koordinaten, Namen oder Missionen zu verraten. Das wird als eigene Entscheidung unter [02.97](KARTEN-WORKSHOP-02.96.md) vorbereitet; keine automatische Lösung/Questwirkung.

## Archivierte Folgefrage 02.96 – inzwischen als C beschlossen

**Beispiel:** Ein Spieler hat nach mehreren Sitzungen viele Notizen über Türcodes, NPCs, Orte und eigene Vermutungen gesammelt. Er möchte eigene Kategorien wie „Codes“, „Verdächtige“, „Rätsel“ und „Offene Fragen“ anlegen und einen alten Hinweis über eine Suche wiederfinden, ohne die Notizen automatisch als wahr erkennen zu lassen.

- **A – Nur eine fortlaufende Notizliste:** Alle privaten und berechtigt geteilten Einträge erscheinen chronologisch. Es gibt keine eigenen Ordner, Tags oder Volltextsuche innerhalb des Spielernotizbuchs.
- **B – Zwangsweise automatische Rätselablage:** Das System analysiert alle Notizen, erkennt automatisch geheime Codes, sortiert Hinweise nach vermeintlich richtigen Lösungen und zeigt die passenden Rätselantworten ungeprüft auch anderen Gruppenmitgliedern.
- **C – Frei konfigurierbare Notizorganisation und berechtigte Volltextsuche (Empfehlung):** Spieler können eigene **frei benennbare Ordner und Unterordner**, Tags/Kategorien und geeignete Sortierung/Filter erstellen und ihre privaten bzw. bewusst geteilten Notizen dort organisieren. Eine **Volltextsuche** findet Titel und eigene Textinhalte **nur im tatsächlich berechtigten Notizbestand** nach 02.95; eigene Vermutungen bleiben unbewertet, keinerlei automatische Codeprüfung/Questfortschritt/Geheimnisoffenlegung. Kampagnen-/Gruppenstandards mit markierten Einzelausnahmen bleiben möglich.


**Aktueller Fortgang:** [02.96 C](KARTEN-WORKSHOP-02.96.md) mit eigenen Ordnern/Unterordnern, Tags und tatsächlicher berechtigter Volltextsuche ist beschlossen. **Nächste offene Frage 02.97:** Notizen mit tatsächlich bekannten Orten, NPCs und Quests bewusst verknüpfen.