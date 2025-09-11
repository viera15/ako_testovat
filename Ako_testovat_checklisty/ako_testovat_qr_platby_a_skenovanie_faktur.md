# Ako testovať QR platby a skenovanie faktúr<br><br>

Predstav si situáciu: zákazník dostane faktúru s QR kódom, ktorý obsahuje všetky potrebné údaje pre platbu (IBAN, suma, variabilný symbol). Stačí ho nasnímať v mobilnej bankovej aplikácii a údaje sa automaticky vyplnia. Rýchle, pohodlné, ale aj veľmi citlivé na chyby – stačí malý detail a platba môže byť odoslaná nesprávne.<br><br>

## Ako to otestovať?<br><br>

1. **Rôzne formáty QR kódov**<br>
- otestovať správnosť načítania oficiálneho bankového formátu (napr. PAY by square),<br>
- skúsiť aj iné typy QR kódov (obyčajný URL kód, QR s textom) – aplikácia by ich mala rozpoznať a primerane reagovať.<br><br>

2. **Kvalita a čitateľnosť kódu**<br>
- ostré vytlačené QR kódy,<br>
- rozmazané, čiastočne poškodené alebo zmenšené,<br>
- rôzne kontrasty (čierna na bielom, farebná kombinácia).<br><br>

3. **Automatické vyplnenie polí**<br>
- IBAN, suma, variabilný symbol, dátum splatnosti – overiť, že sa správne načítajú a zapíšu do polí.<br>
- skúsiť platbu s chýbajúcimi údajmi – má aplikácia ponúknuť doplnenie?<br><br>

4. **Neplatné a manipulatívne kódy**<br>
- QR kód s nesprávnym IBAN-om alebo neexistujúcim účtom,<br>
- QR kód s inou menou (napr. CZK namiesto EUR),<br>
- QR kód, ktorý sa tvári ako faktúra, ale odkazuje na škodlivý link (test bezpečnostného spracovania).<br><br>

5. **Používateľská skúsenosť (UX)**<br>
- aká je rýchlosť načítania QR kódu,<br>
- či má používateľ možnosť manuálne upraviť načítané údaje,<br>
- aké chybové hlášky sa zobrazia pri nečitateľnom kóde.<br><br>

6. **Skenovanie faktúr**<br>
- rôzne rozloženia faktúr (iné pozície QR kódu, formátovanie),<br>
- viac kódov na jednej faktúre – aplikácia musí správne vybrať ten určený na platbu,<br>
- faktúry v PDF verzus papierové.<br><br>

Testovanie QR platieb a skenovania faktúr je kľúčové pre dôveru používateľov – ak banka zaručí, že sa údaje načítajú presne a bezpečne, zákazníci túto funkcionalitu využívajú radi a často.<br>
