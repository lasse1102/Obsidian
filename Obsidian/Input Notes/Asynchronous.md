
--- 
Erstellt: 2026-01-07    07:40 
Tags: 
Link Up: [[TypeScript]]
Link Down:

--- 
### Higher Order Functions vs Callbacks
In JavaScript ist eine higher order functions eine Funktion, welche eine andere Funktion akzeptiert oder zurückgibt oder auch beides.
Eine Callback Funktion ist eine Funktion, welche an eine andere Funktion übergeben wird als Parameter.
```TypeScript
function logString(str: string): void {
	console.log(str);
}

setTimeout(logString, 1000)
```
- `logString` ist die Callback Funktion 
- `setTimeout` ist die higher order function

```javascript
const people = [
  { firstName: "Jack", year: 1988 },
  { name: "Kait", year: 1986 },
  { name: "Irv", year: 1970 },
  { name: "Lux", year: 2015 },
];

people.forEach(function (person) {
  console.log(person);
});
```
In diesem Fall ist `forEach` die Higher Order Function, da sie eine Funktion als Argument akzeptiert, welche bei jedem Aufruf von der Iteration ausgeführt wird.

- [[Schreibweise von Callback-Functions]]

---
### Asynchrone Funktionen
Eine Asynchrone Funktion führt den Code nicht sofort aus sondern später, ohne den restlichen Code zu blockieren.

Asynchrone Funktion:
```TypeScript
console.log("Start")

setTimeout(() => {
	console.log("Hello World")
}, 2000)

console.log("Ende")

//Ausgabe
//1.Start
//2.Ende
//3.Hello World
```
- `setTimeout` blockiert den Code nicht.  
- Der Code läuft weiter und die Callback-Funktion wird erst nach Ablauf der Zeit asynchron ausgeführt, deshalb wird `Ende` vorher ausgegeben.

**Häufige Einsatzfälle**
- API Calls
- Datenbankzugriffe
- Dateizugriffe
- Timer / Verzögerung
- Event Handling
- Parallele Aufgaben

---
### Promises

Ein **Promise** ist ein Objekt, das einen Wert repräsentiert, der **jetzt, später oder nie** verfügbar sein wird.  
Es kapselt asynchrone Vorgänge und erleichtert die **strukturierte Verarbeitung** sowie **Fehlerbehandlung**.

##### Zustände eines Promise
- **Pending** → noch nicht abgeschlossen  
- **Fulfilled** → erfolgreich abgeschlossen (resolve)  
- **Rejected** → fehlgeschlagen (reject)

##### Nutzen
- Verhindert **Callback-Hell**  
- Bessere **Lesbarkeit** des Codes  
- **Fehlerbehandlung** über `.catch()` oder `try/catch` (bei async/await)  
- Kombinierbar (`Promise.all`, `Promise.race`)  
- Einheitliche Handhabung von asynchronen Operationen

##### Syntax (Grundform)
```ts
const promise = new Promise<string>((resolve, reject) => {
    // Asynchrone Aufgabe
    if (erfolg) resolve("Ergebnis");
    else reject("Fehler");
});

```

##### Typische Einsatzgebiete in TypeScript
- API / HTTP-Anfragen (`fetch`) 
- Datenbankzugriffe
- Dateisystem (Node.js)
- Timer / verzögerte Aktionen (`setTimeout`)
- Event-Handling (Callbacks können in Promises umgewandelt werden)

##### Merksätze
- **Promise = „Ich verspreche dir später ein Ergebnis.“**
- **resolve** → Versprechen erfüllt
- **reject** → Versprechen gebrochen
- Promises machen asynchronen Code **übersichtlich und kombinierbar**
- Modernes async/await basiert auf Promises

## References
1. 
