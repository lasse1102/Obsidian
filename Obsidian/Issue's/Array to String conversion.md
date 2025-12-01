
--- 
Date/ Time: 2024-03-20   10:29
Tags: #Issue #programming #PHP 
Link Up: [[PHP]]
Link Down:

--- 

# Fehlermeldung

```php
PHP Warning:  Array to string conversion in C:\xampp\htdocs\phpplayground\src\De\OKMedia\PlayGround\lpoehls\test.php on line 5
```

# Beschreibung
Basically, the **"PHP Warning: Array to string conversion ..."** occurs when the developer is trying or unintentionally (unbeabsichtigt) outputting an array of data. An **Array** of data cannot be converted into a string that's why this PHP warning occurs when we try it.

# Verhalten 
```php
1. <?php 
2. // Sample Array
3. $myArray = [ 'Foo', 'Bar', 'Hello World'];
5. echo $myArray;
6. ?>
```
Bei diesen Code wird der Fehler geschmissen

# Lösungsansätze
#### Solution 1:
The print_r() is a built-in function in PHP that prints human-readable information about the given variable which means this function will output the variable details and its values even for arrays or objects.
```php
1. <?php  
3. $myArray = [ 'Foo', 'Bar', 'Hello World'];
4. print_r($myArray);
5. ?>
```

#### Solution 2:
The var_dump() function is a built-in function that dumps the variable information.
```php
1. <?php  
3. $myArray = [ 'Foo', 'Bar', 'Hello World'];
4. var_dump($myArray);
5. ?>
```
# Reference


