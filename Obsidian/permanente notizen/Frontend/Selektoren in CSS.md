
--- 
Erstellt: 2024-04-09    09:22 
Tags: 
Link Up: [[CSS]]
Link Down:

--- 
# Was sind Selektoren
Mit CSS-Selektoren legt ihr fest, welche Bereiche im HTML-Code ausgewählt werden, damit ein Styling darauf angewendet werden kann. Die Kunst liegt u.a. darin, mit möglichst schlankem Code treffsicher die gewünschten Elemente auszuwählen.

# Attribute Selektor
Syntax:
```css
li[value]{
color: blue;
}
```
Hierbei werden alle li Elemente die einen value Wert haben angesprochen

Spezifischer:
```css
li[value="Test"]{
color: blue;
}
```
Hier werden alle li Elemente die einen value Wert "Test" haben angesprochen

# Universal Selektor

Mit den Universal Selektor wird alles angesprochen auf der Seite
```css
*{
font-size: 40px;
}
```

## References
1. 

## Quellen
1. 