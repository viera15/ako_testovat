# Ako testovať zobrazovanie cien v rôznych menách

**Príklad**<br>
Predstav si, že zákazník si prezerá ponuku zájazdov na webe cestovnej kancelárie.  
Na slovenskej verzii vidí cenu 1 200 €, ale po prepnutí do anglickej verzie sa suma zobrazí ako 1 200 $ — bez prepočtu podľa aktuálneho kurzu.  
Takáto chyba môže spôsobiť nielen reklamácie, ale aj právne problémy pri potvrdení objednávky.  
Zobrazovanie cien v rôznych menách je preto dôležité testovať dôsledne — nielen vizuálne, ale aj funkčne a dátovo.  

<br><br>

## Ako otestovať

**1. Základné zobrazenie a formát meny**  
- Skontroluj, či sa po zmene jazyka automaticky mení aj mena (napr. `€ → $`, `£`).  
- Over formátovanie: pozícia symbolu meny, medzery, desatinná čiarka alebo bodka.  
- Testuj zobrazovanie v rôznych prehliadačoch a zariadeniach — niekedy sa znak meny renderuje odlišne.  

<br>

**2. Kurz a konverzia cien**  
- Over, že kurz sa načítava z aktuálneho zdroja (napr. `ECB`, `NBS` alebo partner).  
- Vypočítaj si kontrolne cenu podľa daného kurzu — odchýlka by nemala presiahnuť 0,5 %.  
- Sleduj, či sa kurz aktualizuje denne, pri zmene meny alebo len pri nasadení novej verzie.  

<br>

**3. Zachovanie meny v procese objednávky**  
- Po výbere meny na webe otestuj, či sa rovnaká mena prenáša cez všetky kroky:  
  košík → platobná brána → potvrdenie objednávky → faktúra.  
- Over, že po prihlásení klienta z inej krajiny systém automaticky rozpozná predvolenú menu (napr. podľa `IP` alebo nastavení účtu).  

<br>

**4. Zaokrúhľovanie a poplatky**  
- Otestuj zaokrúhľovanie pri prepočte — suma `1 234,56 €` sa nemá stať `1 234 $` bez prepočtu.  
- Sleduj drobné rozdiely medzi zobrazením a finálnym zaúčtovaním — najmä pri zľavách a poplatkoch.  
- Over, že všetky zložky (základná cena, DPH, servisný poplatok, zľava) sú prepočítané rovnakým kurzom.  

<br>

**5. Externé integrácie a API**  
- Skontroluj `API` odpovede: mena musí byť uvedená v poli `currency` a suma v `amount`.  
- Testuj reakciu systému pri nedostupnosti kurzu alebo neznámej mene (*fallback mena*).  
- Over konzistenciu dát medzi frontendom a backendom — čísla v UI musia zodpovedať hodnotám v databáze.  

<br>

**6. Viacjazyčné a viacmenové kombinácie**  
- Simuluj preklik z jednej mutácie do druhej (napr. `en → de`) a sleduj, či sa mení len jazyk, alebo aj mena.  
- Otestuj špecifické menové formáty: japonský jen bez desatinných miest, britská libra s oddeľovačom `,`.  
- Over, že systém umožňuje filtrovanie a porovnávanie cien naprieč menami (napr. vyhľadávanie podľa rozpočtu).  

<br>

**7. Testovanie hraníc a výnimiek**  
- Neplatné alebo zakázané meny — systém musí zobraziť zrozumiteľnú chybu.  
- Nulová alebo extrémne vysoká cena — over, ako sa správa UI.  
- Zmena meny po zaplatení — cena na potvrdení a faktúre musí byť v pôvodnej mene platby.  
<br>