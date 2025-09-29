# Ako testovať CRM banky a prepojenie so zmluvami<br><br>

Príklad<br>
Predstav si, že bankár založí v CRM nový profil klienta a rovno vytvorí úverovú zmluvu. Ak sa pole „trvalý pobyt“ uloží len v CRM, ale nedostane sa do zmluvy, dokument je právne neplatný. Ešte horší scenár nastane, ak systém doplní nesprávne údaje zo starej verzie profilu. Chyby v prepojení CRM so zmluvnými systémami znamenajú nielen reklamácie, ale aj vysoké právne a reputačné riziká.<br><br>

## Ako otestovať<br><br>

1. **Základné prepojenie dát**<br>
- Over, či sa všetky povinné polia z CRM (meno, adresa, rodné číslo/IČO, kontakty) korektne prenášajú do zmluvy.<br>
- Skontroluj konzistenciu údajov – ak zmeníš pole v CRM, odrazí sa aj v zmluvnom systéme?<br><br>

2. **Scenáre vytvárania zmluvy**<br>
- Nový klient – vytvorenie profilu a zmluvy naraz.<br>
- Existujúci klient – aktualizácia údajov a generovanie novej zmluvy.<br>
- Hromadná zmena (napr. prechod na nový cenník) a jej premietnutie do viacerých zmlúv.<br><br>

3. **Integrácia a formáty**<br>
- Testuj API volania medzi CRM a zmluvným modulom – správnosť odpovedí, chybové hlášky, timeouty.<br>
- Skontroluj špeciálne znaky a diakritiku v dokumente (napr. „Š“ v mene).<br>
- Over formáty dátumov (DD-MM-YYYY vs. YYYY-MM-DD).<br><br>

4. **Bezpečnosť a oprávnenia**<br>
- Otestuj, kto môže generovať, meniť alebo mazať zmluvy.<br>
- Over, či sa citlivé dáta (rodné číslo, číslo účtu) správne maskujú alebo šifrujú.<br>

5. **Validácia výstupov**<br>
- Skontroluj, či sa zmluva uloží v správnej verzii (PDF/A, podpísané PAdES).<br>
- Porovnaj obsah zmluvy s údajmi v CRM – napr. cez automatizovaný skript alebo kontrolný zoznam.<br>
- Otestuj, že pri zrušení alebo aktualizácii zmluvy v CRM sa to správne premietne aj v archíve dokumentov.<br><br>

6. **Negatívne scenáre**<br>
- Neúplný profil v CRM – systém by nemal dovoliť vytvoriť zmluvu.<br>
- Strata konektivity medzi CRM a zmluvným modulom – čo sa stane s rozpracovanou zmluvou?<br>
- Duplicitný profil klienta – ako sa správa systém pri generovaní dvoch zmlúv?<br>
