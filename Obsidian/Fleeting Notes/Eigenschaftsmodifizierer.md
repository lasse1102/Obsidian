
--- 
Erstellt: 2025-05-09    08:37 
Tags: #Programming/PHP/Klassen  
Link Up: [[PHP]]
Link Down:

--- 
Ich beschreibe hier einmal was die verschiedenen Klassen/Eigenschaftsmodifizierer machen und wofür sie gut sind und verwendet werden sollen. 
1. **final**
2. **readonly**
3. **static**
4. **abstract**

# final
Bedeutung: Diese Klasse oder Methode darf nicht weitervererbt werden bzw. überschrieben werden.

**Beispiel:**
![[Pasted image 20250509084017.png]]
👉 **Fehlermeldung**:
> _Class Dog may not inherit from final class Animal_

#### Warum nutzt man final
- Man möchte verhindern dass die Klasse erweitert wird und sie dadurch möglicherweise verändert
- Man will die Klasse als "abgeschlossen" und "stabil" markieren
- Typisch bei Value Objects, Utility-Klassen() oder Sicherheitskritischen Klassen(Authentifizierung, Validierung, Verschlüsselung)


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

## readonly bei Klassen
Seit **PHP 8.2** gibt es auch **readonly-Klassen**. Alle Eigenschaften einer `readonly class` sind automatisch `readonly`.

 **Vorteile von `readonly class`:**  
✔ Keine Änderungen nach der Initialisierung  
✔ Perfekt für **Datenobjekte (DTOs, Entities), Konfigurationswerte, Value Objects**  
✔ **Performance-Vorteil**, da PHP intern Optimierungen vornehmen kann

Kurz gefasst kann man sagen, dass man alles Klasse readonly machen kann die entweder keine Eigenschaften enthält oder Eigenschaften enthält, die nach der Initialisierung nicht mehr verändert werden dürfen. Gleiche gilt für injezierten Abhängigkeiten im Konstruktor, die können auch nicht mehr verändert werden 

---
# abstract


## References
1. 
