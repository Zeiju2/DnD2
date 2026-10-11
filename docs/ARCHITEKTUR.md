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
| maps | id, campaign_id, asset_path (optional), dimensions, grid_settings; importierte Medien und direkt erstellte Karten trennen |
| tokens | id, map_id, character_id oder enemy_id, x, y, visibility, state |
| scenes (Vorschlag) | id, campaign_id, name, maps/assets, dimensions, grid/scale, editable_layers, active_state |
| actor_templates | id, ruleset_id (optional), actor_type (NPC/Gegner/Fahrzeug...), name, fields_schema, actions (optional) |
| actor_instances | id, template_id, campaign_id, stats/resources (regelabhängig), state |
| item_templates | id, name, type, optionales Feld-/Effektschema, optionale Ausrüstungsslots, asset |
| item_instances | id, template_id, owner_character_id ODER map_id/position, quantity, state |
| encounters | id, campaign_id, map_id, status, initiative_order, turn_index |
| dice_events | id, campaign_id, actor_user_id, character_id, formula, rolls, modifier, total, created_at |
| game_events | id, campaign_id, type, payload, created_at |
| scene_objects (Vorschlag) | id, campaign_id, scene_id, type (Tür/Fahrzeug/Terminal/Truhe/...), position, state, visibility |
| access_controls (Vorschlag) | id, object_ref, Berechtigungen, Zugangsmethoden (Code/Keycard/Schlüssel), lock_state, re_lock_policy |
| access_attempts (Vorschlag) | id, access_control_id, optional actor_user_id, count, reset_policy, last_attempt_at |
| trap_instances (Vorschlag) | id, object_ref (optional), trigger_rules, armed_state, rearm_policy, cooldown_state, visibility |
| triggered_events (Vorschlag) | id, trap_id, trigger_id, type, result, timestamp (idempotente Auslösung) |

**Details später klären:** Aufteilung JSON/normalisierte Felder, Versionierung, Migrationen, Zustands-Snapshots, genaue Besitzer- und Sichtbarkeitsregeln. Bei Inventarwechseln ist eine Transaktion nötig, damit dieselbe Bodenbeute nicht zweimal aufgenommen wird. Ein vollständiges Event-Sourcing-System ist für den Start nicht erforderlich.

### Zugangskontrollen und Fallen – Architekturentscheidung aus dem Feature-Workshop 01.10–01.16

**Produktanforderung:** Interaktive Schlösser/Codeprüfungen/Fallen gehören **nicht allein zum Inventar**. Eine Tür, ein Tor, ein Fahrzeug, ein Terminal, ein Container oder ein anderes Szenenobjekt kann unabhängig konfigurierbare Zugangsmethoden und Fallen besitzen.

- **Szenenobjekt:** Typ, Position, Zustand und Operationen (z. B. Tür öffnen, Fahrzeug starten, Truhe öffnen). Ein Zugang kann eine einzelne Operation schützen statt zwangsläufig das gesamte Objekt.
- **Zugangskontrolle/Schloss:** erlaubte Schlüsselgegenstände, Keycards, sichere Prüfung tatsächlich eingegebener Zahl-/Textcodes, Rollen-/Objektrechte, Verriegelungs- und Wiederverriegelungsregel. **Beschlossen 01.15:** Pro Objekt boolesche Gruppen (**ODER**, **UND**) und **geordnete Sicherheitsstufen**. Hierfür ist eine strukturierte, validierbare Zugangsdefinition vorzusehen; nicht beliebig ausführbarer Programmcode. Status und bereits erfüllte Stufen müssen serverseitig kontrolliert und bei Bedarf persistent abgelegt werden.
- **Zugangsmittelzustand (01.16):** Pro Item-Vorlage/Instanz Nutzungsmodus (unbegrenzt, einmalig, n Nutzungen, zeitliche Gültigkeit oder Kombination) und dazu verbleibende Nutzungen sowie Gültigkeitsgrenzen speichern. Gemeinsame generische Item-Ladungs- und Zeitlogik nutzen; nur die **erfolgreiche, bestätigte** Authentisierung kann ggf. eine Nutzung verbrauchen. Zugangsvorgang/Verbrauch sind atomar, doppelte Clientbefehle idempotent. Entwertung/Verfall als Inventaraktion ist noch nicht spezifiziert.
- **Fehlversuche:** gemeinsam oder pro Spieler, mit eigenen Schwellenwerten und Rücksetzregeln (Zeit, Spielrunden, Erfolg, Story-Ereignis, Spielleiter); zählen nur nach validierter Anfrage; Rate-Limiting gesondert.
- **Falle/Ereignis:** unabhängig von Schlosszustand ein Auslöser, z. B. dritter falscher Code. Pro Falle einmalig oder durch Zeit/Runden/Ereignis/Spielleiter erneut scharfstellbar. Optionale eigenständige Fallen für die Karte benötigen später weitere Auslösertypen.
- **Folgen:** z. B. Alarm, Tür-/Fahrzeugsperre, Explosion als Spieleffekt, Schaden, NPC-Spawn. Konkrete Berechnungen sind abhängig vom Regelprofil, dürfen nicht hart an Fantasy- oder Kampfregeln gekoppelt sein.
- **Sicherheit:** serverseitige Berechtigungs- und Codeprüfung, Geheimnisse nur dem Spielleiter, atomare Verarbeitung paralleler Eingaben, eindeutige Befehls- und Ereigniskennungen; eine Falle darf nicht versehentlich mehrfach auslösen. Zustände und Fristen auch nach Reconnect/Neustart wiederherstellen.
- **Trennung:** Fehlversuchszähler resetten ≠ Falle erneut scharfstellen ≠ Schloss öffnen/entriegeln. Das sind verschiedene Zustände.
- **Noch nicht entschieden:** Entfernen bzw. Behalten erschöpfter Keycards, Beginn/Pausieren einer Gültigkeitsfrist, Wiederaufladen, Zeitlimit und beteiligte Spieler bei mehrstufigen Prüfungen, konkrete Zeit-/Rundensemantik und Mehrfachschwellen, Interaktions-/Fallen-Auslöser und MVP-Einführungsreihenfolge.

Die Tabellenzeilen oben sind **vorläufige Datenobjekte**, noch kein implementiertes Datenbankschema. Das genaue relationale Design wird nach Abschluss des Workshops abgestimmt.

### Karten- und Szenenmodell – Beschlüsse 02.1 bis 02.25

**Produktanforderung:** Fertige Kartenbilder werden importiert **und** Karten können innerhalb der Browseranwendung erstellt werden. **02.2:** Es gibt einen Schnellmodus und einen erweiterten Baumodus auf **demselben bearbeitbaren Szenenmodell**; konkrete Editorwerkzeuge und die Einführungsphase werden später festgelegt.

- **Asset:** hochgeladenes Bild (zunächst JPEG, PNG, WebP als mögliche Formate), mit Speicherpfad, Metadaten und nachweisbaren Nutzerrechten.
- **Szene:** veränderbarer Raum mit optionalem Maßstab/Raster und mehreren grafischen/logischen Ebenen; kann importierte Assets oder eigene Zeichendaten enthalten. **02.3 beschlossen:** Szenentyp – taktisch, Reise-/Weltkarte, Story/Atmosphäre oder freier Spieltisch – mit jeweils passenden Ansichts-/Bedieneinstellungen. Alle verwenden denselben Kampagnenkontext.
- **Raster-/Maßstabsmodell (02.4):** pro Szene wählbar **aus**, **Quadrat** oder **Hex**, mit konfigurierbarer Zellgröße, Koordinatenursprung, Maßstab und Einheit. Render-Sichtbarkeit des Rasters unabhängig von Bewegungs-Snap und von kanonischen Objektpositionen speichern. Umrechnung in Entfernungen nicht fest auf D&D oder Meter zwingen. Hexausrichtung, Distanz-/Diagonalregeln und importierte Rasterkalibrierung sind noch offen.
- **Szenenobjekt:** separate Türen, Container, Fahrzeuge, Fallen, Notizen und Tokens mit eigenen Zuständen und Berechtigungen; darf das Bild-Asset nicht destruktiv verändern.
- **Editorfunktionen (02.2 beschlossen):** Ein Schnellmodus mit Skizzen/Vektorformen und ein erweiterter Baumodus mit Tiles, Stempeln, Räumen, Wänden, Dekoration und Ebenen. Beide nutzen dasselbe Szenenobjekt; technische Umsetzung kann intern verschiedene Layer-/Objekttypen benötigen. Importierte Bilder dürfen nicht destruktiv übermalt werden. Werkzeugdetails, Undo-/Versionsmodell und MVP-Reihenfolge bleiben zu entscheiden.
- **Unterschiedliche Szenenpräsentationen (02.3):** Taktikkarte mit Tokens, Reise-/Weltkarte mit Markern, Storyansicht mit Bild/Portraits/optionalem Audio, freier Tisch zum Skizzieren. Szenentyp und Sichtbarkeit steuern, welche Werkzeuge und Assets freigegeben werden; synchronisierte Szenenwechsel ohne Verlust des persistenten Kampagnenzustands. Für Medienaufbewahrung/Lizenzen und Audio-Synchronisierung benötigen wir später gesonderte Entscheidungen.
- **Sicht- und Fog-Modell (02.5 beschlossen):** Pro Szene wählbarer manueller und dynamischer Fog-of-War-Modus. Manueller Modus speichert freigegebene/verdeckte Kartenflächen; dynamischer Modus ermittelt Sicht anhand der Figurenposition und später Sichtreichweite, Wänden/Türen, Hindernissen und Beleuchtung. Spielleiter können in beiden Modi gezielt Sichtbereiche übersteuern. Gemeinsame oder getrennte Entdeckungshistorie je Spieler und detaillierte Lichtlogik sind noch offen.
- **Erkundungserinnerung (02.6 beschlossen):** Pro Szene wählbare vollständige Wiederverdeckung oder abgedunkelte Kartenerinnerung. **Aktuelle Sicht**, **erkundete Fläche** und **manuelle Spielleiter-Übersteuerung** getrennt modellieren; Persistenz nach Reconnect/Neustart. Erkundungserinnerung berechtigt nicht zum Empfang aktueller geheimer Gegner-, Fallen- oder Objektdaten. Ob die Historie gemeinsam oder individuell gespeichert wird, ist noch offen.
- **Sichtteilung (02.7):** Pro Szene wählt der Spielleiter gemeinsame Gruppensicht/Erkundung oder individuelle Sicht/Erkundung je Spieler. Zustand und Verlauf sind dauerhaft zu speichern und je Spielerfreigabe zu filtern; Gruppenaufteilung und Wechsel zwischen Modi werden später spezifiziert.
- **Lichtmodell (02.8):** Pro Szene einfacher oder dynamischer Beleuchtungsmodus. Lichtquellen haben optional Farbe, Radius, Intensität, Richtung, Status und Referenz auf eine feste Position oder ein bewegliches Objekt (Token, Item, Fahrzeug). Schalten durch autorisierte Spieler, Spielleiter oder Ereignisse. Lichtberechnung, Fog-Masken, Sicht und Objektberechtigungen getrennt behandeln. Zeit- und Verbrauchsregeln bleiben offen.
- **Szenenhindernisse (02.9):** Wiederverwendbare logische Komponente an Wänden, Türen, Fenstern und sonstigen Objekten: Sichtblockade, Lichtblockade, Bewegungsblockade getrennt definieren. Zustände (offen, geschlossen, verriegelt, zerstört, deaktiviert) ändern das Blockadeprofil. Das universelle Zugangs-/Schloss-/Fallensystem ist wiederverwendbar; **Verriegelungszustand ≠ Durchgangs-/Sichtzustand**. Geometrie, Status und Rechte persistent und serverseitig maßgeblich; Geheimtüren nicht vorzeitig an Spieler übertragen. Kollisionsausnahmen und genaue Sichtlinien-/Lichtberechnung später definieren.
- **Mehrere Kartenbilder/Stockwerke (02.10):** Eine Szene referenziert mehrere Bild-/Karten-Instanzen mit eigenen Transformationen (Position, Drehung, Skalierung, Stapelreihenfolge), optional in getrennten Stockwerken. **Grafische Ebenen und logische Stockwerke sind separate Konzepte.** Tokens, Hindernisse, Lichtquellen, Ereignisse und Fog-/Sichtzustände brauchen die korrekte Karten-/Stockwerkszuordnung; Koordinatentransformationen dürfen Objektpositionen nicht stillschweigend zerstören. Synchronisierung, Berechtigungen und persistente Zustände unabhängig vom aktuell gewählten Stockwerk gewährleisten. Übergänge zwischen Stockwerken, parallele Perspektiven und Größenlimits bleiben offen.
- **Szenenfreigabe und Etagenentdeckung (02.11):** Entwürfe bleiben privat und werden für alle, Gruppen oder einzelne Spieler freigegeben. Ein Stockwerk kann optional erst dann im Etagenwähler erscheinen, wenn ein verknüpfter Zugang (Treppe, Aufzug, Portal) nach den Sichtregeln entdeckt wurde. Bekannte Etage, Zutrittsberechtigung, aktuelle Sicht und Freigabe von Karteninhalten bleiben getrennte Zustände; serverseitig prüfen und speichern.
- **Kartenimport (02.12):** Importer-Adapter für Bilddateien und kompatible VTT-Datensätze. Importphasen: Dateiformat sicher erkennen/validieren, lesbare Quelldaten mit unterstützten Metadaten extrahieren, Vorschau und Auswahl durch den Spielleiter, danach persistente Zuordnung zu Kartenbild, Raster, Wänden, Lichtquellen und anderen unterstützten generischen Objekten. Koordinaten/Skalierung gesondert kalibrieren, unbekannte Metadaten protokollieren ohne Geheimnisse zu leaken. Keine ausführbaren Skripte aus Fremdformaten übernehmen. Konkrete DD2VTT/UVTT-Varianten und Exportformate bleiben bis zu Kompatibilitätstests offen.
- **Interaktionsregeln und Aktion-Reaktion-System (02.13):** Gemeinsamer, regelwerksneutraler Mechanismus für typisierte **Auslöser → optionale Bedingungen → erlaubte Reaktionen** über Türen, Truhen, Terminals, Fahrzeuge, Tokens, Items, Fallen und Story-Objekte. Objektübergreifende Aktionen, mehrere Folgen und bedingte Folgeschritte sind als Anforderungen vorzusehen. Regeldefinitionen validieren und in einem **serverautoritären, begrenzten** Ausführungssystem auswerten; keine ungeprüften Nutzerskripte. Jede Aktion überprüft Berechtigungen, Referenzen und Objektzustände. Zustandsänderungen/Inventartransfers atomar bzw. konsistent, ausgelöste Folgen idempotent; Kaskaden gegen Zyklen und endlose Rekursion begrenzen. Ereignisse, Zustände und relevante Fristen persistent synchronisieren; Geheimregeln und versteckte Ereignisse nicht an unberechtigte Clients übertragen.
- **Editor-UX (02.13/02.14 beschlossen):** Zwei Ansichten für **dieselbe persistente, versionierbare Regeldefinition**: ein einfacher WENN/FALLS/DANN-Assistent und ein visueller Knoten-/Ablaufeditor für verzweigte Regeln. Beide bieten Vorlagen, lesbare Regelzusammenfassungen, validierte Objektverknüpfungen, Test-/Prüfmodus und Spielleiter-Log. Komplexe Strukturen, die der Assistent nicht vollständig editieren kann, müssen verlustfrei erhalten bleiben und dort gegebenenfalls nur lesbar bzw. eingeschränkt editierbar sein. Kein Export/Import zwischen getrennten Regelformaten beim Ansichtswechsel; gemeinsame API und serverseitige Validierung. Tests sollten in einer isolierten Vorschau ohne echte Spielzustandsänderung laufen.
- **Auslöserbibliothek (02.15):** Typisierte Ereignisse für Interaktionen, Raum-/Bewegungsereignisse, Objektzustände, Gegenstände/Inventar, Codes/Fehlversuche, Quest-/Storyereignisse, NPCs/Fahrzeuge und Spielleiteraktionen. **Zwei getrennte Zeitgrundlagen als verbindliche Produktanforderung:** (1) verstrichene Echtzeit in Sekunden/Minuten/Stunden und (2) Spielrunden bzw. Rundenereignisse. Kein implizites Umrechnen; Runden-Auslöser benötigen einen tatsächlichen Rundenzähler oder ein entsprechendes Regelmodul. Persistente Timer-/Rundenzählerzustände und eindeutige Ereignis-IDs, idempotente Ausführung, Rechte- und Geheimdatenfilter. **02.16 beschlossen:** Jeder Echtzeit- oder Rundenauslöser ist einmalig oder wiederkehrend konfigurierbar, mit erlaubten Steueraktionen Start, Pause/Fortsetzen, Reset/Neustart und Abbruch durch autorisierte Aktionen/Ereignisse. Serverautoritativer persistenter Status mindestens Regel-/Instanzbezug, Zeitbasis, Zielzeitpunkt bzw. Zielrundenzahl, Aktiv-/Pause-Zustand und eindeutige Auslösekennung. Wiederholungsereignisse unterscheiden, aber einen einzelnen Tick bei Doppelnachrichten/Reconnect idempotent behandeln. **Offen:** Semantik von Offline-Zeit, Pausierung der Kampagne, verpassten Wiederholungen und gleichzeitiger Verarbeitung.
- **Bedingungsgruppen (02.17):** Gruppen aus UND/ODER/NICHT einschließlich Verschachtelung; einheitlich von Regelassistent und Graph-Editor gelesen. Typisierte boolesche/vergleichende Bedingungen müssen serverseitig validiert werden, ohne beliebige Skriptausführung.
- **Objektgebundene Node-Ports (02.17):** Jedes platzierte Szenenobjekt (auch zunächst dekorative Objekte) besitzt eine **stabile Instanz-ID**, einen menschenlesbaren Namen, Szene-/Stockwerkszuordnung und über seinen **Objekttyp definierte Port-Fähigkeiten** (Aktionseingänge, Ereignisausgänge, optional Daten-/Zustandswerte). Die Node-Palette zeigt z. B. `Tür – Szene – Stockwerk – Nordtor` und erlaubt die Auswahl dieser konkreten Objektinstanz. Eine Node verweist auf das reale Objekt und ist **keine duplizierte Kopie**. Umbenennung ändert den Anzeigenamen, nicht die Referenz. Löschung oder fehlende Fähigkeiten führen zu sichtbaren, nicht still reparierten Referenzfehlern.
- **Graph-Verbindungen (02.17):** Persistente Kanten zwischen `sourceNodeId/sourcePortId` und `targetNodeId/targetPortId`; passende Porttypen und Befugnisse vor Speichern und Ausführung prüfen. Beispiel: `Schalter.aktiviert` → `Bedingung(Keycard UND kein Alarm)` → `Tür.entriegeln`, danach `Tür.entriegelt` → `Tür.öffnen`. Ein Aktions-Eingang führt ausschließlich nach erfolgreicher serverseitiger Berechtigungs-/Zustandsprüfung zum entsprechenden Ereignisausgang. Objekt-Ports sollen aus erweiterbaren, versionierten Vorlagen stammen; neue Modultypen dürfen zusätzliche Ports bereitstellen.
- **Graph-Ausführung und UX:** Der einfache Assistent und der visuelle Editor benutzen dasselbe Regelformat; keine Datenverluste beim Ansichtswechsel. Server steuert Ausführung, sichert konsistente Objektzustände, dedupliziert Ereignisse und begrenzt Schleifen/Kaskaden. Das Layout der Nodes und ihrer Verbindungspfade ist Editorpräsentation und vom autoritativen Spielzustand zu trennen. **02.18 beschlossen:** Verbindungen dürfen szenen- und stockwerkübergreifend **innerhalb einer Kampagne** verlaufen. **Offen:** Verhalten in inaktiven Szenen (02.19), Event- versus Datenport-Typen, Konfliktregeln und Bearbeitung unter mehreren Spielleitern.
- **Kampagnenweite Node-Verbindungen (02.18):** Ein serverseitiger Ereignisrouter löst Zielobjekte über stabile IDs mit obligatorischer Kampagnenzuordnung auf. Verbindungen über Szenen und Stockwerke hinweg sind zulässig, über Kampagnengrenzen hinweg nicht. Rechte/Zugangsbedingungen gelten auch für automatisierte Aktionseingänge. Das Auslösen darf nicht vom geöffneten Client oder der aktuell angezeigten Szene abhängig sein; **02.19 beschlossen:** Pro Regel kann für eine inaktive Zielszene sofortige Ausführung, persistentes Vormerken bis zur Aktivierung oder Verwerfen bei inaktiver Szene gewählt werden. Geheime Ziele nicht an unberechtigte Browser ausliefern; Zustandsänderungen speichern, Ereignisse deduplizieren, Zyklen begrenzen und Fehler bei gelöschten Referenzen melden. Echtzeit- und rundenbasierte Trigger unabhängig vom Zielort beibehalten.
- **Ausführungsrichtlinie bei inaktiver Szene (02.19):** Node-Regel speichert den Modus `immediate`, `defer_until_activation` oder `active_only` (konzeptionelle Bezeichnungen). Der Server führt unmittelbare Zustandsaktionen ohne sichtbaren Browser aus; vorgemerkte Aufträge erhalten stabile Ereignis-/Auftrags-IDs, Zielreferenz, Status und Aktivierungsbedingung, bleiben persistent und werden bei späterem Ausführen erneut auf Rechte, Bedingungen und gültigen Objektzustand geprüft. Bei `active_only` wird der Versuch bei inaktiver Szene verworfen, nicht verspätet nachgeholt. Deduplication/Idempotenz je Auftrag und ein nachvollziehbares Spielleiterprotokoll; Fehlziele und ungültige Bedingungen sichtbar als Fehler behandeln. Die Definition von Szenenaktivierung, Gruppenperspektiven, Ablauffristen und konkurrierenden Aufträgen ist später zu entscheiden.
- **Typisierte Node-Ports (02.20):** Portkategorien mindestens Ereignis-/Aktionstrigger, boolescher Zustand, Zahl, Text und stabile Objekt-/Figuren-/Itemreferenzen, später erweiterbar. Portmetadaten umfassen Richtung, Typ und stabile ID. Verbindungen werden beim Bearbeiten und serverseitig bei der Ausführung validiert; inkompatible Typen dürfen nicht stillschweigend vermischt werden.
- **Inverter-Node (02.20):** Eigenständiger sichtbarer, typisierter NOT-Knoten mit booleschem Eingang und booleschem Ausgang; hinter einen Ausgang oder vor einen Eingang schaltbar. Keine implizite Inversion beliebiger Event-, Text- oder Objektports. Details zu Ereignisimpulsen und Dauersignalen werden in 02.21 entschieden.
- **Signalanzeige und farbige Verbindungen (02.20):** Visuelle Leitungen und Ports anhand ihrer **Typen** farblich codieren. Verbindung vorhanden, Wert/Signal aktiv, Ereignisimpuls und Fehlerzustand als **separate Diagnose-/Präsentationsdimension** darstellen; zusätzliche Beschriftungen/Icons statt exklusiver Farbcodierung. Berechtigter Spielleiter kann beim Test den **tatsächlichen Ist-Zustand** aus dem autoritativen Servermodell sehen (inkl. fehlendem Signal), während Simulationen ohne reale Zustandsänderungen gekennzeichnet sind. Eine bestehende Kante ist nicht gleich ein aktives Signal. Signalverlauf und Werte müssen aus Serverzuständen/Ereignissen stammen, Graphlayout/Farbwahl dürfen diese nicht definieren. Debug-Daten und Geheimnisse nur berechtigten Spielleitern liefern.
- **Qualitäts-/Sicherheitsplanung (02.20):** Datentypen, Zustandsmodell, eindeutige Ereigniskennungen, Iterationen/Limits bei Event-Kaskaden, deterministische Regeln bei konkurrierenden Signalen, graphbezogene Versionierung sowie isolierte Testausführung sorgfältig spezifizieren und testen. Konkrete Farbpalette, Persistenz von kurzlebigen Impulsen und exakte Signalzeitpunkte bleiben offen.
- **Signalarten und Halteschalter (02.21):** Ereignisports übertragen **punktuelle Impulse**, Daten-/Statusports dagegen **anliegende aktuelle Werte**. Eine Schaltobjekt-Instanz erhält als Eigenschaft **Schalter** (rastender boolescher EIN/AUS-Zustand) oder **Taster** (EIN ausschließlich während gültiger Drück-/Halteaktion). Der Betätigungsimpuls ist ein eigener Ereignisport und nicht identisch mit einem anliegenden Haltezustand. Bei einem Halteschalter gilt das boolesche Ausgangssignal `true` nur solange die zugeordnete Aktion tatsächlich gültig aufrechterhalten wird; beim Loslassen wird `false` übertragen. Ein anderer Spieler kann währenddessen unabhängig eine so freigegebene Tür durchqueren. Halteaktionen benötigen serverseitig autorisierten Spieler-/Figurenbezug, Start/Ende, Schutz gegen falsche dauerhafte Aktivsignale sowie eine noch zu spezifizierende Abbruchstrategie bei Verbindungsverlust. **02.22 beschlossen:** Die angeschlossene Tür/Barriere definiert unabhängig vom Schalter-/Taster-Modus ihre Signalverlust-Reaktion: sofort zurückschalten, Stellung beibehalten oder nach separat wählbarer Echtzeit- bzw. Rundenverzögerung reagieren. Konsequenzen für Figuren im Durchgang bleiben in 02.23 offen.
- **Ist-Zustand/Simulation (02.21):** Verbindungstopologie, boolesche Ausgangszustände, zuletzt ausgelöster Ereignisimpuls und Fehlersituationen bleiben unterschiedliche Diagnosezustände. Im Live-Test nur autorisierte Serverzustände zeigen; in isolierter Simulation keine echten Objektzustände verändern. Eine Inverter-Node invertiert boolesche anliegende Werte, keine Ereignisimpulse ohne definierten Konverter. Exakte Impulsdauer, Reconnect, Kollision und gleichzeitige Halter offen.
- **Schaltquellen und Signalverlust (02.22):** Die Objektvorlage enthält passende Ports und eine konfigurierbare Betriebsart `switch` (rastend) oder `push_button` (gehalten). Der boolesche Zustand wird serverseitig autoritativ geführt; einzelne Betätigungsereignisse sind separate Ports. Zielobjekte speichern unabhängig davon eine Rückstellregel `immediate`, `retain_state` oder `delayed` samt gewählter Zeitgrundlage Echtzeit/Spielrunden. Stabile Referenzen, berechtigtes Starten/Beenden der Halteaktion, sichere Behandlung von Verbindungsabbrüchen und Synchronisierung von Mehrspielerzuständen vorsehen. Konkrete Kollisions- und Schadensfolgen bei Schließen während einer Durchquerung sind offen (02.23).
- **Blockierte Schließvorgänge (02.23):** Tür-/Barriereninstanzen besitzen eine vom Schaltertyp unabhängige Kollisionsrichtlinie `wait`, `reopen` oder `force_close` (konzeptionelle Namen). Der serverseitige Schließversuch prüft den logischen Durchgangsbereich gegen relevante Figuren/Objekte. Schließbefehl, erkannte Hindernisse, abgebrochener Vorgang, Wiederöffnung und tatsächlich abgeschlossene Schließung sind getrennte Zustände/Ereignisports; `closed` erst nach erfolgreichem Wechsel ausgeben. Parallel ablaufende Figurenbewegung und Türzustandsänderung müssen konsistent verarbeitet werden. Im Modus `force_close` keine implizite Schadens- oder Positionsänderung annehmen; regelwerksabhängige Folgen folgen erst mit 02.24. Exakte Kollisionsgeometrie, unterschiedliche Token-/Fahrzeuggrößen, Wiederholungsversuche, Mehrspielerzustände und Bewegung während der Schließung bleiben zu spezifizieren. Test-/Simulationsdaten dürfen keine echten Zustände verändern.
- **Kampagnenstandards und Objekt-Ausnahmen (02.24):** Kampagneneinrichtung enthält zentrale Standardwerte für allgemeines Objekt-/Interaktionsverhalten (z. B. Tür-Kollision aus 02.23, Folgen erzwungener Türschließung und daran geknüpfte Regelprofil-/Node-Effekte). Für neue Szenenobjekte gelten typbezogene Kampagnenstandards, sofern eine Eigenschaft nicht ausdrücklich an der Objektinstanz überschrieben wurde. In der UI effektiven Wert und Quelle (Standard vs. Instanzausnahme) zeigen. **Auflösung und Rechte serverseitig** durchführen; keine fixen D&D-Formeln im Kern, regelabhängige Schaden-/Statusberechnung nur über vorhandene Profile. Konfiguration und Ausnahmen persistent/versionierbar; **02.25 beschlossen:** Für jede Änderung eine Vorschau und explizite Auswahl, ob sie nur Neuanlagen oder auch bestehende nicht überschriebene Objektwerte betrifft. Objekt-Ausnahmen bleiben geschützt. Bei Anwendung nur auf Neuanlagen muss der alte wirksame Wert bereits bestehender Instanzen erhalten bleiben (z. B. Snapshot/versionierte Default-Bindung). Bestehende Standardwerte nur mit bewusster Auswahl ändern; Zielmenge und Auswirkungen vor Commit ermitteln. Autorisierung, nachvollziehbare Versionierung/Protokollierung und konsistentes Anwenden sind erforderlich. Verhalten aktiver Timer/Node-Ereignisse und Undo bleiben gesondert offen. Kampagnenerstellungs-Assistent wird in Hauptbereich 09 genauer gestaltet.
- **Serverseitiger Geheimnisschutz:** Sicht auf Kartenfläche und Autorisierung für Objektdaten sind getrennt. Verborgene NPCs, Fallen, Geheimtüren, SL-Notizen oder andere sensitive Daten niemals allein durch verdeckende Client-Grafik schützen; serverseitig je Teilnehmer filtern. Persistenz/Neuverbindung und effiziente Synchronisierung der Sichtmasken einplanen.
- **Speicherung/Sicherheit:** persistente Editoroperationen, Versionen/ggf. Undo, Sichtbarkeit und Rechte serverseitig; Bild-Uploads sicher prüfen und begrenzen. Nicht freigegebene Spielleiter-Layer werden Spielerclients nicht übermittelt.

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
