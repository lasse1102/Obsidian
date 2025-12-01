
--- 
Erstellt: 2024-03-21    13:10 
Tags: #programming #PHP 
Link Up: [[PHP]]
Link Down:

--- 

# Definition
Type Casting in PHP wird verwendet um eine variable von einen Typ in einen anderen Typ umzuwandeln. Es wird häufig verwendet im Zusammenhang mit Benutzer eingaben, Datenbank Interaktion oder bei einer Berechnung mit 2 unterschiedlichen Datentypen.

PHP liefert schon vordefinierte In-build-Funktionen mit wie zum Beispiel: (int), (float), (string), (bool), and (array), welche umgewandelt werden können in  integer, float, string, boolean, or array types.

# Introduction
PHP ist eine dynamically typed Language, dass Variablen während ihres gesamten Lebenszyklus Werte unterschiedlichen Typs enthalten können. 

Es wird unterschieden zwischen explicit und implicit Type Casting:

Explicit typecasting wird verwendet wenn wir explizit den type einer Variable ändern. Zum Beispiel beim ändern einer Variable in ein Integer, kann man (int) oder (integer) verwenden vor der Variable. Somit sorgen wir explizit dafür das wir den Type der Variable zum Integer ändern.
Anders als bei der implicit typecasting wird die Typenumwandlung automatisch gemacht. Dies tritt dann auf, wenn PHP erkennt in welchen context es verwendet werden soll, also der Compiler erkennt dies automatisch und ändert das in den richtigen Typ um. Zum Beispiel bei einer addition zwischen einem String(der eine Zahl enthält) und einen Integer Wert, wird der Compiler den String automatisch in einen Integer umwandeln

# Typ in Integer umwandeln
Um eine Variable in Integer umzuwandeln, gibt es Mehrere Möglichkeiten. Eine dieser Möglichkeiten ist die Verwendung von:

- (int) (integer).
```php
$value = 10.5;
$intValue = (int)$value;
echo $intValue; // Output: 10
```

- intval() Funktion
```php
$value = "20";
$intValue = intval($value);
echo $intValue; // Output: 20
```

- settype() Funktion
```php
$value = "15";
settype($value, "integer");
echo $value; // Output: 15
```

Dies funktionier beim umwandeln zum Float und zum String genau so wie beim Integer.

#### Umwandeln zum Array
- (array) casting operator
```php
$value = "Hello";
$arrayValue = (array)$value;
print_r($arrayValue); // Output: Array([0] => Hello)
```

- settype() Funktion
```php
$value = "world";
settype($value, "array");
print_r($value); // Output: Array([0] => world)
```

Bei der Umwandlung zu einem array ist wichtig zu beachten, dass das fertige array numerische Keys besitzt, die bei 0 beginne, es sei denn es handelt sich um ein [[Assoziative Array]]
## References
1. https://www.scaler.com/topics/type-casting-in-php/