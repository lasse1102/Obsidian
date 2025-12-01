
--- 
Erstellt: 2024-07-11    09:15 
Tags: #Programming/Scala/classesAndObjects 
Link Up: [[Scala]]
Link Down:

--- 
# Klassen Konstruktor
Der Konstruktor einer Klasse wird in den geschweiften Klammern hinter den Klassennamen definiert. Hier werden die Parameter übergeben mit der die Funktion arbeiten soll.
```scala
Person(val name: String, val age: Int) { 
	println(s"Ein neues Objekt wurde erstellt: $name, $age Jahre alt")  
	def greet(): Unit = { 
		println(s"Hallo, mein Name ist $name und ich bin $age Jahre alt.") } } 
		
Person("Alice", 30) 
person.greet()
```
1. Variablen in einem String ausgeben:
	Um dies zu tun, wie in der Methode greet, müssen wir am Anfang des Strings ein "s" schreiben und dann können wir die Variablen ausgeben mit einem "$" Zeichen voran


# Override
Der folgende Code würde nur den Hashcode vom Objekt ausgeben und nicht den tatsächlichen Wert:
```scala
class` `Rational(numerator: Int, denominator: Int)
				 
res42:Rational = Rational@1b1bcdee
```
Dies liegt daran, dass die "toString" Methode nicht übergeben wurde.

---
Methode mit "toString":
```scala
class Rational(numerator: Int, denominator: Int){
	override def toString = numerator + "/" + denominator
}
//Erstellen des Objektes und Ausgabe
new Rational(3,5)
res44: Rational = 3/5
```
Das override Schlüsselwort wird verwendet, um anzugeben, dass eine Methode oder ein Mitglied, das in der Oberklasse oder im Trait definiert ist, in einer Unterklasse oder einem anderen Trait überschrieben wird. 
Jede Klasse in Scala erbt von der Klasse "Any"


# Require
Was würde passieren, wenn wir im Nenner eine null angeben würden? Den Bruch "3/0" gibt es ja überhaupt nicht. Um dies zu unterbinden stellt uns Scala die "require"- Methode bereit.
```scala
```scala
class Rational(numerator: Int, denominator: Int){
	require(deonominator !=0)
	override def toString = numerator + "/" + denominator
}
//Erstellen des Objektes und Ausgabe
new Rational(3,5)
`java.lang.IllegalArgumentException``:` `requirement failed`
```

# Companion Objects
Ein Objekte und eine Klasse können den selben Namen haben. Dies ist möglich seit dem Scala globale namespaces eingeführt hat. Ein Namespace für Types und eins für Values.
Klassen leben im type namespace und Objekte in value namespace

Wenn ein Objekt den gleichen Namen wie eine Klasse besitzt und die im gleichen Source file sich befinden, dann nennt man das <mark style="background: #FFF3A3A6;">companions</mark>. 
```scala
class IntSet
object IntSet
	def singleton(x: Int) = NonEmpty(x, Empyt, Empty)
```


```scala
class Rational(x: Int, y: Int):
	def number = x
	def denom = y
	def add(r: Rational) =
		Rational(number * r.denom + r.number * denom,
		denom * r.denom)
	def mul(r: Rational) = ...

	override def toString = s"$number/$denom"

//Main
val x = Rational(1,3)
val y = Rational(5,7)
val z = Rational(3,2)
x.add(y).mul(z)
```

- this 
- Preconditions (require)
	1. Das Video nochmal anschauen an der Stelle wo das erklärt wird: https://www.coursera.org/learn/scala-functional-programming/lecture/TIIQj/lecture-2-6-more-fun-with-rationals
- extensions methods and Substitutions

## References
1. 
