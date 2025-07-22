# Ako testovať lokalizáciu aplikácie?<br><br>

Príklad z praxe:<br>
Testujem aplikáciu, ktorá má byť dostupná v slovenčine, angličtine a arabčine. Prepnem jazyk na arabčinu – text sa síce preložil, ale rozloženie stránky sa nerozbilo? Fajn. Ale dátum má stále európsky formát, nie arabský. A fallback jazyk? Namiesto angličtiny sa zobrazuje poľština... <br><br>

Na čo sa zamerať pri testovaní lokalizácie?<br><br>

**Preklady**<br>
- sú správne, úplné, neobsahujú „Lorem ipsum“?<br>
- nie sú preložené len statické časti?<br>
- neprekrýva preklad tlačidlá alebo nepresahuje okraje?<br><br>

**Formáty dátumu, času, čísel a meny**<br>
- zobrazujú sa podľa lokality používateľa?<br>
napr. 1,000.00 € vs 1 000,00 €<br>
- 12-hodinový vs 24-hodinový formát času<br><br>

**Fallback jazyk**<br>
- čo sa stane, ak jazyk nie je dostupný?<br>
- načíta sa predvolený jazyk alebo zostane prázdna stránka?<br><br>

**Smer písma a rozloženie (LTR vs RTL)**<br>
- funguje RTL správne pre arabčinu, hebrejčinu atď.?<br>
- nie je rozbité UI?<br><br>

**Špecifické znaky a fonty**<br>
- diakritika, ázijské znaky, špeciálne symboly – zobrazenie aj kopírovanie<br><br>

**Rozhranie**<br>
- reaguje UI na zmenu jazyka bez reloadu?<br>
- má každý jazyk svoju lokalizovanú verziu emailov, notifikácií a chýb?<br><br>

**Dĺžka textov**<br>
- nemá nemčina trojnásobne dlhšie popisky?<br>
- neprerazí to dizajn?<br><br>

**Jazyková konzistencia**<br>
- nie sú miešané jazyky v jednej vete alebo tlačidle?<br><br>

**Ako môže pomôcť AI pri testovaní lokalizácie:**<br>
- Automatická detekcia chýbajúcich alebo príliš dlhých prekladov pomocou skriptov či pluginov s AI<br>
- Prekladový audit: AI nástroje (napr. GPT alebo DeepL) porovnajú kvalitu prekladu s referenčným textom<br>
- Generovanie testovacích fráz pre rôzne jazyky a dĺžky<br>
- UI vizuálne testy – porovnanie screenshotov rôznych jazykových verzií cez AI (napr. Percy, Applitools)<br><br>

Lokalizácia nie je len o prekladoch.<br>
Je to detailná a multidisciplinárna kontrola, kde spolupracujú testeri, dizajnéri aj vývojári.<br><br>

#testing #localization #qa #manualtesting #internationalization #softwaretesting #testovanie<br>
