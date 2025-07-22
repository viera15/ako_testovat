# Ako testovať logovanie chýb a auditné záznamy?<br><br>

Bez záznamov niet retrospektívy. A bez retrospektívy niet analýzy ani zlepšovania.<br><br>

**Príklad:**<br>
Testujem webovú aplikáciu pre interný informačný systém. Pridám nový záznam do databázy a úmyselne zmením dátum narodenia na neplatný formát. Aplikácia zobrazí chybu – ale čo ďalej?<br><br>

**Otváram logy – očakávam, že:**<br>
- sa zaznamenala výnimka (napr. InvalidDateFormatException)<br>
- je tam čas, kedy sa to stalo<br>
- vidím, kto (užívateľ / IP adresa / session) to spôsobil<br>
- viem dohľadať, čo tomu predchádzalo<br>
Rovnako pri úprave dát: očakávam auditný záznam, že používateľ XY zmenil hodnotu A na B v čase C.<br><br>

## Čo všetko testovať pri logovaní a audite?<br><br>

**Čo sa zaznamenáva**<br>
- výnimky, chyby, warningy<br>
- zmeny dát (kto, čo, kedy, ako)<br>
- pokusy o prístup k zakázaným častiam systému<br>
- prihlásenia, odhlásenia, neúspešné pokusy<br><br>

**Ako sa zaznamenáva**<br>
- v akom formáte (číta sa to zrozumiteľne?)<br>
- či sa používajú štandardy (napr. JSON, ISO časové pečiatky)<br>
- citlivé dáta sú maskované alebo neprítomné<br><br>

**Kedy sa zaznamenáva**<br>
- vždy, keď dôjde k chybe / udalosti<br>
- či sa záznamy generujú okamžite alebo s oneskorením<br>
- či nevznikajú duplicitné záznamy<br><br>

**Dá sa to dohľadať?**<br>
- existuje centrálne miesto, kde logy/auditné záznamy sú<br>
- sú filtrovatelné podľa času, typu alebo používateľa<br>
- má tester / admin prístup k týmto záznamom?<br>
- nezmiznú po reštarte aplikácie?<br><br>

## Záver:<br>
Logovanie a audit nie sú len o „máme logy“. Sú o tom, či nám pomôžu, keď ich potrebujeme. A to je práca aj pre testera – pýtať sa, skúšať a preverovať.<br>
