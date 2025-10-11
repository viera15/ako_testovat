# Ako testovať správne priradenie izby podľa parametrov (počet lôžok, výhľad)<br><br>

Príklad<br>
Predstav si, že zákazník hľadá dvojlôžkovú izbu s výhľadom na more.  
Po zadaní filtra sa mu zobrazí izba typu *Sea View Double Room*.  
Všetko vyzerá v poriadku — kým zistí, že v skutočnosti dostal izbu s výhľadom na park a s prístelkou namiesto manželskej postele.  
Takéto chyby poškodzujú dôveru a spôsobujú reklamácie.  
Preto je dôležité otestovať, že systém priraďuje izby presne podľa požadovaných parametrov a dostupnosti.<br><br>

## Ako otestovať<br><br>

1. **Definuj vstupné parametre**<br>
- Počet lôžok (1, 2, 3+), typ postele (manželská, oddelené).<br>  
- Typ výhľadu (more, hory, mesto, park).<br>  
- Doplnkové požiadavky (balkón, klimatizácia, bezbariérový prístup).<br><br>

2. **Over mapovanie parametrov v databáze**<br>
- Skontroluj, či má každá izba správne atribúty (napr. `beds=2`, `view=sea`).<br>  
- Porovnaj ich s údajmi, ktoré sa zobrazujú na stránke alebo v aplikácii.<br>  
- Testuj, čo sa stane, ak sú niektoré hodnoty v databáze prázdne alebo nesprávne.<br><br>  

3. **Testuj kombinácie filtrov a výsledkov**<br>
- Zadaj rôzne kombinácie (napr. 2 lôžka + výhľad na hory).<br>  
- Skontroluj, že sa nezobrazujú izby, ktoré tieto kritériá nespĺňajú.<br>  
- Otestuj aj hraničné prípady (napr. výhľad = „akýkoľvek“, počet lôžok = „1–3“).<br><br>  

4. **Simuluj obsadenosť a dynamické priradenie**<br>
- Zarezervuj časť izieb a sleduj, ako sa mení dostupnosť zvyšných.<br>  
- Over, že systém priraďuje izby len zo zoznamu voľných kapacít (t. j. nie už rezervované alebo blokované izby).<br>  
- Skontroluj, či nedochádza ku kolíziám (dve rezervácie rovnakej izby).<br><br>  

5. **Testuj zmeny a prebookovanie**<br>
- Zmeň parametre počas rezervácie (napr. z výhľadu na park na výhľad na more).<br>  
- Over, či systém priradí novú izbu podľa nových podmienok.<br>  
- Sleduj, či pôvodná izba zostane uvoľnená pre iných zákazníkov.<br><br>  

6. **Porovnaj zobrazenie medzi kanálmi**<br>
- Rezervačný portál, hotelová recepcia, interný systém — všetky by mali mať rovnaké dáta.<br>  
- Over, či sa názvy a popisy typov izieb zhodujú naprieč systémami.<br><br>  

7. **Negatívne testy**<br>
- Zadaj neexistujúcu kombináciu (napr. 5 lôžok + výhľad na more).<br>  
- Over, že systém správne zobrazí *„žiadna dostupná izba“* a neponúkne nesprávny typ.<br><br>  

8. **Logovanie a audit**<br>
- Skontroluj, či sa do logu zaznamenáva, akú izbu systém priradil a podľa akých kritérií.<br>  
- Over, že záznam obsahuje aj dátum, čas, používateľa a identifikátor izby.<br>  
