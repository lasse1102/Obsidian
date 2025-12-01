
--- 
Erstellt: 2025-10-17    09:48 
Tags: 
Link Up: [[AP2]]
Link Down:

--- 
**Ziel:** Darstellung eines endlichen Automaten, um das Verhalten eines Systems zu visualisieren. Dabei werden sowohl Aktionen unterstützt, die vom Zustand des Systems und einem auslösenden Ereignis abhängen, als auch Eintritts- und Austritts-Aktionen, die eher zustands- als aktionsorientiert sind (wie in Moore-Automaten).

Beispiel:
![[Pasted image 20251017095310.png]]

---

#### Bestandteile
- **Start/Stopp:** Einstieg und Ausstieg in den Ablauf werden analog zum Aktivitätsdiagramm dargestellt
- **Zustände:** Die einzelnen Zustände werden mit abgerundeten Rechtecken dargestellt
- **Zustandsübergänge(Pfeile):** Auch Transitionen genannt
![[Pasted image 20251017111854.png]]

---
**Effekte:** Effekte sind Aktionen, die ausgeführt werden, wenn ein **Übergang (Transition)** zwischen Zuständen stattfindet
**Guards:** sind boolesche Ausdrücke oder Bedingungen die erfüllt sein müssen, damit ein Übergang überhaupt stattfinden kann.

![[Pasted image 20251017112353.png]]
- `pruefe` ist in diesem Fall ein Effekt welches beim Übergang zwischen "Beantragt" und "Geprueft" stattfindet.
- `genehmige`, `lehnte ab`, `beende`, sind ebenfalls 3 Effekte die basierend auf den Guards ausgeführt werden
- Die werte in eckigen Klammern sin Guards, welche wie Bedingungen sind, also sie bestimmen wann die Effekte ausgeführt werden

---
**Verhaltensspezifikation:** Zustände können Verhalten beschreiben, das ausgeführt wird, sobald der Zustand eintritt (entry), wenn er verlassen wird (exit) oder während der gesamten Lebenszeit des Zustands (do)
![[Pasted image 20251017122336.png]]

WICHTIG: Die Verhaltensspezifikation ist nur eine andere Form von Effekten und Guards, sie können das gleiche darstellen. Am besten auf eines von den beiden konzentrieren (trotzdem wissen wie beides Funktioniert)


























## References
1. 
