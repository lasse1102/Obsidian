
--- 
Erstellt: 2024-06-28    14:34 
Tags: #Programming/Scala/assignments
Link Up: [[Scala]]
Link Down:

--- 
Es soll ein Betrag(money) gegeben sein und eine Liste von münzen(bsp. 1,2)
Nun sollen alle Möglichkeiten angegeben werden den Betrag(money) mit den gegebenen Münzen zurückzuzahlen.

```scala 
def countChange(money: Int, coins: List[Int]): Int = {  
  if (money == 0) 1  
  else if (money < 0 || coins.isEmpty) 0  
  else countChange(money, coins.tail) + countChange(money - coins.head, coins)  
}
```
- Es wird immer 1 returnt, wenn money== 0 ist, dies bedeutet das es eine Gütige Möglichkeit ist. Dies wird dann addiert und am ende erhält man alle verschiedenen Möglichkeiten als Ergebnis

## References
1. 
