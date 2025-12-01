
--- 
Erstellt: 2024-03-28    12:02 
Tags: #PHP #programming 
Link Up: [[PHP]]
Link Down:

--- 
# Definition
isset, prüft ob eine Variable deklariert ist und nicht null ist. Also die Funktion gibt true zurück, wenn die variable existiert und einen anderen Wert als null besitzt

# Parameter
var:
- Die Variable die gecheckt werden soll
vars:
- Weitere variablen die gecheckt werden sollen

# Beispiele
```php
`$var = '';      
// This will evaluate to TRUE so the text will be printed.
if (isset($var)) {  
	echo "This var is set so I will print.";   
}
```

```php
`// In the next examples we'll use var_dump to output   
// the return value of isset().      
$a = "test";   
$b = "anothertest";      
var_dump(isset($a)); // TRUE   
var_dump(isset($a, $b)); // TRUE      

unset ($a);     

var_dump(isset($a)); // FALSE   
var_dump(isset($a, $b)); // FALSE      

$foo = NULL;   
var_dump(isset($foo)); // FALSE`
```

Es funktioniert ebenso mit Elemente aus einem Array
```php
`$a = array ('test' => 1, 'hello' => NULL, 'pie' => array('a' => 'apple'));
var_dump(isset($a['test'])); // TRUE   
var_dump(isset($a['foo'])); // FALSE  
var_dump(isset($a['hello'])); // FALSE
```
## References
1.[[array_key_exists()]] 

## Quellen
1. 