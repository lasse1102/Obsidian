
--- 
Erstellt: 2025-09-04    07:46 
Tags: #Programming/JavaScript/React
Link Up: [[JavaScript]]
Link Down:

--- 

## Was ist das Virtual DOM
Das Virtual DOM ist eine leichtgewichtige Kopie des echten DOMs, das aus JavaScript-Objekten besteht. Wenn sich der Zustand der Anwendung ändert, passiert Folgendes:
- **Erstellung des neuen Virtual DOMs:** Die Rendering-Logik der Anwendung wird erneut ausgeführt, was ein neues Virtual DOM erzeugt, das den neuen Zustand widerspiegelt.
-  **Differenzierung (Diffing):** Das neue Virtual DOM wird mit dem alten Virtual DOM verglichen. Der Algorithmus, der diesen Vergleich durchführt, nennt man **Diffing-Algorithmus**. Er ermittelt die genauen Unterschiede zwischen den beiden virtuellen Bäumen.
- **Anwendung der Änderungen:** Nur die identifizierten Unterschiede werden auf das **echte DOM** angewendet. Dies ist ein entscheidender Schritt, da direkte Manipulationen des echten DOMs sehr kostspielig sein können, insbesondere bei komplexen Benutzeroberflächen.


### Vorteile
- **Leistung:** Der Hauptvorteil des Virtual DOMs liegt in der **Verbesserung der Leistung**. Da die Änderungen am echten DOM minimiert werden, sind die Updates der Benutzeroberfläche schneller und effizienter
- Es bietet eine höhere Abstraktionsebene für die Entwicklung, was zu saubererem und wartbarem Code führt, da die Benutzeroberfläche als eine Funktion des Anwendungszustands behandelt wird.


<mark style="background: #FFF3A3A6;">Merke: **Der Virtual DOM sammelt alle kleinen Änderungen und führt sie als eine einzige, effiziente Aktualisierung auf das echte DOM aus.** Das spart Zeit und Rechenleistung, da nicht für jede Änderung das gesamte DOM aktualisiert werden muss.</mark>


## References
1. [[Was ist das DOM]]
