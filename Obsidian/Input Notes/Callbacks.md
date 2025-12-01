
--- 
Erstellt: 2025-06-02    07:30 
Tags: #Programming/JavaScript 
Link Up: [[JavaScript]] 
Link Down:

--- 
# Was sind Callbacks
Ein Callback ist im Grunde eine Funktion, die als Argument an eine andere Funktion übergeben wird. Diese "übergebene" Funktion wird dann zu einem späteren Zeitpunkt ausgeführt, oft nachdem eine bestimmte Aufgabe abgeschlossen wurde oder ein Ereignis eingetreten ist.

Der Name "Callback" kommt daher, dass die Funktion "zurückgerufen" wird, sobald etwas passiert ist

#### Warum braucht man Callbacks in JavaScript
JavaScript, und besonders Node.js, ist **nicht-blockierend und asynchron**. Das bedeuetet, dass der Code nicht Zeile für Zeile auf die Fertigstellung einer Operation waret, bevor er mit der nächsten Zeile fortfährt. Stattdessen wird eine Operation (z.B. das Lesen einer Datei, eine Datenbankabfrage) gestartet, und der Rest des Codes wird weiter ausgeführt.

Wenn die Operation abgeschlossen ist, soll das Ergebnis verarbeitet werden. Hier kommen Callbacks ins Spiel: Sie ermöglichen es uns, Code auszuführen, nachdem eine asynchrone Operation beendet ist, ohne den Hauptausführungspfad zu blockieren.

#### **Beispiel:**



#### **Beispiel mit anonymen Funktionen:**

Typisches Beispiele sind hier eventListener, die in JavaScript häufig verwendet werden, um auf bestimmte Interaktionen zu warten.
![[Pasted image 20250602075634.png]]
**"click"**: 
- dies ist der typ des Events auf den reagiert wird wenn der Benutzer auf dem spieltagButton drückt.
**"() => { ... }"** : 
- Dies ist die **Callback-Funktion**! Genauer gesagt ist es eine anonyme Arrow Funktion. Diese Funktion wird _nicht sofort_ ausgeführt, wenn `addEventListener` aufgerufen wird. Stattdessen wird sie an den Browser "übergeben" und der Browser "merkt" sich diese Funktion. Sobald das spezifizierte Event (`'click'`) auf dem `spieltagoButton` auftritt, wird der Browser diese Funktion "zurückrufen" (ausführen).
## References
1. 
