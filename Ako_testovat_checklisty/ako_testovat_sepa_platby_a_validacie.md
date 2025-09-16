# Ako testovať SEPA platby a ich validácie (IBAN, BIC, suma, dátum)<br><br>

Predstav si, že klient zadáva SEPA platbu v internet bankingu. Vyplní IBAN príjemcu, zadá sumu a dátum splatnosti. Následne systém zobrazí chybu: „Nesprávny formát IBAN“. V praxi sa často stáva, že klienti uvedú o jeden znak viac alebo menej, alebo preklepnú číslo. Úlohou testera je preveriť, že aplikácia takéto chyby správne zachytí a používateľovi poskytne jasné hlásenie.<br><br>

## Ako otestovať SEPA platby a validácie<br><br>

1. **IBAN**<br>
- Over správny formát podľa krajiny (dĺžka a kontrolné číslice modulo 97).<br>
- Otestuj neexistujúci IBAN (správny formát, ale číslo účtu neexistuje).<br>
- Skús vložiť špeciálne znaky alebo malé písmená – má sa konvertovať na veľké.<br><br>

2. **Formátovanie IBANu**<br>
- Vloženie IBANu s medzerami medzi každými 4 znakmi (napr. SK68 1111 0000 0012 3456 7890).<br>
- Vloženie IBANu s viacerými medzerami na začiatku alebo na konci.<br>
- Overiť, že systém medzery odstráni a validuje len samotný obsah.<br><br>

3. **BIC (SWIFT kód)**<br>
- Over správnu dĺžku (8 alebo 11 znakov).<br>
- Testuj neexistujúci BIC alebo nesprávnu kombináciu znakov.<br>
- Pre lokálne platby môže byť BIC voliteľný – skontroluj, či systém reaguje správne.<br><br>

4. **Suma**<br>
- Over minimálnu a maximálnu povolenú sumu pre SEPA (zvyčajne v EUR) – otestuj maximálnu podľa schémy, maximálnu podľa banky a zároveň denné a mesačné limity.<br>
- Testuj nulovú hodnotu, zápornú sumu alebo nepovolené desatinné miesta.<br>
- Skontroluj zaokrúhľovanie (napr. 0,999 EUR → 1,00 EUR).<br><br>

5. **Dátum**<br>
- Otestuj dátum v minulosti (nemal by byť akceptovaný).<br>
- Skontroluj, či dátum spadá na víkend alebo sviatok – systém má nastaviť najbližší pracovný deň.<br>
- Over formát dátumu (DD.MM.RRRR, RRRR-MM-DD) podľa nastavení aplikácie.<br><br>

6. **Negatívne scenáre**<br>
- Zadanie neúplných údajov (chýba IBAN, BIC alebo suma).<br>
- Zmena meny na inú ako EUR.<br>
- Otestuj limity – počet SEPA platieb za deň, maximálna suma podľa nastavenia banky.<br><br>

7. **Pozitívne scenáre**<br>
- Správne zadaný IBAN a BIC – platba sa úspešne spracuje.<br>
- Validný dátum a suma – používateľ dostane potvrdenie.<br>
- Over generovanie referenčného čísla platby (End-to-End ID).<br><br>

Testovanie SEPA platieb nie je len o zadávaní IBANov – ide o kontrolu, že celý proces (od validácie vstupov po potvrdenie) je bezpečný, presný a zrozumiteľný pre používateľa.<br>
