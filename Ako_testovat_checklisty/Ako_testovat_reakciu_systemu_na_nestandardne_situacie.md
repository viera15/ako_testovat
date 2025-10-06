# Ako testovať reakciu systému na neštandardné situácie (výpadok siete počas platby, offline režim)<br><br>

Príklad<br>
Klient zadá platbu kartou v mobile. Po potvrdení 3-D Secure v bankovej appke vypadne internet. Frontend „zamrzne“, zákazník klikne späť a skúsi to znova.<br>  
**Výsledok:** dve autorizácie, jedno zaúčtovanie, nejasné hlášky a nahnevaný klient.<br><br>  

**Cieľ testu:** systém musí byť odolný voči duplicitnému spracovaniu, správať sa predvídateľne a po obnovení pripojenia sa korektne zotaviť.<br><br>

## Ako otestovať<br><br>

1. **Scenáre výpadku v kritických bodoch**<br>
- Odpájaj sieť pri: odoslaní platby, počas 3-DS overenia/SCA, pri návrate z brány, pri volaní webhooku PSP, počas zápisu do DB.<br>  
- Testuj „flapping“ (rýchle striedanie online/offline) a dlhý timeout.<br><br>

2. **Idempotencia a deduplikácia**<br>
- Znova odošli rovnakú platbu (rovnaký *idempotency key*) pri obnovení siete; očakávaj jeden finálny výsledok.<br>  
- Over blokáciu duplicitných príkazov podľa business kľúčov (account + amount + nonce).<br><br>

3. **Transakčná konzistencia**<br>
- Uisti sa, že aplikácia spracúva kroky platby ako jeden celok: po výpadku má platba stav *„Čaká na potvrdenie“* a po obnovení pripojenia sa informácie doplnia z platobnej brány alebo účtovného záznamu.<br>  
- Skontroluj kompenzačné akcie (*reversal/refund*) pri neúspešnom doúčtovaní.<br><br>

4. **Offline režim (plánované správanie)**<br>
- Jasne definuj, čo ide offline (prehľad histórie z cache, príprava príkazu do fronty) a čo nejde (odoslanie platby).<br>  
- Over šifrované lokálne úložisko, TTL konceptov a obnovu fronty po reštarte appky.<br><br>

5. **UX a hlášky**<br>
- Stručné, akčné a pravdivé:<br>  
  *„Pripojenie zlyhalo. Platba je v stave Neisté. Skontrolujeme a dáme vedieť.“*<br>  
- Zobraz stav *Processing/Retrying*; ponúkni *„Skontrolovať stav“* alebo *„Zrušiť pokus“*.<br><br>

6. **Retry politika (politika opakovaných pokusov)**<br>
- Exponenciálne oneskorenie, maximálny počet pokusov, hrané chyby (DNS, TLS, 5xx, timeout).<br>  
- Rozlišuj, ktoré opakované pokusy sú bezpečné (GET, idempotentné POST) od nebezpečných.<br><br>

7. **Integrácia s PSP/bránou (PSP = platobná brána)**<br>
- Vyvolaj oneskorené/not-delivered webhooky; po neskorom doručení musí systém aktualizovať stav platby.<br>  
- Over zhodu údajov (reconciliation): denné porovnávanie účtovných záznamov ↔ PSP (CSV/API), report nezrovnalostí.<br><br>

8. **Bezpečnosť a overenie používateľa (SCA)**<br>
- Ak sa počas platby preruší dvojstupňové overenie, aplikácia by mala po obnovení pripojenia opäť požiadať o potvrdenie platby.<br>  
- Skontroluj, že systém po návrate neumožní pokračovať bez nového overenia.<br>  
- Zaznamenávaj všetky dôležité kroky a pokusy v záznamoch (audit trail), vrátane tých, ktoré prebehli offline.<br><br>

9. **Hraničné podmienky zariadenia**<br>
- Režim lietadlo, nízka dátová rýchlosť, captive portal, úspora batérie, prepnutie appky do pozadia počas platby.<br><br>

10.**Monitoring a alerting**<br>
- Metriky percenta „Unknown/Pending“, počty retry, priemerný čas zotavenia po výpadku.<br>  
- Alerty pri špičke zlyhaní.<br>
