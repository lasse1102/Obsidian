
--- 
Erstellt: 2024-07-02    15:39 
Tags: #Programming/Scala/higherOrderFunction  
Link Up: [[Scala]]
Link Down:

--- 
# Definition
- Funktionale Sprachen behandeln Funktionen als erstklassige Werte
- Funktionen können, als Parameter an anderen Funktionen übergeben werden und als Ergebnis ins Result Statement gepackt werden
- Dies bietet die Möglichkeit Programme flexible zu gestalten
- Funktionen die andere Funktionen als Parameter enthalten oder Funktionen im Result Keyword enthalten werden Higher Order Functions genannt

# Beispiele Higher Order Functions

Berechnung ohne Higher Order Functions:
```scala
def cube(x: Int): Int = x * x * x

def sumCube(a: Int, b: Int): Int ={
	if(a > b) 0 else cube(a) + sumCube(a + 1, b)
}
```


Berechnung mit Higher Order Functions
```scala
def cube(x: Int): Int = x * x * x

def sumCube2(c: Int => Int, a: Int, b: Int): Int ={  
  if(a > b) 0 else c(a) + sumCube2(c, a + 1, b)  
}
```
- Hier wird cube direkt mit als Parameter(c) übergeben, und kann in der Funktion ganz normal wie jeder andere Wert verwendet werden!

## References
1. 
