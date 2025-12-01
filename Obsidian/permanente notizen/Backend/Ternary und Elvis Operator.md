
--- 
Erstellt: 2024-03-25    06:48 
Tags: 
Link Up: [[PHP]]
Link Down:

--- 
# Definition
In Programmiersprachen sucht man oft nach shortcuts, um Code kürzer zu gestalten. Mit den ? Operator (auch Ternary operator) in PHP und JavaScript kann man conditional statements verkürzen

# Was ist ein Ternary operator
Ein Ternary Operator, dient dazu die länge des Codes zu reduzieren. Dies ist eine alternative für if-else Blöcke und verschachtelte if-else Blöcke. Bei der Verwendung des Operators wird von links nach Rechts gelesen. Es wird viel genutzt, wenn wir Werte zu Variablen zuweisen wollen, wenn wir POST daten zuweisen wollen oder Formulare validieren wollen. 

Es benötigt 3 Operanden (eine Bedingung, Ergebnis für true, Ergebnis für false)

# Syntax
```js
currentEAN = (currentEAN === "" ? currentEAN = "TaringEAN" : 0
```
- currentEAN === "" : Ist die Bedingung, die ein True oder False returnt
- currentEAN = "TaringEAN" : Wird ausgeführt, wenn die Bedingung True ist 
-  0 : Wird ausgeführt, wenn die Bedingung false ist
- Das Ergebnis wird in currentEAN gespeichert

```PHP
$name = "Elvis Presley";
$displayName = (name != null ? name : "Unknown");
```

# Elvis Operator
Der Elvis Operator, wird mit ?: abgekürzt und prüft ob eine Variable null ist, wenn ja dann gibt sie einen standartwert zurück, wenn die Variable nicht null ist gibt sie die Variable zurück

Beispiel:
```php
$name = "Copilot";
$greeting = "Hallo, " . ($name ?: "Gast");
echo $greeting; // Ausgabe: "Hallo, Copilot"
```
Wenn `$name` einen Wert hat (in diesem Fall “Copilot”), wird dieser Wert verwendet. Wenn `$name` jedoch null ist, wird stattdessen der Standardwert “Gast” verwendet.

## References
1. 

