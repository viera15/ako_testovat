# Testerský slovník<br>

(postupne budem zverejňovať pojmy, ktoré som nazbierala)<br><br>

**Placeholder**<br>
Dočasné zástupné miesto vo výstupe (napr. {{meno}}), ktoré sa má nahradiť skutočnou hodnotou z databázy alebo systému.<br><br>

**Fallback**<br>
Záložná hodnota alebo správanie, ktoré systém použije, ak niečo chýba. Napr. ak nie je dostupný preklad, zobrazí sa text v angličtine ako fallback.<br><br>

**Rollback**<br>
Návrat databázy alebo systému do predchádzajúceho stavu, ak niečo zlyhá. Používa sa napríklad po chybe počas aktualizácie údajov.<br><br>

**Validácia**<br>
Overenie, či sú vstupné dáta správne z hľadiska formy (napr. e-mail musí obsahovať @, dátum musí byť v správnom formáte).<br><br>

**Verifikácia**<br>
Overenie, či systém robí to, čo má – teda či zodpovedá špecifikácii. (Opak validácie: validujeme vstup, verifikujeme správanie systému.)<br><br>

**CRON**<br>
Naplánovaná úloha, ktorá sa spúšťa automaticky v určitý čas alebo interval (napr. každý deň o 2:00 v noci). Používa sa napr. na nočné reporty.<br><br>

**API (Application Programming Interface)**<br>
Rozhranie, cez ktoré medzi sebou komunikujú aplikácie. Tester ho používa na overenie, či systém správne reaguje na požiadavky (napr. vytvorenie používateľa cez POST požiadavku).<br><br>

**Bug**<br>
Chyba v systéme – niečo nefunguje podľa očakávania alebo špecifikácie. Môže byť funkčná, vizuálna, bezpečnostná, výkonnostná…<br><br>

**Test case (testovací prípad)**<br>
Konkrétny scenár testovania so vstupmi, krokmi, očakávaným výsledkom a realitou. Napr. „Keď zadám neplatný e-mail, zobrazí sa chyba“.<br><br>

**Edge case**<br>
Hraničný alebo zriedkavý scenár, ktorý sa bežne nestáva, ale môže spôsobiť problém. Napr. používateľ s menom „A“ alebo 0 položiek v košíku.<br><br>

**Smoke test**<br>
Rýchla kontrola, či aplikácia vôbec beží a základné funkcie fungujú. Nejde do hĺbky – len overuje, či „nesmrdí“ (odtiaľ názov).<br><br>

**Regression test (regresný test)**<br>
Overenie, či nové zmeny nerozbili to, čo predtým fungovalo. Pomáha zachytiť „nečakané vedľajšie účinky“ pri vývoji.<br><br>

**Endpoint**<br>
Konkrétny bod v API, kam sa posiela požiadavka. Napr. POST /api/login alebo GET /api/users/123. Môžeme ho testovať ručne aj automatizovane.<br><br>

**Test data (testovacie dáta)**<br>
Sada údajov, ktoré používame pri testovaní. Môžu byť reálne, anonymizované, fiktívne alebo náhodne generované.<br><br>

**Soft delete**<br>
Záznam nie je fyzicky zmazaný z databázy – len označený ako „zmazaný“ (napr. deleted\_at nie je NULL). Bežné napríklad pri používateľoch alebo faktúrach.<br><br>

**Assert/Assercia**<br>
Vyjadrenie v teste, ktoré overuje, či výsledok zodpovedá očakávaniu. Napr. assert status\_code == 200 v automatizovanom teste.<br><br>

**Mockovanie (Mocking)**<br>
Simulovanie správania iných častí systému (napr. databázy, API), ktoré ešte nie sú hotové alebo ich nechceme pri teste volať. Používa sa najmä pri automatizovaných testoch.<br><br>

**Testovací scenár (Test scenario)**<br>
Vyššia úroveň ako test case – popisuje, čo sa má testovať, nie krok po kroku. Napr. „Over, že používateľ môže vytvoriť objednávku bez registrácie.“<br><br>

**Test plan (testovací plán)**<br>
Dokument, ktorý popisuje, čo, ako, kedy a kým sa bude testovať. Obsahuje rozsah, prístup, zdroje, časový plán, riziká a kritériá ukončenia.<br><br>

**Test coverage (pokrytie testami)**<br>
Miera toho, koľko funkčnosti je pokrytej testami. Môže byť merané podľa funkcií, kódu (napr. % riadkov), scenárov atď.<br><br>

**User Story**<br>
Popis funkcie z pohľadu používateľa. Napr. „Ako registrovaný používateľ chcem vidieť históriu objednávok, aby som si mohol dohľadať, čo som kúpil.“<br><br>

**Exploratory testing (prieskumné testovanie)**<br>
Testovanie bez pevne daných krokov. Tester skúma systém, hľadá nečakané správanie a zapája intuíciu, zvedavosť aj predchádzajúce skúsenosti.<br><br>

**Negative test (negatívny test)**<br>
Test, ktorý overuje, že systém správne zvládne nesprávne alebo neočakávané vstupy. Napr. prázdne pole, zlý formát dátumu, nulová hodnota.<br><br>

**Acceptance criteria (akceptačné kritériá)**<br>
Podmienky, ktoré musia byť splnené, aby bola úloha považovaná za hotovú. Pomáhajú testovať, čo má funkcia robiť a čo nie.<br><br>

**Regression bug (regresná chyba)**<br>
Chyba, ktorá sa znovu objavila po tom, čo bola už raz opravená. Zvyčajne spôsobená novou zmenou v kóde, ktorá niečo rozbila.<br><br>

**Test suite (súbor testov)**<br>
Zoskupenie viacerých testovacích prípadov, ktoré sa spúšťajú spolu. Môže ísť o testy jednej funkcie, modulu alebo typu (napr. regresné testy).<br><br>

**Sanity test**<br>
Rýchly test malej časti systému, ktorý overí, či má zmysel pokračovať v ďalšom testovaní. Ak sanity test zlyhá, ostatné testy nemajú význam.<br><br>

**Flaky test**<br>
Test, ktorý raz prejde, raz zlyhá, aj keď sa nič nezmenilo. Veľký problém v automatizácii – testovanie je potom nedôveryhodné.<br><br>

**Test environment (testovacie prostredie)**<br>
Konfigurácia systémov, kde sa testuje. Môže mať inú databázu, verziu kódu, práva než produkcia. Dôležité je vedieť, v akom prostredí testujeme.<br>

**Load test (záťažový test)**<br>
Overuje, ako sa systém správa pri bežnej a zvýšenej záťaži. Napr. 1 000 používateľov naraz, veľké množstvo požiadaviek, dlhé reporty.<br><br>

**Performance test (výkonnostný test)**<br>
Testy, ktoré sledujú rýchlosť reakcie, dobu načítania, spotrebu pamäte, využitie CPU. Cieľ: zistiť, či je systém dostatočne svižný.<br><br>

**Test matrix (testovacia matica)**<br>
Tabuľka, ktorá ukazuje, čo všetko je pokryté testami – napr. rôzne kombinácie prehliadačov, zariadení, vstupov alebo rolí.<br><br>

**Boundary value (hraničná hodnota)**<br>
Najnižšia, najvyššia alebo okrajová hodnota vstupu. Hraničné hodnoty bývajú často miestom výskytu chýb. (Napr. ak vek 18 je povolený – čo 17, 18, 19?)<br><br>

**Equivalence partitioning (rozdelenie do tried ekvivalencie)**<br>
Technika, kde vstupy delíme na skupiny, ktoré by sa mali správať rovnako. Stačí otestovať 1 hodnotu z každej skupiny (napr. platné vs. neplatné PSČ).<br><br>

**Unit test (jednotkový test)**<br>
Test malej časti kódu – najčastejšie jednej funkcie alebo metódy. Píšu ho vývojári, overuje, že „tehlička“ systému funguje samostatne správne.<br><br>

**Integration test (integračný test)**<br>
Test viacerých modulov, ktoré spolu komunikujú – napr. databáza + backend, backend + frontend. Cieľ: nájsť chyby v prepojení.<br><br>

**System test (systémový test)**<br>
Kompletné testovanie celej aplikácie ako celku. Overuje, či spolu všetko funguje, ako má – vrátane UI, databázy, API, autentifikácie…<br><br>

**UAT (User Acceptance Testing)**<br>
Akceptačné testovanie – robia ho samotní používatelia alebo zákazník. Overujú, či systém zodpovedá ich potrebám a požiadavkám.<br><br>

**Static testing (statické testovanie)**<br>
Testovanie bez spustenia kódu – napr. kontrola dokumentácie, revízia špecifikácií, kontrola testovacích prípadov.<br><br>

**Dynamic testing (dynamické testovanie)**<br>
Testovanie reálneho správania systému počas behu – teda klikáš, zadávaš vstupy, sleduješ odpovede. Presný opak statického testovania.<br><br>

**Smoke vs. Sanity test**<br>
<u>Smoke:</u> rýchla kontrola po novej verzii – spustí sa systém?<br>
<u>Sanity:</u> kontrola konkrétnej opravy alebo funkcie – funguje konkrétna vec, na ktorú sme sa zamerali?<br><br>

**Bug lifecycle (životný cyklus chyby)**<br>
Cesta chyby od objavenia po uzavretie. Fázy: New → Open → In progress → Resolved → Retested → Closed (alebo Rejected, Duplicate, Won’t fix…).<br><br>

**Test report (testovacia správa)**<br>
Výstup z testovania – zhrnutie toho, čo bolo testované, čo prešlo, čo zlyhalo, koľko chýb sa našlo a akého typu boli. Dôležité pre rozhodovanie o vydaní verzie.<br><br>

**Environment variables (premenné prostredia)**<br>
Hodnoty špecifické pre prostredie (napr. test, staging, produkcia), ktoré ovplyvňujú beh aplikácie – ako napr. URL databázy, API token, debug mód.<br><br>

**Test data management (správa testovacích dát)**<br>
Organizácia, príprava a čistenie údajov, ktoré sa používajú pri testovaní. Cieľ: mať relevantné, spoľahlivé a opakovateľné testovacie scenáre.<br>

**Defect triage (triedenie chýb)**<br>
Spoločné stretnutie (testeri, vývojári, PM), kde sa prechádzajú nahlásené chyby, priraďujú sa im priority, zodpovednosti a rozhoduje sa, čo sa bude opravovať.<br><br>

**Retesting vs. Regression testing**<br>
<u>Retesting:</u> overujeme, či konkrétna opravená chyba už neexistuje.<br>
<u>Regression testing:</u> overujeme, či oprava nerozbila nič iné.<br><br>

**Precondition/Postcondition**<br>
<u>Precondition:</u> čo musí byť splnené pred testom (napr. „používateľ je prihlásený“)<br>
<u>Postcondition:</u> čo má platiť po teste (napr. „objednávka je v stave 'spracovaná'“)<br><br>

**Severity vs. Priority (závažnosť vs. priorita)**<br>
<u>Severity:</u> ako vážna je chyba (napr. systém padne = vysoká závažnosť)<br>
<u>Priority:</u> ako rýchlo ju treba opraviť (napr. chyba v texte na hlavnej stránke = nízka závažnosť, ale vysoká priorita)<br><br>

**Acceptance test (akceptačný test)**<br>
Test, ktorý potvrdzuje, že funkcia robí to, čo má, podľa zadania. Môže byť formálny (UAT) alebo automatizovaný (napr. cez Cucumber).<br><br>

**Automated test (automatizovaný test)**<br>
Test, ktorý sa spúšťa automaticky (napr. cez skripty alebo CI/CD pipeline). Rýchly, opakovateľný, ale náročný na údržbu.<br><br>

**Manual test (manuálny test)**<br>
Test vykonaný človekom – klikáš, skúšaš, pozoruješ. Pomalší, ale flexibilnejší, ideálny na UI testy, prieskum, alebo keď niečo nie je stabilné.<br><br>

**CI/CD (Continuous Integration / Continuous Delivery)**<br>
Proces, kde sa zmeny kódu automaticky testujú a nasadzujú. Pomáha rýchlemu a bezpečnému vývoju. Tester môže napojiť svoje testy do tohto procesu.<br><br>

**Heuristika**<br>
Skúsenostné pravidlo, ktoré tester používa na odhadovanie chýb tam, kde nemá jasné špecifikácie. Napr. „čo sa často kazí, bude sa kaziť znova“, alebo „najprv otestuj najčastejšie scenáre“.<br><br>

**Bug bash**<br>
Organizované skupinové testovanie, kde sa do hľadania chýb zapoja testeri, vývojári, PM aj ďalší – cieľom je čo najrýchlejšie nájsť čo najviac chýb.<br><br>

**Defect leakage (únik chyby)**<br>
Chyba, ktorá prešla testovaním, ale našla sa až v produkcii. Dôležitý ukazovateľ kvality testovania.<br><br>

**Test oracle**<br>
Zdroje, ktoré ti povedia, čo je správne správanie systému – špecifikácie, návrhy, podobný systém, skúsenosti, zákony, zdravý rozum…<br><br>

**Test strategy (testovacia stratégia)**<br>
Vysoká úroveň popisu ako testovať produkt – aký bude prístup, čo testovať budeme a čo nie, aké typy testov použijeme a prečo.<br><br>

**Test log (testovací záznam)**<br>
Detailný záznam o tom, ako test prebiehal – čo bolo spustené, kedy, s akými dátami a výsledkami. Užitočný pri hľadaní príčiny zlyhania.<br><br>

**Session-based testing**<br>
Forma prieskumného testovania, kde má tester vopred definovaný cieľ, časový rámec a po teste vytvorí záznam o tom, čo skúšal a čo našiel.<br><br>

**Quality gate (kvalitný prah)**<br>
Podmienka, ktorá musí byť splnená, aby systém mohol postúpiť ďalej (napr. z testu do produkcie). Môže byť počet chýb, pokrytie testami, úspešnosť CI testov atď.<br><br>

**Shift-left testing**<br>
Prístup, kde sa testovanie presúva čo najskôr do vývojového procesu – začína už pri návrhu, špecifikácii alebo v kóde (napr. unit testy, code review, CI).<br><br>

**QA vs QC (Quality Assurance vs Quality Control)**<br>
<u>QA:</u> procesy, ktoré predchádzajú chybám (plánovanie, štandardy, prevencia)<br>
<u>QC:</u> konkrétne hľadanie chýb v produkte (testovanie, kontrola výsledkov)<br><br>

**Testability (testovateľnosť)**<br>
Miera, do akej je systém navrhnutý tak, aby sa dal efektívne testovať. Vysoká testovateľnosť znamená jasné logy, jednoduché overenie výstupov, stabilné prostredie a dobrú dokumentáciu.<br>

**Bug reproducibility (reprodukovateľnosť chyby)**<br>
Schopnosť opakovane vyvolať chybu rovnakým spôsobom. Ak sa chyba vyskytne len niekedy, je „flaky“ a ťažko sa opravuje.<br><br>

**Logging**<br>
Zaznamenávanie udalostí počas behu aplikácie. Dobrý log pomáha rýchlo pochopiť, čo sa stalo, kde a prečo – často je prvou pomôckou testera aj vývojára pri chybe.<br><br>

**Root cause analysis (analýza príčiny)**<br>
Postup, ktorým zisťujeme, čo presne spôsobilo chybu. Dôležitý krok pri riešení bugov aj pri zlepšovaní procesov (napr. prečo sa chyba dostala do produkcie?).<br><br>

**Test steps (testovacie kroky)**<br>
Konkrétne inštrukcie, ktoré tester vykoná počas testu. Dobré testovacie kroky sú jednoznačné, očíslované a vedú k overiteľnému výsledku.<br><br>

**Test evidence (dôkaz testu)**<br>
Záznam toho, že test prebehol – napr. screenshot, výpis logu, export údajov. Pomáha preukázať výsledok a je dôležitý pri formálnom testovaní.<br><br>

**Happy path (šťastná cesta)**<br>
Ideálny priebeh scenára, keď všetko prebehne správne bez chýb. Väčšina testov začína práve overením happy path.<br><br>

**Testware**<br>
Všetko, čo vznikne počas testovania: testy, dáta, skripty, výsledky, logy... Testware má svoju hodnotu – treba ho udržiavať a zálohovať.<br><br>

**Timebox**<br>
Časové ohraničenie úlohy alebo testu. Napr. „prieskumné testovanie 60 minút“. Pomáha udržať fokus, najmä pri manuálnych a kreatívnych úlohách.<br><br>

**Blocker**<br>
Chyba alebo okolnosť, ktorá znemožňuje pokračovať v testovaní. Napr. keď nefunguje prihlásenie alebo nemáme prístup do prostredia.<br><br>

**Repro steps (kroky na reprodukciu)**<br>
Popis, ako vyvolať chybu. Jasné a presné repro steps sú základ dobrého bug reportu – bez nich vývojár nevie, čo má opraviť.<br><br>

**Golden path**<br>
Podobné ako „happy path“, ale často širšie – opisuje odporúčaný alebo najčastejší spôsob, ako používateľ systém používa.<br><br>

**Test debt (dlh v testovaní)**<br>
Podobne ako technický dlh – ide o zanedbané alebo chýbajúce testy, ktoré sa „raz vrátia“ a spôsobia problémy. Napr. chýbajúce regresné testy, neautomatizované kritické funkcie.<br><br>

**Scripted vs. Unscripted testing**<br>
<u>Scripted:</u> testujeme presne podľa napísaných krokov.<br>
<u>Unscripted:</u> testujeme voľne, na základe skúseností, intuície a aktuálneho správania systému.<br><br>

**Test freeze**<br>
Stav, keď sa už nemenia testy ani prostredie. V tomto bode by už malo prebiehať len spúšťanie existujúcich testov a príprava na vydanie.<br><br>

**Zombie bug**<br>
Chyba, ktorá sa opakovane vracia, aj keď bola "opravená". Buď nie je naozaj vyriešená, alebo sa vždy niekto „postará“, aby znovu vstala z mŕtvych. <br><br>

**Rubber duck debugging**<br>
Vysvetľovanie problému (často nahlas alebo bábke/kačke) – už samotné rozprávanie pomáha nájsť riešenie. Aj tester to môže využiť na ujasnenie si bug reportu.<br><br>

**Happy smoke + grumpy sanity**<br>
Zábavné pomenovanie na zapamätanie rozdielu: smoke test = „všetko ok, môžeme začať“, sanity test = „ok, ale tá konkrétna oprava fakt funguje?“<br><br>

**Dogfooding**<br>
Interné používanie vlastného softvéru (napr. vývojári testujú vlastnú appku). Tester by mal byť pri tom – nájde chyby, ktoré vývojári ignorujú.<br><br>

**Feature toggle/Flag**<br>
Prepínač, ktorým sa zapína alebo vypína funkcia bez nutnosti meniť kód. Tester musí vedieť, ktoré sú aktívne – inak môže testovať „vzduch“.<br><br>

**Dead code**<br>
Časť kódu, ktorá sa nikdy nevykoná – a tým pádom sa často ani netestuje. Ale keď sa v nej niečo zmení, môže rozbiť to, čo „sa nemalo používať“.<br><br>

**Red-Green-Refactor**<br>
Prístup pri písaní testov (TDD): najprv test zlyhá (red), potom sa opraví (green), a potom sa kód zlepší (refactor). Tester môže sledovať, či vývojári refaktorujú – alebo len zalepujú.<br>

**QA translator**<br>
Tester ako tlmočník medzi tým, čo vývojár povedal, čo PM (projektový manažér) myslel, čo klient chcel a čo appka reálne robí.<br><br>

**Click monkey**<br>
Posmešné označenie manuálneho testera, ktorý len kliká bez kontextu. V dobrom slúži ako memento: tester má byť zvedavý, nie len klikač.<br><br>

**Dirty data**<br>
Testovacie dáta, ktoré sú poškodené, neaktuálne alebo nedokumentované. Skrátka také, čo spôsobia, že test „čudne padne“ a nikto nevie prečo. Dobrý test potrebuje dobré dáta. Chaos v dátach vedie k falošným chybám.<br><br>

**Boomerang bug**<br>
Chyba, ktorá sa vracia po tom, čo bola uzavretá ako „fixed“. Niekedy kvôli nesprávnemu retestovaniu, niekedy preto, že sa fix aplikoval len na polovicu systému.<br><br>

**Test pyramid**<br>
Koncept, podľa ktorého by malo byť najviac unit testov (dole), menej integračných (v strede) a najmenej UI testov (hore). Opačná pyramída = testovacie bolenie brucha (ako budova Slovenského rozhlasu v Bratislave).<br><br>

**Time bomb**<br>
Kód, ktorý funguje len do určitého dátumu. Napr. keď je platnosť testovacích dát „do 2022“ a odvtedy všetko padá. Tester = budík, ktorý to má nájsť skôr, než vybuchne.<br><br>

**Shadow testing**<br>
Testovanie nového systému na pozadí bez toho, aby ovplyvnil produkciu. Napr. nový výpočet ceny sa spúšťa paralelne s tým starým – a porovnávajú sa výsledky.<br><br>

**Mutation testing**<br>
Metóda, pri ktorej sa zámerne vkladajú chyby do kódu, aby sa overilo, či ich testy zachytia. Ak ich nezachytia → testy sú slabé. Hardcore testovacia technika.<br><br>

**Known issue**<br>
Chyba, o ktorej vieme, ale ešte ju nemáme opravenú. Často ju nájde nový tester, s nadšením nahlási... a dostane späť odpoveď „áno, to vieme, máme v Jire od 2019“.<br><br>

**Test branching**<br>
Testy sú verzované podobne ako kód. Rôzne branche testov zodpovedajú rôznym verziám aplikácie. Veľká výzva pre koordináciu medzi QA a vývojom.<br><br>

**Jumping to conclusions**<br>
Keď tester nahlási bug, ale neotestoval všetky možnosti alebo neoveril, že ide o chybu (a nie napr. nepochopenie feature). 🧐 Dobrá poznámka pre juniorov – pozor na zbrklosť.<br><br>

**Fuzzy testing (Fuzz testing)**<br>
Automatizovaný spôsob, ako systém zaplaviť náhodnými, nečakanými alebo „šialenými“ vstupmi. Cieľ: nájsť, kde sa niečo rozsype. Obľúbené pri bezpečnostných testoch.<br><br>

**Bug taxonomy**<br>
Systém triedenia chýb podľa typu, dôvodu alebo dôsledku. Tester vie lepšie analyzovať, kde sa opakujú chyby – a QA tím sa z toho môže učiť.<br><br>

**Heisenbug**<br>
Bug, ktorý zmizne alebo zmení správanie, keď sa ho snažíš debugovať. V bežnom režime padá ako muchotrávka. Zapneš logovanie? Debug mód? Sleduješ ho?<br><br>

**HTML injection**<br>
Zraniteľnosť, pri ktorej môže útočník vložiť vlastný HTML kód do stránky – napr. cez formulár alebo URL. Výsledok? Od obyčajného rozhodenia dizajnu až po falošné tlačidlá, iframe, prehliadanie dát iných používateľov…<br><br>

**XOR**<br>
(z anglického *exclusive OR*, slovensky **„výlučné ALEBO“**) je logická operácia, ktorá vracia hodnotu **pravda (true)** iba vtedy, keď práve **jedna** z dvoch hodnôt je pravdivá.Ak sú obidve hodnoty rovnaké (t. j. obe **true** alebo obe **false**), výsledkom je **false**.<br><br>

**XNOR**<br>
(z anglického *exclusive NOR*, slovensky **„logické rovnocenné“** alebo aj **„negácia výlučného ALEBO“**) je logická operácia, ktorá vracia hodnotu **pravda (true)** iba vtedy, keď **obe** vstupné hodnoty sú rovnaké.
Ak sú hodnoty **odlišné** (t. j. jedna **true**, druhá **false**), výsledkom je **false**.<br><br>

**XAND**<br>
Pojem XAND nie je štandardnou logickou operáciou ako AND, OR, XOR alebo XNOR. Občas sa vyskytuje ako neformálne alebo chybné označenie pre „negáciu XOR“, no tú správne nazývame XNOR. Pojem XAND nie je štandardnou logickou operáciou ako AND, OR, XOR alebo XNOR. Občas sa vyskytuje ako neformálne alebo chybné označenie pre „negáciu XOR“, no tú správne nazývame XNOR.<br><br>

**Monkey Testing**<br>
Pri testovaní mobilných apiek som sa stretla s nástrojom pre náhodné klikanie, ťukanie, scrollovanie, bez plánu. A malo to vcelku prekvapivé výsledky.<br><br>

**Dropdown**<br>
Rozbaľovacie menu – používateľské rozhranie, ktoré zobrazuje zoznam možností po kliknutí na pole alebo šípku. Najčastejšie sa používa pri výbere jednej hodnoty zo zoznamu (napr. výber krajiny, roka, kategórie…).<br><br>

**Checkbox**<br>
Zaškrtávacie políčko – používateľský prvok, ktorý umožňuje vybrať jednu alebo viacero nezávislých možností. Používa sa tam, kde môže byť vybraných viac hodnôt naraz (napr. „Súhlasím s podmienkami“, „Chcem dostávať newsletter“).<br><br>

**Label**<br>
Popisný text, ktorý je priradený k inému prvku používateľského rozhrania – najčastejšie k formulárovému poľu (input, checkbox, radio button…). Pomáha používateľovi pochopiť, čo má do daného poľa zadať alebo čo konkrétny prvok znamená.<br><br>

**Tooltip**<br>
Krátky vysvetľujúci text, ktorý sa zobrazí po nabehnutí kurzora myši (alebo zameraní) na prvok – najčastejšie ikonu, tlačidlo alebo pole. Slúži na doplnenie informácií bez zaberania miesta v rozhraní. Môže vysvetliť funkciu, význam alebo upozorniť na pravidlá.<br><br>

**Sandbox**<br>
Izolované testovacie prostredie, ktoré simuluje reálne podmienky, ale bez rizika ovplyvnenia produkčných dát alebo systémov. Používa sa na bezpečné experimentovanie, testovanie funkcií, API alebo bezpečnostných scenárov.<br><br>

**Seed data**<br>
Vopred pripravené dáta, ktoré sa automaticky nahrajú do databázy pri spustení testovacieho prostredia alebo aplikácie. Slúžia na to, aby mal tester alebo vývojár ihneď k dispozícii niečo, s čím môže pracovať – používateľov, produkty, objednávky, atď.<br><br>

**Timestamp**<br>
Časová pečiatka – presný okamih v čase, zaznamenaný vo formáte dátum + čas (napr. 2025-07-07 13:45:00). Používa sa na evidenciu kedy sa niečo stalo: vytvorenie záznamu, zmena, prihlásenie, chyba, transakcia...<br><br>

**CLI (Command Line Interface)**<br>
Rozhranie príkazového riadku – spôsob ovládania systému alebo aplikácie pomocou textových príkazov, nie klikania v grafickom rozhraní (GUI). Používa sa najmä vývojármi, administrátormi a testermi na rýchle alebo automatizované operácie.<br><br>

**Mitigácia**<br>
Zmiernenie dopadu problému – opatrenie, ktoré nezabráni chybe alebo hrozbe úplne, ale zníži jej vplyv. Používa sa najmä v bezpečnostnom testovaní, rizikovej analýze alebo pri riešení incidentov.<br><br>

**SDLC (Software Development Life Cycle)**<br>
Životný cyklus vývoja softvéru – súbor fáz, ktoré vedú od nápadu k hotovej aplikácii. Každá fáza má svoje úlohy, výstupy a zodpovednosti.<br>

Typické fázy SDLC:<br>

- Zber požiadaviek – čo má systém robiť<br>
- Analýza a návrh – ako to bude fungovať a vyzerať<br>
- Implementácia – vývoj kódu<br>
- Testovanie – overenie kvality, funkčnosti, bezpečnosti<br>
- Nasadenie – uvedenie do prevádzky<br>
- Údržba – opravy, aktualizácie, podpora<br><br>

**Waterfall (vodopádový model)**<br>
Tradičný spôsob vývoja softvéru, kde sa fázy projektu vykonávajú lineárne – jedna za druhou.
Až keď sa dokončí jedna fáza (napr. analýza), môže začať ďalšia (napr. vývoj). Každý krok „padá“ do ďalšieho ako vodopád. Fázy:Zber požiadaviek, Analýza, Návrh, Implementácia, Testovanie, Nasadenie, Údržba<br>

**Agile**<br>
Prístup k vývoju softvéru, ktorý kladie dôraz na pružnosť, spoluprácu a časté zmeny. Namiesto jedného veľkého plánu sa vyvíja postupne v krátkych cykloch (sprintoch) a tím reaguje na spätnú väzbu počas vývoja.<br>

Tester v Agile:<br>
– je aktívnou súčasťou tímu od začiatku,<br>
– testuje priebežne, nielen na konci,<br>
– spolupracuje s vývojármi, PM aj UX,<br>
– pomáha písať akceptačné kritériá a user stories,<br>
– robí exploratívne aj automatizované testy.<br><br>

**Scrum**<br>
Najpoužívanejší Agile framework – vývoj prebieha v sprintoch, tím má definované role (Scrum Master, Product Owner, vývojári/testeri) a pravidelné ceremónie.<br><br>

**Sprint**<br>
Krátky časový úsek (zvyčajne 1–4 týždne), počas ktorého sa doručí konkrétny výstup – funkcia, oprava, zmena. Sprint má svoj cieľ, plán a retrospektívu.<br><br>

**Daily (stand-up)**<br>
Krátke (ideálne 15-minútové) denné stretnutie tímu – každý povie, čo včera robil, čo bude robiť dnes a či niečo blokuje jeho prácu.<br><br>

**Backlog**<br>
Zoznam všetkého, čo by produkt mal vedieť – funkcie, opravy, nápady… Prioritizovaný Product Ownerom, tím si z neho ťahá úlohy do sprintu.<br><br>

**Backlog grooming/refinement**<br>
Spresňovanie backlogu – tím spolu s PO upresňuje, rozdeľuje, boduje a čistí položky, aby boli pripravené na budúci sprint.<br><br>

**User story**<br>
Popis funkčnosti z pohľadu používateľa. Napr. „Ako registrovaný používateľ chcem vidieť históriu objednávok, aby som si mohol niečo dohľadať.“<br><br>

**Acceptance criteria**<br>
Podmienky, ktoré musia byť splnené, aby sa story považovala za hotovú. Pomáhajú testerovi určiť, čo overiť.<br>

**Definition of Done (DoD)**<br>
Dohodnuté kritériá, čo znamená „hotové“. Môže zahŕňať: kód je napísaný, otestovaný, reviewnutý, nasadený a dokumentovaný.<br><br>

**Sprint review**<br>
Stretnutie na konci sprintu, kde tím ukazuje stakeholderom, čo vytvoril. Príležitosť na spätnú väzbu.<br><br>

**Sprint retrospective (retro)**<br>
Reflexia sprintu – čo išlo dobre, čo nie, čo zlepšiť nabudúce. Cieľ: zlepšovať proces, nie hľadať vinníka.<br><br>

**Velocity**<br>
Miera, koľko práce tím zvládne za sprint. Sleduje sa napr. počet story points. Pomáha odhadnúť kapacitu tímu do budúcna.<br><br>
