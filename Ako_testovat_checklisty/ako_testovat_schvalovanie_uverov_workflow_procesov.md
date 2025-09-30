# Ako testovať schvaľovanie úverov a workflow procesov<br><br>

Príklad<br>
Predstav si klienta, ktorý požiada o spotrebný úver. Systém má presne nastavené workflow – od zadania žiadosti, cez kontrolu bonity, scoring, schválenie, až po podpis zmluvy a uvoľnenie peňazí. Ak sa niekde proces zasekne (napr. scoring sa nespustí, alebo dokumenty čakajú v schvaľovaní u nesprávneho pracovníka), klient čaká zbytočne a banka prichádza o dôveru aj príjem. Testovanie workflow procesov je preto kľúčové, aby každý krok fungoval plynulo, správne a v správnom poradí.<br><br>

## Ako otestovať<br><br>

1. **Validácia vstupov**<br>
- Otestuj, či sú povinné polia správne označené a systém kontroluje úplnosť údajov.<br>
- Over formát údajov (rodné číslo, číslo OP, príjem, IBAN).<br><br>

2. **Workflow schvaľovania**<br>
- Skontroluj, či sa žiadosť dostane do správneho kroku podľa nastavených pravidiel.<br>  
- Over, že systém prideľuje úlohy správnemu oddeleniu (scoring, risk, právne, back-office).<br>  
- Testuj paralelné a sekvenčné kroky – napr. scoring beží automaticky, ale právne schválenie až po ňom.<br><br>

3. **Scenáre odmietnutia a výnimiek**<br>
- **Nízka bonita** → zamietnutie s vysvetlením.<br>  
- **Chýbajúci dokument** → workflow sa zastaví a upozorní používateľa.<br>  
- **Neplatný údaj** → chyba, ktorá nedovolí pokračovať.<br><br>

4. **Automatizované rozhodovanie**<br>
- Testuj správne aplikovanie scoring modelov.<br>  
- Over, že systém priradí úver do správnej kategórie rizika.<br>  
- Simuluj rôzne príjmy, výdavky a záväzky.<br><br>

5. **Notifikácie a informovanie klienta**<br>
- Over SMS/email správy pri zmene stavu žiadosti.<br>  
- Testuj eskalácie – ak je krok príliš dlho neuzavretý, príde upozornenie.<br><br>

6. **Integrácie a závislosti**<br>
- Over prepojenie s registrom dlžníkov, databázou príjmov alebo externým scoringovým systémom.<br>  
- Testuj, čo sa stane, ak integrácia zlyhá (timeout, nedostupnosť).<br><br>

7. **Audit a logovanie**<br>
- Skontroluj, či systém zaznamenáva, kto a kedy rozhodol o schválení/zamietnutí.<br>  
- Over kompletnosť histórie workflow pre účely compliance.<br>
