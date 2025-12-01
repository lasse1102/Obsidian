
--- 
Erstellt: 2025-09-12    15:24 
Tags: #Programming/JavaScript
Link Up: [[JavaScript]]
Link Down:

--- 
# Was ist Destructuring
Objekt und Array Destructuring ist eine Möglichkeit **Eigenschaften aus einem Objekt oder Array zu machen** und einzelnen Variablen zuzuweisen

### Bei Objekten
Ohne Destructuring würden Sie die Eigenschaften so abrufen bei Objekten:
``` JS
const user = { 
	name: 'Max', 
	age: 30, 
	city: 'Berlin' 
	}; 

const name = user.name; 
const age = user.age;
```

Mit Objekt-Destrukturierung können Sie das so schreiben:
```JS
const user = { 
	name: 'Max', 
	age: 30, 
	city: 'Berlin' 
	}; 

const { name, age } = user; // name ist jetzt 'Max', age ist 30
```

### Bei Arrays 

**Traditionell** würdest du so auf die Daten zugreifen:
```JS
const colors = ['rot', 'grün', 'blau'];

const firstColor = colors[0]; 
const secondColor = colors[1];
```

**Traditionell** würdest du so auf die Daten zugreifen:
```JS
const [firstColor, secondColor] = colors; 

console.log(firstColor); // Ausgabe: rot 
console.log(secondColor); // Ausgabe: grün
```

Man kann teile des Arrays auch überspringen, wenn man sie leer lässt
```JS
const [, , thirdColor] = colors; // überspringt die ersten beiden Werte 

console.log(thirdColor); // Ausgabe: blau
```

### Rest Operator
Der Rest Operator sorgt dafür das eine beliebige Anzahl der **übrig gebliebenen Argumenten** eines Arrays sammelt
![[Pasted image 20250912154514.png]]

## Spread Operator
Der Spread Operator ist sozusagen das Gegenteil des Rest Operator
![[Pasted image 20250912154658.png]]
Er füge mit "...genres" alle Elemente eines arrays hinzu und man kann anschließen selber noch weiterer Elemente hinzufügen.

## References
1. 
