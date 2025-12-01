
--- 
Erstellt: 2024-03-21    12:51 
Tags: #programming #PHP 
Link Up: [[PHP]]
Link Down:

--- 
# Was ist ein Assortatives Array
Dies ist ein Array, welches nicht einfach nur Values enthält und jeder einzelne Value ein Index hat. Beim Assoziativen Array werden die Values ein Key zugeordnet.

Beispiel:

```php
$car = array("brand"=>"Ford", "model"=>"Mustang", "year"=>1964);
```

# Wie greift man auf ein Assoziatives Array zu
Um auf ein Assoziatives Array zuzugreifen, musst du den Key des Values ansprechen

Beispiel:
```php
$car = array("brand"=>"Ford", "model"=>"Mustang", "year"=>1964);
echo $car["model"];
```

# Ändern von Values
Um ein Value zu ändern musst du den Key des Values ansprechen und neu setzen

Beispiel:
```php
$car = array("brand"=>"Ford", "model"=>"Mustang", "year"=>1964);
$car["year"] = 2024;
```


# Durch ein Assoziatives Array Iterieren

```php
$car = array("brand"=>"Ford", "model"=>"Mustang", "year"=>1964);

foreach ($car as $x => $y) {
  echo "$x: $y <br>";
```


# Praxisbeispiel

```php
$productDatabase[$articleName] = new ProductDatabaseEntry($articleName, $productDescription, $manufacturer, $eanValue);
```
- productDatabase ist ein assoziatives Array
- in diesem Fall wird es dazu verwendet Produktinformationen zu speichern

articleName
- dies ist der Schlüssel, mit dem auf den Wert im productDatabase zugegriffen wird
- Der Wert diese Schlüssels ist ein Objekt der Klasse ProductDatabaseEntry
## References
1. https://www.w3schools.com/php/php_arrays_associative.asp