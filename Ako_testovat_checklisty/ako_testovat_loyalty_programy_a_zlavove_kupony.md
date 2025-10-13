# Ako testovať loyalty programy a zľavové kupóny<br><br>

Príklad<br>
Predstav si, že hotel ponúka 10 % zľavu pre vernostných hostí a 5 % kupón pre nových zákazníkov.  
Klient, ktorý má oba nároky, si rezervuje izbu počas akcie „Black Friday“.  
Ktorá zľava sa uplatní? V akom poradí? A čo ak sa kupón už raz použil?  
Takéto situácie sú bežné – preto je dôležité testovať kombinácie zliav, pravidlá použitia a prenos benefitov medzi kanálmi (web, aplikácia, call centrum).<br><br>

## Ako testovať<br><br>

1. **Registrácia a úroveň vernosti**<br>
- Over vytváranie profilu a pridelenie bodov po prvej objednávke.<br> 
- Kontroluj automatické zmeny úrovne (napr. Silver → Gold po 10 rezerváciách).<br>  
- Testuj reset bodov po expirácii alebo pri neaktivite.<br><br>  

2. ***Pridelenie a čerpanie bodov**<br>
- Vypočítaj body podľa typu služby, ceny a sezóny.<br>  
- Sleduj zaokrúhľovanie (napr. 9,50 € = 9 bodov alebo 10?).<br>  
- Over aktualizáciu konta po storne alebo refundácii.<br><br>  

3. **Zľavové kupóny a promo kódy**<br>
- Testuj formát kódu (dĺžka, znaky, case sensitivity).<br>  
- Over platnosť (dátum od–do, minimálna suma objednávky).  
- Simuluj neplatný, expirujúci a už použitý kupón.<br><br>  

4. **Kombinácie zliav**<br>
- Vyskúšaj poradie uplatnenia: zľava z akcie + kupón + body.<br>  
- Over, či systém správne uprednostní vyšší benefit.<br>  
- Testuj, že sa zľavy nesčítavajú v nepovolených kombináciách.<br><br>  

5. **Viackanálové prostredie**<br>
- Použitie kupónu na webe, v mobile a v pobočke – synchronizácia stavu.<br>  
- Testuj stav po offline rezervácii a následnej synchronizácii.<br>  
- Over správnu komunikáciu medzi frontendom a backendom (loyalty API).<br><br>  

6. **Bezpečnosť a zneužitie**<br>
- Otestuj duplicitné použitie kupónu, viacnásobné účty, skriptové útoky.<br>  
- Validuj, že zľavy sa nedajú uplatniť manuálnou úpravou v DOM alebo API.<br>  
- Over správne logovanie transakcií a audit zliav.<br><br>  

7. **Reporting a analytika**<br>
- Kontroluj správnosť sumárov (vyčerpané body, použité kupóny).<br>  
- Testuj prehľady pre marketing – počty aktívnych členov, úspešnosť kampaní.<br>  
- Over, že sa zľavy zobrazujú v účtovných a daňových výstupoch správne.<br>  
