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
| **01** | **Inventar & Gegenstände** | Liste/Kachel-UI, Kategorie, Slots, Container, Menge, Gewicht, Geld, Aufheben, Handel, Ausrüsten, Effekte | **In Bearbeitung: 01.1 C (Ansicht), 01.2 C (Container), 01.3 B (Traglast), 01.4 C (Handel), 01.5 C (Fenster), 01.6 C (Slots), 01.7 C (Effekte und Verbrauchszähler)** |
| **02** | **Karten & Szenenerstellung** | Upload, freie Zeichenfläche, Karten-Editor, Import, Raster, Ebenen, Szene vs. Karte, Szenenwechsel | Offen |
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
- **Begrenzte Verwendungen und Munition – BESCHLOSSEN:** Gegenstände können eigene Verbrauchszähler mit aktuellen und maximalen Werten haben. Beispiele: **Feuerballstab mit 3/3 Ladungen** (eine Ladung pro tatsächlicher Feuerball-Anwendung) und **Gewehr mit 27/27 Schuss im Magazin** (Schüsse reduzieren die verfügbare Munition). Nutzung muss serverseitig geprüft und der Verbrauch konsistent für alle berechtigten Teilnehmer gespeichert werden. Bei 0 ist die entsprechende Aktion bis zum Wiederaufladen/Nachladen blockiert. **Offen:** Reservemunition, Magazinwechsel, Wiederaufladeregeln, Burst-/Mehrfachschüsse.
- **Zeit- und Rundenzählung – Detailregeln noch offen:** Startzeitpunkt beim Auslösen, Pausen/Offline-Zeit bei Echtzeit-Effekten, Rundenbeginn/-ende als Ablaufauslöser, manuelles Spielleiter-Override und Stapelregeln werden später separat festgelegt. Es wird keine Timer-Semantik stillschweigend vorausgesetzt.
- **Nächster Entscheidungspunkt 01.8:** Wiederauffüllen von Aufladungen/Munition: manuell, automatisch nach Regeln oder **pro Gegenstand konfigurierbar**?

### A. Wie sieht es im Browser aus?

**Mögliche Darstellung:**
- **Liste:** kompakt und gut bei vielen Objekten; Spalten für Name, Anzahl, Gewicht/Tags, Aktionen.
- **Kachelraster:** große Item-Icons, intuitives Ziehen; braucht mehr Platz.
- **Kombination (Empfehlung):** Umschalten zwischen Liste und Kacheln; Suche, Filter, Sortierung; Charakterbogen rechts als eigenes Fenster/Panel.

**Genrebeispiele:** Zauberschwert, Cyberdeck, Pistole, Medkit, Schlüsselkarte, Fahrzeugersatzteil, steampunkartiges Werkzeug und Dokument; **keine** systemseitige Pflicht für Waffen- oder Rüstungswerte.

### B. Wo liegen Gegenstände?

- Beim **Charakter** im Inventar.
- In **Containern** (Rucksack, Truhe, Fahrzeug-Laderaum).
- **Auf dem Spielfeld** als Bodenbeute.
- In einem **gemeinsamen Gruppenlager** (optional).
- Bei einem **NPC/Gegner** (ggf. geheim).
- In der **Vorlagenbibliothek**, wenn noch keine konkrete Instanz erzeugt wurde.

**Entwurfsprinzip:** Eine Item-Vorlage (Definition, Icon und erlaubte Effekte) ist nicht dieselbe Sache wie eine Item-Instanz (Besitzer, Fundort, Menge, individuelle Werte). Transfer gehört auf den Server und muss atomar sein.

### C. Interaktionen

- Fund/Beute ansehen; **Aufnehmen, Ablegen, Ziehen, Übergeben, Ausrüsten/Abnehmen**.
- Stapelbar oder einmalig; Chargen/Verbrauch; optional Haltbarkeit. **Beschlossen:** Ladungen und Munition als aktuelle/maximale Zähler, z. B. Feuerballstab (3/3) oder Gewehrmagazin (27/27).
- Wählbare Regeln zu Gewicht, Volumen, Kapazität oder **keine Traglast**.
- Geld nicht zwingend Gold: frei definierte Währungen oder abstrakte Ressourcen.
- „Unbekannter Gegenstand“: Der SL kann Details bis zur Identifikation verbergen.
- Optional konfigurierbare Ausrüstungsslots, z. B. Hände, Kopf, Cyberimplantate oder freie Slots.
- **Beschlossen:** Effekte können rein beschreibend oder automatisch sein und auch zeitlich (Sekunden/Minuten) oder rundenbasiert ablaufen. Abgeleitete Werte ändern sich während der Wirkung; Basiswerte bleiben erhalten. Für Ladungen/Schüsse wird der Verbrauch serverseitig geprüft.

### D. Offene Entscheidungen für dieses Thema

1. **Entschieden:** Kombinierte Liste/Kachel-Darstellung (Variante C), umschaltbar mit Suche/Filtern/Ausrüstungszugriff.
2. **Entschieden (Konzept):** Verschachtelte Container und gemeinsames Gruppenlager werden unterstützt; Umsetzungstermin/Berechtigungen noch offen.
3. **Teilweise entschieden:** Gewicht, Traglast und Containerkapazität sind pro Kampagne optional (Variante B). **Ausrüstungsplätze sind optional und frei pro Charakterbogenvorlage definierbar (01.6 C).** Währungen und Details der Traglastlogik bleiben offen.
4. **Entschieden:** Gegenstandstausch ist pro Kampagne konfigurierbar (Variante C); Empfangsbestätigung und ggf. SL-Freigabe gehören zum Ablauf.
5. **Entschieden:** Inventar als Reiter im Charakterbogen **und** als separates verschiebbares, skalierbares Fenster; mehrere Inventare gleichzeitig möglich (Variante C).
6. **Entschieden:** Itemeffekte als Kombination aus manuell und automatisch (01.7 C), temporäre Laufzeiten sowohl in Echtzeit als auch Spielrunden, begrenzte Nutzungen und Munition.
7. **Offen, als Nächstes 01.8:** Aufladungen, Magazin-Nachladen und Ressourcen-Wiederherstellung.

**Aktueller Gesprächsstand:** 01.1 Inventaransicht = C; 01.2 Container/Gruppenlager = C; 01.3 Gewicht/Traglast = B; 01.4 Gegenstandstausch = C; 01.5 Inventarfenster = C; 01.6 Ausrüstungsslots = C; **01.7 Itemeffekte = C, inklusive Echtzeit- und Rundendauer sowie Ladungen/Munition**. Als Nächstes 01.8 Wiederaufladen/Nachladen. Weitere Fragen einzeln besprechen.

### E. Vorläufige technische Folgerungen (noch nicht festgelegt)

Objektvorlagen, Item-Instanzen, Speicherorte/Container, optionales Slot-/Effektmodell, Rechteprüfung, serverseitige Transfer-Transaktionen und eine konfigurierbare UI.

---

## 02 – Karten und Szenen: Gesprächsvorlage

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

- Nur 2D-Top-down oder zusätzlich Szenenbilder/Panoramen?
- Reichen Bildimport und einfache Zeichenwerkzeuge für die erste Version?
- Raster wählbar: kein Raster, Quadrat, Hex – und Maßstab (Meter/Fuß/frei)?
- Sicht: manuell aufdeckbarer Nebel oder dynamische Sicht pro Token?
- Dürfen mehrere Karten nebeneinander in einer Szene liegen?
- Welche Interaktionen: Türen öffnen, Beute in Kisten, Teleportfelder, Notizmarker?
- Kartenentwürfe privat für den SL, erst bei Aktivierung für Spieler sichtbar?
- Wie importieren wir externe Kartendaten und dokumentieren die Rechte der Nutzer-Assets?

### Vorläufige technische Folgerungen

Reine Bildspeicherung genügt nicht: Szenen-Metadaten, Raster-/Maßstab, Layer-Objekte, serverseitige Sichtbarkeitsregeln, Objekt-IDs und eigene Speicherformate werden benötigt.

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
