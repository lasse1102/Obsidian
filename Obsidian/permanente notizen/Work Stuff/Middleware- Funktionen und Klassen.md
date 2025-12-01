
--- 
Erstellt: 2024-04-18    07:22 
Tags: #work
Link Up: [[Dashboard]]
Link Down:

--- 
# Sheet Sheet
- [[SheetSheet Klassen]]
- [[SheetSheet Funktionen]]


Die transState Funktion, kriegt 2 Parameter mit der 2 Parameter ist der , der übersetzer werden soll, heißt mit der transState Methode übersetzt man ein $state, welcher ein Status zum Filtern ist
```php
$transState = fn(Helpers $helpers, $state) =>  
$helpers->trans("goodsReceipts.overview.columns.state." . $state);
```


## References
1. [[Middleware - Service Klasse]]
2. [[Middleware - Projektstruktur]]

## Quellen
1. 