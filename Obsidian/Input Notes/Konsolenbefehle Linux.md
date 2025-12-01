
--- 
Erstellt: 2025-03-06    12:58 
Tags: #School/LF07/Linux  
Link Up: [[Linux]]
Link Down:

--- 
# Grundlegende Linux Befehle

### `dir`
- Der `dir`-Befehl listet den Inhalt eines Verzeichnisses auf.
- Er ist ähnlich wie `ls`, zeigt aber standardmäßig weniger Details an.

### **`ls`** (list)
- Zeigt eine detaillierte Liste der Dateien und Ordner in einem Verzeichnis an.
- Häufig verwendete Optionen:
    - `ls -l` → Zeigt detaillierte Informationen (Dateigröße, Berechtigungen, Besitzer usw.).
    - `ls -a` → Zeigt auch versteckte Dateien (Dateien, die mit `.` beginnen).
    - `ls -lh` → Zeigt Dateigrößen in menschenlesbarem Format (z. B. MB, GB statt Bytes).
Beispiel:
-<mark style="background: #FFB86CA6;"> ls -la</mark>
-> Zeigt alle Datein (inkl. versteckter) mit detaillierteren Infos
### **`mkdir`**
- Erstellt ein neues Verzeichnis (Ordner).
Beispiel
- <mark style="background: #FFB86CA6;">mkdir</mark> neuer_Ordner
###### ipconfig
###### ipconfig/ip
### ``alias``
Erstellt Kurzbefehle für längere oder komplizierte Kommandos.
Beispiel:
![[Pasted image 20250306131134.png]]
Danach kannst du einfach ll eingeben statt `ls -la`

### ``iproute2``
`iproute2` ist eine Sammlung von Netzwerktools in Linux, z. B. `ip`, `ss`, `tc`.
Beispiel: 
![[Pasted image 20250306131334.png]]
###### arp
Zeigt und verwaltet die ARP-Tabelle ([[Mac-Adressen]] zu IP-Adressen).
Beispiel:
![[Pasted image 20250306131358.png]]
### `rm`
Mit rm kann man Datein löschen
Beispiel:
![[Pasted image 20250306131630.png]]
###### cp
Kopiert Dateien und Verzeichnisse.
Beispiel:
![[Pasted image 20250306131702.png]]
###### chmod
Ändert Datei- und Verzeichnisbereichte
Beispiel:
![[Pasted image 20250306131755.png]]
###### ping
Prüft, ob eine Verbindung zu einer anderen IP oder Domain besteht.
Beispiel:
![[Pasted image 20250306131834.png]]
###### traceroute
Zeigt den Pfad, den ein Paket zu einem Ziel nimmt
Beispiel:
![[Pasted image 20250306131918.png]]

###### nslookup
Führt DNS-Abfragen durch
Beispiel:
![[Pasted image 20250306131940.png]]
## References
1. [[Basic Linux Befehle| Weitere Linux Befehle]]
