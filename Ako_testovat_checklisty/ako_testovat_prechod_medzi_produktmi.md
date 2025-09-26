# Ako testovať prechod medzi produktmi (napr. z osobného účtu na podnikateľský)<br><br> 

Príklad<br><br>

Predstav si klienta, ktorý doteraz používal osobný účet. Rozhodne sa založiť živnosť a banka mu ponúkne prechod na podnikateľský účet. 
Ak by systém nepreklopil správne všetky údaje – trvalé príkazy, limity, história transakcií či prístup do internet bankingu – klient sa môže dostať do problémov. Nefunkčné inkaso alebo zle nastavený limit znamená oneskorené platby dodávateľom a nespokojnosť zákazníka. Preto je testovanie takéhoto prechodu kľúčové.<br><br> 

## Ako otestovať<br><br> 

1. **Validácia údajov klienta**<br>
- Skontroluj, či sa pri prechode prenesú základné údaje (meno, adresa, kontakty).<br> 
- Over, že zostanú zachované nastavenia prístupov pre všetkých oprávnených používateľov.<br><br> 

2. **Trvalé príkazy, inkasá a platobné šablóny**<br>
- Otestuj, či sa správne prekopírujú všetky existujúce platobné inštrukcie.<br> 
- Over funkčnosť inkás a pravidelných platieb po prechode.<br><br> 

3. **História a zostatky**<br>
- Skontroluj, že história transakcií zostane prístupná aj po migrácii.<br> 
- Otestuj správnosť zostatku – žiadne duplicitné ani chýbajúce transakcie.<br><br>

4. **Limity a oprávnenia**<br>
- Over, že nové produktové limity (napr. vyššie limity podnikateľského účtu) sú nastavené správne.<br> 
- Testuj, či sa oprávnenia administrátora a ďalších používateľov prispôsobia typu účtu.<br><br> 

5. **Integrácie a prístup cez kanály**<br>
- Skontroluj fungovanie internetového a mobilného bankovníctva po prechode.<br> 
- Otestuj prepojenia s účtovnými softvérmi alebo API, ak ich klient využíva.<br><br> 

6. **Notifikácie a komunikácia**<br>
- Over, či klient dostane správne informácie o zmenách produktu (e-mail, SMS, správy v aplikácii).<br> 
- Otestuj, či sú nové notifikácie nastavené podľa pravidiel podnikateľského účtu.<br><br> 

7. **Negatívne scenáre**<br>
- Čo sa stane, ak počas prechodu príde do systému nová transakcia?<br> 
- Ako sa správa systém, ak prechod zlyhá uprostred procesu? Má rollback mechanizmus?<br> 
