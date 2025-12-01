
--- 
Erstellt: 2024-08-19    07:43 
Tags: #Programming/Scala/TypesUndPatternMatching 
Link Up: [[Scala]]
Link Down:

--- 
# Enums
Enums ermöglichen es, eine festgelegte Menge von Instanzen zu definieren, die häufig in Fällen verwendet werden, in denen ein Wert nur eine von mehreren vordefinierten Optionen sein kann
```Scala
enum Farbe
	case rot, grün, blau
```
In diesem Beispiel definiert das `Farbe`-Enum drei mögliche Werte: `Rot`, `Grün` und `Blau`. Diese Werte können dann in Programmen verwendet werden, um sicherzustellen, dass nur diese vordefinierten Farben als Werte verwendet werden.

### Verwendung von Enums
1. Zugriff auf die Enum- Werte
```Scala
val farbe: Farbe = Farbe.rot	
```
2.  Pattern Matching 
```Scala
def beschreibeFarbe(farbe: Farbe): String = farbe match {
	case Farbe.rot => "Die Farbe ist Rot"
	case Farbe.grün => "Die Farbe ist Grün"
	case Farbe.blau => "Die Farbe ist Blau"
}
```
3. Enums mit zusätzlichen Parametern
```Scala
enum Wochentag (val Wochenende: Boolean):
	case Montag, Dienstag, Mittwoch, Donnerstag, Freitag extends Wochentag(false)
	case Samstag, Sonntag extends Wochentag(true)	
```

# Parameter, Typparameter & Vererbung
Enums selbst können Parameter und Typparameter entgegennehmen, um beispielsweise Methoden auf alle Werten des Enums oder Summentyps zu definieren 
```Scala
enum Parts:
	case GramsPer100Milliliters(grams: Double)
	case KilogramsPerLiter(kilograms. Double)

import Parts._

enum GruitWithSuger[T](sugerContent: T):
	def duger : T = sugerContent
	case Orange extends FruitWithSuger(GramsPer100Milliliters(1.2))
	case Apple extends FruitWithSuger(KilogramsPerLiter(0.002))
```

## References
1.  [[Pattern Matching]]
