# DnD2

**Status: Planungsphase – noch keine spielbare Software.**

DnD2 soll ein selbst hostbares, browserbasiertes Multiplayer-Fantasy-Rollenspiel mit virtuellem Spieltisch werden. Mehrere Spieler und ein Spielleiter melden sich über Steam an, spielen gemeinsam auf einer 2D-Karte, bewegen ihre Figuren und sehen synchronisierte Würfelwürfe. Charaktere, Gegner, Ausrüstung, Gegenstände und Spielstände werden gespeichert.

## Dokumentation

- [Projektplan und Roadmap](docs/PROJEKTPLAN.md) – Zielbild, Funktionen, priorisierter Umfang, Meilensteine und offene Fragen.
- [Technische Architektur](docs/ARCHITEKTUR.md) – empfohlener Stack, Spiellogik, Datenmodell, Sicherheitskonzept und Serverbetrieb.

## Geplante Kernfunktionen

- Steam-Anmeldung und kampagnenbezogene Rollen für Spielleiter/Spieler
- Lobby und Spielräume für mehrere Teilnehmer
- Gemeinsames 2D-Spielfeld mit Tokens und Bewegung
- Serverseitig ermittelte Würfelergebnisse mit für alle sichtbarer 3D-Animation
- Charaktere, Werte, Inventar, Ausrüstung und auffindbare Items
- Gegner, Lebenspunkte, Initiative und rundenbasierter Kampf
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

- Möglichst regelgetreues D&D 5e/2024, eigene Hausregeln oder ein eigenständiges Regelsystem?
- Freie Erkundung mit rundenbasiertem Kampf, ausschließlich rundenbasierte Bewegung oder Echtzeitbewegung?
- Zielplattformen für Version 1: Desktop-Browser zuerst oder auch Mobilgeräte?

Bis diese Fragen entschieden sind, dokumentieren wir Annahmen ausdrücklich als **Vorschläge**, nicht als verbindliche Anforderungen.

**Hinweis:** Das Repository enthält anfangs nur die Planung. Es ist keine Veröffentlichung als offizielles Dungeons-&-Dragons-Produkt geplant. Lizenz- und Markenfragen für Regeln, Namen und Bildmaterial werden vor der Nutzung geklärt.
