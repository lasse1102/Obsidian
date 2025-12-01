
--- 
Erstellt: 2024-06-30    19:39 
Tags: #Programming/Scala/Allgemeines 
Link Up: [[Scala]]
Link Down:

--- 
[[Funktionale Programmierung in Scala]] enthalten keine Befehle und manipulieren **keine** Werte von Speicherzellen. Es gibt zwar for und While Loops in Scala aber es wird vermieden, diese zu benutzen, da mehr auf Recursion gesetzt wird in der Funktionales Programmierung. Um eine „Wiederholung“ in einer funktionalen Sprache zu ermöglichen, werden Funktionen **rekursiv** definiert.

# Rekursion vs Iteration
In Imperativen Programmiersprachen können Funktionen sowohl iterativ als auch rekursiv definiert werden:
  
**Iteration**
- Jede Programmiersprache hat ihre Schlüsselwörter (z.B. while und for)
- Die Aufgabe wird schrittweise durchgeführt
- Die Anweisungen, die unter dem Schlüsselwort (z.B. for oder while) stehen, werden mehrfach ausgeführt
- Jede Iteration braucht eine Abbruch-Bedingung, die als ein logischer Ausdruck programmiert wird

**Rekursion**
- Es gibt kein Schlüsselwort
- Die Aufgabe erklärt sich, "durch sich selbst"
- Die rekursive Funktion ruft sich auf
- Eine Rekursion muss terminiert werden, wenn die Funktion "durch sich selbst" nicht mehr definierbar ist, also eine Abbruch Bedingung enthalten

# Linear und Tail Recursion
In Scala, wie auch in anderen funktionalen Programmiersprachen, gibt es zwei Hauptarten der Rekursion: lineare (oder einfache) Rekursion und Tail-Rekursion (Endrekursion).

**Lineare Rekursion**
- Lineare Rekursion ist eine Art von Rekursion, bei der sich die Funktion sich selbst aufruft, <mark style="background: #FFF3A3A6;">aber nur einmal pro Aufruf.</mark> Und der Aufruf muss nicht unbedingt der letzte Schritt in der Funktion sein

Die Fakultätsfunktion ist ein klassisches Beispiel für lineare Rekursion:
```scala
def factorial(x: Int): Int ={
	if(x == 0)0
	else x * factorial(x - 1)	
}

println(factorial(5)) // Ausgabe: 120
```
So würde es aussehen, wenn die Funktion ausgewertet wird:
![[Pasted image 20240703120014.png]]

**Tail-Rekursion**
- Lineare Rekursion, die nicht noch einmal "zurücklaufen"(wie in den Beispiel oben), nennt man Tail Rekursion. 
- Die Funktion ist nicht linear, wenn die Ausführung zu mehr als einem rekursiven Aufruf führt. 
- Außerdem ist eine Tail Rekursion, die letzte Aktion zur Berechnung
- Vorteil bei dieser Funktionsdefinition ist, dass kein zusätzlicher Speicherplatz zur Verwaltung benötigt wird.


Ein Beispiel für eine Tail-Rekursion ist die Fibonacci Funktion in dieser Form
```scala
def fibonacci(x: Int): Int = {
	if(x <= 1)x
	else fibionacci(x - 1) + fibionacci(x - 2)
}
```

___

# Rekursion anhand Beispielen

Beispiel mit Iterationen:
```scala
def summe(x: Int, y: Int): Int = {  
  var ergebnis = 0  
  var i = x  
  while (i <= y) {  
    ergebnis = ergebnis + i  
    i = i + 1  
  }  
  ergebnis  
}
```
Hier lösen wir das Problem mit einer while Schleife und durchlaufen die solange bis die Abbruch- Bedingung eintritt

Beispiel mit Rekursion
```scala
def summe(x:Int, y: Int): Int = {
	if(x > y)0
	else(x + summe(x+1, y))
}
```

Ablauf der Rekursion im Detail:
![[Pasted image 20240701074153.png]]

Quelle: [[https://www.inf.hs-flensburg.de/sadeghi/vorlesungen/fp/einfuehrung/rekursion.html]]



## References
1. 
