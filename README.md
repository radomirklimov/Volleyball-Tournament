# Definitionsphase – Was ist das Projekt?

## Ausgangssituation

### Auftrag
- **Auftraggeber:** Frau Geck-Mügge  
- **Auftragnehmer:** Radomyr Klymov, Mykyta Riabchenko  

### Was möchte der Auftraggeber?
- Eine Anwendung zur Ansicht der Volleyballturniere in Echtzeit.

### Warum ist es wichtig?
- Zurzeit gibt es keine klare UI dafür.

### Was lösen wir?
- Die Teilnehmer wurden nicht über den Stand des Volleyballturniers informiert.

### Was gibt es bereits?
- Eine Datenbank und eine einfache PHP-Webseite.

---

# Projektziele

### Terminierung
- **80 Stunden**

### Kosten
- **15 EUR/Stunde**

### Funktionalität
- Echtzeit-Darstellung der Daten  
- Zugriff über lokales ATIW WLAN

### UI Features
- Filterung  
- Sortierung  
- Ablauf eines Turniers  
- Dashboard  
- Suchseite  
- Mannschaftsprofil  

### Qualität
- Kompatibilität mit Datenbank  
- Antwortzeit: **≤ 3 Sekunden**  
- Wartbarkeit  
- Usability  

---

# Umgebung

### Teilnehmer
- Mykyta Riabchenko  
- Radomyr Klymov  
- Frau Geck-Mügge  

### Abhängigkeiten
- ATIW Firewall  
- Datenbank  

### Risiken
- Serverausfall  
- Fehler im ATIW WLAN  

---

# Anforderungsanalyse

## IST-Analyse
- Lehrkraft aktualisiert die Datenbank manuell während des Turniers.
- Webseite ruft die Daten ab und zeigt sie tabellarisch an.

## Vorhandene Prozesse
- Manuelle Datenaktualisierung  
- Tabellarische Darstellung  

## Probleme der letzten Realisierung
- Kein Design, keine Struktur (hauptsächlich HTML)  
- Keine Echtzeit-Anzeige  

## Vorhandene Daten
- Platzierungen  
- Spiele  
- Mannschaften  
- Spielgruppen  

## Einschränkungen
- Veröffentlichung nur im ATIW-Netz erlaubt  
- Hardware für Deployment notwendig  

---

# Sollkonzept

## Umfeld

### Nutzer
- Hauptsächlich Schüler

### Zweck
- Information über den Verlauf des Turniers

### Szenarien
- Übersicht des gesamten Turniers  
- Übersicht einer Gruppe  
- Mannschaftssuche  
- Ergebnisse eines Teams  

---

# Use Case

### Benutzer
- Normale Benutzer

### Aktionen
- Voller Zugang zu allen Funktionen der Webseite

### Szenarien
- Übersicht des Turniers  
- Übersicht einer Gruppe  
- Mannschaftssuche  
- Ergebnisse eines Teams  

---

# Funktionalität

## Muss
- Grafische Hauptseite mit aktuellem Turnierstand  
- Automatische Echtzeit-Aktualisierung  
- Darstellung von Gruppen/Feldern  
- Teamübersicht und Suche  
- Spieleseite (kommende & abgeschlossene Spiele mit Ergebnissen)

## Soll
- Gerätekompatibilität  
- Leaderboard  
- Angenehme Filterung & Sortierung  
- Klare Seitenstruktur  
- Navigation zwischen Bereichen  

## Kann
- Session-Speicherung durch Cookies  
- Lieblings-Team anpinnen  
- Schiedsrichter anzeigen  
- Spielfeld der Mannschaft anzeigen  

---

# ERM (Entity-Relationship-Modell)

- Beschreibung der Entities  
- Attribute  
- Beziehungen  
- Hinweis: Daten sind bereits vorhanden und werden genutzt  

---

# Schnittstellen (API)

### Geplante Endpunkte
- `GET /api/dashboard`  
- `GET /api/groups`  
- `GET /api/groups/{id}`  
- `GET /api/matches`  
- `GET /api/matches/{id}`  
- `GET /api/matches/filter/{filter}`  
- `WS /ws/live`  
- `GET /api/teams`  
- `GET /api/teams/{id}`  

---

# Prozesse, Abläufe, Sequenzen

### Qualitätsziele
- Geschwindigkeit  
- Stabilität  
- Sicherheit  
- UX  

### Messbarkeit
- Antwortzeit  
- Fehlerquote  
- Stabilität unter Last  

### Technologien
- Websocket  
- REST API  
- Datenbank (bestehend)  
- Frontend-Framework (optional)

### Usability & Softwareergonomie
- Klare Navigation  
- Mobile Kompatibilität  
- Barrierearme Darstellung  

---

# Planungsphase
- Wie erreichen wir das?

# Entwurf
- Wie funktioniert das?

# Implementation
- Code schreiben  
- Unittests  
- Metriken  

# Abgabephase
- Was wurde gemacht?
