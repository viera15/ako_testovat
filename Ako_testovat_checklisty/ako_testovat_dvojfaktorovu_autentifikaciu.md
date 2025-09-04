# Ako testovať dvojfaktorovú autentifikáciu (2FA) (nielen v bankovníctve)<br><br>

1. **Overenie toku autentifikácie:**<br>
- Je 2FA aktivovaná po zadaní správnych prihlasovacích údajov?<br>
- Dostane používateľ výzvu na zadanie kódu (napr. SMS, e-mail, mobilná appka)?<br><br>

2. **Správnosť a jedinečnosť kódu:**<br>
- Kód je jedinečný pre každé prihlásenie?<br>
- Platí len obmedzený čas (napr. 5 minút)?<br>
- Čo sa stane po jeho uplynutí?<br><br>

3. **Chybové stavy a pokusy o zneužitie:**<br>
- Zadanie nesprávneho kódu – koľko pokusov je povolených?<br>
- Ošetrenie opakovaných neúspešných pokusov – je účet zablokovaný?<br>
- Zobrazujú sa zrozumiteľné a nie príliš konkrétne chybové hlásenia?<br><br>

4. **Viacero spôsobov overenia:**<br>
- Funguje aj alternatívna metóda (napr. mobilná appka pri nedostupnosti SMS)?<br>
- Je možné zmeniť preferovaný spôsob 2FA?<br>
- Otestovať obnovu/stratu zariadenia: čo ak používateľ stratí telefón?<br><br>

5. **Scenáre pre rôzne zariadenia a siete:**<br>
- Funguje overenie rovnako cez desktop, mobil, rôzne OS a prehliadače?<br>
- Čo sa stane, ak používateľ prepne sieť (napr. Wi-Fi → mobilné dáta) počas overovania?<br>

6. **Používateľská skúsenosť:**<br>
- Je proces zrozumiteľný aj pre menej technických používateľov?<br>
- Nie je 2FA zbytočne zdržujúce pri častom prihlasovaní?<br><br>

7. **Bezpečnosť a logovanie:**<br>
- Sú pokusy o 2FA zaznamenané v logoch?<br>
- Zobrazí sa používateľovi upozornenie pri prihlásení z nového zariadenia?<br><br>

Ak testujete bezpečnostné prvky ako 2FA, nezabúdajte: nejde len o to, či funguje, ale či je odolné voči zneužitiu, dostatočne rýchle a zároveň zrozumiteľné pre koncového používateľa.<br>
