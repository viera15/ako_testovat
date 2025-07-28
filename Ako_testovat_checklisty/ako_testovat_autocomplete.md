# Ako testovať automatické dopĺňanie údajov (autocomplete)<br><br>

Nie všetky autocomplete fungujú rovnako. Niektoré sa učia z tvojich predchádzajúcich vstupov, iné čerpajú zo širokej databázy a hneď ponúkajú návrhy.<br><br>

Predstavte si pole na zadanie výrobku v e-shope. Používateľ napíše „pracka“ a systém mu navrhne:<br>
- práčka<br>
- pracka na opasok<br>
- práčka Whirlpool<br><br>

Záleží na tom, či vie pracovať s diakritikou, ako rozumie významom a čo má v dátach. Ako sa dá otestovať, že autocomplete funguje správne?<br><br>

Čo otestovať pri autocomplete:<br><br>

**Správnosť výsledkov**<br>
- Zodpovedajú ponuky zadaniu používateľa?<br>
- Nezobrazujú sa irelevantné výsledky?<br><br>

**Poradie výsledkov**<br>
- Je najpravdepodobnejšia položka navrchu?<br>
- Majú výsledky logickú prioritu (napr. podľa frekvencie, vzdialenosti, abecedy)?<br><br>

**Reakcia na rôzne vstupy**<br>
- Funguje hľadanie aj pri čiastočnom alebo neúplnom slove?<br>
- Ako reaguje systém na preklepy („Bartislava“)?<br>
- Podporuje autocomplete aj vstup bez diakritiky („pracka“ vs. „práčka“)?<br>
- Čo ak používateľ zadá malé/veľké písmená, medzery, špeciálne znaky?<br>

**Rýchlosť reakcie**<br>
- Je odpoveď systému dostatočne rýchla (napr. do 200–300 ms)?<br>
- Je systém použiteľný aj pri pomalšom internete?<br><br>

**Počet výsledkov**<br>
- Je počet obmedzený (napr. top 5–10)?<br>
- Funguje stránkovanie alebo „load more“, ak je výsledkov veľa?<br><br>

**Fallback správanie**<br>
- Zobrazí sa hláška, ak nič nevyhovuje („Nenašli sa žiadne výsledky“)?<br>
- Dá sa zadať vlastný údaj, ak autocomplete nič nenájde?<br><br>

**Prístupnosť**<br>
- Ide pohybovať sa po položkách klávesnicou?<br>
- Funguje čítanie položiek cez čítačku obrazovky (napr. ARIA attribúty)?<br>
- Nezostáva starý zoznam „visieť“ na obrazovke?<br><br>

**Bezpečnostné hľadisko**<br>
- Filtruje systém nevhodný obsah, skripty, pokusy o XSS?<br>
- Nie sú návrhy závislé od cudzích nespoľahlivých zdrojov?<br><br>

**Lokalizácia**<br>
- Sú návrhy preložené do správneho jazyka?<br>
- Je zoradenie správne pre danú lokalitu (napr. české „č“ nie je na konci)?<br><br>

**Testovanie pomocou AI**<br>
- Vie AI automaticky otestovať bežné vstupy a porovnať očakávané vs. zobrazené výsledky?<br>
- Vie AI simulovať ľudské správanie – rýchle písanie, úpravy vstupu, preklepy?<br><br>

Autocomplete je malá funkcia s veľkým dopadom. Keď funguje dobre, šetrí čas a zvyšuje komfort. Keď nie, vie používateľa poriadne odradiť.<br>
