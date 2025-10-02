# Ako testovať účty s nulovým alebo záporným zostatkom<br><br>

#Príklad<br>
Klient si všimne, že jeho účet zobrazuje -12,34 € po zaúčtovaní poplatku a súčasne mu aplikácia umožní zadať ďalšiu platbu, ktorá by mala byť zablokovaná. Takéto situácie poškodzujú dôveru zákazníka a môžu viesť k penalizáciám alebo nesprávnym účtovacím reportom. Nižšie sú praktické kroky, ako takéto prípady nájsť a otestovať pred nasadením do produkcie.<br><br>

## Ako otestovať <br><br>

1. **Základná validačná sada**<br>
- Over zobrazenie zostatku pri rôznych stavoch: kladný, nulový, presne 0.00 €, mierne záporný (-0.01 až -10 €), výrazne záporný (napr. < -100 €).<br>  
- Testuj formátovanie, zaokrúhľovanie a miestne meny (ISO 4217).<br>  
- Skontroluj logiku zaokrúhľovania pri viacnásobných transakciách (seriový prepočet).<br><br>  

2. **Scenáre transakčnej konzistencie**<br>
- Vytvor transakčný balík: vklad → nákup → poplatok → spätné zaúčtovanie. Over, či sa rovnaká operácia pri opakovanom spustení nespracuje dvakrát, ale výsledok zostane konzistentný.<br>  
- Simuluj súbežné transakcie (concurrent): dve platby súčasne zo stavu 0.00 € — over, či systém správne blokuje/preferuje jednu z nich alebo umožní prečerpanie podľa pravidiel.<br><br>  

3. **Overovanie obchodných pravidiel (business rules)**<br>
- Testuj limity: povolené prečerpania podľa typu účtu (debetné limity, overdraft, povolené mínusy), denné/mesačné limity pre príkazy.<br>  
- Skontroluj autorizácie: ktoré role/kanály (pobočka, internetbanking, API) môžu vytvoriť záporný zostatok.<br>  
- Otestuj notifikácie a varovania (push/SMS/e-mail) pri prechode na 0.00 € a pri prekročení debetu.<br><br>  

4. **Reakcia UI/UX a API dohody (kontrakty)**<br>
- **UI:** skontroluj, či aplikácia jasne komunikuje stav (napr. „Nulový zostatok — nie je možné odoslať platbu“) a či tlačidlá/akcie menia stav (disabled vs enabled).<br>  
- **API:** over chybové kódy a ich konzistentnosť (napr. 400 vs 409) pri pokuse o platbu z nedostatočného zostatku.<br>  
- Validuj chybové správy v rôznych jazykoch a ich vhodnosť pre zákazníka.<br><br>  

5. **Edge-casey a chyby zaokrúhľovania**<br>
- Testuj mikro-sumy: transakcie menšie ako 1 cent/najmenšia menová jednotka – ako sa zaokrúhľuje a aký to má dopad na zostatok.<br>  
- Over vrátenia platieb (reversals/refundy): či zvrátenie alebo refundácia transakcie zmení zostatok správne pri zápornom stave.<br>  
- Skontroluj prípad, keď poplatok presiahne zostatok a systém musí zaúčtovať prečerpanie + prípadné penalizácie.<br><br>  

6. **Integrácie a súlad (compliance)**<br>
- Over externé zaúčtovania — clearing, card-gateway, SEPA: či prichádzajúce záporné vyrovnania nie sú duplikované.<br>  
- Audit a logging: skontroluj, či všetky kroky majú audit trail (kto, kedy, prečo) a či sú logy konzistentné pre neskoršie vyšetrenie.<br>  
- Testy obnovy (reconciliation): skontroluj, či sa čísla v oboch systémoch rovnajú medzi denníkom transakcií a koncovými reportmi (end-of-day).<br><br>  

7. **Testovanie regresie a monitoring po nasadení**<br>
- Pridaj regresné testy pre scenáre nulového a záporného zostatku do CI/CD.<br>  
- Nastav alerty v monitoringu (anomaly detection) pri náraste záporných účtov nad očakávanú úroveň.<br>  
- Slabé stresové testy: dopytuj veľké množstvo malých transakcií, ktoré môžu spôsobiť kumulatívne prečerpanie.<br>  
