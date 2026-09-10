# Dokumentation

# Ausgangssituation

## Auftrag
Klar, kürzer und direkter:

## Auftrag
Der Auftraggeber des Projekts ist **Frau Geck-Mügge**. Auftragnehmer sind **Radomyr Klymov und Mykyta Riabchenko**. Das Projekt wird im Rahmen eines Schulprojekts am **ATIW Berufskolleg** im Ausbildungsgang **Fachinformatiker für Anwendungsentwicklung** durchgeführt.
Aktuell wird das Volleyballturnier über eine **lokal auf einem Rechner ausgeführte Turnierverwaltung** organisiert. Die dabei erfassten Daten werden in einer bestehenden Datenbank gespeichert und über eine einfache PHP-Webseite tabellarisch angezeigt.
Die lokale Ausführung und die fehlende übersichtliche Weboberfläche erschweren den Teilnehmern den direkten Zugriff auf aktuelle Turnierinformationen. Zudem werden Änderungen nicht automatisch in der Webseite angezeigt.
Ziel des Projekts ist daher die Entwicklung einer **zentral zugänglichen und benutzerfreundlichen Webanwendung**, die den aktuellen Turnierstand, Gruppen, Mannschaften und Spiele übersichtlich darstellt und automatisch aktualisiert.
Die Anwendung soll innerhalb des **ATIW-WLANs** betrieben werden. Die bestehende Datenbank und die vorhandenen Turnierdaten werden weiterverwendet.

# Projektziele
## Terminierung
Für die Durchführung des Projekts steht ein Gesamtzeitbudget von **80 Stunden** zur Verfügung. Die konkrete Verteilung der Arbeitszeit auf die einzelnen Projektphasen wird in der Planungsphase festgelegt.
## Kosten
Für die Umsetzung des Projekts wird ein **Kostenrahmen von 3.000 EUR** veranschlagt.
## Funktionalität
- grafische Darstellung des aktuellen Turnierstands
- automatische Aktualisierung der Turnierdaten
- Darstellung der Spiele
- Darstellung der Gruppen
- Darstellung der Spielfelder
- Übersicht über die teilnehmenden Mannschaften
- Suche nach Mannschaften
- Anzeige der Ergebnisse abgeschlossener Spiele
- Filterung und Sortierung von Daten
- übersichtliche Navigation zwischen den verschiedenen Bereichen
- Darstellung eines Mannschaftsprofils
- Die Anwendung soll innerhalb des **ATIW-WLANs** erreichbar sein.
- für mobile Geräte geeignet 
## Qualität
- **Wartbarkeit:** Die Anwendung soll strukturiert aufgebaut sein, damit spätere Änderungen und Erweiterungen möglich sind.
- **Usability:** Informationen sollen übersichtlich dargestellt und mit möglichst wenigen Interaktionen erreichbar sein.
- **Kompatibilität:** Die Anwendung muss mit der bestehenden Datenbank zusammenarbeiten.

# Umgebung
Das Projekt wird innerhalb der vorhandenen IT-Infrastruktur der ATIW umgesetzt.
Zu den möglichen Risiken gehören:
- bestehende MariaDB-Datenbank
- ATIW-Firewall
- für das Deployment benötigte Hardware
Die Anwendung ist primär für Schülerinnen und Schüler vorgesehen, die während eines Volleyballturniers Informationen über dessen aktuellen Verlauf abrufen möchten. Die Turnierdaten werden weiterhin durch die zuständige Lehrkraft gepflegt.

# Anforderungsanalyse
Die bestehende Lösung stellt die Turnierdaten grundsätzlich bereit, ermöglicht jedoch keine übersichtliche und benutzerfreundliche Darstellung des laufenden Turniers. Die Teilnehmer benötigen daher einen schnellen Zugriff auf den aktuellen Turnierstand sowie auf Informationen zu Gruppen, Mannschaften und Spielen. Zusätzlich sollen die Daten während des laufenden Turniers automatisch aktualisiert werden. Die Anforderungen werden in die Prioritäten MUSS, SOLL und KANN eingeteilt, um den Projektumfang innerhalb des vorgesehenen Zeitbudgets von 80 Stunden gezielt zu steuern.

# IST-Analyse 
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
- Die Anwendung darf ausschließlich innerhalb des **ATIW-Netzwerks** veröffentlicht werden. 
- Für den späteren Betrieb wird entsprechende Hardware benötigt.
- Die bestehende Datenbank soll weiterverwendet werden.
- Die Datenpflege erfolgt weiterhin über den bestehenden Prozess.

# Sollkonzept

## Umfeld
Die neue Anwendung dient als zentrale Informationsoberfläche für die Teilnehmer eines Volleyballturniers. Der Benutzer soll ohne besondere technische Kenntnisse auf die relevanten Turnierinformationen zugreifen können. 
Der geplante Informationsfluss lautet:
**Lehrkraft → Datenbank → Backend/API → Webanwendung → Benutzer**
Die bestehende Datenbank bleibt dabei die Grundlage für die Turnierdaten. Die neue Anwendung übernimmt insbesondere die Aufbereitung und Darstellung dieser Daten.

# Use Case
## Benutzer
Die Hauptnutzer der Anwendung sind Schülerinnen und Schüler beziehungsweise Teilnehmer des Volleyballturniers. Für die Nutzung der Anwendung ist nach aktuellem Stand keine Anmeldung erforderlich.
## Haupt-Use-Cases
### UC-01: Turnierübersicht anzeigen
Der Benutzer öffnet die Anwendung und erhält einen Überblick über den aktuellen Stand des Turniers. Dabei sollen relevante Informationen zu Gruppen, Mannschaften und Spielen übersichtlich dargestellt werden.
### UC-02: Gruppe anzeigen
Der Benutzer wählt eine Gruppe aus und erhält die zugehörigen Informationen.
### UC-03: Mannschaftsinformationen anzeigen
Der Benutzer öffnet das Profil einer Mannschaft und kann deren relevante Turnierinformationen und Ergebnisse einsehen.
### UC-04: Spiele anzeigen
Der Benutzer kann kommende und bereits abgeschlossene Spiele einsehen. Bei abgeschlossenen Spielen werden die vorhandenen Ergebnisse angezeigt.

## Funktionalität
### MUSS
1. Grafische Hauptseite mit aktuellem Turnierstand
2. automatische Aktualisierung der Turnierdaten
3. Darstellung der Gruppen
4. Darstellung der Spielfelder
5. Teamübersicht
6. Mannschaftssuche
7. Übersicht über Spiele
8. Darstellung abgeschlossener Spiele
9. Anzeige der Spielergebnisse
### SOLL
- Kompatibilität mit unterschiedlichen Endgeräten
- Leaderboard
- komfortable Filterung
- komfortable Sortierung
- klare Seitenstruktur
- Navigation zwischen den einzelnen Bereichen
### KANN
- Speicherung von Einstellungen über Cookies
- Anpinnen einer Lieblingsmannschaft
- Anzeige eines Schiedsrichters
  
## ERM

## Schnittstellen
Für die Kommunikation zwischen Frontend und Backend ist eine REST-Schnittstelle vorgesehen.
```text
GET /api/groups
Liefert eine Übersicht aller vorhandenen Gruppen. 
GET /api/groups/{id}
Liefert die Details einer bestimmten Gruppe anhand ihrer ID.
GET /api/matches
Liefert eine Übersicht der vorhandenen Spiele.  
GET /api/matches/{id}
Liefert die Details eines bestimmten Spiels anhand seiner ID.
GET /api/matches/filter/{filter}
Liefert Spiele entsprechend einem angegebenen Filter, beispielsweise alle Spiele alle Spiele einer bestimmten Runde.
GET /api/teams
Liefert eine Übersicht aller teilnehmenden Mannschaften. 
GET /api/teams/{id}
Liefert die Details einer bestimmten Mannschaft anhand ihrer ID.
```
Für die automatische Übertragung von Änderungen ist zusätzlich eine WebSocket-Schnittstelle vorgesehen:
```text
WS /ws/live
Stellt eine dauerhafte Verbindung zwischen Frontend und Backend her und ermöglicht die Übertragung von Aktualisierungen an die Benutzeroberfläche, ohne dass die Webseite manuell neu geladen werden muss.  
```

## Entwurf von Prozesse 
### Abruf der Turnierübersicht
Der Benutzer öffnet die Webanwendung.
1. Das Frontend stellt eine Anfrage an das Backend.
2. Das Backend verarbeitet die Anfrage.
3. Das Backend greift auf die bestehende Datenbank zu.
4. Die benötigten Turnierdaten werden ermittelt.
5. Die Daten werden über die API an das Frontend übertragen.
6. Das Frontend stellt die Daten grafisch dar.
**Benutzer → React → REST API → Backend → MariaDB**
Anschließend:
**MariaDB → Backend → REST API → React → Benutzer**
### Automatische Aktualisierung
Während des Turniers werden Daten durch die Lehrkraft aktualisiert.
Nach einer Änderung sollen die betroffenen Informationen automatisch an die verbundenen Benutzer übertragen werden.
Der geplante Ablauf ist:
**Datenänderung → Backend erkennt/erhält Änderung → WebSocket → Frontend → aktualisierte Darstellung**
### Mannschaftssuche
Der Benutzer gibt einen Suchbegriff für eine Mannschaft ein. Das Frontend übermittelt die Suchanfrage an das Backend beziehungsweise verwendet die dafür bereitgestellten Daten. Das Backend ermittelt die passenden Mannschaften aus den vorhandenen Daten. Anschließend werden die Suchergebnisse im Frontend dargestellt.

## Qualitätsziele
### Usability
Die Benutzeroberfläche soll:
- übersichtlich strukturiert sein
- eine klare Navigation besitzen
- relevante Informationen schnell zugänglich machen
- auf unterschiedlichen Endgeräten nutzbar sein
- eine verständliche Darstellung der Turnierinformationen ermöglichen
## Wartbarkeit
Die Software soll strukturiert und modular aufgebaut werden. Dadurch sollen zukünftige Änderungen und Erweiterungen erleichtert werden.

## Eingesetzte Technologien
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
