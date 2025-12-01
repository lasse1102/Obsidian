
--- 
Erstellt: 2024-04-21    22:16 
Tags: #School/LF03/IPv4-Adressen 
Link Up: [[IPv4 Adresse]]
Link Down:

--- 
Die TTL oder Time-To-Live gibt Ihnen einen Hinweis auf die Anzahl der Router zwischen Quelle und Ziel. Die TTL wird verwendet, um zu verhindern, dass ein IP-Paket eine Schleife innerhalb eines IP Netzes eine Schleife bildet und einen Zusammenbruch des Netzes verursacht. Der anfängliche TTL-Wert für ein IP-Paket ist
255 und wird dann jedes Mal, wenn es auf einen Router trifft, um 1 verringert. Wenn dieser Wert 0 erreicht, wird das Paket von einem Router verworfen. Der TTL-Wert ist in jedem IP-Paket enthalten, auch in ICMP-Pakete. Der vom Ping-Befehl angegebene TTL-Wert ist in Wirklichkeit der TTL-Wert eines echo_response-Pakets. Standardmäßig wird der TTL-Wert unter Windows um 128 und unter Ubuntu Linux
um 192 verringert.

Untersuchen wir drei Szenarien, in denen A B anpingt. B ist ein Router (erster Fall), ein Microsoft-Windows-Rechner (Fall 2) und ein Ubuntu-Linux-Rechner (Fall 3). Der TTL-Wert beträgt zunächst 255 und wird dann wie oben beschrieben verringert.

# Situation 1
Wenn von A ein Ping zu B geschickt wird, wird es ein TTL von 251 erhalten, weil es 4 Router durchläuft(-4)
TTL= 255-4 = 251

![[Pasted image 20240421222430.png]]

# Situation 2
Wenn von A ein Ping zu B geschickt wird, wird es ein TTL von 124 erhalten, weil es 3 Router durchläuft(-3) unter einer Windows Maschine(-128)
TTL=255-3-128 = 124

![[Pasted image 20240421222628.png]]
# Situation 3
Wenn von A ein Ping zu B geschickt wird, wird es ein TTL von 60 erhalten, weil es 3 Router durchläuft(-3) unter einer Ubuntu Maschine(-192)
TTL=255-3-192=60

![[Pasted image 20240421222836.png]]


## References
1. [[IPv4 Datenpaket]]

## Quellen
1. 