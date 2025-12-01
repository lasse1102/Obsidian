
--- 
Erstellt: 2024-06-30    17:46 
Tags: #Programming/Scala/Allgemeines 
Link Up: [[Scala]]
Link Down:

--- 
# val und var
val und var werden zur Deklaration von Variablen verwendet.

val wird verwendet, um eine unveränderliche Variable zu deklarieren, was bedeutet, dass ihr Wert nach der ersten Initialisierung nicht geändert werden kann. Es ist ähnlich wie das Schlüsselwort final in Java.
```scala
val x = 10
```
Wenn versucht wird x zu ändern, dann erscheint ein Kopilierungsfehler

---

var wird verwendet, um eine **veränderliche Variable zu deklarieren** was bedeutet, dass ihr Wert nach der ersten Initialisierung geändert werden kann.
```scala
var y = 20
```
In diesem Fall können Sie `y` ändern, nachdem Sie es auf 20 gesetzt haben. Wenn Sie `y` auf einen anderen Wert setzen, z.B. 30, wird es ohne Fehler kompiliert.
# Funktionen

# Loops und Iteration oder [[Recursions|Recursion]]
- In Programmiersprachen wie Scala wird Unveränderlichkeit bevorzugt. Schleifen und Iterationen erfordern in der Regel die Änderungen des Zustands, was zu Seiteneffekte führen kann
- [[Recursions]] sind effizienter und Verbrauchen weniger Speicherbedarf, wie Loops und Iterationen
- Schleifen und Iterationen erfordern oft die Verwaltung von Zuständen (wie z.B. Zähler oder temporäre Variablen), was zu komplexerem und schwere zu wartenden Code führen kann

## References
1. 
