
--- 
Erstellt: 2025-02-18    08:44 
Tags: #Programming/PHP/Allgemeines 
Link Up: [[PHP]]
Link Down:

--- 
# "parseRequestString"
🔹 **Wird benutzt, wenn der Wert optional ist.**  
🔹 Gibt `null` zurück, falls der Wert nicht vorhanden ist.  
🔹 Kann für optionale Parameter verwendet werden.

```php
$_POST['username'] = "JohnDoe";
$username = $helpers->parseRequestString("username"); // "JohnDoe"

$nickname = $helpers->parseRequestString("nickname"); // NULL (weil nicht gesetzt)
```


# "forceRequestString"
🔹 **Wird benutzt, wenn der Wert zwingend erforderlich ist.**  
🔹 **Löst einen Fehler (Exception) aus, wenn der Wert fehlt oder leer ist.**  
🔹 Wird für Pflichtfelder in einer API oder einem Formular verwendet.

```php
$_POST['clientName'] = " Acme Corp "; 
$clientName = $helpers->forceRequestString("clientName"); // "Acme Corp" 

$location = $helpers->forceRequestString("location"); 
// Exception: "Fehlender oder ungültiger Wert für 'location'."
```


### **Zusammenfassung**

| Methode                    | Kann `null` sein?              | Leer erlaubt? | Fehler bei Fehlen? | Anwendung       |
| -------------------------- | ------------------------------ | ------------- | ------------------ | --------------- |
| `parseRequestString($key)` | ✅ Ja (wenn Wert nicht gesetzt) | ✅ Ja          | ❌ Nein             | Optionale Werte |
| `forceRequestString($key)` | ❌ Nein                         | ❌ Nein        | ✅ Ja (Exception)   | Pflichtwerte    |

## References
1. 
