
--- 
Erstellt: 2025-11-05    07:53 
Tags: 
Link Up: [[TypeScript]] 
Link Down:

--- 

### Wie ist die backend Struktur in einem Projekt aufgebaut?
Wenn man Daten in der Datenbank verwaltet oder Formularvalidierung, benötigt man immer ein entsprechendes Backend/server setup um die Daten dort zu verarbeiten. Wenn die Daten nur statisch auf einer Website sind und dort keine Formularvalidierung oder sonst was zustande kommt, wird nicht zwingend ein Backend benötigt. Dennoch ist es ratsam immer das backend

**Struktur:**
Um das backend sinnvoll einzurichten benötigen wir eine Architektur mit dieser wir das darstellen. Beispielsweise das MVC (Model-View-Controller).
Hierfür benötigen wie folgende Ordner/Klassen, um die Geschäftslogik sinnvoll voneinander zu trennen
- api/routes
	Diese routen sind der Einstiegspunkt. Sie nehmen die url's an, die der User in den Browser eingibt und leiten danach die Aufgabe an den Controller weiter, welcher dann die Geschäftslogik enthält.
- controller
	Der Controller enthält die Geschäftslogik der Anwendung, hier werden alle Funktionen geschrieben, welche essenziell sind, um die Funktionalität der Anwendung zu gewährleisten. Anschließend senden sie das Ergebnis an den Client wieder zurück
- model
	Modells definieren die Struktur, die Datentypen und Methoden einzelner Geschäftsobjekte, diese können dann vom Controller verwendet werden

###### Wann benötigt man diese Struktur?
Sobald das Projekt zustandlos (statful) wird, d.h. wenn Daten gespeichert, geändert oder dynamisch behandelt werden, benötigt man routen, controller und Modells, um die API abfragen zu verarbeiten.


# Wie sieht die Struktur im Frontend aus?
Je nachdem welches Frontend Framework man nutze, kann die Struktur ein wenig anders aussehen. Mit React und vite
## References
1. 
