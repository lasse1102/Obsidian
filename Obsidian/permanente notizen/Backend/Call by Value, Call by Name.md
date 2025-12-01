
--- 
Erstellt: 2024-06-28    09:05 
Tags: #Programming/Scala/Allgemeines 
Link Up: [[Scala]]
Link Down:

--- 
In Scala gibt es zwei Arten von Parameterübergabestrategien **Call by Value**, **Call by Name**
![[Pasted image 20240628091019.png]]

# Call by Value
Bei **Call by Value** wird der Ausdruck, der als Argument übergeben wird, **sofort ausgewertet**. Das bedeutet, dass der Wert des Ausdrucks berechnet wird, bevor die Funktion aufgerufen wird. Innerhalb der Funktion wird dann dieser berechnete Wert verwendet. Hier ein Beispiel:

```scala
def callByValue(x: Int) = {
  println("x1=" + x)
  println("x2=" + x)
}

val a = 10
callByValue(a + 20)
```

In diesem Beispiel wird `a + 20` zuerst ausgewertet und das Ergebnis (30) wird dann an die Funktion `callByValue` übergeben.
# Call by Name
Bei **Call by Name** wird der Ausdruck **nicht sofort ausgewertet**. Stattdessen wird der Ausdruck jedes Mal neu ausgewertet, wenn er innerhalb der Funktion verwendet wird. Hier ein Beispiel:

```scala
def callByName(x: => Int) = {
  println("x1=" + x)
  println("x2=" + x)
}

val a = 10
callByName(a + 20)
```

### Wann verwendet man was?

Call by Value
- ist effizienter, wenn der Ausdruck einfach ist und keine teuren Berechnungen enthält
Call by Name
- ist nützlich, wenn der Ausdruck teuer zu berechnen ist und möglicherweise nicht immer benötigt wird. Ein typisches Beispiel ist das Logging, bei dem man vermeiden möchte, dass teure Berechnungen durchgeführt werden, wenn das Logging-Level dies nicht erfordert


---
# Termination

![[Pasted image 20240628091640.png]]

Hier ein Beispiel, wann Call by Name beendet wird und Call by Value nicht:
![[Pasted image 20240628092000.png]]



## References
1. [[Call by Value, Call by Reference]]
