
--- 
Erstellt: 2024-07-08    14:49 
Tags: #Programming/Scala/Allgemeines 
Link Up: [[Scala]]
Link Down:

--- 
# Anonyme Funktionen in Scala
Anonyme Funktionen haben keinen Namen und werden oft direkt verwendet, wo sie definiert werden. Sie sind besonders nützlich für einmalige Operationen oder wenn man eine Funktion als Argument an eine höhere Funktion übergeben möchte.

### Unterschied der Syntax von einer normalen Funktion und einer anonymen Funktion
1. Normale Funktion
```scala
def add(a: Int, b: Int): Int = {
a + b
}
```
1. Anonyme Funktion
```scala
val add = (a: Int, b: Int) => a + b

// Verwendung
val sum = add(2, 5) // sum ist 7
```

# Vergleich

| Kriterium                       | Normale Funktion                              | Anonyme Funktion                             |
| ------------------------------- | --------------------------------------------- | -------------------------------------------- |
| **Deklaration**                 | Mit `def` und einem Namen                     | Ohne `def`, direkt als Ausdruck              |
| **Syntax**                      | `def name(args: Type*): ReturnType = { ... }` | `(args: Type*) => expression`                |
| **Verwendung**                  | Über den Funktionsnamen                       | Direkt, oder über Zuweisung an eine Variable |
| **Lesbarkeit/Wiederverwendung** | Gut lesbar und wiederverwendbar               | Kürzer, für einmalige oder lokale Nutzung    |
| **Parameterliste**              | Muss angegeben werden                         | Muss angegeben werden                        |
| **Rückgabewert**                | Muss angegeben werden (oder wird abgeleitet)  | Wird abgeleitet                              |

# Wann welche Funktion verwenden
- Normale Funktion: Verwenden, wenn die Funktion mehrfach benötigt wird oder komplex ist. Sie sind besser lesbar uns wiederverwendbar.
- Anonyme Funktionen: Ideal für kurze, einmalige Operationen oder als Argumente für Higher Order Funktionen 

## References
1. 
