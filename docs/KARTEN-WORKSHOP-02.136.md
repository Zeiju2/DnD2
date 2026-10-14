# AdventureShift – Karten-Workshop: Beschluss 02.136 C – kontrollierte Versionsübernahme bei Audio-Playlist- und Soundboardvorlagen

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.136; nächste offene Entscheidung 02.137.
**Status:** Verbindlicher Fachbeschluss, konzeptionelle Umsetzung und fachliche Abnahmetests; **noch keine Softwareimplementierung**, keine endgültigen APIs, Datenbankschemata, UI oder MVP-Einstufung.
**Bezüge:** [02.25 – Kampagnenstandards und markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.85–02.88 – gesicherte Szenenvorlagen, Revisionen und kontrollierte Übernahme](KARTEN-WORKSHOP-02.88.md) · [02.99 – echte berechtigte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – amtliche Korrekturhinweise/ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – optionaler Chat](KARTEN-WORKSHOP-02.105.md) · [02.122 A – keine Chat-Sprachnachrichten](KARTEN-WORKSHOP-02.122.md) · [02.132 C – eigenständige Musik/Playlists/Soundboard](KARTEN-WORKSHOP-02.132.md) · [02.133 A – nur lokale Wiedergabe, kein Musik-Sync](KARTEN-WORKSHOP-02.133.md) · [02.134 C – lokale Loops/Fades/Audio-Layer](KARTEN-WORKSHOP-02.134.md) · [02.135 C – freigegebene Audio-Playlist-/Soundboardvorlagen über Kampagnen](KARTEN-WORKSHOP-02.135.md) · [Dateien, Medien und Lizenzstrategie](LIZENZEN.md).

## 1. Verbindliche Entscheidung – Variante 02.136 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Wird eine gemäß **02.135 C rechtmäßig referenzierte oder kopierte Audio-Playlist-/Soundboardvorlage** in einer neuen **Quellrevision** freigegeben, darf eine dazu tatsächlich berechtigte Zielverwaltung unter **02.25-Kampagnen-/Bibliotheks-/Rollen-/Gruppen-/Personenstandards und gültigen markierten Ausnahmen** diese Änderung **erkennen, geschützt vergleichen, ignorieren, als neue eigene Zielkonfiguration übernehmen oder nach bewusster individueller Freigabe geeignete Änderungen auf eine bestehende Zielkonfiguration anwenden**. Lokale Abweichungen, gesperrte Medien, Zielrechte und konkurrierende Bearbeitungen sind vor jeder Übernahme zu prüfen. **Keine automatische Massenaktualisierung, kein stilles Überschreiben und keine fremde Playlistfernsteuerung.**

**Beispiel:** Die SL aktualisiert die Quellvorlage „Taverne“ von v3 auf v4 und ergänzt einen Regen-Cue. Kampagne B nutzt eine eigene Kopie von v3 mit anderer Trackreihenfolge. Die berechtigte SL von B kann eine erlaubte Vorschau der Änderungen sehen und den Regen-Cue gezielt übernehmen oder v4 als eigenständige neue Kopie speichern. B verliert die eigene Reihenfolge nicht durch bloßes Veröffentlichen von v4; ein geheim gebliebener Track der Quellkampagne erscheint auch nicht in einer Vergleichszählung oder als aufrufbarer Link.

**Nicht gewählt:** A (nur manuell vollständig neue Vorlagen ohne kontrollierte Versionsbeziehung) und B (jede Quellrevision überschreibt weltweit alle Referenzen/Kopien und laufenden Cues automatisch). **C ist keine allgemeine Realtime-/Cloud-Synchronisation, kein automatischer Medien-/Lizenztransfer und keine Aktivierung einer gemeinsamen Musikuhr aus 02.133 A.**

## 2. Fachlicher Versions- und Rechtevertrag

1. **Harte Funktionsvoraussetzungen:** Wirksames **02.132-C-Musik An**, zulässige 02.135-C-Vorlagenverwendung, geeignete 02.25-Updateunterfähigkeit und je Vorgang gültige Quelle-/Ziel-/Vorlagen-/Benutzer-/Medienrechte. Musik Aus stoppt neue Audio-Vorlagen-Anwenden-/Musikoperationen; optionaler Chat und echte Spielweltfunktionen bleiben unabhängig. Sicherheits-/ACL-Prüfungen sind nie abschaltbar.
2. **Quelle und Version:** Nur eine **bewusst gespeicherte, autorisierte neue Quellvorlagenrevision** ist updatefähig; Quellautor-/Bibliotheksrechte, echte Revision und zulässige Audio-Konfigurationsdaten müssen stimmen. Bearbeiten einer Quellvorlage verpflichtet keine Zielkampagne zu etwas.
3. **Abhängigkeitsbindung:** Referenzierte und kopierte Vorlagen können – sofern bei Anlage zulässig erfasst – eine **Version-/Herkunftsbindung** an eine rechtmäßig verwendete Quellrevision haben. Ein solches Bindungsmetadatum verrät dem aktuellen Zielnutzer **keine** geheim gewordenen Quellinformationen, wenn das heutige Quellrecht fehlt.
4. **Prüfung vor Änderungsanzeige:** Für Versionshinweis, Quelle, Tracktitel, Cover, Assetref, Playlist-/Soundboard-Tags, Audio-Cue, Anzahl geänderter Einträge und eventuelle Quellkampagnendetails braucht der konkrete Viewer jeweils echtes **aktuelles** Besitzer-/Quell-/Ziel-/Bibliotheks-/Vorlagen-/Audioasset-/Lizenz-/Geheimnis-/Empfängerrecht. Historische frühere Freigabe ist **keine** automatische heutige Leseberechtigung.
5. **Versionsabgleich statt Blindüberschreiben:** Konzeptionell **Basisrevision (früher erlaubte verwendete Quelle)**, **neue autorisierte Quellrevision** und **aktuelle lokale Zielrevision** vergleichen. Unterschiede kategorisieren: neu/hinzugefügt, geändert, verschoben, umbenannt, lokal angepasst, gelöscht, medienrechtlich nicht mehr zulässig, Zielpolicy inkompatibel. Nur tatsächlich erlaubte Felder und Werte werden angezeigt; kein Geheimtrack-/Datei-/Sender-/Count-Schattenhinweis im Diff.
6. **Getrennte Nutzerentscheidungen:** Berechtigte Zielakteure dürfen nach Policy **ignorieren/später prüfen**, eine **neue unabhängige Vorlage/Kopie** mit eigenen IDs anlegen oder nach Feld-/Cue-/Playlistkonfliktprüfung **einzeln freigegebene** passende Änderungen in der bestehenden Zieldefinition übernehmen. Nicht zulässige Felder werden sicher ausgelassen oder führen zu einem begründeten kontrollierten Abbruch – nicht zu einer heimlichen Rechteerweiterung.
7. **Referenz gegenüber unabhängiger Kopie:** Eine referenzierte Zieldefinition darf **nicht unbemerkt** „immer neueste Quelle“ abspielen. Eine freigegebene Version wird als **geprüft gepinnte erlaubte Revision** oder nach ausdrücklicher Aktualisierung auf eine neue erlaubte Revision bezogen. Eine eigenständige Kopie behält **eigenen** Bearbeitungs-/Revisions-/Herkunftsstand; ein späterer Quellrelease überschreibt ihren Text, ihre Cue-Reihenfolge und ihre lokalen Audio-Parameter nicht.
8. **Löschungen/Rechteentzug:** Ein im Quellrelease entfernter Track wird **nicht automatisch aus einer unabhängigen berechtigten Zielkopie entfernt**. Ein wirklich widerrufenes Medien-/Lizenz-/Quellrecht wird dennoch vor **neuer Audioverwendung** strikt geprüft und darf nicht mit „altes Ziel“ umgangen werden. Im Updatevergleich keine behauptete garantierte physische Löschung bereits rechtmäßig auf einem Gerät gehörter Daten.
9. **Keine stillen laufenden Soundänderungen:** Die neue Vorlagenrevision, ihre bloße Erkennung und eine Diffvorschau ändern **keinen bereits laufenden lokalen Player, Cue, Crossfade oder Loop**. Eine autorisierte spätere Übernahme aktualisiert höchstens die verwaltete Zielkonfiguration; tatsächliche neue Playbackaktionen benötigen weiterhin explizite 02.132-C- und 02.133-A-/02.134-C-Rechte. Abgelaufene echte Asset-/Geheimnisrechte sind separat zu beenden, auch wenn noch kein Vorlagenupdate angenommen wurde.
10. **Quell-/Zielversion und Zustimmung:** Preview/Antrag/Genehmigung/Commit sind verschiedene Schritte; tatsächlicher Updatecommit verlangt einen **aktuellen, unveränderten** Zielbasisstand, wirksame Quellfreigabe und aktuelle Versions-/Rechteprüfung (optimistische Konkurrenzkontrolle, CAS/Idempotenz). Verzögerte SL-Freigabe nach Scene-/Rollen-/Lizenz-/Zielrevisionwechsel darf nicht ungeprüft noch einen Cue/Track veröffentlichen.

## 3. Unverändert gültige bestehende Fachbeschlüsse

| Vorherige Entscheidung | Unveränderliche Grenze |
| --- | --- |
| **02.25 / 02.132 C** | Musikmodul und Updatefähigkeit müssen tatsächlich erlaubt sein; SL-/Personen-/Kampagnenausnahme ersetzt keine Quell-/Lizenzberechtigung |
| **02.135 C – Referenz/Kopie** | Quell-/Ziel-/Owner-/Template-Read-/Copy-/Reuse-/Asset-/Lizenz-/Secretrechte getrennt; keine automatische Binärmedien-/Streaminglizenzkopie |
| **02.133 A – kein gemeinsamer Playhead** | Keine globale Start-/Pause-/Seekposition, kein Musiktiming-Sync, kein AutoJoin/AutoReconnect-/Cue-Catch-up durch Versionsupdate |
| **02.134 C – nur lokale Fades/Loops/Layers** | Neue lokale Mixvoreinstellungen nur bei gültiger Ziel-Capability und aktuellem Audioasset; kein globaler Fade- oder Layer-Zwang |
| **02.85–02.88 Vorlagenprinzip** | Versionierte sichere Diff-/Conflict-Methodik als Analogie, **nicht** als automatische Szenen- oder Audioassetmigration |
| **02.49–02.51 Szenenakustik** | Vorlage „Alarm“ oder „Schuss“ löst weder echten SoundEvent noch Alarm-/Sensor-/Node-/Licht-/Türprozess aus |
| **02.99 Weltaktionen** | Freigabe einer Audio-Templateversion ändert keine NPC-/Quest-/Inventar-/Door-/Würfel-/Turnaktion |
| **02.101–02.104 amtliche ACKs** | „Neue Playlistversion geprüft/übernommen“ ist **keine** persönliche amtliche 02.102-Kenntnisnahmequittung |
| **02.105 Chat / 02.122 A Voice-Memos** | Eigenständige Musikvorlagen brauchen keinen Chat und eröffnen keine Chat-Sprachnachrichten-/Mikrofon-/Transkriptionsfunktion |
| **Allgemeiner Asset-/Lizenzworkshop 12** | Keine ungefragte neue Import-/Exportpaket-, Streamingprovider-, DRM- oder Quellserver-Synchronisationsentscheidung |

## 4. Konzeptioneller Lebenszyklus und sichere Umsetzung

1. **Fachliche Modelle nur als Entwurf:** `AudioTemplateSourceRevision`, `AudioTemplateTargetBaseRevision`, `AudioTemplateTargetLocalRevision`, `AudioTemplateUpdateCandidate`, `AudioTemplateAuthorizedDiff`, `AudioTemplateMergeConflict`, `AudioTemplateUpdateDecision`, `AudioTemplateUpdateOperationId`, `AudioTemplateUpdateAudit`. Keine fertigen Tabellen-/API-Namen.
2. **Neuer Source-Release:** Eindeutige, autorisierte Quellrevision committen, historische Version unter eigener Retention halten. Zugriffsberechtigte Zielvorlagen können über eigene gültige Referenzbindung ein **mögliches Update** erkennen, ohne automatisch zu kopieren oder an alle Kampagnen zu broadcasten.
3. **Diff in erlaubter Projektion:** Server bestimmt für den tatsächlichen Viewer/Target nur die **jetzt autorisierten** Source-/Base-/Local-/Asset-/Lizenz-/Secret-Felder und Versionen. Fehlende Rechte/Retention/Inkompatibilität führen nicht zum Offenlegen verborgener Tracklisten via Counts, Sortierung, Änderungsnamen, Medien-URLs oder generischen Fehlercodes.
4. **Selektive Updateentscheidung:** Einzeln geeignete neue/geänderte Cue-/Track-/Kategorie-/02.134-Loop-/Fade-/Layerparameter zur Übernahme markieren; lokale Zieländerungen werden nicht still verworfen. Unvereinbare Revisionen müssen offen als **berechtigt beschreibbarer** Konflikt, sicherer Abbruch, neue unabhängige Kopie oder explizit bestätigter zulässiger Merge behandelt werden.
5. **Commit atomar und versionsfest:** Nur echte aktuell berechtigte Zielverwaltung darf einen Update-Commit auslösen. Quell-/Basis-/Ziel-/Policy-/Lizenz-/Assetrevision und Operation-ID prüfen; eindeutige neue Zielrevisionsbelege, keine halben Playlist-/Cue-Updates, kein doppelter Commit nach Retry/Reconnect oder parallelem SL-Eingriff. Bei Rollback keine historische Eventlöschung, sondern später gegebenenfalls neue kontrollierte Konfigurationsrevision.
6. **Quell- und Target-Revocation:** Wenn Quellfreigabe oder Asset-/Lizenz-/Empfängerrecht entzogen wird, dürfen Referenzbetrieb, neue Quellversionshinweise, Preview und Updatekopien nicht unberechtigt fortfahren. Eigenständige früher rechtmäßig und weiterhin gültig lizenzierte lokale Kopien werden nicht allein wegen einer fremden Quellversionsmeldung entfernt; jede Mediennutzung wird dennoch neu autorisiert.
7. **Laufende Sitzung bleibt unangetastet:** Updateauswahl/Preview/Commit überträgt **keinen** aktuellen Playbackplayhead, erzeugt keinen globalen Track-/Cue-/Seek-Zwang, triggert kein bereits laufendes Hörereignis neu. Berechtigter Anwender kann später bewusst einen neuen lokalen Audiostart bei 0 auslösen; persönliche Volume-/Mute-/Browserautonomie bleibt.
8. **Rechte-/Performance-/Abusegrenzen:** Rate-/Quota-/Diffgrößen-/Revisionstiefen-/Merge-Konflikt-/Reference-Chain-/Path-/SSRF-/Datei-/MIME-/Medien-/Cache-/Indexgrenzen. Eindeutig getrennte Quell-/Zielkampagnen; keine versteckten anderen Installationen/Marktplatzlisten oder automatischen Cloudpushes.

## 5. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| Musikmodul 02.132 C bei Kampagnenerstellung Aus | Kein aktiver Audio-Vorlagenupdate-/Preview-/Applypfad; unabhängiger Chat/Würfel/System-/02.51-Schall unverändert |
| Quelle v4 erscheint, Zielreferenz hält geprüfte v3 | Keine automatische Umstellung auf v4; berechtigter Zielakteur kann die neue Version nach echter Quellfreigabe prüfen |
| Berechtigte SL von B hat kopierte v3 mit eigener Trackreihenfolge | Diff erkennt lokale Abweichung und überschreibt Reihenfolge nicht still |
| Quelldatei v4 enthält neuen zulässigen Regen-Cue | Nur nach aktuellem Quelle-/Ziel-/Assetrecht optional als neue Konfigurationsänderung anbieten |
| Quelle v4 enthält neuen **geheimen** SL-Track | Nicht Berechtigte sehen weder Existenz, Titel, Count, URL, Diff-Hinweis noch Albumcover |
| SL verwaltet Ziel, hat aber kein Quellvorlagen-Leserecht | Keine Diff-/Update-/Titel-/Versionsdetails fremder Source |
| Früheres Source-Leserecht vor Update widerrufen | Kein neuer Source-Release-/Patch-/Preview-/Index-/Cache-Zugriff |
| Nur Zielkopie bearbeitbar, kein Vorlagenupdate-Recht | Normale eigene Bearbeitung bleibt; geschützte Import-/Mergeaktion unzulässig |
| Neue Version mit abgelaufener Musiklizenz | Kein erlaubter Track-/Stream-/Cue-Nutzungsgrant durch Vorlagenmerge |
| Neu hinzugefügter Track im Zielrollenscope verboten | Geheime Referenz wird sicher ausgelassen bzw. kontrolliert abgelehnt, keine Medienvorschau |
| Quellrelease benennt Playlist um, Ziel hatte selbst anderen Namen | Sicherer Konflikt/ausdrückliche Entscheidung, kein heimlicher Ziel-Rename |
| Quelle v4 löscht Track, Zielkopie hat eigenes gültiges Medienrecht | Zielkopie nicht durch Sourceupdate pauschal gelöscht, echte Lizenzrechte aber unabhängig erneut geprüft |
| Referenzierte Sourcevorlage wird komplett gelöscht | Keine Nutzung der nicht mehr erlaubten Source-Referenz; kein Shadowarchiv neuer Source-Versionen |
| Nutzer wählt „Ignorieren“ | Keine Änderung der Zieldefinition, kein neuer Musik-/Cue-/Worldevent |
| Nutzer wählt „Später prüfen“ | Ziel bleibt unverändert, keine implizite Zustimmung oder Quittierung |
| Nutzer wählt „Neue Kopie erstellen“ | Neue Ziel-ID, eigene Revision/Herkunft und erneute Asset-/Lizenz-/ACL-Prüfung |
| Nutzer übernimmt ausschließlich einen berechtigten Cue | Nur erlaubter Teil der Konfiguration als neue Zielrevision, andere lokale Änderungen bleiben |
| Update-Aktion trifft nach weiterem Ziel-Edit ein | CAS/Versionscheck verwirft stale Aktion, neuer Diff/ausdrücklicher Konfliktweg |
| Source-Revision oder Grant ändert sich nach Preview | Commit verweigert veraltete Annahme, aktuelle Source-/ACL-Prüfung erforderlich |
| SL-/Role-/Scene-/Policyrechte ändern sich vor Approval | Keine automatische nachträgliche Freigabe oder Updatekopie |
| Zwei berechtigte Personen committen denselben Patch | Idempotenz und Revisionssperre verhindern doppelte Titel-/Cue-Einträge |
| Update wird bei mehreren Zielkampagnen angeboten | Jede Zielkampagne separat autorisiert, keine globale Massenüberschreibung |
| Zielkampagne läuft während Updatevorschau mit Soundboard | Keine Wiedergabe-/Loop-/Crossfade-/Trackpositionsänderung durch Vorschau |
| Übernommene Zielkonfiguration erhält neue Trackreihenfolge | Keine automatische Audio-Wiedergabe oder Session-Sync daraus |
| Spieler tritt später bei | Kein LateJoin-/Reconnect-Playback-Catch-up nach 02.133 A |
| Auto-Cue-Regel im Ziel ist deaktiviert | Update schaltet sie nicht heimlich ein oder triggert Spielaktionen |
| Vorlage ändert 02.134-C-Crossfadeparameter | Nur bei gültiger Ziel-Fade-/Mix-Capability übernommen, rein lokal beim späteren eigenen Start |
| Browser blockiert Autoplay oder Spieler hat Audio stumm | Versionsupdate kann weder Player/Mute noch Browserautoplay übergehen |
| Vorlagenname lautet `Alarm` oder `Tür öffnen` | Kein 02.49–02.51-Schall-/Sensor-/Node-/Tür-/NPC-/Quest-/Turn-Effekt |
| Kampagne nutzt Chat Aus, Musik An | Vorlagenupdate gemäß Audio-/Zielrechten möglich ohne Chatmodul |
| Quelle enthält fremde Audio-Datei-URL oder `../`-Pfad | Kein SSRF-/Datei-/Pfad-/Streaming-/DRM-Recht durch Update |
| 02.102-Korrekturmeldung wartet auf bewusste ACK | Übernehmen/Ablehnen/Prüfen der Musikvorlage erzeugt kein amtliches ACK |
| Update benötigt nicht unterstütztes Audioformat | Kein stilles Dekodier- oder Provider-Versprechen; kontrollierter nicht anwendbarer Diffteil |
| Reconnect wiederholt bereits bestätigte Updateoperation | Kein zweiter Versions-/Asset-/Cue-Commit |
| Andere Kampagne hat dieselbe Vorlage lokal verändert | Keine Übernahme/Offenlegung anderer Kampagnen-Diff-/Hörer-/Vorlagen-Daten |
| Externe Installation besitzt zufällig gleiche Template-ID | Kein ungeregelter Remote-/Cross-Server-Updatekanal; allgemeine Paketübernahme bleibt Bereich 12 |
| Sehr große/zyklische Vorlagenabhängigkeit wird aktualisiert | Quota-/Tiefe-/Cycle-/Rate-/Idempotenzschutz; kein Auslösen endloser Cues |
| Quelle wird nach berechtigter Zielkopie gelöscht | Rechtmäßig unabhängige Zieldefinition bleibt nur im Rahmen **eigener** Rechte; keine neue Quellmedienberechtigung |
| SL versucht automatische „Update all, overwrite local“ Funktion | Ohne eigenständige erlaubte individuelle Zustimmungen kein solcher unberechtigter Massenpfad |

## 6. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.136 C – versionierte, nach aktuell echten Rechten gefilterte und bewusst bestätigte Übernahme von Änderungen an 02.135-C-Audio-Playlist-/Soundboardvorlagen.** Quell-/Basis-/Zielrevision und echte heutige Owner-/Kampagnen-/Template-/Medien-/Lizenz-/Secret-/Empfänger-/Rollenrechte sind vor Vergleich und atomarem Commit zu prüfen. Zielakteure dürfen geeignete Updates ignorieren, später prüfen, als neue Kopie übernehmen oder nach bewusster Konfliktbehandlung ausgewählte Änderungen in eine vorhandene Zieldefinition überführen. **Keine automatischen Quellenänderungen in Zielkampagnen oder laufenden Audiospuren.** 02.132 C schaltbares unabhängiges Musikmodul, 02.133 A ohne globalen Sync/AutoJoin und 02.134 C ausschließlich lokales optionales Mixing bleiben; keine 02.49–02.51-Schall-/Node-/Sensorwelt, 02.99-Weltwirkung oder 02.102-ACK-Ersatz.

**Nicht beschlossen:** konkrete Meldungsoberfläche/Notificationintervalle, Mergealgorithmus, Aufbewahrungsfristen alter Vorlagenrevisionen, konkrete Diff-UI, Import-/Exportformate, finale Lizenz-/Medienprovider, APIs/DB/MVP. Die 02.85–02.88-Vorlagenmechanik ist ein Architekturvorbild, **kein** automatischer Cross-Campaign-/Cross-Installation-Source-Push.

## Nächste Entscheidung 02.137 – Audio-Playlist- und Soundboardvorlagen beim Einsatz parametrisieren

**Beispiel:** Eine SL möchte dieselbe freigegebene Taverne-Soundboardvorlage einmal mit Regen und schwacher Hintergrundmusik, einmal mit anderer erlaubter Reihenfolge und stärkerer Musik einsetzen, ohne dafür viele separate feste Vorlagen anzulegen. Die Werte sollen nichts Geheimes freigeben oder eine globale Wiedergabeposition erzwingen.

- **A – Nur feste Vorlagenkonfiguration:** Audio-Vorlagen werden genau mit den gespeicherten zulässigen Parametern eingefügt; Änderungen erfolgen erst als eigene manuelle Zielbearbeitung, kein besonderer Parameterdialog beim Einfügen.
- **B – Beliebige ungeprüfte Audio- und Weltparameter:** Jeder Anwender darf Audioasset-IDs, private Streamingquellen, Lautstärken fremder Hörer, versteckte Szenen-/Node-/Alarmzustände und globale Playback-Positionen ohne Rechte-/Typprüfung überschreiben.
- **C – Berechtigte typisierte lokale Audio-Vorlagenparameter (Empfehlung):** Bei erlaubter 02.132-/02.135-Musik-/Vorlagenfähigkeit kann der Vorlagenautor nach 02.25-Policy **benannte, typisierte und begrenzte** erlaubte Parameter für Trackauswahl aus zugelassenen Assets, lokale Loop-/Fade-/Layer-Voreinstellungen und Kategorien vorsehen. Die SL/Zielrolle kann sie beim berechtigten Einsetzen ausdrücklich wählen. Server prüft Typen, Werte, Quell-/Lizenz-/Empfänger-/Szenenrechte und aktuelle Revision vor Commit. Keine gemeinsame 02.133-A-Musikuhr, keine fremde Masterlautstärke, kein 02.49–02.51-Schall-/Node-/Welt-/ACK-Effekt; UI/MVP später.
