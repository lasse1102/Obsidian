
--- 
Erstellt: 2025-08-21    09:17 
Tags: 
Link Up: 
Link Down:

--- 
# Idee / Ziele

Das Projekt soll eine Web App darstellen. Es soll darauf ausgelegt sein eine bessere Planung und Struktur in seinen Bürojob zu erhalten. Es kann sowohl alleine als auch als Team genutzt werden.

##### Features
1. Kalenderansicht (Hauptfeature)
	- Man kann neue Termine erstellen die man nur selbe sieht oder auch alle Teammitglieder
	- Bearbeiten und Löschen von selbst erstellten Terminen
2. To do Liste
	- Man kann mehrere Listen erstellen
	- Eine Liste hat 2 Abteile (To do, Completed)
	- Filter/sortieren Feature
	- Datum kann hinzugefügt werden und bei Bedarf auch in Kalender eingetragen werden
3. Projekte Planer
	- Hier können Projekte geplant werden (alleine oder mit Teammitglieder)
	- Das ganze soll als Kanban Board dargestellt werden. Jedes Projekt ist ein Kanban Board
	- Spalten können selber erstellt werden (z.B. To do, In Bearbeitung, Überprüfung, Erledigt)
	- Man kann Karten erstellen die die Aufgaben wiederspiegeln
	- Per Drag & Drop kann man sie zwischen den Spalten hin und her schieben
4. Notizen
	Könnte anschließend bei Bedarf implementiert werden sollte zuerst aber kein Fokus drauf gelegt sein.


# Umsetzung

#### Phase 1: Die Grundmauern bauen (Setup & Basis)
Bevor du mit den Features beginnst, musst du das Fundament legen. Ein sauberes Fundament spart dir später viel Zeit und Frust.

1. **Tech-Stack finalisieren**: Bestätige, ob du bei **React** im Frontend und **Node.js/Express** mit **PostgreSQL** (wie wir besprochen haben) im Backend bleibst. Diese Wahl ist sehr gut für dein Vorhaben.
2. **Entwicklungsumgebung einrichten**: Installiere alle notwendigen Tools (Node.js, einen Code-Editor wie VS Code, etc.).
3. **Projekt-Struktur anlegen**: Erstelle zwei separate Verzeichnisse: eines für dein Frontend (`/client`) und eines für dein Backend (`/server`).
    
4. **Datenbank-Schema entwerfen**: Dies ist der **wichtigste erste Schritt**. Visualisiere, wie deine Tabellen aussehen:
    - **`users`**: Speichert Informationen wie `name`, `email` und ein gehashtes `password`.
    - **`teams`**: Speichert Informationen über die Teams.
    - **`user_teams`**: Eine Verknüpfungstabelle, die festlegt, welche User in welchem Team sind.
    - **`events`**: Für Kalendereinträge. Felder wie `title`, `start_date`, `end_date`, `is_private` und `team_id` (kann `null` sein, wenn der Termin privat ist).
    - **`lists`**: Für deine To-do-Listen.
    - **`tasks`**: Die einzelnen Aufgaben innerhalb einer Liste. 
    - **`projects`**: Für deine Kanban-Boards.
    - **`columns`**: Die Spalten eines Kanban-Boards.
    - **`kanban_cards`**: Die einzelnen Aufgaben-Karten in den Spalten.
        

---

#### Phase 2: Das Rückgrat der App (User- & Team-Management)

Beginne mit den Funktionen, die für alle anderen Features notwendig sind.

1. **Backend (API)**
    - Implementiere die **Benutzerauthentifizierung** (Registrierung, Login, Token-basierte Authentifizierung).
    - Erstelle API-Endpunkte, um **Teams zu erstellen** und **Teammitglieder einzuladen**.
    - Stelle sicher, dass nur angemeldete Benutzer auf die geschützten Routen zugreifen können.
        
2. **Frontend (UI)**
    - Erstelle eine **Login- und Registrierungsseite**.
    - Baue eine **Hauptoberfläche**, die nur nach dem Login zugänglich ist.
    - Implementiere die Logik, um Teams zu erstellen und zu verwalten.

---

#### Phase 3: Die Features umsetzen (einzeln nacheinander)

Gehe die geplanten Features in logischer Reihenfolge an, beginnend mit dem Herzstück deiner App.

1. **Kalenderansicht (Hauptfeature)**
    - **Backend**: Erstelle API-Endpunkte, um Termine zu erstellen, zu bearbeiten, zu löschen und abzurufen. Berücksichtige dabei, ob ein Termin privat oder teamweit ist.
    - **Frontend**: Integriere eine Kalender-Komponente (z. B. `react-big-calendar`). Verknüpfe die Komponente mit den API-Endpunkten, sodass Termine aus der Datenbank geladen und gespeichert werden können.
2. **To-do-Liste**
    - **Backend**: Erstelle Endpunkte für Listen (`lists`) und Aufgaben (`tasks`). Jede Liste gehört zu einem User oder einem Team.
    - **Frontend**: Baue Komponenten für die To-do-Listen und ihre Unterteilungen (`To do`, `Completed`). Implementiere die Filter- und Sortierfunktionen auf Basis der Daten aus der API.
3. **Projekte Planer (Kanban Board)**
    - **Backend**: Dies ist die komplexeste Datenstruktur. Du benötigst Endpunkte für Projekte, Spalten und Karten. Die Spalten müssen mit den Projekten verknüpft sein, und die Karten mit den Spalten.
    - **Frontend**: Nutze eine Bibliothek für Drag-and-Drop (z. B. `react-beautiful-dnd`) für die Karten. Stelle das Kanban-Board dynamisch basierend auf den Daten aus deiner API dar.






















## References
1. [[Second Brain Planer]]
