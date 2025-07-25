# Ako testovať API, ktoré vracia zoznam položiek?<br><br>

Predstavme si jednoduchý príklad:<br><br>

GET /api/products?page=2&limit=10<br>
Očakávame odpoveď v JSON formáte s 10 produktmi na druhej stránke výsledkov.<br><br>

Čo všetko je potrebné otestovať?<br><br>

1. **Formát odpovede**<br>
- Je výstup validný JSON?<br>
- Sú všetky povinné polia prítomné?<br>
- Zodpovedajú dátové typy (napr. string, number, boolean) dokumentácii?<br><br>

2. **Počet záznamov**<br>
- Vracia správny počet položiek podľa parametra limit?<br>
- Pri poslednej stránke vracia menší počet, ak už nie je dostatok záznamov?<br><br>

3. **Stránkovanie (pagination)**<br>
- Funguje správne prepínanie medzi stránkami (page)?<br>
- Obsahuje odpoveď metaúdaje ako total, page, per\_page?<br><br>

4. **Filtrovanie a triedenie**<br>
- Správne reaguje na rôzne filtre (napr. category, status)?<br>
- Triedi výsledky podľa zadaného poľa (sort\_by=nameℴ=asc)?<br><br>

5. **Prázdne a neexistujúce výsledky**<br>
- Čo sa stane, ak filtrujeme podľa hodnoty, ktorá neexistuje?<br>
- Vracia prázdne pole [] alebo chybu?<br><br>

6. **Chybové stavy**<br>
- Ako reaguje na neplatné vstupy (limit=-1, page=abc)?<br>
- Očakávame správne HTTP kódy (400, 404, 422…) a popis chyby.<br><br>

7. **Výkon pri veľkom objeme dát**<br>
- Zvláda API vysoký počet záznamov?<br>
- Aká je doba odozvy pri limit=1000?<br><br>

8. **Bezpečnosť**<br>
- Nevracia API citlivé údaje (napr. heslá, interné ID)?<br>
- Sú všetky výstupy správne escapované?<br><br>

9. **Prístupnosť a lokalizácia**<br>
- Vracia API chybové hlášky vo viacerých jazykoch, ak je to potrebné?<br><br>

Testovanie API nie je len o tom, či sa dá zavolať. Je to o tom, ako dobre zvláda rôzne situácie – od ideálnych až po tie hraničné.<br><br>

#apitesting #softwaretesting #qa #restapi #testovanie #postman #testerskazóna #json #automation #juniorqa #testovanieaplikácií #tipnapiatok



