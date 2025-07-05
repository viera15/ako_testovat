# Ako testovať webový formulár: povinné aj voliteľné polia 
<br>

Predstavme si jednoduchý registračný formulár:<br>

Meno* (povinné)<br>

E-mail* (povinné)<br>

Telefón (voliteľné)<br>

Dátum narodenia* (povinné)<br>

Súhlas s newsletterom (voliteľné checkbox)<br><br>



## Čo všetko otestovať?<br>

1. **Kombinácie vstupov**<br>

- Vyplnené len povinné polia<br>

- Vyplnené všetky polia vrátane voliteľných<br>

- Žiadne vyplnené polia → očakávané chyby pre všetky povinné<br>

- Náhodné kombinácie (napr. vynechať Dátum narodenia, ale zadať Telefón)<br><br>

2. **Validácia obsahu**<br>

- E-mail: chýbajúce „@“, nesprávny formát (napr. user@domain)<br>

- Telefón: nesprávne znaky (miesto "+" dať "-" na začiatok), príliš dlhý/krátky formát<br>

- Dátum narodenia: budúci dátum, formát DD.MM.RRRR vs. RRRR-MM-DD<br><br>

3. **Správy o chybách**<br>

- Jasné a konkrétne hlásenia (napr. „Zadajte platný e-mail“)<br>

- Správa pri zobrazení viacerých polí naraz<br>

- Vyplnenie/nevyplnenie údajov a kliknutie na Odoslanie. Chyba sa zobrazí po odoslaní.<br>

- Po každom vyplnení/nevyplnení položky sa zobrazí chybová správa („blur“ event)<br>

- ARIA alert pre čítačky obrazovky (aria-live="assertive")<br><br>

4. **Hraničné hodnoty & dĺžka textu**<br>

- Minimálna a maximálna dĺžka mena<br>

- Skryté biele znaky, Unicode (emoji), diakritika<br>

- SQL-injekcie, XSS – znaky <>, ;, '<br><br>

5. **Prístupnosť (a11y)**<br>

- Label pre každý input ()<br>

- Kontrast textu vs. pozadia (WCAG 2.1 AA)<br>

- Klávesová navigácia (Tab/Shift+Tab, Enter na odoslanie)<br>

- Focus indikátor (outline) viditeľný vo fokusovanom poli<br>

- Popisné aria-describedby pre chyby a doplňujúce inštrukcie<br><br>

6. **UX a UI**<br>

- Vypnuté tlačidlo „Odoslať“, kým nie sú správne údaje v povinný poliach<br>

- Resetovanie formulára – či sa vymažú všetky polia aj chybové hlášky<br>

- Stav „loading“ po odoslaní – spinner, zablokovanie ďalších kliknutí<br><br>

7. **Rôzne zariadenia a prehliadače**<br>

- Mobil (iOS, Android) vs. desktop<br>

- Staršie verzie prehliadačov (IE11, Edge Legacy)<br>

- Rôzne veľkosti obrazovky (responsiveness)<br><br>



#QA #Testovanie #WebAccessibility #a11y #SoftwareTesting #QualityAssurance



