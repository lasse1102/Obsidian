
--- 
Erstellt: 2025-02-14    07:15 
Tags: #IT/Hardware 
Link Up: [[Komponenten]]
Link Down: [[RAM]], [[CPU]]

--- 
## Motherboard: Das Fundament des Computers
Das Motherboard ist die Grundlage, die alle Komponenten eines Computers zusammenhält. Es ermöglicht die Erweiterung der Funktionalität durch Steckkarten, leitet [[Strom]] vom Netzteil und ermöglicht die Kommunikation zwischen den verschiedenen Teilen des Computers.
![[Pasted image 20250214072120.png]]

###### **Schlüsselmerkmale eines Motherboards:**
- **Chipsatz:** Bestimmt, wie die CPU mit der den anderen Hardwarekomponenten kommuniziert. Er besteht traditionell aus zwei Chips:
    - **Northbridge:** Verbindet Komponenten wie [[RAM]] und Grafikkarten. In modernen CPUs ist die Northbridge oft direkt in die [[CPU]] integriert.
    - **Southbridge:** Verwaltet Ein-/Ausgabe-Controller (I/O) wie Festplatten und USB-Geräte.
- **Erweiterungssteckplätze:** Ermöglichen das Hinzufügen von Komponenten zur Erweiterung der Funktionalität (z.B. Grafikkarten). Der aktuelle Standard ist **PCIe (Peripheral Component Interconnect Express)**.
- **Formfaktor:** Bestimmt die Größe des Motherboards und die Anzahl der Komponenten, die darauf Platz finden. Gängige Formfaktoren sind:
    - **ATX (Advanced Technology Extended):** Der häufigste Formfaktor, auch in verschiedenen Größen erhältlich (z.B. Full-Size ATX).
    - **ITX (Information Technology Extended):** Kleinere Formfaktoren, z.B. Mini-ITX, Nano-ITX und Pico-ITX. Oft in kleineren Computern wie dem Intel NUC zu finden.
![[Pasted image 20250214072040.png]]

###### **Wichtige Überlegungen beim Kauf/Bau eines Computers:**
- **Chipsatz:** Der Chipsatz beeinflusst, welche CPUs und RAM-Typen kompatibel sind.
- **Erweiterungssteckplätze:** Welche und wie viele Steckplätze benötige ich für meine Anforderungen (z.B. Grafikkarte, zusätzliche SSDs)?
- **Formfaktor:** Welche Größe passt in mein Gehäuse und welche Funktionalität benötige ich? Muss es ein kleines, energieeffizientes System sein oder ein leistungsstarker Rechner mit vielen Erweiterungsmöglichkeiten?

###### **Bedeutung für die Fehlerbehebung:**
Das Verständnis von Motherboards ist entscheidend für die Fehlerbehebung. Zum Beispiel muss man wissen, welcher RAM-Typ oder CPU-Sockel zum Motherboard passt, um Ersatzteile zu bestellen oder Kompatibilitätsprobleme zu lösen. Wenn ein Benutzer beispielsweise Probleme mit der Grafik hat, sollte man vor dem Kauf einer neuen Grafikkarte sicherstellen, dass diese mit dem Motherboard kompatibel ist (PCIe-Slot, Stromversorgung). Es wäre ärgerlich, zum Benutzer zu fahren und festzustellen, dass die neue Grafikkarte nicht passt.

## References
1. https://www.intel.de/content/www/de/de/gaming/resources/how-to-choose-a-motherboard.html
