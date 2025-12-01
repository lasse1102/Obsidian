
--- 
Erstellt: 2025-09-06    22:41 
Tags: 
Link Up: 
Link Down:

--- 
# 💡 Props in React (Eigenschaften)

Props sind ein grundlegendes Konzept in React. Sie stehen für **Eigenschaften** (Properties) und dienen dazu, Daten von einer übergeordneten (Parent) Komponente an eine untergeordnete (Child) Komponente zu übergeben.

### Die wichtigsten Fakten zu Props:
* **Unidirektionaler Datenfluss:** Props fließen immer nur in eine Richtung: von Parent zu Child. Eine Child-Komponente kann Props lesen, aber sie nicht direkt ändern.
* **Sie sind "read-only":** Props sind unveränderlich (immutable). Innerhalb einer Komponente sollten sie wie konstante Werte behandelt werden.
* **Verwendung:** Du übergibst Props, indem du sie der Child-Komponente wie HTML-Attribute hinzufügst.

```jsx
// Parent-Komponente
function App() {
  return (
    <Greeting name="Anna" />
  );
}

// Child-Komponente
function Greeting(props) {
  return <h1>Hallo, {props.name}!</h1>;
}

## References
1. 
