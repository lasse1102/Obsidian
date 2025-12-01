
--- 
Erstellt: 2025-04-17    14:55 
Tags: 
Link Up: 
Link Down:

--- 
## 🔹 1. **Namespaces in PHP**

### ✅ Was ist ein Namespace?
Ein **Namespace** (Namensraum) ist ein Container für Klassen, Funktionen und Konstanten. Er hilft dir dabei, **Namenskonflikte** zu vermeiden, vor allem in größeren Projekten oder wenn du Drittanbieter-Code nutzt.

### Beispiel ohne Namespace:
![[Pasted image 20250417145742.png]]
Du kannst nur **eine Klasse mit dem Namen `Logger`** im gesamten Projekt haben. Wenn z. B. eine andere Library auch eine Klasse `Logger` hat → **Konflikt**.

Beispiel mit Namespace:
![[Pasted image 20250417145834.png]]

Wenn du die Klasse nutzen willst:
![[Pasted image 20250417145950.png]]
### ✅ Vorteile von Namespaces
- Kein Namenskonflikt bei Klassen/Funktionen.
- Bessere Organisation des Codes.
- Ideal für große Projekte oder PSR-konforme Packages (z. B. Composer).


## 🔹 2. **Autoloader in PHP**

### ✅ Was macht der Autoloader?
Der Autoloader **lädt Klassen automatisch**, sobald sie benötigt werden – **ohne dass du `require` oder `include` schreiben musst**.
Das funktioniert besonders gut in Kombination mit **Namespaces**, weil man dadurch die **Ordnerstruktur mit dem Namespace verbinden kann**.


✅ Composer Autoloader (empfohlen!)
Wenn du Composer nutzt, brauchst du keinen eigenen Autoloader schreiben. Composer macht das für dich, wenn du `"autoload"` im `composer.json` definierst:
![[Pasted image 20250417150048.png]]
Wenn du dann `src/Utils/Logger.php` hast mit Namespace:
![[Pasted image 20250417150105.png]]
…kannst du einfach:
![[Pasted image 20250417150128.png]]
### ✅ Warum ist das wichtig?
- Spart dir Zeit (kein manuelles Einbinden mehr).
- Klar strukturierter Code durch Namespace = Ordnerstruktur.
- Pflicht in modernen Frameworks (Laravel, Symfony etc.).


|Thema|Was es macht|Vorteil|
|---|---|---|
|Namespace|Gruppiert Klassen/Funktionen, verhindert Konflikte|Struktur & Sauberkeit|
|Autoloader|Lädt Klassen automatisch bei Bedarf|Kein `require` nötig, effizient|
|Composer|Tool mit integriertem PSR-4-Autoloader|Industriestandard, super einfach|











































## References
1. 
