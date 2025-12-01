
--- 
Erstellt: 2025-11-27    22:16 
Tags: 
Link Up: [[Was ist Vite]] 
Link Down:

--- 
# Was genau ist ein Build-Tool
Ein Build-Tool ist ein Werkzeug welches den Quellcode (JavaScript, TypeScript, TSX ...) vorbereitet, optimiert und in ein Format bringt, welches der Browser effektiv verarbeiten kann.
**Aufgaben eines Build-Tools**
1. Transpilieren
	- JSX -> normales JavaScript
	- TypeScript -> JavaScript
2. Optimieren
	- JS minimieren
	- CSS minimieren
	- Kommentare entfernen 
	- Variablen kürzen
3. Dev-Server bereitstellen
	Bei der Entwicklung startet das Build-Tool einen lokalen Server mit:
	- Live Reload
	- Hot Module Replacement (HMR)

---
# Was ist ein Bundler
Ein Bundler ist ein Teil eines Build-Tools, der viele einzelne Datein, **in wenig optimierte Datein zusammenfasst**.

Beispiel:
- 200 JavaScript-Datein
	-> am Ende 2-3 fertige JavaScript-Bundles

Warum macht man das?
- der Browser konnte früher viele seperate Datein nicht effizient laden.
- weniger Datein -> weniger Request -> schneller

**Wie funktioniert es:**
![[Pasted image 20251127222448.png]]
Ein **Bundler**:
1. liest **App.jsx**
2. folgt jedem `import`
3. baut einen **Abhängigkeitsgraphen**
4. und schreibt daraus **eine große Datei**:
`bundle.js`

**Beispiel für Bundler:**
- esbuild
- Rollup
- Webpack
- Parcel
- Vite -> ist ein Ganzes Build Tool, welches Rollup in Production-Build verwendet und esbuild beim Pre-building von Dependencies (node_modules)




## References
1. 
