
--- 
Erstellt: 2024-08-12    13:22 
Tags: #Programming/Scala/classesAndObjects 
Link Up: [[Scala]]
Link Down:

--- 
# Listen in Scala
Listen in Scala sind ähnlich wie Arrays in imperativen Programmiersprachen. Es gibt aber 2 wesentliche unterschiede:
- Listen sind unveränderlich, die Elemente einer Liste können nicht verändert werden
- Listen sind Rekursiv, Arrays nicht

Wie Arrays, müssen Listen den gleichen Datentypen haben, es kann in einer Liste also nicht Int und Strings geben
![[Pasted image 20240816095935.png]]

# Andere Möglichkeiten Listen zu erstellen
Eine weitere Möglichkeit Listen zu erstellen, ist mit den Kons-Operator "::".
```Scala
val fruits = "Apple" :: "Banana" :: "Cherry" :: Nil
```

Mit List.fill kann man zu einer Liste wiederholte Elemente hinzufügen
```Scala
val fiveApples = List.fill(5)("Apple")
```

Eine Liste mit List.range erstellen
```Scala
val number = List.range(1,10)
```

Weitere Möglichkeiten Listen zu erstellen oder du ändern
![[Pasted image 20240823090525.png]]
---




# Beispiele
```scala
List(List(true, false), List(3))
```
Das würde wie folgt aussehen: ![[Pasted image 20240812133011.png]]

Beispiel 2 (Listen sind Rekursiv aufgebaut)
![[Pasted image 20240816095801.png]]

Beispiel 3 (Wie ist die Länge der Liste)
![[Pasted image 20240816101247.png]]

# Funktionen die auf Listen angewendet werden können 
- head (gibt das erste Element der Liste aus)
```scala
val fruits = List("apple", "banana", "orange")
fruits.head // apple
```
- tail (entfernt das erste Element der Liste)
```scala
val fruits = List("apple", "banana", "orange")
fruits.tail.head // orange
```
- isEmpty (prüft ob die Liste leer ist)
```Scala
val fruits = List("apple", "banana", "orange")
fruits.isEmpty // false
````

###### Weitere Methoden die auf Listen angewendet werden können
![[Pasted image 20240823085320.png]]

###### Elemente in einer Liste finden
![[Pasted image 20240823090637.png]]
## References
1. 
