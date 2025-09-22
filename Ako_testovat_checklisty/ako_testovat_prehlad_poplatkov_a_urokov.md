Ako testovať prehľad poplatkov a úrokov

Príklad
Predstav si, že klient si otvorí internetbanking a chce si skontrolovať, koľko ho stál účet za posledný mesiac. V prehľade však vidí poplatok za výber z bankomatu, aj keď výber bol z vlastného bankomatu, kde mal mať výber zdarma. Alebo sa mu vygeneruje úrok z povoleného prečerpania, ktorý je vypočítaný nesprávne podľa sadzby. Takéto chyby podkopávajú dôveru klienta v banku a môžu viesť k reklamáciám aj finančným stratám.

Ako otestovať (praktické kroky)

Základná kontrola údajov

Over, či sa v prehľade zobrazujú všetky relevantné položky (poplatky, úroky, zľavy z poplatkov).

Skontroluj priradenie k správnemu účtu, dátumu a časovému obdobiu.

Validuj formát a jednotky (mena, desatinné miesta, percentá).

Testovanie poplatkov

Over výpočet podľa cenníka banky (mesačný poplatok za vedenie účtu, transakčné poplatky, výbery, SEPA platby, zahraničné prevody).

Simuluj rôzne typy účtov (študentský, prémiový, firemný, balíčky služieb).

Otestuj zľavy a výnimky (napr. prvé 3 výbery zdarma, akcia pre nových klientov).

Skontroluj poplatky v cudzej mene – prepočítavajú sa správne podľa devízového kurzu?

Testovanie úrokov

Skontroluj správny výpočet debetných úrokov (pri povolenom aj nepovolenom prečerpaní) a kreditných úrokov (na sporiacom účte).

Over periodicitu výpočtu (denná báza, mesačné zúčtovanie).

Simuluj špeciálne sadzby (zvýhodnené úroky pri viazanosti, sankčné úroky).

Porovnaj výsledok s ručným prepočtom podľa metodiky banky.

Hraničné a negatívne scenáre

Účet bez pohybov – zobrazí sa nulový poplatok/úrok?

Záporné zostatky – správne sa aplikuje úrok?

Zmena tarify alebo balíčka uprostred mesiaca – rozdelí sa poplatok korektne?

Uzavretie účtu – sú poplatky účtované len do dňa zrušenia?

Integrita a zobrazenie

Porovnaj údaje s cenníkom a výstupmi z hlavnej knihy (core banking).

Over export do mesačných výpisov (PDF, CSV, XML) – sú položky konzistentné?

Skontroluj UX – prehľadnosť, čitateľnosť a zarovnanie položiek na rôznych zariadeniach.

Sleduj históriu – sú staršie mesiace dostupné a nemiznú po zmene tarify?

Výkon a reporting

Otestuj spracovanie veľkého počtu položiek (napr. pri firemných účtoch).

Skontroluj, či reporty vygenerujú dáta do určitého času a nepadnú na timeout.

Over napojenie na notifikácie – ak sa účtuje nový poplatok alebo úrok, dostane klient upozornenie?




#testing #qa #banking #fees #interest #fintech #automation #manualtesting #regressiontesting #ux



