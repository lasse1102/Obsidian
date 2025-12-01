
--- 
Erstellt: 2024-03-25    06:53 
Tags: #database #programming #PHP  
Link Up: [[Doctrine DBAL]]
Link Down:

--- 
# executeQuery
Die executeQuery, dient dazu eine SQL-Abfrage gegen eine Datenbank auszuführen. 
```php
public function executeQuery(  
    string $sql,  
    array $params = [],  
    $types = [],  
    ?QueryCacheProfile $qcp = null  
): Result {
```
Die Funktion übernimmt mehrere Parameter, als erstes die SQL-Abfrage selber, optionale Parameter, Typen und ein optionales QueryCacheProfile Objekt. Die Funktion gibt ein Result zurück.

Der Result Part:
```php
if ($qcp !== null) {  
        return $this->executeCacheQuery($sql, $params, $types, $qcp);  
    }  
  
    $connection = $this->getWrappedConnection();  
  
    $logger = $this->_config->getSQLLogger();  
    if ($logger !== null) {  
        $logger->startQuery($sql, $params, $types);  
    }  
  
    try {  
        if (count($params) > 0) {  
            if ($this->needsArrayParameterConversion($params, $types)) {  
                [$sql, $params, $types] = $this->expandArrayParameters($sql, $params, $types);  
            }  
  
            $stmt = $connection->prepare($sql);  
  
            $this->bindParameters($stmt, $params, $types);  
  
            $result = $stmt->execute();  
        } else {  
            $result = $connection->query($sql);  
        }  
  
        return new Result($result, $this);  
    } catch (Driver\Exception $e) {  
        throw $this->convertExceptionDuringQuery($e, $sql, $params, $types);  
    } finally {  
        if ($logger !== null) {  
            $logger->stopQuery();  
        }  
    }  
}
```
## References
1. [[Database Access#fetchAllAssociative|fetchAllAssociative]]

## Quellen
1. 