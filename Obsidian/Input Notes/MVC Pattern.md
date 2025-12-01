
--- 
Erstellt: 2025-10-13    08:31 
Tags: 
Link Up: [[Design Patterns]]
Link Down:

--- 
# MVC - Pattern
![MVC-Process](https://fachinformatikerpruefungsvorbereitung.de/abschlusspr%C3%BCfungteil2ae/ga2/mvc/MVC-Process.svg)

### Komponenten[](https://fachinformatikerpruefungsvorbereitung.de/abschlusspr%C3%BCfungteil2ae/ga2/mvc/#komponenten)
Außer das Aufteilen einer App in die folgenden Komponenten definiert dies Pattern auch die Kommunikation zwischen den einzelnen Teilen.

- Modell: Verantwortlich für das Management der Daten der App. Bekommt den User-Input vom Controller.
- View: Rendert die Präsentation der Anwendung in welcher Form das auch immer sein muss
- Controller: Reagiert auf den Input von Usern und interagiert mit dem Modell. Er empfängt Input validiert ihn gegebenenfalls und gibt ihn dann an das Modell weiter.

#### Modell[](https://fachinformatikerpruefungsvorbereitung.de/abschlusspr%C3%BCfungteil2ae/ga2/mvc/#modell)
Das Modell ist die Zentrale Komponente des Patterns. Es ist die unter Umständen dynamische Datenstruktur der App. Es ist unabhängig vom User-Interface.

#### View 🌄[](https://fachinformatikerpruefungsvorbereitung.de/abschlusspr%C3%BCfungteil2ae/ga2/mvc/#view-)
Die View beinhaltet alle möglichen Arten der Präsentation der Daten. Es sind auch mehrere Views für die selben Daten möglich. Dies kann nützlich sein wenn eine Information für verschiedene Personengruppen dargestellt werden soll.

Zum Beispiel: Diagramme, Tabellen

#### Controller 🎮[](https://fachinformatikerpruefungsvorbereitung.de/abschlusspr%C3%BCfungteil2ae/ga2/mvc/#controller-)
Der Controller verarbeitet Input und wendet diesen anhand von Befehlen an Model oder View an.

## References
1. 
