# Ako testovať e-mailovú šablónu s dynamickými údajmi z databázy<br><br>

Príklad šablóny:<br>

Predmet: Objednávka č. {{order\_id}} bola úspešne prijatá<br>

Dobrý deň, {{customer\_name}},<br>
ďakujeme za Vašu objednávku. Tu sú jej podrobnosti:<br><br>

• Produkt: {{product\_name}}<br>
• Množstvo: {{quantity}}<br>
• Cena spolu: {{total\_price}} €<br><br>

Vaša objednávka bude odoslaná na adresu:<br>
{{delivery\_address}}<br><br>

S pozdravom<br>
Tím {{company\_name}}<br>



## Čo všetko otestovať:<br>

1. **Nahradenie placeholderov**<br>

- Správne načítanie všetkých premenných (napr. {{order\_id}}, {{customer\_name}})<br>

- Ošetrenie prázdnych hodnôt (napr. fallback ako "Zákazník" pri chýbajúcom mene)<br><br>

2. **Lokalizácia a jazyková verzia**<br>

- Správny jazyk podľa preferencie používateľa<br>
    - Over, či systém používa nastavenie jazyka zo správneho zdroja (napr. jazyk v profile používateľa, cookies, nastavenie účtu)<br>
    - Porovnaj, či jazyk e-mailu zodpovedá tomuto nastaveniu (napr. používateľ má zvolenú nemčinu → predmet aj obsah e-mailu sú v nemčine)<br>

- Preklady statických aj dynamických textov<br><br>

3. **Štruktúra a formátovanie e-mailu**<br>

- Korektné HTML zobrazenie v rôznych klientoch (Gmail, Outlook, mobil) prípadne prehliadačoch (Firefox, Safari, Edge, Chrome)<br>

- Odstupňovanie, odrážky, zarovnanie<br>

- Korektné zobrazenie aj v plain-text verzii (čisto textová verzia bez formátovania, ktorú niektoré e-mailové klienty zobrazujú namiesto HTML)<br><br>

4. **Obsahová kontrola dát**<br>

- Zhoduje sa objednávka v e-maile s údajmi v databáze?<br>

- Cena je správne vypočítaná a zaokrúhlená?<br>

- Adresa nie je useknutá?<br><br>

5. **Bezpečnosť**<br>

- Žiadne HTML injekcie cez vstupy. HTML injection (HTML injekcia) je situácia, keď útočník alebo chyba v systéme umožní vložiť nebezpečný HTML kód do obsahu e-mailu. Napríklad ak používateľ zadá do mena reťazec ako alert('hack');, a tento sa bez úpravy dostane do e-mailu, môže spôsobiť problémy v prehliadači príjemcu. Takéto vstupy treba filtrovať alebo escapovať, aby sa zobrazovali len ako text.<br>

- E-mail neobsahuje citlivé dáta (napr. číslo karty)<br><br>

6. **Spúšťanie a logika odosielania**<br>

- Kedy sa e-mail spustí (po objednávke, po úhrade...)?<br>

- Neodosiela sa viackrát?<br>
    - Skontroluj logy systému alebo e-mailovej služby (napr. Sendgrid, Mailgun) – koľkokrát bola odoslaná notifikácia pre tú istú objednávku<br>
    - Pozri záznamy v databáze (napr. tabuľka email\_logs, notifications) – je tam len 1 záznam?<br>
    - Otestuj v QA prostredí: vytvor objednávku a sleduj, či sa e-mail neodošle opakovane, ak klikneš znova<br>
    - Over, či systém používa príznak ako email\_sent = true, a či sa tento stav správne aktualizuje<br>

- Čo sa stane pri chybe v šablóne (log, fallback, chyba v systéme)?<br><br>

7. **Testy okrajových prípadov**<br>

- Chýbajúci produkt (napr. vymazaný z databázy)<br>
- Over, čo sa stane, keď sa po vytvorení objednávky produkt z databázy odstráni. E-mailová šablóna by mala buď:<br>
    - čerpať dáta z momentu objednania (napr. snapshot v inej tabuľke),<br>
    - alebo bezpečne ošetriť chýbajúce hodnoty (napr. „Produkt bol medzičasom odstránený“).<br>

- Test: vytvor testovaciu objednávku → následne produkt z databázy zmaž → spusti generovanie e-mailu a sleduj, čo sa zobrazí v šablóne.<br>

- Príliš dlhé meno alebo adresa<br>

- Zahraničné znaky a diakritika<br><br>

8. **Odhlásenie/footer**<br>

- Obsahuje e-mail možnosť odhlásiť sa z notifikácií (ak má)?<br>

- Správne odkazy, GDPR texty<br><br>


Vysvetlenie pojmu: **Fallback**<br>

Záložná hodnota alebo správanie, ktoré systém použije, ak niečo chýba. Napr. ak nie je dostupný preklad, zobrazí sa text v angličtine ako fallback. Pri e-mailových šablónach sa ako fallback často používa napr. "Zákazník" namiesto {{customer\_name}}, ak meno chýba.<br><br>

#tester #akotestovat #manualnytester #automatizovanytester #ITtester #QA #ITkariera



