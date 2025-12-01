
--- 
Erstellt: 2024-07-16    09:08 
Tags: #Programming/Scala/classesAndObjects 
Link Up: [[Scala]]
Link Down:

--- 
Anonyme Objekte sind Objekte, die instanziiert sind, aber keine Referenz enthalten. Sie können ein anonymes Objekt erstellen, wenn Sie es nicht wiederverwenden möchten.

Beispiel:
```Scala
// Scala program to illustrate how 
// to create an Anonymous object
class GFG
{
	def display()
	{
		println("Welcome! GeeksforGeeks");
	}
}
object Main 
{
	def main(args: Array[String]) 
	{
		// Creating Anonymous object of GFG class
		new GFG().display();
	}
}

```

## References
1. 
