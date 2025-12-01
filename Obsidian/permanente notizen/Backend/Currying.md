
--- 
Erstellt: 2024-07-08    13:34 
Tags: #Programming/Scala/higherOrderFunction 
Link Up: [[Scala]]
Link Down:

--- 
# Was ist Currying
Currying in Scala ist eine Technik, bei der eine Funktion, die mehrere Argumente erwartet, in eine Kette von Funktionen umgewandelt wird, von denen jede nur ein einzelnes Argument erwartet. Dies ermöglicht eine schrittweise Funktionseinführung und hat mehrere Vorteile für die Programmierung.

Eine normale Funktion:
```scala
def add (a: Int, b: Int): Int = a + b
```


Eine Currified Version der selben Funktion
```scala
def add (a: Int)(b: Int): Int = a + b

val addfive = add(5)
val addTen = add(10)

println(addFive(3)) // Ausgabe: 8
println(addTen(3)) // Ausgabe : 13
```

### Welchen Vorteil bietet Currying gegenüber normalen Funktionen
Currying ermöglicht es, eine Funktion teilweise anzuwenden, was bedeutet, dass einige Argumente vorzeitig übergeben werden können und eine neue Funktion zurückgegeben wird, die die verbleibenden Argumente erwartet. (Siehe Beispiel Oben)

# Anwendungsfälle
- Mehrfaches Verwenden einer Funktion mit gleichen Anfangsparametern aber unterschiedlichen Restparametern
- Übergabe von Parametern, wenn sie im Programmverlauf zur Verfügung stehen, ohne sich bereits genutzte Parameter merken zu müssen

## References
1. [[Higher Order Functions]]
