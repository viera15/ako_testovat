# Ako testovať zrušenie účtu a výmaz údajov (GDPR)<br><br>

Príklad<br><br>
Predstav si klienta, ktorý po rokoch využívania bankovej aplikácie požiada o zrušenie účtu a vymazanie všetkých svojich osobných údajov. Ak systém údaje nesprávne ponechá (napr. e-mail v marketingovej databáze alebo históriu prihlásení v logoch), vzniká riziko porušenia GDPR a vysokých pokút. Tester má preto overiť, že proces výmazu je konzistentný, auditovateľný a nezanecháva citlivé zvyšky.<br><br>

## Ako otestovať<br><br>

1. **Overenie žiadosti o zrušenie účtu**<br>
- Simuluj podanie žiadosti (UI, call centrum, písomná forma).<br>
- Skontroluj, či je proces autentifikácie dostatočný (zamedzenie zneužitia treťou stranou).<br>  
- Otestuj, či systém správne zaznamená čas, spôsob a identitu žiadateľa.<br><br>  

2. **Technická realizácia výmazu**<br>
- Over, že všetky osobné údaje používateľa sú odstránené zo systémov v súlade s politikou retention.<br>  
- Kontroluj databázy (produkčné aj archívne), či záznamy boli anonymizované alebo vymazané.<br>  
- Testuj logy – osobné údaje nesmú zostať v prístupných častiach, len v povolených auditoch (hashované, pseudonymizované).<br><br>  

3. **Integrácie a prepojené systémy**<br>
- Otestuj, či sa výmaz premietol do všetkých prepojených systémov (CRM, billing, notifikačné služby, marketing).<br>  
- Over prenos výmazu cez API – neostávajú kópie dát u partnerov?<br>  
- Sleduj správne chybové stavy (napr. ak partner nepotvrdí výmaz).<br><br>  

4. **Retenčné a právne výnimky**<br>
- Over, že údaje, ktoré musia zostať kvôli legislatíve (napr. účtovné doklady), sú zachované, no oddelené od používateľského profilu.<br>  
- V praxi to znamená, že transakčné a účtovné dáta sú uložené v archíve alebo anonymizované tak, aby už neboli priamo spojené s konkrétnym používateľom.<br>  
- Skontroluj, či je k nim obmedzený prístup len pre oprávnené roly, napríklad účtovníkov, audítorov alebo compliance špecialistov.<br><br>  

5. **Používateľská skúsenosť**<br>
- Skontroluj, či používateľ dostane jasné potvrdenie o zrušení účtu a výmaze.<br>  
- Otestuj, či sú komunikácie zrozumiteľné a neobsahujú zvyšky citlivých údajov.<br>  
- Over, že po výmaze sa používateľ už nemôže prihlásiť.<br><br>  

6. **Bezpečnostné a negatívne scenáre**<br>
- Pokus o prihlásenie po výmaze – systém musí odmietnuť.<br>  
- Over, či výmaz jedného používateľa nezasiahne údaje iných.<br>  
- Testuj, že nie je možné proces obísť či zvrátiť bez autorizácie.<br>  
