
--- 
Erstellt: 2024-05-27    15:21 
Tags: 
Link Up: [[JavaScript]]
Link Down:

--- 
In JavaScript kann man ein Objekt als Rückgabewert einer Funktion zurückgeben. Hier ist ein Beispiel, wie man dies machen könnte:
```javaScript
function erstellePerson(name, alter){
	return{
		name: name
		alter: alter
	};
}
let person = erstellePerson("Max", 30)
console.log(person.name) // Gibt Max aus
console.log(person.alter) // Gibt 30 aus
```

Die Verwendung von Objekten als Rückgabewerte ist besonders nützlich, wenn man mehrere Werte aus einer Funktion zurückgeben möchte. Anstatt nur einen einzelnen Wert zurückzugeben, kann man ein Objekt mit mehreren Eigenschaften zurückgeben, wodurch die Funktion flexibler und wiederverwendbarer wird.
## References
1. 

## Quellen
1. 