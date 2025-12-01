
--- 
Erstellt: 2025-11-21    12:24 
Tags: 
Link Up: 
Link Down:

--- 
Wie funktioniert TypeScript im Hintergrund? 
Diese Fragen werden im folgenden erläutern.

### Nutzung von TypeScript mit Vite
Vite ist ein modernes Build-Tool für JavaScript/TypeScript Anwendungen, das speziell für schnelle Entwicklungs- und Build-Prozesse entwickelt wurde. Es bietet eine direkte Unterstützung für TypeScript ohne zusätzliche Bibliotheken oder Tools.

### Wie funktioniert TypeScript mit Vite
1. **Automatische Umwandlung von TypeScript in JavaScript**
	- Wenn man den Befehl `npm run dev` ausführt, startet vite den Entwicklungsserver und sorgt dafür das die TypeScript Datein im Hintergrund automatisch in JavaScript Datein umgewandelt werden
	- Vite nutzt intern **esbuild**, um TypeScript-Datein (.ts und .tsx) extrem schnell zu transpilen.
2. **Wie funktioniert die Umwandlung?**
- **`esbuild`-Transpilation:** `esbuild` führt die Umwandlung von TypeScript zu JavaScript durch, indem es die TypeScript-Syntax entfernt (typische statische Typen und Deklarationen) und den Code in ein modernes JavaScript-Format (meist ESNext) umwandelt.
- Dies geschieht **in Echtzeit**, wenn du die Anwendung im Entwicklungsmodus mit `vite` startest. Du musst also nicht manuell den TypeScript-Compiler (`tsc`) ausführen, da dies automatisch während des Entwicklungsprozesses erledigt wird (siehe. `npm run dev`)


Zusammengefasst:
Der Browser erkennt TypeScript nicht deshalb wird es vor dem kompilieren in JavaScript umgewandelt. TypeScript hilft sozusagen nur uns Entwickler bei der Entwicklung.


---
## tsconfig.json
Beim erstellen einer TypeScript Anwendung wird eine `tsconfig.json` erstellt. Hier geben wir zum Beispiel Daten für den TypeScript Compiler mit (Welche JS Version, wo kompilierte Daten speichern usw.)

Nutzung von **absolut Imports**:




## References
1. 
