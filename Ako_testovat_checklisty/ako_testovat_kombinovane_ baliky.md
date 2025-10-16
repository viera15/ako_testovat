# Ako testovať kombinované balíky (ubytovanie + doprava + transfer)

Príklad
Predstav si klienta, ktorý si cez portál rezervuje balík **„Leto pri mori“** — obsahuje ubytovanie v hoteli, spiatočný let a transfer z letiska.  
Na webe všetko vyzerá v poriadku, ale po príchode zistí, že transfer sa neobjavil v systéme dopravcu, pretože bol uložený pod iným číslom objednávky.  
V praxi to znamená nielen nespokojného zákazníka, ale aj dodatočné náklady na presuny, urgentné telefonáty a poškodenie reputácie.  
Kombinované balíky sú preto testovacou výzvou — vyžadujú dôslednú kontrolu väzieb medzi viacerými systémami.

## Ako otestovať

1. **Prepojenie a identifikácia služieb**
- Over, že všetky položky (hotel, doprava, transfer) majú spoločné **ID balíka** a jednotné číslovanie rezervácií.  
- Kontroluj väzby v databáze aj logoch: subobjednávky musia patriť jednému klientovi.  
- Testuj generovanie potvrdení a voucherov – musia obsahovať všetky súčasti balíka bez vynechania.  

2. **Cenotvorba a účtovanie**
- Otestuj správne rozpočítanie ceny medzi služby (hotel, doprava, transfer), sleduj DPH a servisné poplatky.  
- Validuj zľavy (napr. skorá rezervácia, deti zdarma, promo kódy) – musia sa uplatniť na celý balík.  
- Simuluj zmenu meny alebo kurzu – prepočet sa musí zachovať pri zmenách komponentov.  
- Skontroluj zaokrúhľovanie cien a rozdiely medzi prehľadom a finálnou faktúrou.  

3. **Rezervačný proces a workflow**
- Prechádzaj proces krok po kroku: výber termínu, ubytovania, dopravy a sleduj dynamické aktualizácie cien.  
- Testuj rôzne kombinácie: hotel bez transferu, let + hotel, len transfer – systém musí správne reagovať.  
- Simuluj výpadok jednej služby (napr. API dopravcu) a sleduj, či systém zablokuje platbu alebo uloží chybnú objednávku.  
- Otestuj paralelné rezervácie viacerých klientov na posledné miesto – over konflikt v kapacite.  

4. **Potvrdenia, dokumenty a synchronizácia**
- Kontroluj generované potvrdenia a vouchery – údaje musia sedieť s rezerváciou v systéme partnera.  
- Otestuj preklady a lokalizácie (zmena jazyka webu) – dátumy, mená a miesta sa nesmú zameniť.  
- Validuj dátumy príchodu/odchodu – musia byť synchronizované s časom letu a transferom.  

5. **Zmeny a storno podmienky**
- Simuluj zmenu len jednej časti balíka (napr. iný let) a sleduj, či sa aktualizuje aj ubytovanie a transfer.  
- Over, že storno celého balíka ruší všetky jeho časti a generuje správne storno poplatky.  
- Otestuj čiastočné storno – systém má upozorniť, že balík je nekompletný a vyžaduje potvrdenie.  
- Sleduj, či sa refundácie vykonávajú správne a do správnych kanálov platby.  

6. **Integrácie s partnermi**
- Sleduj API volania medzi systémom cestovky, hotelom a dopravcom; validuj statusy *confirmed*, *cancelled*, *pending*.  
- Testuj príjem odpovedí v rôznych časoch (oneskorené potvrdenie partnera).  
- Otestuj párovanie ID rezervácie s externými systémami a reakciu na chybové kódy.  

7. **Používateľská skúsenosť a komunikácia**
- Notifikácie musia jasne vysvetliť, čo sa zmenilo (napr. *„Zmenil sa termín odletu, hotel ostáva rovnaký“*).  
- Kontroluj načasovanie e-mailov a SMS – informácie musia prísť po potvrdení každej zložky.  
- Over, že používateľ vidí v prehľade všetky časti balíka a ich stav.  
- Testuj chyby: ak jedna služba zlyhá, klient musí dostať jasné vysvetlenie, čo robiť ďalej.  

8. **Testy výnimočných situácií**
- Výpadok partnera počas platby, zmena kurzu, chýbajúce potvrdenie, duplikát objednávky.  
- Kontroluj logy a integrácie – či sa chyby logujú a dajú dohľadať.  
