
--- 
Erstellt: 2024-11-22    14:14 
Tags: #DoctrinDBAL
Link Up: [[Doctrine DBAL]]
Link Down:

--- 
# Array in einer Query durchlaufen

```PHP
public function getAllEntries($articleNumbers): array  
{  
    $qb = $this->middlewareDB->getDatabase()->createQueryBuilder();  
  
    $qb->select('items."itemName", items.currentstock, items."articleNumber", items."permittedArticles", c.name')  
        ->from('"internalShopItemsLP"', 'items')  
        ->join('items', '"clients"', 'c', 'c.id = items.client')  
        ->where($qb->expr()->in('items."articleNumber"', ':articleNumbers'))  
        ->setParameter('articleNumbers', $articleNumbers, ArrayParameterType::STRING);  
  
    $result = $qb->executeQuery()->fetchAllAssociative();
```

### Beschreibung
- **`expr()->in()`**: Diese Methode erstellt eine `IN`-Bedingung, um zu prüfen, ob `items."articleNumber"` in der Liste der `:articleNumbers` enthalten ist.
- **`setParameter()`**: Bindet das Array `articleNumbers` als Parameter an die Query. Der dritte Parameter (`ArrayParameterType::STRING`) spezifiziert, dass die Array-Werte als Strings behandelt werden sollen.

###### expr()
- liefert ein Objekt der Klasse ExpressionBuilder, das Methoden zu Erstellung von SQL-Ausdrücken bereitstellt
- es können verschiedene Arten von Bedingungen und Ausdrücken erstellt werden, die in einer Abfrage verwendet werden, wie z.B. `IN`, `AND`, `OR`, `LIKE`, 
## References
1. 
