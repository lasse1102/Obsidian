
--- 
Erstellt: 2025-11-21    12:21 
Tags: 
Link Up: [[TypeScript]]
Link Down:

--- 
TypeScript ist eine Erweiterung von JavaScript, welches uns das Typisieren von Daten ermöglicht. JavaScript ist eine dynamische Scriptsprache, welches einem ermöglicht Datentypen während des Programms noch zu ändern. Bei größeren Projekten kann dies aber oft zu Fehlern stoßen
TypeScript hingegen ermöglich es einem gar nicht erst bspw. Variablen, Parameter zu erstellen ohne festen Datentyp. Wir müssten immer ein Datentyp mitgeben um sicherzustellen, das bspw. in einer variable "Kontostand" ein Integer Wert und kein String Wert enthalten ist.
![[Pasted image 20251121133544.png]]

##### Beispiel JavaScript vs TypeScript Typisierung
Mit Type Annoations ermöglicht uns TypeScript das Angeben des Typs. Wenn dies Missachtet wird, dann wird bei der Entwicklung schon ein Fehler angezeigt und nicht erst, wenn das Programm ausgeführt wird.
![[Pasted image 20251121134425.png]]

---
### TypeScript strict Mode
Der TypeScript Strict Mode ist eine Einstellung in der tsconfig.json die TypeScript strengere Typeregeln aktiviert und dabei helfen:
- Fehler früh erkennen
- unsicheren Code zu verhindern
- besser vorhersehbaren, robusten Code zu schreiben

Wenn du in deiner `tsconfig.json` folgendes setzt:
```json
{
 "compilerOptions": { 
	 "strict": true 
} 
 
```
... aktiviert TypeScript **alle strengen Typprüfungen**
Das beinhaltet u.a.:
- nolmplicitAny
- strictNullChecks
- strictFunctionTypes
- strictBindCallAply
- strictPropertyInitialization
- nolmplicitThis

---
### Basis Typen
Wie in JavaScript gibt es die grundlegenden Datentypen, die du in TypeScript explizit zuweisen kannst.
- `string`: Text
- `number`: Zahlen (Ganz- und Fließkommazahlen)
- `boolean`: `true` oder `false`
- `any`: Schaltet die Typprüfung aus (sollte vermieden werden!)
- `unknown`: Sicherere Alternative zu `any` (man muss den Typ erst prüfen, bevor man damit arbeitet)

Zugewiesen werden sie so:
```TypeScript 
let Zahl: number;
let isVisible: boolean;
```

Wenn man direkt Werte zu einer Variable zuweist, erkennt TypeScript den Datentyp automatisch und muss ihn nicht explizit angeben
```TypeScript
let zahl = 42 //TypeScript erkennt: number
let isVisble = true // boolean
```

##### Besondere Datentypen
- `void` -> geben wir einer Funktion mit um zu sagen, dass sie nichts return soll. 
- `unknown` -> Mit `unknown` sagen wir, dass ein Wert **beliebigen Typs** sein kann (z. B. `string`, `number`, `boolean` usw.).  Solange der Typ **nicht eingegrenzt** wurde, können wir mit diesem Wert **nichts Typ-spezifisches machen**.  Das heißt: Wir können keine String- oder Number-Methoden aufrufen, da TypeScript nicht weiß, um welchen Typ es sich handelt.  Um den Wert zu verwenden, müssen wir ihn **zuerst prüfen** (z. B. mit `typeof`, `instanceof` oder Type Guards).
- `any` -> ist ähnlich wie `unknown`, also ein Wert kann jeden beliebigen Datentyp haben. Der unterschied ist, dass wir dennoch alle Methoden anwenden können, nicht so wie bei `unknown`

---
### Interfaces
Ein **Interface** beschreibt die "Form" eines Objekts. Es ist wie ein Vertrag, den ein Objekt oder eine Klasse erfüllen muss.
```TypeScript
interface Todo {
	description: string;
	status: string;
	assignee?: string;
}

const todo: Todo = {
	description: "TypScript",
	status: "open"
}
```
Hier können wir sehen wie wir das Objekt todo an einer Festen Struktur aufbauen, welches wir in einem Interface definieren und dann an dem Objekt als Type Annotation angeben.
>Um Werte Optimal zu machen können wir im Interface hinter dem Namen ein `?` setzten.


##### Union Type
Mit einem Union Type können wir einem Wert sagen das er verschiedene Datentypen annehmen kann z.B kann status ein `open`, `done` oder `discarded`sein. 
```TypeScript
interface Todo {
	description: string;
	status: 'open' | 'done' | 'discarded'; 
}
```
**Ja man kann auch einzelne Werte als Datentyp angeben und muss nicht zwingend string oder number angeben z.B.**

Um dies zu vereinfachen kann man das in einen eigenen Typen extrahieren, dies ist kein Interface mehr sondern ein eigener Type den wir dann woanders angeben können. 
Mehr dazu bei **Type Aliases**

---

### Type Aliases
Ein **Type Alias** ist, wie der Name sagt, ein Name für einen beliebigen Typ. Er ist weitaus flexibler als ein Interface, da er nicht auf Objekte beschränkt ist, so wie ein Interface.

Hier ein Beispiel um ein Union Type `Status` zu definieren, welchen wir an einem Interface mitgeben können
```TypeScript
type Status = 'open' | 'done' | 'discarded'; 

interface Todo {
	description: string;
	status: Status; 
}
```


>FAUSTREGEL: Interface definiert ein Objekt und Type definiert alles was kein Objekt ist, insbesondere häufig Union Types

---
### Generics

Generics erlauben es, **Typen als Platzhalter** zu definieren, die erst bei der Verwendung festgelegt werden. Sie erlauben uns Funktionen, Klassen oder Interfaces zu schreiben, welche mit verschiedenen Typen Funktioniert, ohne Typsicherheit zu verlieren.

Statt einen konkreten Type (`string`, `number`, `User`) fest zu verdrahten, sagst du:
> „Dieser Code funktioniert mit _jedem_ Typ – sag mir später, welcher.“

#### **Warum brauchen wir Generics**
>Kurzgesagt brauchen wir es damit Code flexible und typsicher ist.

Stell dir vor, du willst eine Funktion, die für jeden Typ funktioniert.
```TypeScript 
function idenftify(value: any){
	return value
}
```
Probleme:
❌ Keine Typprüfung
❌ Kein Autocomplete
❌ Fehler erst **zur Laufzeit**
❌ TypeScript verliert seinen Sinn

**Generics lösen genau dieses Problem**
```TypeScript
function identfy<T>(value: T): T {
	return value
}
```
✔ Einmal geschrieben  
✔ Für **alle Typen nutzbar**  
✔ Volle **Typprüfung & Autocomplete**

#### **Generics in Interfaces & Klassen**
```TypeScript
interface Todo<T> {
	description: string;
	status: string;
	data: T;
}

interface MetaData {
	assignee: string;
}

const todo: Todo<MetaData> = {
	description: "TypScript",
	status: "open",
	data: {
		assignee: 'goloroden'
	}
}
```

---

## References
1. 
