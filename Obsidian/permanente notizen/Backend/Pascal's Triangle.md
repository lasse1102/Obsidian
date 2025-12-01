
--- 
Erstellt: 2024-06-28    14:46 
Tags: #Programming/Scala/assignments 
Link Up: [[Scala]]
Link Down:

--- 
Die Aufgabe ist es das Pascal Dreieck zu zeichnen in der Konsole. Es soll mit [rekursiven](Recursions.md)Funktion gearbeitet werden!

```scala
object RecFun extends RecFunInterface {  
  def main(args: Array[String]): Unit = {  
  
    //Exercise 1 Pascal Triangle  
    printPascal(2)
 }
}

def printPascal(n: Int): Unit = {  
  for (row <- 0 to n) {  
    for (col <- 0 to row) {  
      print(pascal(col, row) + " ")  
    }  
    println()  
  }  
}

def pascal(c: Int, r: Int): Int = {  
    if (c == 0 || c == r) 1  
    else pascal(c - 1, r - 1) + pascal(c, r - 1)  
  }  

```

Output:
1 
1 1 
1 2 1

## References
1. 
