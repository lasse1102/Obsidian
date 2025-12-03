
--- 
Erstellt: 2025-12-03    09:28 
Tags: 
Link Up: [[Tailwind]]
Link Down:

--- 
#### Wann nutzt man Flexbox?
Man nutzt es sobald man Elemente nebeneinander, zentriert, ausgerichtet oder flexible anpassbar darstellen will. 
Flexbox wird sowohl auf Horizontaler als auch auf Vertikaler Ebene verwendet.
1. Wenn Elemente nebeneinander statt untereinander stehen sollen
	Standardmäßig sind HTML-Elemente block-level und stehen untereinander. Mit Flexbox können wir sie Horizontal anordnen
	![[Pasted image 20251203093818.png]]
2. Wenn Elemente Horizontal oder Vertikal zentriert werden sollen
	![[Pasted image 20251203094228.png]]
3. Wenn der Verfügbare Platz verteilt werden soll
	Abstand zwischen Elementen
	![[Pasted image 20251203094249.png]]
4. Wenn Elemente dynamisch wachsen oder schrumpfen sollen
	![[Pasted image 20251203094316.png]]

---
# 📌 **Kurzvergleich: Flexbox vs Grid**
Hier ist die Entscheidungshilfe:

|Layout-Situation|Flexbox|Grid|
|---|---|---|
|Einfache Ausrichtung (horiz./vert.)|✔ perfekt|–|
|Elemente in eine Richtung (z. B. Navbar)|✔|–|
|Reihen oder Spalten einzeln|✔|✔|
|**Beide gleichzeitig (Reihen + Spalten)**|✖ schwer|✔ perfekt|
|Regelmäßige Card-Grids|funktioniert|✔ viel besser|
|Komplexe, responsive Layouts|teilweise|✔ ideal|
|Elemente exakt positionieren|begrenzt|✔|

---


## References
1. 
