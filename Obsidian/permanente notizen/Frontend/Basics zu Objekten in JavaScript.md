
--- 
Erstellt: 2024-05-27    09:32 
Tags: 
Link Up: [[JavaScript]]
Link Down:

--- 
# Erstellen von Objekte in JS
Anders als in [[PHP]] werden die Objekte nicht aus Klassen erstellen:

Erstellung eines Objektes in JavaScript:
```js
const auto = {
	marke: "BMW",
	modell: "116i",
	krafstoffverbrauch: "Benzin",
	ausstattung: {
		navigationssystem: true,
		Klimaanlage: true,  
	    Sitzheizung: true,  
	    Tempomat: false,  
	    Panoramadach: false,  
},  
	zustand: "Mittel",  
	preis: 4000
}
```

# Zugreifen auf ein Wert im Objekt
Um ein einzelnen Wert aus dem Objekt auszugeben wird die "Dot-Notation" verwendet. 
In [[PHP]] wird hierfür "->" verwendet:
Beispiel:
```js
let tempomat = auto.ausstattung.Tempomat;
console.log(tempomat) // false
```

Mit der Bracket Notation:
```js
let tempomat = auto["aussattung"]["tempomat"];
console.log(tempomat) // false
```

# Eigenschaft hinzufügen und Werte ändern 
Werte zu einem Objekt hinzufügen
```js
auto.ps = 145;
```
Werte ändern:
```js
auto.modell = "118";
```

# Eigenschaften löschen
```js
delete auto.marke
```

## References
1. 

## Quellen
1. 