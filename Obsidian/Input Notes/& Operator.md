
--- 
Erstellt: 2024-12-19    09:41 
Tags: #Programming/PHP/Allgemeines
Link Up: [[PHP]] 
Link Down:

--- 
# Was macht der % Operator in PHP
Der `&`-Operator in PHP hat zwei Hauptverwendungen, abhängig davon, wie er im Code eingesetzt wird:
1. **Referenzzuweisung (`&` in der Zuweisung)**:
	- Das bedeutet, dass Änderungen an der neuen Variable auch die ursprüngliche Variable beeinflussen.
     Beispiel:
	```PHP
$a = 10; 
$b = &$a; // $b ist jetzt eine Referenz auf $a 
$b = 20; 
echo $a; // Gibt 20 aus, weil $b eine Referenz auf $a ist
	```
In diesem Fall wird `b` eine Referenz auf `a`, und Änderungen an `b` wirken sich direkt auf `a` aus.

2. **Referenzparameter in Funktionen**:
	Der `&`-Operator kann auch verwendet werden, um **Referenzen** als Funktionsparameter zu übergeben. Dadurch wird die Variable innerhalb der Funktion direkt verändert, ohne dass eine Kopie der Variablen erstellt wird.
	**Beispiel:**
```PHP
function increment(&$value) {
$value++; 
} 

$num = 5; increment($num); 
echo $num; // Gibt 6 aus, weil $value eine Referenz auf $num ist
```

#### Praxis Beispiel
```PHP
foreach ($selectedItems as &$items) {  
        $itemName = $this->helpers->getClassicDB()->getItem($items["name"],          $items["articleNumber"]);  
        
        $items["itemName"] = $itemName->description;  
    }  
      
unset($items); // Dies verhindert ungewollte Nebenwirkungen außerhalb der Schleife  
  
return $selectedItems;  
}
```
In dem Beispiel wird $items geändert und normalerweise würde nach der foreach Schleife sich nichts in selectedItems geändert haben aber mit dme `&` Operator vor $items wird das auch auf $selectedItems angwendet

### Zusammenfassung:
- Der `&`-Operator wird verwendet, um eine **Referenz auf eine Variable** zu erstellen, sodass Änderungen an der Referenz auch die ursprüngliche Variable beeinflussen.
## References
1. 
