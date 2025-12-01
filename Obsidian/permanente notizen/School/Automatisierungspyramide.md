
--- 
Erstellt: 2024-11-21    09:52 
Tags: #School/LF07/IoT 
Link Up: [[School]]
Link Down:

--- 
# Automatisierungspyramide
Die **Automatisierungspyramide** ist ein Modell, das die Struktur und die Hierarchie von Automatisierungssystemen in industriellen Prozessen beschreibt. Sie dient dazu, die verschiedenen Ebenen der Automatisierung und deren Interaktionen klar zu definieren und die Integration unterschiedlicher Technologien und Systeme zu erleichtern. Das Modell besteht typischerweise aus fünf Ebenen, die von der physischen Geräteebene bis zur Unternehmensleitebene reichen.


### 1.   **ERP (Enterprise Resource Planning) - Unternehmensebene
- **Funktion:** Diese Ebene ist für die strategische Planung und die betriebswirtschaftlichen Entscheidungen des Unternehmens verantwortlich.
- **Elemente:** ERP-Systeme (z. B. SAP, Oracle) integrieren Bereiche wie Einkauf, Vertrieb, Lager und Produktion.
- **Aufgabe:**
    - Ressourcenmanagement (Material, Personal, Finanzen).
    - Langfristige Planung von Produktion und Geschäftsprozessen.
    - Verbindung zwischen Unternehmenszielen und operativer Umsetzung.

---

### **2. MES (Manufacturing Execution System) Betriebsebene**
- **Funktion:** Diese Ebene dient der operativen Planung und Steuerung der Produktion. Sie bildet die Brücke zwischen der Geschäftsebene (ERP) und den produktionsnahen Systemen (SCADA).
- **Elemente:**
    - MES-Systeme koordinieren Produktionsaufträge, verwalten Ressourcen und überwachen den Produktionsfortschritt.
- **Aufgabe:**
    - Produktionsplanung in Echtzeit.
    - Auftrags- und Qualitätsmanagement.
    - Rückmeldungen von Produktionsprozessen an das ERP.

---

### **3. SCADA (Supervisory Control and Data Acquisition) (Prozess-) Leitebene
- **Funktion:** Überwachung, Visualisierung und Datenerfassung von Produktionsprozessen.
- **Elemente:**
    - SCADA-Systeme ermöglichen es Bedienern, Prozesse zu überwachen, Daten zu analysieren und bei Bedarf manuell einzugreifen.
    - HMI (Human-Machine Interface) ist die Benutzeroberfläche zwischen Mensch und Maschine.
- **Aufgabe:**
    - Prozessüberwachung und Datensammlung von der Steuerungsebene (z. B. PLC/SPS).
    - Darstellung von Produktionsdaten in Echtzeit.
    - Ermöglichung manueller Eingriffe bei Abweichungen.

---

### **4. PLC/SPS (Speicherprogrammierbare Steuerungen) Steuerungsebene**
- **Funktion:** Diese Ebene steuert die Maschinen und Prozesse in Echtzeit.
- **Elemente:**
    - SPS (Programmable Logic Controller) verarbeitet Eingaben von Sensoren und sendet entsprechende Steuerbefehle an Aktuatoren.
- **Aufgabe:**
    - Direkte Steuerung von Maschinen und Anlagen.
    - Echtzeit-Ausführung der Prozesslogik basierend auf programmierten Abläufen.

---

### **5. Eingabesignale (Sensoren) und Ausgabesignale (Aktuatoren) Feldebene
- **Funktion:** Verbindung zwischen der digitalen Steuerung und der physischen Welt.
- **Elemente:**
    - **Sensoren:** Erfassen physikalische Größen wie Temperatur, Druck, Füllstand und melden diese an die SPS.
    - **Aktuatoren:** Empfangen Steuerbefehle von der SPS und setzen diese in physische Aktionen um, z. B. Öffnen eines Ventils oder Drehen eines Motors.
- **Aufgabe:**
    - Datenbereitstellung für Steuerungssysteme (Sensoren).
    - Umsetzung der Steuerungsbefehle in physische Prozesse (Aktuatoren).

![[Automatisierungspyramide.png]]
## References
1. 
