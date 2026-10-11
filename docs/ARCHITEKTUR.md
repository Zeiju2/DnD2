# AdventureShift – Technische Architektur (Entwurf)

**Stand:** 11.10.2026  
**Produktname:** AdventureShift (`DnD2` bleibt vorerst GitHub-Repository).
**Status:** Architekturvorschlag, noch keine implementierte Architektur.

> Ziel ist ein wartbarer Multiplayer-Prototyp, der später auf einem eigenen Linux-Server betrieben wird. Bibliotheken, API-Verträge und Struktur werden im ersten Prototyp validiert; sie sind noch nicht endgültig entschieden.

## 1. Architekturprinzipien

1. **Serverautorität:** Der Server bestimmt den gültigen Spielzustand, Würfelergebnisse, Item-Übergänge und zugelassene Bewegungen.
2. **Live-Synchronisierung:** Clients erhalten Änderungen über eine dauerhafte WebSocket-Verbindung.
3. **Geheimnisse bleiben serverseitig:** Nicht sichtbare Gegner, verdeckte Bereiche und Spielleiterdaten werden unberechtigten Clients nicht übermittelt.
4. **Trennung von Darstellung und Regeln:** Grafische 3D-Würfel zeigen ein Ergebnis an, erzeugen es aber nicht verbindlich.
5. **Persistenz:** Längerfristige Daten und wichtige Ereignisse werden in PostgreSQL gespeichert.
6. **Modularer Start:** Ein klar strukturiertes Backend statt unnötig vieler verteilter Microservices.
7. **Self-Hosting:** Browser, Server und Datenbank sollen mit wenigen Diensten lokal bzw. später mit Docker Compose betrieben werden können.
8. **Genre- und Regelwerksneutralität (Produktentscheidung 11.10.2026):** Der Plattformkern darf keine festen D&D-, Fantasy- oder Kampfattributannahmen erzwingen. Cyberpunk, Steampunk, Fantasy, Sci-Fi und andere Genres sind gleichrangig.

### Trennung von Plattformkern und Regelprofilen

- **Plattformkern:** Identität, Kampagnen, Räume, Karten, Tokens, Berechtigungen, Chat/Logs, Würfelereignisse, Persistenz.
- **Konfigurierbare Vorlagen:** Charakterbogenfelder, Ressourcen (z. B. Gesundheit, Energie, Stress), Itemkategorien, Slots, NPCs/Gegner und weitere Objekttypen (z. B. Fahrzeuge, Drohnen).
- **Regelprofile:** Wahlweise rein manuelle Spielweise oder aktivierbare Module für Initiative, Bewegungskosten, Würfelmechanik, Angriffe, Effekte usw.; jedes Profil versionieren.
- **Prüfbare Serverregeln:** Browser dürfen auch bei konfigurierbaren Feldern keine fremden Werte oder Items verändern. Autorisierung, Änderungsrechte und Validierung bleiben serverseitig.
- **Keine vorschnelle Plugin-Laufzeit:** Zunächst Datenvorlagen und wohldefinierte Regel-Interfaces statt beliebig ausführbarem Nutzercode; Sicherheitsmodell für Skripting wäre ein eigenes späteres Projekt.

## 2. Empfohlener Technologie-Stack

| Schicht | Kandidat | Grund | Prüfung |
| --- | --- | --- | --- |
| Web-UI | React + TypeScript | Komponenten für Login, Charakterbogen, Inventar und Menüs | Festlegen |
| Kartenrenderer | PixiJS | 2D-Sprites, Tokens, Raster, Zoom und Effekte | Performance in POC |
| Realtime | Colyseus / WebSocket | Räume, State-Synchronisierung und Multiplayer | Funktionsumfang in POC |
| API & Backend | Node.js + TypeScript | Gemeinsame Sprache, Auth, Regeln und Spielzustand | Festlegen |
| Datenbank | PostgreSQL | Relationen, Transaktionen und dauerhafte Speicherung | Schema entwerfen |
| 3D-Würfel | dice-box-threejs oder Alternative | Würfelanimation als visuelle Ebene | Verbindliche Ergebnisse testen |
| Dateispeicher | Lokales persistentes Volume | Karten- und Token-Bilder | Dateigröße/Backups |
| Betrieb | Docker Compose + Caddy | Container und HTTPS-Reverse-Proxy | Serverumgebung prüfen |

Die Technik ist ein **Vorschlag**, keine bestehende oder getestete Installation.

Referenzen:
- Steam: https://steamcommunity.com/dev
- PixiJS: https://pixijs.com/
- Colyseus: https://docs.colyseus.io/
- dice-box-threejs: https://github.com/3d-dice/dice-box-threejs
- Docker Compose: https://docs.docker.com/compose/
- Caddy: https://caddyserver.com/docs/

## 3. Logische Komponenten

```text
Browser Spieler A         Browser Spieler B         Browser Spielleiter
(React / PixiJS / Würfel-Animation / lokaler UI-Zustand)
             |                    |                    |
             +--------------------+--------------------+
                                  |
                         HTTPS / WebSocket
                                  |
                      Caddy Reverse Proxy
                                  |
                     Node.js Backend
                     |            |
               HTTP/Auth API   Colyseus-Räume
                     |            |
                     +----+-------+
                          |
          Rechteprüfung + Spielregeln + RNG
                          |
               PostgreSQL + Asset-Speicher
```

- **HTTP/API:** Steam-Login, Session, Kampagnenverwaltung, Charakter-/Assetverwaltung.
- **Realtime-Räume:** Bewegungen, Kartenwechsel, Tokens, Initiative, Würfel und Echtzeitereignisse.
- **Regelmodul:** Optionales, kampagnenspezifisches und versioniertes Profil für Würfel, Bewegung, Aktionen, Kampf und Effekte; generische Zugriffsrechte gelten immer.
- **Persistenzmodul:** Lädt und speichert Spielzustand; benutzt Transaktionen für konkurrierende Aktionen.

### Renderer und 3D-Würfel

Ein möglicher Aufbau ist eine PixiJS-Kartenebene mit einem separaten transparenten 3D-Canvas für Würfel. Dabei müssen Eingabeereignisse, Z-Index und Ressourcenverbrauch geprüft werden. Eine 3D-Würfelbibliothek ist austauschbar zu halten, falls die Kopplung an vorgegebene Ergebnisse nicht zuverlässig funktioniert.

## 4. Steam-Authentifizierung und Rollen

### Geplanter Login-Ablauf

1. Browser startet über die eigene Backend-Route die Steam-Anmeldung.
2. Backend leitet auf den offiziellen Steam-OpenID-Endpunkt weiter.
3. Steam bestätigt die Identität durch einen Rücksprung an das Backend.
4. Backend **validiert die OpenID-Antwort serverseitig**, einschließlich Rücksprung-/Anmeldekontext, und liest die SteamID64 aus dem bestätigten Identifikator.
5. Benutzer wird über eindeutige SteamID64 gefunden oder lokal angelegt.
6. Backend setzt eine eigene sichere Sitzung; WebSocket-Verbindungen authentifizieren sich gegen diese Sitzung.
7. Kampagnenrechte werden nach Benutzerkennung und Kampagnenmitgliedschaft geprüft.

Steam OpenID 2.0 ist nicht OpenID Connect. Ein Steam-Login verpflichtet nicht dazu, das Browserspiel über den Steam-Store zu vertreiben.

### Sicherheitsanforderungen

- Steam-Passwörter niemals entgegennehmen oder speichern.
- Sitzung mit sicherem HttpOnly-Cookie, Secure unter HTTPS und geeigneter SameSite-Einstellung.
- CSRF- und Login-State-Schutz sowie Prüfung zulässiger Redirects.
- WebSocket-Handshakes und **jede** Aktion nach Nutzer, Raum und Rolle prüfen.
- Eingaben und Formeln serverseitig validieren; Rate Limits für Login, Würfeln und Bewegung.
- Spielleiterrechte niemals durch ein Client-Flag begründen; sie stammen aus dem Backend.
- Logs datensparsam halten; Cookies/Geheimnisse nicht protokollieren.
- Geheime Daten nicht nur mit CSS/Client-Logik ausblenden.

## 5. Realtime-Nachrichten (vorläufig)

Die genauen Nachrichtentypen werden in einem gemeinsamen TypeScript-Paket definiert.

| Richtung | Event (Arbeitsname) | Inhalt |
| --- | --- | --- |
| Client → Server | join_room | Kampagnen-/Raumkennung |
| Client → Server | move_request | Token, Zielposition, Befehls-ID |
| Client → Server | roll_request | Würfeldefinition, Figur, ggf. Aktion |
| Client → Server | pickup_request | Item-Instanz und Token/Charakter |
| Client → Server | equip_request | Item-Instanz und Zielslot |
| Client → Server | end_turn | Begegnung/Zug |
| Server → Clients | token_moved | Token, neue Position, Versionsnummer |
| Server → Clients | roll_result | Wurf-ID, Würfelwerte, Modifikatoren, Gesamtergebnis |
| Server → Clients | inventory_changed | Autoritativer Inventarstatus |
| Server → Clients | turn_changed | Neue aktive Figur und zulässige Aktionen |
| Server → Clients | action_rejected | Befehls-ID und sichere Fehlermeldung |

**Wichtig:** Es werden nur diejenigen Ereignisse und Zustandsfelder übertragen, die der jeweilige Empfänger sehen darf. Server gibt verbindliche Werte aus, nicht den ungeprüften Client-Vorschlag.

### Beispiel: Bewegung

1. Client sendet „move_request“ mit seinem Token und dem Ziel.
2. Server prüft Identität, Token-Eigentum, Sicht/Regeln, Felder und ggf. Bewegungspunkte.
3. Bei Erfolg aktualisiert der Server den Raumzustand und sendet „token_moved“.
4. Bei Misserfolg erhält nur der anfragende Client „action_rejected“.
5. Bei Neustart lädt das Backend die letzte gespeicherte Position.

Wegfindung (z. B. A*) kann nach dem Prototyp ergänzt werden. Wir dürfen Client-Koordinaten nicht ohne Prüfung übernehmen.

### Beispiel: Würfel

1. Berechtigter Client sendet „roll_request“.
2. Backend entscheidet über die gültige Würfelformel und ermittelt Rohwerte aus einer geeigneten kryptografischen Zufallsquelle.
3. Backend speichert die Wurf-ID und Werte; danach sendet es ein „roll_result“-Event an die zugelassenen Clients.
4. Clients animieren passende Würfel. Das **Serverergebnis** bleibt in jeder Ansicht identisch.
5. Neu verbundene Clients können das Würfelprotokoll laden.

Ein gemeinsamer Startzeitpunkt kann die Animationen zeitlich angleichen; eine identische physikalische Simulation ist nicht zwingend nötig.

## 6. Vorläufiges Datenmodell

| Tabelle / Sammlung | Wesentliche Felder |
| --- | --- |
| users | id, steam_id64 (eindeutig), created_at |
| campaigns | id, name, creator_user_id, settings |
| campaign_members | campaign_id, user_id, role, joined_at |
| characters | id, campaign_id, owner_user_id, name, sheet_template_id, stats/resources (schema-validiert; HP nur optional) |
| maps | id, campaign_id, asset_path, dimensions, grid_settings |
| tokens | id, map_id, character_id oder enemy_id, x, y, visibility, state |
| actor_templates | id, ruleset_id (optional), actor_type (NPC/Gegner/Fahrzeug...), name, fields_schema, actions (optional) |
| actor_instances | id, template_id, campaign_id, stats/resources (regelabhängig), state |
| item_templates | id, name, type, optionales Feld-/Effektschema, optionale Ausrüstungsslots, asset |
| item_instances | id, template_id, owner_character_id ODER map_id/position, quantity, state |
| encounters | id, campaign_id, map_id, status, initiative_order, turn_index |
| dice_events | id, campaign_id, actor_user_id, character_id, formula, rolls, modifier, total, created_at |
| game_events | id, campaign_id, type, payload, created_at |

**Details später klären:** Aufteilung JSON/normalisierte Felder, Versionierung, Migrationen, Zustands-Snapshots, genaue Besitzer- und Sichtbarkeitsregeln. Bei Inventarwechseln ist eine Transaktion nötig, damit dieselbe Bodenbeute nicht zweimal aufgenommen wird. Ein vollständiges Event-Sourcing-System ist für den Start nicht erforderlich.

### Fachliche Trennung

- **Konfigurierbare Charakterwerte** bleiben unabhängig von optionalen **regelbasiert abgeleiteten Werten**.
- **Item-Vorlage** ist nicht dasselbe wie **konkrete Item-Instanz**.
- **Benutzerrolle** ist kampagnenbezogen, nicht global.
- **Sichtbarer Raumzustand** ist eine berechtigungsgesteuerte Sicht auf den internen Spielzustand.
- **Würfelanimation** ist nicht die Quelle des Würfelergebnisses.

## 7. Empfohlene Projektstruktur (noch nicht angelegt)

```text
DnD2/
  README.md
  docs/
    PROJEKTPLAN.md
    ARCHITEKTUR.md
  apps/
    web/                  # React UI, PixiJS und 3D-Würfel
    server/               # HTTP API, Colyseus, Regeln
  packages/
    shared/               # Gemeinsame TypeScript-Typen, Nachrichten
  infra/
    compose.yaml          # Docker Compose (später)
    Caddyfile             # HTTPS/Reverse Proxy (später)
```

Die vorgeschlagene Monorepo-Struktur ist klein genug für den Anfang und trennt Spielserver, UI und gemeinsame Datentypen. Diese Ordner werden erst bei der Implementierung angelegt.

## 8. Self-Hosting und Betrieb

### Ein-Server-Ausbau zu Beginn

- Caddy nimmt HTTPS-Verbindungen entgegen und stellt das Web-Frontend bereit bzw. leitet an die Dienste weiter.
- Der Node.js-Server stellt API und WebSocket-Räume bereit.
- PostgreSQL wird nicht direkt ins Internet veröffentlicht.
- Karten und Token-Dateien liegen auf einem persistenten Volume (später ggf. objektbasiert).
- Docker Compose beschreibt Dienste, Netzwerke, Volumes und Umgebungsvariablen.
- Eigene Domain, TLS-Zertifikate, Firewall, Backup und Monitoring sind einzuplanen.

### Betriebsanforderungen

- Keine Schlüssel oder Zugangsdaten im Git-Repository.
- Konfiguration aus Umgebungsvariablen/Secrets; eine Beispielkonfiguration darf keine echten Secrets enthalten.
- Regelmäßige Backups **von Datenbank und Dateien**; Wiederherstellung testen.
- Versionierte DB-Migrationen, Health-Check, Log-Rotation und Updates.
- Vor Produktivbetrieb Sicherheitstests, insbesondere für Rollen, geheime Daten und Datei-Uploads.

**Noch nicht bestimmbar:** CPU/RAM-Bedarf und Zahl möglicher paralleler Räume. Diese Werte hängen von Bibliotheken, Kartengröße, Animationsaufwand und Nutzerzahl ab und müssen gemessen werden.

## 9. Tests, die wir früh durchführen müssen

1. Zwei bis sechs Browser in einem Raum mit gleichzeitigen Bewegungen.
2. Würfelwurf mit mehreren Empfängern, bei langsamer Verbindung und Reconnect.
3. Nicht autorisierte Tokenbewegung, Würfelformeln, Item-Updates und SL-Aktionen blockieren.
4. Zwei Spieler versuchen gleichzeitig dasselbe Item aufzunehmen.
5. Spielleiter hat geheime Gegner; Spieler-Clients erhalten keine Daten darüber.
6. Browser aktualisiert Seite: Positionen, Inventar und letzte Ergebnisse stimmen.
7. Server startet neu: gespeicherte Kampagne bleibt wiederherstellbar.
8. Erstes Deployment auf Test-Linux mit HTTPS, WebSocket und Backup/Restore.

## 10. Architekturentscheidungen (ADR-Kandidaten)

| ID | Entscheidung | Stand | Begründung |
| --- | --- | --- | --- |
| ADR-001 | Serverautoritative Spiellogik und Würfelergebnisse | Empfohlen | Konsistenz, Manipulationsschutz |
| ADR-002 | Browser-Frontend mit React und PixiJS | Zu validieren | 2D-Spielfeld, getrennte UI |
| ADR-003 | Colyseus für Spielräume | Zu validieren | Realtime- und Raumverwaltung |
| ADR-004 | PostgreSQL für dauerhafte Daten | Empfohlen | Transaktionen, Relationen |
| ADR-005 | Docker Compose auf eigenem Server | Empfohlen | Reproduzierbarer Betrieb |
| ADR-006 | Genre-/Regelwerksneutraler Plattformkern | **Beschlossen (Produktziel)** | Fantasy, Cyberpunk, Steampunk, Sci-Fi usw. auf derselben Plattform |
| ADR-007 | Konkretes Start-Regelprofil und Bewegungsmodus | **Offen** | Unterschiedliche Spielsysteme brauchen verschiedene Mechaniken |

Siehe [Features](FEATURES.md) für Abnahmekriterien und [Projektplan und Roadmap](PROJEKTPLAN.md) für Meilensteine.
