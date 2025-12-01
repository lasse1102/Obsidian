
--- 
Erstellt: 2024-06-28    14:51 
Tags: #Programming/Scala/assignments 
Link Up: [[Scala]]
Link Down:

--- 
Schreiben Sie eine rekursive Funktion, die das Gleichgewicht der Klammern in einer Zeichenkette prüft, die wir als List Char und nicht als String darstellen. Die Funktion soll zum Beispiel für die folgenden Strings true zurückgeben.

```scala
object RecFun extends RecFunInterface {  
  def main(args: Array[String]): Unit = {  
    //Exercise 2 Parantheses Balance  
    val str1 = "(if (zer(o? x) (max) ((/) 1 x)))"  
    val str2 = "I told him (that it's not (yet) done). (But he wasn't listening)"  
    val str3 = ":-)"  
    val str4 = "())("  
  
    println(balance(str1.toList))  
    println(balance(str2.toList))  
    println(balance(str3.toList))  
    println(balance(str4.toList))  

  }

  
@tailrec  
def balance(chars: List[Char], counter: Int = 0): Boolean = {  
  if (chars.isEmpty) {  
    counter == 0  
  } else {  
    val head = chars.head  
    val newCounter =  
      if (head == '(') counter + 1  
      else if (head == ')') counter - 1  
      else counter  
  
    if (newCounter >= 0) balance(chars.tail, newCounter)  
    else false  
  }  
}
```

Output:
true
true
false
false

## References
1. 
