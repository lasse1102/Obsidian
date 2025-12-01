
--- 
Erstellt: 2025-11-06    10:53 
Tags: 
Link Up: [[CSS]]
Link Down:

--- 
# Was ist Scroll Snap
Scroll Snap ermöglicht es Single Page Seiten in mehrere Seiten (Sections) visuell zu unterteilen. Es sorgt dafür das der Scroll Mechanismus verändert wird. Hiermit können wir beispielsweise das flüssige Scrollen auf einer Seite unterbrechen und so Scrollen, dass wir zur nächsten Section gelangen und dort dann "einrasten".

Um dies zu ermöglichen müssen wir einen Container haben der das Scroll Snap ermöglicht und in diesem Container müssen wir die verschiedenen Sections haben, welche dann weiter CSS Eigenschaften bekommen

#### Scroll-Container
Auf das umschließende Elemente wendet man die `scroll-snap-type` Eigenschaft an.

|Eigenschaft|Wert|Beschreibung|
|---|---|---|
|`scroll-snap-type`|`y mandatory;`|**`y`**: Definiert die Scroll-Richtung (vertikal). **`mandatory`**: Erzwingt, dass der Browser immer an einem Snap-Punkt einrastet, sobald das Scrollen stoppt. Alternativ gibt es **`proximity`** (nächstgelegener Punkt wird nur bei geringer Entfernung eingerastet).|
|`overflow-y`|`scroll;`|Stellt sicher, dass das Element scrollbar ist.|
|`scroll-behavior`|`smooth;`|(Optional, aber empfohlen) Sorgt für einen weicheren Übergang beim Einrasten, wenn du zu den Sektionen navigierst, z.B. über interne Links.|
#### Snap-Elemente (deine Sektionen)
Auf die Kind-Elemente (deine Sektionen) wendest du die `scroll-snap-align` Eigenschaft an, um festzulegen, wo genau der Container einrasten soll.

|Eigenschaft|Wert|Beschreibung|
|---|---|---|
|`scroll-snap-align`|`start;`|Definiert, dass das Element einrastet, wenn seine **obere Kante** (bei vertikalem Scrollen) mit der sichtbaren Kante des Scroll-Containers übereinstimmt. Es gibt auch **`center`** und **`end`**.|
|`height`|`100vh;`|(Empfohlen für diesen Effekt) Stellt sicher, dass jede Sektion genau die Höhe des Viewports hat, was den "One-Page-Scroll"-Effekt erzeugt.|
### mandatory vs proximity

|Merkmal|`mandatory` (Obligatorisch)|`proximity` (Nähe)|
|---|---|---|
|**Einrastverhalten**|**Streng** (Strong Snapping)|**Locker** (Weak Snapping)|
|**Wann rastet es ein?**|Der Browser **muss** immer an einem definierten Snap-Punkt einrasten, wenn das Scrollen stoppt. Es ist fast unmöglich, in einem Zustand zu stoppen, der _nicht_ eingerastet ist.|Der Browser rastet nur dann an einem Snap-Punkt ein, wenn der Punkt **nah genug** an der Scroll-Position liegt.|
|**Bestes Einsatzgebiet**|Für Seiten, bei denen der Inhalt strikt sektionsweise angezeigt werden soll, z.B. bei **Full-Page-Scrolling** oder Bilder-Karussells, bei denen immer ein ganzes Bild sichtbar sein muss.|Für Seiten, bei denen das Einrasten eine Hilfe sein soll, aber der Benutzer auch **frei zwischen den Snap-Punkten** scrollen können soll.|


## References
1. 
