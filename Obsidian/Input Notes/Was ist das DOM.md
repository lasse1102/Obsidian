
--- 
Erstellt: 2025-06-03    10:51 
Tags: #Programming/JavaScript/DOM
Link Up: [[JavaScript]] 
Link Down:

--- 
# Was ist das DOM
Das Document Object Model ist eine Programmierschnittstelle (API) für Webdokumente, wie z.B. HTML- oder XML- Dokumente. **Es stellt die Seite so dar, dass Programme ihre Struktur, ihren Stil und ihren Inhalt ändern können.**

Stell dir eine Website vor. Wenn ein Webbrowser ein HTML-Dokument analysiert, baut er einen DOM-Baum (interne Repräsentation) auf und verwendet diesen dann zur Darstellung des Dokuments. Dies ist so vorzustellen, dass es eine logische, baumartige Struktur im Arbeitsspeicher erstellt. Jedes HTML-Element, Attribut und jeder Textknoten wird zu einem "Knoten" in diesem Baum

Das ganze kann man sich so Bildlich vorstellen:
![[Pasted image 20250603110917.png]]
Diese Baumstruktur ist die "interne Repräsentation". Sie ist **kein visuelles Abbild** der Seite, sondern eine **objektbasierte Datenstruktur**. Jeder Knoten in diesem Baum ist ein Objekt, das Eigenschaften (z.B. den Tag-Namen, Attribute) und Methoden (Funktionen, die man darauf anwenden kann) hat.

Wenn der Browser den HTML-Code "liest" und eine "interne Repräsentation" erstellt, bedeutet das, er baut diese logische, objektbasierte Baumstruktur im Arbeitsspeicher auf.

### Kernpunkte des DOM
- Programmierschnittstelle (API): Das DOM ist keine Programmiersprache selbst, sondern eine Schnittstelle, die es Programmiersprachen (insbesondere JavaScript) ermöglicht, mit dem Dokument zu interagieren. Es bietet Methoden und Eigenschaften, um:
	- **Elemente zu finden:** Z.B. `document.getElementById()`, `document.querySelector()`.
	- **Inhalt zu ändern:** Z.B. `element.textContent = "Neuer Text"`.
	- **Stil zu ändern:** Z.B. `element.style.color = "red"`.
	- **Struktur zu manipulieren:** Z.B. `document.createElement()`,
		`parentNode.appendChild()`, `parentNode.removeChild()`.
	- **Auf Ereignisse zu reagieren:** Z.B. Klicks, Tastatureingaben.

- **Dynamische Webseiten:** Das DOM ist entscheidend für dynamische Webseiten. Ohne das DOM könnte JavaScript nicht auf den Inhalt oder die Struktur einer Webseite zugreifen und diese ändern. Wenn du auf einer Webseite eine Schaltfläche klickst und sich etwas ändert, wird das über das DOM gesteuert.
## References
1. 
