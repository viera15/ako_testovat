# Ako testovať cestovné poistenie ako súčasť objednávky

## Príklad
Predstav si, že klient si cez portál kúpi balík **„Víkend v Ríme“** – obsahuje letenku, hotel a voliteľné cestovné poistenie.  
Systém mu však v potvrdení objednávky poistenie neuvádza, pretože API poisťovne v danom momente nevrátilo číslo poistnej zmluvy.  
Klient si myslí, že poistenie má, no v skutočnosti nie je uzavreté.  
V prípade nehody by zodpovednosť niesol predajca.  
Testovanie cestovného poistenia ako súčasti objednávky je preto kľúčové — ide o integráciu viacerých systémov, právnu istotu a dôveru zákazníka.  

## Ako otestovať

1. **Výber a pripojenie poistenia**
- Over, že poistenie možno pridať a odstrániť v správnej fáze objednávky (pred platbou).  
- Skontroluj, či sa ponuka poistenia mení podľa cieľovej destinácie, dĺžky pobytu a veku cestujúceho.  
- Validuj, že sa zobrazuje správny názov produktu, rozsah krytia a cena.  

2. **Dáta odosielané poisťovni**
- Testuj správnosť údajov odosielaných do systému poisťovne (meno, dátumy, destinácia, suma zájazdu).  
- Otestuj chybové scenáre: neúplné údaje, neplatný dátum, prekročený limit veku.  
- Over, že pri zlyhaní API sa zobrazí jasná správa pre používateľa a systém neukončí objednávku v chybnom stave.  

3. **Potvrdenie a dokumentácia**
- Po zaplatení musí byť vygenerované číslo poistnej zmluvy a priložený dokument (PDF).  
- Kontroluj, že údaje na zmluve zodpovedajú objednávke (mená, dátumy, suma, typ poistenia).  
- Otestuj viacjazyčné verzie zmluvy a správne označenie meny.  

4. **Zmeny a storno poistenia**
- Simuluj zmenu termínu cesty — poistenie sa musí automaticky aktualizovať alebo vyžadovať nové uzatvorenie.  
- Pri storne zájazdu over, že poistenie sa buď zruší, alebo zostane podľa podmienok produktu (napr. storno poistenie).  
- Validuj výpočet refundácie a prerozdelenie poistného pri viacerých cestujúcich.  

5. **Integrácie a logovanie**
- Sleduj API volania medzi systémom cestovky a poisťovne – statusy *created*, *confirmed*, *error*.  
- Otestuj spracovanie oneskorených odpovedí a opakované odosielanie dát (*retry policy*).  
- Over, že všetky kroky (odoslanie, potvrdenie, zrušenie) sa logujú a sú dohľadateľné.  

6. **Používateľská skúsenosť**
- Po pridaní poistenia sa musí okamžite zmeniť celková cena objednávky.  
- V e-mailovom potvrdení a prehľade objednávky musí byť poistenie jasne uvedené.  
- Testuj, či klient dostáva notifikáciu aj od poisťovne, nie len od cestovky.  

7. **Špeciálne scenáre**
- Príplatky za rizikové športy, predĺženie pobytu, viacero cestujúcich s rôznym krytím.  
- Over limity – napr. maximálny počet dní, výšku poistného plnenia.  
- Simuluj výpadok poisťovne počas platby – systém nesmie potvrdiť neexistujúcu zmluvu.  
