
--- 
Erstellt: 2024-05-22    10:26 
Tags: 
Link Up: [[JavaScript]]
Link Down:

--- 
# Definition
Anonyme Funktionen sind Funktionen ohne Namen, die sofort ausgeführt werden. Wenn Funktionen sehr einfach sind, verbessern eine anonyme Funktion die Lesbarkeit. Anonyme Funktionen halten den Code besser zusammen und erzeugen einen abgeschirmten Gültigkeitsbereich, ihren Scope

Der Aufruf erfolgt über die den Namen plus die Klammern. Anonyme Funktionen werden auch als "Funktionsausdrücke" bezeichnet

# Schreibweise
```javascript
let show = function(){
console.log("Anonyme Funktion");
};
show();
```
# Verwendung von Anonymen Funktionen
Anonyme Funktionen werden in verschiedenen Szenariien verwendet, vor allem wenn eine Funktion nur einmal verwendet wird oder wenn eine Funktion keinen eigenen Namen benötigt
Hier sind einige Anwendungsfälle:
- Als Argumente: Anonyme Funktionen werden häufig als Argumente an andere Funktionen übergeben, wie setTimeout:
```js
	setTimeout(function(){
		console.log("Ausführen nach 1 Sekunde");
	}, 1000);
```
- Wenn Code direkt ausgeführt werden soll, der keinen weiteren Gebrauch findet:
```js
(function(){
console.log("Dies wird sofort ausgeführt");
})();
```
- Event Listener: Anonyme Funktionen werden oft in Event Listener verwendet, um eine Aktion auszuführen, wenn ein bestimmtes Ereignis eintritt
```js
document.getElemntById("meinButton").addEventListener("click",
													  function(){
	console.log("Button wurde geklickt")
	});
```


# Arrow Funktion
Arrow-Funktionen: Seit ES6 werden anonyme Funktionen auch in Form von Arrow Funktionen für eine kürzere und klarer Syntax verwendet, besonders wenn "this" an den Kontext gebunden bleiben soll
```js
	let liste = [1,,2,3];
	let quadrate = liste.map((zahl) => zahl * zahl);
```


# Unterschiede
- **Benannte Funktionen**(Normale Funktion):
    - Gut für komplexere Funktionen, die mehrfach aufgerufen werden sollen.
    - Bieten bessere Lesbarkeit und Debugging-Möglichkeiten, da der Funktionsname in Fehlerprotokollen angezeigt wird.
- **Anonyme Funktionen**:
    - Häufig verwendet für einmalige Funktionen oder Callbacks.
    - Können direkt als Argumente an andere Funktionen übergeben werden.
- **Arrow-Funktionen**:
    - Kompaktere Syntax, ideal für einfache Funktionen und Inline-Callbacks.
    - Binden `this` nicht neu, was besonders nützlich in Klassenmethoden und bei der Arbeit mit Methoden wie `.map()`, `.filter()`, etc. ist.

## References
1. 

## Quellen
1. 