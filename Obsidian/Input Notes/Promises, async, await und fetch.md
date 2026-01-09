
--- 
Erstellt: 2026-01-08    11:25 
Tags: 
Link Up: [[TypeScript]] [[JavaScript]] [[Asynchronous]] 
Link Down:

--- 

# Promises, async/await & fetch (TypeScript / JavaScript)

## 1. Grundproblem: Asynchronität in JavaScript

JavaScript ist **single-threaded**. Dinge wie:
- API-Requests
- Netzwerkzugriffe
- Dateien lesen
- Timer

können **nicht sofort** abgeschlossen werden.

➡️ Lösung: **asynchroner Code**, damit der Thread nicht blockiert.

---
## 2. Promise – Grundidee
Ein **Promise** ist ein Platzhalter für einen Wert, der **erst in der Zukunft verfügbar ist**.

Ein Promise kann drei Zustände haben:
- `pending` – läuft noch
- `fulfilled` – erfolgreich abgeschlossen
- `rejected` – fehlgeschlagen

Typisches Beispiel:
```ts
Promise<User>
```

➡️ Bedeutet: _Irgendwann bekomme ich einen `User`._

---
## 3. Warum API-Requests Promises sind

Ein API-Request
- geht übers Netzwerk
- dauert unterschiedlich lang
- kann fehlschlagen

➡️ Deshalb **immer asynchron**  
➡️ Deshalb **immer Promise**

Weitere Beispiele bei denen man ein Promise verwendet:
- Datenbankzugriffe
- Dateisystem (Node.js)
- Timer / verzögerte Aktionen (`setTimeout`)
- Event-Handling (Callbacks können in Promises umgewandelt werden)

---
## 4. fetch – was ist das?

`fetch` ist eine eingebaute Web-/Node-API für HTTP-Requests:
- GET, POST, PUT, DELETE
- Abrufen von Daten aus APIs

```ts
fetch(url): Promise<Response>
```

Wichtig:
- `fetch` startet den HTTP-Request
- gibt **sofort** ein Promise zurück
- blockiert **nicht** den Thread

---
## 5. Wichtige Erkenntnis: Zwei asynchrone Schritte

```text
fetch()  ──▶ Response
              |
              └─ response.json() ──▶ Daten (z. B. User)
```

### Schritt 1: `fetch`
- Server antwortet
- Statuscode + Header da
- Body **noch nicht gelesen**

### Schritt 2: `response.json()`
- liest den Response-Body
- parst JSON
- ebenfalls **asynchron**

➡️ Deshalb **zwei Promises**  
➡️ Deshalb **zwei await**

---
## 6. Beispiel: fetch mit async/await

```ts
type User = {
  id: number;
  name: string;
  email: string;
};

async function fetchUser(userId: number): Promise<User> {
  const response = await fetch(`https://api.example.com/users/${userId}`);

  if (!response.ok) {
    throw new Error("User konnte nicht geladen werden");
  }

  const user: User = await response.json();
  return user;
}
```

---

## 7. async / await – was passiert wirklich?

### async
- macht eine Funktion **automatisch Promise-basiert**
- erlaubt die Nutzung von `await`
- Rückgabewert wird automatisch in ein Promise verpackt

```ts
async function f() {
  return 5;
}
// => Promise<number>
```

---

### await
- wartet auf ein Promise
- **pausiert nur die aktuelle Funktion**
- blockiert **nicht** den Thread
- der Event Loop läuft weiter

Gedanklich:
```ts
console.log("A");
await something;
console.log("B");
```

➡️ „A“ läuft  
➡️ Funktion pausiert  
➡️ Promise erfüllt  
➡️ Funktion läuft bei „B“ weiter

---

## 8. await vs .then()

### Mit .then()
```ts
fetchUser(1)
  .then(user => console.log(user.name))
  .catch(err => console.error(err));
```

### Mit await
```ts
try {
  const user = await fetchUser(1);
  console.log(user.name);
} catch (err) {
  console.error(err);
}
```

### Wichtige Erkenntnis
> **await ist syntaktischer Zucker für .then()**

Technisch identisch – syntaktisch unterschiedlich.

---

## 9. Promise.all – mehrere Promises parallel ausführen

`Promise.all` ist nützlich, wenn du **mehrere asynchrone Aufgaben gleichzeitig** starten willst und **warten möchtest, bis alle abgeschlossen sind**.

### Beispiel:
```TypeScript
async function fetchMultipleUsers(userIds: number[]): Promise<User[]> {
	const userPromises = userIds.map(id => fetchUser(id));

	// Alle Promises parallel starten und warten, bis alle erfüllt sind
	const users = await Promise.all(userPromises);
	return users;

}

// Nutzung
(async () => {
	try {
		const users = await fetchMultipleUsers([1, 2, 3]);
		console.log(users);
    }catch (error) {
	console.error(error);
}
})();
```
### Vorteile von Promise.all:
- **Parallel statt seriell**: alle Requests laufen gleichzeitig
- **Schneller** als nacheinander `await` in einer Schleife
- **Fehlerbehandlung zentral**: Promise.all wird abgelehnt, sobald ein Promise fehlschlägt


---
## 9. Warum await meistens besser ist
- bessere Lesbarkeit
- linearer Codefluss
- saubere Fehlerbehandlung mit `try/catch`
- besser debugbar
- Standard in modernen Codebases

➡️ **Best Practice:** `async / await`

---

## 10. Wann .then() trotzdem okay ist
- sehr kurze One-Liner
- kein eigener async-Kontext
- einfache Reaktionen

```ts
fetchUser(1).then(user => console.log(user.name));
```

---
## 11. Fehlerbehandlung
### Mit await
```ts
try {
  await fetchUser(1);
} catch (error) {
  // fängt ALLE Promise-Fehler
}
```
- `throw` → Promise rejected
- landet im `catch`

---

## 12. Wichtige Merksätze 🧠
- Ein Promise bedeutet **nicht**, dass alles fertig ist 
	- Es bedeutet: _Dieser Schritt ist später fertig_
- `fetch` holt die Antwort
- `response.json()` holt die Daten
- `await` blockiert **nicht** den Thread  
	- nur die eigene async-Funktion

---
## 13. Zusammenfassung (Kurzfassung)
- Promises sind die Basis für Asynchronität
- API-Requests sind immer asynchron
- `fetch` → Promise
- `response.json()` → Promise
- `async / await` = lesbare Promise-Syntax
- `.then()` ist korrekt, aber meist unterlegen
➡️ **Standard: await**  
➡️ **Ausnahme: then**


## References
1. 
