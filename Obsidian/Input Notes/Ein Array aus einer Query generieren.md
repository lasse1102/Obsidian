
--- 
Erstellt: 2024-12-17    06:19 
Tags: #DoctrinDBAL 
Link Up: [[Doctrine DBAL]]
Link Down:

--- 
# Ein Array aus einer SQL Abfrage generieren
In dieser Notiz wird erklärt, wie man ein Array aus einer SQL-Abfrage in PHP erhält. Der folgende Code zeigt eine Methode, die Daten aus einer Datenbank abruft und sie in einem assoziativen Array organisiert.

```PHP
public function getDrawData($id): array  
{  
    $qb = $this->middlewareDB->getDatabase()->createQueryBuilder();  
  
    // SQL-Abfrage mit JOIN, um Draw-Daten und die Artikelnummern zu erhalten  
    $qb->select('d.*, i."articleNumber"')  
        ->from('"internalShopDrawsLP"', 'd')  
        ->leftJoin('d', '"internalShopItemsLP"', 'i', 'i."drawId" = d."id"')  
        ->where('d."id" = :id')  
        ->setParameter('id', $id);  
  
    $result = $qb->executeQuery()->fetchAllAssociative();  
  
    $draw = [  
        "id" => $result[0]["id"],  
        "name" => $result[0]["name"],  
        "isActive" => $result[0]["isActive"],  
        "startDate" => $result[0]["startDate"],  
        "endDate" => $result[0]["endDate"],  
        "client" => $result[0]["client"],  
        'articleNumbers' => []  
    ];  
  
    // Alle Artikelnummern sammeln  
    foreach ($result as $row) {  
        if ($row['articleNumber']) {  
            $draw['articleNumbers'][] = $row['articleNumber'];  
        }  
    }  
  
    return $draw;  
}
```
Dies ist der komplette Code.

```PHP
$draw = [
"id" => $result[0]["id"],
"name" => $result[0]["name"],
"isActive" => $reslt[0]["isActive"],
"startDate" => $result[0]["startDate"],
"endDate" => $result[0]["endDate"],
"client" => $result[0]["client"],
'articleNumbers' => [] 
];
```
Hier wird ein assoziatives Array erstellt, welches die Daten aus der Abfrage enthält bei denen EIN EINTRAG abgerufen wurde. Und dazu wird noch "articleNumbers" hinzugefügt um ein Array aus der Join Abfrage zu generieren.

```PHP
foreach ($result as $row) { 
	if ($row['articleNumber']) { 
		$draw['articleNumbers'][] = $row['articleNumber']; 
	} 
}
```
In dieser Schleife werden die Artikelnummern aus der Abfrage gesammelt und dem Array "$draw['articleNumbers']" hinzugefügt

## References
1. [[Array in eine Query einbauen]]
