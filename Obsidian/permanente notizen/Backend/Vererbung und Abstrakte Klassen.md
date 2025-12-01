
--- 
Erstellt: 2024-07-17    13:39 
Tags: #Programming/Scala/classesAndObjects
Link Up: [[Scala]]
Link Down:

--- 
# Vererbung
In Scala ist die Vererbung ein grundlegendes Konzept der objektorientierten Programmierung, das es ermöglicht, eine neue Klasse (Unterklasse) von einer bestehenden Klasse (Oberklasse) abzuleiten. Die Unterklasse erbt die Eigenschaften und Methoden der Oberklasse und kann zusätzliche Eigenschaften und Methoden hinzufügen oder bestehende Methoden überschreiben.

Ein einfaches Beispiel:
```scala
//Basisklasse
class Person(val name: String, val age: Int) { 
	def greet(): String = s"Hello, my name is $name and I am $age years old." 
}



//Abgeleitete Klasse
class Employee(name: String, age: Int, val company: String) extends Person(name, age) { 
	def work(): String = s"I am working at $company."

// Überschreiben der greet-Methode
	override def greet(): String = s"Hello, my name is $name, I am $age years old and I work at $company."																	
```
das Keyword override ist notwendig, um die Methode greet aus der Superklasse zu überschreiben. Wenn wir nur "def greet" schreiben würden, dann würde ein error erscheinen

# Abstrakte Klassen und Methoden
**Abstrakte Klassen und Methoden**: Eine Klasse kann als `abstract` deklariert werden, was bedeutet, dass sie nicht direkt instanziiert werden kann. Sie kann abstrakte Methoden enthalten, die von Unterklassen implementiert werden müssen.
Beispiel.
```scala
abstract class Animal{
	def makesound(): String  //Abstrakte Methode
}
class Dog extends Animal{
	override def makeSound(): String = "Woof"
}

val dog = new Dog
println(dog.makesound())  // Ausgabe Woof
```




## References
1. [[Classes#Override]]
