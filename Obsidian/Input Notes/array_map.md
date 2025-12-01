
--- 
Erstellt: 2024-12-19    08:19 
Tags: #Programming/PHP/Datenstrukturen 
Link Up: [[PHP]]
Link Down:

--- 
### Was macht `array_map` in PHP?
`array_map` ist eine PHP-Funktion, die es erlaubt, eine benutzerdefinierte Funktion oder eine anonyme Funktion auf jedes Element eines Arrays anzuwenden. Die grundlegende Idee ist, dass du ein Array transformieren kannst, indem du jedes Element durch die definierte Funktion "durchlaufen" lässt.

**Syntax**
```PHP
array_map(callable $callback, array $array, array ...$arrays): array
```
#### Parameter:
1. **$callback**: Eine Funktion, die auf jedes Element angewendet wird. Sie kann eine benutzerdefinierte oder eine eingebaute Funktion sein.
2. **$array**: Das Hauptarray, auf dessen Elemente die Funktion angewendet wird.
3. **...$arrays**: Optionale weitere Arrays. Wenn mehrere Arrays angegeben werden, verarbeitet `array_map` die Elemente mit dem gleichen Index in allen Arrays gleichzeitig und übergibt sie an die Funktion.
# Praxisbeispiel
Ausgangssituation: Dies ist das Array von Objekten und wir brauchen hieraus alle Namen
![[Pasted image 20250307105325.png]]

## Lösung 

**Normale anonyme Funktion:**
```PHP
$draw = $helpers->getInternalShopServiceLP()->getDrawsSummary();
// Funktion, die jedes Element verdoppelt 
$doubled = array_map(function($name) {
	return $name->name; 
}, $numbers);
	 
$helpers->exitWithVarExport($draw); 
// Ausgabe: [2, 4, 6, 8, 10]
```

**Arrow Function (`fn`) – Verkürzte Schreibweise**
```PHP
$draw = $helpers->getInternalShopServiceLP()->getDrawsSummary();


$name = array_map(fn($name) => $name->name, $draw);
	 
$helpers->exitWithVarExport($draw); // Ausgabe: [2, 4, 6, 8, 10]
```
- Es wird durch jeden index (Objekt) von $draw durchiterieren
- Wir extrahieren alle Namen der Verlosung indem wir mit -> auf das Objekt Attribut des Objektes zugreifen
##### Vorteil von Arrow Function (fn)
🔹 **Kurze Schreibweise**, wenn nur eine Rückgabe (`return`) benötigt wird.  
🔹 **Kein eigenes `return` notwendig** – der Ausdruck nach => wird automatisch zurückgegeben

##### Ausgabe
![[Pasted image 20250307111037.png]]

---
### **Wann verwende ich welche?**
✅ **Nutze `fn` für einfache Ausdrücke:**
- Wenn die Funktion nur eine Zeile hat und direkt etwas zurückgibt.
✅ **Nutze `function()` für komplexe Logik:**
- Wenn mehrere Zeilen Code oder Bedingungen benötigt werden.

### Vorteile von array_map
- **Kompakt und deklarative Syntax**: Die Funktion ist kürzer und oft besser lesbar als eine Foreach Schleife
- Nicht destruktiv: Das ursprüngliche Array  bleibt unverändert, da ein neues Array zurückgegeben wird (Kann ein Vorteil sein muss aber nicht)
- Eingebaute Funktionen nutzen: Man kann auch eingebaute PHP-Funktionen direkt übergeben

## References
1. 
