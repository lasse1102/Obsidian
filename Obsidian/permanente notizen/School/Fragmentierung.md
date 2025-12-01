
--- 
Erstellt: 2024-03-20 14:35 
Tags: #School/LF03/IPv4-Adressen  
Link Up: [[IPv4 Adresse]]
Link Down:

--- 

Die **Fragmentierung** ist ein wichtiger Aspekt bei der Übertragung von **IPv4-Datenpaketen**. Lassen Sie mich Ihnen erklären, wie sie eine Rolle spielt:

1. **Grund der Fragmentierung**:
    
    - Wenn ein Datenpaket größer ist als die maximale Übertragungsgröße eines Netzwerks (z. B. aufgrund von MTU-Beschränkungen - Maximum Transmission Unit), muss es in kleinere Teile aufgeteilt werden, um über das Netzwerk gesendet zu werden.
    - Dies ist besonders relevant, wenn Datenpakete über verschiedene Netzwerksegmente oder Verbindungen mit unterschiedlichen MTU-Werten übertragen werden.
    
2. **Fragmentierung im Detail**:
    
    - Nehmen wir an, ein Computer sendet ein großes Datenpaket (z. B. eine Datei) an einen anderen Computer. Dieses Paket wird in kleinere Fragmente aufgeteilt, um es über das Netzwerk zu übertragen.
    - Der Absender teilt das ursprüngliche Paket in kleinere Teile auf und fügt in jedem Fragment einen **Fragment-Header** hinzu.
    - Jedes Fragment enthält einen Teil der Nutzdaten sowie Informationen aus dem ursprünglichen IPv4-Header.
    
3. **Empfängerseite**:
    
    - Der Empfänger erhält die Fragmente und setzt sie wieder zu einem vollständigen Paket zusammen.
    - Er verwendet die Informationen im Fragment-Header, um die Fragmente in der richtigen Reihenfolge zu ordnen und die ursprünglichen Daten wiederherzustellen.
    
4. **Probleme mit Fragmentierung**:
    
    - Fragmentierung kann die Netzwerkressourcen belasten und die Verarbeitungszeit erhöhen.
    - Einige Netzwerke oder Geräte können Fragmentierung ablehnen oder nur bestimmte Arten von Fragmenten akzeptieren.
    
5. **TTL (Time-to-Live)**:
    
    - Jedes Fragment hat seinen eigenen TTL-Wert.
    - Wenn ein Fragment durch einen Router weitergeleitet wird, wird der TTL-Wert um mindestens 1 verringert.
    - Wenn der TTL-Wert 0 erreicht, wird das Fragment verworfen.

Insgesamt ermöglicht die Fragmentierung die effiziente Übertragung großer Datenpakete über verschiedene Netzwerke, während gleichzeitig die Netzwerkressourcen berücksichtigt werden.

# Identification / Flags / Fragment-Offset
Die Felder _Identification, Flags_ und _Fragment Offset_ ermöglichen es, ein Datagramm, das größer ist als die MTU des nächsten Links zu fragmentieren und beim Zielrechner wieder zusammenzubauen. Dabei sind folgende Schritte nötig:
1. Als erstes muss das Flags Feld untersucht werden. Dort gibt es ein "Don't Fragment" Bit(Bit 1), wenn das gesetzt ist , kann nicht Fragmentiert werden.
2. Wenn es nicht gesetzt ist, kann der Datenbereich in kleinere Stücke aufgeteilt werden, sodass die Größe der resultierenden IP-Datagramme kleiner ist als die MTU des nächsten Hops
3. Jedes Fragment bekommt einen IP Header, der dem Header des ursprünglichen Datagramms ähnlich ist: Jedes Fragment bekommt die gleichen Werte für Source-Adress, Destination Adress, Protokoll und Identifikation. Die folgenden Felder müssen neu gesetzt werden:
	- Länge des Datagramms
	- Im Flags-Feld gibt es ein "More"-Bit- Diese muss bei allen Fragmenten gesetzt werden, außer beim letzten
	- Das Fragment Offset-Feld gibt die Position der Daten dieses Fragments relativ zum Beginn originalen Datagramms an. Die Startposition ist 0.

### Identification Feld
Das _Identification Feld_ enthält eine 16-bit Zahl, die ein IP-Datagramm eindeutig identifiziert. Fragmente eines Datagramms erhalten die selbe Nummer

### Flags
![[Pasted image 20240422093117.png]]
Wenn der Sender nicht will, das Fragmentiert wird, dann setzt er Bit 1 auf 1. Wenn dann allerdings diese Datagramm nicht ohne Fragmentierung zugestellt werden kann, dann muss es verworfen werden und der Sender erhält eine Fehlermeldung

### Fragment Offset
Das erste Fragment hat immer den Wert 0
Bei allen weiteren Fragments bildet sich der Wert aus dem versendeten Nutzdaten des vorherigen Fragments geteilt durch 8. 
Das bedeutet natürlich auch, dass der Nutzdatenanteil durch 8 teilbar sein muss. Außer beim letzten Fragment

Beispiel1:
![[Pasted image 20240422094405.png]]

Beispiel 2:
![[Pasted image 20240422094703.png]]

Nutzdaten je Ethernet-Frame in Byte = 1250 - 20(Header) = 1230 -> ist nicht teilbar durch 8 weshalb auf 1224 reduziert wird


# References
1. http://www.cip.ifi.lmu.de/~leinfeld/tcpip/node10.html