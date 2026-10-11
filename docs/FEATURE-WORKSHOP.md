# AdventureShift – Gemeinsame Featureplanung (Workshop)

**Beginn:** 11.10.2026  
**Status:** IDEENSAMMLUNG UND ENTSCHEIDUNGSVORBEREITUNG – noch keine endgültige Feature-Spezifikation, noch kein Implementierungsauftrag.  
**Verbindlich aus bisherigen Gesprächen:** genre- und regelwerksunabhängige Browser-Plattform; Steam-Login; mehrere Spieler und Spielleiter; gemeinsame Karte/Movement; von allen sichtbare Würfel; Charaktere, Items und Gegner; später Self-Hosting. Produktname **AdventureShift**.

## Ablauf dieses Workshops

Wir besprechen die Bereiche **nacheinander** und dokumentieren danach jeweils:
1. **Entschieden:** Konkretes Verhalten und gewünschte Oberfläche.
2. **Optional/später:** Erweiterungen, die wir bewusst nicht sofort benötigen.
3. **Offen:** Punkte, die noch abgestimmt werden müssen.
4. **Technische Konsequenzen:** Was Datenmodell, Architektur und Infrastruktur später können müssen.
5. **Abnahmeszenario:** Was Benutzer sehen/tun können, wenn das Feature umgesetzt ist.

**Bis alle Bereiche entschieden sind, setzen wir keine Annahmen stillschweigend als endgültig und beginnen nicht mit der eigentlichen Implementierung.** Vorhandene GitHub-Issues sind ein vorläufiger Backlog; die spätere Aufwandsschätzung und Priorisierung folgt erst nach Abschluss dieses Workshops. Danach werden Produktkonzept, MVP, Datenmodell, UI, Technik- und Implementierungs-Roadmap konsolidiert.

## Recherchierte Muster anderer Plattformen

- **Foundry VTT:** trennt Item-Vorlage/Item-Daten und im Charakter verankerte Gegenstandsinstanzen; unterstützt regelabhängige Effekte, Kompendien, Szenen, Wände, Licht und Journale.
  - https://foundryvtt.com/article/items/
  - https://foundryvtt.com/article/active-effects/
  - https://foundryvtt.com/article/compendium/
  - https://foundryvtt.com/article/scenes/
  - https://foundryvtt.com/article/journal/
- **Owlbear Rodeo:** trennt eine wiederverwendbare Kartenbild-Datei von einer Szene als frei arrangierbarer Spielfläche, inklusive Zeichenwerkzeugen, Raster, Tokens, Fog und mehreren Karten nebeneinander.
  - https://docs.owlbear.rodeo/docs/scenes/
  - https://docs.owlbear.rodeo/docs/drawing/
  - https://docs.owlbear.rodeo/docs/fog/
  - https://docs.owlbear.rodeo/docs/aligning-a-map/
- **Alchemy RPG:** zeigt neben Battle Maps auch atmosphärische Erzähl-Szenen mit Artwork, Musik und privaten SL-Notizen.
  - https://help.alchemyrpg.com/en/articles/9821311-creating-a-scene
- **Kartenerstellung außerhalb der Plattform:** Dungeon Alchemist exportiert Karten samt Wänden/Licht für unterstützte VTTs; Inkarnate bietet Map-Erstellung mit plangebundenen kommerziellen Nutzungsrechten; Dungeondraft kann das verbreitete Universal-VTT-Format (`.dd2vtt`) ausgeben.
  - https://www.dungeonalchemist.com/
  - https://www.dungeonalchemist.com/import-to-foundry
  - https://inkarnate.com/faq/
  - https://dungeondraft-encyclopaedia.gitbook.io/guide/final-steps/exporting-your-map/universal-vtt

Die Inspirationsquellen sind **keine** Lizenz zur Übernahme fremder UI-Grafiken, Modelle, Assets oder Quelltexte. Die tatsächliche Verwendung von fremden Karten verlangt passende Rechte; eine eigene .dd2vtt-Unterstützung wäre zu implementieren, nicht automatisch vorhanden.

## Feature-Katalog / Gesprächsreihenfolge

| Nr. | Themenbereich | Zu planende Features | Entscheidungsstand |
| --- | --- | --- | --- |
| **01** | **Inventar & Gegenstände** | Liste/Kachel-UI, Kategorie, Slots, Container, Menge, Gewicht, Geld, Aufheben, Handel, Ausrüsten, Effekte | **Grundentscheidungen 01.1–01.16 abgeschlossen; Details offen** |
| **02** | **Karten & Szenenerstellung** | Upload, freie Zeichenfläche, Karten-Editor, Import, Raster, Ebenen, Szene vs. Karte, Szenenwechsel | **In Bearbeitung: 02.1 C (Import + Editor), 02.2 C (Schnell- und Baumodus); 02.3 Szenentypen offen** |
| **03** | **Charakterbögen** | Variabel definierbare Attribute, Ressourcen, Vorlagen, Portrait, Berechtigungen, Fortschritt | Offen |
| **04** | **Tokens, Objekte & Bewegung** | Figurengrößen, freie Bewegung/Klick/Drag, Raster/Hex, Kollision, Entfernung, Fahrzeuge | Offen |
| **05** | **Würfelsystem** | 3D-Würfel, Wurfarten, Würfelpools/Formeln, Log, öffentliche/private Würfe | Ziel „alle sehen Würfel“ vorgegeben; Details offen |
| **06** | **NPCs & Gegner** | Figurenbibliothek, Vorlagen, SL-Steuerung, Werte, Ressourcen, Verhalten, Spawn | Offen |
| **07** | **Kampf & Regelmodule** | Sandbox ohne Regeln, Runden/Initiative, Aktionen, Zustände, Regelpakete | Regelwerksneutraler Kern festgelegt; Module offen |
| **08** | **Spielleiter-Werkzeuge** | SL-Sicht, versteckte Objekte, Nebel/Licht, Geheimnotizen, Gruppensteuerung, Rückgängig | Offen |
| **09** | **Kampagnen & Lobby** | Mehrere Kampagnen, Einladungen, Rollen, Spielräume, Charakterzuordnung, Sessionablauf | Steam und SL/Spielerrollen vorgegeben; Details offen |
| **10** | **Journal, Quests & Handouts** | Journal, Questtracking, Kartenmarker, NPC-Dossiers, Texte, Hinweise | Offen |
| **11** | **Kommunikation & Präsentation** | Textchat, Würfel-Feed, Emotes, Musik/Ambiente, Szenenbilder, optional Sprache | Offen |
| **12** | **Assets & Vorlagenbibliothek** | Maps, Portraits, Tokens, Items, Kategorien, Suchfunktion, Import/Export, Lizenznachweise | Offen |
| **13** | **Bedienoberfläche** | Desktop-Layout, Menüs, Andocken von Fenstern, Drag & Drop, Barrierefreiheit, mobil | Offen |
| **14** | **Speichern, Sicherheit & Hosting** | Rollenfilter, Backup/Restore, Steam, Datenschutz, Sessions, Updates, Docker | Server-Eigenbetrieb vorgegeben; Details offen |
| **15** | **Erweiterbarkeit & Zukunft** | Benutzerdefinierte Felder, Genres/Regelsets, Datenexport, Plugin-Schnittstellen, Scripting | Offen |

**Die Reihenfolge ist ein Vorschlag.** Wir können sie jederzeit ändern. Für jedes Thema sammeln wir zuerst Anforderungen und Beispiele und entscheiden dann über den tatsächlichen Funktionsumfang.

---

## 01 – Inventar und Gegenstände: Gesprächsvorlage

### Dokumentierte Entscheidungen

- **01.1 Inventaransicht – BESCHLOSSEN am 11.10.2026:** Variante **C – kombiniertes Inventar**. Spieler können zwischen **Listenansicht** und **Kachelansicht** umschalten. Suche, Filter und Zugriff auf die Ausrüstung sollen in beiden Ansichten möglich sein.
- Die Listen- und Kachelansichten zeigen dieselben Gegenstände; ein Wechsel ändert weder Eigentum noch Itemwerte. Das genaue UI-Styling und die Fenstergrößen bleiben **offen**.
- **01.2 Container und Gruppeninventar – BESCHLOSSEN:** Variante **C – Container und gemeinsames Gruppeninventar**. Charakterinventare, Behälter (z. B. Rucksack, Truhe, Schrank, Fahrzeug-Laderaum), ineinander verschachtelte Behälter sowie ein gemeinsames Gruppenlager sollen vom Gesamtkonzept unterstützt werden. Konkrete Berechtigungen (wer sieht/entnimmt/befüllt welche Behälter), maximale Verschachtelung und Einführung schon im MVP oder später sind **noch offen**.
- **01.3 Gewicht/Traglast – BESCHLOSSEN:** Variante **B – pro Kampagne einstellbar**. Der Spielleiter bestimmt in den Kampagneneinstellungen, ob Gewicht, Traglast und Containerkapazität verwendet werden. Sind die Begrenzungen deaktiviert, kann das Inventar ohne diese Einschränkungen genutzt werden. **Noch offen:** Gewichtseinheit bzw. abstrakte Kapazität, genaue Berechnung bei verschachtelten Behältern und Verhalten bei Überlastung. Ausrüstungsslots und Währungen sind davon getrennte, noch offene Entscheidungen.
- **01.4 Gegenstandstausch – BESCHLOSSEN:** Variante **C – pro Kampagne einstellbar**. Der Spielleiter legt in den Kampagneneinstellungen fest, ob Gegenstände zwischen Spielern ohne zusätzliche Spielleiterfreigabe übertragen werden dürfen oder ob jeder Handel durch den Spielleiter bestätigt werden muss. Im freien Modus bestätigt der Empfänger die Annahme; danach überträgt der Server die Item-Instanz atomar, sodass keine Duplikate entstehen. Im Freigabemodus ist zusätzlich die Zustimmung des Spielleiters erforderlich. **Noch offen:** Ob Drops und gemeinsame Lager dieselben Freigaberegeln verwenden sowie Regeln für gebundene oder nicht handelbare Items.
- **01.5 Inventarfenster – BESCHLOSSEN:** Variante **C – beides möglich**. Das Inventar kann sowohl als Reiter im Charakterbogen als auch in einem separaten, verschiebbaren und größenveränderbaren Fenster geöffnet werden. Mehrere Inventarfenster dürfen parallel geöffnet sein, etwa Charakterinventar und Truhe, um Gegenstände zwischen ihnen zu bewegen. Beide Darstellungen greifen auf denselben aktuellen Inventarzustand zu; Änderungen werden gemeinsam synchronisiert. **Noch offen:** konkrete Fensteranordnung, Andocken und Speicherung der persönlichen Fensterpositionen.
- **01.6 Ausrüstungsplätze – BESCHLOSSEN:** Variante **C – optional und frei konfigurierbar**. Pro Charakterbogenvorlage bzw. Regelsystem können Spielleiter eigene Ausrüstungsslots mit passenden Namen und erlaubten Gegenstandstypen definieren (z. B. Helm/Hand, Cyberimplantate, Raumschiffmodule) oder Ausrüstungsslots vollständig deaktivieren. Ohne Slots verbleiben Gegenstände im Inventar, ohne dass eine feste Ausrüstungsmechanik vorausgesetzt wird. **Noch offen:** Anzahl von Slots, Mehrfachbelegung, Gegenstandsgrößen und Konfliktregeln.
- **01.7 Gegenstandseffekte – BESCHLOSSEN:** Variante **C – manuelle und automatische Effekte kombinierbar**. Der Spielleiter legt je Gegenstand fest, welche Effekte nur beschrieben und welche automatisch auf Charakterwerte/Fähigkeiten angewendet werden. Temporäre Effekte werden ausdrücklich unterstützt: **(a) echtzeit-/zeitbasiert**, z. B. 30 Sekunden oder 10 Minuten; **(b) rundenbasiert**, z. B. drei Kampfrunden. Der jeweils gewählte Timer-Typ und die verbleibende Laufzeit müssen angezeigt und dauerhaft gespeichert werden. Wenn die Laufzeit endet, wird der Effekt entfernt bzw. deaktiviert und seine automatischen Auswirkungen entfallen. Basiswerte werden nicht dauerhaft überschrieben.
- **Begrenzte Verwendungen und Munition – BESCHLOSSEN:** Gegenstände können eigene Verbrauchszähler mit aktuellen und maximalen Werten haben. Beispiele: **Feuerballstab mit 3/3 Ladungen** (eine Ladung pro tatsächlicher Feuerball-Anwendung) und **Gewehr mit 27/27 Schuss im Magazin** (Schüsse reduzieren die verfügbare Munition). Nutzung muss serverseitig geprüft und der Verbrauch konsistent für alle berechtigten Teilnehmer gespeichert werden. Bei 0 ist die entsprechende Aktion bis zum Wiederaufladen/Nachladen blockiert. **Offen:** konkrete Reservemunition, Magazinwechsel, Burst-/Mehrfachschüsse und deren Regelsystem-Kosten. Wiederherstellungsarten sind in 01.8 festgelegt.
- **Zeit- und Rundenzählung – Detailregeln noch offen:** Startzeitpunkt beim Auslösen, Pausen/Offline-Zeit bei Echtzeit-Effekten, Rundenbeginn/-ende als Ablaufauslöser, manuelles Spielleiter-Override und Stapelregeln werden später separat festgelegt. Es wird keine Timer-Semantik stillschweigend vorausgesetzt.
- **01.8 Nachladen / Wiederaufladen – BESCHLOSSEN:** Variante **C – pro Gegenstand konfigurierbar**. Für jeden Gegenstand bzw. dessen Vorlage kann der Spielleiter eine Wiederherstellungsregel wählen: **manuell**, **durch Verbrauch von passender Reservemunition bzw. Wechsel eines Magazins**, **nach Ablauf einer Zeit**, **nach einer definierten Anzahl von Spielrunden**, **nach einer Ruhepause / einem vom Spielleiter auslösbaren Ereignis** oder **gar nicht (endlich verbrauchbar)**. Dabei sind u. a. aktueller/maximaler Vorrat, gegebenenfalls Munitionstyp und Auslösebedingungen getrennt zu speichern. Nicht alle Gegenstände müssen eine Wiederherstellungsregel besitzen.
- **Offene Details für die technische Planung:** Was zählt als Ruhepause? Erfolgt die automatische Wiederherstellung vollständig oder teilweise? Wie lange dauert Nachladen als Spielaktion? Wie viel Reservemunition liegt im Inventar? Werden Magazin und Ersatzmagazine als eigene Items geführt? Wann startet ein Zeit-/Rundentrigger? Diese Punkte dürfen später je Regelprofil bzw. Gegenstand festgelegt werden. Serverseitige Validierung muss unzulässiges Überfüllen, negatives Guthaben und doppelte Verbrauchsbuchungen verhindern.
- **01.9 Währungen und Geldverwaltung – BESCHLOSSEN:** Variante **C – pro Kampagne frei konfigurierbar und vollständig deaktivierbar**. Der Spielleiter kann eigene Währungen mit Name, Kürzel/Symbol und Darstellung definieren, z. B. Gold, Silber, Credits, Euro, Handelsmarken oder abstrakte Punkte. Es gibt kein fest vorgeschriebenes Genre-Währungssystem. Individuelle Guthaben und eine optionale gemeinsame Gruppenkasse sind vorgesehen; Übertragungen zwischen Charakteren und Gruppenkasse benötigen serverseitige Berechtigungs- und Bestandsprüfung. **Mögliche Erweiterungen:** freiwillig festgelegte Umrechnungskurse zwischen Kampagnenwährungen, Transaktionsprotokoll und Zahlungen aus Handelsaktionen. **Noch offen:** Soll Umrechnung automatisch stattfinden, wer verwaltet die Gruppenkasse, welche Wertegenauigkeit und Minus-Beträge sind zulässig, und gehören Geldmünzen zusätzlich als physische Items zum Inventar?
- **01.10 Containerrechte und interaktive Schlösser – BESCHLOSSEN:** Variante **C – Rechte je Behälter individuell konfigurierbar**. Der Spielleiter bestimmt pro Truhe, Rucksack, Schrank, Gruppenlager, Fahrzeug-Laderaum oder vergleichbarem Objekt getrennt, wer es **sehen**, **öffnen**, **befüllen** oder **Gegenstände entnehmen** darf. Diese Rechte werden serverseitig durchgesetzt, unabhängig von der Anzeige im Browser.
- **Storygebundene Zugangsmittel – zusätzlich BESCHLOSSEN:** Optional kann ein Container verschlossen werden und einen **Schlüssel als Gegenstand**, eine **Keycard/Zugangskarte als Gegenstand** oder einen **echten eingabepflichtigen Zahlencode bzw. Textcode** benötigen. Der Spielleiter kann die Zugangsmittel bzw. Hinweise in Beute, Notizen, NPC-Dialogen, Quests, Dokumenten oder Rätseln verstecken. Ein Spieler findet oder erschließt den Code im Verlauf der Geschichte und gibt ihn in ein **tatsächlich bedienbares Code-Eingabefeld** ein; ein korrekter Code entriegelt, ein falscher wird abgelehnt. Schlüssel und Karten werden nach den festgelegten Berechtigungen im Charakter-/Gruppeninventar geprüft.
- **Technische Grundsätze (mit 01.14 erweitert):** Ein **Schloss ist eine separat konfigurierbare Komponente eines beliebigen interaktiven Weltobjekts**, nicht ausschließlich eines Containers. Zugriffsrechte und Schlosszustand sind voneinander getrennt. Codes und geheime Berechtigungen dürfen nicht an unberechtigte Spieler-Browser übertragen werden; Eingaben, Schlüssel/Karten, Fehlversuche, Sperrzustände und Ratenbegrenzungen werden serverseitig geprüft. Spielleiter können Schlösser verwalten und notfalls öffnen. Das System muss für **Türen, Tore, Fahrzeuge, Terminals, Tresore, Truhen und weitere Szeneobjekte** funktionieren.
- **Noch offen nach 01.11:** Sind Schlüssel/Keycards verbrauchbar, sind mehrere Zugangsmittel alternatives „oder“ bzw. kombiniertes „und“, braucht das bloße Anzeigen eines Behälters eine zusätzliche Berechtigung und dürfen bereits bekannte Codes von allen Charakteren benutzt werden? Die Folgen falscher Codeeingaben sind grundsätzlich festgelegt, aber genaue Zähler-/Reset-Regeln bleiben offen.
- **01.11 Wiederverriegelung – BESCHLOSSEN:** Variante **C – je Schloss konfigurierbar**. Der Spielleiter wählt, ob ein erfolgreich entriegeltes Schloss **dauerhaft entriegelt** bleibt, **beim Schließen** wieder verriegelt wird oder **nach einer einstellbaren Zeit** wieder zusperrt. Der offene/geschlossene Zustand des Behälters und der verriegelte/entriegelte Zustand des Schlosses sind getrennt zu führen. Timer bzw. Status bleiben bei Reconnect und Neustart des Spielservers nachvollziehbar; Details des Pausierens sind noch offen.
- **01.11 Fehlversuche und Story-Folgen – zusätzlich BESCHLOSSEN:** Schlösser mit tatsächlich einzugebenden Codes erhalten **optional konfigurierbare Fehlversuchszähler** und **Ereignisse bei Schwellenwerten**. Der Spielleiter legt pro Schloss beispielsweise **maximal drei falsche Codes** fest und wählt die Konsequenz aus. Beim dritten falschen Versuch kann der Behälter eine **Explosion als In-Game-Ereignis** auslösen (sichtbarer Effekt, optionaler Schaden und Zustandsänderungen nach dem aktivierten Regelprofil). Andere Folgen wie **Alarm**, **zeitweilige Sperre**, **dauerhaftes Blockieren**, **Falle/Status-Effekt** oder **NPC-Verstärkung** sollen ebenfalls als auswählbare Ereignistypen vorgesehen werden. Die konkrete Schadenshöhe, Zielauswahl und Grafik sind noch zu planen.
- **Designanforderungen für Fehlversuche:** Der Server prüft den Code, zählt tatsächlich gültige Eingabeversuche und steuert die Folge **genau einmal** beim Erreichen des Schwellwerts; wiederholte Anfragen dürfen nicht zu mehreren Explosionen führen. Geheimcodes bleiben serverseitig und werden nicht in reguläre Client-Daten oder öffentliche Logs aufgenommen. Nach einem Auslöser sehen die berechtigten Spieler das Ereignis auf dem Spielfeld; der Spielleiter kann es verwalten und gegebenenfalls zurücksetzen. Spielrelevanter Fehlversuchszähler und technische Missbrauchsbegrenzung (Rate-Limit) sind zwei verschiedene Mechanismen.
- **Offen für die Detailplanung (aktualisiert nach 01.13/01.14):** Kombinierbarkeit der nun festgelegten Resetoptionen, mehrere Fehlversuchs-Schwellenwerte, Sichtbarkeit verbleibender Versuche, Identitätsschlüssel bei getrennten Zählern (Spielerkonto oder Charakter) und Verhalten bei gleichzeitigen Eingaben. Ob eine konkrete Falle wieder scharfgestellt werden kann, ist **grundsätzlich pro Falle konfigurierbar**; Details zu Auslöserkombinationen und Effekten bleiben offen.
- **01.12 Zählweise von Code-Fehlversuchen – BESCHLOSSEN:** Variante **C – pro Schloss konfigurierbar**. Der Spielleiter wählt für jedes Codeschloss: **gemeinsamer Zähler über alle Spieler** oder **getrennte Fehlversuchszähler pro Spieler**. Beispiel für gemeinsame Zählung: Drei unterschiedliche Spieler geben jeweils einen falschen Code ein; nach dem dritten falschen Versuch wird die konfigurierte Folge ausgelöst. Beispiel für getrennte Zählung: Jeder Spieler besitzt sein eigenes Budget von drei Fehlversuchen. Die konfigurierte Folge ist beim Erreichen des jeweiligen Schwellwerts möglich; für eine Explosion gilt weiterhin: ein einzelner Auslösevorgang darf nicht mehrfach ausgeführt werden. Ob ein Schloss/eine Falle später neu scharfgeschaltet werden kann, bleibt offen.
- **Technische Konsequenzen:** Autoritative, persistente Fehlversuchszähler je Schloss, mit optionalem Unterzähler pro Spieler; atomare Verarbeitung gleichzeitiger Eingaben, eindeutige Anfragen und idempotente Auslösung von Folgen. Das Spielsystem darf den Code oder geheime Schwellwerte nicht an unberechtigte Browser ausliefern; sichtbare Warnungen sind eine separate Spielleiter-Einstellung.
- **01.13 Fehlversuche zurücksetzen – BESCHLOSSEN:** Variante **C – je Schloss konfigurierbar**. Der Spielleiter kann pro Codeschloss eine geeignete Rücksetzbedingung für die Fehlversuchszähler festlegen: **nur manuell durch den Spielleiter**, **nach einer definierten Echtzeitdauer**, **nach einer festgelegten Anzahl Spielrunden**, **bei erfolgreicher Codeeingabe**, **durch ein Story-Ereignis** oder **kein automatischer Reset**. Welche Auslöser miteinander kombiniert werden dürfen und wie Echtzeit-Timer beim Pausieren/Offline-Betrieb laufen, klären wir später. Zählertyp aus 01.12 (gemeinsam oder pro Spieler) muss berücksichtigt werden. Rücksetzungen und Restwerte sind serverseitig nachvollziehbar und persistent.
- **Wichtige Trennung:** Das Zurücksetzen des Zählers ist **nicht** automatisch eine erneute Aktivierung einer ausgelösten Falle. Gerade bei einer Explosion dürfen nach einem simplen Zählerreset keine ungewollten zweiten Explosionen auftreten. Ein eigenes Konzept für den **Scharf-/Ausgelöst-Zustand** einer Falle ist erforderlich.
- **01.14 Fallen-Reaktivierung – BESCHLOSSEN:** Variante **C – pro Falle konfigurierbar**. Eine Falle kann **einmalig** sein, nach einer **Echtzeitdauer** oder festgelegten **Spielrunden** automatisch erneut scharf werden, durch ein **Story-Ereignis** erneut scharf werden oder durch den **Spielleiter manuell** reaktiviert werden. Die Wiederherstellung der Fehlversuche (01.13) und das erneute Scharfstellen einer Falle bleiben zwei voneinander **unabhängige Zustände**. Eine ausgelöste Falle darf nur nach ihrer konfigurierten Reaktivierung erneut auslösen.
- **01.14 Universelles Schloss- und Fallensystem – zusätzlich BESCHLOSSEN:** **Schlösser, Zugangsmittel, Codeeingaben, Fehlversuchszähler, Zurücksetzen, Konsequenzen und Fallen** sollen **nicht nur bei Containern**, sondern auch an **Türen, Toren, Fahrzeugen, Fahrzeugzugängen, Terminals, Tresoren und sonstigen interaktiven Szenenobjekten** verwendet werden können. Beispiel: Ein Türcode löst nach drei Fehlversuchen einen Alarm aus; ein Fahrzeug kann eine Keycard erfordern und nach falschen Codes verriegeln; eine Truhe kann einmalig explodieren. Auch **eigenständige Fallen** ohne zwingend vorgeschaltetes Schloss sollen im Konzept vorgesehen werden; deren Auslöser (Betreten, Berühren, Benutzen usw.) werden gesondert geplant.
- **Einheitliche Zugangseinstellungen – BESCHLOSSEN:** Ein einzelnes Objekt kann Zahl-/Textcode, Schlüsselgegenstand, Keycard und passende weitere Methoden anbieten. Für jede Codeeingabe gelten die Mechanismen aus **01.10–01.13** (Fehlversuchszähler, Folgen, Rücksetzung und Wiederverriegelung). **Mit 01.15 ist auch die freie Kombination der Methoden ausdrücklich beschlossen** (ODER, UND sowie mehrstufige Abfolgen).
- **Technische Konsequenzen (Planung):** Objekt (z. B. Tür/Fahrzeug/Container), Zugangsregeln, Schlosszustand, Versuchszähler, Fallenstatus und Folgeereignisse als getrennte, wiederverwendbare Datenkomponenten. Autoritative Prüfung am Server, geheime Codes und Fallen nur für Berechtigte, persistente Timer/Status, atomare Prüfung und **idempotente Auslösung** (keine unbeabsichtigte Mehrfachexplosion bei wiederholten oder parallelen Anfragen). Auswirkungen wie Schaden, Alarm, blockierte Tür, Fahrzeugschaden oder Gegner-Spawn werden später durch Regel-/Ereignismodule ausgestaltet.
- **Offen nach 01.15:** Verbrauch/Nutzungsbeschränkungen von Schlüsseln und Keycards, exakte Regeln für Fortschritt und Abbruch mehrstufiger Zugänge, Details zur Fallenreaktivierung, eigenständige Fallen-Auslöser, Reparatur/Entschärfung, Schadensberechnung und Sichtbarkeit von Warnungen.
- **01.15 Kombination von Zugangsmethoden – BESCHLOSSEN:** Variante **C – pro Objekt vollständig konfigurierbar**. Der Spielleiter kann mehrere Methoden als **Alternative (ODER)** oder **gemeinsam erforderlich (UND)** definieren sowie **aufeinanderfolgende Stufen** festlegen. Beispiele: Tür mit **Keycard ODER Code**; Hochsicherheitstresor mit **Keycard UND Code**; Raumschiffzugang mit **zuerst Schlüsselkarte, danach Code, anschließend Freigabe durch eine weitere Berechtigung**. Eine objektbezogene Konfiguration soll diese Varianten ohne eigenen Programmcode für Türen, Fahrzeuge, Container und Terminals ermöglichen.
- **Technische Planung zu 01.15:** Zugang als Regelstruktur mit Methoden, Verknüpfungen und optionaler Reihenfolge modellieren; serverseitig prüfen, welche Stufe erfüllt wurde, welche noch offen ist und wer sie erfüllen darf. Codes und verborgene Bedingungen bleiben vertraulich. Ein fehlgeschlagener Codeschritt verwendet die zuvor beschlossenen Fehlversuchs- und Fallenregeln des betroffenen Schlosses. Gleichzeitige Interaktionen dürfen keinen unberechtigten Zugang ermöglichen. **Offen:** Dürfen verschiedene Spieler nacheinander unterschiedliche Stufen erfüllen, wie lange bleibt ein Zwischenschritt gültig, wie wird der Fortschritt nach Fehlern/Neustart zurückgesetzt?
- **01.16 Nutzungsregeln für Schlüssel und Keycards – BESCHLOSSEN:** Variante **C – pro Zugangsmittel frei konfigurierbar**. Ein Schlüssel, eine Keycard oder ein vergleichbares Zugangs-Item kann **unbegrenzt wiederverwendbar**, **nur einmal nutzbar**, auf eine **festgelegte maximale Zahl erfolgreicher Nutzungen** (z. B. 3/3) oder auf eine **Gültigkeitsdauer** (z. B. 30 Minuten) begrenzt sein. Kombinationen (z. B. fünf Anwendungen innerhalb von 24 Stunden) sind ebenfalls möglich. Spielleiter können die Regeln über die Item-Vorlage festlegen; individuelle Item-Instanzen besitzen ihren aktuellen Restbestand und Gültigkeitsstatus. Das vorhandene generische Ressourcen-/Ladungssystem aus 01.7/01.8 soll dafür wiederverwendet werden.
- **Sichere Nutzung:** Der Server prüft Besitz/Berechtigung, Gültigkeit und verbleibende Nutzungen im Rahmen der Zugangskontrolle. Verbrauch erst bei **erfolgreicher** Nutzung, nicht wegen eines fehlgeschlagenen oder wiederholten Aufrufs. Ein abgelaufenes oder ausgeschöpftes Zugangsmittel darf keine neuen Zugänge freischalten. Der Zugriff auf andere Zugangswege (z. B. Code ODER Keycard) bleibt davon unberührt.
- **Für die Abschlussplanung noch offen:** Bleibt eine ungültige/verwendete Karte im Inventar oder wird sie entfernt? Lassen sich Karten neu aufladen bzw. ihre Gültigkeit verlängern? Beginnt die Gültigkeitsdauer beim Finden, Aktivieren oder ersten Benutzen? Wie lange laufen Timer bei pausierter Kampagne/Offline-Server? Welche Anzeige/Berechtigung erhalten Spieler? Keine dieser Detailentscheidungen ist bisher verbindlich.
- **Inventar-Workshop – fachliche Grundentscheidungen 01.1–01.16 durchlaufen.** Ausstehende Spezialfragen werden in einer späteren Detailrunde geklärt (z. B. tief verschachtelte Container, Slots, Geldumtausch, Timersemantik, mehrstufiger Zugang und Zugangsmittellebensdauer). Wir wechseln nun wie gewünscht zum Karten- und Szenensystem, bevor eine technische Umsetzung beschlossen wird.
- **Nächster Hauptbereich 02 – Karten & Szenen, Entscheidung 02.1:** Wie sollen Karten erstellt werden – Bildimport, integrierter Editor oder **beides**?

### A. Wie sieht es im Browser aus?

**Mögliche Darstellung:**
- **Liste:** kompakt und gut bei vielen Objekten; Spalten für Name, Anzahl, Gewicht/Tags, Aktionen.
- **Kachelraster:** große Item-Icons, intuitives Ziehen; braucht mehr Platz.
- **Kombination (Empfehlung):** Umschalten zwischen Liste und Kacheln; Suche, Filter, Sortierung; Charakterbogen rechts als eigenes Fenster/Panel.

**Genrebeispiele:** Zauberschwert, Cyberdeck, Pistole, Medkit, Schlüsselkarte, Fahrzeugersatzteil, steampunkartiges Werkzeug und Dokument; **keine** systemseitige Pflicht für Waffen- oder Rüstungswerte.

### B. Wo liegen Gegenstände?

- Beim **Charakter** im Inventar.
- In **Containern** (Rucksack, Truhe, Fahrzeug-Laderaum), optional mit individuell konfigurierten Rechten und interaktiven Schlössern (Schlüssel, Keycard, eingegebener Code).
- **Auf dem Spielfeld** als Bodenbeute.
- In einem **gemeinsamen Gruppenlager** (optional).
- Bei einem **NPC/Gegner** (ggf. geheim).
- In der **Vorlagenbibliothek**, wenn noch keine konkrete Instanz erzeugt wurde.

**Entwurfsprinzip:** Eine Item-Vorlage (Definition, Icon und erlaubte Effekte) ist nicht dieselbe Sache wie eine Item-Instanz (Besitzer, Fundort, Menge, individuelle Werte). Transfer gehört auf den Server und muss atomar sein.

### C. Interaktionen

- Fund/Beute ansehen; **Aufnehmen, Ablegen, Ziehen, Übergeben, Ausrüsten/Abnehmen**.
- Stapelbar oder einmalig; Chargen/Verbrauch; optional Haltbarkeit. **Beschlossen:** Ladungen und Munition als aktuelle/maximale Zähler, z. B. Feuerballstab (3/3) oder Gewehrmagazin (27/27).
- Wählbare Regeln zu Gewicht, Volumen, Kapazität oder **keine Traglast**.
- **Beschlossen 01.9:** Frei definierbare, bei Bedarf deaktivierbare Kampagnenwährungen und optionale Gruppenkasse; mögliche Wechselkurse bleiben Detailentscheidung.
- „Unbekannter Gegenstand“: Der SL kann Details bis zur Identifikation verbergen.
- Optional konfigurierbare Ausrüstungsslots, z. B. Hände, Kopf, Cyberimplantate oder freie Slots.
- **Beschlossen:** Effekte können rein beschreibend oder automatisch sein und auch zeitlich (Sekunden/Minuten) oder rundenbasiert ablaufen. Abgeleitete Werte ändern sich während der Wirkung; Basiswerte bleiben erhalten. Für Ladungen/Schüsse wird der Verbrauch serverseitig geprüft.

### D. Offene Entscheidungen für dieses Thema

1. **Entschieden:** Kombinierte Liste/Kachel-Darstellung (Variante C), umschaltbar mit Suche/Filtern/Ausrüstungszugriff.
2. **Entschieden (Konzept):** Verschachtelte Container und gemeinsames Gruppenlager werden unterstützt; Umsetzungstermin/Berechtigungen noch offen.
3. **Teilweise entschieden:** Gewicht, Traglast und Containerkapazität sind pro Kampagne optional (01.3 B); Ausrüstungsplätze sind optional und frei pro Charakterbogenvorlage definierbar (01.6 C); Währungen sind pro Kampagne frei konfigurierbar oder deaktivierbar (01.9 C). Details von Traglast und Geldtransfer bleiben offen.
4. **Entschieden:** Gegenstandstausch ist pro Kampagne konfigurierbar (Variante C); Empfangsbestätigung und ggf. SL-Freigabe gehören zum Ablauf.
5. **Entschieden:** Inventar als Reiter im Charakterbogen **und** als separates verschiebbares, skalierbares Fenster; mehrere Inventare gleichzeitig möglich (Variante C).
6. **Entschieden:** Itemeffekte als Kombination aus manuell und automatisch (01.7 C), temporäre Laufzeiten sowohl in Echtzeit als auch Spielrunden, begrenzte Nutzungen und Munition.
7. **Entschieden:** Verbrauchte Ladungen und Munition können pro Gegenstand manuell, durch Nachladen, Zeit-/Rundenablauf, Ruhepause/Ereignis oder gar nicht wiederhergestellt werden (01.8 C); genaue Trigger- und Mengenregeln bleiben offen.
8. **Entschieden:** Pro Kampagne frei definierbare oder abschaltbare Währungen, optional mit Gruppenkasse (01.9 C); genaue Wechselkurs- und Guthabenregeln offen.
9. **Entschieden:** Individuelle Rechte für Sicht, Öffnen, Befüllen und Entnehmen pro Container sowie optionale Schlüssel/Keycards und tatsächlich eingegebene Story-Codes (01.10 C).
10. **Entschieden:** Schlossverhalten pro Objekt einstellbar: dauerhaft offen, beim Schließen verriegeln oder nach einer Zeit (01.11 C). Ebenfalls beschlossen: konfigurierbare Fehlversuche mit Story-Folgen, z. B. einmalige Explosion nach drei falschen Codes.
11. **Entschieden:** Fehlversuche je Schloss entweder gemeinsam für alle oder separat pro Spieler zählen (01.12 C); serverseitig und persistent.
12. **Entschieden:** Fehlversuchszähler je Schloss durch den Spielleiter, Zeit, Runden, erfolgreichen Code oder Story-Ereignis zurücksetzen lassen (01.13 C); die Falle wird dadurch nicht automatisch neu scharfgestellt.
13. **Entschieden:** Fallen sind pro Falle einmalig oder automatisch/nach Story-Ereignis/manuell reaktivierbar (01.14 C); Wiederaktivierung ist unabhängig vom Fehlversuchsreset.
14. **Entschieden:** Universelles Zugangs- und Fallensystem für Türen, Fahrzeuge, Terminals, Truhen und andere Weltobjekte; Zugang via Code/Schlüssel/Keycard und Fehlversuche auch außerhalb von Containern (01.14).
15. **Entschieden:** Zugangsmethoden als ODER, UND und geordnete mehrstufige Prüfungen pro Objekt konfigurierbar (01.15 C).
16. **Entschieden:** Wiederverwendbare, einmalige, begrenzt nutzbare und zeitlich begrenzte Schlüssel/Keycards, auch kombinierbar, pro Zugangsmittel konfigurierbar (01.16 C). Details zur Entwertung/Timersemantik offen.
17. **Nächster Hauptbereich:** Karten & Szenen – zuerst 02.1 Kartenerstellung.

**Aktueller Gesprächsstand:** Inventar 01.1–01.2 C, 01.3 B, 01.4–01.16 C. **01.16 C = freie Nutzungsanzahl und Gültigkeitsdauer für Schlüssel/Keycards**. Der Inventarbereich ist auf Ebene der Hauptentscheidungen besprochen; explizit genannte Detailfragen bleiben offen. **Nächstes Thema: 02 – Kartenerstellung und Szenen.**

### E. Vorläufige technische Folgerungen (noch nicht festgelegt)

Objektvorlagen, Item-Instanzen, Speicherorte/Container, optionales Slot-/Effektmodell, Rechteprüfung, serverseitige Transfer-Transaktionen und eine konfigurierbare UI.

---

## 02 – Karten und Szenen: Gesprächsvorlage

### Dokumentierte Entscheidungen zum Kartenbereich

- **02.1 Kartenerstellung – BESCHLOSSEN:** Variante **C – beide Wege**. Spielleiter können fertige Kartenbilder importieren **und** eigene Karten direkt im Browser von AdventureShift erstellen. Importierte Karten lassen sich innerhalb der Szene mit interaktiven Elementen wie Türen, Schlössern, Fallen, Tokens, Notizen und Objekten ergänzen. Das gilt genreunabhängig für Fantasy, Cyberpunk, Steampunk und andere Settings.
- **Bewusste Trennung:** (1) Kartenbild/Asset, (2) bearbeitbare Szene mit Position, Raster und Maßstab, (3) platzierte interaktive Objekte/Layers. Ein importiertes Bild soll beim Hinzufügen von Objekten nicht destruktiv verändert werden; ob ein Export als flaches Bild angeboten wird, ist noch offen.
- **02.2 Umfang Karteneditor – BESCHLOSSEN:** Variante **C – Schnellmodus und erweiterter Baumodus**. Der **Schnellmodus** soll spontane Skizzen über einfache Zeichenwerkzeuge ermöglichen (Freihandlinien, Rechtecke, Kreise, Text, Farben und einfache Symbole). Der **Baumodus** soll umfassendere Karten aus Bauteilen und Objekten (z. B. Böden, Wände, Räume, Türen, Straßen, Möbel, Dekoration und genreübergreifende Asset-Bibliothek) mit Ebenenverwaltung ermöglichen. **Beide Modi bearbeiten dieselbe Karte/Szene**, sodass zwischen ihnen ohne Neuerstellung oder Datenverlust gewechselt werden kann.
- **Geplanter Ablauf:** Für improvisierte Situationen direkt skizzieren; später dieselbe Szene mit Bauteilen, Dekoration und interaktiven Weltobjekten ergänzen. Der Baumodus darf den Schnellmodus nicht ersetzen und der Schnellmodus soll vorhandene Bauteile nicht unbeabsichtigt entfernen.
- **Technische Planungsfolgen:** Ein einheitliches editierbares Szenenmodell mit separaten Daten für Freihand-/Vektor-Zeichnungen, Bauteil-/Tile-Instanzen, importierte Kartenbilder und interaktive Objekte. Ebenen, Reihenfolge, Bearbeitungsrechte und mindestens grundlegende Rückgängig-Funktionen sind einzuplanen; genauen Umfang, Bibliotheken, Format und Startversion später abstimmen.
- **Weiterhin offen:** Unterstützte Importformate jenseits von PNG/JPG/WebP, konkrete Bauwerkzeuge/Automatik, Kartenexport, gemeinsames gleichzeitiges Editieren, Assets und Lizenzrechte, UI/Hotkeys und stufenweise Implementierungsreihenfolge.
- **Nächster Entscheidungspunkt 02.3:** Welche **Szenentypen** brauchen wir – nur taktische Top-down-Karten, zusätzlich Story-/Atmosphäre-Szenen oder flexibel wählbare Taktik-, Reise-/Weltkarten-, Story- und freie Spieltisch-Szenen?

### Mögliche Wege zur Kartenerstellung (die Optionen hier sind Ideensammlung, kein neuer Beschluss)

### Grundsatz: Kartenbild ≠ Szene ≠ spielbare Objekte

- **Kartenbild:** JPG/PNG/WebP-Grafik (z. B. Stadtkarte, Raumschiffdeck).
- **Szene:** Spielraum-Ausschnitt mit einem oder mehreren Kartenbildern, Rastereinstellungen, Kamera, Bereichen/Orten.
- **Objekte:** Tokens, Türen, Möbel, Beute, SL-Marker, Nebel, Licht und interaktive Auslöser.

### Wie entstehen Karten?

**Weg A (einfach, sofort nutzbar – Empfehlung für erste Version):** SL lädt fertiges Bild hoch, richtet Maßstab/Raster aus und platziert Tokens, Notizen und einfache Formen.

**Weg B (leichter In-App-Editor):** SL baut auf leerer Fläche mit Grundformen, Linien, Texten, farbigen Flächen, Stempeln und frei platzierbaren Objekten eine Karte. Keine komplexe Terrain-Engine.

**Weg C (vollständiger Karteneditor – spätere Ausbaustufe):** Kachel-/Tile-Editor mit Böden, Wänden, Räumen, Dekoration, automatisch ausgerichteten Türen und Export/Vorlagen.

**Weg D (externer Editor):** Karten aus Inkarnate, Dungeon Alchemist, Dungeondraft oder eigenen Grafikprogrammen als Bild importieren. Später ggf. `.dd2vtt` / `.uvtt` mit Metadaten für Wände und Licht; Formatgenauigkeit prüfen.

### Kartentypen

- **Taktik:** kleine Battle Map (Quadrat/Hex/frei), Reichweite und Bewegung.
- **Erkundung:** große Dungeon- oder Stadtkarte mit Fog/Entdeckung.
- **Weltkarte:** Reise und Ortsmarker, keine Einzelfeldbewegung nötig.
- **Atmosphäre/Story:** Panorama oder Szenenbild, Musik, Handout, Figurenportraits, keine taktische Karte notwendig.
- **Freier Tisch:** leere Zeichenfläche für improvisierte Situationen.

### Ebenen-Vorschlag

1. Hintergrundbilder/Kartenteile.
2. Gelände, Dekoration und statische Objekte.
3. Unsichtbare Logik: Wände, Türen, Kollision, Sichtlinien (optional).
4. Tokens, Fahrzeuge, Kreaturen, frei bewegliche Objekte.
5. SL-Geheimnisse, getrennte Berechtigung.
6. Nebel, Licht, Effekte und Zeichnungen/Markierungen (logische Render-Reihenfolge später klären).

### Offene Karten-Entscheidungen

- **02.1 entschieden:** Bildimport und selbst erstellte Karten im Browser sind beides vorgesehen.
- **02.2 entschieden:** Schnellmodus für Zeichnungen und erweiterter Baumodus mit Tiles/Objekten bearbeiten dieselbe Karte (Variante C). Werkzeugdetails bleiben offen.
- **02.3 als Nächstes:** Nur 2D-Top-down oder zusätzlich Story-Szenen, Reise-/Weltkarten und freie Spieltische?
- Reichen Bildimport und einfache Zeichenwerkzeuge für die erste Version?
- Raster wählbar: kein Raster, Quadrat, Hex – und Maßstab (Meter/Fuß/frei)?
- Sicht: manuell aufdeckbarer Nebel oder dynamische Sicht pro Token?
- Dürfen mehrere Karten nebeneinander in einer Szene liegen?
- Welche Interaktionen: Türen öffnen, Beute in Kisten, Teleportfelder, Notizmarker?
- Kartenentwürfe privat für den SL, erst bei Aktivierung für Spieler sichtbar?
- Wie importieren wir externe Kartendaten und dokumentieren die Rechte der Nutzer-Assets?

### Vorläufige technische Folgerungen

Reine Bildspeicherung genügt nicht: Szenen-Metadaten, Raster-/Maßstab, Layer-Objekte, serverseitige Sichtbarkeitsregeln, Objekt-IDs und eigene Speicherformate werden benötigt. **Beschlossen 02.1:** Importierte Bild-Assets und direkt im Browser editierbare Karten/Szenen sind zwei unterstützte Erstellungswege. **Beschlossen 02.2:** Schnellmodus und Baumodus benötigen ein gemeinsames bearbeitbares Szenenmodell; konkrete Werkzeuge, Versionierung und MVP-Zeitpunkt bleiben offen.

---

## 03–15 – Leitfragen für die späteren Gesprächsrunden

### 03 Charakterbögen
Frei definierte Feldtypen (Text, Zahl, Schalter, Ressourcen, Auswahl, Würfelaktion)? Wer erstellt Templates? Wie viel dürfen Spieler ändern? Sind mehrere Charaktere pro Spieler sinnvoll? Aussehen: kompakte Seitenleiste oder umfassendes Blatt?

### 04 Tokens und Bewegung
Freier Drag, Klickziel, gemeinsamer Routen-Vorschlag oder Kampf-Zugbudget? Quadrat/Hex/freier Modus? Größen/Rotation, Fahrzeuge und Reittiere? Darf der SL Figuren sperren oder ziehen?

### 05 Würfel
W4 bis W100, Würfelpools, automatische Proben, Erfolgszählung? Animierte Würfel zentral oder bei der Figur? Sichtbar, geheim oder geflüstert? Serververbindliche Werte, gemeinsames unveränderbares Log.

### 06 NPCs und Gegner
NPC-Datenbank und Tokenbibliothek, einfache SL-Steuerung, Status, Dialognotizen, Gegner-Templates, Beute, Geheimdaten; später Automatik.

### 07 Regelmodule
Einfacher Sandbox-Modus ohne automatische Regeln; pro Kampagne Regeln zuschaltbar. Beispiele: Initiative, Aktionskosten, Ressourcen, Angriff/Verteidigung. Versionierte Profile; keine ungesicherten Nutzerskripte.

### 08 Spielleiter-Werkzeuge
Szenen-vorab-Editor, versteckte Tokens, Nebel, Türen und Licht, nur SL lesbare Notizen, Gruppenfunktionen, Spielersicht-Vorschau, Undo.

### 09 Kampagnen und Lobby
Steam-Login, Einladungen, mehreren Kampagnen beitreten, SL-Rollen, Berechtigungen, Pausieren/Fortsetzen, Vorlagen- und Regelprofil pro Kampagne, ggf. parallele Räume.

### 10 Journal und Handouts
Eigene und geteilte Notizen, Queststatus, Ereignischronik, Kartenmarker, NPC-Dossiers, Bilder/PDF-Handouts, abgestufte Freigabe.

### 11 Kommunikation
In-Game-Textchat, Würfelprotokoll, private Nachrichten, Emotes/Marker/Pings, Musik-Playlist; Voice/Video möglichst zunächst über externe Tools.

### 12 Assets und Bibliothek
Dateiupload, Ordner/Tags/Suche/Versionierung, wiederverwendbare Vorlagen und Karten, Datenexport, Herkunft/Lizenzen, Upload-Berechtigungen, Größenbegrenzungen.

### 13 Oberfläche
Desktop zuerst oder responsive? Fenster/Seitenleisten, anheftbare Popovers, Dark/Light, Tastatur, Hotkeys, Barrierefreiheit, SL-Arbeitsplatz vs. Spielersicht.

### 14 Speichern, Hosting, Sicherheit
PostgreSQL, Medienablage, regelmäßiges Backup, Wiederherstellen, Steam-Session, Rechte und Rechtefilter, Audit, Docker, HTTPS, Updates und Datenschutz.

### 15 Erweiterbarkeit
Regel-/Genrevorlagen, Module/Plugin-APIs, Import/Export, gemeinsame Bibliotheken. Drittanbieter-Scripting nur mit Sicherheits- und Berechtigungskonzept.

---

## Ergebnisdokument am Ende (noch zu erstellen)

Wenn alle Gesprächsrunden abgeschlossen sind, fassen wir die Entscheidungen in **einem verbindlichen Gesamtplan** zusammen:
1. Produktdefinition und Zielgruppen.
2. Verbindliche Feature-Liste mit MVP / später / ausgeschlossen.
3. UI-/UX-Flows und Beispielansichten.
4. Datenobjekte und Beziehungen (Karte/Szene/Token; Template/Item/Inventar; Nutzer/Kampagne/Rollen).
5. Realtime-Events, Rechte, Sichtbarkeit und Sicherheit.
6. Technikentscheidungen, offene Risiken und Serverbedarf.
7. Reihenfolge, Abnahmetests und Zeit-/Komplexitätsabschätzung.

Erst dann wird der vorläufige GitHub-Backlog gegen den abgestimmten Feature-Plan abgeglichen.
