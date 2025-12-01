
--- 
Erstellt: 2025-11-04    13:46 
Tags: 
Link Up: [[TypeScript]]
Link Down:

--- 
# Schritte zur Einrichtung des Backend's
![[Unbenannt.jpg]]

# Schritte zur Einrichtung des Frontends
1. Wir gehen ins root Verzeichnis und öffnen das Termin und geben ein
	- `npm create vite@latest`
	- Dies erstell die gesamte Anwendung mit React und Vite 
2. Um nun noch das Backend mit dem Frontend zu verknüpfen gehen wir in de vite.config.js, hier ändern wir folgendes. Wir setzten den Port des Frontends (bspw. 3000) und fügen einen proxy hinzu der uns erlaubt api calls an das backend weiterzuleiten
```js
server: {
	open: true,
	port: 3000,
	proxy: {
		"/api": "http://localhost:5001"  // Der Port des backends
	}

}
```

# Stack
**Backend & Frameworks**
- `express`: Dies ist das zentrale Web-Framework, das zur Erstellung des Servers und der APIs (Routen) verwendet wird. Das Projekt ist eine Node.js Anwendung
- `dotenv`: Wird genutzt, um Konfigurationsdaten (wie z.B. Datenbank-Zugangsdaten oder Port-Nummer) aus einer .env-Datei zu laden und als Umgebungsvariablen bereitzustellen

**Datenbank & ORM**
- `mongoose`: Dies ist der Object Data Modeling Layer, der es dir ermöglicht, mit einer MongoDB-Datenbank zu interagieren. Es stellt Schemas und Modelle bereit, um die Datenstruktur zu definieren und Abfragen durchzuführen

**Entwicklungstools & TypeScript**
Diese Pakete dienen dazu, das Projekt in TypeScript zu entwickeln, zu kompilieren und auszuführen:
- **`typescript`** (`^5.9.3`): Die Programmiersprache und der Compiler, die dein gesamtes Projekt definieren.
- **`ts-node`** (`^10.9.2`): Ein Runner, der es erlaubt, TypeScript-Dateien **direkt** in Node.js auszuführen, ohne sie vorher manuell kompilieren zu müssen.
- **`@types/express`** und **`@types/node`**: Bereitstellung der **Typdefinitionen** für Express und Node.js, was die Entwicklung in TypeScript erst ermöglicht.
- **`ts-node-dev`** (Im `dev`-Skript): Ein Tool, das das Kompilieren und Neustarten des Servers beim Speichern von Änderungen automatisiert (**Hot Reload**).
- **`eslint`** (Im `lint`-Skript): Ein Tool zum statischen Code-Analyse (**Linting**), um Code-Qualität und -Stil zu gewährleisten.
Zusammenfassend ist es ein TypeScript/Node.js-Backend-Projekt mit Express als Server-Framework und MongoDB als Datenbank.

Ausschnitt aus der package.json:
![[Pasted image 20251104135636.png]] 

---
### ⚙️ Projekt-Skripte erklärt
Diese Befehle automatisieren wichtige Schritte in deinem Entwicklungs- und Deployment-Prozess:
- **`npm run build`**
    - **Bedeutung:** **Kompilieren** des TypeScript-Codes.
    - **Was es macht:** Führt den TypeScript-Compiler (`tsc`) aus. Dieser liest deinen Quellcode aus dem `src/`-Ordner (Dateien mit der Endung `.ts`) und wandelt ihn in reinen JavaScript-Code um, der von Node.js direkt ausgeführt werden kann. Die resultierenden Dateien landen im `dist/`-Ordner.
        
- **`npm start`**
    - **Bedeutung:** **Starten** der kompilierten Anwendung.
    - **Was es macht:**
        1. Führt zuerst das Skript **`prestart`** aus (was wiederum **`npm run build`** aufruft). Dadurch wird sichergestellt, dass die Anwendung immer mit dem neuesten kompilierten Code gestartet wird.
        2. Führt dann den Befehl `node dist/index.js` aus. Dies startet deine eigentliche Anwendung (den Express-Server) im Produktionsmodus, indem der **fertige JavaScript-Code** im `dist/`-Ordner verwendet wird.
            
- **`npm run dev`**
    - **Bedeutung:** **Entwicklungsmodus** (Development).
    - **Was es macht:** Führt `ts-node-dev` aus. Dieses Tool ist ideal für die Entwicklung, da es:
        - Deine TypeScript-Dateien **direkt** ausführt (`--transpile-only`).
        - Deinen Code **überwacht** (`--respawn`). Sobald du eine Datei speicherst, wird der Server automatisch neu gestartet, damit du die Änderungen sofort testen kannst (**Hot Reloading**).
            
- **`npm run lint`**
    - **Bedeutung:** **Code-Analyse** (Linting).
    - **Was es macht:** Führt `eslint` aus. Es prüft deinen gesamten Quellcode (`src/**/*.ts`) auf Stil- und potenzielle Fehler, ohne den Code auszuführen. Dies hilft, die Code-Qualität und -Konsistenz im gesamten Projekt zu gewährleisten.

Zusammenfassend verwendet man für die tägliche Arbeit fast immer `npm run dev`, während `npm start` der Befehl für das finale Deployment ist.

--- 
### 📝 Erstellung der `tsconfig.json`
Diese Datei ist das Herzstück des Projektes. Sie teilt dem TypeScript-Compiler (tsc) mit, wie er deine `.ts`-Datein kompilieren soll.

Lege im **Wurzelverzeichnis** deines Projekts (dort, wo auch die `package.json` liegt) eine neue Datei namens `tsconfig.json` an und füge den folgenden Inhalt ein:
![[Pasted image 20251104135950.png]]
### 🔍 Erklärung der wichtigsten Optionen
Hier ist eine kurze Erklärung, was die Schlüsseloptionen in dieser Konfiguration bewirken.

|Option|Wert|Funktion|
|---|---|---|
|**`target`**|`"es2020"`|Definiert die **Ziel-JavaScript-Version** für den kompilierten Code. `es2020` ist eine moderne, stabile Wahl.|
|**`module`**|`"commonjs"`|Legt fest, welches **Modulsystem** im kompilierten JavaScript verwendet werden soll. `commonjs` ist der Standard für Node.js-Projekte.|
|**`rootDir`**|`"./src"`|Der **Quellordner**, in dem sich deine TypeScript-Dateien (`.ts`) befinden.|
|**`outDir`**|`"./dist"`|Der **Zielordner**, in den der kompilierte JavaScript-Code abgelegt wird.|
|**`esModuleInterop`**|`true`|Ermöglicht eine bessere **Interoperabilität** zwischen CommonJS-Modulen (Node.js) und ES-Modulen. Dies ist oft notwendig, um Pakete wie **Express** und **Mongoose** korrekt zu importieren.|
|**`strict`**|`true`|Aktiviert eine Reihe von strengen **Typ-Überprüfungen**, was die Code-Qualität deutlich verbessert. **Empfohlen** für moderne Projekte.|
|**`include`**|`["src/**/*"]`|Weist den Compiler an, alle Dateien im `src`-Ordner und dessen Unterordnern zu berücksichtigen.|

---


















## References
1. 
