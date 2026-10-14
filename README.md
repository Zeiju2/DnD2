# AdventureShift

**Produktname: AdventureShift.** Das GitHub-Repository heißt derzeit noch `DnD2`.

**Status: gemeinsamer Feature-Workshop – noch keine Implementierung.**
**Beschlussstand 14.10.2026:** 02.151 C (geschützte persönliche Speicherung von Audioeffekt-Präferenzen mit optionalem Eigengeräte-Sync) [Beschluss und Tests](docs/KARTEN-WORKSHOP-02.151.md); nächste Featurefrage **02.152** (Vorrang und Konflikte bei mehreren persönlichen Präferenzen).

AdventureShift soll eine selbst hostbare, browserbasierte und **genre- wie regelwerksunabhängige Virtual-Tabletop-Plattform (VTT)** für Pen-&-Paper-Rollenspiele werden. Mehrere Spieler und ein Spielleiter melden sich über Steam an, spielen gemeinsam auf einer 2D-Karte, bewegen ihre Figuren und sehen synchronisierte Würfelwürfe. Charaktere, Gegner, Ausrüstung, Gegenstände und Spielstände werden gespeichert.

## Dokumentation

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
- Freie Erkundung mit rundenbasiertem Kampf, ausschließlich rundenbasierte Bewegung oder Echtzeitbewegung?
- Zielplattformen für Version 1: Desktop-Browser zuerst oder auch Mobilgeräte?

Bis diese Fragen entschieden sind, dokumentieren wir Annahmen ausdrücklich als **Vorschläge**, nicht als verbindliche Anforderungen.

**Hinweis:** Das Repository enthält anfangs nur die Planung. `DnD2` ist lediglich ein Arbeitstitel für eine universelle Rollenspielplattform; eine Veröffentlichung als offizielles Dungeons-&-Dragons-Produkt ist nicht geplant. Lizenz- und Markenfragen für Regeln, Namen und Bildmaterial werden vor der Nutzung geklärt.
