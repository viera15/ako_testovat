# Ako testovať obmedzenie prístupu k citlivým údajom (napr. zostatky, výpisy, IBANy)<br><br>

Predstav si, že si tester v banke a máš za úlohu overiť, že bežný zákazník nemá prístup k údajom iného klienta. V praxi to znamená, že ak sa prihlásim ako používateľ A, nesmiem vidieť zostatky, IBANy ani výpisy používateľa B – a naopak.<br><br>

V jednej firme, kde som testovala, sa stalo, že backend posielal viac údajov, než bolo potrebné. Frontend síce zobrazoval len povolené dáta, ale systém posielal aj iné. Tester si to všimol pri kontrole komunikácie medzi aplikáciou a serverom – teda pri štandardnej validácii, ktorú robíme, aby sme sa uistili, že aplikácia neodhalí informácie navyše. Tento príklad ukazuje, že bezpečnosť musí byť riešená už na úrovni backendu, nie len skrytím na obrazovke.<br><br>

## Ako otestovať obmedzenie prístupu k citlivým údajom:<br><br>

1. **Testuj s viacerými rolami**<br>
- Over, že zákazník vidí len svoje dáta.<br>
- Manažér má prístup len k účtom svojich podriadených.<br>
- Admin má len tie oprávnenia, ktoré sú skutočne potrebné.<br><br>

2. **Priame volanie API**<br>
- Skús zavolať endpoint s iným ID účtu alebo klienta.<br>
- Očakávaj chybovú hlášku alebo prázdnu odpoveď, nikdy nie dáta iného používateľa.<br><br>

3. **Manipulácia s URL**<br>
- Ak aplikácia používa URL s parametrami (napr. /account/1234), skús ich manuálne zmeniť.<br>
- Dáta iného používateľa sa nesmú zobraziť.<br><br>

4. **Testovanie prístupových tokenov**<br>
- Použi token jedného používateľa pre dopyt na účet iného.<br>
- Backend musí prístup odmietnuť.<br><br>

5. **Kontrola logov**<br>
- Over, že v logoch sa neukladajú celé čísla účtov alebo IBANy v čitateľnej podobe.<br>
- Citlivé údaje majú byť maskované alebo anonymizované.<br><br>

6. **Negatívne scenáre**<br>
- Skús prístup bez prihlásenia.<br>
- Skús prístup s expirovaným tokenom.<br>
- Over, že systém vráti bezpečnú chybu (napr. 401 Unauthorized, 403 Forbidden).<br><br>

7. **Regresné testy**<br>
- Po každej zmene backendu alebo oprávnení zopakuj testy, aby sa neotvorili nové bezpečnostné diery.<br><br>

Dostupnosť citlivých údajov je jedným z najkritickejších miest v bankovníctve a financiách. Jedna chyba môže znamenať únik dát, pokuty a stratu dôvery klientov. Preto je dôležité testovať prístupové obmedzenia systematicky a nielen „kliknutím cez UI“.<br>
