
--- 
Erstellt: 2025-09-02    06:47 
Tags: 
Link Up: 
Link Down:

--- 
### Pagination

1. Wann werden die Tabellen aktualisiert
	- Beim Laden der Seite
	- Beim Filtern 
	- Beim wechseln von der Section (Orders, Orderlines, Units) nicht!
		- Es wird immer alles schon geladen basierend auf dem Filter.
		- Es ändert sich lediglich die Sichbarkeit von den tabs (active = true)

2. handleResponse beinhaltet 3 Funktionen zum erstellen von Orders, Orderlines und Units
	- Jede build Funktion wird mit dem Ersetzt was im HTML vordefiniert ist
	- im HTML wird es dann draus gelöscht

3. paginationAjaxCall(page)
	1. Wann wird es aufgerufen
		- Wird beim Laden der Seite aufgerufen
		- Wird beim ändern des Filters aufgerufen
		- Wird beim ändern der Seiten Zahl aufgerufen (Vor, Zurück, Bestimmte Seite)
	- holt immer die Entries für Orders, Orderlines und Units aus dem Backend **für die richtige Seite**

4. Im Backend muss implementiert werden welche Entries zu welcher Seite gehören
	- Datenstruktur bleibt gleich aber wie gesagt nur mit der richtigen Entries basierend auf (maxAnzahl und PageNumber)
	- Gegebenenfalls Model Klassen bauen zum Veranschaulichen wie das Geschäftsobjekt aufgebaut ist














## References
1. 
