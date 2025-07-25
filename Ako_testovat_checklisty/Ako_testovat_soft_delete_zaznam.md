# Ako testovať „nezmazateľný“ záznam (soft delete)<br><br>

V niektorých systémoch býva soft delete implementovaný veľmi jednoducho – záznam sa fyzicky neodstráni, len sa v databáze nastaví určitá hodnota (napr. is_deleted = true alebo stav = 'zmazané').<br>
Vďaka tomu sa dá záznam opäť zobraziť úpravou tejto hodnoty, ak je na to oprávnenie. V logoch alebo histórii záznamu býva zaznamenané, kto a kedy záznam zmazal.<br><br>

Takéto riešenie je praktické, ale vyžaduje dôsledné testovanie. Na čo všetko sa zamerať?<br><br>

Čo otestovať pri soft delete?<br><br>

1. **Zobrazenie v UI**<br>
- Bežný používateľ záznam nevidí<br>
- Admin/tester ho vidí, prípadne s info „zmazané“<br>
- V detaile záznamu môže byť hláška „Tento záznam bol zmazaný“<br><br>

2. **API správanie**<br>
- GET môže vrátiť 404, 410 alebo špeciálnu hlášku<br>
- PUT/PATCH/DELETE: povolené len pre vybrané roly?<br>
- Zabezpečiť, aby sa „mŕtvy“ záznam nedal modifikovať bez oprávnení<br><br>

3. **Zmeny v databáze**<br>
- Pole is_deleted, deleted_at, deleted_by (alebo omyl) má správnu hodnotu<br>
- Záznam nebol fyzicky zmazaný<br>
- Dáta sú konzistentné (žiadne siroty v iných tabuľkách)<br><br>

4. **Logy a audit**<br>
- Kto, kedy a ako záznam zmazal?<br>
- Je zaznamenaný aj pokus o prístup k zmazanému záznamu?<br><br>

5. **Obnovenie záznamu**<br>
- Dá sa obnoviť cez UI alebo iba cez databázu?<br>
- Obnova vracia záznam do pôvodného stavu?<br>
- Funguje aj prepojenie na ďalšie dáta (napr. komentáre, prílohy)?<br><br>

6. **Bezpečnostné testy**<br>
- Vie si bežný používateľ načítať zmazané dáta cez API/URL?<br>
- Ošetrené sú aj pokusy o úmyselnú obnovu dát bez práv?<br><br>

**Tip pre testerov:**<br>
Pri testovaní soft delete sa pozeraj nielen na to, čo vidíš, ale aj na to, čo už vidieť nemáš – a či sa to nedá obísť. Kombinuj testy cez UI, API a priamu kontrolu v databáze.<br>
