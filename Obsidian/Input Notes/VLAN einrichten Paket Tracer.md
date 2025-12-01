
--- 
Erstellt: 2024-11-21    14:51 
Tags: #School/LF09/VLANs 
Link Up: [[VLANs]]
Link Down:

--- 
# Konfiguration

| Befehl                             | Kurzform                    | **Beschreibung**                                                 |
| ---------------------------------- | --------------------------- | ---------------------------------------------------------------- |
| enable -> usermode                 | en                          |                                                                  |
| show vlan brief                    | sh vlan brief               |                                                                  |
| show mac-adress-table              | sh mac-address-table        | Zeigt die Zuweisung der Vlans                                    |
| config terminal ->privilidged mode | conf t                      | ab hier kann man sachen ändern                                   |
| vlan 10                            |                             | den Vlan den wir bearbeiten wollen                               |
| interface fastethernet0/1          |                             |                                                                  |
| switchport mode access             |                             |                                                                  |
| switchport access vlan 10          |                             |                                                                  |
| interface range fa 0/3-4,12        | int range fa 0/3-4, fa 0/12 | Wenn man mehrere Schnitstellen direkt einen Vlan zuweisen wollen |
| no switchport access fa0/1         |                             | Einen Vlan entfernen                                             |


## References
1. 
