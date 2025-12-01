
--- 
Erstellt: 2025-09-15    14:02 
Tags: 
Link Up: [[React]]
Link Down:

--- 
# Was ist JSX 
- **Deklarative Syntax:** JSX ist eine Syntax, um zu beschreiben, wie UI-Komponenten aussehen und funktionieren.
- HTML-ähnlich: Es ist eine Erweiterung von JavaScript, die es ermöglicht, HTML-ähnliches Markup direkt in JavaScript- Code zu schreiben.
- **Komponenten-Rückgabe:** Komponenten müssen EINEN Block von JSX zurückgeben.
- **Konvertierung:** Jedes JSX-Element wird in einen `React.createElement` Funktionsaufruf umgewandelt.
- **Transpilierung:** JSX wird mit einem Transpiler wie Babel in normales JavaScript umgewandelt, damit es vom Browser verstanden wird.
- **Keine Pflicht:** Man könnte React auch ohne JSX verwenden, allerdings ist die Nutzung von JSX die gängige und empfohlene Methode.

### Deklarativ vs Imperativ
- **Deklarativ:** JSX ist deklarativ. Das bedeuted, du beschreibst, wie das Endresultat aussehen soll und nicht, wie man dorthin gelangt (wie es bei imperativen Code der Fall ist). Im Gegensatz zu manuellen DOM-Zugriff beschreibst du mit JSX, wie die UI auf Grundlage des aktuellen Datenzustands aussehen soll. React kümmert sich dann um die nötige Aktualisierung.
- **HTML-ähnlich, aber nicht HTML:** Obwohl es sehr ähnlich aussieht, ist es kein reines HTML. Du kannst JavaScript-Ausdrücke, CSS und sogar andere React-Komponenten direkt in das Markup einbetten.

---
# Allgemeine JSX-Regeln
- JSX ähnelt HTML, aber du kannst in den "JavaScript-Modus" wechseln, indem du geschweifte Klammern verwendest. Das ist nützlich für Text oder Attribute
- Du kannst **JavaScript-Ausdrücke** in die geschweiften Klammern setzen. Beispiele dafür sind Referenzvariablen, Arrays (`.map()`) und der ternäre Operator.
- **Anweisungen** (wie `if/else`, `for` oder `switch`) sind in JSX nicht erlaubt.
- JSX erzeugt einen **JavaScript-Ausdruck**, was bedeutet, dass `<p>Hallo</p>` dasselbe ist wie `React.createElement('p', null, 'Hallo')`.
- Du kannst **andere JSX-Elemente** in geschweifte Klammern setzen, um sie zu verschachteln.
- JSX kann **überall in einer Komponente** verwendet werden: innerhalb von `if`-Anweisungen, bei der Zuweisung an Variablen oder wenn du es an Funktionen übergibst.
- Ein JSX-Block darf nur **ein einziges Wurzelelement** haben. Das bedeutet, dass alle anderen Elemente in einem übergeordneten Element (wie einem `<div>`) verschachtelt sein müssen.

# Unterschiede zwischen JSX und HTML
- **`className`** wird anstelle von `class` verwendet.
- **`htmlFor`** wird anstelle von `for` verwendet.
- **Jeder Tag muss geschlossen werden**, zum Beispiel `<img />` oder `<br />`.
- - Alle **Event-Handler und Eigenschaften** werden in der **camelCase**-Schreibweise geschrieben, wie zum Beispiel `onClick` oder `onMouseOver`.
- Eine Ausnahme bilden die Attribute **`aria-*` und `data-*`**, die mit Bindestrichen geschrieben werden, so wie in HTML.
- **CSS-Inline-Stile** werden als JavaScript-Objekt geschrieben, zum Beispiel: `{ { style } }`.
- Die **Namen von CSS-Eigenschaften** werden ebenfalls in der **camelCase**-Schreibweise geschrieben.
- **Kommentare** müssen in geschweifte Klammern `{}` eingeschlossen werden, da sie als JavaScript interpretiert werden.

## References
1. [Zur Verdeutlichung von JSX](https://react.dev/learn/writing-markup-with-jsx)
