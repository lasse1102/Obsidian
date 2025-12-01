
--- 
Erstellt: 2024-06-27    14:32 
Tags: #Programming/Scala/Allgemeines 
Link Up: [[Scala]]
Link Down:

--- 
Ein Objekt, welches zu einen "val" zugeordnet ist kann nicht geändert werden, wobei ein Objekt, welches zu einen "var" zugeordnet ist schon geändert werden kann. 

Allerdings kann der interne Zustand des Objektes geändert werden:
```scala
class A(n: Int) {
  var value = n
}

class B(n: Int) {
  val value = new A(n)
}

object Test {
  def main(args: Array[String]) {
    val x = new B(5)
    x = new B(6) // Doesn't work, because I can't replace the object created on the line above with this new one.
    x.value = new A(6) // Doesn't work, because I can't replace the object assigned to B.value for a new one.
    x.value.value = 6 // Works, because A.value can receive a new object.
  }
}
```
Wir man hier sieht, kann man weder "val x" ändern noch Werte aus dem Objekt. Stattdessen können wir Werte aus dem Objekt a ändern
## References
1. [Erklärung in Stackoverflow](https://stackoverflow.com/questions/1791408/what-is-the-difference-between-a-var-and-val-definition-in-scala)
