
--- 
Erstellt: 2024-05-23    12:52 
Tags: 
Link Up: [[JavaScript]]
Link Down:

--- 
# let
- Dieses Schlüsselwort wird verwendet, um eine Variable zu deklarieren, deren Wert später im Code geändert werden kann
- Es hat Block-Scope, was bedeutet, dass die Variable nur innerhalb des Blocks (zum Beispiel innerhalb einer Schleife oder eines if-Statements) zugänglich ist, in dem sie definiert wurde.

# const
- Dieses Schlüsselwort wird verwendet, um eine Konstante zu deklarieren, also eine Variable, deren Wert nach der Initialisierung nicht mehr geändert werden kann
- Besitzt ebenfalls Block Scope

### const bei Objekten
Eigentlich kann man Werte mit const nicht ändern. Anders ist es bei Objekten die als const deklariert sind. Hier kann man Werte ändern, Eigenschaften hinzufügen oder löschen
Beispiel:
```js
const person = {
	name: "Lasse",
	nachname: "Pöhls",
	alter: 20
}

person.name = "Peter" // Wert von name wird zu Peter geändert
person.haarfarbe = "braun" // haarfarbe wird als Eigenschaft hinzufügt
delete person.alter // alter wird gelöscht
```
# var
**Hoisting**: Variablen, die mit var gekennzeichnet werden, werden "gehoisted". Das bedeutet, dass ihre Deklaration an den Anfang des Skripts verschoben wird aber ihre initialisierung bleibt an der ursprünglichen Stelle:
```js
a = 10;
console.log(a); // error

var = a; // dies rückt direkt beim ausführen des Skriptes an den Anfang 
console.log(a) // 10
```
Hint: Dennoch sollte man niemals var verwenden, da es logisch keinen Sinn macht und die Gültigkeitsbereiche unbrauchbar macht. Am besten immer let und const verwenden

# Kurzschreibweise Deklaration von Variablen
Wenn man mehrere Variablen deklarieren oder initialisieren will auf einmal, kann man eine verkürtzte Schreibweise verwenden, um nicht vor jeder Variable let oder const schreiben muss:
```js
let einnahmen = 0,  
    ausgaben = 0,  
    bilanz = 0,  
    titel,   
    typ,   
    betrag,   
    datum;
```

# References
1. 

# Quellen
1. 