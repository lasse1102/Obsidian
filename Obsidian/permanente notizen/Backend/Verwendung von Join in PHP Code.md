
--- 
Erstellt: 2024-06-13    14:05 
Tags: #PostgreSQL
Link Up: [[PostgreSQL]]
Link Down:

--- 
# Verwendung von Join
Im folgenden Code zeige ich ein Beispiel Code wie man ein einfachen Join verwendet:

```php
$qb = $this->middlewareDB->getDatabase()->createQueryBuilder();  
$qb->select('items."itemName", items.currentstock, c.name')  
    ->from('"internalShopItemsLP"', "items")  
    ->join("items", '"clients"', "c", "c.id = items.client");  
  
$result = $qb->executeQuery()->fetchAllAssociative();
```
Hierbei muss folgendes beachtet werden:
- Spalten mit Großbuchstaben, müssen extra mit doppelten Anführungszeichen umschlossen sein innerhalb der einfachen Anführungszeichen
- im form Statement muss immer ein Alias stehen, welches wir im join als ersten Parameter übergeben
- Anschließend kommt die Tabelle auf die wir Joinen wollen mit dazugehörigen Alias
- Und zu guter letzt kommt die condition, die wir anwenden wollen
	- In diesem Falle wollen wir alle Einträge von internalShopItemsLP ausgegeben haben und immer den dazugehörigen client Namen, den wir in der condition prüfen 
## References
1. 

## Quellen
1. 