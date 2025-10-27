# Ako testovať storno z dôvodu vyššej moci (napr. štrajk, pandémia)

**Príklad**<br>
Predstav si klienta, ktorý má zaplatený zájazd s letom, hotelom a prenajatým autom.  
Týždeň pred odchodom dôjde k štrajku letovej kontroly alebo uzavretiu hraníc z dôvodu pandémie.  
Cestovná kancelária musí zrušiť celý zájazd, vrátiť peniaze alebo ponúknuť náhradný termín.  
V praxi sa tu stretávajú právne, zmluvné a technické procesy — čo musí systém spraviť automaticky a čo ručne rieši pracovník cestovky?  
Tester má preveriť, či systém reaguje korektne: ruší všetky zložky balíka, informuje klienta a účtovne zachytí dôvod storna ako vyššiu moc (*force majeure*), nie ako bežné zrušenie.  

<br><br>

## Ako otestovať

**1. Identifikácia dôvodu storna**  
- Over, že v systéme existuje samostatný typ storna *„vyššia moc“* odlíšený od bežného zrušenia klientom.  
- Skontroluj, že tento dôvod nemožno meniť manuálne bez oprávnenia (napr. len admin alebo pracovník s právom eskalácie).  
- Testuj, či sa dôvod prenáša do všetkých napojených systémov – účtovníctvo, CRM, reporting.  

<br>

**2. Reťazová reakcia na zrušenie**  
- Simuluj aktiváciu storna na úrovni jednej služby (napr. zrušený let) a sleduj, či systém automaticky zruší aj ubytovanie, transfer a doplnkové služby.  
- Otestuj, že klient dostane len jedno súhrnné potvrdenie o zrušení, nie viacero čiastočných e-mailov.  
- Over, že rezervácie u partnerov sa rušia s rovnakým `ID` balíka a dôvodom *force majeure*.  

<br>

**3. Refundácie a dobropisy**  
- Skontroluj výpočet vrátenej sumy – pri vyššej moci sa obvykle vracia 100 % ceny, ak nie je stanovené inak.  
- Validuj kurzové rozdiely, zaokrúhlenia a spôsob refundácie podľa pôvodného kanála (`karta`, `prevod`, `poukaz`).  
- Simuluj zlyhanie refundácie a sleduj chybové správy a logovanie.  

<br>

**4. Notifikácie a komunikácia s klientom**  
- Over načasovanie e-mailu a SMS: informácia o storne musí prísť ihneď po zmene stavu.  
- Skontroluj text notifikácií – musí obsahovať dôvod *„vyššia moc“*, poučenie o náhradných možnostiach a kontakty.  
- Testuj viacjazyčné verzie správ a diakritiku.  

<br>

**5. Prepojenia s partnermi a právne väzby**  
- Sleduj `API` volania – či partneri dostávajú správny status `cancelled by supplier / force majeure`.  
- Otestuj prípad, keď partner neakceptuje dôvod *„vyššia moc“* – systém má umožniť eskaláciu a ručné potvrdenie.  
- Validuj auditný záznam – dátum, kto storno spustil, aký bol dôvod, komu bolo nahlásené.  

<br>

**6. Zmeny po storne**  
- Pokus o opätovné obnovenie storna musí byť blokovaný, pokiaľ nie je povolený výnimkou.  
- Over, že systém správne zakazuje ďalšie úpravy (napr. zmenu dátumu) po potvrdení storna vyššou mocou.  
- Skontroluj, že balík zostáva v stave *cancelled*, ale údaje o klientovi a transakcii sú zachované pre audit.  

<br>

**7. Reporting a štatistiky**  
- Over, že storno z dôvodu vyššej moci sa zobrazuje v samostatnej kategórii reportov.  
- Otestuj export do účtovného a analytického systému – správne zaúčtovanie bez penalizačných poplatkov.  
- Sleduj konzistentnosť medzi reportom a databázou – počet stornovaných balíkov, sumy, dátumy.  

<br>

**8. Výnimočné situácie**  
- Testuj hromadné storno viacerých zájazdov (napr. pri plošnej uzávierke letiska).  
- Simuluj rozdielne dátumy zrušenia jednotlivých služieb (hotel zrušený neskôr ako let).  
- Over, že logy zaznamenávajú všetky udalosti vrátane neúspešných pokusov o refundáciu.  
<br>