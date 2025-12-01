
--- 
Erstellt: 2024-04-21    12:47 
Tags: #School/LF03/IPv4-Adressen 
Link Up: [[IPv4 Adresse]]
Link Down:

--- 
# IPv4 Header
Jedes IPv4-Datenpaket besteht aus einem Header (Kopf) und dem Payload, in dem sich die Nutzdaten befinden. Der Header ist den Nutzdaten vorangestellt. Im IP-Header sind Informationen enthalten, die für die Verarbeitung durch das Internet Protocol notwendig sind.

# Aufbau eines Ipv4 Headers
![[Pasted image 20240421161222.png]]
Der IPv4 Header besteht aus mindestens 20 Byte(1Byte = 8 Bits). Die Abbildung oben sind genau 20 Byte. Dazu kommen noch Optionale Daten, diese können bis zu 40 Byte lang sein.
Der Header ist in jeweils 32 Bit Blöcken aufgeteilt(4 Byte). 
Der IPv4-Header enthält viele verschiedene Informationen, die der Übertragung des Datenpaketes dienen. Dazu gehören die Adressen von Absender und Empfänger, Details zur [[Fragmentierung]] (wurde das Paket in kleine Häppchen geteilt?) und eine Lebensdauer, die verhindern soll, dass falsch geroutete Pakete ewig durch das Netz schwirren.

# Bedeutung der Felder im IPv4 Header
>Eigentlich ist der IPv4-Header nichts anderes als eine Folge von Einsen und Nullen, die zwischen Sender und Empfänger eines Pakets ausgetauscht werden. Die obige Tabelle mit Feldern dient nur der übersichtlicheren Darstellung und dem besseren Verständnis.
### Version
Die ersten 4 Bits im IPv4-Header beschreiben, um welche Version des Internet-Protokolls es sich bei diesem Paket handelt. Im Falle von IPv4 steht hier die Bitkombination 0100 drin (also eine 4 als vierstellige Binärzahl)

### IHL
Steht für IP Header Length. Das Feld gibt an, wie groß der IP-Header ist und zeigt damit auch an, ab welchem Bit die Nutzdaten beginnen. Das Feld ist 4 Bit lang und der Wert, der darin steht, wird vom Empfänger mit 32 multipliziert, um die Gesamtgröße des Headers (immer ein Vielfaches von 32) zu ermitteln. Steht hier also eine 5 drin, so ist der Header 5 • 32 Bit = 160 Bit lang. Steht eine 6 drin, so ist der Header 192 Bit lang.

### Type of Service
Steht für [[Type of Service]]. Das Feld kann genutzt werden, um bestimmte Datenpakete zu priorisieren, damit diese z.B. bei den Vermittlungsstellen (= Routern) schneller weitergeleitet werden. Hiermit können bestimmte Dienste (Videostream, Telefonie, etc.) bevorzugt behandelt werden.

### Total Length
Gibt die gesamte Länge des IP-Pakets (Header + Nutzdaten) an. Das Feld ist 16 Bit lang, daraus ergibt sich eine maximale IP-Paketlänge von 65535 Byte.

### Identification, Flags und Fragments Offset
Diese drei Felder kann man kaum getrennt voneinander betrachten. Alle dienen der [[Fragmentierung]] (Zerlegung) von IPv4-Paketen in kleinere Teile. Genaueres zu [[Fragmentierung]] hier: [[Fragmentierung]]

### Time to Live
Das [[Time to Live]] Feld ist 8 Bit lang. Der Wert wird als Zahl interpretiert, die die Lebensdauer des Pakets angibt. Ein Paket startet mit einem bestimmten Wert (je nach [[Betriebssystem]] kann dieser z.B. 128 oder 255 sein), der von jedem Router auf dem Weg zum Ziel um eins verringert wird. Wenn ein Router den Wert auf 0 verringert, so verwirft er das Paket.

### Protocol
In diesem 8-Bit Feld steht ein Wert, der das Protokoll auf der Folgeschicht angibt. Steckt das IP-Paket in einem TCP-Segment, so steht hier eine 6 drin. Bei UDP wäre es eine 17. Die genauen Kodierungen können in [RFC 3232](https://tools.ietf.org/html/rfc3232) nachgelesen werden.

### Header Checksum
Dieses 16-Bit lange Feld, enthält eine Prüfsumme, über die der Kopfdatenberiech gesichert wird. Diese Checksumme wird von jedem Router neu berechnet, da sich bei jedem Router die TTL ändert.

### Source-Address / Destination Address
Diese beiden Felder enthalten die Absender- und Empfänger-IP-Adresse

### Options und Padding
Das Optionsfeld des IP-Headers enthält hauptsächlich Informationen zu Routing-, Debugging-, Statistik- und Sicherheitsfunktionen. Dieses Feld ist optional und kann bis zu 40 Byte lang sein. Es ist immer in 32 Bit aufgeteilt und wird bei Bedarf mit Nullen aufgefüllt.  
Auf die genauen Funktionen dieses Feldes wird hier nicht weiter eingegangen. Nur soviel sei noch gesagt: das Optionsfeld wird meist zu Diagnosezwecken verwendet.


# Traceanalyse
Tabelle Protokolle: https://de.wikipedia.org/wiki/Protokoll_(IP)



## References
1. [[Time to Live]]
2. [[Type of Service]]
3. [[Fragmentierung]]

## Quellen
1. https://www.elektronik-kompendium.de/sites/net/2011241.htm