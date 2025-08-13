# Ako testovať plánovanú odstávku systému?<br><br>

Predstav si, že program na fakturáciu s mesačným/ročným predplatným (SaaS aplikácia) má naplánovanú nočnú odstávku kvôli migrácii databázy. Počas tohto obdobia by mal byť systém nedostupný – ale používateľ nemá vidieť len „chybu 500“. Mal by ho privítať oznam, ktorý mu zrozumiteľne vysvetlí, čo sa deje.<br><br>

## Ako by si to ako tester/testerka otestoval?<br><br>

Na čo sa zamerať pri testovaní maintenance módu:<br><br>

1. **Aktivácia režimu**<br>
- Dá sa maintenance režim zapnúť podľa plánu? (napr. cron job, manuálne prepnutie)
- Je dostupné konfiguračné rozhranie?<br><br>

2. **Zobrazenie oznamu používateľom**<br>
- Vidí bežný používateľ po prihlásení informáciu o odstávke?<br>
- Zobrazuje sa oznam aj na verejných stránkach (napr. login page)?<br>
- Je text zrozumiteľný, lokalizovaný a obsahuje odhad trvania?<br><br>

3. **Správanie frontendu**<br>
- Nenačítava sa rozhranie „na polovicu“? (napr. spinner bez obsahu – točiace sa koliesko (indikátor načítania) bez reakcie)<br>
- Sú všetky API volania korektne blokované?<br><br>

4. **Správanie backendu a API**<br>
- Vráti API pri maintenance správny HTTP kód? (napr. 503 Service Unavailable)<br>
- Obsahuje odpoveď aj Retry-After hlavičku, ak je dostupný odhad konca?<br><br>

5. **Autentifikácia a oprávnenia**<br>
- Sú výnimky správne nastavené? (napr. admin sa vie prihlásiť, ale bežný používateľ nie)<br>
- Sú cron úlohy, ktoré nemajú bežať, skutočne pozastavené?<br><br>

6. **Obnovenie prevádzky**<br>
- Po vypnutí maintenance režimu sa systém správa normálne?<br>
- Neostali zapnuté obmedzenia alebo oznamy?<br><br>

7. **Prístupnosť a UX**<br>
- Dá sa oznam prečítať čítačkou obrazovky?<br>
- Je kontrast a formát vhodný aj pre mobil?<br><br>

8. **Logy a monitoring**<br>
- Zaznamenáva sa prechod do/zo stavu odstávky v logoch?<br>
- Posielajú sa alerty (napr. do Slacku, e-mailom) pri aktivácii?<br><br>

Maintenance mód nie je len „prepnutie prepínača“. Správne otestovanie zabezpečí, že používateľ neodíde frustrovaný — a že tím DevOps vie, že všetko prebehlo hladko.<br>
