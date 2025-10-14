# Ako testovať rezervačný systém leteniek (trasy, prestupy, triedy)<br><br>

Príklad<br>
Predstav si, že klient si chce kúpiť letenku z Bratislavy do Tokia s prestupom vo Frankfurte.  
Vyberie ekonomickú triedu, no po zaplatení mu príde potvrdenie s inou trasou alebo triedou.  
Takáto chyba môže vzniknúť pri zlom párovaní údajov z rôznych systémov (rezervačný engine, letecká spoločnosť, platobná brána).  
Cieľom testovania je preveriť, že každý krok – od výberu trasy po potvrdenie letu – funguje konzistentne a bez straty informácií.<br><br>

## Ako otestovať<br><br>

1. **Vyhľadávanie letov**<br>
- Otestuj rôzne kombinácie miest (priamy let, let s prestupom, viac prestupov).<br>  
- Over reakciu systému pri neplatnom dátume, neexistujúcej trase alebo zrušenom lete.<br>  
- Sleduj výkon pri veľkom počte dostupných letov.<br><br>

2. **Výber trasy a triedy**<br>
- Skontroluj zobrazenie všetkých dostupných tried (economy, business, first).<br>  
- Otestuj zmenu triedy počas rezervácie – napr. upgrade pri prestupe.<br>  
- Over, že sa správne prepočítava cena pri zmene trasy alebo počte prestupov.<br><br>

3. **Kombinované a spätné lety**<br>
- Otestuj obojsmerné rezervácie (round-trip) a lety s viacerými prestupmi.<br>  
- Sleduj, či sa správne načítavajú dátumy a časy v rôznych časových pásmach.<br>  
- Over, že systém správne páruje odlety a prílety (žiadne chýbajúce úseky).<br><br>

4. **Cenotvorba a platba**<br>
- Otestuj výpočet ceny podľa triedy, trasy a poplatkov (letiskové, servisné).<br>  
- Simuluj zmenu meny alebo promo kódu – systém musí prepočítať sumu.<br>  
- Over reakciu na zlyhanie platby – chybová hláška, možnosť opakovania.<br><br>

5. **Rezervácia a potvrdenie**<br>
- Sleduj, či všetky údaje (mena, let, dátumy, sedadlo) zodpovedajú výberu.<br>  
- Over generovanie potvrdenia (e-ticket) – číslo rezervácie, PDF, e-mail.<br>  
- Skontroluj aj integráciu s partnerskými systémami (napr. letecká aliancia).<br><br>

6. **Zmeny a storno**<br>
- Otestuj prebookovanie letu, zmenu dátumu alebo mena cestujúceho.<br>  
- Over správnosť výpočtu doplatkov, poplatkov a refundácií.<br>  
- Simuluj výpadok API leteckej spoločnosti počas zmeny rezervácie.<br><br>

7. **UX a edge prípady**<br>
- Testuj dostupnosť na mobile, responzivitu a prístupnosť formulárov.<br>  
- Otestuj prácu s neúplnými údajmi (napr. chýbajúci pas).<br>  
- Sleduj rýchlosť načítania výsledkov a správne zobrazovanie dĺžky prestupov.<br>

