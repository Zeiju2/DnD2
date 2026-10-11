# AdventureShift – Projektplan und Roadmap

**Stand:** 11.10.2026  
**Projektstatus:** Featureplanung / keine Implementierung  
**Geltungsbereich:** Eigenständige, browserbasierte, genreunabhängige Multiplayer-Rollenspielplattform auf einem später selbst betriebenen Server.

> Dieses Dokument hält die bisherigen Wünsche und Vorschläge fest. Es ist **kein** Nachweis einer bereits implementierten Funktion. Nicht entschiedene Fragen sind ausdrücklich als offen markiert.

## 1. Zielbild

Ein Spielleiter und mehrere Spieler betreten nach Anmeldung mit ihrem Steam-Konto eine gemeinsame Kampagne. Sie sehen eine von oben dargestellte 2D-Karte, bewegen ihre Figuren, entdecken Gegenstände, kämpfen gegen Gegner und können selbst Würfelwürfe auslösen. Jeder freigegebene Würfelwurf wird für die relevanten Teilnehmer sichtbar animiert und protokolliert.

**Ausgangsannahme für Tests:** 1 Spielleiter und ca. 4–6 Spieler gleichzeitig; keine feste Obergrenze versprochen.

**Produktprinzip:** Der Spielleiter behält erzählerische Freiheit. Die Software unterstützt und automatisiert wiederkehrende Regeln und Verwaltungsaufgaben, statt ein vollautomatisches Action-Spiel zu erzwingen.

### Festgelegte Ausrichtung: universelle Rollenspielplattform (11.10.2026)

- **Genreunabhängig:** Fantasy, Cyberpunk, Steampunk, Science-Fiction, Horror, Gegenwart und eigene Welten sind gleichberechtigte Einsatzszenarien. Das Projekt ist **kein reines D&D- oder Fantasy-Spiel**.
- **Regelwerksunabhängiger Kern:** Steam-Login, Räume/Kampagnen, Karte, Tokens, Bewegung, Würfel, Rechte und Speicherfunktionen dürfen kein einzelnes Spielsystem voraussetzen.
- **Konfigurierbare Inhalte:** Charakterbögen, Werte, Ressourcen, Item-Slots, NPCs/Gegner, Effekte und Würfelmechanismen sollen durch Kampagneneinstellungen und Vorlagen variierbar sein.
- **Optionales Regelmodul:** D&D-SRD 5.1/5.2.1 ist ein mögliches Paket und kein fest eingebauter Standard. Andere, eigene oder später separat lizenzierte Regeln sollen möglich sein.
- **Neutraler erster Prototyp:** Freier Spielraum mit allgemeinen Tokens und Würfeln. Automatischer rundenbasierter Kampf und bestimmte Schadens-/HP-Regeln sind abhängig vom späteren Regelprofil.
- **Naming:** **AdventureShift** ist als Produktname gewählt. Das GitHub-Repository bleibt bis zu einer bewussten Umbenennung `DnD2`. Domain- und Markenprüfung sind noch nicht abgeschlossen.

**Laufende gemeinsame Featureplanung und offene Produktentscheidungen:** siehe [FEATURE-WORKSHOP.md](FEATURE-WORKSHOP.md). **Vorläufige** Features, Akzeptanzkriterien und Ausbaustufen: siehe [FEATURES.md](FEATURES.md). Vor Abschluss der Workshop-Themen keine technische Implementierung oder Festlegung des MVP-Umfangs.

## 2. Anforderungen und Prioritäten

### MUSS – erste spielbare Version (MVP)

- [ ] Anmeldung per Steam (Steam OpenID 2.0) und eigenes Benutzerprofil über die Steam-ID.
- [ ] Kampagne / Lobby erstellen, Einladung oder Beitritt steuern.
- [ ] Rollen und Rechte **pro Kampagne**: Spieler und Spielleiter.
- [ ] Gemeinsamer Spielraum mit Live-Verbindung und Teilnehmerstatus.
- [ ] 2D-Karte mit optionalem Raster, Zoom, Verschieben des Bildausschnitts und frei verwendbaren Tokens.
- [ ] Eigene Figur bewegen; Gegner und andere Figuren werden vom Spielleiter kontrolliert.
- [ ] Server prüft Bewegungen und sendet autoritative Positionen an alle Clients.
- [ ] Spieler können Würfel selbst auslösen: mindestens W4, W6, W8, W10, W12, W20 und Prozentwurf; Formeln wie 2W6+3 sowie spätere regelwerksabhängige Würfelpools werden berücksichtigt.
- [ ] Der Server erzeugt das gültige Würfelergebnis; alle berechtigten Teilnehmer sehen Ergebnis, Absender und Animation.
- [ ] Würfelprotokoll mit Zeit, Figur, Würfeltyp, Rohwerten und Modifikatoren.
- [ ] Charaktere mit konfigurierbaren Feldern/Werten (z. B. Attribute, Gesundheit, Energie, Panzerung oder Stress), optionaler Figur auf dem Spielfeld und neutraler Basisvorlage.
- [ ] Gegenstände und Ausrüstung beliebiger Genres auffinden, aufnehmen, ablegen und verwalten; Ausrüstungsplätze je Vorlage konfigurierbar.
- [ ] Konfigurierbare Gegenstandseffekte dürfen – wenn das gewählte Regelprofil sie vorsieht – abgeleitete Charakterwerte ändern, ohne Basiswerte zu überschreiben.
- [ ] NPCs, Gegner, Kreaturen, Fahrzeuge oder Drohnen platzieren, verwalten und bewegen.
- [ ] Optionale Initiative, Rundenreihenfolge, Angriff und Schaden in einem ersten Beispiel-Regelprofil demonstrieren; der neutrale Kern erzwingt keine Kampfregeln.
- [ ] Kampagnen-, Charakter- und Inventardaten dauerhaft speichern.
- [ ] Installation der Software auf einem eigenen Linux-Server per Container-Konfiguration.

### SOLL – nach stabiler MVP-Version

- [ ] Nebel des Krieges / Sichtbereiche, verdeckte Gegner und geheime Räume.
- [ ] Türen, Hindernisse, schwieriges Gelände, Sichtlinien und Wegfindung.
- [ ] Karten und Token-Bilder durch den Spielleiter hochladen.
- [ ] Interaktive Truhen, Bodenbeute und gemeinsame Beuteverteilung.
- [ ] Spielleiter kann versehentliche Änderungen rückgängig machen.
- [ ] Quest-/Abenteuerjournal, Notizen und Ereignis-Auslöser.
- [ ] Eigene Charakterbogen-, Item-, NPC-/Gegner- und Genrevorlagen über eine Administrationsoberfläche.
- [ ] Spielleiter-Testansicht aus Spielersicht.
- [ ] Wiederaufnahme nach Verbindungsabbruch und klare Offline-Indikatoren.

### KANN – spätere Ideen

- [ ] Automatische NPC-Handlungen und gegebenenfalls Kampfentscheidungen (vorläufig später; Umsetzung und Umfang erst nach dem Workshop festlegen). Fachlich gilt 02.54: manuelle, automatische und SL-bestätigte NPC-Steuerung samt globalen Defaults und Ausnahmen vorsehen.
- [ ] Animierte Angriffe, Status-Effekte, Zaubervorlagen und Beleuchtung.
- [ ] Karteneditor, regelbasierte Automatisierungen und Skripte.
- [ ] Chat, Soundeffekte, Sprache oder Integration mit vorhandenen Sprachdiensten.
- [ ] Mobil-/Tablet-optimierte Oberfläche und Barrierefreiheit.
- [ ] Wiederverwendbare Kampagnenvorlagen oder Import/Export.

## 3. Spielsystem und Rollen

### Spieler

- Meldet sich über Steam an; erstellt oder wählt einen zur Kampagne gehörenden Charakter.
- Sieht seine freigegebenen Informationen und die Karte aus seiner Perspektive.
- Bewegt den eigenen Token im erlaubten Rahmen.
- Würfelt selbst, nutzt Items, verwaltet Inventar und kontrolliert eigene Aktionen.
- Kann nur Informationen sehen bzw. bearbeiten, für die eine ausdrückliche Berechtigung besteht.

### Spielleiter

- Erstellt/verwaltet Kampagnen, Szenen, Karten, Teilnehmer und Zugriffsrechte.
- Platziert und steuert NPCs, Monster, Türen, Items und Ereignisse.
- Legt fest, welche geheimen Informationen Spieler sehen dürfen.
- Kann Werte korrigieren, Runden fortsetzen und Aktionen gegebenenfalls rückgängig machen.
- Verwaltet Würfeloptionen; verdeckte Spielleiterwürfe wären eine spätere Erweiterung.

**Wichtig:** Eine Person kann in einer Kampagne Spielleiter und in einer anderen Spieler sein. Rollen nicht global an ein Steam-Konto binden.

## 4. Bewegung und Kampf (Entwurfsannahmen)

Empfohlene Ausgangsbasis ist eine **Top-down-2D-Karte mit quadratischem Raster**. Der gewünschte Bewegungsmodus muss noch entschieden werden.

**Vorschlag A – Hybrid (bevorzugt, aber nicht beschlossen):**
- Erkundung: Figuren frei per Klick/Ziehen bewegen; der Server verhindert verbotene Positionen.
- Kampf: Initiative und Zugreihenfolge aktivieren, Bewegung und Aktionen einschränken.

**Alternative B:** Bewegung jederzeit in Runden.  
**Alternative C:** Kontinuierliche Echtzeitbewegung, auch im Kampf; deutlich anderes System und höherer Synchronisierungsaufwand.

### Minimaler Kampffluss

1. Spielleiter startet den Kampf.
2. Initiative aller Beteiligten wird gewürfelt bzw. festgelegt.
3. Aktiver Teilnehmer bewegt den Token und führt Aktionen aus.
4. Server prüft Reichweite, Zugrecht, Werte und veränderte Lebenspunkte nach den gewählten Regeln.
5. Ereignisse erscheinen im gemeinsamen Protokoll.
6. Spielleiter beendet den Kampf oder startet die nächste Begegnung.

**Festgelegt:** Die Plattform ist genre- und regelwerksneutral. **Nicht festgelegt:** Welche konkreten Regelprofile zuerst angeboten werden (z. B. D&D-SRD, Hausregeln, eigenes System). Angriffs-, Rüstungs-, Aktions-, Gesundheits- und Bewegungsregeln sind daher nur Beispiele eines später wählbaren Regelmoduls.

## 5. Würfel – fachliches Sollverhalten

1. Spieler fordert mit seiner identifizierten Figur einen Wurf an.
2. Server prüft Spielraum, Rechte, Würfelart und ggf. erlaubte Modifikatoren.
3. Server erzeugt den Zufallswert mit einer geeigneten kryptografischen Zufallsquelle und legt ein Ereignis mit eindeutiger ID an.
4. Das Ereignis wird an alle berechtigten Clients geschickt; diese spielen eine 3D-Würfelanimation ab.
5. Alle sehen verbindlich **dasselbe Ergebnis**. Die physikalische Flugbahn muss nicht bei jedem Client pixelgenau gleich sein.
6. Bei Reconnect bleibt das Ergebnis über Protokoll und Serverzustand nachvollziehbar.

**Technisches Risiko:** Ob eine Würfelbibliothek bestimmte Ergebnisse zuverlässig animieren kann, muss im Prototyp geprüft werden. Verbindliches Ergebnis und Visualisierung bleiben deshalb unabhängig voneinander.

## 6. Charaktere, Items und Gegner

### Charakter

- Gehört zu einem Benutzer und einer Kampagne.
- Speichert Name, optionale Klasse/Volk/Herkunft, Basiswerte, Trefferpunkte, Ausrüstungsslots, Position und Zustände.
- Berechnete Werte entstehen aus Basiswert + regelbasierte Effekte + ausgerüstete Items.

### Item

- **Vorlage:** Name, Typ, Seltenheit, Darstellung, erlaubter Ausrüstungsslot, Regeln/Effekte.
- **Instanz:** konkreter Fund im Inventar oder auf der Karte, Besitzer, Anzahl, Zustand und ggf. individuelle Eigenschaften.
- Beispiel: „Frostklinge“ mit +2 auf einen definierten Angriffswert. Die Wirkung hängt vom später gewählten Regelwerk ab.
- Eigentumswechsel und Ausrüstungsänderungen sind serverseitige Aktionen; Dopplung durch gleichzeitiges Aufheben verhindern.

### Gegner

- Gegner-Vorlagen mit Werten, Angriffen, Bewegungsprofil und Beute.
- Gegner-Instanzen mit aktuellen HP, Position, Effekten und Status.
- **Verbindliches Featureziel 02.54:** Generell bei Kampagnenerstellung wählbar, ob NPCs/Gegner **vom SL selbst gespielt**, **automatisch durch zulässige Regeln gesteuert** oder **nach SL-Bestätigung von vorgeschlagenen Aktionen** geführt werden; pro NPC, Vorlage und Gruppe bewusste Ausnahmen. Die Moduswahl gilt **nicht nur für Geräuschreaktionen**. Art und Umfang automatisch erlaubter Dialog-, Bewegungs-, Interaktions- und Kampfhandlungen werden in den Featurebereichen 06/07 detailliert geplant. Generative KI ist damit **nicht automatisch vorgeschrieben**.
- **Featureziel 02.55:** Konfigurierbare NPC-Verdachts-/Aufmerksamkeits-/Such-/Alarmphasen und Regeln für Eskalation, Abklingen, Rückkehr, Echtzeit-/Rundenfristen und SL-Eingriff, mit globalen Profilstandards und gekennzeichneten Ausnahmen für Gruppen, Vorlagen und Einzel-NPCs. NPC-Wachsamkeit bleibt getrennt von konkreten Aktionen und dem allgemeinen manuellen/automatischen/SL-bestätigten NPC-Steuerungsmodus (02.54) sowie quittierbaren technischen Sensoralarmen (02.44–02.47). Kommunikation/Warnungsweitergabe an andere NPCs folgt erst nach Entscheidung 02.56; genaue Implementierungspriorität/MVP-Zuordnung weiterhin offen.
- **Featureziel 02.56:** NPCs/Gegner/Tiere dürfen Warnungen, Verdacht und zulässiges Wissen **nur über explizit konfigurierbare Kommunikationswege** weitergeben – etwa Ruf mit tatsächlicher akustischer Hörprüfung, Sichtzeichen, Funk/Telefon, passende magische Regelprofile oder autorisierte Node-/Alarm-Verbindungen. **Keine automatische allwissende Fraktion:** Senderwissen, Nachrichtengenauigkeit, Kanalvoraussetzungen/Reichweite, Empfängergruppen/Tags und Rechte serverseitig prüfen; Empfang vom NPC-Verdachts-/Aktionszustand (02.55) trennen. Die allgemeinen NPC-Steuerungsmodi aus 02.54 gelten auch für das Senden; kampagnenweite Standards und gezielte Vorlagen-/Gruppen-/NPC-/Kanal-Ausnahmen vorgesehen. Nachrichtenausfall, Verzögerung und Wiederholung werden ab 02.57 entschieden. Die tatsächliche Priorisierung und MVP-Zuordnung bleiben bis zum vollständigen Workshop offen.
- **Featureziel 02.57:** NPC-Nachrichten und Warnungen aus 02.56 können je Kommunikationskanal **sofort, verzögert, unterbrochen, fehlgeschlagen, wiederholt oder wegen Ablaufs verworfen** werden; Kampagnenstandards mit passenden Geräte-/Quellen-/NPC-/Gruppen-/Regionsausnahmen und Zeitbasis Echtzeit/Runden vorsehen. **Nur erfolgreiche Zustellung erzeugt Empfängerwissen**, daraus abgeleitete NPC-Wachsamkeit und technische Alarm-Nodes bleiben eigenständig. Wiederholungen dürfen keine doppelten Ereigniswirkungen verursachen; Rufe/Sichtzeichen nicht als nachträglich zustellbare digitale Warteschlange behandeln. SL-Eingriffe, Serverautorität und Debug/Tests vorgesehen. **Feste Werte, Pause-/Offline-Semantik und eigentliche MVP-Priorität weiterhin offen.** In 02.58 wird gesondert entschieden, ob Abfangen/Mithören/Täuschen möglich sein soll.
- **Featureziel 02.58:** Abhören, Abfangen, Unterdrücken, Umleiten, Verändern und inweltliche Fälschung von NPC-/Figurenkommunikation **optional pro Spielweltkanal und Setting** erlauben; kampagnenweite Standards mit Fähigkeiten-/Geräte-/NPC-/Kanal-/Regionsausnahmen und ggf. regelprofilabhängigen Proben. Echte Sender-/SL-Geheimnisse bleiben serverseitig; die behauptete Senderkennung ist **keine technische Berechtigung**. Änderungen wirken nur nach gültiger Manipulations- und Zustellprüfung aus 02.56–02.57; NPC-Wissen/Wachsamkeit, automatische NPC-Aktionen und Alarm-/Node-Reaktionen bleiben gesondert servervalidiert (02.54–02.55). Tests für Abhörberechtigung, verdeckte Quellen, unterdrückte Nachricht, empfängerspezifische Fälschung, Replay und NPC-Modus vorsehen. In **02.59** noch offene Vertrauens- und Echtheitsprüfung planen; genaue MVP-/Implementierungsphase erst nach dem vollständigen Featureworkshop festlegen.
- **Featureziel 02.59:** Je Kampagne/Kanal/NPC/Fraktion konfigurierbare Echtheits-/Vertrauensprüfungen (Kennwort, bekannte Kennung, passive/aktive Probe, technische/magische Verifikation, Rückfrage oder SL-Eingriff). Echte Identität, behauptete Absenderidentität, Nachricht, NPC-Glaube, Reaktion und tatsächliche Node-Aktion strikt trennen; keine technische Rechtevergabe durch Täuschung.
- **Späterer Node-Featurebedarf (konkrete Nutzerbeispiele 02.59):** Szenen-Telefone als vernetzte interaktive Objekte mit gefilterter Wahlliste; Anruf erzeugt Node-Ereignis, Dialog-/Text-Node kann **„Wer sind Sie? Wachen!“** ausgeben. Eigenständige **Spawn-Node** mit Trigger, Zielszene, Spawnposition(en), Vorlagenauswahl aus Liste und Menge (zwei Wachen). Alternativ Passwortabfrage mit serverseitiger Prüfung: **richtig → Tür-Node öffnen, falsch → Gespräch auflegen**. Alle Knoten frei kombinierbar, typisiert, serverautorisiert, mit Geheimnisschutz und Doppelspawn-Vermeidung. Konkrete Node-/Telefonnetz-/Dialog-/Spawn-Details und Umsetzung erst später planen.
- **Featureziel 02.60:** Kommunizierte Inhalte können **vollständig, teilweise oder überhaupt nicht verständlich** sein, abhängig von kampagnen-/regelprofilabhängigen Sprach-/Schrift-/Codekenntnissen, optionalen technischen/magischen Übersetzungshilfen, Fähigkeiten, Prüfungen und SL-Entscheidungen. Globale Standards und Figuren-/NPC-/Kanal-/Region-Ausnahmen. Empfang, Verständnis, Echtheit/Vertrauen, NPC-Wissen und Aktion bleiben unabhängig; der Server liefert einem Spieler keine nicht verständlichen geheimen Klartexte oder Übersetzungen. Keine universelle Live-Transkript-/Übersetzungs-KI verpflichtet. Telefon-/Dialog-/Passwort-/Spawn-Nodes aus 02.59 bleiben für spätere Fachplanung vorgemerkt, Eingabe-/Kennwortprüfung bleibt getrennt von Sprachverständnis. Die genaue Umsetzung/Priorisierung sowie das NPC-Gedächtnis (nächste Frage 02.61) bleiben offen.
- **Ergänzung 02.60 – Sprachen sind Skills:** Im **Sprachmenü** kann die Spielleitung Sprachen **kampagnenweit als gemeinsame Skilldefinitionen anlegen**. Wie **Schießen oder Nahkampf** können Sprachfertigkeiten einer Figur/einem NPC individuell zugewiesen, erlernt und verbessert werden; globaler Sprachkatalog bedeutet **nicht**, dass alle Figuren sie automatisch beherrschen. Spracheinträge und referenzierte Skillwerte stabil/persistent führen; dieselbe später festzulegende allgemeine Steigerungs-/Skillmechanik verwenden. Verständlichkeit prüft gültige individuelle Skillwerte, optional Übersetzungshilfen und Regelproben; geheime Klartexte bleiben serverseitig. Genaues Sprachmenü-Layout und Skillverbesserungsregeln erst in der späteren UI-/Charakter-/Regelplanung (03/07), endgültige MVP-Phase noch nicht beschlossen.
- **Featureziel 02.61:** NPC-Gedächtnis für legitim erworbene Informationen, Verdacht und Vermutungen **dauerhaft, zeitlich begrenzt oder ereignisabhängig** verwalten, verstärken, korrigieren, widerlegen oder vergessen lassen. Kampagnenstandards mit Gruppen-/Vorlagen-/NPC-Ausnahmen, Fristen in Echtzeit oder Runden und SL-Eingriff. **NPC-Gedächtnis bleibt getrennt von aktueller Wachsamkeit (02.55), allgemeiner Steuerung (02.54), objektiver Weltwahrheit und technischen Alarm-Node-Zuständen**; gefälschte Nachricht höchstens als subjektiv geglaubte Information, keine heimliche Kenntnis verdeckter Spielerorte. Sichere Memory-/Quell-/Timerreferenzen und deduplizierte serverseitige Ereignisse sowie SL-Debug/isolierte Tests vorsehen. Konkrete Algorithmen, Zeitwerte, Aufbewahrung, Verhalten in Pausen/inaktiven Szenen und Wiedererkennung **02.62** offen; MVP-Priorisierung erst nach Workshopabschluss.
- **Featureziel 02.62:** NPCs sollen bekannte Personen unter **regel-/settingabhängig konfigurierbaren Wiedererkennungsbedingungen** identifizieren oder für ähnlich halten können. Prüfung nur gegen **tatsächlich wahrgenommene und legitim erinnerte** Merkmale (z. B. Gesicht, Stimme, Kleidung, besondere Merkmale, frühere Begegnungen), einschließlich Licht-/Hörbedingungen, vergangener Zeit, möglichen Verkleidungen, Fähigkeiten, optionalen Proben oder SL-Entscheidungen. Kampagnenstandards mit NPC-/Vorlagen-/Gruppen-/Situationsausnahmen. **Wahre Figurenidentität, subjektive NPC-Vermutung, Erinnerung 02.61, momentaner Verdacht 02.55 und Aktion nach 02.54 strikt getrennt**; ein Irrtum kann korrigiert werden, kein automatischer allwissender Token-Lookup und kein Alarm ohne autorisierte gesonderte Reaktion. Serverseitiger Geheimnisschutz, deduplizierte Prüfungen und isolierte Tests. Die konkreten Verkleidungs-/Tarnidentitätswerkzeuge folgen in **02.63**, genaue Umsetzung/MVP weiterhin offen.
- **Vorläufige Implementierungsannahme:** NPCs im ersten Prototyp manuell zu steuern und automatische NPC-Handlungen später umzusetzen bleibt eine mögliche Entwicklungsreihenfolge, **kein fachliches Verbot automatischer NPC-Steuerung und noch keine finale MVP-Entscheidung**.

## 7. Meilensteine und Abnahmekriterien

### Phase 0 – Entscheidungen und technisches Fundament
- [ ] Neutrales Basisprofil, erstes Demo-Regelmodul und konfigurierbare Bewegungsmodi festlegen.
- [ ] Lizenzen für Regeln, Bilder und Karten klären.
- [ ] Projektstruktur, TypeScript, Tests, Konfiguration und lokale Entwicklungsumgebung vorbereiten.
- [ ] Architekturkonzept und Event-Schnittstellen abstimmen.

**Abnahme:** Eine dokumentierte Entwicklungsumgebung ist reproduzierbar startbar.

### Phase 1 – Echtzeit-Prototyp (höchste Priorität)
- [ ] Zwei Browser treten demselben Raum bei.
- [ ] Beide sehen eine einfache Karte und synchronisierte Tokens.
- [ ] Eine Bewegung erscheint auf beiden Bildschirmen.
- [ ] Ein Spieler löst einen W20 aus; beide sehen dasselbe Server-Ergebnis und eine passende Animation.
- [ ] Reconnect, Latenz und konkurrierende Aktionen werden getestet.

**Abnahme:** Demo in zwei unabhängigen Browsern ohne manuelles Aktualisieren.

### Phase 2 – Identität und Kampagnen
- [ ] Steam-Login, sichere Sitzung und Logout.
- [ ] Kampagne erstellen, beitreten, Mitgliedschaften und Rollen verwalten.
- [ ] Charaktere erstellen, einem Nutzer zuordnen und speichern.

**Abnahme:** Spieler kehren nach erneutem Login zur eigenen Kampagne zurück.

### Phase 3 – Spiellogik
- [ ] Bewegung mit Hindernissen/Rasterregeln.
- [ ] Gegner, Initiative, Zugverwaltung und einfache Angriffe.
- [ ] Lebenspunkte und Aktionen konsistent synchronisieren.

**Abnahme:** Ein vollständiger Testkampf mit Spielleiter und mehreren Spielern.

### Phase 4 – Inventar und Fortschritt
- [ ] Items auf der Karte, Aufheben, Ausrüsten, Abwerfen und Tauschen nach Regelentscheidung.
- [ ] Bonuseffekte, Beute und persistente Inventare.
- [ ] Spielstand nach Neustart des Servers wiederherstellen.

**Abnahme:** Charakter kann ein Item finden, ausrüsten, einen Bonus erhalten und es nach Neustart behalten.

### Phase 5 – Ausbau und Betriebsreife
- [ ] Kartenverwaltung, Geheimnisse/Sicht, Spielleiter-Tools, Journale.
- [ ] Tests auf Berechtigungen, Manipulationsversuche, Last und Ausfallsicherheit.
- [ ] Server-Installation, HTTPS, Backup und Restore dokumentieren.

**Abnahme:** Kampagne kann zuverlässig auf dem eigenen Server betrieben werden.

## 8. Definition of Done für neue Funktionen

Eine Funktion gilt erst als abgeschlossen, wenn:
- fachliche Akzeptanzkriterien erfüllt sind;
- ein anderer Browser Änderungen korrekt sieht;
- der Server Berechtigungen validiert;
- relevante Daten bei Neustart erhalten bleiben;
- Fehlerfälle (z. B. ungültiger Zug, Netzwerkverlust) berücksichtigt sind;
- Tests und Dokumentation entsprechend ergänzt wurden.

## 9. Offene Entscheidungen

| Thema | Mögliche Varianten | Status |
| --- | --- | --- |
| Regelsystem | Regelwerksneutraler Kern **beschlossen**; welche optionalen Regelprofile (D&D-SRD, eigene Regeln etc.) zuerst? | **Kern festgelegt, Profile offen** |
| Bewegung | Hybrid, ausschließlich Runden, Echtzeit | **Offen** |
| Kartenart | Quadrat-, Hex-Raster oder freies Spielfeld – unabhängig von Genre und Regeln | Offen |
| Würfe | Sichtbar für alle; geheime Würfe später | Vorschlag |
| Endgeräte | Desktop-Browser zuerst; Mobilgerät später | Vorschlag |
| Item-Komplexität | Einfache Boni zuerst; Zustände/aktive Fähigkeiten später | Vorschlag |
| Benutzerzahl | Test mit etwa 1 SL + 4–6 Spielern; echte Kapazität messen | Annahme |
| Betriebsumgebung | Eigener Linux-Server mit Docker | Gewünscht, Details offen |
| Lizenz/Veröffentlichung | Eigene Inhalte; offizielle Regeltexte nur soweit lizenziert | Zu prüfen |

## 10. Risiken und Gegenmaßnahmen

- **Synchronisierung / Race Conditions:** Autoritativer Server, eindeutige Event-IDs, atomare Item-Übergänge und Tests mit mehreren Browsern.
- **3D-Würfel und Ergebnisbindung:** Bibliothek früh prototypisieren; Ergebnis unabhängig von Animation berechnen.
- **Geheime Informationen:** Niemals alle Daten an Clients schicken und nur optisch verstecken; serverseitig je Rolle filtern.
- **Regelwerksumfang:** System modular und anfangs bewusst klein halten.
- **Steam-Identität / Sicherheit:** Login-Response serverseitig prüfen; Tokens/Cookies absichern und niemals Steam-Passwörter speichern.
- **Eigener Server / Datenverlust:** Docker, persistente Datenträger, regelmäßige getestete Backups und Monitoring.
- **Rechtliche Fragen:** Regeln, Marken, Karten, Monster und Bildmaterial auf Nutzungserlaubnis prüfen.

## Lizenz- und Inhaltsstrategie (recherchiert am 11.10.2026)

- **Empfehlung:** Eigene regelwerksneutrale Spiellogik und selbst erstellte bzw. lizenzierte Inhalte verschiedenster Genres, aber permissiv lizenzierte Open-Source-Bibliotheken wiederverwenden.
- **Technik:** React, PixiJS, Colyseus, dice-box-threejs u. a. grundsätzlich frei und kommerziell nutzbar – Lizenztexte und Lizenzen der Unterabhängigkeiten prüfen.
- **Steam:** Login per OpenID vorgesehen; Steam ist keine Open-Source-Bibliothek. Valve-Bedingungen für API, Marken und Daten beachten.
- **D&D:** Nur ausdrücklich unter CC BY 4.0 freigegebenes SRD-Material (SRD 5.1 / SRD 5.2.1; deutsche Fassung verfügbar) verwenden; keine automatische Erlaubnis für offizielles Artwork, alle Buchinhalte, Logos oder Settings.
- **Eigene Inhalte:** Karten, Monster- und Itemgrafiken, Texte, Charaktere und Welten selbst erstellen oder Assets mit dokumentierter Lizenz nutzen.
- **Noch offen:** Soll die eigene Software proprietär oder Open Source werden? Das Repository ist derzeit öffentlich, was nicht mit einer erteilten Open-Source-Lizenz gleichzusetzen ist.
- **Dokumentation:** Die Lizenzmatrix und Prüfcheckliste stehen in [LIZENZEN.md](LIZENZEN.md).

## 11. Nächste konkrete Schritte

1. Regelwerk und Bewegungsmodus festlegen.
2. Minimales Datenmodell und Serverevents („join“, „move“, „roll“) spezifizieren.
3. Einfachen Zwei-Browser-Prototyp umsetzen.
4. Früh prüfen, ob eine 3D-Würfelbibliothek Server-Ergebnisse zuverlässig darstellen kann.
5. Danach Steam-Login und Kampagnendaten ergänzen.

---

**Pflegehinweis:** Neue Festlegungen, Abweichungen und erledigte Meilensteine werden bei der Weiterentwicklung in diesem Dokument aktualisiert. Für technische Details siehe [ARCHITEKTUR.md](ARCHITEKTUR.md).
