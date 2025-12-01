
--- 
Erstellt: 2025-03-11    09:46 
Tags: #Programming/Allgemeines  
Link Up: [[Programming]]
Link Down:

--- 
# Was ist ein LookUp Table (LUT)
Ein LookUp Table ist eine Datenstruktur, die dazu dient, Werte schnell nachzuschlagen, anstatt sie zur Laufzeit aufwendig zu berechnen.

##### Grundidee
Statt aufwendige Funktion oder Berechnung mehrfach auszuführen, speichert man die Ergebnisse vorab in einer Tabelle und kann sie dann mit einem einfachen Indexzugriff abrufen. Das spart Rechenzeit und kann die Performance enorm verbessern.

## **Beispiel: Schnelles Nachschlagen in Datenbanken**

Ein **LookUp Table** kann auch eine kleine **Referenztabelle** sein, die IDs zu bestimmten Werten zuordnet.

```PHP
// LookUp Table für Statuscodes
$statusCodes = [
    200 => "OK",
    404 => "Not Found",
    500 => "Internal Server Error"
];

$code = 404;
echo "Status: " . $statusCodes[$code]; // Gibt "Not Found" aus
```

---
## **📌 Fazit**
Ein **LookUp Table** ist einfach ein **Array oder eine Tabelle**, die bereits berechnete Werte enthält, um schnellen Zugriff zu ermöglichen.

💡 **Nutzen:**
- Performance-Optimierung
- Reduzierung komplexer Berechnungen
- Direktes Nachschlagen von Werten

Benutzt wird es oft in **Mathematik, Grafikverarbeitung, Datenbanken** und vielen anderen Bereichen. 🚀
## References
1. 
