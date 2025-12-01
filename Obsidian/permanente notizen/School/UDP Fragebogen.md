
--- 
Erstellt: 2024-06-05    13:33 
Tags: #School/LF02 
Link Up: [[School]]
Link Down:

--- 
# 1
User Datagram Protocol
# 2
UPD arbeitet auf der Schicht 4, der Transportschicht, des OSI-Schichtmodells
# 3 
Der Header des UDP besteht aus vier Feldern, und ist insgesamt 8Byte groß

1. **Source port**: Dieses Feld gibt den Port des SourcePort an.
2. **Destination port**: Dieses Feld gibt den Destination port an, also da wo hingesendet wird.
3. **Länge**: Dieses Feld gibt die Länge des gesamten UDP-Datagramms an, einschließlich Header und Daten.
4. **Prüfsumme**: Dieses Feld wird verwendet, um die Integrität des Headers und der Daten zu überprüfen.

# 4 
Jeweils all 2 Byte bzw. 16Bit groß

1. **Quellport**: Gibt den Quellport an
2. **Zielport**: Gibt den Zielport an
3. **Länge**: Dieses Feld gibt die Länge des gesamten UDP-Datagramms an, einschließlich Header und Daten.
4. **Prüfsumme**: Dieses Feld wird verwendet, um die Integrität des Headers und der Daten zu überprüfen.
# 5 
- DNS Anfragen
- VPN Verbindungen
- Audio und Video Streaming

# 6
- Die Anzahl der möglichen Ports ist 65.535
- Dies liegt daran, dass die Portnummer eine 16-Bit-Zahl ist. Da ein Bit zwei mögliche Werte hat (0 oder 1), gibt es 2^16 oder 65.536 mögliche Kombinationen. 

# 7
Vorteile:
- Schnelle Übertragung: 
	UPD bietet eine schnelle, aber möglicherweise weniger zuverlässige Übertragungsmethode im Vergleich zu TCP
- Da UPD ein einfacheres Protokoll ist als TCP, erzeugt es weniger Overhead im Netzwerkverkehr

Nachteile:
- Keine Fehlerkorrektur: 
	UPD bietet keine Mechanismen zur Fehlerprüfung oder Korrektur
- Unzuverlässige Zustellung: 
	UPD kann nicht sicherstellen, dass alle Datenpakete den Empfänger erreichen oder in der richtigen Reihenfolge ankommen

## References
1. 

## Quellen
1. 