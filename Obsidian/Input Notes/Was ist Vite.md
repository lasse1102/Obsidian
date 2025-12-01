
--- 
Erstellt: 2025-11-27    22:07 
Tags: 
Link Up: [[JavaScript]] 
Link Down:

--- 
# Was genau ist Vite
Vite ist ein Build-Tool für moderne Webanwendungen, welche sie schneller und effizienter macht - besonders im Vergleich zu traditionellen Bundlern wie Webpack (was früher genutzt wurde häufig).

Es löst primär 2 große Probleme:
- Langsame Builds
- Lange Startzeiten im Dev-Server

[[Was ist ein Build-Tool und was ist ein Bundler]]

---
### Wichtigsten Vorteile von Vite
1. Extrem schneller Dev-Server (<1 Sekunde)
	Mit WebPack dauert das länger, bis der Dev-Server Startet, weil das gesamte Projekt erst einmal gebundeld werden muss und das dauert mit WebPack deutlich länger.

	**Wie genau macht Vite das:**
	Vite bündelt beim Entwickeln nicht das gesamte Projekt im voraus. 
	- Der Browser lädt jede Datei direkt als Module (import ... from ...)
	- Vite liefert die Datein nur auf Anfrage aus
	- Keine vollständige Vorab-Kompilierung
2. Hot Module Replacement (HMR) 
	HMR aktualisiert Teile der Anwendung, ohne die Seite neu zu laden.
	Wie wird das gemacht:
	- trackt Abhängigkeiten pro Modul
	- nutzt native ESM, um nur wirklich geänderte Module neu zu senden
	- sendet die geänderte Datei über WebSockets an den Browser 
	Keine Neubündelung des gesamten Bundles

Weitere Vorteile sind Unter anderem:
- Fürs Pre-Bundling von Dependencies (node_modules) verwendet Vite esbuild, sonst nicht
- Schnelle Production-Build durch Rollup
- Modular, modern und weniger Overhead

---
# 🧠 Zusammenfassung in einfachen Worten

Vite ist sinnvoll, weil es:
- deinen Entwicklungsserver extrem schnell macht
- deine Codeänderungen fast sofort aktualisiert
- sehr schnelle Builds erstellt
- moderne Browsertechnologie nutzt (ESM)
- esbuild und Rollup kombiniert (schnell + optimiert)
- mit React hervorragend funktioniert (via SWC)

## References
1. [[Architektur von TypeScript]]
