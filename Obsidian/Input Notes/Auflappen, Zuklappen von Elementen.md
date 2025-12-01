
--- 
Erstellt: 2025-11-10    08:28 
Tags: 
Link Up: 
Link Down:

--- 
# Die verschiedenen Elemente die das Verhalten steuern
**Container-Element:**
![[Pasted image 20251110083016.png]]
Dies ist der Hauptcontainer für das Accordion
Die Id wird für die Verbindung zwischen Buttons und Panels zuständig

**Button Attribute:**
- `data-toggle="collapse"` -> Erzeugt das Aufklappverhalten
- `data-target="#collapse1"` -> Verweist auf das dazugehörige Panel
- `aria-expanded="false"` -> Zeigt den aktuellen Zustand an (false = zuklappen)
- `aria-controls="collapse1"` -> Verknüpft Button mit dem Panel

**Panel-Attribute:**
`class="collapse"` -> Basis Klasse für das Auf/Zuklappen
`id="collapse1"` -> Muss mit `data-target` übereinstimmen
`aria-labelledby="heading1` -> Verknüpft Panel mit der Überschrift


## References
1.  https://getbootstrap.com/docs/4.6/components/collapse/
