
--- 
Erstellt: 2024-03-22    14:11 
Tags: #Programming/DesignPattern 
Link Up: [[Programming]]
Link Down:

--- 
# Was ist Dependency Injection
Dependency Injection - zu deutsch etwa „Abhängigkeits-Injektion“ - beschreibt ein Verfahren, die von einer Klasse benötigten Objekte (Abhängigkeiten) von außen in die Klasse zu injizieren. Dies ist der Neigung vieler Anfänger entgegengesetzt, Objekte oftmals direkt in der Klasse zu instanziieren (erstellen).

Beispiel direkter Instanzierung (**keine** Dependency Injection):
```PHP
class MyController {

    private $logger;

    public function __contruct() {
        $this->logger = new Logger();
    }

    public function myAction() {
        $this->logger->log("someone called myAction");
    }
}
```
Die Klasse MyController enthält einen Konstruktor und eine Methode. Beim Aufrufen der Methoden soll eine Funktion der Klasse Logger verwendet werden. Der hierfür verantwortliche Logger mit der Klasse Logger wird im Konstruktor instanziiert. Somit hängt MyController von der Klasse Logger mit allen Ihren potenziellen Eigenheiten ab.
Dies ist u. a. aus folgenden Gründen nicht erstrebenswert:
- Verändert sich beispielsweise die Instanziierung der Klasse _Logger_ (z. B. weil Argumente benötigt werden), muss die Klasse _MyController_ ebenfalls angepasst werden
- Verändern sich die Methoden der Klasse _Logger_, müssen auch diese in _MyController_ angepasst werden
- Soll das _Logger_-Objekt über Methoden konfiguriert werden, müsste auch dies direkt in _MyController_ eingebaut werden
Des weiteren ist es strenggenommen nicht die Aufgabe von MyController, sich um die Erstellung anderer Klasse zu kümmern.

## Konstruktor Injection
Bei der Constructor Injection wird die Abhängigkeit als Konstruktorargument übergeben.
```PHP
class MyController {

    private $logger;

    public function __construct(Logger $logger) {
        $this->logger = $logger;
    }

    public function myAction() {
        $this->logger->log("someone called myAction");
    }
}
```
An der Stelle, wo _MyController_ instanziiert wird, muss nun eine Instanz der Klasse _Logger_
übergeben werden:
```PHP
$logger = new Logger();

$myController = new MyController($logger);
```
Vorteil ist hier jedoch, dass die Instanziierungslogik für die Klasse _Logger_ nicht mehr in _MyController_ benötigt wird. Wir haben _MyController_ also bereits schlanker gemacht.

# Vor und Nachteile von DI
- Die Klasse MyController muss nichts über die Instanziierung von Logger-Objekten wissen
- Wir könnten je nach Anwendungsfall Objekte der Logger-Klasse unterschiedlich konfigurieren, bevor sie via Dependency Injection in MyController eingefügt werden
- Hätten wir mehrere Controller Objekte, könnten wir stets die gleiche Logger-Instanz übergeben(**bessere Performance**)
- Das Testen der MyController Klasse würde nun die Verwendung von speziellen Mock-Objekten für den Logger erlaubt


## References
1. [[Design Pattern]]

## Quellen
1. https://de.wikibooks.org/wiki/Websiteentwicklung:_PHP:_Dependency_Injection