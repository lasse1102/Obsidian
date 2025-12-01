
--- 
Erstellt: 2024-03-22    14:12 
Tags: #inProcess #PHP 
Link Up: [[PHP]]
Link Down:

--- 
# Definition
Lazy Initialization bedeutet, dass ein Objekt erste dann erstellt wird oder geladen wird, **wenn sei wirklich gebraucht wird** - also **nicht sofort beim Start** sondern erst auf Nachfrage.

Das spart Speicher, Rechenzeit und manchmal sogar Netzwerk oder Festplattenzugriffe, weil vielleicht nie alles gebraucht wird.

# Was macht das Lazy Initialization Pattern
- Bei der Lazy Initialization wird die Erstellung eines Objekts so lange wie möglich hinausgezögert
- Statt ein Objekt sofort zu erstellen, wird es erst dann erzeugt, wenn es **wirklich benötigt wird**
- Ein häufiges Beispiel ist die späte Erstellung einer Datenbankverbindung, die nur dann erfolgt, wenn tatsächlich Daten aus der Database abgerufen werden müssen
## References
1. [[Design Pattern]]

## Quellen
1. https://stackoverflow.com/questions/978759/what-is-lazy-initialization-and-why-is-it-useful