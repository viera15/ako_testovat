Ako testovať opakované platby a trvalé príkazy v bankovníctve?

Predstavte si klienta, ktorý si nastaví trvalý príkaz na úhradu nájmu každý mesiac k 15. dňu v sume 750 €. Po čase zmení číslo účtu prenajímateľa, no zároveň chce, aby starý príkaz zanikol a nový sa vykonával bez prerušenia. Ak systém spracuje oba príkazy súčasne alebo naopak žiadny, vznikajú vážne komplikácie – od dvojnásobnej úhrady až po omeškanie platieb.

Ako teda testovať takéto scenáre?

Založenie trvalého príkazu
Overiť, či je možné nastaviť správny dátum prvého vykonania, periodicitu (denná, týždenná, mesačná), výšku sumy a príjemcu.

Úprava príkazu
Testovať zmenu sumy, dátumu splatnosti alebo účtu príjemcu – systém má zachovať históriu zmien a vykonať platbu podľa posledného nastavenia.

Zrušenie príkazu
Overiť, či je možné príkaz zrušiť pred vykonaním a či sa ďalšie platby už nevykonajú.

Spracovanie v rôznych dátumoch
Skontrolovať vykonanie platby cez víkend, sviatok alebo pri posune splatnosti (napr. bankový deň nasledujúci po sviatku).

Opakované platby pri nedostatku prostriedkov
Simulovať situáciu, keď účet nemá dostatok financií – testovať, či banka platbu zopakuje ďalší deň alebo ju zamietne.

Notifikácie a prehľad v histórii
Platba sa musí zobraziť vo výpise, pohyboch aj v upozorneniach (SMS, push, e-mail). Overiť správnosť textu, sumy a variabilného symbolu.

Limity a kombinácie
Otestovať, či pravidelné platby neprekračujú denný alebo mesačný limit, prípadne či sa správne kombinujú s inými transakciami.

Viacero aktívnych príkazov
Vyskúšať, či systém zvládne súbežné príkazy (napr. nájom, energie, poistka) a nespôsobí kolíziu v poradí spracovania.

Negatívne scenáre
Nesprávne číslo účtu, zadaný dátum v minulosti, neplatná mena, neexistujúci príjemca. Otestovať, ako aplikácia reaguje – má upozorniť, neuložiť alebo zamietnuť.

Testovanie trvalých príkazov nie je len o jednorazovej platbe – ide o dlhodobý proces, ktorý musí byť spoľahlivý, presný a predvídateľný. Každé zlyhanie má dopad na dôveru klienta v banku.

#testing #qa #banking #payments #automation #manualtesting #qualityassurance #finance

