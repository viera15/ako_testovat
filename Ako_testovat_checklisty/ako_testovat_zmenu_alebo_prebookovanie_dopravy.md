# Ako testovať zmenu alebo prebookovanie dopravy<br><br>

**Príklad**
Klient si zarezervuje spiatočnú cestu autobusom, no deň pred odchodom sa rozhodne pre skorší spoj.  
Po zmene termínu však systém ponechá pôvodnú rezerváciu v stave *confirmed* a dopravca má klienta zapísaného dvakrát.  
Takéto situácie môžu spôsobiť duplicity, nesprávne fakturácie a zbytočné reklamácie.  
Preto treba testovať nielen zmenu cestovného termínu, ale aj celú logiku rebookingu.<br><br>  

## Ako otestovať<br><br>

**1. Proces zmeny dopravy**<br>  
- Over, že používateľ môže zmeniť termín len pre *aktívnu* rezerváciu.<br>  
- Otestuj, či systém pri zmene termínu automaticky ruší pôvodnú jazdu.<br>  
- Skontroluj, že po úspešnom rebookingu má nová rezervácia správny stav (*confirmed*).<br><br>  

**2. Validácia dát a väzieb**<br>  
- Sleduj, či zostáva zachované ID klienta, číslo objednávky a napojenie na platbu.<br>  
- Over, že nové termíny sa správne prepíšu aj v databáze dopravcu a v notifikáciách.<br>  
- Kontroluj, že sa neobjaví viac ako jedna aktívna rezervácia pre rovnakého klienta.<br><br>  

**3. Platby a refundácie**<br>  
- Ak sa cena zmenila, otestuj, či systém vypočíta rozdiel (doplatok alebo vratku).<br>  
- Skontroluj, že refundácia prebieha cez rovnaký platobný kanál ako pôvodná transakcia.<br>  
- Validuj správne generovanie dokladu o zmene alebo potvrdenia o rebookingu.<br><br>  

**4. Integrácie a API**<br>  
- Otestuj odosielanie aktualizovaných dát do systému dopravcu (status `changed`, `cancelled`, `new`).<br>  
- Simuluj oneskorenú odpoveď dopravcu – systém má zmenu označiť ako *pending*.<br>  
- Kontroluj logy, či obsahujú údaje o pôvodnom aj novom termíne.<br><br>  

**5. Notifikácie a komunikácia**<br>  
- Otestuj, že po zmene termínu sa odošle potvrdenie e-mailom aj SMS.<br>  
- Over, že text správy obsahuje nové údaje o spojoch, dátumoch a časoch.<br>  
- Sleduj, či staré notifikácie neostanú aktívne alebo duplicitné.<br><br>  

**6. Používateľské rozhranie**<br>  
- Skontroluj, že klient vidí jasne označenú pôvodnú aj novú rezerváciu (napr. *Zmenené 12. 10. 2025*).<br>  
- Testuj správanie tlačidla `Zmeniť spoj` – musí byť nedostupné po termíne odchodu.<br>  
- Otestuj, že systém upozorní na poplatok za zmenu, ak sa uplatňuje.<br><br>  

**7. Chybové scenáre**<br>  
- Simuluj výpadok počas potvrdenia zmeny – systém má umožniť pokračovať po obnovení.<br>  
- Skontroluj, že pri chybe platobnej brány sa rebooking zruší a nevznikne duplicita.<br>  
- Testuj manuálne zásahy v backende – zmena termínu nesmie porušiť väzby na cestovný lístok.<br><br>  

**8. Záznamy a audit**<br>  
- Over, že v audit logu sa zaznamená pôvodný aj nový termín, čas zmeny a používateľ, ktorý ju vykonal.<br>  
- Skontroluj, že sa do exportov (napr. pre dopravcu) dostane len platná verzia rezervácie.<br>  
