# AdventureShift – Karten-Workshop: Beschluss 02.129 C – persönliche Chatkanal-Favoriten, Sortierung und Einklappbereiche

**Stand:** 14.10.2026 – Fachbeschlüsse 02.1 bis 02.129; nächste offene Frage 02.130
**Status:** Verbindlicher Fachbeschluss mit konzeptioneller Umsetzung und Abnahmetests; **noch keine Softwareimplementierung**, kein finales Datenbank-/API-/UI-Schema und keine MVP-Priorisierung.
**Bezüge:** [02.25 – Kampagnenstandards und markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.94–02.98 – selbstständige Spieler-Notizen](KARTEN-WORKSHOP-02.98.md) · [02.99 – autorisierte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.101–02.104 – offizielle Notices/ACKs](KARTEN-WORKSHOP-02.104.md) · [02.105 – Chat An/Aus](KARTEN-WORKSHOP-02.105.md) · [02.106 – echte Kanal-/Gruppen-/DM-/SL-Rechte](KARTEN-WORKSHOP-02.106.md) · [02.107 – heutige UND historische Empfängerrechte/Retention](KARTEN-WORKSHOP-02.107.md) · [02.108 – Edit/Withdraw](KARTEN-WORKSHOP-02.108.md) · [02.109 – Moderation](KARTEN-WORKSHOP-02.109.md) · [02.110 – Mutes/Blocks](KARTEN-WORKSHOP-02.110.md) · [02.111 – Mentions](KARTEN-WORKSHOP-02.111.md) · [02.113 – Replies/Threads](KARTEN-WORKSHOP-02.113.md) · [02.115 – Kanalpins und Nachrichten-Bookmarks](KARTEN-WORKSHOP-02.115.md) · [02.116 A – keine individuellen Lesebestätigungen](KARTEN-WORKSHOP-02.116.md) · [02.117 – Suche/Filter](KARTEN-WORKSHOP-02.117.md) · [02.118 A – keine Draftspeicherung](KARTEN-WORKSHOP-02.118.md) · [02.126 – Notifications](KARTEN-WORKSHOP-02.126.md) · [02.127 A – kein Slowmode, technischer Spamschutz](KARTEN-WORKSHOP-02.127.md) · [02.128 A – keine persönlich verborgenen Einzelmessages](KARTEN-WORKSHOP-02.128.md).

## 1. Verbindliche Entscheidung – Variante 02.129 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Bei **02.105 Chat An** kann die SL nach 02.25-Kampagnen-/Kanaltyp-/Gruppen-/Rollen-/Personenstandards und gültigen **markierten Ausnahmen** die rein persönliche Organisation tatsächlich zugänglicher Chatkanäle ermöglichen. Die eigene berechtigte Kanalübersicht darf **private Favoriten, eigene Reihenfolge und optional einklappbare eigene Bereiche** enthalten. Diese Ansicht ist **ausschließlich für den jeweiligen Account** wirksam; niemand sortiert damit fremde Listen.

**Beispiel:** Spielerin A sieht nach echter Berechtigung „Kampagne“, „Späher“ und ihre DM mit B. Sie setzt „Späher“ als eigenen Favoriten und sortiert die eigenen Gruppen anders. Für B und die SL bleibt deren eigene Kanalansicht unverändert. A erhält dadurch weder zusätzliche SL-Kanäle noch verborgene Gruppennamen oder frühere DMs; auch eine nicht favorisierte berechtigte Nachricht wird nicht gelöscht.

**Nicht gewählt:** A (nur starre systemweite Kanalreihenfolge) und B (jeder darf ohne Recht Kanallisten, Favoriten und Sichtbarkeit für andere verändern). Auch C **gibt kein globales Umbenennungs-, Mitgliedschafts-, Kanalverwaltungs-, Sende-, Lese- oder Moderationsrecht**. Eine SL darf per 02.25 die *Möglichkeit* zur persönlichen Organisation setzen, aber nicht ungefragt fremde persönliche Listen lesen oder manipulieren.

## 2. Umfang und Einstellungsgrenzen

1. **Chat als harte Voraussetzung:** Ist 02.105-Chat bei Kampagnenerstellung oder später wirksam **Aus**, werden weder aktive Kanalübersichten noch neue Chat-Favoriten-/Sortier-/Collapse-Operationen angeboten oder serverseitig ausgeführt. Andere unabhängige Module laufen weiter. Reaktivierung prüft alle aktuellen Rechte neu; kein eigenständiger Chat-Umgehungspfad.
2. **Konfiguration:** Eigene Favoriten, selbstbestimmte Sortierung und optionales Einklappen sind fachlich getrennt zulässige Unterfähigkeiten nach 02.25-Defaults und begründeten gültigen Ausnahmen. Bei ausgeschalteter Unterfähigkeit keine neue entsprechende Änderung; eine neutrale autorisierte Standardansicht bleibt. Der genaue Settings-Assistent wird erst nach allen Featurefragen entworfen.
3. **Eigener Bereich:** Persönliche Favoriten können eigene Kanäle hervorheben; Sortierung verändert ausschließlich die Reihenfolge der **tatsächlich berechtigten** Einträge; eingeklappte Bereiche begrenzen nur die **Darstellung des eigenen Navigationsbereichs**. Keine physische Nachrichten-/Kanalarchivierung, kein automatisches Verlassen einer Gruppe und kein persönliches Einzel-Nachrichten-Hide nach 02.128 A.
4. **Keine fremden Listen:** Eigene Präferenzen sind privat; andere Spieler, Gruppenleiter, SL oder Moderatoren bekommen nicht ohne gesondertes legitimes Verwaltungs-/Datenschutzrecht eine Ansicht „Wer hat welchen Kanal favorisiert?“. Die UI erzeugt weder ein „A hat dich favorisiert“ noch verdeckte Mitglieder-/DM-/SL-Kanalstatistiken.
5. **Bestandsschutz:** Wenn eine eigene Konfigurationsfähigkeit deaktiviert wird, sind deren Einträge **inaktiv** und dürfen nicht neue unerlaubte Listen freigeben. Ob alte private Einstellungen begrenzt aufbewahrt oder verworfen werden, folgt später einer ausdrücklich festgelegten Datenschutz-/Retention-Policy; niemals blind durch Feature-Aus eine Quelle freischalten oder historische Kanaldaten wiederherstellen.

## 3. Rechte, Historie und benachbarte Features

| Bereits beschlossen | Verbindliche Wirkung für 02.129 C |
| --- | --- |
| **02.105 Chat An/Aus und 02.25 Policy** | Persönliche Kanalorganisation nur bei aktivem Chat und tatsächlich zugelassener Unterfähigkeit, markierte Ausnahmen mit serverseitiger Prüfung |
| **02.106 Kanal-/DM-/Gruppen-/SL-Rechte** | Kanalexistenz, Titel, Teilnehmer, Typ und Mitgliedschaft werden **pro aktuellem Nutzer** vor Anzeige oder Änderung geprüft; Favoriten gewähren keine Rechte |
| **02.107 heutige UND historische Nachrichtensicht** | Letzter Nachrichtentext, Vorschau, Unread, Suche und History bleiben an ursprünglich historische Empfängerbindung, heutige Quell- und Retentionrechte gebunden; Kanal-Favorit erzeugt keine Nachrichtensicht |
| **02.108-/02.109 Bearbeitung/Moderation** | Geänderte oder entfernte Quellen dürfen auch im Favoritenkanal keine alte Message-Vorschau bzw. Secret-Revisionskopie liefern |
| **02.110 persönliche Mutes und DM-Senderblocks** | Muting/Blocking ändern eigene Kontakt-/Notificationregeln, **nicht** automatisch Favoritenreihenfolge oder pauschal den alten rechtmäßig lesbaren Verlauf |
| **02.111 Pings / 02.126 Badges, Töne, OS-Toasts** | Favorit oder Einklappen erhöht/senkt nicht automatisch Ping-/Notificationrechte; Counts und Previews nur unter eigener tatsächlicher Recipient-/Privacy-/Mute-Policy |
| **02.113 Replies, 02.115 Pins/Bookmarks, 02.117 Suche** | Favorisierter *Kanal* ist keine gepinnte *Nachricht*, kein eigener Message-Bookmark, kein neuer Thread-/Quellen-/Search-/Export-Scope |
| **02.116 A keine individuellen Chat-Receipts** | Sortieren, Favorisieren und Öffnen/Einklappen liefern keinem Sender „zugestellt“, „gelesen“ oder „favorisiert“-Status |
| **02.118 A keine gespeicherten Chatentwürfe; 02.128 A kein Message-Hide** | Gespeicherte **Navigationspräferenz** ist kein geschützter Textentwurf, Offline-Outbox, verstecktes Message-Archiv oder Wiederherstellungsrecht |
| **02.101–02.104 amtliche Notices und 02.99 Weltaktionen** | Kanalorganisation quittiert keine Korrekturmeldung, verändert keine echte Quest-/NPC-/Tür-/Inventar-/Node-/Würfel-/Turnaktion |

**Gefahr durch Metadaten:** Auch der Name einer geheimen DM-/SL-Gruppe, eine Kanal-ID, Favoritenanzahl, Sortierposition, ein versteckter Eintrag, Suchvorschläge oder „Zuletzt aktiv“-Text können Existenz und frühere Zugehörigkeit verraten. Darum werden alle sichtbaren Einträge und abgeleiteten Werte **erst nach aktiver Channel-ACL** erzeugt; History-/Unread-/Snippetdaten benötigen zusätzlich die jeweilige **heutige UND historische Message-/Recipient-/Retentionprüfung**. Nur das Sortierergebnis einer bereits berechtigt gefilterten Liste wird angezeigt.

## 4. Lebenszyklus, Mehrgeräte und Missbrauchsschutz

1. **Neue, entfernte, umbenannte oder geänderte Kanäle:** Neue eigene gültige Kanäle erhalten eine deterministische neutrale Einordnung. Umbenennungen werden aus dem **aktuell berechtigten echten Kanalobjekt** geladen, nicht als alte private Titelkopie. Bei Verlust der aktuellen Mitgliedschaft/Channelrechte verschwinden Eintrag, Favoritenmarkierung, alte Titel, Preview, Badge und Such-/Realtimeprojektion **sofort aus allen aktiven Ansichten**.
2. **Keine Schattenfreigabe bei Rückkehr:** Eine zuvor gespeicherte private Kanalreferenz ist nur inert; bei neuem Join, Rollentausch, Gruppenwechsel oder Chat-Reaktivierung ist die Anzeige stets frisch auf **heutige** Rechte zu begrenzen. Keine automatische neue 02.107-Historieneinsicht. Ob die Präferenz nach ordnungsgemäßer Rückkehr wieder gilt, hängt von tatsächlich gültigen eigenen Settings und Retention ab.
3. **Mehrgeräte/Reconnect:** Eigene Sortier-/Favoritenänderungen sind benutzer- und kampagnenbezogen, können über zulässige Geräte synchronisiert werden; Konflikte müssen nachvollziehbar durch Version-/Compare-and-set oder deterministische Reihenfolgeverarbeitung entschieden werden. Keine fremde Preference lesen/ändern, keine alten Cache-/Push-/Offline-Listen gegen heutige Channelrechte anzeigen.
4. **Sichere Änderungsbefehle:** Server ermittelt den Actor aus der echten Session; akzeptiert keinen frei angegebenen fremden Nutzer als Eigentümer. Bei Favorite/Reorder/Collapse Scope, Kanalberechtigung, Featurepolicy, gültige ID und Objektversion prüfen. Idempotenz, Eingabelimits/Quoten und Abuse-Ratebegrenzungen gegen Spam und Sortierrennen.
5. **Geheimnissichere Fehler:** Erratene verborgene Kanal-IDs, alte DMs und nicht existente Kanäle haben keine unterscheidbare Content-/Member-/Count-/Titelausgabe. Ungültige Reihenfolgelisten dürfen weder fremde Einträge „mitziehen“ noch aus Cache vorzeigen.
6. **Richtige Trennung:** Nur die persönliche Layoutpräferenz kann länger als eine *sichtbare Listenprojektion* bestehen, soweit Datenschutz/Retention zulässt. Es wird **kein Nachrichtentext, Dateiinhalt, vollständiger Historysnapshot oder eigenständiger Kanaltitel** als persönliche Sortierkopie gespeichert.

## 5. Konzeptioneller Umsetzungsplan (kein fertiges Schema)

1. **Policy-Vertrag:** 02.105 Chat An und 02.25 gültige Kampagnen-/Kanaltyp-/Gruppen-/Rollen-/Personenausnahmen für die drei persönlichen Unterfähigkeiten auswerten; ausgeschaltete Funktion auch serverseitig nicht ausführbar. Sicherheitschecks selbst sind niemals schaltbar.
2. **Autorisierte Kanalprojektion:** Getrennten Serverresolver für aktuell sichtbare 02.106-Channel-IDs, Typen und **heute zulässige** Titel/Metadaten definieren. Aus Message-/History-/02.126-Notificationresolvern nur jeweils gesondert 02.107-/02.108-/02.109-/02.110-berechtigte Snippets, Unread, Mentions und Counts hinzunehmen.
3. **Rein eigener Präferenzdatensatz:** Konzeptionell `ChatChannelOwnViewPreference` mit Account/Kampagne, optionalem Channel-Referenzschlüssel, eigenem Favorite-/Order-/Bereichs-/Collapsezustand, Versionsmarker und begrenzter Aufbewahrung; **keine** Originaltexte, alten Namen, Message-IDs als Schattenarchiv und keine neu gewonnenen Leserechte. Noch keine endgültigen Tabellen-/API-Namen.
4. **Vorgänge und Race-Schutz:** Konzeptionell `updateMyChannelFavorite`, `reorderMyVisibleChannels` und `setMyChannelGroupCollapsed`; aus echter Session abgeleiteter Owner, Policy+Membership-Prüfung, erlaubte ID-Mengen, CAS/Idempotenz, Quoten, Retry/Reconnect-Handling. Normaler Serverkanalstatus und Channel-ACL bleiben unangetastet.
5. **Ausgabe und Rückfall:** Erst serverseitig Autorisiertes filtern, **danach** persönliche Reihenfolge/Favoriten/Einklappbereiche anwenden; falls Policy oder Daten fehlen, eine einfache rechtmäßig sichtbare Standardliste. Kein übernommenes Fremdprofil und kein Realtime-Leak in fremde Sessions.
6. **Tests und Priorisierung:** Fachliche Zugriffs-/Mehrgeräte-/Race-/Settings-/Revocation-/Retention-/DM-/Moderator-/Chat-Aus-/No-World-Tests unten vorbereiten. Exakte Navigation, Drag-and-drop, Tastatur/Screenreader, mobile Umsetzung, Datenmodell, Limits und MVP erst nach Abschluss aller Featureentscheidungen finalisieren.

## 6. Fachliche Abnahmetests

| Testfall | Erwartetes Ergebnis |
| --- | --- |
| 02.105 Chat Aus ab Kampagnenerstellung | Kein persönlicher Chatkanal-Organisationspfad aktiv; unabhängige Notizen/Würfel/Systemnotices normal |
| Chat An, 02.25 erlaubt Favoriten | A darf nur eigene **aktuell sichtbare** Kanäle favorisieren |
| A sortiert Kampagnen-, Gruppen- und DM-Kanal | Nur As eigene berechtigte Liste ändert sich; Bs und SLs Reihenfolge bleibt identisch |
| B versucht mit manipulierter Owner-ID As Favoriten zu ändern | Serverseitig abgelehnt, kein Einsichts-/Änderungsrecht |
| SL deaktiviert persönliche Sortierung für passende Policy | Keine neue Sortieroperation, rechtmäßig sichtbare neutrale Reihenfolge; Nachrichten unverändert |
| Markierte 02.25-Personen-/Kanaltyp-Ausnahme | Genau effektive, gültige Fähigkeit greift; keine Quell-/Gruppenrechte durch Ausnahme |
| A favorisiert einen alten jetzt geheimen/entfernten Gruppenkanal | Keine Kanalexistenz, Titel, Member, Count, Preview oder Navigation in As aktueller Sicht |
| A errät ID eines geheimen SL-/DM-Channels | Kein Favorisieren, Enumeration, anderer Fehlertext oder Realtime-Existenzsignal |
| Neuer Spieler tritt Gruppe mit älteren Privatmessages bei | Nur jetzt erlaubter Channel, keine alte 02.107-Nachricht ohne historische Originalempfängerberechtigung |
| Kanalname ändert sich | Aus echter autorisierter Quelle aktualisiert, keine veraltete private Titelkopie |
| A verliert Gruppenrecht während offenem Favorit-Tab | Aktive Liste und Cache verlieren den Kanal/Unread/Preview, kein Reconnect-Leak |
| A erhält später wieder Gruppenrecht | Neu gefilterte erlaubte Liste, keine automatische alte History-Freigabe aus gespeicherter Präferenz |
| A klappt einen Favoritenbereich ein | Nur eigene Navigation reduziert, kein Chatmessage-Hide, keine Historylöschung |
| Kanal ist nach 02.110 stumm | Benachrichtigungen folgen Mute, Fav und Sortierung führen nicht automatisch wieder Töne ein |
| Blockierter neuer DM-Kontakt | Favorit darf neue durch 02.110 geblockte DM nicht herbeiführen; eigene private Blockgründe nicht auslesbar |
| 02.126-Badge in eingeklapptem Bereich | Nur wirklich erlaubt berechnete Infos, keine zusätzlichen DMs, Pings oder personenbezogene 02.116-Lesebestätigung |
| 02.108 Edit/Withdraw oder 02.109 Removal | Keine alte Text-/Anhangvorschau aus private Fav-/Reorder-Cache |
| 02.107-flüchtiger/abgelaufener Nachrichtentext | Kein Text-Backup oder Wiederherstellen durch Channel-Favorite |
| Zwei Geräte ordnen dieselbe Liste gleichzeitig um | Deterministisches Version-/CAS-Ergebnis ohne Überschreiben fremder Nutzer oder Phantomkanäle |
| Reconnect mit alten ID-/Orderdaten | Erneuter ACL-/Policyfilter, keine veralteten verborgenen Kanalmetadaten |
| A versucht tausende gefälschte IDs/Reorder-Events | Typ-/Anzahl-/Rate-/Idempotenzgrenzen greifen, ohne 02.127-Spiel-Slowmode einzuführen |
| 02.115 Nachrichtenpin oder privater Message-Bookmark | Unabhängig von Channel-Favorite, keine Verwechslung von Nachricht und Kanal |
| Favorite-Aktion bei wichtiger 02.102-Korrektur | Kein automatisches offizielles ACK; 02.101–02.104 separat |
| Kanalname „Tür öffnen“, Favoritenreihenfolge geändert | Keine 02.99-Tür-/Quest-/NPC-/Node-/Würfel-/Turnwirkung |

## 7. Beschlussgrenze und nächste Entscheidung

**Verbindlich beschlossen: 02.129 C – konfigurierbare, ausschließlich eigene Favoriten, Reihenfolge und optional einklappbare Bereiche der 02.106-heute berechtigten Chatkanalübersicht.** 02.105-Chat An/Aus, 02.25 gültige markierte Ausnahmen, 02.107-**heutige UND historische** Message-/Recipient-/Retentionrechte, 02.108-/02.109-Moderation, 02.110-Mutes/DM-Blocks, 02.115-Nachrichtenpins/-Bookmarks, 02.116 A **keine individuellen Read-/Delivery-Receipts**, 02.118 A **keine Draftspeicherung**, 02.126 C **eigene sichere Notifications**, 02.127 A kein spielerischer Slowmode und 02.128 A **kein Einzelmessage-Hide** bleiben erhalten. Änderungen gelten nur für den jeweiligen eigenen Kanalnavigator; keine zusätzliche Sicht auf fremde Kanäle/DMs, keine globale Kanalliste und keine echte Welt- oder Notice-/ACK-Wirkung.

**Noch nicht beschlossen:** konkrete UI, Einstellungsassistent-/MVP-Priorisierung, genaue Sortierinteraktion, Speicher-/Löschfristen und finale Schema-/REST-/WebSocket-Namen. Die Fachplanung ist **keine fertige Implementierung**.

## Nächste Entscheidung 02.130 – Kanalübergreifende persönliche Chat-Sammelansicht

**Beispiel:** Eine Spielerin ist in mehreren Gruppenkanälen und DMs. Statt jeden Kanal einzeln zu öffnen, möchte sie auf Wunsch die **ihr wirklich erlaubten** neueren Chatbeiträge gesammelt betrachten. Sie darf aber weder geheime SL-Kanäle noch fremde DMs oder alte, historisch nicht an sie gerichtete Beiträge sehen.

- **A – Keine Sammelansicht:** Chatbeiträge werden ausschließlich innerhalb der einzelnen berechtigten Kanäle geöffnet; keine kanalübergreifende Nachrichtenübersicht.
- **B – Globaler Vollfeed für alle:** Eine gemeinsame Liste zeigt alle Kampagnenchatbeiträge einschließlich fremder Gruppen, privater DMs und früherer Inhalte ohne heutige/historische Rechteprüfung.
- **C – Konfigurierbare persönliche, berechtigte Sammelansicht (Empfehlung):** Bei 02.105 Chat An und gemäß 02.25-Defaults/markierten Ausnahmen kann eine Person **nur die für sie heute UND historisch wirklich 02.106-/02.107-berechtigten und noch verfügbaren Beiträge** aus ausgewählten Kanaltypen gemeinsam sehen/filtern. 02.108-/02.109-Revisions-/Moderationsregeln, 02.110-Mutes/DM-Blocks, 02.116-A-Receipt-Verbot, 02.117-Such-/Historygrenzen, 02.126-Notification-Privatsphäre und 02.128-A-Verbot für Einzelmessage-Hide gelten unverändert. Keine Nachrichtenkopie, keine neuen Channels, kein Weiterleiten nach 02.123 A, keine automatisch echten 02.102-ACKs oder 02.99-Weltaktionen; genaue UI später.
