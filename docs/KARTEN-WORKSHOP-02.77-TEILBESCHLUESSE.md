# AdventureShift – Karten-Workshop: Teilentscheidungen zu 02.77

**Stand:** 12.10.2026 – verbindliche Präzisierungen zu Check-/Ergebnis-Nodes und Test-Diagnose; Gesamtfrage 02.77 zu mehrstufigen Node-Ketten noch offen.  
**Status:** Fachliche Anforderung und Umsetzungsplanung; keine Implementierung, keine finale API.  
**Bezüge:** [Hauptworkshop](KARTEN-WORKSHOP.md) · [02.76](KARTEN-WORKSHOP-02.76.md) · [Feature-Katalog](FEATURE-WORKSHOP.md)

## 02.77 – Bereits vereinbarte Teilentscheidungen

**Die folgenden Produktanforderungen wurden im Gespräch ausdrücklich festgelegt.** Die separate Auswahl A/B/C für die Behandlung fehlschlagender **weiterer Schritte einer mehrstufigen Node-Kette** ist dadurch noch nicht abschließend getroffen. Insbesondere darf ein normaler Würfel-Misserfolg nicht mit einem Programmfehler verwechselt werden.

### 1. Check-Nodes: einfache Erfolg-/Misserfolgsausgänge

- **Voreinstellung:** Eine Check-/Fertigkeitsprobe stellt für den Regelautor die typisierten Ausgänge **Erfolg** und **Misserfolg** bereit. Misserfolg ist ein vollständig gültiges fachliches Ergebnis; ein Spieler, der zu niedrig würfelt, verursacht damit keinen Softwarefehler.
- **Verbindlicher Check-Grundsatz aus 02.63/02.64:** Für aktive würfelpflichtige Fertigkeitschecks gilt nach dem wirksamen Regelprofil weiterhin echter serverseitiger Würfelwert plus gültiger Skillwert gegen numerischen Mindestwurf (bei Gleichstand Erfolg). Keine fiktive reine Animation, kein W20-Zwang und keine automatische Übertragung dieser Formel auf Schadens-, Loot- oder reine Zufallstabellen.
- **Würfel- und Geheimnisschutz:** Check-ID, echte Rohwerte, Skillbeitrag, Schwierigkeit, ggf. ausgewählte Advantage-/Disadvantage-Würfel und kanonisches Ergebnis werden einmalig serverautoritativ ermittelt. Anzeige folgt 02.65/02.66; unbemerkte geheime Wahrnehmungschecks dürfen weder durch Ports noch durch Testdiagnose an Spieler verraten werden.

### 2. Optionaler erweiterter Ergebnismodus

- **Explizit zuschaltbar:** Ein zusätzlicher Schalter bzw. ein Häkchen an der jeweiligen geeigneten Check-/Ergebnis-Node aktiviert **frei definierbare Ergebnisstufen und mehrere benannte Ausgänge** statt der einzigen binären Erfolg-/Misserfolgverzweigung. Ohne Aktivierung bleibt die einfache Ansicht erhalten; die Erweiterung ist kein genereller Zwang für alle Proben.
- **Freie Ergebnisbereiche:** Die Spielleitung legt je Ergebnisprofil/Node mehrere eindeutig definierte Bereiche oder Kriterien an, z. B. auf Basis **des tatsächlichen Rohwurfs**, **des regelkonformen Gesamtwerts** oder **der Differenz zum Mindestwurf**. Die gewählte Bezugsgröße wird gespeichert und darf nicht im Hintergrund wechseln. Ergebnisstufen können etwa „Niete“, „Kleingewinn“, „Großgewinn“, „Jackpot“, „knapp gescheitert“, „Teil-Erfolg“ oder „herausragender Erfolg“ heißen. Anzahl und Bezeichnung der Ports bleiben konfigurierbar; keine fest eingebaute D&D-Liste.
- **Beispiel Glücksspielautomat:** Eine reine Zufalls- bzw. Ergebnis-Node mit **nur beispielhaftem** W20-Profilergebnis könnte 1–10 = Niete, 11–16 = Kleingewinn, 17–19 = Großgewinn, 20 = Jackpot ausgeben. Das ist eine Demonstration der frei festlegbaren Bereichszuordnung, **keine beschlossene Standardchance, Auszahlungsquote, Spiellogik oder Echtgeldfunktion**. Ein solcher Automat erfordert keinen passenden Skill-/Mindestwurfcheck, solange das Regelprofil nur eine Zufallsauswahl vorsieht.
- **Kritische Ergebnisse extra aktivieren:** „Natural 20“, kritischer Erfolg, kritischer Fehlschlag und vergleichbare Würfel-/Regel-Sonderfälle sind **separat, optional und pro anwendbarer Node/Regel konfigurierbar**. Sie dürfen eigene zusätzliche bzw. vorrangige Ergebnisports erhalten, aber erst wenn ihre wirksamen Erkennungs-, Auswertungs- und Prioritätsregeln explizit festgelegt wurden. **Natural 20 ist nicht automatisch Erfolg oder Jackpot; Natural 1 nicht automatisch Patzer.** Für andere Würfelarten oder Würfelpools sind die passenden Krit-Kriterien ebenfalls regelabhängig.
- **Klare Eindeutigkeit:** Eine echte Check-ID führt zu genau einer kanonischen Ergebnisauswertung; für überlappende Bereiche/aktive Krit-Sonderfälle muss vor Ausführung eine nachvollziehbare Regelpriorität oder Validierungsfehlermeldung bestehen. Keine doppelte Auszahlung, doppelte Wirkung oder willkürliche Portauswahl. Bei ungültiger Konfiguration keine Schein-Niete und kein technischer Fehlerport als Spielevent.
- **Ports und Graph:** Jeder definierte Fachausgang ist ein typisierter Node-Ausgang für die ausdrücklichen, tatsächlich verkabelten Folgeaktionen (Gewinn geben, Tür öffnen, Alarm auslösen usw.). Die Ausgabe mehrerer Ergebnisvarianten bedeutet nicht die gleichzeitige Ausführung aller Varianten. Die konsequente Trennung von Ausgangssignal, Verbindung und tatsächlichem Effekt folgt 02.17/02.20–02.21/02.35/02.73/02.76.

### 3. Keine technischen Systemfehler als normale Spielausgänge

- **Drei Ebenen trennen:** (a) erfolgreiches/fehlgeschlagenes **spielerisches** Ergebnis, (b) normale fachliche Ablehnung wie nicht erfüllte Bedingung oder fehlendes Spielrecht, sofern von der Node vorgesehen, (c) echter **technischer Fehler** wie Codeausnahme, beschädigter interner Zustand oder fehlgeschlagene Server-/Speicheroperation.
- **Technischer Fehler außerhalb des Spiel-Graphs:** Ein solcher Fehler darf **niemals** als Misserfolg, „kritischer Fehlschlag“, Niete oder Jackpot auf einem Spielergebnis-Port ausgegeben werden. Die Server-Laufzeit verarbeitet ihn zentral: betroffene Ausführung sicher stoppen/isolieren, transaktionale Konsistenz und Idempotenz erhalten, berechtigt protokollieren, Fehlerursache in geschütztem SL-/System-Debug anzeigen. Keine automatisch kostenlose neue Würfelprobe oder Replay-Auszahlung.
- **Fachlicher Check-Misserfolg:** Auf den regulären, konfigurierten Fachausgang verzweigen. Eine nicht verkabelte Zweigverbindung beendet höchstens diesen Zweig nach bestehender Graphlogik; sie ist kein Programmfehler.

### 4. Einfärbung bei Event- und Node-Tests: Rahmen vs. ganze Node

**Verbindlich:** Während Event-/Node-Test und isolierter Simulation wird für normale Testdiagnose **nur der Node-Rahmen** eingefärbt; die Füllfläche bleibt im normalen Node-Stil. **Bei einem echten technischen Systemfehler wird dagegen die ganze betroffene Node rot eingefärbt.** Diese Unterscheidung gilt einheitlich in allen drei Node-Ansichten aus 02.27, ohne die zugrunde liegenden Node-Ports und Signaltypen zu ändern.

| Befund im Test/Debugger | Darstellung | Bedeutung |
| --- | --- | --- |
| Regulärer Pfad, auch regulärer Würfel-/Check-Misserfolg | Ggf. Hervorhebung des **Rahmens** für den gerade untersuchten Testpfad; **keine rote Fehlerfüllung** | Fachlich zulässiges Ergebnis, keine Systemstörung |
| Nicht verbundener relevanter/benutzter Ausgang | **Orangefarbener Node-Rahmen**, normale Node-Füllung | An diesem Port führt aktuell keine Graphverbindung weiter; diagnostischer Hinweis, keine Codeausnahme |
| Tatsächliche interne Code-/Runtime-/Persistenzstörung | **Gesamte Node rot eingefärbt** (einschließlich ihrer Fläche) | Technischer Systemfehler; echte Ausführung über sicheren externen Fehlerpfad stoppen/isolieren |
| Technischer Fehler gleichzeitig mit fehlendem Ausgang | **Rot der ganzen Node hat Vorrang**, offene Ausgänge ggf. separat im Detailfenster vermerken | Kritischer Systemfehler wird nicht durch harmlosen Verdrahtungshinweis verdeckt |

- **Text/Icon zusätzlich zur Farbe:** Orange-/Rot-Befunde erhalten eindeutige Kurztexte, Statussymbole und bei Auswahl Details; die Ursache darf auch ohne Farbwahrnehmung erkennbar sein. Kontrast und Lesbarkeit der Node-Beschriftung/Ports auf vollständig rotem Hintergrund sichern. Farben an typisierten Leitungen/Ports aus 02.20 nicht durch Rahmenfarbe semantisch umdefinieren.
- **Diagnostik nur für Berechtigte:** Geheim-Nodes, geheimer Check, versteckter Alarm oder Fehlerdetails dürfen in Spieleransichten/Spielprotokollen nicht durch Farben, Portzahl oder Fehlermeldungen sichtbar werden. Berechtigte Spielleitungen sehen die betroffenen Node-/Event-/Check-IDs und die Ursache. Bei Tests wird die Spielwelt nicht real verändert (02.31–02.34).
- **Orange ist kein globaler Verkabelungszwang:** Optional nicht angeschlossene Ports müssen nicht grundsätzlich als Programmfehler gelten. Orange weist im untersuchten Test auf einen **relevanten, nicht weiterverbundenen Ausgang** hin; welcher Ausgang gewählt wurde, bleibt nachvollziehbar.

### 5. Implementierungs- und Testplanung

1. Konzeptionelle, versionierte `CheckOutcomeProfile`-/`OutcomeRange`-/`CriticalOutcomeRule`-Modelle als Platzhalter vorsehen; binäre Grundausgänge und separat aktivierbare benannte Bereichsports mit stabilen IDs. Dieselbe Regel im No-Code-Assistenten und visuellen Node-Editor bearbeiten können.
2. Vor Aktivierung alle Bereiche gegen passende Rohwurf-/Gesamtwert-/Erfolgsspannen und Krit-Prioritäten validieren; Überlappung, nicht behandelte Werte und fehlerhafte Pflichtkonfiguration nachvollziehbar anzeigen. Wo keine Regel besteht, keine impliziten Jackpot-/Krit-Regeln erfinden.
3. Check-IDs, echte RNG-Ergebnisse, Regelversions-/Akteurs-/Szenenrechte, Geheimnisfilter und tatsächlich gewählten Einzel-Outcome-Port serverseitig festhalten. Gleicher Versuch über Replay/Reconnect/Node-Loop erzeugt keinen neuen Wurf oder mehrfachen Gewinn.
4. Node-/Event-Testdarstellung mit separaten Befundklassen `outcome`, `unconnected_output` und `system_fault` (Bezeichner exemplarisch) und klarer Priorität für den **vollen Rotzustand**; die normalen Test-/Signalpfade färben lediglich den Rahmen. Strikter SL-Geheimnisschutz.
5. Isolierte Abnahme: Basiswürfel Erfolg/Misserfolg; Natur-20-Krit ausgeschaltet/eingeschaltet; regelabhängiger Krit-Fehlschlag; Glücksspielautomat mit Niete/Klein/Groß/Jackpot; eindeutige Ranges; Advantage mit einem ausgewählten kanonischen Ergebnis; doppelter Trigger ohne doppelten Gewinn; unverbundener ausgewählter Port erzeugt orangefarbigen **Rahmen**; simulierter Runtime-/Speicherfehler färbt **komplette Node rot** ohne Spielergebnisport und ohne reale Welt-/Itemwirkung. Anzeige in allen drei Ansichten und ohne Farbsehen prüfen.

## 02.77 – Noch offene Hauptentscheidung: Verhalten nach einem fehlgeschlagenen Folgeschritt

**Nicht durch diese Teilentscheidungen beschlossen:** Was eine **mehrstufige, bereits teilweise wirksame** Node-Kette tut, wenn eine Fachaktion (etwa Alarm zurücksetzen) scheitert, obwohl der vorherige Schritt (Tür öffnen) erfolgreich war. Die Optionen aus [02.76](KARTEN-WORKSHOP-02.76.md) bleiben als A/B/C offen:

- **A:** Weitere Schritte immer stoppen; abgeschlossene frühere Wirkungen nicht ungefragt zurücknehmen.
- **B:** Fehlgeschlagene Schritte stets überspringen und nachfolgende Schritte versuchen.
- **C (Empfehlung):** Fachlich konfigurierbare Erfolgs-, Misserfolgs- und Folgepfade, z. B. stoppen, geeignetem Port folgen, sicher erneut versuchen oder auf SL warten. Rückabwicklung bereits realer Wirkungen nur, wenn ausdrücklich definiert und tatsächlich sicher möglich. **Technische Systemfehler sind davon ausgenommen und werden zentral ausfallsicher behandelt.**

**Nächster Gesprächsschritt:** 02.77 Hauptentscheidung A/B/C ausdrücklich festlegen; danach erst 02.78 vorbereiten. Dieser Eintrag stellt keine vorzeitige Auswahl von C dar.
