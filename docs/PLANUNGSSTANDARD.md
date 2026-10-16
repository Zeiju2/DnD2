# AdventureShift – Verbindlicher Planungsstandard

**Beschlossen am 14.10.2026.** Dieser Maßstab gilt für die weiteren Featureworkshops; keine Software wurde dadurch implementiert.

## Grundsatz

**Die Softwarearchitektur wird ausreichend detailliert geplant; konkrete Feineinstellungen müssen nicht jetzt vollständig festgelegt werden.**

Für jedes Modul sind jetzt zu klären:
1. Kernaufgaben und klare Abgrenzung; optionales An/Aus und relevante Abhängigkeiten zu anderen Modulen.
2. Grundlegende Datenobjekte, stabile Referenzen, Beziehungen, Versionen und Änderungsabläufe.
3. Autorität des VPS und Rechte von SL, Spieler, Gruppen, Szenen, Figuren und geheimen Daten.
4. Welche Aktionen, Zustandswechsel und Realtime-Ereignisse tatsächlich passieren; Browser sind getrennte Ansichten und lokale Renderer.
5. Fachliche Schnittstellen zu Inventar, Charakteren, Tokens, Karten, Nodes, Würfeln, Regeln und Kampagne.
6. Sicherheitskritische Randfälle, Rechteentzug, Join/Reconnect, Speichern, Fehler und grundlegende Abnahmetests.

**Später bestimmen:** exakte Defaultzahlen, Fensterabmessungen, Farben, Presets, Spezial-Shortcuts, konkrete Ressourcenlimits, detaillierte Formeln, Codebibliotheken und Feinbedienung, soweit sie die Grundarchitektur nicht ändern.

**Beispiel Inventar:** Jetzt wichtig sind das Modell für Container, Slots, Gegenstände und Ausrüstung, die Beziehungen, Verschiebungen und Berechtigungen sowie Folgen von Regel-/Kapazitätsänderungen. Ob eine konkrete Vorlage **zwei oder vier Slots** besitzt, lässt sich später konfigurieren. Deshalb darf eine Slotanzahl keine hartcodierte Architekturannahme sein.

## Wann wird eine Frage gestellt?

Eine eigene A/B/C-Frage ist sinnvoll, **wenn verschiedene Antworten zu anderen Datentypen, Rechtegrenzen, Modulschnittstellen oder grundlegenden Abläufen führen**. Reine Parameter- oder Layoutentscheidungen werden als später festzulegende Details markiert, statt die Arbeit in immer neue Unterfragen aufzuteilen.

Wird eine Frage entschieden, werden die fachlichen Auswirkungen samt notwendigen Rechte-/Mehrbrowser-/Fehlerfalltests in Git dokumentiert. Bewusst abgewählte Funktionen sind genauso verbindlich wie gewählte Funktionen. Die bisherige umfassende Planung wird nicht gelöscht.

## Nächste Projektphasen

**A – Fundamentale Architektur aller Hauptmodule:** 01 Inventar und 02 Karten/Szenen wurden bereits ausführlich besprochen. Audio 02.132–02.155 ist als **später zu realisierendes optionales Modul** ausreichend für diese Runde strukturiert; weitere Audio-Unterfragen zunächst aussetzen. Nächster Block: **03 Charakterbögen**, beginnend mit **03.1**. Danach 04–15 mit Schwerpunkt auf Grundmodellen statt Feindetails.

**B – Gemeinsame Struktur und Priorisierung:** Querschnittliches Datenmodell, Realtime/VPS, SL-/Spieler-ACL, Kampagneneinstellungen mit Module-An/Aus, Schnittstellen, konfigurierbare Automatisierung und **nur berechtigtes** Browser-Vorladen vereinheitlichen. MVP, spätere Module und Ausschlüsse priorisieren.

**C – Umsetzungsdetails bei Entwicklungsbeginn:** Spezifische Defaultwerte, Audio-DSP, Presetbibliotheken, Bedienoberfläche, Serverlastbudgets, technische Felder/API, Tests und Code für den tatsächlich anstehenden Implementierungsschritt konkretisieren.

Es gibt **keine verbindliche Restzahl von Fragen**. Entscheidend ist eine vollständige und technisch tragfähige Grundstruktur, nicht die Anzahl beantworteter Kleinstoptionen.

## Hosting und Sicherheit gelten durchgehend

AdventureShift läuft später auf eigenem VPS; SL und Spieler verwenden jeweils **eigene Browser**. Serverautorität, Rechteschutz, versteckte SL-Informationen und getrennte lokale Darstellungen sind nicht optional. Vorausschauend geladen werden dürfen nur **gegenwärtig berechtigte** Medien, niemals ungefilterte geheime Teile einer späteren Kampagne.

## Aktueller Übergang

**02.155 C abgeschlossen:** Persönliche freiwillige Audioeffektänderung nach gültigen Rechten entweder begrenzt sofort im eigenen laufenden erlaubten Cue oder ab dem nächsten unabhängig autorisierten Cuestart; echter Rechteentzug stoppt verbotene Effekte unabhängig vom gewählten Modus. [Detail](KARTEN-WORKSHOP-02.155.md).

**03.1 C beschlossen:** Versionierbare typisierte Charaktervorlagen und eigene Charakterinstanzen mit stabilen Feldern/gesicherten Schnittstellen [Beschluss](CHARAKTER-WORKSHOP-03.1.md). **03.2 C beschlossen:** Konfigurierbare Charakterzuordnung, Mehrfiguren-/Gruppensteuerung und getrennt authorisierte temporäre Kontrolle/Verhexung/Übernahme [Beschluss](CHARAKTER-WORKSHOP-03.2.md). **03.3 C beschlossen:** Geschützte Entwurf-/Publikationsrechte für CharacterSheets; **zusätzlich optionale datengetriebene Charaktererstellung mit Klassen-/Fähigkeitswahl und Punkteverteilung eingeplant** [Beschluss](CHARAKTER-WORKSHOP-03.3.md). **03.4 C beschlossen:** Versionierte datengetriebene Klassen-/Skill-/Fähigkeitsmodule mit getypten Feld-/Regel-/Punkte-/Aktionsreferenzen, ohne unkontrollierte Änderung bestehender Basiswerte [Beschluss/Tests](CHARAKTER-WORKSHOP-03.4.md). **03.5 C beschlossen:** Optionales regelwerkskonfigurierbares Fortschrittssystem mit XP/Punkten/Meilensteinen, Skills/Leveln, getrennten Draft-/Freigabe-/Award-/Anwendungsrechten und einmaligen Servercommits [Beschluss/Tests](CHARAKTER-WORKSHOP-03.5.md). **Nächste Strukturfrage 03.6:** kontrollierte Migration bestehender Figuren bei Vorlagen-/RulePack-Änderungen.  Keine automatische Fortsetzung mit Audio-Detailfragen.
