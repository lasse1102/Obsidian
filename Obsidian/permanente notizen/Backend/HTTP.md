
--- 
Erstellt: 2024-09-12    10:48 
Tags: #Programming/HTTP
Link Up: [[Programming]]
Link Down: 

--- 
# HTTP - Hypertext Transfer Protocol

HTTP bildet die Grundlage für das WWW - World Wide Web. Während [[Html]] definiert wie eine Website aufgebaut wird, legt die <mark style="background: #FFF3A3A6;">URL (Uniform Resource Locator)</mark> fest, wie die Ressource (z.B eine Website) im Web adressiert werden muss. Und HTTP ist dann dafür zuständig wie diese Website vom Server zum Client übertragen wird.

# URL (Uniform Resource Locator)
![[Pasted image 20240916121658.png]]
- <mark style="background: #BBFABBA6;">Ist das Protokoll was verwendet wird</mark>
- <mark style="background: #D2B3FFA6;">Dies ist der Server zu den wir sprechen und uns diese Website holen</mark>
- <mark style="background: #FFB86CA6;">Dies ist das Document, welches wir uns vom Server holen und welches wir aufrufen</mark>
# Prinzip des HTTP
Wenn man im Browser eine Internetadresse (URL) eingibt und sich daraufhin eine Website öffnet, hat der Browser über HTTP mit dem Webserver kommuniziert und sich die Website von ihm geholt. Dies nennt man auch das Request - Response verfahren.
Ums kurz zu fassen ist HTTP ein Anwendungsprotokoll, das zum Abrufen von Ressourcen wie Webseiten und Dateien von einem Web-Server verwendet wird.

![[Pasted image 20240912111622.png]]

#  HTTP und TCP
HTTP und TCP (Transmission Control Protocol) sind eng miteinander verknüpft, aber sie erfüllen unterschiedliche Rollen im Kommunikationsprozess zwischen Computern.

- HTTP verwendet TCP als Transportprotokoll, um die zuverlässige Übertragung von Anfragen und Antworten zwischen Client und Web Server zu gewährleistet. 
- Eine HTTP Anfrage initiiert eine TCP-Verbindung zum Web Server, auf der die HTTP Daten übertragen werden. 
- Dank TCP wird sichergestellt, dass die HTTP Anfragen und Antworten vollständig und in der richtigen Reihenfolge ankommen.

# HTTP/2 und HTTP/3
### HTTP/2
Je komplexer eine Seite wird, desto länger braucht es bis sie aufgerufen wird, da HTTP/1 vorsieht, dass die Requests innerhalb einer Verbindung nacheinander abgearbeitet werden.

Hierdurch wurde HTTP/2 2015 als neuer Standard festgelegt, um unteranderem das Laden von Websites zu beschleunigen.
- Das Protokoll basiert auf <mark style="background: #FFF3A3A6;">Binärdaten</mark> statt Textdateien
- Client und Server können <mark style="background: #FFF3A3A6;">mehrere HTTP-Requests parallel absenden bzw. verarbeiten</mark>
- Wenn der Server voraussehen kann, welche Daten der Client noch benötigen wird, kann er ihm diese von sich aus – ohne vorgängigen HTTP-Request – in einen Client-Cache senden
### HTTP/3 (Die Zukunft)
Das Problem bei den anderen HTTP Arten ist, dass das zugrundeliegende Transportprotokoll TCP. Dies verlangt, dass der Empfänger jedes Datenpaket zurückbestätigt, bevor das nächste gesendet werden darf. Wenn nun ein Paket verloren geht, müssen alle anderen Pakete auf die erneute Übertragung des verlorenen warten

Das neue HTTP/3 soll daher nicht mehr auf TCP aufbauen, sondern auf UDP, das keine derartigen korrigierenden Maßnahmen verlangt


# HTTPS
Das S in HTTPS steht für "sicher". HTTPs verwendet TLS (oder SSL), um HTTP-Anfragen und Antworten zu verschlüsseln. 
TLS verwendet eine Technologie namens [Public-Key-Kryptographie](https://www.cloudflare.com/de-de/learning/ssl/how-does-public-key-encryption-work/)

## References
1. [[Routing]]
