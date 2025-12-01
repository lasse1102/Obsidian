
--- 
Erstellt: 2024-04-19    13:57 
Tags: #School/LF03/IPv4-Adressen 
Link Up: [[IPv4 Adresse]]
Link Down:

--- 
# Definition Subnetting
Subnetting ist das Bilden von Teilnetzen innerhalb eines zusammenhängenden Adressraums von IP-Adressen

Ein Subnet, Subnetz bzw. Teilnetz ist ein physikalisches Segment eines Netzwerks, in dem IP-Adressen mit der gleichen Netzwerkadresse benutzt werden. Diese Teilnetze können über Router miteinander verbunden werden und bilden dann ein großes zusammenhängendes 
Netzwerk.

# Grundlegendes Verständnis
- IP-Adresse: Eine logische numerische Adresse, die jedem einzelnen Computer, Drucker, Switch, Router oder jedem anderen Gerät zugewiesen wird, das Teil eines TCP/IP-basierten Netzwerks ist
- Teilnetz: Ein separater und identifizierbarer Teil des Netzwerks einer Organisation, der normalerweise auf einer Etage, einem Gebäude oder an einem geografischen Ort angeordnet ist.
- Subnetz-Maske: Eine 32-Bit-Zahl, die zur Unterscheidung der Netzwerkkomponente einer IP-Adresse verwendet wird, indem die IP-Adresse in eine Netzwerkadresse und eine Hostadresse unterteilt wird
	Beispiel: 255.255.255.0 =  1111 1111. 1111 1111. 1111 1111. 0000 0000 = 32Bit

# Warum wir Subnetze brauchen
Wir benötigen Subnetze, um ein Netzt zum Beispiel ein Unternehmen in mehrere Teilnetzte zu unterteilen. Diese Teilnetzte haben jeder einzelne Hosts. 
In diesem Beispiel wäre zum Beispiel das Netzt OKLogistics, welches in verschiedene Abteilung unterteilt ist(IT, Einkauf, Lager), jeder dieser einzelnen Abteilung wird jetzt in Subnetz unterteilt. Jedes Gerät(Drucker, Computer usw.) hat eine eigene Adresse, die es logisch mit den andren Geräten im selben Subnetz verbindet. Diese Geräte werden auch als Hosts bezeichnet.
Somit kann die Abteilung Einkauf nicht die Drucker im Bereich IT einsehen oder andersherum, da es unterschiedliche Subnetze sind

# Verstehen von Binärzahlen

Mit dem Dezimalsystem können wir immer größere Zahlen darstellen, indem wir Zahlen aneinander heften. So gibt es einstellige Zahlen wie 1, zweistellige Zahlen wie 12, dreistellige Zahlen wie 105 und so weiter und so fort. Wenn die Zahlen größer werden, steht jede Ziffer für einen immer größeren Wert. Es gibt eine 1er-Stelle, eine 10er-Stelle, eine 100er-Stelle und so weiter.
![[dezimahlzahlen.jpeg]]

Bei dieser Zahl haben wir eine 5 an der 1er-Stelle, eine 0 an der 10er-Stelle und eine 1 an der 100er-Stelle. Daraus folgt,

1 x 100 + 0 x 10 + 5 x 1 = 105

Binäre Zahlensysteme basieren auf demselben Konzept, mit dem Unterschied, dass es im Binärsystem nur zwei Zahlen gibt, 0 und 1, und daher viel mehr Gruppierungen erforderlich sind, um dieselbe Zahl darzustellen. Das binäre Äquivalent von 105 ist zum Beispiel 01101001 (eigentlich wird es normalerweise als 1101001 geschrieben, da wie im Dezimalsystem führende Nullen weggelassen werden. Wir lassen jedoch die erste Null an Ort und Stelle, um das nächste Konzept zu erklären).

Auch hier gilt, dass mit zunehmender Größe der Binärzahlen jede Ziffer einen immer größeren Wert darstellt, aber das Binärsystem hat jetzt eine 1er-Stelle, eine 2er-Stelle, eine 4er-Stelle, eine 8er-Stelle, eine 16er-Stelle, eine 32er-Stelle und so weiter.

![[binaerzahlen.jpeg]]
Daraus folgt,
**0 x 128 + 1 x 64 + 1 x 32 + 0 x 16 + 1 x 8 + 0 x 4 + 0 x 2 + 1 x 1**
ist gleich:
**0 + 64 + 32 + 0 + 8 + 0 + 0 + 1 = 105**

# Netzanteil und Hostanteil
Eine IP-Adresse besteht aus einem Netzanteil und einem Hostanteil. Der Netzanteil identifiziert ein Teilnetz, der Hostanteil identifiziert ein Gerät (Host) innerhalb eines Teilnetzes.

Die genaue Aufteilung zwischen Netz und Hostanteil, wird durch eine Subnetzmaske festgelegt.
`Bsp: 
``255.255.255.0 wäre in binärer Schreibweise 11111111.11111111.11111111.00000000`
Die Bits die 1 ergeben gehören zum Netzanteil der IP-Adresse und die Bits die 0 ergeben gehören zum Hostanteil der IP-Adresse. In dem Beispiel würden es 24 Bits für den Netzanteil entsprechen, diese werden meist als Suffix an die IP Adresse gehängt, beispielsweise 192.0.2.155/24. Somit ist der Netzanteil 24 Bits lang, was die Subnetzmaske 255.255.255.0 entspricht

``
Der Netzanteil wird verwendet um Subnetze zu definieren und die Größe des Netzwerks zu bestimmen. Der Hostanteil wird verwendet, um individuelle Geräte innerhalb eines Netzwerkes zu identifizieren. Beide Anteile sind entscheidend für das Routing von Datenpaketen im Internet. Wenn der Netzanteil identisch ist, können die Endgeräte innerhalb einer [[Broadcast-Domäne]] direkt miteinander kommunizieren, beispielsweise per Ethernet oder WLAN

# Subnetting und die Subnetzmaske



## References
1. 

## Quellen
1. https://www.techopedia.com/de/in-8-schritten-ip-subnetting-verstehen