
--- 
Erstellt: 2024-11-21    13:44 
Tags: #School/LF09/VLANs
Link Up: [[VLANs]]
Link Down:

--- 
# Einführung in VLAN 
Warum Subnetze = VLANs ?

weil:
- Vermeidung von unnötigem Datenverkehr, weil jedes VLAN ist eine [[Broadcast-Domäne|BC-Domäne]]. Somit beschränkt sich der Anmeldeprozess nur auf das eigene Subnetz und beeinträchtigt nicht das ganze Netz => <mark style="background: #FFF3A3A6;">Netzwerkperformance</mark>
- Weniger Hardware als beim klassischen [[Subnetting]], weil Switches sich **flexible** unterteilen lassen
- Verschiedene Berechtigungen für Zugriffe u. Dienste je Subnetz konfigurierbar => <mark style="background: #FFF3A3A6;">Datensicherheit</mark>
	z.B. Gastnetz darf nicht auf Server zugreifen
- **VLANs sind einfacher Konfigurierbar** als klassische Subnetzte (Portzuweisung leichter als IP-Adressensteuerung)
- Effizientere Fehlersuche möglich, weil Fehler durch bessere Übersicht/Struktur leichter einzugrenzen sind.
- Fehler in einem Subnetz(z.B Maleware) legt nicht gleicht das gesamte Netzt lahm => <mark style="background: #FFF3A3A6;">Ausfallsicherheit</mark>

<mark style="background: #FF5582A6;">Merke: Jedes VLAN hat einen eigenen IP-Adressbereich</mark>

# VLANS (Virtual Local Network)
- Ein physikalischer Switch 
	mehrere logische Switchs
- Ports des Switches werden VLANs zugeordnet
- VLANs werden mit Hilfe von VLAN-IDs (siehe LF3, Ethernet Frame) unterschieden
- Datenpakete werden (ohne Mitwirkung eines Router) nur an Ports im selben VLAN weitergeleitet


## References
1. 
