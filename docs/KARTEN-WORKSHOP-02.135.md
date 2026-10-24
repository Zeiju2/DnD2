# AdventureShift – Karten-Workshop: Beschluss 02.135 C – berechtigte kampagnenübergreifende Audio-Playlist- und Soundboardvorlagen

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.135; nächste offene Frage 02.136.
**Status:** Verbindlicher Fachbeschluss mit konzeptionellem Umsetzungs-/Abnahmetestplan; **noch keine Softwareimplementierung**, kein finales UI, keine abschließenden DB-/API-Verträge und keine MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnenstandards und gültige markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.85–02.88 – gesicherte Vorlagenbibliothek, Berechtigungen, Pakete und kontrollierte Updates](KARTEN-WORKSHOP-02.88.md) · [02.87 – Export/Import von Szenenvorlagen](KARTEN-WORKSHOP-02.87.md) · [02.49–02.51 – Schall-/Sensor-/Nodewelt](KARTEN-WORKSHOP.md) · [02.99 – echte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – amtliche Hinweise/ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – optionaler Chat](KARTEN-WORKSHOP-02.105.md) · [02.114 – gesicherte Medien](KARTEN-WORKSHOP-02.114.md) · [02.122 A – keine Chat-Voice-Memos](KARTEN-WORKSHOP-02.122.md) · [02.132 C – optionales Sessionmusik-/Playlist-/Soundboardmodul](KARTEN-WORKSHOP-02.132.md) · [02.133 A – nur lokale Wiedergabe, keine gemeinsame Musikuhr](KARTEN-WORKSHOP-02.133.md) · [02.134 C – lokale Loops/Fades/Layer](KARTEN-WORKSHOP-02.134.md) · [Lizenzen und Medien](LIZENZEN.md).

**Nachfolgender Beschluss 12.4 C:** [Selektive sichere 12.4-Medienpakete](ASSETS-WORKSHOP-12.4.md) können eine tatsächlich export-/lizenzberechtigte AudioAssetRevision transportieren, **nicht automatisch** die 02.135-konfigurierbare AudioPlaylist-/Soundboard-Vorlagendefinition. AudioConfigTemplateSharing und Quellmedien-Export sind eigene 02.135-/12.1–12.4-Fachrechte; kein 02.133-Musikplayhead-Sync oder automatische Wiedergabe nach Import. V1 ein SL, Formate später.

**Nachfolgender Beschluss 12.5 C:** [Lizenz-/quell-/variantgeprüfte AudioDerivate](ASSETS-WORKSHOP-12.5.md) dürfen für tatsächlich zulässige 02.135-Playlist-/SoundboardTemplateQuellmedien dienen, aber eine neue AudioDerivedVersion verändert weder TemplateDefinition noch importierte PlaylistRevision ohne eigenen 02.136-/12.2-C-Target-/SelectiveMerge-/ListenerGrantCommit. Kein globaler MusikSync/Play oder rechtloser AudioExport. V1 ein SL; Codec-/Quality-/UI-Details später.

## 1. Verbindliche Entscheidung – Variante 02.135 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Bei wirksamem **02.132-C-Musikmodul An** dürfen hierzu berechtigte SL-/Verwaltungsrollen nach 02.25-Kampagnen-/Bibliotheks-/Rollen-/Gruppen-/Personenstandards mit **gültigen markierten Ausnahmen** gezielt **eigene oder ausdrücklich zum Wiederverwenden freigegebene Playlist- und Soundboard-Konfigurationen als Vorlagen** in einer anderen zulässigen Kampagne **referenzieren oder bei erlaubter Kopierbefugnis als eigene neue Konfiguration übernehmen**. Jede Aktion verlangt aktuelle wirkliche **Besitzer-, Quellkampagnen-, Zielkampagnen-, Vorlagen-, Audioasset-, Datei-/Lizenz-, Geheimnis- und Empfängerrechte**; die Vorlage ist **keine globale öffentliche Musikbibliothek**.

**Beispiel:** Eine SL hat eine „Taverne“-Playlist mit eigenen Cues organisiert. Sie kann die Konfiguration für Kampagne B zulässig freigeben, eine dafür erlaubte Vorlage auswählen und den Zielbestand mit gültigen Audioassets referenzieren oder bei gültigem Kopierrecht eine eigene Konfiguration anlegen. Eine geheime Szene, lizenzrechtlich nicht teilbare Musikdatei und ein anderes privates Soundboard bleiben **unsichtbar bzw. ungeöffnet**. Eine Vorlage verleiht weder Media-/Streamingrechte noch ein Recht auf unbekannte alte Geheimnisse.

**Nicht gewählt:** A (keine eigene kampagnenübergreifende Vorlagenwiederverwendung) und B (alle Audiofiles, Playlists, Kampagnen-/Geheimdaten für alle freigeben). C ist **weder** allgemeiner Kampagnenklon **noch** pauschaler Assettransfer, automatische Veröffentlichung oder Lizenz zum kopierten Stream/Download.

## 2. Vorlage, Quelle, Ziel und Freigabe

1. **Wirksame Modulgrenze:** Bei 02.132 Musik **Aus** keine aktive Musikvorlagenanwendung oder durch Vorlage gestartete Medien-/Cue-Wiedergabe. Das eigenständige Audio-/Asset-Bibliotheksobjekt darf allenfalls nach künftig eigens bestimmter Bestands-/Retentionregel geschützt verwaltet bleiben; **keine** stille Aktivierung des Musikmoduls. 02.105-Chat, Würfel-/Systemfeed und 02.49–02.51-Schall bleiben unabhängig.
2. **Was die Vorlage enthält:** Erlaubte **Konfiguration** wie eigene benennbare Playlist-/Soundboardtitel, Kategorien, Cue-/Trackreihenfolge, erlaubte Referenzen auf Audioassets sowie optional zulässige lokale 02.134-C-Loop-/Fade-/Layer-Voreinstellungen. Keine automatisch ausgegebenen Originaldateibinärdaten, keine privaten Streamtokens, DRM-Schlüssel, versteckten Szenennamen, fremden Empfängerlisten oder Original-Asset-Lizenzzusagen.
3. **Ausdrückliche Freigabe, getrennte Rollen:** Vorlagen-Owner darf nach echter Policy verwalten; Quellfreigabe, *als Vorlage sehen*, *in Ziel verwenden*, *als Kopie speichern*, *Originalvorlage bearbeiten*, *Medien nutzen*, *an weitere Kampagnen weitergeben* sind **verschiedene Befugnisse**. Reines Kampagnenbeitritts- oder SL-Verwaltungsrecht gibt keinen automatischen Zugriff auf private Vorlagen fremder Gruppen/Accounts.
4. **Zielkampagne separat berechtigen:** Die Zielkampagne kann auf Vorlage/-Revision ausdrücklich zugreifen, sofern Actor die Freigabe besitzt. Jede tatsächlich abgespielte Track-/Cuequelle ist **im Ziel erneut** auf Audioasset-/Lizenz-/Format-/Medien-/Szenen-/Empfänger-/Musikpolicy zu prüfen; eine freigegebene Liste darf sonst leere/ausgelassene nicht berechtigte Referenzen liefern, niemals die verbotene Datei.
5. **Referenzmodus:** Verknüpfung auf eine zulässig freigegebene, versionierte Quellvorlage, ohne unkontrollierte Kopie von Original-Audiofiles. Bei Zugriff müssen Quellfreigabe, Vorlagenversion, Ziel-/Musikpolicy und **jede Medienreferenz** wieder gelten. Rechteentzug, Löschung, Ablauf oder Wechsel der Ursprungsvorlage machen den entsprechenden aktiven Zugriff unwirksam. **Keine Zusicherung**, dass nach Quelllöschung eine abhängige Referenz weiter funktioniert.
6. **Kopiermodus:** Nur nach echtem **Kopier-/Weiterverwendungs- und Ziel-Erstellungsrecht** eine eigenständige neue **Playlist-/Soundboard-Konfiguration** mit neuen Ziel-IDs, dokumentierter Herkunft und explizit übertragbaren erlaubten Einstellungen anlegen. Ein unabhängiger Konfigurations-Snapshot ist **keine** automatisch kopierte Audio- oder Streamingdatei und **kein** neues Recht auf sie. Quell-/Zielrevisionen und zulässige Rechte des eigenständigen Zielobjekts bleiben nachvollziehbar getrennt.
7. **Quell-/Ziellizenz und spätere Widerrufe:** Ein Quellzugriff darf bei neuen Abrufen/Downloads/Wiedergaben gesperrt werden. Bereits rechtmäßig unter einem tragfähigen dauerhaften Zielrecht erstellte unabhängige Kopien sind **nicht automatisch fernsteuerbar oder rückwirkend physisch löschbar**; tatsächliche Rechte und vertragliche Lösch-/Lizenzpflichten müssen im Asset-/Lizenzmodell gesondert geklärt werden. Keine erfundene Garantie nachträglichen Entfernens schon heruntergeladener Medien.
8. **Geheimnis- und Metadatenfilter:** Vorlagenexistenz, Titel, Ordner, Cover, Trackanzahl/-folge, Dateinamen/-URLs, fehlende Audioassetverknüpfungen, Szenenbezüge und Besitzer dürfen **nur für wirklich berechtigte Nutzer** sicht-/such-/previewbar sein. Auch Counts, Sortierreihenfolge, Vorschau, Fehlerantwort, Quell-/Ziel-IDs, Realtime, Export und Caches dürfen keine verborgene Kampagne verraten.
9. **Nur berechtigte Bibliotheksteile:** Das Vorlagenkonzept aus 02.85–02.88 ist ein Vergleich für Rechte, IDs, Revisionen und Konflikte, **keine** automatische Übernahme dort geregelter Szenen-/Node-/Live-Instanzmigration auf Audio. Allgemeiner übergreifender Assetimport/-export, Lizenztransfer, Online-Marktplatz, externe Musikprovider und Paketformat bleiben **Thema 12** und separat offen.

## 3. Frühere Beschlüsse bleiben unverändert

| Fachbeschluss | Bedeutung der wiederverwendeten Vorlage |
| --- | --- |
| **02.25, 02.132 C** | Vorlagenfunktion nur als zugelassene Unterfähigkeit des aktivierten Musikmoduls; Rollen-/Quell-/Ziel-/Actor-/Asset-/Lizenzrechte bleiben serverautoritativ |
| **02.133 A** | Keine globale Musikzeit, kein gemeinsamer Playerzustand, kein Synchronisieren von Play-/Pause-/Seek, kein automatischer Start bei Join/Reconnect. Jede neu gestartete Quelle beginnt lokal bei **Titelanfang** |
| **02.134 C** | Übernommene Fade-/Loop-/Layer-Konfiguration ist **nur lokale unterstützte Option**; keine simultane Ausgabe für alle oder ungeprüfte Audioquellen |
| **02.85–02.88** | Sichere Vorlagen-/Version-/Bibliotheksprinzipien sind Vorbild; keine stillschweigende automatische Cross-Campaign-Audio-Synchronisierung oder Überschreibung lokaler Zielkonfiguration |
| **02.49–02.51** | Ein importierter Alarmton erzeugt niemals selbst echte Schallwellen, Wahrnehmung, Mikrofon-/Bewegungssensortreffer, NPC-Reaktion oder Node-/Alarmoutput |
| **02.99 / 02.101–02.104** | Reuse/Track-/Cue-Auswahl macht keine echte Quest-/Tür-/Inventar-/Würfel-/Turnaktion und keine bewusste 02.102-ACK-Quittierung |
| **02.105 / 02.122 A** | Musik-/Vorlagenmodul braucht keinen Chat, eröffnet keine neuen Chat-Sprachnachrichten-/Mikrofon-/Transkriptionsfunktionen |
| **02.110 / 02.126** | Individueller Audiomute ist nicht Chat-Mute; Vorlagenfreigabe erzeugt keine neuen Chatkontakte, Pings, Push-Rechte oder fremde Benachrichtigungen |
| **Assets/Lizenzen** | Wiederverwenden einer Konfiguration garantiert keine Nutzung fremder Audiofiles; personenbezogene, vertragliche und Medien-/Dateirechte gelten getrennt |

## 4. Lebenszyklus, Versionskonflikte und Missbrauchsgrenzen

1. **Autorisiertes Vorlageninventar:** Nur berechtigte und tatsächlich freigegebene Vorlagen und Versionen pro Besitzer-/Bibliotheks-/Kampagnen-/Rollen-/Gruppen-/Personenscope listen; keine erratbaren fremden Titel/IDs, Preview-/Index-/Search-/Member-/Count-Leaks.
2. **Explizite Zielauswahl/Operation:** Referenzieren, Kopieren, Zielinstanz anlegen, Trackzuordnung prüfen sind **eigenständig serverautorisierte Vorgänge**, ohne unbewussten Massentransfer von Medien/Assets oder stillen SL-Allzugriff auf Fremdkampagnen.
3. **Revision und Namenskonflikte:** Vorlage und Zielplaylist tragen eigene Identität, Owner-/Herkunftshinweis und passende Versionsmarkierung. Doppelte Einfügung, gleichnamige Playlist und konkurrierende Editierungen brauchen deduplizierte, nachvollziehbare eindeutige Ziel-IDs/Revisionen und bewusste Konfliktentscheidung; kein blindes Überschreiben fremder Zieländerungen.
4. **Referenzauflösung zur Nutzungszeit:** In Quelle und Ziel wirksame Policy/Secret-/Lizenz-/Asset-/Retention-/Mediarechte, etwaige Verfügbarkeit und gültige Revision **bei jedem** Playlist-/Track-/Cueabruf, Reconnect, Reload, Download/Streaming und lokaler Wiedergabe serverseitig prüfen. Alte signierte URLs, Index-/Browsercache oder Playlist-Referenzen dürfen nicht heimlich gesperrte Medien bereitstellen.
5. **Rechteentzug und Herkunft:** Entzug der Quellfreigabe stoppt neue Referenzverwendungen; bereits unabhängig unter zulässigen Rechten gespeicherte Zielkonfigurationen bleiben als eigene Quelle geprüft, nicht als durch fremde Adminrechte beliebig manipulierbare Kopie. Lizenz-/Datenschutzpflichten dürfen nicht durch Umbenennen/Kopieren umgangen werden.
6. **Keine unkontrollierte Live-Updatekette:** Quellrevisionen dürfen referenzierte Zielkonfigurationen, lokal geänderte Playlists oder laufende Audio-Cues **nicht automatisch überschreiben/auslösen**. Behandlung von geänderten Vorlagenversionen, Versionshinweisen und gezieltem Update/Abgleich ist **02.136** zu entscheiden.
7. **Audio-Laufzeit und Sessionrechte:** Übernahme eines Vorlagen-Tracksets ist **kein Start-Cue**, keine Wiedergabe, kein gemeinsamer Playhead und keine Umgehung individueller Browserautoplay-/Volume-/Mute-Entscheidungen. Echte Musikaktionen verlangen 02.132-Berechtigung und 02.133-A-/02.134-C-lokale Ausführung.
8. **Quoten und Pakete:** Begrenzung von Templatezahl, Referenzketten/Tiefe, Asset-IDs, Importmengen, Pfadlängen, Upload-/Storage-/Bandbreite, Rate, Replays und Cache. Kein zirkulärer Templatescope, keine ausführbaren Skripte, kein Metadaten-/Track-SSRF oder automatische Drittprovider-Weitergabe.

## 5. Konzeptioneller Umsetzungsplan (kein fertiger Code)

1. **Policy-/Capabilityvertrag:** 02.132-Musik An als harte Grenze für Musikvorlagenfunktionen; 02.25-Defaults und markierte Ausnahmen getrennt für Eigentümer, Quelle, Ziel, Template-Lesen, Referenz-/Kopierberechtigung, Audio-/Lizenz-/Szenenzugriff und Freigabe; Sicherheitskontrollen nicht abschaltbar.
2. **Vorlagen- und Quellresolver:** Konzeptionelle Arbeitsmodelle `AudioTemplateDefinition`, `AudioTemplateRevision`, `AudioTemplateGrant`, `AudioTemplateAssetRef`, `AudioTemplateTargetBinding`, `AudioTemplateCopyOrigin` und `AudioTemplatePermissionDecision` (keine finalen Tabellen-/API-Namen). Nur Metadaten/Audio-Referenzen ohne Binär-Shadow-Archiv.
3. **Zwei explizite Wiederverwendungsarten:** Referenz: aktiver Quell-/Ziel-/Asset-/Revisions-/Lizenzguard bei jeder Verwendung. Kopie: neue unabhängige Zielkonfiguration/ID nach sicherer Kopierlizenz und expliziter Useraktion; keine Quell- oder Mediarechte durch ID-Kopie.
4. **Strikter Audio-/ACL-Einsatz:** Nach geladenem erlaubtem Template weiterhin tatsächliche 02.132-C-Actor-/Cue-/Asset-/Empfängerrechte, 02.133-A-lokaler Start am Anfang und ggf. zugelassene 02.134-C-lokale Mixfähigkeiten mit per-Hörer-Mute/Browserautonomie; keine 02.51-World-/Node-/ACK-Wirkung.
5. **Lifecycle/Sicherheit:** Version/CAS-/Idempotenz-/Konfliktschutz, Revocation/Retention/Lizenzaktualisierung, Source-/Target-Campaign-Isolation, Cache-/Realtime-/Media-URL-Invalidierung, Ressourcen-/Rate-/Path-/SSRF-Schutz und Berechtigungstests. Automatische Vorlagenupdatepolitik nicht unter 02.135 hineininterpretieren.
6. **Abnahme und spätere Gesamtplanung:** Tests nachfolgend; konkreter globaler Assistent, Speicherstruktur, Asset-/Import-/Export-Pakete, Lizenz-/Streamingprovider, finaler UI-Flow und MVP bleiben im späteren Gesamtkonzept.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| 02.132-Musik Aus, Spieler ruft Audio-Vorlage zur Wiedergabe auf | Kein aktiver Musikvorlagen-/Track-/Cuepfad; Chat, Würfel-/Systemfeed und 02.51-Schall unabhängig |
| Kampagne A und B haben Musik An, SL besitzt Vorlage | SL kann nur nach ausdrücklichen echten Quell-/Ziel-/Template-Rechten referenzieren oder zulässig kopieren |
| Neue Kampagne ohne Freigabe der Vorlage | Kein Eintrag, Vorschau, Tracktitel, Count, Download oder belegender Fehlertext |
| SL verwaltet Zielkampagne, aber besitzt keine fremde Source-Leseberechtigung | Kein Zugriff auf private fremde Playlist oder deren Metadaten |
| Spielleiter erlaubt nur Referenz, nicht Kopie | Zulässige Referenz möglich, eigenständige Zielkonfiguration wird abgelehnt |
| Spieler darf Zielplaylist anlegen, aber nicht Vorlage lesen | Kein Source-Template-/Tracklistenabruf durch Targetrecht |
| Berechtigter Quellowner gibt ausdrücklich kopierbare Playlist frei | Eigene neue Zielplaylist-ID mit gültiger Herkunfts-/Revisionsbindung, keine Originalüberschreibung |
| Vorlage enthält Audioasset ohne Weitergaberecht | Keine automatische Übertragung der Bytes oder neue Streaming-/Downloadberechtigung |
| Vorlage enthält drei erlaubte und zwei verbotene Audioreferenzen | Nur nach Policy ausdrücklich zulässige Einträge/Redaktion/Warnung, keinerlei Secret-Asset-Existenzleck |
| Nutzer versucht geheime Track-ID aus kopierter Playlist als URL | Kein Audioabruf ohne aktuelle Ziel-/Medien-/Lizenzrechte |
| Quelldatei wird bei referenzierter Vorlage gelöscht/gesperrt | Abhängige neue Referenzverwendung stoppt, kein Schatten-Audiostore |
| Sourceowner widerruft Freigabe nach erfolgreichem Reference-Reuse | Kein weiterer Zugriff auf Referenz/Medien ohne neu gültige Freigabe |
| Zielkopie hat unabhängig gültige dauerhafte Lizenz | Keine falsche Behauptung, Sourceowner könne bereits zulässige lokale Dateien rückwirkend physisch löschen |
| Tracklizenz endet auch in einer eigenständigen Zielkonfiguration | Keine weitere unerlaubte Mediennutzung durch kopierte Metadaten |
| Versteckte Szenentitel in Quelltemplate | Kein Szenenname, Ort, NPC-, Fog-, Secret- oder Szenen-Assetleck im Ziel |
| Quelle gehört privater Gruppe der anderen Kampagne | Keine unberechtigten Memberlisten, Gruppennamen, Template-Existenz- oder Suchfacets |
| SL kopiert zweimal dieselbe Vorlagenrevision | Idempotenz/gezielte Duplikatentscheidung, kein ungeplanter doppelter Live-Cue |
| Vorlage und Zielplaylist haben identischen Namen | Neue sichere IDs und sichtbare Konfliktbehandlung, kein stilles Überschreiben |
| Quellplaylist hat neue Revision nach Kopieren | Alte unabhängige Zielkonfiguration wird nicht automatisch ersetzt |
| Quellowner ändert referenzierte Playlist während eines Browsercaches | Erneute Quell-/Revisions-/Lizenz-/Empfängerprüfung; keine alte geheime Vorschau |
| Zwei Nutzer ändern zeitgleich Zielplaylist | Konflikt-/CAS-/Rolechecks, keine fremde stille Last-Writer-Wins-Änderung |
| User versucht `reuseTemplate` mit fremder Owner-/Campaign-ID | Serverseitig nicht berechtigt; keine fremde Metadatenantwort |
| Reconnect mit alter freigegebener Template-URL | Jetzt entzogene Rechte und Signatur-/Retentiongrenzen gelten weiter |
| Importierte Vorlage enthält lokale Crossfade-/Loop-Einstellungen | Nur technisch unterstützte, in Ziel 02.134-C-berechtigte lokale Mischvoreinstellungen |
| SL wählt neue Playlistvorlage für Sitzung | Keine automatische Musikquelle gestartet, keine gemeinsame Transport-/Playhead-Synchronisation |
| Spieler tritt Session erst nach Vorlagenanwendung bei | Keine automatische Musik-/Playhead-/Cue-Nachholung; freiwilliger lokaler Start bei 0 |
| Hörer hat Audio-Master-Mute | Referenz/Kopie darf eigenen Mute nicht übersteuern |
| Browser verhindert Audio-Autoplay | Kein Play-Zwang oder Umgehen von Usergesture-/Geräteeinstellungen |
| Vorlage enthält Alarm-Soundeffekt | Kein 02.49–02.51-Schallsensor-/Node-/Alarm-/Door-/NPC-Gameevent |
| Vorlagenname lautet `Quest abgeschlossen` | Kein 02.99-Quest-/Door-/Turn-/Würfel-/Inventarcommit |
| Chat Aus und Musik An | Rechtmäßige Audio-Vorlage verwendbar, Chat/Voice-Memos bleiben ausgeschlossen |
| Audio-Vorlagenfreigabe im Chat verlinkt | Keine zusätzlichen 02.106-/02.107-DM-/History-/Sender-/Empfängerrechte |
| Bestätigungspflicht aus 02.102 besteht | Template speichern/verwenden/abspielen ist niemals bewusstes offizielles ACK |
| Quelle gelöscht; zulässige eigenständige Zielkopie besitzt eigenes Assetrecht | Nur das tatsächlich gültige unabhängige Zielrecht zählt; kein pauschales Weiterleben fremder Source-Referenzen |
| Vorlage enthält ausführbares Skript, fremde Web-URL oder Pfad `../` | Keine Skriptausführung/SSRF/Pfadumgehung oder ungeprüfter Massendownload |
| Tausende Cross-Campaign-Vorlagen/IDs als Request | Ressourcen-/Quoten-/Rate-/Existenz- und Autorisierungsschutz greift |
| Mehrere Kampagnen auf getrennten eigenen Serverinstallationen | Kein automatisch beschlossenes Online-Sharing-/Import-Paket oder fremder Serverzugang |
| Fehlende Quelllizenz und scheinbar identisches Zielaudio | Keine erfundene pauschale Lizenz durch Template-Referenz oder Kopie |

## 7. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.135 C – ausdrücklich berechtigte Wiederverwendung freigegebener Audio-Playlist-/Soundboard-Konfigurationen als referenzierte oder zulässig unabhängig kopierte Vorlagen über Kampagnen hinweg.** 02.132-C-Musik-An-/Ausgrenze, 02.25 gültige Defaults/markierte Ausnahmen, getrennte Owner-/Quell-/Ziel-/Vorlagen-/Asset-/Lizenz-/Empfängerrechte, Geheimnisschutz, Quellenrevisionen und Revocation behalten Vorrang. **02.133 A bleibt unverändert:** rein lokale Trackwiedergabe ohne globale Timeline oder Late-Join-/Reconnect-Catch-up. **02.134 C bleibt unverändert:** ausschließlich lokale optionale Loops/Fades/Soundboard-Layer. Keine 02.49–02.51-Schall-/Sensor-/Nodewirkung, keine 02.99-Weltaktion und kein offizielles 02.102-ACK aus Template-/Cue-/Playlistaktionen.

**Nicht beschlossen:** allgemeines Audio-Dateipaket/-Import/-Exportformat, dauerhafte Streaminglizenzen, automatisierte Vorlagenupdates, Sync-Dienste, unbeschränkte Kopien/Veröffentlichung, konkretes Bibliotheks-UI, DB/API, MVP. Die Vorlagenberechtigung ist **keine** umfassende neue Freigabe fremder Kampagnendaten.

## Nächste Entscheidung 02.136 – Versionierte Aktualisierung wiederverwendeter Audio-Vorlagen

**Beispiel:** Eine SL hat eine Taverne-Soundboardvorlage in mehrere Kampagnen kopiert oder referenziert. Später korrigiert sie den Cue für Regen und ergänzt einen Song. Die Zielkampagnen haben inzwischen eigene Änderungen und dürfen nicht ungefragt überschrieben werden.

- **A – Nur neue manuelle Kopien:** Eine einmal wiederverwendete Vorlage erhält keine eigene kontrollierte Änderungsverknüpfung. Spätere Quellenänderungen können ausschließlich als ausdrücklich neu eingefügte unabhängige Konfiguration behandelt werden.
- **B – Ungefragte globale Aktualisierung:** Jede neue Vorlagenversion verändert automatisch alle referenzierten und kopierten Playlists/Soundboards samt laufenden lokalen Audio-Cues, auch gegen lokale Änderungen und aktuelle Rechte.
- **C – Konfigurierbare sichere Versionsübernahme (Empfehlung):** Nach gültigen 02.25-/02.132-/02.135-Quell-/Ziel-/Vorlagen-/Asset-/Lizenz-/Rollen-/Szenen-/Empfängerrechten dürfen berechtigte Zielverwalter neue Versionen erkennen, vergleichen, als eigene neue Kopie verwenden oder **bewusst freigegebene** Änderungen in geeignete lokale Konfigurationen übernehmen. Konflikte/Löschungen/Secret-/Assetrechte sind zu prüfen; keine stillen Änderungen laufender Cues, keine automatische globale Playbacktimeline nach 02.133 A, keine Schall-/Node-/Welt-/ACK-Wirkung.
