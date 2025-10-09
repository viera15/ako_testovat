# Ako testovať dynamické ceny (sezóna, obsadenosť, akcie)

Príklad
Predstav si hotel, ktorý má počas leta vyššie ceny než v zime, ale zároveň poskytuje zľavy pri nižšej obsadenosti.  
Ak tester spustí rovnaký dopyt na rovnakú izbu v rôznych dátumoch, môže zistiť, že niekedy systém nezohľadňuje všetky podmienky – napríklad zľava sa uplatní aj počas top sezóny, hoci by nemala.  
Chyby v dynamickom cenníku môžu viesť k strate príjmov alebo nespokojnosti zákazníkov, ak vidia nekonzistentné ceny.

## Ako otestovať

1. **Základné scenáre**
- Porovnaj ceny za rovnaký typ izby v rôznych obdobiach (sezóna vs. mimo sezóny).  
- Skontroluj, či sa zmena sezóny prejaví automaticky podľa dátumu.  
- Over, že ceny sú aktualizované aj po zmene konfigurácie (napr. po úprave sezónneho kalendára).

2. **Obsadenosť**
- Testuj, ako systém reaguje na zmeny počtu dostupných izieb – či pri poklese dostupnosti rastie cena a naopak.  
- Simuluj masové rezervácie a sleduj, či sa ceny menia v reálnom čase.  
- Otestuj, či sa po stornovaní rezervácií ceny opäť znížia.

3. **Akcie a zľavy**
- Over kombináciu zliav (napr. *first minute* + vernostná karta + promo kód).  
- Otestuj, že sa zľava uplatní iba v období platnosti akcie a na správne produkty.  
- Skontroluj, či sa zľava neaplikuje opakovane alebo nad rámec povoleného maxima.

4. **Dynamický prepočet v čase**
- Sleduj správanie systému pri dopytoch v rôznych časoch dňa (napr. ceny sa menia raz za hodinu).  
- Otestuj, či systém používa aktuálne dáta (napr. nie cacheované staré ceny).  
- Over reakciu API – či vráti rovnakú cenu, ak rovnaký dopyt odošleš o pár sekúnd neskôr.

5. **Externé vplyvy**
- Over, ako systém reaguje na pripojené externé služby (napr. partneri typu Booking.com, Expedia).  
- Testuj synchronizáciu cien medzi interným systémom a verejným portálom.  
- Sleduj zaokrúhľovanie pri prepočtoch medzi menami a kurzami.

6. **Výkonnosť a presnosť**
- Otestuj správanie pri veľkom objeme dopytov (napr. 100 paralelných vyhľadávaní).  
- Zaznamenaj rozdiely medzi cenou zobrazenou na stránke a cenou v potvrdení objednávky.  
- Over, či systém loguje všetky prepočty (audit trail pre dohľadanie chyby).
