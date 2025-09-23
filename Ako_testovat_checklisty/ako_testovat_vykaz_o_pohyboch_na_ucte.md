Ako testovať výkaz o pohyboch na účte (z pohľadu účtovníctva)

Príklad
Predstav si účtovníčku, ktorá si stiahne výkaz pohybov na účte, aby spárovala bankové operácie s účtovníctvom. Očakáva, že každá platba, poplatok či úrok bude jasne viditeľný a bude sa dať priradiť k účtovnému dokladu. Ak je formát nezrozumiteľný, chýba variabilný symbol alebo sú poplatky zlúčené bez detailu, účtovníctvo sa dostáva do chaosu – výkazy strácajú význam a proces párovania sa spomaľuje. Tester má preto preveriť, či sú údaje vo výkaze kompletné, správne a konzistentné a či výkaz spĺňa potreby účtovníctva aj legislatívy.



Ako otestovať 

Základná kontrola údajov

Skontroluj, či výkaz obsahuje polia: dátum, suma, mena, číslo účtu, variabilný/špecifický symbol, popis transakcie.

Over, či sa zobrazujú záporné hodnoty (poplatky, storno).

Uisti sa, že mena a suma korešpondujú s pohybom na účte.

Súlad s účtovníctvom

Porovnaj výkaz s účtovníctvom – či sa každá transakcia dá priradiť k dokladu.

Over priraditeľnosť podľa symbolu, čísla faktúry alebo referencie.

Pri hromadných inkasách skontroluj rozpad na jednotlivé transakcie.

Otestuj aj párovanie platieb v cudzej mene.

Správnosť súčtov a zostatkov

Skontroluj, či počiatočný a konečný zostatok sú správne (začiatočný stav + pohyby = konečný stav).

Otestuj mesačné uzávierky – súčty musia sedieť aj po exporte.

Over kontinuitu – konečný stav jedného mesiaca = počiatočný stav ďalšieho.

Formát a export

Otestuj export do formátov (CSV, XML, ABO) a ich import.

Over, či sa zachovávajú diakritika, znaky a celé čísla účtov.

Skontroluj, že výkaz je možné uložiť a spätne otvoriť bez straty dát.

Vyskúšaj export pri rôznych rozsahoch – mesačný, kvartálny, ročný.

Negatívne scenáre

Čo ak transakcia nemá variabilný symbol – ako sa zobrazí?

Ako sa prejaví oprava alebo storno?

Over spracovanie duplicitných alebo oneskorene doručených transakcií.

Otestuj, ako sa výkaz správa, ak chýbajú údaje (napr. popis).

Právne a metodické požiadavky

Skontroluj, či výkaz spĺňa požiadavky legislatívy.

Uisti sa, že dátumy sú vo formáte podľa slovenských štandardov (DD-MM-YYYY alebo DD.MM.YYYY).

Over, či systém dokáže pracovať aj s formátom ISO 8601 (YYYY-MM-DD) pri cezhraničnej komunikácii.

Otestuj, či sú splnené požiadavky na archiváciu výkazov.


#testing #qa #banking #accounting #financialreports #automation #compliance #datavalidation



