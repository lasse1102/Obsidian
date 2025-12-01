
--- 
Erstellt: 2025-11-24    07:09 
Tags: 
Link Up: [[AP2]] 
Link Down:

--- 
# Continuous Integration (CI)
Continuous Integration ist die Praxis, bei der Entwickler ihren Code mehr mal täglich oder bei jeder Änderung auf Git zusammenführen (mergen).
- **Ziel:** Frühzeitiges Erkennen und Beheben von Integrationsproblemen
- **Prozess:** Nach jeder Code-Zusammenführung wird automatisch ein Build Prozess gestartet und es werden automatisierte Tests (z.B. Unit Test) durchgeführt.
- **Vorteil** Die Codebasis ist stets in einem funktionsfähigen Zustand

# Continuous Delivery (CD) vs. Continuous Deployment (CD)
Beide beziehen sich auf die Automatisierung der Freigabe von Änderungen nach der CI-Phase.
### 📦 Continuous Delivery (Kontinuierliche Bereitstellung)
- **Was es ist:** Die erstellte und getestete Software wird automatisch in ein **Repository** (z.B. einen Artefaktspeicher) oder in eine **Staging-Umgebung** überführt. Die Software ist jederzeit **bereit** für die Bereitstellung (Deployment).
- **Wann es live geht:** Die **eigentliche Bereitstellung** in die Produktionsumgebung (Go-Live) erfordert einen **manuellen Schritt** oder eine explizite Genehmigung (z.B. durch einen Manager oder das Operations-Team).

### ⚙️ Continuous Deployment (Kontinuierliche Auslieferung)
- **Was es ist:** Die erstellte, getestete und freigegebene Software wird **vollautomatisch** und **ohne menschliches Eingreifen** in die Produktionsumgebung bereitgestellt, vorausgesetzt, alle automatisierten Tests und Qualitätsprüfungen sind erfolgreich.
- **Wann es live geht:** Jede Änderung, die den **CI/CD-Pipeline-Test** besteht, geht automatisch und sofort **live** für die Endbenutzer.
## References
1. 
