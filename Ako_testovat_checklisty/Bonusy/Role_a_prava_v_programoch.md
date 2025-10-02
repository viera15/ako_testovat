# Role a práva v programoch<br><br>

Správne nastavené roly a prístupové práva sú základom bezpečnosti a funkčnosti každého systému. Rozhodujú o tom, kto čo môže vidieť, upravovať alebo spúšťať. Nižšie je prehľad najčastejších typov rolí, práv a ich rozdielov.<br><br>

## Typy rolí<br><br>

### Administrátor (Admin)<br>
- plný prístup k systému,<br> 
- správa používateľov, rolí, nastavení a dát,<br>  
- zodpovedá za konfiguráciu a bezpečnosť.<br><br>  

### Manažér / Vedúci<br>
- prístup k dátam tímu,<br>  
- schvaľovanie procesov, reporty, monitoring výkonu,<br>  
- má menej práv ako admin, viac ako bežný používateľ.<br><br>  

### Operátor<br>
- interný pracovník (napr. bankový úradník, pracovník helpdesku),<br>  
- spracúva dáta a žiadosti v mene klientov alebo organizácie,<br>  
- má prístup k viacerým účtom či záznamom,<br>  
- jeho akcie podliehajú prísnemu logovaniu a kontrole.<br><br>  

### Bežný používateľ (User)<br>
- koncový užívateľ systému (napr. zákazník banky),<br>  
- má prístup len k vlastným údajom,<br>  
- môže vykonávať len akcie týkajúce sa jeho účtu (napr. zadanie platby, zmena hesla).<br><br>  

### Read-only / Auditor<br>
- prístup len na čítanie,<br>  
- vhodné pre kontrolu a audit, bez možnosti meniť dáta.<br><br>  

### Externý používateľ (Partner, Klient)<br>
- obmedzený prístup len k tomu, čo potrebujú (napr. partner nahráva faktúry, zákazník vidí stav objednávky).<br>  

## Typy práv<br><br>

- **CRUD práva** – Create (vytvoriť), Read (čítať), Update (meniť), Delete (mazať).<br>  
- **Konfiguračné práva** – nastavenia systému, workflow, šablóny.<br>  
- **Prístupové práva podľa oblasti** – modulové (účtovníctvo, sklady, HR), dátové (vlastné dáta vs. všetky dáta), akčné (spúšťanie procesov).<br>  
- **Bezpečnostné práva** – správa hesiel, tokenov, certifikátov, dvojfaktorová autentifikácia.<br><br>  

## Rozdiel Operátor vs. Bežný používateľ<br><br>

**Operátor:**<br>
- profesionál, ktorý pracuje so systémom v mene iných,<br>  
- má prístup aj k cudzím dátam,<br>  
- vykonáva operácie ako otvorenie účtu, zadanie transakcie, zmena údajov klienta.<br><br>  

**Bežný používateľ:**<br>
- koncový klient alebo zamestnanec,<br>  
- pracuje výlučne so svojimi dátami,<br>  
- jeho možnosti sú obmedzené na vlastný účet (napr. zadanie platby v internetbankingu).<br><br>  

**Kľúčový rozdiel:** Operátor má právomoci konať nad údajmi iných ľudí, bežný používateľ len nad svojimi.<br>
