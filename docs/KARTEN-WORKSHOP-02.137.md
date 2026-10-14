# AdventureShift – Karten-Workshop: Beschluss 02.137 A – Audio-Vorlagen unverändert einsetzen, erst danach berechtigt bearbeiten

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.137; nächste offene Entscheidung 02.138.
**Status:** Verbindlicher Fachbeschluss, konzeptioneller Umsetzungs- und Abnahmetestplan; **noch keine Softwareimplementierung**, kein finales UI, keine endgültigen APIs/DB-Schemata und keine MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnen-/Rollenstandards und markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.85–02.89 – Szenenvorlagen, Berechtigung, Updates und dort separat beschlossene typisierte Szenenparameter](KARTEN-WORKSHOP-02.89.md) · [02.99 – autorisierte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – offizielle Hinweise/ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – optionaler Chat](KARTEN-WORKSHOP-02.105.md) · [02.122 A – keine Chat-Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.132 C – optionales Musik-/Playlist-/Soundboardmodul](KARTEN-WORKSHOP-02.132.md) · [02.133 A – ausschließlich lokale Musik, kein gemeinsamer Playhead](KARTEN-WORKSHOP-02.133.md) · [02.134 C – lokale Loops/Fades/Layer](KARTEN-WORKSHOP-02.134.md) · [02.135 C – rechtmäßig wiederverwendbare Audio-Konfigurationsvorlagen](KARTEN-WORKSHOP-02.135.md) · [02.136 C – bewusste kontrollierte Vorlagenversionsübernahme](KARTEN-WORKSHOP-02.136.md) · [Medien und Lizenzen](LIZENZEN.md).

## 1. Verbindliche Entscheidung – Variante 02.137 A

**Der Projektinhaber hat ausdrücklich A gewählt:** Eine rechtmäßig zugängliche Playlist- oder Soundboardvorlage wird **beim Einfügen in die Zielkampagne mit ihren bereits gespeicherten und dort zulässigen Konfigurationseinstellungen** übernommen. **Kein Parameterdialog vor/während dem Einfügen, keine vom Vorlagenautor definierte parametrisierbare Einfügemaske, keine an den Insert-Aufruf angehängten Track-/Cue-/Loop-/Fade-/Layer-Overrides.** Wer anschließend eine eigene Zielplaylist oder ein Soundboard verändern möchte, verwendet **erst nach der regulären, vollständig geprüften Übernahme** den bestehenden, dafür berechtigten normalen Bearbeitungsvorgang.

**Beispiel:** Die SL verwendet eine freigegebene „Taverne“-Soundboardvorlage mit den gespeicherten, für diese Kampagne erlaubten Tracks und Cue-Reihenfolgen. Beim Einfügen gibt es keine zusätzliche Frage „Regen?“, „Musik stärker?“, „andere Track-Reihenfolge?“. Erst nachdem die erlaubte Vorlage übernommen und eine entsprechende Zielkonfiguration erzeugt wurde, kann eine dazu berechtigte Person in dieser Zielkonfiguration solche fachlich unterstützten Felder separat bearbeiten. Die Quellvorlage bleibt unverändert. Persönliche Lautstärke/Mute bleiben unabhängig.

**Nicht gewählt:** B (ungeprüft alle Source-/Asset-/Fremd-/Weltwerte überschreiben) und C (frei benennbare, typisierte Parameter mit Eingabedialog zum Zeitpunkt der Audio-Vorlagenübernahme). **A ist bewusst ein negativer Funktionsentscheid:** Kein versteckter 02.25- oder SL-Ausnahmeschalter, der genau diese Audio-Einfügeparameter wieder aktiviert. Dieser Beschluss verbietet **nicht** 02.89 C – dort separat beschlossene parametrisierte *Karten-/Szenen*-Vorlagen bleiben ein anderes Feature.

## 2. Was eine feste Audio-Vorlage bedeutet – Rechte vor jedem Einfügen

1. **Modul-/Kampagnengrenze:** Die Musikunterfunktion aus **02.132 C** muss beim tatsächlich anzuwendenden Audio-Vorlagenvorgang eingeschaltet sein; 02.25-Kampagnen-/Rollen-/Gruppen-/Personenstandards mit gültigen markierten Ausnahmen bleiben. Musik Aus führt zu **keinem** neuen Audio-Vorlagen-Insert-/Cue-/Playbackvorgang; integrierter Chat, Würfel/System und 02.49–02.51-Spielszenenakustik bleiben eigenständig.
2. **02.135-C-Quell-/Zielvertrag:** Einfügen als **freigegebene Quellreferenz** oder **tatsächlich lizenz-/kopierberechtigte neue Konfigurationskopie** weiterhin gemäß 02.135 C. Das bedeutet weder pauschale Dateikopie noch automatisch übertragenes Medien-/Streaming-/DRM-/Lizenzrecht; Original-Owner-/Quelle-/Ziel-/Rollen-/Szenen-/Empfänger-/Geheimnisrechte pro Vorgang validieren.
3. **Nur erlaubte gespeicherte Werte:** Die übernommenen Audioasset-Referenzen, Track-/Cue-Reihenfolgen, Kategorie-/Playlist-/Soundboardnamen sowie für die Zielkampagne zugelassene 02.134-C-Loop-/Fade-/Layer-Voreinstellungen stammen aus der **gewählten freigegebenen Vorlagenrevision**. Für fehlende, verbotene, technisch inkompatible oder abgelaufene Abhängigkeiten **vor Commit** sicher abweisen oder – nur wenn eine gesonderte, klar erkennbare Zielpolicy dies bereits ausdrücklich vorsieht – ohne Geheimnisleck rechtmäßig auslassen; niemals mit willkürlich gewählten neuen geheimen Tracks „reparieren“.
4. **Keine Template-Insert-Overrides:** Kein `audioTemplateParameters`, `insertOverrides`, `templateTrackChoice`, `initialFadeOverride`, `templatePlayerGain`, `customSoundboardLayerOnInsert` oder gleichartiger User-/SL-/API-/Node-Eingabepfad in der **Einfügeoperation**. Eventuell später definierte Server-/Clientnamen sind nur Negativbeispiele, keine endgültigen Schemaentscheidungen.
5. **Quelle und Ziel versioniert trennen:** Bei Kopie werden nach den bereits beschlossenen Rechten neue Ziel-IDs/Herkunft/Zielrevisionen angelegt, Sourcekonfiguration bleibt unverändert. Bei Referenz wird eine **wirklich freigegebene, geprüfte Revision** verwendet, nicht ungefragt „immer neueste“ (02.136 C); der Referenzmodus ist nicht heimlich eine editierbare Kopie.
6. **Bearbeitung erst nach Einfügen:** Wer im Ziel bearbeiten darf, kann anschließend mit eigenständigen **02.132-/02.135-konformen** Playlist-/Cue-/Soundboard-Bearbeitungsrechten und 02.25-Policy z. B. Trackreihenfolge oder erlaubte lokale 02.134-Mischvoreinstellungen bearbeiten, falls diese Bearbeitungsfunktion implementiert und aktiviert ist. Jeder nachgelagerte Edit ist eine **separate, bewusste, revisions-/ACL-/Lizenzgeprüfte** Zieloperation – keine mit Insert atomar verschmolzene Parametereingabe.
7. **Quellreferenz nicht frei veränderbar:** Der Referenzmodus darf durch nachträgliches „Bearbeiten“ **nicht** die fremde Quellvorlage, andere Kampagnen oder ihre Assets ändern. Für eigenständige Zielanpassungen ist nach 02.135 C nötigenfalls die **zusätzlich erlaubte Kopie** und deren separates Bearbeitungsrecht erforderlich. Berechtigte lokale Source-Owner dürfen Source-Templates nur in einem separat autorisierten Source-Editor ändern; nicht durch Target-Insert.
8. **Kein pauschales Defaultergänzen:** A verpflichtet das System nicht zu permanenten Einfüge-Vorschlägen, vorgefertigten „Sofortvarianten“, automatischer Tracksubstitution, Playlist-Generierung oder einer stillen Profilentscheidung je Session. Etwaige technische Migrationsdefaults dürfen niemals Quell-/Lizenz-/Geheimnis-/Actor-/Szenenrechte erweitern oder die semantischen gespeicherten zulässigen Templatewerte unbemerkt ersetzen.

## 3. Fortgeltende Rechte und bereits entschiedene Funktionstrennung

| Bestehender Beschluss | Folgerung für 02.137 A |
| --- | --- |
| **02.25** | Rollen-/Kampagnen-/Personen-/Gruppenstandards und gültige Ausnahmen für *bestehende* Rechte; **keine** Audio-Insert-Parameterfähigkeit als Ausnahme |
| **02.132 C** | Playlists/Soundboards, erlaubte Asset-/Cueverwaltung, SL-bestätigte/geprüfte automatisierte Musikauswahl und individuelle Volume/Mute bleiben – aber **kein** besonderer Inserttuning-Workflow |
| **02.133 A** | Nur individuelle lokale Wiedergabe, jeder neue Track beginnt bei **0**; keine globale Play-/Pause-/Seekzeit, kein Join-/Reconnect-Catch-up |
| **02.134 C** | Freigegebene lokale Loop-/Fade-/Crossfade-/Layer-Optionen bleiben; übernommen werden nur zulässige **gespeicherte** Werte, Änderungen erst separat am Ziel |
| **02.135 C** | Getrennter referenzierter oder rechtmäßig kopierter Vorlageneinsatz, Source-/Target-/Owner-/Audioasset-/Lizenz-/Secret-/Empfängerrechte bleiben |
| **02.136 C** | Neue Quellvorlagenversionen können nach Diff/Conflict/ACL und **bewusstem** separatem Update übernommen werden; kein Insert-Parameterdialog, kein Auto-Update |
| **02.89 C Szenen-/Kartenvorlagen** | Dort ausdrücklich gewählte parametrische Einfügefelder bleiben **nur** für Szenen-/Kartenobjekte beschlossen, nicht für Audio-Plays |
| **02.49–02.51 / 02.99** | Audio-Vorlage erzeugt keinen realen Schall-/Sensor-/Node-/Alarm-/Tür-/NPC-/Quest-/Würfel-/Turn-/Inventareffekt |
| **02.101–02.104** | Einfügen, Bestätigen oder nachträgliches Bearbeiten erzeugt kein amtliches 02.102-ACK |
| **02.105 / 02.122 A** | Kein Chatzwang, keine Integration von Chat-Sprachnachrichten, Mikrofonmitschnitt oder externer Voice-Transkription |

## 4. Ablauf und konzeptionelle Architektur

1. **Nur bestehende Insert-Varianten:** `ReferenceAudioTemplate` oder `CopyAudioTemplateConfiguration` sind **konzeptionelle** 02.135-Operationstypen. Ihre Payload umfasst erlaubte Quellrevision, rechtmäßig gewählten Zielscope, dokumentierte Berechtigungen und erwartete Revision/Operation-ID – **keine** Endbenutzer-Parameterwerte für Trackwahl, Kategorie, Fade, Gain oder Layer.
2. **Quelle vor Ziel:** Bei jeder Vorlagenauflösung aktuelle Source-/Bibliotheks-/Owner-/Campaign-/Role-/Asset-/Medien-/Lizenz-/Geheimnisberechtigung zuerst validieren; Zielkampagne, Zielmusikfähigkeit, Target-Create-/Copy-/Reference-ACL und gewählte gepinnte Quellrevision zusätzlich. Unautorisierte Source-IDs dürfen weder Templateexistenz, Assetmenge, Titel, geänderte Liste, Warnung noch versteckte Fehlersignale verraten.
3. **Feste Übernahme atomar:** Server plant nur die **unveränderten zulässigen Werte** der gewählten Revision; bevor eine neue Zielkonfiguration publiziert wird, referentielle Integrität/unterstützte Cue-/Track-/Layer-/Loop-Werte und Zielmusik-/Lizenzrechte prüfen. Bei unzulässigen Einträgen nicht auf einen geheimen Ersatzwert zurückfallen; kontrollierter sicherer Abbruch oder ausschließlich bereits autorisierter Redaktionspfad. CAS-/Idempotenz-/Quota-/Transaktionsschutz gegen Duplikat, veraltete Vorlagenrevision und gleichzeitige Zielbearbeitung.
4. **Post-Insert-Edit separat:** Nach erfolgreichem Commit nur durch berechtigten Target-Editor mit eigener **neuer** Change-Operation, revalidiertem Asset-/Targetscope, eigener erwarteter Revision und unabhängigem Audit- und Konfliktpfad. Keine „Insert + Edit“ als ein einziger stiller parametrischer Submit – selbst wenn eine spätere UI beides bequem nacheinander navigiert.
5. **Referenzen, Kopien und Updates:** Quelle bleibt Owner-gesteuert. Eigenständige Kopie erhält neue Ziel-IDs und editierbare eigene zulässige Felder; nicht im Besitz befindliche Referenz wird durch Zielnavigation nicht verändert. 02.136-C-Source/Base/Target-Diff und ausdrückliche Zustimmung bleibt ein separater Versionsupdatevorgang. Keine unkontrollierte permanente Quell→Zielsynchronisierung.
6. **Audio-Laufzeit vollständig unabhängig:** Vorlagen-Auswahl/Reference/Copy/Target-Edit ist kein Musik-Play-/Cue-/AutoJoin-Event. Erst 02.132-autorisiertes Cueangebot und lokale 02.133-A-Wiedergabe mit persönlicher Volume/Mute/Browserentscheidung kann später tatsächlich abspielen, 02.134-Mix nur nach eigener Capability. Keine World-/SoundEvent-/ACK-Wirkung.
7. **Negativer UI-/API-Vertrag:** Es soll keinen spezifischen Audio-Template-Insert-Wizard, Parameterdefinitionen des Templateautors, dynamischen Feldauswahldialog oder über URL/API/Clientflags erlaubten Insert-Override geben. Die exakte gewöhnliche Auswahl-/Kopier-/Referenzierungsoberfläche wird später entworfen; keine UI-MVP-Priorisierung heute.
8. **Sicherheit und Ressourcen:** Quoten/Rate-/Request-/Media-/Path-/SSRF-/Malformed-Payloadschutz, per-Kampagne/Owner/Nutzer isolierte Revisions- und Mediencaches, User-/Policy-/Scenewechsel-Invalidierung, ungültige Referenzketten und doppelte Requests. Kein Spezialparameterpfad, der ansonsten verbotene Daten erst bei Fehler oder Preview verrät.

## 5. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| SL fügt rechtmäßig freigegebene Taverne-Playlist als Kopie ein | Zulässige gespeicherte Track-/Cue-/Loop-/Fade-/Layer-Einstellungen, neue Ziel-IDs; **kein** Insert-Parameterdialog |
| Vorlage hat gespeicherte Reihenfolge A–B–C | Zulässige Zielplaylist übernimmt Reihenfolge A–B–C; kein per-Insert-Umsortieren |
| Vorlagenautor wünscht ein Feld „Regen beim Einfügen?“ | Kein eigener definierbarer Audio-Template-Insertparameter; späterer Ziel-Edit getrennt |
| Spieler sendet manipulierte `insertOverrides`-Payload | Kein Parameter-Override über API/Client/URL/Node oder stille Verarbeitung |
| Kampagne erlaubt Audio-Crossfades nach 02.134 C | Beim Einfügen nur gespeicherte rechtmäßige Crossfadevorgabe, keine freie Dauerwahl in Inserteingabe |
| Lokale Mixfunktion in Ziel verboten | Kein Kopieren unzulässiger aktiver Layerfunktion gegen Zielpolicy; sicher ablehnen/auslassen nach eigens zulässigem bestehenden Redaktionsweg |
| Musik 02.132 C ist Aus | Keine aktive Audio-Template-Anwendung oder neue Playlist-/Cueaktion; Chat/Würfel/Schall unabhängig |
| Musik An, Chat 02.105 Aus | Erlaubte Audio-Template-Kopie ohne Chatzwang; keine Voice-Memo-Aufnahme |
| SL besitzt Ziel-Copy-Recht, aber kein Quell-Leserecht | Keine fremde Playlist-/Track-/Vorlagen-Vorschau oder Kopie |
| Source-Template darf gelesen, nicht kopiert werden | Referenz nur soweit separat erlaubt, keine unberechtigte Zielkopie |
| Quelle ist auf Revision v4 gepinnt, v5 existiert | Kein „latest“-Einfügeoverride und keine heimliche Auswahl von v5 |
| Source-Release v5 ist vorhanden, berechtigter Updater möchte Änderungen | Separater geschützter 02.136-C-Diff-/Zustimmungspfad, nicht Insertparametereingabe |
| Quellasset oder Musiklizenz nach Freigabe abgelaufen | Kein neuer Mediaabruf durch ehemals erlaubtes Template; sicherer Ablehnungs-/Redaktionspfad |
| Template enthält geheime SL-Playlist | Kein Titel-/Track-/Count-/Cover-/Datei-/URL-/Fehlermetadatenleck an unberechtigte Zielrolle |
| Zulässige Kopie wurde erzeugt, Nutzer darf nur ansehen | Keine nachträgliche Bearbeitung ohne echte Target-Edit-ACL |
| Zieleditor darf nach Kopieren Trackreihenfolge verändern | Erst separate berechtigte Zielrevision; Originalvorlage unverändert |
| Nutzer hat eine read-only Quellreferenz und versucht „Edit Ziel“ | Kein Edit der fremden Source; explizites Copyrecht und eigene Zielkonfiguration ggf. nötig |
| Berechtigter Source-Owner editiert Originalvorlage | Eigener rechtmäßiger Source-Edit-/Revisionspfad, nicht Target-Insert |
| Nutzer besitzt persönliche Musiklautstärkepräferenz | Eigener Volume-/Mutezustand durch Template-Insert unverändert |
| Spieler verweigert Browser-Autoplay | Übernahme startet keine Musik und übergeht keine Usergesture |
| Importierte Vorlage mit erlaubten lokalen Loops | Keine globale Playhead-/Track-/Fade-Uhr, Track später lokal bei 0 |
| Late Join nach Audio-Template-Einsatz | Kein AutoJoin-/Reconnect-Catch-up nach 02.133 A |
| SL fügt Vorlage mit Alarm-Soundboard ein | Kein Schallwellen-/Game-SoundEvent-/Sensor-/Alarm-/Node-/Tür-/NPC-Effekt |
| Vorlage heißt `Quest erledigt` | Kein 02.99-Quest-/Würfel-/Inventar-/Turn-Worldcommit |
| Server erhält doppelte Insertoperation nach Netzfehler | Idempotenz und Zielrevision verhindern doppelte Playlist-/Cue-Instanzen |
| Zwei Zielverwalter legen zeitgleich Audio-Konfiguration an | Eindeutige IDs und echte Create-/Target-/Revisionprüfung, keine Phantomduplikate |
| Quellrevision verändert sich zwischen Preview und Apply | Recheck/konfliktfreier sicherer Abbruch, keine unbemerkte Werteänderung |
| Ziel-Rollen-/Gruppenrechte werden vor Commit entzogen | Operation wird verweigert; keine alten berechtigten Audioassets im neuen Ziel |
| Quellplayer spielt Track, Ziel kopiert Vorlagenkonfiguration | Keine Übernahme des laufenden Source-Playheads oder Mastervolumes |
| Kopierter Track fehlt im Ziel aus lizenzrechtlichen Gründen | Keine automatische unzulässige Media-/Provider-/Streaming-/DRM-Freigabe |
| Vorlagennamen enthalten HTML/Script/PathTraversal | Nur gesicherte Metadaten, keine Codeausführung oder Dateipfadumgehung |
| Versteckte Szenenplaylist aus fremder Kampagne über erratene ID | Kein Existenz-/Count-/Name-/Trackzugriff über Insert/Cache/Search |
| 02.89 C parametrisierte Karten-/Szenenvorlage wird eingefügt | Deren eigener zuvor gewählter Parameterdialog darf weiterbestehen; kein Übertrag auf Audio-Vorlagen |
| Vorlagenbezug vor Quelllöschung erlaubt, danach entzogen | Neue abhängige Referenz-/Media-Abrufe gesperrt; rechtmäßig eigenständige Kopie nur nach eigenen Rechten |
| SL bestätigt spätere manuelle Zielbearbeitung | Kein 02.102-amtliches ACK, keine automatische Musik-/Quest-/Nodeaktion |
| Zwei lokale Soundboardplayer spielen dieselbe erlaubte Vorlage | Independent 02.133-A-Playheads und 02.134-C-Layer, kein globaler Sync |
| Nutzer wünscht Sondermodus „Insert plus Track austauschen“ | Kein einziger verdeckter Insertparameter-Commit; erst regulär einfügen, danach separat prüfen/bearbeiten |
| Automatische Cue-Auswahl gemäß 02.132 C | Nur erlaubter späterer Cuepfad, keine stillen „Template-Insertparameter“ |
| Komplette Zielkampagne deaktiviert Musik im laufenden Betrieb | Kein neu nutzbarer Audiovorlagen-/Media-/Playbackpfad; unabhängige Systeme bleiben |

## 6. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.137 A – Audio-Playlist-/Soundboardvorlagen werden ohne besondere parametrisierbare Einfügefelder ausschließlich mit gespeicherten, im Ziel tatsächlich berechtigten Werten referenziert/kopiert; Veränderungen erst nach der Übernahme durch separat autorisierte normale Zielbearbeitung.** Kein 02.25-Ausnahmeschalter für abgewählte Audio-Insert-Overrides. Fortgeltend: 02.132 C schaltbares Musikmodul/Actor-/Asset-/Lizenz-/Empfängerrechte; 02.133 A ausschließlich lokale Wiedergabe ab Titelbeginn, ohne Sync oder AutoJoin; 02.134 C konfigurierbare lokale Loops/Fades/Layers; 02.135 C geschützte Template-Referenz oder erlaubte Konfigurationskopie; 02.136 C bewusst bestätigte Source-/Base-/Target-Vorlagenupdates. **02.89 C parametrisiert weiterhin nur die gesonderten Karten-/Szenenvorlagen**, kein Widerspruch. Keine echte 02.49–02.51-Schall-/Sensor-/Nodewelt, kein 02.99-NPC-/Quest-/Door-/Würfel-/Turn-/Inventareffekt, kein 02.102-ACK.

**Nicht beschlossen:** finale Bibliotheks-/Editor-/Wiedergabe-UI, genaue Konflikt-/Redaktionsdialoge, API/DB-/Medien-/Providerdetails, Aufbewahrung/MVP; spätere **reguläre** Zielbearbeitung und von 02.136 C unabhängig kontrollierte Versionsupdates bleiben planbar. Kein fertiger Code.

## Nächste Entscheidung 02.138 – Soundboard-Cues priorisieren und Hintergrundmusik lokal absenken

**Beispiel:** In einer Sitzung läuft erlaubte Tavernenmusik lokal. Eine autorisierte SL löst einen kurzen Glockenton aus. Damit dieser gut hörbar ist, könnte der lokale Player die **eigene** Hintergrundmusik kurz absenken und anschließend sanft auf den eigenen Pegel zurückführen – ohne anderen Spielern die Lautstärke zu ändern und ohne Voicechat-Aufnahme.

- **A – Kein automatisches Ducking:** Ein Musik- oder Soundboard-Cue verändert keine Lautstärke einer anderen Audiolage automatisch. Jeder regelt ausschließlich die eigene Musik- und Effektlautstärke; 02.134 C erlaubt weiterhin Layer und Fades, aber kein zusätzliches Prioritäts-/Ducking-System.
- **B – Alle Cues erzwingen fremde Lautstärken:** Jeder Soundboardeffekt senkt alle Spieler-/System-/Voice-Lautstärken automatisch ab oder übersteuert ihre persönliche Stummschaltung, ungeachtet von Berechtigung, Browser-/Audio-/Geheimnisrechten.
- **C – Berechtigtes lokales Cue-Prioritäts-/Ducking-Modul (Empfehlung):** Bei aktivem 02.132-C-Musikmodul darf die SL nach 02.25-Policy getrennt erlauben, dass **ein tatsächlich autorisierter Soundboard-Cue auf dem jeweiligen eigenen Gerät** für eine begrenzte Zeit nur passende eigene Musik-/Ambient-Layer absenkt und danach bis zum gewählten lokalen Wert zurückführt. Persönliches Volume/Mute/Browserentscheidung bleiben unangetastet, keine Erfassung externer Voicechat-Audiopegel, kein gemeinsamer 02.133-A-Musik-Sync und keine 02.49–02.51-Schall-/Sensor-/Node-/Welt-/ACK-Wirkung. Konkrete Kurven, Prioritäten und UI später.
