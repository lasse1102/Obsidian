
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


#### Interfaces
Nehmen wir mal als Beispiel wir erstellen ein Objekt und wollen dieses auch Typisieren also jeden einzelnen Wert. Das geht und würde so aussehen:
```TypeScript
let kunde1: {name: string, guthaben: number} =
{
	name: "Max",
	guthaben: 10000
};
```
Nachteil:
- Das Objekt ist dann fest auf diese Struktur fixiert
- Wiederverwendbarkeit und Erweiterbarkeit sind eingeschränkt

**Interfaces**
Hier kommen Interfaces ins Spiel. Man kann sie einmal definieren  und sie dann wiederverwenden. Das ist besonders nützlich wenn man viele Objekte oder Klassen hat, die die gleiche Struktur haben

```TypeScript
interface iKunde {
	name: string,
	guthaben: number
}

let kunde1: iKunde = {
	name: "Max",
	"guthaben": 10000
}

let kunden: iKunde[] = [];
kunden.push(kunde1)
```

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

## References
1. 
