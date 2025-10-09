# Ako testovať storno podmienky a vrátenia peňazí

Príklad
Klient A si rezervuje izbu online s možnosťou bezplatného zrušenia do 48 hodín. Po 24 hodinách zmení plány a rezerváciu zruší – očakáva vrátenie celej sumy na kartu do 5 pracovných dní. Systém však vráti iba čiastočný kredit (bez poplatku za spracovanie) a email o vrátení peňazí neobsahuje sumu – zákazník volá na podporu. Takýto prípad odhalí chyby v nastavení pravidiel, vo výpočte poplatkov aj v textoch oznámení.

## Ako testovať

1. **Zmapovať pravidlá a scenáre**
- Získať od produktového tímu alebo právnikov presné podmienky storna (lehoty, poplatky, výnimky, vrátenie formou poukazu alebo hotovosti).  
- Vybrať testovacie situácie: bezplatné zrušenie, zrušenie s poplatkom, zrušenie po lehote (tzv. noshow), čiastočné zrušenie, vrátenie cez poukaz, vrátenie na pôvodnú platobnú metódu, prípadne reklamácia platby (chargeback).  

2. **Funkčné testy vrátenia peňazí**
- Otestovať každý typ storna: vytvoriť rezerváciu → zrušiť v rôznych časoch pred príchodom → overiť vrátenú sumu (vrátené = zaplatené – poplatok).  
- Overiť, že sa peniaze vracajú správnym spôsobom: karta, bankový prevod, poukaz, interný kredit.  
- Skontrolovať čiastočné vrátenia (napr. zrušenie len doplnkovej služby) a ich správne spočítanie.  
- Otestovať rôzne spôsoby platby – platobná karta, Google Pay, terminál, platobná brána.  

3. **Testy prepojenia s platobnou bránou alebo bankou**
- Nasimulovať rôzne odpovede: úspešné vrátenie, čakajúce, zamietnuté, prerušené spojenie, duplicitné požiadavky.  
- Overiť prevod stavov medzi bránou a systémom (napr. VRÁTENÉ, ČAKÁ NA VRÁTENIE, NEPODARILO SA).  
- Otestovať správanie pri chybách siete a opakované pokusy o vrátenie (systém by mal zabrániť duplicitám).  

4. **Výpočty, zaokrúhľovanie a cudzie meny**
- Overiť výpočty pri rôznych menách (prevody, kurz, zaokrúhľovanie).  
- Testovať hraničné prípady zaokrúhľovania (napr. 0,005 podľa bankových pravidiel).  
- Skontrolovať, kto účtuje poplatky (hotel, partner, banka) a či sú správne uvedené v potvrdení.  

5. **Súbežnosť a hraničné situácie**
- Simulovať paralelné akcie: zákazník ruší, podpora mení rezerváciu, platobná brána spracúva platbu – čo sa stane, ak prebehnú súčasne?  
- Otestovať opakované kliknutia na zrušenie a zabezpečiť, že systém nespracuje požiadavku viackrát.  
- Skontrolovať reakciu systému pri zlyhaní (napr. či sa vytvorí hlásenie alebo podnet pre podporu).  

6. **Oznámenia, dokumenty a záznamy**
- Overiť texty emailov, SMS a oznámení: či obsahujú správnu sumu, poplatky, dátumy a čas vrátenia, ako aj správny formát meny.  
- Skontrolovať účtovné záznamy a denníky zmien (kto, kedy a prečo zrušil).  
- Otestovať generovanie potvrdení (napr. PDF, CSV) a zhodu údajov so skutočne vrátenou sumou.  

7. **Právne a bezpečnostné požiadavky**
- Overiť, že vrátenie prebieha iba na pôvodnú platobnú metódu, ak to vyžaduje pravidlo, alebo že zákazník súhlasí s poukazom.  
- Otestovať spracovanie reklamácie platby po vrátení (chargeback) a zablokovanie ďalších pokusov o vrátenie.  
- Skontrolovať dodržiavanie GDPR – uchovávanie informácií o platbe len po potrebnú dobu.  

8. **Automatizované testy a testovacie dáta**
- Pripraviť automatické testy pre hlavné prípady (vrátená suma, stav, oznámenia, prepojenie s bránou).  
- Použiť testovacie karty alebo prostredia platobných brán s jedinečnými identifikátormi požiadaviek.  
- Testovať s účtami s rôznymi oprávneniami (zákazník, podpora, účtovník, partner).  

9. **Regresné testy pri nasadení**
- Pri každej aktualizácii systému overiť základný tok: zaplatenie → zrušenie → vrátenie.  
- Skontrolovať stavy záznamov v databáze (zrušenie, účtovné zápisy, záznamy v logoch).  

10. **Sledovanie po spustení**
- Monitorovať ukazovatele: počet vrátení, neúspešné vrátenia, priemerný čas vrátenia peňazí, počet reklamácií.  
- Nastaviť upozornenia pri zvýšenom počte chýb alebo dlhých čakajúcich vráteniach.  
