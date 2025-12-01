
--- 
Erstellt: 2024-06-12    11:28 
Tags: 
Link Up: [[JavaScript]]
Link Down:

--- 
# Grundlagen
So ist eine Switch Case Anweisung aufgebaut:
```JavaScript
switch(ausdruck){
	case wert1:
		// auszuführender Code
		break;
	case wert2:
		// auszuführender Code
		break;
	case wert3:
		// auszuführender Code
		break;
	case wert4:
		// auszuführender Code
		break;
	default:
		//auszuführender Code
		break;
}
```

- Der Ausdruck wird mit den jeweiligen Cases überprüft wenn eine davon mit den Ausdruck übereinstimmt wird der code darin ausgeführt.
- Mit den break keyword sagen wird das der case beendet wird, wenn wir den weglassen würden, dann würde der nächste case ebenfalls ausgeführt werden, solange bis der nächste break kommt.
- Wenn mehrere cases mit den Ausdruck übereinstimmen, dann wird immer der erste case ausgeführt der mit den Ausdruck übereinstimmt.
- Wenn kein Case übereinstimmt, kann man ein default wert hinzufügen, der dann ausgeführt wird, wenn nicht übereinstimmt. Der ist aber nur optimal, wenn der nicht da ist, dann wird eben nichts ausgeführt

# Vorteil gegenüber if else 
Mit If else kann man sehr gut boolesche Werte überprüfen, also sozusagen komplexere Bedingungen.

- Switch case sind sehr praktische, wenn man ganz einfach nur 2 Dinge miteinander vergleichen will. Zum Beispiel ob A = B ist usw.
- Switches sind effizienter und schneller. Eine If Anweisungen mit 20 else braucht länger, als eine switch Anweisung mit 20 cases

# Mehrere Cases zu einer Anweisungen
Es kommt öfter vor das mehrere cases im Switch das gleiche ausführen. Hierzu kann man die einzelnen cases, die das gleiche ausführen verknüpfen, um redundanz zu vermeiden.
```js
const essen = "Pizza"

switch(essen){
	case "Nudeln":
	case "Pizza":
	case "Steak":
		console.log("Das mag ich")
		break;
	case "Fisch":
	case "Hummer":
	case "Kavier":
		console.log("Das mag ich nicht")
		break;
	default:
		console.log(`Ich kenne "${essen}" nicht! Was ist das?`)
		break;
}
```
Dies funktioniert, weil wir beispielsweise hinter den case "Nudeln" kein break haben, somit wird der nächste auch noch ausgeführt.
## References
1. 

## Quellen
1. 