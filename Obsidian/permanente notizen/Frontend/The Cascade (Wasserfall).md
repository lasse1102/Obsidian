
--- 
Erstellt: 2024-04-09    15:20 
Tags: 
Link Up: [[CSS]]
Link Down:

--- 
# Was ist das Cascade
Cascade ist ein Algorithmus zur Lösung von Konflikten, bei denen mehrere CSS Regeln für ein HTML-Element gelten. Er unterteilt sich in 4 Phasen, wobei die letzte Phase die ist die am meisten gewichtet wird(kann man sich wie beim Pokern vorstellen):
1. Position und Reihenfolge
	Dieser Algorithmus bestimmt die Reihenfolge der Selektoren, der letzte Selektor ist der Befehl den der Benutzer dann final sieht
	```CSS
		p{
		color:red;
		}	
		p{
		color:blue;
		}
	```
	In diesem Fall werden alle p Tags blau sein

1. Spezifikation
	Da die Spezifikation stärker gewichtet wird als die Position, wird dieser entscheidender sein. Dieser Algorithmus bestimmt welcher Selektor am wichtigsten ist die Reihenfolge sieht wie folgt aus:
	1. Element
	2. class
	3. attribute
	4. id -> am wichtigsten
	Der "Element" Sektor ist am schwächsten und der id Sektor ist am stärksten. 
	
1. Ursprung / Typ
	Dieser Algorithmus gewichtet danach, von wo sie her stammen, also ob sie von einer Extern, Intern oder Inline CSS stammen:
	1. Extern
	2. Intern
	3. Inline -> am wichtigsten
	
1. Wichtigkeit
	Einige CSS-Regeln werden stärker gewichtet als andere, insbesondere beim Regeltyp `!important`
	```Css
	p{
		color:red;
		}	
		p{
		color:blue !important;
		}
	```
In diesem Beispiel würde es blue werden



## Verdeutlichung 

![[Pasted image 20240409150124.png]]

## References
1. 

## Quellen
1. https://web.dev/learn/css/the-cascade?hl=de