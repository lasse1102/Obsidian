
--- 
Erstellt: 2024-03-28    11:26 
Tags: #PHP #programming 
Link Up: [[PHP]]
Link Down:

--- 
# Definition
Die Funktion check ob eine gegebener key oder ein index eines Arrays existiert oder nicht.

# Parameter
key:
- Value der gecheckt werden soll
array:
- Das Array mit keys zum prüfen ob der key vorhanden ist



NOTE: 
array_key_exists sucht nur nach den Schlüsseln in der ersten Dimension. Verschachtelte Schlüssel in mehrdimensionalen Arrays werden nicht gefunden.

# Beispiele

Beispiel 1:
```php
`$search_array = array('first' => 1, 'second' => 4);   
if (array_key_exists('first', $search_array)) {   
	echo "The 'first' element is in the array";   
}
```

Beispiel 2: 
[[isset()]] returnt kein true, wenn ein key auf null gesetzt ist, array_key_exists() tuet das schon
```php
`$search_array = array('first' => null, 'second' => 4);   

// returns false   
isset($search_array['first']);    

// returns true   
array_key_exists('first', $search_array);`
```

## References
1. [[isset()]]

## Quellen
1. [array_key_exists](https://www.php.net/manual/en/function.array-key-exists)