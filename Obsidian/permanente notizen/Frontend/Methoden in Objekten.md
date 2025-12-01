
--- 
Erstellt: 2024-05-27    15:38 
Tags: 
Link Up: [[JavaScript]]
Link Down:

--- 
# Eine Methode in einem Objekt hinzufügen
```js
let konto_3 = {  
    iban: "DE7563429763234644",  
    bic: "GHEROWGWNOIE",  
    inhaber: {  
        vorname: "Svea",  
        nachname: "Wildhagen",  
        geschlecht: "weiblihc",  
        alter: 18,  
        greet: function (){  
            console.log(`Hallo ${vorname} ${nachname}`)  
        }  
    },  
    kontostand: 2500,    
    einzahlen:(value){  
        this.kontostand += value  
    },  
    auszahlen:(value){  
        this.kontostand -= value  
    }  
}  
  
konto_3.auszahlen(1000)  
console.log(konto_3.kontostand) // Ausgabe 1500
```
Seit ECMA 6 kann man für eine kürzere Schreibweise das keyword function vor der Parametern weglassen.

## References
1. 

## Quellen
1. 