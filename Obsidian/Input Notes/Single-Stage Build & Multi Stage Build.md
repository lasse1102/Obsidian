
--- 
Erstellt: 2025-06-17    14:02 
Tags: 
Link Up: [[Docker]]
Link Down:

--- 
# Single-Stage und Multi-Stage build
Ein Single-Stage Dockerfile bedeutet, dass du dein Image in einem einzigen Schritt erstellst, ohne zwischen verschiedenen `FROM`-Anweisungen zu wechseln. Eine Single-Stage Dockerfile wird hauptsächlich für Entwicklungs-Server verwendet.

**Beispiel für eine Single-Stage Entwicklungs-Dockerfile (wie deine aktuelle Frontend-Dockerfile):**
![[Pasted image 20250617140602.png]]
Eigenschaften des Single-Stage Builds:

- **Einfachheit**: Direkter und unkomplizierter Aufbau.
- **Image-Größe:** Das resultierende Image enthält alle Build-Werkzeuge, Quellcode-Dateien (wenn nicht gemountet), und Abhängigkeiten, die für den Build-Prozess und die Ausführung notwendig waren. Es kann relativ groß sein, da es oft auch Dinge enthält, die zur Laufzeit nicht mehr benötigt werden (z.B. der gesamte node_modules Baum, auch wenn nur ein kleiner Teil davon wirklich zum Ausführen der Anwendung gebraucht wird).
- **Entwicklung**: Super geeignet für die Entwicklung, besonders in Kombination mit Volume-Mounts, da der Entwicklungsserver (z.B. Vite) im Container laufen kann und direkt auf lokale Dateisystemänderungen reagiert (HMR/Live-Reload). Du brauchst die Build-Tools im Container, um den Dev-Server zu starten und Live-Kompilierung durchzuführen.

---

#### **Multi-Stage Dockerfile (fast immer für Produktion)**
Eine Multi-Stage Dockerfile verwendet mehrere FROM-Anweisungen. Jede FROM-Anweisung startet eine neue Build-Phase. Das Geniale daran ist, dass du Artefakte (Dateien) von einer früheren Phase in eine spätere Phase kopieren kannst, ohne die gesamte "Geschichte" (und die damit verbundenen großen Dateien wie Build-Dependencies) der früheren Phase in das finale Image zu übernehmen.

**Beispiel für eine Multi-Stage PRODUKTIONS-Dockerfile (wie deine frühere Frontend-Dockerfile):**
![[Pasted image 20250617141233.png]]
**Eigenschaften des Multi-Stage Builds:**

- **Optimierung für Produktion:** Dies ist die primäre Stärke. Es ermöglicht die Erstellung von sehr schlanken und effizienten Produktions-Images.
- **Kleinere Image-Größe:** Die Tools und Abhängigkeiten, die nur für den Build-Prozess benötigt wurden (z.B. der gesamte `node_modules`-Ordner aus der `build_stage`), werden im finalen Image nicht enthalten sein. Nur die wirklich notwendigen Laufzeit-Artefakte (die gebauten HTML/CSS/JS-Dateien und der Nginx-Server) sind enthalten.
- **Bessere Sicherheit:** Weniger unnötige Dateien und Software im finalen Image bedeuten eine kleinere Angriffsfläche.
- **Trennung von Build- und Laufzeitumgebung:** Die Build-Umgebung kann groß und reich an Tools sein, während die Laufzeitumgebung (das finale Image) minimal und spezialisiert ist.
- **Entwicklung:** **Nicht** direkt für die Entwicklung mit Live-Reload geeignet. Warum? Weil der finale Schritt nur statische Dateien bereitstellt, die zur Build-Zeit erstellt wurden. Er beinhaltet keinen aktiven Entwicklungsserver, der auf Dateiänderungen lauschen könnte. Jede Code-Änderung würde einen kompletten Neubau und Neustart des Containers erfordern.


Fazit:
Wenn man auf einen Entwicklungsserver(dev) arbeiten will, dann nutzt man ein Single-Stage Build. Wenn man auf einer Produktionsumgebung arbeiten will, dann nutzt man ein Multi-Stage Build
## References
1. 
