# Ako testovať systém, kde sa menia práva používateľa?<br><br>


Zmeny roly môžu výrazne ovplyvniť, čo používateľ vidí, čo môže robiť a čo má zakázané. A práve to je výzva pre testerov.<br><br>

Príklad zo života:<br>
Máme interný systém, kde môže byť používateľ zamestnancom, manažérom alebo adminom. Každá rola má iné oprávnenia – napríklad zamestnanec môže vidieť len svoje dáta, manažér údaje svojho tímu a admin všetko vrátane nastavení systému.<br><br>

Na čo sa zamerať pri testovaní zmien rolí a oprávnení?<br><br>

**Správna dostupnosť funkcií**<br>
▫️ Po zmene roly sú dostupné len funkcie prislúchajúce danej roli?<br>
▫️ Nezostali aktívne žiadne “zakázané” tlačidlá?<br><br>

**Skryté vs. zakázané akcie**<br>
▫️ Je rozdiel medzi tým, čo je skryté (nevidno) a čo je zakázané (vidno ale nefunguje)?<br>
▫️ Vie sa používateľ pomocou priameho linku dostať k akcii, ktorú by nemal?<br><br>

**Zmena počas relácie**<br>
▫️ Čo sa stane, keď sa rola zmení počas toho, ako je používateľ prihlásený?<br>
▫️ Zmení sa UI dynamicky, alebo sa musí znovu prihlásiť?<br><br>

**Roly vs. údaje**<br>
▫️ Zobrazujú sa len tie dáta, ktoré daná rola smie vidieť?<br>
▫️ Nedá sa pomocou filtrov či API vytiahnuť niečo, čo by nemalo byť dostupné?<br><br>

**Audity a logovanie**<br>
▫️ Zaznamenáva sa, kto a kedy zmenil rolu?<br>
▫️ Dá sa dohľadať, aké oprávnenia boli pridelené a odstránené?<br><br>

**Regresné testovanie pri každej zmene práv**<br>
▫️ Over, či nová úroveň prístupu nezrušila predchádzajúce funkčnosti<br>
▫️ Spusti testy opakovane po zmene konfigurácie rolí<br><br>

Zmena oprávnení je citlivá vec – malá chyba a systém môže byť nechtiac zneužiteľný. Pri testovaní práv je potrebné mať oči otvorené nielen pre UI, ale aj pre backendové volania, API a dáta.<br><br>

#testing #securitytesting #rolesandpermissions #QA #softwaretesting #manualtesting #testovanie #testautomation



