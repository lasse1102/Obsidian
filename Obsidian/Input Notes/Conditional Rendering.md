
--- 
Erstellt: 2025-10-10    09:15 
Tags: 
Link Up: [[React Grundlagen]]
Link Down:

--- 
# Was genau ist Conditional Rendering
Conditional Rendering in React ist der Prozess, bei dem du unterschiedliche Elemente oder Komponenten abhängig von einen bestimmten Zustand rendern kannst. Im Grunde bedeutet es, dass du festlegst, was auf dem Bildschirm angezeigt wird, basierend darauf, ob eine bestimmte Bedingung wahr (true) oder falsch (false) ist.

## Häufige Anwendungsfälle
Hier sind einige gängige Szenarien, in denen Conditional Rendering zum Einsatz kommt:
- **Anzeigen/Ausblenden von Elementen:** Eine Warnmeldung anzeigen, wenn ein Formular ungültige Daten enthält.
- **Benutzerauthentifizierung:** Einen "Anmelden"-Button für nicht eingeloggte Nutzer und ein "Abmelden"-Button für eingeloggte Nutzer rendern.
- **Ladezustände:** Eine Ladeanzeige anzeigen, während Daten von einer API abgerufen werden, und die eigentlichen Daten, sobald sie verfügbar sind.
- **Rechteverwaltung:** Bestimmte UI-Elemente nur für Administratoren anzeigen.

## Methoden des Conditional Rendering
In React gibt es verschiedene Möglichkeiten, dies umzusetzen. Die gebräuchlichsten sind:
### 1. `if...else` (Innerhalb der Funktion)
Du kannst normale JavaScript `if/else`-Anweisungen **innerhalb** deiner Komponentenfunktion verwenden, aber **außerhalb** des zurückgegebenen JSX, weil in JSX kann man keine if else Blöcke machen.
![[Pasted image 20251010092150.png]]

### 2. Ternärer Operator (`? :`)
Dies ist die gängigste und prägnanteste Methode, um **innerhalb von JSX** bedingt zu rendern.
![[Pasted image 20251010092208.png]]

### 3. Logischer `&&` Operator (Short-Circuit Evaluation)
Wenn du nur dann etwas rendern möchtest, wenn die Bedingung **wahr** ist (d. h. du hast keinen `else`-Fall), kannst du den logischen AND-Operator (`&&`) verwenden.
Wenn die Bedingung links von `&&` **true** ist, wird der Ausdruck rechts gerendert. Wenn die Bedingung **false** ist, stoppt React die Auswertung und rendert nichts.
![[Pasted image 20251010092223.png]]

























## References
1. 
