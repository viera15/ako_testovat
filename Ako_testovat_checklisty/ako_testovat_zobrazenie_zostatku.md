# Ako testovať zobrazenie zostatku, pohybov a výpisov<br><br>

Predstav si situáciu: zákazník sa prihlási do internetového bankovníctva a očakáva, že uvidí správny zostatok, všetky svoje transakcie a výpis za vybrané obdobie. Ak sa zobrazia nesprávne údaje alebo sú neúplné, môže to spôsobiť stratu dôvery voči banke a zbytočné reklamácie.<br><br>

## Ako to teda otestovať?<br><br>

1. **Zostatok účtu**<br>
- Over, či sa zobrazuje aktuálny zostatok po každej transakcii (platba, výber, prevod).<br>
- Skontroluj, či je zostatok konzistentný na všetkých obrazovkách (dashboard, detail účtu, export).<br>
- Otestuj rôzne typy účtov – bežný, sporiaci, úverový.<br><br>

2. **Pohyby na účte (transakcie)**<br>
- Over, že sa každá transakcia zobrazí so správnym dátumom, sumou, menou a protistranou.<br>
- Testuj radenie (podľa dátumu, sumy, typu operácie).<br>
- Skontroluj filtrovanie (napr. len prichádzajúce platby, len výdavky kartou).<br>
- Otestuj, čo sa stane, keď je veľké množstvo transakcií (1000+).<br><br>

3. **Výpisy**<br>
- Skontroluj generovanie mesačných/štvrťročných výpisov v PDF a iných formátoch.<br>
- Over, že údaje vo výpise sedia s pohybmi v aplikácii.<br>
- Otestuj jazykové verzie výpisov, ak sú dostupné.<br>
- Skontroluj, či výpis obsahuje všetky povinné náležitosti (IBAN, meno majiteľa, dátumy, začiatočný a konečný zostatok).<br><br>

4. **Bezpečnosť a prístup**<br>
- Over, že k zostatku a výpisom má prístup len majiteľ účtu alebo oprávnený používateľ.<br>
- Otestuj, čo sa stane, keď používateľ nemá žiadne pohyby – zobrazí sa prázdna stránka alebo vhodná správa?<br>
- Skontroluj, či výpis nie je možné stiahnuť bez prihlásenia.<br><br>

5. **Negatívne scenáre**<br>
- Čo ak sa preruší spojenie počas načítania výpisu?<br>
- Ako sa správa aplikácia, keď banka odošle oneskorené dáta?<br>
- Ako sa zobrazia storno transakcie alebo opravy?<br><br>

Správne otestované zobrazenie zostatkov, pohybov a výpisov je základom dôvery klienta v banku – pretože práve tu vidí, ako banka narába s jeho peniazmi.<br>
