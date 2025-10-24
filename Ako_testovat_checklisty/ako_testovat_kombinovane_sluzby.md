# Ako testovať kombinované služby od viacerých partnerov (hotel + prenájom auta)

**Príklad**<br>
Predstav si klienta, ktorý si cez portál objedná balík *„Víkend v Toskánsku“* – ubytovanie v penzióne, prenájom auta od lokálneho partnera a doplnkové služby ako GPS či detská sedačka.  
Po príchode na miesto zistí, že auto nečaká – rezervačný systém odoslal údaje s oneskorením a partner ich nesynchronizoval.  
Klient je bez dopravy, hotel musí volať náhradného poskytovateľa a vznikajú ďalšie náklady aj stres.  
Práve preto je testovanie takýchto multi-partner integrácií kľúčové – každý článok reťazca musí spoľahlivo spolupracovať.  

<br><br>

## Ako otestovať

**1. Integrácia a identifikátory služieb**  
- Over, že každá služba (hotel, prenájom auta, doplnky) je priradená k spoločnému `ID` rezervácie.  
- Sleduj, či sa do databázy zapisuje správny vzťah medzi subobjednávkami (parent-child väzby).  
- Testuj, že potvrdenia obsahujú všetky súčasti – hotel, auto, prípadne doplnky – s jednotnými číslami.  

<br>

**2. Cenotvorba a fakturácia**  
- Otestuj výpočet ceny: základ, dane, poplatky (napr. airport fee, city tax).  
- Sleduj, či sa zľavy alebo kupóny aplikujú na celkový balík, nie len na jednu službu.  
- Pri zmene meny alebo kurzu sleduj, či sa cena preratá vo všetkých položkách.  

<br>

**3. Rezervačný proces a validácie**  
- Prejdi kompletný proces: výber auta podľa kategórie, miesta prevzatia, času a dostupnosti.  
- Simuluj zmenu dátumu hotela – prenájom sa musí automaticky posunúť alebo upozorniť používateľa.  
- Otestuj situáciu, keď partner nahlási nedostupnosť – systém má ponúknuť alternatívu, nie zlyhať.  

<br>

**4. API komunikácia s partnermi**  
- Sleduj výmenu správ medzi systémami: `confirmed`, `cancelled`, `pending`.  
- Testuj, ako systém reaguje na oneskorené odpovede alebo chybové kódy (`500`, `408`).  
- Over, že logy obsahujú presné časové pečiatky a dá sa dohľadať celá história komunikácie.  

<br>

**5. Zmeny a storno podmienky**  
- Simuluj storno len prenájmu auta – over, či zostane platné ubytovanie.  
- Otestuj storno celého balíka – zrušiť sa musia všetky služby a správne vypočítať storno poplatky.  
- Sleduj, či refundácia ide na správny účet a vo výpise sú uvedené všetky položky.  

<br>

**6. Potvrdenia a dokumenty**  
- Kontroluj e-maily a vouchery – musia jasne rozlišovať partnerov (hotel, car rental).  
- Otestuj viacjazyčné verzie – lokalizácia mien, dátumov a miest musí byť jednotná.  
- Validuj, že všetky časy sú v správnych časových pásmach (napr. letisko vs. hotel).  

<br>

**7. Používateľská skúsenosť a komunikácia**  
- Over, že používateľ v prehľade vidí stav každej služby (*potvrdené*, *čaká sa*, *zrušené*).  
- Simuluj notifikácie: e-mail o potvrdení auta, SMS o zmene hotela – načasovanie musí byť logické.  
- Testuj chybové situácie: ak auto nie je dostupné, systém musí jasne vysvetliť, čo sa dá urobiť.  

<br>

**8. Výpadky a výnimočné scenáre**  
- Simuluj výpadok `API` partnera, chybu platby, duplikáciu objednávky.  
- Sleduj, či sa transakcia správne roll-backne a klient nedostane neúplné potvrdenie.  
- Kontroluj záznamy v logoch – musia byť dohľadateľné všetky chybové stavy.  
<br>