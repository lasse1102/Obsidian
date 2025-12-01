
--- 
Erstellt: 2024-03-22    13:43 
Tags:  #database 
Link Up: [[Doctrine DBAL]]
Link Down:

--- 
# Was ist Doctrine
Doctrine ist ein Open-Source-Projekt für PHP, das verschieden Bibliotheken umfasst, die sich hauptsächlich auf Datenbanken und Objekt-Mapping konzentrieren. Doctrine ist dazu da um eine Verbindung zwischen [[Databases]] und PHP herzustellen. Ein wichtiger Kernpunkt von Doctrine ist DBAL

## DBAL (Database Abstraction Layer)
Diese Schicht dient dazu, eine Abstraktionsebene zwischen PHP und der Datenbank zu schaffen. Sie ermöglicht es, mit denselben **PHP-Aufrufen** unterschiedliche Datenbankmanagementsysteme (DBMS) anzusprechen. Zu den unterstützten Systemen gehören unter anderem MySQL, Oracle, [[PostgreSQL]] und Microsoft SQL Server


# Vorteile von Doctrine
- Entwickelt seit 2006: Doctrine hat eine stabile und qualitativ hochwertige Codebasis.
- Flexibles und mächtiges Objekt-Mapping: Es bietet vielseitige Möglichkeiten zur Abbildung von Objekten auf Datenbanktabellen.
- Doctrine wird in viele Frameworks wie Symfony und Zend Framework eingesetzt


# Integration von Doctrine DBAL in php
Zuerst müssen wir in unsere composer.json doctrine installieren:
```php
"require": {
"doctrine/dbal": "^3.6"
}
```

Anschließend müssen wir die composer.json updaten. Somit werden alle relevanten dependencies installiert und wir können es dann verwenden.

# Connection auf Doctrine

Mit diesem Code erstellen wir ein Connection zur Datenbank
```php
public function getConnection(): Connection  
{  
    if ($this->connection === null) {  
        $connectionParams = [  
            'dbname' => $this->playgroundDbName,  
            'user' => $this->playgroundDbUser,  
            'password' => $this->playgroundDbPassword,  
            'host' => $this->playgroundDbHost,  
            'port' => $this->playgroundDbPort,  
            'driver' => $this->playgroundDbDriver,  
        ];  
  
        $this->connection = DriverManager::getConnection($connectionParams);  
    }  
    return $this->connection;  
}
```

Diese Funktion gibt ein Wert von Typ Connection zurück. 
1. Wenn die Variable connection noch nicht initialisiert wurde, wird eine Verbindung zur Datenbank erstellt
2. Es werden alle notwendigen Parameter in einem [[Assoziative Array]] gespeichert
3. Mit der Funktion DriverManger wird eine Verbindung zu Datenbank hergestellt
4. Anschließend wird die Verbindung der Datenbank zurückgegeben




Dies wäre die dazugehörige Route, um eine einfache SQL Abfrage zu gestalten:
```php
$this->get('/databaseTest', "databaseTest", function (Helpers $helpers) {  
    $connection = $helpers->getDatabaseService()->getConnection();  
    $result = $connection->executeQuery(
    "SELECT ma.name, ROUND(AVG(v.base_price), 2)  
    FROM variants v        
    JOIN models mo on v.model_id = mo.id        
    JOIN manufacturers ma on mo.manufacturer_id = ma.id        
    GROUP BY ma.name        
    ORDER BY ma.name");  
  
    return $helpers->htmlResponse(
    "<pre>" . print_r($result->fetchAllAssociative(), true) . "</pre>");  
});
```
- "$helpers->getDatabaseService()->getConnection();"  , erstellen wir eine Verbindung zu unserer Datenbank und Speichern sie in $connection
- $connection.[[execute a Query in Doctrine#executeQuery|executeQuery]] , erstellen wir ein Query PHP und Speichern es in Result
- Mit $helpers->htmlResponse fetchAllAssociative(), können wir unser Query auf der Website ausgeben
## References
1. [[PostgreSQL]]
2. [[execute a Query in Doctrine]]

## Quellen
1. https://www.doctrine-project.org/projects/doctrine-dbal/en/3.8/reference/introduction.html
2. https://www.youtube.com/watch?v=bfTIVQvS5JI&list=PLr3d3QYzkw2xabQRUpcZ_IBk9W50M9pe-&index=83