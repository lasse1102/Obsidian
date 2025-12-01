
--- 
Erstellt: 2024-12-04    11:20 
Tags: #DoctrinDBAL 
Link Up: [[Doctrine DBAL]]
Link Down:

--- 
# SQL Injection
Angreifer können SQL-Injection in einer Anwendung verwenden, wenn diese [[#Dynamische Datenbankabfragen |dynamische Datenbankabfragen]] enthält, die String-Verkettung und Benutzereingaben verwenden. Um SQL-Injection-Fehler zu vermeiden, müssen Entwickler Folgendes tun

- keine dynamischen Abfragen mit String-Verkettung mehr schreiben oder
- verhindern, dass bösartige SQL-Eingaben in ausgeführte Abfragen aufgenommen werden.

Es gibt einfache Techniken zur Verhinderung von SQL-Injection-Schwachstellen, die bei praktisch jeder Programmiersprache und jeder Art von Datenbank eingesetzt werden können.
### Dynamische Datenbankabfragen
Dynamische Datenbankabfragen sind SQL-Abfragen, die zur Laufzeit generiert werden, oft durch die Verkettung von Zeichenfolgen, die Benutzereingaben enthalten. Hier ist ein einfaches Beispiel:
```Php
public function isEmptySelectedItems($drawId): array  
{  
    $qb = $this->middlewareDB->getDatabase()->createQueryBuilder();  
  
    $qb->select("*")  
        ->from('"internalShopSelectedItemsLP"')  
        ->where('"drawId" = :drawId')  
        ->setParameter('drawId', $drawId);  
  
    return $qb->executeQuery()->fetchAllAssociative();  
}
```

## References
1. 
