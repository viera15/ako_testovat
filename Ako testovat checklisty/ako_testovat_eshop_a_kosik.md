# Ako testovať e-shopovú objednávku – od košíka po potvrdenie?<br><br>

Predstavte si, že testujete e-shop s oblečením. Zákazník si do košíka pridá tričko a bundu. Vyberie osobný odber v Bratislave a platbu kartou. V poslednom kroku sa však suma zrazu zvýši – bez dôvodu. Takéto situácie musíme odhaliť pred tým, než sa dostanú k zákazníkovi.<br><br>

Na čo všetko sa zamerať pri testovaní objednávky?<br><br>

1. **Košík**<br>
- Správne načítané produkty, ceny, zľavy, dostupnosť<br>
- Množstevné zmeny a ich vplyv na cenu<br>
- Odstránenie produktu, aktualizácia košíka<br><br>

2. **Doprava a platba**<br>
- Rôzne kombinácie spôsobov dopravy a platby (osobný odber, kuriér, dobierka, platba kartou, prevodom...)<br>
- Správne vypočítané ceny dopravy, vrátane prípadných výnimiek (napr. doprava zadarmo od 50 €)<br>
- Overenie podmienok – čo sa stane, ak nie je zvolený žiadny spôsob dopravy<br><br>

3. **Overenie objednávky**<br>
- Zobrazenie súhrnu: produkty, doprava, spôsob platby, celková cena vrátane DPH<br>
- Súlad medzi tým, čo je v košíku, a tým, čo sa posiela na server<br>
- Funkčnosť tlačidla „Objednať“<br><br>

4. **Technické chyby a výpadky**<br>
- Výpadok platobnej brány – čo sa zobrazí používateľovi?<br>
- Timeout pri odosielaní objednávky<br>
- Duplikovanie objednávky pri opakovanom kliknutí<br><br>

5. **Cenové nezrovnalosti**<br>
- Nesúlad medzi zobrazenou a účtovanou cenou<br>
- Dvojité uplatnenie zľavového kódu<br>
- Manipulácia s HTML (napr. pokus zmeniť cenu v košíku cez vývojárske nástroje)<br><br>

6. **Notifikácie a potvrdenie**<br>
- Správne odoslaný e-mail / SMS s potvrdením<br>
- Obsah potvrdzovacieho e-mailu – produkty, cena, spôsob platby a dopravy<br>
- Prístup používateľa k detailu objednávky po prihlásení<br><br>

7. **Prístupnosť a použiteľnosť**<br>
- Viditeľnosť chybových hlášok (napr. pri chýbajúcich údajoch)<br>
- Čitateľnosť a orientácia v krokoch nákupu<br>
- Správne fungovanie s čítačkami obrazovky<br><br>

Aj keď ide len o „bežný nákup“, cesta od košíka po potvrdenie má veľa kritických bodov. Odhaľme ich skôr, než to spraví zákazník.<br><br>

#testing #QA #eshop #automatizacia #UXtesting #manualtesting #testovanie



