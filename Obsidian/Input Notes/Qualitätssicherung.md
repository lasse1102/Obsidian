
--- 
Erstellt: 2025-10-13    09:33 
Tags: 
Link Up: [[AP2]]
Link Down:

--- 
# Qualitätssicherung
Qualitätssicherung umfasst alle Maßnahmen, die sicherstellen sollen, dass Softwarequalität erreicht wird.

Da verschiedene Stakeholder unterschiedliche Anforderung an unser Projekt haben, ist die Qualität recht subjektiv. Alle Stakeholder zu 100% zufrieden zu stellen. wird in einem echten Projekt wohl nicht möglich sein. Jeder Stakeholder würde die Qualität vermutlich anders bewerten, da jeder ein anderes Interesse hat und, das Projekt demnach verschiedene Qualität für verschiedene Bereiche hat

# Ziele der Qualitätssicherung
- Steigerung der Kundenzufriedenheit durch die Erfüllung oder Übertreffen der Kundenanforderungen und Erwartungen
- Vermeidung von Qualitätsproblemen, durch Überprüfung und Verbesserung der Prozesse
- Erhöhung von Effizient, durch Optimieren von Prozessen und und Ressourcennutzung
- Verbesserung der Wettbewerbsfähigkeit des Unternehmens
- Einhaltung gesetzlicher Anforderungen


# Allgemeine Maßnahmen von Qualitätssicherung
- Qualitätsplanung
	- Entwickeln eines Qualitätsplan. Dieser legt die Qualitätsziele fest
- Qualitätskontrolle
	Beinhaltet die Überwachung und Messung der Qualität von Produkten, Dienstleistungen oder Prozessen
- Qualitätsverbesserung
	Kontinuierliche Verbesserung der Qualität, dies kann durch die Identifizierung und Beseitigung von Qualitätsproblemen oder Schwachstellen sein.

# Maßnahmen zur Qualitätssicherung bezogen auf Softwareentwicklung
- Audits
- Code Reviews
	Dieser Punkt ist meist für die Wartbarkeit zuständig.(Oft geschieht das über Pull-Request, wobei die eine andere Person den Code bestätigen muss bevor er in den Haupt Branch gelangt, dies ist auch schon eine Code-Review)
- Testmethoden
	Hiermit können beispielsweise die Funktionalen Anforderungen getestet werden, ob das Programm beispielsweise wirklich funktioniert
- Entwicklungsprozess
	- Hierbei geht es darum, durch eine strukturierte Vorgehensweise (Scrum, Wasserfallmodell, Kanban) Qualität systematisch zu verankern.
	- **Standards und Transparenz:** Der Prozess definiert, wie gearbeitet wird, welche Qualitätsziele gelten und wie der Zustand der Software transparent gemacht wird
- Dokumentation
	- **Nachvollziehbarkeit:** Sie sorgt dafür, dass Entscheidungen, Anforderungen, Design und Testergebnisse **rückverfolgbar** sind
	- Gut geführte Dokumentationen erleichtern neuen Entwicklern das Einarbeiten und helfen, wenn der Code später geändert oder gewartet werden muss
- Statische Codeanalyse
	- Die statische Codeanalyse ist eine **automatisierte Untersuchung** des Quellcodes **ohne ihn auszuführen**.
	- **Sicherheits- und Qualitätsprüfung:** Tools suchen nach potenziellen **Bugs, Sicherheitslücken, Verstößen gegen Codierungsstandards** (Code-Style) und komplexen Stellen
- Pair Programming
	- **Kontinuierlicher Echtzeit-Review:** Es fungiert als sofortiger Code Review in Echtzeit, wodurch Fehler oder Designschwächen direkt bei der Entstehung erkannt und vermieden werden
	- Hierdurch wird direkt bei der Entwicklung die Qualität erhöht
- Bugtracking
	- **Strukturierte Fehlerbehebung:** Durch ein **Bug-Tracking-System** wird sichergestellt, dass kein gemeldeter Fehler vergessen wird, die Behebung **priorisiert** erfolgt und der Status jederzeit **transparent** ist.
	- Gerade wenn das Projekt fertig Entwickelt wurde und nun im Einsatz kommt, ist Bugtracking dafür da um während der Laufzeit Schwachstellen zu identifizieren
- Continuous Integration/Delivery/Deployment
	- **Continuous Integration (CI):** Entwickler integrieren Codeänderungen **regelmäßig** in ein gemeinsames Repository. Jede Integration wird **automatisiert gebaut und getestet**, um Integrationsprobleme frühzeitig zu erkennen.
	- **Continuous Delivery (CD):** Der Code wird nach erfolgreichem Bau und Test **automatisch für die Bereitstellung vorbereitet** und kann jederzeit per Knopfdruck in die Produktion gebracht werden.
	- **Continuous Deployment (CDP):** Geht noch einen Schritt weiter und **rollt den Code automatisch** in die Produktion aus, wenn alle automatisierten Tests erfolgreich waren.
	- **Qualitätseffekt:** Durch die Automatisierung und die **häufigen, schnellen Feedbackschleifen** werden Fehler schneller gefunden, die Qualität bleibt durchgehend hoch und die Auslieferung wird sicherer.

---

# Softwarequalität
Softwarequalität beschreibt wie  gut eine Software ist.
#### Definition
Anforderungen kann man in funktionale und nicht funktionale Anforderungen einsortieren
- **Funktionale Anforderungen:** Bedeutet konkret das das Programm funktioniert und das tut was es auch tun soll
- **Nicht funktionale Anforderungen:** Bspw. sollte die Performance gut sein und das Programm sollte nicht zu langsam laufen. 


#### Softwarequalität nach Norm 25010
Wir definieren Softwarequalität nach der internationalen Norm **ISO/IEC 25010:2023**. Dieser Standard betrachtet Qualität ganzheitlich und geht weit über die rein funktionale Korrektheit hinaus. Während die **funktionale Eignung,** also die Frage, ob die Software das tut, was sie soll, die Grundlage bildet, sind es oft die nicht-funktionalen Merkmale, die über den langfristigen Erfolg entscheiden.

Die Norm unterteilt Qualität in folgende zentrale Merkmale:
- **Funktionale Eignung:** Die Software stellt die geforderten Funktionen korrekt, vollständig und angemessen bereit.
- **Leistungseffizienz:** Die Anwendung reagiert schnell und nutzt Systemressourcen (wie CPU oder Speicher) effizient.
- **Kompatibilität:** Die Software arbeitet nahtlos mit anderen Systemen und Komponenten zusammen.
- **Benutzbarkeit:** Die Bedienung ist intuitiv, verständlich und für die Zielgruppe angenehm (hohe User Experience).
- **Zuverlässigkeit:** Die Software läuft stabil, ist fehlertolerant und kann sich nach einem Ausfall schnell wiederherstellen.
- **Sicherheit:** Die Anwendung schützt Daten und Systeme vor unberechtigtem Zugriff und Angriffen.
- **Wartbarkeit:** Der Code ist modular, verständlich und leicht anpassbar, was zukünftige Änderungen vereinfacht.
- **Übertragbarkeit:** Die Software kann einfach in einer anderen Umgebung (z. B. anderes Betriebssystem) installiert oder betrieben werden.

![[Pasted image 20251028175803.png]]
**Benutzbarkeit:** (**Auch wichtig für das Abschlussprojekt, könnte im Fachgespräch dran kommen**)

**Merkmale der Benutzbarkeit:**

| Dein Begriff            | Bezug zu ISO 9241 / Standard                     | Erklärung und Fazit                                                                                                                                                                                 |
| ----------------------- | ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Attraktivität**    | **Attraktivität**                                | Attraktivität ist ein direktes Qualitätsmerkmal der Benutzungsschnittstelle. Eine ansprechende, **moderne Ästhetik** beeinflusst die Akzeptanz und die emotionale Bindung des Benutzers positiv.    |
| **2. Bedienbarkeit**    | **Effizienz** und **Effektivität**               | Dies zielt darauf ab, dass Benutzer ihre Ziele **schnell** (Effizienz) und **fehlerfrei** (Effektivität) erreichen können. Einfache, **nicht-komplexe** Abläufe sind hier der Schlüssel.            |
| **3. Erlernbarkeit**    | **Erlernbarkeit**                                | Es beschreibt, wie leicht ein neuer Benutzer die notwendigen Interaktionen lernt, um die Anwendung zu nutzen. Hilfen wie **Dokumentation, Onboarding** und **intuitives Design** unterstützen dies. |
| **4. Verständlichkeit** | **Gebrauchstauglichkeit** / **Verständlichkeit** | Dieser Punkt betont die **Klarheit** der Informationen. Die Vermeidung von unnötigen **Fachbegriffen und Abkürzungen** ist entscheidend, um die Anwendung für die Zielgruppe zugänglich zu machen.  |






## References
1. [[13b - Qualitätssicherung]]
2. [[13 - Softwarequalität und -sicherheit]] 