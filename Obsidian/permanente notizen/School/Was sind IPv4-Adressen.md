
--- 
Erstellt: 2024-03-20    23:27 
Tags: #inProcess #School/LF03/IPv4-Adressen 
Link Up: [[IPv4 Adresse]]
Link Down:

--- 
## Was sind IPv4-Adressen?

>Eine Internet-Protocol-Adresse ist eine eindeutige Kennung von Geräten, die mit einem Netzwerk verbunden sind. Anhand dieser eindeutigen Kennung können Geräte einander finden und miteinander kommunizieren.

## Format einer IPv4-Adresse

[[Das Format einer IPv4-Adresse]] wird in einer Reihe von vier 8-Bit-Binärzahlen, die durch einen Dezimalpunkt getrennt sind dargestellt. Jedes Oktett repräsentiert einen Wert zwischen 0 und 255. Zum Beispiel: `192.168.1.1`. Obwohl eine eindeutige 32-Bit-Nummer anhand eines beliebigen Zahlensystems dargestellt werden kann, sind IP-Adressen meistens mit der Punktdezimal-Schreibweise zu sehen z.B. `192.168.1.28`.

## Wichtige Informationen zu IPv4-Adressen:

1. [[Private vs. Öffentliche Adressen]]:
   - **Private Adressen** werden innerhalb eines lokalen Netzwerks verwendet und sind nicht im öffentlichen Internet sichtbar.
   - **Öffentliche Adressen** sind eindeutig und werden für die Kommunikation im Internet verwendet.

2. [[Subnetting]]:
- [[Subnetting]] bezeichnet die Aufteilung eines Netzwerks in mehrere kleine Teilnetze (Subnetze).
- Dadurch können verschiedene Hosts (z. B. Computer oder Server) effizient miteinander kommunizieren.
- Mehrere Subnetze können über Router verbunden werden, um ein großes, zusammenhängendes Netzwerk zu bilden.

3. [[DHCP]] (Dynamic Host Configuration Protocol):
   - [[DHCP]] ermöglicht die automatische Zuweisung von IP-Adressen in einem Netzwerk.

4. Statische vs. Dynamische Adressen:
   - Statische Adressen werden manuell konfiguriert und ändern sich nicht.
   - Dynamische Adressen werden vom [[DHCP]]-Server zugewiesen und können sich ändern.

5.  Klassen von IP-Adressen
	- Jede IP-Adresse gehört zu einer Klasse von IP-Adressen, abhängig von der Zahl im ersten Oktett. Diese Klassen sind:
	 ![[tabelle_oktettwerte.jpeg]]
	 Beachten Sie, dass nur die ersten drei Klassen – A, B und C – von Netzwerkadministratoren verwendet werden. Dies sind die am häufigsten verwendeten Klassen. Die anderen beiden, D und E, sind reserviert.
	 
	 ![[netzwerk-host.jpeg]]

# [[Paketformate]] und [[Fragmentierung]]

Ein IP-Paket besteht aus einem Header und den eigentlichen Nutzdaten. Insgesamt ermöglichen IP-Datenpakete die Kommunikation zwischen Geräten im Netzwerk und über das Internet.

Die [[Fragmentierung]] von IP-Paketen ist der Prozess, bei dem ein großes IP-Paket in kleinere Fragmente aufgeteilt wird, um es über ein Netzwerk zu übertragen

## References
1. https://www.uptrends.de/was-ist/ipv4
2. https://de.wikipedia.org/wiki/IPv4