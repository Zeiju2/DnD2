# AdventureShift – Karten-Workshop: Beschluss 02.109 C – begrenzte Chatmeldungen und Moderation

**Stand:** 13.10.2026 – Fachbeschlüsse 02.1 bis 02.109; nächste offene Frage 02.110  
**Status:** Verbindlicher fachlicher Beschluss, konzeptioneller Umsetzungs- und Testplan; **keine implementierte Software**, finale API, Datenbankstruktur, globale Kampagnen-Einstellungsführung, festen Fristen oder MVP-Priorität.  
**Bezüge:** [02.25 Defaults und Ausnahmen](KARTEN-WORKSHOP.md) · [02.5 Fog, 02.54–02.64 NPC-Wissen, 02.65–02.67 Geheimwürfe](KARTEN-WORKSHOP.md) · [02.94–02.98 private Notizen, Spieler-Marker und optionaler Generator](KARTEN-WORKSHOP-02.98.md) · [02.99/02.100 echte manuelle Ergebnisse/Korrektur](KARTEN-WORKSHOP-02.100.md) · [02.101–02.104 Meldungen/Acks/Audit](KARTEN-WORKSHOP-02.104.md) · [02.105 C Chat An/Aus bei Kampagnenerstellung](KARTEN-WORKSHOP-02.105.md) · [02.106 C berechtigte Kampagnen-/Gruppen-/DM-/SL-Kanäle](KARTEN-WORKSHOP-02.106.md) · [02.107 C heutige und historische Sichtrechte und Retention](KARTEN-WORKSHOP-02.107.md) · [02.108 C versionierte Edits, Zurückziehen/Entfernung](KARTEN-WORKSHOP-02.108.md) · [Workshop Kommunikation 11](FEATURE-WORKSHOP.md).

## 1. Verbindliche Entscheidung 02.109 – Variante C

**Vom Projektinhaber gewählt: C – konfigurierbares, fallbezogenes Melden problematischer Chatnachrichten und gesondert berechtigte Moderation mit datensparsamem Belegzugriff.** In Kampagnen mit **aktivem Chatmodul nach 02.105 C** dürfen unter gültiger **02.25-Kampagnen-/Kanaltyp-/Kanal-/Gruppen-/Rollen-/Personen-/Nachrichtenartpolicy** und markierten fachlich zulässigen Ausnahmen **konkret tatsächlich aktuell berechtigte Nachrichtenteilnehmer** eine **ihnen bekannte und heute lesbare Nachricht** aus nach 02.106 C erlaubten Kampagnen-, Gruppen-, Einzel-/Mehrpersonen-Direkt- oder SL-bezogenen Kanälen bewusst melden. Die Leitung kann fachlich geeignete Meldeschalter sowie getrennte Rechte für Melden, eigenen Fallstatus, Fallzuweisung, minimalen Fallbeleg, Überprüfung, Maßnahme, Abschluss und Audit festlegen.

**Kein pauschaler Zugang zu privaten DMs:** Eine Meldung von Nachricht X aus einer persönlichen Unterhaltung gibt der SL **nicht automatisch den gesamten DM-Verlauf, die anderen Nachrichten, verborgene Channelnamen, frühere Nachrichtenversionen, private Notizen oder andere Gesprächspartner** frei. Nur ein **konkret für den gemeldeten Fall, die Nachrichtenversion und die für diesen Zweck erlaubten Felder berechtigter Moderator** darf zulässige Belege sehen. Gibt es keine passende Erlaubnis auf den Textbeleg, darf ein Moderator nur rechtmäßig minimale Verwaltungsmetadaten sehen, nicht geheimen Inhalt aus einem Report-Bypass.

**Meldung ist kein Schuldspruch:** Jeder Report ist eine behauptete Beanstandung, keine automatische Feststellung. Maßnahmen wie eng begrenztes Nachrichtentext-Ausblenden/Entfernen nach 02.108, getrenntes Chat-Schreibrecht einschränken, Fall schließen und berechtigt weitergeben müssen jeweils **eigenständig genehmigt, aktuell berechtigt, begründet und nachvollziehbar protokolliert** werden. Niemals World-/Quest-/NPC-/Würfel-/Tür-/Alarm-/Node-/Timer-/Turn-Effekt allein durch Reporttext, Chatinhalt oder Moderationsentscheidung.

**Nicht gewählt:** A (kein Meldetool als einzige Kampagnenlösung) und B (uneingeschränkte pauschale DM-Einsicht und stille Löschung durch alle SL). Innerhalb von C darf der optionale Meldungs- und Moderationskomfort pro Kampagne und Kanal ausdrücklich aus sein; echte Auth-/Secret-/Nachrichtenintegritätsprüfungen bleiben unangetastet.

## 2. Konfigurierbare Rechte und Maßnahmen

| Recht / Aktion | Eigene fachliche Berechtigung | Grenze |
| --- | --- | --- |
| **Nachricht melden** | Bericht über tatsächlich aktuell sichtbare konkrete Channel-/Message-/Revisions-ID durch berechtigte Lesende | Bewusster Meldeakt, kein Löschen, kein automatische Strafe |
| **Eigenen Fallstatus sehen** | Nur eigenen zulässigen Status nach aktuellen Kampagnen-/Report-/Privatrechten abrufen | Keine geheimen SL-Notizen, fremden Reporteridentitäten oder ganzen DM-Akte |
| **Zuständige Fälle auflisten** | Explizit zugewiesene Fälle plus aktuelle Fall-/Kanal-/Quellrechte | Keine universelle Moderations-Inbox aller privaten Chats |
| **Fallbeleg lesen** | Eigenständiger fallgebundener minimaler Evidence-Grant für konkrete Nachricht/Revision/Felder | Keine pauschale Freigabe umgebender privater Unterhaltung |
| **Fall bewerten** | Separates Review-/Decision-Recht und ggf. explizite zusätzliche Freigabe | Prüfstatus allein kein Nachrichteneingriff |
| **Nachricht entfernen/ausblenden** | Spezifisches Moderationsrecht nach Kanal/Message/Revision plus 02.108-Edit-/Historienvorgaben | Originales Senden, Autor-/Empfängerbindung nicht heimlich ändern |
| **Chat-Schreiben einschränken** | Eigens erlaubtes Restriktionsrecht für bestimmte Person/Rolle/Gruppe/Channel und ggf. Zeitfenster | Nur Chat-Sendpfad betroffen, nicht Steam, Würfeln, Karte oder Quest |
| **Fall schließen/weitergeben** | Explizites Closing-/Escalation-Recht mit gültiger Zielrollenpolicy | Begründeter Auditbeleg und nur berechtigte Felder weitergeben |
| **Audit lesen** | Gesondertes tatsächliches Fall-/Evidence-/Rollen-/Quell-Auditrecht | SL/Administration allein kein Lesen aller DMs oder früheren Revisionen |

**Policyhierarchie:** Chat **An** nach 02.105 → erlaubter Channeltyp/Channel/Recipient aus 02.106 → **heutige und historische** Sicht-/Empfängerrechte aus 02.107 → 02.108-konforme tatsächliche Nachrichten-/Revisions-/Retentionlage → eigene 02.109-Report-/Evidence-/Review-/Action-Policies unter 02.25-Defaults/Ausnahmen. Source-/Fog-/NPC-/Quest-/Notiz-/Geheimwurf-ACLs können durch Melden, Marker oder SL-Status nicht ausgeschaltet werden.

**Verschiedene Moderationsrollen:** Je Kampagne können nach echten jeweiligen Berechtigungen SL, Co-SL oder ausdrücklich beauftragte Moderatoren nur die geeigneten erlaubten Kanaltypen/Fälle verwalten. Globale Kampagnenverwaltung bedeutet nicht automatisch freie Lese-/Bearbeitungsberechtigung für einzelne private Gespräche. Bei mehreren Kampagnen bleiben Berichtskorrelationen und Moderationsentscheidungen isoliert.

## 3. Meldeablauf und minimaler fallbezogener Beleg

1. **Bewusste Auswahl:** Der Reporter sieht die relevante Chatnachricht bereits rechtmäßig in seinem eigenen 02.106-/02.107-Channel-/Verlauf. Er wählt einen vorhandenen gültigen konkreten Message-/Revision-Scope, nicht eine frei erfundene versteckte DM-ID.
2. **Aktuelle serverseitige Prüfung:** Kampagne, echtes Mitglied, Channel/Recipient/Report-Schalter, ursprüngliche historische 02.107-Empfängerperiode, heutige tatsächliche Leseberechtigung, 02.108-Revisions-/Withdraw-/Retentionstatus und erlaubter Meldungsgrund werden erneut geprüft.
3. **Minimales Fallereignis:** Neue echte Report-ID mit meldender Identität, Kampagne, konkretem Nachricht-/Revisions-/Kanal-/Empfänger-/Policyversionbezug, erlaubter Kategorie und ggf. freiwilligem Grundtext. Freitext ist untrusted, keine ausführbare Anweisung, kein automatisch gültiger Moderationsbefund.
4. **Fallbeleg begrenzen:** Falls diese Nachrichtenversion nach 02.107 tatsächlich noch vorhanden ist und für den konkreten Reportingzweck legitim minimal gesichert/zugänglich gemacht werden darf, nur die **konkrete gemeldete Text-/Revisionseinheit** eng zweck- und rollenberechtigt referenzieren bzw. mit ausdrücklich zulässigem Mindestumfang als beschränkten Fallbeleg erfassen. Kein Pauschal-Snapshot des privaten Kanals.
5. **Flüchtiger Chat:** Ist die flüchtige Nachricht schon nicht mehr serverseitig tatsächlich abrufbar, nicht behaupten, es existiere noch eine geprüfte Originalfassung. Ggf. zulässige minimale Sachverhaltsmeldung ohne bestätigten Textbeleg, keine erfundene Schattenhistorie.
6. **Änderung seit dem Report:** Meldung bezieht sich eindeutig auf die wirklich gemeldete konkrete Revision. Wurde danach editiert/zurückgezogen, alte Revision nur unter gesonderter legitimer 02.107-/02.108-Historien- und Fallbeweisberechtigung offenlegen, ansonsten neutralen Status statt heimlichen Reveal.
7. **Gezielte Zuständigkeit:** Report nicht automatisch an alle SL und Spieler pushen. Nach aktueller Rollen-/Kanal-/Fallpolicy zugelassene Moderatoren erhalten nur entsprechende bereinigte Cases; kein Report-/Unread-/Count-/Timing-Leak bei geheimen DMs.
8. **Separate Bearbeitung:** Lesen, Bewerten, Entscheiden und Entfernen/Restriktieren jeweils mit eigenem, unmittelbar vor dem tatsächlichen Commit neu geprüftem Recht. Fall-Preview und Antragsstatus sind nicht automatisch ausführende Aktionen.

**Beweissicherung vs. Retention:** 02.109 ist keine Erlaubnis für unbegrenzte, unbemerkte Kopien sämtlicher privater Chats. Fallgebundener textlicher Beleg darf nur unter konkret berechtigter Zweck-/Aufbewahrungs-/Datenschutzpolicy gespeichert und später wieder abgerufen werden. Nach Ablauf der tatsächlichen 02.107-Messageretention darf keine normale Chat-History aus einem Moderationsdatensatz rekonstruiert werden. Wo keine valide Evidenzgrundlage vorliegt, darf nicht so getan werden, als sei der Textinhalt geprüft worden.

## 4. Moderationsentscheidung und Grenzen

**Fachlicher Statusentwurf:** Gemeldet → aktuell berechtigt zugewiesen → in Prüfung → begründete Entscheidung mit ggf. explizit freigegebener Maßnahme → abgeschlossen / berechtigt weitergegeben / sachlich nicht belegbar. Ein Fall darf ohne Maßnahme geschlossen werden; mehrere identische Meldungen sind kein Beweis für den behaupteten Verstoß.

**Mögliche Maßnahmen im beschlossenen Umfang:**
- **Keine Sanktion / Fall schließen:** Nur begründeter Fallbeleg, keine Veränderung des Chat- oder Weltzustands.
- **Konkrete zulässige Nachricht ausblenden, zurückziehen oder moderativ entfernen:** Nur mit 02.108-kompatibler einmaliger typisierter Message-/Removal-/Revision-Operation und begrenzter aktueller Moderator-Capability; damals wirklich sichtbarer Text bleibt historisch als gesehen behandelt.
- **Chat-Schreibrecht einer bestimmten Person/Rolle/Gruppe im konkret berechtigten Channel-Scope zeitweise oder anderweitig nach fachlich gültiger Policy beschränken:** serverseitig wirksames Chat-Send-Gateway, nachvollziehbare Ziel-/Grund-/Actor-/Policy-/Versions-ID; kein automatischer Kampagnenausschluss oder Spielen-stopp.
- **Begrenzte berechtigte Fallweitergabe:** Nur an rechtmäßig zuständige Bearbeiter mit eigenem engeren Evidence-/Falldatengrant und Audit; keine vollständigen privaten Chatverläufe ungeprüft kopieren.

**Nicht automatisch beschlossen:** Spotify-/Steam-/Kontosperren, Bann über alle Kampagnen, automatische KI-/Voice-/Transkriptmoderation, globales Abhören von DMs, automatische externe Anzeigen oder Meldeportale, dauerhafte Nachrichtenschattenkopien, ungeprüfte Sanktionen allein durch Reportanzahl oder ein konkretes Einspruchs-/Fristsystem. Dies bedürfte einer eigenen späteren Policy-/UX-Entscheidung.

**Einzelfall-Privatsphäre:** Sender/Meldender, konkrete Nachricht, Channel-/Empfängerliste, Reportgrund, Belegtext, interne Notizen, Maßnahmen und Fallstatus dürfen nur nach eigenem aktuellen Fall-/Recipient-/Fieldrecht erscheinen. „Moderator“ reicht nicht für jeden anderen Privatchat. Notwendige Reporter-Vertraulichkeit gegenüber anderen Spielern und Betroffenen einplanen; mögliche zulässige Fallbenachrichtigungen später separat spezifizieren.

## 5. Technische Konzeptobjekte und Konsistenz

**Kandidaten, noch keine API/DB-Verträge:** ChatReportPolicy, ChatMessageReport, ChatReportCase, ChatReportReason, ChatScopedEvidenceGrant, ChatReportEvidenceSnapshot, ChatModerationCaseRole, ChatModerationDecision, ChatModerationAction, ChatSendRestriction, ChatModerationAuditReceipt, ChatCaseVisibilityProjection, ChatModerationOperationId.

**Korrelationen:** Kampagnen-ID, tatsächlicher Sender, Reporter, 02.106-Channel, ursprüngliche 02.107-Nachrichten-/Recipient-/Policy-/Membershiprevision, 02.108-Nachrichtenstatus-/Editrevision, jetzige Sicht-/Beweisberechtigung, verantwortlicher Moderator/ggf. ausdrücklich anderer Genehmiger, Case-/Action-/Receipt-/Policy-/Versions-/Operation-/Zeitbeleg. Kein Vertrauen auf vom Browser selbst als wahr behauptete Rollen, Message-IDs, Evidence-Hashes, gemessene Fristen oder „Kanal ist öffentlich“-Flags.

**Race-/Replay-Schutz:** Dieselbe Meldung mehrfach senden, Duplicate-Reports durch Reconnect, zwei Moderatoren gegensätzlich, zugleich Nachrichten-Edit/Withdraw, ablaufende Retention, Gruppenaustritt, Wegfall der Zuständigkeit, Chat-Schalter Aus/An oder Serverneustart dürfen nicht doppelte Strafen, unberechtigte Beleglecks, Nachrichtenwiederherstellung oder doppelte Nachrichtentfernung bewirken. Vorgänge als type-/version-/idempotenzgesicherte Ereignisse mit eindeutiger Actor-/Scope-/Operation-ID und aktuellem Authorisierungscheck beim wirklichen Commit führen. Ein Stale-Review wird nicht als sofort gültige Maßnahme umgesetzt.

**Geheimnisschutz in jeder Oberfläche:** Inbox, Reportliste, Case-Suchfilter, Dashboardzählung, Badge, Realtime-Abos, Export, Snippets, Fehlermeldungsdetails, Autocomplete, Debug/Serverlogs und Replayprojektionen müssen pro Empfänger/Field, **heutiger und historischer** Nachrichtenzugehörigkeit sowie Report-/Moderationsrechte geprüft werden. Auch Existenz/Zeitpunkt einer geheimen DM-Meldung dürfen durch Counts oder Fehler nicht abgeleitet werden.

**02.105 global Chat Aus:** Keine gewöhnlichen neuen Chat-/Report-/Send-/Subscribe-/History-/Message-Edit-Aktionen über den normalen Spielbetrieb. Unabhängig begründete datenschutz-/sicherheitsrechtliche Verwaltung vergangener legitimer Fall-/Chatdaten muss getrennt autorisiert sein und darf nicht als allgemeiner Schreibkanal versteckt aktiv bleiben. Karten, Charaktere, Spieler-Notizbuch, Würfel- und Systemprotokoll, 02.101-Hinweise und 02.102/02.103-Acks/Reminder bleiben selbständig.

**Strikte Weltwirkungsfreiheit:** Report, Meldungsgrund, Moderatorentext, Einsehen von Fallbelegen, Schreiben sperren, Message entfernen oder Fall schließen dürfen keinerlei echten Tür-/Code-/Quest-/NPC-/Würfel-/Alarm-/Sensor-/Node-/Timer-/Turn-/Inventarbefehl erzeugen. Ein regelwirksames Spielereignis benötigt weiterhin separate ursprüngliche 02.99-/02.100- oder andere konkret autorisierte Eventaktion.

## 6. Konzeptioneller Umsetzungsplan – noch kein Code

1. **Separaten 02.109-Policyresolver ausarbeiten:** Chat global 02.105, 02.106-Channeltyp, 02.107-aktuelles+historisches Rechte-/Retentionfenster und 02.108-Message-Revision als Voraussetzung; getrennte Report-, ReadOwnCase-, AssignedReview-, ScopedEvidence-, Close-/Forward-, Remove- und RestrictSend-/Audit-Capabilities unter 02.25-Defaults/markierten Ausnahmen.
2. **Fallbeleg-/Reportzustände modellieren:** Echte stabile Message-/Revision-/Recipient-/Channel-/Policyreferenz, Reporter, minimale Kategorie, besondere getrennt berechtigte fallgebundene Originaltext-/Revision-Belege nur falls zulässig; Deduplikation, Retention und Schutz vor Schattenchatarchiv.
3. **Serverseitigen Melde-Gateway entwerfen:** Nur aktuell und historisch sichtbare konkrete Nachricht melden; echte Actor-, Role-, Target-, Channel-, Report-Schalter- und Scopeprüfung, Spam-/Rate-/Duplicate-/Race-/Replay-Schutz, keine secret Entity-ID-Orakel.
4. **Fall-Inbox-/Beweisprojektion:** Status, erlaubte Kanal-/Message-/Autor-/Reporter-/Belegfelder pro heutigem Assigned-Moderator und tatsächlichem fallbezogenem Evidence-Grant; kein allgemeiner SL-Privatnachrichtenleser.
5. **Getrennten Maßnahmen-Gateway:** Einzelne neue 02.108-kompatible Revision-/Removal-Aktion und eigene, idempotente Channel-/Person-/Zeitscope-Schreibrestriktion, mit effektfreier Preview, aktuellem revalidiertem Entscheidungsrecht und Audit.
6. **Notification und Reconnect:** Minimal erlaubte eigene Reporterstatus-/Moderatorstatus-Projektionen, sichere Rollen-/Gruppen-/Policy-Revocation, Ablauf des Belegfensters, veraltetes Edit/Withdraw, doppelte Moderatorenaktionen, Server-Restart/Retry; kein Leak über Counts/Debug.
7. **Spätere Bedienoberfläche und Abhängigkeiten:** Eigener sichtbarer Meldeweg an tatsächlich erlaubter Nachricht, rechtlich/fachlich klare anforderbare Nachweise, Datenschutz-/Moderations-/Einspruchs-UX und Gesamt-Kampagneneinstellungsassistent erst nach vollständigem Featureworkshop.

## 7. Fachliche Abnahmetests

| Test | Erwartung |
| --- | --- |
| Kampagne mit Chat Aus erstellt | Normale Chat-/Report-/Edit-/Subscribe-/Historypfade serverseitig gesperrt, Würfel/Notizen/Karten/Systemhinweise unverändert |
| Aktivierter Kampagnenchat mit freigegebenem Meldetool | Tatsächlich berechtigter Spieler darf eine ihm sichtbare konkrete Nachricht melden, kein unbeabsichtigter Message-Effekt |
| Gruppenkanal nur für Späher | Außenstehende dürfen Nachrichten weder melden noch in Fallliste/Badge/Autocomplete identifizieren |
| Fremde, erratene private DM-/SL-only-Message-ID | Kein Report, kein Secret-/Teilnehmer-/Count-/Zeit-Leak |
| Meldung eigener heute noch sichtbarer DM | Nur zulässige fallgebundene Belege; keine Freigabe kompletter privater DM-Historie |
| SL besitzt Kampagnenadminrolle, aber keinen konkreten privaten Evidence-Grant | Keine geheime private DM-Beleg-/Reporttexteinsicht |
| Eigenständiger zugewiesener Moderator mit gültigem Case-Grant | Nur die konkret freigegebene Message-/Revision-/Feldprojektion, kein Nachbarchat |
| Meldende Person hat Gruppe inzwischen verlassen | Historische alte Teilnahme ist kein automatisches heutiges Lesen/Melden |
| Nachricht bereits rechtmäßig bearbeitet/zurückgezogen | Report referenziert echte Version; alte Texte nur wenn 02.107-/02.108- und Beweisrechte es heute erlauben |
| Flüchtige ursprüngliche Nachricht nicht mehr vorhanden | Keine erfundene reproduzierte Historie; ggf. nicht textlich belegbarer Fallstatus |
| Doppelte Report-Klicks / hoher Melde-Spam | Rate-Limit/Idempotenz, keine automatische Feststellung oder Flut an SL |
| Reporter sieht offenen Fall | Nur eigener erlaubter Status, keine anderen Reporter/privaten SL-Fallnotizen |
| Moderator darf Fall lesen, aber nicht entfernen | Kein unberechtigter Change im 02.108-Message-Gateway |
| Berechtigter Moderator entfernt genau eine Nachricht | Neue protokollierte, versionierte Removalaktion mit korrekt nur erlaubt sichtbarer Projektion |
| Channel-Schreibrecht durch berechtigten Entscheid gesperrt | Server verweigert neue Sendung für konkret eingeschränkte Person/Kanal, andere Spielaktionen bleiben zulässig |
| Restriktion wird durch manipulierte Chat-API umgangen | Keine unberechtigte Nachricht, echte Serverpolicy bleibt wirksam |
| Zwei Moderatoren entscheiden widersprüchlich gleichzeitig | Transaktion/Versionscheck, keine doppelte oder inkompatible Aktion |
| Chatrolle wird vor Case-Öffnung entzogen | Veraltete Inbox/Realtime liefert keine unberechtigten Textbelege/Counts |
| Nachricht läuft nach 02.107 ab | Kein unautorisiertes dauerhaftes Schattenreportarchiv, Beweiszugriff folgt eigener zulässiger Retentionpolicy |
| Berichtstext lautet „Quest gelöst“ oder „Tür öffnen“ | Keine Welt-/Door-/Quest-/Würfel-/Node-/Turnwirkung |
| Moderation aus Kampagne A liest Nachricht aus Kampagne B | Kein Zugang/Verbindung der beiden Kampagnenscopes |
| Report wurde geschlossen, Serverreconnect/retry | Konsistente echte Einmaligkeits-/Auditbelege, kein erneutes Entfernen/Schreibrestriktions-Event |
| Kein Missionsgenerator/keine Voice-Integration | Melde-/Moderationsplan bleibt unabhängig; Voicechat-first-Nutzung bei Chat Aus funktioniert weiter |

## 8. Beschlussgrenze und Folgefrage

**Jetzt beschlossen:** **02.109 C**, also konfigurierbare, bewusst ausgelöste Meldungen **aktuell wirklich sichtbarer einzelner Chatnachrichten**, streng eingeschränkte und zweckgebundene Moderator-/SL-Beweissicht, selbständige Rollenrechte für Report/Review/Case/Remove/RestrictChatSend/Close/Escalate/Audit sowie datensparsame nachvollziehbare Entscheidungen. **Keine** pauschale DM-Auslesbarkeit für jede SL, keine automatische Weltwirkung, keine beliebige Schattenaufzeichnung. **02.105 Chat An/Aus bei Kampagnenerstellung, 02.106-Kanalscopes, 02.107-Historien-/Retentionrechte und 02.108-Edit-/Withdrawrechte bleiben vollständig verbindlich.**

**Offen:** Exakte Moderationsoberfläche, konkrete Fristen, zulässige case-spezifische Beweisaufbewahrung, Einzelheiten zu Kontaktblockierung/Benachrichtigungsfiltern, Einspruch/Feedback an Betroffene, technische Tabellen/API, MVP-Priorität und Gesamt-Einstellungsassistent nach allen Featureentscheidungen.

## Nächste Entscheidung 02.110 – Persönliche Stummschaltung und Kontaktblockierung im optionalen Chat

**Beispiel:** Ein Spieler will vorübergehend bestimmte Gruppenchat-Hinweise stummschalten oder keine privaten Direktnachrichten mehr von einer anderen Person erhalten. Die SL soll nicht jeden unerwünschten Kontakt erst durch einen 02.109-Moderationsfall lösen müssen.

- **A – Keine persönlichen Filter:** Chatnutzer können empfangene erlaubte Kanäle und Direktpersonen weder stummschalten noch aus eigenen Nachrichtenfiltern ausschließen.
- **B – Absolutes Blockieren aller Informationen:** Ein persönlicher Block-Schalter verhindert auch zwingende offizielle Sicherheits-/Moderationshinweise, echte wichtige 02.101–02.103-Mitteilungen, autoritativen Spielzustand und jede berechtigte SL-Verwaltungskommunikation.
- **C – Konfigurierbare persönliche Lautlos- und DM-Kontaktfilter (Empfehlung):** Nach Kampagnen-/Kanal-/Rollenstandard mit zulässigen 02.25-Ausnahmen können Spieler **eigene Chatbereiche und deren optionalen Hinweiston stummschalten** oder **direkte Nachrichten einzelner Personen für sich blockieren**, soweit dazu tatsächliche berechtigte Policy besteht. Es werden dadurch keine fremden Kanal-/Secretrechte geschaffen, keine echten Spielwelt-/Questzustände verändert und **keine zwingenden autoritativen Sicherheits-, Korrektur- oder Moderationsmitteilungen unterdrückt**. Details erst mit 02.110 beschließen.
