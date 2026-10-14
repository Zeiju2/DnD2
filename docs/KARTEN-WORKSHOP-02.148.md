# AdventureShift – Karten-Workshop: Beschluss 02.148 C – sichere konfigurierbare Priorität von Szenen-Audioeffektprofilen

**Stand:** 14.10.2026. Fachentscheidungen 02.1–02.148, nächste offene Frage **02.149**.
**Status:** Verbindliche Fachplanung mit Umsetzungsentwurf und Abnahmetests, **noch keine implementierte Software**, keine fertigen Datenbank-/API-Verträge, Audio-Engine, Benutzeroberfläche oder MVP-Einstufung.
**Bezüge:** [02.25 – globale Kampagnenstandards, Vorschau und markierte Ausnahmen](KARTEN-WORKSHOP.md) · [02.49–02.51 – echte Spielweltakustik und Nodes](KARTEN-WORKSHOP.md) · [02.99 – autorisierte Weltaktionen](KARTEN-WORKSHOP-02.99.md) · [02.102 – amtliche ACKs](KARTEN-WORKSHOP-02.102.md) · [02.105 – optionaler Chat](KARTEN-WORKSHOP-02.105.md) · [02.132 C – optionale Musik/Soundboard](KARTEN-WORKSHOP-02.132.md) · [02.133 A – persönliche Audiowiedergabe ohne globale Uhr](KARTEN-WORKSHOP-02.133.md) · [02.134 C – lokale Layer/Fades/Loops](KARTEN-WORKSHOP-02.134.md) · [02.135–02.136 C – Vorlagen](KARTEN-WORKSHOP-02.136.md) · [02.137 A – keine zusätzlichen Audio-Insertparameter](KARTEN-WORKSHOP-02.137.md) · [02.138 C – Ducking](KARTEN-WORKSHOP-02.138.md) · [02.139 A – keine besonderen Audio-Captions](KARTEN-WORKSHOP-02.139.md) · [02.140 A – kein Editor-Sonder-Vorhörplayer](KARTEN-WORKSHOP-02.140.md) · [02.141 C – sichere Loudness](KARTEN-WORKSHOP-02.141.md) · [02.142–02.145 C – räumliche Audiofähigkeiten](KARTEN-WORKSHOP-02.145.md) · [02.146 C – lokaler Hall/Echo](KARTEN-WORKSHOP-02.146.md) · [02.147 C – geschützte Szenen-Audioeffektprofile](KARTEN-WORKSHOP-02.147.md) · [VPS- und Browser-Vorladen](SITZUNGS-VORLADEN-CACHE.md).

## 1. Verbindlicher Beschluss – Variante 02.148 C

**Der Projektinhaber hat ausdrücklich C gewählt:** Treffen bei aktivierter 02.132-Musikfähigkeit, gesondert erlaubter 02.146-Hall-/Echo-Fähigkeit und 02.147-Szenenprofilfähigkeit für **denselben tatsächlich berechtigten Hörer-/Szenen-/Cue-Scope** mehrere ebenfalls gegenwärtig zulässige Audioeffektprofile zu, wird nach **02.25-Kampagnen-/Rollen-/Gruppen-/Szenen-/Personenstandards und gültigen ausdrücklich markierten Ausnahmen** eine **konfigurierbare, sichere, begrenzte, deterministische und eindeutig wirksame Priorität** ermittelt. Nicht berechtigte Profile werden **vor jeder Prioritätsprüfung** entfernt. Eine rechtmäßige persönliche Ausnahme kann einen allgemeinen Szenenstandard übersteuern, wenn dies nach der wirksamen Policy so festgelegt ist. Bei nicht sicher auflösbarem Konflikt erfolgt ein **geschützter neutraler/dry Fallback oder kontrollierter Verzicht**, niemals geheimes Preset, unbegrenztes Profilstapeln oder unautorisiertes Audio.

**Beispiel:** Eine für Spielerin A freigegebene Höhle hat das abstrakte erlaubte Hallprofil „Große Halle“. Die SL hat für A eine ausdrücklich markierte, in der Kampagnenpolicy höher priorisierte Ausnahme „Kleine Kammer“ eingerichtet. A hört bei ohnehin rechtmäßig laufendem Ambienttrack ihre **eigene erlaubte** Profileinstellung. Spieler B bekommt ohne entsprechende gültige Ausnahme ausschließlich sein wirksames zulässiges Profil. A und B erhalten **keinen** Hinweis auf geheime andere Profile oder auf die Gründe in fremden Rollen-/SL-Bereichen.

**Nicht gewählt:** **A** (jede Mehrfachzuordnung zwingt grundsätzlich eine manuelle SL-Einzelauswahl, keinerlei zulässige automatische Konfliktauflösung) und **B** (ungeprüfte parallele Überlagerung aller Profile einschließlich ungültiger, widersprechender, geheimer oder ressourcenintensiver Hallketten). **C wählt eine einzige effektiv anwendbare Szenen-Hall-/Echo-Profilentscheidung je passendem Scope, nicht beliebig viele Effektketten.** Bestehende getrennt berechtigte Audiolayer und andere Audiofähigkeiten aus 02.134/02.138/02.141 bleiben davon unabhängig.

## 2. Fachliches Prioritätsmodell

1. **Voraussetzungen hart vor Vorrang:** Ist Musik 02.132, Hall/Echo 02.146 oder Szenenprofil 02.147 im geltenden Kampagnen-/Hörerscope Aus, gibt es **keine** automatisch wirksame 02.148-Szenenprofilentscheidung. Priorität kann weder Fähigkeiten reaktivieren noch Audio-/Medien-/Lizenzenrechte ersetzen.
2. **Kandidaten vorab autorisieren:** Der autoritative VPS bildet einen nur intern sichtbaren Kandidatensatz für die **heute gültige** Szene, Person, Gruppe, Rolle, zugelassene Quelle/Cue, Preset, Medienasset/Lizenz und einen etwa geschützten hörbaren Raumcharakter. Fehlt eine erforderliche Freigabe, wird der Kandidat komplett ausgeschlossen, **bevor** Gewicht, Existenz, ID, Zahl oder Konfliktdetails an einen Client gelangen.
3. **Kampagnenkonfigurierbare Präzedenz:** Die SL kann nach effektiver 02.25-Policy zulässige Vorrangklassen für Kampagnenstandard, Szenenstandard, Gruppenregel, Rollenregel, ausdrücklich markierte persönliche Ausnahme und gültig autorisierte manuelle Auswahl vorsehen. Empfohlene Ausgangserwartung: gezielte ausdrücklich markierte gültige Ausnahmen können geerbte Standards überschreiben; **die genaue Reihenfolge zwischen diesen Klassen bleibt als konfigurierte Kampagnenregel nachvollziehbar** und wird nicht unabhängig davon durch zufällige DB-/Browser-Reihenfolge festgelegt.
4. **Wirksame Ausnahmen bleiben erhalten:** Eine Änderung globaler Prioritätsvorgaben folgt 02.25: betroffene vorhandene Bindungen/Ausnahmen in einer zulässigen Vorschau erkennen, bewusst zwischen zukünftigen und bestehenden Instanzen wählen, ausdrücklich markierte Ausnahmen nicht still überschreiben. Keine automatische Rechteausweitung durch Prioritätsänderung.
5. **Manuell gegen automatisch:** Eine nach 02.147 zulässige manuelle Profilwahl erhält **nur dann** den festgelegten Vorrang, wenn die aktuelle Policy dies ausdrücklich vorsieht. Die getrennt schaltbare 02.147-SceneSwitch-Automation kann eine bestehende manuelle Wahl nicht ungeprüft verdrängen. Gültigkeit und Lebensdauer einer manuell gewählten Prioritätsausnahme sind pro Policy zu bestimmen; konkrete UI und Ablaufwerte später.
6. **Eindeutige Entscheidung pro Scope:** Innerhalb eines autorisierten, konkret definierten lokalen Hörerszenen-/Quell-Cue-Kontexts entsteht genau **ein** wirksames Hall-/Echo-Szenenprofil oder der sichere neutral/dry Zustand. Dies verbietet nicht mehrere **separat legitime** Musik-/Soundboard-Layer, sondern nur unkontrolliertes Überlagern konkurrierender Profilentscheidungen auf demselben Kontext.
7. **Gleichrangigkeit und Konflikte:** Wenn mehrere zulässige Profile nach den wirklich gültigen Vorrangregeln gleichrangig sind und die Policy **keinen eindeutigen erlaubten Sieger** ergibt, gilt **fail closed**: neutraler erlaubter Effekt/dry Originalcue oder keine Profilwirkung. Niemals nach vermeintlich geheimer ID/Erstellungszeit oder clientseitig geratenem Rang heimlich „zufällig“ gewinnen lassen. Ein berechtigter SL-Bearbeiter kann den Konflikt in einer geschützten Diagnose erkennen und bewusst durch erlaubte neue Regel/markierte Ausnahme korrigieren.
8. **Geheimnisse im Diagnoseweg:** Spieler erhalten ausschließlich die für sie zulässige wirksame Präsentation; kein unberechtigter globaler Profilkatalog, unberechtigte Tie-Break-Hinweise, ProfileCount, geschützter Quell-/Szenenname, „warum ich nicht gewann“-Log oder Zeitmesskanal. SL-Diagnose zeigt ausschließlich bei aktueller Berechtigung gerade benötigte Ursachen und darf nicht fremde Kampagnen/Mediendetails offenlegen.
9. **Keine Umkehr der Autorisierung:** Ein höherer Rang macht ein inzwischen nicht mehr erlaubtes Preset **niemals** verwendbar. Bei Entzug einer Person-/Scene-/Cue-/Preset-/Medien-/Lizenzfreigabe wird aktuell neu autorisiert und nur mit verbleibenden **jetzt** erlaubten Kandidaten entschieden; bereits an Endgeräte übertragene Klartextbytes sind nicht verlässlich rückrufbar.
10. **Versioniert und reproduzierbar:** Konfliktauflösung basiert auf einem aktuellen serverautoritativ überprüften Kampagnen-/Scene-/ACL-/Policy-/Cue-/Presetstand, nicht auf Browserzeit, zufälligen Netzwerkreihenfolgen oder clientseitigen geheimen Metadaten. Versionierte pro Empfänger berechtigte Projektion; Replay-/Duplikat-/Out-of-order-/Reconnect-Guards verhindern spätere Anwendung veralteter Gewinner.
11. **Browserdarstellung:** Jeder Hörerbrowser erhält nur die aktuell zulässige minimale Gewinnerkonfiguration und wendet sie mit seinen 02.146-Hall-/Echo-Budgets gerätelokal auf separat erlaubte Quellen an. Browser darf keinen eigenen Kandidatenvergleich anhand vollständiger SL-Daten verlangen oder durchführen. Bei nicht verfügbarer Engine, hohem CPU-Bedarf oder fehlendem rechtmäßigem Asset sicherer gewöhnlicher/dry Ton oder Abbruch.
12. **Personensteuerung gewinnt:** Persönlicher Master-/Layer-Mute, Lautstärke, Browser-Autoplay und geltende Nutzerentscheidung werden durch höhere Priorität **nie** übergangen. Keine fremden OS-/Voicechat-/Mikrofonaudioeingriffe. 02.133 A bleibt: kein gemeinsamer Playhead, kein Session-Start/Seek/Pause oder LateJoin-/Reconnect-Autoplay, auch wenn alle Hörer denselben Profilnamen sehen dürfen.
13. **Rechtssichere Presetwechsel:** Ein rechtmäßig neu berechneter Gewinner darf, soweit nach 02.147 erlaubt, ausschließlich die lokale Profilkonfiguration ändern. **Wie** zwischen alten und neuen gleichzeitig noch erlaubten Hall-/Echoeffekten akustisch gewechselt wird, entscheidet erst **02.149**. Bei Rechteentzug dürfen alte nicht mehr erlaubte Tails/Profile keinesfalls für einen angenehmen Übergang weitergespielt werden.
14. **Vorladen und Speicher:** Vorabladen gemäß VPS-/Browser-Querschnittsbeschluss darf nur Assets/Presets für **heute tatsächlich erlaubte** Empfängerscopes und zur sinnvollen Priorisierung bereitstellen. Ein Profilranking ist **keine zusätzliche Medienfreigabe**; keine geheimen Alternativprofile im Spieler-Manifest oder Browsercache zur vermeintlich schnelleren Konfliktlösung. Kein garantierter Offline-Weltbetrieb.
15. **Kein Welt-/Sensorpfad:** Die Prioritätsberechnung ist **nur eine lokale Audio-Präsentationsentscheidung**, kein 02.49–02.51-physikalisches SoundEvent, keine NPC-Hör-, Schall-/Präsenz-/Bewegungsmelder-/Alarm-/Licht-/Nodewirkung; keine 02.99-Tür-/Quest-/NPC-/Würfel-/Inventar-/Turnaktion, keine 02.102-ACK-Quittierung. 02.137 A, 02.139 A und 02.140 A bleiben auch im Profilkonflikt gültig.

## 3. Architekturentwurf und unverbindliche Datenobjekte

**Arbeitsbegriffe – keine fertigen DB-Tabellen oder APIs:** SceneAudioProfilePriorityPolicy, AuthorizedAudioProfileCandidate, EffectiveViewerSceneAudioProfile, ProtectedProfileConflictReason, ProfilePriorityPolicyRevision, SceneAudioPriorityDecision, LocalAudioProfileApplyToken.

**Geplanter serverseitiger Ablauf:**

1. Nach tatsächlicher Erlaubnis zur 02.147-Zuordnung bzw. aktivem SceneSwitch wird für jeden relevanten Hörer und erlaubten Quell-Cue zunächst die aktuelle **Capability-/ACL-/Fog-/Secret-/Medien-/Lizenzlage** ermittelt.
2. Kandidaten **ausschließlich intern** und nach aktueller Berechtigung filtern. Die konfliktierende Information über nicht erlaubte Profile hat niemals eine zulässige Client-Projektion.
3. Über aktuell geltende 02.25-Inherit-/Default-/markierte Ausnahmeregeln eine deterministische Priorität zwischen verbleibenden berechtigten Kandidaten bestimmen. Autorisierte manuelle Wahl und SceneSwitch-Auto sind eigenständige Policies, keine implizite Rechtausweitung.
4. Nur ein eindeutiger **jetzt gültiger** Gewinner wird versioniert pro Hörer-/Szene-/Cue-Kontext bereitgestellt; sonst sichere neutrale/trockene Einstellung oder definierter Verzicht. Empfängergültige Event-/Policy-Revisions und Idempotenz für Reconnect, Retry und Out-of-order.
5. Hörerbrowser wendet Gewinner nur im zulässigen bestehenden gerätelokalen 02.146-Audioeffektpfad an. **Kein** automatisch neuer Cue, keine globale Audiouhr, keine fremde Lautstärkeänderung, keine echte Welt-/Sensor-/ACK-Aktion.
6. Bei einer wirksamen Änderung von Szene, Rolle, Gruppe, Person, Quelle, Preset, Asset, Lizenz, Vorrangregel, Musik-/Hall-/Profil-Aus neu prüfen; alte kontrollierbare Effekttails/URLs/Caches bei Rechteverlust entwerten. Erst die noch offene 02.149 entscheidet über klangliche Übergänge **wenn beide Seiten weiter erlaubt** sind.
7. Audit/SL-Debug nur für aktuell berechtigte Betrachter und nur in geeignet bereinigter Form. Datenminimierung, Ressourcenbudgets und globale Defaults/Ausnahmen bleiben maßgeblich; keine öffentliche Anzeige interner Konkurrentenlisten.

## 4. Konzeptioneller Umsetzungsplan

1. **Policy/Capability-Modell:** 02.25-Vererbung, Markierungen, Bearbeitungs-/Vorschau-/Ausnahmerechte, 02.132-/02.146-/02.147-An-Schalter und 02.148-Vorrangklassen getrennt entwerfen.
2. **Berechtigter Kandidatenresolver:** Kampagne, Hörer, Gruppe, Rolle, konkrete Szene, vorhandene Cues, erlaubte Preset-/Asset-/Lizenz-/Secret-Projektion, manueller/SceneSwitch-Modus und effektive Ausnahme zu jeder Auswertung serverseitig kontrollieren.
3. **Deterministische Konfliktauswertung:** Eine gültige Policy-Revisionsentscheidung mit eindeutigem Gewinner oder fail-closed-Fallback je zulässigem Kontext. Verifizierbare, aber vor Unberechtigten geschützte SL-Konfliktdiagnose und 02.25-Auswirkungsvorschau.
4. **Realtime/lokale Wirkung:** Minimales versioniertes Ergebnis ohne geheime Kandidatenliste, lokale 02.146-Effektkonfiguration ohne Audio-Neustart, globale Uhr, Mute-Bypass, Rekursion, übermäßige DSP-/CPU-/Tail-Nutzung oder Sensor-/Worldwirkung.
5. **Lifecycle und Widerruf:** Konkurrierende Änderungen, ACL-/Fog-/Rollen-/Asset-/Lizenz-/Preset-/Scene-/AudioAus-Rechteentzug, Split-Party, LateJoin/Reconnect, doppelte/stale Realtime-Events, Browsercache und mögliche Fallbacks testen.
6. **Spätere Realisierung:** Konkrete Prioritätskonfigurations-UI, API-/DB-Felder, Diagnosedetails, DSP-/Latenzgrenzen, Cachegrößen und MVP-Zuordnung erst nach vollständiger Featureplanung finalisieren. Audioübergänge explizit mit 02.149 entscheiden.

## 5. Fachliche Abnahmetests

| Szenario | Erwartetes Verhalten |
| --- | --- |
| 02.132 Musik Aus | Keine wirksame Szenen-Hall-Prioritätsanwendung; Chat/Welt unabhängig |
| 02.146 Hall oder 02.147 Szenenprofile Aus | Keine 02.148-Szenenprofilwirkung, auch nicht über hohen Rang |
| Erlaubter Szenenstandard ohne Ausnahme | Nur dessen eine zulässige Profilwirkung |
| Erlaubte ausdrücklich höher priorisierte persönliche Ausnahme | Berechtigter Hörer erhält Ausnahme statt geerbtem Standard |
| Zweiter Hörer ohne persönliche Ausnahme | Keine fremde Ausnahme oder Existenzoffenlegung |
| Rollen-/Gruppenvorgabe und Szenenstandard kollidieren | Aktuelle konfigurierte 02.25-Priorität entscheidet deterministisch |
| Zwei gültige Profile mit identischer nicht auflösbarer Priorität | Sicherer neutral/dry Fallback, kein geheimes willkürliches Winner-Preset |
| Eine manuelle Wahl und eine automatische Szenezuordnung kollidieren | Nur die dafür aktuell konfigurierte berechtigte Reihenfolge gilt |
| SL ändert Kampagnen-Priorität mit markierten Ausnahmen | 02.25-Auswirkungsvorschau und Ausnahmeschutz, keine stille Altbestandsänderung |
| Profil hat höchsten Rang, Scene-/Cue-/Presetrecht fehlt | Kandidat wird ausgeschlossen, Rang gewährt keine Rechte |
| Nur geheime unzulässige Profile bleiben | Kein Name, Count, Track, Cache- oder Fehlerdetail beim Spieler |
| Berechtigter SL untersucht Konflikt | Minimal notwendige sichere Diagnose, keine fremden Geheimnisse |
| Spieler versucht manipulierte Rang-/Preset-ID | VPS verwirft und gibt keine verborgenen Kandidaten preis |
| SL und Spieler in getrennten Szenen | Je Empfänger eigene autorisierte Gewinnerprojektion |
| SceneSwitch-/Policy-Ereignisse kommen vertauscht | Alte Version darf neuere erlaubte Entscheidung nicht überschreiben |
| Browser-Reconnect, zwei Tabs desselben Hörers | Kein globaler Seek-/Playhead-/Auto-Startzwang, konsistente gegenwärtige ACL |
| Spieler schaltet während Gewinnerwechsel Mute ein | Mute bleibt verbindlich auch für Hall-/Echo-Tails |
| Gewonnenes Preset wird während des Spiels widerrufen | Alte kontrollierbare Effekttails und Zugriff stoppen; nur jetzt gültige Alternative |
| Alte Profilrechte vor lokalem Crossfade erloschen | Kein Weiterklingen unberechtigter Tails zur Übergangsglättung |
| Gewinner-Preset darf nicht vorgeladen werden | Kein unzulässiger Medien-/Presetdownload, sicherer Fallback |
| Zwei Kampagnen verwenden gleichen Profilnamen | Keine kampagnenübergreifende ACL-, Medien- oder Policyübernahme |
| Viele Profile, großes Assetset, Mobilgerät | Serverseitig begrenzte Auswertung, kein massiver illegaler Kandidatendownload |
| Hallrenderer fehlt | Nur zulässiger trockener Ton oder kontrollierter Abbruch |
| Browser-Player läuft mit 02.142–02.145 Aus | Kein Positions-/Velocityleck; generischer Hall eigenständig berechtigt |
| Winner-/Konfliktprofil heißt „Alarm“ oder „Tür öffnen“ | Keine 02.49–02.51-Sensor-/Node-/World- oder 02.99-Aktionswirkung |
| Amtliche 02.102-Kenntnisnahme erforderlich | Profilwahl/Anzeige erzeugt kein ACK |
| 02.137/139/140-Ausschlüsse | Kein Insertparameter-Dialog, Audio-Captionfeed oder Editor-Sonder-Vorhörplayer |

## 6. Beschlussgrenze und nächste Entscheidung

**Fest beschlossen: 02.148 C – konfigurierbare, sichere, deterministische Priorität nur zwischen heute tatsächlich berechtigten Szenen-Audioeffektprofilen unter 02.25-Defaults und markierten Ausnahmen.** Je relevantem Empfänger-/Szene-/Cue-Scope genau eine wirksame Profilentscheidung oder neutraler geschützter Fallback. Berechtigte persönliche Ausnahmen können bei entsprechender aktueller Policy Szenenstandards übersteuern. Nicht berechtigte Presets, Audioassets, Räume oder Rechte und unkontrollierte Effektketten bleiben ausgeschlossen. VPS bestimmt gültige Berechtigung, Browser rendert lokal und respektiert Mute, 02.133 A sowie alle NoWorld-/NoSensor-/NoACK-Grenzen.

**Nicht beschlossen:** Endgültige konkrete UI-/DB-/API-Struktur, finale Standard-Rangfolge jedes Scopes, exakte DSP-/CPU-/Effekt-/Cachegrenzen, MVP oder die klangliche Übergangsweise zwischen zwei **weiterhin autorisierten** Gewinnerprofilen. Fachplanung, keine Softwareimplementierung.

## Nächste Entscheidung 02.149 – Wie wechseln lokale Hall-/Echoprofile bei einem neuen berechtigten Gewinner?

**Beispiel:** Die Gruppe geht von einer erlaubten Höhle in eine erlaubte kleine Kammer. 02.148 hat den neuen gültigen Effekt eindeutig ausgewählt. Soll der Hall abrupt umspringen oder im persönlichen Browser sanft übergehen? Wird ein altes Profil geheim/entzogen, muss seine kontrollierbare Audioausgabe unabhängig davon sofort unterbunden werden.

- **A – Sofortiger harter Wechsel:** Bei jedem legalen Profilwechsel wird die alte lokale Einstellung ohne speziellen Übergangsmodus gestoppt und die neue zulässige Einstellung direkt angewendet. Persönliche Mutes und Rechteentzug bleiben verbindlich.
- **B – Erzwungene globale Überblendung:** Alle Hörer müssen alte und neue Profile über eine gemeinsame Sessionuhr und unbeschränkt lange Echo-Tails ineinanderblenden, selbst wenn ein altes Profil inzwischen nicht mehr erlaubt ist oder der Browser stumm ist.
- **C – Konfigurierbare sichere lokale Profilübergänge (Empfehlung):** Für **beide weiterhin tatsächlich berechtigte** Profile kann die SL unter 02.25-Policy eine ressourcenbegrenzte lokale sanfte Hall-/Echo-Überblendung oder einen sofortigen Wechsel wählen. **Bei Widerruf wird das alte Profil samt kontrollierbaren Tails ohne Geheimnisleck gestoppt**; persönliche Mutes, Browserautoplay, 02.133 A ohne globale Musikzeit und fehlende Sensor-/World-/ACK-Wirkung bleiben verbindlich. Konkrete Crossfade-/Tailbudgets, DSP/UI erst später.
