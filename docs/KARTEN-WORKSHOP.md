# AdventureShift – Karten-Workshop: beschlossene Funktionen

**Stand:** 12.10.2026 – Beschlüsse 02.1 bis 02.73; als Nächstes 02.74  
**Status:** Entscheidungen zum Karten- und Szenensystem. Kein Programmcode. Der Hauptkatalog steht in [FEATURE-WORKSHOP.md](FEATURE-WORKSHOP.md); hier werden die Kartendetails fortgeführt.

**Späterer ergänzender Grundstrukturbeschluss (17.10.2026):** Die bei 02.4/02.9/02.23 noch offenen Fragen zur **fachlichen Token-Ausdehnung, Platzbelegung und optionalen Kollision** wurden im Bewegungsblock unter [04.2 C](BEWEGUNG-WORKSHOP-04.2.md) entschieden: versionierte logische Größen unabhängig von Tokenbildern, kompatibel mit Rasterfrei/Quadrat/Hex und bestehenden Tür-/Hindernis-/Sensorpolicies. **Die ursprünglichen Einzelbeschlüsse einschließlich der gesondert konfigurierbaren 02.23-Türschließreaktionen gelten unverändert**; genaue Geometrie-/Höhen-/Fahrzeugregeln und Algorithmen bleiben offen. [04.1 C Bewegungsmodi](BEWEGUNG-WORKSHOP-04.1.md), [04.2 C Kollisionsmodell](BEWEGUNG-WORKSHOP-04.2.md). Diese Notiz aktualisiert den fachlichen Stand, ohne historische Fragen rückwirkend zu verändern.

**Weiterer Querschnittsbeschluss 04.3 C (17.10.2026):** [Getypte Transport-/Reit-/Passagier-/Begleitbeziehungen](BEWEGUNG-WORKSHOP-04.3.md) erlauben bei gültiger 04.1-/04.2-Bewegung ein konsistentes Mitführen berechtigter Passagiere und getrennt geprüfte Folgemoves, ohne Figuren-/Fahrzeug-/Inventaridentitäten zu verschmelzen. Szene/Stockwerk/Token, 02.9-/02.23-Hindernisse/Türen, 02.39-Sensoren, 02.13-Nodeevents, 02.25-Rechte und 02.67–02.73-Turnkontexte bleiben maßgeblich. Ein Transport schafft kein automatisch neues Sicht-, Sensor-, Node- oder Steuerrecht; insbesondere verdeckte Fahrgäste/Innenräume bleiben für nicht berechtigte Browser geheim. Die bisherigen Karten-/Node-Entscheidungen werden dadurch ergänzt, nicht ersetzt. [04.3 C Beschluss/Tests](BEWEGUNG-WORKSHOP-04.3.md).

**Ergänzender Bewegungs-Grundstrukturbeschluss 04.4 C (17.10.2026):** [Typisierte eigenständig autorisierte Positionsaktionen](BEWEGUNG-WORKSHOP-04.4.md) unterscheiden normale Bewegung, regelbasiertes Schubsen/Ziehen, Teleport, Portal-/Stockwerks-/Szenentransfer sowie gesondert berechtigtes und auditiertes SL-Versetzen. Bereits beschlossene 02.4-/02.9-/02.11-Karten-/Fog-/Zugangsrechte, 02.13–02.16-Node-/Eventlogik, 02.23-Türen, 02.25-Standards/Ausnahmen und 02.39–02.48-Sensoren bleiben gültig. **Physisch durchquerte Wegstrecken** können passende Sensoren/Nodes auslösen; ein **Teleport erzeugt keine erfundene Bewegung durch Zwischenräume**, kann aber eigene zulässige Abgangs-/Ankunfts-/Portaltrigger besitzen. 04.3-Träger-/Passagierbeziehungen müssen bei gezieltem Transfer sicher geprüft werden; kein automatischer fremder Mittransport oder Geheimnisleck. Eine SL-World-Reposition ist **nicht** das Verschieben eines Editor-/Vorlagenobjekts oder ein historischer Rollback. [04.4 C Beschluss/Tests](BEWEGUNG-WORKSHOP-04.4.md). Die bisherigen historischen Einzelbeschlüsse werden ergänzt, nicht überschrieben.

**Ergänzender Bewegungs-Grundstrukturbeschluss 04.5 C (17.10.2026):** [Optionale, versionierte Gelände-/Weg-/Passierbarkeits-/Bewegungskostenmodelle](BEWEGUNG-WORKSHOP-04.5.md) nutzen denselben 02.4-Szenenraum für Rasterfrei/Quadrat/Hex sowie 02.9-/02.23-Tür-/Hindernis- und 02.13-/02.39-Node-/Sensorregeln. 03.7-Regel-/04.1-Bewegungs-/04.2-Kollisions-/04.3-Träger-/Follower-/04.4-Positionsaktionspolicies steuern gültige passierbare Wegabschnitte und optionale Kosten; **Routen-/Kostenvorschauen sind niemals echte Bewegungsereignisse**. Nur wirksam bestätigte und erneut geprüfte VPS-Bewegungen verbuchen Turnressourcen und erzeugen legitime Zonen-/Sensor-/Node-/Entdeckungsevents. Geheime Gelände-/NPC-/Portal-/Fog-Inhalte dürfen nicht über Route oder Kosten verraten werden. Keine obligatorische Wegsuche, keine hartcodierte Geländeliste. [04.5 C Beschluss und Tests](BEWEGUNG-WORKSHOP-04.5.md). Die früheren 02-Kartenentscheidungen bleiben in Kraft.

**Nachfolgender Würfel-Grundstrukturbeschluss 05.1 C (17.10.2026):** Das [sichere, regelwerksneutrale Modell für numerische, Pool- und geeignete Symbol-/Ergebnistypen](WUERFEL-WORKSHOP-05.1.md) erweitert die **Würfel-Definitionen und Auswertungsfähigkeit** der Plattform, ohne die verbindlichen 02.63–02.67-Entscheidungen neu auszulegen: echte numerische Skillchecks mit Wurf + passendem Skill ≥ Mindestwurf (Gleichstand Erfolg); 02.64-Vorteil/Nachteil mit zwei echten Rohwürfen und einmaligem Skill; **vollständig vor Spielern verborgene unbemerkte Wahrnehmungschecks** selbst ohne Roll-/Metadatenspur; 02.65 vier geschützte Sichtbarkeitsmodi, 02.66 nur geeignete bewusste spätere Freigaben, 02.67 Log/Retention. Getrennte 02.77-Krit-/Resultat-/Systemfehlerports bleiben; ein echter RollRecord wird vom VPS **genau einmal** bestimmt, ohne zusätzliche Weltwirkung durch grafische Animation. [05.1 C Beschluss, Schnittstellen und Tests](WUERFEL-WORKSHOP-05.1.md). Historische 02-Einzelbeschlüsse bleiben in Kraft.

**Ergänzender Würfel-Grundstrukturbeschluss 05.2 C (17.10.2026):** [Geschützte, gemischte Wurfauslösung](WUERFEL-WORKSHOP-05.2.md) ermöglicht je gültiger Kampagnen-/RulePack-/Check-/Figur-/NPC-/Sensor-/Node-/Aktionspolicy manuelle Spieler-/SL-Würfe, gesonderte nicht würfelnde Genehmigungsanträge und automatische echte Serverchecks. 02.25-Rechte, 02.13-/02.39-Ereignisvalidierung, 02.63-/02.64-aktive bzw. unbemerkte echte Checks, 02.65-Vierfachsicht, 02.66-geprüfte Spätfreigabe, 02.67-Logs und 02.77-Resultat-/Technikfehlerports werden **nicht** aufgeweicht. **Ein Pending oder genehmigter Antrag ist noch kein echter Wurf**; vor einem einmaligen VPS-RollCommit werden aktuelle Quellen, Rechte und Geheimnispolicies nochmals geprüft. Spieler erhalten selbst keine Metadaten über zwingend geheime Wahrnehmung. WorldActions/04.1-Turnwechsel bleiben separat autorisiert. [05.2 C Umsetzungsplan und Tests](WUERFEL-WORKSHOP-05.2.md).

**Nachfolgender Würfel-Grundstrukturbeschluss 05.3 C (17.10.2026):** [Optionale sichere, versionierte und typisierte Würfelketten](WUERFEL-WORKSHOP-05.3.md) mit getrennten tatsächlich gezogenen Folge-/Neuwürfen, Root-/Step-Korrelation, gültigen 05.2-Freigaben und eigenständigen WorldActions. Die 02.64-Zwei-Rohwürfe-Probe, 02.65-Geheimwürfel-/Metadatenschutz, 02.66-Freigabe und 02.77-Ergebnis-/Fehlerports werden nicht verändert; keine unendlichen Triggerketten. **Konkrete Würfelmechaniken ausdrücklich später detaillieren; Block 05 grundstrukturell abgeschlossen.**

**Ergänzung zu 05.3 C – gleichzeitig präsentierte Würfel (17.10.2026):** Mehrere physisch/grafisch gleichzeitig geworfene Würfel sind erlaubt, auch wenn der VPS deren echte Rohwerte und Ergebnisauswertung nacheinander bestimmt. Eine logische Probe kann mehrere echte Faces im selben RollRecord enthalten; mehrere eigenständige Wurfaktionen bleiben getrennte RollRecords und können nur durch berechtigte Präsentationsgruppen gemeinsam animiert werden. Die Animationszeit/Server-Auswertungsreihenfolge erzeugt keine eigene Spielweltwirkung, und 02.64-/02.65-Geheimrechte bleiben unverändert. [Ergänzung und Tests](WUERFEL-WORKSHOP-05.3.md).

**Neuer NPC-Grundstrukturbeschluss 06.1 C (17.10.2026):** [Versionierte NPC-/Gegnervorlagen und konkrete getrennte Instanzen](NPC-WORKSHOP-06.1.md) übernehmen die bereits unter 02.54 C erlaubten manuellen/SL-bestätigten/automatischen Steuerungsmodi, 02.55-Wachsamkeits- und 02.56–02.59-Wissensregeln, ohne geheime NPC-/Template-/Figuren-/Fogdaten zu deklassifizieren. NPC-ID, Character-ID, Token-ID und Steamkonto bleiben getrennt; eine Vorlage allein erzeugt keinen echten NPC/Spawn/Node-/Würfel-/Inventareffekt. Genaue NPC-Zahlen und -Werte später; 06.2 C NPC-Lebenszyklus beschlossen.

**Weiterer NPC-Grundstrukturbeschluss 06.2 C (17.10.2026):** [Optionaler geschützter NPC-Lebenszyklus und Erzeugungs-/Aktivierungs-/Transfer-/Persistenzmodell](NPC-WORKSHOP-06.2.md). Validierte echte SL-/Quest-/Node-/RulePack-Ereignisse können einmalig neue Instanzen aus Vorlagen erzeugen oder bestehende Instanzen aktivieren; echter 04.4-Szenentransfer bewahrt die stabile NPC-ID und korrekt aktuelle 01-Item-/03.8-Status-/02.55-/02.59–02.62-Wissenszustände, ohne Token-/NPC-/Inventarverdopplung. Verbergen/Ruhen/Entfernen/Tod sind **nicht** identisch, inaktive Szenen fordern keine pauschale Voll-KI; 02.19, 02.25, 02.54, 02.55, 02.65 und Fog/Secret-ACL bleiben gültig. Nur berechtigte Empfänger sehen existierende oder kommende NPCs; keine Spawn-/Timer-/Cachelecks. **Konkrete NPC-Werte, Spawnmengen und Detailregeln später; Frage 06.3 Gruppen/Fraktionen/Relationen.** [06.2 C Beschluss/Tests](NPC-WORKSHOP-06.2.md).

## Bisherige Entscheidungen

| Punkt | Entscheidung | Status |
| --- | --- | --- |
| 02.1 | Kartenbilder hochladen **und** Karten direkt im Browser erstellen | Beschlossen: C |
| 02.2 | **Schnellmodus** zum Skizzieren und **erweiterter Baumodus** mit Tiles/Bauteilen und Ebenen; beide bearbeiten dieselbe Szene | Beschlossen: C |
| 02.3 | **Taktikkarten**, **Welt-/Reisekarten**, **Story-/Atmosphäre-Szenen** sowie **freier Spieltisch** | Beschlossen: C |
| 02.4 | **Rasterfrei**, **Quadratraster** oder **Hexraster**, frei konfigurierbare Maßeinheit und Maßstab je Szene | Beschlossen: C |
| 02.5 | Manuelle Sichtfreigabe und dynamische Sicht, pro Szene wählbar; Spielleiter kann jederzeit eingreifen | Beschlossen: C |
| 02.6 | Erkundete Flächen vollständig verbergen oder abgedunkelt als Erinnerung anzeigen | Beschlossen: C |
| 02.7 | Sicht und Entdeckungen pro Szene gemeinsam oder individuell verwalten | Beschlossen: C |
| 02.8 | Einfache und dynamische Beleuchtung, feste und bewegliche Lichtquellen | Beschlossen: C |
| 02.9 | Wände, Türen, Fenster: Sicht, Licht und Bewegung pro Objekt getrennt blockierbar | Beschlossen: C |
| 02.10 | Mehrere Kartenbilder frei angeordnet, überlagert und als Stockwerke/Ebenen | Beschlossen: C |
| 02.11 | Private Szenenvorbereitung, gezielte Freigabe und Entdeckung von Stockwerken über sichtbare Zugänge | Beschlossen: C |
| 02.12 | Erweiterbarer Bild- und VTT-Import mit Vorschau und auswählbarer Metadatenübernahme | Beschlossen: C |
| 02.13 | Zentrales Aktion-Reaktion-System für interaktive Objekte, ohne Programmierkenntnisse | Beschlossen: C |
| 02.14 | Einfacher Regelassistent und visueller Ablaufeditor für dasselbe Regelmodell | Beschlossen: C |
| 02.15 | Frei kombinierbare Auslöser einschließlich Echtzeit und Spielrunden | Beschlossen: C |
| 02.16 | Zeit-/Rundenauslöser pro Regel einmalig oder wiederkehrend, mit steuerbarem Start/Pause/Reset/Abbruch | Beschlossen: C |
| 02.17 | UND/ODER/NICHT-Bedingungsgruppen und Node-System mit Objekt-Ein-/Ausgängen | Beschlossen: C |
| 02.18 | Kampagnenweite Node-Verbindungen über Szenen und Stockwerke hinweg | Beschlossen: C |
| 02.19 | Ausführung in inaktiven Szenen pro Regel: sofort, vormerken oder nur wenn aktiv | Beschlossen: C |
| 02.20 | Typisierte Node-Ports mit farblich codierten Leitungen, Signal-Iststand und expliziten Inverter-Nodes | Beschlossen: C |
| 02.21 | Ereignisimpulse, anliegende Werte und Spieler-Halteschalter | Beschlossen: C |
| 02.22 | Türreaktion bei Signalverlust konfigurierbar; Schalter oder gehaltenen Taster wählen | Beschlossen: C |
| 02.23 | Tür/Barriere reagiert pro Objekt auf Figuren im Durchgang: warten, öffnen oder Schließen erzwingen | Beschlossen: C |
| 02.24 | Folgen gefährlicher Türen und Barrieren: globale Kampagnenstandards mit Objektausnahmen | Beschlossen: C |
| 02.25 | Änderung globaler Kampagnenregeln: Vorschau, Auswahl Altbestand/Neuanlagen, Ausnahmen schützen | Beschlossen: C |
| 02.26 | Frei benannte Node-Arbeitsbereiche, Gruppen, Untergraphen und kampagnenweite Querverbindungen | Beschlossen: C |
| 02.27 | Wiederverwendbare parametrisierbare Node-Bausteine und drei unabhängige Ansichten | Beschlossen: C, ergänzt |
| 02.28 | Automatische Layouts mit manueller Neuanordnung und Positionen-Fixierung | Beschlossen: C |
| 02.29 | Szenenübergreifende Leitungen: direkt oder über beschriftete Rahmen-Übergangspunkte | Beschlossen: C |
| 02.30 | Frei festlegbare primäre Anzeige-Szene oder „Kampagnenweit“ mit Referenzen in anderen Szenen | Beschlossen: C |
| 02.31 | Vollständige Node-Diagnose mit Live-Iststand, Ereignisverlauf, Schrittfolge und Breakpoints | Beschlossen: C |
| 02.32 | Gespeicherte Testszenarien mit Ausgangszustand, Eingaben, Echtzeit/Runden und Soll-Ist-Vergleich | Beschlossen: C |
| 02.33 | Testläufe pro Schaltung manuell, nach Änderungen oder vor Aktivierung festlegen | Beschlossen: C |
| 02.34 | Test-Freigaberegel je Kampagne und Schaltung: Warnung, Sperre und protokollierte Übersteuerung | Beschlossen: C |
| 02.35 | Konfigurierbare Konfliktregeln für gleichzeitige Node-Aktionen, Kampagnenstandard und Objektausnahmen | Beschlossen: C |
| 02.36 | Mehrfach-Halter je Taster wählbar, mit globalem Kampagnenstandard und Objektausnahmen | Beschlossen: C + globaler Standard |
| 02.37 | Verbindungsabbruch beim Halten: globale Sofortfreigabe oder begrenzte Nachfrist, Ausnahmen je Taster | Beschlossen: C |
| 02.38 | Bewegung, Aktionen, Reichweite und Figurenzustand beim Halten: Kampagnenstandard mit Ausnahmen | Beschlossen: C |
| 02.39 | Interaktionsreichweite global mit Ausnahmen; Präsenz- und Bewegungsmelder als Node-Objekte | Beschlossen: C + Sensoren |
| 02.40 | Sensorfilter je Sensortyp frei konfigurierbar, globale Standards und Objektausnahmen | Beschlossen: C |
| 02.41 | Frei gestaltbare Sensorzonen und deren globale Sichtbarkeit mit Objektausnahmen | Beschlossen: C + Sichtbarkeit |
| 02.42 | Hindernis-/Sichtlinienverhalten je Sensortyp: Kampagnenstandards und Sensor-Ausnahmen | Beschlossen: C |
| 02.43 | Licht und Dunkelheit sensortypabhängig, Kampagnenstandards mit Ausnahmen je Sensor | Beschlossen: C |
| 02.44 | Sensortypabhängige Verzögerung, Nachlauf, Wiederholungsimpulse und quittierbare Alarme | Beschlossen: C |
| 02.45 | Berechtigte Sensoralarm-Quittierung per SL, Bedienobjekt oder Node: global und je Sensor | Beschlossen: C |
| 02.46 | Quittierung, Stummschaltung und Rücksetzung bei fortbestehender Gefahr | Beschlossen: C |
| 02.47 | Konfigurierbare Wiederalarmierung bei neuen Ereignissen, Eskalation und Fristablauf | Beschlossen: C |
| 02.48 | Separater Alarm-Node mit regionalem/Szenen-/globalem Geltungsbereich und Ziel-/Tagfiltern; Geräuschsensoren; Global-UI später planen | Beschlossen: C + Präzisierungen |
| 02.49 | Kombinierbare Geräuschquellen; Schallbereich-Anzeige global, pro Quelle und Region mit Tutorial-Sichtbarkeit | Beschlossen: C + Sichtbarkeit |
| 02.50 | Konfigurierbare Schallausbreitung: Entfernung, Material, Öffnungen, Stockwerke sowie Quellen-/Bereichsausnahmen | Beschlossen: C |
| 02.51 | Kombinierte Lautstärkestufen und präzise Zeitverläufe; Akustik bei Kampagnenerstellung an/aus und konfigurierbar; manuelle sichtbare Schallhinweise an Szenenpositionen | Beschlossen: C + Erweiterungen |
| 02.52 | Genauigkeit sichtbarer Akustiksignale frei wählbar: exakter Punkt, ungefährer Bereich oder Richtung; Kampagnenstandard und Ausnahmen pro Hinweis/Empfänger | Beschlossen: C |
| 02.53 | Kombinierte Geräuschwahrnehmung: offensichtliche Geräusche automatisch, schwierige nach Fähigkeiten/Hörschwellen, optionaler passiver oder aktiver Probe bzw. SL-Freigabe | Beschlossen: C |
| 02.54 | NPC-Geräuschreaktionen manuell, automatisch oder nach SL-Bestätigung; NPCs generell selbst spielen oder automatisch handeln lassen, Kampagnenstandard und Einzel-/Gruppenausnahmen | Beschlossen: C + allgemeine NPC-Steuerung |
| 02.55 | NPC-Wachsamkeitsphasen und Verdacht: konfigurierbare Eskalation, Abklingen, Fristen in Echtzeit/Runden, SL-Eingriff und Ausnahmen | Beschlossen: C |
| 02.56 | Regelbasierte NPC-Kommunikation: Rufe, Sichtzeichen, Funk/Telefon, Magie, Node-/Alarm-Verbindungen; Reichweite, Empfänger, Wissensgenauigkeit und Steuerung mit Standards/Ausnahmen | Beschlossen: C |
| 02.57 | Konfigurierbare sofortige/verzögerte Zustellung, Unterbrechung, Ausfall, Ablauf, Wiederholung und SL-Eingriff pro Kommunikationsweg, Zeitbasis und Ausnahme | Beschlossen: C |
| 02.58 | Kanal- und settingabhängig mögliches Mithören, Abfangen, Blockieren, Umleiten, Fälschen und Verändern von Nachrichten mit Fähigkeiten/Proben, Standards und Ausnahmen | Beschlossen: C |
| 02.59 | Konfigurierbare Absender-/Vertrauensprüfung (Erkennung, Codewort, passive/aktive Probe, SL-Entscheid, Standards/Overrides); vernetzte Telefone, Dialog-/Passwort-/Spawn-Nodes für spätere Planung notiert | Beschlossen: C + vorgemerkte Node-Beispiele |
| 02.60 | Kampagnenweit im Sprachmenü angelegte Sprachen als erlernbare/verbesserbare Skills (wie Schießen/Nahkampf) plus Teilverständnis, Codekenntnisse, Übersetzung und konfigurierbare Proben | Beschlossen: C + Sprachskill-Ergänzung |
| 02.61 | Konfigurierbares NPC-Gedächtnis: dauerhafte, befristete und ereignisgebundene Erinnerungen; Bestätigung, Widerspruch, Korrektur und Vergessen; Standards und Ausnahmen | Beschlossen: C |
| 02.62 | NPC-Wiedererkennung nach tatsächlich gemerktem Aussehen, Stimme, Kleidung, Merkmalen und zeitlichem Kontext; Verkleidung, optionale Proben, SL-Freigabe, Standards und Ausnahmen | Beschlossen: C |
| 02.63 | Settingabhängige Verkleidungs- und Tarnidentitätsprofile; echter Wurf plus passender Skill gegen numerischen Mindestwurf bei würfelpflichtigen Fertigkeitsproben | Beschlossen: C + echte Skillprobe |
| 02.64 | Mindestwurfstufen und Ausnahmen, echte geheime Wahrnehmungswürfe; zusätzlich situatives Advantage/Disadvantage bei Überraschungen | Beschlossen: C + geheime Proben + Vorteil/Nachteil |
| 02.65 | Kampagnenweit konfigurierbare Wurfsichtbarkeit (öffentlich, Spieler+SL, nur SL, ausschließlich Server), Ausnahmen je Spieler/NPC/Probe/Node/Szene; geheime unbemerkte Wahrnehmung unveränderlich spielerseitig verborgen | Beschlossen: C |
| 02.66 | Bewusste SL-Freigabe einzelner geeigneter privater Würfe oder bereinigter Ergebnisinformationen für ausgewählte Empfänger; Original unverändert und Geheimwahrnehmung ausgeschlossen | Beschlossen: C |
| 02.67 | Konfigurierbarer Würfelprotokoll-Detailgrad und separate Speicher-/Archivfristen für Spielerlog/geschütztes Audit; zusätzliche Next-Player-Node nach gültigem Türöffnen | Beschlossen: C + Node-Zusatz |
| 02.68 | Next-Player-Node: konfigurierbare Zielwahl zwischen nächstem Teilnehmer in Turnliste, festem Spieler/Charakter und geeignetem Gruppen-/Team-/Szenen-Teilnehmer; Kampagnenstandards und Ausnahmen | Beschlossen: C |
| 02.69 | Next-Player-Ausfallprofile: warten/pausieren, berechtigt überspringen, definiertes Ersatzziel oder SL-Entscheid; Warte-/Offline-Regeln mit Kampagnen-/Node-/Szenenausnahmen | Beschlossen: C |
| 02.70 | Konfigurierbare parallele Turn-/Zugkontexte kampagnenweit, je Szene, Gruppe/Team oder Rätsel; Next-Player-Node mit festgelegter Kontext-ID und isolierter Turngeneration, Defaults/Ausnahmen | Beschlossen: C |
| 02.71 | Konfigurierbarer Figuren-Eintritt, -Austritt und Transfer zwischen Zugkontexten per SL, gültigem Szenen-/Raum-/Gruppenereignis oder Node; Rechte-, Turn- und Ressourcenschutz | Beschlossen: C |
| 02.72 | Figur je Policy exklusiv oder ausdrücklich Mitglied mehrerer Zugkontexte; nur eine echte Figur und ein Inventar, keine unbegründeten doppelten Aktions-/Bewegungs-/Itemressourcen | Beschlossen: C |
| 02.73 | Gleichzeitige Figurenaktionen nach Regelprofil unabhängig erlauben oder kollidierende Aktionen erneut geprüft serialisieren, pausieren, ablehnen bzw. SL-bestätigen; atomare Ressourcen- und Rechteprüfung | Beschlossen: C |
| 02.74 | Laufende und ausstehende Aktionen beim Ende eines Zuges | Als Nächstes |

## 02.4 – Raster und Maßstab (11.10.2026)

**Beschluss:** Für jede Szene kann der Spielleiter Rastermodus, Feldgröße, Maßstab und Maßeinheit einstellen. Beispiele: 1 Feld = 1 Meter, 1 Feld = 1,5 Meter, 1 Feld = 5 Fuß, oder eine eigene frei benannte Einheit.

- Rastermodi: **kein Raster**, **Quadrat**, **Hex**.
- Das Raster kann sichtbar oder verborgen sein, ohne Kartenbild, Token, Objekte oder Zeichnungen zu löschen.
- **Rasteranzeige** und **Einrasten am Raster (Snap)** sollen getrennte Einstellungen sein. Freie Bewegung bleibt bei Bedarf möglich.
- Marker und Figuren benötigen rasterunabhängige kanonische Weltpositionen; Rendern und Messung beziehen sich auf die Szeneinstellungen.
- Ein Szenenwechsel soll weder Charaktere noch Kampagneninventare beeinflussen.
- Alle Einstellungen und Positionen müssen bei Reconnect und Neustart erhalten bleiben.

**Offen und nicht als beschlossen zu behandeln:** Hexausrichtung (spitze/flache Oberkante), Diagonalbewegungsregeln, Positionieren und Ausrichten des Rasters über importierten Bildern, Raster-Snap im Kampf, konkrete Distanz-/Reichweitenberechnung bei unterschiedlichen Regelwerken sowie MVP-Priorität.

### Technische Vorbereitung (Entwurf)

Ein konfigurierbares `SceneGrid`-Objekt könnte Felder für `kind` (`none`, `square`, `hex`), `cellSize`, `origin`, `scale`, `unit`, `visible` und `snap` besitzen. Dies ist nur ein konzeptionelles Beispiel, noch keine endgültige API. Positionsspeicherung und Darstellung müssen entkoppelt bleiben.

## 02.5 – Sichtbereiche und Nebel des Krieges (11.10.2026)

**Beschlossen: Variante C – manueller und dynamischer Sichtmodus, je Szene einstellbar.**

- **Manueller Modus:** Der Spielleiter kann Kartenbereiche gezielt aufdecken und wieder verdecken, z. B. durch Malen/Markieren von Sichtflächen.
- **Dynamischer Modus:** Der sichtbare Bereich ergibt sich aus Figurenposition, konfigurierbarer Sichtweite sowie später Wänden, Türen, Hindernissen, Licht und besonderen Sichtfähigkeiten.
- **Spielleiter-Eingriff:** Auch bei dynamischer Sicht kann der Spielleiter Bereiche manuell aufdecken oder verbergen, ohne den Modus wechseln zu müssen.
- **Rechte und Geheimnisse:** Verborgene Tokens, Gegner, Fallen, Notizen und nicht freigegebene Kartenelemente dürfen nicht lediglich visuell mit Nebel überdeckt werden. Der Server muss den für jeden Empfänger erlaubten Zustand berechnen und nur berechtigte Informationen an dessen Browser übertragen.
- **Persistenz:** Einstellungen, manuelle Aufdeckungen und notwendige Sichtzustände bleiben bei Reconnect und Serverneustart erhalten.
- **Szenentypen:** Fog/Sichtberechnung ist optional; Storyansichten oder freie Spieltische müssen es nicht verwenden.

**Noch offen:** Ob Entdeckungen für alle Spieler geteilt oder individuell gespeichert werden, wie Licht- und Wandberechnung im Detail funktioniert, wie Spielleiter-Übersteuerungen priorisiert werden, ob Sichtverläufe gespeichert werden und welche Teile zur ersten Version gehören.

## 02.6 – Bereits erkundete Bereiche (11.10.2026)

**Beschlossen: Variante C – pro Szene konfigurierbar.**

Der Spielleiter wählt, wie sich Kartenbereiche nach dem Verlassen der aktuellen Sicht verhalten:
- **Vollständig verdecken:** Bereits besuchte Bereiche verschwinden wieder vollständig im Nebel.
- **Erkundungserinnerung:** Bereits erkundete Bereiche bleiben als abgedunkelte, bekannte Kartenfläche sichtbar.
- **Manuelle Übersteuerung:** Der Spielleiter kann jederzeit wieder Bereiche aufdecken oder verdecken.

**Aktuelle Sicht ist nicht dasselbe wie Erinnerung.** Gegner, bewegliche Figuren, Fallen und neue Veränderungen in einem aktuell nicht sichtbaren Bereich werden durch eine gespeicherte Kartenerinnerung nicht automatisch sichtbar. Vertrauliche Objektdaten bleiben serverseitig geschützt.

**Technischer Entwurf:** Aktuell sichtbare Flächen, erkundete Flächen und manuelle Spielleiter-Übersteuerungen getrennt verwalten. Die Szeneneinstellung sowie notwendige Zustände müssen bei Reconnect und Neustart erhalten bleiben.

**Noch offen:** Gemeinsame oder individuelle Entdeckungshistorie, Erinnerung an ehemals sichtbare statische Objekte, Vorrang manueller Änderungen und Verhalten beim Wechsel des Erinnerungsmodus.

## 02.7 – Gemeinsame oder individuelle Sicht (11.10.2026)

**Beschlossen: Variante C – pro Szene wählbar.**

- **Gemeinsame Gruppensicht:** Die für die Gruppe freigegebenen aktuell sichtbaren Bereiche und die Erkundungserinnerung werden gemeinsam verwaltet. Entdeckt ein Mitglied einen neuen Raum, wird dieser gemäß den Szeneneinstellungen auch für die anderen Gruppenmitglieder freigegeben.
- **Individuelle Sicht:** Jeder Spieler sieht die Bereiche, die seiner eigenen Sicht und seinen Freigaben entsprechen, und besitzt eine eigene Entdeckungshistorie. Das unterstützt getrennte Gruppen oder geheime Erkundungen.
- **Spielleiter-Übersteuerung:** Der Spielleiter kann in beiden Modi einzelne Bereiche gezielt zeigen oder verbergen. Nicht für den jeweiligen Empfänger freigegebene NPCs, Fallen, Geheimräume und andere sensitive Objektdaten bleiben serverseitig verborgen.
- **Zusammenhang mit 02.6:** Gemeinsame/individuelle Sicht ist **unabhängig** davon, ob erkundete Flächen wieder komplett verschwinden oder als abgedunkelte Erinnerung bleiben.
- **Persistenz:** Szenenmodus, erkundete Sichtflächen und notwendige Freigaben bleiben bei Reconnect und Serverneustart erhalten.

**Technische Planung:** Szenenweites Sichtprofil plus gegebenenfalls getrennte Spieler-Sichtzustände, die serverseitig in eine erlaubte Gruppensicht bzw. individuelle Sicht umgerechnet werden. Der Browser bekommt nur berechtigte Daten. Die genaue Frage, ob einzelne Figuren eines Spielers ihre Sicht kombinieren, bleibt für die spätere Detailplanung offen.

**Weitere offene Punkte:** Umgang mit getrennten Gruppen und einem späteren Zusammenführen ihrer Entdeckungen, manuelle Freigaben nur an ausgewählte Spieler, mehrere Charaktere pro Spieler und Wechsel des Modus innerhalb einer laufenden Szene.

## 02.8 – Licht und Dunkelheit (11.10.2026)

**Beschlossen: Variante C – pro Szene einfache oder dynamische Beleuchtung.**

- **Einfach:** Licht wird optisch dargestellt; Sicht steuert der Spielleiter über die bereits beschlossenen Nebel- und Sichtoptionen.
- **Dynamisch:** Umgebungshelligkeit, Dunkelheit und Lichtquellen beeinflussen die Szene und können mit der dynamischen Sichtberechnung interagieren.
- **Feste Lichtquellen:** Fackeln, Straßenlampen, Lagerfeuer oder Raumbeleuchtung.
- **Bewegliche Lichtquellen:** Taschenlampen, Laternen oder Scheinwerfer, die einer Figur, einem Gegenstand oder einem Fahrzeug folgen.
- **Pro Lichtquelle einstellbar:** Farbe, Reichweite, Intensität, Richtung/Lichtkegel und Ein-/Ausschaltzustand. Berechtigte Spieleraktionen und Story-Ereignisse dürfen Lichtquellen schalten; der Spielleiter kann eingreifen.
- **Persistenz:** Einstellungen und aktive Lichtzustände bleiben nach Neustart oder Neuverbindung erhalten.

**Technischer Planungsgrundsatz:** Lichtdarstellung, Sicht- und Schattengeometrie, Fog-of-War-Masken und serverseitiger Geheimnisschutz sind getrennte Komponenten. Lichtquellen sollen als wiederverwendbare Komponenten für Szenenobjekte, Charaktere und Fahrzeuge funktionieren.

**Offen:** Schattenqualität und Performance, Akku/Brennstoff, zeitliche und rundenbasierte Lichtdauer, Nachtsicht/Spezialsicht, genaue Wechselwirkung mit Hindernissen und Entwicklungsreihenfolge.

## 02.9 – Wände, Türen und Fenster (11.10.2026)

**Beschlossen: Variante C – pro Hindernis frei konfigurierbar.**

- **Unabhängige Eigenschaften:** Wände, Türen, Fenster, Glasflächen, Kraftfelder und andere Hindernisse können getrennt **Sicht**, **Licht** und **Bewegung** blockieren oder passieren lassen.
- **Beispiele:** Eine Steinwand blockiert alle drei; Glas lässt Licht und Sicht durch, blockiert jedoch Bewegung; eine magische Barriere kann nur Bewegung verhindern.
- **Interaktive Zustände:** Türen, Fenster und Barrieren besitzen optional Zustände wie geöffnet, geschlossen, verriegelt, zerstört oder deaktiviert. Zustandsänderungen können ihre Blockade- und Sichtregeln verändern.
- **Verbindung zum universellen Schloss-/Fallensystem (01.10–01.16):** Eine Tür kann Schlüssel, Keycards, Codes, Fehlversuchsgrenzen und Folgen besitzen. Eine Verriegelung ist nicht gleichbedeutend mit einer Licht- oder Sichtbarriere.
- **Verborgene Objekte:** Geheime Türen, unsichtbare Barrieren und versteckte Fallen dürfen vor Entdeckung oder SL-Freigabe nicht als Geheimnis im Spielerclient sichtbar werden. Berechtigte Spiellogik bleibt serverseitig.
- **Persistenz und Mehrspieler:** Zustandswechsel werden synchronisiert und nach Reconnect/Neustart wiederhergestellt. Sicht-/Lichtberechnung und gegebenenfalls Bewegungskollision verwenden den aktuellen Zustand.

**Technische Vorbereitung:** Wiederverwendbare Hindernis-/Durchlasskomponente an Szenenobjekten mit Sicht-, Licht- und Bewegungseigenschaften; keine hardcodierten Regeln je Objektgrafik. Der Zeichen-/Tile-Editor muss logische Hindernisse von bloß dekorativ gemalten Linien unterscheiden.

**Noch offen:** Ausmaß der Kollision (Token-Größen, Fahrzeuge, fliegende Figuren), besondere Einweg-/Spezialbarrieren, genaue Sichtlinienberechnung und welche Zustandsübergänge animiert werden.

## 02.10 – Mehrere Karten und Stockwerke in einer Szene (11.10.2026)

**Beschlossen: Variante C – frei kombinierbare Karten und Stockwerke.**

- **Mehrere Kartenbilder:** Ein Spielleiter kann mehrere Karten innerhalb derselben Szene platzieren: nebeneinander, überlappend oder auf unterschiedlichen Karten-/Bild-Ebenen.
- **Anordnung:** Jedes eingefügte Kartenbild kann unabhängig **verschoben, gedreht und skaliert** werden; individuelle Ausrichtung auf einen gemeinsamen Szenenmaßstab ist vorzusehen.
- **Stockwerke/Etagen:** Szenen dürfen mehrere getrennte Stockwerke wie Keller, Erdgeschoss und Obergeschoss besitzen, zwischen denen der Spielleiter ohne Szenenwechsel umschaltet.
- **Positionen und Objekte:** Tokens, Türen, Hindernisse, Lichtquellen, Fallen und andere Objekte werden der richtigen Kartenfläche bzw. Etage zugeordnet. Das Umschalten entfernt keine Spielobjekte.
- **Sicht und Geheimnisse:** Nebel des Krieges, Licht und berechtigte Sichtbereiche müssen auch in mehrstöckigen Szenen funktionieren. Ein verborgenes Stockwerk oder geheimer Kartenabschnitt darf nicht bloß optisch ausgeblendet sein; nicht berechtigte Clients bekommen keine vertraulichen Daten.
- **Spielzustand:** Etagenzuordnung, Transformationsdaten, Platzierungen und Sichtzustände werden persistent gespeichert und synchronisiert.

**Technischer Entwurf:** Eine Szene besitzt mehrere Kartenbild-Instanzen mit individuellen Transformationsdaten (Position/Rotation/Skalierung/Reihenfolge) sowie logische Ebenen und optionale Stockwerke. Eine **Render-Ebene** (z. B. Dekoration) ist nicht dasselbe wie ein **Stockwerk** (z. B. Obergeschoss); beides separat modellieren. Lokale Koordinaten je Kartenbild müssen auf den Szenenraum transformierbar sein.

**Noch offen:** Wie Figuren Treppen, Aufzüge, Portale und andere Stockwerksübergänge benutzen; ob verschiedene Spieler gleichzeitig unterschiedliche Etagen sehen; getrennte oder gemeinsame Fog-Masken je Stockwerk; Kollisionsberechnung über mehrere Etagen; Begrenzung von Bildgröße/Anzahl; Import mehrstöckiger Dateien.

## 02.11 – Szenen vorbereiten und flexibel freigeben (11.10.2026)

**Beschlossen: Variante C – flexible Freigabe von Szenen und Inhalten.**

- **Privater Entwurf:** Spielleiter können Szenen, Stockwerke und Objekte vorbereiten, ohne dass Spieler diese schon sehen oder ihre Existenz erfahren.
- **Spielervorschau:** Spielleiter können prüfen, wie die Szene für einen bestimmten Spieler oder eine Gruppe mit ihren tatsächlichen Rechten aussieht.
- **Gezielte Freigabe:** Szenen werden wahlweise allen, ausgewählten Gruppen oder einzelnen Spielern zugänglich. Auch nachträglich können neue Stockwerke und Inhalte gezielt veröffentlicht oder weiter verborgen bleiben.
- **Freigaberegel für Stockwerke – zusätzlich ausdrücklich gewünscht:** Pro Stockwerk ist einstellbar, dass seine **Existenz und Auswahlmöglichkeit für Spieler erst sichtbar wird, sobald sie einen zugeordneten Zugang tatsächlich sehen** (beispielsweise Treppe, Leiter, Aufzug, Luke, Tür, Portal oder Fahrzeugzugang). Die Freigabe wird durch das Entdecken des Zugangspunkts ausgelöst, **nicht erst beim Betreten**. Spielleiter dürfen Stockwerke außerdem gezielt sofort freigeben.
- **Entdecken ist nicht Betreten und nicht vollständiges Aufdecken:** Die Entdeckung eines Zugangs kann eine Etage im Etagenwähler bekannt machen, gibt aber **nicht automatisch alle Räume, Gegner, Fallen oder Kartendetails dieser Etage preis**. Sicht/Fog, Zugangsregeln, Schlösser und tatsächlicher Stockwerkswechsel gelten unabhängig voneinander.
- **Gruppensicht vs. individuelle Sicht (02.7):** Im gemeinsamen Sichtmodus kann die Entdeckung für die Gruppe gelten; im individuellen Modus nur für berechtigte Entdecker. Die Feinheiten bei Gruppenwechsel und mehreren verbundenen Zugängen bleiben offen.
- **Geheime Zugänge:** Ein verborgener Treppenaufgang löst keine Enthüllung aus, bevor der Zugang selbst nach den geltenden Sicht-/Entdeckungsregeln sichtbar bzw. entdeckt wurde.
- **Serverseitiger Schutz und Persistenz:** Zugangsbeobachtung, Entdeckungsfreigabe, Veröffentlichungsstatus und Empfängerrechte werden serverseitig geprüft, gespeichert und an berechtigte Clients synchronisiert. Eine bloße UI-Ausblendung reicht nicht aus.

**Technische Planungsfolgen:** Die Konzepte **Szenenentwurf**, **Freigabe für Spieler/Gruppe**, **Stockwerk entdeckt**, **Zugangspunkt erkannt**, **aktuelle Sicht**, **Stockwerk begehbar** und **Inhalt per Fog sichtbar** müssen getrennt modelliert werden. Zugangspunkte können eine Liste verknüpfter Stockwerke freischalten. Noch offen: Priorität mehrerer Zugänge, erneutes Verbergen bereits bekannter Stockwerke, Etagenwechsel und Szenenfreigabe während paralleler Spielgruppen.

## 02.12 – Erweiterbares Kartenimport-System (11.10.2026)

**Beschlossen: Variante C – Bilder und unterstützte VTT-Daten importieren, mit Vorschau und frei wählbarer Datenübernahme.**

- **Bildimport:** Kartenbilder wie PNG, JPG und WebP sollen sich als bearbeitbare Szenenhintergründe importieren lassen.
- **VTT-Import:** Ein erweiterbares Importsystem für geeignete Austauschformate, z. B. DD2VTT/UVTT, ist vorzusehen. Welche konkreten Varianten vollständig unterstützt werden, muss anhand ihrer Spezifikationen und Testdateien geprüft werden; nicht jede Datei enthält alle nachfolgend genannten Daten.
- **Importvorschau:** Vor der Übernahme sieht der Spielleiter, welche Inhalte und Metadaten erkannt wurden, und kann sie gezielt auswählen: Kartenbild, Raster/Maßstab, Wände/Sichtlinien, Lichtquellen, Türen und weitere unterstützte Objekte, soweit in der Quelle vorhanden.
- **Zuordnung:** Importierte Wände, Lichtquellen oder Türen sollen nach Möglichkeit in die bereits geplanten generischen Szenenobjekte umgewandelt werden. Nicht unterstützte Eigenschaften werden kenntlich gemacht; der Spielleiter kann sie anschließend manuell ergänzen.
- **Erweiterbarkeit:** Spätere Importadapter für weitere Kartenwerkzeuge/Dateiformate können ergänzt werden, ohne den Szeneneditor neu entwerfen zu müssen.
- **Sicherheit:** Dateien validieren, Größe/Typ begrenzen, keine unkontrollierten Makros/Skripte aus importierten Daten ausführen. Interaktive Objekte und Geheimnisse erst nach Spielleiterprüfung/Freigabe an berechtigte Spieler übertragen.
- **Erhalt des Originals:** Quelldatei/Bild nicht destruktiv verändern; eingefügte Karten und übernommene Objekte bleiben im AdventureShift-Editor separat editierbar.

**Noch offen:** Exakte Liste unterstützter Dateiformate und Versionsvarianten, Umgang mit mehrstöckigen Dateien, Export zurück in Fremdformate, fehlende oder abweichende Einheiten, Vorschau- und Fehlerbehandlung sowie konkrete Implementierungsreihenfolge.

## 02.13 – Interaktive Objekte und Aktion-Reaktion-System (11.10.2026)

**Beschlossen: Variante C – frei konfigurierbare Interaktionen und ein zentrales, übersichtliches Aktion-Reaktion-System.** Der Spielleiter soll ohne Programmierkenntnisse selbst bestimmen können, was ein Ereignis auslöst, welche Bedingungen dafür gelten und welche Reaktionen eintreten.

### Grundmodell: WENN – FALLS – DANN

1. **Auslöser (WENN):** Ein Spieler klickt oder benutzt ein Objekt, betritt einen Bereich, gibt einen Code ein, bewegt eine Figur, ein Zustand verändert sich oder ein Zeit-/Rundenereignis tritt ein. Die konkrete vollständige Auslöserliste wird später beschlossen.
2. **Bedingungen (FALLS):** Beispielsweise passende Berechtigung, Schlüssel/Keycard im Inventar, richtiger Code, aktivierter Schalter, bestimmter Objektzustand oder erfüllte Questbedingung. Bedingungen sollen sich bei Bedarf mit UND/ODER verknüpfen lassen.
3. **Reaktionen (DANN):** Beispielsweise Tür öffnen/verschließen, Licht schalten, Alarm auslösen, Falle aktivieren, Figur teleportieren, neue Etage nach 02.11 bekannt machen, Gegenstände freigeben, NPC erscheinen lassen, Mitteilung anzeigen oder ein anderes Ereignis auslösen. Mehrere Folgen und geordnete Abläufe sollen möglich sein.

**Beispiel:** Spieler betätigt Schalter -> System prüft Schlüsselkarte und Berechtigung -> Geheimtür öffnet sich, Alarm geht aus und Raumbeleuchtung wird eingeschaltet. Das System muss auch einfache Ein-Schritt-Regeln ohne unnötige Konfiguration ermöglichen.

### Verbindliche Bedienanforderungen

- **Eine wiederverwendbare Oberfläche für alle Objektarten:** Türen, Schalter, Truhen, Terminals, Fahrzeuge, Fallen, Figuren, Gegenstände, Szenen- und Story-Ereignisse. Keine getrennte Programmlogik oder eigene komplizierte Bedienung je Objekttyp.
- **Ohne Programmierung:** Auslöser, Bedingungen und Reaktionen aus verständlich benannten Auswahlmöglichkeiten zusammenstellen; keine Pflicht, Code, Skripte oder Konfigurationsdateien zu schreiben.
- **Übersichtlich:** Kurze menschenlesbare Regelzusammenfassung (z. B. „Wenn Schalter A betätigt wird und Karte B vorhanden ist, öffne Tür C“), klare Unterscheidung von Auslöser/Bedingung/Reaktion, leicht auffindbare Verknüpfungen und sinnvolle Vorlagen.
- **Einfacher Einstieg und komplexe Möglichkeiten:** Eine einzelne Wenn-Dann-Regel soll schnell angelegt werden können. Fortgeschrittene Regeln können mehrere Bedingungen, mehrere Aktionen, Verzweigungen, Reihenfolgen und ggf. Verzögerungen/Timer verwenden. Deren genaue Grenzen, UI und Semantik werden separat festgelegt.
- **Testen und Fehlersuche:** Regel vor der Spielrunde prüfen können; erkennbar machen, welches Zielobjekt fehlt, welche Bedingung nicht erfüllt ist oder warum ein Ereignis nicht ausgelöst hat. Spielleiterseitiges Ereignis-/Ausführungsprotokoll ohne Preisgabe von Geheimnissen an Spieler.
- **Vorlagen:** Beispielsweise „Schalter öffnet Tür“, „Bodenplatte löst Falle aus“, „Code startet Alarm“, „Portal wechselt Stockwerk“, „Lampe schalten“; Vorlagen müssen anpassbar sein.

### Technische und Sicherheitsanforderungen

- **Gemeinsamer serverautoritärer Ereignis-/Regelkern** mit typisierten Auslösern, Bedingungen und erlaubten Aktionen sowie überprüften Zielobjekt-Referenzen; regelwerks- und genreunabhängig.
- **Sicherheit:** Berechtigungen und Geheimdaten konsequent serverseitig prüfen. Nur erlaubte Reaktionen; keine beliebigen, ungeprüften Benutzerskripte.
- **Konsistenz:** Objektzustände und Inventaränderungen transaktional, konkurrierende Aktionen kontrolliert und Folgewirkungen idempotent, damit etwa Fallen nicht durch Doppelanfragen zweimal explodieren.
- **Vermeidung von Endlosschleifen:** Ein Regelereignis, das weitere Ereignisse auslöst, muss mit Ausführungsgrenzen/Zyklenschutz verarbeitet werden.
- **Persistenz/Mehrspieler:** Regeln, aktivierte/deaktivierte Zustände und notwendige Timer nach Reconnect und Serverneustart erhalten; nur berechtigte Spieler über Folgen informieren.
- **Offen:** Exakte Auslöser-/Aktionsbibliothek, Regeln für mehrstufige Abfolgen und Verzögerungen, Ereignis-Reihenfolge, Versions-/Undo-Verhalten, maximaler Umfang und Einführungsphase.

## 02.14 – Bedienung des Aktion-Reaktion-Editors (11.10.2026)

**Beschlossen: Variante C – einfacher Regelassistent UND visueller Ablaufeditor für dasselbe Regelmodell.**

- **Einfacher Regelassistent:** Schrittweise, verständlich beschriftete Auswahl von **WENN (Auslöser)**, **FALLS (Bedingungen)** und **DANN (Reaktionen)**. Gut für schnelle und überschaubare Regeln, ohne grafische Knoten verknüpfen zu müssen.
- **Visueller Ablaufeditor:** Blöcke/Knoten mit Verbindungen für komplexe Ereignisketten, mehrere Aktionen, Verzweigungen, Reihenfolge und optional später Zeitbedingungen.
- **Eine gemeinsame Regeldefinition:** Wechsel zwischen beiden Ansichten ohne doppelte oder abweichende Regeln und ohne Informationsverlust; Speichern aus einer Ansicht aktualisiert die andere.
- **Komplexität sicher behandeln:** Wenn eine Regel Knoten oder Verknüpfungen enthält, die der einfache Assistent nicht vollständig bearbeiten kann, wird sie dort als verständliche, gegebenenfalls nur teilweise bearbeitbare Zusammenfassung angezeigt. Beim Zurückwechseln dürfen weder Verzweigungen noch Parameter stillschweigend gelöscht oder verändert werden. Erweiterte Funktionen bleiben im visuellen Modus bearbeitbar.
- **Nutzerführung:** Durchsuchbare Objekt- und Ereignisauswahl, einsteigerfreundliche Vorlagen, klare Beschriftungen und Verknüpfungsvorschau, menschenlesbare Zusammenfassung der Regel.
- **Test und Fehlersuche:** In beiden Ansichten Möglichkeit zur Prüfung/Simulation vor der Freigabe, Anzeige erkannter Fehler oder fehlender Referenzen und ein verständliches, nur für berechtigte Spielleiter sichtbares Ausführungsprotokoll.
- **Sicherheit:** Beide Oberflächen verwenden dieselbe validierte, serverseitig ausgeführte und berechtigungsgeschützte Ereignisdefinition; keine frei ausführbaren Nutzerskripte.

**Technische Planung:** Die Regelstruktur muss unabhängig von einer konkreten Oberfläche gespeichert werden. Der Assistent und die grafische Ansicht sind zwei Bearbeitungsoberflächen für dasselbe Modell. Regeländerungen werden geprüft, Versionierung/Undo und Testmodus sind vorzusehen; genaue UI-Details, Vorlagen, Simulationsumfang und Kopier-/Vorlagenfunktionen bleiben offen.

## 02.15 – Umfangreiches Auslösersystem mit Echtzeit und Spielrunden (11.10.2026)

**Beschlossen: Variante C – ereignisübergreifend konfigurierbare Auslöser, ausdrücklich in beiden Zeitmodellen.**

### Geplante Auslöserkategorien

- **Direkte Aktionen:** Anklicken, Benutzen, Öffnen/Schließen, Schalter betätigen, Terminal bedienen, manuelle Spielleiteraktion.
- **Bewegung und Umgebung:** Bereich betreten oder verlassen, sich einem Objekt nähern, Figur oder Fahrzeug bewegen; weitere Distanz- und Kollisionsregeln später.
- **Zustandsänderungen:** Türzustand, Schalter, Lichtquelle, Schloss/Falle, NPC-/Fahrzeugstatus, Regeln aus anderen Objekten.
- **Gegenstände und Inventar:** Aufheben, Ablegen, Ausrüsten, Verwenden, Verbrauch einer Ladung, Schlüssel/Keycard einsetzen.
- **Codes und Sicherheit:** Richtige oder falsche Codeeingabe, bestimmter Fehlversuchsschwellenwert, Entriegelung, Falle ausgelöst; bestehendes Zugangssystem aus 01.10–01.16 wiederverwenden.
- **Story und Spielverlauf:** Questfortschritt, individuelle Story-Flags, Spielleiterereignis und Regelereignisse; konkretes Datenmodell später.
- **Echtzeit-Auslöser:** **Sekunden, Minuten oder Stunden** nach einem definierten Startpunkt oder Ereignis (z. B. drei Echtzeitsekunden nach Betreten einer Bodenplatte).
- **Rundenbasierte Auslöser:** **Nach einer festgelegten Anzahl Spielrunden** oder bei einem definierten Rundenereignis, sofern die Kampagne einen Rundenmodus verwendet (z. B. Alarm nach zwei abgeschlossenen Runden).

### Zwingende Trennung beider Zeitarten

- **Echtzeit** und **Spielrunden** sind eigenständige, pro Auslöser wählbare Zeitgrundlagen, ohne automatische Umrechnung. Ein Ablauf von zwei Runden ist nicht gleich einer festen Zahl Sekunden.
- **Ohne aktives Rundensystem** dürfen rundenbasierte Regeln nicht irrtümlich durch verstrichene Echtzeit auslösen.
- **02.16 beschlossen:** Einmalige oder wiederkehrende Timer und deren Starten, Pausieren, Fortsetzen, Zurücksetzen und Abbrechen sind pro Regel konfigurierbar. **Weiterhin offen:** Exakte Semantik bei pausierter Kampagne, ausgeschaltetem Server, Offline-Spielern und gleichzeitigen Ereignissen.
- Bereits definierte Echtzeit- und Rundenwirkungen auf Gegenstände, Schlösser und Fallen sollen dieselben grundlegenden Zeitkonzepte nutzen, aber je Objekt eigene Regeln behalten.

### Ausführung und Bedienung

- Auslöser sind im **einfachen Regelassistenten** und im **visuellen Ablaufeditor** aus 02.14 auswählbar, mit klaren Bezeichnungen wie „Wenn Spieler Bereich betritt“, „Nach 30 Sekunden“ oder „Nach 3 Spielrunden“.
- Bedingungen (FALLS) und Reaktionen (DANN) werden getrennt von den Auslösern modelliert; mehrere Reaktionen und objektübergreifende Ketten bleiben möglich.
- Ereignisse, Timer und Rundenzähler werden serverautoritär und nach Berechtigung verarbeitet, bei Reconnect/Neustart persistent; doppelte Clientaktionen lösen keine doppelte Konsequenz aus.
- Ereignisketten erhalten Limits gegen unendliche Schleifen. Der Spielleiter kann geplante Auslöser vorab testen, ohne das echte Spiel zu verändern.

**Offen:** Konkrete Timersemantik bei pausierter Kampagne oder Serverausfall, Bedingungen/Operatoren, Reihenfolge bei gleichzeitigen Auslösern, Auslöser- und Reaktionsbibliothek im Detail und Implementierungsphase. **Einmalig/wiederkehrend und steuerbarer Timerzustand sind durch 02.16 entschieden.**

## 02.16 – Einmalige und wiederkehrende Zeit-/Rundenauslöser (11.10.2026)

**Beschlossen: Variante C – pro Regel frei konfigurierbar.**

- **Einmalig:** Ein Auslöser tritt nach einer eingestellten Dauer (z. B. 30 Echtzeitsekunden) oder einer definierten Zahl Spielrunden genau einmal ein.
- **Wiederkehrend:** Ein Auslöser kann nach einem bestimmten Echtzeit- oder Rundenintervall mehrfach eintreten (z. B. alle 20 Sekunden oder jede zweite Runde).
- **Steuerung durch Aktionen/Ereignisse:** Timer lassen sich je nach Regel **starten, pausieren, fortsetzen, zurücksetzen, neu starten oder abbrechen**, auch über andere Auslöser oder eine berechtigte Spielleiteraktion.
- **Zeitarten getrennt:** Ein Echtzeitintervall ist keine feste Zahl Spielrunden. Rundenbasierte Zeitabläufe benötigen einen aktiven Rundenzähler; das Aktion-Reaktion-System darf sie nicht von sich aus mit Sekunden simulieren.
- **Einheitliches No-Code-Design:** Der einfache Regelassistent und der visuelle Ablaufeditor aus 02.14 bieten dieselben Konfigurationsmöglichkeiten für Wiederholung, Intervall und zulässige Steueraktionen, soweit die Oberfläche diese Regeln darstellen kann.
- **Sicherheit und Konsistenz:** Persistente Timerzustände, Zuordnung zur Regel/Objektinstanz, autorisierte Änderungen und idempotente Ausführung; ein einzelner Tick darf bei doppelten Anfragen oder nach Reconnect nicht mehrfach als dieselbe Auslösung verarbeitet werden. Wiederkehrende Auslöser sind dennoch bewusst mehrere Ereignisse.
- **Beispiele:** Nach Betreten eines Bereichs nach 5 Sekunden einmal eine Tür schließen; alle 3 Spielrunden eine Warnleuchte einschalten, solange ein Alarm aktiv ist; Countdown durch einen Schalter anhalten oder zurücksetzen.

**Noch offen:** Ob Echtzeit beim Pausieren der Kampagne oder bei ausgeschaltetem Server weiterläuft, ob versäumte wiederkehrende Ereignisse nachgeholt oder übersprungen werden, maximale Wiederholungszahl, parallele Timer, Zeitanzeige für Spieler und genaues Verhalten beim Speichern/Laden. Keine stillschweigende Festlegung zu diesen Punkten.

## 02.17 – Bedingungsgruppen und objektgebundenes Node-System (11.10.2026)

**Beschlossen: Variante C – frei kombinierbare UND-/ODER-/NICHT-Bedingungen, einschließlich gruppierter und verschachtelter Bedingungen.** Dazu die ausdrückliche Anforderung: Ein späteres **visuelles Node-/Verbindungssystem** ist nicht nur eine optionale Darstellung, sondern ein grundlegender Baustein für das Aktion-Reaktion-Konzept.

### Objekte besitzen von Anfang an Ein- und Ausgänge

1. **Beim Platzieren wird jedes interaktive Objekt benannt**, z. B. eine Tür mit dem Namen „Nordtor“ in der Szene „Festung“, Stockwerk „Erdgeschoss“. Der Spielleiter soll den Namen später ändern können.
2. **Passende Anschlüsse (Ports) stehen ab Erstellung für jedes Objekt bereit:** Bereits beim Platzieren erhält jedes Szenenobjekt eine typabhängige Anschlussdefinition; eine Tür besitzt sinnvolle Tür-Ein-/Ausgänge, ein Schalter andere und ein Fahrzeug eigene. Auch zunächst dekorative Objekte bleiben als Node auffindbar und können einen kleinen Satz allgemeiner Steuerports besitzen oder später erweiterte Fähigkeiten erhalten. Die Ports sind Teil des Objekttyps und können mit geeigneten Erweiterungsmodulen später ergänzt werden.
3. **Objekt-Node über eine Such-/Ereignisauswahl einfügen:** Die Palette bietet verständliche Bezeichnungen nach dem Muster `Tür – [Szene] – [Stockwerk] – [Türname]` mit Such- und Filterfunktionen. Wird die Node im Ablaufeditor platziert, verweist sie auf **dasselbe bereits existierende Szenenobjekt**, nicht auf eine Kopie.
4. **Ein- und Ausgänge durch Verbindungen/Pfade koppeln:** Der Spielleiter zieht eine Verbindung von einem Ereignis-Ausgang zu einem passenden Aktions-Eingang; Bedingungen und Zwischenschritte können dazwischenliegen. So entstehen einfache oder komplexe Schaltungen ohne Programmierung.
5. **Regeln bleiben auch im einfachen Assistenten nutzbar (02.14):** Die Node-Ansicht ist die detaillierte grafische Darstellung derselben Regeldefinition. In der Assistentenansicht sollen einfache Verbindungen und komplexere Regeln als verständlicher Text erkennbar bleiben, ohne Graphen beim Umschalten zu verlieren.

### Beispiel einer Tür-Node

**Objektbezeichnung in der Auswahl:** `Tür – Festung – Erdgeschoss – Nordtor`

| Typ | Anschluss-Beispiele | Verhalten |
| --- | --- | --- |
| **Eingang (Aktion)** | `Entriegeln`, `Öffnen`, `Schließen`, `Verriegeln` | Ein verbundenes Ereignis fordert die jeweilige Zustandsänderung an; tatsächliche Zulässigkeit wird serverseitig geprüft |
| **Ausgang (Ereignis)** | `Bei Benutzung`, `Entriegelt`, `Geöffnet`, `Geschlossen`, `Verriegelt`, `Zugriff verweigert` | Sendet das Ereignis an verbundene Nodes, sobald das jeweilige Ereignis tatsächlich eintritt |
| **Bedingungswerte (optional)** | `Ist verriegelt?`, `Ist offen?` | Werte können als Bedingung gelesen werden, statt eine Aktion zu starten |

**Beispielverschaltung:** `Schalter – aktiviert` → `Bedingung: passende Keycard UND Alarm aus` → `Tür – Nordtor [Eingang: Entriegeln]` → `Tür – Nordtor [Ausgang: Entriegelt]` → `Tür – Nordtor [Eingang: Öffnen]`.

Die Tür-Eingänge dürfen nicht unkontrolliert bestehende Rechte/Schlösser umgehen. Gegebenenfalls muss die Automatik ausdrücklich berechtigt sein oder zuvor die vorgesehenen Voraussetzungen erfüllen. Ein fehlgeschlagener Aktionsversuch darf nicht fälschlich ein „Entriegelt“-Ereignis ausgeben.

### Wiederverwendbares Architekturprinzip

- **Objekttyp definiert Port-Vorlage:** z. B. `Door`, `Switch`, `Light`, `Vehicle`, `Trap`, `Container`, `Terminal`, `Timer`, `Character`; anwendbare Ein-/Ausgänge ergeben sich aus den Fähigkeiten des Objekts und sollen im Editor angezeigt werden.
- **Objektinstanz erhält stabile ID:** Referenzen in Verbindungen verwenden interne unveränderliche IDs, nicht den sichtbaren Türnamen. Umbenennen einer Szene/Tür/Etage aktualisiert nur die Anzeige, nicht bestehende Verbindungen.
- **Port- und Verbindungstypen:** Ereignis-Ausgänge und Aktions-Eingänge sowie Bedingungs-/Datenwerte dürfen nicht ohne Prüfung beliebig verbunden werden. Ungültige Verknüpfungen werden verständlich erklärt, nicht stillschweigend ausgeführt. Genaue Typspezifikation ist eine offene Detailfrage.
- **Lebenszyklus:** Objekt löschen, verschieben oder seine Fähigkeiten ändern muss in betroffenen Graphen sichtbar werden, z. B. als klar markierte fehlende Referenz; keine unbeabsichtigte Bindung an ein anderes Objekt mit gleichem Namen.
- **Serverautorität:** Alle Node-Aktionen prüfen Berechtigungen, gültige Zustände, Szene-/Spielerfreigaben und vorhandene Voraussetzungen. Ereignisse werden synchronisiert; Zyklen, doppelte Auslösung und unendliche Ketten sind abzufangen.
- **Genre-/Regelwerkneutralität:** Das System ist auch für Items, Fallen, NPCs, Fahrzeuge, Quests, Zeit- und Runden-Timer geeignet. Spezialisierte Module können neue Node-/Port-Vorlagen anbieten, ohne bestehende Regeln zu ändern.

**Mit 02.18 entschieden:** Node-Verbindungen können **kampagnenweit**, also auch über Szenen- und Stockwerksgrenzen hinweg, aufgebaut werden. **Weiterhin offen:** Umgang mit inaktiven Szenen (02.19), genaue Ereignis- und Datenports, Gruppierung von Bedingungen/Werten, Graph-Verwaltung, Debug-Ansicht, Vorlagen, Reihenfolge konkurrierender Ereignisse und Implementierungsphase.

## 02.18 – Kampagnenweite Node-Verbindungen (11.10.2026)

**Beschlossen: Variante C – Verbindungen dürfen jede passende Node innerhalb derselben Kampagne erreichen.** Das schließt andere Stockwerke und andere Szenen derselben Kampagne ausdrücklich ein.

- **Beispiel:** Ein Terminal im Raumschiff-Kontrollraum sendet das Ereignis `Code bestätigt` über einen Verbindungspfad an `Tür – Maschinenraum – Unterdeck – Schott A`, Eingang `Entriegeln`. Der erfolgreiche Statuswechsel kann weitere Nodes benachrichtigen.
- **Node-Auswahl:** Objekte anderer Szenen/Stockwerke erscheinen in der durchsuchbaren Palette mit ihrem vollständigen Namen und Ort. Die referenzierte Objekt-ID bleibt stabil, auch wenn Tür oder Szene umbenannt wird.
- **Kampagnengrenze:** Es werden **keine unkontrollierten Verbindungen in andere Kampagnen** zugelassen. Verbindungsziele und zulässige Aktionseingänge werden serverseitig auf identische Kampagne und passende Berechtigungen geprüft.
- **Unabhängig von geöffnetem Browser:** Für die Auswertung einer Verbindung darf nicht erforderlich sein, dass ein Spieler gerade die Zielszene in seinem Browser anzeigt. Wie schnell bzw. wann Änderungen an **inaktiven Szenen** stattfinden, entscheiden wir ausdrücklich in 02.19.
- **Geheimnisse und Freigaben:** Die Existenz anderer/geheimer Szenen, Stockwerke und Objekte darf durch eine Verbindung nicht an unberechtigte Spieler gelangen. Sichtbarkeit der Graphen und Spielleiter-Rechte getrennt von der Spieleransicht; Clients erhalten nur freigegebene Zustandsänderungen.
- **Verkettung und Zuverlässigkeit:** Weitergeleitete Ereignisse benötigen eindeutige Kennungen, Berechtigungs- und Zustandsprüfung sowie Begrenzungen gegen endlose Schleifen. Zielobjekte und Verbindungen müssen persistent bleiben; fehlende/gelöschte Ziele werden als Fehler angezeigt, nicht durch gleichnamige Objekte ersetzt.
- **Echtzeit und Spielrunden:** Beide Zeitmodelle aus 02.15/02.16 können auch kampagnenweite Verbindungen auslösen; der Zielort ändert die Zeitsemantik nicht automatisch.

**Technische Planung:** Objekt- und Node-IDs kampagnenweit referenzierbar; `campaign_id` für jede Referenz prüfen. Ereignisse über einen serverseitigen Ereignisrouter an Ziel-Objektinstanzen zustellen, ohne die grafische Zielszene laden zu müssen. Das tatsächliche Verhalten bei inaktiven Ziel-Szenen bleibt offen.

## 02.19 – Node-Ereignisse in inaktiven Szenen (11.10.2026)

**Beschlossen: Variante C – pro Regel frei konfigurierbarer Ausführungsmodus**, auch wenn die Zielszene gerade in keinem Spielerbrowser angezeigt wird.

- **Sofort ausführen:** Der Server wendet die Wirkung unmittelbar auf das Zielobjekt in der anderen Szene an. Beispiel: Ein Terminal entriegelt sofort die Maschinenraumtür; diese ist beim späteren Betreten bereits entriegelt.
- **Bis zur Szenenaktivierung vormerken:** Der Server speichert die ausstehende Aktion zuverlässig und führt sie beim Aktivieren der Zielszene aus. Beispiel: Eine Begrüßungssequenz oder ein vorbereiteter Alarm beginnt erst beim Betreten bzw. Aktivieren.
- **Nur bei aktiver Zielszene:** Die Aktion wird nur ausgeführt, wenn die Szene zum Auslösezeitpunkt aktiv ist; sonst **entfällt sie und wird nicht nachgeholt**. Beispiel: Ein kurzlebiger optischer Effekt soll in einer unbenutzten Szene nicht später abgespielt werden.

**Zentrale Anforderungen:**
- Der Spielleiter kann die Ausführungsart für jede Node-Regel wählen, sowohl im Regelassistenten als auch im visuellen Node-Editor. Die Einstellung gehört zur gespeicherten Regel, nicht zur Grafikverbindung allein.
- Eine vorgemerkte Aktion ist **nicht bereits erfolgreich ausgeführt**. Beim tatsächlichen Ausführungszeitpunkt müssen aktuelle Zielobjektzustände, Berechtigungen und Bedingungen erneut geprüft werden. Ungültige oder gelöschte Ziele dürfen nicht stillschweigend ersetzt werden.
- Vorgemerkte Einträge erhalten eindeutige IDs und nachvollziehbare Zustände (z. B. wartend, ausgeführt, übersprungen, fehlgeschlagen, abgebrochen). Ein und derselbe Eintrag darf nicht mehrfach ausgeführt werden; wiederkehrende Ereignisse aus 02.16 besitzen dagegen jeweils eigene Auslösungen.
- Wirkungen und Warteschlangen müssen Verbindungsabbrüche und Serverneustarts überstehen; nur berechtigte Spielleiter sehen die interne Warteliste und Fehlerursachen. Eine entfernte Szene wird durch Node-Verbindungen **nicht automatisch für Spieler freigegeben**.
- Echtzeit- und Rundenereignisse aus 02.15/02.16 bleiben zwei getrennte Zeitgrundlagen. Der Modus „bis Szenenaktivierung“ ersetzt nicht die explizit konfigurierte Timerlogik.

**Noch offen:** Was genau als „Szenenaktivierung“ gilt (z. B. durch einen Spieler, eine Gruppe oder den Spielleiter), Umgang mit mehreren Gruppen, Gültigkeitsdauer einer Vormerkung, Reihenfolge konkurrierender Ereignisse und das Nachholen wiederholter Auslösungen. Diese Regeln werden später einzeln festgelegt.

## 02.20 – Typisierte Node-Ports, farbige Leitungen, Signalanzeige und Inverter (11.10.2026)

**Beschlossen: Variante C – vollständig typisierte Ein- und Ausgänge**, mit zusätzlichen verbindlichen Anforderungen für die Bedienbarkeit und die spätere saubere technische Planung.

### 1. Ein- und Ausgänge für unterschiedliche Signal- und Datenarten

- **Aktion/Ereignis:** Ein Ausgang meldet eine tatsächlich erfolgte Aktion bzw. ein Ereignis; ein passender Eingang kann eine Aktion anfordern (z. B. `Tür.Entriegelt` -> `Licht.Einschalten`).
- **Boolescher Zustand (Ja/Nein):** z. B. `Tür.IstVerriegelt` oder `Schalter.IstAn`.
- **Zahlenwerte:** z. B. verbleibende Ladungen, Entfernung, Rundenanzahl oder andere regelunabhängige numerische Werte.
- **Textwerte:** z. B. Nachrichten oder freigegebene Statusbezeichnungen; geheime Codes müssen vertraulich bleiben.
- **Typisierte Referenzen:** Verweise auf Figuren, Gegenstände und andere Szenenobjekte (später eventuell Szenen, Stockwerke, Gruppen).
- **Erweiterbare Typen:** Die Port-Vorlagen werden versionierbar geplant, sodass Module neue Typen/Ports ergänzen können.

Nur **kompatible Ports** sollen sich verbinden lassen. Im Editor sind Ein- und Ausgangsrichtung sowie Datentyp klar erkennbar; fehlerhafte Verbindungen erhalten verständliche Hinweise statt stiller Konvertierungen.

### 2. Farblich codierte Verbindungen – zusätzlich ausdrücklich beschlossen

- Jede Leitung/Portart erhält eine **eindeutige visuelle Typ-Kennzeichnung durch Farbe**, z. B. getrennte Kategorien für Ereignis, Boolesches Signal, Zahl, Text oder Objektverweis. Die tatsächlichen Farben legen wir später gemeinsam im UI-Design fest.
- **Farbe kennzeichnet den Typ**, der **aktuelle Signalzustand wird davon unabhängig** kenntlich gemacht, beispielsweise durch Leuchtintensität, Linienanimation, Markierung und beschriftete Statusanzeige. Damit sind „verbunden“, „kein Signal“, „Signal liegt an“ und „Fehler“ unterscheidbar.
- Für Zugänglichkeit nicht nur auf Farbe vertrauen: Port-Symbole, kurze Typbezeichnungen und optional einblendbare Signaltexte müssen die Bedeutung ebenfalls erklären.

### 3. Ist-Zustand und Signallauf im Test

- Im Node-Editor ist in der **Test-/Diagnoseansicht** erkennbar, ob ein Ein-/Ausgang **physisch verbunden**, aber derzeit **inaktiv**, oder ob dort **tatsächlich ein Signal/Wert** anliegt bzw. gerade ein Ereignis eintrifft.
- Eine vorhandene Verbindung bedeutet **nicht**, dass sie aktiv ist. Bei Dauerwerten sollte der aktuelle Wert angezeigt werden (z. B. `false`, `true`, `3`); bei Ereignissen wenigstens die sichtbare Auslösung bzw. das zuletzt beobachtete Ereignis.
- Der Spielleiter kann entlang der Verbindungen nachvollziehen, **an welcher Node ein Signal angekommen ist, welche Bedingung erfüllt wurde und warum etwas nicht ausgeführt wurde**.
- **Realen Ist-Zustand** aus dem autoritativen Server unterscheiden von einer **isolierten Simulation/Testausführung**, die keine tatsächlichen Türen, Inventare, Fallen oder Timer verändern darf.
- Aus der fehlenden Anzeige bei einer inaktiven Szene oder nicht freigegebenen Datenquelle darf niemals auf einen falschen Zustand geschlossen werden; berechtigte Diagnose und verständliche Statushinweise sind erforderlich.

### 4. Explizite Inverter-Nodes – zusätzlich ausdrücklich beschlossen

- Jeder für **logische Signale** geeignete Eingang oder Ausgang kann durch Vorschalten bzw. Nachschalten einer **sichtbaren Inverter-Node (NICHT/NOT)** logisch umgekehrt werden. Die Umkehrung soll als eigener Knoten im Graphen sichtbar bleiben statt einer versteckten Option am Port.
- Grundprinzip: `TRUE` -> **Inverter** -> `FALSE` und `FALSE` -> **Inverter** -> `TRUE`. Ein Beispiel: `Tür.IstVerriegelt` -> `NOT` -> `Freigabe erlaubt`.
- Eine Inverter-Node besitzt einen **passenden booleschen Eingang und einen booleschen Ausgang**; Porttypprüfung verhindert, dass z. B. Text, ein Ereignisimpuls oder eine Figurenreferenz ohne explizite Typkonvertierung als boolescher Wert behandelt wird.
- **02.21 beschlossen:** Ereignisports übertragen Impulse; Zustands-/Datenports liefern anliegende Werte. Präzise Impulsdauer und Unterbrechungsverhalten von Halteaktionen werden später spezifiziert. Für Ereignisse wird **keine stillschweigende „Umkehrung“** angenommen.

### Technische Qualitätsanforderungen

Node- und Portvorlagen erhalten stabile IDs/Typdefinitionen; Kanten besitzen Quell-/Zielportreferenzen und ihren Datentyp. Der **Graphzustand**, der **aktuelle Server-Signalzustand**, **letzter Ereignisimpuls** und die **rein grafische Präsentation** (Farbe, Linienführung, Hervorhebung) dürfen nicht vermischt werden. Statusänderungen werden nur für berechtigte Spielleiter dargestellt; doppelte Events, Endlosschleifen, konkurrierende Ausführungen und nicht mehr vorhandene Referenzen sind explizit zu behandeln. **Besondere Sorgfalt bei Spezifikation und Tests vor der Implementierung ist verbindliche Anforderung.**

**Noch offen:** Genaue Typ- und Portfamilien, die Farbpalette, Verhalten und Lebensdauer von Signalen, eventuelle Konverter-Nodes, Datenschutz bei Debug-Daten, Höchstgröße eines Graphen, Live-Debug-Frequenz und Undo/Versionierung.

## 02.21 – Impulse, Dauersignale und Halteschalter (11.10.2026)

**Beschlossen: Variante C.** Das Node-System unterstützt **kurze Ereignisimpulse** und **dauerhaft anliegende Zustands-/Datenwerte**, abhängig vom Porttyp.

- **Betätigungsimpuls:** Beim Betätigen kann ein einzelnes Ereignis ausgegeben werden. Dies ist kein dauerhaftes Signal.
- **Schalter (rastend):** Das platzierte Schaltobjekt besitzt den Modus **Schalter**; es speichert EIN oder AUS bis zur nächsten Betätigung.
- **Taster (gehalten):** Das gleiche Objekt kann stattdessen als **Taster** konfiguriert sein. Der boolesche Ausgang bleibt nur während des tatsächlichen Haltens EIN und wird beim Loslassen AUS. Ein zusätzlicher kurzer Ereignisimpuls beim Drücken ist ein separater Port, kein Ersatz für den Haltezustand.
- **Kooperatives Mehrspieler-Beispiel:** Spieler A hält den Schalter, sodass `Schalter.Gehalten = true` gilt. Dadurch ist eine verbundene Tür oder Barriere passierbar, während Spieler B hindurchgeht. Spieler A und B können gleichzeitig unabhängig handeln. Beim Loslassen wird `false` übertragen. Das Verhalten der Tür beim Signalverlust legen wir in 02.22 fest.
- **Node-Diagnose:** Der Spielleiter erkennt getrennt, ob eine Leitung verbunden ist, ob ein anliegendes Signal EIN oder AUS ist, ob gerade ein Ereignisimpuls eintrifft und ob ein Fehler vorliegt. Der reale Server-Iststand ist von einer gefahrlosen Simulation zu unterscheiden.
- **Inverter:** Eine sichtbare NOT-Node kehrt boolesche Dauerzustände um; Ereignisimpulse werden ohne gesonderte Umwandlung nicht invertiert.
- **Serverlogik:** Halteaktionen werden an berechtigte Spieler-/Figurenaktionen gebunden. Server validiert Start, Aufrechterhaltung und Ende. Verbindungsverlust, Reichweite, Spielerwechsel und gleichzeitiges Halten durch mehrere Figuren sind gesondert zu spezifizieren. Clients dürfen nicht unbegrenzt ein aktives Signal behaupten, nachdem die Aktion ungültig geworden ist.

**Noch offen:** Genauer Lebenszyklus von Halteaktionen, Eingabebedienung auf Maus/Touch/Tastatur, sichere Kollision bei schließender Tür, Impulsdauer und Ausführung bei Netzwerkstörungen. Die sofortige physische Schließung bei Signalverlust ist ausdrücklich **nicht** automatisch beschlossen.

## 02.22 – Türreaktion bei Signalverlust und Schalter-/Taster-Modus (11.10.2026)

**Beschlossen: Variante C – pro Zielobjekt konfigurierbar.** Wenn ein anliegendes Haltesignal wegfällt, kann die angeschlossene Tür oder Barriere **sofort** in den Ausgangszustand zurückkehren, **geöffnet/aktiviert bleiben** oder **nach einer einstellbaren Echtzeitdauer bzw. Anzahl von Spielrunden** reagieren.

**Zusätzliche ausdrückliche Vorgabe:** Beim Anlegen und Bearbeiten eines Schaltobjekts gibt es eine verständliche Einstellung **Schalter oder Taster**:

| Modus | Bedienung | Boolescher Ausgang |
| --- | --- | --- |
| **Schalter** | Einmal betätigen schaltet um; erneutes Betätigen wieder zurück | Bleibt EIN oder AUS bis zur nächsten Zustandsänderung |
| **Taster** | Muss gedrückt bzw. gehalten werden | EIN nur solange eine berechtigte Halteaktion andauert; beim Loslassen AUS |

Ein getrennt nutzbarer **Ereignisimpuls beim Betätigen** bleibt möglich, darf aber nicht fälschlich den anliegenden Zustand eines Tasters ersetzen.

**Kooperatives Beispiel:** Spieler A hält einen Taster. Dessen `IstGedrückt`-Ausgang liefert EIN und ermöglicht Spieler B den Durchgang durch die Tür. Beim Loslassen wird AUS übertragen. Ob die Tür schließt oder offen bleibt, bestimmt **die eigene Einstellung dieser Tür**. Schalter-Modus und Tür-Reaktion sind somit getrennte Konfigurationen.

**Technische Anforderungen:** Objektinstanzen bekommen eine persistente Betriebsart `Schalter/Taster`, einen booleschen Ist-Zustand sowie separate Ereignisausgänge. Halteaktionen werden vom Server einer berechtigten Figur zugeordnet; Clients dürfen kein ungültig gewordenes Signal endlos aufrechterhalten. Die genaue Behandlung von Verbindungsabbrüchen, gleichzeitigen Haltern und Eingabegeräten bleibt zu spezifizieren. Verzögerungen verwenden getrennte Echtzeit- und Runden-Timer. Im Node-Test sind Verbindung, anliegendes EIN/AUS und Betätigungsimpuls unterscheidbar.

**Nicht vorweggenommen:** Eine sich schließende Tür kann mit einer Figur im Durchgang kollidieren. Schadensfolgen, Bewegung und Sicherheitsverhalten sind noch nicht entschieden; keine automatische Einklemm- oder Schadenregel annehmen.

## 02.23 – Figuren im Durchgang bei schließenden Türen und Barrieren (11.10.2026)

**Beschlossen: Variante C – das Verhalten ist pro Tür oder Barriere konfigurierbar.**

- **Warten / Schließen verhindern:** Ist der Durchgang belegt, wird das Schließen nicht vollendet. Das Schließen kann nach Freigabe des Durchgangs erneut versucht werden; die genaue Wiederholungsregel wird später festgelegt.
- **Wieder öffnen:** Erkennt die Tür beim Schließversuch eine Figur, stoppt sie und öffnet wieder; dieser Zustandswechsel kann andere Nodes ansteuern.
- **Trotz Hindernis schließen:** Der Spielleiter kann eine gefährliche Tür oder Barriere so einstellen, dass ihr Schließvorgang auch bei belegtem Durchgang fortgesetzt wird. Welche Auswirkungen das auf betroffene Figuren hat, ist **nicht automatisch vorgeschrieben**, sondern folgt aus einem getrennten, später zu konfigurierenden Effekt/Regelprofil.

**Beispiel:** Spieler A lässt einen gehaltenen Taster los. Die Tür versucht gemäß 02.22 zu schließen, während Spieler B noch im Türrahmen steht. Die Einstellung dieser Tür entscheidet, ob sie wartet, wieder aufschwingt oder trotz Hindernis den Schließvorgang fortsetzt.

### Anforderungen für das Node- und Bewegungsmodell

- Die Durchgangserkennung muss die tatsächliche Platzierung von Figuren und den logischen Tür-/Barrierenbereich berücksichtigen; reine Bildschirmgrafik ist kein zuverlässiger Kollisionsnachweis. Genauer Algorithmus, Token-Größe, Raster-/Freibewegung, Fahrzeuge und unterschiedliche Höhen bleiben separat offen.
- **Schließbefehl ist nicht automatisch erfolgreiches Schließen:** Für das Node-System unterscheiden wir Ereignisse wie `Schließen angefordert`, `Hindernis erkannt`, `Schließen blockiert`, `Wieder geöffnet` und `Geschlossen`. Erfolgs-Ausgänge feuern nur nach tatsächlichem Statuswechsel.
- Mehrspielerbewegungen und Schließversuche werden serverseitig konsistent verarbeitet. Doppelte Netzwerknachrichten dürfen keine unbeabsichtigten mehrfachen Auswirkungen erzeugen.
- Schalter-/Tastermodus aus 02.22 sowie Echtzeit-/Rundenverzögerungen bleiben unabhängig von der Kollisionseinstellung des Zielobjekts.
- **Keine vorausgesetzten Schäden oder automatische Verschiebung von Figuren:** Wer Schaden erhält, wie eine Figur blockiert oder verschoben wird und welche Rettungsmöglichkeiten bestehen, sind gesonderte Spielregelentscheidungen. Der Spielleiter kann eine Tür als gefährlich konfigurieren, ohne dass AdventureShift ein festes D&D-Schadenssystem erzwingt.
- Der Spielleiter sieht im Node-Testmodus den realen Schließstatus sowie gegebenenfalls Hinderniserkennung und gewählte Reaktion; eine isolierte Simulation darf keine echte Figur verletzen oder bewegen.

**Noch offen:** Kollisionsgeometrie und Größe, gleichzeitige Figuren, Verhalten bei dauerhaft blockiertem Durchgang, Schadens- und Bewegungseffekte, Effekte wiederkehrender Schließversuche und Definition von „trotz Hindernis geschlossen“ im konkreten Regelprofil.

## 02.24 – Folgen gefährlicher Türen und globale Kampagnenstandards (11.10.2026)

**Beschlossen: Variante C mit ausdrücklicher Erweiterung – solche Verhaltensregeln werden bereits bei der Kampagnenerstellung zentral festgelegt.**

### Globale Vorgaben bei der Kampagnenerstellung

- Unter **Kampagneneinstellungen → Spielregeln → Umgebung und Interaktionen** (Arbeitstitel) kann der Spielleiter **globale Standardregeln** festlegen. Insbesondere für Türen, Schleusen, Tore, Fallen und Barrieren sollen sich wiederkehrende Einstellungen und Konsequenzen nicht an jedem neuen Objekt einzeln wiederholen müssen.
- **Typische Voreinstellungen:** Verhalten bei Figur im Durchgang aus 02.23 (warten, wieder öffnen, erzwungen schließen); zulässige Folgen einer erzwungenen Schließung (kein zusätzlicher Effekt, Warnung/Alarm, Schadens-/Statuseffekt, Node-/Story-Ereignis); gegebenenfalls Regeln mit **Echtzeit** oder **Spielrunden**.
- Die Kampagneneinstellung verweist bei Schadens-/Statusberechnung auf das **aktivierte Regelprofil**, soweit vorhanden. Der Systemkern schreibt keinen festen D&D-Schaden vor. Ohne passendes Regelmodul darf keine nicht konfigurierte automatische Schadensberechnung angenommen werden.
- **Vererbung und individuelle Ausnahmen:** Neue Objekte übernehmen zunächst die **globalen Kampagnenstandards** ihres Typs. Die Spielleiter können für besondere Objekte einzelne Eigenschaften **bewusst überschreiben**, etwa eine Sicherheitsschleuse mit gefährlichem Schließverhalten. Eine Ausnahme soll klar als solche markiert sein.
- **Nicht nur Türen:** Das Prinzip zentraler Kampagnenstandards soll für ähnliche allgemein nutzbare Objekt- und Interaktionsregeln vorbereitet werden, statt später zahlreiche unabhängige Eigenschaftsfenster pflegen zu müssen. Welche anderen Einstellungen im Kampagnenassistenten erscheinen, wird im Kampagnen-Workshop detailliert geklärt.
- **Regeln und Signalgraph getrennt:** Der Standard bestimmt das normale Objektverhalten; das Node-System kann zusätzliche definierte Ereignisse auslösen. Freigaben, Schlüssel-/Codeprüfung und Sicherheitsvorgaben dürfen durch die globale Vererbung nicht unbeabsichtigt umgangen werden.

### Beispiel

Kampagne: Standardtüren warten, wenn eine Figur im Durchgang steht; **kein automatischer Schaden**. Eine eigens konfigurierte Sicherheitsschleuse darf stattdessen schließen und ein Node-Ereignis `Einklemmung erkannt` auslösen, dessen Folgen das aktive Regelprofil definiert.

### Architektur- und UX-Folgen

Kampagneneinstellungen benötigen versionierbare, serverseitig geprüfte **Regelprofile und Standardwerte**, die per Objekttyp an Instanzen vererbt werden können. Jede Objekt-Eigenschaft sollte erkennbar machen: **„Kampagnenstandard“** oder **„individuell überschrieben“**. In der Spielleiteransicht sind die tatsächlich wirksamen Werte (Ist-Konfiguration) zu zeigen. Änderung von Kampagnenregeln erfordert nachvollziehbare Auswirkungen auf vorhandene Instanzen.

**Mit 02.25 entschieden:** Änderungen an Kampagnenstandards bieten vorab eine Vorschau und eine Wahl zwischen nur künftigen Objekten oder auch bestehenden, bisher nicht individuell überschriebenen Objekten. Bereits gesetzte individuelle Ausnahmen bleiben geschützt. **Offen:** Pflichtangaben im Kampagnenassistenten, Regelprofilwechsel, genaue Konflikt-/Rollback-Semantik und die technische Vererbungsauflösung.

## 02.25 – Änderungen globaler Kampagnenregeln während einer Kampagne (11.10.2026)

**Beschlossen: Variante C – bei jeder Änderung mit Vorschau wählbar, ob bestehende Objekte aktualisiert werden.**

- **Vorschau vor dem Speichern:** Der Spielleiter sieht für die betroffene Einstellung den bisherigen und neuen Standard, die betroffenen Objekttypen sowie eine nachvollziehbare Aufschlüsselung: vorhandene Objekte ohne Ausnahme, vorhandene mit individueller Ausnahme und neu zu erstellende Objekte. Geheime Objekte bleiben vor unberechtigten Spielern geschützt.
- **Wahl bei jeder Änderung:** (1) **Nur für künftig neu erstellte Objekte** oder (2) **auch auf vorhandene Objekte ohne individuelle Ausnahme anwenden**. Bereits festgelegte Ausnahmen werden bei beiden Varianten respektiert und nicht überschrieben.
- **Alte Werte erhalten:** Bei der Auswahl „nur künftige Objekte“ behalten bestehende Objekte ihren wirksamen bisherigen Wert, obwohl sich der neue Kampagnenstandard für Neuanlagen ändert. Dazu muss die technische Vererbung bestehende Werte gegebenenfalls als historische Vorlage/Snapshot sichern, statt sie versehentlich dynamisch mitzuändern.
- **Bestehende Objekte aktualisieren:** Bei bewusster Anwendung auf den Altbestand ändern sich ausschließlich die ausgewählten, bisher nicht individuell überschriebenen Eigenschaften. Nach Möglichkeit den bisherigen und neuen wirksamen Wert anzeigen; eine individuelle Ausnahme bleibt sichtbar und unverändert.
- **Bewusste Freigabe:** Der Spielleiter bestätigt die Änderung erst nach Vorschau. Serverseitige Rechteprüfung, nachvollziehbare Speicherung und Versions-/Änderungsprotokoll sind erforderlich. Fehler bei teilweise möglichen Aktualisierungen dürfen nicht still übergangen werden.
- **Laufender Spielzustand:** Änderung einer Türregel ist von einem tatsächlichen Türöffnungs- oder Türschließereignis zu unterscheiden. Keine unvorhergesehenen Node-Auslösungen nur durch das Umschreiben einer Einstellung. Welche bereits aktiven Timer/Schaltungen neu bewertet werden, ist später separat zu spezifizieren.
- **Genre- und Regelprofilneutral:** Die Vererbungslogik soll für Türen, Fallen, allgemeine Objektinteraktionen und künftige Kampagnenstandardwerte gelten; kein festes D&D-System voraussetzen.

**Beispiel:** In einer Kampagne lautet der bisherige Standard „Tür wartet bei Hindernis“. Der Spielleiter ändert ihn auf „Tür öffnet wieder“. Er kann auswählen, ob diese Regel erst für neue Türen gilt oder auch für die bestehenden Standardtüren. Eine besondere Sicherheitstür mit eigener Einstellung „trotz Hindernis schließen“ bleibt in beiden Fällen unverändert.

**Noch zu spezifizieren:** Nachträgliche Rücknahme/Undo, Versionsmigration, aktive Spielereignisse beim Regelwechsel, Auswahl einzelner Objektgruppen innerhalb einer globalen Änderung und Verhältnis von Regelprofil- zu Kampagnenstandards.

## 02.26 – Frei organisierbare Node-Arbeitsbereiche (11.10.2026)

**Beschlossen: Variante C – frei benannte und organisierbare Node-Pläne mit Gruppen, Untergraphen und kampagnenweiten Verknüpfungen.**

- **Mehrere Node-Arbeitsbereiche:** Spielleiter können beliebig viele logisch getrennte, benannte Arbeitsflächen innerhalb einer Kampagne anlegen, um beispielsweise „Türen und Schalter“, „Fallen“, „Hauptquest“ oder „Raumschiffsteuerung“ getrennt zu bearbeiten. Die genaue technische Obergrenze für sehr große Kampagnen ist später zu prüfen.
- **Freie Organisation:** Ein Arbeitsbereich lässt sich nach Szene, Stockwerk, Thema oder Funktion benennen und ordnen; die Zuordnung ist organisatorisch, **keine technische Beschränkung der Verbindungen** auf diese Szene oder dieses Stockwerk.
- **Gruppen und Untergraphen:** Zusammengehörige Nodes können auf einer Arbeitsfläche gruppiert, umbenannt, eingeklappt und wieder aufgeklappt werden. Ein Untergraph lässt sich als übersichtlicher Block mit klaren Ein-/Ausgängen darstellen, während seine innere Schaltung weiterbearbeitbar bleibt.
- **Kampagnenweite Querverbindungen:** Die Entscheidung 02.18 gilt auch über verschiedene Arbeitsbereiche hinweg. Eine Leitung von „Türen und Schalter“ kann einen Eingang einer Node in „Hauptquest“ ansteuern. Querverbindungen müssen als nachvollziehbare Referenzen und sichtbare Übergänge erkennbar bleiben; nichts darf beim Einklappen stillschweigend getrennt werden.
- **Gesamtübersicht:** Eine durchsuchbare Liste/Übersicht zeigt alle Arbeitsbereiche und Querverbindungen, einschließlich Quell- und Zielort. Navigationsfunktionen sollen von einer referenzierten Node oder Verbindung zum richtigen Plan führen.
- **Farbcodes und Iststand erhalten:** Port- und Leitungstypen bleiben wie 02.20 farblich codiert, die Testansicht unterscheidet weiterhin verbundenes Kabel, aktiven Zustand, Ereignisimpuls und Fehler, auch bei Übergängen zwischen Arbeitsbereichen.
- **Objekt-Identität bewahren:** Ein Objekt-Node ist eine **Referenz auf eine konkrete, stabile Objektinstanz**, nicht automatisch eine neue Tür, ein neuer Schalter oder eine Kopie des Objektzustands. Ein Objekt kann aus mehreren Ansichten referenziert werden, darf dadurch aber keine widersprüchlichen Spielzustände erhalten.
- **Rechte und Geheimnisse:** Arbeitsbereiche mit vertraulichen Spielleiter-Schaltungen bleiben für unberechtigte Spieler verborgen. Verschieben, Umgruppieren oder Umbenennen ändert nicht unbemerkt die Sicherheit der referenzierten Szenen oder Objekte.
- **Persistenz:** Zugehörigkeiten, Gruppierung, Untergraph-Ansichten, Layout, Zoom und Positionen sollten unabhängig von den autoritativen Ausführungsregeln speicherbar sein. Änderungen an der Darstellung dürfen keine echte Node-Aktion auslösen.

**Technische Planung:** Ein logischer kampagnenweiter Graph bzw. verknüpfbare Teilgraphen mit stabilen Objekt-, Node-, Port- und Kanten-IDs. Arbeitsbereiche/Groups sind persistente editorseitige Ordnungs- und Sichtstrukturen. Für gruppierte Bausteine gelten explizite Schnittstellenports; die tatsächliche Signalauswertung verbleibt beim Server. Zwischen Arbeitsbereichen sind klare Sprungverweise und Referenz-/Verbindungsprüfungen vorzusehen.

**Mit 02.27 entschieden:** Wiederverwendbare parametrisierbare Untergraph-Vorlagen mit Ein-/Ausgängen, stabilen Versionen sowie drei Layoutansichten: manuell, automatisch szenenweise gerahmt und automatisch szenenunabhängig. **Weiter offen:** Details von Untergraph-Schnittstellen, Navigation bei tausenden Nodes, frei definierte Hierarchie, Mehrpersonenbearbeitung, algorithmische Leitungsführung und Kopierregeln.

## 02.27 – Wiederverwendbare Node-Bausteine und drei Layoutansichten (11.10.2026)

**Beschlossen: Variante C – wiederverwendbare, parametrisierbare Node-Bausteine mit definierter Schnittstelle, ergänzt durch drei unterschiedliche Darstellungsansichten desselben Node-Netzes.**

### Wiederverwendbare Schaltungs-Bausteine

- Ein Spielleiter kann eine Node-Gruppe bzw. einen Untergraphen als **benannte Vorlage** speichern, mit klaren **Eingangs- und Ausgangsports** und **einstellbaren Parametern** (z. B. Zeitverzögerung, Anzahl Spielrunden, boolesche Optionen).
- Beispiel: „Zeitgesteuerte Sicherheitstür“ umfasst Taster-/Schalterlogik, Timer, Bedingungen und Türsteuerung. Beim Einsetzen werden die konkreten Tür-/Schalterinstanzen und die benötigten Parameter gewählt.
- Eine gespeicherte Vorlage ist **nicht automatisch eine zweite echte Tür**: Objektverweise werden beim Einsetzen ausdrücklich auf vorhandene konkrete Objekte gebunden; die internen Node- und Portreferenzen sind stabil und validierbar.
- Vorlagen erhalten eine **Version**. Ändert der Spielleiter die Vorlage später, dürfen bereits eingesetzte Schaltungen **nicht ungefragt oder mit Informationsverlust** geändert werden. Ob eine Instanz Updates bewusst übernimmt, wird separat geplant.
- Als wiederverwendbarer Untergraph kann ein Baustein kompakt dargestellt und für die Bearbeitung wieder aufgeklappt werden; dies passt zum Beschluss 02.26 über Gruppen und mehrere Node-Arbeitsbereiche.

### Drei Ansichten (ausdrückliche zusätzliche Produktvorgabe)

**Ansicht 1 – Manuelle Spielleiteransicht**
- Originale Arbeitsansicht, in der der Spielleiter Nodes selbst platziert, ausrichtet und nach eigenen Wünschen organisiert.
- Bewahrt dessen **handgesetzte Positionen**, eigene Arbeitsbereiche, Gruppen und Pfadführung. Keine automatische Anordnung überschreibt diese Arbeit stillschweigend.

**Ansicht 2 – Automatische Szenenansicht**
- Beim Umschalten werden Nodes automatisch räumlich **nach ihrer Szenenzuordnung gruppiert** und möglichst übersichtlich angeordnet.
- **Jede Szene erhält einen klar abgegrenzten rechteckigen Rahmen mit sichtbarem Szenentitel**. Nodes, die zu dieser Szene gehören, werden innerhalb des Rahmens platziert; die Rahmen wachsen bei Bedarf mit.
- Innerhalb jeder Szenengruppe sollen Node-Überlappungen und Leitungskreuzungen **möglichst gering** sein. Beziehungen zwischen Szenen werden mit nachvollziehbaren, typfarbigen Verbindungen über Rahmengrenzen hinweg visualisiert.
- Logik-/Timer-/Kampagnen-Nodes ohne eindeutige Szenenzuordnung erhalten eine passende, als **„Kampagnenweit / ohne Szene“** gekennzeichnete Gruppe statt einer erfundenen Szenenzuordnung. Bei Bezug zu mehreren Szenen ist die eindeutige Gruppierungsregel später zu spezifizieren; kein ungewolltes Duplizieren von Objekt-/Logikzustand.

**Ansicht 3 – Automatische Gesamtansicht**
- Ebenfalls automatische räumliche Anordnung aller im gewählten Umfang sichtbaren Nodes, aber **vollständig unabhängig von Szenengruppierung** und Szenenrahmen.
- Der Anordnungsalgorithmus kann dabei primär die **Verbindungsstruktur** berücksichtigen: nah zusammengehörige Nodes sinnvoll positionieren, Kollisionen zwischen Nodes vermeiden und Leitungsüberkreuzungen sowie unnötig lange Kabel möglichst minimieren.
- Diese Ansicht soll für das Verstehen längerer kampagnenweiter Signalketten geeignet sein, ohne szenenweise Aufteilung zu erzwingen.

### Gemeinsame Grenzen und Anforderungen

- **Eine einzige funktionale Schaltungsdefinition:** Alle drei Ansichten verwenden **dieselben Node-/Objekt-/Port-/Kanten-IDs, die gleiche Ausführungslogik und dieselben zugriffsberechtigten Ist-Signalwerte**. Sie sind **Ansichten**, keine voneinander abweichenden Kopien der Schaltung.
- **Ansichtswechsel darf die manuelle Ansicht nicht verändern:** Die von Hand gesetzten Positionen und Organisation bleiben gespeichert; für die automatischen Ansichten gibt es unabhängige berechnete und ggf. zwischengespeicherte Layoutdaten.
- **„Möglichst ohne Überschneidungen“ als klares Optimierungsziel:** Node-Karten und Gruppenrahmen sollen sich nicht überdecken, Signalwege sollen lesbar bleiben, Leitungskreuzungen soweit praktikabel reduzieren. Bei sehr großen/komplexen Graphen sind absolute Kreuzungsfreiheit oder exakte optimale Graphlayouts nicht garantiert. Stabile, nachvollziehbare Anordnung ist wichtiger als hektisches Hin- und Herspringen.
- **Gleichbleibende Darstellung der Signale:** Farblich typisierte Leitungen, aktive/inaktive Zustände, Impulse und Diagnosefehler aus 02.20/02.21 bleiben in allen Ansichten erkennbar. Die Test-/Simulationsfunktion ändert durch Layoutwechsel keine echten Spielzustände.
- **Skalierung und Navigation:** Zoomen, Verschieben, Suche, Auswahl, „auf Inhalt einpassen“, zu Node/Szene springen und visuelle Übergänge beim automatischen Umordnen sind als UX-Anforderungen vorzusehen. Das Detailverhalten und die Layoutaktualisierung bleiben noch offen.
- **Rechte:** Nur autorisierte Spielleiter dürfen versteckte Szene-/Objektinformationen in der Gesamtschaltung sehen; Spieler erhalten durch eine automatische Szenenübersicht keine neuen Geheimdaten.
- **Server vs. Anzeige:** Automatische Positionierung und Leitungsrouting sind **reine editorseitige Layoutberechnung**; der eigentliche Aktionsgraph und die serverseitige Regelverarbeitung bleiben unverändert.

**02.28 beschlossen:** Automatische Ansichten können beim ersten Aufruf und bei relevanten Änderungen neu layoutet werden; 'Neu anordnen', Pausieren und Fixieren kontrollieren die Aktualisierung. Die manuelle Spielleiteransicht bleibt unangetastet. **Weiter offen:** genaue Regeln für einzelne fixierte Nodes, mehrere Szenenzuordnungen, Leitungsrouting, Layoutanimationen, große Graphen sowie Vorlagenverwaltung.

## 02.28 – Automatische Neuanordnung mit Fixierfunktion (11.10.2026)

**Beschlossen: Variante C – automatische Layoutberechnung mit Kontrolle und Fixiermöglichkeiten.**

- **Erstes Öffnen oder Wechsel in eine automatische Ansicht:** Szenenansicht und freie Gesamtansicht erzeugen ein passendes Layout mit ausreichenden Abständen, möglichst wenigen Überschneidungen und nachvollziehbaren Verbindungen.
- **Relevante Graphänderungen:** Neue bzw. entfernte Nodes, neue Verbindungen und veränderte Gruppierungen dürfen eine automatische, möglichst schonende Aktualisierung der jeweiligen Ansicht auslösen. Es sollen nach Möglichkeit nur betroffene Bereiche verschoben werden, damit der restliche Graph für den Spielleiter räumlich wiedererkennbar bleibt.
- **'Neu anordnen':** In beiden automatischen Ansichten gibt es eine explizite Aktion, um das gesamte sichtbare Netz bzw. den gewählten Bereich neu zu layouten. Dabei gelten weiterhin die Gruppierungsregeln der gewählten Ansicht (Szenenrahmen in Ansicht 2, ohne Szenengruppierung in Ansicht 3).
- **'Positionen fixieren' / Auto-Anordnung pausieren:** Der Spielleiter kann die automatische Neupositionierung während des Bearbeitens vorübergehend anhalten, um zu verhindern, dass Nodes und Verbindungen ständig ihre Position wechseln. Ein klar sichtbarer Status zeigt, ob der Auto-Layout-Modus momentan aktiv oder fixiert ist. Fixierung lässt die Schaltung weiter funktionieren; nur die Darstellung wird festgehalten.
- **Manuelle Ansicht dauerhaft schützen:** Die vom Spielleiter eigenständig gesetzten Positionen, Gruppen und die manuelle Anordnung aus Ansicht 1 werden **niemals** durch Berechnung oder Fixierung der automatischen Ansichten überschrieben. Beim Zurückwechseln ist die ursprüngliche Anordnung unverändert wieder da.
- **Ein Graph, getrennte Layoutzustände:** Die drei Ansichten teilen die gleichen logischen Node-/Port-/Kanten-/Objekt-IDs und Signalzustände, aber haben unabhängige Layoutkoordinaten bzw. Darstellungscaches. Ansicht wechseln, Layout neu berechnen oder fixieren ist **keine Node-Aktion** und darf keine Schalter, Timer, Türen oder Fallenauslöser aktivieren.
- **Wartende Layoutänderungen:** Wenn während der Fixierung neue Nodes hinzukommen oder Verbindungen geändert werden, gehen sie im Graphen nicht verloren. Ihre Darstellung wird auch im fixierten Modus nachvollziehbar ergänzt bzw. eine ausstehende Layoutaktualisierung kenntlich gemacht. Die genaue Strategie, wie neue Nodes zunächst positioniert werden, bleibt offen.
- **Testansicht und Rechte:** Farben, aktive/inaktive Signalzustände und Fehlersymbole funktionieren auch bei fixierter Anordnung. Geheime Objekte und Szeneinformationen dürfen durch Auto-Layout nicht an Spieler weitergegeben werden.
- **Leistungsziel:** Bei großen Graphen unnötige permanente Neuberechnung vermeiden; stabile räumliche Orientierung ist wichtiger als nach jeder kleinen Zustandsänderung ein optimales, aber völlig anderes Layout.

**Mit 02.29 entschieden:** Direkte Kabel über Szenenrahmen oder kompakte beschriftete Rahmen-Übergangspunkte sind in der Szenenansicht umschaltbar; beide spiegeln identische Verbindungen und Signalzustände wider. **Weiter offen:** einzelne fixierte Nodes, genaue Neuberechnungsregeln, Leitungsrouting, Zoom-/Animationsverhalten, Layoutalgorithmus und Grenzfälle bei großen Graphen.

## 02.29 – Verbindungen zwischen Szenenrahmen wahlweise direkt oder kompakt (11.10.2026)

**Beschlossen: Variante C – beide Darstellungsarten sind in der automatischen Szenenansicht umschaltbar.**

### Ansicht „Direkte Leitungen“

- Farbig typisierte Kabel verlaufen **direkt von den Ports der Quell-Node zu den Ports der Ziel-Node**, auch wenn sie Szenenrahmen kreuzen.
- Die Leitung soll sich bis zu beiden Endpunkten nachvollziehen lassen; beim Darüberfahren bzw. Auswählen werden zusammengehörige Kabel und Portbezeichnungen hervorgehoben.
- Der Layoutalgorithmus minimiert soweit sinnvoll verdeckte Ports, Überlagerungen, unlesbare Kreuzungen und unnötig lange Wege; absolute Kreuzungsfreiheit ist bei komplexen Graphen nicht garantiert.

### Ansicht „Übergangspunkte am Szenenrahmen“

- Szenenübergreifende Kabel werden **an eindeutig beschrifteten Ein- und Ausgangspunkten am rechteckigen Szenenrahmen** dargestellt, z. B. `Ausgang → Maschinenraum / Schott A / Öffnen`.
- Die Punkte sind **grafische Weiterleitungen/Anker**, keine zusätzlichen funktionalen Nodes und keine neu angelegten Ereignisregeln. Sie referenzieren dieselbe bestehende Kante zwischen realen Node-/Port-IDs.
- Durch Anklicken/Anwählen eines Übergangspunkts lässt sich **die Gegenstelle finden, hervorheben und anspringen**. Quelle, Ziel, Szenenname und Porttyp bleiben auffindbar.
- Bei vielen Verbindungen dürfen Übergangspunkte zur Entlastung der Darstellung kompakt gruppiert werden, sofern **jede zugrunde liegende Verbindung einzeln identifizierbar** bleibt. Das genaue Bündelungsverhalten wird später gestaltet.

### Gemeinsame technische und UX-Vorgaben

- **Umschalter innerhalb der Szenenansicht:** „Direkte Leitungen“ / „Übergangspunkte“ ohne Verlust von Graphinformationen oder Bewegung der manuell gesetzten Nodes. Es ist eine Präsentationsoption, keine Änderung der Signal- oder Ereignisverarbeitung.
- **Farbkodierung und Iststand (02.20/02.21):** Beide Darstellungen erhalten korrekte Leitungstypfarben, Angaben zu verbunden/nicht aktiv/Signal aktiv, Ereignisimpulsen und Fehlern. Kompakte Übergangspunkte zeigen Signalstatus ebenso nachvollziehbar wie direkte Leitungen.
- **Gleicher kanonischer Graph:** Eine Verbindung besitzt weiterhin genau eine autoritative Quell-/Zielidentität. Keine duplizierten Schaltungen, keine neuen Ports im Servermodell allein wegen eines Rahmenübergangs.
- **Ansichten getrennt (02.27/02.28):** Manuelle Spielleiteransicht und automatische szenenunabhängige Gesamtansicht bleiben von der gewählten szenenbezogenen Kabeldarstellung unberührt; Fixier-/Neu-anordnen-Funktionen wirken nur auf die Layoutdaten.
- **Rechte und Navigation:** Geheime Szenen-/Objektverknüpfungen bleiben für unberechtigte Teilnehmer unsichtbar; nur autorisierte Spielleiter dürfen zu verborgenen Zielen springen.

**Mit 02.30 entschieden:** Mehrfach szenenbezogene Nodes erhalten einen frei wählbaren primären Anzeigeort (eine Szene oder „Kampagnenweit“), mit Referenz-/Übergangspunkten in anderen Szenen statt Node-Kopien. **Weiter offen:** Standardwahl für direkte Leitungen/Übergänge, Leitungskabel-Routing, Bündelung, Statusaktualisierungsrate und Zoom-abhängige Details.

## 02.30 – Primärer Anzeigeort für mehrfach szenenbezogene Nodes (11.10.2026)

**Beschlossen: Variante C – der Spielleiter kann für eine Node, die mehrere Szenen betrifft, die primäre Szene oder „Kampagnenweit“ als ihren Anzeige-Heimatort festlegen.** Andere Szenen erhalten bei Bedarf nur beschriftete Referenz-/Übergangspunkte.

### Verbindliche Darstellung

- **Wählbarer Anzeigeort:** Der Spielleiter kann einem szenenübergreifenden Timer, einer Bedingung oder einer Logik-Node als primären Anzeigeort **eine konkrete Szene oder den Bereich „Kampagnenweit“** geben. Die Position innerhalb dieses Rahmens wird von der automatischen Szenenansicht nach 02.27–02.28 berechnet.
- **Ein echter Node-Zustand:** In der automatischen Szenenansicht erscheint die eigentliche Node genau einmal am primären Anzeigeort. Die weiteren Szenen zeigen bei Bedarf **beschriftete Referenzen/Anschlüsse**, über die man dieselbe Node erreichen, hervorheben und ihren Status nachvollziehen kann. **Keine Duplikate der Ausführung, Signale, Timer oder Objektzustände.**
- **Referenzen bleiben interaktiv:** Ein Klick auf den Referenz-/Übergangspunkt navigiert zur primären Node und zeigt die relevante Verbindung. Der Anzeigeort und die aktuellen Porttypen/-werte bleiben verständlich. Bei der alternativen Darstellung mit direkten Leitungen aus 02.29 darf die Kante dennoch direkt zur eigentlichen Node laufen.
- **Trennung von Ort und Logik:** Der primäre **Anzeigeort ist eine reine Editor-/Layoutzuordnung**. Er ändert **nicht** die echte Szenen- und Stockwerkszuordnung eines bereits platzierten Tür-, Schalter-, NPC- oder anderen Szenenobjekts. Ein Umgruppieren kann niemals physisch eine Tür in eine andere Szene versetzen.
- **„Kampagnenweit“:** Nodes ohne eindeutige Szenenzugehörigkeit oder mit kampagnenübergreifenden Abhängigkeiten innerhalb derselben Kampagne können gesammelt in einem eigenen, eindeutig benannten Rahmen stehen. Querverweise zu betroffenen Szenen bleiben sichtbar; Szenen-IDs werden nicht erfunden.
- **Persistenz und Bearbeitung:** Die Anzeige-Heimat lässt sich später ändern und wird als eigene Präferenz/Eigenschaft der Graphdarstellung gespeichert. Bei Änderung bleiben stabile Node-/Port-/Kanten-IDs, Ausführungsregeln, Signalzustände und die vom Spielleiter angelegte **manuelle Ansicht** unverändert.
- **Umbenennen, Löschen und Sicherheit:** Namen von Szenen werden in den Referenzen aktualisiert; bei entfernten Szene-/Objektreferenzen ist ein verständlicher Hinweis erforderlich, statt still auf andere Ziele umzubiegen. Versteckte Szenen- und Node-Details bleiben ausschließlich für berechtigte Spielleiter sichtbar.

**Technische Abgrenzung:** Die Zuordnung `scene_auto_display_home = scene_id | campaign_wide` ist ein **Präsentationsattribut**, getrennt von `physical_scene_id` eines Szenenobjekts sowie getrennt von der logischen Node-/Event-Definition. Querverweise sind reine UI-Projektionen derselben Graphkante, keine neuen serverseitigen Ports oder zusätzlichen Auslöser. Die exakten Feldnamen sind nicht verbindlich.

**Noch offen:** Automatische Vorgabe für neue Mehr-Szenen-Nodes, besondere Fälle von dynamischer Szenenzuordnung, Mehrfachbezüge an Stockwerke, Darstellung der Referenzen bei hohem Verbindungsaufkommen und endgültige Layout-/Navigationsdetails.

## 02.31 – Vollständiger Node-Test- und Debugmodus (11.10.2026)

**Beschlossen: Variante C – Live-Iststand, Ereignisprotokoll und umfassende isolierte Schritt-für-Schritt-Simulation mit Breakpoints.**

### 1. Live-Iststand – nur beobachten

- **Direkt an Port und Verbindung:** Anzeige, ob ein Kabel angeschlossen ist, ob ein boolescher Dauerwert `true` oder `false` ist, welcher Zahlen-/Textwert aktuell vorliegt, ob zuletzt ein Ereignisimpuls einging und ob Fehler/ungültige Referenzen bestehen. **Verbindung vorhanden ≠ Signal liegt an.**
- **Farblich codierte Signalpfade:** Die Leitungstypfarben aus 02.20 gelten unverändert. Zusätzliche Hervorhebung und Beschriftung zeigen die aktuell aktiven bzw. zuletzt durchlaufenen Pfade; allein die Farbe darf nicht die Bedeutung tragen.
- **Szenen und Arbeitsbereiche:** Live-Status und Fehlerhinweise müssen über szenenübergreifende Verbindungen (02.18/02.29), Untergraphen und die drei Ansichten (02.27) nachvollziehbar bleiben.
- **Read-only-Diagnose:** Das Ansehen von Live-Signalen, Verlauf und aktuellen Werten darf **keine** Aktionen auslösen, **keine** echten Timer anhalten und **keine** Spielobjekte verändern.

### 2. Ereignisverlauf und Ursachenanalyse

- Ein verständliches Spielleiter-Protokoll dokumentiert je beobachtetem Ausführungsschritt die auslösende Node und den Port, den betroffenen Graph-/Szenen-/Objektbezug, Zeitpunkt bzw. Spielrunde, weitergeleitete Werte, ausgewertete Bedingungen, Folgereaktionen und Fehler.
- Bei fehlgeschlagenen oder gestoppten Ketten soll der Editor den **Grund** zeigen: Bedingung falsch, Eingang nicht verbunden, falscher Porttyp, fehlende Rechte, nicht aktive Szene gemäß 02.19, gelöschte Objekt-Referenz oder durch Schleifenschutz unterbrochen.
- Einzelne Ereignisse bzw. Graphketten können im Editor wiedergefunden, gefiltert und hervorgehoben werden. **Live-Blick** und **historisches Protokoll** klar getrennt beschriften.
- Die Aufbewahrung, datenschutzkonforme Berechtigungen und Größe des Protokolls werden später detailliert geplant; verborgene Spielleiterinformationen niemals an nicht berechtigte Spieler liefern.

### 3. Isolierte Simulation mit Haltepunkten

- Der Spielleiter kann eine **Testausführung unabhängig vom laufenden Spiel** starten. Die Simulation verwendet eine gesonderte Zustandskopie bzw. isolierte Testwelt und darf reale Türen, Figuren, Inventare, Fallen, Timer, Entdeckungszustände oder Spielrunden **nicht** verändern.
- **Schrittweise verfolgen:** Die Simulation kann nach jedem Schritt angehalten und vorwärts bewegt werden. Ein aktiver Signalpfad, Eingangs-/Ausgangswerte, erfüllte/nicht erfüllte Bedingungen und geplanter Folgeeffekt werden verständlich angezeigt.
- **Breakpoints (Haltepunkte):** An einer Node oder einem Verbindungsschritt kann ein Haltepunkt gesetzt werden. Während der **Simulation** stoppt die Verarbeitung dort, sodass Werte kontrolliert werden können, bevor der nächste Schritt ausgelöst wird.
- **Fehler sichtbar machen:** Port-/Typkonflikte, fehlende Objektbindung, unerlaubte Aktion, nicht ausgelöste oder nicht erfüllte Bedingung, unbeabsichtigte Zyklen, wiederholte Ereignisse und zurückgestellte Aktionen müssen diagnostizierbar sein.
- **Echtzeit- und Rundenlogik** bleiben zwei getrennte Zeitgrundlagen (02.15–02.16). Exakte Bedienung von virtueller Zeit und virtuellen Spielrunden wird später entschieden.
- **Dieselbe fachliche Logik:** Simulation und tatsächliche Serverausführung sollen dieselben validierten Regeldefinitionen und fachlichen Prüfungen verwenden, statt durch eine oberflächliche Browseranimation voneinander abweichende Ergebnisse zu liefern. Simulationseffekte werden nicht in die reale Kampagne zurückgeschrieben.

### UX, Rechte und Qualität

- „**Live beobachten**“ und „**Simulation starten**“ sind deutlich unterschiedliche Bedienmodi. Es darf nicht unklar sein, ob der tatsächliche oder ein simulierter Iststand angezeigt wird.
- Fehler und Ursachen auch für Anfänger in **lesbaren Sätzen**, für fortgeschrittene Spielleiter zusätzlich technisch exakt und portbezogen darstellen.
- Szenen- und Kampagnen-Geheimnisse, Codewerte und Berechtigungen aus den vorigen Entscheidungen auch im Debugger schützen.
- Log- und Statusdaten nicht ungebremst sammeln; große Graphen müssen performant bleiben. Die Grenzen, Filter und Exportformate sind später zu planen.

**02.32 beschlossen:** Speicherung wiederholbarer Testfälle mit Ausgangszuständen, definierten Aktionen, Echtzeit-/Rundenschritten und Soll-Ist-Prüfungen. **Weiter offen:** Zeitpunkt automatischer Regressionstests (02.33), virtuelle Zeitführung im Detail, Protokollaufbewahrung, Breakpoint-Details, parallele Signalpfade, Export und große Graphen.

## 02.32 – Wiederholbare Node-Tests mit gespeicherten Soll-Ergebnissen (11.10.2026)

**Beschlossen: Variante C – komplette, speicherbare und wiederholbare Testszenarien mit Ausgangszuständen, Eingabefolgen, kontrolliertem Zeitverlauf und automatischem Soll-Ist-Vergleich.**

### Aufbau eines Testszenarios

- **Name und Geltungsbereich:** Der Spielleiter benennt einen Test und ordnet ihn einer Node-Schaltung, einer Gruppe/Untergraph-Vorlage, einem Arbeitsbereich oder einer übergreifenden Ereigniskette zu. Testeinstellungen und Testfälle sind persistent und versionierbar.
- **Isolierter Startzustand:** Ein Test enthält oder referenziert explizite Startwerte für relevante Türen, Schalter/Taster, Inventare, Figurenpositionen, Objektzustände, Berechtigungen, Signale und Timer. Keine unbeabsichtigte Abhängigkeit vom gerade live laufenden Spielzustand.
- **Eingabeschritte:** Der Spielleiter kann Aktionen wie Taster drücken/halten/loslassen, Schalter umlegen, Figur bewegen, Codeeingabe simulieren, Objektzustand ändern, NPC-/Questereignis auslösen oder die Aktivierung einer Szene simulieren. Nur kompatible, validierte Testaktionen zulassen.
- **Zeitsteuerung:** Echtzeit- und Rundenfortschritte sind **getrennte, kontrollierbare Eingaben**: zum Beispiel '5 simulierte Sekunden weiter' oder '2 simulierte Spielrunden weiter'. Beide Zeitbasen werden nicht stillschweigend ineinander umgerechnet.
- **Soll-Ergebnisse:** Pro Schritt oder Testende können erwartete Ausgänge, anliegende Portwerte, tatsächlich gesendete Ereignisimpulse, Objektzustände (z. B. Tür offen), Bedingungen, verbotene Aktionen und fehlende Auslösungen festgelegt werden. Auch 'darf nicht passieren' ist ein gültiger Testfall.
- **Vergleich:** Der Debugger zeigt je Prüfung **erfüllt/fehlgeschlagen**, tatsächlichen und erwarteten Wert sowie den zugehörigen Node-/Portpfad. Bei Abweichungen direkt zur betroffenen Node, Bedingung und zum relevanten Trace-Schritt springen.
- **Manuelle Tests bleiben möglich:** Zusätzlich zu gespeicherten Szenarien darf ein Spielleiter weiterhin einzelne Testsignale von Hand setzen und eine Kette Schritt für Schritt untersuchen (02.31).

### Konkretes Mehrspieler-Beispiel

**Test 'Taster hält Sicherheitstür frei':** (1) Taster ist anfangs AUS und Tür geschlossen; (2) Spieler A hält Taster -> Erwartung: Ausgang EIN und Tür freigegeben; (3) Spieler B passiert den Durchgang -> Erwartung: Bewegung erlaubt; (4) Spieler A lässt los -> Erwartung: Ausgang AUS; (5) der Test vergleicht anschließend die Türreaktion mit ihrer individuell eingestellten Regel aus 02.22/02.23. Sämtliche Figuren, Türen und Zeiten sind dabei nur simuliert.

### Wiederholung und Sicherheit

- Testszenarien können gespeichert, kopiert, erneut gestartet und **nach Änderungen an Schaltungen** erneut ausgeführt werden. Der Spielleiter sieht die Ergebnisse je Durchlauf sowie nach Möglichkeit, was sich seit dem letzten Test verändert hat.
- Der Test benutzt **dieselbe validierte fachliche Node-Auswertungslogik** wie das echte Spiel, jedoch einen **vollständig isolierten Testkontext**. Weder echte Kampagnenobjekte noch Inventare, Echtzeit-Timer, Spielrunden, Fog-of-War, Chatnachrichten oder externe Aktionen dürfen verändert werden.
- Referenzen in Tests sollen stabile Objekt-/Node-/Port-IDs verwenden und beim Kopieren von Vorlagen ausdrücklich auf Testobjekte gemappt werden. Fehlende oder umbenannte Referenzen werden verständlich angezeigt und nicht heimlich auf gleichnamige andere Objekte gebunden.
- Zufallseffekte und simultane Spieleraktionen müssen reproduzierbar testbar werden; konkrete Seed-/Ablaufsteuerung wird später festgelegt. Nichtdeterministische Ergebnisse dürfen keine irreführenden Erfolgsmeldungen erzeugen.
- Geheimnisse, private Spielleiterdaten und Testprotokolle dürfen nur berechtigten Personen zugänglich sein; Grenzen für Testdauer, Schleifen und Datenvolumen einplanen.

**02.33 beschlossen:** Testläufe pro Schaltung manuell, automatisch nach relevanten Änderungen und/oder vor Aktivierung konfigurierbar. **Weiter offen:** Sperr- oder Warnverhalten (02.34), Versionierung von Teständerungen, Zufall/gleichzeitige Ereignisse, Testfixtures, Export, Sammelberichte und Reihenfolge.

## 02.33 – Ausführungszeitpunkte gespeicherter Node-Tests (11.10.2026)

**Beschlossen: Variante C – der Spielleiter wählt pro Node-Schaltung, wann ihre gespeicherten Tests ausgeführt werden.** Die Methoden dürfen je Schaltung kombinierbar sein; es gibt keinen Zwang, jede Schaltung automatisch bei jedem Bearbeitungsschritt durchzutesten.

### Drei Testauslöser

- **Manuell:** Spielleiter können einzelne Tests oder die gesamten zugeordneten Testszenarien jederzeit gezielt starten.
- **Automatisch nach relevanten Änderungen:** Beim Speichern oder Übernehmen einer echten Änderung an der Node-Logik, Portverbindung, Parametrisierung, Objektbindung oder passenden Vorlage werden betroffene gespeicherte Tests in einem isolierten Kontext erneut geprüft. Reine Layoutaktionen (Node verschieben, Ansicht wechseln, Szenenrahmen automatisch anordnen) sollen **keinen Logiktest auslösen**. Bei schneller Änderungsfolge Tests sinnvoll bündeln, nicht nach jedem Tastendruck starten.
- **Vor Aktivierung/Freigabe:** Der Spielleiter kann für eine Schaltung eine zusätzliche Testprüfung vor dem Wirksamschalten bzw. Freigeben vorsehen. Ergebnisse sind klar sichtbar und der geprüften Version der Schaltung zugeordnet. **02.34 beschlossen:** Das Verhalten bei fehlgeschlagenen, fehlenden oder veralteten Tests hängt von der gewählten Kampagnen-/Schaltungsrichtlinie ab.

### Bedienung, Nachvollziehbarkeit und Sicherheit

- **Einstellung pro Schaltung:** Auswahl im Eigenschaften-/Testbereich des betreffenden Graphen; passende globale Standardvorgaben bei Kampagnenerstellung sind als spätere mögliche Ergänzung vorzusehen (vgl. 02.24–02.25), ohne die individuelle Steuerung abzuschaffen.
- **Ergebnisstatus:** Für die geprüfte Graph-/Vorlagenversion lesbar anzeigen: bestanden, fehlgeschlagen, noch nie ausgeführt, nach relevanter Änderung veraltet, Test läuft oder Test technisch nicht ausführbar. Eine alte erfolgreiche Prüfung darf nicht irreführend als aktuelle Freigabe angezeigt werden.
- **Betroffene Tests erkennen:** Testzuordnungen und Abhängigkeiten (Schaltung, Untergraph, Vorlage, referenziertes Objekt) nutzen; Tests anderer unabhängiger Pläne nicht unnötig starten. Bei Querverbindungen zwischen Arbeitsbereichen/Szenen die relevanten Abhängigkeiten verfolgen.
- **Ausführung ohne Nebenwirkungen:** Auch automatische und Vor-Freigabe-Prüfungen erfolgen ausschließlich in der **isolierten Simulation aus 02.31/02.32**, nie in der echten Kampagne. Keine unkontrollierten Live-Aktionen, beschädigten Inventare, ausgelösten Fallen, veränderten Timern oder blockierten Echtzeit-Spielabläufe.
- **Grenzen und Fehlersuche:** Ressourcenlimits, Abbruch, Testprotokolle, Soll-Ist-Differenzen, Zuordnung zur konkreten Graphversion sowie klare Hinweise bei fehlenden/ungültigen Testfixtures. Berechtigungsprüfung und Geheimdatenschutz bleiben bestehen.
- **Aktivierungsprüfung ist keine automatische Sicherheitsfreigabe:** Die tatsächliche Ausführung von Nodes bleibt bei allen Testmodi serverseitig validiert. **02.34 beschlossen:** Per Kampagne mit optionaler Schaltungsausnahme Warnung oder verpflichtend erfolgreicher Test; ausdrücklich erlaubte und protokollierte Übersteuerung nur für berechtigte Spielleiter. Technisch ungültige/unerlaubte Graphen bleiben unabhängig davon gesperrt.

**02.34 beschlossen:** Kampagnenstandard und optionale Schaltungsausnahmen für Warnung, Aktivierungssperre sowie separat erlaubte, protokollierte Spielleiter-Übersteuerung. **Weiter offen:** konkreter Standardwert im Kampagnenerstellungs-Assistenten, Änderungserkennung/Testbündelung, maximale Laufzeit, laufende Tests während weiterer Bearbeitung und parallele Signalkonflikte (02.35).

## 02.34 – Fehlgeschlagene Tests und Freigaberichtlinie (11.10.2026)

**Beschlossen: Variante C – bei Kampagnenerstellung global einstellbar, pro Schaltung bei Bedarf individuell überschreibbar.** Bei nicht bestandenen, fehlenden oder veralteten Testergebnissen gilt die gewählte Freigaberichtlinie.

### Richtlinie und Vererbung

- **Kampagnenstandard:** Im Bereich Kampagneneinstellungen / Spielregeln / Node-Testfreigabe (Arbeitstitel) legt ein berechtigter Spielleiter den Standard für die Kampagne fest. Eine neu angelegte Node-Schaltung übernimmt die passende Richtlinie zunächst aus dem Kampagnenprofil.
- **Abweichung pro Schaltung:** Der Spielleiter kann für eine bestimmte Schaltung oder einen wiederverwendbaren Baustein eine ausdrücklich gekennzeichnete Ausnahme konfigurieren. Eine globale Änderung darf individuelle Ausnahmen nicht stillschweigend ersetzen (02.24–02.25).
- **Warnmodus:** Tests mit fehlgeschlagenem, noch fehlendem oder veraltetem Ergebnis sind klar sichtbar, verhindern aber allein durch ihren Status nicht die Aktivierung. Eine erfolgreiche Testprüfung darf nicht vorgetäuscht werden.
- **Strenger Modus:** Für die entsprechend verpflichtenden Tests ist ein **aktuelles, erfolgreiches Ergebnis zur exakt freizugebenden Schaltungsversion** erforderlich; ansonsten wird deren Aktivierung/Freigabe abgewiesen.
- **Optionale Übersteuerung:** Der Kampagnen-/Schaltungsstandard kann ausdrücklich festlegen, ob ein **berechtigter Spielleiter** die testbedingte Sperre im Einzelfall nach Warnung bewusst übersteuern darf. Der Vorgang ist mit Identität, Zeitpunkt, Grund, Graphversion, Testergebnissen und Entscheidung nachvollziehbar zu protokollieren.

### Freigabe und technische Grenzen

- **Testzustände differenzieren:** Bestanden, fehlgeschlagen, nie ausgeführt, aufgrund von Änderungen veraltet, noch laufend oder technisch nicht ausführbar sind unterschiedliche Zustände. Der Regelmodus bestimmt, ob diese für eine Freigabe toleriert werden. Niemals einen veralteten Erfolg als neuen Erfolg anzeigen.
- **Sperre betrifft testbedingte Freigabe:** Eine ausdrücklich erlaubte Übersteuerung darf **keine fehlenden Berechtigungen, inkompatiblen Ports, kaputten Objektreferenzen, invaliden Regeldefinitionen oder sonstige unverzichtbare Sicherheitsprüfungen** umgehen.
- **Autoritativ und versionsbezogen:** Die Freigabeentscheidung muss serverseitig auf die tatsächlich aktuelle Graphversion, das gültige Regelprofil und die dazu gehörigen Testergebnisse bezogen werden. Parallel vorgenommene Änderungen dürfen nicht unbemerkt zwischen Test und Freigabe eingeschoben werden.
- **Simulation bleibt isoliert:** Die Prüfung vor Freigabe nutzt den Sandbox-Testmodus aus 02.31–02.33; kein echter Tür- oder Fallenimpuls wird beim Testen ausgelöst.
- **Bedienung:** Sichtbare Statusanzeige am Graphen (z. B. Warnung, freigabebereit, testbedingt gesperrt, übersteuert) mit nachvollziehbarer Erklärung und direktem Sprung zu fehlgeschlagenen Assertions und betroffenen Nodes. Details zu Berechtigungsebenen und Änderungs-/Audit-Aufbewahrung werden später festgelegt.

**Noch offen:** Die konkrete vorbelegte Warn-/Streng-Richtlinie bei neu erzeugten Kampagnen, wählbare Kategorien von Pflicht- und optionalen Tests, Ablauf einer Übersteuerung, mögliche Ablaufzeit einer Ausnahme und Veröffentlichung in Mehrspielergruppen. Konflikte gleichzeitiger Node-Aktionen sind ab 02.35 durch kampagnenweit vorgegebene und objektbezogen überschreibbare Regeln zu behandeln; genaue Konfliktalgorithmen bleiben eine spätere Detailplanung. Unverzichtbare Sicherheitsprüfungen gelten weiterhin.

## 02.35 – Konfliktregeln für gleichzeitig eintreffende Node-Aktionen (12.10.2026)

**Beschlossen: Variante C – Konflikte werden regelwerksneutral, serverautoritativ und konfigurierbar aufgelöst.** Der Spielleiter kann bei der **Kampagnenerstellung** globale Standards festlegen; **pro Objekt bzw. geeigneter Aktion** sind bewusst gekennzeichnete Ausnahmen möglich (Vererbungsregeln 02.24–02.25).

### Konfigurierbare Strategien

- **Eingangsreihenfolge:** Für dasselbe Ziel eintreffende, konkurrierende Befehle werden in einer eindeutig nachvollziehbaren serverseitigen Reihenfolge verarbeitet. Reihenfolge nicht allein an unzuverlässiger Browserzeit festmachen.
- **Prioritäten:** Unterschiedliche Node-Auslöser, Eingänge oder Aktionsarten können definierte Vorränge besitzen, z. B. Sicherheitssperre vor gewöhnlichem Öffnungsbefehl. **Gleichstand und spätere Wiederaufnahme** sind später genau zu spezifizieren.
- **Gegenseitige Sperre / Serialisierung:** Ein Objekt kann während einer kritischen Zustandsänderung widersprüchliche neue Aktionen vorübergehend ablehnen, zurückstellen oder gemäß später festzulegenden Regeln ausführen; keine unabsichtliche gleichzeitige Ausführung.
- **Definierte Zusammenführung:** Kompatible anliegende Signale oder Werte dürfen nach einer ausdrücklich ausgewählten Regel (z. B. boolesche UND-/ODER-Verknüpfung über geeignete Bedingungs-Nodes) zusammengeführt werden. **Event-Impulse, Boolesche Werte und Aktionsbefehle nicht stillschweigend gleichsetzen oder ohne Typprüfung vermischen.**

### Beispiel

Ein Spieler hält einen Taster, der die Tür freigeben soll. Gleichzeitig befiehlt ein Echtzeittimer der Tür, sich zu schließen. Das aktive Konfliktprofil dieser Tür entscheidet nachvollziehbar, ob Vorrang, Eingangsreihenfolge, gegenseitige Sperre oder ein definiertes Signalzusammenspiel gilt. Der tatsächliche Türzustand und die gefeuerten Ereignisausgänge ergeben sich **nur aus der erfolgreich verarbeiteten Aktion**, nicht bereits aus einem eingehenden Befehl.

### Anforderungen

- **Kampagnenstandard und Ausnahme:** Im Kampagnenassistenten ist ein Standardprofil für Konflikte vorzusehen; neue Objekte übernehmen es zunächst. Der Spielleiter kann bei einer Tür, einem Schalter, einer Falle, einem Fahrzeug oder einem anderen unterstützten Objekt gezielt einen abweichenden Modus einstellen. Änderungen der globalen Vorgabe bieten die Vorschau und Auswahl für Bestandsobjekte aus 02.25.
- **Atomare Ausführung:** Ein einziges serverautoritatives Verfahren entscheidet bei konkurrierenden Ereignissen über konsistente Objektzustände. Doppelte Netzwerkereignisse nicht mehrfach anwenden; gleichzeitige Ausführung, Rekursion und unerlaubte Aktionskombinationen absichern.
- **Gleichzeitigkeit definieren:** Bei praktisch gleichzeitigen Aktionen sind verlässliche Ereignis-IDs, Serverreihenfolge und ggf. Kampagnen-Rundenschritte zu berücksichtigen. Exakte zeitliche Konfliktfenster, Gleichstandsregeln und Warteschlangenverhalten folgen später.
- **Zusammenspiel mit 02.17/02.20/02.21:** Bedingungs-Nodes können UND/ODER/NICHT, ein Taster liefert ein anliegendes boolesches Haltesignal, und ein Schalter kann rasten. Die Konfliktpolitik **ergänzt** diese Logik, statt automatisch andere Signaltypen zu konvertieren.
- **Debugger und Tests:** Der Spielleiter sieht im Live-/Testprotokoll (02.31–02.33), welche Ereignisse konkurrierten, welche Regel griff, welche Aktion umgesetzt, unterdrückt oder verschoben wurde und warum. Gleichzeitige Testereignisse müssen in isolierten Soll-Ist-Szenarien nachvollziehbar überprüfbar sein.
- **Rechte und Sicherheitsgrenzen:** Priorität darf Zugriffs-/Sicherheitsrechte, Verriegelungsregeln, ungültige Ports und zwingende Servervalidierung nicht umgehen. Einstellungen und geheime Ausführungsdetails sind nur berechtigten Spielleitern sichtbar.

**Noch offen:** Exakte Prioritätsstufen und Tie-Breaker, Zeitfenster, Queue/Timeout, Konflikte von Impulsen gegen Dauerzustände, Zusammenführung mehrerer Halter, Konflikte von Eingaben aus mehreren Szenen und Behandlung laufender Animationen. **02.36 beschlossen:** Gleichzeitige Halter desselben Tasters werden anhand eines Kampagnenstandards mit gezielten Ausnahmen pro Taster ausgewertet; Details zum Verbindungsabbruch folgen 02.37.

## 02.36 – Gemeinsames Halten von Tastern: Kampagnenstandard und Ausnahmen (12.10.2026)

**Beschlossen: Variante C mit ausdrücklicher Erweiterung – die Regel für gleichzeitig haltende Figuren wird bereits bei der Kampagnenerstellung als globaler Standard festgelegt; jeder Taster darf eine eigene, klar erkennbare Ausnahme verwenden.**

### Konfigurierbare Mehrspieler-Modi

- **Exklusiv ein Halter:** Höchstens eine berechtigte Figur hält einen konkreten Taster gleichzeitig. Eine zweite Halteaktion wird nicht zusätzlich gezählt; die Reaktion auf einen solchen Versuch ist verständlich.
- **Mehrere Halter, mindestens einer genügt:** Mehrere berechtigte Figuren dürfen gleichzeitig halten. Das boolesche Haltesignal ist EIN, solange **mindestens eine gültige, noch laufende Halteaktion** existiert; erst wenn die letzte endet, wird AUS.
- **Einstellbare Mindestzahl N:** Ein Taster benötigt mindestens **N verschiedene berechtigte, gleichzeitig haltende Figuren** (N >= 1). Sein boolescher Ausgang ist EIN nur bei aktiver Halterzahl >= N; fällt die Zahl darunter, wird der Ausgang wieder AUS. Dies erlaubt Rätsel, bei denen z. B. zwei oder drei Figuren gemeinsam einen Mechanismus bedienen müssen.

### Globaler Standard bei der Kampagnenerstellung

- Im Kampagnenassistenten unter **Spielregeln → Umgebung / Interaktionen → Taster-Mehrspielerregel** (Arbeitstitel) setzt der Spielleiter eine Vorgabe für neu angelegte Taster; diese Regel ist **kein festes D&D-Regelwerk**.
- Bei einer einzelnen Tasterinstanz kann der Spielleiter von der Vorgabe abweichen, z. B. global „mindestens einer“ und für einen schweren Torhebel „mindestens zwei“. Die Eigenschaften zeigen eindeutig **„Kampagnenstandard“ oder „individuelle Ausnahme“** samt effektivem Modus und gegebenenfalls N.
- Änderungen globaler Vorgaben erfolgen gemäß 02.25 mit **Vorschau und Wahl**, ob nur neue oder auch bereits vorhandene, nicht individuell überschreibende Taster betroffen sind. Explizite Ausnahmen werden nicht stillschweigend verändert.
- Die Halterzahl-Regel gilt ausschließlich für den **gehaltenen Tastermodus** aus 02.22; ein rastender **Schalter** funktioniert weiterhin ohne Halten. Beide Objekt-Modi und ihre typisierten Ausgänge bleiben erhalten.

### Signalzustand, Beispiele und Serverausführung

- **Beispiel 1 – mindestens einer:** Zwei Figuren halten denselben Taster; lässt eine los, bleibt das Signal EIN, solange die andere gültig weiterhält.
- **Beispiel 2 – mindestens zwei:** Spieler A hält zunächst allein: 1/2, Ausgang AUS. Spieler B beginnt ebenfalls zu halten: 2/2, Ausgang EIN und Tür wird gemäß verknüpfter Regel freigegeben. Einer lässt los: 1/2, Ausgang AUS. Ob die Tür dann unmittelbar oder verzögert reagiert, bestimmt weiterhin das Zielobjekt nach 02.22.
- **Unterschiedliche Halter zählen:** Der Server zählt unterschiedliche, berechtigte Figuren/Halteaktionen ohne doppeltes Zählen durch dieselbe Figur, wiederholte Netzwerknachrichten oder parallele Eingabegeräte. Die genaue Regel zu Mehrfachfiguren pro Nutzer und Interaktionsreichweite bleibt gesondert zu spezifizieren.
- **Typisierte Outputs:** Der boolesche Ausgang `IstAktiv` ergibt sich aus der aktiven Halterzahl und der gewählten Schwelle; ergänzende Statuswerte/Events wie `AktiveHalterzahl`, `SchwelleErreicht` oder `SchwelleUnterschritten` sind sinnvolle Vorlagen für den späteren Portkatalog.
- **Live-Anzeige und isolierte Tests:** Der Spielleiter kann aktive Halterzahl, geforderte Mindestzahl, Haltezustand und Signalabfall beobachten. Gespeicherte Testszenarien können mehrere Spieler gleichzeitig halten und loslassen lassen, ohne die reale Kampagne zu beeinflussen.
- **Sicherheit:** Jede Halteaktion erhält eine serverseitig geprüfte Figuren-/Interaktionszuordnung; Rollen, Zugriff, Doppelanfragen und gleichzeitige Änderungen werden zuverlässig verarbeitet. Eine ungültig gewordene Halteaktion darf ein Signal nicht dauerhaft auf EIN halten. **02.37 beschlossen:** Abbruch bei Verbindungsverlust erfolgt anhand des globalen bzw. am Taster überschriebenen Sofort-/Nachfrist-Profils. Nach Fristende zählt ein abgemeldeter Halter nicht mehr.

**Mit 02.37 entschieden:** Die Kampagne hat einen Standard für Verbindungsabbrüche: Halteaktion sofort beenden oder begrenzte Echtzeit-Nachfrist erlauben, mit Objektausnahmen und serverseitiger Neubewertung der Halterzahl. **Weiter offen:** Unterbrechung beim Bewegen/Verlassen der Reichweite (02.38), mehrere Figuren pro Nutzer, Sichtbarkeit der Halter, technische Erkennung verlorener Verbindungen und Schutz vor unerreichbar hohen Mindestzahlen. Die Ziel-Türreaktion bleibt unabhängig.

## 02.37 – Verbindungsverlust beim Halten eines Tasters (12.10.2026)

**Beschlossen: Variante C – der Spielleiter kann bereits bei der Kampagnenerstellung festlegen, wie eine laufende Taster-Halteaktion bei Verbindungsabbruch behandelt wird. Einzelne Taster dürfen vom Standard abweichen.**

### Global wählbare Verbindungsabbruch-Regel

- **Sofort beenden:** Sobald der Server den Verbindungsverlust einer haltenden Figur erkannt hat, wird deren Halteaktion beendet. Ihre Figur zählt nicht mehr zur Halterzahl; `IstAktiv` wird nach den Halteschwellen aus 02.36 neu berechnet.
- **Begrenzte Wiederverbindungsfrist:** Statt sofort zu lösen, darf eine Figur für eine **vorher konfigurierte, endliche Echtzeitdauer** als vorübergehend gehalten gelten. Nach Ablauf endet diese Halteaktion serverseitig sicher und die Mindesthalterzahl wird erneut bewertet. Eine unendliche Frist ist **nicht** vorgesehen.
- **Wiederverbinden:** Verbindet sich derselbe berechtigte Spieler rechtzeitig erneut, wird die bestehende Halteaktion nach Prüfung der Figur-/Sitzungszuordnung und aktuellen Objektbedingungen fortgeführt, **ohne doppelt zu zählen**. Ein anderer Spieler darf die Halteaktion nicht durch bloßes Nachahmen einer Clientnachricht übernehmen.
- **Kampagnenstandards und Tasterausnahmen:** Der globale Modus und die gegebenenfalls erlaubte Frist gelten für neu angelegte Taster; an jedem konkreten Taster kann der Spielleiter den Modus und die Frist ausdrücklich ändern. Die UI zeigt die Herkunft der wirksamen Einstellung. Spätere Änderungen am Kampagnenstandard folgen der Vorschau-/Bestandsschutzregel 02.25.

### Mehrspieler-Schaltung und Node-Zustand

- **Mehrere Halter:** Für N=2 zählen während einer erlaubten Nachfrist die gültigen bzw. befristet aufrechterhaltenen Halteaktionen nach der Regel der jeweiligen Tasterinstanz. Scheidet ein Halter endgültig aus und sinkt die Halterzahl unter N, fällt das anliegende boolesche Signal auf AUS. Weitere, noch verbundene Spieler halten weiterhin unabhängig.
- **Klare Statusanzeige:** Live-Debugger, Objekt-Eigenschaften und isolierte Tests können `Verbunden/Hält`, `Verbindung unterbrochen – Frist läuft` und `Halteaktion beendet` unterscheiden; aktiver Halterstand, erforderliches N und gegebenenfalls Restfrist sind nachvollziehbar. Nicht als echte Spielerpräsenz ausgeben, wenn nur eine Nachfrist läuft.
- **Türreaktion bleibt getrennt:** Sobald der Tasterausgang auf AUS wechselt, entscheidet wie bisher die **Konfiguration der Ziel-Tür** aus 02.22 (sofort zurückstellen, offen bleiben, verzögert) über die Wirkung. Der Verbindungsabbruch erhält keine eigene versteckte Tür-Sonderregel.
- **Isolierte Tests:** Einen Disconnect, eine Wiederverbindung innerhalb/außerhalb der Frist, den Ablauf einer Nachfrist und den Wechsel des Schwellenwerts (z. B. 2/2 -> 1/2) als speicherbare Tests aus 02.32 unterstützen.

### Serverseitige Absicherung und offene Implementierungsdetails

- Server ist allein für den echten Zeitpunkt der **erkannten** Unterbrechung, den Zeitablauf der Nachfrist, deren Aufhebung und den Signalwechsel verantwortlich. Die Frist folgt **Echtzeit**, nicht automatisch Spielrunden, und wird unabhängig von Client-Timern ermittelt.
- Abbruch-/Wiederaufnahmeereignisse benötigen eindeutige IDs, damit wiederholte Netzwerkpakete und neue Browser-Verbindungen weder zusätzliche Halter noch ein dauerhaftes EIN erzeugen.
- **Sicherheit:** Bei widerrufener Berechtigung, zerstörtem Taster, ungültigem Haltezustand oder anderer zwingender Spielregel darf eine Frist keine ungültige Aktion künstlich fortsetzen. Diese Prüfungen stehen über einer Verbindungsabbruch-Komfortregel.
- Die exakte Verbindungsverlust-Erkennung (Heartbeat/Timeout), die konkrete maximale Nachfrist, die Persistenz eines offenen Grace-Timers bei Serverneustart und das Verhalten bei pausierter Kampagne bleiben zur technischen Detailplanung offen.

## 02.38 – Bewegung und andere Aktionen beim Halten eines Tasters (12.10.2026)

**Beschlossen: Variante C – bei der Kampagnenerstellung zentral konfigurierbar, mit individuellen Ausnahmen an einzelnen Tastern.**

- **Bewegung:** Der Spielleiter legt fest, ob die haltende Figur während einer gültigen Halteaktion stillstehen muss oder sich bewegen darf. Wenn das Bewegen das Halten aufhebt, wird die Halteaktion serverseitig beendet; ob unzulässige Bewegungen alternativ abgewiesen werden, wird später separat entschieden.
- **Interaktionsdistanz:** Ein ortsfester Taster kann eine begrenzte Reichweite erfordern, während ein tragbarer oder fernbedienbarer Taster eigene Reichweitenregeln haben kann. Die genauen Distanzregeln folgen in 02.39.
- **Zusätzliche Handlungen:** Der Kampagnenstandard und mögliche Tasterausnahmen legen fest, welche weiteren Figurenaktionen parallel erlaubt sind oder das Halten unterbrechen, beispielsweise Sprechen, Inventarbenutzung, Angreifen oder Gegenstände verwenden. Das aktive Regelprofil bestimmt verfügbare Aktionen.
- **Figurenzustände:** Regeln können eine Halteaktion bei passenden Zustandswechseln wie Handlungsunfähigkeit oder Bewusstlosigkeit beenden. Es gibt keine fest eingebaute D&D-spezifische Statusliste; die Zustände stammen gegebenenfalls aus dem Regelprofil.
- **Globale Voreinstellung und Ausnahmen:** Neue Taster übernehmen den Kampagnenstandard; der Spielleiter darf einzelne Eigenschaften je Taster sichtbar überschreiben. Änderungen des globalen Standards folgen 02.25: Vorschau, Wahl nur für neue oder auch bestehende Standardobjekte, Schutz individueller Ausnahmen.
- **Schalter bleiben separat:** Ein rastender Schalter erfordert kein aktives Halten (02.22). Die Halterzahlregel (02.36) und Wiederverbindungsfrist (02.37) bleiben unabhängige Konfigurationen.
- **Signalaktualisierung:** Wenn eine Halteaktion endet, berechnet der Server die aktiven Halter (02.36) und den booleschen Ausgang neu. Das angeschlossene Objekt reagiert gemäß seinen eigenen Signalverlustregeln aus 02.22.
- **Testbarkeit:** Live-Debugger und isolierte Tests sollen anzeigen, ob eine Bewegung, Reichweitenüberschreitung, verbotene Aktion oder ein relevanter Figurenzustand die Halteaktion beendete. Bei mehreren Spielern wird ausschließlich der betroffene Halter entfernt; doppelte Clientereignisse dürfen nicht doppelt wirken.

**Mit 02.39 entschieden:** Standard-Interaktionsreichweite und zugehörige Distanzmessung werden bei Kampagnenerstellung festgelegt, mit individuell markierten Abweichungen. Präsenz- und Bewegungsmelder sind zusätzlich als eigene Node-fähige Objekttypen vorgesehen; Erfassungsbereich und manuelle Bedienreichweite bleiben getrennte Eigenschaften. **Weiter offen:** Exakte Formeln/Skalen der Distanzmessung, Maus-/Tastatur-/Touch-Bedienung, Bewegung zurückweisen oder Halten beenden, Zustandskatalog und Besonderheiten tragbarer/Fahrzeugauslöser.

## 02.39 – Interaktionsreichweiten und Präsenz-/Bewegungsmelder (12.10.2026)

**Beschlossen: Variante C – die Standardreichweite und Distanzmessung für Schalter/Taster werden zentral bei der Kampagnenerstellung festgelegt; jedes Objekt kann eine eigene Ausnahme verwenden. Zusätzliche ausdrückliche Anforderung: Platzierbare Präsenzmelder und Bewegungsmelder sind als eigene Node-fähige Szenenobjekte vorzusehen.**

### 1. Bedienreichweite von Schaltern und Tastern

- **Kampagnenweiter Standard:** Der Spielleiter wählt eine Standard-Bedienreichweite und die passende Distanzmessregel. Die Skalierung muss zum Raster/maßstabsfreien/Hex-/Quadrat-Szenenmodell aus 02.4 passen und darf kein D&D-festes Feldmaß voraussetzen. Die konkrete Berechnungsformel bleibt offen.
- **Individuelle Objektausnahmen:** Ein Wandtaster kann Berührung erfordern, ein Schaltpult aus geringer Distanz bedienbar sein und ein Funkschalter eine abweichende Reichweite oder andere Interaktionsvoraussetzungen besitzen. Die wirksame Einstellung und ihre Herkunft (Kampagnenstandard/Objektausnahme) sind deutlich sichtbar.
- **Start und Halten getrennt prüfen:** Der Server validiert die zulässige Distanz beim Betätigen und bei einem gehaltenen Taster regelmäßig bzw. bei relevanter Bewegung. Wird die Haltebedingung ungültig, endet die Halteaktion nach 02.38 und Halterzahl/Signal werden neu berechnet.
- **Globale Änderungen:** Bei Änderung eines Standards greift die Vorschau-/Bestandsobjekt-/Ausnahmeregel aus 02.25. Bestehende bewusst gesetzte Ausnahmen werden nicht ohne Zustimmung überschrieben.

### 2. Interaktive Sensoren als Szenen- und Node-Objekte

- **Präsenzmelder:** Erkennt, ob mindestens ein zulässiges Ziel **im eingestellten Erfassungsbereich vorhanden** ist, unabhängig davon, ob das Ziel sich gerade bewegt. Ein typischer **boolescher Zustandsausgang** `Präsenz = EIN/AUS` ist aktiv, solange die definierte Präsenzbedingung zutrifft. Zusätzliche Ereignisausgänge wie `Bereich betreten` / `Bereich verlassen` sind vorgesehen.
- **Bewegungsmelder:** Erkennt **Bewegung eines zulässigen Ziels im Erfassungsbereich**; im Unterschied zum Präsenzmelder ist eine stillstehende Figur nicht allein wegen ihrer Anwesenheit ein Bewegungstreffer. Typischer **Ereignisausgang** `Bewegung erkannt`, mögliche kontinuierliche Bewegungsstatuswerte und Auslöse-/Rücksetzzeiten werden später detailliert entschieden.
- **Beim Platzieren benennbar:** Etwa `Präsenzmelder – Labor – Eingang Nord` oder `Bewegungsmelder – Hangar – Tor 3`. Beide gehören als eigenständige Objekttypen in die Karten-/Szenenbibliothek und liefern automatisch passende, typisierte **Ein-/Ausgangsports** für den bereits beschlossenen visuellen Node-Editor (02.17/02.20). Konkrete Ports und Sensoreinstellungen bleiben erweiterbar.
- **Auslöseketten:** Ein Präsenzmelder kann das Licht solange einschalten, wie sich eine Figur im Raum aufhält; ein Bewegungsmelder kann beim Vorbeilaufen einen Alarm oder Timer auslösen. Beide lassen sich mit Bedingungen, Inverter-Nodes, Echtzeit-/Rundenregeln und kampagnenweiten Schaltungen kombinieren.
- **Erfassungsbereich getrennt von Bedienreichweite:** Die **Reichweite, Form und Orientierung der Sensorzone** sind eigene Objekteigenschaften und nicht automatisch die Reichweite zum manuellen Bedienen dieses Sensors. Globale Erfassungsstandards mit gezielten Objekt-Ausnahmen sollen im Kampagnenassistenten vorbereitet werden; genaue Zonenformen, Sicht-/Wandblockade und Reichweitenberechnung folgen später.
- **Konfigurierbare Sensorziele:** Welche Figur-, NPC-, Tier-, Fahrzeug- oder sonstigen Objektarten ein Sensor erkennt, wie Sensitivität/Filter funktionieren und ob Verstecken/Sichtblockaden die Erkennung ändern, bleibt für 02.40 und weitere Detailentscheidungen offen. Keine pauschale Erkennung sämtlicher versteckter Objekte oder Figuren annehmen.

### 3. Serverlogik, Geheimnisschutz und Debugging

- Sensoren lesen **serverautoritär ausgewertete Szenenpositionen, Bewegung und zutreffende Zielkategorien**; nicht allein die gezeichnete Browserposition oder die Clientmeldung. Szenen-/Stockwerkszuordnung, Rasteroptionen und relevante Berechtigungen berücksichtigen.
- Die Sensorzone darf in der Spielleiteransicht sichtbar und bearbeitbar sein, auch wenn der Sensor bzw. seine Regeln für Spieler verborgen bleiben. **Sensorauslösung bedeutet nicht automatisch, dass die ausgelöste Figur durch Fog-of-War sichtbar wird** oder dass geheime Entitäten an nicht berechtigte Clients gesendet werden.
- Im Node-Testmodus sind Zustand/Impuls und erkannte Wechsel nachvollziehbar. Isolierte Tests sollen `Figur betritt Zone`, `Figur bleibt stehen`, `Figur bewegt sich innerhalb` und `Figur verlässt Zone` einschließlich mehrerer Figuren und Spielrunden/Echtzeit prüfen können. Ein simulierter Alarm darf niemals im realen Spiel aktiviert werden.
- Sensoren dürfen kein fest vorprogrammiertes Schaltziel benötigen, sondern ihre typisierten Ausgänge über dieselben farbig codierten Node-Leitungen und Bedingungen an beliebige berechtigte Reaktions-Nodes liefern.

**Noch offen:** Zielklassen und Filter (02.40), genaue Sensorzone (Kreis/Rechteck/Sichtkegel), Messskala, Wände/Hindernisse, Sichtlinie, Sensitivität, kontinuierliche Bewegung versus Einzelimpuls, Rücksetzen/Wiederholen, größere Sensorzahlen und Performance.

### Ergänzung zu 02.39 – Settingabhängige Kameras, Rauchmelder und erweiterbare Sensorarten (12.10.2026)

**Ausdrückliche Nutzeranforderung:** Neben Präsenz- und Bewegungsmeldern können je nach **Kampagnensetting** auch **Kameras, Rauchmelder und weitere passende Sensoren** eingesetzt werden. Das Sensor-/Node-System darf deshalb nicht auf nur zwei fest verdrahtete Gerätetypen beschränkt werden.

- **Kamera / Überwachungskamera:** Platzierbares und benennbares Szenenobjekt mit **Blickfeld bzw. Erfassungszone**, Ausrichtung und für das Setting/Modul geeigneten Erkennungsarten. Mögliche typisierte Node-Ausgänge: `Ziel erkannt`, `Bewegung erkannt`, `Alarm` oder `Kamera aktiv`. Ob Kameras zusätzlich eine aufrufbare simulierte In-Game-Sicht/Kameraansicht oder Aufzeichnungen liefern, ist eine **gesonderte spätere Entscheidung**; keine reale Video-Hardware oder Videostreamingpflicht wird vorausgesetzt.
- **Rauchmelder:** Platzierbares, benennbares Szenenobjekt, das auf den **serverseitig modellierten Rauch-/Gefahrenzustand** seiner Erfassungszone reagiert. Mögliche Node-Ausgänge: `Rauch erkannt` als Ereignis und `Rauchalarm aktiv` als boolescher Zustand. Der Melder darf nicht voraussetzen, dass bereits eine globale Rauchsimulation existiert; passende Umweltzustände/Regelmodule oder ausdrücklich gesetzte Story-/Node-Werte müssen als Datenquelle vorgesehen werden.
- **Weitere Sensorfamilien je Setting:** Erweiterbare Vorlagen statt einer endgültig geschlossenen Liste, z. B. Temperatur-/Hitze-, Gas-, Licht-, Geräusch-, Laser-/Lichtschranken- oder magische Detektoren als **mögliche** spätere Typen. Nicht alle Beispiele sind bereits als einzelne konkrete Funktionen vollständig entschieden; die Fähigkeit zum Erweitern ist die Produktvorgabe.
- **Setting-/Kampagnenbibliothek:** Die für den Spielleiter angebotenen Sensorvorlagen sollen sich nach Genre/Regelprofil/Kampagnenauswahl sinnvoll filtern oder freischalten lassen. Fantasy-Szenen können andere Vorlagen verwenden als Science-Fiction- oder Cyberpunk-Szenen, ohne separate Event-Engines zu brauchen.
- **Gemeinsame Infrastruktur:** Sensorobjekte haben stabile IDs, Szenenzuordnung, Objektnamen, passende typisierte Eingänge/Ausgänge, kampagnenweite Verbindungen, farbcodierte Leitungen und Live-Istwerte im Test-/Debugmodus. Sensor-**Erfassungsbereich**, relevante Ziel-/Umweltmerkmale, Empfindlichkeit/Schwellenwert, Aktiviert/Deaktiviert und etwaige Hindernis-/Sichtregeln sind je nach Sensorfähigkeit konfigurierbar; genauer Portkatalog und Geometrie folgen später.
- **Unterschiedliche Datenquellen:** Kameras, Präsenzmelder und Bewegungsmelder können Position, Bewegung und Sichtbedingungen auswerten; Rauchmelder dagegen **Umwelt-/Gefahrenzustände**. Diese Arten von Eingaben dürfen nicht als dieselbe Figurenerkennungslogik behandelt werden.
- **Kampagnenstandards und Ausnahmen:** Sinnvolle Vorlagen und Defaultparameter bei Kampagnenerstellung vorsehen, mit gezielten Abweichungen pro Sensor und Bestandsänderungs-/Ausnahmeregeln nach 02.24–02.25.
- **Sicht- und Geheimnisschutz:** Eine Kamera- oder Melderauslösung berechtigt nicht automatisch zur Offenlegung geheimer Figuren, Szenen, Sensoren oder der überwachten Bereiche. Simulierte Sensorreaktionen bleiben im isolierten Node-Test ohne reale Alarm- oder Spielwirkungen.
- **Abgrenzung:** Gemeint sind zunächst **virtuelle Kampagnenobjekte**. Schnittstellen zu physischen Kameras oder Rauchmeldern sind weder vorausgesetzt noch beschlossen.

**Mit 02.40 entschieden:** Sensorfähigkeiten bestimmen die erlaubten, frei kombinierbaren Ziel-/Merkmals-/Fraktions-/Umweltfilter und Schwellenwerte; globale Kampagnenstandards mit bewusst gesetzten Objektausnahmen. **Weiter offen:** Erfassungsgeometrie (02.41), Wände/Sichtlinie/Licht, konkrete Schwellen-/Einheitenprofile, Alarm-Rücksetzung, Kamerasichten/Aufzeichnungen, virtuelle Umweltmodellierung, zusätzliche Sensortypen und Umsetzung.

## 02.40 – Frei konfigurierbare Sensorfilter (12.10.2026)

**Beschlossen: Variante C – Sensoren erhalten frei konfigurierbare, aber zu ihren Fähigkeiten passende Erkennungsfilter. Die Kampagnenerstellung bietet globale Standards; ein einzelner Sensor kann davon ausdrücklich abweichen.**

### Filter abhängig von der Sensorart

- **Präsenzmelder:** Geeignete Zielarten auswählen, z. B. Spielerfiguren, NPCs/Kreaturen, Tiere, Fahrzeuge, Gegenstände oder weitere durch das Regel-/Szenenmodell beschriebene Entitäten. Präsenz bedeutet weiterhin „geeignetes Ziel befindet sich im Bereich“, auch wenn es stillsteht.
- **Bewegungsmelder:** Filter für Zielarten und Bewegung; nur passende Bewegungsereignisse auswerten. Stillstehende Anwesenheit allein ist kein Bewegungsereignis.
- **Kameras:** Zu ihren Sicht-/Erkennungsfähigkeiten passende Kriterien, z. B. ausgewählte Figuren, Fraktionen, Charakter-/Objekt-Tags, definierte Zustände oder Bewegung innerhalb des Blickfeldes. Ob eine Kamera tatsächliche eigene Aufnahmen/Bilder liefert, wird getrennt geplant.
- **Rauch- und weitere Umweltmelder:** Passende, vorhandene **Umweltwerte oder Gefahrzustände** auswählen und mit Vergleichs-/Schwellwerten verknüpfen, z. B. Rauchwert über einem einstellbaren Schwellwert oder Hitze-/Gasalarm. Ein Rauchmelder benötigt eine **gültige Datenquelle** (Umweltmodul, Story-/SL-Zustand oder erlaubte Node-Eingabe), nicht eine vorausgesetzte globale Physiksimulation.
- **Weitere settingabhängige Sensoren:** Die Sensorfamilien sind erweiterbar; konkrete Datentypen und erlaubte Vergleichsmöglichkeiten stammen aus ihren versionierten Fähigkeiten-/Portvorlagen. Unpassende Filter wie „Rauchkonzentration“ für einen gewöhnlichen Präsenzmelder dürfen ohne passendes Erweiterungsmodul nicht frei erfunden werden.

### Logik, Kampagnenstandards und Ausnahmen

- **Mehrere passende Bedingungen:** Filter lassen sich mit den beschlossenen **UND/ODER/NICHT-Gruppen aus 02.17** und den zulässigen typspezifischen Vergleichen kombinieren. Beispiel Kamera: `(Zielart Spielerfigur UND Fraktion feindlich) ODER Ziel-Tag Eindringling`.
- **Voreinstellungen bei Kampagnenerstellung:** Sensortypen erhalten passende Standardfilter, Zielgruppen und wo sinnvoll Schwellenwerte aus dem Kampagnen- bzw. Genreprofil. Neue Sensoren übernehmen diese Voreinstellungen.
- **Pro Sensor gezielt abweichen:** Jedes Objekt kann eigene Zielkategorien, Tags, Bedingungen oder Schwellen festlegen, klar als **Kampagnenstandard** oder **individuelle Ausnahme** gekennzeichnet. Änderungen an globalen Regeln mit Vorschau, Altbestand-Auswahl und Ausnahmeschutz nach 02.25.
- **Eindeutige Portausgabe:** Sensoren geben entsprechend ihrem Typ anliegende Zustandswerte, Zahlenwerte und/oder Ereignisimpulse über typisierte Ports aus. Ein Ausgang wird nur aktiviert, wenn die Erkennungsbedingungen tatsächlich erfüllt wurden; „Kabel verbunden“ heißt weiterhin nicht „Signal erkannt“.
- **Serverautorität und Berechtigungen:** Der Server wertet gültige Positionen, Entitätstags/-zustände oder die tatsächlich vorhandenen Umweltwerte aus. Versteckte Sensoren und Zielinformationen dürfen durch Filterresultate, Node-Logs oder Kameras nicht an unberechtigte Spieler gelangen.
- **Einfach und fortgeschritten:** Filtervorlagen mit verständlicher Auswahl für Anfänger, frei kombinierbare Bedingungsgruppen und Node-Logik für Fortgeschrittene, ohne unkontrolliert ausführbare Skripte. Falsche Kombinationen oder fehlende Datenquellen werden erklärt.
- **Testbarkeit:** Der isolierte Debugger kann Ziele mit verschiedenen Kategorien/Tags, Bewegungswechsel, Fraktionen sowie eine veränderte Rauch-/Umweltgröße simulieren und das tatsächliche Filterergebnis mit der erwarteten Auslösung vergleichen. Die Liveansicht zeigt Signal und Filterentscheidung nur berechtigten Spielleitern.

**Abgrenzung:** Dieses Feature beschreibt virtuelle Objekte einer Kampagne, keine Überwachung realer Personen oder Anbindung realer Kameras/Rauchmelder. Eine vorgegebene Kamera-Aufzeichnung, echte Rauchphysik oder eine fest verdrahtete Liste zusätzlicher Sensoren wird hier nicht beschlossen.

**Mit 02.41 entschieden:** Sensorzonen mit Kreis, Rechteck, Sichtkegel oder frei zeichnbarem Polygon direkt im Karteneditor bearbeiten; Sichtbarkeit der Zonen wird als Kampagnenstandard mit gezielten Sensor-Ausnahmen gespeichert. **Weiter offen:** Sichtlinien-/Wand- und Lichtblockaden (02.42), genaue Stockwerks-/Geometrie- und Schwellenregeln, mehrstufige Alarme, Rücksetzzeiten, Kameraansichten und Umweltmodule.

## 02.41 – Flexible Sensorzonen und global steuerbare Sichtbarkeit (12.10.2026)

**Beschlossen: Variante C – Sensoren unterstützen Kreis, Rechteck, gerichteten Sichtkegel und frei gezeichnete Polygone. Zusätzliche ausdrückliche Produktanforderung: Die Sichtbarkeit der Sensor-Erfassungsbereiche wird bei der Kampagnenerstellung global festgelegt, mit bewussten Ausnahmen für einzelne Sensoren.**

### Formen und Bearbeitung im Karteneditor

- **Standardformen:** Kreis mit Radius, Rechteck mit Maßen/Drehung, Sichtkegel mit Richtung/Öffnungswinkel/Reichweite sowie frei gezeichnete **Polygonzonen** mit veränderbaren Eckpunkten.
- **Direkt im Karteneditor:** Der Spielleiter kann eine Zone aufziehen/zeichnen, verschieben, skalieren, drehen und später an Griffpunkten bearbeiten. Die Darstellung von Grenzen und Flächen soll bei Zoom und unterschiedlichen Kartenmaßstäben verständlich bleiben.
- **Objektgebundene Erfassung:** Die Zone gehört zu einer stabil identifizierten Kamera, einem Präsenz-/Bewegungs-, Rauch- oder sonstigen Sensor. Sie kann je Sensortyp eine geeignete vorgegebene Form erhalten und am Objekt bewusst überschrieben werden. Ob Zone und Sensor beim Verschieben automatisch gekoppelt bleiben, ist bei der Detailumsetzung zu klären; die Objektzuordnung darf dabei nicht verloren gehen.
- **Eine gemeinsame Sensorlogik:** Der Server verwendet die gespeicherte **logische Geometrie** und Szenen-/Stockwerkszuordnung zur Ermittlung der tatsächlichen Erfassung. Eine gezeichnete Markierung ist nur eine Visualisierung, niemals die alleinige Grundlage der Spiellogik.
- **Validierung:** Unsinnige Maße, ungültige/selbstschneidende Polygone und nicht zuordenbare Karten-/Stockwerksbezüge müssen erkannt werden; die konkrete Flächen-, Koordinaten- und Höhenberechnung bleibt für die technische Planung offen.
- **Nicht automatisch durch Wände hindurch:** In dieser Entscheidung wird **noch nicht** festgelegt, wie Mauern, Fenster, Türen oder Sicht-/Lichtbedingungen eine Zone begrenzen. Das folgt in 02.42.

### Sichtbarkeit der Sensorzonen – globaler Standard mit Ausnahmen

- **Kampagnenerstellung:** Der Spielleiter bestimmt eine zentrale **Sichtbarkeitsrichtlinie für Sensor-Erfassungsbereiche**, statt bei jedem Sensor dieselbe Sichtbarkeit erneut einzustellen. Mögliche Freigaben sind **nur für berechtigte Spielleiter** oder zusätzlich **für freigegebene Spieler bzw. Gruppen** sichtbar; welche feingranularen Freigaben als Oberfläche verfügbar sind, wird später im Berechtigungs- und Sichtbarkeitsdesign präzisiert.
- **Ausnahme je Sensor:** Ein einzelner Präsenzmelder, Rauchmelder oder eine Kamera darf von diesem Standard abweichen. Die Objekt-Eigenschaften zeigen klar „Kampagnenstandard“ oder „individuelle Ausnahme“ und den **wirksamen** Sichtbarkeitsstatus.
- **Änderung späterer Standards:** Globale Anpassungen folgen 02.25: Vorschau der betroffenen Zonen, wahlweise nur neue Sensoren oder zusätzlich bestehende Sensoren ohne Ausnahme; gezielte Ausnahmen bleiben geschützt.
- **SL-Editorvorschau separat:** Berechtigte Spielleiter können die Zonen beim Bearbeiten und Debuggen einblenden, um Form, Ausrichtung, Reichweite und Auslösungen zu prüfen. Diese **Editoranzeige ist nicht gleich Spielerfreigabe**.
- **Geheimnisschutz:** Für Spieler nicht freigegebene Bereiche, verborgene Kameras/Sensoren und interne Erkennungsdaten dürfen nicht bloß unsichtbar gezeichnet werden; der Server liefert nicht berechtigten Clients diese Zone/Metadaten gar nicht. Spielerfreigabe einer Zone ist außerdem **getrennt von der Sichtbarkeit des Sensorgehäuses, von Fog-of-War, von Figurenpositionen und von der Sensor-Aktivität**. Eine sichtbare Zone darf keine versteckten Figuren automatisch enthüllen.
- **Sichtbar heißt nicht aktiv:** Die Visualisierung der Erfassungsfläche und der aktuelle Erkennungszustand/Impuls sind getrennte Größen. Live-Iststand und isolierter Simulationstest aus 02.20/02.31–02.32 bleiben funktionsfähig, auch wenn Spieler die Zone nicht sehen dürfen.

### Beispiele

- Eine Überwachungskamera nutzt einen gedrehten Sichtkegel, dessen Grenze Spieler je nach Kampagnenrichtlinie erkennen oder nicht erkennen können.
- Ein Präsenzmelder in einem unregelmäßig geschnittenen Raum nutzt eine Polygonzone, die der Spielleiter direkt auf der Karte anlegt.
- Ein Rauchmelder hat einen rechteckigen oder polygonalen Erfassungsbereich; seine Rauch-Erkennung setzt weiterhin eine reale Datenquelle innerhalb der Spielsimulation voraus.
- Eine geheime Falle verwendet eine **nur für Spielleiter sichtbare** Sensorzone als bewusste Ausnahme, auch wenn andere, öffentlich angekündigte Gefahrenzonen für die Spieler eingeblendet werden.

**Mit 02.42 entschieden:** Hindernisse wirken abhängig vom Sensortyp – unabhängig von Hindernissen, per Sichtlinie oder nach definierten Durchdringungs-/Blockaderegeln; Kampagnenstandards und Sensorausnahmen. **Weiter offen:** Erfassung über mehrere Stockwerke, konkrete Licht-/Dunkelheitseinflüsse (02.43), feingranulare Spieler-/Gruppenfreigabe, Darstellungsstil, bewegliche Sensorzonen und Umweltwerte.

## 02.42 – Wände, Türen und Hindernisse bei Sensoren (12.10.2026)

**Beschlossen: Variante C – je Sensortyp konfigurierbare Hindernisprüfung mit globalen Kampagnenstandards und individuellen Ausnahmen pro Sensor.**

### Drei grundlegende Erfassungsstrategien

- **Hindernisunabhängig:** Ein entsprechend befähigter Sensor wertet passende Ziele innerhalb seiner Erfassungszone aus, ohne Wände bzw. Türen als pauschalen Ausschluss zu behandeln. Diese Fähigkeit muss bewusst zum Sensortyp bzw. Regelmodul passen.
- **Sichtlinienabhängig:** Kameras und andere optische Sensoren können eine freie Sichtverbindung zwischen Sensor und Ziel voraussetzen. Undurchsichtige, sichtblockierende Wände und entsprechend geschlossene Türen verhindern die Erkennung; offene Türen können die Sicht freigeben. Ob Fenster durchsichtig sind, folgt ihren bestehenden individuellen Sichtblockade-Eigenschaften (02.9).
- **Eigene sensorabhängige Hindernis-/Materialregeln:** Bestimmte Sensoren können Materialien oder Objektarten unterschiedlich behandeln, z. B. ein magischer, thermischer oder ein anderer spezieller Detektor, der ausgewählte Barrieren durchdringen darf. Konkrete Durchdringungsfähigkeit und Materialkatalog sind später pro Sensortyp/Modul zu spezifizieren; keine universelle Durchdringung annehmen.

### Kampagnenstandards, konkrete Sensoren und Änderungen

- **Globaler Standard bei der Kampagnenerstellung:** Für unterstützte Sensorfamilien werden geeignete Standard-Hindernisprofile festgelegt; beispielsweise bei normalen optischen Kameras Sichtlinienprüfung. Diese globale Vorgabe darf keine technischen Fähigkeiten an einen Sensor erfinden, der sie nicht besitzt.
- **Individuelle Ausnahmen:** Ein einzelner Sensor darf – innerhalb seiner tatsächlich verfügbaren Fähigkeiten – vom Kampagnenstandard abweichende, sichtbar markierte Hindernis-/Durchdringungsregeln nutzen. Änderungen globaler Regeln folgen 02.25 mit Vorschau, Bestandsschutz und Schutz eigener Ausnahmen.
- **Bestehende Hindernis-Komponenten wiederverwenden:** Die Sicht-, Licht- und Bewegungsblockade von Wänden, Türen und Fenstern aus 02.9 sind **getrennte Eigenschaften**. Eine bewegungsblockierende, aber sichtdurchlässige Glasscheibe verhindert nicht schon allein deshalb eine optische Sichtlinie. Ein spezieller Sensor kann ein anderes Blockadeprofil verwenden.
- **Dynamische Neuauswertung:** Tür öffnen/schließen, Hindernis verändern/zerstören oder einen Sensor bzw. ein Ziel bewegen kann die tatsächlich erfassten Ziele verändern. Der Server muss die betroffenen Erkennungszustände konsistent neu ermitteln, ohne allein einem Client zu vertrauen.
- **Rauchmelder und Umweltwerte:** Ein Rauchmelder prüft einen gültigen Rauch-/Gefahrenwert in seiner Zone, nicht einfach die Sichtlinie zu einer Figur. Ob und wie Rauch durch Türen, Fenster oder Öffnungen strömt, ist Sache eines gesondert zu definierenden Umwelt-/Ausbreitungsmodells und **nicht** automatisch durch diese Entscheidung festgelegt.
- **Stockwerke:** Wände, Sensoren und Ziele dürfen nicht ohne nachvollziehbare Regeln über Stockwerksgrenzen hinweg gemischt werden; vertikale Reichweiten, Treppenöffnungen und durchdringende Sensoren über mehrere Ebenen bleiben gesondert offen.

### Editor, Signale und Sicherheit

- **Sensorzone ≠ wirksame Erfassungsfläche:** Die gezeichnete Zone aus 02.41 ist zunächst der geometrische Suchbereich. Abhängig von Hindernisregeln kann der **tatsächlich erfasste Teil** kleiner sein. Im Spielleiter-Editor/Testmodus sollen Hindernis- und Sichtlinien-Blockaden sowie Gründe für Treffer/Nicht-Treffer nachvollziehbar angezeigt werden.
- **Typisierte Node-Ports:** Detektionszustände und Ereignisimpulse bleiben wie in 02.20/02.21 unterscheidbar und können in allen Ansichten an Alarm, Licht, Tür oder Storylogik weitergegeben werden. Eine blockierte Erkennung darf kein erfolgreiches „Ziel erkannt“-Ereignis erzeugen.
- **Geheimnisschutz:** Selbst eine bewusst durchdringende Kamera/Sensorregel hebt niemals automatisch Fog-of-War oder Spielerrechte auf; verborgene Sensoren, Zonen, Ziele und interne Erkennungswerte nur an berechtigte Clients übertragen.
- **Isolierte Tests:** Hindernis öffnen/schließen, Glasfenster, undurchsichtige Wand, sensorabhängige Durchdringung und geänderte Zonen lassen sich im Debugger mit Soll-/Ist-Prüfung testen, ohne echte Spielszenen zu verändern.

**Mit 02.43 entschieden:** Je Sensortyp abhängige Licht-/Dunkelheitsprüfung, darunter normale Kameras, Nachtsicht, Wärmebild und nichtoptische Sensoren; Kampagnenstandards mit Objektausnahmen. **Weiter offen:** Material-/Sensortyp-Matrix, Hindernisgeometrie, Stockwerke, konkrete Lichtskala/Spezialoptik-Profile, Wahrnehmungsalgorithmus, Geräusch-/Rauch-Ausbreitung sowie Auslöse- und Rücksetzverhalten (02.44).

## 02.43 – Licht und Dunkelheit bei Sensoren (12.10.2026)

**Beschlossen: Variante C – die Lichtabhängigkeit wird je Sensortyp beziehungsweise Sensormodul frei innerhalb seiner zulässigen Fähigkeiten konfiguriert. Der Spielleiter wählt passende globale Standardeinstellungen bei der Kampagnenerstellung; einzelne Sensoren können davon abweichen.**

### Erkennungsprofile

- **Gewöhnliche optische Kamera:** Kann eine **ausreichende Beleuchtung** des Ziels bzw. der erfassten Umgebung benötigen. Liegt die serverseitig ausgewertete Helligkeit unter einem geeigneten, konfigurierten Schwellenwert, wird das Ziel nicht allein wegen seiner Position im Sichtkegel als optisch erkannt.
- **Nachtsichtkamera / Restlichtverstärker:** Darf abhängig von ihren definierten Fähigkeiten schwaches Licht nutzen oder andere zulässige Nacht-Erkennungsregeln anwenden. **Nachtsicht ist nicht pauschal dasselbe wie Wände durchsehen**; die Hindernisprüfung aus 02.42 bleibt unabhängig.
- **Wärmebildsensor:** Kann für ein geeignetes Ziel **verfügbare Wärme-/Temperaturmerkmale oder entsprechende Regelprofilwerte** auswerten und von normalem sichtbarem Licht unabhängig sein. Temperatur- oder Wärmebilder benötigen eine gültige simulierte Datenquelle; eine realistische Wärmephysik wird nicht automatisch vorausgesetzt.
- **Bewegungs- und Präsenzmelder:** Lichtabhängigkeit richtet sich nach der konkret ausgewählten Sensortechnik. Passive Präsenz- oder nichtoptische Bewegungsmelder müssen nicht automatisch sichtbares Licht erfordern; eine auf optischer Bilderkennung basierende Variante kann Licht prüfen.
- **Rauch-/Gas-/Hitze-/magische Sensoren:** Nutzen ihre jeweilige Umwelt- bzw. settingabhängige Erkennungsquelle. Sichtbare Dunkelheit ist für einen Rauchmelder keine generelle Sperre. Magische Sensoren können nur die vom zugehörigen Regel-/Objekttyp wirklich vorgesehenen Lichtregeln umgehen.

### Einstellung, Ausnahmen und dynamische Neubewertung

- **Bei der Kampagnenerstellung:** Passende Sensortyp-Defaults konfigurieren, beispielsweise `sichtbares Licht nötig`, `bei schwachem Licht möglich` oder `sichtlichtunabhängig` mit gegebenenfalls geeigneten Schwellen. Nur die vom gewählten Sensorprofil unterstützten Varianten anbieten; der genaue Lichtmaßstab bleibt offen.
- **Je Sensor überschreibbar:** Eine gewöhnliche Kamera kann eine bewusst gesetzte Abweichung erhalten, **soweit ihre Fähigkeiten diese erlauben** (etwa ein konfiguriertes Nachtsichtmodul). Die UI unterscheidet geerbten Kampagnenstandard, individuelle Ausnahme und effektiv geltendes Profil.
- **Änderung der globalen Vorgabe:** Vorschau und Wahl zwischen nur neu erzeugten oder auch bestehenden, nicht explizit überschriebenen Sensoren; individuelle Ausnahmen schützen (02.25).
- **Beleuchtung als wirkliche Spielgröße:** Der Server verwendet die kanonischen Lichtquellen, Licht- und Sichtblockaden und gegebenenfalls gültige Umweltdaten des Szenenmodells (02.6 und 02.9). Geht ein Licht an/aus, bewegt sich eine Lichtquelle oder ändert sich die Dunkelheit, müssen betroffene Sensoren nachvollziehbar neu bewertet werden. Eine bloße grafische Helligkeitsanimation im Client darf keine Detektion begründen.
- **Getrennte Regeln:** Erfassungsgeometrie (02.41), Hindernisse (02.42), Lichtabhängigkeit (02.43), Ziel-/Umweltfilter (02.40), Sichtbarkeit von Sensorzonen (02.41) und Sensor-Ausgangslogik sind unabhängige, gemeinsam auszuwertende Dimensionen.
- **Node-Ports und Debugger:** Die tatsächliche Erkennung kann einen getypten booleschen Ausgang beziehungsweise Ereignisimpuls erzeugen. Im berechtigten Debugger erläutern Zustände wie `Ziel in Zone, aber zu dunkel`, `Nachtsicht verfügbar`, `Wärmesignal nicht vorhanden`, `Sicht durch Wand blockiert` den jeweiligen Grund.
- **Isolation, Sicherheit und Geheimhaltung:** Gespeicherte Tests können Licht an-/ausschalten, Nachtsichtfähigkeiten variieren und Treffer/Nichttreffer prüfen, ohne die echte Kampagne zu verändern. Sensorerkennung darf keine verborgenen Objekte, Figuren oder sensorinternen Details unberechtigt an Spieler freigeben.

**02.44 beschlossen:** Pro Sensortyp konfigurierbare Ansprech-/Nachlauf-/Wiederholungszeiten und speicherbare quittierbare Alarme, jeweils mit globalen Standards und Objektausnahmen sowie Echtzeit- und Rundenzeitbasis. **Weiter offen:** Quittierungsrechte und Resetwege (02.45), Licht-/Wärmedetailmodelle, Timer-Neustart, Pause-/Offline- und Performanceverhalten.

## 02.44 – Sensor-Auslösezeiten, Nachlauf und quittierbare Alarme (12.10.2026)

**Beschlossen: Variante C – Sensoren erhalten je nach Sensortyp frei konfigurierbare Auslöse-, Halte- und Rücksetzregeln. Die Kampagnenerstellung legt globale Standards je Sensortyp fest, mit sichtbar markierten Ausnahmen pro Sensor.**

### Unterstützte Modi

- **Sofortige Auslösung:** Die erfolgreich geprüfte Erkennungsbedingung kann unmittelbar einen booleschen Zustand ändern und/oder einen Ereignisimpuls ausgeben; Impuls und anliegender Wert sind gemäß 02.20–02.21 zu unterscheiden.
- **Ansprech-/Auslöseverzögerung:** Ein Sensor reagiert erst, nachdem eine qualifizierte Bedingung lang genug bestand. Beispiel: Kamera erkennt einen Eindringling erst nach einer gewählten Verweildauer. Verhalten bei einer kurzen Unterbrechung innerhalb der Verzögerung später detaillieren.
- **Fortbestehender Zustandsausgang:** Präsenz kann als EIN anliegen, solange tatsächlich mindestens ein geeignetes Ziel die Erkennungsregel erfüllt; die Roh-Erkennung und ein nachfolgend gespeicherter Alarm müssen getrennt behandelt werden.
- **Nachlaufzeit:** Nach Wegfall der Erkennung kann ein Ausgang eine wählbare Dauer aktiv bleiben. Beispiel: Licht bleibt nach Verlassen des Raums noch eine Weile an. Ob erneute Erkennung den Nachlauf zurücksetzt oder verlängert, wird später präzisiert.
- **Wiederholte Impulse:** Ein dafür geeigneter Sensor kann bei weiter bestehender Bedingung in konfigurierbaren, begrenzten Abständen erneut Ereignisse ausgeben. Ereignisschleifenschutz und Duplikaterkennung gelten weiterhin.
- **Gespeicherter/quittierbarer Alarm:** Ein Alarmsignal kann nach einem Treffer dauerhaft aktiv bleiben, selbst wenn die Erkennungsbedingung entfällt, bis ein ausdrücklich vorgesehenes Reset-/Quittierungsereignis akzeptiert wurde. Rechte und Resetwege werden in 02.45 gesondert entschieden.
- **Fähigkeitsgrenzen:** Aus einer Einstellung darf keine nicht vorhandene Sensortechnik entstehen. Kamera-, Rauch-, Präsenz-, Bewegungs- und settingabhängige Sensorvorlagen bieten nur die für sie unterstützten Modi und Porttypen an.

### Voreinstellungen und zeitliche Grundlagen

- **Kampagnenweite Standards:** Je Sensortyp Standardmodus, erlaubte Ansprechdauer, Nachlauf, Wiederholungsintervalle und gegebenenfalls Alarm-Speicherverhalten im Kampagnenerstellungs-Assistenten definieren.
- **Individuelle Sensor-Ausnahmen:** Der Spielleiter kann einzelne Sensoren anders konfigurieren und sieht geerbte bzw. überschriebene Werte. Spätere Änderung der Kampagnenstandards mit Vorschau/Bestandsauswahl und Schutz von Ausnahmen gemäß 02.25.
- **Echtzeit oder Runden:** Eine passende Verzögerung und ein Nachlauf können wahlweise in echten Sekunden/Minuten oder Spielrunden bemessen sein. Die Zeitgrundlagen sind ausdrücklich getrennt und werden nicht automatisch ineinander umgerechnet (02.15–02.16).
- **Unabhängig von Erkennungsbedingungen:** Zielarten/Filter (02.40), Zonenform/Sichtbarkeit (02.41), Hindernisse (02.42), Licht (02.43), Rohdetektion und die spätere Alarmrücksetzung sind getrennte Eigenschaften.

### Serverseitige Logik, Tests und Geheimnisse

- **Autoritativer Sensorzustand:** Server startet, unterbricht und beendet Zeitgeber; er erstellt die daraus folgenden Signaländerungen atomar. Wiederholte Netzwerkereignisse dürfen keinen doppelten Alarm oder unerwartete Verlängerungen verursachen.
- **Debug-Modus:** Spielleiter sehen nachvollziehbar Rohdetektion, laufende Auslöseverzögerung, Zustand EIN/AUS, aktive Nachlaufzeit, nächsten wiederholten Impuls, gespeicherten Alarm sowie akzeptierte/abgelehnte Resets. Die genauen Namen von Ports/Statuswerten folgen später.
- **Wiederholbare Tests:** In der isolierten Simulation können Auslöseverzögerungen, kurzzeitiges Betreten und Verlassen, Nachlauf, erneute Erkennung, wiederholte Impulse sowie Alarmquittierungen im Echtzeit- oder Rundenmodus überprüft werden. Keine echten Türen, Timer oder Spielzustände verändern.
- **Sicherheits- und Sichtbarkeitskontrolle:** Sensorreset nur nach serverseitiger Autorisierung. Interne Signale/Alarmdaten und versteckte Sensoren dürfen nicht an unberechtigte Spieler gesendet werden; die Zone-Sichtbarkeit aus 02.41 bleibt unabhängig.

**02.45 beschlossen:** Berechtigungen und Resetwege für Alarme über Kampagnenstandard und Sensor-Ausnahmen mit überprüften SL-Aktionen, Bedienobjekten und Node-/Szenen-Ereignissen; alle Vorgänge werden protokolliert. **Weiter offen:** Quittierung und Rücksetzung bei fortbestehender Gefahr (02.46), erneute Erkennung während Nachlauf, Entprellung/Wiederholungsgrenzen, Timer bei Pause/Neustart, Persistenz und Skalierung.

## 02.45 – Berechtigte Sensoralarm-Quittierung über SL, Bediengeräte und Node-Signale (12.10.2026)

**Beschlossen: Variante C – der Spielleiter definiert im Kampagnenassistenten einen globalen Berechtigungs- und Auslöse-Standard für quittierbare/gespeicherte Sensoralarme, der pro Sensor gezielt überschrieben werden kann.**

### Mögliche Quittierungs- und Resetwege

- **Direkte Spielleiteraktion:** Eine berechtigte Spielleitung darf über die Sensor-Eigenschaften, eine Alarmliste oder den Node-Editor den Quittierungs-/Resetvorgang anfordern. Der Server prüft die Kampagnenrolle und den zugeordneten Sensor.
- **Bedienobjekt im Spiel:** Ein vom Spielleiter platzierter Reset-Taster, ein Terminal, eine Alarmzentrale oder ein vergleichbares settingabhängiges Objekt kann eine Quittierung auslösen, sofern die konkrete Figur zum Bedienobjekt Zugang hat, die Bedieninteraktion zulässig ist und die Sensor-Quittierungsrichtlinie sie ausdrücklich gestattet.
- **Node-/Szenenereignis:** Ein geeignetes, überprüftes Node-Signal oder definiertes Szenenereignis kann eine Alarm-Quittierung bzw. einen Reset anfordern. Das Signal darf die Sensor-Berechtigungsprüfung **nicht umgehen**: Herkunft, Berechtigungskontext und zulässige Automationsquelle werden serverseitig validiert. Automatische Resets nur nach explizit autorisierter Regel.
- **Beschränkung nach Rollen und Figuren:** Der Spielleiter kann bestimmen, welche Spielleiter-/Mitspielleiter-Rollen, Spielerrollen, Figuren/Fraktionen oder explizit freigegebenen Akteure und Bedienobjekte einen bestimmten Alarm quittieren dürfen. Zugriff auf das Bedienobjekt allein ist nicht zwingend bereits eine Resetberechtigung.
- **Passende Sensortypen:** Quittierung/Reset ist nur für Sensoren und Signalzustände verfügbar, die einen gespeicherten bzw. quittierpflichtigen Alarm oder eine eigene Resetfunktion tatsächlich unterstützen. Ein einfacher Präsenzzustand braucht nicht unnötig eine Quittierung.

### Globale Vorgaben und Objektausnahmen

- **Bei Kampagnenerstellung:** Voreinstellung für autorisierte Rollen/Akteure, zulässige Bedienwege und die verfügbaren Reset-/Quittierereignisse festlegen. Genre und Regelprofil dürfen passende Vorgaben liefern, die Event-Engine bleibt generisch.
- **Pro Sensor abweichend:** Eine geheime Sicherheitskamera kann ausschließlich durch den SL zurücksetzbar sein, während ein öffentlicher Rauchmelder über eine berechtigte Alarmzentrale quittiert werden darf. Die wirksamen, geerbten und individuell überschriebenen Einstellungen sind sichtbar markiert.
- **Globale Einstellungen später ändern:** Vorschau, wahlweise nur neue oder auch bisher nicht individuell überschriebene Sensoren und Schutz bestehender Ausnahmen gemäß 02.24–02.25.
- **Rechte und Geheimnisschutz:** Spieler müssen weder einen versteckten Sensor noch seinen internen Alarmzustand kennen, wenn sie dazu nicht berechtigt sind. Die Bedienbarkeit einer Resetstelle und Sichtbarkeit von Sensorzonen (02.41) sind voneinander unabhängig.

### Serverseitige Prüfung, Audit und Debugging

- **Jede Anforderung prüfen:** Authentifizierte Identität bzw. vertrauenswürdige Automationsquelle, Kampagnen-/Szenenzuordnung, Rollen-/Figurenrecht, Objektrechte und die konkret freigegebene Resetmethode werden geprüft. Ein bloßes Clientkommando oder irgendein angeschlossenes Node-Kabel darf einen Alarm nicht ungeprüft zurücksetzen.
- **Audit:** Akzeptierte und abgelehnte Vorgänge werden für berechtigte Spielleiter nachvollziehbar erfasst, einschließlich Zeitpunkt/Spielrunde, Sensor, handelnder Figur/Rolle oder Automationsquelle, Resetweg, vorherigem/nachherigem Zustand und Abweisungsgrund. Aufbewahrungsfrist und Detailtiefe später entscheiden.
- **Atomarer Statuswechsel:** Serverseitiger Alarmzustand und relevante Node-Ausgänge dürfen nicht doppelt oder widersprüchlich verändert werden, auch nicht bei konkurrierenden Reset-, Alarm- und Auslöseereignissen (02.35). Wiederholte Netzwerkpakete sind sicher zu deduplizieren.
- **Quittieren ist nicht automatisch Gefahrenbeseitigung:** Eine Reset-Anforderung ändert nicht die real ausgewertete Präsenz-, Rauch- oder Sicherheitsbedingung. **02.46 beschlossen:** Die Quittierung ist vom Stummschalten und vom vollständigen Reset getrennt; fortbestehende Gefahren dürfen durch diese Aktionen nicht als beseitigt erscheinen.
- **Isolierte Tests:** Szenarien prüfen berechtigte/unberechtigte SL- und Spieleraktionen, Alarmterminal, Node-Reset, konkurrierende Ereignisse und fehlende Sensorberechtigung. Simulation schreibt niemals echte Alarme oder Kampagnenzustände.

**Mit 02.46 entschieden:** Gefahreneingang, Quittierung, Stummschaltung und gespeicherter Alarm sind getrennte Zustände mit globalen Sensortyp-Vorgaben und Objektausnahmen. **Weiter offen:** Wiederalarmierung nach neuen Ereignissen (02.47), Mehrpersonenfreigabe, Auditspeicherung, Gruppenwechsel und Alarmzentrale-UI.

## 02.46 – Getrennte Quittierung, Stummschaltung und Rücksetzung (12.10.2026)

**Beschlossen: C – je Sensortyp konfigurierbar als Kampagnenstandard bei der Erstellung, mit bewusst markierten Ausnahmen an einzelnen Sensoren. Auch bei weiter bestehender Erkennungsbedingung kann die berechtigte Quittierung von einem vollständigen Reset getrennt werden.**

### Zustände und Aktionen

- **Gefahr erkannt:** Die tatsächliche serverseitige Erkennungsbedingung bleibt unabhängig von einer Quittierung aktiv, zum Beispiel ein zu hoher Rauchwert. Eine Quittierung darf sie nicht künstlich beseitigen.
- **Quittiert:** Berechtigte Personen oder explizit freigegebene Automationen können eine Meldung als zur Kenntnis genommen markieren. Die Anzeige einer bestehenden Gefahr bleibt erhalten.
- **Stummgeschaltet:** Der akustische oder ein sonstiger Benachrichtigungskanal kann entsprechend der Regel abgeschaltet werden, ohne notwendigerweise das Gefahren- oder das gespeicherte Alarmsignal zu beseitigen.
- **Vollständig zurückgesetzt:** Das gespeicherte Alarmsignal wird nur bei erfüllten Rücksetzvoraussetzungen gelöscht. Mögliche Einstellungen: erst nach Entwarnung, auch bei fortbestehender Gefahr mit unverändert sichtbarem Gefahrenstatus, oder nach einer zusätzlichen freigegebenen Bedingung. Der tatsächliche Sensoreingang bleibt unbeeinflusst.
- **Neue Auslösung:** Bei bestehender Gefahr darf ein Reset nicht unkontrolliert Ereignisschleifen verursachen. Welche neuen oder verstärkten Vorfälle eine quittierte oder stumme Meldung erneut aktivieren, folgt in 02.47.

### Globale Regeln, Rechte und Diagnose

- **Kampagnenerstellung:** Passende Quittierungs-, Stummschalt- und Rücksetzregeln je Sensorfamilie festlegen. Eine Sensorinstanz darf ein eigenes, ausdrücklich markiertes Profil erhalten. Globale Änderungen folgen Vorschau und Ausnahmeschutz gemäß 02.25.
- **Berechtigung:** Quittieren, Stummschalten und Reset sind separate, serverseitig autorisierte Handlungen über die erlaubten Spielleiter-, Bediengerät- oder Node-Wege aus 02.45. Ein Quittierrecht gibt nicht automatisch Resetrechte.
- **Auswertung:** Rohdetektion, Quittierungsstatus, Stummstatus und gespeicherter Alarm sind getrennte Zustände und typisierte Node-Ausgänge. Serverseitige Verarbeitung und Audit dokumentieren Akteur bzw. Automationsquelle, Zeit/Runde, Grund und Vorher-/Nachherzustand.
- **Sicherheit:** Verborgene Sensorinformationen werden nicht an unberechtigte Spieler übertragen. Die Spielerfreigabe einer Zone aus 02.41 ist von Quittierungsrechten unabhängig.
- **Test:** Isolierte Tests decken anhaltende Gefahr, berechtigte Quittierung, Stummschaltung, abgelehnten Reset und Reset nach Entwarnung ab. Die laufende Kampagne bleibt unverändert.

**02.47 beschlossen:** Wiederalarmierung nach neuen Ereignissen, höheren Gefahrenstufen, erneutem Grenzwertübertritt oder Ende einer Stummschaltfrist je Sensortyp mit Kampagnenstandards und Ausnahmen konfigurierbar; Sperrfristen verhindern Alarmfluten. **Weiter offen:** Empfänger und Alarmkanäle (02.48), genaue Signalports und Fristen sowie mehrere parallele Meldungen.

## 02.47 – Wiederalarmierung nach Quittierung oder Stummschaltung (12.10.2026)

**Beschlossen: Variante C – je Sensortyp legt der Spielleiter bei Kampagnenerstellung eine globale Richtlinie fest, wann ein quittierter oder stummgeschalteter Alarm erneut eine Meldung auslöst. Einzelne Sensoren können ausdrücklich abweichende Regeln erhalten.**

### Wählbare Auslöser für erneute Alarmierung

- **Neues qualifiziertes Ereignis oder Ziel:** Wird eine neue Figur vom Bewegungsmelder bzw. der Kamera erkannt oder trifft eine weitere eigenständige Erkennung ein, kann eine Alarmmeldung erneut ausgegeben werden. „Weiterhin dasselbe Ziel im Bereich“ ist nicht automatisch ein neues Ereignis.
- **Erneute Schwellwertüberschreitung:** Fällt ein Umwelt- oder Rauchwert unter die Bedingung und überschreitet sie später erneut, kann dies als neuer Vorfall gelten. Eine reine Dauerüberschreitung erzeugt ohne ausdrücklich gewählte Wiederholungsregel keine unendlichen Re-Alarme.
- **Neue bzw. höhere Gefahrenstufe:** Erreicht eine tatsächlich vorhandene, zum Sensortyp passende Alarmgröße eine höhere konfigurierte Stufe, kann der Sensor trotz Quittierung oder Stummschaltung wieder benachrichtigen. Stufen- und Schwellenkatalog werden später ausgestaltet.
- **Ablauf einer Stummschalt-/Sperrfrist:** Nach einer festgelegten Echtzeitdauer oder passenden Spielrundenzahl darf bei weiterhin gültiger Bedingung erneut alarmiert werden. Die Zeitbasis ist ausdrücklich zu wählen; **keine automatische Umrechnung zwischen Echtzeit und Runden**.
- **Keine Wiederalarmierung bis Reset:** Ebenfalls als auswählbares Verhalten möglich, sofern vom betreffenden Sensorprofil gestattet. Die aktive Gefahr wird trotzdem weiter angezeigt und intern protokolliert.

### Kontrolle gegen Alarmfluten

- **Entprellung und Mindestabstand:** Für gleiche oder ähnliche Ereignisse können gesonderte Sperrfristen, eine minimale Wartezeit zwischen Meldungen und eine Höchstfrequenz festgelegt werden. Die konkrete Maximalzahl/Zeitspanne wird später im Detail geklärt.
- **Ereignisse deduplizieren:** Derselbe Netzevent, derselbe bloß fortbestehende boolesche Wert und ein erneuter Clientversuch dürfen nicht versehentlich als mehrere neue Sensortreffer zählen.
- **Eskalation differenzieren:** Eine höhere Gefahrenstufe darf eine bestehende Stummschaltung **nur dann** vorzeitig übergehen, wenn der gewählte Sensortyp-/Kampagnenstandard diese Eskalationsregel ausdrücklich vorsieht.
- **Gefahr bleibt unabhängig sichtbar:** Quittieren, Stummschalten, gespeicherter Alarm und tatsächlich vorhandene Detektion bleiben getrennte Zustände nach 02.46. Eine unterdrückte akustische Meldung darf eine weiterhin bestehende Gefahr nicht verfälschen.

### Globale Vorgaben, Objekt-Ausnahmen und Diagnose

- **Bei Kampagnenerstellung:** Standard je Sensortyp für Re-Alarm-Auslöser, Stummschaltfristen, Eskalation und geeignete Entprell-/Sperrintervalle. Bereits bestehende generische Ereignis-/Runden-/Echtzeitkonzepte verwenden (02.15–02.16/02.44).
- **Pro Sensor:** Eine einzelne Kamera oder ein Rauchmelder kann eine markierte Ausnahme vom Kampagnenprofil erhalten. Spätere globale Änderungen mit Vorschau und Schutz bisheriger Ausnahmen entsprechend 02.25.
- **Serverautorität:** Der Server wertet qualifizierte neue Events, aktuelle Gefahrenstufen, Zeitgeber und eindeutige Ereigniskennungen konsistent aus. Wiederholungs- und Konfliktschutz (02.13/02.35) bleiben verbindlich.
- **Node-Ports und Debugger:** Roh-Erkennung, quittierter/stummer Zustand, Re-Alarm-Impuls, Grund der Eskalation und ggf. aktive Sperrfrist sind im berechtigten Signalprotokoll unterscheidbar. Ein nicht alarmierendes Ereignis kann trotzdem als erfasst bzw. unterdrückt diagnostiziert werden.
- **Isolierte Tests:** Ein zweites Ziel, durchgehender Rauchwert, Absinken/erneuter Anstieg, Stufenverschärfung, Ablaufen einer Frist sowie zurückgewiesene Wiederholungsimpulse sind reproduzierbar testbar, ohne echte Sensoren oder Alarmkanäle anzustoßen.
- **Sicherheit:** Die Entscheidung regelt, **ob** erneut alarmiert wird, nicht automatisch **an wen** oder wie. Empfänger- und Kommunikationsberechtigungen werden in 02.48 festgelegt; geheime Entitäten, Sensoren und Zonen dürfen nicht unberechtigt offengelegt werden.

**02.48 beschlossen:** Alarmweiterleitung erfolgt nicht direkt am Sensor, sondern über eine eigene Alarm-Node mit typisiertem Alarm-Eingang, Geltungsbereich (Region/Szene/Kampagne) und Zielklassen-/Fraktions-/Tagfiltern (z. B. Tiere, Gegner, Freunde, alle); Geräuschsensoren sind weitere Sensortypen. **Weiter offen:** Sound-Ereignisquellen und akustische Erkennung (02.49), Ausgabetypen im Detail, Alarmstufen sowie Pausierungs-/Neustartverhalten. Globale Einstellungsführung und vollständig abschaltbare Featurebereiche werden erst nach Abschluss sämtlicher Featurebereiche geplant.

## 02.48 – Alarm-Node als eigenständiger Ausgang und Geräuschsensoren (12.10.2026)

**Beschlossen: Variante C mit ausdrücklicher Korrektur des Node-Modells. Ein Sensor erzeugt einen typisierten Ausgang; eine separate, frei verkabelbare Alarm-Node hat einen passenden Alarm-Eingang und entscheidet über Wirkung, Empfänger und räumlichen Geltungsbereich. Empfängerlisten werden nicht fest in den Sensor eingebaut.**

### 1. Entkoppelte Alarm-Node

- **Datenfluss:** Kamera-, Präsenz-, Bewegungs-, Rauch-, Geräusch- oder anderer Sensor -> eigener Node-Ausgang -> geeigneter Alarm-Eingangsport der Alarm-Node. Beliebige weitere gültige Node-Quellen (Falle, NPC, Quest, SL-Auslöser, Timer, Regel) können ebenfalls einen Alarm auslösen, sofern ihre Porttypen passen.
- **Eigenes Objekt im Node-Graphen:** Die Alarm-Node hat eine stabile ID, benennbare Instanz und einen typisierten Alarm-Eingang für kompatible Ereignisse/Zustände. Konkrete Detailports und Regeln für dauerhafte versus impulsartige Alarme werden gesondert spezifiziert; keine unkontrollierte Typumwandlung.
- **Eine Quelle, mehrere Wirkungen:** Ein Sensor-Ausgang lässt sich mit mehreren kompatiblen Reaktions-Nodes verbinden. **Konkretes Nutzerbeispiel:** Bewegungsmelder erkennt Bewegung -> Licht-Node schaltet Licht ein, Alarm-Node löst eine passende lokale/szenenweite/kampagnenweite Alarmwirkung aus, Meldungs-Node sendet eine berechtigte Nachricht und Tür-Node öffnet, schließt oder verriegelt eine Tür entsprechend ihren eigenen Berechtigungs- und Zustandsregeln. Diese Reaktionen sind **frei kombinierbare Node-Verbindungen, nicht fest in den Bewegungsmelder eingebaut**. Eine Quelle kann mehrere Alarm-/Aktion-Nodes ansprechen und mehrere berechtigte Quellen können dieselbe Reaktion auslösen. Wiederverwendbar für andere Sensoren, Schalter, Fallen und Ereignis-Nodes.
- **Räumlicher Geltungsbereich pro Alarm-Node:** Der Spielleiter kann festlegen, ob die Alarmwirkung **regional/lokal** in einer definierten Kartenregion oder Reichweite, **szenenweit** oder **kampagnenweit/global** gelten soll. Ob ein Effekt räumlich hörbar, als Ereignis zugestellt oder als Nachricht sichtbar ist, bleibt zusätzlich vom Ausgabetyp und Berechtigungen abhängig. Regionen dürfen die Zonen-/Szenenmodelle aus 02.41 wiederverwenden, ohne Sensorzone und Alarmwirkungszone gleichzusetzen.
- **Wer wird alarmiert bzw. soll reagieren:** Zielgruppen über **alle, Freunde/Verbündete, Gegner/Feinde, Tiere/Kreaturen, NPCs, Spielerfiguren**, geeignete Fraktionen oder **frei kombinierbare Tags** und gültige Bedingungen eingrenzen. Bei Freunden/Gegnern braucht der Graph einen ausdrücklich gewählten Bezugsakteur, eine Fraktion oder eine Kampagnenbeziehungsregel; die Kategorien sind nicht automatisch objektiv.
- **Alarmkanäle/Aktionen:** Je nach Alarm-Node unter anderem hörbares In-Game-Geräusch, Hinweis/Meldung für berechtigte Nutzer, Alarmterminal-Anzeige, Statusänderung an Figuren/NPCs oder weitere Node-Ausgänge. **Eine Figur oder ein Tier als Ziel** bedeutet nicht automatisch einen Browser-Popup-Empfänger; passende Spielwelt-/NPC-Reaktionen laufen über die verfügbaren Regeln und Node-Anschlüsse.
- **Sicht-/Berechtigungsschutz:** Der Server löst den Alarm-Node autoritativ aus, prüft die berechtigten Empfänger und gibt keine geheimen Sensordaten, Positionen, Ziele oder Grapheninhalte an unberechtigte Clients. Die räumliche Wirkung einer Sirene und die Datenberechtigung für eine Nachricht sind unterschiedliche Prüfungen.
- **Kombinationen:** Region/Szene/global und Zielgruppen/Tags werden miteinander verknüpft; beispielsweise **nur Gegner mit Tag 'Wache' in dieser Szene** oder **alle Tiere in einer lokalen Region**. Das Verhalten muss im Live-Debugger mit tatsächlich alarmierten/nicht alarmierten Zielen nachvollziehbar und in isolierten Node-Tests prüfbar sein.

### 2. Sound-/Geräuschsensoren als weiterer Sensortyp

- **Vorgemerkt als eigener, platzierbarer Sensortyp:** Geräuschsensor bzw. akustischer Sensor mit eigenem Objektnamen, geeignetem Erfassungsbereich, typisierten Ein-/Ausgangsports und der Möglichkeit, erkannte Geräusche als Event bzw. Zustand an beliebige Node-Schaltungen weiterzugeben.
- **Erkennung von Spielweltgeräuschen:** Geräuschereignisse aus einer **modellierten Spielquelle** oder ausdrücklich erzeugte Regel-/SL-/Node-Ereignisse erfassen; je nach späterer Konfiguration z. B. Schritte, Gespräch/Lärm, Schüsse, Alarmtöne, Kreaturengeräusche oder Maschinen. Die Erkennungsquelle, Lautstärke/Intensität, Art/Tags, Dämpfung und Zeitpunkt werden gesondert in 02.49 entschieden.
- **Quelle und Output trennen:** Geräuschsensor erkennt ein Geräusch; eine Alarm-Node erzeugt gegebenenfalls eine Reaktion/eine Sirene. Ein Audioausgang kann wiederum ein Spielweltgeräusch sein, wenn dies durch spätere Regeln bewusst zugelassen wird; Schleifenschutz aus 02.13 bleibt verbindlich.
- **Keine pauschale Mikrofonfunktion:** Keine automatische Erfassung realer Mikrofone oder Gesprächsaudios nötig oder beschlossen. Eine echte Mikrofon-/Voice-Integration wäre ein separates Feature mit Datenschutz und Einwilligungsanforderungen.
- **Standards und Ausnahmen als Produktprinzip:** Verfügbare Sensorarten, Vorlagen und sinnvolle Vorgabewerte je Kampagne/Setting unterstützen; individuelle Objektausnahmen bleiben möglich. Das genaue Einstellungs- und Modul-UX folgt jedoch ausdrücklich erst nach kompletter Featureplanung.

### 3. Übergreifender Workshop-Beschluss zur Kampagnenerstellung

**Neue verbindliche Prozessvorgabe des Nutzers:** Erst wenn alle Featurebereiche vollständig besprochen sind, entscheiden wir, **wie der Kampagnen-Erstellungsassistent durch die globalen Einstellungen führt** und **welche Funktionsbereiche auf Kampagnenebene vollständig deaktivierbar** sein sollen. Bis dahin lediglich die pro Feature gewünschten Defaults/Overrides als Anforderungen sammeln. **Noch keine endgültige Menüstruktur, Seitenreihenfolge, Pflichtfelder, Modulabschaltungen oder Implementierung festlegen.** Das gilt nicht nur für Sensoren, sondern für sämtliche bisher beschriebenen globalen Kampagnenoptionen.

**02.49 beschlossen:** Geräuschereignisse aus Spielaktionen, Objekten, Geräusch-/Alarm-Nodes und SL-/Szenenereignissen kombinierbar; ihre Visualisierung als Schallwellen/-bereiche ist global regelbar mit Ausnahmen pro Geräuschquelle oder Kartenbereich und zeit-/ereignisabhängigem Tutorialmodus. **Weiter offen:** Klang-/Raumausbreitung und Dämpfung (02.50), Freund-/Feindbeziehungen, Tagfilter-UX, konkrete Portschemata, Offline-Zustellung. Aufbau des globalen Kampagnenassistenten und komplett abschaltbare Featurebereiche bleiben bis nach allen Features zurückgestellt.

## 02.49 – Kombinierbare Geräuschquellen und zeitweise sichtbarer Schall (12.10.2026)

**Beschlossen: Variante C mit verbindlicher Ergänzung – Geräusche können aus Spielaktionen, Gegenständen, passenden Nodes oder manuell durch die Spielleitung entstehen. Ihre Darstellung als Schallbereich/Schallwelle ist global einstellbar, mit individuellen Ausnahmen pro Geräuschquelle und räumlichen Ausnahmen für Kartenbereiche. Eine sichtbare Tutorialphase kann später automatisch oder gezielt beendet werden.**

### Geräuschereignisse als Teil der Spielwelt

- **Figurenaktionen:** Regel- und settingabhängige Aktionen können passende Geräuschereignisse erzeugen, zum Beispiel Gehen/Laufen, Sprechen, Schreien, Schießen, Angriffe oder der Gebrauch lauter Gegenstände. Welche Aktionen tatsächlich Geräusche erzeugen, ist regelprofilabhängig; ein Geräusch ist nicht automatisch bloß das Abspielen einer Audiodatei.
- **Interaktive Weltobjekte:** Türen, Maschinen, Fahrzeuge, Fallen, Kreaturen, Alarmsirenen oder andere Objektaktionen dürfen bei geeigneter Konfiguration akustische Ereignisse erzeugen.
- **Sound-/Alarm- und andere Nodes:** Entsprechend typisierte und autorisierte Node-Ausgänge können Geräuschereignisse in der Spielwelt auslösen. Das Sound-Ereignis ist ein **eigenes fachliches Ereignis**, das wiederum mit Geräuschsensoren und beliebigen geeigneten Node-Reaktionen verbunden werden kann.
- **SL-/Szenenereignisse:** Der Spielleiter darf Geräusche bewusst platzieren, simulieren oder mittels vorbereitetem Story-/Szenenereignis auslösen – auch ohne zugehöriges Spielfiguren-Geräusch.
- **Geräuschattribute:** Sinnvolle, nicht zwingend immer befüllte Werte sind Ereignis-ID, Szene/Stockwerk, Quellobjekt oder Quellposition (ggf. verdeckt), Geräuschart, Tags, Intensität bzw. Lautstärkestufe, Zeitbasis/Zeitpunkt, gegebenenfalls Dauer und passende Regel-/Berechtigungsmetadaten. Konkrete Skalen erst später definieren.
- **Sound-Sensor-Node:** Nimmt nur zu seinen Fähigkeiten passende Geräusch-/Akustikereignisse wahr, wendet vereinbarte Sensorfilter und den tatsächlich berechneten Erfassungsbereich an und gibt seine typisierten Zustände/Ereignisimpulse an den Graphen aus. Eine Geräusch-Quelle darf parallel Licht, Alarm, Nachricht oder Tür steuern (02.48); keine fest kodierte Reaktion im Sensor.
- **Keine Mikrofonpflicht:** Das System wertet zunächst **virtuelle Spielwelt-Ereignisse**, nicht reale Mikrofonaufnahmen oder den Voicechat, aus. Solche externen Audioquellen wären ein später bewusst zu diskutierender eigenständiger Anwendungsfall.
- **Schleifenschutz und Serverautorität:** Von Alarm-/Sound-Nodes erzeugte Geräusche dürfen weitere Sensoren auslösen, sofern die Konfiguration das zulässt. Dabei gelten typisierte Ports, serverseitige Ereignis-IDs, Deduplikation und Schutz vor sich endlos selbst verstärkenden Schaltungsketten.

### Globale und lokale Sichtbarkeit von Schall – ausdrücklicher Zusatz

- **Globale Voreinstellung:** Die Kampagne besitzt eine Regel, ob und für wen **Schallwellen, Geräuschradien, Hör-/Ausbreitungsbereiche oder Geräuschmarkierungen auf der Karte grafisch sichtbar** sein sollen. Die SL-Debug-/Editoransicht kann die Visualisierung unabhängig von der Spielerfreigabe zur Kontrolle einblenden.
- **Ausnahme pro Quelle / Einzelereignis:** Eine einzelne Geräuschquelle bzw. ein dafür geeignetes Sound-Objekt kann eine eigene Sichtbarkeitsregel erhalten. Beispielsweise wird nur die Welle eines Tutorialsignals angezeigt, obwohl die normale Kampagnendarstellung bereits deaktiviert ist.
- **Räumliche Ausnahmen:** Auf Karten-/Szenenregionen können Regeln gelegt werden, die dort **Schall visualisieren oder verbergen**, unabhängig von der sonst geltenden Kampagnenvorgabe: beispielsweise Übungsraum sichtbar, Schleichpassage unsichtbar. Eine solche Bereichsregel ist nicht identisch mit dem tatsächlichen Hörbereich; bei überlappenden Bereichen muss die spätere Auswertung eindeutig sein.
- **Zeit- und Ereigniswechsel:** Sichtbarkeitsregeln dürfen über **Spielleiteraktion, Start/Ende einer Szene bzw. eines Tutorials, passende Node-/Questereignisse oder eine ausdrücklich konfigurierte Echtzeit-/Rundendauer** wechseln. Beispiel: **Zu Beginn sehen Spieler die ausgehenden Schallwellen zum Lernen; nach dem Tutorial werden sie unsichtbar**, während Geräusche weiterhin dieselben Sensoren und NPCs beeinflussen.
- **Nur Darstellung, keine Änderung der Weltlogik:** Das Ein-/Ausblenden darf **niemals die tatsächliche Geräuscherzeugung, Hörbarkeit, Lautstärke, Schallausbreitung, Sensor-Erkennung oder Node-Auslösung ändern**. Grafisch unsichtbarer Schall kann weiterhin gehört bzw. von einem Sensor erkannt werden.
- **Spielerberechtigungen:** Eine Schallvisualisierung darf nicht heimlich Quellort, verborgene Figur, geheimes Objekt oder nicht freigegebene Szene offenlegen. Sichtbarkeit von Quellmarkierung, grafischer Ausbreitung und tatsächlicher Berechtigung, ein Geräusch wahrzunehmen, sind getrennt zu prüfen; Daten unberechtigter Quellen dürfen nicht einfach als versteckte Clientgrafik übertragen werden.
- **Vererbung und Änderungen:** Globale Regel, ausdrücklich gesetzte Einzel-Ausnahmen und Regionsregeln sind in ihrer **wirksamen Herkunft** im Spielleiter-Editor erkennbar. Bestehende Objektausnahmen respektieren die Bestands-/Vorschaubeschlüsse 02.24–02.25. Genaue Priorität bei mehreren gleichzeitig wirkenden Bereichs-/Objektregeln sowie deren UI-Gestaltung wird später abgestimmt.

### Beispiele, Tests und Abgrenzung

- Ein Schuss erzeugt ein Geräusch mit Art und Intensität. Ein Sound-Sensor registriert es und startet über die Verkabelung eine Alarm-Node; ob die Spieler die **grafische Schallwelle** sehen, entscheidet ausschließlich die Sichtbarkeitsrichtlinie.
- Im **Tutorial-Bereich** werden Schritte durch kurz sichtbare Schallringe erklärt. Nach einer SL-Aktion oder einem Tutorial-Abschlussereignis verschwindet die Anzeige. Geräuscherkennung und Alarmketten bleiben unverändert.
- Während ein global unsichtbares Geräusch in einem **besonderen Kartenbereich** sichtbar dargestellt wird, können andere Geräusche außerhalb weiterhin unsichtbar bleiben.
- Der isolierte Debugger prüft Geräuschquelle/-Typ/Tag/Intensität, Sensor-Treffer und getrennt davon, welche Visualisierungsdaten ein berechtigter Spieler erhalten dürfte. Simulierte Geräusche lösen keine echten Alarme aus.

**Noch offen:** tatsächliche Schallreichweite, Hindernisdämpfung, Schallausbreitung über Räume und Ebenen (02.50), Geräuschintensität und -dauer, NPC-Hörlogik, Überschneidung/Priorität von Sichtbarkeitsregeln, Audioausgabe versus abstraktes Event und die spätere zentrale Menü-/Modulgestaltung. Die Entscheidung zum Kampagnenassistenten bleibt aus 02.48 unverändert: **globaler Einstellungsablauf und völlig abschaltbare Featurebereiche erst nach Abschluss aller Featurethemen.**

## 02.50 – Konfigurierbare Schallausbreitung und Dämpfung (12.10.2026)

**Verbindlich beschlossen: Variante C.** Virtuelle Geräusche breiten sich nach einem konfigurierbaren Spielweltmodell aus. **Entfernung, Wand-/Türmaterial, Öffnungszustand, Durchgänge, geeignete Stockwerksverbindungen und bewusst gesetzte Quellen-/Raumausnahmen** können die wahrnehmbare Intensität beeinflussen. **Ob eine Schallwelle grafisch gezeigt wird (02.49), bleibt streng unabhängig davon.** Die fachliche Anforderung ist beschlossen; die folgenden Daten- und Implementierungsschritte sind Entwurf, keine fertige Software.

### Fachverhalten und Konfigurationsgrenzen

- **Ereignis statt bloßer Audiodatei:** Eine gültige Aktion, ein Objekt, eine Sound-/Alarm-Node oder die Spielleitung erzeugt ein kanonisches akustisches Ereignis nach 02.49. Ein zusätzlich abgespielter Soundeffekt kann das begleiten, ist aber nicht die Berechnungsgrundlage.
- **Reichweite und Intensitätsabnahme:** Die Hörbarkeit nimmt grundsätzlich abhängig von Entfernung und Geräusch-/Kampagnenprofil ab. Keine universelle feste Distanz oder konkrete Dezibelgleichung beschlossen; besondere Settings (Magie, Funk, Schalldämpfung) dürfen geeignete ausdrücklich konfigurierte Regeln nutzen.
- **Material und Hindernisse:** Wände, Türen, Fenster und andere geeignete Bauteile tragen eigene akustische Durchlässigkeit/Dämpfung, unabhängig von ihren bisherigen Eigenschaften für Licht, Sicht und Bewegung (02.9). Eine geöffnete Tür kann andere Übertragung erlauben als dieselbe geschlossene Tür; Material- und Türzustandswechsel wirken serverseitig.
- **Räume, Umwege und Stockwerke:** Öffnungen und ausdrücklich modellierte Übergänge können akustisch verbundene Regionen bzw. Stockwerke koppeln. Wo kein Übergang konfiguriert ist, wird keine automatische Weiterleitung zwischen Szenen/Stockwerken behauptet. Die Frage, ob Schall um Ecken, durch alternative Wege oder durch große Flächen mit einem vereinfachten Modell berechnet wird, bleibt eine technische Modellierungsentscheidung.
- **Globale Standards mit Ausnahmen:** Pro Kampagne sinnvolle Akustikprofile vorsehen; bei Bedarf abweichende Profile für Szenen/Geräuschklassen, Materialien/Objekte, konkrete Geräuschquellen oder Raum-/Kartenbereiche. Wirksame Herkunft und explizite Ausnahmen sind im SL-Editor erkennbar; Änderungen der Standards beachten Vorschau, vorhandene Objekte und geschützte Ausnahmen aus 02.25. Die genaue Rangfolge überlappender Ausnahmen wird später verbindlich festgelegt.
- **Empfänger getrennt prüfen:** Figuren, NPCs und Sound-Sensoren nutzen den serverseitig ermittelten ankommenden Geräuschwert und ihre eigenen, später definierten Hör-/Erkennungsschwellen, Kategorien, Zustände und Filter. Ein registriertes Geräusch bedeutet nicht automatisch, dass ein NPC reagiert oder dass eine Alarm-Node auslöst; das bestimmen eigene Regeln bzw. Node-Verbindungen aus 02.40/02.48.
- **Dynamischer Zustand:** Änderungen an Position, Türen, Hindernissen, Raumprofilen oder aktivem Geräusch lösen eine konsistente Neubewertung betroffener Ereignisse bzw. Hörer aus, soweit die jeweilige Ereignisdauer das noch erfordert. Event-IDs, Deduplikation und Schleifenschutz aus 02.13/02.49 bleiben Pflicht.
- **Sichtbarkeit, Fog und Geheimnisse:** Akustische Wahrnehmung, berechtigte Informationen über ein Geräusch und grafische Anzeige sind drei getrennte Entscheidungen. Ein Spieler darf ein verborgenes Geräusch hören, ohne die genaue geheime Position zu erhalten. Verborgene Quellen-/Sensor-/Zonendaten dürfen nicht ungefiltert zum Client gesendet werden.

### Technischer Realisierungsentwurf (noch keine API-Festlegung)

1. **Kanonische Daten:** Ein `SoundEvent` referenziert Quelle, Szene/Stockwerk, Position bzw. gekennzeichnete verdeckte Quelle, Geräuschtyp/Tags und später gewählte Intensitäts-/Zeitwerte. `AcousticProfile` beschreibt gültige Dämpfungsregeln; `AcousticObstacle` akustische Material-/Zustandseigenschaften; `AcousticRegion` Raumprofile/Ausnahmen und `AcousticLink` optionale akustische Übergänge (Bezeichnungen exemplarisch, nicht beschlossenes Schema).
2. **Serverseitiger Ausbreitungsdienst:** Eine eigene deterministische fachliche Komponente ermittelt pro Ereignis und Ziel die effektiv ankommende Geräuschwirkung. Einfachen Distanz- und Materialansatz zuerst implementierbar machen; zusätzliche Wege/Stockwerksverbindungen auf demselben Regelmodell aufbauen. Keine vollständig realistische Wellenphysik und keine pauschale Durchdringung behaupten.
3. **Wahrnehmungsprüfung:** Ergebnis mit den zum Hörer-/Sensorprofil passenden, ausdrücklich konfigurierten Kriterien vergleichen. Daraus nur zulässige typisierte Wahrnehmungs-/Sensorevents ableiten; Sensoren können danach Licht-, Tür-, Alarm- oder Meldungs-Nodes ansteuern, nicht im Akustikdienst selbst.
4. **Änderungsereignisse und Laufzeit:** Betroffene Verbindungen nach Türen-, Objekt-, Positions- oder Profiländerung gezielt ungültig machen und neu auswerten; räumliche Indizes/Caches sind mögliche Optimierung. Begrenzungen für Zahl aktiver Geräusche, Hörer, Ausbreitungsschritte und Node-Kaskaden vorsehen; genaue Limits und Echtzeit-/Rundensemantik bleiben offen.
5. **Ansicht und Diagnose:** Die SL-Debugansicht darf Quellen, wirksames Profil, relevante Hindernisse, Dämpfungspfad, Hör-/Nicht-Hörgründe und resultierende Node-Ereignisse zeigen. Die Spieleransicht nutzt die separate Berechtigungs- und Visualisierungsrichtlinie 02.49. Simulationen und gespeicherte Soll-Ist-Tests aus 02.31–02.34 dürfen keine realen Alarme auslösen.

### Prüffälle zur späteren Abnahme

- Gleiche Quelle und gleiche Entfernung, aber offene bzw. geschlossene Tür: das konfigurierte Akustikprofil führt nachvollziehbar zu unterschiedlichen Hörwerten.
- Materialwechsel oder individuelle Raum-/Quellenausnahme ändert den Ausbreitungswert, ohne Licht-, Sicht- oder Bewegungsblockade unbeabsichtigt umzuschreiben.
- Ein ausdrücklich modellierter Übergang kann Geräusche zwischen verbundenen Stockwerken weitergeben; eine nicht modellierte Verbindung führt nicht heimlich zu einer Übertragung.
- Ein Sound-Sensor reagiert nur bei passender akustischer Erfassung und seinen eigenen Filtern; danach funktionieren separate Alarm-/Licht-/Tür-Nodes bei gültiger Verkabelung.
- Sichtbare Tutorial-Schallwelle an/aus: identische serverseitige Hör- und Sensorergebnisse.
- Spieler hören zulässige Geräusche, ohne geheime Quellkoordinaten, verdeckte Objektinformationen oder SL-Debugwerte zu erhalten.
- Doppelte Geräuschereignisse oder verkettete Sirenen verursachen keine unendliche oder mehrfache unberechtigte Alarmserie.

**Noch ausdrücklich offen:** Intensitätsstufen, exakte Dämpfungszahlen, Geräuschdauer und Abklingen, aktive Wiederholungen, hörbezogene Fähigkeiten/Schwellen, NPC-Reaktionen, Detailmodelle für Ecken/Umwege/Umgebung, Vorrang überlappender Overrides sowie tatsächliche UI des Kampagnenassistenten. **Die globalen Einstellungswege und komplett abschaltbaren Featurebereiche werden wie in 02.48 beschlossen erst nach Abschluss aller Featurethemen geplant.**

## 02.51 – Kombinierte Lautstärke und Geräuschdauer; Akustikschalter und SL-Schallhinweise (12.10.2026)

**Beschlossen: Variante C mit zwei ausdrücklichen Ergänzungen des Projektinhabers.** Geräusche erhalten **verständliche voreingestellte Lautstärkestufen und Zeitverläufe** mit optional präzisen, individuell konfigurierbaren Intensitäts-, Dauer-, Abkling- und Wiederholungswerten. **Die Akustik als Spielweltfunktion ist bei Kampagnenerstellung an-/abschaltbar und konfigurierbar.** Zusätzlich darf der **Spielleiter an beliebigen vorgesehenen Positionen in einer Szene sichtbare Akustiksignale/Hörhinweise für Spieler auslösen**, damit Spieler z. B. Schritte oder ein Geräusch hinter einer verschlossenen Tür bemerken und **selbst vermuten**, ob sich dort ein Gegner befindet. Diese Markierung enthüllt **nicht automatisch** ein verborgenes NPC-Token oder seine Identität. Es handelt sich um Anforderungen und Realisierungsentwürfe, nicht um bereits implementierte Funktionen.

### 1. Lautstärke, zeitliche Verläufe und Vererbung – C

- **Einfache Voreinstellungen:** Geeignete benannte Lautstärkestufen (etwa leise, normal, laut) und verständliche Ereignisformen wie **kurzer Impuls**, **anhaltendes Geräusch**, **wiederkehrendes Geräusch** oder **ausklingender Klang** bereitstellen. Die konkrete Zahl der Stufen und die Skalenwerte bleiben frei für spätere Spezifikation; diese Beispiele sind keine verbindlichen Normwerte.
- **Erweiterte individuelle Werte:** Bei Bedarf darf der Spielleiter pro Geräuschart, Quelle, Sound-/Alarm-Node oder konkretem Ereignis präzise Intensität, Dauer, Anstieg, Abklingen, Wiederholungsabstand und Anzahl/Endbedingung angeben, soweit zum Typ passend. Damit sind sowohl Schritte als kurzer Impuls als auch ein Maschinenbrummen oder periodisches Klopfen möglich.
- **Kampagnenstandard und Abweichungen:** Geräuschklassen-/Quelltypen übernehmen passende Standardwerte aus dem Kampagnenprofil. Einzelquellen oder geeignete Bereichs-/Szenenprofile können bewusste, gekennzeichnete Ausnahmen enthalten; Vererbungsursprung, Standardänderung, Vorschau und Bestands-/Ausnahmeschutz aus 02.25 berücksichtigen. Keine ungeprüfte Übernahme inkompatibler Parameter.
- **Echtzeit und Spielrunden:** Eine Geräuschdauer oder Wiederholung kann je nach später zulässigem Profil auf Echtzeit oder Runden basieren, **ohne stillschweigende automatische Umrechnung**. Pausierung, Wiederaufnahme, Reconnect, Offline-Szenen sowie Persistenz aktiver/terminierter akustischer Ereignisse werden für die technische Detailplanung gesondert entschieden.
- **Ausbreitung getrennt:** Das auf 02.50 beruhende Dämpfungs-/Hörmodell nimmt die gültige Intensität und ihren zeitlichen Verlauf als Eingabe. Die Sensorempfindlichkeit/Hörschwelle und eine etwaige NPC-Reaktion werden weiterhin durch eigene Regeln bestimmt; visuelle Darstellung und eventuell abgespielte Audiodateien dürfen das serververbindliche Ergebnis nicht ersetzen.

### 2. Akustik bei der Kampagnenerstellung an/aus und konfigurierbar – ausdrücklicher Zusatz

- **Verbindlicher Funktionswunsch:** Bei der **Erstellung einer Kampagne** kann der Spielleiter entscheiden, ob Akustik als modellierte Spielweltfunktion **aktiv**, **deaktiviert** oder **mit eigenen Profilen/Werten konfiguriert** sein soll. Die genaue Ausgestaltung eines simplen Schalters gegenüber Profilstufen/Expertenoptionen, Standardvorauswahl und der genauen Einrichtungsoberfläche wird später geplant.
- **Einfacher und konfigurierter Einsatz:** Aktivierte Akustik erlaubt die vereinbarten Ereignisse, Dämpfungsregeln, Hör-/Sensorprüfung und manuelle Spielleiterhinweise; detaillierte Profilwerte und Ausnahmen bleiben optional und settingabhängig.
- **Wirkung von „aus“ technisch sauber definieren:** Ein abgeschaltetes akustisches **Simulationssystem** soll **keine automatischen** Hörbarkeits-/Dämpfungsberechnungen und **keine dadurch ausgelösten akustischen Sensorereignisse** erzeugen. Andere gültige Node-Eingänge und Licht-/Tür-/Alarmfunktionen dürfen dadurch nicht pauschal ausfallen. Ob ein *rein manuell* veröffentlichter, erzählerischer Geräuschhinweis auch ohne aktivierte Simulation verfügbar bleibt, ist eine **eigene noch offene Detailfrage**; kein stillschweigendes Durchbrechen des Schalters.
- **Unabhängig von Schallwellen-Sichtbarkeit (02.49):** **Akustik an/aus** ist nicht mit **grafische Schallwellen sichtbar/unsichtbar** gleichzusetzen. Ein unsichtbares akustisches Ereignis kann weiterhin wirken, wenn das System aktiv ist; ein sichtbares SL-Hinweissymbol muss nicht die reale Schallwellengeometrie offenlegen.
- **Vereinbarkeit mit der Workshop-Reihenfolge (02.48):** Mit diesem expliziten Nutzerwunsch ist der **fachliche Akustik-An/Aus-Schalter bei der Kampagnenerstellung beschlossen**, nicht aber das gesamte Assistenten-UX. **Welche anderen Featurebereiche sich vollständig abschalten lassen und wie alle Einstellungen geführt/angeordnet werden**, bleibt weiterhin bis zum Abschluss aller Featurethemen offen. Spätere Änderungen an aktivierter Akustik müssen bestehende Objekte, laufende Ereignisse und definierte Ausnahmen vorhersehbar behandeln; exakte Umschaltregeln später spezifizieren.

### 3. Spielleiter platziert sichtbare akustische Hinweise in der Szene – ausdrücklicher Zusatz

- **Manuelle Positionierung:** Der Spielleiter kann eine geeignete Karten-/Szenenposition auswählen (auch hinter einer Tür oder in einem nicht freigegebenen Raum) und dort einen **Akustikhinweis** mit beispielsweise „Schritte“, „Klopfen“, „Kratzen“, „Stimmen“ oder eigener Beschreibung auslösen. Die Quelle muss **kein echtes sichtbares NPC-Token** besitzen und darf bewusst nur ein Storyhinweis sein.
- **Spieler sollen etwas sehen:** Der Spielleiter kann die akustische Wahrnehmung durch ein **sichtbares, temporäres Geräuschsymbol, einen Hinweisbereich oder eine andere Freigabe-Markierung** auf der Spielerkarte vermitteln. Der eigentliche Klang ist optional; ein solches Signal ist nicht bloß ein im SL-Editor unsichtbar gespeicherter Geräuschwert. Die drei Ortsgenauigkeitsmodi und ihre individuellen Ausnahmen sind in 02.52 festgelegt; die konkrete Icon-/Animationsgestaltung bleibt offen.
- **Spielwelt-Ereignis vs. Präsentationshinweis:** Ein *wirkliches* akustisches SoundEvent (mit Ausbreitung und gegebenenfalls Sensor-/Node-Folgeeffekten) sowie der *für Spieler freigegebene* Hinweis auf ein gehörtes Geräusch sind **unterschiedliche Datenobjekte bzw. fachliche Ebenen**. Ein manueller Hinweis kann einen validierten Schallvorgang repräsentieren oder eine gezielte, erzählerische Andeutung sein. **Keine automatische gleichzeitige Detektion oder Alarmweiterleitung nur wegen einer gezeichneten Markierung.**
- **Gezielte Empfänger:** Der Spielleiter muss den Hinweis gezielt an berechtigte Spieler oder Gruppen freigeben können, statt immer pauschal allen den Ort eines Ereignisses mitzuteilen. Die gemeinsame, individuelle oder gruppenbasierte Freigabe aus 02.7/02.49 beachten. Ob ein Hinweis von der Hörbarkeit eines Tokens oder ausdrücklich von einer SL-Freigabe abhängt, wird als Detail noch entschieden.
- **Geheime Gegner und Fog:** Die angezeigte Position eines **Geräuschhinweises** ist *nicht automatisch* die exakte interne Koordinate eines Gegners. Ein absichtlich hinter einer Tür platzierter oder ungenauer Hinweis lässt Spieler einen Gegner **vermuten**, enthüllt aber weder gegnerische Existenz/Werte/Identität noch andere verdeckte Karten- und Szeneninhalte. Fog, Spielerberechtigungen und Geheimnisfilter werden serverseitig geprüft; die **vom Spielleiter ausdrücklich freigegebene Hinweismarkierung** darf angezeigt werden, ohne den verdeckten Raum oder dessen Objekte offenzulegen.
- **Zeitablauf und Änderungen:** Sichtbare Hinweise sollen zu gültiger Dauer bzw. bewusstem SL-Auslösen und Beenden passen und nach der für sie freigegebenen Zeit/Regel wieder verschwinden können. Ein Hinweis kann auch von einem Node-/Quest-/Szenenereignis kommen, soweit später ausdrücklich vorgesehen und typisiert. Keine endlosen Audio-/Alarm-Schleifen.
- **SL-Vorschau und Tests:** In der Spielersicht-Vorschau kann der SL kontrollieren, ob die Spieler wirklich *nur* das beabsichtigte Geräuschzeichen erkennen; Debugging unterscheidet Ursache, Quelle, hörberechtigtes Ziel, gezeigten Hinweis sowie verborgen bleibende Objekte. Testfälle müssen ohne laufende Kampagnenänderungen simuliert werden.

### 4. Beispiel und spätere Abnahme

**Beispiel „Schritte hinter der Tür“:** Ein Spieler steht vor einer geschlossenen Tür. Der Spielleiter platziert in einem nicht aufgedeckten Bereich hinter der Tür einen akustischen Hinweis „schwere Schritte“ und gibt ihn für den Spieler bzw. die Gruppe frei. In der Spieleransicht erscheint ein erkennbares Geräuschsymbol oder ein entsprechend approximierter Hinweis. Der Spieler darf auf einen Feind schließen, aber die Software zeigt **nicht** automatisch einen unsichtbaren Gegner oder den geheimen Raum. Ob zusätzlich ein echtes ausbreitungswirksames SoundEvent die Hörbarkeit und Sensoren prüft, hängt von der aktivierten Akustik und der gewählten Erzeugungsart ab.

**Tests:** (1) Lautstärke-Preset erben, dann gezielt pro Quelle überschreiben; (2) kurz, dauerhaft, abklingend und wiederholt in realer Zeit/Runden unterscheidbar; (3) bei ausgeschalteter Simulation keine automatischen akustischen Sensor-/Node-Auslösungen; (4) sichtbarer SL-Hinweis auf der Spielerkarte ohne Preisgabe des verborgenen Gegners; (5) nur freigegebene Empfänger erhalten den Hinweis; (6) Markierung erzeugt nicht ungefragt ein weiteres Spielweltgeräusch; (7) Änderungen und Wiederverbindungen führen nicht zu doppelten Geräuschimpulsen.

**Noch offen:** Konkrete Skala und Defaultwerte, Zeitpunkt-/Rundensemantik und Pausenverhalten, Konflikte überlappender Akustikregeln, ob rein manuelle Hinweise bei deaktivierter Simulation separat aktivierbar sind, Wiedergabe von Sounds, Hörschwellen sowie die genaue visuelle Gestaltung der Hinweissymbole (die drei Ortsgenauigkeitsmodi wurden in 02.52 entschieden).

## 02.52 – Frei wählbare Ortsgenauigkeit für Akustikhinweise (12.10.2026)

**Beschlossen: Variante C.** Spielleiter dürfen bei sichtbaren Akustiksignalen/Hörhinweisen auf der Karte zwischen **exakter Punktmarkierung**, **ungefährem Bereich** und **bloßer Richtung** wählen. Die Kampagne erhält einen **globalen Standard für die Ortsgenauigkeit**; der Spielleiter kann ihn bei einem konkreten Geräuschereignis/Hinweis und **bei Bedarf für einzelne berechtigte Empfänger oder Gruppen** sichtbar und ausdrücklich überschreiben. Die tatsächliche Quelle eines SoundEvents, das hörbare Ereignis, die dargestellte Schallwelle aus 02.49 und der dem Spieler gesendete Hinweis sind fachlich **getrennt**. Es sind Produktanforderungen und technische Entwürfe, keine vorhandene Implementierung.

### Drei Darstellungsmodi – verbindlicher Funktionsumfang

- **Exakter Punkt:** Ein berechtigter Spieler sieht einen klar bezeichneten Geräuschmarker **an der vom Spielleiter für die Anzeige festgelegten Position**. Diese Anzeige-Koordinate muss nicht die interne Position eines Gegners oder der tatsächlichen Geräuschquelle sein. Die SL kann bewusst die exakte Geräuschstelle anzeigen; solche Offenlegung soll in der Spielersicht-Vorschau erkennbar sein.
- **Ungefährer Bereich:** Der Spieler sieht einen größeren gekennzeichneten **Schätzbereich**, z. B. „Geräusche kommen aus diesem Flur/Teil des Raums“. Der Bereich bezeichnet die vom SL bzw. einer späteren berechtigten Wahrnehmungsregel gewollte Unsicherheit; kein verborgener Quellpunkt wird stillschweigend übermittelt. Freihand-/Formwerkzeuge dürfen sich am Szenen-/Zonenmodell orientieren, die konkreten Formen/Standardgrößen bleiben offen.
- **Nur Richtung:** Ein berechtigter Spieler sieht eine **Richtung ohne konkrete Zielkoordinate**, etwa „nördlich von dir“ oder „von hinter der Tür“. Bei gerichteten Hinweisen braucht der Server einen wohldefinierten **Beobachter-/Figurenbezug**, falls Spieler mehrere Figuren kontrollieren. Der Pfeil oder Sektor darf keine versteckte Entfernung bzw. geheime Zielposition im Client offenlegen.
- **Eigenständige Hinweismarkierung:** Ein sichtbar freigegebener Hinweis ist nicht gleichbedeutend mit sichtbaren Schallwellen. Eine Kampagne kann die flächige Schallwellen-Darstellung aus 02.49 deaktivieren und dennoch einen bewusst durch den SL veröffentlichten Geräuschmarker anzeigen, sofern die betreffenden Freigaberegeln das erlauben. Das An-/Ausschalten der automatischen Akustik aus 02.51 bleibt eine getrennte Einstellung.

### Standards, Einzel-Ausnahmen und Empfänger

- **Kampagnenweiter Standard:** Für Akustikhinweise kann bei der Kampagnenerstellung ein **Standard-Genauigkeitsmodus** hinterlegt werden, mit geerbten Anzeigeparametern, ohne für jeden einzelnen Hinweis die Art erneut festlegen zu müssen. Die konkrete Einstellungsoberfläche wird erst nach vollständiger Featureplanung ausgearbeitet (02.48).
- **Gezielte Einzel-Ausnahmen:** Spielleiter können für eine Quelle/einen konkreten Hinweis/ein relevantes Ereignis einen abweichenden Modus samt gewünschtem Anzeigeort, Bereich oder Richtung vorsehen; Herkunft der wirksamen Einstellungen ist im Editor nachvollziehbar.
- **Empfängerspezifische Freigabe:** Abweichende Genauigkeit und ein eigener sichtbarer Orts- bzw. Richtungs-Hinweis dürfen an ausdrücklich autorisierte Spieler oder Gruppen gesendet werden. Beispiel: Die Figur an der Tür erhält „ungefähr dahinter“, eine andere Figur erkennt nur „aus dem Norden“. Die tatsächliche Hörberechtigung, SL-Freigabe und visuelle Präzision werden separat geprüft. Falls dieselbe Person mehrere Figuren/Empfängerrollen hat, muss die spätere Auswertung eindeutig sein.
- **Änderungen am Standard:** Änderungen berücksichtigen Vorschau, Übernahme in geeigneten Altbestand oder nur Neuanlagen und Schutz expliziter Ausnahmen gemäß 02.25. Bei sich überlagernden Objekt-, Regions-, Einzel- und Empfängerregeln wird eine eindeutige spätere Prioritätsauflösung spezifiziert; nicht beiläufig neue vollständige Konfliktrichtlinien festlegen.
- **Andere Einstellungen bleiben unabhängig:** Ob ein Geräusch überhaupt im Spiel entsteht, welchen physikalischen Wert es nach 02.50–02.51 beim Hörer hat und ob es einen Sensor oder eine Node auslöst, ist **nicht** von Punkt-, Bereichs- oder Richtungsgrafik abhängig.

### Umsetzungsvorschlag und Geheimnisschutz

1. **Internes Ereignis:** Das bestehende konzeptionelle `SoundEvent` führt nur serverseitig seine validierten Quell-/Ereignisdaten; bei einem SL-Storyhinweis darf dieses Event ganz fehlen. Es wird kein realer NPC oder exakter Quellort benötigt, um einen Hinweis zu veröffentlichen.
2. **Eigene Präsentation:** Für einen `SoundCue` bzw. `AcousticHint` getrennte Information über Szene, berechtigte Empfänger, Beschreibung/Typ, **Anzeigemodus** (`point`, `area`, `direction` als beispielhafte Namen), **freigegebene** Hinweisgeometrie/Beobachterbezug, Anzeigefrist, wirksame Policyherkunft und ggf. serverinterne Eventverknüpfung vorsehen. Diese Begriffe sind noch kein endgültiges API-Schema.
3. **Sichere Empfängeransicht:** Der Server berechnet pro Spieler/Gruppe eine **bereinigte Ansicht** und versendet ausschließlich die explizit veröffentlichte Markierung samt nötigen Metadaten; bei grober Zone oder Richtung erhält der Client **keine** versteckte tatsächliche Punktkoordinate, Schallquellen-ID, Gegnerdaten, Pfadgeometrie oder Fog-Inhalte. Verschiedene Empfänger können unterschiedlich genaue Hinweise zum selben Ereignis erhalten.
4. **Fog bleibt wirksam:** Ein bewusst freigegebenes Geräuschsymbol kann als Hinweis auf oder über einem noch verdeckten Bereich erscheinen; es **öffnet keine Karte**, enthüllt keine Türinnenseite und veröffentlicht keine Figur. Exakt gesetzte sichtbare Positionen sind jedoch eine bewusste Informationsfreigabe und müssen in der SL-Spielersicht-Vorschau vorab erkennbar sein.
5. **Node- und Akustiktrennung:** Das reine Anzeigen, Ausblenden, Verschieben oder Verfeinern des Hinweises darf **keine** zusätzlichen Geräuschereignisse, akustischen Sensortreffer, Alarme, Türen oder andere Node-Reaktionen auslösen. Ereignisbasierte Spielweltwirkungen erfordern einen eigenständig validierten SoundEvent-/Node-Auslöser aus 02.48–02.51. Rechte, eventuelle Fristen, IDs, Wiederverbindung und Debugprotokolle bleiben serverautoritativ.

### Abnahmetests (spätere Umsetzung)

- Bei identischem Sound-/SL-Ereignis können **exakter Punkt, grobe Fläche oder reine Richtung** angezeigt werden, ohne die akustische Ausbreitungsberechnung oder Node-Aktivierung zu verändern.
- Standard aus der Kampagne wird geerbt; eine ausdrückliche Ausnahme pro Hinweis funktioniert, ohne andere Geräuschhinweise umzuschreiben.
- Zwei berechtigte Spieler dürfen unterschiedlich genaue Hinweise zum selben Ereignis sehen; ein nicht berechtigter dritter Spieler sieht **keinen** Hinweis.
- Grobe Markierung und Richtung enthalten im übertragenen Clientzustand **keine verborgene präzise Quellkoordinate**; eine exakte, bewusst vom Spielleiter gesetzte Anzeige zeigt nur den freigegebenen Punkt.
- „Schritte hinter der Tür“ bleiben sichtbar, obwohl Raum und möglicher Gegner im Fog versteckt sind; keine automatische Token-/Raum-Enthüllung.
- Sichtbare Hinweise bleiben bei Reconnect gemäß gültiger Anzeigefrist konsistent, ohne doppelte Node- oder Schallereignisse.
- Ein Umschalten der **grafischen** Genauigkeit ändert weder wirkliche Hörbarkeit noch das an-/ausgeschaltete Akustikmodul.

**Weiter offen:** Gestaltung konkreter Pfeile/Icons/Umrandungen, Standardgrößen und Skalierung, genaue Konfliktauflösung überlappender Richtlinien, konkrete Schwellen-/Regelprofilwerte für die in 02.53 beschlossene Hörprüfung sowie rein erzählerische Hinweise bei vollständig deaktivierter automatischer Akustik. Die vollständige Kampagneneinstellungsführung und Abschaltbarkeit **anderer** Featurebereiche bleiben nach 02.48 auf später verschoben.

## 02.53 – Kombinierte automatische und regelbasierte Geräuschwahrnehmung (12.10.2026)

**Verbindlich beschlossen: Variante C.** **Deutlich und für eine Figur grundsätzlich hörbare Geräusche** können automatisch wahrgenommen werden; bei **leisen, schwer erkennbaren oder verborgenen Geräuschen** dürfen **Figurenfähigkeiten, individuelle Hörschwellen, passive Wahrnehmung, optionale aktive oder regelprofilabhängige Würfelproben sowie ausdrücklich autorisierte Spielleiterentscheidungen** berücksichtigt werden. Das ist **regelwerksneutral**: Kein festes D&D-Attribut, kein verpflichtender W20 und keine Probe für *jedes* Ereignis. Die genaue Schwellenwerteskala und der Würfelmechanismus bleiben für die spätere Detailplanung offen. Es ist eine Produktentscheidung mit technischem Entwurf, keine bereits implementierte Spiellogik.

### 1. Fachliche Wahrnehmungsregeln

- **Eindeutig hörbar – automatische Prüfung:** Zuerst wird das virtuelle Geräusch nach 02.49–02.51 serverseitig erzeugt und unter Berücksichtigung von Entfernung, Wänden, Türen, Material, Lautstärke, Stockwerk und gültigen Ausnahmen nach 02.50 gedämpft. Überschreitet sein am Ziel eintreffender Wert die zum **Empfänger passende** konfigurierte automatische Hörschwelle, kann das Geräusch ohne Würfelprobe als wahrgenommen gelten. Ein lauter Schuss ist nicht für alle Empfänger automatisch hörbar: fehlendes Gehör, unpassender Empfängertyp oder andere explizite Bedingungen bleiben relevant.
- **Schwierig oder verborgen – passive/aktive Erkennung:** Erreicht ein Geräusch einen als schwierig konfigurierten Bereich der Wahrnehmbarkeit, kann das aktivierte Regelprofil **passive Wahrnehmungswerte**, eine **berechtigte aktive Hör-/Wahrnehmungsprobe** oder andere geeignete regelbasierte Prüfungen vorsehen. Eine einfache regelfreie Sandbox darf stattdessen Schwellen/SL-Freigaben verwenden. **Ob und wann** passiv oder aktiv geprüft wird, ist kampagnen-/regelprofilabhängig und noch nicht als universelle Entscheidung festgelegt.
- **Figurenfähigkeiten und Zustände:** Geeignete Hörmerkmale einer Figur, Kreatur, Drohne oder eines anderen wahrnehmenden Objekts (z. B. gutes Gehör, eingeschränktes/fehlendes Gehör, magische bzw. technische Sensorik) dürfen die Erkennung beeinflussen, **aber nur sofern eine Vorlage oder das Regelprofil diese Fähigkeiten tatsächlich modelliert**. Temporäre Zustände/Items können gültige Modifikatoren liefern, ohne Grundattribute stillschweigend umzuschreiben. Das spätere Charakterbogen- und Regelprofilkonzept (Bereiche 03/07) muss dafür Schnittstellen vorsehen.
- **Umgebungsbedingungen und Störungen:** Nur wenn ein Kampagnen-/Szenenprofil sie ausdrücklich vorsieht, dürfen Umgebungslärm, Ablenkung, Hörschutz oder vergleichbare Effekte in die Wahrnehmung einfließen; eine komplette physikalische Überlagerung mehrerer Schallwellen wird mit diesem Beschluss nicht gefordert. Keine erfundenen oder heimlich aktiven Wahrnehmungsstrafen.
- **Spielleiterkontrolle und Ausnahmen:** Passende globale Kampagnen-/Regelprofil-Standards für automatische Erkennung, schwierige Wahrnehmung und optionale Proben sammeln. Für geeignete Geräuschquellen, Bereiche, Figuren oder konkrete Wahrnehmungssituationen sind **bewusste, sichtbare individuelle Ausnahmen** vorgesehen. Die Spielleitung darf berechtigte Hinweise ausdrücklich freigeben oder unterdrücken und die sachlichen Gründe im SL-Log nachvollziehen. Ein erzählerischer SL-Hinweis nach 02.51–02.52 kann unabhängig von einem formalen Hörtest sein; seine Nutzbarkeit bei **deaktivierter** Akustiksimulation bleibt separat offen.
- **Keine automatische Identifikation:** Ein wahrgenommenes Geräusch muss **nicht** seine Ursache, den Namen einer Figur, eine exakte Position oder den Inhalt eines unerforschten Bereichs verraten. Die bisher beschlossene Wahl zwischen **Punkt, Bereich und Richtung (02.52)** regelt die an den Spieler übermittelte räumliche Genauigkeit unabhängig davon, **ob** er etwas gehört hat.
- **Empfängergruppen unterscheiden:** Spielerfiguren, NPCs/Tiere und technische Sound-Sensoren müssen nicht dasselbe Wahrnehmungsprofil nutzen. **Akustische Sensoren** behalten ihre typisierten Schwellwerte/Filter und Node-Verknüpfungen nach 02.40/02.48; eine für eine Spielfigur erfolgreiche Wahrnehmungsprobe löst nicht automatisch Alarm-, Licht- oder Tür-Nodes aus. **Was NPCs/Gegner nach erfolgreicher Wahrnehmung tun**, ist in 02.54 als wählbares Reaktionsverhalten samt allgemeinem NPC-Steuerungsmodus beschlossen.

### 2. Technischer Realisierungsentwurf – keine endgültige API

1. **Verbindlicher Geräuschzustand:** Der autoritative Server verwaltet `SoundEvent` mit Quell-/Szenenbezug und gültiger Intensität/Zeitverlauf aus 02.49/02.51; aktiv nur, wenn das entsprechende automatische Akustiksystem nach 02.51 eingeschaltet ist.
2. **Akustischer Empfangswert:** Der Schallausbreitungsdienst 02.50 berechnet eine für den betreffenden Standort/Empfänger wirksame, ggf. gedämpfte Intensität. Dies allein gilt noch **nicht** als erfolgreiche Wahrnehmung.
3. **Empfängerprofil und Erkennung:** Ein eigener konzeptioneller `HearingProfile`-/`PerceptionResolver`-Dienst liest ausschließlich tatsächlich vorhandene Fähigkeiten, gültige Zustände und die zum Regelprofil gehörigen Hörschwellen. Er entscheidet **automatisch hörbar**, **schwierige Prüfung erforderlich**, **nicht wahrgenommen** oder **manuelle Entscheidung nötig**; Bezeichner sind exemplarisch. Proben dürfen nur durch ein aktiviertes und berechtigtes Regelmodul angestoßen werden.
4. **Regelmodul und Würfel:** Bei zugelassener optionaler Probe prüft der Server Figurenberechtigung, konkrete Probe, Modifikatoren und Ergebnis; erforderliche Würfe werden wie die übrigen Würfel serververbindlich ausgewertet. Sichtbarkeit von Proben und Ergebnissen richtet sich nach Rechte-/Geheimnisregeln; keine geheimen Schwierigkeiten oder Gegnertokens in frei zugängliche Würfelprotokolle schreiben.
5. **Wahrnehmungsergebnis und freigegebener Hinweis trennen:** Ein individuelles `PerceptionResult` (beispielhafter Begriff) soll Ereignis-/Empfängerbezug, angewandte Regel/Grund, Wahrnehmungsstatus und gegebenenfalls Prüfungsreferenz serverseitig festhalten. Nur ein **ausdrücklich für diesen Spieler bereinigtes** `SoundCue`/`AcousticHint` aus 02.51–02.52 wird dem Client übermittelt. Weder konkrete verborgene Quellenkoordinaten noch geheime Skillwerte/Prüfungsschwellen dürfen über das Markersystem unberechtigt sichtbar werden.
6. **SL-Freigaben und Wiederholungen:** Ein SL darf gezielt einen Hinweis anzeigen, selbst wenn kein automatischer Erkennungstreffer vorliegt; diese Präsentation wird als **SL-Hinweis** statt als angeblich bestandene Würfelprobe nachvollziehbar ausgewiesen. Bei anhaltenden oder wiederholten Geräuschen (02.51) sind **Ereignis-ID, Empfänger, Zustandswechsel und definiertes Auslöseintervall** zur Deduplikation zu verwenden: kein automatischer neuer Wurf bei jedem Server-Tick, kein unbegrenztes Würfel-/Benachrichtigungs-Spamming.
7. **NPCs, Sensoren und Sicherheit:** Für NPCs kann ein geprüftes Wahrnehmungsereignis an eine separat zu entscheidende Reaktionslogik übergeben werden (02.54). Für technische Sound-Sensoren gelten weiterhin die sensortypabhängigen Filter und Alarm-Node-Verbindungen aus 02.48. Abschalten des automatischen Akustiksystems verhindert automatische Wahrnehmungsberechnungen und daraus abgeleitete Sensorimpulse, ohne andere Node-Funktionen zu deaktivieren.
8. **Live-Debugger und isolierte Tests:** Berechtigte SL-Diagnose zeigt den konkreten Weg `SoundEvent -> ankommender Wert -> Hörprofil/Schwelle -> ggf. Probe/SL-Override -> Wahrnehmungsergebnis -> freigegebener Hinweis`; simulierte Würfel/Events verändern nicht die echte Kampagne. Persistenz von prüfrelevanten Ereignissen und Auditdaten mit angemessenen Aufbewahrungs-/Datenschutzgrenzen später spezifizieren.

### 3. Abnahmeszenarien für die spätere Entwicklung

- **Lautes Geräusch:** Ein hinreichend lautes Geräusch wird nach tatsächlicher Ausbreitung von einem passenden Hörer ohne Probe erkannt; eine ausdrücklich gehörlose bzw. ungeeignete Figur erhält dadurch keinen automatischen Hörtreffer.
- **Leises Geräusch hinter geschlossener Tür:** Gedämpfte Schritte erfordern bei entsprechendem Regelprofil eine passive oder aktive Hörprüfung. Eine Figur kann sie wahrnehmen, eine andere nicht; nur die jeweils berechtigte bekommt einen passenden Hinweis.
- **Verschiedene Regelprofile:** In einer einfachen Sandbox entscheidet eine konfigurierte Schwelle oder die Spielleitung; in einer anderen Kampagne kann ein regelprofilspezifischer Wahrnehmungswurf erfolgen. Kein obligatorischer D&D-W20.
- **Geheimnisschutz:** Der Spieler erfährt z. B. „Schritte hinter der Tür“ oder die freigegebene Richtung, **nicht** die versteckte Figur, tatsächliche Quellkoordinate oder interne Prüfungsschwelle. SL-spezifische Testergebnisse bleiben geschützt.
- **Sensor-/Node-Trennung:** Ein Charakter hört ein Geräusch, aber ein nicht geeigneter Sound-Sensor löst keine Alarm-Node aus. Eine rein visuelle Markierung erzeugt ebenfalls kein Sensorereignis.
- **Dauer und erneute Prüfung:** Ein dauerhaftes Geräusch löst keine unendliche Folge neuer Proben oder Hinweise aus. Gültige Änderungen an Position, Tür, Lautstärke oder Fähigkeiten werden konsistent und ohne doppelte Events neu bewertet.
- **Akustikschalter aus:** Bei deaktivierter automatischer Akustik gibt es keinen automatischen Erkennungslauf, auch wenn unabhängige Nodes weiter funktionieren; manuelle Erzählhinweise bleiben als gesondert zu entscheidende Funktion gekennzeichnet.

**Weiter offen:** Schwellen und Einheiten, konkrete Eigenschaftsfelder, Regelprofil-Anbindung, Zeitpunkt/Art von Aktiv- oder Passivproben, Umgebungslärm und verdeckte Proben, erneute Versuche nach Zustandswechsel, Behandlung aktiver Szenen/Offlinefällen, exakte Sichtbarkeit von Würfelprotokollen und erzwungene vs. rein erzählerische SL-Freigaben. **Kampagnenakustik an/aus wurde in 02.51 beschlossen; Details der gesamten Kampagneneinstellungsoberfläche sowie die Abschaltbarkeit anderer Featurebereiche werden weiterhin erst nach allen Featurethemen geplant.**

## 02.54 – NPC-Geräuschreaktionen und allgemeine NPC-Steuerung (12.10.2026)

**Beschlossen: Variante C mit ausdrücklicher Ergänzung.** NPCs, Gegner, Tiere und andere geeignete Kreaturen reagieren auf tatsächlich wahrgenommene Geräusche nach 02.53 **wahlweise manuell durch den Spielleiter, automatisch nach gültigen Verhaltensregeln oder erst nach ausdrücklicher Spielleiterbestätigung**. **Zusätzlicher verbindlicher Nutzerwunsch:** Auch **unabhängig von Geräuschen** muss der Spielleiter **bei Kampagnenerstellung** einstellen können, ob NPCs **von ihm selbst gespielt oder automatisch von der Software gesteuert** werden sollen. Ein Modus mit SL-Bestätigung kann als gemeinsame dritte Variante genutzt werden. **Kampagnenstandard, NPC-Vorlagen, Gruppen und bewusst gesetzte Einzel-NPC-Ausnahmen** sind vorzusehen. Hier werden Funktion und technische Anforderungen geplant, keine NPC-KI implementiert.

### Allgemeiner NPC-Steuerungsmodus – unabhängig von Akustik

- **Manuell / Spielleiter spielt:** Der Spielleiter steuert den NPC selbst, einschließlich zulässiger Bewegung, Dialog, Kampf, Interaktionen und anderer Aktionen. Das System darf Ereignisse wahrnehmen und dem Spielleiter Hinweise geben, **aber keine eigenständigen NPC-Aktionen ohne ausdrücklich freigegebene Ausnahmeregel ausführen**.
- **Automatisch:** Der NPC darf selbst handeln, jedoch **ausschließlich mit konfigurierten, erlaubten und serverseitig geprüften Verhaltens-/Aktionsregeln**. Dazu können später u. a. Patrouille, Nachforschung, Flucht, Warnung, Dialog, Gegenstandsinteraktion und Kampf zählen, sofern der jeweilige Bereich tatsächlich solche Aktionen bereitstellt. Dieser Beschluss bedeutet **nicht automatisch freie generative KI**, spontane Regeln oder vollständige selbstständige Dialog-/Kampfintelligenz. Den Detailumfang der allgemeinen NPC-Automatisierung planen wir ausdrücklich in den Featurebereichen **06 NPCs/Gegner und 07 Regel-/Kampfsystem**.
- **Nach SL-Bestätigung:** Die Runtime darf **Vorschläge** für erlaubte Aktionen erstellen. Erst nach ausdrücklicher Zustimmung oder bewusster Änderung durch den berechtigten SL und **erneuter Serverprüfung** entsteht eine Aktion. Ablehnung oder ausstehende Bestätigung verändern den NPC nicht. Fristablauf und Verhalten ohne online verfügbaren Spielleiter bleiben offen.
- **Globale Defaults und Ausnahmen:** Grundsteuerungsmodus pro Kampagne wählbar; NPC-Vorlagen, Fraktionen/geeignete Gruppen und Instanzen können klar gekennzeichnete abweichende Modi erhalten. Beispielsweise sind Wach-NPCs automatisch, ein wichtiger Story-NPC dagegen vollständig handgesteuert. Regeln aus 02.25 für Vorschau, Bestandsauswahl, geschützte explizite Overrides und Dokumentation der tatsächlich wirksamen Herkunft beachten. Wie die Gesamt-Kampagnen-UX aussieht, wird erst nach dem kompletten Feature-Workshop definiert (02.48).
- **Übernahme durch den SL:** Eine berechtigte direkte Übernahme und Rückgabe der Steuerung bei einem zuvor automatisierten NPC als technische Möglichkeit vorsehen; eine laufende automatische Aktion darf nicht parallel zu einer manuellen, widersprüchlichen Aktion dieselbe Figur bewegen. Exakte Übergabe-, Abbruch-, Verzögerungs- und Offline-Regeln sind offen.
- **Keine unbemerkte Übersteuerung:** Spezifische Geräuschreaktionsregeln dürfen einen **allgemein manuell gesteuerten NPC** nicht heimlich autonom handeln lassen. Einzelabweichungen müssen ausdrücklich autorisiert und in der SL-Ansicht erkennbar sein. Prioritäten bei kollidierenden Kampagnen-, Gruppen-, NPC- und Ereignisregeln im Detail später spezifizieren.

### Geräuschabhängige Reaktionen – drei Wege

- **Manuell:** Bei einem erfolgreichen `PerceptionResult` aus 02.53 erhält nur die berechtigte Spielleitung die relevante Wahrnehmung; sie entscheidet über umsehen, untersuchen, warnen, fliehen, sich verstecken, kampfbereit werden oder ignorieren.
- **Automatisch:** Eine definierte NPC-Reaktionsregel darf beispielsweise **Blick/Aufmerksamkeit wenden, einen vermuteten Bereich untersuchen, warnen, Deckung suchen, zurückweichen, Wachsamkeit erhöhen oder nichts tun**. Vorhandene Regelprofile, Aktionen und Zustände bestimmen, was tatsächlich erlaubt und ausführbar ist. Ohne passende aktive Regel wird keine automatisierte Entscheidung hinzuerfunden.
- **Mit Bestätigung:** Eine vorgeschlagene Reaktion wird dem SL einschließlich Reiz, Wahrnehmungswissen, beabsichtigter Aktion und eventuellen Folgen gezeigt; **keine reale Bewegung, Meldung, Alarmierung oder Kampfaktion vor Freigabe**. SL kann ablehnen, bestätigen oder eine andere autorisierte Aktion wählen.
- **Bedingungen:** Zulässige Auslöser/Bedingungen sind etwa Geräuschtyp/-Tags, empfangene Lautstärke und Dauer, NPC-Rolle und Status, erlaubte Fraktions-/Beziehungsregeln, Wachprofil, aktuelle Szene, geeignete Fähigkeiten und zuvor gültig erworbene Wahrnehmungsinformationen.
- **Keine Allwissenheit:** Ein NPC mit bloßer Richtungs- oder Bereichsinformation darf **nicht** automatisch die exakte versteckte Spielerposition, Identität oder geheime Raumgeometrie als Zielwissen erhalten. Aktionen zum Suchen/Bewegen brauchen gültige Wege, Durchgänge und Regelrechte; ein Geräusch ist kein automatisch legaler Angriff.
- **Node-Anbindung:** Ein NPC kann, sofern geeignet verkabelt, seine **Warnung/Alarmreaktion über einen typisierten Ausgang** an die unabhängige Alarm-Node aus 02.48 senden. Reichweite/Empfänger/Fraktionen/Tags bestimmt die Alarm-Node. Ein wahrgenommenes Geräusch sendet nicht pauschal an alle Gegner Alarm. Von NPCs erzeugte neue SoundEvents unterliegen denselben Schleifen-/Frequenzgrenzen aus 02.13/02.49.
- **Trennung vom SL-Spielerhinweis:** Ein vom SL auf die **Spielerkarte gemaltes Geräuschsymbol** `SoundCue` nach 02.51–02.52 gilt nicht als tatsächliches, vom NPC gehörtes `SoundEvent` und löst keine NPC-Aktion automatisch aus. Ist die akustische Simulation aus 02.51 deaktiviert, entfallen **akustisch verursachte automatische** NPC-Reaktionen; **unabhängige NPC-Automatiken oder manuelle Steuerung funktionieren weiterhin**, soweit konfiguriert.

### Technischer Entwurf (noch keine endgültige API)

1. **`NpcControlPolicy` (beispielhafter Bezeichner):** Kampagnen-/Vorlagen-/Gruppen-/Instanzrichtlinie mit Modi `manual`, `automatic`, `approval`, wirksamer Vererbungsquelle und gekennzeichneten Overrides. Die allgemeine NPC-Steuerung ist getrennt von spezifischen Geräuschreaktionsfiltern/`NpcReactionProfile`.
2. **Reaktionspipeline:** Validiertes `PerceptionResult` -> für den NPC **zulässiges Wahrnehmungswissen** (Art/Intensität/ungefähre Richtung/Region, aber keine verborgenen Koordinaten) -> wirksame Steuerungs- und Reaktionsrichtlinie -> manuelle SL-Benachrichtigung, automatisch validierte Aktion **oder** noch nicht ausgeführter `ReactionProposal` (Bezeichner nur Beispiel).
3. **Prüfung und Ausführung:** Eindeutige NPC-/Ereignis-/Vorschlags-/Aktions-IDs, serverseitige Rechte-, Bewegungs-, Kampf-, Szenen- und Node-Prüfung; bei SL-Freigabe erneut validieren. Konflikte mit manuellen Eingriffen und mehreren Ereignissen nach 02.35, inaktiven Szenen nach 02.19, gültigen Runden-/Echtzeitregeln und Schleifenschutz behandeln. Vorschläge nicht automatisch genehmigen.
4. **SL-Werkzeuge und Diagnose:** Steuerungsmodus, Herkunft/Ausnahme, Hörereignis, zulässiges NPC-Wissen, geplante oder abgelehnte Reaktion sowie **wirklich ausgeführte** Aktion im berechtigten Live-Debug/isolierten Tests unterscheidbar anzeigen. Keine geheimen NPC- und Spieler-/Szenen-Interna an unberechtigte Clients. Übernahme und Rückgabe mit eindeutiger Kontrolle ohne Doppelbewegung entwerfen.
5. **Sichere Tests:** Manuelle Story-NPCs neben automatischen Wachen, verschiedene Gruppen-/Instanz-Overrides, Geräusch hinter verschlossener Tür, nur grobe Richtung, ausstehende/abgelehnte Freigabe, veralteter Vorschlag, fehlende Node-Verbindung, Akustik aus bei aktiver Nicht-Akustik-Patrouille, Offline-/Reconnect- und Mehrspielerfälle reproduzierbar prüfen; Simulation ohne echte NPC-Bewegung oder Alarm.

**Offen:** Vollständiger Umfang automatischer Handlungen (Bereiche 06/07), Dialog- und Kampfautomaten, gemeinsame Rollen/Sitzungsübernahme, Vorrang konkurrierender Reaktionen, Vorschlagsfristen, NPC-Patrouillendetails, konkrete UI, NPC-Verdachtszeit und -Eskalation sowie generelles Verhalten automatischer NPCs in inaktiven Szenen. Die zeitlichen NPC-Wachsamkeitsphasen sind in **02.55** beschlossen. Globale Akustikoption wurde in 02.51 beschlossen; der umfassende Kampagneneinstellungsassistent und weitere Modul-Abschaltungen bleiben bis zum Ende der Featureplanung offen.

## 02.55 – Konfigurierbare Verdachts-, Such- und Alarmzustände von NPCs (12.10.2026)

**Verbindlich beschlossen: Variante C.** NPCs, Gegner, Tiere und geeignete Kreaturen können konfigurierbare Wachsamkeits-/Verdachtsphasen besitzen, etwa **normal → aufmerksam → sucht → alarmiert**, mit **passenden Echtzeit- oder Rundenfristen, Eskalation bei neuen Ereignissen, Abklingen, Rückkehr und manuellem SL-Eingriff**. Diese Phasen sind **Beispiele, keine für alle Genres verpflichtende starre Vier-Stufen-KI**. Es gelten globale Kampagnenstandards und bewusst gesetzte individuelle Ausnahmen für NPC-Vorlagen, Gruppen und einzelne NPCs, einschließlich Vorschau/Bestandsschutz aus 02.25.

### Fachliche Regeln

- **Normal:** Der NPC führt entsprechend seinem allgemeinen Grundsteuerungsmodus aus 02.54 seine vorgesehenen Aufgaben aus. „Normal“ bedeutet nicht zwangsläufig „friedlich“; Zustandsnamen und Startwerte gehören zum Profil.
- **Aufmerksam:** Ein **gültig wahrgenommenes** Geräusch oder ein anderer ausdrücklich autorisierter Auslöser darf die Wachsamkeit erhöhen. Die Figur bekommt **keine automatische Kenntnis über exakte verborgene Quellorte oder Gegneridentitäten**, sondern höchstens das nach 02.53 erlaubte Wissen (beispielsweise eine grobe Richtung).
- **Sucht:** Die Figur kann sich an eine gültig wahrgenommene letzte Hinweisregion erinnern und in einen Suchzustand wechseln. Die **Suchbewegung ist eine eigene Aktion** und erfolgt nur nach der allgemein wirksamen NPC-Steuerungsrichtlinie, ihren Fähigkeiten und gültigen Bewegungsregeln.
- **Alarmiert:** Ein höherer zulässiger Verdachtszustand kann eine vorbereitete Reaktion nach 02.54 anbieten. **Nicht automatisch** bedeutet das einen Kampf, die Entdeckung des Gegners oder eine Nachricht an alle Wachen.
- **Auslöser und Eskalation:** Schwere/mehrfache Ereignisse, eine neue gültige Wahrnehmung oder ein ausdrücklich konfigurierter SL-/Node-/Quest-/Sichtauslöser können Phasen oder Fristen verändern. Ohne passende aktivierte Übergangsregel keine erfundene Eskalation. Wiederholte identische Ereignisse dürfen nicht pro Servertick neue Übergänge auslösen.
- **Abklingen/Erholung:** Bleiben Reize aus, können die Phasen nach konfigurierbaren Fristen stufenweise oder gemäß frei definiertem Profil zu einem vorherigen Zustand zurückkehren. Bestimmte Phasen dürfen stattdessen bis zu einer **autorisierten manuellen oder typisierten Reset-Aktion** bestehen bleiben, sofern das Profil das vorsieht. Keine allgemeine feste Sekunden-/Rundenzahl vorgeschrieben.
- **Zeitmodelle:** Phasenfristen, Mindestwachsamkeit, Suchdauer, Wiederholungs- und Rückkehrbedingungen können wahlweise **verstrichene Echtzeit** oder **Spielrunden** nutzen (02.15/02.16), ohne heimliche Umrechnung. Der Umgang mit pausierten Kampagnen, inaktiven Szenen (02.19), Offline-Phasen und Timerablauf beim Serverneustart bleibt als konkrete technische Detailentscheidung offen; es müssen konsistente speicherbare Timer und Zustände möglich sein.
- **Standards/Overrides:** Die Kampagne führt globale Phase-/Timer-/Übergangsstandards, mit markierten Vorlagen-/Gruppen-/NPC-Ausnahmen und nachvollziehbarer wirksamer Herkunft. Spätere globale Änderung mit Vorschau/Übernahme- oder Bestandsschutz aus 02.25; genaue Priorität überlappender Einstellungen später festlegen.

### Verträglichkeit mit 02.54, Sensoren und Geheimnissen

- **Manuell gesteuerter NPC:** Ein NPC, den die SL selbst spielt, führt keine autonomen Aktionen oder unangekündigten weltwirksamen Statusübergänge aus. Das System darf Beobachtungen und mögliche Phasenwechsel an die Spielleitung melden; echte Änderungen erfordern eine gültige SL-Aktion oder **ausdrücklich erlaubte besondere Regel**.
- **Automatische NPC-Steuerung:** Nur definierte, erlaubte Übergänge werden serverseitig ausgeführt. Selbst eine bestätigte Phase „sucht“ darf eine Bewegung nur über gesondert autorisierte NPC-Aktionen bewirken.
- **SL-Bestätigungsmodus:** Vorgeschlagene Zustands-/Aktionsänderungen haben bis zur **ausdrücklichen Bestätigung** keine reale Wirkung. Bei Annahme aktuelle Bedingungen erneut validieren; Ablehnung oder veralteter Vorschlag darf nichts im Weltzustand verändern.
- **NPC-Wachsamkeit ≠ Sensoralarm:** „NPC alarmiert“ ist **nicht derselbe Zustand** wie ein gespeicherter Sensor-/Alarm-Latch (02.44–02.47) oder eine Alarm-Node (02.48). Ohne passende typisierte, berechtigte Node-Verbindung darf es **keinen automatischen globalen Alarm** geben; umgekehrt kann ein gültiger Alarm-Node-Ausgang nur mit ausdrücklich erlaubter NPC-Übergangsregel wirken.
- **Akustikschalter:** Bei nach 02.51 deaktivierter automatischer Akustik sind **aus akustischer Simulation abgeleitete automatische** NPC-Wachsamkeitswechsel ausgeschaltet; eigenständige SL-Aktionen und andere gültige, nichtakustische Auslöser dürfen weiterhin funktionieren.
- **Geheimes NPC-Wissen:** Intern dürfen nur tatsächlich erlaubte Verdachtshinweise, Erinnerungspositionen als zulässige Schätzregion und der legitime Ereignisgrund gespeichert/benutzt werden; tatsächliche versteckte Spielertokenpositionen und SL-Geheimnisse dürfen nicht allein wegen Serverzugriff als NPC-Wissen gelten. NPC-Status und Logs nur nach Sicht-/SL-Rechten ausgeben.

### Technischer Entwurf – noch keine feste API

1. **Profil und Zustand:** Konzeptionelle `NpcAwarenessProfile`-/`NpcAlertPolicy`-Regeln definieren Phasen, Startwerte, Trigger, erlaubte Übergänge, Abkling-/Eskalationsbedingungen und Zeitbasis; pro NPC speichert `NpcAwarenessState` lediglich bestätigte Phase, wirksames Regelprofil, Ausgangsereignis, eingeschränktes gültiges Hinweis-/Verdachtswissen sowie laufende Echtzeit-/Rundenfrist. Namen sind Platzhalter.
2. **Serverseitiger Zustandsautomat:** Validierte `PerceptionResult`-Ereignisse nach 02.53 und sonstige freigegebene Node-/SL-/Szenensignale werden mit der NPC-Steuerungsrichtlinie aus 02.54 verknüpft. Nur autorisierte, versions-/zustandskonsistente Übergänge werden ausgeführt; Aktion, vorgeschlagene Aktion, bestätigter NPC-Status und Sensoralarm bleiben getrennte Objekte.
3. **Zeitplanung und Persistenz:** Gültige Fristart, Ereignis-/NPC-/Timer-ID, Generation/Version und nächster Ablauf speichern; Deduplikation und kontrollierte Neuterminierung verhindern mehrfach ausgeführte Abläufe nach neuen Geräuschen, Reconnect und Neustart. Pausenverhalten und exakte Zeitwerte werden ausdrücklich später entschieden.
4. **Node-System:** Nur zulässige typisierte NPC-Status-/Übergangsports dürfen bestehende Node-Schaltungen (02.13, 02.20, 02.48) auslösen; Zielgruppen/Tag-/Fraktionsfilter und Rechte prüfen. Konfliktregel 02.35, Schleifenschutz, Rate-Limits und getrennte SL-Freigaben berücksichtigen.
5. **SL-Diagnose/Tests:** Für berechtigte Spielleiter Status, wirksames Profil/Ausnahme, Ursache, legitimes NPC-Wissen, nächste Fälligkeit (Echtzeit/Runden), Vorschlagsstatus und tatsächliche Folgeaktionen in Live-Debug und isolierten Node-Tests (02.31–02.34) nachvollziehbar machen. Die Simulation darf echte NPCs/Alarme nicht verändern.

### Spätere Abnahmeszenarien

- Zwei unterschiedlich konfigurierte NPCs hören dieselben Schritte; nur nach eigener gültiger Wahrnehmung wechseln sie gemäß wirksamen Profilen in „aufmerksam“ oder „sucht“. Ein NPC kennt deshalb nicht automatisch eine versteckte Figur.
- Eine neue gültige Wahrnehmung verlängert oder eskaliert die passende Phase; doppelte Events und Timer dürfen keine unendliche Wachsamkeits-/Alarmkaskade erzeugen.
- Nach einer eingestellten Echtzeit- oder Rundenfrist wird ein suchender NPC ohne neue Reize gemäß seinem Profil zurückgesetzt. Abweichende Fristen und individuelle Vorlagen-/Gruppenausnahmen werden berücksichtigt.
- Manueller Story-NPC und automatisch gesteuerte Wache verhalten sich unterschiedlich; im Bestätigungsmodus verändert eine abgelehnte oder wartende Aktion/Statusänderung nichts.
- „NPC alarmiert“ setzt keinen technischen Sensoralarm und verrät keine versteckten Spielerdaten; eine ausdrücklich verbundene Alarm-Node kann gemäß ihren eigenen Regeln reagieren.
- Nach Wiederverbindung oder Serverneustart bleibt der vorher bestätigte Zustand nachvollziehbar, ohne doppelte Zeit-/Node-Ereignisse; Details zur Kampagnenpause und zur inaktiven Szene werden erst später spezifiziert.

**Noch offen:** Konkrete Statusnamen und Anzahl, Frist-/Schwellwerte, Übergangs- und Override-Konfliktprioritäten, Pausen- und Inaktiv-Szenen-Semantik, Such-/Kampf-Automatisierung in 06/07, Aufbewahrungsdauer von NPC-Verdacht und die detaillierte Zustellung und Störung von nach 02.56 konfigurierbaren NPC-Warnungen. Die übergreifende Kampagneneinstellungs-UX und Abschaltung weiterer Funktionsbereiche bleiben bis zum vollständigen Feature-Workshop zurückgestellt.

## 02.56 – Regelbasierte Informations- und Warnungsweitergabe zwischen NPCs (12.10.2026)

**Verbindlich beschlossen: Variante C.** NPCs, Gegner, Tiere und weitere dafür geeignete Spielweltakteure dürfen Verdacht, Warnungen, Alarmhinweise und andere **tatsächlich bekannte Informationen nur über gültige, bewusst konfigurierte Kommunikationswege** weitergeben. Die zulässigen Wege, Reichweiten, Empfänger-/Fraktions-/Tag-Filter, Informationsgenauigkeit, Steuerungsmodus und passende Ausnahmen werden regel- und settingabhängig festgelegt. **Weder alle Mitglieder einer Fraktion noch alle NPCs einer Szene erhalten automatisch identisches Wissen.** Die globale NPC-Grundsteuerung (02.54), NPC-Wachsamkeit (02.55), Akustik (02.49–02.53) und gesonderten Alarm-Nodes (02.48) behalten ihre jeweiligen Zuständigkeiten.

### 1. Unterstützte Arten der Kommunikation

- **Ruf, Sprache, Tierlaut:** Ein dafür geeigneter NPC kann eine **echte Spielwelt-SoundEvent-Kommunikation** auslösen. Der Server wertet die Hörbarkeit über die Akustik-/Hörprofile aus 02.50–02.53 aus: Schallausbreitung, Entfernung, Wände/Türen/Stockwerke, Empfänger-Hörfähigkeit und ggf. Regelprobe. Nur NPCs, die den Ruf **nach ihren eigenen Regeln tatsächlich wahrnehmen können**, dürfen dadurch eine Information empfangen. Ein Geräusch wahrzunehmen ist nicht zwangsläufig dasselbe, **die gesamte Nachricht zu verstehen**; die konkrete Verständlichkeitsprüfung bleibt später auszugestalten.
- **Sichtzeichen/Gesten/Lichtzeichen:** Zeichen oder sichtbare Hinweise erfordern eine gültige Wahrnehmungs-/Sichtbeziehung mit passenden Fähigkeiten, Blickrichtung, Hindernissen und ggf. Lichtzustand nach 02.5–02.9/02.42–02.43. Der Empfänger muss das Zeichen sehen und entsprechend dem gültigen Profil verstehen können. Eine nur dem SL sichtbare unsichtbare Figur kann nicht bloß deshalb heimlich allen anderen NPCs ein sichtbares Zeichen zustellen.
- **Funk, Telefon, Intercom, technische Netzwerke:** Geeignete **Geräte, Besitz-/Rollen-/Kanalberechtigungen**, aktivierte Verbindung sowie nach Szenario konfigurierte Reichweite/Netzabdeckung/Adressierung prüfen. Eine technisch weitergeleitete Nachricht benötigt nicht automatisch akustische Ausbreitung durch Wände. Die Plattform verspricht **keine echte Funkphysik oder simulierte Telefoninfrastruktur**, sondern ein dafür vorgesehenes konfigurierbares Verbindungsmodell.
- **Magische/übernatürliche/settingabhängige Verbindung:** Nur wenn ein entsprechendes optionales Regel-/Genreprofil die benötigte Fähigkeit, Reichweite, Zielbedingung und ggf. Kosten definiert, darf eine magische Gedanken- oder Botenschaft stattfinden. Keine magischen Standardrechte in genreunabhängigen Kampagnen.
- **Node-Schaltung und eigenständige Alarm-Node:** Typisierte, autorisierte Node-Verbindungen (02.13, 02.20, 02.48) können gezielt Mitteilungen oder zulässige Alarmreaktionen bewirken, z. B. ein angeschlossenes Alarmterminal informiert Wachen in der passenden Szene oder Fraktion. Die **Alarm-Node entscheidet über Region/Szene/Kampagne und Ziel-Tags**; der Kommunikationsweg benötigt gültige Anschlüsse und Berechtigungen. Eine NPC-Warnung ohne diese Verbindung darf nicht alle Ziele automatisch alarmieren.
- **SL-/Szenen-/Quest-Warnungen:** Bewusst ausgelöste und autorisierte erzählerische Informationen dürfen als eigene Quelle existieren und adressatenspezifisch freigegeben werden. Sie sind nicht gleichbedeutend mit der Behauptung, dass ein NPC einen akustischen Ruf gehört oder ein verborgenes Ziel selbst identifiziert hätte.

### 2. Wissen, Empfänger und Grenzen

- **Sender weiß nicht alles:** Ein NPC kann nur das weitergeben, was ihm nach 02.53/02.55, durch eine andere **wirklich empfangene** Nachricht oder durch eine gültige SL-/Regelaktion bekannt ist. Kennt eine Wache bloß die Richtung eines verdächtigen Geräuschs, darf daraus keine exakte verborgene Spielerposition, wahre Identität oder ein unbekannter Raumplan werden.
- **Gezielter Empfängerkreis:** Der Kommunikationskanal kann **konkrete NPCs/Bediengeräte, Gruppen, Fraktionen, Freund-/Feindrelationen, Rollen, Tags oder räumliche Reichweiten** auswählen, soweit die entsprechende Empfängerdefinition gültig ist. Fraktionszugehörigkeit bestimmt nicht allein eine magische Fernübertragung. Beziehungen benötigen wie in 02.48 einen gültigen Bezugsakteur/Fraktionskontext.
- **Informationsumfang und Genauigkeit:** Zulässige Nachrichtentypen sind beispielsweise *„ungewöhnliche Schritte gehört“*, *„Verdacht in dieser Region“*, *„Wachposten benötigt Hilfe“* oder ein ausdrücklich freigegebenes Alarmlevel. Quelle, bekannte Richtung/Region, Sicherheitsstufe und Wissensumfang müssen pro Nachricht geprüft werden; die an den Empfänger zugestellte Information ist höchstens so präzise wie **tatsächlich gewusst und zur Übertragung freigegeben**. Falls ein Empfänger unabhängig bereits zusätzliche Erkenntnisse besitzt, bleibt sein eigenes Wissen davon getrennt.
- **Empfang ≠ Zustandswechsel:** Eine technisch oder akustisch **erfolgreich zugestellte** Mitteilung ist zunächst eine eigene fachliche Information. Ob der Empfänger dadurch **aufmerksam, suchend oder alarmiert** wird, entscheidet sein gültiges NPC-Wachsamkeitsprofil nach 02.55 und die wirksame Steuerungsrichtlinie aus 02.54. Es entsteht **kein automatischer Angriff, keine garantierte Suche und kein allgemein verteilter Alarm**.
- **Manuell/automatisch/SL-Freigabe:** Für manuell gespielte NPCs darf das System eine Kommunikationsoption oder einen privaten Hinweis anbieten, die Figur aber **nicht ungefragt eigenständig sprechen, funken oder eine Warnung senden lassen**. Automatische NPCs können nur erlaubte, definierte Senderegeln ausführen; ein NPC im Bestätigungsmodus wartet bei weltwirksamen Sendungen auf den berechtigten Spielleiter und eine gültige Serverprüfung.
- **Globale Standards mit Ausnahmen:** Kampagnenweite Kommunikationsprofile vorsehen, für settingabhängig erlaubte Kanäle sowie geeignete NPC-Arten/Gruppen und **konkrete NPC-/Geräte-/Regions-Ausnahmen**. Vererbungsquelle und Overrides sichtbar, Änderungen an Defaults mit Vorschau/Bestands-/Ausnahmeschutz nach 02.25. Die endgültige Struktur des Kampagnenerstellungsassistenten wird weiterhin **erst nach allen Featurebereichen** festgelegt (02.48).
- **Szenen/Stockwerke und Abschaltung:** Kanalübergreifende Nachrichten über Szenen/Stockwerke benötigen **ausdrücklich modellierte** Verbindung, Funknetz/Wege oder erlaubte kampagnenweite Node-Weiterleitung (02.18–02.19). Bei ausgeschalteter Akustiksimulation nach 02.51 entsteht **kein automatischer Hörtreffer durch einen Ruf**; nichtakustische, separat zulässige Funk-, magische oder Node-Kommunikation darf davon unabhängig funktionieren. **Rein manuelle sichtbare Geräuschhinweise bei Akustik-aus** bleiben wie schon zuvor eine eigene ungeklärte Detailfrage und werden nicht durch 02.56 stillschweigend freigegeben.

### 3. Technische Umsetzung (fachlicher Entwurf, keine endgültige API)

1. **Fähigkeiten und Kanäle:** Eine konzeptionelle `NpcCommunicationPolicy` bzw. `CommunicationChannel`-Definition führt Kanalart, gültige Sender/Empfänger, Voraussetzungen, Reichweiten/Topologie, Rollen-/Fraktions-/Tagfilter und Ausnahmeregeln. Beispiele: `voice`, `visual`, `radio`, `magic`, `node`; dies sind **nur mögliche Typnamen**, keine implementierte Datenbank.
2. **Autorisiertes Sendereignis:** Nach gültiger Hör-/Sicht-/NPC-/SL-Reaktion entsteht ein `CommunicationEvent` (Beispielname) mit Ereignis-ID, Quelle/Sender, tatsächlich zulässigem Informationsinhalt, adressierter Zielmenge, Kanal, Szenen-/Zeitbezug und gegebenenfalls referenziertem bekannten Bereich. **Ein SL-Vorschlag ist noch keine gesendete Nachricht.**
3. **Kanalprüfung pro Empfänger:** Server prüft reale Kanalvoraussetzungen (Hörbarkeit für Rufe, Sichtzeichen-Erkennung, zulässigen Funkempfang, verknüpfte Nodes oder Regelfähigkeiten) und alle Rechte **vor Zustellung**. Nicht erreichte Empfänger werden nicht als informiert markiert. Eine Empfängerliste, die auf einer Fraktion basiert, ersetzt die Kanal-/Reichweitenprüfung nicht.
4. **Bereinigte Information statt Quellkoordinaten:** Der Server erstellt ein empfängerbezogenes `NpcKnowledgeUpdate`/Wissensevent (Beispielname) **nur aus legitimem Senderwissen und übertragener Genauigkeit**. Die zugrunde liegenden versteckten NPC-/Spielerpositionen, geheimen Node-Geometrien und SL-Notizen bleiben getrennt; ein NPC darf nicht aus der Datenhaltung des Servers „allwissend“ werden.
5. **Empfängerreaktion getrennt:** Ein erfolgreiches Kommunikations-/Wissensevent ist ein **typisierter, validierter Eingang** für die NPC-Wachsamkeits- und Aktionsregeln 02.54–02.55. Nur dort wird bei gültiger Einstellung entschieden, ob ein NPC Verdacht ändert, sucht, einen weiteren Ruf sendet oder nichts unternimmt. Die eigene Alarm-Node kann zusätzliche gezielte Aktionen auslösen, aber nur über die explizite, autorisierte Schaltung.
6. **Verteilungs-/Schleifenschutz:** Für Mehrfach-Zustellung/Weiterleitungen **Ursprungs- und Nachrichten-ID**, bereits informierte Empfänger, begrenzte Weitergabe, Idempotenz und Schutz vor zyklischer Kettenweiterleitung vorsehen. Gleichzeitige Alarm-/Warnungen nach Konfliktregel 02.35 behandeln; keine unendliche Sirenen-/Funkschleife oder identische Nachricht bei jedem Servertick. Zustände und relevante Sendevorgänge serverseitig persistierbar, Geheimnisse nur auf autorisierten SL-Clients darstellen.
7. **SL-Debug und isolierte Tests:** Für berechtigte Spielleiter Senderwissen, erlaubten Kommunikationsweg, erfolgreiche/gescheiterte Empfängerprüfung, tatsächlich übermittelte Genauigkeit, realen Empfang, optionalen NPC-Zustandswechsel und weitere Node-Reaktionen anzeigen. Gespeicherte Tests aus 02.31–02.34 dürfen keine echten NPCs, Alarme oder Sendungen beeinflussen.

### 4. Spätere Abnahmeszenarien

- **Fantasy-Wachen:** Eine Wache ruft „Schritte im nördlichen Flur“; nur Wachen, die den Ruf **nach ihren eigenen Hörregeln** wahrnehmen, erfahren diese ungenaue Information. Durch eine geschlossene schalldämmende Tür hinter einer Wand kann die Zustellung gemäß 02.50 ausbleiben.
- **Funknetz:** Eine technisch ausgerüstete Wache kann eine Warnung über gültige Funkabdeckung an geeignete Empfänger senden, obwohl keine direkte Hör- oder Sichtverbindung besteht; NPCs ohne Gerät oder Kanalberechtigung erhalten sie nicht.
- **Sichtzeichen:** Ein Wachposten deutet auf einen vermuteten Bereich. Eine zweite Wache mit Sichtkontakt darf den Hinweis entsprechend der Freigaberegel übernehmen, eine verdeckte oder nicht sehfähige Figur nicht.
- **Manueller Story-NPC:** Dieser kann den SL auf eine Sendemöglichkeit aufmerksam machen, sendet aber keine automatische Warnung. Ein NPC im Bestätigungsmodus wartet vor dem Senden auf den SL; NPC-Automatiken senden nur wenn zulässig.
- **Unterschiedliche Fraktionen:** Ein Alarm-Node benachrichtigt ausschließlich die nach Regions-/Fraktions-/Tagfiltern ausgewählten Ziele. Andere Fraktionsmitglieder werden nicht automatisch informiert, nur weil sie derselben Fraktion angehören.
- **Wissensschutz:** Ein NPC teilt eine vermutete Richtung mit; der Empfänger bekommt **keine exakte geheime Spielerposition**. Der Empfang ändert nicht automatisch die Wachsamkeit, wenn keine passende 02.55-Regel existiert.
- **Akustik aus:** Automatische Ruf-Hörerkennung unterbleibt; unabhängig erlaubte Funk-/Node-Nachrichten und manuelle NPC-Steuerung können weiter funktionieren.
- **Mehrfachweitergabe:** Mehrere Wachen reichen denselben Warnhinweis über zulässige Wege weiter, ohne endlose Reaktions- oder doppelte Alarmketten; geheime Nutzerdaten bleiben aus Spieler-Clients heraus.

**Noch offen:** Konkrete Kommunikationslatenzen und Fristen, Funkstörungen/Ausfälle, unterbrochene Nachrichten und eventuelle Abfang-/Täuschungsmechaniken; Verständlichkeits-/Sprachregeln, gespeicherte Wissensdauer und genaue Übertragungspayloads, Vorrang konkurrierender Kampagnen- und NPC-Ausnahmen, Verhalten in inaktiven Szenen und die genaue Bedienoberfläche. Diese Punkte sind mit der Auswahl C **nicht automatisch entschieden**. Vollständiger Kampagnenassistent und Abschaltbarkeit anderer Featurebereiche werden weiterhin erst nach dem Gesamtworkshop geplant.

## 02.57 – Konfigurierbare Zustellung, Verzögerung, Unterbrechung und Ausfall von NPC-Nachrichten (12.10.2026)

**Verbindlich beschlossen: Variante C.** Für die in 02.56 vereinbarten Kommunikationswege können **sofortige und verzögerte Übertragung, Störungen/Unterbrechungen, endgültiger Zustellfehler, zeitlicher Ablauf und erlaubte Wiederholungsversuche** eingestellt werden. Es gelten **passende globale Kampagnenstandards mit bewussten Ausnahmen** für Kanäle, Geräte, Gruppen/NPCs, Regionen und konkrete Kommunikationsquellen, einschließlich der bestehenden Vererbungs-, Vorschau- und Bestandsregeln aus 02.25. Zeiten können **in Echtzeit oder Spielrunden** angegeben werden (02.15/02.16), ohne unbemerkte Umrechnung. Der Spielleiter darf berechtigt eingreifen. Dieser Beschluss ist eine Anforderung an die spätere Umsetzung und **keine implementierte Kommunikationsengine**.

### 1. Fachliches Zustellverhalten

- **Sofort:** Eine Nachricht wird nach gültiger Sendeberechtigung und erfolgreicher Kanal-/Empfängerprüfung direkt als zugestellt betrachtet. **Senden ≠ Empfangen ≠ Verstehen ≠ Reagieren**: Die tatsächliche Zustellung und die erlaubte Informationsverarbeitung sind eigene Schritte; aus einem bloßen Sendeversuch entsteht kein NPC-Wissen.
- **Verzögert:** Der konfigurierte Kanal darf eine Nachricht erst nach einer angegebenen Frist oder einem gültigen Zeit-/Rundenereignis transportieren. Während die Übertragung noch **ausstehend** ist, darf das empfangende NPC-Wissen bzw. dessen Verdachtszustand aus 02.55 **nicht bereits verändert** werden. Vor der tatsächlichen Zustellung müssen jeweils nötige Kanal-, Rechte- und Empfängerbedingungen geprüft werden; welche Voraussetzungen bereits beim Senden gesichert bleiben oder erneut erfüllt sein müssen, ist profilabhängig und wird im technischen Detail bestimmt.
- **Unterbrochen:** Verliert eine laufende Übertragung ihre benötigte Verbindung oder tritt ein ausdrücklich konfigurierter Störzustand ein, kann sie je Kanal als **unterbrochen**, **wartend** oder **fehlgeschlagen** behandelt werden. Ob und wann ein unterbrochener Transport fortgesetzt werden darf, ist pro Kommunikationsprofil konfigurierbar. **Die Nachricht gilt bis zur erfolgreichen Zustellung nicht als empfangen.**
- **Fehlgeschlagen:** Eine technisch unmögliche, unberechtigte, endgültig abgebrochene oder nicht rechtzeitig zustellbare Nachricht darf als gescheitert gespeichert werden. Es darf **keine rückwirkende Kenntnis des Empfängers**, kein erfundener NPC-Alarm und kein automatisch freigegebener Node-Effekt entstehen.
- **Ablauf/Verfall:** Nachrichten können eine begrenzte Gültigkeit besitzen. Ist sie abgelaufen, wird die Lieferung verworfen oder ausdrücklich nach einer gültigen, zukünftigen Regel neu erzeugt. Alte Warnungen sollen **nicht ohne konfigurierbare Prüfung veraltete NPC-Reaktionen auslösen**. Ob bereits zugestelltes NPC-Wissen später vergessen wird, ist die gesonderte Gedächtnisfrage und wird nicht mit dem Transport-Ablauf gleichgesetzt.
- **Wiederholung/Retry:** Ein profilabhängig zulässiger Wiederholungsversuch kann nach Frist, Wiederverbindung, SL-Aktion oder gültigem Node-Ereignis erfolgen, mit **begrenzten Versuchen bzw. Endbedingung**. Ein Retry darf niemals Senderautorisierung, Empfängerfähigkeit, Kanalreichweite, Gültigkeit der Nachricht oder andere Sicherheitsregeln umgehen. Keine unendlichen Retry-/Alarmkaskaden.
- **Spielleiterkontrolle:** Berechtigte Spielleiter können je nach gültiger Policy eine wartende Zustellung einsehen, gezielt abbrechen, erneut versuchen oder eine **ausdrückliche Sonderzustellung** erlauben. Diese Aktionen müssen den Unterschied zwischen einem erzählerisch gesetzten SL-Hinweis und einer tatsächlich übertragenen NPC-Nachricht nachvollziehbar halten. Keine unbemerkte automatische Bestätigung.
- **Echtzeit und Runden:** Verzögerung, Ablauf und Wiederholungsintervalle dürfen je Kommunikationsweg auf Echtzeit **oder** Spielrunden beruhen. **Keine heimliche Umrechnung** und keine endgültige Entscheidung über Pause, inaktive Szenen, Offline-Zustellung oder Warteschlangenpersistenz ohne die zugehörige spätere technische Abstimmung.

### 2. Unterschiedliche Transportkanäle realistisch und regelneutral behandeln

- **Rufen/Sprache:** Das Ereignis ist nach 02.49–02.53 ein **tatsächlich ausgesendetes Spielweltgeräusch**. Eine bereits vergangene Schallwelle wird **nicht einfach in einer digitalen Warteschlange nachträglich hörbar**. Ein späterer neuer Ruf benötigt, sofern konfiguriert, eine neue gültige Äußerung bzw. ein autorisiertes neues SoundEvent. Akustik-aus nach 02.51 unterbindet automatische Ruf-Hörerkennung; technische/magische Kommunikationswege bleiben davon unabhängig.
- **Sichtzeichen:** Der Zeitpunkt des Signals und eine tatsächlich gültige Sicht-/Erkennungsbeziehung sind entscheidend. Bei Sichtverlust während einer geplanten Zeichengabe kann sie gemäß Kanalregel scheitern oder zu einem späteren Zeitpunkt bewusst **neu ausgelöst** werden; kein rückwirkendes Sehen.
- **Funk/Telefon/Intercom:** Verbindungsaufbau, nicht verfügbare Kanäle, Funklöcher und profilabhängiges zeitversetztes Übertragen können unterstützt werden, **ohne** die physikalische Modellierung realer Funknetze vorauszusetzen. Speichern/Puffern oder erneutes Senden erfordert entsprechende kanalbezogene Konfiguration; ein nicht gespeichertes Live-Gespräch darf nicht stillschweigend nachgeliefert werden.
- **Magie/Spezialkanäle:** Dauer, Erfolg, Kosten und Wiederholung ergeben sich nur aus aktivierten Regelprofilen und tatsächlich verfügbaren Fähigkeiten. Dieser Beschluss erzeugt keine neue Standard-Zauberwirkung.
- **Node-/Alarm-Wege:** Verzögerungen und Wartestatus können über gültige, typisierte Nachrichten-/Timer-/Alarmverbindungen (02.15–02.20, 02.48) modelliert werden. **Nur eine wirklich ausgeführte, zulässige Aktion** darf Folge-Nodes auslösen; ein zur Zustellung anstehendes Ereignis ist kein bereits ausgelöster Alarm.

### 3. Verträglichkeit mit NPC-Steuerung, Wissen und Sicherheit

- **NPC-Steuerungsmodus 02.54:** Bei manuellen NPCs veranlasst ausschließlich der SL bzw. eine ausdrücklich freigegebene besondere Regel eine Sendung; im Automatikmodus braucht es eine gültige Reaktions-/Kommunikationsregel; im Bestätigungsmodus findet **keine Sendung vor SL-Genehmigung** statt. Ein Transport-Retry ist nicht dasselbe wie eine Genehmigung eines neuen NPC-Handlungswunsches; nötige erneute Berechtigungsprüfung gilt trotzdem.
- **NPC-Wissen 02.53/02.55/02.56:** Sender dürfen nur tatsächlich bekanntes Wissen übertragen. Bis zum **bestätigten Empfangen** erlangt der Ziel-NPC kein Wissen und wechselt nicht automatisch seine Wachsamkeitsphase. Erst ein separates, validiertes Wissens-/Zustandsereignis nach 02.55 darf eine NPC-Reaktion auslösen.
- **Keine Informationslecks:** Wartende Nachrichten, fehlgeschlagene Versuche, innere Sender-/Empfängerlisten, Geräte-/Node-Zustände und nicht veröffentlichte Geräuschpositionen bleiben serverseitig. Nur berechtigte Spielleiter sehen die genaue Zustellkette; Spieler dürfen keine geheimen NPC-Positionen oder verborgene Kommunikation durch Netzwerkdaten erfahren.
- **Schleifen und Doppelwirkung:** Erneute Übertragung einer Nachricht muss mit **stabiler Ursprungskette, Sendungs-ID und empfängerbezogener Zustellungs-/Wirkungs-ID** dedupliziert werden; kein mehrfaches NPC-Wissensupdate oder Node-Alarm nur wegen Wiederholung, Reconnect, doppelter Netzwerkpakete oder paralleler Wachen. Falls eine neue Nachricht mit bewusst geändertem Inhalt entsteht, ist das ein neues **gültig autorisiertes Ereignis** und keine unkontrollierte Nebenwirkung.
- **Defaults/Overrides:** Wirksamer Kanalstandard, Objekt-/Geräte-/NPC-/Gruppenausnahme, Verzögerungsregel, laufender Retry-Plan und Status sollen für berechtigte SL im Debugger unterscheidbar sein. Globale Änderungen folgen 02.25; eine bereits ausstehende Nachricht darf beim Ändern eines Defaults nicht unkontrolliert umgedeutet oder doppelt ausgeliefert werden.

### 4. Technischer Realisierungsentwurf – noch keine feste API

1. **Transport-Policy:** Eine konzeptionelle `CommunicationDeliveryPolicy` ergänzt den Kanal 02.56 um optionale Verzögerung, Zeitbasis (`realtime`/`rounds`), Ablauf, Störung/Unterbrechungsstrategie, erlaubte Retry-Bedingungen und Versuchsgrenzen. Werte und endgültige JSON-/DB-Feldnamen sind **nicht beschlossen**.
2. **Nachrichtenlaufzeit:** Serververwaltete `MessageDelivery`-Instanzen mit Sendungs-/Ursprungs-/Empfänger-ID, überprüften Senderrechten, zulässigem Nachrichteninhalt, **Status** (beispielsweise `pending`, `in_transit`, `interrupted`, `delivered`, `failed`, `expired`), Versuchsnummer, Kanalprofilversion und gültiger Frist. Nicht jeder Kanal muss jeden Status unterstützen.
3. **Deterministischer Übergang:** Eindeutige Statuswechsel und erneute Kanal-/Empfängerprüfung bei tatsächlicher Zustellung; die endgültige Reihenfolge von Ablauf, Empfang, gleichzeitiger Störung und manueller SL-Aktion wird später als testbare Konfliktregel konkretisiert. Ein erfolgreiches `delivered` darf pro Empfänger nur **ein wirksames NPC-Wissensupdate** (02.56) verursachen. Auch eine Nachricht, die nie ankommt, bleibt als gescheiterter Versuch erklärbar.
4. **Scheduler und Persistenz:** Echtzeit-/Rundenfristen nicht vermischen; bei wiederaufgenommenen Szenen, Reconnect und Serverneustart idempotente Wiederaufnahme oder nachvollziehbarer gültiger Abbruch gemäß noch zu entscheidender Policy. Keine unbegrenzten Queues, unkontrollierte Wiederholungen oder Endlosschleifen; Kapazitäts- und Retentionslimits später festlegen.
5. **Node-/Alarm-Integration:** Eindeutige, typisierte Ausgänge für tatsächlichen Erfolg, Fehlversuch, Ablauf oder geeignete Retry-Ereignisse als **mögliche** Anschlüsse vorsehen; konkrete Ports und Rechte später spezifizieren. Reine Transport-Störungen erzeugen nicht automatisch einen Alarm an die ganze Szene. Bestehende Konflikt-, Deduplikations- und Sicherheitsregeln 02.13/02.20/02.35/02.48 gelten.
6. **Debug/Simulation:** Berechtigter SL sieht Ursache, Sender, Kanal, empfängerabhängige Statusfolge, Wartefrist, Wiederholung, verbindliche Zustellung und daraus **getrennte** NPC-Wissens-/Wachsamkeits-/Alarmfolgen. Isolierte Tests nach 02.31–02.34 simulieren Echtzeit- und Rundenschritte, Netzstörungen, Reconnect und Mehrspieler, **ohne echte Nachrichten oder NPC-Aktionen auszulösen**.

### 5. Tests zur späteren Abnahme

- **Funkverbindung unterbrochen:** Ein NPC sendet gültig eine Warnung; der Kanal fällt während der Übertragung aus. Der Empfänger weiß noch nichts. Nach zulässiger Wiederverbindung erfolgt je Policy gültiger Retry oder endgültiger Fehler; keine Mehrfachbenachrichtigung.
- **Zeitversetzte Nachricht:** Die passende Spielrundenzahl oder Echtzeitfrist muss verstreichen; bis dahin gibt es kein NPC-Wissensupdate. Bei Ablauf vor Zustellung wird die Nachricht als abgelaufen statt empfangen behandelt.
- **Ruf statt digitaler Queue:** Ein Geräuschruf, der keinen NPC erreicht, darf nicht später „aus dem Nichts“ gehört werden. Wenn eine neue gültige Rufaktion vorgesehen ist, wird sie eigenständig geprüft.
- **Manuelle NPCs und Bestätigung:** Kein automatisches Senden eines manuell gespielten NPCs und kein Senden vor SL-Bestätigung; ein von der Spielleitung korrekt ausgelöster Kanal darf dennoch nach seiner Transportpolicy ausfallen.
- **Fraktionen und Geheimnisse:** Gleicher Funkkanal, aber unterschiedliche Berechtigungen: Nur berechtigte und tatsächlich erreichbare Empfänger erhalten die inhaltlich zulässige Nachricht, ohne mehr über geheime Spielerpositionen zu erfahren.
- **Alarm- und Wiederholungsschutz:** Drei wiederholte Transportversuche dürfen bei nur einer gültigen Zustellung keine drei NPC-Verdachtssteigerungen oder mehrfachen Alarm-Node-Wirkungen hervorrufen.
- **Neustart und Zeitmodelle:** Ausstehende Vorgänge dürfen weder verloren gehen noch ungefragt doppelt wirksam werden; ihr konkretes Pausen-/Offlineverhalten bleibt eine gesonderte noch offene Policy-Frage.

**Weiter offen:** Exakte Verzögerungswerte, Limits und Standard-Retry-Policy, atomare Reihenfolge konkurrierender Transportereignisse, Offline-/Pausen- und inaktive-Szenen-Behandlung, partielle Nachrichten/Verständlichkeit, Störungsursachen, Übertragungsdauer und Speicherung von Live-Sprache, gegebenenfalls spielerisches Mithören/Abfangen/Verfälschen. **Die grundsätzliche Möglichkeit gezielter Informationsmanipulation wurde anschließend in 02.58 C beschlossen; konkrete Vertrauens-/Erkennungsprüfungen folgen in 02.59.** Der globale Kampagnenassistent sowie die vollständige Abschaltbarkeit weiterer Featurebereiche werden wie bisher erst nach dem Gesamtworkshop geplant.

## 02.58 – Regel- und settingabhängiges Abhören und Manipulieren von Kommunikation (12.10.2026)

**Verbindlich beschlossen: Variante C.** Kommunikationswege nach 02.56 dürfen **je nach Kampagnen-/Regelprofil, konkretem Kanal, Ausstattung, Fähigkeit, Berechtigung, Reichweite und gültiger Spielsituation** abgehört, abgefangen, blockiert, umgeleitet, in ihrem Inhalt verändert oder durch vorgetäuschte Absender gefälscht werden. Die einzelnen Manipulationsarten sind **eigenständige, wählbare Fähigkeiten – nicht automatisch an jedem Kanal vorhanden**. Regelwerksabhängige Proben, wenn gewünscht, können über die spätere generische Regel-/Würfel-Engine erfolgen. **Globale Kampagnenstandards mit bewussten Ausnahmen je Kanal, Szene/Region, Gerät, Kommunikationsobjekt, NPC/Gruppe und geeigneter Quelle** sind vorzusehen. Diese Entscheidung definiert die Funktionsanforderungen, **nicht** ein implementiertes Hacking-System, den endgültigen Regelalgorithmus oder die Kampagnen-Einstellungsoberfläche.

### 1. Fachlicher Funktionsumfang

- **Mithören / passive Einsicht:** Eine dazu befähigte und situativ geeignete Figur kann gegebenenfalls **den tatsächlich für sie wahrnehmbaren Inhalt** einer fremden Kommunikation mitbekommen, ohne deren vorgesehenen Transport automatisch zu unterbrechen: etwa einen Ruf durch eine Tür hören, eine passende Funkfrequenz empfangen, ein berechtigt verzaubertes Signal erfassen oder an ein entsprechend erlaubtes Kommunikationsobjekt gelangen. Hörbarkeit nach 02.50–02.53 und Verständlichkeit bleiben getrennt. Abhören bedeutet **nicht** automatisch Klartext-Verstehen, vollständiges NPC-Wissen oder Kenntnis geheimer Absender-/Positionsdaten.
- **Abfangen:** Ein gültiges Spielereignis kann bei einem geeigneten Kanal eine fremde Nachricht **vor ihrer eigentlichen Zustellung** erfassen; ob zusätzlich der reguläre Empfänger sie erhält, hängt von der konfigurierten Aktion ab. Nicht jede Kommunikation ist als „physisch abfangbares Paket“ modelliert: Eine Stimme, ein Handzeichen, ein Brief, ein Funkspruch oder eine magische Botschaft benötigen **kanalspezifische** Voraussetzungen.
- **Blockieren / Unterdrücken:** Eine erlaubt ausgeführte Aktion kann eine Zustellung stören oder verhindern und erzeugt einen begründeten **Transportzustand** aus 02.57 (beispielsweise unterbrochen, fehlgeschlagen oder bei passender Regel erneut versuchbar). Nur **eine tatsächlich unterdrückte Zustellung** darf dem Ziel die Nachricht vorenthalten; andere gültige Empfänger bleiben ggf. informiert.
- **Umleiten:** Bei vorhandenem regel-/kanalabhängigem Mittel kann eine Kommunikation statt oder zusätzlich zu ursprünglichen Empfängern an andere geeignete Ziele geführt werden. **Zielrechte und Kommunikationsvoraussetzungen** werden erneut geprüft. Ein neues Ziel darf nicht allein durch einen manipulierten Empfängernamen heimlich Zugriff auf geheime Serverdaten erhalten.
- **Verändern / Fälschen:** Bei einer erfolgreichen ausdrücklich erlaubten Manipulationsaktion darf eine wirksame Nachricht **mit verändertem Inhalt** übertragen oder **als Botschaft eines vorgetäuschten Absenders** dargestellt werden. Der tatsächliche Ursprung, die behauptete Absenderidentität, der ursprüngliche Inhalt und der an einzelne Empfänger tatsächlich zugestellte Inhalt sind fachlich **verschiedene Dinge**. Die tatsächliche Quelle darf serverseitig für SL/Audit bekannt bleiben, ohne sofort allen Empfängern offengelegt zu werden.
- **Wiederholte Täuschungsversuche:** Eine kopierte oder wiederholt versandte manipulierte Botschaft ist nicht automatisch ein neuer gültiger Weltzustand; zusätzliche Replay-, Duplikations- und Spam-Schutzregeln aus 02.13/02.35/02.57 gelten. Nur ausdrücklich erlaubte neue Aktionen/Versuche erzeugen neue mögliche Effekte.
- **Regelwerks-/Settingbindung:** Fantasy kann z. B. einen abgefangenen Botenbrief oder einen magischen Boten behandeln; moderne/Science-Fiction-Szenen Funkverkehr und technische Terminals; Horror/Steampunk ganz andere Kommunikationsfähigkeiten. **Keine universelle Kryptografie-, Funkhacking-, Zauber- oder Voice-Erkennung wird vorausgesetzt.** Nur passende in Spielwelt/Regelprofil vorhandene Mechaniken sind nutzbar.
- **Spielleiterkontrolle:** Der SL darf solche Spielaktionen gemäß Kampagnenrollen/Freigaben einsetzen oder nach den gültigen Regeln zulassen. **Manuell gespielte NPCs** manipulieren keine fremde Kommunikation von selbst, **automatisch gesteuerte NPCs** nur nach expliziten passenden Regeln, und **bestätigungspflichtige NPCs** erst nach tatsächlicher SL-Genehmigung (02.54). Auch Spielercharaktere brauchen jeweils die im Regelprofil vorgesehenen Fähigkeiten und eine servervalidierte Aktion; die bloße Benutzerrolle erlaubt keinen ungeprüften Zugriff auf Daten oder Serverrechte.

### 2. Zusammenhang mit Nachrichtenzustellung, Wissen, Alarm und Sichtbarkeit

- **Wahrnehmung vor Informationsgewinn:** Ein erfolgreicher Abhör-/Abfangversuch bedeutet lediglich eine **regelgerecht erworbene Teil- oder Vollinformation**. Ob der Akteur Inhalt und Absender korrekt erkennt, hängt vom Kanal und dem später zu planenden Verifikations-/Verständnisprofil ab. **Fehlgeschlagene Versuche** erzeugen keine heimliche Erkenntnis.
- **Absender und Echtheit nicht gleichsetzen:** `claimedSender` bzw. ein sichtbares Rufzeichen darf vom authentischen Auslöser abweichen. Empfänger **müssen nicht automatisch** bemerken, dass eine Nachricht gefälscht ist; sie dürfen aber auch nicht allein durch eine behauptete Identität zusätzliche technische Rechte oder echtes Weltwissen erhalten. **Wie sie Täuschungen erkennen und welche Vertrauensprüfung gilt, entscheiden wir gesondert in 02.59.**
- **Nachrichtenlaufzeit (02.57):** Abhören/Manipulieren darf nur in einer **fachlich gültigen Phase** erfolgen. Eine bereits zugestellte Nachricht wird durch nachträgliches Blockieren nicht ungeschehen gemacht; bei ausstehenden, verzögerten oder erneut versuchten Zustellungen muss der gültige Zeitpunkt und die Zielgruppe erneut geprüft werden. Eine manipulierte Nachricht, die nicht zugestellt wird, darf keinen Empfängerwissen-Eintrag auslösen.
- **Empfängerspezifische Zustellung:** Bei Teilgruppen können Empfänger **verschiedene Nachrichtenversionen** erhalten oder ein Teil erhält gar nichts. Jede tatsächliche Version muss zugelassen, nachvollziehbar und genau einmal wirksam zugestellt sein. Ursprüngliche Sender-/Empfängerlisten, unfreigegebene Inhalte und genaue verdeckte Quellorte bleiben geschützt.
- **NPC-Wissen und Verdacht:** Ein NPC kann aufgrund einer zugestellten **glaubhaft wirkenden falschen Information** eine falsche Vermutung bilden, sofern seine Regeln aus 02.55 dies erlauben. **Eine manipulierbare Nachricht darf nicht direkt den tatsächlichen verborgenen Tokenstandort, die reale Fraktionszugehörigkeit oder die echten Spielweltfakten ändern.** NPCs sind nicht automatisch allwissend; Wissen, Vermutung, technischer Sensoralarm und tatsächliche Aktion bleiben getrennt.
- **Node-/Alarm-Pfade:** Eine gefälschte Warnung kann einen passenden **typisierten Kommunikations-/Alarm-Eingang** nur dann erreichen, wenn Manipulationsaktion, Kanal, Porttyp, Quelle, Berechtigung und nachgelagerte Node-Regel gültig sind (02.20/02.48). **Spoofing einer Spielweltidentität ist kein Umgehen der Serverautorisierung**. Keine frei geschriebenen Nachrichtentexte als beliebig ausführbarer Code und keine unkontrollierten Node-Kaskaden.
- **Spielerrechte und Fog:** Der Server darf für erlaubtes Mitlesen nur den tatsächlich freigegebenen inweltlichen Nachrichteninhalt oder ein passendes geschütztes Fragment ausliefern. Die internen Originalereignisse, echte Absenderkoordinaten, versteckte NPC-Daten, SL-Protokolle und nicht autorisierte Empfängernachrichten bleiben auf dem Server und beim berechtigten SL. Eine Fälschung enthüllt nicht heimlich verborgene Quellen oder das hinter Fog liegende Kartenbild.

### 3. Technischer Umsetzungsentwurf (noch keine feste API)

1. **Profil und Fähigkeitsprüfung:** Ein konzeptionelles `CommunicationInterferencePolicy` bzw. `InterceptionCapability`-Modell definiert zulässige Manipulationsaktionen **pro Kanal/Regelprofil/Objekt/Region/Akteur**, notwendige Fähigkeiten/Geräte, eventuelle Probe, Sender-/Zielbedingungen und vererbbare Kampagnenstandards mit markierten Overrides nach 02.25. Keine realen Netzwerkkontrollrechte aus einer Spielweltfähigkeit ableiten.
2. **Autoritativer Manipulationsversuch:** Ein `CommunicationInterferenceAttempt` (Name beispielhaft) referenziert den gültigen Kommunikationsvorgang 02.56–02.57, Akteur/Fähigkeit, ausdrücklich gewählte Operation (z. B. `observe`, `suppress`, `reroute`, `alter`, `impersonate`), Zeitpunkt/Runde, benötigte Regelprüfung und eindeutige ID. Der Server prüft vor Erfolg und Wirkung tatsächliche Spielberechtigung, Kanalverfügbarkeit, Fähigkeiten, Rechte und relevante Geheimnisse. **Ein fehlgeschlagener Versuch verändert den Nachrichtenweg nicht.**
3. **Original und wirksamer Inhalt getrennt:** Ein ursprüngliches `CommunicationEvent` bleibt für die serverseitige Ursachen-/Audit-Kette **unverändert**. Die Folge der erfolgreich autorisierten Manipulation kann **je Empfänger eine zulässige Transport-/Inhaltsvariante** erzeugen, mit Originalevent-Referenz, tatsächlichem/behauptetem Absender, veränderten Nutzdaten, wirksamen Empfängern und Manipulationsherkunft. Unberechtigte Clients erhalten weder die interne Originalreferenz noch den wahren Täter durch eine unsichtbare Payload.
4. **Anbindung an 02.57:** Nach einem Eingriff wird für betroffene Empfänger der **wirksame Zustellplan** nach den gültigen Verzögerungs-, Unterbrechungs-, Ablauf- und Retry-Regeln neu geprüft. **Nur eine erfolgreiche tatsächliche Zustellung** erzeugt ein empfängerbezogenes Wissensupdate; blockierte/abgelaufene Nachrichten nicht. Unterschiedliche legitime Empfänger dürfen ungleiche Inhalte erhalten; pro tatsächlich zugestellter Version idempotente Wirkung sicherstellen.
5. **Reaktion erst nach Empfang:** Ein empfangender NPC behandelt erhaltene Inhalte nach seinen vorhandenen Wissens-/Wahrnehmungsregeln und späteren Echtheits-/Vertrauensprüfungen (02.59). Seine allgemeine Steuerung nach 02.54 und Verdachtsphasen nach 02.55 können danach eine Änderung zulassen – nicht automatisch durch die Manipulation selbst.
6. **Kontrollierte Rechte und Schutz:** Strikt zwei Ebenen unterscheiden: **Spielweltberechtigung**, einen Funkspruch/Brief/Alarm zu beeinflussen, und **technische Autorisierung**, auf Serverdaten, Node-Ports, Nutzerkonten und Geheimnisse zuzugreifen. Selbst eine erfolgreich dargestellte Identitätstäuschung kann keine technische Adminrolle, ungeschützte Datenbankabfrage oder privilegierte Node-Ausführung schaffen. Alle externen Inhalte/Ereignisse typisiert validieren.
7. **Ereignis- und Replayschutz:** Stabile Ursprungs-/Versuchs-/Varianten-/Zustellungs-IDs, einmalige Wirkung pro gültiger Empfänger-Zustellung, begrenzte Wiederholung, Konfliktauflösung nach 02.35 sowie Loop-/Rate-Limits gegen endlose Alarm-, Täuschungs- oder Weiterleitungsketten. Alle zeitlich relevanten Regeln weiterhin getrennt in Echtzeit oder Spielrunden auswerten.
8. **SL-Debug und Tests:** Berechtigter SL kann Sender, ursprüngliche und tatsächlich zugestellte Version, Manipulationsversuch/Grund, Probe, nur für Empfänger freigegebene Anzeige, Zustellstatus und getrennte Folge-NPC- und Node-Ereignisse nachvollziehen. Isolierte Tests nach 02.31–02.34 dürfen keine echten Nachrichten, NPC-Zustände, Türen oder Alarm-Nodes verändern.

### 4. Prüffälle für die spätere Umsetzung

- **Mithören eines Rufes:** Eine Figur darf eine fremde Warnung nur hören, wenn die akustische Erfassung und die jeweilige Erlaubnis zutreffen. Damit ist **nicht** automatisch jeder geheime Empfänger, die genaue Quellposition oder die Sprache bekannt.
- **Funkwarnung umlenken:** Ein gültiger Eingriff führt nur dann zu einer anderen Empfängergruppe, wenn Kanal-/Akteurs-/Zielregeln passen. Nicht berechtigte Spieler erhalten keine internen Funk- oder NPC-Metadaten.
- **Gefälschte Absenderkennung:** Ein NPC erhält gegebenenfalls eine falsche, aber regelgerecht zugestellte Warnung mit **behaupteter** Absenderidentität. Der Server führt den tatsächlichen Ursprung geschützt; NPC-Erkennung/Vertrauen wird **nicht automatisch** vorentschieden, sondern in 02.59 geplant.
- **Blockierte Nachricht:** Ein Ziel bleibt uninformiert; andere nach eigener Zustellprüfung erreichte Ziele behalten ihre gültig zugestellte Nachricht. Blockieren nach tatsächlicher Zustellung löscht kein bereits erworbenes NPC-Wissen.
- **Node-/Alarm-Sicherheit:** Eine gefälschte In-Game-Meldung kann nicht ohne gültigen typisierten Port, berechtigte Automationsquelle und Rechteprüfung einen beliebigen Kampagnenalarm oder eine gefährliche Tür betätigen.
- **Automatik/SL-Freigabe:** Ein manuell kontrollierter NPC sendet/manipuliert nichts selbsttätig; ein NPC im SL-Bestätigungsmodus wirkt erst nach echter Bestätigung. Sonst identische gültige Kanalregeln.
- **Retry und Doppelwirkung:** Unterbrochene/manipulierte Funknachrichten werden gemäß 02.57 genau einmal wirksam zugestellt, ohne doppelte NPC-Wachsamkeit oder Kaskaden.
- **Informationsschutz:** Spieler erhalten nur tatsächliche erlaubte Abhörergebnisse; Hintergrunddaten wie echte geheime Senderkoordinaten und vollständige SL-Kommunikationslogs bleiben verborgen.

**Noch offen:** Konkrete Abhör-/Manipulationsfähigkeiten und Probenwerte, Zeitfenster für Eingriffe, Entdeckung von Fälschungen, Absenderverifikation, notwendige Sprachen/Geräte, Falschinformationen und NPC-Vertrauensstufen, partielle Informationsgewinnung, genaue Kollision mehrerer Manipulatoren und Offline-/Pausen-Semantik. Der Kampagnenassistent und vollständige Ein-/Ausschaltregeln für **andere** Featurebereiche bleiben bis nach dem gesamten Workshop aufgeschoben.

## 02.59 – Konfigurierbare Echtheits- und Vertrauensprüfung (12.10.2026)

**Beschlossen: Variante C.** Der Spielleiter darf je **Kampagne, Kommunikationsweg, Fraktion, NPC-Vorlage, Gruppe und Einzel-NPC** festlegen, wie die Glaubwürdigkeit und behauptete Absenderidentität einer empfangenen Nachricht beurteilt wird. Je passendem Regel-/Settingprofil darf ein vertrauter Absender **ohne neue Probe** akzeptiert werden oder eine **passive/aktive Prüfung**, ein Kennwort bzw. Codewort, ein bekanntes Erkennungszeichen, eine Rückfrage, eine technische/magische Authentifizierung oder ein **ausdrücklicher SL-Entscheid** erforderlich sein. **Keine generelle Pflichtprüfung und keine automatische Entdeckung aller Fälschungen.** Globale Standards und gekennzeichnete Ausnahmen mit Vorschau/Bestandsschutz nach 02.25. Dieser Beschluss betrifft die Fachplanung, nicht eine bereits implementierte Funktion.

### Anforderungen und Integrationen

- **Empfang, Behauptung, Prüfung, Glauben und Reaktion getrennt:** Eine nach 02.56–02.57 zugestellte Nachricht kann einen echten technischen Ursprung, einen inweltlich **behaupteten** Absender, eine nach 02.58 manipulierte Inhaltsversion sowie eine vom NPC angenommene Identität besitzen. Ein NPC kann die Nachricht glauben, ablehnen oder für ungewiss halten; eine dadurch ausgelöste Veränderung von NPC-Wissen/Alarmbereitschaft nach 02.54–02.55 ist eine **eigene regelvalidierte Folgeaktion**. Geglaubter Inhalt ist nicht automatisch objektiv wahr.
- **Kanal- und Fähigkeitsabhängigkeit:** Sichtzeichen, Stimme, Funkrufzeichen, Rückruf, persönliches Kennwort, technische Prüfung und magische Identifikation gelten nur dort, wo passende Kanal-/Geräte-/NPC-Fähigkeiten und aktive Regeln sie tragen. Spielwelt-Identitätstäuschung gewährt **niemals technische Serverrechte**, Zugriff auf geheime Daten oder beliebige Node-/Tür-/Alarm-Aktionen.
- **Optionale Prüfungen:** Passive Erkennung, gezielte Nachfrage und regelprofilabhängige Würfelproben werden serverautoritativ geprüft. Die konkrete Art, Schwellen, Dauer, Wiederholungen und Aufbewahrung von Ergebnissen bleiben offen; keine D&D-spezifischen Pflichtwerte. **Korrekt, falsch, abgebrochen, unbestimmt und zeitlich abgelaufen** sollen für geeignete Node-/Dialogprüfungen unterscheidbar bleiben, ohne feste Node-Portnamen vorwegzunehmen.
- **Geheimnisschutz:** Nur der berechtigte Spieler/NPC bekommt die tatsächlich freigegebene Nachricht bzw. Antwort. Geheime Passwörter, interne Prüfungsschwellen, echte verdeckte Absender- und NPC-Positionen bleiben serverseitig. Ein als Kommandant getarnter Spieler kann nur die **inweltliche** Nachricht manipulieren, keine serverseitige Autorisierung.
- **NPC-Grundsteuerung bleibt verbindlich:** Manuell gespielte NPCs entscheiden nicht autonom über neue Gespräche oder Aktionen; NPCs im Bestätigungsmodus benötigen SL-Freigabe. Eine positive Vertrauensprüfung öffnet selbst noch keine Tür, alarmiert keine Wache und spawnt keine Figur: nur der **explizite, autorisierte Node-Graph** kann nach seinen typisierten Ports entsprechende Aktionen auslösen.
- **Diagnose und Abnahme:** Berechtigter Debugger und isolierte Tests zeigen wirklichen Ursprung, behaupteten Absender, Zustellung, wirksame Vertrauensregel, Prüfergebnis und davon getrennte NPC-/Node-Folgen. Fälle: bekannte/fremde Stimme, gültiges/falsches Kennwort, erkannte/nicht erkannte Fälschung, abgebrochene Verbindung, verdeckte Position, manuell/automatisch/SL-bestätigter NPC. Kein mehrfaches Auslösen durch Replay/Retry.

### Zusätzlich vom Projektinhaber für spätere Detailplanung vorgemerkt – Telefonnetz und neue Nodes

**Dieser Anwendungsfall ist ausdrücklich für später notiert.** Es wird jetzt **noch kein vollständiges Telefon-/Dialog-/Spawn-UI und keine Implementierungsphase beschlossen**. Die Funktion muss später über dieselben frei kombinierbaren **typisierten Node-Graphen** nach 02.13–02.20, 02.31–02.35 umsetzbar sein – nicht nur durch ein festes Telefonskript.

- **Vernetzte Telefone:** Spielleiter können Telefonobjekte mit eigener Position, Objekt-/Node-ID und **konfigurierbarer Verbindung zu anderen Telefonen** in ihren Szenen platzieren. Ein Spieler darf ein Telefon z. B. **im Büro einer Wache** gemäß geltender Reichweite/Berechtigung bedienen und sieht eine **Liste der für ihn freigegebenen, anwählbaren anderen Telefone** im passenden Netz. Ein geheimes Telefon oder Ziel darf nicht allein wegen der Netztopologie unberechtigt offengelegt werden.
- **Anrufen als Ereignis:** Die Auswahl eines Zieltelefons löst nach Serverprüfung einen **typisierten Anruf-/Wähl-Ereignisimpuls** aus. Geräte, Kanal, Erreichbarkeit, Verzögerung, Verbindung, Störung und gegebenenfalls Gesprächsstatus müssen mit 02.56–02.57 vereinbar sein; ein fehlgeschlagener Anruf darf keine angenommene Gesprächsverbindung vortäuschen. Ausgehende/ankommende Telefon-Nodes können frei mit anderen passenden Nodes verbunden werden.
- **Text- und Dialog-Nodes:** Während eines gültigen Gesprächs kann ein Node einen Text oder eine Antwort für den berechtigten Anrufer ausgeben, Spieler-Eingaben entgegennehmen und typisierte Ereignisse auslösen. **Beispiel:** Eine angerufene Wache antwortet **„Wer sind Sie? Wachen!“**. Der Spielleiter darf diesen Ausgang **mit einer gesonderten Spawn-Node** verbinden.
- **Eigenständige Spawn-Node:** Die **Spawn-Node** ist ein wiederverwendbarer, separat verkabelbarer Node-Typ mit **Auslöser-Eingang, wählbarer Zielszene, einer oder mehreren Spawnpositionen und der Auswahl des zu spawnenden Inhalts aus einer Liste/Vorlagenbibliothek**, einschließlich der Anzahl. Beispiel: **zwei Wachen** aus ausgewählter NPC-Vorlage an vorgegebenen Punkten in der Szene platzieren. Weitere spawnfähige Objektarten und ihre Vorlagen werden später spezifiziert. Spawn muss serverseitig Rechte, Szenenzugehörigkeit, verfügbare Positionen/Kollision, Sicherheits-/Sichtregeln und Idempotenz prüfen: keine mehrfach erzeugten Wachen durch doppelte Netzwerknachrichten oder Node-Schleifen.
- **Passwort- und Verzweigungs-Nodes:** Angerufener fragt per Dialog-Node nach einem Passwort. Spieler gibt eine Antwort ein; eine **serverseitige, geheime Prüf-/Bedingungs-Node** vergleicht sie nach den passenden Zugangscode- und Fehlversuchsregeln aus 01.10–01.16. **Richtig → passend verbundene Tür-Node öffnet die Tür. Falsch → Telefon-/Auflegen-Node beendet den Anruf.** Die genauen Portnamen, Sicherheitsfristen, Falscheingabe-/Wiederholungslogik, Rechte und Zeitlimits werden später ausgearbeitet.
- **Freie Kombination:** Telefon-, Textausgabe-, Dialog-/Eingabe-, Passwort-/Vergleichs-, Alarm-, Spawn-, Tür- und Auflegen-Nodes bleiben voneinander getrennte, wiederverwendbare Bausteine. Eine Alarm-Node kann alternativ Wachen warnen, eine Spawn-Node auf andere autorisierte Ereignisse reagieren, ein Passwort einen anderen Effekt auslösen. Über Szenengrenzen gelten die bestehenden kampagnenweiten Node-Verbindungen; die Spielleitung darf echte Spielweltfolgen nach ihren Berechtigungen testen/debuggen.
- **Keine voreilige Festlegung:** Telefon-Verzeichnis und Sichtbarkeit, Leitungs-/Sitzungsmodell, automatische NPC-Dialoge, Telefonnetz-Topologie, verfügbare Spawnarten, platzierbare Spawnpunkte, Konflikt-/Schutzregeln und endgültige Editoroberfläche bleiben für die jeweiligen späteren Featurefragen offen. Diese Beispiele sind **als konkrete Anforderungen vorgemerkt**, keine fertigen Implementierungen.

## 02.60 – Flexible Sprachen, Codes, Übersetzung und teilweise Verständlichkeit (12.10.2026)

**Verbindlich beschlossen: Variante C.** Kommunikation in AdventureShift kann je Kampagne/Setting und Regelprofil **automatisch verständlich, nach Sprach-/Codekenntnis prüfbar oder nur teilweise verständlich** sein. **Sprachen, Schrift-/Zeichensysteme, Codes, technische Übersetzer, magische Übersetzung, andere ausdrücklich modellierte Hilfsmittel und bei Bedarf regelprofilabhängige passive/aktive Proben oder SL-Freigaben** können bestimmen, welche Information ein Spielercharakter, NPC oder anderer berechtigter Empfänger aus einer Nachricht gewinnt. **Globale Kampagnenstandards und markierte Ausnahmen** für Figuren-/NPC-Vorlagen, einzelne Figuren, Kommunikationswege, Nachrichtentypen und geeignete Szenen/Regionen vorsehen (Bestandsänderung/Overrides nach 02.25). Keine universelle Pflichtsprache, kein D&D-spezifisches Attribut und **keine automatische Übersetzung allein weil der Server einen Text kennt**. Der Beschluss ist eine **Featureanforderung, keine implementierte Sprachverarbeitung oder echte maschinelle Übersetzung**.

### 1. Fachliche Ebenen und Verständnisprofile

- **Nachricht empfangen ≠ verstehen ≠ glauben ≠ handeln:** Der Kommunikationsweg/Transport (02.56–02.57) entscheidet über den Empfang, Abhören/Manipulation (02.58) über eine möglicherweise wirksame Nachrichtenversion, **02.60 über verständliche Inhalte**, 02.59 über Echtheit/Vertrauen und 02.54–02.55 über später zulässige NPC-Reaktionen. Die genaue Reihenfolge nach einer Rückfrage kann je Regelprofil variieren, aber kein Schritt darf unberechtigte Informationen als bereits verstanden oder wahr markieren.
- **Sprach-/Schrift-/Codekenntnis:** Sprachkenntnisse oder Verständniseigenschaften sind **nur dann** vorhanden, wenn sie durch das konfigurierte Charakter-, NPC- oder Regelprofil tatsächlich definiert werden. Spoken Language, Schrift/Symbole, Gebärden, Zeichencodes und technische Kommunikationsformate dürfen als verschiedene geeignete Kompetenztypen behandelt werden. Ein gesprochener Ruf erfordert weiterhin die passende akustische Wahrnehmung, ein geschriebenes Zeichen geeignete Sicht/Interaktion.
- **Einfache Sandbox-Variante:** Eine Kampagne ohne besondere Sprachregeln darf Nachrichten als verständlich behandeln. In anderen Settings können Sprachen oder Codes streng geprüft oder teilweise erschließbar sein. Kampagne, einzelne Kommunikationskanäle und Figuren dürfen die wirksame Einstellung gemäß 02.25 überschreiben, ohne andere Wahrnehmungs- oder Rechteprüfungen abzuschalten.
- **Abgestuftes Teilverständnis:** Ein Empfänger kann gemäß gültigen Regeln **keine Information**, **nur ausgewählte Wörter/Fragmente**, **ungefähren Sinn** oder **vollständige inhaltliche Verständlichkeit** erhalten. Diese Beispiele definieren **keine erzwungene numerische Verständnisskala**. Welche Fragmente oder Bedeutungen ersichtlich werden, muss durch explizite Inhalte/Regelprofile, SL-Freigaben oder eine passende validierte Probe bestimmt sein; **keine erfundene KI-Interpretation eines unbekannten Textes**.
- **Übersetzer und Sonderfähigkeiten:** Ein vorhandenes Gerät, eine magische Wirkung, Dolmetscher, Lesefähigkeit, unterstütztes Modul oder ein anderes geeignetes Spielweltmittel kann nach eigenen Bedingungen die Verständlichkeit verändern. Voraussetzung können Ausstattung, Aktivierungszustand, Ziel, Wirkungslaufzeit, Kosten, Reichweite und vorhandene Übersetzungsdefinitionen sein, **soweit das jeweilige Modul diese tatsächlich bereitstellt**. Nicht automatisch jedes Wort in beliebiger Sprache entschlüsseln oder technische Verschlüsselung brechen.
- **Optionaler regelprofilabhängiger Test:** Bei teilweise bekannter Sprache, fremdem Dialekt, undeutlichem Funk, Schrift-/Codeanalyse oder anderen geeigneten Fällen darf ein vorhandenes Modul passive Kenntnisprüfung, aktiven serververbindlichen Würfelwurf oder einen SL-Entscheid ausführen. **Wahrnehmung, Übersetzung/Interpretation und Echtheitsprüfung können verschiedene Proben sein**. Die konkreten Schwellen, Erfolgsstufen, Wiederholungsregeln und Standardwerte werden später bestimmt.
- **Falsche bzw. absichtlich verschleierte Information:** Ein Empfänger kann einen Inhalt sprachlich verstehen und dennoch eine Fälschung nach 02.58/02.59 glauben. Umgekehrt kann er einen Absender wiedererkennen, obwohl er dessen Aussage nicht versteht. Die echte Spielweltquelle, der geglaubte Inhalt und der verstandene Inhalt sind **voneinander unabhängig**.
- **Empfängerspezifisch:** Zwei Spieler können denselben Funkspruch oder Schrifttext unterschiedlich weit verstehen; passende Berechtigungen und ggf. SL-Entscheid steuern, wer welche Übersetzung/Fragmente sieht. Empfänger dürfen ihre gewonnenen Informationen später gemäß 02.56 weitergeben, dabei aber **nicht automatisch mehr semantische Details übertragen als sie selbst begründet verstanden haben**.

### 2. Konzeptionelle technische Umsetzung

1. **Kanonischer Nachrichteninhalt:** Ein `CommunicationEvent` enthält nur serverseitig eine erlaubte inweltliche Inhaltsreferenz, Quell-/Kanal-/Sprach- bzw. Codesystemkennung, ggf. definierte **semantische Fragmente** und passende Metadaten. Tatsächlich zugestellte/manipulierte Versionen nach 02.58 bleiben getrennt vom Original; die tatsächliche semantische Information darf bei Fälschung abweichen. Die folgenden Bezeichner sind nur Datenmodellvorschläge.
2. **`ComprehensionProfile` und `ComprehensionResolver`:** Konzeptionell versionierbare Regeldefinitionen für Kampagne/Charakter/NPC, bekannte Sprachen/Schrift-/Codesysteme, erlaubte Übersetzungshilfen, gültige Fähigkeiten und Ausnahmequelle; die serverseitige Prüfung erzeugt aus der **tatsächlich zugestellten Version** und vorhandenen Empfängerfähigkeiten ein empfängerbezogenes `ComprehensionResult` (nur Platzhalterbegriff). Ein optionaler Würfel-/SL-Entscheid ist mit eindeutiger Prüfung und Berechtigung verknüpft.
3. **Separate Daten-/Wissensstufen:** Der Resolver darf *nur* verständliche, vom Empfänger legitim erworbene Information freigeben; eine noch nicht verstandene Nachricht verleiht weder verborgenes Wissen noch automatisch einen glaubhaften Handlungsbefehl. Die Vertrauensauswertung 02.59 und NPC-Wissens-/Wachsamkeitsverarbeitung 02.54–02.55 erhalten nur dafür geeignete Fakten/Hypothesen und bleiben eigene fachliche Schritte. Fehlende Sprachkenntnis verhindert jedoch **nicht automatisch** das Erkennen eines Alarmtons oder anderer nonverbaler Ereignisse, sofern es ein gültiges separates Profil vorsieht.
4. **Gefilterte Client-Ausgabe:** Das Backend erzeugt pro Spieler **nur erlaubte sichtbare Originalzeichen, freigegebene Fragmente, Zusammenfassung oder Übersetzung**. Unverstandener Inhalt darf als nicht interpretierbare Zeichen/Platzhalter erkennbar sein, **aber kein geheimes Klartext-Payload oder versteckte Übersetzungsdaten dürfen an nicht berechtigte Browser übertragen werden**. Fog, Original-/Absendergeheimnisse, SL-Notizen und geheime Codes sind weiterhin geschützt. In einer Spielleiter-Vorschau ist die tatsächliche Empfängeransicht prüfbar.
5. **Telefon-/Passwort-/Dialogbezug:** Die in 02.59 für später vorgemerkten Telefon-/Text-/Dialog-/Passwort-Nodes können eine Sprache oder Codeart tragen, ohne selbst eine vollständige Sprach-KI zu benötigen. Eine **korrekt eingegebene, serverseitig geprüfte Passwortzeichenfolge** (01.10–01.16, 02.59) ist **nicht** automatisch dasselbe wie eine Sprachverständnisprobe; die Wahl, ob ein fremdsprachiger NPC überhaupt eine Passwortfrage verständlich stellen kann, bleibt eine gültige Dialog-/Verständnisregel. **Richtig → Tür-Node, falsch → Auflegen-Node** gilt nur bei autorisierter Verbindung und ist kein generischer Sprachautomatik-Effekt.
6. **Zeit, Persistenz und Tests:** Temporäre Übersetzungshilfen besitzen, sofern vorgesehen, eigene regelprofilabhängige Dauer und Auslösung in Echtzeit oder Spielrunden ohne Umrechnung (02.15–02.16); diese Detailwerte bleiben offen. Verständnisergebnisse sind je Nachrichtenvariante, Empfänger und Regelversion nachvollziehbar und idempotent, sodass Reconnect/Retry keine Mehrfachwürfe oder unerlaubtes Lernen verursacht. Berechtigter SL-Debug und isolierte Tests unterscheiden Lieferstatus, Sprach-/Codefähigkeit, Übersetzungsquelle, aktive/passive Probe, freigegebenes Verständnis, Trust-Ergebnis, NPC-Reaktion und Node-Output.

### 3. Abnahmeszenarien (spätere Implementierung)

- Zwei Figuren hören denselben gültigen Ruf; nur eine kennt die verwendete Sprache. Die andere hört nach 02.53 einen Ruf, erhält aber **nicht automatisch den Inhalt**. Bei geeigneter konfigurierter Regel bekommt sie einzelne Wörter oder den ungefähren Sinn.
- Eine Figur liest unbekannte Schrift und darf optional Zeichen erkennen, ohne den geheimen Klartext zu bekommen. Ein geeignetes Übersetzungsgerät kann nach gültiger Nutzung zusätzliche Teile freigeben; die Client-Netzwerkdaten enthalten zuvor keine versteckte Übersetzung.
- Ein regelgerecht übersetzter Funkruf wird trotzdem als möglicherweise gefälscht geprüft (02.59); Verständnis und Vertrauen bleiben unabhängig.
- Bei einer Kampagne ohne Sprachkomplexität ist allgemeine Verständlichkeit als Standard zulässig; eine bestimmte NPC-/Kanal-Ausnahme kann Codes oder Sprachkenntnisse verlangen. Eine einzelne Änderung darf die ursprüngliche Kommunikation und andere Empfänger nicht rückwirkend entstellen.
- Ein Spieler verwendet das vorgemerkte Telefon und erhält eine Dialogfrage in gültiger Sprache; eine korrekte Passwortantwort wird **erst durch die eigenständige sichere Prüf-Node** zur erlaubten Türöffnung. Ein falsches Passwort kann über eine andere Kante das Auflegen bewirken; die bloße Darstellung erzeugt keine Spawn-/Tür-Wirkung.
- Ein manipulierter Nachrichtentext und eine wiederholte Zustellung liefern nur das jeweils zulässige **Empfänger-Verständnisergebnis**; fremde Übersetzungen, versteckte Originale und SL-Geheimnisse werden nicht übertragen.

**Weiter offen:** Konkretes Sprachen-/Schriftsystem und Charakterbogenfelder (Feature 03), Code- und Übersetzungsmechaniken (Regelprofil 07), partielle Verständnisskalen, Sprachlernen und Gedächtnisdauer, Dialekte/Gebärden-/Bildzeichenfähigkeiten, Sprach-/Text-UI und Ziel-/Übersetzungsbibliotheken. Es ist **kein generelles Voice-to-Text oder Live-Übersetzungsmodell beschlossen**. Telefon-, Dialog- und Spawn-Nodes aus 02.59 bleiben für die spätere passende Detailplanung vorgemerkt. Der vollständige Kampagnenassistent und das vollständige Abschalten weiterer Featurebereiche bleiben bis nach der Gesamt-Featureplanung aufgeschoben.

### Verbindlicher Nutzerzusatz zu 02.60 – Sprachen sind erlernbare und verbesserbare Skills

**Sprachen sind Fertigkeiten im selben übergreifenden Skillsystem wie etwa Schießen oder Nahkampf.** Sie können einem Charakter oder NPC nach den geltenden Regeln **beigebracht, zugeordnet und verbessert** werden. Eine einzelne Sprache ist keine universell angeborene, starre Ja/Nein-Eigenschaft, sofern das gewählte Regelprofil abgestufte Kenntnisse unterstützt. **Welche Skillstufen, Lernkosten, Trainingszeiten, Erfahrungspunkte, Steigerungsvoraussetzungen oder Probenformeln gelten, wird ausdrücklich erst bei den allgemeinen Charakter-/Skill- und Regelmodulen (03/07) entschieden**; es werden hier keine fixen Zahlen erfunden.

- **Kampagnenweites Sprachmenü:** In einem eigenen **Sprachmenü** können berechtigte Kampagnenverantwortliche/Spielleiter **Sprachen hinzufügen und verwalten**. Eine so angelegte Sprache wird im **gemeinsamen Sprach-/Skill-Katalog dieser Kampagne** verfügbar und kann von den dafür berechtigten Figuren-/NPC-/Vorlagensystemen als Fertigkeit referenziert werden. **Nicht** automatisch in alle anderen Kampagnen übertragen und **nicht** automatisch allen Charakteren beigebracht.
- **Individuelle Beherrschung:** Jeder Charakter/NPC besitzt – soweit zugewiesen – einen **eigenen Fortschritt/Beherrschungsstand** für jede Sprache, nicht bloß ein kampagnenweites Flag „spricht Sprache“. Die Beziehung **Kampagnensprache als Definition** versus **Charakter-Skill-Wert als Instanz** ist getrennt. Auch verschiedene Figuren derselben Kampagne dürfen unterschiedliche Sprachstände besitzen.
- **Steigerung wie andere Fertigkeiten:** Die Sprachfertigkeit soll **dieselben konfigurierbaren Steigerungs-/Skillregeln** benutzen können, die später auch für Schießen, Nahkampf oder andere Fähigkeiten gelten. Teilverständnis, sichere Verständlichkeit, Lese-/Schreibfähigkeit oder Übersetzungseignung dürfen sich **regelprofilabhängig** aus dem wirksamen Skillwert und ggf. definierten Hilfsmitteln ergeben; diese Teilaspekte nicht ohne späteren Beschluss zu festen Pflicht-Unterfertigkeiten machen.
- **Umgebung und Rechte:** Die Figur kann bei passendem Fortschritt mehr oder genauer verstehen. Der Server bestimmt mit dem auf die Figur bezogenen Skillwert und aktiver Regel, welche Inhalte aus 02.60 legitim verstanden wurden; **eine neue Sprache im Katalog darf keine geheimen Übersetzungen im Browser offenlegen**. Spieler dürfen nur auf Basis ihrer Rollen/Figurenrechte Skillwerte ändern oder eine zulässige Steigerungsaktion auslösen; die Spielleitung behält entsprechende Änderungsrechte.
- **Persistenz und Pflege:** Sprachdefinition mit stabiler ID sowie Skillzuordnungen/-fortschritte müssen pro Kampagne bzw. Figur speicherbar sein. Umbenennung/Deaktivierung/Löschen einer bereits verwendeten Sprache darf bestehende Charakterwerte, Vorlagen, NPCs oder Dialog-/Kommunikationsregeln **nicht unbemerkt zerstören**; Vorschau, Referenzen und Bestands-/Ausnahmenregeln aus 02.25 bei relevanten Änderungen einplanen.
- **Abnahmefälle:** (1) SL legt im Sprachmenü eine neue Sprache an; sie ist für die **Kampagne** auswählbar, aber nicht automatisch erlernt. (2) Zwei Figuren besitzen unterschiedliche Werte in derselben Sprache und verstehen ggf. verschieden viel. (3) Zulässige Verbesserung eines Sprachskills verändert nur den Wert der betreffenden Figur. (4) Bereits existierende Sprach-/Telefon-/Dialog-Nodes können auf die gemeinsame Sprachdefinition und die jeweiligen Skillwerte zugreifen, ohne geheime Inhalte offenzulegen. (5) Verändern der kampagnenweiten Sprachdefinition führt nicht zu stillschweigendem Verlust vorhandener Skillwerte.

**Prozessgrenze:** Mit diesem Nutzerzusatz ist die Funktion eines **Sprachmenüs zum kampagnenweiten Anlegen von Sprachen** ausdrücklich beschlossen. Die genaue Gestaltung/Position des Sprachmenüs, der gesamte Kampagnenerstellungsassistent und alle übrigen Modulabschaltungen werden wie in 02.48 vereinbart erst nach Abschluss der vollständigen Featureplanung festgelegt.

## 02.61 – Konfigurierbares NPC-Gedächtnis, Erinnern, Korrigieren und Vergessen (12.10.2026)

**Verbindlich beschlossen: Variante C.** NPCs, Gegner, Tiere und geeignete andere Figuren dürfen **dauerhafte, zeitlich begrenzte oder ereignisabhängige Erinnerungen** an tatsächlich erworbene Informationen, Vermutungen, Warnungen oder Begegnungen besitzen. Eine passende Regel kann eine Erinnerung durch neue Hinweise **verstärken, bestätigen, als widersprüchlich markieren, berichtigen, ersetzen oder vergessen lassen**. **Globale Kampagnenstandards sowie bewusste Ausnahmen pro NPC-Vorlage, Gruppe/Fraktion und Einzel-NPC** sind vorgesehen, mit Vererbungs-/Änderungsvorschau und Bestandsschutz aus 02.25. Gedächtnisfristen können entweder in **Echtzeit oder Spielrunden** geführt werden (02.15/02.16), ohne heimliche Umrechnung. Dies ist eine fachliche Festlegung, kein bereits implementiertes Gedächtnissystem.

### 1. Gedächtnisregeln und Gültigkeit

- **Dauerhaft:** Eine Erinnerung bleibt für die betreffenden NPC-Regeln gültig, bis sie durch einen eigens autorisierten SL-, Regel- oder Node-Eingriff ersetzt, berichtigt oder entfernt wird. „Dauerhaft“ ist keine Freigabe geheimer Daten an Spieler und bedeutet nicht, dass NPCs die gesamte Kampagnenwelt kennen.
- **Zeitlich begrenzt:** Nach einer konfigurierten Echtzeit- oder Rundenfrist kann eine Information gemäß Gedächtnisprofil an Stärke/Gültigkeit verlieren, in einen unsicheren Status wechseln oder vergessen werden. Keine universelle Zeit oder numerische Verfallsformel vorgeben.
- **Ereignisbezogen:** Neue gültige Wahrnehmung, eine tatsächlich erhaltene und verstandene Nachricht, bestätigende/widersprechende Evidenz oder eine berechtigte SL-/Quest-/Node-Aktion kann nach ausdrücklicher Regel eine Erinnerung erzeugen, aktualisieren, verstärken, korrigieren oder löschen. Wiederholte identische Netzwerkpakete dürfen keine unbegrenzte Gedächtnisstärkung erzeugen.
- **Informationsquelle und subjektiver Wahrheitsgrad:** Zwischen eigener Beobachtung, Hörvermutung, fremder Aussage, gefälschter Nachricht, geprüftem Hinweis und bloßer Schlussfolgerung unterscheiden. Ein NPC darf **Falsches glauben**; ein glaubhaft empfangener Funkspruch ist nicht automatisch objektiv wahr. Gültig erworbene grobe Richtungen/Regionen dürfen nicht in geheime exakte Spielerkoordinaten umgewandelt werden.
- **Neue Informationen und Widersprüche:** Zusätzliche legitime Hinweise können frühere Informationen bekräftigen oder ausdrücklich widerlegen. Ein Korrektureintrag muss den Bezug zum ursprünglichen Eintrag nachvollziehbar halten; ob ein NPC die Korrektur übernimmt, ergibt sich aus der gültigen Gedächtnis-/Vertrauensregel oder SL-Entscheidung. Die ursprünglichen historischen Ereignisse werden nicht rückwirkend gefälscht.
- **Lernen und Erinnern sind nicht dasselbe:** Fortschritt in einer Fertigkeit – etwa den kampagnenweit verfügbaren verbesserbaren Sprachskills aus 02.60 – bleibt ein anderes Daten- und Regelsystem als das Vergessen einer konkreten Unterhaltung oder Begegnung.
- **Nicht fraktionsweit geteilt:** Gedächtniseinträge gehören zu einem bestimmten NPC, nicht automatisch zu seiner gesamten Fraktion. Informationsaustausch funktioniert nur durch wirklich gültige Kommunikationswege aus 02.56–02.60 und die jeweils zulässigen Verständlichkeits-/Vertrauensprüfungen.

### 2. Verhältnis zu NPC-Zustand, Steuerung und Rechten

- **Gedächtnis ≠ Wachsamkeit:** Die Phasen normal/aufmerksam/sucht/alarmiert (02.55) beschreiben aktuelle Zustände, **nicht** die komplette Erinnerung des NPC. Eine Wache kann sich nach beendeter Suche beruhigen und sich dennoch an einen früheren Eindringling erinnern. Umgekehrt löst eine alte Erinnerung allein keinen neuen Alarm oder Angriff aus.
- **Erinnerung ≠ Wiedererkennen:** Eine frühere Begegnung als Erinnerung zu haben bedeutet **nicht automatisch**, einen später verkleideten oder anders aussehenden Spieler mit derselben Identität wiederzuerkennen. Die Wahrnehmungs-/Wiedererkennungsregel wurde in 02.62 als konfigurierbar beschlossen.
- **Steuerungsmodus bleibt wirksam:** Die allgemeine manuelle/automatische/SL-bestätigte NPC-Steuerung (02.54) bestimmt weiterhin echte NPC-Handlungen. Der SL darf bei einem manuell geführten NPC Erinnerungen nachvollziehen und berechtigt ändern. Ob automatische Gedächtnisänderungen auch bei manuell gesteuerten NPCs direkt oder nur nach Freigabe erfolgen, ist je Profil bzw. späterem Ablauf zu regeln; **kein unbemerkter automatischer Kampf oder Alarm** allein aufgrund der Speicherung.
- **Spielleiterzugriff:** Berechtigte Spielleiter können Erinnerungen und Herkunft einsehen, fehlerhafte Einträge korrigieren und gemäß Rechten vergessen lassen. Solche Eingriffe sind nachvollziehbar und müssen die tatsächliche Spielwelt von der subjektiven NPC-Erinnerung getrennt halten.
- **Akustik und Sensoren:** Bei deaktivierter akustischer Simulation (02.51) entstehen keine neuen automatisch akustisch abgeleiteten Gedächtniseinträge; bereits vorhandenes gültiges Gedächtnis und andere zulässige Wissensquellen bleiben unberührt. Technische Sensoralarm-Latches aus 02.44–02.47 sind keine NPC-Erinnerungen. Node-Folgeaktionen benötigen weiterhin eigene zulässige typisierte Verbindungen und Berechtigungen.

### 3. Technischer Entwurf (noch kein finales Schema)

1. **Pro-NPC Memory-Record:** Ein konzeptioneller `NpcMemoryRecord` enthält eine eindeutige ID, NPC-/Kampagnenbezug, Wissenskategorie, **nur tatsächlich bekannte oder geglaubte Information**, Informationsquelle/Provenienz (z. B. erfolgreiches `PerceptionResult`, tatsächlich zugestellte und verstandene Nachricht, SL-/Node-Ereignis), Sicherheits-/Glaubensstatus, Gültigkeitsregel, Erfassungs-/Änderungszeit bzw. Spielrunde und referenzierte Regelversion. Die konkreten Feldnamen sind lediglich Vorschläge.
2. **Policy und Resolver:** Eine versionierte `NpcMemoryPolicy` definiert Arten von Erinnerungen, erlaubte Auslöser, Ablauf-/Korrekturstrategien, Zeitbasen, Änderungsrechte und Defaults/Overrides. Ein serverautoritärer Resolver prüft neue legitime Informationen, Widersprüche, Fristwechsel, gezielte SL-Korrektur und Vergessen, ohne geheime tatsächliche Spielerdaten als NPC-Wissen bereitzustellen.
3. **Gedächtnisstatus getrennt vom Event-Log:** Vergessene oder als falsch markierte Informationen sind für NPC-Verhaltensregeln nicht mehr als gültige Erkenntnis zu behandeln. Ein berechtigtes Audit kann die historische Quelle weiterhin protokollieren; **inweltliches Vergessen bedeutet nicht automatisch Löschung aller technischen Auditdaten**. Datenschutz, Aufbewahrungsfristen und Bereinigungsregeln erst in den entsprechenden späteren Bereichen endgültig bestimmen.
4. **Zeitplanung und Persistenz:** Ablauf wahlweise in Echtzeit oder Spielrunden, mit stabilen Memory-/Timer-/Ereignis-IDs, Idempotenz und Versionierung. Zustände und wirksame Fristen müssen Reconnect und Neustart nachvollziehbar überstehen. Was bei Pause oder inaktiven Szenen passiert (02.19), wird nicht ohne weitere Entscheidung vorausgesetzt.
5. **Sichere Ausgabe und Nutzung:** Nur berechtigte SL erhalten interne NPC-Memory-Diagnose; Spieler sehen lediglich nach tatsächlicher Kommunikation/Sichtbarkeit erlaubte Hinweise. NPC-Verhalten darf nur noch gültige Erinnerungen im erlaubten Detailgrad abfragen, ohne verdeckte exakte Quellorte oder geheime Metadaten. Eventuell künftige `memoryAdded`-/`memoryCorrected`-/`memoryExpired`-Ports müssen explizit verbunden sein und dürfen nicht automatisch Alarm-Nodes/Spawn-/Tür-Nodes aktivieren.
6. **Tests:** Zwei NPCs mit unterschiedlichen Gedächtnisprofilen; dauerhafte vs. zeitlich befristete Erinnerung; neue bestätigende Beobachtung vs. doppelte Nachricht-Retry-ID; gefälschte Warnung mit späterer Korrektur; unbekannte Sprache erzeugt kein geheimes Klartextwissen; Alarmphase endet, Erinnerung bleibt; Reconnect/Neustart und Rechtefilter; alles im isolierten Debug-/Testlauf (02.31–02.34).

**Offen:** Konkrete Gedächtnisstärken und Zeitwerte, Konfliktstrategien, Kategorien, Umfang technisch aufzubewahrender Historie, Pausen-/Offline-/inaktive-Szenen-Semantik, Bedienoberfläche, Auswirkungen auf automatische Suche sowie die persönliche Wiedererkennung in 02.62. Der globale Kampagnenassistent und vollständig abschaltbare weitere Module bleiben bis nach dem gesamten Featureworkshop zurückgestellt.

## 02.62 – Konfigurierbare Wiedererkennung von Personen durch NPCs (12.10.2026)

**Verbindlich beschlossen: Variante C.** NPCs dürfen eine ihnen **tatsächlich bekannte oder zuvor legitimerweise wahrgenommene Person** anhand der in ihrem Gedächtnis vorhandenen Merkmale erneut erkennen oder sie nur für ähnlich/verdächtig halten. Das System berücksichtigt je gewähltem Kampagnen-/Regelprofil **Aussehen, Stimme, Kleidung, besondere Merkmale, frühere Begegnungen, verstrichene Zeit, Verkleidungen, Wahrnehmungsbedingungen und tatsächliche NPC-Fähigkeiten**. Eine passende Wiedererkennung kann **automatisch**, durch **passive oder aktive regelprofilabhängige Probe** oder **auf ausdrückliche Spielleiterentscheidung** erfolgen. **Globale Kampagnenstandards mit gezielten Ausnahmen** für NPC-Vorlagen, Gruppen, einzelne NPCs, Situationen oder passende Wahrnehmungskontexte, nach dem Bestands-/Overrideprinzip 02.25. Keine feste D&D-Probe, kein vorgeschriebener Prozentwert und keine automatische Unfehlbarkeit.

### 1. Was Wiedererkennung fachlich bedeutet

- **Erinnerung als Voraussetzung, nicht als Ergebnis:** Der NPC vergleicht die aktuell **legitim erkannten Merkmale** einer beobachteten Figur mit seinen gültigen Erinnerungsinformationen aus 02.61. Ein NPC, der nur „Schritte aus dem Norden“ gehört hat, darf daraus weder die wahre Identität noch das Aussehen des Eindringlings ableiten. Erinnerungsqualität, Frist, Quellen, mögliche Fehler und Widersprüche bleiben gemäß 02.61 erhalten.
- **Merkmalstypen:** Geeignete wiedererkennbare Merkmale können Stimme und Sprechweise, sichtbares Gesicht oder Körper-/Kleidungsmerkmale, Gegenstände/Uniform, auffällige Zeichen, Verhalten oder frühere Gespräche sein – **nur wenn das jeweils aktive Regel-/Figuren-/Szenenmodell sie wirklich definiert**. Nicht jedes Spielsystem braucht alle Merkmale.
- **Tatsächliche Wahrnehmung begrenzt Prüfung:** Optische Merkmale benötigen gültige Sicht, Licht-/Dunkelheits- und Sichtbarkeitsbedingungen/Fog; Stimme und Geräusche benötigen nach 02.49–02.53 eine zulässige Hörwahrnehmung, Sprachkenntnis für konkrete Wortinhalte ggf. nach 02.60. Ein geschlossenes Hindernis kann Sicht verdecken, ohne ein zulässiges Stimmerkennen zu verhindern. Der Server kennt zwar reale Token-IDs, **diese dürfen aber keine fehlende NPC-Wahrnehmung umgehen**.
- **Verkleidung und Veränderungen:** Kleidung, Maske, Uniform, verstellte Stimme, technische/magische Effekte, Dunkelheit oder andere **tatsächlich modellierte** Tarnmerkmale dürfen je Profil die Wiedererkennung erschweren, erleichtern oder auf andere Merkmale verschieben. Eine optische Verkleidung verdeckt nicht automatisch die Stimme; eine Stimmverstellung verändert nicht notwendig das Gesicht. **Konkrete Arten, Ausrüstung, Tarnidentitäten und Erstellung werden in 02.63 separat entschieden.**
- **Zeit und Erinnerung:** Ein altes, als unsicher gekennzeichnetes oder abgelaufenes Erinnerungsmerkmal darf anders bewertet werden als eine aktuelle klare Begegnung. Zeitliche Gedächtniseffekte aus 02.61 verwenden passende Echtzeit-/Rundenregeln aus 02.15–02.16, ohne universelle feste Verfallsrate.
- **Ergebniszustände statt Allwissen:** Mögliche fachliche Ergebnisse sind **wiedererkannt**, **für ähnlich/verdächtig gehalten**, **nicht erkannt** oder **falsch zugeordnet**; konkrete Ergebnisstufen bleiben profilabhängig. Die Vermutung „Das könnte der Einbrecher sein“ ist **keine bestätigte wahre Identität**. Ein NPC darf bei geltender Regel einen Irrtum später anhand neuer Informationen korrigieren.
- **Regelabhängigkeit:** Für eindeutige Merkmale und passende Erinnerung darf eine automatische Wiedererkennung zulässig sein. Für schwierige Fälle können Skills/Fähigkeiten, Verkleidungs-/Täuschungswerte, passive Erkennung, aktive Probe oder berechtigter SL-Entscheid gelten. Keine verpflichtende Probe für jede erneute Begegnung. Das allgemeine Character-/Skillsystem aus 03/07 bleibt zuständig für Formeln, Modifikatoren und Fortschritt; **verbesserbare Sprachskills aus 02.60** bleiben unabhängig davon.
- **NPC- und Fraktionsgrenzen:** Ergebnisse gehören zunächst **dem konkreten wahrnehmenden NPC**. Andere NPCs wissen davon erst nach gültigem Kommunikationsweg und Informations-/Vertrauens-/Sprachprüfung aus 02.56–02.60, nicht automatisch wegen gemeinsamer Fraktion oder Szene.

### 2. Verhältnis zu NPC-Steuerung, Spielweltrechten und Anzeige

- **Wiedererkennung ist keine NPC-Aktion:** Ein erfolgreiches oder zweifelhaftes Erkennen darf nach einer ausdrücklich konfigurierten Regel eine neue Erinnerung (02.61) oder einen zulässigen Verdachts-/Wachsamkeitswechsel (02.55) **anbieten**. **Keine automatische Bewegung, Verfolgung, Kampfhandlung, Spawn oder Alarm-Node** allein durch einen bloßen Erkennungsvergleich.
- **Grundsteuerungsmodus 02.54:** Ein manuell durch die SL gespielter NPC führt keine autonomen Folgehandlungen aus; automatisierte NPCs nur mit definierten Reaktionsregeln; SL-bestätigte NPC-Aktionen bleiben bis zur Genehmigung wirkungslos. Die genaue Automatisierbarkeit von Statusupdates im manuellen Modus folgt der dort genannten offenen Policy.
- **Wahre Identität und angenommene Identität trennen:** Ein Spieler kann im Spiel unter falschem Namen oder mit Verkleidung auftreten; der tatsächliche Spielweltcharakter und die **vom NPC vermutete Person** sind getrennte Daten. Die tatsächliche technische Nutzer-/Token-/Objektidentität, Steam-Rollen und Sicherheitsberechtigungen bleiben unverändert. Eine überzeugende Tarnidentität ist **keine technische Befugnis**, eine Tür, ein Systemkonto oder einen Node-Port ohne gültige Prüfung zu bedienen (siehe 02.59).
- **Fog und Geheimnisse:** Verborgene Token, Namen, interne Spieler-IDs, verdeckte Gegenstände, exakte Positionsdaten und SL-Notizen werden nicht allein wegen einer Wiedererkennungsregel an NPC- oder Spielerclients ausgeliefert. Der autoritative Server sendet nur pro berechtigtem Client ausdrücklich freigegebene Hinweise/Erkennungsreaktionen. Berechtigte SL-Diagnose darf zugrunde liegende wahre und vermutete Zusammenhänge zur Kontrolle anzeigen.
- **Globale Defaults und gezielte Ausnahmen:** Der SL kann Kampagnenstandards und nachvollziehbare individuelle NPC-/Gruppen-/Situationswerte vorsehen. Änderungen mit Vorschau, expliziten geschützten Overrides und Referenzschutz nach 02.25. Die genaue Priorität überlappender Wahrnehmungs-/Verkleidungs-/Gedächtnisregeln bleibt eine spätere Detailentscheidung.

### 3. Technischer Entwurf – keine endgültige API

1. **Wahrnehmungsmerkmale getrennt vom realen Token:** Auf dem Server gibt es eine **wahre Welt-/Objektidentität**; für Wahrnehmungsprüfungen entsteht eine **gefilterte Merkmalsbeobachtung** nur aus tatsächlich wahrnehmbaren Eigenschaften. Konzeptionelle Bezeichner `ObservedIdentityFeatures` bzw. `PerceivedPersonDescriptor` sind bloße Vorschläge, keine beschlossene Implementierung. Keine automatische biometrische Identifikation echter Fotos oder Stimme erforderlich.
2. **Erinnerungsvergleich:** Ein `RecognitionResolver` (Beispielname) prüft die beobachteten Merkmale gegen nur **noch gültige, von diesem NPC tatsächlich gespeicherte** `NpcMemoryRecord`-Merkmale (02.61); Gedächtnisquelle, Zeit, Unsicherheit, passende Regeln, optionale Skill-/Würfelreferenz und SL-Freigabe berücksichtigen. Die tatsächliche unveröffentlichte Token-ID darf nicht als „Hinweis“ an den NPC-Entscheider durchgereicht werden.
3. **Ergebnis als eigener Fakt bzw. Eindruck:** Ein `RecognitionResult` (Beispiel) verbindet NPC, Wahrnehmungs-/Gedächtnisreferenzen und das **subjektive** Resultat (sicher, vermutet, negativ oder mögliche Fehlzuordnung), ohne den wahren Charakter zwangsweise zu identifizieren. Wird eine falsche Person verdächtigt, muss das als NPC-Annahme von den objektiven serverinternen Zuordnungen unterscheidbar bleiben.
4. **Nachgelagerte Regeln:** Ein geeignetes Erkennungsereignis kann eine autorisierte Änderung an NPC-Erinnerung (02.61), Wachsamkeit (02.55) oder eine typisierte Node-Information anstoßen, **aber nur über eine ausdrücklich gültige Policy/Kante/SL-Bestätigung**. Wiederholte Sichtprüfungen pro Server-Tick dürfen nicht zu neuen Würfeln, unendlichen Erinnerungsupdates oder Alarmschleifen führen.
5. **Serverrechte, Debug und Tests:** Stabil referenzierte NPC-/Ereignis-/Erinnerungs-/Beobachtungs-/Probe-IDs, idempotente Neuauswertung nach gültiger Licht-, Sicht-, Verkleidungs- oder Positionsänderung. Die SL-Debugansicht unterscheidet **tatsächliche Figur**, sichtbare Merkmale, NPC-Vorwissen, Probe, vermutete Identität und ausgeführte Folgeaktion; isolierte Tests aus 02.31–02.34 verändern nie reale Figuren oder Szenen.

### 4. Abnahmebeispiele für die spätere Umsetzung

- Eine Wache erkennt einen bekannten Charakter bei guter Sicht anhand **gültig erinnerter sichtbarer Merkmale**; eine andere Wache ohne dieselben Erinnerungen kennt ihn nicht automatisch.
- Mit Maskierung oder anderer Uniform und gültigem Tarnprofil kann sich das Erkennungsergebnis ändern, **ohne die echte Figurenidentität** oder technische Benutzerrechte zu verändern.
- Eine Wache hört hinter einer Tür eine früher bekannte Stimme und darf bei geeignetem Hör-/Wiedererkennungsprofil eine Vermutung entwickeln; sieht sie die Person nicht, dürfen **keine zusätzlich verborgenen optischen Merkmale** in die Prüfung einfließen.
- Eine veraltete, unsichere Erinnerung kann zu **falscher Wiedererkennung** führen; die entsprechende NPC-Annahme bleibt von objektiver Spielweltwahrheit getrennt und kann später berichtigt werden.
- Ein erfolgreiches Wiedererkennen löst **ohne gesonderte Reaktions-/Alarm-Node** keinen globalen Alarm oder Angriff aus. Eine manuell gespielte bzw. SL-bestätigungspflichtige Wache handelt weiterhin gemäß 02.54.
- Spieler erhalten keine verborgenen Token-IDs, tatsächlichen Identitäten oder internen SL-/NPC-Prüfdetails; doppelte Wahrnehmungsereignisse wiederholen keine Probe oder Node-Wirkung unbegrenzt.

**Weiter offen:** Konkrete Merkmalskataloge, Erkennungs-/Täuschungs-Skillwerte und Schwellen, Fehlzuordnungsregeln, optische/akustische Effekte und deren Priorität, Detailverknüpfung mit NPC-Memory und Erfahrungspunkten, NPC-/Spieler-UX sowie **konkrete Verkleidungs-/Tarnidentitätsmechanik (02.63)**. Die allgemeine Kampagnen-Einstellungsführung und Abschaltung weiterer Module bleiben gemäß 02.48 auf nach dem vollständigen Featureworkshop verschoben.

## 02.63 – Konfigurierbare Verkleidungen und Tarnidentitäten mit echten Fertigkeitsproben (12.10.2026)

**Verbindlich beschlossen: Variante C mit Zusatz.** Figuren können je Setting/Regelprofil aus tatsächlich vorhandenen Kleidungsstücken, Uniformen, Masken, Ausweisen, Decknamen, angenommener Rolle, Stimmverstellung und geeigneten technischen oder magischen Hilfen ein **konfigurierbares Tarnprofil** bilden. Wirkung und Erkennbarkeit hängen von verfügbaren Fähigkeiten, Inventar, Szene, NPC-Wahrnehmung, Erinnerung und ggf. tatsächlicher Probe ab. **Kampagnenstandards mit bewussten Ausnahmen pro NPC, Figur, Gegenstand, Szene/Bereich oder konkreter Situation** nach 02.25. Der aktive Tarnauftritt darf die **wahre** serverinterne Charakter-/Token-/Nutzeridentität und technisch geprüfte Berechtigungen nicht verändern. Die Wirkung gegen NPCs wird gemäß 02.62 geprüft, ohne geheime Figuren-IDs als NPC-Wissen zu verwenden.

**Verbindlicher Zusatz des Projektinhabers zu Skillchecks:** Wenn das Regelprofil für eine Aktion ausdrücklich eine **aktive würfelpflichtige Fertigkeitsprobe** verlangt, wird **tatsächlich gewürfelt**. Die zugehörige Schwierigkeit/Checkdefinition muss in einen **numerischen Mindestwurf** aufgelöst werden. Die verbindliche Grundregel für diesen Probentyp lautet:

```text
Gesamtwert = tatsächliches Würfelergebnis + passender numerischer Skillwert
bestanden  = Gesamtwert >= numerischer Mindestwurf
```

**Gleichstand mit dem Mindestwurf bedeutet Erfolg.** Zum Beispiel (frei gewählte Zahlen, **keine festgelegten Standardwerte**): Bei Mindestwurf 15, Skill „Täuschen“ 4 und echtem Würfelwert 12 ist 12 + 4 = 16, also **bestanden**.

**Präzisierung des Ausdrucks „aktive würfelpflichtige Skillchecks“:** Gemeint sind **Fertigkeitsproben, für die die jeweils gültige Kampagnen-/Regeldefinition einen tatsächlichen Wurf verlangt** – beispielsweise bei Verkleiden, Schleichen, Schlösserknacken, Überreden oder Schießen, **wenn** diese Situation als solche Skillprobe definiert ist. **Nicht jede Aktion muss gewürfelt werden**, und passive/automatische Wahrnehmungen nach 02.53/02.59/02.62 bleiben ohne aktiven Wurf möglich, wenn so geregelt. **Schadenswürfe und andere eigenständige Wurfarten** unterliegen nicht automatisch dieser Skillcheck-Gleichung; ihre Formeln werden im Würfel-/Kampf-Workshop 05/07 entschieden. Das bedeutet auch **keinen universell vorgeschriebenen W20** und keine heute schon festgelegten Schadens-/Kampfregeln.

### Fachliches Tarnsystem

- **Tarnmittel und Zustand:** Eine Uniform, Maske, gefälschte Papiere, Deckname, Stimmverstellung, Technik oder Magie wirkt nur, wenn die Figur das dafür zulässige Objekt, die Fähigkeit oder den aktiven Zustand wirklich besitzt. Kleidungsstücke/Masken dürfen optische Merkmale beeinflussen, ohne automatisch Stimme oder Zugangsrechte zu ändern. Regeln für Ausrüstungs- und Objektzustand aus Inventar 01; Skill-/Charakterstruktur aus 03/07.
- **Kombination ohne erfundene Boni:** Eine Tarnung kann aus mehreren Quellen bestehen, aber **ob und wie** deren Werte zusammenwirken, entscheidet das gewählte Regelprofil. Keine unbeschlossene additive Bonus- oder Strafmatrix.
- **Echte vs. behauptete Identität:** Eine überzeugende Verkleidung kann bewirken, dass eine NPC-Wache eine Person für eine andere hält. Tatsächliche Token-ID, Spielerrolle, Serverzugang, Fraktionswahrheit und technische Tür-/Node-Rechte bleiben davon unberührt.
- **Wiedererkennung und Erinnerung:** Ein NPC vergleicht nur Merkmale, die er wahrnehmen und entsprechend 02.61 tatsächlich erinnern darf (02.62). Erfolgreiches Täuschen bei einer Wache wird nicht automatisch von allen NPCs akzeptiert; Sicht-, Hör-, Situations- und Gedächtnisunterschiede können getrennte Ergebnisse erzeugen.
- **SL-Kontrolle und Rechte:** Der Spielleiter kann bei passenden Regeln die Tarnung verwalten, Anwendungsbedingungen festlegen und gültige Checks freigeben; die Wirkung wird durch serverautorisierte Aktionen ausgelöst, nicht durch bloße Client-Textänderung.
- **Umfang und Grenzen:** Kompletter Tarneditor, Oberflächen, konkrete Proben- und Objektlisten sowie Abnahmewerte erst später im passenden Funktionsworkshop; die globalen Kampagneneinstellungen im Ganzen gemäß 02.48 erst nach allen Featurebereichen planen.

### Technische Planung echter Fertigkeitschecks

1. **Typisierter Checkauftrag:** Eine gültige Interaktion, NPC-Regel oder Node erzeugt einen Checkauftrag mit eindeutiger Ereignis-/Akteursreferenz, **passender Skill-ID**, aktiver Difficulty-/Checkdefinition, zulässiger Würfelart/Formel, Berechtigungen und Szenenkontext. Welche Skillwerte benutzt werden, stammt aus dem autoritativen Charakter-/NPC-Skillsystem (03/07), nicht aus einem beliebigen vom Client gelieferten Bonus.
2. **Numerischer Mindestwurf:** Der Check wird gemäß Kampagnen-/Regelprofil in einen **konkreten numerischen Mindestwurf** umgewandelt, bevor das Ergebnis ausgewertet wird. Eine Schwierigkeitsstufe darf nach gültiger Regel einem Mindestwurf entsprechen; **02.64** beschließt Stufen mit numerischen Mindestwürfen und bewussten Einzel-Ausnahmen; konkrete Werte und situative Modifikatoren werden in 03/05/07 weiter spezifiziert.
3. **Echter, verbindlicher Wurf:** Der Server prüft Berechtigung und Würfelregel und erzeugt **wirkliche zufällige Rohwürfelwerte**, versieht den Wurf mit stabiler ID und speichert ihn als autoritatives Ereignis. Die 3D-Würfelanimation stellt dieses Ergebnis dar; sie darf es nicht selbst willkürlich festlegen oder ersetzen.
4. **Auswertung:** Für den hier beschlossenen aktiven Fertigkeitscheck werden **Rohwürfel-Ergebnis plus gültiger passender numerischer Skillwert** berechnet. Ist die Summe **größer oder gleich** dem aufgelösten Mindestwurf, ist der Check erfolgreich; andernfalls fehlgeschlagen. Situative Boni/Strafen, Vorteile, kritische Ergebnisse oder Opposed Checks werden **nicht ohne späteren Beschluss erfunden**; wenn vorgesehen, müssen sie als nachvollziehbare Bestandteile der Regeldefinition und der Berechnung modelliert werden.
5. **Log und Geheimnisschutz:** Server kennt Wurf-ID, verwendeten Skillwert, echte Rohwerte, Mindestwurf, Gesamtwert und Erfolg. Die an die Teilnehmer ausgelieferte Animation und das Würfelprotokoll folgen vorhandenen Rechte-/Geheimnisregeln, z. B. bei geheimen NPC-Erkennungswürfen; geheime Mindestwürfe und verdeckte NPC-Informationen nicht unberechtigt weitergeben.
6. **Folgeaktionen getrennt:** Ein typisiertes Erfolg-/Misserfolgsergebnis darf nach den vorhandenen Node- und Objektregeln andere Nodes (z. B. Dialog, Tür, Alarm oder die später vorgemerkte Spawn-Node aus 02.59) ansteuern – nur bei gültiger Verkabelung, Sicherheits-/Objektfreigabe und serverseitiger Validierung. Ein erfolgreicher Tarnwurf gewährt nicht unmittelbar privilegierte Node-/Serverrechte.
7. **Idempotenz und Tests:** Gleicher gültiger Check darf bei Reconnect, Node-Kaskaden und doppelter Client-Anfrage nicht ungefragt neu ausgewürfelt werden. Isolierte Tests aus 02.31–02.34 belegen echte Wurfwerte, Skillbeiträge, Mindestwurfauflösung, Gleichstand-Erfolg, Fehlversuch, Rechteschutz sowie ausbleibende Doppelwirkungen.

### Beispielhafte spätere Abnahmen

- Tarnung aus Wachenuniform + Deckname: Eine Wache kann je Memory/Regelprofil eine Täuschungs-Skillprobe verlangen. Bei Mindestwurf 15, Skill 4 und tatsächlichem Wurf 12 besteht die Figur (16 >= 15). Das ist nur ein **Beispielwert**, kein Standard-Schwierigkeitsgrad.
- Derselbe tatsächliche Wurf kann je nach Skillwert und gültigem Mindestwurf bestehen oder scheitern. Ein exakt erreichter Mindestwurf zählt als Erfolg.
- Ein Charakter kann eine vertraute Sprache nutzen oder einen eindeutigen Gegenstand erkennen, ohne dass die Regeln zwangsläufig einen Würfelwurf erzwingen. Ein Schadenswurf ist keine automatische Anwendung der Fertigkeitscheck-Gleichung.
- Eine erfolgreiche Tarnprobe beeinflusst ggf. NPC-Erkennung, ohne echte Benutzeridentität, Serverrechte oder den tatsächlichen Gegenstand zu ändern. Ein NPC mit anderer Erinnerung kann anders reagieren.
- Check-/Wurfereignisse bleiben serververbindlich, berechtigt sichtbar, dedupliziert und mit Simulation testbar; keine rein gefälschte Würfelanimation.

**Noch offen:** konkrete Zahlenwerte und Zuordnungen für die in 02.64 beschlossenen Mindestwurf-Stufen, zulässige Würfelarten/Poolmodelle, Sonderergebnisse und zusätzliche Modifikatoren, Skillwerte-/Steigerungsmodell (03), genaue Auswirkungen einer Tarnung, automatische/passive Spezialfälle und Verhältnis zu Kampf-/Schadenswürfen (05/07). Die verbindliche Kernformel für **würfelpflichtige Fertigkeitschecks** ist jedoch beschlossen.

## 02.64 – Numerische Mindestwürfe aus Schwierigkeitsstufen; verdeckte Wahrnehmungswürfe (12.10.2026)

**Verbindlich beschlossen: Variante C mit ausdrücklicher Ergänzung des Projektinhabers.** Die Kampagne bzw. ihr aktives Regelprofil besitzt **benannte Schwierigkeitsstufen mit jeweils einem konfigurierbaren numerischen Mindestwurf**. Eine berechtigte Spielleiterentscheidung oder ein gültig konfigurierter Check, Gegenstand oder Node darf stattdessen **einen ausdrücklich gekennzeichneten eigenen numerischen Mindestwurf** verwenden. Für die in 02.63 festgelegten würfelpflichtigen Fertigkeitschecks lautet die verbindliche Grundauswertung weiterhin:

```text
Gesamtwert = tatsächlich gewürfeltes Ergebnis + passender Skillwert
Erfolg     = Gesamtwert >= wirksamer numerischer Mindestwurf
```

**Gleichstand ist Erfolg.** Beispielsweise kann der Spielleiter einer Stufe „schwer“ in einer Kampagne einen Mindestwurf zuordnen, der für alle geerbten Checks gilt, während eine besonders aufwendig gesicherte Tür einen individuell festgelegten anderen Mindestwurf nutzt. **Die Namen, Anzahl und Zahlenwerte der Stufen sind noch nicht festgelegt.** Keine unbeschlossenen Zusatzmodifikatoren oder feste Würfelart vorwegnehmen.

### 1. Schwierigkeitsprofil und gezielte Ausnahmen

- **Vordefinierte Namen mit Zahlen:** Für eine Kampagne und das passende Regelprofil darf die Spielleitung Schwierigkeitsstufen wie „leicht“, „mittel“ oder „schwer“ definieren und jeder Stufe den **numerischen Mindestwurf** zuordnen. Die Stufennamen sind nur Beispiele; ihre konkreten Werte und die Standardvorauswahl sind noch offen.
- **Wirksamer Zielwert vor Auswertung:** Ein Check referenziert seine Schwierigkeitsstufe und ggf. eine ausdrückliche Abweichung. Der Server löst **vor dem Ergebnisvergleich** den endgültigen Mindestwurf auf, protokolliert Stufe, verwendete Zahl, Regel-/Profilversion und Herkunft des individuellen Overrides. Keine uneindeutige Priorität bei gleichzeitig vorhandenem Stufen- und Einzelwert.
- **Einzelne Objekte, Nodes und Situationen:** Berechtigte SL-Aktionen, gegenstands- oder szenengebundene Check-Definitionen und typisierte Node-Eingänge können bei Bedarf **einen konkreten Zielwert** statt geerbtem Stufenwert erhalten. Dasselbe gilt für später geeignete Skill- und Figurenregeln, sofern das jeweilige Regelprofil diesen Override erlaubt.
- **Globale Änderungen mit Schutz:** Änderungen der Kampagnen-Schwierigkeitszuordnung folgen den Regeln für Vorschau, bestehenden Checks, vererbbare Defaults und geschützte individuelle Ausnahmen aus 02.25. Ein bereits autoritativ ausgeführter Wurf wird nicht rückwirkend umgedeutet; simulierte Änderungen gehören in den isolierten Test.
- **Rechte und Folgeregeln:** Mindestens die aktive Regeldefinition und ein gültiger Skill sind vor dem Wurf erforderlich. Das Auflösen einer Zahl erlaubt **keinen** Zugriff auf verborgene SL-Schwierigkeiten oder fremde Tokenwerte. Erfolg-/Fehler-Node-Ausgänge lösen nur ausdrücklich erlaubte, servervalidierte Aktionen aus.

### 2. Ergänzung: Möglichst viele echte Würfe, geheime Prüfungen dürfen nichts verraten

**Zusätzlicher verbindlicher Nutzerwunsch:** Im Spiel soll möglichst häufig **wirklich gewürfelt** werden, wenn eine passende Fertigkeits- oder Ereignisregel eine Probe vorsieht. Jedoch dürfen Spieler **nicht durch den Wurf selbst erfahren, dass es ein verborgenes Geräusch, eine Falle, einen NPC oder ein anderes geheimes Ereignis gibt**. Insbesondere bei der Frage **„Hört diese Figur ein unbemerktes Geräusch?“** gilt:

- **Verdeckter realer Serverwurf:** Wenn das aktive Wahrnehmungsprofil (02.53) für einen nicht offensichtlichen Reiz eine Würfelprüfung vorsieht, erzeugt der autoritative Server **einen echten Zufallswurf**, liest den gültigen Wahrnehmungs-/Hörskill und vergleicht `Skill + Wurf` mit dem wirksamen numerischen Mindestwurf. Das ist keine simulierte Erfolgswahrscheinlichkeit und keine dekorative Animation.
- **Vollständig unsichtbar für betroffene Spieler:** **Weder Würfelanimation noch Wurfmeldung, Skill-Check-Popup, Würfelprotokolleintrag, Benachrichtigung oder übermittelte versteckte Ereignisdaten** dürfen dem Spieler den geheimen Wurf oder allein dessen Existenz verraten – unabhängig davon, ob er bestanden oder verfehlt hat. **Eine versteckte Probe wird nicht in einem nur grafisch verdeckten öffentlichen Clientevent verschickt**, sondern serverseitig ausgeführt und nur in entsprechend berechtigten Spielleiter-/Auditansichten nachvollziehbar.
- **Nur zulässige Konsequenzen freigeben:** Bei erfolgreicher Wahrnehmung darf ein Spieler **die laut 02.51–02.52 und 02.53 freigegebene Information** erhalten, zum Beispiel eine ungenaue Geräuschrichtung. Bei Misserfolg **keine Offenlegung**, nicht einmal „Du hast den Wahrnehmungswurf nicht bestanden“. Auch mögliche geheime Zielzahl/Quelle und verborgene Figuren bleiben geschützt.
- **Offensichtliche Ereignisse:** Ein klar und ohne Probe erkennbares Geräusch kann nach dem bisherigen Beschluss 02.53 weiterhin **automatisch** erkannt werden. Das neue Ziel „häufig würfeln“ ist **keine Verpflichtung zu unnötigen Würfen in jeder Situation**. Wann eine aktive oder geheime Probe sinnvoll ist, bestimmt später das jeweilige Regelprofil, nicht ein unbegründeter zusätzlicher Check bei jeder Serveraktualisierung.
- **Spielerinitiierte Proben:** Wenn der Spieler selbst absichtlich untersucht, horcht, schleicht oder eine andere Aktion versucht, kann ein **sichtbarer echter Wurf** gemäß separater Berechtigungs-/Sichtbarkeitsrichtlinie passend sein. Ob andere Teilnehmer das Ergebnis sehen, wird in 02.65 behandelt. **Heimliche Auslösung durch die Welt** und **bewusste Spieleraktion** sind unterschiedliche Fälle.
- **Andere verdeckte Erkennungen:** Für versteckte Gegner, Fallen und unbemerkte Details können die gleichen Geheimnisschutzregeln gelten, wenn das aktivierte Modul entsprechende Checks unterstützt. **Keine globale Vorabverpflichtung, dass jede Fallenerkennung, jedes Sichtfeld oder jede Bewegung einen Würfelwurf erfordert.**
- **Verteilte Proben ohne Informationslecks:** Bei mehreren Figuren bewertet der Server jeden geeigneten Empfänger gesondert; der Wurf für Figur A darf Figur B keine Informationen liefern. Spieler erhalten keinerlei Metadaten oder Nachrichtenzahlen aus verborgenen Checks. Verdeckte Würfe sollen nur bei gültigen Ereignissen/Änderungen stattfinden, nicht ungehemmt in jeder Simulationsschleife.

### 3. Technischer Realisierungsentwurf – keine finale API

1. **Versionierter Schwierigkeitskatalog:** Konzeptionelle `DifficultyProfile`-/`DifficultyTier`-Einträge je Kampagne/Regelprofil mit Anzeigename, numerischem Mindestwurf und IDs. `CheckDefinition` referenziert Stufe oder individuell berechtigt festgelegten Mindestwurf. Der `DifficultyResolver` (alle Namen exemplarisch) ermittelt genau **eine gültige Zahl** und deren Herkunft nach 02.25.
2. **Serverautoritärer Check:** `SkillCheckRequest` (nur Konzept) wird auf Trigger, Akteur, Skillwert, zulässige Würfeldefinition, Skill-/Profilversion, Schwierigkeit und Rechte geprüft. **Echtes RNG** liefert Würfelrohwert/-werte; die im passenden Regelprofil gebildete Probe verwendet für den festgelegten Standardtyp **Würfelergebnis plus numerischen Skill** und vergleicht gegen numerischen Mindestwurf. Log-/Ergebnisobjekt enthält Check-ID, Wurf-ID, Rohwerte, Skillanteil, Mindestwurf und Erfolg – jedoch nur **serverseitig** in für diese Vertraulichkeitsstufe autorisierten Speicher-/SL-Kontexten.
3. **Check-Vertraulichkeit vor dem Wurf:** Eine fachliche `CheckVisibilityPolicy` (noch kein endgültiger Port/Name) klassifiziert verborgene **passive/unbemerkte Erkennungschecks bereits vor ihrer Ausführung** als **servergeheim**. Die Berechnung darf keine Würfelanimation, keine gewürfelte Zahl und **auch kein Event über den stattgefundenen Wurf** an unberechtigte Spieler-Clients senden. Nur berechtigte SL können den Wert im internen Debug-/Auditbereich einsehen. Andere Sichtbarkeitsmodi folgen in 02.65.
4. **Freigabefilter auf Ergebnis statt Wurf:** Nach einem erfolgreichen geheimen Hör-/Wahrnehmungscheck prüft eine separate serverseitige Präsentationsregel, **ob und was** die Figur wahrgenommen hat, und gibt ausschließlich einen erlaubten `SoundCue` oder passenden Entdeckungshinweis frei. Kein Zugriff auf Rohwurf, Skill-/Mindestwurfwerte, Geheimkoordinaten oder nicht entdeckte Inhalte.
5. **Deduplikation und Szenenregeln:** Stabile Stimulus-/Empfänger-/Check-/Wurf-IDs, definierte Neubewertung bei relevanten Änderungen statt ständigem Neurollen, Neustart-/Reconnect-Schutz, getrennte Echtzeit-/Rundenereignisse und Konfliktregeln aus 02.35. Eine Check-Dopplung darf nicht durch wiederholte Node-Impulse Erfolgswahrscheinlichkeiten künstlich steigern.
6. **Tests und Debug:** Isolierte Soll-Ist-Tests aus 02.31–02.34 prüfen Stufe → Zielwert, gezielten Override, Gleichstand-Erfolg, fehlende oder invalidierte Werte und **echten geheimen Wurf ohne jede spielerseitig erkennbare Spur**. Erfolgreicher Hörtest kann anschließend ausschließlich die freigegebene Richtung anzeigen; erfolgloser Test erzeugt keinerlei Hinweis. Keine echten Alarm-/Tür-/Spawnaktionen während der Simulation.

### 4. Beispielhafte Abnahmefälle

- Die Kampagne ordnet einer benannten Schwierigkeit einen numerischen Mindestwurf zu. Zwei unterschiedliche Checks erben ihn; ein bewusst abweichender Tür-Node verwendet nur seinen eigenen Zielwert.
- Wurf 12 und Skill 4 gegen Mindestwurf 16 gilt als bestanden, gegen 17 als fehlgeschlagen; **beides sind frei gewählte Beispielzahlen**.
- Hinter einer Tür befindet sich eine geheime Geräuschquelle: Beim relevanten Ereignis führt der Server gegebenenfalls einen echten Hörskillwurf aus; ein Spieler, der nichts wahrnimmt, sieht **weder den Wurf noch eine sonstige Andeutung**.
- Bei gelungenem verborgenem Check erscheint nur der berechtigte Hinweis „ungefähre Richtung hinter der Tür“, ohne Wurfzahl, geheime Quelle oder exakte Position.
- Ein spielerinitiierter offener Fertigkeitscheck kann als echter Würfelwurf für berechtigte Teilnehmer sichtbar animiert werden; er ist nicht mit dem verdeckten unbemerkten Wahrnehmungscheck zu verwechseln.
- Doppelte Netzwerkereignisse/Reconnect führen zu keinem zweiten geheimen Check und keiner mehrfachen gewürfelten Erfolgschance; die SL-Diagnose ist vollständig, Spieler-Log und Netzwerkzustand enthalten keinen Hinweis auf den verborgenen Check.

**Noch offen:** Anzahl und Zielwerte der benannten Schwierigkeitsstufen, konkrete Würfelarten/-pools, Skills/Zusatzmodifikatoren und passive Werte, die Kriterien für automatische vs. geheime Proben, Wiederholungszeitpunkte, Sichtbarkeit anderer Wurfarten, Audit-Aufbewahrung und die vollständige Kampagnen-Einstellungsführung. Details zu Würfel- und Charakterregeln folgen in 03/05/07; 02.65 behandelt die Sichtbarkeit von Proben außerhalb der stets geheim zu haltenden unbemerkten Wahrnehmungschecks.

### Ergänzung zu 02.64 – Advantage und Disadvantage bei Überraschungen (Nutzerwunsch)

**Zusätzlich beschlossen:** Situative Vorteil-/Nachteil-Würfel müssen insbesondere bei einer gültigen Überraschung oder einem Hinterhalt **als echte Würfelwürfe** unterstützt werden. Ob eine bestimmte Überraschung und welche Skill-/Kampfaktion betroffen ist, hängt vom aktivierten Kampagnen-/Regelprofil, einer zulässigen Szene-/NPC-/Objekt-/Node-Regel und gezielten Ausnahmen gemäß 02.25 ab. Keine Pflicht, dass jede Überraschung immer denselben Bonus auslöst.

- **Klassischer Modus:** Bei Advantage **zweimal tatsächlich auf dem Server würfeln, höheres Ergebnis wählen**; bei Disadvantage **zweimal tatsächlich würfeln, niedrigeres Ergebnis wählen**. Bei einer würfelpflichtigen Fertigkeitsprobe anschließend den passenden numerischen Skillwert **einmal** hinzufügen und gegen den numerischen Mindestwurf aus 02.63–02.64 vergleichen (Gleichheit Erfolg).
- **Beispiel (nicht bindende Werte):** Echte Würfel 7 und 16, Skill +4, Mindestwurf 18: Advantage 16+4=20 bestanden; Disadvantage 7+4=11 nicht bestanden.
- **Genre- und Regelwerksneutralität:** Die klassische Auswertung ist eine unterstützte Option, nicht ein universeller W20-Zwang. Die genaue Anwendung auf mehrteilige Würfelpools und andere Würfelarten, die Dauer von Überraschung, Mehrfachvorteile, gegenseitige Aufhebung und konkrete Kampf-/Initiative-/Schadenseffekte bleiben für 05/07 offen.
- **Verdeckt bleibt verdeckt:** Bei einer nach 02.53/02.64 **unbemerkt ausgelösten geheimen Wahrnehmungsprobe** werden bei entsprechender Vorteils-/Nachteilsregel **beide echten Würfe vollständig serverseitig** ausgeführt. Keine Animation, kein Wurfereignis, kein Logeintrag, kein Hinweis auf die Prüfung oder den Vor-/Nachteil an unberechtigte Spieler. Nur zulässig gewonnene und freigegebene Wahrnehmungsinformation darf sichtbar werden.
- **Technischer Plan:** Geprüfter situativer Roll-Modus je autorisiertem Check, zwei echte zufällige Rohwerte, gültige Auswahl (hoch/niedrig), Skillbeitrag, Mindestwurf, Regelversion sowie stabile IDs für Wurf, Probe und Auslöser. Serverseitige Berechtigungsprüfung, Deduplikation, SL-Debug und isolierte Tests gegen doppelte Events/Geheimnislecks. Keine Implementierung oder festgelegte API.

**02.65 ist inzwischen beschlossen:** Andere Würfe erhalten konfigurierbare Sichtbarkeitsprofile; unbemerkte geheime Wahrnehmungschecks bleiben für Spieler zwingend verborgen. Details stehen im Abschnitt 02.65.

## 02.65 – Konfigurierbare Würfelsichtbarkeit mit zwingend geheimen Wahrnehmungschecks (12.10.2026)

**Verbindlich beschlossen: Variante C, vom Projektinhaber ausdrücklich bestätigt.** Bei der **Kampagnenerstellung** ist fachlich festlegbar, **wer welche Würfelwürfe sehen darf**. Für passende Probenarten/Regelmodule, **Spieler, NPCs, einzelne Würfe/Checks, Nodes und Szenen** müssen **globale Kampagnenvorgaben mit ausdrücklich gekennzeichneten individuellen Ausnahmen** möglich sein. **Unbemerkte geheime Wahrnehmungs-/Entdeckungswürfe aus 02.53/02.64 bleiben unabhängig von allen sonstigen Anzeigeeinstellungen vollständig vor Spielern verborgen** – einschließlich jeder Würfelanimation, Nachricht, Würfellog-Zeile oder Metadaten über die Existenz des Checks. Die Fachentscheidung zum Sichtbarkeitsprinzip ist beschlossen; die konkrete Gesamteinrichtungsoberfläche wird gemäß 02.48 weiterhin erst nach Abschluss aller Featurethemen geplant.

### 1. Vier verfügbare Sichtbarkeitsmodi

- **Öffentlich:** Der echte, serververbindliche Wurf darf **allen nach Kampagnen-/Szenen-/Spielerrechten berechtigten Teilnehmern** als Würfelanimation und entsprechend freigegebener Logeintrag erscheinen. Das ursprüngliche Ziel „gemeinsam sichtbare Würfel“ wird für solche offenen Würfe erfüllt. Die Öffentlichkeit eines Wurfes ist **keine Freigabe verborgener Szenen-, NPC-, Ziel- oder SL-Daten**; bei Bedarf nur bereinigte Anzeigeangaben veröffentlichen.
- **Beteiligter Spieler und Spielleiter:** Den Wurf und sein erlaubtes Ergebnis sehen nur der **zur Figur berechtigte Beteiligte** und berechtigte Spielleiter. Andere Spieler erhalten **weder Animation noch Wurf-ID, Logeintrag oder nicht freigegebene Ergebnisdaten**. Welche Person bei mehreren kontrollierten Figuren als beteiligt gilt, wird aus den gültigen Figuren-/Aktionsrechten bestimmt; ein NPC besitzt nicht allein deshalb einen berechtigten Spielerempfänger.
- **Nur Spielleiter:** Der Wurf ist **für berechtigte Spielleiter sichtbar**, für Spieler aber nicht. Das ist für geeignete NPC-/SL-Aktionen oder bewusst verborgene Storyprüfungen möglich, soweit das jeweilige Regelprofil und die übergeordneten Geheimnisregeln es zulassen. Selbst sichtbare SL-Würfe dürfen keine technische Node-Autorisierung ersetzen.
- **Vollständig verdeckter Serverwurf:** Der echte Wurf wird **ohne Live-Animation, Live-Wurfmeldung, öffentliches Log oder Wurfankündigung** ausschließlich in der autoritativen Serverlogik ausgeführt. Für berechtigte SL kann eine **geschützte nachträgliche Diagnose/Auditprüfung** vorgesehen sein, ohne dass der Wurf als Live-Anzeige erscheint; die genaue Auditansicht, Aufbewahrung und eventuelle Freigabe sind später gesondert zu entscheiden. Kein bloßes clientseitiges Ausblenden bei trotzdem übertragenen geheimen Daten.

### 2. Kampagnen- und Einzelkonfiguration

- **Globaler Standard bei Kampagnenerstellung:** Definierbare Sichtbarkeitsvorgaben pro Aktion/Check- oder Würfelart, Figur-/Spielerrolle, NPC-Kontext und geeignetem Regelmodul. Voreinstellungen für offene, private, SL-interne und servergeheime Würfe müssen verständlich und einheitlich vererbbar sein. Es ist **noch nicht** entschieden, welche Modi eine neu angelegte Kampagne als Default vorauswählt.
- **Gezielte Ausnahmen:** Berechtigte Spielleiter können bei passenden **Spielern, NPCs, einzelnen Proben, Node-Schaltungen, Szenen oder konkreten Ereignissen** abweichende Anzeigeempfänger und Modi festlegen. Ein Ausnahmeprofil muss Herkunft, übernommene Kampagneneinstellung, geschützte individuelle Festlegung und wirksame Sichtbarkeit im SL-Editor nachvollziehbar machen. Änderungen an globalen Standards mit Vorschau/Bestandsentscheidung und geschützten Overrides nach 02.25; konkrete Konflikt-Priorität erst in den späteren UI-/Regeldetails festlegen.
- **Schutz geht vor öffentlicher Vorgabe:** Eine **unbemerkte automatische Wahrnehmungsprüfung** für geheime Geräusche, Fallen, Gegner oder Entdeckungen ist eine **verbindliche Sicherheitsausnahme**. Auch ein globaler Öffentlich-Modus und gewöhnliche spieler-/szenenbezogene Ausnahmen **dürfen diesen Check nicht an Spielerclients ausliefern**. Die tatsächliche Erkennung des Ergebnisses wird separat nach den wahrgenommenen Informationen und Freigaben 02.51–02.53 gezeigt, niemals durch den Wurf selbst.
- **Echte RNG-Ergebnisse unabhängig vom Empfänger:** Sichtbarkeit darf **weder Rohwürfel, Auswahl bei Advantage/Disadvantage (02.64), Skillwert, numerischen Mindestwurf (02.63–02.64) noch das objektive Ergebnis** manipulieren. Der Server legt den Wurf gemäß gültiger Checkdefinition einmal fest. Die Präsentation filtert nur, **was welcher Teilnehmer sehen darf**, sie entscheidet nicht neu über Erfolg.
- **Daten- statt nur Pixel-Geheimhaltung:** Keine versteckten Wurfpakete, Transportzähler mit erkennbarer Checkbedeutung, Roll-IDs, vorzeitige Sync-Logeinträge oder andere Spieler-Datenereignisse, aus denen eine unbemerkte Probe erkennbar wird. Berechtigte SL können über isolierte/geschützte Diagnose und Prüfungen die echte Auswertung nachvollziehen. Das allgemeine Spielerlog muss denselben Berechtigungsfilter verwenden wie die Live-Anzeige.
- **Sichtbarkeit bei NPCs und Nodegraphen:** NPC-Erkennungen, Alarmauslöser, Türen, spätere Spawn-/Telefon-/Dialog-Nodes und weitere Regelprüfungen können in ihren **eigenen gültigen Checkkontexten** einen Sichtbarkeitsmodus erben oder ausdrücklich überschreiben. Ein Prüfergebnis kann eine typisierte Node-Aktion nach sicherer Prüfung anstoßen, auch wenn die Würfelgrafik verborgen bleibt. Die reine Node-Aktion darf geheime Checkdaten nicht indirekt durch ein Wurfprotokoll veröffentlichen.
- **Mehrspieler/Verbindungen:** Die Sichtbarkeitsrichtlinie gilt bei Reconnect, verspätetem Betreten der Szene, Änderung der Rollen/Berechtigungen, gespeicherten Würfelprotokollen und realen Animationsereignissen gleich. Ein bisher privater oder geheimer Wurf darf **nicht allein durch erneutes Verbinden oder eine spätere Änderung des Kampagnenstandards plötzlich öffentlich** werden.

### 3. Realisierungsentwurf (noch keine endgültige API)

1. **Policy-Auflösung vor der eigentlichen Wurfverarbeitung:** Ein konzeptionelles `RollVisibilityPolicy`-Profil (Bezeichnung exemplarisch) wird für einen gültigen `CheckRequest` anhand Kampagnenregel, Würfel-/Checktyp, Akteur, zuständigem Spieler/NPC, Node-/Szenenbezug und erlaubten Overrides serverseitig ermittelt. Ein zwingend geheimer unbemerkter Wahrnehmungscheck erhält den **nicht für Spieler aufweichbaren Modus servergeheim**, bevor der Zufall erzeugt wird.
2. **Ein kanonischer Wurf statt Empfängerwürfen:** Server berechnet einmal die echte Wurf-ID, Würfelrohwerte, Advantage-/Disadvantage-Auswahl, Skill und Checkresultat. Die Auswahl von sichtbaren Empfängern ändert keine Rohwerte. Für gleichzeitige Reaktionen stabile Check-/Stimulus-/Spieler-/Figuren-IDs, Deduplikation und kontrollierte Wiederholungen.
3. **Berechtigungsgefilterte Projektion:** Serverseitige Nachrichtenzustellung erstellt **pro berechtigtem Empfänger** eine passende ggf. redigierte Ergebnisansicht. Öffentliche/offene Würfe dürfen sichtbar animiert werden, private nur beim betroffenen Spieler und SL, SL-interne nur bei berechtigter SL, servergeheime bei **keinem Live-Empfänger**. Verborgene Probe: keine Roll-Existenz-Ereignisse, die für Spieler auch nur einen geheimen Auslöser verraten.
4. **Getrennte Logschichten und Audit:** **Kanonisches serverseitiges Roll-/Auditprotokoll** mit geschützten technischen Daten getrennt von **pro Nutzer berechtigtem Spielerlive-Feed und nachladbarem Würfellog**. Die ausdrücklich kontrollierte spätere Freigabe geeigneter privater Einträge wurde in 02.66 C beschlossen; normales Nachladen allein veröffentlicht keinen Eintrag. Detailgrad und Aufbewahrung der Protokolle wurden in 02.67 C als konfigurierbar beschlossen.
5. **SL-Spielersicht-Vorschau und Testisolation:** SL-Vorschau kann Anzeigeempfänger und tatsächliche Inhalte für offene/private/SL-interne Würfe demonstrieren; Testmodus 02.31–02.34 prüft getrennte Clientprojektionen mit mehreren Spielern und NPCs. Ein simuliertes Event muss Wurf-IDs, Geheiminhalte und Nebenwirkungen vollständig aus der echten Kampagne heraushalten.

### 4. Abnahmeszenarien

- Gleicher echte Skillwurf kann in einer Kampagne gemäß globaler Richtlinie offen und in einer anderen privat ausfallen, **ohne eine andere Wurfzahl zu erhalten**. Eine ausdrücklich konfigurierte Szene-/NPC-/Node-Ausnahme ändert nur die berechtigte Anzeige.
- Ein öffentlicher Wurf wird den dafür berechtigten Teilnehmern mit gleicher verbindlicher Zahl und 3D-Animation gezeigt; ein privater Wurf erscheint nur bei passendem Spieler und SL; SL-intern nur beim berechtigten SL.
- Ein servergeheimer Wurf erzeugt **keine Live-Anzeige**, eine unbemerkte Wahrnehmungsprobe **niemals ein Ereignis an Spieler**, auch nicht bei globaler Einstellung „öffentlich“.
- Eine Figur hört nur bei erfolgreicher gültiger Wahrnehmung ein Geräusch bzw. bekommt eine freigegebene Richtung; sie sieht keinen verdeckten Roll, keine geheime Quelle und keinen Failtext.
- Zwei echte Advantage-/Disadvantage-Rohwürfe müssen bei offenen Würfen nach gültiger Anzeige erscheinen können; bei geheimen Wahrnehmungsprüfungen dürfen **beide** Rohwürfe und die Existenz der Probe nicht preisgegeben werden.
- Erneutes Verbinden und Laden alter Logs darf keinen bisher geheimen Wurf oder geschützte NPC-Daten sichtbar machen; eine spätere Kampagneneinstellungsänderung veröffentlicht keine alten geheimen Daten.
- Ein manipulierter Client versucht einen geheimen NPC-Wurf anzufordern, die fremden Logeinträge zu laden oder eine Szeneausnahme zu ändern: Der Server lehnt unzulässige Zugriffe ab.

**Offen:** Standardvorauswahl für neue Kampagnen, feingranulare Sichtbarkeit von Skill/Mindestwurf/Erfolgsstatus, genaue Hierarchie widersprechender Ausnahmen, Protokollaufbewahrung und genaue Redaktions-/Protokolldetails für gezielte 02.66-Freigaben. Verbindlich bleibt, dass unbemerkte Geheimprüfungen unabhängig vom Konfigurationsmodus **vor Spielern verborgen** bleiben. Die vollständige Kampagnen-Einstellungsoberfläche und Deaktivierbarkeit anderer Features planen wir erst nach Abschluss aller Featurethemen.

## 02.66 – Kontrollierte nachträgliche Freigabe privater Würfe (12.10.2026)

**Verbindlich beschlossen: Variante C.** Ein **berechtigter Spielleiter** kann einen bereits wirklich ausgeführten, **ausdrücklich freigabefähigen** privaten bzw. SL-internen Würfelwurf oder eine **für den ausgewählten Empfängerkreis bereinigte Ergebnisinformation** zu einem späteren Zeitpunkt **bewusst und gezielt** veröffentlichen. Die Freigabe kann sich an **einzelne Spieler, bestimmte berechtigte Gruppen oder die ganze dafür autorisierte Runde** richten. **Kein automatisches Öffentlichwerden** durch Zeitablauf, Szenenende, Reconnect, neue Kampagnenstandards oder Laden alter Logs. **Unbemerkte geheime Wahrnehmungs-/Entdeckungswürfe aus 02.53/02.64/02.65 bleiben vollständig ausgeschlossen**: Diese Spieler-Geheimnisklassifikation darf nicht durch eine spätere Würfelfreigabe überschrieben werden. Der SL kann **stattdessen ausdrücklich zulässige Story-/Wahrnehmungsinformationen separat erzählen oder freigeben**, nicht den ursprünglichen geheimen Würfeldatensatz.

### 1. Freigabefähigkeit, Zielgruppen und Inhalte

- **Freigabefähige Ursprungseinträge:** Zulässig sind **private (beteiligter Spieler + SL) oder SL-interne Würfe**, deren ursprüngliche Klassifikation, Check-/Szenenrechte, aktives Regelprofil und eventuelle geschützte Geheimnisse eine ausdrückliche Freigabe gestatten. Ein Spieler hat daraus **kein selbständiges Recht**, fremde Würfe oder geheime Daten zu veröffentlichen. Vollständig serverinterne Würfe dürfen **nicht pauschal** wie gewöhnliche private Würfe freigegeben werden; speziell zwingend geheime Wahrnehmungschecks sind **nie** ein solcher freigabefähiger Wurfdatensatz.
- **Ganzes oder bereinigtes Ergebnis:** Für einen tatsächlich freigabefähigen Wurf darf eine passende SL-Aktion je Regel/Freigabeumfang entweder (a) die **erlaubten Original-Würfelwerte und Ergebnisinformationen**, einschließlich ggf. tatsächlicher Advantage-/Disadvantage-Rohwürfe, oder (b) **nur ausgewählte freigegebene Teilinformationen** – beispielsweise den Erfolg/Misserfolg oder ein bereinigtes Resultat ohne geheimen Zielwert/Skillwert/Absender – veröffentlichen. Welche Feldkombinationen freigegeben werden dürfen, ist vorab serverseitig zu prüfen; die SL darf nicht durch Freitext- oder UI-Feldwahl verdeckte Objekt-/Token-/SL-Daten ausleiten.
- **Gezielter Empfängerkreis:** Einzelspieler, bestehende berechtigte Gruppen/Teams oder geeignete komplette Runde. **Der berechtigte Empfängerkreis wird für genau dieses Freigabeereignis geprüft**, inklusive aktueller Rollen-/Szenenrechte. Eine Freigabe für Spieler A macht den Wurf **nicht** für Spieler B oder den gesamten Spielersicht-Feed öffentlich.
- **Sichtbare Herkunft:** Eine nachträgliche Freigabe muss für ihre berechtigten Empfänger eindeutig als **historischer, bereits früher tatsächlich ausgeführter Wurf** erkennbar sein. Ausführungszeit und spätere Freigabezeit sind **verschiedene Zeitpunkte**. Eine mögliche erneute Darstellung/Animation darf **keine neue Zufallsprobe, kein neues Regelresultat und keine neue Node-/Kampfaktion** auslösen.
- **Original bleibt unverändert:** Wurf-ID, echte RNG-Rohwürfelwerte, ggf. Vorteil-/Nachteil-Auswahl, passender Skill, numerischer Mindestwurf und kanonisches Erfolgsergebnis aus 02.63–02.65 bleiben dauerhaft für das ursprüngliche Checkereignis unverändert. Die **Freigabe ist ein eigenes autorisiertes Ereignis bzw. eine redigierte Ansicht**, kein Umschreiben oder Wiederholen des ursprünglichen Wurfs.
- **Keine implizite Freigabe:** Weder Änderung einer globalen Kampagnenwürfelsichtbarkeit noch Szenenwechsel, neu zugeordnete Spieler oder Neustart darf rückwirkend unautorisierte Ergebnisse sichtbar machen. Bewusst erteilte Freigaben sind **nur** im definierten Umfang in später ladbaren Ergebnisansichten verfügbar; weiterer Zugriff verlangt die jeweils gültigen Rechte.

### 2. Geheimnisschutz bleibt wichtiger als Veröffentlichung

- **Zwingend geheime Erkennungswürfe nie deklassifizieren:** Ein unbemerkt heimlich ausgelöster Hör-, Wahrnehmungs-, Entdeckungs- oder vergleichbarer Check nach 02.53/02.64 behält für Spieler seine **unveränderliche Schutzklasse**, auch wenn ein SL gerade öffentliche Würfel wählt oder später Ergebnisse präsentiert. **Keine echte Wurfzahl, Wurf-ID, Fehlermeldung, geheimen Checkdetails oder bloße Checkexistenz** an Spielerclients, weder live noch später durch Wurfprotokoll, Ergebnisfreigabe, Roll-Replay oder Reconnect. Ein von dieser Regel betroffener Wurf darf nicht versehentlich aus dem geschützten SL-Audit als Spieler-Wurf exportiert werden.
- **Getrennte erzählerische Veröffentlichung:** Der Spielleiter kann nach passender Szenen-/Storyberechtigung später unabhängig einen Hinweis, ein Resultat oder eine passende Erzählung veröffentlichen, **ohne den technischen Ursprung als geheimen Wahrnehmungscheck zu enthüllen**. Beispiel: „Im Flur waren Schritte zu hören“ ist eine freigegebene Storyinformation, **nicht** der Spieler-Logeintrag des vorherigen verborgenen Wurfs. Auch hierbei dürfen verborgene Quellkoordinaten/Fog/Identitäten nicht ungeplant offengelegt werden.
- **Kein Erfolgstrigger bei Freigabe:** Ein Check, der bereits erfolgreich oder erfolglos ausgewertet wurde, hat seine fachliche Wirkung bereits gehabt. Die spätere Freigabe von Wurf-/Ergebnisinformationen darf **keinen Check erneut würfeln, keinen neuen Alarm auslösen, keinen NPC-Status verändern, keine Tür öffnen und keine Spawn-Node anstoßen**.

### 3. Technischer Entwurf – noch keine feste API

1. **Ursprünglicher Roll-Record:** Versionierter serverseitiger kanonischer Würfeleintrag (konzeptionell `RollRecord`) hält Check-/Wurf-ID, ursprüngliche Sichtbarkeitsklassifikation, zwingend geheime Schutzkennzeichen, erlaubte Freigabefähigkeit, Quelle, echten Zufallswert, Regelversion und berechtigte technische Auditdaten. **Dieses Objekt wird durch die Freigabe nicht geändert**, insbesondere nicht seine ursprüngliche Sichtbarkeit.
2. **`RollDisclosure` als neues berechtigtes Ereignis:** Eine eigenständige serverseitige Freigabeaktion (Beispielname) referenziert unverändert den historischen Roll-Record, die ausführende autorisierte SL-Rolle, **Freigabezeit**, ausgewählte Zielspieler/Gruppen, Art/Detailgrad der zugelassenen Informationen und die verwendeten Regeln. Eine Freigabe prüft die Berechtigung **bevor** Projektion oder Push an irgendeinen Empfänger stattfindet.
3. **Pflichtmäßiges Redigieren und Prüfen:** Die Freigabe-Runtime ermittelt pro Empfänger eine ausdrücklich zugelassene **DisclosureProjection**, die nur jene Rohwürfel, Skill-/Mindestwurf-/Ergebnisinformationen oder Nachrichtenfragmente enthält, die der SL in der jeweiligen Sicherheitsklasse veröffentlichen darf. Originale SL-Notizen, verdeckte Spieler-/NPC-Positionen und zwingend geheime Check-Metadaten gelangen **nie** in den unberechtigten Client.
4. **Getrennte Kanäle und Historie:** Das geschützte kanonische SL-/Server-Audit, der Live-Würfelfeed und das nachladbare Spieler-Würfellog sind getrennte Projektionen. Eine bewusste Freigabe darf den berechtigten Empfängern **ein eigenes historisch markiertes Freigabeereignis** hinzufügen, aber keine ursprünglichen verborgenen Würfe im öffentlichen Feed retroaktiv einblenden. Reconnect und erneuter Logabruf prüfen Rechte/Freigabeprojektionen nochmals und reproduzieren **keine** Wurf-/Node-Nebenwirkungen.
5. **Replayschutz und Nachweis:** Eindeutige historische Wurf-ID, Freigabe-ID, verantwortliche SL, Freigabezeit, unverändert referenziertes Original und bereits adressierte Empfänger verhindern doppelte Einträge/Kaskaden. Im geschützten Audit ist nachvollziehbar, **wer was wem wann freigegeben hat**, ohne dass das Publikum die interne SL-/Geheimprüfungs-Historie erhält. Das nachträgliche Widerrufen einer bereits gelernten Nachricht ist nicht zuverlässig möglich; eventuelle Rücknahme **nur als spätere Sichtbarkeits-/Logpolitik**, nicht als behauptetes tatsächliches Vergessen durch Spieler.
6. **SL-Vorschau und isolierte Tests:** Vor Freigabe kann die SL eine empfängerbezogene Vorschau des bereinigten Ergebnisses prüfen; Sicherheitsvalidierung bleibt serverseitig. Tests für berechtigte/unerlaubte Empfänger, vollständige und Teilfreigabe, geheimen Skill-/Mindestwurf, falsche Gruppe, SL-Rechtewechsel, alte Logs/Reconnect, doppelte Freigabe, AdventureShift-Advantage/Disadvantage-Rohwerte und zwingend geheimen Wahrnehmungswurf ohne Wurfdatensatz bei Spielern.

### 4. Abnahmekriterien

- Ein zunächst privater Skillcheck darf nach einer echten SL-Freigabe **nur einem gewählten Spieler** später als historisch freigegebener Wurf mit erlaubten Details erscheinen, anderen Spielern bleibt er verborgen.
- Ein SL-interner NPC-Wurf darf für eine berechtigte Gruppe nur mit **bereinigtem Erfolgsergebnis** erscheinen; NPC-Zielzahl, Geheimwerte und tatsächliche verdeckte Figurenlage bleiben unsichtbar.
- Der autoritative Würfelwert und seine Wirkung bleiben unabhängig von nachträglichem Freigabemodus erhalten; Advantage-/Disadvantage-Werte werden nur im tatsächlich freigegebenen Umfang angezeigt.
- Ein zwingend geheimer unbemerkter Hörwurf darf selbst bei SL-Klick, pauschalem „öffentlich“, Reconnect und Wurflog-Export **nie** als Roll-Record an Spieler gelangen. Die SL kann lediglich getrennte freigegebene Storyinformationen mitteilen.
- Weder Zeitablauf noch Szenenende noch Wechsel der Kampagneneinstellungen veröffentlichen private Würfe automatisch.
- Wiederholte Clientanfragen/Freigabe-Events führen weder zu neuen Zufallswürfen noch zu duplizierten NPC-/Node-/Alarmfolgen.
- Ein Berechtigungswechsel oder der Versuch eines unberechtigten Spielers, einen historischen geheimen Wurf abzurufen, wird serverseitig zurückgewiesen.

**Weiter offen:** Konkrete Redaktionsauswahlen, Darstellung einer historischen Wurfanimation, Protokollaufbewahrung, mögliche eigene Retention für SL-Audit und Spieler-Logs, zeitlicher Gültigkeitsbereich geänderter Gruppenrechte, Details einer bewussten ggf. eingeschränkten Rücknahme von Ansichten. Die zwingende Geheimhaltung unbemerkter Wahrnehmungswürfe ist **keine offene Einstellung**. Die Gestaltung des kompletten Kampagnenassistenten und die Abschaltbarkeit anderer Funktionsbereiche bleiben wie vereinbart bis nach dem gesamten Feature-Workshop zurückgestellt.

## 02.67 – Konfigurierbare Würfelprotokolle und Aufbewahrungsregeln (12.10.2026)

**Verbindlich beschlossen: Variante C.** Bei Kampagnenerstellung legt die Spielleitung fachlich fest, **welche Würfel-/Checkdetails wie lange in Spielerprotokollen und geschützten SL-/Serveraudits gespeichert, angezeigt, archiviert oder entsprechend gültiger Retention gelöscht werden**. Für Spielerprotokolle und geschützte Audits können **verschiedene Zeiträume, Detailgrade und Archivregeln** gelten. Berechtigte Spieler können nur die für sie freigegebenen Würfe und 02.66-Freigaben einsehen; **unbemerkte, geheime Wahrnehmungs-/Entdeckungswürfe aus 02.53/02.64/02.65 bleiben auch in historischen Spielerlogs, Exporten und Archiven vollständig verborgen**, einschließlich der Existenz des Wurfes. Es wird noch kein Datenbankschema oder allgemeiner Kampagnen-Assistent implementiert.

### Fachliche Protokoll- und Sicherheitsregeln

- **Spielerprotokoll:** Nur Würfe, Ergebnisse und historische Freigaben, die einem einzelnen Teilnehmer aufgrund seiner tatsächlichen Rollen-/Spieler-/Figuren-/Szenen-/Gruppenrechte und der ursprünglichen bzw. ausdrücklich geänderten Freigabe aus 02.65/02.66 zustehen. Suche, Pagination, Nachladen, Export und Reconnect dürfen nicht mehr verraten als der Live-Feed.
- **Geschütztes SL-/Serveraudit:** Berechtigte Spielleitung bzw. ausdrücklich autorisierte technische Rollen können je gültiger Audit-/Retention-Policy Rohwürfel, Wurf-/Check-IDs, Skillwerte, numerische Mindestwürfe, Advantage-/Disadvantage-Auswahl, Ergebnis, Auslöser und historische Disclosure-Ereignisse prüfen. Ein vollständig servergeheimer Wurf darf im geschützten Audit existieren, ohne dass er der SL live als Würfelanimation angezeigt wurde.
- **Detailtiefe konfigurierbar:** Je Kampagnen- und Regelfunktion ggf. Zeit, Figur, Würfeltyp, einzelne Rohwerte, zugelassene Modifikatoren, Endergebnis und Erfolg/Misserfolg darstellen; **keines dieser Felder darf entgegen seiner Sichtbarkeits-/Geheimnisklasse ausgeliefert werden**. Offene/private/SL-interne und rein serverseitige Würfe sind unterschiedlich gefiltert. Keine festen Pflichtspalten oder Exportformate beschlossen.
- **Speicher- und Archivfrist:** Kampagnenstandard und passende ausdrücklich markierte Ausnahmen bestimmen, ob eine Historie nur über eine Sitzung oder länger verfügbar ist, wie lange sie bei zulässiger Retention gespeichert bleibt und wann sie archiviert oder entfernt wird. Löschung/Archivierung ist **keine nachträgliche Änderung der ursprünglichen RNG-Zahl oder der tatsächlich stattgefundenen Spielweltfolgen**. Ein bereits nicht mehr gespeicherter Wurf darf nicht für eine spätere 02.66-Freigabe durch eine erfundene neue Zahl rekonstruiert werden.
- **Rechte gehen vor Fristen:** Eine generell längere Aufbewahrung verleiht Spielern keinen Zugang zu fremden Würfen. Datenschutz-, Sicherheits-, Speicher- und Backupanlagen sowie tatsächliche gesetzliche Retentionsanforderungen werden erst in der späteren technischen Detailplanung festgelegt und können Kampagneneinstellungen begrenzen. Keine pauschale Garantie unbegrenzter Speicherung.
- **Geheime Checks nie im Spielerexport:** Weder Roll-IDs, zeitliche Metadaten, Zusatzwürfe bei Advantage, verdeckte Mindestwürfe, Fehlanzeigen, Server-Sync-Ereignisse noch Hinweise auf das Vorhandensein einer geheimen Erkennungsprobe dürfen in irgendeinem Spielerprotokoll auftauchen. Berechtigte separate erzählerische Hinweise sind weiterhin nur eigene Freigabeereignisse.
- **Nachträgliche Freigabe separat:** Eine gezielte 02.66-Freigabe bleibt ein eigenes historisch markiertes, auditierbares Ereignis mit tatsächlichem SL-/Empfängerkreis und Zeitpunkt; es setzt weder einen Würfel neu ab noch betätigt es Tür-, Alarm-, NPC- oder Spawn-Nodes.

### Technische Planung (keine feste API)

1. **Aufbewahrungs-Policy:** Konzeptionelle RollRetentionPolicy mit Version, gültigem Kampagnenstandard, optionaler Wurfarten-/Spieler-/Gruppen-/Szenen-Ausnahme sowie getrennten Vorgaben für berechtigtes Spielerlog und internes Audit. Ein Originalroll bleibt während seiner gültigen Retention unverändert, Archiv-/Löschprozesse verändern keine vergangenen Weltzustände.
2. **Getrennte Projektionen:** Kanonisches, serverseitiges Wurf-/Freigabeereignis und berechtigungsspezifisches Spieler-/SL-Würfellog voneinander trennen. Suchfilter, Historie und Export müssen serverseitig nur tatsächlich erlaubte Inhalte zählen, anbieten und liefern; geheime unbemerkte Checks nie in Spielerclients übertragen.
3. **Retention, Backup, Rechte:** Ablauf-/Archiv- und Löschfristen, Wiederherstellung, begrenzten Speicher, technische Auditfähigkeit und rechtlich begründete Mindest-/Höchstfristen im passenden späteren Sicherheits-/Betriebsworkshop konkretisieren. Keine automatische Veröffentlichung bei Zeitablauf oder Szenenende.
4. **Tests:** Unterschiedliche Retentionsprofile, Offen/Privat/SL-only/Servergeheim, gezielte 02.66-Freigabe, Export, Archivierung, Berechtigungswechsel, Reconnect, alte Logs und geheime Hörprobe ohne irgendeinen Spieler-Hinweis. Logabfragen oder Export dürfen keine neue RNG-/Regel-/Node-Wirkung verursachen.

**Offen:** Exakte Speicherfristen und Grenzen, Archivformate, Export- und Such-UI, zulässige Standarddetailfelder, Datenschutz-/Backup-Aufbewahrung. Die fachliche Existenz der konfigurierbaren Historie ist beschlossen; die konkrete Gesamt-Kampagnen-Einstellungsführung bleibt bis nach dem vollständigen Featureworkshop zurückgestellt.

### Zusätzlicher verbindlicher Nutzerwunsch – Next-Player-Node

**Im universellen Node-Graph soll eine eigenständige, wiederverwendbare „Next Player“-Node einen gültigen Zugwechsel auslösen können.** Konkretes Nutzerbeispiel: Ein Spieler soll aus einem Raum; er **öffnet erfolgreich eine Tür** und durch die passende Node-Verbindung **ist anschließend der nächste Spieler an der Reihe**. Der Spielleiter soll die Logik durch Verkabeln bestehender Tür- und neuer Next-Player-Nodes gestalten können, ohne ein fest eingebautes Türrätsel-Skript. Dies ist eine Funktionsanforderung für spätere Umsetzung, keine bereits laufende Turnengine.

- **Tür tatsächlich geöffnet als Trigger:** Beispiel **Tür-Node: Zustandswechsel geschlossen → tatsächlich offen**, ihr typisierter Erfolgs-/Öffnungsereignis-Ausgang speist den **Trigger-Eingang der Next-Player-Node**. **Eine Öffnungsabsicht, fehlgeschlagene Tür-/Schlossprüfung oder ein erneut eingehender Impuls bei bereits geöffneter Tür löst im Beispiel keinen neuen Zugwechsel aus**. Soll statt dem Öffnen erst das wirkliche **Verlassen des Raums** zählen, braucht es einen passend angeschlossenen separaten Raum-/Bewegungs-Sensor; das wird nicht automatisch aus dem Türzustand angenommen.
- **Wiederverwendbarkeit:** Der Node darf außerdem durch andere vorhandene geeignete typisierte Ereignisse, z. B. Schalter-, Puzzle-, Dialog-, Quest-, Timer-, Raumverlassen- oder SL-Events, angesteuert werden. Die Zugübergabe ist **nicht nur im Kampf**, sondern auch bei rätsel- oder szenenbezogenen Spieleraufgaben sinnvoll, sofern das Regel-/Szenenprofil eine Turnfolge aktiviert. Keine Verpflichtung zu grundsätzlich rundenbasiertem Spielen.
- **Turnmanagement und Berechtigungen:** Die Node ist eine **Anfrage an den serverautoritär verwalteten Zug-/Teilnehmerzustand**, kein ungeprüftes Clientkommando. Vor dem Wechsel prüfen: gültiger Node-Auslöser, tatsächlicher alter Zuginhaber, Spieler-/Figurenkontrolle, erlaubte Aktion/Turn-Generation, Szenen-/Kampagnenbezug, Rechte und laufende Turn-Regeln. Nach Erfolg aktuellen Zug genau einmal beenden und den berechtigten nächsten Teilnehmer aktivieren. Keine implizite Aufhebung von Bewegungs-/Kampf- und NPC-Rechten.
- **Zielwahl nach 02.68 C beschlossen:** Die Next-Player-Node unterstützt als jeweils konfigurierte Alternative **den nächsten gültigen Turn-Listeneintrag, einen festgelegten Spieler/eine festgelegte Figur oder den nächsten geeigneten Teilnehmer einer definierten Gruppe/Team-/Szenenfolge**. Mehrere Charaktere eines Spielers und ggf. NPC-/KI-Züge bleiben getrennte Turn-Teilnehmer; die konkrete Behandlung nicht verfügbarer Ziele folgt **02.69**.
- **Node-Ports, Szenen, Sichtbarkeit:** Konzeptionell ein typisierter Next-Player-Trigger-Eingang und getrennte Erfolgs-/Ablehnungs-/Event-Ausgänge; konkrete Portnamen erst später. Übergreifende Node-Verbindungen nach 02.18–02.20 prüfen. Die Anzeige eines Zugwechsels darf nur berechtigte neue Zuginhaber/Spieler informieren und keine versteckten NPCs/Szenen/SL-Informationen offenlegen.
- **Einmaliger Wechsel und Schleifenschutz:** Eindeutige Türzustands-, Node-Ereignis- und Turnversions-IDs; mehrfach eintreffende Türöffnungs-Events und Reconnect dürfen **höchstens einen** Zugwechsel pro gültigem Trigger und Turn-Generation bewirken. Gleichzeitige Nodes/Automatik-Ketten gemäß Konflikt- und Schleifenschutz 02.13/02.35 behandeln. Bereits abgeschlossene Ereignisse dürfen nicht sofort wiederholt den Zug weiterdrehen.
- **SL-Debug und isolierte Tests:** Erfolgreich geöffnet → genau ein Next-Player-Wechsel; gesperrt/fehlgeschlagen → kein Wechsel; Tür schon offen → kein weiterer Wechsel; falscher Zuginhaber, fehlende Turnfolge oder doppeltes Event → Ablehnung statt Überspringen. Debugger dokumentiert Quelle, aktuellen Zug, geprüfte Turnrichtlinie und neuen Zuginhaber. Simulation aus 02.31–02.34 darf keinen realen Turnzustand verändern.

**Später im Featurebereich 07** sind die allgemeine Turn-/Rundensteuerung, Spieler-/Figuren-Zuordnung, Zugberechtigungen, Kampf-Integration, Offline-/Skip-Verhalten, SL-Übersteuerung und UI im Detail zu spezifizieren. **02.68 C** legt die konfigurierbare Zielwahl fest; die Behandlung nicht verfügbarer Spieler/Zugziele folgt in **02.69**.

## 02.68 – Konfigurierbare Zielauswahl der Next-Player-Node (12.10.2026)

**Verbindlich beschlossen: Variante C.** Die bereits in 02.67 vorgesehene **frei verkabelbare Next-Player-Node** kann pro gültigem Node-/Szenen-/Kampagnenkontext bestimmen, **welcher Spieler bzw. welche von ihm kontrollierte Spielfigur** nach einem zulässigen Auslöser an die Reihe kommt. Für jede Next-Player-Node sind **drei alternative Auswahlarten** vorgesehen: (1) **nächster berechtigter Eintrag der geltenden Zugreihenfolge**, (2) **ausdrücklich gewählter Zielspieler oder Zielcharakter**, (3) **nächster geeigneter Teilnehmer einer konfigurierten Gruppe, eines Teams oder einer Szenen-Teilnehmerliste**. Ein **Kampagnenstandard mit bewusst gekennzeichneten Ausnahmen je Node, Szene und geeignetem Regel-/Zugprofil** sowie Spielleiterkontrolle sind Teil des Beschlusses, nach den Vererbungs-/Bestandsprinzipien aus 02.25.

### 1. Fachliche Zielauswahl

- **Modus „nächster in der Zugreihenfolge“:** Die Next-Player-Node referenziert die **wirklich aktive und autorisierte Turnfolge** ihres zuständigen Zugkontexts. Der Turnmanager ermittelt aus dem gültigen bisherigen Teilnehmer einen passenden nachfolgenden Eintrag. Die Zugliste kann später beispielsweise für ein Puzzle oder für einen regelprofilabhängigen Kampf entstehen, **ohne jetzt ein universelles Initiative- oder Kampfsystem festzulegen**.
- **Modus „fester Spieler oder Charakter“:** Der Spielleiter kann als explizites Ziel einen **gültigen Kampagnenspieler** oder eine **bestimmte Spielfigur/Teilnehmerinstanz** auswählen, soweit dieser Zieltyp im jeweiligen Turnprofil erlaubt ist. **Spieleridentität, Charakteridentität und tatsächlicher Turn-Slot sind unterschiedliche Konzepte**; besitzt ein Spieler mehrere Charaktere, muss der Turnmanager mit einer dafür definierten gültigen Zuordnung arbeiten statt stillschweigend den falschen Token zu aktivieren.
- **Modus „Gruppe, Team oder Szene“:** Die Node kann einen ausdrücklich definierten **Teilnehmerkreis** (z. B. Gruppe, Team oder aktuelle Szenenfolge) als Quelle verwenden und den **nächsten tatsächlich geeigneten Teilnehmer dieser zugelassenen Folge** bestimmen. **Gruppenmitgliedschaft allein erzeugt weder einen unbekannten Spielerzug noch eine unbegrenzte Zufallsauswahl**. Die Art der gruppeninternen Turnreihenfolge und Fälle ohne gültigen Teilnehmer werden in der späteren Turnregelplanung präzisiert.
- **Kampagnenstandards und lokale Ausnahmen:** Für neue passende Nodes kann ein globales Standard-Zielverhalten gelten; **Node-/Szenen-/Turnkontext-Overrides** können eine der drei Alternativen festlegen. Wirksame Einstellungsquelle und Ausnahmen in der berechtigten SL-Vorschau klar kennzeichnen, Änderungen mit Bestands-/Vorlagenschutz aus 02.25. Die **gesamte Kampagneneinstellungsführung und sonstige Modulabschaltungen** bleiben bis nach allen Featurebereichen offen (02.48).
- **Berechtigter SL-Eingriff:** SL darf je gültigem Rollen-/Kampagnenprofil das Ziel in der Node festlegen oder übersteuern, aber kein nicht berechtigter Spieler darf durch manipulierte Node-Parameter beliebige fremde Züge aktivieren. Das Ausfallverhalten bei nicht verfügbarer Zielperson wurde in **02.69 C** als konfigurierbar beschlossen; konkrete Zeitwerte und globale Turn-Systemdetails bleiben offen.
- **Beispiel „Tür auf, Spielerwechsel“:** Spieler 1 ist in einem Rätseldurchlauf am Zug und öffnet die Tür **tatsächlich erfolgreich**. Der typisierte Tür-Node-Ausgang „geöffnet“ löst die Next-Player-Node aus. Im Reihenfolgemodus wird der nächste gültige Zuglisteneintrag aktiv; im Zielmodus z. B. ein ausdrücklich ausgewählter Spieler 2; im Gruppenmodus der nächste geeignete Spieler der definierten Rätselgruppe. **Die Türinteraktion selbst braucht keinen fest eingebauten Zugwechsel**, sondern die jeweilige autorisierte Graphkante.

### 2. Zugrechte und sichere Ausführung

- **Nur bei aktivem Turn-/Teilnehmerkontext:** Die Node braucht eine tatsächlich gültige Turnfolge oder ein ausdrücklich zulässiges Ziel innerhalb eines aktiven Puzzle-/Szenen-/Regelkontexts. In einer freien, nicht zugbasierten Szene **darf keine künstliche globale Spielersperre** durch die Node entstehen, solange das Szenenprofil keine solche Regel vorsieht.
- **Ziel zur Ausführungszeit serverseitig validieren:** Angegebene Spieler-/Charakter-/Gruppenreferenz, momentane Kampagnen-/Szenenteilnahme, Kontrollrechte, zulässige Turnfolge, eventuelle NPC-/SL-Sonderrolle, aktuelle Turn-/Objektversion und Node-Auslöser **vor der echten Zugübergabe prüfen**. Ein ursprünglich ausgewählter Zielspieler kann zum Ausführungszeitpunkt nicht mehr berechtigt oder nicht verfügbar sein; **02.69 C** legt konfigurierbare Warten-/Überspringen-/Ersatzziel-/SL-Entscheidungsregeln fest.
- **Kein unberechtigter Turn-Sprung:** Die Auswahl eines festen Ziels bzw. einer Gruppenzuordnung ist kein Freibrief, Aktionspunkte, Bewegung, Kampfregeln, Spielerzugrechte oder geheim gehaltene Szenendaten zu umgehen. Eine autorisierte Turnzustandsänderung ist **nicht** gleichbedeutend mit dem Ausführen einer Spielerfigur-Aktion.
- **Atomar und einmalig:** Pro gültigem **Node-Ereignis + Turngeneration** wird **höchstens ein** erfolgreicher Wechsel festgeschrieben. Gleichzeitige Node-Verbindungen, doppelte Tür-Events, Reconnect und Replay werden durch eindeutige IDs/Versionsprüfung und die Konfliktregeln 02.35 behandelt. Mehrfaches Senden des gleichen Türöffnungsereignisses darf weder mehrere Spieler überspringen noch einen Turn endlos weiterschieben.
- **Ungeeignetes Ziel:** Bei fehlender aktiver Zugliste, ungültiger Spieler-/Charakter-ID, nicht berechtigter Gruppe, bereits beendeter Aktion oder inkonsistentem Turnkontext darf das System **nicht stillschweigend irgendeinen anderen Spieler wählen**. Es soll einen für berechtigte SL/Nodes überprüfbaren Fehler-/Aussetzungsstatus liefern. Bei nach gültiger Zielwahl **tatsächlich nicht verfügbarem, ansonsten berechtigtem Ziel** gelten die in **02.69 C** beschlossenen Ausfallregeln; **ungültige/ungeprüfte Trigger und nicht autorisierte Zielrechte** dürfen dadurch niemals in einen erfolgreichen Wechsel verwandelt werden.
- **Geheimnisschutz:** Die aktuelle Zuganzeige und Übergabeereignisse werden nach gültigen Rollen-/Szene-/Fog-Rechten an die tatsächlich berechtigten Teilnehmer projiziert. Ein Teilnehmer einer anderen Szene darf nicht allein aus einem versteckten Turn-Slot die Existenz eines Geheim-NPCs oder einer unbekannten Spielerfigur erkennen.

### 3. Technischer Entwurf – keine finale API

1. **Zielprofil je Node:** Ein konzeptionelles `NextPlayerTargetPolicy` (nur beispielhafter Name) mit Auswahlmodi `next_in_order`, `specific_player_or_character` und `next_in_group`; dazu Referenzen auf den gültigen Turn-/Szenen-/Gruppenkontext, explizites Ziel oder Turn-Listendefinition, wirksame Kampagnen-/Node-/Szenenregelversion und markierte Overrides. Eine Identität wird als eindeutige ID referenziert, nicht durch angezeigten Benutzernamen.
2. **Turn-Kontext:** Der spätere serverautoritär verwaltete `TurnController` (Begriff nur beispielhaft) besitzt getrennte Referenzen für **Kampagne/Szene, aktive Zugfolge oder Teilnehmerslots, bisher aktiven Slot, besitzenden Spieler oder NPC-Modus, Turngeneration und geltende Regelversion**. Präzise Turn-/Kampfrundenregeln erst im Bereich 07.
3. **Pipeline:** Gültiges Tür-/Rätsel-/SL- oder anderes Node-Ereignis → typisierter Next-Player-Trigger → wirksame Zielpolicy mit geerbtem Standard und Ausnahmen → Prüfung des gegenwärtigen Zuginhabers/Turns → Auflösung des nächsten **berechtigten** Zielslots nach gewähltem Modus → **atomare, idempotente** Turnzustandsänderung → berechtigt projizierte Erfolg-/Ablehnungsnachricht bzw. typisierter Ausgang. Das Wählen des Ziels darf weder ungültige Türereignisse akzeptieren noch beliebige Node-Portrechte erschließen.
4. **Race-Condition-/Replay-Schutz:** Eine Turngeneration kann nur durch einen autorisierten erfolgreichen Trigger fortgeschrieben werden; mehrere gleichzeitig laufende Trigger müssen gemäß konfliktauflösender serverseitiger Regel 02.35 geordnet und geprüft werden. Konflikte/Fehlziel liefern nachvollziehbare Diagnose, **kein erzwungenes Doppel-Vorschalten**.
5. **Abnahme und Debug:** Isolierte Tests für feste/variierende Zugfolge, ausgewählten Spieler, bestimmte Figur bei Mehrcharakterbesitz, Gruppe/Team/Szene mit klarer Teilnahmeliste, ungültige/frühere Turnversion, erfolgreiche Tür, Tür-Fehlversuch, parallel betätigte Nodes, fehlende Zielberechtigung, Szenen-/Fog-Projektion und SL-Übersteuerung. Tests greifen nie in echte Zugfolgen ein.

**Weiter offen:** Numerische Warte-/Offlinefristen und deren präzise Semantik für die in 02.69 C beschlossenen Alternativen, Gruppen-Reihenfolgedetails, individuelle Turn-/Kampfaktionseinschränkungen, Zeit-/Rundenregeln, Ablauf/Inaktiv-Szenen, Offline-Reconnect und genaue Graph-Port-/SL-UX. Die drei Zielmodi und ihre gezielte Konfiguration sind jedoch beschlossen.

## 02.69 – Konfigurierbare Ausfall- und Vertretungsregeln für Next-Player-Nodes (12.10.2026)

**Verbindlich beschlossen: Variante C.** Wird der nach 02.68 **zunächst gültig ausgewählte nächste Zugteilnehmer** vor der tatsächlichen Turnübergabe **nicht verfügbar**, kann der Spielleiter für den passenden Kampagnen-, Szenen-, Zugfolgen- oder Node-Kontext konfigurieren, **ob gewartet/pausiert, automatisch ein berechtigter folgender Teilnehmer gewählt, auf ein ausdrücklich definiertes Ersatzziel umgeschaltet oder eine Spielleiterentscheidung eingeholt wird**. Die fachlichen Begriffe für Verfügbarkeit, optionaler Reconnect-Aufschub, Wartefrist und Gültigkeitsdauer sind ebenfalls **profilabhängig einstellbar**; Kampagnenstandards mit bewussten **Node-/Szenen-/Turnprofil-Ausnahmen** folgen dem allgemeinen Vererbungs-/Vorschau-/Bestandsschutz aus 02.25. **Ein unberechtigter oder ungültiger Trigger darf durch keine Fallbackregel jemals zu einem Zugwechsel werden.** Dieser Beschluss plant die Funktion, aber keinen bereits implementierten Turnmanager.

### 1. Konfigurierbare Strategien

- **Warten oder Pausieren:** Der zulässige Zielteilnehmer steht fest, ist aber beispielsweise temporär offline oder seine Figur vorübergehend nicht handlungsfähig. Je Profil hält der Turnmanager die Übergabe **als ausstehend oder pausiert** fest, ohne unbeabsichtigt den vorherigen Turn erneut als frei ausführbar zu gewähren oder einen alternativen Spieler zu aktivieren. Die genaue Darstellung, wer in der Wartephase Aktionen ausführen darf, wird mit den allgemeinen Zugrechten im späteren Featurebereich **07** definiert. Nur gültige Wiederverbindung, Wegfall der Blockade, ausdrückliche Fristregel oder SL-Eingriff darf die Wartephase auflösen.
- **In einer erlaubten Reihenfolge überspringen:** Ist ein zur Turnliste oder Gruppe gehörendes Ziel zum Ausführungszeitpunkt nicht verfügbar, darf der serverseitige Controller nach der **tatsächlich ausgewählten, autorisierten** Folge den nächsten **berechtigten, verfügbaren** Teilnehmer suchen, **nur wenn die wirksame Ausfallpolicy das Überspringen ausdrücklich erlaubt**. Die Suche ist endlich begrenzt und berücksichtigt die aktuell gültige Mitgliedschaft sowie Zug-/Szenenrechte. Ein fest ausgewähltes Ziel darf **nicht** allein wegen Offlinezustands eigenmächtig durch irgendeine andere Person ersetzt werden.
- **Festes Ersatzziel:** Ein berechtigter SL kann für geeignete Node-/Turn-Kontexte **einen ausdrücklich referenzierten Ersatzspieler, Ersatzcharakter oder zugelassenen Ersatzzielslot** konfigurieren. Die Ersatzidentität wird genau wie die ursprüngliche Wahl nach 02.68 vor Ausführung serverseitig geprüft. Ein ungültiges Ersatzziel bewirkt keine implizite Freigabe eines beliebigen Zugs; eine weitere erlaubte Alternative oder ein nachvollziehbarer nicht erfüllter Zustand kann in der Policy vorgesehen werden.
- **Ausdrückliche SL-Entscheidung:** Bei nicht verfügbarem Ziel darf der Controller **nur die dafür berechtigte Spielleitung** über eine ausstehende Entscheidung informieren. Der SL kann im Rahmen seiner Berechtigungen gültig fortsetzen, ein berechtigtes Ersatzziel bestätigen, den Zug pausieren oder den Vorgang abbrechen. **Bis zur ausdrücklichen, erneut servervalidierten Entscheidung findet kein als freigegeben fingierter Zielzug statt.**
- **Verfügbarkeit definieren:** Profilabhängige Ursachen können u. a. **fehlende Verbindung/offline, Reconnect in vereinbarter Nachfrist, temporär nicht handlungsfähige Figur, ausdrücklich gesperrter Zugslot, verlassenes Team oder inaktive Szene** sein. **„Nicht verfügbar“ ist nicht dasselbe wie „unberechtigter Spieler oder ungültiger Node-Auslöser“**: bei fehlender Autorisierung wird der Vorgang zurückgewiesen, auch wenn ein Fallback konfiguriert ist.
- **Warte- und Offlinefristen:** Berechtigte Kampagnen-/Turn-/Node-Policies können Fristen für Wiederverbindung, Pause, Ablauf und anschließendes erlaubtes Fallback vorsehen. **Echtzeit- und Spielrundenfristen aus 02.15–02.16 bleiben getrennt**, ohne heimliche Umrechnung. Konkrete Zeitwerte, Wirkung einer allgemeinen Kampagnenpause und das Ablaufverhalten in inaktiven Szenen (02.19) sind weiterhin offen. Kein willkürlicher Default-Timer.
- **Räumliche/spielerische Sonderfälle:** Ziel ist ein bestimmter Spieler mit mehreren Figuren, eine geänderte Gruppe oder ein außerhalb der aktuell erlaubten Szene befindlicher Charakter: **Teilnehmer-/Turnslot-ID, tatsächliche Figurenkontrolle und Berechtigungen** sind getrennt auszuwerten. NPC-Züge oder automatisierte Gegner bleiben unter der allgemeinen NPC-Steuerung (02.54) bzw. späteren Turn-/Kampfregeln; eine Node stellt nicht selbst eine neue KI bereit.

### 2. Zusammenspiel mit vorherigen Entscheidungen

- **Nur nach gültigem Trigger:** Beispiel aus 02.67: Spieler 1 **öffnet die Tür tatsächlich**, und der durch 02.68 ausgewählte Spieler 2 ist offline. Jetzt darf **eine** 02.69-Ausfallregel greifen. Eine **gesperrte Tür, fehlgeschlagene Prüfung, bereits offener Zustand oder unberechtigter Türimpuls** erzeugt dagegen **gar keinen** Next-Player-Zugwechsel, auch nicht zu einem Ersatzziel.
- **Turnrechte bleiben geschützt:** Eine erfolgreiche, pausierte oder auf SL wartende Zugübergabe muss den aktuell gültigen Turnkontext konsistent fortführen; es darf durch Warte-/Reconnectereignisse weder **zwei gleichzeitig autorisierte Zuginhaber** noch ein ungeprüfter NPC-/Spieler-Aktionswechsel entstehen.
- **Zugfolgen und individuelle Konfiguration:** Für die drei 02.68-Zielmodi (nächster in Liste, bestimmter Spieler/Charakter, Gruppe/Team/Szene) können passende unterschiedliche Ausfallstrategien gelten. Eine neue Kampagnenstandardregel darf bestehende explizite Node-Ausnahmen nicht ohne die Bestandsentscheidung aus 02.25 überschreiben.
- **Rechte- und Geheimnisschutz:** Nur tatsächlich berechtigte Teilnehmer erfahren, wer auf welchen Spieler wartet oder aus welcher Teilnehmergruppe ein Ersatz gesucht wird. Durch Fallback darf niemand versteckte NPCs, unbekannte Szenen oder SL-interne Teilnehmerlisten in Clientdaten oder der sichtbaren Zuganzeige entdecken.
- **Node-Graph-Komposition:** Die Next-Player-Node soll bei zulässiger Konfiguration **typisiert unterscheidbare Resultate** wie erfolgte Übergabe, wartend, SL-Entscheidung erforderlich oder abgelehnt/fehlgeschlagen für weitere erlaubte Nodes anbieten können. Konkrete Portnamen und zulässige Benachrichtigungen sind später festzulegen; ein Statusausgang darf weder automatisch einen zweiten Turn noch einen Alarm/eine Tür ohne gültige Verbindung betätigen.

### 3. Technische Planung (noch keine endgültige API)

1. **`TurnFallbackPolicy` (nur Beispiel):** Versionsbezug auf die gültige Next-Player-Zielpolicy aus 02.68, gewählten Ausfallmodus (`wait`, `skip_in_sequence`, `explicit_substitute`, `gm_decision` als Entwurfsnamen), Verfügbarkeitskriterien, Fristgrundlage, optionale Warte-/Reconnectfristen, ausdrücklich definierte Ersatzziele und Herkunft wirksamer Kampagnen-/Node-/Szenen-Overrides.
2. **`PendingTurnHandoff` als konzeptioneller Zustand:** Bei **berechtigtem** Quellereignis eine eindeutige Turn-/Node-/Ziel-/Triggerreferenz mit Ausgangs-Turngeneration, ursprünglichem Kandidaten, aktuellem Warte-/Ersatzzielstatus, Fälligkeit bzw. SL-Freigabestatus vorsehen. **Keine voreilige Festlegung einer Doppel-Aktivierung**: Solange eine Übergabe aussteht, werden Zugrechte zentral durch einen konsistenten Turncontroller geregelt.
3. **Zweifache Sicherheitsprüfung:** Erst **Quellereignis, zugelassene Graphverbindung, zuständiger alter Zuginhaber und aktuelle Turngeneration** prüfen; erst danach ist Ausfall-/Verfügbarkeitsbehandlung zulässig. Jedes neu vorgeschlagene Ziel (auch Ersatz, Gruppenfolge, Reconnect oder SL-Wahl) muss zusätzlich **aktuell berechtigt und nach passendem Turnprofil verfügbar** sein, bevor der Controller atomar eine neue Generation festschreibt.
4. **Deterministisches Replay-/Fristverhalten:** Eindeutige Ereignis-/Handoff-/Turngeneration-/Timer-IDs, atomare Statusübergänge, idempotentes Wiederaufgreifen und Begrenzung von Ersatz-/Skipketten vorsehen. Reconnect, Neustart, gleichzeitige Turn-Nodes und verzögerte Timer dürfen nicht aus demselben erfolgreichen Türereignis **mehrere** Zugwechsel machen. Konfliktauflösung aus 02.35 beachten.
5. **SL-Anzeige und Simulation:** Berechtigter Debugger zeigt Quelle/Türzustand, gültige Zielpolicy, ursprünglichen Zielslot, Grund der Nichtverfügbarkeit, tatsächlich wirksame Fallbackregel, ggf. Wartedauer, SL-Freigabe und schließlich erfolgreich aktivierten Teilnehmer bzw. Ablehnung. Isolierte Tests nach 02.31–02.34 dürfen **keinen realen Turnwechsel, keine Rollenfreigabe und keine Side Effects** verursachen.

### 4. Abnahmebeispiele

- Spieler 1 öffnet die Tür, Spieler 2 ist offline: Bei `wait` bleibt eine ausstehende Übergabe bestehen. Reconnect darf **höchstens einmal** den gültigen Zug aktivieren; währenddessen gibt es keine zweite unautorisierte Aktion.
- Dieselbe Situation mit explizit erlaubter `skip_in_sequence`-Policy: Der Controller wählt nur einen **wirklich berechtigten, verfügbaren** Teilnehmer der aktiven Liste. Fehlt ein solcher, bleibt der Vorgang nachvollziehbar unerfüllt.
- Bei gezielter 02.68-Spielerauswahl darf der Server nur auf einen **bewusst eingetragenen und erlaubten Ersatzspieler** wechseln; nicht automatisch den nächsten beliebigen Online-Nutzer.
- Bei `gm_decision` wird der Wechsel erst nach einer gültigen SL-Aktion ausgeführt; ausstehende, abgelehnte oder veraltete Bestätigungen verändern den aktiven Turn nicht.
- Ist die Tür noch verschlossen, der Öffnungsversuch gescheitert, der auslösende Spieler nicht am Zug oder die Node nicht berechtigt, tritt **auch bei konfiguriertem Fallback kein Zugwechsel** ein.
- Ein Offline-/Reconnect-Wechsel mit doppeltem Event, zwei parallelen Next-Player-Nodes und Ablauf einer Frist darf keinen doppelten Turnwechsel verursachen.
- Verborgene Team-/NPC-/Szenen-Teilnehmer werden nur den dafür Berechtigten angezeigt; SL-Debug und isolierte Tests zeigen die tatsächliche Kausalkette.

**Noch offen:** Konkrete Warte-/Reconnectdauer, Reihenfolge mehrerer eventueller Fallbackstufen, Definition handlungsunfähiger Figur je Regelprofil, Verhalten bei Kampagnenpause/inaktiver Szene, Unterschiede Spieler/Charakter/NPC/Team, genaue Zugrechte, Node-Portbezeichnungen und UI. Diese Punkte werden bei der späteren Zug-/Regelplanung (07) spezifiziert; **die vier Ausfallstrategien sind mit 02.69 C als Funktionen beschlossen.** Die allgemeine Kampagnen-Einstellungsführung und Abschaltung anderer Module bleiben wie in 02.48 ausdrücklich erst für nach dem gesamten Feature-Workshop vorgesehen.

## 02.70 – Konfigurierbare parallele Zugfolgen auf Kampagnen-, Szenen-, Gruppen- und Rätselebene (12.10.2026)

**Verbindlich beschlossen: Variante C.** AdventureShift darf je **gültigem Kampagnen-/Regelprofil mehrere gleichzeitig aktive und voneinander unabhängige Zug-/Turn-Kontexte** unterhalten: **eine kampagnenweite Folge**, **eigene Folgen einzelner Szenen** sowie **getrennte Folgen einzelner Gruppen, Teams, Rätsel oder geeigneter Teilbereiche**, gegebenenfalls mehrere unabhängige Rätselgruppen innerhalb **derselben** Szene. Welche Ebenen eine Kampagne nutzt und wie neue Turn-Kontexte angelegt/zugewiesen werden dürfen, ist konfigurierbar. **Globale Kampagnenstandards und bewusst markierte Ausnahmen pro Szene, Gruppe, Turn-Kontext und Next-Player-Node** nach 02.25. Eine Node kann nur den **ausdrücklich ausgewählten wirksamen Turn-Kontext** beeinflussen, niemals stillschweigend einen anderen. Dies beschreibt ein Produktziel und technische Planung, **keine implementierte Turnengine oder abgeschlossene Kampfregel**.

### 1. Fachliches Modell paralleler Zugfolgen

- **Kampagnenweiter Kontext:** Eine geeignete Kampagne darf eine gemeinsame Zugfolge verwenden, ohne dafür alle anderen konfigurierbaren Möglichkeiten verpflichtend aktivieren zu müssen. Eine bestehende kampagnenweite Folge ist nicht automatisch ein globaler Lock für jede Figur und jede freie Szene.
- **Szenenkontext:** Geeignete Szenen dürfen **eigene aktive Turnfolgen** mit eigenem Zuginhaber und eigener Turngeneration führen. Ein Tür-Node in Szene A, der an eine Next-Player-Node für **Kontext A** angeschlossen ist, beendet weder das parallele Rätsel noch einen Kampf in Szene B.
- **Gruppen-/Team-/Rätselkontext:** In derselben Szene können beispielsweise **Rätselgruppe Rot und Rätselgruppe Blau** voneinander unabhängige Spieler-/Figurenreihenfolgen besitzen. Die Mitgliedschaft eines Spielers in einer Szene verpflichtet ihn nicht automatisch zur Teilnahme an allen dort existierenden Zuglisten.
- **Explizite Kontextbindung einer Node:** Die Next-Player-Node aus 02.67 führt eine vom SL bzw. geerbten Profil festgelegte **Turn-Kontext-Referenz**. Zielauswahl aus 02.68 und Nichtverfügbarkeits-/Fallback-Policy aus 02.69 beziehen sich **zuerst auf diesen Kontext und dessen erlaubte Teilnehmer**. Ein „nächster Spieler“ wird nicht aus einer fremden Szene oder dem globalen Online-Verzeichnis erraten.
- **Unabhängige Fortschrittszustände:** Jeder aktive Kontext hat eigene **Zugliste/Teilnehmerslots, aktuellen Zuginhaber, Zug-/Turngeneration, eventuelle ausstehende Übergabe, Ausfallpolicy und Freigabe-/Sperrbedingungen**. Ein gültiger Wechsel in Kontext A aktualisiert ausschließlich A; Kontext B verbleibt bei unverändertem Spieler, sofern keine **zusätzliche explizit autorisierte** Kontext-Verknüpfung vorliegt.
- **Gemeinsame Spielwelt, getrennte Turnkonten:** Mehrere Turn-Kontexte sind **keine getrennten Kopien der Kampagnenwelt**: dieselbe physische Tür, derselbe Charakter und dasselbe Inventar dürfen nicht durch parallele Teilkontexte doppelt erzeugt oder widersprüchlich überschrieben werden. Objekt-/Node-/Bewegungsänderungen aus unterschiedlichen Kontexten brauchen die allgemeinen serverseitigen Rechte-, Objektzustands- und Konfliktregeln aus 02.13/02.35.
- **Zeit- und Regelprofil:** Ein Kontext kann gemäß seiner gültigen Regeln zugbasiert arbeiten, während andere Szenen frei, zeitbasiert oder in einem separaten Rätselmodus laufen. Die Trennung von Echtzeit und Spielrunden aus 02.15–02.16 bleibt bestehen; es gibt **keine stillschweigende Synchronisierung oder Umrechnung** der Runden verschiedener Kontexte.
- **SL-Kontrolle und globale Defaults:** Ein berechtigter Spielleiter kann den Kontext einer Next-Player-Node auswählen sowie Kampagnen-/Szenen-/Rätsel-Voreinstellungen und gezielte Ausnahmen verwalten. Die wirksamen Herkunftsregeln werden nachvollziehbar gezeigt (02.25); der genaue Kampagnenerstellungsassistent und vollständige Feature-Abschaltregeln werden wie in 02.48 bis nach allen Featureentscheidungen aufgeschoben.

### 2. Kontextgrenzen, Mitglieder und Next-Player-Nodes

- **Gültige Mitglieder statt globale Spielerliste:** Jede Zugfolge führt eine **eigenständig erlaubte Teilnehmermenge** mit getrennten Referenzen auf Spieler, gesteuerte Figur, ggf. später NPC-Turnslot und passende Szene/Gruppe. Die Kriterien, ob derselbe Charakter **zeitgleich mehreren Zugkontexten angehören darf**, sowie der eigentliche **Eintritt/Wechsel** zwischen Kontexten sind **nicht automatisch aus 02.70 entschieden** und folgen in 02.71.
- **Keine ungefragte querlaufende Übergabe:** Eine Node, die für Rätsel A konfiguriert ist, darf weder die Turngeneration von Rätsel B verändern noch einen Spieler aus einer fremden Gruppe aktivieren. Auch Zielmodus `specific_player_or_character` aus 02.68 unterliegt **weiterhin** der Prüfung der Teilnehmerberechtigung in **diesem** Kontext.
- **Bewusste übergreifende Verbindung:** Wenn ein Szenen- oder Gruppenereignis fachlich in einem anderen Kontext wirken soll, muss ein **explizit autorisiertes und typisiertes** Graph-/Regelereignis mit gültigem Quell-/Zielkontext vorhanden sein; bloße Verbindung zwischen Szenen oder gleichnamige Spieler genügt nicht. **02.71 C** legt den regel-/Node-abhängigen und berechtigt validierten Mitgliedschaftswechsel fest; eine parallele Mehrfachmitgliedschaft folgt gesondert unter 02.72.
- **Warten, Skip und Ersatz bleiben lokal:** Ausfallregeln 02.69 werden **innerhalb der ausdrücklich ausgewählten gültigen Turnfolge** ausgeführt. Ist Spieler 2 im Rätsel A offline, so pausiert oder ersetzt das **nur den berechtigten Übergang in A**. In einem unabhängigen Rätsel B darf deshalb niemand übersprungen werden.
- **Geheimnisse und Darstellung:** Turnlisten, Identitäten, ausstehende Übergaben, Offline-/Teilnahmestatus und Zuganzeige dürfen nur an gemäß **Szenen-, Gruppen-, NPC-/Fog- und Kampagnenrollen** berechtigte Teilnehmer projiziert werden. Die Existenz eines geheimen Kampfes oder Rätsels in einer anderen Szene wird Spielern nicht über die Liste paralleler Turn-Kontexte offengelegt.
- **Keine doppelten Zugrechte oder globalen Sperren aus Versehen:** Ein Spieler in einer parallelen Rätselgruppe darf nicht zufällig eine gültige Aktion in einer anderen, fachlich unabhängigen Szene blockieren. Andererseits berechtigt eine aktive Turnmarkierung in A **nicht automatisch** zur Bewegung oder zur Ausgabe gemeinsamer Ressourcen in B. Das spätere Regelprofil muss bei geteilten Figuren/Ressourcen die gültigen Rechte und die Konfliktbehandlung bestimmen.

### 3. Technischer Entwurf (keine feste API)

1. **Eigenständiger `TurnContext` (konzeptioneller Name):** Stabile Kontext-ID, Kampagnen-ID, optional Szenen-/Rätsel-/Team-/Gruppenbezug, Kontexttyp `campaign`/`scene`/`group`/`team`/`puzzle` als Beispiel, konfiguriertes Zugprofil, Teilnehmerslots, aktueller Slot, **Kontext-eigene Turngeneration**, Aktiv-/Pause-/Abschlussstatus und Policyversion. `TurnContext` ist keine zwingende neue Datenbanktabelle, sondern ein fachliches Modell.
2. **Next-Player mit explizitem Kontext:** Konzeptionell `NextPlayerNode.turnContextRef` bzw. gleichwertige Referenz, deren Zugänglichkeit, Existenz und Gültigkeit der Server gegen Szene/Graph/Kampagnenrechte prüft. Zielwahl (02.68) und Ausfalloptionen (02.69) werden **in diesem Kontext** ausgewertet. Eine Node ohne gültige Kontextbindung erzeugt **keine** globale Ersatzübergabe.
3. **Isolierter atomarer Turnwechsel:** Gültiges Türauf-/Node-Ereignis → Prüfung der typisierten Graphkante und zulässigen Kontextquelle → TurnContext laden → alte Turngeneration und aktuellen Besitzer validieren → gültigen nächsten Teilnehmer nach 02.68/02.69 wählen → **atomarer Commit genau der betroffenen Kontextgeneration** → berechtigt projiziertes Ereignis. Der Token-/Objektzustand bleibt gemäß den eigenen Welt- und Konfliktregeln gesondert konsistent.
4. **Getrennte Sequenzen, geteilte Weltobjekte:** Turngenerationen/Übergabe-IDs und Teilnehmerlisten **pro Kontext** führen, statt ein einzelnes globales „currentPlayer“-Feld für die ganze Kampagne. Zugänderung A darf B nicht überschreiben; wenn zwei Kontexte eine **geteilte Tür** betätigen, schützen die globalen Objektzustands-/Node-Konfliktregeln aus 02.35 vor doppelten Öffnungen. Es wird nicht ohne weiteres angenommen, dass eine Figur in zwei Kontexten doppelte Aktions-/Ressourcenbudgets erhält.
5. **Replay-/Node-Loop-/Reconnect-Schutz:** Schlüssel aus Quellereignis-ID, wirksamer Turn-Kontext-ID, alter Kontextgeneration und Node-/Auslöserreferenz; innerhalb des betroffenen Kontexts **höchstens eine gültige Änderung pro Event/Generation**, selbst bei mehrfachen Graphkanten oder Reconnect. Cross-Context-Effekte verlangen getrennte gültige, referenzierte Events und Rechte; keine automatische Endlosschaltung zwischen Kontexten.
6. **Debug/SL-Vorschau/isolierte Tests:** Berechtigte SL können eine Szene mit zwei Rätselgruppen oder zwei Szenen mit getrennten aktuellen Zugbesitzern simulieren. Tests: Öffnen einer Tür in A aktiviert den nächsten Spieler in A, **B bleibt exakt unverändert**; fester Spieler außerhalb A wird abgelehnt; parallele Fallback-/Reconnect-Events beeinflussen nur ihren eigenen Kontext; gleichzeitiger Zugriff auf eine gemeinsame Tür ist atomar; geheime Kontexte werden anderen Gruppen nicht offenbart; getrennte Versionen überstehen Neustart. Isolierter Test darf **keine echten Turn- oder Szenenänderungen** verursachen (02.31–02.34).

### 4. Abnahmebeispiele

- In Szene A (Spieler 1 → Spieler 2) und Szene B (Spieler 3 → Spieler 4) sind gleichzeitig zwei unabhängige Zugfolgen aktiv. **Tür geöffnet in A** → Next-Player-Node für A → Spieler 2 übernimmt A; **Spieler 3 bleibt in B am Zug**.
- Innerhalb einer Szene laufen die Rätselgruppen Rot (Spieler 1/2) und Blau (Spieler 3/4) mit getrennten Turngenerationen. Ein Ereignis der Gruppe Rot verändert weder Blaufolge noch deren Warten-/Fallbackzustand.
- Eine Node ohne gültige Kontext-ID, fremde Gruppe oder nicht berechtigter Kontextwechsel wird serverseitig abgelehnt; kein stillschweigender globaler Zugwechsel.
- Eine Figur nutzt ein shared Szenenobjekt: Es gibt nur den einen autoritativen Türzustand; parallele Zugfolgen dürfen keine zweite Tür-Instanz oder neue Aktionsrechte erschaffen.
- Die SL sieht in der Debugansicht mehrere Kontexte und deren tatsächliche Versions-/Zugzustände; ein Spieler einer anderen Szene erhält **keine** geheimen Teilnehmer-/NPC-Daten.
- Nach Reconnect oder doppelter Ereigniszustellung wird pro betroffenem Kontext höchstens der erlaubte einzelne Turnwechsel wirksam, andere Turnkontexte bleiben unberührt.

**Offen:** Eintritt/Austritt/Übergang von Figuren zwischen unabhängigen Turn-Kontexten (02.71), gleichzeitige Mitgliedschaft eines Charakters in mehreren Folgen, Ressourcen-/Aktionskonflikte, Gruppenregistrierung und Context-UI, Zeit-/Runden-/Kampfprioritäten, Pausen-/inaktive Szenen und genaue Semantik cross-szenischer Übertragung. Es wird **kein allgemeines Initiative-/Kampfsystem** oder genereller globaler Aktivitätslock vorweggenommen.

## 02.71 – Berechtigter, konfigurierbarer Wechsel zwischen Zugkontexten (12.10.2026)

**Verbindlich beschlossen: Variante C.** Eine Figur darf in AdventureShift je gültiger **Kampagnen-, Szenen-, Gruppen-/Team-/Rätsel- und Turn-Kontext-Regel** ihren Zugkontext verlassen, einem anderen beitreten oder einen geregelten Transfer durchführen. **Auslöser können berechtigte Spielleiteraktionen, gültige Szenen-/Raum-/Gruppenereignisse oder ausdrücklich verkabelte, typisierte Node-Verbindungen sein.** Pro Quelle und Ziel sind Eintritt, Austritt, Behandlung laufender und ausstehender Züge, Beginn neuer Zugrechte und Zugreihenfolgen konfigurierbar. **Globale Defaults mit sichtbar markierten Ausnahmen pro Szene, Gruppe/Team/Rätsel, Node oder Turn-Kontext**, entsprechend 02.25. Ein Szenenwechsel erzeugt **nicht ungefragt** in allen Kampagnen einen Turnkontextwechsel; ebenso löst eine geöffnete Tür oder eine Next-Player-Node aus 02.67 nur das aus, was ihre gültigen typisierten Verbindungen tatsächlich vorsehen. **Keine unbeabsichtigten zusätzlichen Aktionen, Ressourcen oder doppelten Züge.** Ob dieselbe Figur bewusst gleichzeitig in mehreren Turnkontexten vertreten sein darf, ist die offene Folgefrage **02.72**. Kein Programmcode implementiert.

### 1. Fachliche Ein- und Austrittsregeln

- **Berechtigte Trigger:** Der SL kann einen Figurenslot bewusst einem Zielkontext zuordnen; passende Szenen-/Raum-/Team-/Gruppeninteraktionen oder gültig verbundene Nodes können diesen Vorgang nur auslösen, wenn die aktive Policy den Vorgang und die Quelle erlaubt. Eine Türöffnung allein bedeutet **weder automatisch Raumverlassen noch Szenenübertragung oder Eintritt in eine andere Turnfolge**. Für jeden fachlichen Schritt kann die Spielleitung separate, passende Graphkanten bestimmen.
- **Quell- und Zielkontext:** Beide Turnkontexte aus 02.70 werden durch stabile IDs und getrennte Generationen geprüft. Der Ausgangs-Kontext kann eine geregelte Austrittsaktion verlangen; der Ziel-Kontext hat seine eigene Eintrittsregel. Eine Gruppe, Szene oder gleichnamiger Benutzer ist **kein automatischer Beitrittsnachweis**.
- **Eintrittszeit und Position in der Reihenfolge:** Die wirksame Regel kann nach konkreter Kontextart bestimmen, wann eine Figur Mitglied wird und ab wann sie einen Zug antreten darf. Eine sofortige Freigabe der Figur oder ein fester Listenplatz sind **nicht universell vorgeschrieben**; Einfügeposition, Startzeit und ggf. erforderliche SL-Zustimmung werden in der späteren Turn-/Regelplanung konkretisiert.
- **Aktiver alter Zug:** Wird der aktuelle Zuginhaber selbst übertragen, muss die gültige Austrittsregel klären, ob die bisherige Aktion zunächst korrekt abgeschlossen, der Zug gültig übergeben oder bis zu einer Freigabe pausiert wird. Ein Kontextwechsel darf **nicht ungefragt andere Teilnehmer überspringen oder eine fremde Kampfrunde beenden**.
- **Ausstehende Node-Übergaben:** Noch nicht erfüllte Next-Player-Handoffs und Offline-/Fallbackregeln aus 02.68–02.69 werden kontrolliert geprüft und je Konfigurationsregel abgeschlossen, angehalten oder als nicht mehr gültig verworfen. **Ein altes Event darf später keine bereits übertragene Figur ein zweites Mal aktivieren.**
- **Rechte und Identitäten:** Eindeutig zwischen **Spieleraccount, kontrollierter Figur, tatsächlichem Welt-Token und Turn-Mitgliedschaft** unterscheiden. Verändert wird nur die gewählte berechtigte Teilnehmer- oder Kontextzuordnung, nicht automatisch die physische Tokenposition, Spielerrolle, NPC-KI oder die berechtigte Kontrolle über mehrere Figuren.
- **Eine reale Spielwelt:** Derselbe Charakter, Inventar, Gegenstände, Zauber-/Skillressourcen und Weltobjekte sind trotz der verschiedenen Zuglisten **keine getrennten Kopien**. Ein Kontexttransfer erzeugt **keinen kostenlosen zusätzlichen Zug** oder doppelte Aktions-/Bewegungsressourcen. Die konkrete Bewirtschaftung bewusster Mehrfachmitgliedschaften ist **02.72** vorbehalten.
- **Standards und SL:** Aus einem kampagnenweiten Profil folgen je Szene/Gruppe/Node/Turnkontext geltende Standard-Austritts-/Eintrittsregeln, mit markierten Overrides, Herkunft, SL-Vorschau und Bestandsänderung gemäß 02.25. Gesamte Kampagnen-Einstellungsführung erst nach dem Featureworkshop (02.48).

### 2. Technische Umsetzungsskizze (noch keine fertige API)

1. **Konzeptionelle Modelle:** Eine Turn-Mitgliedschaft mit stabilen Figuren-, Turnslot- und Kontextreferenzen; eine versionierte Transfer-Policy für erlaubte Trigger, Quell-/Zielregeln, Pending-Handoffs, Spielleiterfreigaben und Zugrechte; ein Transferauftrag mit **gültiger ursprünglicher Node-/SL-/Szenenaktion**. Beispielbegriffe: TurnContextMembership, TurnContextTransferPolicy, TurnContextTransferRequest. Die genaue Datenbank- oder Portstruktur ist noch offen.
2. **Autorisierte Transferprüfung:** Serverseitig vor Änderung die Kontrolle über die konkrete Figur, den alten und den neuen Kontext, gültige Szenen-/Gruppenmitgliedschaften, zulässige Graphquelle, Spieler-/NPC-/SL-Rechte, Turngenerationen, aktiven Zug und bestehende ausstehende Handoffs prüfen. **Unzulässige oder veraltete Quellaktionen erzeugen keinen Transfer**, auch nicht über vermeintliche Fallbacks.
3. **Atomarer Zustandswechsel:** Quell-Mitgliedschaft und Ziel-Mitgliedschaft mit den tatsächlich erlaubten Zug-/Turnzuständen als **zusammenhängenden, konsistenten Übergang** behandeln. Scheitert die Zielaufnahme durch fehlende Rechte oder konkurrierende Ereignisse, darf die Figur nicht bereits dauerhaft aus dem Quellkontext verschwunden sein. Implementierungsdetail wie Datenbanktransaktion/Versionssperre bleibt offen.
4. **Idempotenz und gemeinsamen Weltzustand schützen:** Pro Ursprungsereignis, Figur und alter/neuer Turngeneration höchstens eine bestätigte Transferaktion. Doppelter Tür-Node, gleichzeitiger Gruppenwechsel, Reconnect oder Graphschleife erzeugen keine zweite Mitgliedschaftsänderung und keine zweite Tür/Inventar-/Würfel-/Zugwirkung. Gemeinsame Objektkonflikte weiterhin nach 02.35 lösen.
5. **Geheimnisschutz und Projektionen:** Verborgene Teilnehmerlisten, Gruppen/Rätsel, NPCs und Szenen dürfen nicht durch die Liste möglicher Ziel-Kontexte oder Transfer-/Fehlermeldungen bei unberechtigten Spielerclients auftauchen. Berechtigte SL sehen tatsächliche Quelle, Ziel, aktive Regel-/Ausnahmekette und Ausführung im geschützten Debug.
6. **Isolierte Tests:** SL-Transfer, genehmigter Raum-/Szenenwechsel, Gruppen-/Rätsel-Node, ungültige oder bereits offene Tür, abgelehntes Ziel, veraltete Turngeneration, ausstehender Next-Player-Handoff, konkurrierende Node-Trigger, mehrfacher Event, Reconnect und private Szenen. Simulation aus 02.31–02.34 verändert keine echte Zugfolge oder Tokenposition.

### 3. Abnahmebeispiele

- Spieler 1 verlässt per berechtigtem Raum-/Gruppenwechsel Zugkontext A und tritt gemäß gültiger Eintrittsregel Kontext B bei; die anderen Zuginhaber bleiben ohne eigenen autorisierten Trigger unverändert.
- Spieler 1 öffnet die Tür: Die ausdrücklich verbundene Next-Player-Node kann in A den Zug weitergeben; **nur ein zusätzlicher gültiger Transferauslöser** darf die Figur selbst in B übernehmen.
- Ein Node versucht die Figur in eine geheime, nicht berechtigte Zielgruppe aufzunehmen: **kein Transfer, kein Berechtigungs- oder Geheiminformationsleck**.
- Ein Transfer wird bei einer bereits wartenden 02.69-Zugübergabe angefordert: Vor endgültigem Wechsel wird der alte Pending-Zustand regelgerecht abgeschlossen/verwaltet, ohne einen alten Turn später doppelt zu aktivieren.
- Zwei gleiche oder konkurrierende Transferimpulse erzeugen höchstens einen gültigen Übergang; das Inventar wird nicht verdoppelt und keine kostenlose Bewegung/zusätzliche Aktion vergeben.
- Der SL kann die Effektiv-Policy und den echten alten/neuen Kontext prüfen, ohne im isolierten Test die reale Kampagne zu ändern.

**Weiter offen:** Gleichzeitige Mitgliedschaft derselben Figur in mehreren Turnkontexten (02.72), daraus folgende gemeinsame Aktions-/Ressourcenregeln, exakte Position im Ziel-Zugplan, NPC-/Offline-/Pausen-/Initiative-/Kampfdetails (07), konkrete Typports, UI und Kampagnen-Einstellungsassistent nach vollständigem Workshop.

## 02.72 – Konfigurierbare Mehrfachmitgliedschaft in parallelen Zugfolgen (12.10.2026)

**Verbindlich beschlossen: Variante C.** Eine Figur kann je Kampagne, Regelprofil und Turn-Kontext **exklusiv einer aktiven Zugfolge** angehören oder **bewusst in mehreren voneinander unabhängigen Zugfolgen gleichzeitig Mitglied sein**. Kampagnenweite Standards und ausdrücklich markierte Figur-, Szenen-, Gruppen-, Rätsel- und Turn-Kontextausnahmen nach 02.25 mit berechtigter SL-Kontrolle. Die Entscheidung betrifft die Mitgliedschaft und den Ressourcenschutz, nicht eine fertige Kampfrunde oder einen kostenlosen neuen Zug.

### 1. Mitgliedschaft und Grenzen

- **Exklusiv:** Die Figur ist höchstens in der zulässigen einen aktiven Zugfolge vertreten. Für einen Wechsel gelten die berechtigten atomaren Austritts-/Eintrittsregeln aus 02.71; eine unberechtigte zweite Mitgliedschaft wird nicht einfach hinzugefügt.
- **Mehrfach:** Dieselbe kanonische Figur darf bei bewusst erlaubt konfigurierter Policy mehrere gültige Turnslots in den parallelen Kontexten aus 02.70 besitzen. Die Kontexte behalten getrennte Zuglisten, Turngenerationen und eigene Next-Player-/Fallbackregeln aus 02.67–02.69. Eine Mitgliedschaft ist noch **keine aktive Zug- oder Spielweltaktionsfreigabe**.
- **Ein Charakter, eine Spielwelt:** Figur, aktuelle Position, Gegenstände/Inventar, Munition, Zauber-/Fähigkeits-/Skillressourcen sowie global verfügbare Aktions- und Bewegungspunkte bleiben **einmalige tatsächliche Figurenwerte**, nicht mehrere Kopien pro Zugfolge. Zwei Turnslots erlauben weder das zweimalige Verwenden desselben Schlüssels noch zwei Ausgaben der letzten Munition.
- **Explizit getrennte Budgets nur nach Regeln:** Ein passendes Kampagnen-/Regelprofil darf bewusst **eigene kontextgebundene Aktions- oder Rätselbudgets** anlegen. Diese müssen ausdrücklich definiert und begrenzt werden. Ihr Vorhandensein vervielfältigt keine gemeinsam geteilten Lebenspunkte, Items, Tokenpositionen oder globalen Aktionsressourcen. Allgemeine Verbrauchswerte/Regelprofile werden in 03/05/07 konkretisiert.
- **Spieler und Figuren unterscheiden:** Mehrere verschiedene Figuren eines Spielers haben verschiedene reale Figurenressourcen; eine einzelne Figur in mehreren Kontexten hat weiterhin nur einen Ressourcenzustand. NPCs erben daraus keine automatische KI oder zusätzlichen Rechte; NPC-Kontrollmodus 02.54 gilt.
- **Sichtbarkeit und SL-Overrides:** Effektive Figur-/Kontext-Regeln und Ausnahmen sind für berechtigte SL nachvollziehbar. Unberechtigte Spieler dürfen aus einer zweiten Mitgliedschaft nicht auf versteckte NPCs, andere Rätsel oder geheime Teilnehmerlisten schließen. Der vollständige Kampagnen-Einrichtungsassistent bleibt wie in 02.48 auf nach allen Features verschoben.

### 2. Technischer Umsetzungsentwurf (keine endgültige API)

1. **Mitgliedschaftsdaten:** Konzeptionelle Versionierung einer TurnMembershipPolicy und TurnContextMembership mit stabiler Figuren-/Turn-Kontext-/Turnslot-ID, Modus exklusiv oder ausdrücklich mehrfach erlaubt und wirksamer Overridequelle. Mehrfache Mitgliedschaften **referenzieren dieselbe Charakter-ID**.
2. **Ressourcenscope und Budget:** Ressourcentypen werden konzeptionell als **figurenweit gemeinsam** oder **ausdrücklich turnkontextbezogen** geführt (nur Entwurfsbegriff: ResourceScopePolicy). Die tatsächlich ausgeführte Aktion muss ihren gültigen Figurenkontrolleur, aktiven Turnslot, Szenen-/Node-/Regelberechtigung und den verfügbaren globalen bzw. explizit lokalen Bestand prüfen.
3. **Einmalig atomar verbuchen:** Jede gemeinsame Ressourcenausgabe serverseitig unter einer eindeutigen Aktion-/Figuren-/Ressourcenreferenz und aktueller Version nur einmal akzeptieren. Zwei gleichzeitig ankommende Versuche mit derselben letzten Ladung dürfen nicht zweimal erfolgreich sein. Konfliktschutz, Node-IDs, Replay-Schutz und Reconnect nach 02.35. Kein automatisches Reset eines bereits verbrauchten Aktionsbudgets durch einen bloßen zusätzlichen Turnslot.
4. **Unabhängige Kontexte erhalten:** Ein Zugwechsel in Kontext A verändert nicht die Zugliste von Kontext B. Mitgliedschaft/Aktion in A ist keine automatische Bewegung in eine andere Szene und legitimiert nicht ungeprüfte Handlungen in B; physische Transfers bleiben 02.71. Unterschiedliche, tatsächlich zulässige Aktionen anderer Figuren dürfen nicht durch einen generellen Kampagnenlock blockiert werden.
5. **Offene Konkurrenzdetails:** Falls dieselbe Figur gleichzeitig gültige Aktionen in zwei Kontexten anfordert, ist die gemeinsame Ressource stets geschützt. **Ob die weitere Aktion wartend erneut geprüft, abgelehnt, aufgeschoben oder vom SL entschieden wird, ist die nächste Entscheidung 02.73** – keine vorzeitige First-Come-/Queue-Pflicht.
6. **Isolierte Tests:** Exklusivmodus verweigert zweiten Slot, erlaubte Mehrfachzuordnung führt nicht zu zweiter Figuren-/Inventarinstanz, figurenweit letzte Munition nur einmal nutzbar, ausdrücklich getrennte Rätselbudgets nur nach Regelprofil, gültiger Kontextwechsel erzeugt keine Gratisaktion, Doppel-Nodeimpulse/Reconnect erzeugen keine zweite Ressourcenausgabe. SL-Debug und Testsystem 02.31–02.34 ohne echte Weltwirkung.

**Noch offen:** Action-Budget-Zahlen, Regeneration, tatsächliche Parallelaktionsfreigabe und Konfliktpriorität (02.73), Kampf-/Initiative-/Bewegungsregeln in 03/05/07, finale UI, konkrete Datenbank- und API-Struktur. Die Möglichkeit exklusiver oder ressourcensicherer Mehrfachmitgliedschaft ist beschlossen.

## 02.73 – Konfigurierbare Konfliktbehandlung gleichzeitig angeforderter Figurenaktionen (12.10.2026)

**Verbindlich beschlossen: Variante C.** Wenn dieselbe Figur nach 02.72 in mehreren Zug-Kontexten vertreten ist, können je **Kampagne, Regelprofil, Figur, Aktion/Aktionsklasse, Szene, Node und Turn-Kontext** gültige Aktionen **unabhängig parallel ausgeführt** oder konkurrierende Aktionen **geordnet/serialisiert und erneut geprüft, in einen definierten Wartezustand versetzt, sicher abgelehnt oder einer berechtigten SL-Entscheidung vorgelegt** werden. Kampagnenweite Standards mit eindeutig gekennzeichneten Ausnahmen nach 02.25. Maßgeblich sind die **aktuellen Rechte und echten Ressourcen-/Weltzustände vor jeder tatsächlichen Ausführung**, nicht ausschließlich die Uhrzeit, zu der ein Client eine Anfrage abgesendet hat. **Keine automatische verdoppelte Munition, Bewegung, Aktionsbudgets, Gegenstandsladungen oder zusätzliche Node-/Würfelwirkungen.** Dies ist eine fachliche Architekturplanung, kein bereits implementiertes Aktions-/Kampfsystem.

### 1. Wann Aktionen unabhängig sind und wann sie kollidieren

- **Unabhängige Aktionen zulassen:** Für unterschiedliche, laut aktiver Regel tatsächlich kompatible Handlungen derselben Figur darf die Verarbeitung gleichzeitig stattfinden, wenn keine gemeinsamen gesperrten Ressourcen, inkompatiblen Figurenpositionen oder exklusiven Weltobjektzustände betroffen sind. Die Zugehörigkeit zu unterschiedlichen Rätseln **allein** beweist keine Unabhängigkeit – dieselbe Figur darf nicht ungeprüft an zwei physisch widersprüchlichen Orten gleichzeitig handeln.
- **Geordnet und vor Ausführung neu prüfen:** Die wirksame Konfliktregel darf kollidierende Aktionen serialisieren. Bevor die zweite Aktion tatsächlich wirkt, sind **Ressourcen, Position, aktueller Turn-/Figuren-/Szenenstatus, verwendete Items, Ziel-/Objektzustände und Node-/Regelrechte** erneut zu prüfen. Eine alte Queue-Position garantiert keinen späteren Erfolg. Die allgemeine Prioritätsfolge (Ankunftszeit, Spielregel, SL, explizite Aktion) bleibt regelprofilabhängig, **keine universelle First-Come-Regel**.
- **Warten/Pausieren:** Eine zulässige Aktion darf ausstehend werden, wenn gültige Wartebedingungen wie freizugebende Ressourcen oder SL-Freigabe erfüllt werden sollen. **Ausstehend heißt nicht bereits ausgeführt**, und eine spätere Freigabe muss weiterhin berechtigt und möglich sein. Reservierungen, Wartefristen und Wirkung pausierter Kampagnen werden später konkretisiert.
- **Sicher ablehnen:** Nicht mehr gültiger Zug, verbrauchtes Item, ungültiges Bewegungsziel, gesperrte Figur, geschlossener Zugang, ungültige Nodeversion oder abgelaufener Auftrag können eine serverautoritär abgelehnte Aktion ohne Weltwirkung verursachen. Die Spieler-Fehlermeldung darf keine geheimen Gegner-/SL-Werte verraten.
- **SL-Entscheidung:** Eine entsprechend konfigurierte Aktion kann bis zu einer **berechtigten ausdrücklichen Spielleiterfreigabe** warten. Der SL darf nach aktiven Rechten Reihenfolge, Zurückstellung oder zulässigen Abbruch entscheiden; **bei tatsächlicher Fortsetzung erfolgt eine erneute serverseitige Berechtigungs-/Ressourcenprüfung**. Der manuelle/automatische/SL-bestätigte NPC-Modus aus 02.54 wird nicht umgangen.
- **Geteilte und eigene Budgets:** Die bei 02.72 beschlossenen global geteilten Figuren-/Inventar-/Fähigkeitsressourcen bleiben einmalig und versionsgebunden. Auch explizit eigene, regelkonforme Kontextbudgets begründen keine zweite Weltfigur und keine unberechtigte Doppelverwendung gemeinsamer Items. Andere unabhängige Figuren und Turn-Kontexte sollen nicht unnötig kampagnenweit gesperrt werden.

### 2. Konzeptioneller sicherer Prüf- und Commitpfad

1. **Aktionsauftrag:** Serverseitig autorisierter Actor/Character, auslösender Spieler/NPC/Node, gültiger Kontext und Turngeneration, Aktions- und Ereignis-ID, Regelprofilversion, erforderliche Objekt-, Positions- und Ressourcenreferenzen; der Client darf nicht unüberprüft von sich aus Kosten oder Zugrechte festlegen.
2. **Konflikt- und Unabhängigkeitsentscheidung:** Ein exemplarischer ActionConflictResolver bewertet anhand einer versionierten ActionConflictPolicy, ob zwei laufende/angefragte Aktionen wirklich unabhängig sind oder auf dieselben exklusiven Zustände/Ressourcen zugreifen. Modus und Policyquelle werden im berechtigten Debug nachgewiesen.
3. **Wartestatus ohne heimliche Wirkung:** Für serialisiert, pausiert und SL-pending werden getrennte Status/IDs geführt; **kein vorzeitiger Angriff, Türenöffnen, Spawn, Node-Alarm, Itemverbrauch, Zugwechsel oder verdecktes Endresultat**, solange die Aktion nicht nach ihrer geltenden Regel bestätigt wirksam geworden ist. Eine ausdrücklich erlaubte Reservierung muss einen eigenen konsistenten Zustand erhalten.
4. **Aktuelle Gültigkeit direkt vor Wirkung:** Vor jeder später nachgeholten Aktion **Figur, ihre Kontrolle, Szenen-/Positionszustand, Zielobjekt, globale und lokale Ressourcen, Turn-Kontextgeneration, berechtigte Node-/SL-Freigabe und Regelversion erneut verifizieren**. Ein veralteter Befehl darf nicht deshalb durchlaufen, weil er früher noch gültig war. Falls revalidierte Bedingungen scheitern: konfigurationsgemäß sicher ablehnen oder erneut in den erlaubten Pending-/SL-Pfad geben, **niemals unkontrolliert ausführen**.
5. **Atomare einmalige Ausführung:** Gemeinsam verbrauchte Ressourcen und Änderungen am echten Figuren-/Objektzustand **einmalig transaktional** buchen, bevor gültige Folgeports aktiv werden. Zwei fast gleichzeitige Versuche mit der letzten Munition dürfen nicht beide bestätigt werden. Dabei bleiben die Turngenerationen anderer unabhängiger Kontextgruppen unverändert. Idempotente Ereignis-, Figuren-, Ressourcen- und Turnversions-IDs schützen gegen Reconnect, Graphschleifen und Replay (02.35).
6. **Würfel- und Geheimnisschutz:** Bei einer nach 02.63–02.65 gültigen, würfelpflichtigen Aktion echte serverautoritative Rohwerte/Check-ID verwenden; Wiederholung oder Queueretry erzeugt nicht unbegrenzt neue kostenlose Erfolgsversuche. Ergebnis- und Würfelanzeige gelten nur nach Rollenrechten aus 02.65/02.66; **unbemerkte geheime Wahrnehmungswürfe bleiben vollständig vor Spielerclients verborgen**, auch bei internen Konfliktprüfungen.
7. **Schnittstelle zu Next Player und Transfers:** Zugwechsel- und Figuren-Kontexttransfer-Nodes 02.67–02.72 dürfen nur bei tatsächlich freigegebener und erfolgreich wirksamer Quellaktion ausgelöst werden. Ein inzwischen geschlossenes Rätsel, ein bereits geänderter Turn oder alter Türimpuls darf durch eine wartende Aktion nicht rückwirkend Next Player oder Spawn auslösen.
8. **SL-Debug und isolierte Tests:** Berechtigte SL sehen Soll-/Ist-Weltzustand, konkurrierende Aktions-IDs, Regel-/Overridequelle, angenommene Unabhängigkeit, Wartezustand, erneute Prüfung, reelle Ressourcenausgabe und ggf. Ablehnung. Isolierte Tests aus 02.31–02.34 verursachen keine echten Würfel-/Inventar-/Node-/Turnwirkungen.

### 3. Abnahmeszenarien

- Eine Figur versucht beinahe gleichzeitig in zwei Zugkontexten mit ihrer **letzten Patrone** zu schießen. Höchstens ein gültiger Verbrauch ist möglich; der zweite Auftrag wird je aktiver Regel erneut geprüft, zurückgestellt, abgelehnt oder dem SL vorgelegt, jedoch **niemals als zweiter kostenloser Schuss ausgeführt**.
- Zwei laut Regel unabhängig erlaubte Tätigkeiten können parallel erfolgen, wenn ihre Figuren-/Orts-/Objekt-/Ressourcenabhängigkeiten dies tragen. Unterschiedliche Zuglisten allein beweisen das nicht.
- Eine wartende Interaktion wird nach einem Kontextwechsel erneut geprüft; besitzt die Figur inzwischen weder Zugrecht noch Zugriff auf das Objekt, **kein spätes Türöffnen/Next-Player-/Alarm-/Spawn-Ereignis**.
- Ein SL bestätigt eine ausstehende Aktion erst, nachdem sich Ziel und Munition geändert haben. Der Server prüft die aktuellen Bedingungen und darf eine vorher gültige Aktion nun sicher ablehnen.
- Doppelte Client- oder Node-Events, erneut zugestellte ausstehende Aufträge und Reconnect lassen weder Ressourcen doppelt verschwinden noch dasselbe Würfelergebnis durch neue kostenlose Würfe ersetzen.
- Der isolierte Test zeigt die Reihenfolge und die Resultate, ohne eine reale gemeinsame Ressource oder geheime Roll-Daten an Spieler auszugeben.

**Noch offen:** Welche Arten laufender Aktionen bei **Zugende** fertiglaufen, pausieren oder abgebrochen werden (02.74); genaue Priorisierung mehrerer Aktionsklassen, Queue-/Timeout-/Reservierungsregeln, Reaktions-/Kampfkosten, zulässige Gleichzeitigkeit und UI. Nicht jede Handlung muss künftig synchron oder rundenbasiert werden; der allgemein zugbasierte und freie Modus werden später im Regel-/Kampfworkshop (03/05/07) konkretisiert. Globale Kampagnenassistentenführung und Abschaltung weiterer Featurebereiche weiterhin erst nach allen Features.

## Nächste Entscheidung 02.74 – Was geschieht mit laufenden Aktionen, wenn ein Zug endet?

- **A – Immer abbrechen:** Bei regulärem Zugende durch Spieler, Next-Player-Node oder SL werden alle noch laufenden/ausstehenden Aktionen ohne Ausnahme beendet.
- **B – Immer weiterlaufen:** Laufende/ausstehende Aktionen laufen nach Zugende stets automatisch zu Ende, auch wenn der ursprünglich gültige Turn-, Figuren- oder Zielzustand sich verändert hat.
- **C – Konfigurierbar nach Aktion und Kontext (Empfehlung):** Je Kampagnen-/Regelprofil, Aktion, Figur und Zugkontext darf eine laufende Handlung **regelgerecht beendet, über das Zugende hinaus fortgesetzt, pausiert, abgebrochen oder bis zur SL-Freigabe angehalten** werden. Die Einhaltung aktueller Figuren-/Ressourcen-/Objekt-/Zugrechte und Node-/Timerbedingungen wird vor jeder späteren Wirkung erneut geprüft. **Halteaktionen** (z. B. ein gedrückter Taster), **zeitbasierte Vorgänge, Würfelprüfungen und ausstehende Next-Player-Übergaben** dürfen unterschiedliche Policies und passende Ausnahmen verwenden – ohne doppelte Ressourcenwirkung oder unberechtigt ausgelöste Nodes.
