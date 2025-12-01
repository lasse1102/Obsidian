
--- 
Erstellt: 2025-08-19    07:54 
Tags: 
Link Up: [[JavaScript]]
Link Down:

--- 
# DOM Elemente dynamisch stylen mit jQuery

### Problemstellung

Wie kann man bei einer Gruppe von Buttons, die eine Position auswählen, den **aktiven Button visuell hervorheben** und die anderen Buttons in ihren **Standardzustand zurücksetzen**? Der Stilwechsel soll dynamisch nach einem Klick erfolgen und den aktuellen Zustand widerspiegeln.

---

### Verwendete Techniken

- **jQuery**: Eine schnelle, kleine und funktionsreiche JavaScript-Bibliothek. Sie vereinfacht das Traversieren von HTML-Dokumenten, die Ereignisbehandlung, Animationen und Ajax-Interaktionen.
    
- **CSS-Klassen**: Die Stile der Buttons werden nicht direkt inline, sondern über CSS-Klassen wie `btn-primary` (für den aktiven Zustand) und `btn-default` (für den Standardzustand) verwaltet. Dies trennt die Darstellung vom Verhalten.
    
- **DOM-Manipulation**: Mit jQuery werden Klassen dynamisch zu den Elementen hinzugefügt (`.addClass()`) und entfernt (`.removeClass()`), um ihr Aussehen zu ändern.
    

---

### Code-Analyse

#### HTML-Struktur

Die Buttons haben alle IDs, die mit **`setPosition`** beginnen, und ein **`data-position`**-Attribut, das ihre jeweilige Position speichert.

HTML
```PHP
<div> <button id="setPosition1" class="btn btn-default" data-position="1">{{ "articleDimensions.position1"|trans|default("Position 1") }}</button> 

<button id="setPosition2" class="btn btn-default" data-position="2">{{ "articleDimensions.position2"|trans|default("Position 2") }}</button> 

<button id="setPosition3" class="btn btn-default" data-position="3">{{ "articleDimensions.position3"|trans|default("Position 3") }}</button> </div>
```

#### jQuery-Code
![[Pasted image 20250819080121.png]]
1. **Event-Handler einrichten**:
    - `$("[id^=setPosition]").click(function(event) { ... });`
    - Dieser Selektor wählt alle Elemente aus, deren ID mit **`setPosition`** beginnt.
    - Ein Klick-Event-Handler wird an diese Elemente gebunden.
2. **Klick-Aktion ausführen**:
    - `event.preventDefault();`: Verhindert das Standardverhalten eines Klicks (z.B. das Absenden eines Formulars), falls der Button in einem Formular ist.
    - `const position = $(this).data("position");`: Liest den Wert des **`data-position`**-Attributs des geklickten Buttons aus. Dieser Wert wird in der Variablen `position` gespeichert.
    - `$.post("{{ setPositionURL }}", { position: position }, function(data) { ... });`: Sendet eine **POST-Anfrage** an den Server, um die Position zu aktualisieren. Der Erfolgscallback wird ausgeführt, sobald die Anfrage erfolgreich ist.
3. **Styling im Erfolgsfall**:
    - `$("[id^=setPosition]").removeClass("btn-primary").addClass("btn-default");`: **Setzt alle Buttons zurück**. Alle Buttons mit einer ID, die mit `setPosition` beginnt, verlieren die Klasse `btn-primary` und erhalten die Klasse `btn-default`. Dadurch wird der vorherige aktive Button deaktiviert.
    - `$(`#setPosition${position}`).removeClass("btn-default").addClass("btn-primary");`: **Hebt den aktuell geklickten Button hervor**. Mithilfe der ausgelesenen `position` wird der spezifische Button selektiert (z.B. `#setPosition1`). Dieser eine Button verliert die Klasse `btn-default` und erhält die Klasse `btn-primary`.
        
4. **Fehlerbehandlung**:
    - `.fail(function(jqx) { ... });`: Dieser Block wird ausgeführt, wenn die Serveranfrage fehlschlägt.
    - Er zeigt eine rote **Fehlermeldung** (`<div class="alert alert-danger">`) in einem Bereich mit der ID `#errors` an, die entweder vom Server (`jqx.responseJSON.error`) oder einer Standardnachricht (`"Error setting position"`) stammt.

---

### Anwendung und Vorteile
- **Benutzerfreundlichkeit**: Die visuelle Rückmeldung zeigt dem Nutzer sofort, welche Option er gewählt hat.
- **Zustandsverwaltung**: Das Styling der Buttons spiegelt den aktuellen Zustand der Anwendung wider.
- **Trennung von Concerns**: Das Verhalten (JavaScript) und die Darstellung (CSS) sind getrennt, was den Code wartbarer macht.
- **Skalierbarkeit**: Das System funktioniert automatisch für jede Anzahl von Buttons, solange die ID-Konvention (`setPositionX`) beibehalten wird.
- **Optimale Nutzung von jQuery**: Effiziente Selektoren (`[id^=...]`) und DOM-Manipulationsmethoden werden kombiniert, um eine kompakte und leistungsfähige Lösung zu schaffen.
## References
1. 
