
--- 
Erstellt: 2025-10-29    13:23 
Tags: 
Link Up: [[IT-Sicherheit]]
Link Down:

--- 
**Inhalt der Notiz:**
- Diese Punkte sind wichtig, wenn Sie eine Lösung **planen** oder **bewerten** müssen.
### 5. 🔍 Zugangskontrollen & Risikobewertung
- **Unterscheidung:** **Zutritt vs. Zugang vs. Zugriff** (wird oft abgefragt).
- **Risikoanalyse:** Grober Ablauf: Bedrohung erkennen → **Schaden einschätzen** (wirtschaftlich/Imageschaden).
- **Prüfung:** Wissen, was ein **Penetrationstest** ist und was man damit erreicht.


## 🔍 Zugangskontrollen & Risikobewertung

### 🚪 Unterscheidung: Zutritt vs. Zugang vs. Zugriff
Diese drei Begriffe werden oft verwechselt, sind aber für die Planung von Sicherheitskonzepten (z. B. im Rahmen der ISO 27001) fundamental.

| Begriff     | Schutzziel                              | Beschreibung                                                                                                                    | Beispiel                                                    |
| ----------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| **Zutritt** | Physische Verfügbarkeit/Vertraulichkeit | Kontrolle des **Betretens** von Räumen, Gebäuden oder gesicherten Bereichen (z. B. Serverraum).                                 | Türschlösser, Schlüsselkarten, Wachpersonal.                |
| **Zugang**  | Logische Verfügbarkeit/Vertraulichkeit  | Kontrolle des **Eintritts** in ein IT-System, ein Netzwerk oder eine Anwendung.                                                 | Login (Benutzername und Passwort), VPN-Verbindung.          |
| **Zugriff** | Vertraulichkeit/Integrität              | Kontrolle der **Berechtigung**, Ressourcen (Dateien, Daten, Funktionen) innerhalb eines bereits zugänglichen Systems zu nutzen. | Lese-, Schreib- oder Löschrechte auf eine Datenbanktabelle. |
|             |                                         |                                                                                                                                 |                                                             |

### ⚠️ Risikoanalyse: Grober Ablauf
Bei der Planung von Schutzmaßnahmen ist die Einschätzung des Risikos der entscheidende Schritt zur **Priorisierung der Investitionen** (wirtschaftlicher Aspekt).
1. **Bedrohungsszenario erkennen:** Identifizieren Sie die potenziellen Angriffsvektoren oder Schwachstellen, die die drei Schutzziele gefährden könnten (z. B. DDoS-Angriff, Datenverlust, Phishing).
2. **Schadenspotenzial einschätzen:** Bewerten Sie die potenziellen Auswirkungen, wenn die Bedrohung eintritt.
    - **Wirtschaftlicher Schaden:** Wiederherstellungskosten, Produktionsausfall, Konventionalstrafen.
    - **Imageschaden:** Reputationsverlust bei Kunden, Geschäftspartnern und in der Öffentlichkeit.
3. **Risiko priorisieren:** Das Risiko ergibt sich aus der **Eintrittswahrscheinlichkeit** multipliziert mit dem **Schadenspotenzial**. Maßnahmen sollten zuerst dort ergriffen werden, wo das Risiko am größten ist.
    

### 🧪 Prüfung: Penetrationstest (Pentest)
Der Penetrationstest ist eine essenzielle **Prüfungsmethode** zur Bewertung der realen Sicherheitslage.
- **Was ist ein Penetrationstest?** Ein autorisierter und kontrollierter **Angriffssimulationstest** auf ein IT-System, eine Anwendung oder ein Netzwerk durch ethische Hacker (Pentester). Ziel ist es, Schwachstellen zu finden, zu dokumentieren und deren Ausnutzbarkeit nachzuweisen.
- **Was erreicht man damit?**
    - **Realistische Bewertung:** Er liefert eine tatsächliche Momentaufnahme der Sicherheitslage aus der Perspektive eines Angreifers.
    - **Schwachstellen identifizieren:** Er deckt Konfigurationsfehler, fehlende Patches und logische Fehler in Anwendungen auf, die automatisierte Scanner oft übersehen.
    - **Risikobestätigung:** Er untermauert die Ergebnisse der theoretischen **Risikoanalyse** durch praktische Beweise (Proof-of-Concept).
    - **Compliance-Anforderung:** Er dient oft als Nachweis für Compliance-Standards (z. B. für PCI DSS oder im Rahmen von Zertifizierungen).

## References
1. 
