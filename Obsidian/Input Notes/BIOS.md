
--- 
Erstellt: 2025-02-17    09:24 
Tags: #IT/Hardware 
Link Up: [[Komponenten]]
Link Down:

--- 
## Kommunikation im Computer: Treiber, BIOS und POST
Nachdem wir uns die wichtigsten Komponenten eines Computers angesehen haben, geht es nun darum, wie diese miteinander kommunizieren. Programme werden von der Festplatte zur [[CPU]] ausgeführt, aber wie gelangen Informationen von Geräten wie Maus und Tastatur zur CPU?

###### **Treiber:**
Einfache Geräte wie Tastaturen enthalten keine Anweisungen, die die CPU direkt verstehen kann. Daher verwenden Geräte **Treiber**. Treiber sind Programme, die der CPU erklären, wie sie mit externen Geräten (Tastatur, Webcam, Drucker usw.) kommunizieren soll.

###### **BIOS (Basic Input/Output System) / UEFI (Unified Extensible Firmware Interface):**
Die CPU muss wissen, dass ein Gerät überhaupt existiert, mit dem sie kommunizieren kann. Hier kommt das **BIOS** (oder sein moderner Nachfolger **UEFI**) ins Spiel. Das BIOS ist eine Software, die die Hardware initialisiert und das [[Betriebssystem]] startet. Es ist auf einem speziellen Speicherchip auf dem [[Motherboard]] gespeichert, dem **ROM-Chip (Read-Only Memory)**. Im Gegensatz zum [[RAM]] ist ROM nichtflüchtig, d.h. die Daten bleiben auch nach dem Ausschalten des Computers erhalten.

UEFI ist der modernere Nachfolger des BIOS und bietet bessere Kompatibilität und Unterstützung für neue Hardware. Die meisten aktuellen Systeme verwenden UEFI.

###### **POST (Power-On Self-Test):**

Beim Einschalten des Computers führt dieser einen Selbsttest durch, den **POST**. Der POST überprüft, ob alle Hardwarekomponenten korrekt funktionieren. Da zu diesem Zeitpunkt noch keine Treiber geladen sind, werden Fehler durch eine Reihe von **Pieptönen** signalisiert (ähnlich Morsecode). Jeder Piepton-Code bedeutet etwas anderes. Die Bedeutung der Codes kann im Handbuch des Motherboards nachgelesen werden. Nicht alle Computer haben eingebaute Lautsprecher, daher kann es vorkommen, dass beim Starten kein Piepton zu hören ist.

###### **CMOS und BIOS-Einstellungen:**
Auf dem Motherboard befindet sich ein Chip namens **CMOS**, der grundlegende Einstellungen für den Computer speichert, wie Datum, Uhrzeit und Startreihenfolge. Diese Einstellungen können im **BIOS-Einstellungsmenü** geändert werden. Dieses Menü wird normalerweise durch Drücken einer bestimmten Taste (z.B. Entf, F2, F10) während des Startvorgangs aufgerufen.
## References
1. 
