
--- 
Erstellt: 2024-12-16    07:28 
Tags: #Programming/PHP/Datenstrukturen 
Link Up: [[PHP]]
Link Down:

--- 
### Einführung in Datenobjekte in PHP
In PHP sind Datenobjekte in der Regel Instanzen von Klassen, die dazu dienen, strukturierte Daten zu speichern und zu verwalten

#### Was ist ein Datenobjekt?
Ein Datenobjekt ist eine einfache Klasse, die in der Regel Eigenschaften (Properties) enthält. Es enthält die Daten für die Geschäftslogik und wird oft genutzt, um Daten zwischen verschiedenen Teilen in der Anwendungen zu transportieren und abzurufen.

##### Beispiel einer Klasse
```PHP
readonly class Draw  
{  
  
    /**  
     * @param string $id  
     * @param string $clientId  
     * @param string $name  
     * @param \DateTime $startDate  
     * @param \DateTime $endDate  
     * @param array<DrawItem> $items  
     */  
    public function __construct(public string $id,     //UUid  
                                public string $clientId,     //UUid  
                                public string $clientName,  
                                public string $name,  
                                public string $startDate,  
                                public string $endDate,  
                                public ?int   $availableVotes,  
                                public ?array $items)  
    {  
    }  
  
     public function getItemIdByItemNumber($itemNumber): string  
    {  
        foreach ($this->items as $item) {  
            if (trim($item->itemNumber) === trim($itemNumber)) {  
                return $item->id;  
            }  
        }  
        throw new \Exception("Item not Found");  
    }  
  
    public function getNumberOfItems(): int  
    {  
        $sum = 0;  
        foreach ($this->items as $item) {  
            $sum += $item->totalStock;  
        }  
        return $sum;  
    }
```
Das Beispiel zeigt eine Datenklasse "DRAW", die als Datenobjekt fungiert. Sie enthält Eigenschaften, die beim Erstellen des Objektes über den Konstruktor gesetzt werden, und Methoden zur Verarbeitung der enthalten Daten. 
Das Datenobjekt kann mittels verschiedener Methoden Daten aus dem Objekt abrufen und verändern

### Eigenschaften (Attribute)
Eigenschaften sind Variablen, die innerhalb einer Klasse definiert werden. Sie repräsentieren den Zustand oder die Daten, die das Objekt hält. In PHP können Eigenschaften verschiedene Sichtbarkeitsmodifikatoren haben:

- **public**: Die Eigenschaft ist von überall zugänglich.
- **protected**: Die Eigenschaft ist innerhalb der Klasse und von abgeleiteten Klassen zugänglich.
- **private**: Die Eigenschaft ist nur innerhalb der Klasse zugänglich.

### Methoden
Methoden sind Funktionen, die innerhalb einer Klasse definiert werden. Sie können auf die Eigenschaften der Klasse zugreifen und diese manipulieren.
## References
1. [[readonly]]
