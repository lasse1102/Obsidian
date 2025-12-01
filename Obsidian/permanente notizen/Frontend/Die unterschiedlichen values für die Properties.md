
--- 
Erstellt: 2024-04-09    12:35 
Tags: 
Link Up: [[CSS]]
Link Down:

--- 
# Unterschiede zwischen 1px / 1pt / 1em / 1rem
1px:
- entsprechen 0,26mm
1pt:
- entsprechen 0,35mm
1em:
- entspricht die Größe des Eltern Elementes
```css
<div class="content" style="font-size:1.0em"> 
	<h2 style="font-size:2.5em">Eine Headline</h2> 
</div>
```
Eine Überschrift **h2** sitzt in einem Container mit der CSS-Klasse „content“.  
Als Schriftgröße (_font-size_) für den Container sind 1.0em definiert – in der Regel entspricht das 16 Pixeln. Eine **h2**, deren Größe mit 2.5em angegeben ist, hat also die 2,5-fache Größe. Aber 2,5 wovon? Der Faktor 2,5 bezieht sich auf den Wert, der im Container „content“ festgelegt ist, das ist die font-size: 1.0em. Wenn man nun 1.0em mit 16 Pixeln gleich setzt, wären das also 16 Pixel *2,5= 40 Pixel.

1rem:
- entspricht die Größe des root Elements, im Normalfall ist es das html Element

### Und warum nicht einfach Pixel?

Eigentlich ist nichts falsch an Pixeln. Die Handhabung ist denkbar einfach und man muss sich nicht viel denken. Die Einheit Pixel ist allerdings nicht flexibel. 16 Pixel sind immer 16 Pixel, ganz gleich, was um sie herum passiert.  
Wenn jemand beispielsweise in seinem Browser die Schriftgröße verändert, weil er alles ein bisschen größer sehen möchte, reagieren Texte, bei denen die Schriftgröße in Pixel angegeben ist, nicht auf diese Einstellung. Ist die Schriftgröße in em oder rem angegeben, skaliert der Text.

Aus demselben Grund sind Pixel für das Responsive Design ein bisschen unpraktisch. Das Arbeiten mit relativen Einheiten hat hier einige Vorteile.
## References
1. 
## Quellen
1. 