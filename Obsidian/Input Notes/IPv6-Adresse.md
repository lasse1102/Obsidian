
--- 
Erstellt: 2025-03-19    10:09 
Tags: #School/LF03 
Link Up: [[School]]
Link Down:

--- 
## 1. Grundlegender Aufbau einer IPv6-Adresse

- Eine IPv6-Adresse besteht aus **128 Bit**.
- Sie ist in **8 Blöcke** zu je **16 Bit** unterteilt.
- Die Blöcke werden **hexadezimal** geschrieben und durch Doppelpunkte (`:`) getrennt.

**Beispiel:**

```
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

### 1.1. Warum 16 Bit pro Block?
- IPv6-Adressen werden in **Hexadezimaldarstellung** geschrieben.
- **1 Hexadezimalziffer = 4 Bit**.
- Ein Block mit **4 Hex-Zeichen** entspricht daher: **4 × 4 Bit = 16 Bit**.
- Ein einzelner 16-Bit-Block kann **65.536 verschiedene Werte** annehmen (`0000` bis `FFFF`).

## 2. Adressstruktur in IPv6
Eine IPv6-Adresse ist in zwei Hauptteile unterteilt:

|**Teil**|**Größe**|**Bedeutung**|
|---|---|---|
|**Netzwerk-Präfix**|**64 Bit**|Identifiziert das Netzwerk (ähnlich wie Netz-ID in IPv4)|
|**Interface Identifier**|**64 Bit**|Eindeutige Adresse des Geräts im Netzwerk|

**Beispiel:**

```
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

- **2001:0db8:85a3** → Netzwerk-Präfix (64 Bit)
- **0000:0000:8a2e:0370:7334** → Interface Identifier (64 Bit)

> Der Interface Identifier kann aus der **MAC-Adresse** generiert werden (EUI-64-Verfahren).

## 3. Verkürzung von IPv6-Adressen
Da IPv6-Adressen sehr lang sind, gibt es Regeln zur **Verkürzung**:

|**Regel**|**Beispiel**|
|---|---|
|**Führende Nullen in einem Block weglassen**|`2001:0db8:0000:0000:0000:ff00:0042:8329` → `2001:db8:0:0:0:ff00:42:8329`|
|**Lange Ketten von `0000`-Blöcken durch `::` ersetzen**|`2001:db8:0:0:0:ff00:42:8329` → `2001:db8::ff00:42:8329`|

⚠️ **Regel:** `::` darf **nur einmal** in einer Adresse vorkommen!

## 4. Weitere wichtige Konzepte
- **Link-Local-Adressen** (`fe80::/10`): Automatisch vergebene Adressen für lokale Netzwerke.
- **Global Unicast** (`2000::/3`): Öffentlich routbare IPv6-Adressen.
- **Multicast-Adressen** (`ff00::/8`): Adressen für Gruppenkommunikation.
- **Keine Broadcasts**: Stattdessen **Multicast & Anycast**.

---




## References
1. 
