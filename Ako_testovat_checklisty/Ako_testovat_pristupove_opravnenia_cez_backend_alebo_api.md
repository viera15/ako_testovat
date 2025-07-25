# Ako testovať prístupové oprávnenia cez backend alebo API<br>
(áno, aj 401 ≠ 403)<br>

Predstavte si interný systém na správu podujatí  – organizátori môžu pridávať eventy, upravovať detaily alebo pozývať účastníkov. Dobrovoľníci majú prístup len na čítanie. A bežní používatelia môžu vidieť len verejné podujatia. Všetko beží cez REST API.<br><br>

## Ako otestovať, že oprávnenia fungujú správne?<br><br>

Čo všetko treba otestovať:<br><br>

**Autorizácia vs. autentifikácia**<br>
- 401 Unauthorized: nedodaný alebo neplatný token → používateľ nie je prihlásený<br>
- 403 Forbidden: token je platný, ale používateľ nemá práva na danú akciu<br><br>

**Rôzne úrovne oprávnení**<br>
- prihlásený organizátor môže POST /events, PATCH /events/:id<br>
- dobrovoľník môže len GET /events<br>
- anonymný používateľ môže len GET /events?public=true<br><br>

**Neplatné tokeny alebo chýbajúce hlavičky**<br>
- token s preklepom alebo expirovaný → očakávaj 401<br>
- žiadny token → 401<br>
- token iného používateľa → 403, ak má práva inde<br><br>

**Zmena rolí počas relácie**<br>
- zmena práv by sa mala prejaviť okamžite alebo po relogine – otestuj oba prípady<br><br>

**Cross-role útoky**<br>
- napr. dobrovoľník skúsi zmeniť detail eventu → 403<br>
- bežný používateľ sa pokúsi získať zoznam všetkých e-mailov → 403<br><br>

**Prístup k neexistujúcim alebo cudzím záznamom**<br>
- GET /events/99999 (neexistujúce ID) → 404<br>
- GET /events/5 (ak patrí inej organizácii) → 403 alebo 404 (podľa politiky)<br>
- Či sú tokeny viazané na IP alebo User-Agent<br>
- niektoré systémy vyžadujú tokeny len z rovnakého zariadenia – over<br><br>

**Ošetrenie zneužitia**<br>
- príliš veľa 401/403 za krátky čas → test rate limiting alebo blokovanie<br><br>

**Záznam v logoch alebo auditných stopách**<br>
- pokusy o neoprávnený prístup by mali byť zaznamenané<br><br>

**Automatizované testy**<br>
- odporúča sa vytvoriť sadu testov pre rôzne role + pozitívne aj negatívne scenáre<br><br>

**Bonus:** Testuj aj cez rôzne frontend klienty – web, mobil, CLI – každý môže posielať hlavičky trochu inak.
Dobré testovanie oprávnení je o hraniciach – kto má čo vidieť a robiť. A hlavne, čo nemá.<br>



