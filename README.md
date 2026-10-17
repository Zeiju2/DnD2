# AdventureShift

**Produktname: AdventureShift.** Das GitHub-Repository heißt derzeit noch `DnD2`.

**Status: gemeinsamer Feature-Workshop – noch keine Implementierung.**
**Beschlussstand 17.10.2026:** **02.155 C** – lokale FX-Anpassung sofort oder beim nächsten erlaubten Cuestart [Beschluss/Tests](docs/KARTEN-WORKSHOP-02.155.md). **Audio-Unterfragen vorerst beendet. 03.1 C beschlossen:** [versionierbare, typisierte Charaktervorlagen](docs/CHARAKTER-WORKSHOP-03.1.md). **03.2 C beschlossen:** [mehrere Figuren, getrennte Rechte und temporäre Übernahmen/Verhexungen](docs/CHARAKTER-WORKSHOP-03.2.md). **03.3 C beschlossen:** [geschützte Vorlagenentwürfe und Veröffentlichung](docs/CHARAKTER-WORKSHOP-03.3.md); **zusätzlich optionale Charaktererstellung mit Klassen, Fähigkeiten und Punkteverteilung** als späteres Modul eingeplant. **03.4 C beschlossen:** [modulare versionierbare Klassen-/Skill-/Fähigkeitsbausteine](docs/CHARAKTER-WORKSHOP-03.4.md) mit typsicheren Referenzen, Voraussetzungen und Budgets. **03.5 C beschlossen:** [optionales, regelwerkskonfigurierbares Fortschrittssystem](docs/CHARAKTER-WORKSHOP-03.5.md). **03.6 C beschlossen:** [selektive kontrollierte Migration bestehender Figuren](docs/CHARAKTER-WORKSHOP-03.6.md) mit typisierter Vorschau, Rechtekontrolle und einzeln atomarem Commit. **03.7 C beschlossen:** [optionale sichere Berechnungsregeln und anlegbare/speicherbare sowie mitgelieferte Regelwerksvorlagen zum Schnellstart](docs/CHARAKTER-WORKSHOP-03.7.md). **03.8 C beschlossen:** [optionales, datengetriebenes Zustands-/Effektmodell](docs/CHARAKTER-WORKSHOP-03.8.md) mit sicheren Laufzeiten, manueller oder regelbasierter Wirkung und 03.2-/03.7-Kopplung. **Block 03 Grundstruktur vorläufig abgeschlossen. 04.1 C beschlossen:** [regel-/kampagnenabhängig umschaltbare freie, Ziel-/Wegpunkt- und rundenbasierte Bewegung; ausdrücklich darf eine gültige Gegnerentdeckung frei → rundenbasiert auslösen](docs/BEWEGUNG-WORKSHOP-04.1.md). **04.2 C beschlossen:** [optionale regelwerksneutrale logische Token-Größe, Platzbelegung und Kollision, getrennt von Grafik sowie mit Rasterfrei-/Quadrat-/Hex- und 02.9-Tür-/Hindernisbezügen](docs/BEWEGUNG-WORKSHOP-04.2.md). **04.3 C beschlossen:** [optionale getrennte Transport-, Reit-, Passagier- und Begleitbeziehungen mit servergeprüfter Mit- und Folgebewegung](docs/BEWEGUNG-WORKSHOP-04.3.md). **04.4 C beschlossen:** [getrennte, servergeprüfte Positionsaktionen für freiwillige und erzwungene Bewegung, Teleport, Portal-/Szenentransfer und gesondertes SL-Versetzen](docs/BEWEGUNG-WORKSHOP-04.4.md) mit individuellen Rechte-/Trigger-/Kollisions-/Transportregeln. **04.5 C beschlossen:** [optionale versionierte Geländetypen, Passierbarkeit, Weg-/Bewegungskosten und sichere Routenprüfung ohne geheime Karteninformationen](docs/BEWEGUNG-WORKSHOP-04.5.md). **Block 04 grundstrukturell abgeschlossen. 05.1 C beschlossen:** [versionierte sichere klassische Würfel, Würfelpools, Sonder-/Symboldatentypen und getrennte Roll-/Ergebnismodelle](docs/WUERFEL-WORKSHOP-05.1.md) mit einmaligem VPS-Zufall und unverändert geschützten 02.63–02.67-Proben-/Geheimwürfelrechten. **05.2 C beschlossen:** [kombinierbare manuelle, SL-bestätigte und automatisch durch Regeln/NPCs/Nodes ausgelöste Würfe](docs/WUERFEL-WORKSHOP-05.2.md) mit geschützten Anträgen, Freigaben, einmaligem VPS-RollCommit und getrennten WorldActions. **05.3 C beschlossen:** [optionale sichere, typsichere und begrenzte regelwerksabhängige Würfelketten](docs/WUERFEL-WORKSHOP-05.3.md) mit getrennten echten Teilwürfen. **05.3 C Zusatz:** Auch **gleichzeitig dargestellte Würfel** sind möglich; der VPS darf die echten Rohwerte und Auswertungen **nacheinander** ausführen, unabhängig vom gemeinsamen visuellen Wurf [Ergänzung](docs/WUERFEL-WORKSHOP-05.3.md). Konkrete Würfeloperatoren erst in der Detailphase. **06.1 C beschlossen:** [versionierte NPC-/Gegnervorlagen und unabhängige reale NPC-Instanzen](docs/NPC-WORKSHOP-06.1.md) mit eigenen Werten, Ressourcen, Inventaren, Tokens, Steuer- und Geheimrechten; Zahlen/Details später. **06.2 C beschlossen:** [versionierter, konfigurierbarer und geschützter NPC-Lebenszyklus](docs/NPC-WORKSHOP-06.2.md) für berechtigtes Erzeugen/Platzieren/Aktivieren/Verbergen/Deaktivieren/Transfer/Archivieren mit regelabhängiger Persistenz und ohne duplizierte NPCs oder Items. Konkrete NPC-Werte, Spawnmengen und Detailregeln später. **Nächste Grundstrukturfrage 06.3 – Gruppen/Fraktionen und Beziehungen.**

AdventureShift soll eine selbst hostbare, browserbasierte und **genre- wie regelwerksunabhängige Virtual-Tabletop-Plattform (VTT)** für Pen-&-Paper-Rollenspiele werden. Mehrere Spieler und ein Spielleiter melden sich über Steam an, spielen gemeinsam auf einer 2D-Karte, bewegen ihre Figuren und sehen synchronisierte Würfelwürfe. Charaktere, Gegner, Ausrüstung, Gegenstände und Spielstände werden gespeichert.

## Dokumentation

- [Verbindlicher Planungsstandard](docs/PLANUNGSSTANDARD.md) – Grundstruktur und Rechte jetzt; Mengen, Defaults und UI-Details später.
- [Feature-Workshop (laufende Planung)](docs/FEATURE-WORKSHOP.md) – bereichsübergreifender Hauptkatalog mit den bisherigen Workshop-Entscheidungen.
- [Karten-Workshop](docs/KARTEN-WORKSHOP.md) – Detailentscheidungen 02.1–02.4 zu Import, Editor, Szenentypen, Raster und Maßstab; laufende Kartenfragen.
- [Features und MVP-Anforderungen](docs/FEATURES.md) – priorisierte Funktionen mit Nutzerabläufen und Abnahmekriterien.
- [Projektplan und Roadmap](docs/PROJEKTPLAN.md) – Zielbild, Funktionen, priorisierter Umfang, Meilensteine und offene Fragen.
- [Technische Architektur](docs/ARCHITEKTUR.md) – empfohlener Stack, Spiellogik, Datenmodell, Sicherheitskonzept und Serverbetrieb.
- [Namensrecherche](docs/NAMENSRECHERCHE.md) – dokumentierte Prüfung von RoleShift, gefundenen Angeboten, Marken- und Domainrisiken.
- [Lizenzen und Nutzungsrechte](docs/LIZENZEN.md) – geprüfte Open-Source-Lizenzen, Steam-Bedingungen, SRD 5.2.1, Assets, Hinweise zur Veröffentlichung.

## Verbindliche Produktausrichtung (11.10.2026)

Die Plattform ist **nicht auf Dungeons & Dragons oder Fantasy begrenzt**. Sie soll auch Cyberpunk, Steampunk, Science-Fiction, Horror, Gegenwart und frei erfundene Welten unterstützen. Das gemeinsame Spielfeld, Benutzerverwaltung, Würfel, Tokens und Kampagnen sind der neutrale Kern. Charakterbögen, Gegenstandstypen, Gegnerwerte und Kampfregeln müssen konfigurierbar sein; D&D/SRD ist höchstens ein **optionales Regelpaket**, nicht der feste Standard. **AdventureShift** ist der vom Projektinhaber gewählte Produktname (11.10.2026). Die Marken- und Domainverfügbarkeit ist noch **nicht abschließend bestätigt**. `DnD2` bleibt vorerst der technische Arbeitstitel.

## Geplante Kernfunktionen

- Steam-Anmeldung und kampagnenbezogene Rollen für Spielleiter/Spieler
- Lobby und Spielräume für mehrere Teilnehmer
- Gemeinsames 2D-Spielfeld mit Tokens, Bewegung und optionalem Raster
- Serverseitig ermittelte Würfelergebnisse mit für alle sichtbarer 3D-Animation
- Konfigurierbare Charakterbögen, Werte, Inventare, Gegenstände und Ausrüstung für unterschiedliche Spielsysteme
- NPCs und Gegner; optionale Trefferpunkte, Initiative und Kampfmodule je nach Regelwerk
- Persistente Kampagnen und Spielstände
- Spätere Installation auf einem eigenen Linux-Server

## Vorgeschlagene Technik (noch zu validieren)

React + TypeScript, PixiJS, Node.js + Colyseus, PostgreSQL, 3D-Würfelbibliothek, Docker Compose und Caddy.

Der **Server ist autoritativ** für Regeln, Bewegung, Items und Würfelergebnisse. Ein Browser darf diese Daten nicht eigenmächtig verändern.

## Erste Umsetzung

1. Technischer Prototyp: zwei Browser, eine Karte, Bewegung und gemeinsame Würfelwürfe.
2. Steam-Login, Lobby, Benutzer- und Kampagnenverwaltung.
3. Charaktere, Gegner und erster spielbarer Kampf.
4. Inventar, Ausrüstung, Beute und Speichern.
5. Erweiterungen wie Nebel des Krieges, Karteneditor und Spielleiter-Werkzeuge.

## Offene Produktentscheidungen

- Welches neutrale Basisprofil und welche optionalen Regelmodule bieten wir zuerst an (z. B. D&D-SRD oder eigene Regeln)?
- Wie soll die Oberfläche der ersten Version gestaltet sein und welche Bedienaktionen priorisieren wir?
- Welches konkrete Start-Regelprofil und welche Standardkonfiguration nutzen die in 04.1 C bereits beschlossenen flexiblen Bewegungsmodi im ersten Prototyp?
- Zielplattformen für Version 1: Desktop-Browser zuerst oder auch Mobilgeräte?

Bis diese Fragen entschieden sind, dokumentieren wir Annahmen ausdrücklich als **Vorschläge**, nicht als verbindliche Anforderungen.

**Hinweis:** Das Repository enthält anfangs nur die Planung. `DnD2` ist lediglich ein Arbeitstitel für eine universelle Rollenspielplattform; eine Veröffentlichung als offizielles Dungeons-&-Dragons-Produkt ist nicht geplant. Lizenz- und Markenfragen für Regeln, Namen und Bildmaterial werden vor der Nutzung geklärt.
