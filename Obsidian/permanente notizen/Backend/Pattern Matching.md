
--- 
Erstellt: 2024-07-24    08:04 
Tags: #Programming/Scala/TypesUndPatternMatching 
Link Up: [[Scala]]
Link Down:

--- 
# Pattern Matching in Scala
Patter Matching ermöglicht es Werte und Strukturen zu überprüfen und zu zerlegen. Es ähnelt dem `switch` - Statement in anderen Programmiersprachen, ist jedoch wesentlich flexibler und ausdrucksstärker. Pattern Matching wird häufig mit `match` Ausdrücken und `case` Klauseln verwendet.

Einfaches Beispiel:
```scala
val x = Int = Random.nextInt(10)

x match
	case 0 => "Null"
	case 1 => "Eins"
	case 2 => "Zwei"
	case _ => "Other"
```

Pattern Matching als Funktion
```scala
def matchTest(x: Int): String = x match
	case 0 => "Null"
	case 1 => "Eins"
	case 2 => "Zwei"
	case _ => "Other"

//Returns
matchTest(2) // Zwei
matchTest(6) // Other
```

# Case Classes
Case Classes spielen eine zentrale Rolle im Zusammenhang mit Pattern Matching in Scala. Sie sind speziell dafür ausgelegt, effizient und einfach in `match`-Ausdrücken verwendet zu werden. Diese Integration ermöglicht es, komplexe Datenstrukturen übersichtlich und sicher zu handhaben. Außerdem sind Case Classes besonders sinnvoll für unveränderliche Daten (immutable Data)

- **Automatische Deconstruction:**
    - Eine Case Class kann im `match`-Ausdruck automatisch "zerlegt" (deconstructed) werden, sodass man direkt auf ihre Felder zugreifen kann, ohne zusätzliche Methoden oder Operationen definieren zu müssen.
- **Vergleichbarkeit:**
    - Da Case Classes automatisch die `equals`-Methode basierend auf ihren Feldern implementieren, kann man sie einfach und direkt in Pattern Matching verwenden, um Vergleiche durchzuführen.

Einfaches Beispiel: 
```Scala
// Definition der Case Classes 
sealed trait Shape 
case class Circle(radius: Double) extends Shape 
case class Rectangle(width: Double, height: Double) extends Shape 
case class Triangle(a: Double, b: Double, c: Double) extends Shape 

// Funktion zur Berechnung des Umfangs 
def perimeter(shape: Shape): Double = shape match { 
	case Circle(radius) => 2 * math.Pi * radius 
	case Rectangle(width, height) => 2 * (width + height) 
	case Triangle(a, b, c) => a + b + c 
} 

// Funktion zur Berechnung der Fläche 
def area(shape: Shape): Double = shape match { 
	case Circle(radius) => math.Pi * radius * radius 
	case Rectangle(width, height) => width * height 
	case Triangle(a, b, c) => 
		val s = (a + b + c) / 2 
		math.sqrt(s * (s - a) * (s - b) * (s - c)) // Heronsche Formel 
} 

// Beispiele 
val circle = Circle(5.0) 
val rectangle = Rectangle(3.0, 4.0) 
val triangle = Triangle(3.0, 4.0, 5.0) 

println(perimeter(circle)) // Ausgabe: 31.41592653589793 println(area(rectangle)) // Ausgabe: 12.0 
println(area(triangle)) // Ausgabe: 6.0
```

- sealed trait Shape: Hier definieren wir eine geschlossene Oberklasse, die von verschiedenen geometrischen Formen wie "Circle", "Rectangle" und "Triangle" erweitert wird
- Pattern Matching mit Case Classes: 
	- **`case Circle(radius) => ...`**: Wenn das `Shape` ein `Circle` ist, wird das `radius`-Feld extrahiert und verwendet.
	- **`case Rectangle(width, height) => ...`**: Ähnlich wird bei einem `Rectangle` das `width`- und `height`-Feld extrahiert.
	- **`case Triangle(a, b, c) => ...`**: Beim `Triangle` werden die drei Seitenlängen `a`, `b` und `c` extrahiert und für die Berechnung verwendet.

### Vorteile des Einsatzes von Case Classes im Pattern Matching
1. Klarheit und Übersichtlichkeit
2. Sicherheit
3. Einfaches Handlich komplexer Datenstrukturen
## References
1. 
