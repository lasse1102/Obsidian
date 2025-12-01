
--- 
Erstellt: 2025-10-13    10:51 
Tags: 
Link Up: [[AP2]]
Link Down:

--- 
Themen:
- Select
- Delete
- Update
- Read
- Insert
- Union
- Create Index

# Befehle
##### Group By / Order By

Die **Order By** Klausel wird verwendet, um die Ergebnismenge einer Select Anweisung entweder in aufsteigender oder absteigender Reihenfolge zu sortieren

```SQL
Order By column_name ASC|DESC
```
DESC ist absteigend und ASC ist aufsteigend (ASC ist Standard)

Die GROUP BY-Klausel wird verwendet, um Zeilen zu gruppieren, die in einer bestimmten Spalte die gleichen Werte haben.

```SQL
SELECT category, AVG(price)
FROM products
GROUP BY category;
```

---
#### DateDiff
`DATEDIFF` ist eine Funktion, die die **Differenz zwischen zwei Datums- oder Zeitangaben** berechnet und das Ergebnis in einer **bestimmten Einheit** (z.B. Jahre, Monate, Tage, Minuten, Sekunden) zurückgibt.

|**Parameter**|**Beschreibung**|**Beispielwerte für die Einheit**|
|---|---|---|
|**`Einheit`**|Die Zeiteinheit, in der das Ergebnis zurückgegeben werden soll.|`YEAR`, `MONTH`, `DAY`, `HOUR`, `MINUTE`, `SECOND`|
|**`Startdatum`**|Das frühere Datum oder der frühere Zeitpunkt.|`'2024-01-01'`|
|**`Enddatum`**|Das spätere Datum oder der spätere Zeitpunkt.|`'2024-01-10'`|

#### Union 
SQL Union vereint Datensätze aus zwei oder mehr Tabellen in einer Zieltabelle ohne Duplikate 
![[Pasted image 20251027132009.png]]

Wenn man die Duplikate nicht entfernen will dann nutzt man UNION ALL, somit werden die Duplikate nicht entfernt
![[Pasted image 20251027132118.png]]

### Like
Mit dem Like Operator können wir alle Spalten abfragen die mit dem bestimmten wort anfangen oder enden.
bsp.
![[Pasted image 20251027134707.png]]
Dies gibt uns alle Bewohner wieder die friedlich sind und deren Beruf mit schmied endet











































# Aufgaben
![[Pasted image 20251027110227.png]]

![[Pasted image 20251027110244.png]]

![[Pasted image 20251027110305.png]]





Lösungen
![[Pasted image 20251027113015.png]]




![[Pasted image 20251027122518.png]]



Lösungen
![[Pasted image 20251027122541.png]]

## References
1. [[08 - Übung SQL und JOIN]]
2. [[08a - Lösungen SQL und JOIN]]
3. [[08c - Aufgaben SQL (schwieriger)]]
4. [[06 - Wiederholung SQL JOIN.excalidraw]]
5. [[Teil 2, Aufgabe 4 (SQL).excalidraw]]


https://blog.christianeirich.de/lernzettel-sql-zur-gap2-fuer-fachinformatiker-anwendungsentwicklung/