
--- 
Erstellt: 2024-05-27    15:00 
Tags: 
Link Up: [[JavaScript]]
Link Down:

--- 
In JavaScript, **Call by Value** und **Call by Reference** sind zwei Methoden, mit denen Funktionen ihre Argumente behandeln. Hier ist eine kurze Erklärung
# Call by Value

Bei **Call by Value** wird der Wert einer Variable an eine Funktion übergeben. Das bedeutet, dass innerhalb der Funktion eine lokale Kopie des Wertes erstellt wird. Änderungen an dieser Kopie haben keinen Einfluss auf die ursprüngliche Variable außerhalb der Funktion.

Beispiel:
```javascript
function changeValue(value) {
  value = "etwas anderes";
}
let myVar = "Original";
changeValue(myVar);
console.log(myVar); // Gibt "Original" aus, da `myVar` nicht verändert wurde.
```

## Call by Reference

**Call by Reference** bezieht sich auf das Übergeben einer Referenz auf die Variable, nicht den tatsächlichen Wert. In JavaScript geschieht dies bei Objekten, wie Arrays oder Funktionen. Wenn die Eigenschaften eines Objekts innerhalb der Funktion geändert werden, spiegeln sich diese Änderungen auch außerhalb der Funktion wider.

Beispiel:
```javascript
function changeProperty(obj) {
  obj.property = "etwas anderes";
}

let myObj = { 
	property: "Original" 
};

changeProperty(myObj);
console.log(myObj.property); // Gibt "etwas anderes" aus, da `myObj.property` verändert wurde.
```
## References
1. 

## Quellen
1. 