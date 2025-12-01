
--- 
Erstellt: 2025-09-16    15:15 
Tags: 
Link Up: 
Link Down:

--- 
Dies ist eine kleine Liste der wichtigsten Array-Funktionen die in React oft benötigt werden.

### `map()`
Die am häufigsten verwendete Funktion in React. Sie wird verwendet, um eine Liste von Elementen zu transformieren und sie in einer neuen Liste zu speichern. In React wird `map()` typischerweise verwendet, um für jedes Element in einem Array eine Komponente zu erstellen, also Daten in ein JSX-Element umzuwandeln und dann zu rendern.
```JSX
const pizzaData = [
  {
    name: "Focaccia",
    ingredients: "Bread with italian olive oil and rosemary",
    price: 6,
    photoName: "pizzas/focaccia.jpg",
    soldOut: false,
  },

  {
    name: "Pizza Margherita",
    ingredients: "Tomato and mozarella",
    price: 10,
    photoName: "pizzas/margherita.jpg",
    soldOut: false,
  },
  ...
];

{pizzaData.map((pizza) => (
   <Pizza pizzaObj={pizza} />
 ))}
```
Hier wird für jedes Element in pizzaData eine neue Komponente erzeugt, indem wir der Komponente die Daten als Props mitgeben

<mark style="background: #FFB86CA6;">**Tipp: Mit forEach geht das nicht, da wir JSX zurückgeben müssen und das machen wir mit map(), da wir dort ein neues Array zurückgeben. Mit forEach würden wir kein JSX zurückgeben**</mark>

---
### filter()`

### `reduce()`

### `slice()`

## References
1. 
