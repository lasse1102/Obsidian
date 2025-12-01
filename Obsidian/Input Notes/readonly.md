
--- 
Erstellt: 2025-02-07    12:57 
Tags: #Programming/PHP/Klassen  
Link Up: [[PHP]]
Link Down:

--- 
# readonly
- readonly gibt es seit PHP 8.1, dass beispielsweise verwendet wird für unveränderliche Objekte
- Eine readonly Klasse oder Eigenschaft, kann nach der Initialisierung nicht mehr verändert werden

## readonly bei Eigenschaften
```php
class User { 
public readonly string $name; 

public function __construct(string $name) {
	$this->name = $name; // ✅ Erlaubt (Initialisierung)
	} 
}

$user = new User("Max");
echo $user->name; // ✅ Gibt "Max" aus 

$user->name = "Peter"; // ❌ Fehler: readonly Eigenschaften können nicht geändert werden
```

---

## readonly bei Klassen
Seit **PHP 8.2** gibt es auch **readonly-Klassen**. Alle Eigenschaften einer `readonly class` sind automatisch `readonly`.

🚀 **Vorteile von `readonly class`:**  
✔ Keine Änderungen nach der Initialisierung  
✔ Perfekt für **Datenobjekte (DTOs, Entities)**  
✔ **Performance-Vorteil**, da PHP intern Optimierungen vornehmen kann

---
### Vorteile von `readonly`
✅ **Sicherheit**: Verhindert unerwünschte Änderungen nach der Initialisierung  
✅ **Bessere Code-Qualität**: Klare Trennung zwischen veränderbaren und unveränderlichen Objekten  
✅ **Optimierung**: PHP kann readonly-Objekte effizienter verwalten
## References
2. 
