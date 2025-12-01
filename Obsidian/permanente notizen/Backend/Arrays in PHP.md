
--- 
Erstellt: 2024-03-21    11:44 
Tags: #PHP #programming 
Link Up: [[PHP]]
Link Down: 

--- 
# Was sind Arrays in PHP
Arrays in PHP sind ein sehr nützliche Datenstruktur, die es ermöglicht, mehrere Werte in einer einzigen Variable zu speichern. 
Es gibt drei Arten von Arrays in PHP:
1. Indizierte Arrays -> Arras mit eine nummerischen Index
2. [[Assoziative Array]] -> Arrays mit benannten Schlüsseln
3. Mehrdimensionale Arrays -> Arrays , die ein oder mehrere Arrays enthalten


# Syntax
Ein Array kann durch Konstrukt array() erzeugt werden. Dies nimmt beliebig viele kommagetrennt Werte entgegen "Key"  => "Value". 
Der Key kann entweder ein Integer sein oder eine Zeichenkette. Der Value kann beliebige Datentypen annehmen

Ein einfaches Beispiel:
```php
`<?php   
	$array = array("foo", "bar");`

//Verkürtzte Schreibweise:
`$array = ["foo", "bar"];`
?>
```

# Zugriff auf ein Array
Um auf ein Indiziertes Array zuzugreifen, muss man den Index des Values angeben. Beginnend tuet es bei 0
```php
$cars = array("Volvo", "BMW", "Toyota");
echo $cars[0];
```

# Build in Functions
Build in Funktionen sind Funktionen die schon vordefiniert in PHP sind. Diese Funktionen funktionieren ohne irgendwelche Anforderungen oder neuinstallationen.

[Alle Build-In Funktionen](https://www.php.net/manual/en/indexes.functions.php)

# [[Type Casting]]
- [[Type Casting]] wird verwendet um eine Variable von einem bestimmten Type in einen anderen Typen umzuwandeln 
- Dies kann aus verschiedenen Gründen auftreten z.B um eine Operation zwischen verschiedenen Typen durchzuführen


## References
- [[Assoziative Array]]
- [[Type Casting]]

## Quellen
1. https://www.w3schools.com/php/php_arrays.asp
2. https://www.php.net/manual/de/language.types.array.php