
--- 
Erstellt: 2025-09-06    00:17 
Tags: 
Link Up: 
Link Down:

--- 

### Was sind Hooks
Hooks sind spezielle JavaScript-Funktionen in der React-Bibliothek, die es Entwicklern ermöglichen, den Zustand (State) und den Lebenszyklus (Lifecycle) von Komponenten in funktionsbasierten Komponenten zu verwalten. Bevor es Hooks gab, waren diese Funktionen ausschließlich in klassenbasierten Komponenten verfügbar.

### Warum wurden Hooks eingeführt
Vor der Einführung von Hooks im Jahr 2019 wurden viele komplexe Funktionen in React mithilfe von **klassenbasierten Komponenten** realisiert. Diese waren oft schwer zu lesen, zu verstehen und zu testen, da sie häufig komplizierte Logik in den verschiedenen Lebenszyklus-Methoden (wie `componentDidMount` oder `componentDidUpdate`) verteilten.

Hooks wurden eingeführt, um dieses Problem zu lösen und die Entwicklung von React-Anwendungen zu vereinfachen. Mit ihnen kann man nun auch **funktionale Komponenten** nutzen, die in der Regel kürzer, übersichtlicher und leichter zu testen sind. Ein wesentlicher Vorteil ist, dass man Zustand- und Logikmanagement zentralisieren kann, ohne die Komponente zu sehr aufzublähen.

## Die verschiedenen Hooks und wie sie funktionieren

**`useState`**: Dieser Hook ermöglicht es, einen **Zustand** zu einer funktionalen Komponente hinzuzufügen. Er gibt ein Paar von Werten zurück: den aktuellen Zustandswert und eine Funktion, um diesen Wert zu aktualisieren. Ein klassisches Beispiel ist das Zählen von Klicks auf einen Button.
![[Pasted image 20250907115455.png]]

**`useEffect`**: Mit diesem Hook können **Nebeneffekte** (Side Effects) in funktionalen Komponenten ausgeführt werden. Nebeneffekte sind Aktionen, die außerhalb der normalen Render-Schleife der Komponente stattfinden, wie z.B. das Abrufen von Daten von einer API, das Setzen eines Timers oder das Manipulieren des DOM.































## References
1. 
