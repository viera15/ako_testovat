# Ako testovať generovanie reportu s filtrami?<br><br>

Predstav si, že testuješ aplikáciu, kde si používateľ môže vygenerovať report o tržbách za zvolené obdobie – podľa krajiny, typu produktu a stavu objednávky.<br><br>

Čo všetko treba pri testovaní overiť?<br><br>

1. **Kombinácie filtrov**<br>
- jednotlivo: iba krajina, iba produkt, iba stav<br>
- dvojice: krajina + produkt, krajina + stav, produkt + stav<br>
- všetky filtre naraz: krajina + produkt + stav<br>
- nevyplnené filtre (všetko ponechané default)<br><br>

2. **Limity a rozsahy**<br>
- dátumy: správne fungovanie od–do (napr. od 1.1.2020 do 31.12.2020)<br>
- extrémne hodnoty (napr. 1.1.1900 alebo budúce roky)<br>
- maximálny počet záznamov v reporte (napr. limit na 1000 riadkov)<br><br>

3. **Default nastavenia**<br>
- je predvolený výber nastavený správne?<br>
- má používateľ automaticky zvolený najčastejšie používaný filter?<br>
- vráti sa očakávaný výsledok aj bez zmeny filtrov?<br>
- môže si prihlásený používateľ uložiť vlastnú kombináciu filtrov a znovu ju použiť po ďalšom prihlásení? Funguje výber a načítanie uložených filtrov správne?<br><br>

4. **Neexistujúce alebo prázdne hodnoty**<br>
- kombinácia filtrov, ktorá nemá žiadne dáta (napr. Nemecko + banány + stornované)<br>
- správne zobrazenie hlášky „Nenašli sa žiadne výsledky“<br>
- nespadne systém pri nulovom výstupe?<br><br>

5. **Technické a bezpečnostné aspekty**<br>
- zvládne systém rýchle opakované požiadavky (rate limit)?<br>
- funguje export (CSV, PDF) pri všetkých kombináciách?<br>
- nemôžem získať údaje mimo svojho oprávnenia (napr. cez manipuláciu s parametrami)?<br><br>

6. **UI komponenty filtrov**<br>
- sú všetky vstupné polia, dropdowny a checkboxy funkčné?<br>
- sú správne označené (labely, placeholdery, tooltipy)?<br>
- reagujú dynamicky, ak je niektorý filter závislý od iného?<br><br>

7. **Výkon pri veľkých dátach**<br>
- ako rýchlo sa vygeneruje report pri maximálnom objeme dát?<br>
- zvládne systém opakované požiadavky od viacerých používateľov?<br>
- nezamrzne UI pri filtrovaní veľkých datasetov?<br><br>

8. **Lokalizácia a jazyková verzia filtrov**<br>
- sú názvy filtrov a ich hodnoty správne preložené?<br>
- fungujú filtrovania v rôznych jazykových verziách rovnako?<br>
- nezamieňajú sa hodnoty (napr. iný formát dátumu alebo čísel)?<br><br>

9. **Audit a logovanie filtrovania**<br>
- zaznamenáva sa, kto aký filter použil a kedy?<br>
- sú logy dostupné pre administrátora/analytika?<br>
- môžu sa tieto údaje použiť pri spätnom overení generovania reportu?<br><br>

10. **Prístupnosť (accessibility)**<br>
- sú filtre ovládateľné pomocou klávesnice?<br>
- sú všetky ovládacie prvky čitateľné pre čítačky obrazovky?<br>
- majú vizuálne prvky (farby, kontrast) správne nastavené hodnoty pre slabozrakých používateľov?<br>



