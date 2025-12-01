
--- 
Erstellt: 2024-05-22    17:09 
Tags: 
Link Up: [[JavaScript]]
Link Down:

--- 
# Was machen Default Parameter
In JS sind Default-Parameter Funktionen, die es ermöglichen, benannte Parameter mit Standartwerten zu initialisieren, wenn kein Wert oder undefined übergeben wird. Normalerweise werden Funktionen in JS mit undefined initialisiert, Default Parameter sind jedoch nützlich um andere Standartwerte festzulegen

# Beispiele
```js
function multiply(a, b = 1){
	return a * b;
}

console.log(multiply(5,2)); // 10
console.log(multiply(5)) // 5
```
In erstem console.log wird der Default Parameter mit der 2 überschrieben somit ist b = 2. Im zweiten console.log wird der Default Parameter angewendet, weil kein 2 Parameter mitgegeben wird.

# Was ist wenn wir nur eine Teilmenge an Parameter mitgeben wollen

```js
const begruesung = function (vorname = "Max", nachname = "Mustermann", alter = 43){  
  console.log(`Hallo ${vorname} ${nachname},  
  du bist ${alter} Jahre alt.  Wie geht es dir?  `)  
}  
  
let vorname = "Lasse";  
let nachname = "Pöhls";  
let alter = 20;  
  
begruesung(vorname, nachname,alter)  // Überschreibt alle Default Parameter
begruesung(); // Nimmt alle Default Parameter
begruesung(undefined, nachname, alter)// Hiermit geben wir nur den nachnamen und das alter mit und beim vorname wird der Default Parameter verwendet
```
## References
1. 

## Quellen
1. 