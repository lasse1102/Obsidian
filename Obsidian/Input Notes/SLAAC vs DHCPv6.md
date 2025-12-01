
--- 
Erstellt: 2025-07-03    13:58 
Tags: 
Link Up: 
Link Down:

--- 
1. Statfull:
	DHCPv6 - Server -> Server verwaltet die Leases für die IPv6-Adressen Rahmen vordefiniert (Kontrollierte Vergabe)

2. Stateless:
	Stateless Adresse Auto Configuration (SLAAC)
	- Router verteilen Prefixes Clients bilden selbst den Interface Identifier mit Hilfe der MAC-Adresse (Keine zentrale Verwaltung)
	- Router Solicitation: Client fordert beim Start ein Prefix an und erhält es im vorgesehenen Zeitintervall
	- Periodisches Zeitintervall, lässt sich einstellen z.B. alle 30sec oder alle 200sec usw. ... (Router Advertisement)
Inhalt Advertisment:
- Prefix
- Flags/Options
- Lifetimes
- 0-Flag oder z.B. M Flag gesetzt für Kombinationen von SLAAC und DHCPv6

## References
1. 
