
--- 
Erstellt: 2025-12-03    11:14 
Tags: 
Link Up: [[Tailwind]]
Link Down:

--- 
# **1. Die Position-Klassen**
Tailwind benutzt die gleichen Konzepte wie CSS `position`:

| Tailwind-Klasse     | CSS-Äquivalent       | Bedeutung                                                                 |
| ------------------- | -------------------- | ------------------------------------------------------------------------- |
| `static` (Standard) | `position: static`   | Normale Positionierung, keine Veränderung                                 |
| `relative`          | `position: relative` | Element wird relativ zu seiner normalen Position verschoben               |
| `absolute`          | `position: absolute` | Element wird relativ zum nächsten `relative`-Elterncontainer positioniert |
| `fixed`             | `position: fixed`    | Element bleibt immer an der gleichen Stelle im Viewport                   |
| `sticky`            | `position: sticky`   | Element bleibt „kleben“, wenn man scrollt, innerhalb des Containers       |

---
# 🔷 **2. Die Positionierungs-Utilities**
Nachdem du `relative`, `absolute` usw. gesetzt hast, benutzt du **Offsets**:

|Tailwind-Klasse|CSS|
|---|---|
|`top-0`|`top: 0`|
|`right-0`|`right: 0`|
|`bottom-0`|`bottom: 0`|
|`left-0`|`left: 0`|
|`top-4`|`top: 1rem` (16px)|
|`inset-0`|`top: 0; right: 0; bottom: 0; left: 0`|

---
### **3. Beispiel: Absolute Positionierung innerhalb eines Containers**
![[Pasted image 20251203113645.png]]
**Erklärung:**
1. `relative` auf dem Container → macht den Container zur Bezugsebene für das absolute Element.
2. `absolute bottom-4 right-4` → Button wird **unten rechts** innerhalb des Containers positioniert.
3. `p-2` und `bg-blue-500` → nur Styling.
>Man nutzt React, als Bezugspunkt für absolute Positionierung, indem ein übergeordnetes Element `position: relative` erhält und absolute Elemente innerhalb dieses Element positioniert werden können.

**Wann nutzt man es:**
- Wenn ein Element **genau an einer Position innerhalb eines Containers** sitzen soll
- Es wird aus dem normalen Layoutfluss genommen

---
### **4. Fixed Position (immer sichtbar)**
![[Pasted image 20251203114428.png]]
→ Button bleibt immer **unten rechts im Viewport**, egal wie viel gescrollt wird.

**Wann nutzt man es:**
- Wenn ein Element **immer sichtbar bleiben soll** egal wie die Seite gescrollt wird
	Beispiel:
	- "Zurück nach oben" Button am Bildschirmrand
	- Sticky Navigation, die Permanent oben bleibt

---
### 5. Sticky Position (klebt beim Scrollen)
![[Pasted image 20251203114732.png]]
→ `sticky` + `top-0` = Element bleibt oben sichtbar, bis der Container vorbei gescrollt ist.

**Wann nutzt man es:**
- Wenn ein Element nur innerhalb eines Containers kleben soll, während gescrollt wird
- Es verhält sich wie `relative` bis zu einem Punkt und "klebt" dann

---


## References
1. 
