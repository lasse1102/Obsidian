
--- 
Erstellt: 2024-05-17    13:56 
Tags: 
Link Up: [[JavaScript]]
Link Down:

--- 
Template Strings, auch bekannt als Template Literals, sind in JavaScript eine Möglichkeit, Zeichenketten zu definieren, die es erlauben, Ausdrücke einzubetten und Mehrzeiligkeit zu unterstützen. Sie werden mit Backticks anstelle von doppelten ("") Anführungszeichen definiert. 
Hauptmerkmale:
- **Mehrzeilige Strings**: Mit Template Strings können Sie Zeichenketten über mehrere Zeilen erstrecken, ohne explizite Zeilenumbrüche (\n) einfügen zu müssen.
```js
let mehrzeiliger_template_string = `Hallo ${name}!  
Du bist ${alter} Jahre alt.
Wie geht es dir?`;  
console.log(mehrzeiliger_template_string);
// Ausgabe
//Hallo Ruben Winkler!
//Du bist 24 Jahre alt.
//Wie geht es dir?
```
- **String-Interpolation**: Sie können Variablen und Ausdrücke direkt in die Zeichenkette einbetten, indem Sie sie in `${}` setzen. Zum Beispiel:
```javascript
let name = "Welt";
let greeting = `Hallo ${name}!`;
console.log(greeting); // Ausgabe: Hallo Welt!
```

Die Verwendung von `${}` innerhalb der Backticks ermöglicht es, dass der Wert der Variable `name` in den String eingefügt wird, was zu einer nahtlosen und lesbaren Ausgabe führt.


## References
1. 

## Quellen
1. 