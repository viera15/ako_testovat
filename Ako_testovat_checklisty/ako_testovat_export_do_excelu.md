# Ako testovať export do Excelu
<br>
V dnešnej dobe sú Excelové exporty základným spôsobom, ako zdieľať a analyzovať dáta. Ak ale pri exporte niečo nefunguje, môže to viesť k chybným reportom, zle interpretovaným výsledkom a strate času. Preto by mal každý QA inžinier či analytik mať pripravený jednoduchý, no dôkladný check-list.<br>
<br><br>

1. **Správnosť údajov**<br>

- Porovnajte vybrané riadky (napr. 5–10 z rôznych častí súboru) s originálnym zdrojom (databáza/API).<br>

- Skontrolujte okraje (min/max hodnoty), priemery či sumy agregovaných stĺpcov.<br><br>

2. **Zoradenie dát**<br>

- Zoradenie dát<br>

- Otestujte predvolený export aj rôzne možnosti zoradenia (vzostupne, zostupne).<br>

- Skontrolujte, že po zmene filtrovania alebo sort-poradia sa zmení aj poradie riadkov v Exceli.<br><br>

3. **Typ stĺpcov**<br>

- Overte, že číselné polia sú naformátované ako Number (nie Text) – napr. sumy, percentá, desatinné čísla.<br>

- Dátumy by mali byť rozpoznané ako Date (a nie textový reťazec).<br>

- E-maily, telefónne čísla či kódy často musia zostať Text, aby sa nezmenili úvodné nuly.<br><br>
  

4. **Špeciálne znaky**<br>

- Skontrolujte výskyt &, %, $, €, @, #, /, \ a pod.<br>

- Uistite sa, že Excel správne zobrazuje tieto znaky a neprepisuje ich do unikódu (napr. “\u0026”).<br><br>
  

5. **Diakritika**<br>

- Otestujte slovenské znaky (č, ď, ľ, ť, ž, š, ň).<br>

- Skontrolujte, že sa neobjavujú “krivo” (možné problémy s kódovaním – UTF-8 vs. ANSI).<br><br>
  

6. **Prázdne a null hodnoty**<br>

- Uistite sa, že prázdne polia nie sú zamieňané za “0” alebo “FALSE”.<br>

- Overte správanie na konci a začiatku dokumentu (bloku prázdnych riadkov).<br><br>
  

7. **Formátovanie buniek**<br>

- Skontrolujte, či sa nastavené formáty (farby, fonty, zarovnanie) nepoškodia pri exporte.<br>

- Ak export generuje šablónu s hlavičkou/pätou, otestujte, či ostáva nezmenená.<br><br>
  

8. **Veľkosť a výkon**<br>

- Export väčších datasetov (tisíce až desiatky tisíc riadkov) – či sa súbor načíta a nepadá.<br>

- Merajte dobu exportu a otvárania v Exceli.<br><br>
  

9. **Edge-case testy**<br>

- Dátum 29. 2. (prestupný rok), koncové znaky reťazcov (>255 znakov), diakritika v hlavičkách stĺpcov.<br>

- Rôzne jazykové lokálne nastavenia (desatinná čiarka vs. bodka).<br><br>



#Excel #QA #Testovanie #DataQuality #ExportTestovanie



