# AdventureShift – Feature-Spezifikation

**Stand:** 11.10.2026  
**Produktname:** AdventureShift (vom Projektinhaber gewählt). Das Repository heißt vorerst weiterhin `Zeiju2/DnD2`.  
**Status:** Vorläufiger Entwurf. Aktuell besprechen wir die einzelnen Funktionen zunächst gemeinsam im [Feature-Workshop](FEATURE-WORKSHOP.md); **Prioritäten, Detailumfang und Entwicklungsstart sind noch nicht final freigegeben**. Noch keine implementierten Funktionen.  
**Produktvision:** Selbst hostbare, browserbasierte, genre- und regelwerksunabhängige Plattform für Pen-&-Paper-Rollenspiele; von Fantasy über Cyberpunk bis Steampunk und Horror.

> Trennung der Aussagen: **Vorgabe** = vom Projektinhaber bereits genannt; **Empfehlung** = vorgeschlagene Umsetzung; **Offen** = noch zu entscheiden. Details sind keine bereits erfolgte Implementierung.

## 1. Produktprinzipien

1. **Beliebige Genres:** Keine Fantasy-, D&D-, Lebenspunkt- oder Klassenpflicht. Kampagne und Spielsystem bestimmen Werte und Regeln.
2. **Menschlicher Spielleiter:** Der Spielleiter moderiert Szenen und kann erzählerische Entscheidungen treffen; Automatisierung soll unterstützen, nicht erzwingen.
3. **Gemeinsamer Zustand:** Alle Teilnehmer sehen zulässige Änderungen live. Der Server entscheidet über gültige Bewegungen, Würfel und Item-Übergänge.
4. **Flexible Regeln:** Basis-Sandbox funktioniert ohne formales Regelwerk; optionale Regelprofile können zusätzliche Prüfungen und Berechnungen aktivieren.
5. **Einfach selbst betreibbar:** Späterer Betrieb auf einem Linux-Server mit Docker Compose, HTTPS, persistenten Daten und Backups.
6. **Sicher nach Rollen:** Spielleiter-Geheimnisse nie ungefiltert an Spieler-Browser schicken.
7. **Planbare Entwicklung:** Erst gemeinsames Spielfeld + Würfel testbar machen, dann Identität, Charaktere und Regeln ergänzen.

## 2. Feature-Katalog

| ID | Modul | Muss-Funktion | Priorität | Zielversion |
| --- | --- | --- | --- | --- |
| AS-01 | Steam-Identität | Steam-Login, sichere Sitzung, SteamID und eigenes Konto | Muss | MVP |
| AS-02 | Kampagnen/Lobby | Erstellen, betreten, Spieler/SL-Rollen pro Kampagne | Muss | MVP |
| AS-03 | Echtzeit-Raum | Verbundene Spieler, Zustands-Sync, Reconnect | Muss | Prototyp/MVP |
| AS-04 | Spielfeld | Karte, Pan/Zoom, Token-Layer, optionales Raster | Muss | Prototyp |
| AS-05 | Bewegung | Eigene Tokens bewegen, SL steuert NPCs; Server validiert | Muss | Prototyp/MVP |
| AS-06 | Gemeinsame Würfel | Spielerwürfe, verbindliches Serverergebnis, gemeinsame Animation + Log | Muss | Prototyp/MVP |
| AS-07 | Charakterbogen | Konfigurierbare Felder und Ressourcen, Zuordnung zu Spieler/Token | Muss | MVP |
| AS-08 | Items & Effekte | Auffinden, Aufheben, Ausrüsten, serverseitige Bonusberechnung | Muss | MVP |
| AS-09 | NPC-/Gegnersteuerung | SL platziert und bewegt eigene Figuren, Werte frei definierbar | Muss | MVP |
| AS-10 | Persistenz | Karten, Charaktere, Inventar und Kampagnen sichern/laden | Muss | MVP |
| AS-11 | Regelprofile | Sandbox + optionale, austauschbare Regeln | Soll (Grundkonzept im MVP) | MVP/1.1 |
| AS-12 | Kampfsystem | Initiative, Züge, Aktionen, Schaden nur bei aktiviertem Regelprofil | Soll | 1.1 |
| AS-13 | Spielleiter-Werkzeuge | Szenenwechsel, Token/Objektverwaltung, SL-Notizen | Soll | 1.1 |
| AS-14 | Sicht/Geheimnisse | Nebel des Krieges und geheime Elemente serverseitig gefiltert | Soll | 1.1 |
| AS-15 | Chat & Journal | Gruppenchat, Würfelhistorie, Quests, Handouts | Soll | 1.1 |
| AS-16 | Karten/Assets | Bild-Uploads, Speicher, Asset-Rechte und Größenlimits | Soll | 1.1 |
| AS-17 | Erweiterte Szenen | Türen, Truhen, Fallen, Ereignis-Trigger | Kann | 2.x |
| AS-18 | Regel- und Inhaltseditor | Benutzerdefinierte Bögen, Items, Effekte, Import/Export | Kann | 2.x |
| AS-19 | Gegner-Automatisierung | Optionale KI/Verhaltensregeln statt SL-Steuerung | Kann | 2.x |
| AS-20 | Betriebsverwaltung | Container, HTTPS, Backup/Restore, Healthchecks und Logs | Muss | MVP |

### AS-01: Steam-Anmeldung und Identität

**Nutzerablauf:** „Mit Steam anmelden“ → Steam bestätigt Identität → AdventureShift ordnet SteamID64 einem eigenen Benutzerkonto zu → Kampagnenübersicht öffnet sich.  
**Anforderungen:** Sitzung sicher mit HttpOnly/Secure; kein Steam-Passwort; Rollen werden **nicht** aus Steam abgeleitet, sondern in der Kampagne vergeben. Steam-Login für Produktivversion, lokale Entwickler-Testidentitäten nur im Entwicklungsmodus.  
**Abnahme:** Nutzer A sieht ohne Mitgliedschaft weder private Kampagnen noch deren geheime Daten; nach Logout sind geschützte APIs/WebSocket-Aktionen gesperrt.

### AS-02/03: Kampagnen, Lobby und gemeinsame Spielräume

- SL erstellt Kampagne mit Titel, optionalem Genre-Label und Basis-Regelprofil („Sandbox“).
- Zugang zunächst über Einladungscode oder Freigabe; Kampagnen sollen nicht automatisch öffentlich sein.
- Mitglied kann pro Kampagne SL oder Spieler sein; dieselbe Person kann in anderen Kampagnen anders berechtigt sein.
- Alle Teilnehmer sehen Liste anwesender Spieler und den aktuellen Spielraum.
- Wiederverbinden synchronisiert den **autoritativen** Zustand neu, keine lokalen Phantombewegungen.
- **Abnahme:** Zwei bis sechs Browser nehmen an derselben Testkampagne teil und sehen in Sekundenbruchteilen bis kurzer Netzlatenz dieselbe freigegebene Karte und Tokenpositionen; kein manuelles Aktualisieren nötig. Exakte Leistungswerte erst messen.

### AS-04/05: Karte und Movement

**Erstes Spielfeld (Prototyp):**
- 2D-Ansicht von oben, Pan, Zoom, platzierbare Tokens, einfache Hintergrundkarte; Quadrat-Raster als **optionale** Ansicht, Freibewegung erlaubt.
- Bewegung per Drag-and-Drop und später Klickziel; Spieler nur mit eigenen Tokens, SL mit allen.
- Server speichert kanonische Positionen und weist ungültige Aktionen zurück.
- Koordinatensystem grundsätzlich unabhängig von Spielregeln.

**Spätere Erweiterungen:** Hex-Raster, Hindernisse/Kollision, Pfadfindung, Reichweitenmessung, Bewegungspunkte und rundenbasiertes Movement als Regelprofile. **Offen:** Welche Bewegungsregel pro Kampagne standardmäßig aktiviert wird.

**Abnahme:** Spieler A verschiebt eigenen Token und Spieler B sieht dieselbe Endposition; B darf fremden Token nicht verschieben; SL darf NPC verschieben.

### AS-06: Gemeinsame 3D-Würfel

**Vom Nutzer vorgegeben:** Spieler würfeln selbst, alle sehen die Würfel auf dem Spielfeld.

**Erste Würfel:** W4, W6, W8, W10, W12, W20, W100; Würfelformeln wie `2d6+3` nach Parser-Einführung. Für genreunabhängige Systeme später Würfelpools, Erfolgszählung und Sonderwürfel.

**Ablauf:** Client sendet Wurf-Anfrage mit Figur und erlaubter Formel → Server prüft und bestimmt Zufall → Server verteilt Wurf-ID/Rohwerte/Modifikatoren/Endwert → jeder berechtigte Client animiert Würfel sichtbar auf dem Board und zeigt den Logeintrag.

- **Standard:** Öffentlicher Wurf für alle Teilnehmer. Geheime SL-Würfe und gezielt private Würfe später als bewusst berechtigte Modi.
- **Wichtig:** Identisches Ergebnis, nicht zwingend identische physikalische Würfel-Flugbahn.
- Ergebnisse sind nachträglich nicht stillschweigend veränderbar; Würfelprotokoll mit Datum, Auslöser und Aktion.
- **Abnahme:** Zwei Browser sehen für denselben W20-Wurf exakt denselben Rohwert und dieselbe Wurf-ID; wiederholte/ungültige Netzwerkbefehle erzeugen keine Doppelwürfe. Würfelanimation wird zunächst technisch mit vorgegebenen Ergebnissen evaluiert.

### AS-07: Konfigurierbare Charakterbögen

Kein fester D&D-Charakterbogen. Anfangs wird ein **generisches Basisprofil** verwendet:
- Name, Portrait, Beschreibung, frei benennbare Zahlen-/Text-/Auswahlfelder
- frei benennbare Ressourcen (z. B. Ausdauer, Energie, Stress, Lebenspunkte)
- Spielerzuordnung und Rechte zum Bearbeiten; SL darf korrigieren
- Position und Token unabhängig vom Charakterbogen speichern

**Beispiele:** Fantasy-Charakter mit Stärke/LP; Cyberpunk-Agent mit Energie/Panzerung; Steampunk-Pilot mit Treibstoff/Technik.  
**Abnahme:** SL erstellt zwei unterschiedliche Charakterbogen-Vorlagen mit verschiedenen Feldern, ohne Quellcode zu ändern; Werte bleiben nach Neustart erhalten.

### AS-08: Gegenstände, Inventar und Effekte

- **Item-Vorlage:** Name, Beschreibung, Genre/Tags, optionaler Slot, visuelles Asset, frei definierbare Eigenschaften.
- **Item-Instanz:** Konkreter Fundort (Karte/Behälter/Charakter), Besitzer, Anzahl, Zustand.
- Spieler hebt Gegenstand vom Spielfeld auf; Inventar synchronisiert sich. Item kann abgelegt und ggf. ausgerüstet werden.
- Konfigurierbare, aber **sicher beschränkte** Modifikatoren auf vorhandene Zahlenfelder (z. B. `+2 Angriff`, `+5 Schild`). Keine unkontrolliert ausführbaren Nutzerskripte.
- Ausrüstungsboni sind abgeleitet: Beim Ablegen verschwindet Bonus ohne permanenten Schaden an Basiswerten.
- **Beschlossen im Feature-Workshop 01.7:** Itemeffekte können manuell beschrieben oder automatisch berechnet werden; temporäre Effekte dürfen mit Echtzeit-Laufzeiten oder rundenbasierten Laufzeiten definiert werden. Ablaufzeit, verbleibende Runden und Zustand sind nachvollziehbar und persistent. Start-/Ende-Semantik und Offline-Verhalten sind noch zu spezifizieren.
- **Beschlossen 01.7:** Gegenstände können aktuelle/maximale Nutzungen besitzen, beispielsweise Feuerballstab **3/3 Ladungen** oder Gewehr **27/27 Schuss**.
- **Beschlossen 01.8:** Nachladen bzw. Wiederherstellen ist pro Item-/Regelprofil konfigurierbar: manuell, durch passende Reservemunition/Magazinwechsel, per Zeit, per Runden, über Ruhe-/Spielleiterereignis oder gar nicht. Mengen, Trigger und Regelsystem-Effekte sind noch offen; keine Nachladung aus dem Nichts annehmen. Der Server prüft Zustände, Ressourcenverbrauch und Nachladerechte.
- **Beschlossen 01.9:** Währungen werden pro Kampagne frei durch den Spielleiter definiert und können vollständig deaktiviert werden. Der Entwurf berücksichtigt persönliche Guthaben und eine optionale Gruppenkasse. Optionale Umrechnungskurse, Zugriffsrechte und Transaktionsdetails werden noch abgestimmt.
- **Beschlossen 01.10:** Für Container und Gruppenlager gibt es individuell konfigurierbare Rechte für **Sehen, Öffnen, Befüllen und Entnehmen**. Optional besitzen Behälter ein interaktives Schloss, das über **Schlüssel-Item**, **Keycard-Item** oder einen **tatsächlich vom Spieler eingegebenen Zahlen-/Textcode** entriegelt wird. Hinweise und Zugangsmittel können im Spiel gefunden, über Quests/NPCs erhalten oder durch Rätsel erschlossen werden. Server prüft Zugangsrechte und Code, ohne geheime Werte an Unberechtigte auszuliefern. Prinzip soll für Türen/Terminals wiederverwendbar sein.
- **Beschlossen 01.11:** Schlösser können pro Objekt dauerhaft entriegelt bleiben, beim Schließen des Behälters automatisch verriegeln oder nach einer konfigurierbaren Zeit erneut sperren.
- **Beschlossen 01.11:** Für echte Codeeingaben kann der Spielleiter **Fehlversuchsgrenzen** und **Konsequenzen** je Schloss definieren. Beispiel: Nach drei falschen Codes löst ein Sicherheitscontainer **einmalig eine Explosion als Spielereignis** aus; weitere konfigurierbare Ereignisse sind Alarm, Sperre, Fallen-/Statuseffekt oder das Erscheinen von NPCs. Schaden und Reichweite richten sich nach einem später konfigurierbaren Regelprofil. Der Server verwaltet Zähler, Berechtigungen und atomare Auslösung; Klientdaten dürfen weder echte Codes noch verborgene Fallen preisgeben.
- **Beschlossen 01.12:** Der Spielleiter konfiguriert bei jedem Codeschloss, ob Fehlversuche **gemeinsam für alle Spieler** oder **getrennt pro Spieler** zählen. Zähler und Auslöser liegen autoritativ beim Server und werden persistent gehalten. Gleichzeitige Eingaben müssen atomar verarbeitet werden; ein einzelnes Fallenereignis darf nicht durch doppelte Anfragen mehrfach ausgelöst werden.
- **Beschlossen 01.13:** Fehlversuchszähler lassen sich pro Schloss nach einer frei festlegbaren Bedingung zurücksetzen: manuell durch den Spielleiter, nach Echtzeitdauer, nach Spielrunden, nach korrektem Code, durch ein Story-Ereignis oder ohne automatischen Reset. Zustände und Timer müssen serverseitig nachvollziehbar gespeichert werden. **Ein Zählerreset reaktiviert eine ausgelöste Falle nicht automatisch.**
- **Beschlossen 01.14:** Fallen können pro Falle **einmalig**, nach Ablauf einer **Echtzeitdauer**, nach bestimmten **Spielrunden**, durch **Story-Ereignisse** oder durch den **Spielleiter** erneut scharfgestellt werden. Rücksetzen eines Fehlversuchszählers stellt eine Falle **nicht automatisch** wieder scharf.
- **Beschlossen 01.14 – plattformweites Zugangssystem:** Schloss-/Zugangsregeln mit **Schlüsseln, Keycards, tatsächlich eingegebenen Codes, individuellen Fehlversuchsregeln und daraus folgenden Ereignissen** gelten nicht nur für Behälter, sondern auch für **Türen, Tore, Fahrzeuge, Terminals, Tresore und beliebige geeignete Szenenobjekte**. Fallen werden als wiederverwendbare, optional auch von Schlössern unabhängige Komponente konzipiert. Beispiele: Alarm bei falschem Türcode, Fahrzeugsperre bei unberechtigter Codeeingabe, explodierende Truhe. Wiederverwendbare serverseitige Prüf- und Ereignislogik statt unterschiedlicher Einzellösungen für jede Objektart.
- **Beschlossen 01.15:** Zugangsbedingungen pro Objekt lassen sich **alternativ (ODER)**, **kumulativ (UND)** und als **mehrstufige Reihenfolge** konfigurieren. Beispiele: Keycard oder Code, Keycard plus Code, nacheinander mehrere Sicherheitsstufen. Der Server validiert jeden Schritt und den Zugriff; Codes und nicht freigegebene Bedingungen bleiben geheim.
- **Beschlossen 01.16:** Schlüssel, Keycards und andere Zugangsgegenstände können pro Vorlage/Instanz als **unbegrenzt verwendbar**, **einmalig**, mit **begrenzten Nutzungen** und/oder **zeitlich befristet** konfiguriert werden. Der Server prüft vor dem Zugang die Restnutzungen/Gültigkeit und verbraucht eine Nutzung nur bei einer erfolgreich bestätigten Verwendung. Ausgeschöpfte/abgelaufene Zugangsgegenstände können keine neuen Zugänge freischalten. Die generische Itemressourcen-/Timerlogik soll wiederverwendet werden.
- **Offene Detailfragen:** Aufbewahren oder Entfernen erschöpfter Karten, Beginn und Pausieren von Gültigkeitsfristen, Wiederaufladen, Fortschritt bei mehrstufigen Eingaben (mehrere Spieler, Timeout, Reset), unabhängige Fallen-Auslöser, mehrere Resetbedingungen, Spielerkonto-/Charakterbezug bei personenbezogenen Zählern, Sichtbarkeit der Restversuche und mehrere Schwellenwerte. Der detaillierte Entwicklungsumfang bleibt bis Ende des Workshops vorläufig.
- **Die verbindliche Detaildiskussion steht im [Feature-Workshop](FEATURE-WORKSHOP.md);** der hier genannte MVP-/Versionsumfang bleibt bis zur gemeinsamen Abschlussplanung vorläufig.
- **Abnahme:** Ein Gegenstand kann nicht von zwei Spielern gleichzeitig aufgenommen werden; ausgerüsteter Bonus erscheint bei beiden Clients konsistent und ist nach Neustart noch korrekt.

### AS-09/12: NPCs, Gegner und Kämpfe

- SL kann beliebige NPCs/Monster/Roboter/Drohnen erstellen oder aus Templates platzieren.
- Solange kein Regelprofil aktiv ist, sind NPCs **allgemeine Figuren** – Lebenspunkte/Kampfrunden sind optional.
- Erste Kampfautomation später: Initiative, Aktionsmarker, Zugwechsel, vordefinierte Würfe und Ressourcenanpassung je Regelprofil.
- **Abnahme MVP:** SL kann mehrere NPCs verwalten und bewegen; Spieler haben keine SL-Rechte.
- **Abnahme 1.1:** Beispiel-Regelprofil führt einen vollständigen Testkampf durch, ohne andere Kampagnen zur Nutzung dieses Regelwerks zu zwingen.

### AS-10/20: Spielstände, Betrieb und Sicherheit

- PostgreSQL speichert Nutzer, Kampagnen, Mitgliedschaften, Charaktere, Kartenreferenzen, Tokens, Items und Würfelereignisse.
- Dateien liegen dauerhaft auf Datenträgern/Volumes, nicht nur im Container.
- HTTPS und abgesicherter WebSocket, Validierung jedes Befehls, Rechtefilter, Rate Limits und begrenzte Uploads.
- Automatisierte Datenbankmigrationen, Konfigurationsvorlage, Healthcheck und dokumentierte Backup- und Restore-Prozedur.
- **Abnahme:** Spielleiter beendet den Server, startet ihn neu und findet die Testkampagne samt Spielerfiguren, Itemstatus und Würfelprotokoll wieder; Restore aus Backup getestet.

## 3. Rollenrechte – Minimalmatrix

| Aktion | Spieler | Spielleiter |
| --- | --- | --- |
| Eigene Charakterwerte ändern | Je Freigabe | Ja |
| Eigene Figur bewegen | Ja | Ja |
| NPC oder fremden Token bewegen | Nein | Ja |
| Sichtbare Würfel werfen | Ja | Ja |
| Item aufnehmen/ausrüsten | Eigener Charakter | Ja / verwalten |
| Szene wechseln | Nein | Ja |
| Gegner, Karten und Vorlagen bearbeiten | Nein | Ja |
| Geheimdaten sehen | Nein | Ja |
| Rollen und Mitgliedschaften verwalten | Nein | Ja |

Ein Teilnehmer darf niemals durch Manipulation im Browser SL-Rechte erhalten.

## 4. Vorgeschlagene Oberfläche

**A. Login:** Logo AdventureShift, Steam-Anmeldeknopf.  
**B. Dashboard:** Meine Kampagnen, Kampagne beitreten, neue Kampagne als SL anlegen.  
**C. Spielraum (Desktop zuerst):**
- **Mitte:** 2D-Spielfeld, Figuren, Würfelanimation.
- **Links:** Szenen-/Kartenliste (SL) und Spielerübersicht.
- **Rechts:** Charakterbogen, Attribute, Ausrüstung, Inventar.
- **Unten:** Würfelleiste, gemeinsames Ereignisprotokoll und ggf. Chat.
- **SL-Modus:** Zusätzliche Werkzeugleiste für Tokens, Szenen, NPCs, Geheimnisse.

Mobilgerät/Tablet: später eigene Layoutprüfung; Touch-Interaktion von Anfang an nicht grundsätzlich ausschließen.

## 5. Meilensteine und Reihenfolge

| Phase | Funktionen | Fertig, wenn ... |
| --- | --- | --- |
| **P0 – Technischer Vertical Slice** | AS-03, AS-04, AS-05, AS-06 (lokale Demoidentitäten) | Zwei Browser bewegen Tokens und sehen dieselben serverseitigen Würfelergebnisse |
| **P1 – Erste spielbare MVP-Version** | AS-01, AS-02, AS-07, AS-08, AS-09, AS-10, AS-20 | Steam-Anmeldung, Kampagne, Charakter/Items/SL und Persistenz funktionieren Ende-zu-Ende |
| **P2 – Spieltisch ausbauen** | AS-11–AS-16 | Optionale Regelprofile, Kampf, Sicht, Journal, Szenen- und Assetverwaltung |
| **P3 – Erweiterungssystem** | AS-17–AS-19 | Ausgereifte Inhaltseditoren, Trigger und optionale Automatisierung |

**Warum P0 ohne Steam?** Die kritischen Risiken – synchrones Spielbrett und gemeinsames 3D-Würfeln – lassen sich so unabhängig von einem öffentlich erreichbaren Login-Callback testen. Diese Testidentitäten sind **ausschließlich** für die lokale Entwicklung; kein öffentlicher Gastmodus.

## 6. Erste konkret umzusetzende Tickets

1. Projektgrundgerüst (Monorepo mit Web, Server, Shared, Tests) und lokales Setup.
2. Multiplayer-Spielraum: beitreten, getrennte Identitäten, Reconnect, serverseitiger State.
3. Spielfeld und Tokens: Drag/Zoom/Rasteroption, Regelprüfung, Positions-Sync.
4. Würfel: Server-RNG, Ergebnis-Event, Protokoll, geteilte Animation.
5. Steam-Login und Rollen: Secure Session, Kampagne, Mitgliedschaft, Autorisierung.
6. Persistenz: PostgreSQL-Modelle, Kampagne/Token/Würfe laden und speichern.
7. Neutrale Charakterbögen sowie erstes Item-/Bonussystem.

Vor produktiver Nutzung alle Änderungen mit Rollen-, Zustands-, Mehrbrowser- und Neustart-Tests prüfen.

## 7. Offene Designentscheidungen (nicht blockierend für P0)

- Wie streng soll das Movement standardmäßig sein: freies Ziehen, Wegfindung oder Zugbudget?
- Soll die Würfelanimation in einem festen Boardbereich oder frei über der Karte erscheinen?
- Wird der erste generische Charakterbogen vollständig frei konfigurierbar oder aus vordefinierten Feldtypen zusammengesetzt?
- Welche Item-Aktionen darf ein Spieler ohne SL-Freigabe durchführen?
- Welche Regelprofile und Würfelpools priorisieren wir nach dem Sandbox-Modus?
- Wie viele Szenen und parallele Kampagnen soll ein Server anfangs zuverlässig unterstützen?

## 8. Bewusste Nicht-Ziele des MVP

- Keine vollautomatische KI-Spielleitung.
- Keine integrierte Video-/Sprachkonferenz (bestehende Lösungen können parallel genutzt werden).
- Kein offener Plugin-Marktplatz und keine unkontrollierten Nutzerskripte.
- Kein vollständiger D&D-Regelwerksimulator mit allen Klassen/Zaubern.
- Keine Verpflichtung auf Quadratfelder, Lebenspunkte oder rundenbasierten Kampf.

## 9. Verweise

- [Projektplan](PROJEKTPLAN.md)
- [Architektur](ARCHITEKTUR.md)
- [Lizenzen](LIZENZEN.md)
- [Namensrecherche](NAMENSRECHERCHE.md)

**Hinweis zu AdventureShift:** Der Name ist vom Projektinhaber ausgewählt. Marken- und Domainverfügbarkeit sind nach der bisherigen Recherche **nicht abschließend bestätigt**. Vor externer Veröffentlichung gesondert prüfen.
