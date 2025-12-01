
--- 
Erstellt: 2025-08-22    11:34 
Tags: 
Link Up: [[React Grundlagen]]
Link Down:

--- 
## 📂 Typische React-Projektstruktur
![[Pasted image 20250822113730.png]]
### 📑 Erklärung der Ordner & Dateien

### **1. `node_modules/`**
- Enthält alle installierten **Dependencies** (z. B. React, ReactDOM, andere Bibliotheken).
- Wird automatisch erstellt, wenn du `npm install` ausführst.
- ➡️ Nicht selber bearbeiten!

---

### **2. `public/`**
- Enthält statische Dateien, die **nicht von React verarbeitet** werden.
- **Wichtige Files:**
    - `index.html`: Das Haupt-HTML-Template, in das deine React-App eingebunden wird.
    - `favicon.ico`: Das kleine Icon im Browser-Tab.
    - `manifest.json`: App-Infos für PWA (Progressive Web App).

---

### **3. `src/`**
- Hier liegt **dein ganzer React-Code**.
- **Wichtige Files:**
    - `index.js`: Einstiegspunkt der App → rendert `<App />` in das `index.html`.
    - `App.js`: Hauptkomponente, die meistens die Basis deiner App darstellt.
    - `App.css`: CSS für `App.js`.
    - `index.css`: Globale Styles.
    - `components/`: Hier packt man wiederverwendbare UI-Bausteine (z. B. Buttons, Navbar, Cards).
    - `assets/`: Bilder, Fonts, Icons usw.
        

---

### Unterschied zwischen `App.js` und `index.js`
###### **1. `index.js` → Einstiegspunkt der gesamten React-App**
- Hier startet deine Anwendung.
- Aufgabe: React in die HTML-Datei (`public/index.html`) „einzuhängen“.
- Typischer Code:
![[Pasted image 20250822114304.png]]
Erklärung:
- `ReactDOM.createRoot(...).render(<App />)` sagt:  
    👉 „Nimm die Komponente `<App />` und rendere sie in das `div` mit der ID `root` in `index.html`.“

###### **2. `App.js` → Hauptkomponente deiner Anwendung**
- Enthält den **eigentlichen Inhalt der App**.
- Das ist sozusagen dein Startpunkt für deine UI.
- Typischer Code:
![[Pasted image 20250822114339.png]]
Erklärung:
- `App.js` ist eine **Komponente**, die alles enthält, was du darstellen willst.
- Sie wird von `index.js` importiert und gerendert.



💡 Merksatz:  
👉 **`index.js` = verbindet React mit HTML**  
👉 **`App.js` = beschreibt, wie die App aussieht**
## References
1. 
