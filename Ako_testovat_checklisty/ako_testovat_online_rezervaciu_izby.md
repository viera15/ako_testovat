# Ako testovať online rezerváciu izby (dostupnosť, termíny, kapacita)

Príklad
Predstav si, že používateľ chce zarezervovať dvojlôžkovú izbu v hoteli na 10.–12. augusta. Systém mu však umožní zvoliť termín, hoci je už obsadený. Po zaplatení mu príde potvrdenie, ale recepcia ho kontaktuje, že izba nie je voľná. Takýto bug má okamžitý dopad na reputáciu hotela a spôsobuje refundácie aj nespokojnosť klienta. Preto je dôležité testovať rezervácie nielen z pohľadu UX, ale aj z pohľadu dátovej konzistencie, kapacít a prepojení s inými systémami.

## Ako otestovať

1. **Dostupnosť izieb**
- Over, že systém správne zobrazuje len voľné izby podľa termínu a počtu osôb.  
- Simuluj paralelné rezervácie (dvaja klienti v tom istom čase) a sleduj, či nedôjde k prekrývaniu.  
- Skontroluj logiku blokovania izby po odoslaní rezervácie (napr. rezervácia v stave *pending payment*).

2. **Termíny a kalendár**
- Testuj správne zobrazovanie dní – vrátane prechodu mesiacov, sviatkov a rôznych časových pásiem.  
- Skontroluj, či systém neumožňuje výber dátumu v minulosti alebo dlhšie pobyty, než hotel povoľuje.  
- Otestuj správanie pri čiastočne obsadených termínoch (napr. prvý deň voľný, druhý nie).

3. **Kapacita a typ izby**
- Over, že počet osôb nepresahuje kapacitu izby (dospelí, deti, prístelky).  
- Skontroluj, že zobrazená cena sa aktualizuje podľa kapacity a dĺžky pobytu.  
- Testuj prepojenie s inventárom (napr. ak je izba mimo prevádzky, nesmie byť dostupná).

4. **Cenové a storno podmienky**
- Otestuj, že zľavy (napr. *„3 noci za cenu 2“*) sa uplatnia len v platnom období.  
- Skontroluj, či systém správne aplikuje sezónne ceny a dane.  
- Over proces storna a refundácie – automatická vs. manuálna.

5. **Integrácie a platby**
- Testuj spojenie s platobnou bránou (úspešná platba, zamietnutie, timeout).  
- Over prepojenie s externým PMS (Property Management System) – aktualizácia stavu izieb po potvrdení.  
- Skontroluj, či sa potvrdenie rezervácie generuje správne (obsah, jazyk, dátumy).

6. **UX a chyby používateľa**
- Skús neúplnú alebo chybne vyplnenú rezerváciu (chýbajúci dátum, nesprávny e-mail).  
- Over zrozumiteľnosť chybových hlášok (*„Izba už nie je dostupná“*).  
- Otestuj responzívnosť formulára a použiteľnosť na mobile.

7. **Negatívne a hraničné scenáre**
- Viacero používateľov rezervuje poslednú izbu naraz → over, kto ju skutočne dostane.  
- Skontroluj, čo sa stane po výpadku internetu počas platby.  
- Testuj, či systém správne obnoví stav po opätovnom prihlásení.
