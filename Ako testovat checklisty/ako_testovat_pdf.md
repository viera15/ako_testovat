# Ako testovať PDF výstup z aplikácie<br><br>

Ukážka scenára<br>

Používateľ vyplní formulár (napr. fakturačný), klikne na „Generovať PDF“ a stiahne si PDF súbor. PDF má obsahovať údaje zo systému, logo firmy a čitateľné formátovanie.<br><br>

## Čo testovať – kontrolný zoznam v bodoch<br>

🔹 1. Generovanie PDF<br>

- Spustí sa generovanie PDF po očakávanej akcii?<br>

- Je proces generovania úspešný bez technických alebo vizuálnych chýb (napr. prázdny súbor, chýbajúce dáta, chybové hlášky)?<br>

- Má súbor správny názov (napr. faktura\_2025-06-27.pdf)?<br><br>

🔹 2. Obsah súboru<br>

- Zodpovedá obsah údajom zo systému (napr. meno, adresa, suma)?<br>

- Sú dynamické údaje správne vyplnené (nie {{meno}})?<br>

- Obsahuje všetky povinné sekcie (napr. hlavička, tabuľka položiek, podpis)?<br>

- Ak je to napr. faktúra, sú výpočty správne?<br><br>

🔹 3. Formátovanie a dizajn<br>

- Správne zoradenie a zarovnanie textov?<br>

- Fonty a štýly podľa dizajnového manuálu?<br>

- Logo, hlavička, päta sú zobrazené?<br>

- Nechýbajú žiadne časti (napr. orezaná tabuľka)?<br><br>

🔹 4. Jazyk a lokalizácia<br>

- Správna verzia jazyka podľa používateľského rozhrania?<br>

- Dátumy a meny vo formáte podľa lokality (napr. 27. 6. 2025, 1 200,00 €)?<br><br>

🔹 5. Technické vlastnosti<br>

- Súbor sa dá otvoriť v štandardných PDF prehliadačoch (Adobe Reader, prehliadač v Chrome)?<br>

- Neobsahuje chyby ako napr. nečitateľné znaky, chybné znaky Unicode, poškodené obrázky, chýbajúce fonty alebo výstražné hlásenia pri otvorení súboru?<br>

- Veľkosť súboru je primeraná obsahu? (napr. bežné PDF do 1 MB, výnimočne do 5 MB pri obrázkoch alebo grafike; ak presiahne 10 MB, prever dôvod – môže ísť o neoptimalizované obrázky alebo zbytočné vrstvy)<br><br>

🔹 6. Automatizované testy (voliteľné)<br>

- Overenie obsahu cez čítanie textu z PDF (napr. knižnice ako PyPDF2, pdfplumber)<br>

- Porovnanie s referenčným PDF<br><br>

🔹 7. Prístupnosť (accessibility)<br>

- Má PDF textovú vrstvu, ktorú dokáže načítať čítačka obrazovky (napr. NVDA, JAWS)?<br>

- Obsahuje potrebné značkovanie (tagy) pre štruktúru dokumentu – nadpisy, tabuľky, alternatívne texty k obrázkom?<br>

- Je možné PDF navigovať pomocou klávesnice?<br>

- Spĺňa základné požiadavky podľa smernice EAA (European Accessibility Act)?<br>

- Overenie obsahu cez čítanie textu z PDF (napr. knižnice ako PyPDF2, pdfplumber)<br>

- Porovnanie s referenčným PDF<br><br>

#tester #akotestovat #manualnytester #automatizovanytester #ITtester #QA #ITkariera



