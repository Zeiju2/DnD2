# AdventureShift – Karten-Workshop: Beschluss 02.86 C

**Stand:** 12.10.2026 – Beschluss 02.86 C; nachfolgende 02.87 C beschlossen, als Nächstes 02.88  
**Status:** Fach- und Umsetzungsplanung; noch keine fertige Software, API, konkrete Datenbanktabellen oder endgültige UI.  
**Anschluss:** [Karten-Hauptworkshop](KARTEN-WORKSHOP.md) · [Vorlagen, selbst benennbare Ordner und Volltextsuche 02.85](KARTEN-WORKSHOP-02.85.md) · [Graph-Versionierung 02.80–02.82](KARTEN-WORKSHOP-02.82.md) · [Karten-/Szenenversionierung 02.83](KARTEN-WORKSHOP-02.83.md) · [Feature-Workshop](FEATURE-WORKSHOP.md) · [02.87 Austauschpakete](KARTEN-WORKSHOP-02.87.md)

## 02.86 – Private, kampagnenbezogene und freigegebene Vorlagenbibliotheken mit differenzierten Rechten

**Verbindlich beschlossen: Variante C.** Bibliotheken für wiederverwendbare Karten-/Szenen-/Gebäude-/Raum-/Stockwerk-/Gelände-/Objekt-/Nodebausteine aus 02.85 dürfen **privat**, **einer Kampagne zugeordnet** oder **bewusst für ausgewählte andere Berechtigte gemeinsam nutzbar** sein. Sichtbarkeit und erlaubte Handlungen sind **je Bibliothek, Ordner/Unterordner, Vorlage/Vorlagenrevision sowie Empfängerrolle oder gezielter Freigabe** konfigurierbar. Kampagnen-/Regelprofilstandard, klar sichtbare Ausnahmen und Änderungs-/Bestandsschutz folgen 02.25. Es gibt **keine automatische öffentliche Bibliothek**, keinen impliziten Zugang fremder Kampagnen, keine unbemerkte Weitergabe von Geheimnissen und kein uneingeschränktes „ein Recht gilt für alles“.

**Nachfolgender Beschluss 12.1 C:** Die [eigenständig geschützte Asset-/Quell-/License-/Use-Bibliothek](ASSETS-WORKSHOP-12.1.md) ergänzt 02.86-TemplateLibraryRights: Das Teilen einer TemplateDefinition/Ordnerstruktur gewährt **nicht** automatisch Eigentum, OriginalRead/Download, Kopier-/Export-/Bearbeitungs-/Publikationslizenz für ihre abhängigen Medien. TemplateReuse und AssetUse/Copy/Export erfordern separat aktuelle Source-/Target-/Asset-/Owner-/Recipient-/Historyrechte. V1 ein aktiver SL, Lizenz-/Asset/UISpezifika später.

**Nachfolgender Beschluss 12.4 C:** [Separate selektive Medien-AssetPackages](ASSETS-WORKSHOP-12.4.md) transportieren nur tatsächlich exportberechtigte Versionen, Eigentums-/Herkunfts-/Lizenzminimummetadaten und zulässige Original-/Variantbytes. Bestehende 02.86-TemplateLibrary-/Folder-/SourceRead-/Share-/Copy-/Exportrechte werden durch ein Medienpaket **nicht** automatisch erweitert; ein an eine Vorlage gebundenes Bild hat eigene 12.1–12.3-MediaUse-/Source-/License-/Exportrechte. Zielimporte erzeugen ausschließlich legitimierte neue lokale LibraryAssetRefs, keine fertigen Szenen/World-Objekte. V1 ein SL, Pakettechnik später.

### 1. Eigentum, Bibliothekstypen und Sichtbarkeit

- **Persönliche private Bibliothek:** Eine berechtigte Spielleitung besitzt ihren eigenen Ablagebereich. Andere Teilnehmer erhalten nur dann Zugriff, wenn eine tatsächlich gültige explizite Freigabe vorliegt. Alle Vorlagen und deren selbst erstellte/beliebig benannte Ordner aus 02.85 bleiben standardmäßig nicht für unberechtigte Dritte sichtbar.
- **Kampagnenbibliothek:** Vorlagen können einer bestimmten Kampagne zugeordnet und ausgewählten Kampagnenrollen/SL bzw. Gruppen freigegeben werden. Mitgliedschaft in einer Kampagne begründet **nicht automatisch** das Recht auf jeden geheimen SL-Ordner oder alle dortigen Vorlagen; die konkrete Freigabe entscheidet.
- **Bewusst geteilte Bibliothek:** Berechtigte Eigentümer/Administratoren können ausgewählte Bibliotheken, Ordner oder Einzelvorlagen gezielt an eine andere berechtigte SL, Gruppe bzw. Kampagne freigeben. Eine plattformweit öffentliche Bibliothek ist dadurch **nicht automatisch** eingeführt. Reichweite, Empfänger und Weitergabe sind ausdrücklich zu wählen und zu protokollieren.
- **Eigentümer und verantwortlicher Freigeber:** Jede Bibliothek, jeder Ordner und jede Vorlage referenziert stabile Eigentümer-/Kampagnen-/Scope-IDs, mögliche berechtigte Administratoren und Freigabeherkunft. Ein neu anlegender Bearbeiter wird nicht stillschweigend Eigentümer fremder Quellen oder ermächtigter Weiterverteiler. Sicherheitskritischer Eigentümertransfer bleibt nur berechtigt und prüfbar.
- **Standard und Ausnahmen:** Per Kampagnen-/Regelprofil und Bibliotheks-/Ordner-/Vorlagentyp können sinnvolle sichtbare Defaults und ausdrücklich benannte Overrides gelten (02.25). Gültige übergeordnete Verbote, Eigentümer-/Adminbeschränkungen, erforderliche Freigaben sowie Rechte des **eigentlichen** Ursprungsassets sind nicht durch eine Unterordnerausnahme auszuschalten.

### 2. Trennbare Aktionen und Schutzprinzipien

| Berechtigung | Fachliche Bedeutung |
| --- | --- |
| **Auffinden / Durchsuchen** | Eine Berechtigte darf die jeweilige Vorlage im Ordner und in der Volltextsuche aus 02.85 finden; kein Suchtreffer, Trefferzähler, Pfad oder Such-Snippet ohne wirksamen Zugriff |
| **Ansehen / Vorschau** | Tatsächlich erlaubte Metadaten, Szene-/Vorlagen-Vorschau und abhängige Assets einsehen, ohne verborgene Node-, Türcode-, NPC-, Karten- oder SL-Daten mitzuliefern |
| **Als Kopie verwenden / Importieren** | Eine bestehende Vorlagendefinition in einen zulässigen eigenen Vorlagen-/Szenen-Draft übernehmen, mit neuen realen Objekt-IDs, gültigem Node-/Asset-Mapping und Zielkampagnenprüfung aus 02.85 |
| **Vorlage bearbeiten** | Änderungen an der gemeinsamen Vorlagendefinition bzw. einem dazu berechtigten Entwurf vornehmen, nach Versions-, Eigentümer- und Konfliktschutz; kein Recht auf bestehende echte Instanzen |
| **Ordner organisieren** | Ordner erstellen/benennen, Vorlagen einsortieren/verschieben, kontrolliert archivieren/löschen; Zielordner braucht ebenfalls aktuelle Rechte |
| **Freigeben / Weiterteilen** | Nur ausdrücklich ermächtigte Berechtigte dürfen Leserechte, Kopierrechte oder weitere Freigaben an andere vergeben, ggf. befristet und widerrufbar |
| **Freigaben administrieren** | Rechte, Empfänger und Eigentümer-/Sicherheitsregeln innerhalb des ausdrücklich zulässigen Scopes ändern, mit Audit und Schutz der Original-/Quellrechte |

Die Bedienoberfläche soll **wirksame Berechtigung und Quelle** (Bibliothek, Elternordner, Einzelvorlage, gezielte Freigabe/Ausnahme, vorhandene Sperre) nachvollziehbar anzeigen, ohne andere geschützte Personen oder Inhalte zu verraten. **Lesen ist nicht Bearbeiten, Kopieren nicht Weiterfreigeben, Ordnerverwalten nicht Adminrechte.** Berechtigte Autorität und Fähigkeiten prüft immer der Server, nicht ein Client-Menü oder ein ungeprüfter Link.

### 3. Ordner, Vererbung, Volltextsuche und Teilbarkeit

1. **Ordner bleiben benennbar und verschachtelbar:** Benutzer können weiterhin eigene Ordner und Unterordner frei erstellen, umbenennen, verschieben und zur Strukturierung verwenden (02.85). Ein Ordner kann eine bewusst konfigurierte vererbbare Sicht-/Aktionsfreigabe besitzen; Einzelvorlagen und Unterordner dürfen nur innerhalb tatsächlich erlaubter Rechte wirksam abweichen.
2. **Umordnung ohne Rechteverlust oder Privileg-Eskalation:** Beim Verschieben einer Vorlage zwischen privaten/geteilten Ordnern oder zwischen Kampagnen-/Persönlich-/Team-Scope den **neuen wirksamen Empfängerkreis vor der Änderung** anzeigen und erneut autorisieren. Ein bloßer Ordnerwechsel darf nicht unbemerkt eine geheime Falle, Vorlagenbeschreibung, Assetreferenz oder Text-Snippet anderen Nutzern offenlegen. Die stabile Vorlagen-ID bleibt erhalten, sofern wirklich ein Umordnen und keine neue Kopie gewählt wird.
3. **Volltextsuche bleibt vollständig:** Vorlagennamen, Beschreibung, Tags, Ordnernamen und Pfade, benannte Räume/Komponenten sowie andere zugelassene textuelle Vorlagenmetadaten sind gemäß 02.85 auch **über mehrere zugängliche Ordner und Bibliotheken hinweg** auffindbar. Suchscope und Ergebnis-/Snippet-/Vorschauberechtigung immer pro Empfänger prüfen; private Ordner dürfen selbst durch Gesamtzahl, Autovervollständigung, Timing, Filtervorschläge oder Caches nicht verraten werden.
4. **Freigaben bewusst erteilen:** Vor Bestätigung deutlich machen, ob nur einzelne Vorlagen, ein Ordner inklusive Unterordnern oder eine ganze Bibliothek betroffen ist; Empfängertyp, Zweck, Rechtelevel, ggf. Zeitablauf und mögliche verbundene Assets/Node-Informationen prüfen. Neues Freigaberecht darf niemals Rechte auf fremde Assets/Geheimnisse erzeugen, die der Freigebende selbst nicht hat.
5. **Rechteentzug und Verschärfung:** Nach Widerruf keine neue Suche, Vorschau, Kopie, neue Vorlagenrevision oder Nutzung vertraulicher Quellen ohne erneut gültige Berechtigung. Indizes/Caches/Abonnements bei Rechteänderung absichern. **Bereits rechtmäßig und unabhängig erzeugte Kopien und platzierte echte Weltobjekte werden nicht ungeprüft gelöscht, umkonfiguriert oder zurückgesetzt**; falls eine konkrete Weiterverwendung nach gültiger Lizenz/Sicherheitsregel nicht mehr zulässig ist, müssen neue Zugriffe/Updates gesperrt und Berechtigten eine sichere Prüfung/Entscheidung angeboten werden. Freigabeentzug ist kein rückwirkender Weltrollback.
6. **Versionsstand und Referenzbindung:** Eine berechtigte Freigabe gilt für den klar definierten Vorlagen-/Ordnerumfang und die jeweils gültigen Versionen gemäß ausdrücklicher Policy. Eine neu veröffentlichte Vorlagenrevision oder geänderte Sichtbarkeit darf bereits eingefügte Szenen-/Graphinstanzen nicht stillschweigend umschreiben (02.80–02.85).
7. **Kampagnenwechsel oder Eigentümerverlust:** Wenn Benutzer eine Kampagne verlassen, Rollen verlieren oder ihre Rechte ändern, dürfen alte gespeicherte Freigabereferenzen und Browser-Sessions keine weiteren Zugriffe erlauben. Verwaiste Bibliotheken/Ordner nach sicherem Besitz-/SL-/Adminprozess verwalten, **nicht** automatisch öffentlich machen oder löschen.
8. **Freigabeinformationen selbst schützen:** Wer eine geheime Vorlage teilt, darf deren Geheimnis nicht über Berechtigtenlisten, Freigabenamen, Änderungsverlauf, Audit, Indexreferenzen, Suchtreffer, Vorschau oder Ordnerhierarchie an unberechtigte Mitglieder preisgeben. Ein gültig berechtigter Empfänger erhält nur den Umfang, zu dem er auch Zugriff hat.

### 4. Sichere Kopie zwischen Kampagnen und gemeinsam genutzte Versionen

- **Aus Quelle in Zielszenen-Draft:** Ein bewusst berechtigtes Kopieren/Importieren kann ausgewählte geometrische/Asset-/Objekt-/Node-Konfigurationen aus 02.85 übernehmen. Für echte neue Weltobjekte immer neue eigene stabile Objekt-/Port-/Kantenbindungen bzw. explizit gültige externe Referenzen erzeugen; Quellfigur, laufender Timer, Inventarbestand, Fog-Verlauf, Würfelereignisse, unbekannter NPC und vertrauliche SL-Historie dürfen nicht versehentlich mitwandern.
- **Dependencies, Lizenzen und Geheimnisse:** Quelle und Ziel benötigen wirkliche kompatible Rechte auf Vorlageninhalt, Bilder/Assets, Regelmodule und enthaltene Node-/Objektdefinitionen. Nicht erlaubte Bestandteile gesondert auslassen, sicher anonymisieren, gültige neue Bindung fordern oder den Kopiervorgang ablehnen. **Fremde geheime Codes/SL-Szenen/NPC-Wissen nie durch Kopieren in eine neue Kampagne einschmuggeln.**
- **Verknüpfung ist nicht Eigentumsübertragung:** Ein Empfänger kann je erteiltem Recht eine unabhängige Vorlagenkopie/Instanz nutzen oder eine zulässige quellversionbezogene Referenz halten. Die neue eigene echte Spielwelt bleibt unabhängig; gemeinsame Quell-Updates erzeugen kein automatisches Weiterlaufen, kein Gratiswürfeln und keine Live-Zustandsänderung. Ein bewusstes späteres Templateupdate müsste eigene aktuelle Änderungs-/Sicherheits-/Publikationsregeln erfüllen.
- **Audit und Einmalwirkung:** Stabile Freigabe-/ACL-/Revisions-/Transfer-/Kopier-/Zieloperations-IDs und aktuelle Rollen-/Objekt-/Assetprüfung. Doppelte Freigabe- oder Netzwerkpakete dürfen keine unkontrollierte neue Verteilung, neue Tür, zweite Nodewirkung oder rückwirkende Änderung erzeugen.

### 5. Konzept und geplanter Umsetzungsweg – kein Code

**Mögliche Modellnamen:** `TemplateLibrary`, `TemplateFolder`, `TemplatePermissionPolicy`, `TemplateShareGrant`, `LibraryMembership`, `TemplateRevisionAccess`, `TemplateVisibilityProjection`, `TemplateImportAuthorization`, `TemplateSharingAudit`. Benötigt werden stabile Template-/Ordner-/Bibliotheks-/Revision-/Eigentümer-/Kampagnen-/Empfänger-/Freigabe-/Operations-IDs, gültige Rechte für **Search/View/Preview/Copy/Edit/Organize/Share/Manage**, Scope-/Policyherkunft, Recht-Version und geschützte Auditinformationen. Noch keine verbindliche Festlegung auf ein bestimmtes ACL-/Datenbank-/Freigabetoken-Verfahren.

**Geplante Schritte:** (1) Eigentümer-/Bibliotheks-/Kampagnenscopes und wirksame Vererbungs-/Ausnahmenregeln festhalten; (2) serverautoritative Aktionsrechte, Freigabeerteilung/-widerruf, Berechtigungsprüfung beim Ordner-Verschieben und Versionsänderung; (3) sichere Volltext-/Ordnerindexprojektionen aus 02.85 pro Rolle, einschließlich Ergebniszahlen, Vorschau und Reconnect/Cache-Invalidierung; (4) bewusst erlaubte Template-Instanziierung zwischen Kampagnen mit Asset-/Regel-/Objekt-/Node-Mapping, eigenständigen neuen Welt-IDs und Geheimnisschutz; (5) Änderungs-Audit, Nachvollziehbarkeit, SL-Vorschau und isolierte Rechte-/Race-/Revocation-/Replay-/Such-/Kopiertests. Konkrete Benutzerführung, globale Kampagnenassistentenstruktur und MVP-Auswahl erst nach kompletter Featureplanung. Allgemeiner Assetbereich 12 behält seinen eigenen offenen Umfang.

### 6. Abnahmetests

| Fall | Erwartetes Ergebnis |
| --- | --- |
| SL A hat private Ordner `Fantasy/Gasthäuser` mit zwei Vorlagen | SL B sieht ohne Freigabe weder Ordner, Vorlage noch Trefferzahl oder Suchsnippet |
| A teilt ein Gasthaus mit B nur zum Lesen/Suchen | B findet und sieht zulässige Vorschau, kann aber weder fremde Vorlage ändern noch unberechtigt weiterteilen |
| A erteilt B explizit das Kopier-/Importrecht | B kann mit aktuellen Kampagnen-/Assetrechten eigene geprüfte neue Objektinstanzen anlegen; keine Quellzustände |
| A teilt nur Unterordner, nicht benachbarten geheimen Ordner | Keine Einsicht/Indizierung des anderen Ordners, seiner Namen oder Inhalte |
| A teilt einen Ordner mit Unterordnern; eine sensible Einzelvorlage ist ausdrücklich ausgeschlossen | Gültige Ausnahme schützt die sensible Vorlage und ihre Text-/Bildvorschau |
| B hat Kopierrecht, aber kein Weitergaberecht | B kann je Policy zulässig kopieren, aber die Quellvorlage nicht an Dritte freigeben |
| Vorlagenordner wird von privat nach geteilt verschoben | Vor Änderung sichtbare Reichweiten-/Rechteprüfung; keine unbemerkte Freigabe vertraulicher Inhalte |
| Volltextsuche nach `Keller Falltür` in zwei ausdrücklich freigegebenen Bibliotheken | Vorlagen werden unabhängig von ursprünglichem Ordner durchsucht, nur berechtigte Treffer angezeigt |
| Freigabe wird während Suche oder Reconnect widerrufen | Kein späteres Durchsickern über alte Treffer/Snippets/Indexcache oder neue Kopier-/Preview-Aktion |
| Quellvorlage referenziert fremde geheime Falle/Node oder urheberrechtlich nicht teilbares Asset | Keine unberechtigte Datenkopie, sicherer Ausschluss/Mappingschritt oder Abbruch |
| B hat vor Widerruf ein eigenständiges zulässiges Gasthaus in einer anderen Kampagne eingesetzt | Widerruf verhindert künftige Quellzugriffe, löscht aber nicht unkontrolliert das bereits echte Gasthaus oder frühere Spieleraktionen |
| Vorlage wird umbenannt/als Revision erneuert | Neue gültige Suche/Versionsprojektion; bereits platzierte konkrete Objektinstanzen nicht heimlich aktualisiert |
| SL verliert Kampagnenrolle | Zugriff/Freigaberecht neu prüfen; keine alte Sessionberechtigung oder automatische öffentliche Bibliothek |
| Doppelte Freigabe-/Kopieranforderung nach Netzwerkfehler | Deduplizierte einmalige berechtigte Aktion, keine doppelte Weltinstanz und kein unberechtigter Transfer |
| Unberechtigte Person sieht online andere SL-Bearbeiter der geheimen Bibliothek | Keine Lecks über Lock-/Presence-/Audit-/Versionstexte |
| Isolierter Test mit unterschiedlichen Rollen | Zutreffender Rechte-/Freigabe-/Suchstatus ohne reale Spielwelt- oder Inventaränderung |

### 7. Abgrenzung und nächste Entscheidung

- **02.85 C** hat die **selbst erstellbaren benennbaren Vorlagenordner** und **bibliotheksweite Volltextsuche** sowie sichere neue Szenen-/Objektinstanzen verbindlich beschlossen; diese Funktionen bleiben unabhängig davon, ob Bibliotheken privat oder geteilt sind. **02.86 C** ergänzt die **Eigentümer-, Sichtbarkeits-, Rollen- und Weitergaberegeln**.
- Eine gültige geteilte Vorlagendefinition ist **keine Freigabe ihrer gesamten Quellkampagne** und kein Besitzrecht an realen Figuren, Geheimnissen oder Ressourcen. Kontinuierliche Aktualisierung echter platzierter Objektinstanzen ist nicht implizit beschlossen.
- Die allgemeine Asset-/Medienbibliothek, beliebige Packdateiformate und globale Einstellungen folgen späteren Featurethemen; technische Speicherung/Datenbankschema/konkrete Rechte-UI sind noch offen.

## Archivierte Folgefrage 02.87 – inzwischen als C beschlossen

**Beispiel:** Eine Spielleitung möchte ihre selbst organisierten Raum-/Gebäudevorlagen samt erlaubten Bildern und ausgewählten Ordnern in eine andere AdventureShift-Installation oder einen späteren eigenen Server übertragen, ohne dort Zugriff auf ihre ursprüngliche Kampagne zu benötigen.

- **A – Nur innerhalb derselben Installation:** Vorlagen können gemäß 02.86 nur intern geteilt werden; es gibt keinen gezielten Paketexport und -import der Vorlagenbibliothek.
- **B – Ungeprüfte Komplettkopie:** Alle Bibliotheks-, Medien- und Konfigurationsdaten inklusive möglicher Geheimnisse, Rechte, aktiver Spielstände und fremder Assets werden ohne Prüfung als Paket exportiert bzw. importiert.
- **C – Konfigurierbarer sicherer Vorlagenpaket-Austausch (Empfehlung):** Berechtigte SL können ausgewählte Vorlagen, erlaubte Ordnerstruktur, versionierte Definitionen und tatsächlich zur Weitergabe freigegebene Assets in ein geprüftes Austauschpaket exportieren/importieren. Zielkampagnenregeln, Lizenzen, Fremd-IDs, Geheimnisse, Node-/Port-Abhängigkeiten und neue Instanzreferenzen vor Import prüfen; kein Mitnehmen realer Würfe/Inventare/Fog/Timer-/Kampf-/Turnzustände. Kein unberechtigter Zugriff auf Ursprungskampagnen und kein stilles Ersetzen bereits vorhandener Vorlagen.


**Aktueller Fortgang:** **02.87 C** ist in [KARTEN-WORKSHOP-02.87.md](KARTEN-WORKSHOP-02.87.md) mit berechtigtem selektivem Export/Import von Vorlagenpaketen samt Ordnern, zulässigen Assets, Manifest-/Lizenz-/Regel-/ID-Mappings und strengem Ausschluss echter Weltzustände beschlossen. **02.88** fragt nach späteren versionssicheren Updates bereits importierter Vorlagen ohne automatisches Überschreiben eingesetzter Weltinstanzen.