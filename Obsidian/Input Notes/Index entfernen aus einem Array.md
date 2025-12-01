
--- 
Erstellt: 2025-03-11    09:08 
Tags: #Programming/PHP/Datenstrukturen 
Link Up: [[PHP]] 
Link Down:

--- 
Um ein Index aus einem Array zu entfernen gibt es 2 Funktionen die unterschiedliche Funktionieren.
## unset + array_values
- unset() entfernt eine Variable oder ein Array-Element aus dem Array
- Es löscht das Element, aber die restlichen Indizes werden **nicht neu geordnet**
- Bei nummerischen Arrays entsteht eine Lücke im Index

Beispiel:
```PHP
$array = [1, 2, 3, 4, 5];

unset($array[2]);  // Entfernt das Element mit Index 2

print_r($array);
```

Ausgabe
```PHP
Array
(
    [0] => 1
    [1] => 2
    [3] => 4
    [4] => 5
)
```

Um dies zu umgehen, sodass das Array neu instanziert wird, kann man **array_values** verwenden nach dem unset().
```PHP
$array = [1, 2, 3, 4, 5];

unset($array[2]);  // Entfernt das Element mit Index 2
$array = array_values($array); // Neu instanzieren, um Indizes neu zu ordnen
print_r($array);
```

Ausgabe
```PHP
Array
(
	[0] => 1
    [1] => 2
    [2] => 4
    [3] => 5
)
```
## array_splice
- `array_splice()` entfernt Elemente **und schiebt automatisch alle verbleibenden Elemente nach vorne**, sodass **keine Lücke entsteht**.  
-  Es kann auch mehrere Elemente entfernen oder neue Elemente einfügen.

```PHP
$array = [10, 20, 30, 40, 50];
array_splice($array, 2, 1); // Entfernt das Element bei Index 2 (30)

print_r($array);
```

```PHP
Array
(
    [0] => 10
    [1] => 20
    [2] => 40
    [3] => 50
)
```


## Wann verwende ich was?
#### unset + (array_values)
- Wenn du **einzelne Elemente** aus einem assoziativen oder numerischen Array entfernen willst.
- Wenn du die Indizes erst **nachträglich neu ordnen** möchtest.
- Wenn du nicht jedes Mal eine Kopie des Arrays erzeugen möchtest (Performance-Vorteil).

#### array_splice
- Wenn du **schnell ein Element entfernen und das Array direkt neu indexieren** möchtest.
- Wenn du mit **numerischen Arrays arbeitest**.
- Wenn du einen bestimmten Bereich oder mehrere Elemente entfernen willst.
## References
1. 
