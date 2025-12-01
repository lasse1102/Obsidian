
--- 
Erstellt: 2024-08-16    07:54 
Tags: #Programming/Scala/TypesUndPatternMatching
Link Up: [[Scala]]
Link Down:

--- 
# Type Test
Ein "Type Test" in Scala bezieht sich auf die Überprüfung des Types eines Objektes zur Laufzeit. Dies wird häufig mit Pattern Matching oder der Methode `isInstanceOf` durchgeführt. Type Test sind nützlich, wenn du je nach Typ eines Objektes unterschiedliche Operationen ausführen musst.

Beispiel bei Pattern Matching:
```Scala
def TypTest(x: Any): String = x match {
	case i: Int => s"Integer mit Wert: $i" 
	case s: String => s"String mit Wert: $s" 
	case d: Double => s"Double mit Wert: $d" 
	case _ => "Unbekannter Typ" 
	}

println(typeTest(10)) // Ausgabe: Integer mit Wert: 10 println(typeTest("Hallo")) // Ausgabe: String mit Wert: Hallo println(typeTest(3.14)) // Ausgabe: Double mit Wert: 3.14

```

Beispiel mit `isInstanceOf`:

`isInstanceOf` überprüft ob ein Objekt einem bestimmten Typs entspricht
```scala
def typeTest(x: Any): String = { 
	if (x.isInstanceOf[Int]) { 
		s"Integer mit Wert: ${x.asInstanceOf[Int]}" } 
	else if (x.isInstanceOf[String]) {
		 s"String mit Wert: ${x.asInstanceOf[String]}" 
		 } else { 
		 "Unbekannter Typ" } 
		 } 
println(typeTest(10)) // Ausgabe: Integer mit Wert: 10 println(typeTest("Hallo")) // Ausgabe: String mit Wert: Hallo
```
# Type Cast
"Type Cast" in Scala bezieht sich auf den Vorgang, bei dem ein Wert explizit von einem Typ in einen anderen umgewandelt wird. Scala stellt dafür die Methode `asInstanceOf` zur Verfügung. Diese sollte jedoch mit Vorsicht verwendet werden, da sie bei inkompatiblen Typen zu einer `ClassCastException` führen kann.

Beispiel mit `asInstanceOf`:
```Scala 
val x: Any = "Hallo" 
val y: String = x.asInstanceOf[String]
println(y) // Ausgabe: Hallo
```

Beispiel einer `ClassCastException`:
```Scala
val x: Any = "Hallo"
val y: String = x.asInstanceOf[Int] // Dies wird ein ClassCastException auslösung, weil man keine Wörter in ein Integer umwandeln kann 
```

## References
1. [[Pattern Matching]]
2. 
