
--- 
Erstellt: 2025-03-04    13:38 
Tags: #IT/Betriebssystem 
Link Up: [[IT]]
Link Down:

---
## Dateiverwaltung und Dateisysteme
### Grundlagen der Dateiverwaltung
- **Herausforderung**: Die Verwaltung einer großen Anzahl von Dateien erfordert ein effizientes System.
- **Kernel-Rolle**: Der Kernel ist für die Dateispeicherung und die Verwaltung von Dateisystemen verantwortlich.
- **Hauptkomponenten**:
    - Dateisystem
    - Datei-Daten
    - Metadaten

### Dateisysteme
- **Initialisierung**: Neue Festplatten müssen formatiert werden, damit das [[Betriebssystem]] Daten lesen und schreiben kann.
- **Vielfalt**: Es gibt verschiedene Dateisysteme für unterschiedliche Zwecke (z.B. größe Datenmengen, Geschwindigkeit).
- **Betriebssystemspezifische Dateisysteme**:
    - **Windows**: NTFS (New Technology File System) ist das Standard-Dateisystem.
        - Funktionen: Verschlüsselung, schnelle Zugriffszeiten, Sicherheit.
        - ReFS (Resilient File System) ist in der Entwicklung.
    - **[[Linux]]**: Verschiedene Distributionen verwenden unterschiedliche Dateisysteme, z.B. EXT4.
        - EXT4 ist kompatibel mit älteren EXT Dateisystemen.
- **Kompatibilität**: Unterschiedliche Dateisysteme sind oft nicht kompatibel.
- **Empfehlung**: Verwenden Sie das vom [[Betriebssystem]] empfohlene Dateisystem.

### Datei-Daten
- **[[Datenspeicherung]]**: Daten werden in Form von Datenblöcken auf der Festplatte gespeichert.
- **Blockspeicherung**: Daten werden in mehrere Teile zerlegt und an verschiedenen Stellen auf der Festplatte gespeichert.
    - Vorteile: Schnellere Datenverarbeitung, bessere Speichernutzung.

### Metadaten
- **Informationen**: Metadaten enthalten Informationen über eine Datei (z.B. Ersteller, Änderungsdatum, Zugriffsrechte).
- **Dateityp**: Metadaten geben den Dateityp an.
- **Dateierweiterung**: Ein Teil des Dateinamens, der den Dateityp angibt (z.B. .jpg, .txt).
- **Beispiel**: cool_image.jpg (JPG ist die Dateierweiterung für Bilddateien).

## References
1. 
