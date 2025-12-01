
--- 
Erstellt: 2025-03-19    09:59 
Tags: #School/LF03 
Link Up: [[School]]
Link Down:

--- 
# Was ist eine Mac-Adresse
- Eine **MAC-Adresse** ist eine **physikalische Adresse**, die einer Netzwerkschnittstelle (z. B. einer Netzwerkkarte oder einem WLAN-Modul) zugewiesen wird.
- Sie besteht aus **48 Bit** (6 Byte) und wird meist in **hexadezimaler Schreibweise** dargestellt (z. B. `00:1A:2B:3C:4D:5E`).

### **2. Aufbau einer MAC-Adresse**
- **Ersten 24 Bit (3 Byte)** → OUI (**Organizationally Unique Identifier**) → Herstellerkennung (z. B. `00:1A:2B`)
- **Letzten 24 Bit (3 Byte)** → Gerätekennung (**Device Identifier**) → Einzigartige Seriennummer innerhalb des Herstellers

Beispiel:  
`00:1A:2B:3C:4D:5E`
- `00:1A:2B` = Hersteller (z. B. Intel, Realtek, Broadcom)
- `3C:4D:5E` = Einzigartige Kennung des Geräts

### **3. MAC-Adressen und Netzwerkkommunikation**
- Wird für die **Datenübertragung auf Schicht 2 (Sicherungsschicht) des OSI-Modells** verwendet.
- Ermöglicht die **Identifikation von Geräten** innerhalb eines lokalen Netzwerks (LAN).
- Wird in **Ethernet-Frames** und bei **ARP-Anfragen (Address Resolution Protocol)** genutzt.
- **Switches lernen MAC-Adressen**, um Frames gezielt an das richtige Gerät zu senden (**MAC-Adress-Tabelle**).

### **6. Unterschied MAC-Adresse vs. IP-Adresse**

|**Merkmal**|**MAC-Adresse**|**IP-Adresse**|
|---|---|---|
|**Ebene**|Schicht 2 (Sicherungsschicht)|Schicht 3 (Netzwerkschicht)|
|**Vergabe**|Vom Hersteller vergeben|Vom DHCP-Server oder manuell|
|**Gültigkeit**|Nur im lokalen Netzwerk|Weltweit eindeutig (öffentlich)|
|**Veränderbar?**|Eigentlich fest, aber änderbar|Kann dynamisch vergeben werden|

## References
1. [[IPv4 Adresse]]
