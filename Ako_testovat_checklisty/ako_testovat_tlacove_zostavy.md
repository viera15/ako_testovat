Ako testovať tlačové zostavy – obsah, formát a cesty k vzorom

Zobrazí sa, ale nie je to správne. Alebo sa nezobrazí vôbec.
Aj takto môže vyzerať tlačová zostava v aplikácii, ak nefunguje dobre šablóna (template), cesta k nej alebo samotné generovanie.

Príklad z praxe:
Tester si chcel overiť tlačovú zostavu, ktorá sa generuje z používateľských údajov. V aplikácii bol odkaz na štandardné vzory, no konfigurácia ukazovala na iný adresár. Časť zostavy sa zobrazila správne, zvyšok úplne chýbal.
Pomohol nástroj Procmon (Sysinternals Suite), ktorý odhalil, že aplikácia sa pozerá ešte na tretí – úplne iný – adresár. Teda nie jeden, ale tri rôzne zdroje vzorov a každý hral svoju rolu.



Čo všetko testovať?

1. Obsah zostavy

správne údaje, zoradenie, výpočty, filtrovanie

správny počet riadkov, súčtov, hlavičky/päty

dynamické údaje: dátum generovania, názov používateľa

2. Formát a vizuál

zarovnanie, zalomenie, veľkosť písma, medzery

logo, farby, rozloženie na stránke

správna orientácia (na výšku/šírku), číslovanie strán

3. Export

generovanie bez chyby do PDF, XLS, DOC

súbor nie je poškodený, má rozumnú veľkosť

špeciálne znaky, diakritika, fonty

4. Tlač

korektné zobrazenie na papieri

okraje a rozloženie sú v súlade so šablónou

kontrola, či sa všetky stránky vytlačia

5. Výkon

čas generovania pri rôznych množstvách údajov

nesmie sa spomaliť pri veľkých zostavách

6. Prístupnosť

PDF má textovú vrstvu (nie len obrázok), čitateľné čítačkou

tabuľky a štruktúra sú zrozumiteľné

7. Vzory zostáv (templates)

odkiaľ sa šablóna načítava? Je to zdokumentované?

zhoda medzi tým, čo tvrdí aplikácia, čo je v konfigurácii a kam sa pozerá runtime (pomôže Procmon)

funguje fallback? Čo sa stane pri chýbajúcej šablóne?

pozor na duplicity, nesprávne verzie, cache a sieťové zdieľania

po výmene vzoru: treba reštart, alebo sa načíta hneď?

🧠 Bonus: v logoch by mala byť informácia, z akej cesty bol vzor použitý. Ak tam nie je, ťažko sa debuguje.



#AkoTestovať #SoftwareTesting #Testovanie #Tester #TesterskyZivot #TestovanieZostav #QA #ManualneTestovanie #TestovanieAplikácií #Procmon #Sysinternals #PDF #PrintTesting #TemplateDebugging



