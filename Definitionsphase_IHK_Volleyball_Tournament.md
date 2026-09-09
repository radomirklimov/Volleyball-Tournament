# 1. Definitionsphase

## 1.1 Ausgangssituation

Im Rahmen von Volleyballturnieren werden verschiedene Informationen wie Mannschaften, Gruppen, Spiele und Ergebnisse in einer bestehenden Datenbank erfasst. Die Datenbank wird während des Turniers durch die zuständige Lehrkraft manuell aktualisiert.

Für die Darstellung der vorhandenen Daten existiert bereits eine einfache PHP-Webseite. Diese stellt die Informationen überwiegend tabellarisch dar. Eine übersichtliche und für die Teilnehmer optimierte Benutzeroberfläche zur Darstellung des aktuellen Turnierverlaufs ist derzeit nicht vorhanden.

Insbesondere fehlt eine komfortable Möglichkeit, den aktuellen Stand des Turniers schnell zu erfassen. Die vorhandene Darstellung bietet keine geeignete grafische Aufbereitung und keine automatische Aktualisierung der angezeigten Daten.

Dadurch entsteht für die Teilnehmer zusätzlicher Aufwand, um sich über den aktuellen Stand des Turniers zu informieren.

---

## 1.2 Problemstellung

Die bestehende Lösung erfüllt die grundlegende Aufgabe, vorhandene Turnierdaten aus der Datenbank abzurufen und darzustellen. Die Darstellung ist jedoch hinsichtlich Übersichtlichkeit, Benutzerführung und Aktualität eingeschränkt.

Während eines laufenden Turniers ändern sich die gespeicherten Daten regelmäßig. Die Benutzer sollen diese Änderungen möglichst zeitnah erkennen können, ohne die Webseite manuell aktualisieren zu müssen.

Darüber hinaus fehlen Funktionen, mit denen sich die vorhandenen Daten gezielt durchsuchen, filtern und nach unterschiedlichen Kriterien sortieren lassen.

---

# 2. Projektauftrag

## 2.1 Auftraggeber und Auftragnehmer

**Auftraggeber:**  
Frau Geck-Mügge

**Auftragnehmer:**  
Radomyr Klymov und Mykyta Riabchenko

## 2.2 Projektauftrag

Ziel des Projekts ist die Entwicklung einer Webanwendung zur übersichtlichen Darstellung von Volleyballturnieren.

Die Anwendung soll vorhandene Turnierdaten aus der bestehenden Datenbank abrufen und für die Benutzer grafisch aufbereitet darstellen. Änderungen an den Turnierdaten sollen automatisch und möglichst ohne manuelles Neuladen der Webseite sichtbar werden.

Die Anwendung soll insbesondere Informationen über Gruppen, Mannschaften und Spiele bereitstellen und dem Benutzer eine schnelle Orientierung über den aktuellen Turnierstand ermöglichen.

---

# 3. Projektziele

Die Anwendung soll folgende Kernfunktionen bereitstellen:

### MUSS-Ziele
- Darstellung des aktuellen Turnierstands auf einer grafischen Übersichtsseite
- automatische Aktualisierung der angezeigten Turnierdaten
- Darstellung der vorhandenen Gruppen und Spielfelder
- Übersicht über teilnehmende Mannschaften
- Darstellung von Spielen
- Darstellung bereits abgeschlossener Spiele einschließlich ihrer Ergebnisse

### SOLL-Ziele
- Filterung der dargestellten Daten
- Sortierung von Daten
- übersichtliche Navigation zwischen den einzelnen Bereichen
- Darstellung eines Mannschaftsprofils
- Leaderboard
- Anzeige eines Schiedsrichters

### KANN-Ziele
- Speicherung von Benutzereinstellungen über Cookies
- Markieren beziehungsweise Anpinnen einer Lieblingsmannschaft
- Suche nach Mannschaften

---

# 4. Messbare Projektziele

| Ziel | Messkriterium |
|---|---|
| Anzeige aktueller Turnierdaten | Die Anwendung stellt die vorhandenen Turnierdaten aus der bestehenden Datenbank dar. |
| Automatische Aktualisierung | Änderungen an relevanten Turnierdaten werden ohne manuelles Neuladen der Webseite übertragen. |
| Erreichbarkeit | Die Anwendung ist innerhalb des vorgesehenen **ATIW-WLANs** erreichbar. |
| Benutzerfreundlichkeit | Die definierten Kernbereiche sind über eine klare Navigation erreichbar. |

→ **[INFORMATION FEHLT: Konkrete maximale Verzögerung der Live-Aktualisierung]**

---

# 5. Projektumfang und Abgrenzung

## 5.1 Bestandteil des Projekts

Zum Projektumfang gehören:

- Entwicklung einer neuen grafischen Weboberfläche
- Anbindung an die vorhandenen Turnierdaten
- Bereitstellung einer REST-API für die benötigten Daten
- Umsetzung der automatischen Aktualisierung
- Darstellung von Gruppen, Mannschaften und Spielen
- Such-, Filter- und Sortierfunktionen
- Umsetzung einer übersichtlichen Navigation
- Berücksichtigung mobiler Endgeräte
- Durchführung von Tests

Die vorhandene MariaDB-Datenbank wird weiterverwendet.

## 5.2 Nicht Bestandteil des Projekts

Die folgenden Bereiche sind nach aktuellem Stand nicht als Entwicklungsbestandteil beschrieben:

- Erstellung einer neuen Datenbank
- Erfassung der Turnierdaten
- Durchführung beziehungsweise Organisation des Volleyballturniers
- Administration der Turnierdaten durch die Lehrkraft
- **[INFORMATION FEHLT: Wird eine Administrationsoberfläche zur Bearbeitung der Turnierdaten ausdrücklich ausgeschlossen?]**
- **[INFORMATION FEHLT: Wird ein öffentliches Deployment außerhalb des ATIW-Netzwerks ausgeschlossen?]**

Eine klare Abgrenzung ist für die IHK besonders wichtig, da dadurch erkennbar wird, **welche Aufgaben tatsächlich Gegenstand des Projekts sind und welche vorhandenen Systeme beziehungsweise Prozesse übernommen werden.**

---

# 6. Stakeholder und Benutzer

## 6.1 Stakeholder

| Stakeholder | Rolle / Interesse |
|---|---|
| Frau Geck-Mügge | Auftraggeberin; definiert beziehungsweise bewertet die Anforderungen |
| Mykyta Riabchenko | Auftragnehmer / Projektbearbeitung |
| Radomyr Klymov | Auftragnehmer / Projektbearbeitung |
| Schülerinnen und Schüler | Hauptnutzer der Anwendung |
| Lehrkraft | Aktualisierung der Turnierdaten |
| ATIW / Netzwerkumgebung | Technische Rahmenbedingung für den Betrieb |

## 6.2 Benutzer

Die Hauptzielgruppe der Anwendung sind Schülerinnen und Schüler, die während eines Turniers Informationen über den aktuellen Spielstand und Turnierverlauf benötigen.

Die Anwendung wird dabei als Informationssystem betrachtet. Eine Anmeldung oder Benutzerverwaltung ist nach aktuellem Stand nicht vorgesehen.

→ **[INFORMATION FEHLT: Soll es unterschiedliche Benutzerrollen oder ausschließlich einen anonymen Benutzerzugriff geben?]**

---

# 7. Rahmenbedingungen

## 7.1 Technische Rahmenbedingungen

Für das Projekt sind folgende Rahmenbedingungen vorgegeben beziehungsweise vorhanden:

- bestehende MariaDB-Datenbank
- vorhandene Turnierdaten
- Betrieb innerhalb des ATIW-WLANs
- vorhandene ATIW-Firewall
- Hardware für das Deployment erforderlich
- bestehende PHP-Webseite als Ausgangslösung

Als geplante Technologien sind vorgesehen:

- Kotlin
- Spring Boot
- React
- JavaScript
- HTML
- CSS
- REST API
- WebSocket
- MariaDB

Die Auswahl und konkrete Begründung der Technologien sollte jedoch erst in der **Planungs- beziehungsweise Entwurfsphase** ausführlich dokumentiert werden.

---

# 8. Organisatorische Rahmenbedingungen

Für die Durchführung des Projekts steht ein Zeitrahmen von insgesamt **80 Stunden** zur Verfügung.

Der angesetzte Stundensatz beträgt **15 EUR pro Stunde**.

Daraus ergibt sich bei vollständiger Ausschöpfung des angegebenen Zeitbudgets ein rechnerischer Projektwert von:

**80 Stunden × 15 EUR = 1.200 EUR**

→ **[INFORMATION FEHLT: Ist der Stundensatz ein tatsächlicher interner Kostensatz oder lediglich eine Vorgabe für die Projektdokumentation?]**

Für eine vollständige IHK-Dokumentation sollte später außerdem eine Aufteilung der 80 Stunden auf die einzelnen Projektphasen erstellt werden.

---

# 9. Abhängigkeiten

Die Umsetzung des Projekts ist von mehreren externen beziehungsweise bereits vorhandenen Komponenten abhängig.

### Datenbank

Die Anwendung verwendet die bestehende Datenbank. Änderungen an deren Struktur können daher Auswirkungen auf die Anwendung haben.

### Netzwerk

Die Anwendung soll innerhalb des ATIW-WLANs erreichbar sein. Die bestehende Firewall stellt dabei eine technische Rahmenbedingung dar.

### Deployment-Hardware

Für den Betrieb der Anwendung wird entsprechende Hardware benötigt.

---

# 10. Risiken

| Risiko | Auswirkung | Gegenmaßnahme |
|---|---|---|
| Serverausfall | Anwendung ist nicht erreichbar | **[INFORMATION FEHLT: Geplante Ausfallstrategie]** |
| Fehler im ATIW-WLAN | Benutzer können Anwendung nicht erreichen | **[INFORMATION FEHLT: Geplante alternative Zugriffsmöglichkeit]** |
| Änderung der bestehenden Datenbank | API beziehungsweise Anwendung kann Daten nicht mehr korrekt verarbeiten | Datenbankstruktur analysieren und Schnittstelle möglichst eindeutig definieren |
| Fehler bei der Live-Aktualisierung | Benutzer sehen veraltete Informationen | Tests der Aktualisierungsmechanik und Fehlerbehandlung |
| Hohe Anzahl gleichzeitiger Benutzer | Antwortzeiten können steigen | **[INFORMATION FEHLT: Erwartete beziehungsweise maximale Benutzerzahl]** |

Für eine noch bessere IHK-Dokumentation sollte später zusätzlich eine **Risikobewertung nach Eintrittswahrscheinlichkeit und Schadenshöhe** ergänzt werden.

---

# 11. Qualitätsziele

Neben der Funktionalität werden folgende Qualitätsziele verfolgt:

### Geschwindigkeit

Die Anwendung soll Daten innerhalb einer definierten maximalen Antwortzeit bereitstellen.

**Zielwert: ≤ 3 Sekunden**

### Stabilität

Die Anwendung soll auch während eines laufenden Turniers zuverlässig funktionieren.

→ **[INFORMATION FEHLT: Konkretes messbares Stabilitäts-/Verfügbarkeitsziel]**

### Usability

Die wichtigsten Informationen sollen schnell auffindbar und übersichtlich dargestellt werden.

### Wartbarkeit

Die Anwendung soll strukturiert aufgebaut sein, sodass zukünftige Änderungen und Erweiterungen mit vertretbarem Aufwand möglich sind.

### Kompatibilität

Die Anwendung muss mit der vorhandenen Datenbank und der vorgesehenen Netzwerkumgebung funktionieren.

### Sicherheit

Der Zugriff soll entsprechend der vorgesehenen Netzwerkumgebung eingeschränkt werden.

→ **[INFORMATION FEHLT: Welche konkreten Sicherheitsanforderungen gelten für die Anwendung?]**

---

# 12. Fachliches Sollkonzept

Ausgehend von der beschriebenen Problemstellung soll die bisherige einfache Tabellenansicht durch eine strukturierte Webanwendung ersetzt beziehungsweise erweitert werden.

Der Benutzer soll auf einer zentralen Übersichtsseite zunächst einen Überblick über das laufende Turnier erhalten. Von dort aus sollen die relevanten Detailinformationen erreichbar sein.

Das vorgesehene Nutzungskonzept umfasst insbesondere:

1. **Turnierübersicht**  
   Anzeige des aktuellen Turnierstands.

2. **Gruppenübersicht**  
   Anzeige der einzelnen Gruppen und der zugehörigen Informationen.

3. **Mannschaftssuche**  
   Suche nach einer bestimmten Mannschaft.

4. **Mannschaftsprofil**  
   Darstellung der für eine Mannschaft relevanten Informationen und Ergebnisse.

5. **Spieleübersicht**  
   Anzeige kommender und abgeschlossener Spiele einschließlich der Ergebnisse.

6. **Live-Aktualisierung**  
   Automatische Übertragung von Änderungen an die Benutzeroberfläche.

---

# 13. Datenmodell

Die Anwendung verwendet die bereits vorhandenen Turnierdaten.

Aus dem vorliegenden ER-Modell ergeben sich unter anderem die Entitäten:

- **Gruppe**
- **Team**
- **Runde**
- **Feld**
- **Spiel**

sowie die zugehörigen Beziehungen.

Beispielsweise wird ein Team einer Gruppe zugeordnet und Spiele werden zwischen Teams ausgetragen. Eine Runde enthält mehrere Spiele beziehungsweise Felder werden für die Durchführung von Spielen verwendet.

Das bestehende Datenmodell soll im Projekt nicht grundlegend neu erstellt, sondern für die neue Anwendung genutzt werden.

**Wichtig für die Dokumentation:** Die detaillierte technische Beschreibung des ER-Modells gehört eher in den Bereich **Analyse/Entwurf**. In der Definitionsphase reicht zunächst die Aussage, dass eine bestehende Datenbasis verwendet wird.

---

# 14. Vorgesehene Schnittstellen

Für die spätere technische Umsetzung sind folgende Schnittstellen vorgesehen:

```text
GET /api/dashboard
GET /api/groups
GET /api/groups/{id}
GET /api/matches
GET /api/matches/{id}
GET /api/matches/filter/{filter}
GET /api/teams
GET /api/teams/{id}
WS  /ws/live
```

Diese Endpunkte stellen aktuell eine **Planung** dar und sollten in der Definitionsphase noch nicht als bereits implementierte Lösung dargestellt werden.

Die konkrete API-Struktur sowie die Entscheidung für REST und WebSocket werden in der Planungs-/Entwurfsphase begründet.

---

# 15. Projektabgrenzung zur bestehenden Lösung

Ein wesentlicher Bestandteil des Projekts ist die Weiterverwendung bereits vorhandener Ressourcen.

| Vorhanden | Wird im Projekt |
|---|---|
| MariaDB-Datenbank | weiterverwendet |
| Turnierdaten | weiterverwendet |
| einfache PHP-Webseite | dient als Ausgangslösung |
| manueller Datenpflegeprozess | bleibt nach aktuellem Stand bestehen |
| neue Benutzeroberfläche | wird entwickelt |
| automatische Aktualisierung | wird entwickelt |
| neue API | wird entwickelt |
| Such-/Filter-/Sortierfunktionen | werden entwickelt |

Dadurch liegt der Schwerpunkt des Projekts nicht auf der Neuerstellung der Datenhaltung, sondern auf der **Entwicklung einer modernen Anwendung zur Aufbereitung und Bereitstellung der bereits vorhandenen Daten**.

---

# 16. Abnahmekriterien

Für eine Note-1-Dokumentation sollten bereits in der Definitionsphase Abnahmekriterien festgelegt werden. Damit lässt sich am Ende objektiv feststellen, ob das Projektziel erreicht wurde.

- Die Turnierübersicht kann innerhalb des ATIW-WLANs aufgerufen werden.
- Die Anwendung zeigt die vorhandenen Gruppen an.
- Die Anwendung zeigt die vorhandenen Mannschaften an.
- Spiele können angezeigt werden.
- Abgeschlossene Spiele werden mit ihrem Ergebnis dargestellt.
- Mannschaften können gesucht werden.
- Relevante Daten können gefiltert beziehungsweise sortiert werden.
- Änderungen an den relevanten Turnierdaten werden automatisch übertragen.
- Die definierte Antwortzeit von maximal 3 Sekunden wird eingehalten.

Für das konkrete Live-Verhalten fehlt noch ein messbarer Wert:

> **[INFORMATION FEHLT: Wie schnell nach einer Änderung in der Datenbank muss diese Änderung auf dem Bildschirm sichtbar sein?]**

---

# 17. Zusammenfassung der Definitionsphase

Das Projekt verfolgt das Ziel, die bestehende Darstellung von Volleyballturnierdaten durch eine übersichtliche und benutzerfreundliche Webanwendung zu ersetzen beziehungsweise zu erweitern.

Die vorhandenen Daten und die bestehende Datenbank werden weiterverwendet. Der Schwerpunkt des Projekts liegt auf der strukturierten Darstellung der Informationen, der Verbesserung der Benutzerführung und der automatischen Aktualisierung während eines laufenden Turniers.

Die Hauptnutzer sind Schülerinnen und Schüler, die sich schnell über den aktuellen Stand des Turniers informieren möchten.

Die Anwendung soll innerhalb des ATIW-WLANs betrieben werden und eine Antwortzeit von maximal drei Sekunden erreichen. Der vorgesehene Projektumfang umfasst 80 Stunden.

Die technische Umsetzung mit React, Kotlin/Spring Boot, REST API und WebSocket wird in den nachfolgenden Projektphasen konkret geplant und umgesetzt.

---

# 18. IHK-Prüferperspektive

## Stärken

- Das eigentliche Problem ist klar erkennbar.
- Der Nutzen für die späteren Benutzer ist nachvollziehbar.
- Bestehende und neu zu entwickelnde Komponenten können voneinander abgegrenzt werden.
- Die Muss-/Soll-/Kann-Priorisierung schafft eine gute Grundlage für die weitere Anforderungsanalyse.
- Mit der maximalen Antwortzeit von 3 Sekunden existiert bereits ein konkretes Qualitätsziel.
- Die vorhandene Datenbank wird sinnvoll als Ausgangspunkt berücksichtigt.

## Noch zu verbessern

### 18.1 Problem quantitativ belegen

Die Aussage, dass die bestehende Oberfläche „nicht übersichtlich“ ist, sollte möglichst durch konkrete Beobachtungen oder Messwerte ergänzt werden.

**[INFORMATION FEHLT: Konkrete Messwerte beziehungsweise Beobachtungen zur bestehenden Lösung]**

### 18.2 Echtzeit definieren

„Echtzeit“ muss als messbares Ziel formuliert werden.

**[INFORMATION FEHLT: Maximale Verzögerung zwischen Datenänderung und Anzeige]**

### 18.3 Projektabgrenzung konkretisieren

Insbesondere muss eindeutig festgelegt werden, ob eine Administrationsoberfläche, Datenbankänderungen und ein öffentliches Deployment ausgeschlossen sind.

### 18.4 Stakeholder bewerten

Neben der Aufzählung sollten Interessen und Einfluss der Stakeholder dokumentiert werden.

### 18.5 Risiken bewerten

Risiken sollten zusätzlich nach Eintrittswahrscheinlichkeit, Auswirkung und Priorität bewertet werden.

### 18.6 Ressourcen ergänzen

Es fehlen noch konkrete Angaben zu:

- Deployment-Hardware
- Entwicklungsumgebung
- Testgeräten
- Server
- Datenbankzugriff
- benötigten Netzwerkfreigaben

**[INFORMATION FEHLT]**

### 18.7 Anforderungen mit IDs versehen

Für den roten Faden durch die gesamte Projektdokumentation empfiehlt sich eine eindeutige Nummerierung, beispielsweise:

- F-01 – Turnierübersicht
- F-02 – Live-Aktualisierung
- F-03 – Mannschaftssuche
- F-04 – Spieleübersicht
- NF-01 – Antwortzeit
- NF-02 – Wartbarkeit

Diese IDs können später in Entwurf, Implementierung und Test wiederverwendet werden.

---

# 19. Empfehlung für die weitere Dokumentationsstruktur

Für die vollständige IHK-Projektdokumentation empfiehlt sich anschließend folgende Struktur:

1. **Definitionsphase**
   - Ausgangssituation
   - Problemstellung
   - Projektauftrag
   - Ziele
   - Anforderungen
   - Stakeholder
   - Rahmenbedingungen
   - Risiken
   - Projektabgrenzung

2. **Anforderungsanalyse**
   - IST-Analyse
   - bestehende Prozesse
   - vorhandene Daten
   - funktionale Anforderungen
   - nichtfunktionale Anforderungen
   - Use Cases
   - Sollprozess

3. **Planungsphase**
   - Projektstruktur
   - Zeitplanung
   - Ressourcenplanung
   - Meilensteine
   - Risikoanalyse
   - Auswahl und Begründung der Technologien

4. **Entwurfsphase**
   - Systemarchitektur
   - Datenmodell
   - API-Konzept
   - Frontend-Konzept
   - UI/UX
   - Kommunikationskonzept
   - Begründung technischer Entscheidungen

5. **Implementierung**
   - Backend
   - REST-Schnittstelle
   - WebSocket/Live-Aktualisierung
   - Frontend
   - Datenbankanbindung
   - relevante technische Entscheidungen

6. **Test und Qualitätssicherung**
   - Teststrategie
   - Testfälle
   - Funktionstests
   - Integrationstests
   - Performance
   - Fehlerbehandlung

7. **Abgabephase**
   - Abnahme
   - Soll-Ist-Vergleich
   - Zielerreichung
   - offene Punkte
   - Fazit
   - mögliche Weiterentwicklung

8. **Anhang**
   - ER-Modell
   - Screenshots
   - Testprotokolle
   - API-Dokumentation
   - ggf. Quellcodeauszüge
