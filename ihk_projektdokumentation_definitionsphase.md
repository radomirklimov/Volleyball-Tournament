# Dokumentation

# Ausgangssituation

## Auftrag
Der Auftraggeber des Projekts ist **Frau Geck-Mügge**. Auftragnehmer sind **Radomyr Klymov und Mykyta Riabchenko**. Aufgabe des Projekts ist die Entwicklung einer Webanwendung zur übersichtlichen Darstellung von Volleyballturnieren. Die Anwendung soll den Teilnehmern ermöglichen, sich während eines laufenden Turniers schnell über den aktuellen Turnierstand, Gruppen, Mannschaften und Spiele zu informieren. Als Grundlage wird eine bereits vorhandene Datenbank mit den benötigten Turnierdaten verwendet. Zusätzlich existiert eine einfache PHP-Webseite, über die die Daten derzeit tabellarisch dargestellt werden. Die bestehende Lösung soll durch eine strukturierte und benutzerfreundliche Webanwendung ersetzt. Ein besonderer Schwerpunkt liegt auf der automatischen Aktualisierung der angezeigten Daten während des laufenden Turniers.

# Projektziele
## Terminierung
Für die Durchführung des Projekts steht ein Gesamtzeitbudget von **80 Stunden** zur Verfügung. Die konkrete Verteilung der Arbeitszeit auf die einzelnen Projektphasen wird in der Planungsphase festgelegt.
## Kosten
Für die Projektkalkulation wird ein Stundensatz von **15 EUR** angesetzt. Bei einem Gesamtaufwand von 80 Stunden ergibt sich ein kalkulatorischer Projektaufwand von **1.200 EUR**
## Funktionalität
- grafische Darstellung des aktuellen Turnierstands
- automatische Aktualisierung der Turnierdaten
- Darstellung der Spiele
- Darstellung der vorhandenen Gruppen
- Darstellung der Spielfelder
- Übersicht über die teilnehmenden Mannschaften
- Suche nach Mannschaften
- Anzeige der Ergebnisse abgeschlossener Spiele
- Filterung und Sortierung von Daten
- übersichtliche Navigation zwischen den verschiedenen Bereichen
- Darstellung eines Mannschaftsprofils
- Die Anwendung soll innerhalb des **ATIW-WLANs** erreichbar sein.
## Qualität
- **Wartbarkeit:** Die Anwendung soll strukturiert aufgebaut sein, damit spätere Änderungen und Erweiterungen möglich sind.
- **Usability:** Informationen sollen übersichtlich dargestellt und mit möglichst wenigen Interaktionen erreichbar sein.
- **Kompatibilität:** Die Anwendung muss mit der bestehenden Datenbank zusammenarbeiten.

# UMGEBUNG
Das Projekt wird innerhalb der vorhandenen IT-Infrastruktur der ATIW umgesetzt.
Zu den möglichen Risiken gehören:
- bestehende MariaDB-Datenbank
- ATIW-Firewall
- für das Deployment benötigte Hardware
Die Anwendung ist primär für Schülerinnen und Schüler vorgesehen, die während eines Volleyballturniers Informationen über dessen aktuellen Verlauf abrufen möchten. Die Turnierdaten werden weiterhin durch die zuständige Lehrkraft gepflegt.

# ANFORDERUNGSANALYSE
Die vorhandene Lösung stellt die Daten grundsätzlich bereit, ermöglicht jedoch keine komfortable und übersichtliche Darstellung des laufenden Turniers. Aus Sicht der Benutzer besteht insbesondere der Bedarf, den aktuellen Stand des Turniers schnell erfassen zu können. Dafür müssen relevante Informationen wie Gruppen, Mannschaften und Spiele strukturiert dargestellt werden. Die Anforderungen werden in drei Prioritätsstufen eingeteilt. Die Priorisierung ermöglicht es, den Projektumfang bei begrenztem Zeitbudget von 80 Stunden kontrolliert zu steuern.

# ISTANALYSE
## Bestehender Prozess
Die Turnierdaten werden während des Turniers durch die zuständige Lehrkraft manuell in der bestehenden Datenbank aktualisiert. Die vorhandene Webseite ruft die Daten anschließend aus der Datenbank ab und stellt diese überwiegend tabellarisch dar.
Der derzeitige Ablauf lässt sich vereinfacht wie folgt darstellen:
**Lehrkraft → manuelle Datenaktualisierung → Datenbank → PHP-Webseite → Benutzer**
## Vorhandene Daten
In der bestehenden Datenbasis befinden sich unter anderem Informationen zu:
- Runden
- Gruppen
- Mannschaften
- Spielen
- Spielfeldern
- Ergebnissen
- Teilnahme der Mannschaft
## Probleme der bestehenden Lösung
Die bestehende Webseite weist insbesondere folgende Einschränkungen auf:
- überwiegend tabellarische Darstellung
- keine moderne grafische Benutzeroberfläche
- eingeschränkte Übersichtlichkeit
- keine automatische Echtzeit-Aktualisierung
- keine komfortable Mannschaftssuche
- keine Filter- und Sortiermöglichkeiten
## Einschränkungen

Die Anwendung darf nach den aktuellen Rahmenbedingungen ausschließlich innerhalb des **ATIW-Netzwerks** veröffentlicht werden.

Für den späteren Betrieb wird entsprechende Hardware benötigt.

Weitere Einschränkungen:

- Die bestehende Datenbank soll weiterverwendet werden.
- Die Datenpflege erfolgt weiterhin über den bestehenden Prozess.

**[INFORMATION FEHLT: Genaues Verfahren der Datenpflege und verwendetes System durch die Lehrkraft]**

# SOLLKONZEPT

## UMFELD

Die neue Anwendung dient als zentrale Informationsoberfläche für die Teilnehmer eines Volleyballturniers.

Der Benutzer soll ohne besondere technische Kenntnisse auf die relevanten Turnierinformationen zugreifen können.

Der geplante Informationsfluss lautet:

**Lehrkraft → Datenbank → Backend/API → Webanwendung → Benutzer**

Die bestehende Datenbank bleibt dabei die Grundlage für die Turnierdaten.

Die neue Anwendung übernimmt insbesondere die Aufbereitung und Darstellung dieser Daten.

# USECASE

## Benutzer

Als Benutzer wird ein normaler Teilnehmer beziehungsweise Besucher der Anwendung betrachtet.

Eine Anmeldung ist nach aktuellem Stand nicht vorgesehen.

**[INFORMATION FEHLT: Ob tatsächlich keine Benutzerverwaltung vorgesehen ist]**

## Haupt-Use-Cases

### UC-01: Turnierübersicht anzeigen

Der Benutzer öffnet die Anwendung und erhält einen Überblick über den aktuellen Stand des Turniers.

Dabei sollen relevante Informationen zu Gruppen, Mannschaften und Spielen übersichtlich dargestellt werden.

### UC-02: Gruppe anzeigen

Der Benutzer wählt eine Gruppe aus und erhält die zugehörigen Informationen.

### UC-03: Mannschaft suchen

Der Benutzer sucht nach einer bestimmten Mannschaft und erhält deren relevante Informationen.

### UC-04: Mannschaftsinformationen anzeigen

Der Benutzer öffnet das Profil einer Mannschaft und kann deren relevante Turnierinformationen und Ergebnisse einsehen.

### UC-05: Spiele anzeigen

Der Benutzer kann kommende und bereits abgeschlossene Spiele einsehen.

Bei abgeschlossenen Spielen werden die vorhandenen Ergebnisse angezeigt.

### UC-06: Turnierdaten automatisch aktualisieren

Während des laufenden Turniers werden Änderungen an den relevanten Daten automatisch an die Benutzeroberfläche übertragen.

Ein manuelles Neuladen der Webseite soll hierfür nicht erforderlich sein.

# FUNCTIONALITAET

## MUSS

Folgende Funktionen sind für die Anwendung zwingend erforderlich:

1. Grafische Hauptseite mit aktuellem Turnierstand
2. automatische Aktualisierung der Turnierdaten
3. Darstellung der Gruppen
4. Darstellung der Spielfelder
5. Teamübersicht
6. Mannschaftssuche
7. Übersicht über Spiele
8. Darstellung kommender Spiele
9. Darstellung abgeschlossener Spiele
10. Anzeige der Spielergebnisse

## SOLL

Folgende Funktionen sollen umgesetzt werden:

- Kompatibilität mit unterschiedlichen Endgeräten
- Leaderboard
- komfortable Filterung
- komfortable Sortierung
- klare Seitenstruktur
- Navigation zwischen den einzelnen Bereichen

## KANN

Folgende Funktionen stellen optionale Erweiterungen dar:

- Speicherung von Einstellungen über Cookies
- Anpinnen einer Lieblingsmannschaft
- Anzeige eines Schiedsrichters
- Anzeige des Spielfelds einer Mannschaft

Die Kann-Anforderungen besitzen eine geringere Priorität und werden nur umgesetzt, wenn dies innerhalb des verfügbaren Zeitbudgets möglich ist.

# ERM

Die Anwendung greift auf eine bereits vorhandene Datenstruktur zurück.

Das bestehende Entity-Relationship-Modell enthält unter anderem folgende Entitäten:

- **Runde**
- **Gruppe**
- **Team**
- **Feld**
- **Spiel**

### Runde

Eine Runde wird über eine eindeutige ID und eine Nummer identifiziert.

### Gruppe

Eine Gruppe wird über eine Gruppen-ID und eine Bezeichnung beschrieben.

### Team

Ein Team besitzt unter anderem eine ID, eine Klasse und einen Namen.

Teams werden Gruppen zugeordnet.

### Feld

Ein Feld besitzt eine eindeutige ID und eine Bezeichnung beziehungsweise einen Namen.

### Spiel

Ein Spiel enthält die Informationen über die beteiligten Mannschaften und das Ergebnis. Im vorhandenen Modell werden unter anderem die Punkte der beiden beteiligten Mannschaften gespeichert.

Die Beziehungen zwischen den Entitäten bilden beispielsweise ab:

- Eine Runde enthält mehrere Felder beziehungsweise Spiele.
- Eine Gruppe enthält mehrere Teams.
- Ein Spiel wird zwischen Teams ausgetragen.
- Ein Spiel findet auf einem Feld statt.

**Hinweis:** Die genaue Kardinalität der einzelnen Beziehungen sollte entsprechend des tatsächlich verwendeten Datenbankschemas dokumentiert werden.

# SCHNITTSCHTELLEN

Für die Kommunikation zwischen Frontend und Backend ist eine REST-Schnittstelle vorgesehen.

Geplante Endpunkte:

```text
GET /api/dashboard
GET /api/groups
GET /api/groups/{id}
GET /api/matches
GET /api/matches/{id}
GET /api/matches/filter/{filter}
GET /api/teams
GET /api/teams/{id}
```

Für die automatische Übertragung von Änderungen ist zusätzlich eine WebSocket-Schnittstelle vorgesehen:

```text
WS /ws/live
```

## Zweck der REST-Schnittstelle

Die REST-Schnittstelle stellt die benötigten Turnierdaten für das Frontend bereit.

Beispielsweise können darüber Gruppen, Mannschaften oder Spiele abgerufen werden.

## Zweck der WebSocket-Schnittstelle

Die WebSocket-Verbindung soll für die automatische Aktualisierung der Benutzeroberfläche verwendet werden.

Dadurch soll vermieden werden, dass der Benutzer die Webseite manuell aktualisieren muss.

**[INFORMATION FEHLT: Welche konkreten Daten beziehungsweise Events werden über den WebSocket übertragen?]**

# ENTWURF VON PROCESSEN

## Abruf der Turnierübersicht

Der Benutzer öffnet die Webanwendung.

1. Das Frontend stellt eine Anfrage an das Backend.
2. Das Backend verarbeitet die Anfrage.
3. Das Backend greift auf die bestehende Datenbank zu.
4. Die benötigten Turnierdaten werden ermittelt.
5. Die Daten werden über die API an das Frontend übertragen.
6. Das Frontend stellt die Daten grafisch dar.

Vereinfacht:

**Benutzer → React → REST API → Backend → MariaDB**

Anschließend:

**MariaDB → Backend → REST API → React → Benutzer**

## Automatische Aktualisierung

Während des Turniers werden Daten durch die Lehrkraft aktualisiert.

Nach einer Änderung sollen die betroffenen Informationen automatisch an die verbundenen Benutzer übertragen werden.

Der geplante Ablauf ist:

**Datenänderung → Backend erkennt/erhält Änderung → WebSocket → Frontend → aktualisierte Darstellung**

Der Benutzer muss die Webseite dabei nicht manuell neu laden.

**[INFORMATION FEHLT: Wie wird die Änderung im Backend erkannt?]**

## Mannschaftssuche

Der Benutzer gibt einen Suchbegriff für eine Mannschaft ein.

Das Frontend übermittelt die Suchanfrage an das Backend beziehungsweise verwendet die dafür bereitgestellten Daten.

Das Backend ermittelt die passenden Mannschaften aus den vorhandenen Daten.

Anschließend werden die Suchergebnisse im Frontend dargestellt.

## Anzeige eines Spiels

Der Benutzer öffnet die Spieleübersicht.

Die Anwendung ruft die vorhandenen Spiele ab und unterscheidet zwischen kommenden und abgeschlossenen Spielen.

Bei abgeschlossenen Spielen werden die gespeicherten Ergebnisse angezeigt.

# QUALITAETZIELE

## Geschwindigkeit

Die Antwortzeit der Anwendung soll maximal **3 Sekunden** betragen.

Dieses Ziel soll durch Messungen während der Testphase überprüft werden.

## Stabilität

Die Anwendung soll während des Turnierbetriebs zuverlässig funktionieren.

**[INFORMATION FEHLT: Konkretes messbares Stabilitätsziel, beispielsweise maximale Fehlerquote oder Mindestverfügbarkeit]**

## Sicherheit

Die Anwendung soll entsprechend der vorgesehenen Netzwerkumgebung betrieben werden.

Der Zugriff ist auf das **ATIW-WLAN** beschränkt.

**[INFORMATION FEHLT: Konkrete Anforderungen an Authentifizierung, Autorisierung und weitere Sicherheitsmaßnahmen]**

## Usability

Die Benutzeroberfläche soll:

- übersichtlich strukturiert sein
- eine klare Navigation besitzen
- relevante Informationen schnell zugänglich machen
- auf unterschiedlichen Endgeräten nutzbar sein
- eine verständliche Darstellung der Turnierinformationen ermöglichen

## Wartbarkeit

Die Software soll strukturiert und modular aufgebaut werden. Dadurch sollen zukünftige Änderungen und Erweiterungen erleichtert werden.

# EINGESETZTE TECHNOLOGIEN

Für die Umsetzung sind folgende Technologien vorgesehen:

| Technologie | Einsatzbereich |
|---|---|
| **Kotlin** | Backend-Entwicklung |
| **Spring Boot** | Entwicklung des Backend-Systems |
| **React** | Entwicklung der Benutzeroberfläche |
| **JavaScript** | Funktionalität im Frontend |
| **HTML** | Struktur der Webseiten |
| **CSS** | Gestaltung der Benutzeroberfläche |
| **REST API** | Kommunikation zwischen Frontend und Backend |
| **WebSocket** | automatische Übertragung von Aktualisierungen |
| **MariaDB** | bestehende Datenhaltung |

Die bestehende **MariaDB-Datenbank** wird weiterverwendet.

Die Kombination aus REST API und WebSocket ist vorgesehen, um zwischen dem initialen Abruf von Daten und der laufenden Aktualisierung zu unterscheiden. Die REST-Schnittstelle dient dabei der Bereitstellung von Daten, während WebSocket für die Übertragung von Änderungen während des laufenden Betriebs vorgesehen ist.

**[INFORMATION FEHLT: Konkrete Begründung, warum Kotlin/Spring Boot, React und WebSocket gegenüber möglichen Alternativen ausgewählt wurden.]**

---

# IHK-PRÜFERCHECK

Aus Prüfersicht bildet die Dokumentation einen nachvollziehbaren roten Faden:

**Ausgangssituation → Problem → Ziele → Ist-Analyse → Soll-Konzept → Anforderungen → Prozesse → Technologien**

Für eine sehr gute IHK-Dokumentation sollten insbesondere folgende Punkte noch ergänzt werden:

1. **Ist-Zustand quantifizieren**
   - Anzahl der Teams
   - Anzahl der Spiele
   - erwartete Benutzerzahl
   - Häufigkeit der Datenaktualisierung
   - aktueller Zeitaufwand für die Informationsbeschaffung

2. **Echtzeit konkret definieren**

   Es sollte festgelegt werden, innerhalb welcher maximalen Zeit eine Änderung nach ihrer Erfassung in der Benutzeroberfläche sichtbar sein muss.

3. **Projektabgrenzung schärfen**

   Es sollte eindeutig festgehalten werden, welche Aufgaben nicht Bestandteil des Projekts sind, insbesondere ob die Datenbank und die Datenpflege vollständig außerhalb des Projektumfangs liegen.

4. **Stakeholder detaillierter betrachten**

   Für eine professionelle Darstellung können Interesse, Einfluss und Anforderungen der einzelnen Stakeholder gegenübergestellt werden.

5. **Risiken bewerten**

   Die Risiken sollten später um Eintrittswahrscheinlichkeit, Auswirkung, Priorität und konkrete Gegenmaßnahmen ergänzt werden.

6. **Ressourcen dokumentieren**

   Benötigte Hardware, Entwicklungsumgebung, Server und Testgeräte sollten aufgeführt werden.

7. **Anforderungen nummerieren**

   Es empfiehlt sich, Anforderungen mit IDs wie `F-01`, `F-02` usw. zu versehen und diese IDs später in Entwurf, Implementierung und Test wiederzuverwenden.

8. **Technologieentscheidungen begründen**

   Die Auswahl von React, Kotlin/Spring Boot und WebSocket sollte anhand der tatsächlichen Projektanforderungen begründet werden.

9. **ERM mit der tatsächlichen Datenbank abgleichen**

   Die dargestellten Entitäten und Kardinalitäten müssen exakt der vorhandenen Datenbank entsprechen.
