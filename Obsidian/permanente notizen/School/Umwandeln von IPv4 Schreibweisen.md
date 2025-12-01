
--- 
Erstellt: 2024-03-27    08:56 
Tags: #School/LF03/IPv4-Adressen  
Link Up: [[IPv4 Adresse]]
Link Down:

--- 

Wir unterscheiden bei IPv4-Adressen zwischen der dezimalen, binären und hexadezimalen Schreibweise. Diese wurden schon ausführlich hier besprochen: [[Das Format einer IPv4-Adresse]]. Um aber zum Beispiel von der dezimalen Schreibweise auf die hexadezimale Schreibweise zu kommen müssen wir dies Umrechnen:

# Umrechnungen

## Dezimal zu [[Binär]] 
- Jedes Oktett der IP-Adresse wird in eine 8-stellige Binärzahl umgewandelt.
- Beispiel: **192.0.2.155** in binärer Schreibweise:
    - 192: 11000000
    - 0: 00000000
    - 2: 00000010
    - 155: 10011011

## Dezimal zu Hexadezimal
- Jedes Oktett der  IP-Adresse wird in eine 2-stellige hexadezimale Zahl umgewandelt.
- Beispiel: 192.168.32.155 in hexadezimaler Schreibweise:
    192 : 16 = 12    R 0
	= C0
	
	168 : 16 = 10    R8
	8     : 16 = 0      R8
	= A8
	
	32 = 16 = 2      R0
	= 20

	155 : 16 = 9     R11
	6     :16  = 0     R11
	= 9B
Ergebnis = C0 A8 20 9B

## [[Binär]] zu Dezimal
- Jedes 8-stellige Binär-Oktett wird in eine dezimale Zahl umgewandelt.
- Beispiel: **11000000** in dezimaler Schreibweise ist **192**.
## [[Binär]] zu Hexadezimal
Hier rechnen wir zuerst von [[#Binär zu Dezimal]] um und anschließend dann von [[#Dezimal zu Hexadezimal]] um
## Hexadezimal zu Dezimal
Wir nehmen als Beispiel den Hexadezimal wert 9B
- Um diesen umzuwandeln muss die letzte Ziffer also B in diesem fall immer mit 16 hoch 0 multipliziert werden 
- Somit wird die 9 dann mit 16 hoch 1 multipliziert
Berechnung:
	9 x 16 hoch 1 = 144
	+ 11 x 16 hoch 0 
	= 155
	
2 Beispiel:
	A8 =
	10 x 16 hoch 1 = 160
	+ 8 x 16 hoch 0 
	= 168

Verkürtzt kann man auch einfach den letzten wert immer einfach drauf addieren, wile 16 hoch 0 immer 0 ergibt, dann spart man sich die Berechnung

	
## Hexadezimal zu [[Binär]]
Hierzu berechnen wir Zuerst [[#Hexadezimal zu Dezimal]] und anschließend dann [[#Dezimal zu Binär]]

## References
1. [[Das Format einer IPv4-Adresse]]