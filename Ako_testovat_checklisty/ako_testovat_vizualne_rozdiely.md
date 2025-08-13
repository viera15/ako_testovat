# Ako testovať vizuálne rozdiely medzi verziami (regresné UI testy)<br><br>

Príklad:<br>
Predstav si e-shop, ktorý spustil novú verziu katalógu produktov. Dizajnér zmenil farby tlačidiel, upravil font nadpisov a pridal viac miesta medzi jednotlivé položky filtrov. Tester má preveriť, či sa tieto zmeny prejavili presne podľa návrhu a či sa nezmenilo nič, čo sa meniť nemalo – napríklad rozbité zarovnanie textu, posunuté obrázky alebo neviditeľné tlačidlá.<br><br>

## Ako otestovať:<br><br>

1. **Príprava baseline (referenčných screenshotov)**<br>
- Pred spustením testov si ulož snímky obrazovky aktuálnej (starej) verzie.<br>
- Použi rovnaké podmienky pre snímkovanie: rozlíšenie obrazovky, prehliadač, zoom, téma (dark/light).<br>
- Ulož ich v štruktúre podľa stránok, aby sa dali ľahko spárovať s novými screenshotmi.<br><br>

2. **Porovnanie screenshotov**<br>
- Urob snímky novej verzie a porovnaj ich pixel po pixeli s baseline.<br>
- Nástroje ako Pixelmatch, Resemble.js alebo Wraith dokážu vizuálne vyznačiť odlišné miesta.<br>
- Vyhodnoť, či ide o plánovanú zmenu alebo chybu (napr. posun textu kvôli inému fontu).<br><br>

3. **Kontrola layoutu a responzivity**<br>
- Over umiestnenie, veľkosť a zarovnanie prvkov (menu, tlačidlá, obrázky, formuláre).<br>
- Testuj v rôznych rozlíšeniach a zariadeniach – zmena CSS môže spôsobiť chyby len na mobile alebo tablete.<br><br>

4. **Farebné a typografické zmeny**<br>
- Porovnaj farby s návrhom (hex/RGB hodnoty).<br>
- Skontroluj font (typ, veľkosť, hrúbku) podľa dizajn manuálu.<br>
- Pozor na rozdiely v renderovaní fontov medzi prehliadačmi.<br><br>

5. **Nástroje na vizuálne regresné testovanie**<br>
- Applitools Eyes, Percy, Chromatic, BackstopJS umožňujú automatizované porovnania a integráciu do CI/CD pipeline.<br>
- Nastav ignorovanie dynamických častí (napr. dátum, reklamy), aby testy nepadali na nepodstatných zmenách.<br><br>

6. **Dynamický obsah a animácie**<br>
- Pri porovnávaní screenshotov animácie a časovo závislé prvky môžu spôsobiť falošné rozdiely.<br>
- Použi „freeze“ stav alebo maskovanie týchto oblastí.<br><br>

7. **Výstup a report**<br>
- Každú odchýlku zdokumentuj – pridaj screenshot „pred“ a „po“.<br>
- V reporte jasne označ, či ide o očakávanú zmenu alebo chybu.<br>
- Uveď aj podmienky testu (verzia prehliadača, rozlíšenie, dátum porovnania).<br><br>

Vizuálne regresné testy sú silným nástrojom, ktorý pomáha odhaliť zmeny, ktoré by inak unikli. Najlepšie fungujú, keď sú spustené automaticky po každom nasadení a majú dobre udržiavanú baseline.<br>
