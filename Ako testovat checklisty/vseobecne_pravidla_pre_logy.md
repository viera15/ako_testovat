# Všeobecné pravidlá pre logy<br><br>

1. **Štruktúrovanosť**<br>
- Logy by mali byť strojovo čitateľné (napr. JSON, XML, CSV), nie len voľný text.<br>
- Vhodné na parsing, filtrovanie, vizualizáciu.<br><br>

2. **Konzistentný formát**<br>
- Rovnaké poradie a názvy polí (napr. timestamp, level, message, user\_id, session\_id, error\_code).<br>
- Časová pečiatka v štandarde ako ISO 8601 (napr. 2025-07-21T10:23:45Z).<br><br>

3. **Jasné úrovne logovania**<br>
- DEBUG, INFO, WARNING, ERROR, CRITICAL<br>
- Vyberaj primeranú úroveň – nech nie sú všetky chyby len INFO alebo všetko ERROR.<br><br>

4. **Bez citlivých údajov**<br>
- Neloguj heslá, celé rodné čísla, čísla kariet, adresy a pod.<br>
- Maskuj alebo anonymizuj citlivé dáta (****, hash()).<br><br>

5. **Obsahujúce kontext**<br>
- Kto akciu vykonal (user/session/token)<br>
- Kde sa stala (modul, služba)<br>
- Čo sa stalo (popis + vstupné hodnoty, ak sú bezpečné)<br><br>

6. **Jednoznačnosť a čitateľnosť**<br>
- Každý záznam má byť pochopiteľný bez potreby čítať celý stacktrace.<br>
- Vyhýbaj sa vnútorne nezmyselným hláškam typu „unexpected error“ bez detailov.<br><br><br>



# Pravidlá pre auditné záznamy<br><br>

1. **Nezmazateľnosť a nemennosť**<br>
- Auditný záznam by sa nemaže, ale dopĺňa (princíp nemenného záznamu).<br>
- Ak sa opravuje záznam, pôvodný stav sa zachováva.<br><br>

2. **Zaznamenáva sa:**<br>
- Kto – používateľ, rola, systém<br>
- Čo – zmena (napr. stav: "schválené" → "zamietnuté")<br>
- Kedy – presná časová pečiatka<br>
- Odkiaľ – IP adresa, prehliadač, API klient<br><br>

3. **Čitateľnosť a auditovateľnosť**<br>
- Auditný záznam má byť ľahko dohľadateľný v prípade kontroly (GDPR, bezpečnostný incident).<br>
- Často je viazaný na konkrétny objekt alebo entitu (napr. objednávka č. 1234).<br><br>

4. **Neslúži na ladenie**<br>
- Audit je právna/zodpovednostná stopa, nie debug nástroj.<br><br>


---
<br>

**Stacktrace**<br>
(alebo „výpis zásobníka volaní“) je technický výpis, ktorý ukazuje reťazec volaní funkcií, ktoré viedli k chybe alebo výnimke v programe.<br><br>

**Čo to presne znamená?**<br>
Keď program zlyhá (napr. spadne na chybe), operačný systém alebo runtime (napr. Python, Java, .NET) zobrazí stacktrace – zoznam funkcií, ktoré sa volali predtým, než chyba nastala.<br><br>

**Prečo je stacktrace užitočný?**<br>
Pomáha vývojárovi alebo testerovi zistiť:<br>
- kde presne v kóde sa chyba stala (riadok, súbor, trieda),<br>
- čo sa volalo predtým – teda ako sa program dostal do chybového stavu,<br>
- aký typ chyby nastal (napr. NullPointerException, IndexError, TypeError...).<br><br>

**Príklad – jednoduchý stacktrace v Pythone:**<br><br>

```
Traceback (most recent call last):

 File "main.py", line 10, in 

 divide(4, 0)

 File "main.py", line 6, in divide

 return a / b

ZeroDivisionError: division by zero

```
<br>


**Vysvetlenie:**<br>
- Funkcia divide bola volaná na riadku 10 súboru main.py<br>
- V tele tejto funkcie (riadok 6) sa vykonalo a / b, kde b bolo 0<br>
- Program zlyhal na chybe ZeroDivisionError: division by zero<br><br>

**Stacktrace môžeš nájsť:**<br>
- v konzolovom výstupe (ak testuješ lokálne),<br>
- v logoch (produkčných alebo testovacích),<br>
- vo výstupoch testovacích nástrojov (napr. Selenium, pytest, JUnit),<br>
- v chybných reportoch alebo bug trackeri (napr. Jira).<br>
