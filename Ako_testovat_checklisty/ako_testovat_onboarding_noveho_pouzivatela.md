# Ako testovať onboarding nového používateľa<br><br>

Predstav si, že testuješ aplikáciu na evidenciu dochádzky vo firme. Nový zákazník si práve kúpil program a po prvom prihlásení musí:<br>
- astaviť základné údaje o firme,<br>
- pridať oddelenia a manažérov,<br>
- priradiť personalistov,<br>
- vytvoriť šablóny pre dochádzku (napr. 8h pracovný čas, skrátený úväzok),<br>
- pridať zamestnancov.<br>
Niektoré funkcie (napr. export reportov alebo práca so schvaľovaním neprítomností) sa sprístupnia až po dokončení onboarding krokov.<br><br>

## Čo otestovať pri onboardingu používateľa:<br><br>

1. **Prvé prihlásenie**<br>
- Je používateľ presmerovaný na onboarding flow?<br>
- Je možné sa z onboardingu „prekliknúť“ späť do aplikácie – a ak áno, čo sa stane?<br>
- Je možné zrušiť sprievodcu a nastaviť program podľa seba?<br><br>

2. **Sprievodca (wizard)**<br>
- Funguje správne poradie krokov?<br>
- Dá sa krok preskočiť, vrátiť sa späť, opraviť údaje?<br>
- Sú povinné polia naozaj povinné a zvalidované?<br>
- Reaguje UI zrozumiteľne na chyby?<br><br>

3. **Podmienené zobrazenie funkcií**<br>
- Sú určité časti aplikácie nedostupné alebo skryté, kým nie je onboarding dokončený?<br>
- Zobrazujú sa správne hlášky (napr. „Najprv nastavte šablónu“)?<br>
- Je možné „obísť“ onboarding cez URL?<br><br>

5. **Prerušenie a pokračovanie**<br>
- Ak používateľ nedokončí onboarding, vráti sa po opätovnom prihlásení tam, kde skončil?<br>
- Nezostávajú po nedokončenom onboardingu nekonzistentné dáta?<br><br>

6. **Roly a oprávnenia**<br>
- Dostane správnu rolu (napr. admin vs. personalista)?<br>
- Má prístup len k tomu, čo mu prináleží?<br><br>

7. **Technické kontroly**<br>
- Zapisujú sa údaje do databázy podľa očakávania?<br>
- Logujú sa jednotlivé kroky (audit trail)?<br>
- Volajú sa API v správnom poradí?<br><br>

Dobrý onboarding pomáha novému používateľovi pochopiť aplikáciu a zvýši šancu, že ju bude naozaj používať.
Dobrý tester overí, že onboarding je jasný, funkčný a bezpečný.<br>
