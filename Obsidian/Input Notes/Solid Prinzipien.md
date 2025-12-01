
--- 
Erstellt: 2025-03-11    11:18 
Tags: #Programming/PHP/cleanCode  
Link Up: [[PHP]]
Link Down:

--- 
# Was sind die SOLID-Prinzipien
Die SOLID-Prinzipien sind eine Sammlung von fünf Designprinzipien, die darauf abzielen, Software flexible, wartbar und erweiterbar zu gestalten. Diese Prinzipien sind besonders in Objektorientierten Programmiersprachen wie PHP von Bedeutung. Sie helfen dabei gut strukturierte und skalierbare Software zu entwickeln.

#### S - Single Responsibility Principle (SRP)
==„Es sollte nie mehr als einen Grund dafür geben, eine Klasse zu ändern.“==

In erster Linie beschreibt das Single-Responsibility-Prinzip, dass jede Klasse nur eine fest definierte Aufgabe haben soll. Diese Aufgabe soll, soweit es möglich ist und es Sinn ergibt, abstrahiert sein.

Im Beispiel haben wir eine Klasse die in erster Linie zum Speichern von Daten des Users dienen. Mit der Aufgabe, Daten zu speichern, wäre diese Klasse an der Stelle schon ausgelastet und hätte **eine direkte Verantwortlichkeit**: den User betreffende Daten durch die Software transportieren.
Außerdem wird in der Klasse noch ein Error Logger mit hinzugefügt, der dafür da sein könnte, wenn ein User importiert werden mus, beispielsweise aus einer API. Wenn der Logger im User selbst gespeichert ist, könnte man bei eine fehlerhaften Import jederzeit darauf zugreifen. Dies verstößt aber gegen das Single Responsibility Principle, denn jetzt hat die Klasse zwei Aufgaben (Transportieren von User Daten und das Loggen von Errors)

In diesem Fall müsste das ErrorLogInterface aus dem User entfernt werden und in eine eigene Klasse überführt werden.
```PHP
class User {
  public $firstName;
  public $lastName;
  public $errorLog;
 
  public function __construct(ErrrorLogInterface $errorLog)
  {
    $this->errorLog = $errorLog;
  } 
 
  public function setFirstName(string $firstName) 
  { 
    $this->firstName = $firstName; 
  }
 
  public function getFirstName() : string
  {
    $this->firstName = $firstName;
  }
 
  public function setLastName(string $lastName)
  {
    $this->lastName = $lastName;
  }
  public function getLastName() : string
  {
    $this->lastName = $lastName;
  }
  public function setErrorInLog(string $message)
  {
    $this->errorLog->setError($message);
  }
}
```

# Open Closed Prinzip
==„Module sollten sowohl offen (für Erweiterungen) als auch geschlossen (für Modifikationen) sein.“==
Das Open Closed Prinzip(OCP) beschreibt, dass Änderungen an Klassen oder Funktionen das Verhalten dieser nicht ändern dürfen. Die Klasse Calculator soll Rechenaufgaben, wie beispielsweise eine leichte Multiplikation übernehmen

Sie multipliziert 2 Integer und gibt das Produkt ebenfalls als Integer aus. Anschließend wird das Ergebnis als Integer zurückgegeben
```PHP
class Calculator { 
  public function multiply(int $firstNumber, int $secondNumber) : int
  {
    $solution = $firstNumber * $secondNumber; 
    return $solution;
  }
}
```
Hier dran ist auch nichts falsch, die Klasse wurde geschrieben und funktioniert. Sie wurde zum Beispiel in einer Klasse eingebaut, in der es darum geht, den Flächeninhalt eines Quadrates zu berechnen, das klappt auch alles.
```PHP
Class Square {
  public function calculateArea(int $length) : int
  {
    return $this->calculator->multiply($length,$length);
  }
}
```

**Problem**
Man stelle sich vor das irgendwann eine neue Anforderung  aufkommt, dass der Flächeninhalt von Quadraten auf einen geraden Wert nicht mehr ausreichend ist. Der Kunde möchte gerne Nachkommastellen. Man müsste die multiply anpassen und den Datentyp float einbauen. 
Das Problem und damit damit die Verletzung des Open-Closed-Prinzips wäre jedoch, dass wir damit das **Verhalten der Klasse und der Funktion ändern**. Derzeit gibt die Funktion ein Integer zurück, welches in der Software eventuell an vielen anderen Stellen weiterhin so ist.

# Liskovsches Substitutionsprinzip
Das Liskov Substitution Principle besagt, dass eine Unterklasse die Oberklasse ersetzen können muss, ohne das Verhalten des Programms zu verändern oder Fehler zu verursachen.
- Eine Unterklasse übernimmt alle Eigenschaften und Methoden. Sie muss zwar nicht alle Methoden verwenden aber dennoch sollten alle Methoden sinnvoll in der Unterklasse verwendet werden können.
- Eine Unterklasse darf keine Methoden verändern oder unbrauchbar machen, sodass sie sich anders verhält als erwartet
```PHP
class Bird {
    public function fly() {
        // Vögel können fliegen
    }
}

class Sparrow extends Bird {
    public function fly() {
        // Sperling fliegt
    }
}

class Ostrich extends Bird {
    public function fly() {
        throw new Exception("Strauße können nicht fliegen.");
    }
}
```
Im obigen Beispiel verletzt der `Ostrich`-Klasse das Liskovsche Substitutionsprinzip, weil sie die Methode `fly()` anders implementiert, was das Verhalten des Programms in der `Bird`-Klasse beeinträchtigen könnte. Stattdessen sollte eine `FlyableBird`-Klasse für flugfähige Vögel eingeführt werden.


## References
1. 



