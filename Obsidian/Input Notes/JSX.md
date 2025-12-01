
--- 
Erstellt: 2025-09-04    07:57 
Tags: #Programming/JavaScript/React
Link Up: [[JavaScript]]
Link Down:

--- 
### Was ist JSX
JSX steht für JavaScript XML und ist eine Syntaxerweiterung für JavaScript, die es Entwicklern ermöglicht, HTML-ähnlichen Code direkt in JavaScript zu schreiben. Es wurde von Facebook entwickelt und wird hauptsächlich in der JavaScript-Bibliothek React verwendet, um Benutzeroberflächen zu beschreiben.

## SX: Die JavaScript-Erweiterung

JSX steht für **JavaScript XML**. Es ist keine eigene Sprache, sondern eine **syntaktische Zucker-Erweiterung** für JavaScript. JSX sieht zwar wie HTML aus, wird aber direkt in JavaScript-Code geschrieben. Die Browser können JSX nicht direkt verstehen. Vor dem Rendern wird der JSX-Code von einem Compiler wie **Babel** in reguläre JavaScript-Funktionsaufrufe umgewandelt. Beispielsweise wird das JSX-Fragment `<h1>Hello, World!</h1>` in `React.createElement('h1', null, 'Hello, World!')` übersetzt.

**Vorteile von JSX:**
- **Lesbarkeit:** Es macht den Code verständlicher, da die Struktur der UI direkt im JavaScript-Code sichtbar ist.
- **Ausdrucksstärke:** Da JSX JavaScript ist, kann man direkt JavaScript-Variablen, Ausdrücke und Logik in den Code einbetten, indem man geschweifte Klammern (`{}`) verwendet.
- **Komponentenbasiertes Design:** Es unterstützt die Erstellung wiederverwendbarer UI-Komponenten, was die Entwicklung großer Anwendungen erleichtert.

![[Pasted image 20250904080117.png]]
## References
1. 
