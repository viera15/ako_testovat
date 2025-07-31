# Ako testovať zmeny v databáze po určitej akcii?<br><br>

 `INSERT, UPDATE, DELETE`… v testoch nestačí len kliknúť. Treba sa pozrieť, čo sa reálne zmenilo v databáze.<br><br>

Príklad:<br>
Tester vyplní formulár objednávky a stlačí tlačidlo Vytvoriť. Objednávka je vytvorená a zobrazí sa v zozname objednávok.<br>
Otázka je: Naozaj vznikla nová objednávka v databáze? A má správne údaje?<br><br>

Čo všetko treba otestovať:<br><br>

1. **SELECT pred akciou** (kontrola stavu pred akciou): Napr. si vyselektuj zoznam existujúcich objednávok a zisti, aké je posledné ID:<br>

```

SELECT MAX(id) FROM objednavky;

```

Uistite sa, že záznam predtým neexistoval (napr. podľa ID, e-mailu, kódu).<br><br>

2. **Spustenie akcie** (napr. POST požiadavka, klik v UI): Tester spustí testovanú akciu. To môže byť kliknutie na tlačidlo v používateľskom rozhraní alebo odoslanie požiadavky cez API. V našom príklade klikne na Vytvoriť objednávku. Tým odošle údaje na server, ktorý by mal vytvoriť nový záznam v databáze.<br><br>

3. Overenie zmeny v databáze: Keďže sme vytvárali v UI novú objednávku, teraz pomocou `SELECT` dotazu overujeme, či pribudlo nové číslo objednávky oproti bodu 1. V prvom rade nás zaujíma, či sa v databáze nachádza nový záznam s novým ID a či obsahuje správne údaje z formulára.
- bol `INSERT` - záznam pribudol – napr. pribudlo nové číslo objednávky a obsahuje údaje z formulára
- bol `UPDATE` - záznam so zadaným číslom objednávky existuje a obsahuje upravené údaje
- bol `DELETE`- objednávka sa v databáze už nenachádza, alebo má príznak “zmazaná” – preto sa nezobrazuje v UI

4. **Kontrola integrity údajov:** Pozri sa, či údaje v novom alebo upravenom zázname dávajú zmysel. Nemali by tam byť prázdne polia (napr. meno zákazníka nie je vyplnené), ani nezmyselné hodnoty (napr. záporná cena). Tiež si všimni, či sú údaje vo správnom formáte – napríklad dátum vyzerá ako dátum a nie ako náhodný reťazec. A ak objednávka odkazuje na inú tabuľku (napr. zákazníka), ten musí existovať – teda tzv. referenčná väzba musí byť platná. Over, že sa nepridali „slepé“ hodnoty (napr. `NULL`, prázdne reťazce), neporušené referencie, správne formáty.<br><br>

5. **Rollback** (pri manuálnom testovaní v testovacej databáze):
Keď testuješ vytvorenie alebo úpravu záznamu, môžeš po skončení testu databázu “upratať” – teda záznam odstrániť alebo vrátiť späť, aby test nezanechal trvalé zmeny. Napríklad testovaciu objednávku môžeš po overení zmazať, aby si mal čisté prostredie pre ďalší test.
Pri automatizovaných testoch sa na to používajú tzv. transakcie – test beží v dočasnom režime a na konci sa všetky zmeny vrátia späť pomocou funkcie rollback. Tým pádom databáza ostane nezmenená.<br><br>

6. **Audit/logy** (ak sú): Skontroluj, či sa zmena správne zaznamenala do logu alebo audit trailu (história záznamov). Audit trail je záznam o tom, kto čo v systéme urobil, kedy a ako. Pomáha zistiť, kto záznam vytvoril, upravil alebo zmazal.<br><br>

Napríklad: používateľ s ID 102 zmenil stav objednávky č. 97 z „nová“ na „zrušená“ dňa 1. augusta o 13:41. Takýto zápis by sa mal objaviť v histórii, ak je auditovanie správne nastavené.<br><br>

7. **Testuj aj neúspešné scenáre:**<br>
čo sa stane, keď zadáš nevalidné dáta?<br>
- nezmení sa databáza?<br>
- neduplikujú sa dáta?<br><br>

Tip: Aj keď testuješ cez UI, nezabudni si sem-tam „odskočiť“ do databázy – odhalíš tým množstvo chýb, ktoré by inak ostali skryté.<br>

