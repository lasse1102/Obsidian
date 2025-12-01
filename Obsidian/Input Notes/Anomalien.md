
--- 
Erstellt: 2025-10-27    17:43 
Tags: 
Link Up: [[AP2]]
Link Down:

--- 

Datenbankanomalien sind ==Fehler und unerwünschtes Verhalten, die zu Dateninkonsistenzen führen, wenn Daten eingefügt, geändert oder gelöscht werden==. Sie entstehen meist durch unzureichende Normalisierung oder Datenredundanz, also durch doppelte und nicht optimal strukturierte Daten. Die drei Haupttypen sind die Einfüge-, Änderungs- und Lösch-Anomalie.

Arten von Datenbankanomalien
- **[Einfüge-Anomalie](https://www.google.com/search?client=firefox-b-d&sca_esv=cc90a75d2fff157b&channel=entpr&sxsrf=AE3TifNB3BzVXl2_dtqNozOC63rcB3tmoQ%3A1761583382815&q=Einf%C3%BCge-Anomalie&sa=X&ved=2ahUKEwjJo5m-6cSQAxVAS_EDHW9GFK0QxccNegQIMxAB&mstk=AUtExfAlQZiK5eVHJUatg9UIxTM3RJxQTXV5aotWGi4KAdOFLLs9zH3vjtvHCiZBlfCvNi2eI6vzt95nygXu6pKAbyfqzhz_jkN475LZqoJzPIivetkeYIyV_CVei9UfZetKnMtwL13e43oJBIBG04WscWNI3acxY7xfGn4_d9tP6FgNTHjbFJgV4DWfw2TbYx2Ld4Q74-HM2ciXYJWyDpC1PZ9i2HV08B1-nzRrz3gnb0Jk8FiJDrh9B7N2GR5t_2QBXJSCmdNPhpWW3sX5puBGTKvh&csui=3):**
    Ein neuer Datensatz kann nicht hinzugefügt werden, weil Daten fehlen, die für den Primärschlüssel erforderlich sind. Beispielsweise kann man keinen neuen Schüler anlegen, wenn dieser noch keinem Kurs zugeordnet ist, da die Kurszuweisung Teil des Primärschlüssels ist. 
- **[Änderungs-Anomalie](https://www.google.com/search?client=firefox-b-d&sca_esv=cc90a75d2fff157b&channel=entpr&sxsrf=AE3TifNB3BzVXl2_dtqNozOC63rcB3tmoQ%3A1761583382815&q=%C3%84nderungs-Anomalie&sa=X&ved=2ahUKEwjJo5m-6cSQAxVAS_EDHW9GFK0QxccNegQIehAB&mstk=AUtExfAlQZiK5eVHJUatg9UIxTM3RJxQTXV5aotWGi4KAdOFLLs9zH3vjtvHCiZBlfCvNi2eI6vzt95nygXu6pKAbyfqzhz_jkN475LZqoJzPIivetkeYIyV_CVei9UfZetKnMtwL13e43oJBIBG04WscWNI3acxY7xfGn4_d9tP6FgNTHjbFJgV4DWfw2TbYx2Ld4Q74-HM2ciXYJWyDpC1PZ9i2HV08B1-nzRrz3gnb0Jk8FiJDrh9B7N2GR5t_2QBXJSCmdNPhpWW3sX5puBGTKvh&csui=3):**
    Bei der Änderung eines Datenpunkts müssen alle redundanten Vorkommen geändert werden. Passiert dies nicht, entstehen widersprüchliche Daten. Zum Beispiel könnten sich Adressdaten nur in einigen Tabellenzeilen ändern und nicht in allen. 
- **[Lösch-Anomalie](https://www.google.com/search?client=firefox-b-d&sca_esv=cc90a75d2fff157b&channel=entpr&sxsrf=AE3TifNB3BzVXl2_dtqNozOC63rcB3tmoQ%3A1761583382815&q=L%C3%B6sch-Anomalie&sa=X&ved=2ahUKEwjJo5m-6cSQAxVAS_EDHW9GFK0QxccNegQIdRAB&mstk=AUtExfAlQZiK5eVHJUatg9UIxTM3RJxQTXV5aotWGi4KAdOFLLs9zH3vjtvHCiZBlfCvNi2eI6vzt95nygXu6pKAbyfqzhz_jkN475LZqoJzPIivetkeYIyV_CVei9UfZetKnMtwL13e43oJBIBG04WscWNI3acxY7xfGn4_d9tP6FgNTHjbFJgV4DWfw2TbYx2Ld4Q74-HM2ciXYJWyDpC1PZ9i2HV08B1-nzRrz3gnb0Jk8FiJDrh9B7N2GR5t_2QBXJSCmdNPhpWW3sX5puBGTKvh&csui=3):**
    Beim Löschen eines Datensatzes gehen unbeabsichtigt weitere, nicht zusammenhängende Daten verloren. Wenn ein Schüler, der auch eine Tutorin hatte, gelöscht wird, könnten auch die Daten der Tutorin verloren gehen, wenn beides in der gleichen Tabelle gespeichert ist
## References
1. 
