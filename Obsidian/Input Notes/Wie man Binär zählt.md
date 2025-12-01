
--- 
Erstellt: 2025-02-03    11:12 
Tags: #IT/Einführung 
Link Up: [[Digitale Logik]]
Link Down:

--- 
## **Binärsystem: Die Grundlage der Computerkommunikation**

### **Warum ist Binär wichtig?**

- Binär wird nicht nur für **Text & Bilder**, sondern auch in Bereichen wie **Netzwerke & Sicherheit** genutzt.
- IT-Spezialisten müssen verstehen, **wie Binärzahlen funktionieren** und wie sie in dezimale Werte umgerechnet werden.

### **Binär vs. Dezimal**

- Menschen nutzen das **Dezimalsystem (Basis 10)** → Zahlen von **0 bis 9**.
- Computer nutzen das **Binärsystem (Basis 2)** → nur **0 & 1**.
- Alle Zahlen lassen sich mit **Bits (1 oder 0)** darstellen.
### **Beispiel: Binär → Dezimal**

- Binär: **00001010**
- Aktive Werte (1er): **8 + 2 = 10**
- Dezimalzahl: **10** ✅

### **ASCII & Binär**

- **ASCII-Tabelle** nutzt Binärcodes für Zeichen.
- Beispiel:
    - Buchstabe **h** in Binär: **01101000**
    - In Dezimal: **104**
    - Berechnung: **64 + 32 + 8 = 104** ✅

# Umwandlung
### Grundlagen
- Computer kommunizieren in Binär (0 und 1).
- Binärwerte können in Dezimalwerte und Zeichen umgewandelt werden.
- Jedes Bit in einem Byte hat einen spezifischen Wert: **128, 64, 32, 16, 8, 4, 2, 1**.
- Ein Byte kann Werte von **0 bis 255** darstellen.

### Umwandlung
- **Binär → Dezimal**: Addiere die Dezimalwerte der gesetzten Bits (1).
    - **Beispiel**: `10011101` = **157** (128+16+8+4+1).
- **Dezimal → Binär**: Zerlege die Zahl in die größten passenden Zweierpotenzen.
    - **Beispiel**: `87` → **01010111** (64+16+4+2+1).

### [[Zeichencodierung]]
- **ASCII**: 1 Byte pro Zeichen (max. 256 Zeichen).
    - **Beispiel**: `01100001` = **97** = `a`.
- **UTF-8**: Erweiterung von ASCII, unterstützt mehr Zeichen inkl. Emojis.
## References
1. 
