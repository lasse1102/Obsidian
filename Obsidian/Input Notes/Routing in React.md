
--- 
Erstellt: 2025-09-04    14:16 
Tags: #Programming/JavaScript/React  
Link Up: [[JavaScript]]
Link Down:

--- 
### Installation
Um **React Router** zu installieren, öffne dein Terminal im Projektordner und führe den folgenden Befehl aus: `npm install react-router-dom`

### Einbindung in deine Anwendung

#### 1. Den Router importieren und einbinden
In deiner Hauptdatei (z.B. `index.js` oder `main.jsx`) musst du den `BrowserRouter` importieren und deine Hauptkomponente (`App`) damit umhüllen. Dies ermöglicht der gesamten Anwendung, die Routing-Funktionalität zu nutzen.

![[Pasted image 20250904141920.png]]

#### 2. Routen definieren
In deiner Hauptkomponente (z.B. `App.js`) definierst du die Routen. Hierfür verwendest du die Komponenten `<Routes>` und `<Route>`.
- **`<Routes>`**: Dies ist der übergeordnete Container, der die Routen-Definitionen enthält. Er schaut sich die aktuelle URL an und rendert die erste `<Route>`, die übereinstimmt.
- **`<Route>`**: Definiert einen spezifischen Pfad (`path`) und die Komponente (`element`), die bei Übereinstimmung gerendert werden soll.

![[Pasted image 20250904142120.png]]

#### Wichtiger Hinweis:
Ein `<Route>` darf nur als Kind eines `<Routes>`-Elements verwendet werden. Das ist eine wichtige Regel in React Router v6, um die Routing-Logik übersichtlicher und effizienter zu gestalten.


### Element für 2 Routen zugänglich machen

![[Pasted image 20250904142345.png]]







## References
1. 
