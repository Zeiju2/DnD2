# AdventureShift – Karten-Workshop: Beschluss 02.106 C – konfigurierbare Chatbereiche

**Stand:** 13.10.2026 – Beschluss 02.106 C; Folgeentscheidung 02.107 C zur berechtigten Chat-Historie beschlossen, nächste offene Frage 02.110  
**Status:** Verbindlicher fachlicher Beschluss und konzeptioneller Umsetzungs-/Testplan; **noch keine Softwareimplementierung**, endgültige API/Datenbank, fertige UI, Kampagnenassistenten-Reihenfolge oder MVP-Freigabe.  
**Bezüge:** [02.25 globale Kampagnenvorgaben/markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.5 Sicht/Fog, 02.54–02.64 NPC-Wissens-/Gruppenrechte](KARTEN-WORKSHOP.md) · [02.65–02.67 geschützte Würfel/Audit](KARTEN-WORKSHOP.md) · [02.93–02.98 optionaler Generator, private Notizen, Spieler-Kartenpins und Kampagnen-Automatisierung](KARTEN-WORKSHOP-02.98.md) · [02.99 manuelle Ergebnisse](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 Notice-/Ack-/Reminderschutz](KARTEN-WORKSHOP-02.104.md) · [02.105 C kontrollierte Ack-Neuanforderung und **optionaler Chat An/Aus bei Kampagnenerstellung**](KARTEN-WORKSHOP-02.105.md) · [Kommunikationsbereich 11](FEATURE-WORKSHOP.md).

## 1. Verbindliche Entscheidung 02.106 C

**Vom Projektinhaber gewählt: C – konfigurierbare, tatsächlich berechtigte Chatkanäle.** Bei der Erstellung einer Kampagne lässt sich der **integrierte Spiel-/Textchat als Ganzes weiterhin eigenständig und wirksam an- oder ausschalten (02.105)**. Nur wenn er **aktiv** ist, kann die Spielleitung nach gültigem Kampagnen-/Regel-/Rollen-/Gruppenstandard und zulässigen **markierten 02.25-Ausnahmen** diejenigen Kanal-/Gesprächsformen erlauben, die die Gruppe nutzen soll: gemeinsamer **Kampagnenchat**, **Gruppen-/Teamchat**, **direkt adressierte Einzel-/Mehrpersonenunterhaltung** und geeignete **spielleitungsbezogene Kanäle/Kommunikation**. Es besteht **keine Pflicht, alle vier Formen zu aktivieren**. Jede Form hat eigene Rechte für Sichtbarkeit, Erstellen, Beitreten, Lesen, Schreiben und Verwaltungen sowie pro tatsächlich unterstütztem Scope nachvollziehbare Ausnahmen.

**Nicht gewählt:** Variante A (nur ein gemeinsamer Chat als einzig mögliche Lösung) und Variante B (alle privaten, Gruppen- und SL-Nachrichten ungeprüft allen verfügbar machen). Ein **einziger gemeinsamer Chat** darf sich aber durch die C-Konfiguration als einfache Kampagne ergeben, wenn nur dieser Kanaltyp aktiviert wird.

**Beispiel:** Bei der Kampagnenerstellung wählt die SL `Chat An`, erlaubt einen gemeinsamen Kampagnenkanal, ausgewählte Gruppenkanäle und Direktnachrichten an konkrete Empfänger. Die Gruppe „Späher“ darf in ihrem Gespräch Hinweise besprechen, ohne diese allen anderen Spielerclients zu senden. Ein Spieler kann eine bewusst an eine berechtigte SL-Adresse gerichtete private Nachricht verfassen, ohne dass alle Kampagnenmitglieder dieselbe Nachricht erhalten. Eine separate SL-interne Unterhaltung darf – wenn dafür explizit erlaubt – nur tatsächlich berechtigten Rollen sichtbar sein. **Die Teilnahme als SL allein ist keine pauschale Erlaubnis, private Spieler-zu-Spieler-Direktnachrichten mitzulesen.**

## 2. Chat-On/Off auf zwei fachlich getrennten Ebenen

| Ebene | Fachliche Bedeutung und Pflichten |
| --- | --- |
| **Kampagnenweites Chatmodul Aus (02.105)** | Serverseitig keine neuen Chat-Nachrichten, Kanal-Erstellung, aktive Chat-Subscription oder normalen Chatverlaufsabrufe durch Spieler; Oberfläche entsprechend deaktiviert. Bestehende rechtmäßig gespeicherte Daten nicht unbemerkt löschen/veröffentlichen; streng autorisierte Archiv-/Aufbewahrungsvorgänge als gesonderte spätere Regel. |
| **Kampagnenweites Chatmodul An (02.105)** | Chatfähigkeit grundsätzlich verfügbar, aber **noch keine pauschale Berechtigung** zum Lesen/Schreiben in jedem Kanal. Pro Typ/Instanz gültige Kanaleinstellungen und aktuelle Mitgliedschaft prüfen. |
| **Kanaltyp deaktiviert** | Auch bei globalem Chat An darf die betreffende Art (z. B. Direktnachricht) weder über sichtbare UI noch manipulierte API für neue Sendungen/Kanalaktionen genutzt werden. Andere aktivierte Kanaltypen funktionieren gemäß ihren Berechtigungen weiter. |
| **Kanal-/Gruppen-/Personenausnahme** | 02.25-Standard gilt, soweit die konkrete fachlich zulässige Ausnahme und die tatsächliche Quell-/Empfänger-/Objektsicht gelten. Eine Ausnahme darf keine geheimen SL-Daten, fremde DMs oder andere Kampagnen unautorisiert freigeben. |
| **Späteres Umschalten** | Geschützte bestehende Daten und Channel-Revisionen unter Bestandsschutz; keine rückwirkend für alle öffentlich gemachten Nachrichten, keine stillschweigende Löschung. Offene Echtzeitabos dürfen nach Entzug nicht weiterliefern. |

**Unabhängige Systemfunktionen:** Würfel-/Server-Eventfeed, Spieler-Freitextnotizbuch, 02.101-Korrekturmitteilungen, 02.102-Acks, 02.103-Reminder, Karten, echte manuelle 02.99-/02.100-Aktionen und externe Voicechat-Kommunikation werden **nicht** durch Chat Aus deaktiviert. Mitteilungen aus anderen Modulen dürfen auch **nicht** heimlich in unberechtigte Chatkanäle gespiegelt werden.

## 3. Grundtypen der Chatkanäle

| Kanaltyp | Geplante Empfänger-/Rechteidee | Grenzen |
| --- | --- | --- |
| **Gemeinsamer Kampagnenchat** | Bewusst freigegebener Gesprächskanal für aktuell dafür berechtigte Kampagnenmitglieder, mit eingeschränkten Rollen-/Gast-/Gruppenausnahmen | Nicht „öffentlich im Internet“; Kampagnenmitgliedschaft und gültige Send-/Leserechte bleiben Pflicht |
| **Gruppenchat / Teamchat** | Nur nach aktueller ausgewählter Gruppe, erlaubtem Channel-Scope und ggf. ausdrücklich eingeladenen berechtigten Teilnehmern | Mitgliedschaftswechsel oder Umbenennung darf nicht unkontrolliert neue oder alte Nachrichten freigeben |
| **Direkt-/Privatnachricht (DM)** | Konkrete explizit ausgewählte berechtigte einzelne oder mehrere Empfänger und eigens autorisierter Sender; Empfängerkreis transparent | Standardmäßig nicht an gesamte Kampagne, an alle SL oder die ganze Gruppe senden. Keine automatisch nachträglich erweiterte Empfängerliste |
| **SL-bezogene Kommunikation** | Entweder absichtlich an konkrete berechtigte SL-Personen adressierte Anfrage/Unterhaltung **oder** eigens eingerichteter SL-interner Kanal mit passenden Rollen | Spieler→SL bedeutet **nicht** automatisch jede SL und SL-intern bedeutet **nicht** allen Spielern/Assistenzrollen; keine stillschweigende Offenlegung von Spieler-DMs |

**Keine verfrühte Festlegung:** Ob automatisch Standardkanäle erzeugt, wie Kanäle benannt, wie mehrere Kampagnenräume, Rollen und Untergruppen technisch organisiert, welche Direktadressierungen erlaubt und ob archivierte Nachrichten wieder sichtbar gemacht werden, gehört in die weitere Kommunikationsplanung. 02.106 beschließt **die konfigurierbaren Kanalarten und ihre Sicherheitsinvarianten**, nicht ihre genaue Oberfläche oder die Pflicht, von jeder Art eine Instanz bereitzustellen.

**Private Kommunikation mit sichtbarer Zugriffslogik:** Beim Anlegen/Senden für berechtigte Nutzer vorab anzeigen, **in welchen tatsächlichen Kanal und an welche aktuellen Empfänger** die Nachricht geht; falsche „privat“-Anmutung bei anschließend öffentlicher Zustellung ausschließen. Ein späterer Gruppenwechsel darf nicht still automatisch bisher private Inhalte in eine neue Gruppe überführen. Ob neue Mitglieder alten Verlauf lesen dürfen, ist **nicht automatisch entschieden** und wird mit 02.107 zur Historie/Retention getrennt geklärt.

## 4. Granulare Capability- und Policygrenzen

**Sinnvolle, vorläufige getrennte Rechte:** `createChannel`, `listVisibleChannels`, `discoverRecipient`, `joinChannel`, `readMessage`, `sendMessage`, `invite/removeMember`, `configureChannel`, `archiveChannel`, `manageOwnDM` und spätere Moderations-/Auditberechtigungen. Diese Namen sind **fachliche Entwurfsbegriffe**, keine fertigen API-Routen oder Produkt-Freigabe. `send` bedeutet nicht `readAll`, `read` nicht `editOtherMessages`, `manageChannel` nicht pauschal `readPrivateDM`.

**Schnittmenge zwingend:** Kampagnenchat `An` UND gewünschter Kanaltyp aktiv UND autorisierte Kampagnenmitgliedschaft UND aktuelle Sender-/Empfänger-/Gruppen-/Rollen-/Kanalscopes UND zulässige 02.25-Ausnahmen UND tatsächliche Secret-/Sichtrechte etwa eingebundener Objekte. Eine Chatnachricht oder deren Metadaten sind niemals ein Token, um Zugang zu einem verborgenen NPC, einer geheimen Szene, einem privaten Notizbuch oder einer unpublizierten Quest zu erhalten.

**Jeder echte Zugriff neu prüfen:** Kanal erstellen, Empfänger auflösen, Auflistung/Suche/Autocomplete, Einladen, Senden, Broadcast, Subscription, historischer Abruf, Export, Reconnect, Benachrichtigung/Unread-Count und Moderations-/Adminprojektionen werden **serverseitig** anhand **aktueller** Chat-/Kampagnen-/Rollen-/Gruppen-/Channel-ACL und deren Version geprüft. Nicht nur die UI ausblenden. Abos bei Gruppenentzug/Kanalwechsel wirksam revalidieren und neue unzulässige Sendungen stoppen. Bereits rechtmäßig an menschliche Empfänger offenbarter Text ist nicht aus deren Gedächtnis oder Kopien rückholbar.

**Feld-/Existenzschutz:** Geheime Kanalnamen, Teilnehmer, Nachrichtenanzahl, ungelesene Badge-Zähler, Sendungszeit, private Dialogpartner, Autocomplete-Einträge, Preview und Suchtreffer dürfen keinen versteckten Channel oder fremde private Kommunikation verraten. Ein Gruppenchatscope macht keine versteckte Karte sichtbar; aus Text/Link im Chat dürfen private SL-/Spielernotizen, echte NPC-/Quest-/Kartenmarker nicht über fremde ACL geöffnet werden.

**SL-Rechte ausdrücklich modellieren:** Die Spielleitung kann organisatorische Channel-Policies setzen, ohne deswegen allgemein alle privaten Gesprächsinhalte abrufen zu dürfen. Besondere berechtigte Moderations-/Melde-/Rechtsfälle und Datenschutzhinweise werden erst im Kommunikationsworkshop detailliert spezifiziert; keine versteckte globale Mithörfunktion oder vorweggenommene vollständige Ende-zu-Ende-Verschlüsselungszusage.

## 5. Nachrichten und Wirkungen strikt trennen

Chattext ist **untrusted Nutzereingabe** und wird für UI/Server als Daten verarbeitet, nicht als HTML/JavaScript/SQL/Nodegraph-/Administrationskommando. Sichere Größenlimits, Sanitizing/Escaping, Rate-Limits, Spam-/Missbrauchs- und Reconnectschutz planen. Ein Satz „Türcode 1234“, „Quest erledigt“, „Alarm auslösen“, `/roll 20` oder ein privater NPC-Dialog im Chat ist **ohne eine gesondert bewusst vom Nutzer ausgelöste und nach dem jeweiligen Feature ermächtigte, serverseitig tatsächlich geprüfte Handlung** keinerlei gültiges Welt-/Würfel-/Quest-/Tür-/NPC-/Inventory-/Node-/Timer-/Next-Player-Ereignis. Die Entscheidung, ob es später speziell erkennbare Befehls-UI für Chat gibt, ist **nicht** getroffen; ein unautorisierter Textparser darf keine Autorität erzeugen.

**Andere Inhalte nicht ungewollt spiegeln:** Würfelergebnisse und echte Serverprotokolle aus 02.65–02.67, manuelle Ergebnisse 02.99, Korrekturen 02.100 und geschützte Systemhinweise 02.101–02.103 bleiben eigenständige Kanäle/Module mit eigener Berechtigung und Sichtfeldprojektion. Nur durch künftig **explizit** erlaubte Anzeige-Integration und **gleichzeitige** Quell- und Chat-Zugriffsrechte können dort Ausschnitte erscheinen; das bloße Aktivieren von Chat publiziert weder private Würfe noch SL-Debug noch persönliche Notes.

## 6. Entwurfsobjekte und Umsetzungsplanung

**Konzeptionelle Namen, keine verbindlichen Tabellen/APIs:** `CampaignChatPolicy`, `ChatChannelType`, `ChatChannelPolicy`, `ChatChannelInstance`, `ChatChannelMembership`, `ChatRecipientScope`, `ChatDirectRecipientSet`, `ChatAccessProjection`, `ChatMessage`, `ChatMessageRevision`, `ChatChannelAccessRevision`, `ChatDeliveryOperation`, `ChatSubscription`, `ChatAccessAudit`. Entwurfskennungen: Kampagne, Channel/Type, tatsächlicher Autor, Empfängerscope, Membership-/Policy-/Channelrevision, msg-/operation-/delivery-/correlation-ID. Keine endgültige Aufbewahrungsfrist oder Historie-/Löschregel.

**Schritte zur späteren Umsetzung (nur Architekturplan):**
1. **Kampagnenweite Chatfähigkeits-/Kanaltyp-Policies:** `Chat An/Aus` wirksam bei Erstellung, getrennt pro Typ (Kampagne/Gruppe/DM/SL), aktuelle 02.25-Inheritance und sichere markierte Ausnahmen; nie Auth/Secrets abwählbar.
2. **Channel-/Membership-Resolver:** Serverseitig typisierte Channel-IDs, stabile Mitglieder/Empfänger, kanalspezifische Berechtigungen für Create/List/Join/Send/Read/Subscribe; SL/DM/Group nicht implizit alles-öffentlich oder alles-SL-lesbar machen.
3. **Chat-Transport und Persistenzgrenzen:** Chatpayloads feldberechtigt projizieren, Senden mit Client-/Server-Operations-ID idempotent gegen Doppel-Events, sichere Realtime-Subscriptions und Reconnect; historische Verfügbarkeit und Lösch-/Archivfristen erst 02.107.
4. **Sichere Übermittlung und Moderationsgrundlagen:** Untrusted-Text-Sanitizing, Größenlimits, Abuse-/Rate-Limits, Serverlogs ohne geheime unnötige Chatinhalte, dokumentierbare separate Moderations-Rechte für spätere Planung.
5. **Chat-OFF und Policywechsel:** Keine neuen Channel- oder Message-Operationen bei Chat Aus, technische Sperre und Realtime-Subscription-Entzug, Schutz gespeicherter Altchats ohne stille Weitergabe oder Löschung. Unabhängiger Würfel-/System-/Notiz-/Correction-Feed bleibt aktiv.
6. **UI-Abläufe nur fachlich vormerken:** Sichtbare erlaubte Kanäle, tatsächliche Empfängerauswahl bei DMs und eine erkennbare Grenze zwischen SL-intern/Spieler→SL/Gruppen-/Kampagnenchat. Exakte Fenster/Navigation/Onboarding nach Featureabschluss planen.
7. **Regressionen:** Gruppen-/Rollen-/Channel-/Empfängerwechsel, invite/revoke, Secret-/NPC-/Fog-Rechte, DM-Vertraulichkeit, SL-Admin ohne DM-Leserecht, manipulierter Subscribe/Message-ID, Chat Off bei Creation/Policywechsel, Spam/Duplicate/Reconnect, No-World-Effect und Unabhängigkeit anderer Module.

## 7. Fachliche Abnahmetests

| Test | Erwartung |
| --- | --- |
| Kampagne mit `Chat Aus` angelegt | Keine neuen Chat-Send-/Join-/Subscribe-/Channel-Operationen; Würfel, Karten, freie Notes und autorisierte Systemmeldungen unabhängig |
| Kampagne mit `Chat An`, nur gemeinsamer Kanaltyp freigegeben | Berechtigte Mitglieder können im gemeinsamen Kanal schreiben; verbotene DM-/Gruppen-/SL-Kanaltypen serverseitig gesperrt |
| `Chat An`, Gruppenchat „Späher“ erlaubt | Nur berechtigte tatsächliche Späher-Empfänger erhalten Inhalt, Preview/Unread-Count und Suche |
| Ein anderer Spieler manipuliert Channel-ID auf Späher-Kanal | Kein Abo, kein Nachrichtentext, kein verborgenes Channel-Existenz-/Member-/Count-Leak |
| Direkte Einzel-/Mehrpersonen-Nachricht an konkrete Empfänger | Nur diese aktuell berechtigten tatsächlichen Teilnehmer können den dafür erlaubten Inhalt sehen |
| Ein Spieler adressiert ausdrücklich eine berechtigte SL-Person | Nur die wirklich adressierten/autorisierten SL-Empfänger, nicht automatisch alle SL und alle Spieler |
| SL-interner Kanal angelegt | Spielerseite sieht weder Text noch Existenz/Badge/Teilnehmer; kein Zugang aus SL-Notiz-/Kampagnen-Adminstatus ohne Rechte |
| SL besitzt Verwaltungsrecht, aber kein DM-Leserecht | Keine unbefugte Einsicht in private Spieler-DMs |
| Spieler wird aus Gruppe entfernt, bestehender Realtime-Subscription läuft | Neue unzulässige Zustellungen/Abrufe stoppen; bereits offengelegte Vergangenheit nicht „aus menschlichem Wissen“ zurückholbar |
| Neues Gruppenmitglied tritt bei | Keine automatische pauschale Einsicht in alten privaten Gruppenverlauf ohne gesondert beschlossene 02.107-Historie-/ACL-Regel |
| Chat wird während Kampagne abgeschaltet | Neue Chat-Operationen serverseitig gestoppt, alte Chatinhalte nach Bestandsschutz nicht veröffentlicht/heimlich gelöscht |
| Chat wird später wieder aktiviert | Alte Nachrichten nur nach heutiger gültiger Kanal-/Empfänger-/Bestandsschutzpolicy sichtbar; keine unfreiwillige neue Gruppensicht |
| Spieler sendet `Quest abgeschlossen`, `Türcode 1234` oder `/roll W20` als Text | Keine echte Quest-/Door-/NPC-/Node-/Würfel-/Turn-/Itemwirkung aus bloßem Text |
| Text enthält ausführbares Markup/Script oder überlange Payload | Keine Codeausführung; serverseitige sichere Validierung und Größengrenzen |
| Nachricht doppelt gesendet nach Reconnect | Operations-/Message-ID verhindert unbeabsichtigte doppelte Veröffentlichung |
| Geheimer Würfel, private Spielnotiz und SL-Quest haben eigene ACL | Chatstatus/-freigabe macht diese Daten nicht automatisch in Chat sichtbar |
| Zwei verschiedene Kampagnen des selben Accounts | Keine kanal-/empfängerübergreifenden IDs, History-/Membership- oder Exportlecks |
| Chat global Aus, 02.101 wichtige Korrekturmeldung wird erzeugt | Nur nach eigenen Notice-Rechten richtige Mitteilung/World-State; der ausgeschaltete Chat ist kein erforderlicher Transport |
| Kampagnenerstellung mit Chat An/Aus oder Kanalauswahl | Nur tatsächlich unterstützte wählbare Module, klare Rechte-/Ausnahme-Policy; konkrete spätere UX nicht vorab fixiert |

## 8. Beschlussgrenze und Folgefrage

**Verbindlich entschieden:** Variante **02.106 C**, also konfigurierbare gemeinsame Kampagnen-, Gruppen-, direkte private und geeignete SL-bezogene Chatbereiche mit **getrennten aktuellen Send-/Lese-/Mitgliedschafts-/Verwaltungs- und Empfängerrechten**, 02.25-Defaults/Ausnahmen. 02.105-Chat **An/Aus bei Kampagnenerstellung** bleibt die vorrangige, tatsächlich serverwirksame globale Fähigkeitsgrenze. Geheime SL-/NPC-/Quest-/Fog-/Wurf-/Notizdaten werden nicht durch Chat unberechtigt weitergegeben, und Chattext hat keine automatische Spielweltwirkung.

**Noch offen:** Exakte Kanal-/Empfängereinrichtungs-UI, automatische Default-Channel-Instanzen, Messengerformatierung, Moderation/Meldewege, Such-/Verlaufs- und Lösch-/Archivfristen, konkret technische Kanalberechtigungsdatenbank und MVP-/Release-Prioritäten. Vollständige Kampagnen-Einstellungsmasken erst nach den Featureentscheidungen.

## Archivierte Folgefrage 02.107 – inzwischen als C beschlossen

**Beispiel:** Eine aktive Kampagne nutzt Gruppenchat und Direktnachrichten. Ein Spieler verlässt die Spähergruppe, später tritt jemand Neues hinzu. Einige Nachrichten enthalten private Absprachen oder frühere Informationen, die heute nicht für alle sichtbar sein sollen. Die SL möchte entscheiden können, wie lange der Chatverlauf erhalten bleibt und wer **ältere** Nachrichten sehen darf.

- **A – Immer nur live, kein Verlauf:** Nachrichten werden nach der unmittelbaren Zustellung grundsätzlich nicht als abrufbarer Verlauf gespeichert. Nach Reconnect oder Neustart bleiben keine Chattexte zugänglich.
- **B – Dauerhaft für alle offen:** Alle ehemaligen Nachrichten bleiben für immer abrufbar und werden auch neuen Gruppenmitgliedern, früher unbeteiligten SL und anderen Kampagnenteilnehmern unabhängig von ihren damaligen/aktuellen Rechten angezeigt.
- **C – Konfigurierbarer, berechtigungssicherer Chatverlauf (Empfehlung):** Pro Kampagne/Kanaltyp/Gruppe bzw. zulässigen 02.25-Ausnahmen darf die SL zwischen geeignetem flüchtigem oder gespeichertem Verlauf, passenden Aufbewahrungs-/Archivregeln und **getrennten historischen Leserechten** wählen. Neue Gruppenmitglieder erhalten nicht automatisch alte private Nachrichten; Revocation, aktueller Zugriff und die historische Empfängerbindung werden serverseitig geschützt geprüft. Details zu Löschung, Bearbeiten und Moderation folgen separat.

**Aktueller Fortgang:** [02.107 C](KARTEN-WORKSHOP-02.107.md) hat flüchtige oder gespeicherte Chatverläufe, geeignete Aufbewahrung/Archiv und getrennte aktuelle/historische Empfänger-/Kanal-/Gruppenrechte verbindlich beschlossen. **Neue Gruppenmitglieder, spätere SL und fremde Direktnachrichten-Teilnehmer erhalten private frühere Texte nicht automatisch.** Chat bei Kampagnenerstellung An/Aus und einzeln konfigurierte Chatbereiche bleiben. **02.108 C** hat nach gültiger Kanal-/Personen-/Nachrichtenpolicy kontrollierte, versioniert nachvollziehbare eigene Edits/Zurücknahmen und eng berechtigte Entfernung beschlossen [Detail](KARTEN-WORKSHOP-02.108.md). **02.109 C** hat berechtigt eingeschränkte Meldungs-/Moderationsabläufe mit minimalem Fallbeweis statt globaler SL-DM-Einsicht beschlossen [Detail](KARTEN-WORKSHOP-02.109.md). **02.110** fragt nach persönlichen Kanal-Lautlos-/DM-Kontaktfiltern.
