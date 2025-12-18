
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



---
# Todos heute
- [x] Bug Fixen, wenn Keine Daten Verfügbar sind, dass die Seitennummern auch nicht angezeigt werden ✅ 2025-12-17
- [ ] Items einbinden
- [ ] Testen
- [ ] Pushen
  
  
Hallo Yasmin, soweit fehlt bei dem Pickstatistik Tool nur noch die integration der Artikel. 
Wie wäre es am sinnvollsten die ganzen Artikel abzurufen?
Aktuell habe ich dafür eine DB Tabelle mit Beispieldaten (pick_statistics_items), dort würden dann aber täglich vermutlich Tausende von Zeilen hinzukommen, weil ich für jeden Tag alle verschiedenen Artikel speichere.
Wäre es in diesem Fall sinnvoller vielleicht die ganzen Artikel direkt aus dem WMS abzurufen basieren auf den eingegebenen Filter?




Die Frage die ich mir stelle ist, ob die DB Tabelle "pick_statistics_items" so sinnvoll ist, ich wüsste derzeit aber auch keine alternative wie man das sonst aufbauen sollte. 
Ich benötige halt für jeden Tag alle verschiedenen Artikel die gepicked wurden sind mit deren Anzahl wie viele gepicked wurden sind und wie oft man den Artikel gepicked hat.

Heißt konkret wenn nur heute 1500 verschiedene Artikel gepicked wurden sind, würden es auch 1500 neue Einträge in der Tabelle geben.
Oder wäre es hier vielleicht sinnvoll die Daten direkt aus dem WMS abzufragen und die Tabelle zu löschen?

## References
1. 
