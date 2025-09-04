# Ako testovať systém na detekciu podvodov (fraud detection)<br><br>

Predstav si banku, ktorá zaviedla nový systém na detekciu podozrivých transakcií.
Zákazník napríklad nikdy neposielal peniaze do zahraničia a zrazu zadá prevod vysokej sumy na účet v inej krajine. Systém má takúto anomáliu zachytiť a transakciu označiť alebo dočasne zablokovať.<br><br>

Ako tester však musíš overiť, či systém funguje správne – či dokáže rozlíšiť bežné správanie od skutočne podozrivého a či zbytočne neblokuje klientov. Samozrejme, testovanie sa nerobí na živej databáze klientov, ale v testovacom prostredí, kde je možné simulovať transakcie a nastaviť systém tak, aby tieto udalosti bezpečne hlásil.<br><br>

## Ako otestovať systém na detekciu podvodov<br><br>

1. **Testovanie bežného správania**<br>
- simulovať transakcie v rámci obvyklých limitov a vzorcov správania klienta,<br>
- overiť, že systém neoznačí takéto transakcie ako podozrivé (minimálny počet falošne pozitívnych).<br><br>

2. **Testovanie podozrivých vzorcov**<br>
- náhle zvýšenie sumy transakcie,<br>
- nezvyčajné destinácie (napr. exotické krajiny),<br>
- neobvyklý čas prevodu (napr. v noci),<br>
- veľký počet opakovaných pokusov o transakciu.<br><br>

3. **Hraničné prípady**<br>
- transakcie tesne pod alebo nad limitmi (napr. 9 999 € vs. 10 001 €),<br>
- kombinácie viacerých menších transakcií v krátkom čase („smurfing“).<br><br>

4. **Scenáre s viacerými účtami**<br>
- prevody medzi vlastnými účtami klienta,<br>
- prevody medzi rôznymi klientmi v rámci tej istej banky.<br><br>

5. **Reakcia systému**<br>
- čo sa stane po označení transakcie (blokácia, požiadavka na dodatočné overenie, notifikácia?),<br>
- logovanie a audit trail – či sa udalosť správne zaznamená,<br>
- eskalácia na bezpečnostný tím.<br><br>

6. **Výkonnostné a objemové testy**<br>
- ako rýchlo systém dokáže vyhodnotiť tisíce transakcií za sekundu,<br>
- či pri vysokom zaťažení nedochádza k oneskoreniam alebo nesprávnym klasifikáciám.<br><br>

7. **Bezpečnostné a integračné testy**<br>
- či sa s dátami manipuluje bezpečne (šifrovanie, prístupové práva),<br>
- integrácia s inými bankovými systémami (core banking, mobilná aplikácia).<br>

Testovanie fraud detection systému nie je len o hľadaní chýb, ale aj o hľadaní rovnováhy: aby banka ochránila klientov pred skutočnými podvodmi, ale zároveň im neznepríjemňovala život falošnými alarmami.
