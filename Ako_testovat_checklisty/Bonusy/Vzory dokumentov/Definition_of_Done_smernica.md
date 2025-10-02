# Interná smernica: Definition of Done (DoD)<br><br>
## Verzia 1.0 — účinná od: [dopíš dátum]<br><br>

### Účel dokumentu<br>
Táto smernica slúži na zjednotenie vnímania stavu „hotovo“ naprieč všetkými rolami v tíme. Zamedzuje nejasnostiam a zvyšuje kvalitu doručovaných výstupov.<br><br>

## Spoločné základné DoD pre všetky úlohy<br>
Každá úloha (story, bug, task...) sa považuje za „hotovú“ iba vtedy, ak sú splnené nasledovné spoločné podmienky:<br>
- Úloha má priradeného zodpovedného človeka.<br>
- Je presne popísaná a má definované akceptačné kritériá.<br>
- Bolo vykonané peer-review alebo code review.<br>
- Sú pokryté testami (unit/integration/E2E podľa potreby).<br>
- Výsledky testov sú zelené.<br>
- Úloha je nasadená (do test/prod podľa definície) alebo pripravená na release.<br>
- Dokumentácia bola aktualizovaná (ak sa týka funkcionality alebo API).<br>
- Stakeholderi boli informovaní.<br>
- Výstup bol overený podľa role QA/testera.<br><br>

## Definition of Done podľa rolí<br><br>

### Vývojár<br>
- Kód je commitnutý do hlavnej vetvy podľa Git flow.<br>
- Prešiel code review (nie self-merge).<br>
- Je pokrytý unit testami s minimálnym pokrytím XX %.<br>
- Edge casy sú zohľadnené.<br>
- Kód je nasadený na test prostredie.<br>
- Do ticketu sú pridané poznámky pre testera (napr. čo overiť, na čo si dať pozor).<br><br>

### Tester/QA<br>
- Sú vytvorené testy podľa akceptačných kritérií (manuálne alebo automatizované).<br>
- Testy sú vykonané vo všetkých definovaných prostrediach.<br>
- Založené chyby sú vyriešené a overené.<br>
- Funkcionalita neporušila žiadnu inú časť systému (regresné testy).<br>
- V prípade potreby je pripravený testovací report.<br><br>

### Biznis analytik/Produktový vlastník<br>
- Funkcionalita napĺňa potreby zákazníka (alebo interného zadávateľa).<br>
- Bola validovaná so stakeholdermi.<br>
- Sú doplnené akceptačné kritériá pre testerov.<br>
- V prípade potreby je spracovaný release note pre zákazníka.<br><br>

### Dizajnér/UX<br>
- UX dizajn je schválený pred implementáciou.<br>
- Funkcionalita zodpovedá návrhu.<br>
- Sú aktualizované figma/mockupy, ak nastali zmeny počas vývoja.<br>
- Bola vykonaná validácia použiteľnosti (napr. s testerom alebo používateľom).<br><br>

### DevOps/Release inžinier<br>
- Funkcionalita je súčasťou buildu.<br>
- Prebehlo úspešné nasadenie na produkciu/test.<br>
- Rollback plán je pripravený.<br>
- Monitorovanie je nastavené, metriky sú dostupné.<br>
- Je pripravený deployment report alebo changelog.<br><br>

## Príklady DoD podľa typu úlohy<br><br>

| Typ úlohy         | Minimálne DoD                                               |
|-------------------|-------------------------------------------------------------|
| Bugfix            | Zreprodukovaný, opravený, overený v test aj prod            |
| Nová funkcia      | Prešla testami, dokumentovaná, nasadená, bez regresie       |
| Refaktoring       | Nemá dopad na správanie, testy zelené, prešlo review        |
| Testovacia úloha  | Skripty sú v repozitári, sú zrozumiteľne pomenované, bežia  |
| Analýza           | Je spracovaný dokument (napr. špecifikácia, návrh), schválený|
| Dokumentácia      | Aktuálna, odovzdaná, validovaná technickým aj biznis pohľadom|
<br><br>

## Revízia a zlepšovanie<br>
- DoD je živý dokument a má byť pravidelne revidovaný.<br>
- Zmeny sa prejednávajú na retrospektíve alebo grooming meetingu.<br>
- Každý člen tímu môže navrhnúť doplnenie alebo úpravu.<br>
