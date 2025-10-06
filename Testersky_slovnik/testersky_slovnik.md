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

**AI-under-test**
Testujeme samotnú umelú inteligenciu – teda model, algoritmus alebo systém, ktorý sa správa „inteligentne“.
Napr. testujeme, či chatbot odpovedá správne, či ML model klasifikuje e-maily dobre, alebo či odporúčací systém neponúka nezmysly.
Tester sa tu zameriava na presnosť, spravodlivosť, stabilitu a chovanie pri rôznych vstupoch.

**AI-assisted testing**
Tester používa AI ako pomocníka pri testovaní – napr. na generovanie testovacích dát, návrh testov, analýzu logov, písanie skriptov alebo odhaľovanie vzorov.
AI = testovací kolega (ktorý nepije kávu a píše rýchlejšie než ty).
Je to ako mať „copilota“ – ty riadiš, AI navrhuje.

**AI-driven testing**
AI automaticky riadi testovanie – sama analyzuje aplikáciu, rozhoduje, čo testovať, generuje a spúšťa testy, vyhodnocuje výsledky.
Cieľ: maximálna automatizácia pomocou AI – najmä pri komplexných systémoch, ktoré sa často menia.
Nie vždy ide o úplne samostatné testovanie, ale AI tu hrá hlavnú rolu v rozhodovaní.

**Bias (zaujatosť)**
Nežiaduca systematická odchýlka v správaní AI modelu, ktorá vedie k nerovnakému zaobchádzaniu s rôznymi skupinami vstupov (napr. demografickými, jazykovými, kontextovými).

**Hlavné metriky Machine Learning a AI**
Krátky prehľad najpoužívanejších metrík na hodnotenie kvality modelov a AI systémov:
- **Accuracy (presnosť)**
Podiel správnych predikcií na všetkých prípadoch. Vhodná, keď sú triedy vyvážené.
- **Precision (presnosť)**
Podiel správne označených pozitívnych prípadov na všetkých prípadoch, ktoré model označil za pozitívne. Kritická pri vysokých nákladoch falošne pozitívnych.
- **Recall (Citlivosť)**
Podiel správne zachytených pozitívnych prípadov na všetkých skutočných pozitívnych. Dôležitá, keď je nevyhnutné nájsť čo najviac reálnych pozitív.
- **F1-score**
Harmonický priemer precision a recall. Vhodný pre vyvážené hodnotenie tam, kde ani jedna metrika nestačí.
- **ROC-AUC**
Plocha pod krivkou Receiver Operating Characteristic (True Positive Rate vs. False Positive Rate). Ukazuje celkovú schopnosť modelu rozlišovať triedy pri rôznych prahových hodnotách.
- **Confusion Matrix**
Dvojrozmerná tabuľka TP (true positive), FP (false positive), FN (false negative), TN (true negative) pre detailný pohľad na typy chýb.
- **Log Loss (Cross-entropy loss)**
Penalizuje neisté predikcie, vhodná pre pravdepodobnostné výstupy.
- **Mean Absolute Error (MAE) / Mean Squared Error (MSE)**
Štandardné metriky pre regresiu – priemer absolútnych alebo kvadratických odchýlok od skutočných hodnôt.

**Canary release**
Postupné nasadzovanie novej verzie len na malú časť produkčných serverov/používateľov, aby sa overilo, že nová verzia funguje, skôr než sa rozšíri na celek.

**Blue-green deployment**
Strategia nasadenia, kde existujú dve identické produkčné prostredia (blue a green). Nová verzia sa nasadí na nepoužívané prostredie a po úspešnom otestovaní sa “prepne” na používateľov.

**Chaos engineering**
Prístup, pri ktorom sa do systému cielene zavádzajú chyby (výpadky, latencia, zlyhania služieb), aby sa overila jeho odolnosť a schopnosť zotaviť sa.

**Service virtualization**
Simulovanie správania závislých služieb (napr. externé API, mikroservisy), ktoré ešte nie sú dostupné alebo sú nákladné, aby testy mohli bežať izolovane a rýchlo.

**Contract testing**
Testovanie dohôd (kontraktov) medzi službami – overenie, či poskytovateľ aj konzument API dodržiavajú spoločné špecifikácie.

**Data-driven testing**
Technika, kde sa rovnaký testovací scenár spúšťa s rôznymi vstupnými dátami (napr. z CSV/tabulky) bez potreby písať duplicitný kód.

**Keyword-driven testing**
Štruktúra testov, kde sú kroky definované pomocou „kľúčových slov“ s mapovaním na implementované funkcie, čo uľahčuje údržbu a čitateľnosť skriptov.

**Model-based testing**
Generovanie testovacích scenárov automaticky z formálneho modelu (napr. stavového diagramu) systému, čím sa zabezpečí lepšie pokrytie.

**Orthogonal array testing**
Matematická technika na redukciu počtu kombinácií vstupov pri zachovaní dobrého pokrytia, často používaná pri testovaní veľkého množstva parametrov.

**Usability testing**
Testovanie z pohľadu reálnych používateľov, zamerané na to, ako intuitívne a pohodlné je používateľské rozhranie, typicky s využitím scenárov a pozorovania.

**Accessibility testing**
Overovanie, či je aplikácia prístupná aj používateľom so zdravotným znevýhodnením (napr. čítačky obrazovky, klávesové skratky, kontrast farieb).

**Security testing**
Testy, ktoré odhaľujú zraniteľnosti (XSS, SQL injection, CSRF), kontrolujú autentifikáciu/autorizáciu, šifrovanie dát atď.

**Performance profiling**
Podrobná analýza, kde dochádza k úzkym miestam (CPU, pamäť, I/O) v aplikácii, často s použitím profilovacích nástrojov.

**Pair testing**
Dve osoby (tester–tester alebo tester–developer) spoločne pri jednom počítači identifikujú chyby a diskutujú o scenároch, čo zvyšuje kvalitu a vedomosti tímu.

**Shift-right testing**
Doplnenie testovania do produkcie – monitorovanie, A/B testy, canary analýzy a chaos engineering už po nasadení, na doplnenie klasických testov.

**DevOps culture (kultúra DevOps)**
Spoločný prístup tímov vývoja a prevádzky, ktorý zdôrazňuje automatizáciu, spoluprácu a neustále doručovanie (CI/CD). Tester v DevOps tíme participuje na návrhu pipeline, sleduje metriky nasadení a pomáha rýchlo identifikovať regresie.

**Release management (riadenie vydaní)**
Proces plánovania, koordinácie a monitorovania nasadení softvéru. Zahŕňa definovanie termínov, zodpovedností, rollback plánov a komunikačné plány – všetko, čo tester potrebuje vedieť, aby pripravil testovacie prostredie a testovacie dáta.

**Change management (riadenie zmien)**
Štruktúrovaný proces na schvaľovanie, dokumentovanie a komunikovanie zmien v systéme. Tester sa zúčastňuje posudzovania dopadu zmien, aby vedel, ktoré testy treba spustiť pri každom nasadení.

**Configuration management (správa konfigurácií)**
Udržiavanie a verzovanie softvérových a hardvérových nastavení (vstupné parametre, sieťové profily, verzie knižníc). Tester potrebuje konzistentné prostredia, preto sleduje, či sa konfigurácie správne synchronizujú naprieč test, staging a produkciu.

**Observability (pozorovateľnosť)**
Schopnosť získať prehľad o vnútri bežiaceho systému pomocou logov, metrík a tracingu. Dobrá observability umožňuje testerovi rýchlo lokalizovať problém a overiť, či testované scenáre spôsobili očakávané udalosti.

**Monitoring (monitorovanie)**
Nepretržité sledovanie dostupnosti a výkonnosti systému v testovacích aj produkčných prostrediach. Tester spolupracuje s tímom prevádzky, aby nastavil alarmy na kritické chyby alebo regresné metriky.

**Incident management (riadenie incidentov)**
Postup pri riešení neplánovaných výpadkov alebo chýb v produkcii. Tester sa môže zapojiť do post-mortem analýzy, pomáha so zberom dôkazov (test evidence) a overuje, či implementované opravy skutočne chyby odstránili.

**Service Level Agreement (SLA) (dohody o úrovni služieb)**
Kontrakt medzi poskytovateľom služby a zákazníkom, ktorý definuje garancie dostupnosti, odozvy a obnovy. Tester musí overiť, či systém dodržiava SLA parametre počas záťažových a stresových testov.

**Service virtualization (virtualizácia služby)**
Simulácia správania externých systémov (API, mikroservisov, databáz), ktoré sú ťažko dostupné alebo nákladné. Tester tak môže izolovane overovať logiku aplikácie bez závislosti na reálnych službách.

**Contract testing (testovanie kontraktov)**
Overenie, že poskytovateľ a konzument API dodržiavajú dohodnuté špecifikácie (“kontrakty”). Pomáha predchádzať integračným zlyhaniam medzi tímami a zabezpečuje, že zmeny na strane API nepretrhnú dohody.

**Behavior-driven development (BDD)**
Metodika, ktorá definuje testovacie scenáre v prirodzenom jazyku (napr. Gherkin), spájajúca technickú a netechnickú dokumentáciu. Tester i biznis analytik spolu píšu “user stories” so scenármi formou „Given–When–Then“.

**Test-driven development (TDD)**
Prístup, kde sa najprv napíše test, potom ho kód “červený” (zlyhá), následne sa implementuje kód tak, aby test prešiel (“zelený”) a potom sa refaktoruje – princíp Red-Green-Refactor.

**End-to-end testing**
Komplexné testovanie celého toku aplikácie od UI až po databázu a späť. Simuluje reálne používateľské scenáre a overuje integritu všetkých vrstiev.

**API testing**
Cielené testovanie REST/SOAP či GraphQL rozhraní. Overuje kódy odpovedí, schému dát, čas odozvy a správanie pri chybových vstupoch.

**UI testing (User Interface testing)**
Automatizované alebo manuálne overovanie funkčnosti a vzhľadu používateľského rozhrania – tlačidlá, formuláre, navigácia, responzívnosť.

**Cross-browser testing**
Testovanie webových aplikácií naprieč rôznymi prehliadačmi (Chrome, Firefox, Safari, Edge) a ich verziami, aby sa zabezpečila konzistentná funkcionalita a vzhľad.

**Fault injection**
Cielené vkladanie chýb (sieťové oneskorenie, zlyhanie služby, nedostatok pamäte) do systému, aby sa overila jeho odolnosť a správne ošetrenie výnimiek.

**Synthetic monitoring**
Automatizované “robotické” testy, ktoré pravidelne kontrolujú dostupnosť a výkon kľúčových funkcií na produkcii z rôznych geografických lokalít.

**Mobile testing**
Testovanie aplikácií na mobilných zariadeniach vrátane simulátorov a reálnych zariadení, so zameraním na rôzne OS (iOS, Android), rozlíšenia a hardvérové špecifiká.

**Localization testing**
Overovanie, či je aplikácia správne prispôsobená pre rôzne jazyky a regióny – formáty dátumov/času, preklady, rozloženie textu.

**Penetration testing**
Etický “útok” na aplikáciu s cieľom nájsť bezpečnostné dierky (SQL injection, XSS, CSRF, zle nastavené autorizácie) predtým, než zneužijú útočníci.

**Compliance testing**
Kontrola, či systém spĺňa regulačné požiadavky (napr. GDPR, PCI DSS, ISO normy), vrátane auditných záznamov a ochrany osobných údajov.

**A/B testing**
Porovnanie dvoch verzií funkcie alebo UI prvku (Variant A vs. Variant B) na vzorke používateľov, aby sa vyhodnotilo, ktorá prináša lepší výsledok (konverzie, retention).

**Test harness**
Rámec alebo sada nástrojov (skripty, knižnice), ktorá umožňuje spúšťať a reportovať výsledky testov (napr. JUnit, pytest, TestNG).

**Stacktrace**
(alebo „výpis zásobníka volaní“) je technický výpis, ktorý ukazuje reťazec volaní funkcií, ktoré viedli k chybe alebo výnimke v programe.

**Feature toggles/Feature flag**
sú prepínače, ktorými možno zapnúť alebo vypnúť konkrétnu funkcionalitu bez nutnosti meniť kód. Umožňujú napríklad nasadiť funkciu na všetky prostredia, ale aktivovať ju len v niektorých z nich (napr. len v teste).

**SMTP **
(Simple Mail Transfer Protocol) je protokol na odosielanie e-mailov z aplikácie – typicky sa používa na zasielanie notifikácií, potvrdení objednávky alebo resetovacích odkazov. V testovaní je dôležité overiť, či je SMTP správne nakonfigurovaný, aby e-maily odchádzali a neboli zablokované alebo označené ako spam.

**Build number**
je číselný identifikátor konkrétneho zostavenia (build-u) aplikácie. Pomáha rozlíšiť jednotlivé verzie softvéru – napríklad ak vývojári vykonali zmeny a znova aplikáciu zbuildovali, každé nové zostavenie dostane nové „build number“, čo umožňuje presne sledovať, ktorá verzia je nasadená v ktorom prostredí.

**Commit hash**
je jedinečný identifikátor (zvyčajne dlhý reťazec znakov), ktorý označuje konkrétny commit v systéme na správu verzií (napr. Git). Vďaka nemu vieš presne určiť, aký kód bol nasadený – aj keď dve verzie aplikácie vyzerajú rovnako, rôzny commit hash odhalí, že pochádzajú z iného stavu vývoja.

**Version endpoint**
je špeciálne API rozhranie (napr. /version), ktoré vracia aktuálne informácie o nasadenej verzii aplikácie – ako napr. číslo buildu alebo commit hash. Tester si tak vie jednoducho overiť, či je v danom prostredí nasadená správna verzia softvéru.

**Debug logy**
sú detailné výpisy z aplikácie určené najmä pre vývojárov – obsahujú technické informácie, ktoré pomáhajú pri hľadaní chýb (napr. hodnoty premenných, priebeh funkcií). V produkčnom prostredí by nemali byť zapnuté, pretože môžu spomaliť aplikáciu a odhaliť citlivé informácie.

**Latency**
je oneskorenie medzi požiadavkou a reakciou – teda čas, ktorý uplynie od odoslania požiadavky (napr. klik na tlačidlo) po prijatie odpovede zo servera. V testovaní je dôležité sledovať, či toto oneskorenie neprekračuje akceptovateľné limity, najmä pri prechode na produkčné prostredie, kde môže byť infraštruktúra odlišná.

**HTTP**
(Hypertext Transfer Protocol) je základný komunikačný protokol, pomocou ktorého prehliadač posiela požiadavky na webový server a prijíma odpovede (napr. HTML stránky, obrázky, API odpovede). Je to nezabezpečený protokol – preto sa v praxi často používa jeho bezpečná verzia HTTPS, ktorá navyše šifruje komunikáciu.

**HTTPS**
(Hypertext Transfer Protocol Secure) je zabezpečená verzia protokolu HTTP, ktorá šifruje komunikáciu medzi prehliadačom a serverom pomocou SSL/TLS certifikátu. Vďaka tomu sú údaje chránené pred odpočúvaním, manipuláciou a falošnými stránkami.

**TLS**
(Transport Layer Security) je kryptografický protokol, ktorý zabezpečuje šifrovanie a integritu dát pri prenose medzi klientom a serverom – je nástupcom SSL. Používa sa v spojení s HTTPS a zabezpečuje, že komunikácia nemôže byť odpočúvaná ani zmenená.

**DNS**
(Domain Name System) je systém, ktorý prekladá názvy domén (napr. example.com) na IP adresy serverov, kde beží aplikácia. Ak DNS nefunguje správne alebo je zle nastavený, aplikácia sa nemusí načítať, pretože sa klient nedostane na správny server.

**Redirect**
je automatické presmerovanie používateľa z jednej adresy na inú – napríklad keď zadáš example.com a prehliadač ťa presmeruje na https://www.example.com. V testovaní kontrolujeme, či sú tieto presmerovania správne nastavené (napr. HTTP → HTTPS alebo staré URL → nové) a či nevedú na chybné alebo neexistujúce stránky.

**SSL certifikáty**
slúžia na zabezpečenie šifrovanej komunikácie medzi klientom a serverom (napr. pri HTTPS). Overením certifikátu zisťujeme, či je platný, vydaný dôveryhodnou autoritou a či zodpovedá doméne, na ktorej beží aplikácia.

**CSP**
(Content-Security-Policy) je bezpečnostný HTTP header, ktorý určuje, z akých zdrojov môže webová stránka načítať obsah (napr. skripty, obrázky, štýly). Pomáha zabrániť útokom ako Cross-Site Scripting (XSS), pretože obmedzuje, čo sa môže na stránke spúšťať a odkiaľ.

**X-Frame-Options**
je bezpečnostný HTTP header, ktorý určuje, či sa môže stránka zobraziť v rámci iného webu (napr. v <iframe>). Slúži ako ochrana pred útokmi typu „clickjacking“, kde by útočník mohol cez neviditeľné prekrytie manipulovať so stránkou bez vedomia používateľa.

**CORS**
(Cross-Origin Resource Sharing) je bezpečnostný mechanizmus, ktorý určuje, ktoré domény môžu pristupovať k zdrojom (napr. API) na inej doméne. Ak nie je CORS správne nastavený, aplikácia môže buď zbytočne blokovať požiadavky, alebo naopak umožniť prístup neoprávneným doménam, čo je bezpečnostné riziko.

**Integrity constraints**
Pravidlá v databáze, ktoré zabezpečujú správnosť a konzistenciu dát. Napríklad obmedzenie, že hodnota v stĺpci nemôže byť NULL alebo že musí byť jedinečná.

**Orphan records**
Záznamy v databáze, ktoré nemajú nadväzujúci rodičovský záznam (napr. objednávka priradená k neexistujúcemu zákazníkovi). Často ide o dôsledok chýb v mazacích alebo aktualizačných operáciách.

**Stavový diagram**
Grafické znázornenie stavov systému alebo objektu a prechodov medzi nimi. Pomáha testerom pochopiť logiku správania a identifikovať možné scenáre.

**UML**
(Unified Modeling Language) štandardizovaný jazyk na vizuálne modelovanie softvéru. Používa sa na tvorbu diagramov procesov, tried, sekvencií či stavov.

**Session management**
Správa používateľských relácií v aplikácii – od prihlásenia až po odhlásenie alebo vypršanie časového limitu. Nesprávne nastavenie môže viesť k bezpečnostným rizikám.

**Batch processing**
Spracovanie väčšieho množstva dát naraz v dávkach, často plánovane mimo špičky. V testovaní sa overuje správnosť, výkon a spracovanie chýb.

**Cache invalidácia**
Spracovanie väčšieho množstva dát naraz v dávkach, často plánovane mimo špičky. V testovaní sa overuje správnosť, výkon a spracovanie chýb.

**Force refresh**
Spracovanie väčšieho množstva dát naraz v dávkach, často plánovane mimo špičky. V testovaní sa overuje správnosť, výkon a spracovanie chýb.

**HSTS**
(HTTP Strict Transport Security) bezpečnostný mechanizmus, ktorý núti prehliadače používať HTTPS namiesto HTTP. Pomáha chrániť pred útokmi typu downgrade a cookie hijacking.

**Maintenance mode**
Režim, v ktorom je aplikácia dočasne nedostupná pre používateľov z dôvodu údržby. Tester kontroluje, či sa zobrazuje správna informačná stránka a či sa neodošlú nežiadané požiadavky.

**Fuzzy match**
Metóda porovnávania reťazcov, ktorá umožňuje malé odchýlky (napr. preklepy). Používa sa pri vyhľadávaní alebo kontrole dát, kde sa očakávajú nepresnosti.

**Spätná kompatibilita**
Schopnosť novej verzie systému fungovať s dátami, rozhraniami alebo komponentmi zo starších verzií. V testovaní je kľúčové overiť, že existujúci používatelia nebudú mať problémy.

**UTC**
(Coordinated Universal Time) svetový časový štandard používaný na synchronizáciu systémov. Tester overuje správnu konverziu na lokálny čas a spracovanie časových zón.

**Responzivita**
Schopnosť používateľského rozhrania prispôsobiť sa rôznym veľkostiam obrazovky a zariadeniam. V testovaní sa kontroluje čitateľnosť, dostupnosť funkcií a zachovanie dizajnu.

**Trigger**
Automatická akcia v databáze, ktorá sa spustí pri určitej udalosti (napr. vloženie alebo úprava záznamu). Testuje sa, či vykonáva očakávané operácie bez nežiaducich vedľajších efektov.

**REST API**
(Representational State Transfer API) architektonický štýl pre tvorbu webových služieb. Používa HTTP metódy (GET, POST, PUT, DELETE) a pracuje s dátami vo formátoch ako JSON alebo XML.

**SOAP API**
(Simple Object Access Protocol) protokol pre výmenu dát medzi aplikáciami cez XML. Je prísnejší než REST, často používaný vo firemných systémoch.

**OAuth**
Otvárací štandard pre bezpečnú delegovanú autentifikáciu. Umožňuje používateľovi prihlásiť sa do aplikácie pomocou účtu z inej služby (napr. Google, Facebook) bez zdieľania hesla.

**Deprecated polia**
Polia v API alebo databáze, ktoré sú označené ako zastarané a plánuje sa ich odstránenie. Tester má overiť, že ich odstránenie neovplyvní funkčnosť.

**Screenshot**
Obrázok zachytávajúci aktuálny stav obrazovky alebo aplikácie. Používa sa ako dôkaz pri bug reportoch a dokumentácii testov.

**Layout**
Rozloženie prvkov na obrazovke alebo v dokumente. V testovaní sa kontroluje, či sa prvky zobrazujú správne na rôznych zariadeniach a rozlíšeniach.

**UI**
(User Interface) používateľské rozhranie aplikácie – všetko, s čím používateľ priamo interaguje. Tester overuje funkčnosť, vzhľad a intuitívnosť.

**UX**
(User Experience) celkový zážitok používateľa pri používaní aplikácie. Zahŕňa použiteľnosť, prístupnosť, rýchlosť a spokojnosť používateľa.

**Token**
Bezpečnostný reťazec znakov používaný na autentifikáciu a autorizáciu. Často nahrádza heslá pri komunikácii medzi klientom a serverom.

**Token**
V AI predstavuje token najmenšiu jednotku textu, s ktorou model pracuje – môže to byť celé slovo, časť slova alebo aj interpunkcia. Model rozdeľuje vstupy a výstupy na tokeny, čo ovplyvňuje dĺžku spracovania, cenu a rýchlost́ odpovede. Počet tokenov zároveň určuje, koľko textu model dokáže naraz spracovať.

**Multibyte znaky**
Znaky, ktoré sa ukladajú pomocou viac ako jedného bajtu (napr. á, 😊, 中文). Tester overuje, či aplikácia správne spracuje a zobrazí tieto znaky.

**Forgot password flow**
Proces, ktorým si používateľ obnoví zabudnuté heslo. Tester overuje bezpečnosť, funkčnosť a použiteľnosť tohto postupu.

**MVP**
(Minimum Viable Product) minimálna životaschopná verzia produktu s kľúčovými funkciami. Slúži na rýchle uvedenie na trh a zistenie spätnej väzby.

**MAU**
(Monthly Active Users) metrika počtu jedinečných používateľov, ktorí aplikáciu použili aspoň raz za mesiac. Pomáha sledovať popularitu produktu.

**PaaS**
(Platform as a Service) cloudová služba, ktorá poskytuje vývojové prostredie vrátane infraštruktúry, nástrojov a knižníc. Umožňuje rýchle nasadenie a škálovanie aplikácií.

**SEO**
(Search Engine Optimization) optimalizácia webovej stránky pre vyhľadávače. Tester môže overovať, či sú implementované správne meta tagy, URL a štruktúra obsahu.

**iOS**
Operačný systém od Apple určený pre mobilné zariadenia ako iPhone a iPad. Tester overuje kompatibilitu aplikácie s rôznymi verziami iOS a zariadeniami.

**Android**
Operačný systém od Google pre mobilné zariadenia, používaný širokou škálou výrobcov. Testovanie zahŕňa rôzne verzie systému, nadstavby výrobcov a veľkosti obrazoviek.

**BFF**
(Backend for Frontend) Architektonický vzor, pri ktorom sa vytvára špeciálna backendová vrstva prispôsobená potrebám konkrétneho frontendového klienta. Pomáha optimalizovať dáta a znížiť zložitosť na strane klienta.

**BFF (ohľadne contract testov)**
Backend for Frontend v kontexte contract testovania – testovanie, či API medzi BFF a frontendom spĺňa dohodnuté kontrakty.

**API Gateway**
Služba alebo komponent, ktorý sprostredkováva komunikáciu medzi klientmi a mikroservismi. Poskytuje centralizované riadenie autentifikácie, autorizácie, logovania a limitov požiadaviek.

**Rate-limit**
Mechanizmus obmedzujúci počet požiadaviek, ktoré môže klient odoslať na server v danom časovom intervale. Slúži na ochranu pred zneužitím a preťažením systému.

**ML pipeline**
Sústava krokov na spracovanie dát a trénovanie modelov strojového učenia – od získania dát až po nasadenie modelu. V testovaní sa overuje správnosť jednotlivých fáz a ich integrácia.

**NSFW/duplikáty**
Označenie pre obsah „Not Safe For Work“ (nevhodný do práce) alebo pre detekciu duplicitného obsahu. Používa sa pri filtrovaní a moderovaní dát.

**Funnel**
Model, ktorý znázorňuje, ako používatelia prechádzajú jednotlivými krokmi procesu (napr. nákupný proces). Tester môže sledovať, kde dochádza k odpadnutiu používateľov.

**Cohorty**
Skupiny používateľov rozdelené podľa spoločnej charakteristiky (napr. dátum registrácie) na účely analýzy správania. Pomáhajú pri hodnotení úspešnosti zmien alebo kampaní.

**Elasticsearch**
Vyhľadávací a analytický nástroj založený na Lucene. Používa sa na rýchle fulltextové vyhľadávanie a analýzu veľkých objemov dát.

**OpenSearch**
Open-source vyhľadávací a analytický nástroj, ktorý vznikol ako vetva Elasticsearch. Používa sa na podobné účely – indexovanie a rýchle vyhľadávanie dát.

**Meilisearch**
Ľahký a rýchly open-source vyhľadávací engine s jednoduchou integráciou. Hodí sa pre aplikácie, kde je potrebné rýchle a relevantné vyhľadávanie.

**CDN**
(Content Delivery Network) sieť serverov, ktoré distribuujú obsah bližšie k používateľom podľa ich geografickej polohy. Znižuje latenciu a zlepšuje dostupnosť obsahu.

**Cache feed**
Uložená verzia dátového kanála (feedu), ktorá umožňuje rýchlejšie načítanie obsahu. Tester overuje správnu aktualizáciu cache a jej vyprázdnenie pri zmene obsahu.

**RabbitMQ**
Open-source systém na riadenie správ (message broker), ktorý sprostredkováva komunikáciu medzi rôznymi časťami aplikácie. Tester kontroluje správne odosielanie, prijímanie a spracovanie správ.

**SQS**
(Amazon Simple Queue Service) spravovaná služba od AWS na riadenie front správ medzi aplikáciami. Umožňuje asynchrónnu komunikáciu a škálovanie bez potreby spravovať vlastný message broker.

**Remote config**
Mechanizmus, ktorý umožňuje meniť nastavenia aplikácie na diaľku bez potreby vydania novej verzie. Tester overuje, či sa nové hodnoty správne načítajú a aplikujú.

**LaunchDarkly**
Platforma na správu feature flagov a experimentov. Umožňuje vývojárom nasadzovať a zapínať/vypínať funkcie bez zásahu do kódu.

**Observabilita**
Schopnosť systému poskytovať dostatok informácií (logy, metriky, trasy požiadaviek) na pochopenie jeho stavu a príčin problémov. Tester ju využíva pri analýze chýb a monitorovaní výkonu.

**OIDC**
(OpenID Connect) autentifikačný protokol nad OAuth 2.0, umožňujúci prihlásenie cez externých poskytovateľov identity, ako sú Apple alebo Google.

**Krátke JWT + refresh tokeny v secure úložisku klienta**
(JSON Web Token) implementácia autentifikácie, kde sa používa krátko platný JSON Web Token a dlhšie platný refresh token, uložený bezpečne na strane klienta (napr. Secure Enclave, Keychain).

**Signed URLs pre upload/download médií**
Predpísané (podpísané) URL adresy, ktoré umožňujú dočasný prístup k nahraniu alebo stiahnutiu súboru bez priameho sprístupnenia súboru verejne.

**WAF**
(Web Application Firewall) bezpečnostná vrstva chrániaca webové aplikácie pred útokmi ako SQL injection, XSS či DDoS. Filtruje a blokuje škodlivé požiadavky.

**Mikroslužby (scale-out)**
Architektonický prístup, kde sa aplikácia skladá z viacerých nezávislých služieb. „Scale-out“ znamená horizontálne škálovanie pridaním ďalších inštancií služby.

**JVM**
(Java Virtual Machine) virtuálne prostredie, ktoré spúšťa Java aplikácie a zabezpečuje ich prenositeľnosť medzi platformami.

**Kotlin Multiplatform Mobile (KMM)**
Rámec od JetBrains umožňujúci zdieľanie logiky aplikácie medzi Androidom a iOS-om pri zachovaní natívnych UI.

**SwiftUI Compose bridge**
Prepojenie medzi SwiftUI (Apple) a Jetpack Compose (Google) na zdieľanie alebo premostenie komponentov pri multiplatformovom vývoji.

**NFR**
(Non-Functional Requirements-nefunkčné požiadavky) špecifikácie, ktoré neurčujú funkcie systému, ale jeho kvalitatívne vlastnosti, ako je výkon, bezpečnosť alebo škálovateľnosť.

**Monorepo**
Vývojová stratégia, pri ktorej sa kód viacerých projektov alebo služieb udržiava v jednom spoločnom repozitári.

**Polyrepo**
Opak monorepa – každý projekt alebo služba má vlastný samostatný repozitár. Umožňuje nezávislé riadenie a nasadzovanie.

**SAST**
(Static Application Security Testing) metóda testovania bezpečnosti aplikácie analýzou jej zdrojového kódu alebo binárky bez spustenia. Pomáha odhaliť zraniteľnosti už počas vývoja

**Canary/blue-green nasadenia**
Strategické spôsoby nasadzovania nových verzií aplikácií. Canary nasadenie nasadzuje zmenu najprv malej skupine používateľov, blue-green má dve prostredia, medzi ktorými sa prepína.

**Terraform**
Nástroj na deklaratívnu správu infraštruktúry ako kódu. Umožňuje definovať a automatizovať vytváranie cloudových a on-premise prostredí.

**Vault/SM**
Služby a nástroje na bezpečné ukladanie a správu citlivých údajov (tajomstiev), ako sú heslá, API kľúče či certifikáty.

**Guardrail na postupné rollouty**
Mechanizmus, ktorý zabraňuje rýchlemu alebo nekontrolovanému nasadeniu funkcie všetkým používateľom naraz, aby sa minimalizovalo riziko chýb.

**RPS**
(Requests Per Second) metrika udávajúca, koľko požiadaviek spracuje server za sekundu. Používa sa na hodnotenie výkonu a kapacity systému.

**Cold/warm cache**
Cold cache je prázdna vyrovnávacia pamäť (bez uložených dát), warm cache už obsahuje uložené dáta a poskytuje rýchlejšie odpovede.

**DAST**
(Dynamic Application Security Testing) testovanie bezpečnosti aplikácie počas jej behu. Simuluje útoky z pohľadu útočníka, aby sa identifikovali zraniteľnosti.

**Mobilné MASVS checky**
Kontrolný zoznam Mobile Application Security Verification Standard – slúži na overenie bezpečnostných opatrení mobilných aplikácií.

**MASVS**
(Mobile Application Security Verification Standard) je štandard pre overovanie bezpečnosti mobilných aplikácií. Obsahuje úrovne a kontrolné body, ktoré pomáhajú testerom systematicky hodnotiť bezpečnosť aplikácií.

**ASVS**
(Application Security Verification Standard) je štandard OWASP pre testovanie bezpečnosti webových aplikácií. Poskytuje zoznam požiadaviek a odporúčaní na rôznych úrovniach zabezpečenia.

**Scope creep**
Postupné rozširovanie rozsahu projektu nad pôvodný plán bez adekvátnej úpravy času a zdrojov. V testovaní to môže viesť k nárastu práce a oneskoreniu dodania.

**Nice-to-have**
Požiadavky alebo funkcie, ktoré nie sú nevyhnutné, ale bolo by dobré ich mať. Majú nižšiu prioritu než „must-have“ funkcie.

**Must-have**
označuje funkcie alebo požiadavky, ktoré sú nevyhnutné na správne fungovanie produktu alebo splnenie cieľov projektu. Bez ich implementácie by bol produkt nekompletný alebo nepoužiteľný. V testovaní majú najvyššiu prioritu a ich chýbanie môže zastaviť nasadenie.

**JS/TS doména**
Časť projektu alebo kódu implementovaná v JavaScripte alebo TypeScripte, ktorá má konkrétnu zodpovednosť (napr. správa UI, dátová vrstva).

**SDK**
(Software Development Kit) balík nástrojov, knižníc a dokumentácie na vývoj aplikácií pre konkrétnu platformu alebo službu.

**IDE**
(Integrated Development Environment) integrované vývojové prostredie poskytujúce editor kódu, ladiace nástroje a ďalšie pomôcky na uľahčenie vývoja.

**RPC**
(Remote Procedure Call) je mechanizmus, ktorý umožňuje programu spúšťať funkcie alebo procedúry na inom počítači či serveri, akoby boli lokálne. Skrýva detaily sieťovej komunikácie, takže vývojár pracuje s volaním vzdialených služieb podobne ako s bežnými funkciami v kóde. Používa sa na jednoduchú integráciu distribuovaných systémov.

**gRPC**
Vysokovýkonné, open-source RPC rozhranie od Google založené na HTTP/2 a Protobuf. Používa sa na komunikáciu medzi službami, pričom poskytuje rýchly prenos dát a podporu pre viacero jazykov.

**ACID**
Súbor vlastností databázových transakcií – Atomicita, Konzistencia, Izolácia a Trvácnosť (Durability). Zabezpečujú, že transakcie budú spracované spoľahlivo a predvídateľne.

**MVCC**
(Multi-Version Concurrency Control) mechanizmus riadenia súbehu v databázach, ktorý umožňuje viacerým transakciám čítať dáta bez blokovania zápisov, vďaka čomu sa znižuje riziko konfliktov.

**JSONB**
Dátový typ v PostgreSQL, ktorý umožňuje efektívne ukladanie a vyhľadávanie JSON dát vo formáte binárneho úložiska. Zlepšuje výkon oproti bežnému JSON.

**ORM**
(Object-Relational Mapping) technika, ktorá mapuje objekty v kóde na tabuľky v relačnej databáze. Uľahčuje prácu s databázami bez písania SQL dotazov.

**TypeORM/Prisma**
Moderné ORM nástroje pre JavaScript/TypeScript aplikácie. Umožňujú jednoduchú prácu s databázami a generovanie typovo bezpečných dotazov.

**PITR**
(Point In Time Recovery) proces obnovy databázy do konkrétneho okamihu v minulosti. Používa sa pri haváriách alebo chybách na minimalizáciu straty dát.

**PostgreSQL**
Výkonný open-source relačný databázový systém s podporou rozšírených dátových typov a pokročilých funkcií. Je obľúbený pre svoju stabilitu a flexibilitu.

**MySQL**
Populárny open-source relačný databázový systém. Často používaný v webových aplikáciách, známy pre svoju jednoduchosť a širokú podporu.

**MSSQL**
(Microsoft SQL Server) komerčný relačný databázový systém od Microsoftu. Poskytuje široké možnosti integrácie s produktmi Microsoftu.

**SQL**
(Structured Query Language) štandardizovaný jazyk na správu a manipuláciu s dátami v relačných databázach. Používa sa na vytváranie, čítanie, aktualizáciu a mazanie dát.

**MariaDB**
Open-source vetva MySQL vyvíjaná komunitou, zameraná na vyšší výkon, otvorenosť a kompatibilitu s MySQL.

**CockroachDB**
Distribuovaná SQL databáza odolná voči výpadkom. Navrhnutá na horizontálne škálovanie a automatickú replikáciu dát.

**SQLLite**
Ľahká embedded SQL databáza uložená v jednom súbore. Nepotrebuje samostatný server, často používaná v mobilných a desktopových aplikáciách.

**SQLAlchemy**
Populárna Python knižnica na ORM a prácu s databázami. Poskytuje vysokú flexibilitu pri tvorbe dotazov a správe schém.

**Kafka**
Distribuovaná platforma na spracovanie prúdových dát v reálnom čase. Umožňuje publikovať, odoberať a uchovávať veľké objemy správ s vysokou priepustnosťou a nízkou latenciou.

**Tosca**
Nástroj na automatizované testovanie podnikových aplikácií, známy pre modelovo-riadený prístup. Umožňuje testovať webové, desktopové, mobilné aj API rozhrania bez potreby rozsiahleho programovania.

**Jira**
Populárny nástroj na riadenie projektov a sledovanie chýb. Používa sa na plánovanie úloh, sledovanie progresu a komunikáciu v tíme, často v spojení s metodikami Agile/Scrum.

**Xray**
Rozšírenie pre Jira (platené) určené na správu testov a testovacích cyklov. Umožňuje prepojiť požiadavky, testovacie prípady, výsledky testov a reportovanie.

**AWS**
(Amazon Web Services) cloudová platforma poskytujúca širokú škálu služieb – od výpočtových kapacít cez databázy až po AI/ML nástroje. Používa sa na nasadzovanie a prevádzku aplikácií v cloude.

**Microsoft Azzure**
Cloudová platforma od Microsoftu poskytujúca infraštruktúru, platformu aj softvérové služby. Podporuje integráciu s produktmi Microsoftu a hybridné riešenia.

**Thumbnail**
Zmenšená verzia obrázka alebo videa, používaná ako náhľad. V testovaní sa overuje kvalita, rozmery a správne načítanie v rôznych zariadeniach.

**NSFW klasifikátor**
Algoritmus na detekciu obsahu „Not Safe For Work“ (nevhodného na pracovisku), ako je napríklad nahota alebo násilie. Používa sa na filtrovanie alebo označovanie obsahu.

**AWS Cognito**
Služba od AWS na správu používateľských účtov, autentifikácie a autorizácie. Podporuje registráciu, prihlásenie aj viacfaktorové overenie.

**Ory/Keycloak (self-host)**
Open-source riešenia na správu identít a prístupov, ktoré si organizácia môže prevádzkovať vo vlastnej infraštruktúre. Podporujú OIDC, OAuth2 a ďalšie štandardy.

**Sociálne prihlásenia**
Možnosť prihlásiť sa do aplikácie pomocou účtu z inej služby (napr. Facebook, Google, LinkedIn). Zjednodušuje registráciu, no vyžaduje správne zabezpečenie.

**Active Directory**
(AD) je adresárová služba od Microsoftu na správu používateľov, skupín, počítačov a ďalších zdrojov v rámci siete organizácie. Umožňuje centralizovanú autentifikáciu a autorizáciu, často v kombinácii so Single Sign-On (SSO), aby sa používatelia po prihlásení do domény mohli automaticky dostať aj k ďalším interným službám. Používa sa najmä vo firemných a školských prostrediach.

**Docker**
Platforma na tvorbu, distribúciu a spúšťanie aplikácií v kontajneroch. Kontajnery izolujú aplikáciu a jej závislosti, čo uľahčuje nasadzovanie a škálovanie.

**GitHub**
Online platforma na správu kódu a verzií pomocou Git. Ponúka nástroje na spoluprácu, správu projektov, CI/CD a bezpečnostné funkcie.

**GitLab**
Platforma na správu kódu a DevOps procesov. Okrem Git repozitára obsahuje nástroje na plánovanie, CI/CD, monitoring a bezpečnostné analýzy.

**Bitbucket**
Platforma od Atlassianu na správu Git repozitárov, úzko integrovaná s nástrojmi Jira, Confluence a Trello. Podporuje súkromné aj verejné repozitáre a ponúka zabudovaný CI/CD systém Bitbucket Pipelines.

**Azure DevOps Repos**
Súčasť balíka Azure DevOps od Microsoftu, poskytuje Git repozitáre aj nástroje na riadenie projektov, testovanie a CI/CD. Je silno prepojená s ďalšími službami Azure a vhodná pre enterprise prostredia.

**AWS CodeCommit**
Plne spravovaná cloudová služba od Amazonu na hosťovanie súkromných Git repozitárov. Ponúka vysokú bezpečnosť, škálovateľnosť a integráciu s ďalšími AWS službami, ako sú CodeBuild či CodePipeline.

**SourceForge**
Jedna z najstarších platforiem na hostovanie open-source projektov, podporuje Git, SVN aj Mercurial. Poskytuje úložisko kódu, správu chýb, diskusné fóra a distribúciu binárnych súborov.

**Gitea**
Ľahká a rýchla open-source platforma na správu Git repozitárov, ktorú si môžeš prevádzkovať sama. Ponúka webové rozhranie, správu úloh a jednoduché CI integrácie.

**Gogs**
Minimalistická open-source Git platforma navrhnutá na nízku spotrebu zdrojov a jednoduchú inštaláciu. Vhodná pre malé tímy alebo projekty, ktoré potrebujú základné funkcie Git servera.

**Phabricator**
Open-source balík nástrojov od Facebooku na správu kódu, úloh a dokumentácie. Hoci jeho vývoj bol ukončený, stále sa používa v niektorých organizáciách, ktoré si ho prevádzkujú samostatne.

**Assembla**
Platforma zameraná na komerčné tímy, podporuje Git, Subversion (SVN) a Perforce. Ponúka hostovanie kódu, správu úloh a nástroje pre spoluprácu, vhodné pre väčšie vývojové tímy.

**Grafana**
Open-source platforma na vizualizáciu a monitoring dát z rôznych zdrojov (databázy, metriky, logy). Umožňuje vytvárať interaktívne dashboardy, ktoré pomáhajú pri sledovaní výkonu aplikácií a infraštruktúry.

**GDPR**
(General Data Protection Regulation) nariadenie Európskej únie o ochrane osobných údajov. Stanovuje pravidlá pre spracovanie, ukladanie a zdieľanie osobných údajov občanov EÚ.

**AI Act**
Pripravované nariadenie EÚ, ktoré má regulovať používanie umelej inteligencie. Zameriava sa na bezpečnosť, transparentnosť a zodpovednosť pri vývoji a nasadzovaní AI systémov.

**WCAG**
(Web Content Accessibility Guidelines) súbor odporúčaní na zlepšenie prístupnosti webového obsahu pre osoby so zdravotným znevýhodnením. Stanovuje zásady, ako má byť obsah vnímateľný, ovládateľný, zrozumiteľný a robustný.

**EAA**
(European Accessibility Act) európska smernica, ktorá stanovuje požiadavky na prístupnosť produktov a služieb pre osoby so zdravotným postihnutím. Platí pre rôzne odvetvia, vrátane IT a e-commerce.

**Izolácia tajomstiev**
(Secrets Manager/Vault) mechanizmus na bezpečné ukladanie a správu citlivých údajov, ako sú API kľúče, heslá a certifikáty. Zabraňuje ich úniku a umožňuje riadiť prístup len oprávneným používateľom alebo službám.

**TypeScript**
Programovací jazyk nadstavujúci JavaScript o statické typovanie. Pomáha predchádzať chybám počas vývoja a uľahčuje udržiavateľnosť kódu vo väčších projektoch.

**Python**
Vysokoúrovňový, interpretovaný programovací jazyk známy pre svoju jednoduchosť a čitateľnosť. Používa sa na webový vývoj, analýzu dát, strojové učenie aj automatizáciu.

**Java**
Objektovo orientovaný programovací jazyk navrhnutý na prenositeľnosť medzi platformami. Využíva sa pri vývoji enterprise aplikácií, mobilných aplikácií (Android) a backend systémov.

**JavaScript**
Skriptovací jazyk používaný primárne na tvorbu interaktívneho obsahu na webových stránkach. Spúšťa sa v prehliadači aj na serveri (Node.js).

**Ruby**
Dynamický, interpretovaný programovací jazyk známy pre svoju jednoduchosť a produktivitu. Často sa používa s frameworkom Ruby on Rails na vývoj webových aplikácií.

**C**
Jazyk nižšej úrovne vhodný na systémové programovanie a vývoj aplikácií s vysokou výkonnosťou. Mnohé moderné jazyky (napr. C++, Java) z neho čerpajú základy.

**C++**
Rozšírenie jazyka C o objektovo orientované prvky. Používa sa na vývoj softvéru s vysokými nárokmi na výkon, ako sú hry alebo embedded systémy.

**C#**
Programovací jazyk od Microsoftu, ktorý kombinuje jednoduchosť C a C++ s modernými funkciami. Často sa používa v .NET prostredí na vývoj webových, desktopových a mobilných aplikácií.

**Asembler**
Nízkoúrovňový jazyk, ktorý priamo zodpovedá inštrukciám procesora. Používa sa na vývoj systémového softvéru a optimalizáciu výkonu na hardvérovej úrovni.

**Golang (Go)**
Moderný, kompilovaný programovací jazyk vyvinutý v Google, známy pre svoju jednoduchosť, rýchle kompilácie a podporu paralelizmu cez gorutiny. Používa sa na vývoj backendových služieb, cloudovej infraštruktúry a nástrojov.

**MS-DOS**
(Microsoft Disk Operating System) starší operačný systém s textovým rozhraním, používaný najmä v 80. a 90. rokoch. Slúžil ako základ pre spúšťanie aplikácií pred nástupom grafických systémov ako Windows.

**Basic**
(Beginner’s All-purpose Symbolic Instruction Code) jednoduchý programovací jazyk navrhnutý na výučbu programovania. V minulosti často používaný na domácich počítačoch v 80. rokoch.

**Rust**
Moderný programovací jazyk zameraný na výkon, bezpečnosť pamäte a prevenciu chýb pri súbežnom spracovaní. Vhodný na systémové programovanie aj webové aplikácie.

**Fortran**
(Formula Translation) jeden z najstarších programovacích jazykov, stále používaný v oblasti vedeckých a numerických výpočtov. Známy pre vysoký výkon pri práci s číselnými dátami.

**COBOL**
(Common Business-Oriented Language) programovací jazyk navrhnutý pre obchodné aplikácie a spracovanie veľkých objemov dát. Dodnes používaný v bankových a poisťovacích systémoch.

**Pascal**
Programovací jazyk vytvorený na výučbu štruktúrovaného programovania. V minulosti sa používal aj na vývoj desktopových aplikácií.

**PHP**
(PHP: Hypertext Preprocessor) skriptovací jazyk určený na tvorbu dynamických webových stránok a backendových aplikácií. Beží na strane servera a často sa kombinuje s databázami ako MySQL.

**Podpora ICU kolácií**
Možnosť databázy alebo aplikácie používať ICU (International Components for Unicode) na správne triedenie a porovnávanie textu podľa jazykových pravidiel. Je dôležité pri práci s viacerými jazykmi a znakmi.

**YugabyteDB**
Distribuovaná SQL databáza s kompatibilitou s PostgreSQL a Cassandra API. Navrhnutá na vysokú dostupnosť, horizontálne škálovanie a prácu v cloude.

**MongoDB**
Dokumentovo orientovaná NoSQL databáza, ktorá ukladá dáta vo formáte podobnom JSON. Vhodná na flexibilné schémy a rýchly vývoj aplikácií.

**DynamoDB**
Plne spravovaná NoSQL databáza od AWS optimalizovaná na rýchlosť a škálovanie. Podporuje kľúčovo-hodnotové aj dokumentové úložisko.

**Neo4j**
Grafová databáza optimalizovaná na ukladanie a dotazovanie vzťahov medzi entitami. Používa sa v odporúčacích systémoch, sieťových analýzach a detekcii podvodov.

**ClickHouse**
Rýchla open-source analytická databáza pre spracovanie veľkých objemov dát v reálnom čase. Vhodná na OLAP dotazy a business intelligence.

**Stemming**
Technika spracovania textu, pri ktorej sa slová redukujú na ich kmeň (napr. „bežal“ → „bež“). Používa sa vo vyhľadávačoch a NLP na zlepšenie zhody výsledkov.

**Syntetické TPS grafy**
Vizualizácie zobrazujúce počet transakcií za sekundu (Transactions Per Second) vytvorených umelo, napr. simuláciou záťaže. Slúžia na testovanie výkonu systému bez použitia reálnych dát. Tester sleduje tvary kriviek, výkyvy a limity systému.

**Anti-abuse**
Opatrenia a mechanizmy na ochranu systému pred zneužitím, ako sú spam, podvodné registrácie či automatizované útoky. Môžu zahŕňať detekciu anomálií, blokovanie IP alebo obmedzovanie rýchlosti požiadaviek.

**Bayesovou korekciou**
Štatistická metóda úpravy výsledkov (napr. hodnotenia) na základe Bayesovej pravdepodobnosti. Pomáha znížiť vplyv malých vzoriek – napr. nová položka s jedným 5★ hodnotením nebude hneď na vrchole rebríčka.

**Wilsonovo skóre**
Výpočet intervalov spoľahlivosti pre podiely, napr. pre percento pozitívnych hodnotení. Používa sa na spravodlivejšie zoradenie položiek pri nerovnakom počte hodnotení.

**Shadow-ban**
Tichý zákaz, pri ktorom používateľ stále vidí svoj obsah, ale iní ho nevidia. Slúži na potlačenie škodlivého správania bez upozornenia pôvodcu.

**Decay**
Mechanizmus postupného znižovania váhy starších dát alebo hodnotení. Umožňuje algoritmom preferovať novšie a relevantnejšie informácie.

**Idempotentnosť**
Vlastnosť operácie, pri ktorej jej opakované vykonanie vedie k rovnakému výsledku ako prvé vykonanie. Dôležitá pri API, aby nedošlo k duplicitám (napr. opakovaná platba).

**Re-compute job po batchi zmien**
Úloha, ktorá sa spustí po hromadnej zmene dát a znovu prepočíta odvodené hodnoty alebo agregáty. Tester overuje, že výpočty prebehli správne a sú aktuálne.

**DAU**
(Daily Active Users) – počet unikátnych používateľov, ktorí použili aplikáciu aspoň raz za deň. Sleduje sa ako metrika zapojenia a rastu.

**Survivorship bias**
Kognitívne skreslenie, keď vyhodnocujeme len „preživšie“ prípady a ignorujeme tie, ktoré zlyhali. V testovaní môže viesť k nesprávnym záverom, ak analyzujeme len úspešné scenáre.

**Redis cache agregátov**
Ukladanie vypočítaných agregovaných hodnôt (napr. počtu lajkov) v Redis databáze pre rýchly prístup. Tester sleduje, či sa cache aktualizuje pri zmene dát.

**Antimissuse**
Opatrenia proti nesprávnemu použitiu systému, aj keď nejde o úmyselné zneužitie. Môže zahŕňať ochranu pred chybnými vstupmi, neštandardnými požiadavkami alebo nadmerným zaťažením.

**Facetové štatistiky**
Rozdelenie dát podľa kategórií alebo filtrov (facets) – napr. počet produktov podľa značky, farby či ceny. Tester overuje správnosť počtov a reakcie na kombinácie filtrov.

**E2E testy**
(End-to-End) testy, ktoré overujú celú cestu používateľa alebo procesu od začiatku po koniec, vrátane všetkých integrovaných komponentov. Cieľom je simulovať reálne použitie.

**Managed IdP**
(Managed Identity Provider) – služba tretej strany, ktorá spravuje autentifikáciu a identitu používateľov. Umožňuje organizáciám využiť cloudové riešenia namiesto vlastnej infraštruktúry na správu účtov a prístupov.

**Rotácia signing keys v IdP**
Pravidelná výmena podpisových kľúčov v poskytovateľovi identity na zvýšenie bezpečnosti. Zabraňuje zneužitiu kompromitovaných kľúčov.

**Authorization Code Flow**
Autentifikačný tok používaný v OAuth 2.0, pri ktorom klient najprv získa autorizačný kód a až následne ho vymení za prístupový token. Zvyšuje bezpečnosť, pretože token sa neposiela cez prehliadač používateľa.

**PKCE (S256)**
(Proof Key for Code Exchange) je rozšírenie OAuth 2.0 na bezpečnejšie získanie prístupového tokenu v klientskej aplikácii. Metóda S256 využíva SHA-256 hashovanie pre overenie výmeny kódu.

**URI**
(Uniform Resource Identifier) je reťazec, ktorý jednoznačne identifikuje zdroj na internete alebo v systéme. Môže byť vo forme URL (adresy) alebo URN (názvu zdroja).

**URN**
(Uniform Resource Name) je typ URI, ktorý slúži na jednoznačnú identifikáciu zdroja podľa názvu, nie podľa jeho umiestnenia. Na rozdiel od URL neobsahuje informáciu o tom, kde sa zdroj nachádza, ale len jeho trvalý identifikátor.

**Bearer access token**
Typ prístupového tokenu, ktorý poskytuje držiteľovi („bearerovi“) plný prístup k zdrojom, na ktoré bol vydaný. Musí byť chránený, pretože ktokoľvek s tokenom môže získať prístup.

**Hash RT**
Hashovanie refresh tokenu pred uložením do databázy na ochranu pred jeho zneužitím. Aj keby databáza unikla, útočník nedostane platný token.

**Passwordless**
Metóda prihlasovania, ktorá nevyžaduje heslo, ale používa alternatívne mechanizmy ako e-mailové odkazy alebo biometrické overenie. Znižuje riziko odcudzenia hesiel.

**Magic link**
Prihlasovací odkaz zaslaný používateľovi (napr. e-mailom), po kliknutí na ktorý sa okamžite prihlási. Jednoduché na použitie, ale časovo obmedzené kvôli bezpečnosti.

**Passkeys**
Moderná náhrada hesiel založená na kryptografických kľúčoch uložených v zariadení používateľa. Umožňuje bezpečné a rýchle prihlásenie bez zadávania hesla.

**Argon2id**
Pokročilá hashovacia funkcia pre heslá, odolná voči útokom hrubou silou aj útokom pomocou GPU. Kombinuje vlastnosti algoritmov Argon2i a Argon2d.

**Bcrypt s costom**
Hashovacia funkcia pre heslá, pri ktorej parameter „cost“ určuje náročnosť výpočtu. Vyšší cost zvyšuje bezpečnosť, ale aj čas spracovania.

**Unikátne salting**
Pridanie náhodnej hodnoty (saltu) ku každému heslu pred jeho hashovaním, aby sa zabránilo útokom s rainbow tabuľkami. Každý používateľ má vlastný unikátny salt.

**Rainbow tabuľky**
Predvypočítané tabuľky hashov pre veľké množstvo možných hesiel, používané na rýchle prelomenie hashovaných údajov. Útoky s rainbow tabuľkami sa dajú efektívne zmierniť použitím saltovania pri hashovaní hesiel.

**Minimá + haveibeenpwned kontrola reťazcov**
Overenie, či heslo spĺňa minimálne požiadavky na dĺžku a komplexitu, doplnené o kontrolu proti databáze uniknutých hesiel služby haveibeenpwned. Zvyšuje to odolnosť voči opätovnému použitiu kompromitovaných hesiel.

**MFA**
(Multi-Factor Authentication) je viacfaktorová autentifikácia vyžadujúca kombináciu aspoň dvoch rôznych overovacích faktorov. Zvyšuje bezpečnosť prístupu k účtom.

**TOTP**
(Time-based One-Time Password) je jednorazové heslo generované na základe času a zdieľaného tajomstva. Používa sa najmä v aplikáciách pre dvojfaktorovú autentifikáciu.

**WebAuthn**
(Web Authentication) je webový štandard pre bezheslové prihlasovanie pomocou verejnej kryptografie. Umožňuje overenie pomocou biometriky, bezpečnostných kľúčov alebo zariadení.

**RBAC**
(Role-Based Access Control) je model riadenia prístupu, kde sa oprávnenia prideľujú podľa role používateľa. Zjednodušuje správu prístupov a znižuje riziko neoprávneného prístupu.

**ABAC**
(Attribute-Based Access Control) je model riadenia prístupu, ktorý rozhoduje na základe atribútov používateľa, zdroja a kontextu. Umožňuje jemnejšie nastavenie pravidiel než RBAC.

**Claimy do access tokenu**
Dáta (claimy) vložené do prístupového tokenu, ktoré obsahujú informácie o používateľovi alebo relácii. Používajú sa na autorizáciu a overovanie požiadaviek.

**Exponenciálny backoff**
Technika riadenia opakovaných pokusov o spojenie, pri ktorej sa interval medzi pokusmi postupne zvyšuje. Znižuje zaťaženie systému pri dočasných problémoch.

**IP allow/deny list pre admin endpoints**
Bezpečnostné opatrenie, ktoré povoľuje alebo blokuje prístup k administrátorskym rozhraniam podľa IP adries. Pomáha obmedziť prístup len na dôveryhodné adresy.

**PII**
(Personally Identifiable Information) sú údaje, ktoré môžu identifikovať konkrétnu osobu. Zahŕňajú napríklad meno, adresu, rodné číslo alebo e-mail.

**JWKS podpisu**
(JSON Web Key Set) je formát na distribúciu verejných kľúčov používaných na overenie podpisu tokenov. Umožňuje klientom automaticky získavať aktuálne kľúče od servera.

**Bruteforce scenáre**
Útoky, pri ktorých útočník systematicky skúša rôzne kombinácie prihlasovacích údajov, kým nenájde správnu. Testovanie zahŕňa overenie, či systém takéto pokusy deteguje a blokuje.

**CSRF**
(Cross-Site Request Forgery) je útok, pri ktorom útočník prinúti používateľa vykonať nechcenú akciu na webovej aplikácii, kde je prihlásený. Prevencia zahŕňa kontrolu tokenov a pôvodu požiadaviek.

**SSRF/redirect hijack**
(Server-Side Request Forgery) je útok, pri ktorom útočník prinúti server vykonať požiadavku na iný server. Redirect hijack zneužíva presmerovania na získanie citlivých údajov alebo presmerovanie používateľa.

**Pre-podpísané URL**
Odkaz s dočasnou platnosťou, ktorý umožňuje prístup k súboru alebo zdroju bez ďalšieho overovania. Používa sa napríklad na bezpečné zdieľanie súborov v cloude.

**MIME**
(Multipurpose Internet Mail Extensions) je štandard, ktorý určuje typ obsahu súborov prenášaných cez internet. Pomáha klientom správne interpretovať text, obrázky, video alebo iné dáta.

**POP3**
(Post Office Protocol version 3) je protokol na sťahovanie e-mailov zo servera do poštového klienta. Správy sa zvyčajne po stiahnutí zo servera odstránia, čo šetrí miesto na serveri.

**IMAP**
(Internet Message Access Protocol) je protokol na prácu s e-mailami priamo na serveri. Umožňuje synchronizáciu priečinkov a správ medzi viacerými zariadeniami bez nutnosti sťahovať ich lokálne.

**Pipeline**
Sekvencia krokov, cez ktoré prechádzajú dáta alebo kód od vstupu po výsledok. V softvérovom vývoji sa používa na automatizáciu buildov, testovania a nasadzovania.

**EXIF**
(Exchangeable Image File Format) je dátový formát pre ukladanie metadát v obrázkoch, napríklad dátum, čas alebo GPS súradnice. Často sa používa pri digitálnej fotografii.

**HEIC**
(High Efficiency Image Coding) je moderný formát obrázkov založený na kodeku HEVC, ktorý ponúka vysokú kvalitu pri menšej veľkosti súboru. Bežne sa používa v zariadeniach Apple.

**AVIF/WebP**
Formáty obrázkov optimalizované pre web, ktoré poskytujú menšiu veľkosť súboru pri zachovaní kvality. AVIF využíva kodek AV1, WebP vyvinul Google pre rýchlejšie načítanie webu.

**JPEG**
(Bežne Joint Photographic Experts Group) je rozšírený formát kompresie obrázkov s miernou stratou kvality. Je vhodný na fotografie, ale menej na obrázky s ostrými hranami.
AV sken
Antivírusová kontrola súborov alebo systémov na prítomnosť škodlivého kódu. Môže byť vykonaná manuálne alebo automaticky v rámci bezpečnostných nástrojov.

**ClamAV**
Open-source antivírusový program určený na detekciu trójskych koní, vírusov a iného malvéru. Často sa používa na serveroch a v e-mailových bránach.

**Managed AV**
Antivírusová ochrana poskytovaná a spravovaná treťou stranou. Umožňuje organizáciám outsourcovať správu bezpečnostného softvéru a jeho aktualizácií.

**pHash**
(Perceptual Hash) je metóda hashovania, ktorá vytvára odtlačok obrázka podľa jeho vizuálnych vlastností. Umožňuje porovnávať obrázky aj pri malých zmenách, napríklad pri zmene veľkosti.

**Vendor lock-in**
Situácia, keď je zákazník závislý na jednom dodávateľovi technológie alebo služby a prechod ku konkurencii je nákladný alebo zložitý. Znižuje flexibilitu a môže zvyšovať náklady.

**Smart crop**
Automatické orezanie obrázka tak, aby sa zachovala najdôležitejšia časť. Využíva analýzu obsahu, napríklad detekciu tvárí alebo objektov.

**DPA**
(Data Processing Agreement) je zmluva medzi prevádzkovateľom a spracovateľom údajov, ktorá definuje podmienky spracúvania osobných údajov. Je požadovaná legislatívou, napríklad GDPR.

**GPS**
(Global Positioning System) je satelitný navigačný systém umožňujúci určenie polohy kdekoľvek na Zemi. Používa sa v navigácii, lokalizačných službách a sledovaní zariadení.

**SSIM/PSNR**
(Structural Similarity Index / Peak Signal-to-Noise Ratio) sú metriky na hodnotenie kvality obrázka po kompresii alebo spracovaní. SSIM sa zameriava na vizuálnu podobnosť, PSNR na pomer signálu k šumu.

**Metadáta**
Údaje o iných údajoch, ktoré opisujú obsah, pôvod, štruktúru alebo formát dátového súboru. Využívajú sa napríklad na vyhľadávanie, organizáciu alebo správu obsahu.

**Malvér**
(Škodlivý softvér) je softvér navrhnutý s cieľom poškodiť, zneužiť alebo neoprávnene získať prístup k systémom či dátam. Patrí sem napríklad vírus, trójsky kôň, ransomware alebo spyware.

**SLA**
(Service Level Agreement) je zmluvná dohoda medzi poskytovateľom služby a zákazníkom, ktorá stanovuje úroveň poskytovaných služieb. Obsahuje metriky, ako napríklad dostupnosť, čas odozvy a sankcie pri nedodržaní.

**MD** 
(man day) Jednotka odhadu práce vyjadrujúca množstvo práce, ktoré vykoná jedna osoba za jeden pracovný deň. Používa sa pri plánovaní projektov a odhadovaní nákladov.

**NDA**
(Non-Disclosure Agreement) je dohoda o mlčanlivosti, ktorá zaväzuje strany zachovať dôverné informácie v tajnosti. Často sa podpisuje pred začiatkom spolupráce alebo výmenou citlivých údajov.

**PM**
(Project Manager) projektový manažér zodpovedný za plánovanie, koordináciu a riadenie projektu. Sleduje časový harmonogram, rozpočet, kvalitu a komunikáciu medzi členmi tímu a zainteresovanými stranami.

**BA** 
(Business Analyst) business analytik je zodpovedný za zber, analýzu a dokumentovanie požiadaviek od zainteresovaných strán. Prekladá obchodné potreby do technických špecifikácií pre vývojový tím a pomáha zabezpečiť, aby výsledné riešenie spĺňalo očakávania.

**QA**
(Quality Assurance) špecialista na zabezpečenie kvality má na starosti procesy, ktoré zaručujú, že produkt spĺňa stanovené štandardy kvality. Zahŕňa to tvorbu testovacích plánov, vykonávanie testov a reportovanie chýb.
DEV (Developer)
Vývojár je zodpovedný za návrh, implementáciu a údržbu softvéru. Pracuje s rôznymi programovacími jazykmi a technológiami s cieľom vytvoriť funkčné a efektívne riešenia.

**UX**
(User Experience Designer) dizajnér používateľskej skúsenosti sa zameriava na návrh rozhraní a interakcií, ktoré sú intuitívne a príjemné pre používateľa. Využíva výskum, testovanie a prototypovanie na optimalizáciu zážitku z používania produktu.

**DBA**
(Database Administrator) databázový administrátor je zodpovedný za správu, údržbu a optimalizáciu databáz. Zabezpečuje dostupnosť, bezpečnosť a výkon databázových systémov a vykonáva zálohovanie a obnovu dát.

**KPI**
(Key Performance Indicator) je kľúčový ukazovateľ výkonnosti používaný na meranie úspešnosti procesov alebo projektov. Pomáha sledovať pokrok voči stanoveným cieľom a identifikovať oblasti na zlepšenie.

**ROI**
(Return on Investment) je ukazovateľ, ktorý vyjadruje ziskovosť investície. Vypočíta sa ako pomer čistého zisku k investovaným nákladom a používa sa na hodnotenie efektívnosti projektov.

**Item-to-item**
Metóda odporúčacích systémov, ktorá vyhľadáva podobné položky na základe histórie správania používateľov. Často sa využíva v e-shopoch a streamingových službách.

**Save-rate@K**
Metrika vyjadrujúca percento položiek z odporúčacieho zoznamu dĺžky K, ktoré si používateľ uloží na neskoršie použitie. Hodí sa na meranie užitočnosti odporúčaní.

**CTR@K**
(Click-Through Rate) pri K odporúčaných položkách udáva percento kliknutí na položky zo zoznamu. Používa sa na hodnotenie atraktívnosti odporúčaní.

**Cook-proxy@K**
Špecifická metrika alebo mechanizmus proxy merania v odporúčacom systéme, ktorý sa aplikuje na K návrhov. Slúži na testovanie výkonu algoritmov nepriamo cez náhradné ukazovatele.

**Churn guardrails**
Opatrenia a metriky, ktoré bránia prudkému poklesu aktívnych používateľov (tzv. odlivu). Pomáhajú udržať stabilitu používateľskej základne pri zavádzaní zmien.

**Precision@K**
Metrika presnosti odporúčaní – vyjadruje podiel relevantných položiek medzi prvými K odporúčaniami. Vhodná na hodnotenie kvality návrhov.

**Recall@K**
Vyjadruje, akú časť zo všetkých relevantných položiek sa podarilo odporučiť medzi prvými K výsledkami. Dôležitá pre systémy, kde je prioritou úplnosť odporúčaní.

**nDCG@K**
(Normalized Discounted Cumulative Gain) je metrika hodnotiaca kvalitu zoradených odporúčaní, pričom zohľadňuje pozíciu relevantných položiek v zozname. Normalizácia umožňuje porovnanie medzi rôznymi zoznamami.

**Coverage**
Pokrytie – vyjadruje, akú časť dostupných položiek systém vôbec odporučí. Vyššie pokrytie znamená, že odporúčací systém ponúka väčšiu rozmanitosť.

**Intra-List Diversity (ILD) a novelty**
ILD meria rôznorodosť položiek v zozname odporúčaní, zatiaľ čo novelty hodnotí, do akej miery sú položky pre používateľa nové alebo neznáme. Obe metriky prispievajú k lepšej používateľskej skúsenosti.

**Latency P95**
Meria čas odozvy systému, pod ktorý sa zmestí 95 % všetkých požiadaviek. Používa sa na hodnotenie rýchlosti a konzistencie systému.

**Serendipity proxy**
Metrika alebo mechanizmus na meranie prekvapivosti a príjemnej neočakávanosti odporúčaní. Pomáha odlíšiť systém, ktorý neponúka len očakávané položky.

**Popularity-bias index**
Index merajúci, do akej miery odporúčací systém uprednostňuje populárne položky pred menej známymi. Vysoká hodnota môže signalizovať nedostatok diverzity odporúčaní.

**Temporal split**
Metóda delenia dát na trénovacie a testovacie časti na základe času. Používa sa najmä pri modeloch, kde poradie udalostí zohráva významnú úlohu.

**Golden set párov**
Súbor referenčných alebo „zlatých“ dát použitých na porovnanie a validáciu modelov či algoritmov. Slúži ako etalón, voči ktorému sa meria presnosť alebo výkon systému.

**Skóre cosine embeddings**
Metrika založená na kosínovej podobnosti, ktorá vyjadruje, ako sú si dva vektorové reprezentácie (embeddings) podobné. Hodnota blízka 1 znamená vysokú podobnosť.

**TF-IDF/Jaccard**
TF-IDF je metóda váženia slov podľa ich frekvencie v dokumente a zriedkavosti v celom korpuse. Jaccardov index meria podobnosť množín na základe prieniku a zjednotenia prvkov.

**Top-K**
Označuje výber K najlepších alebo najrelevantnejších položiek podľa určitého hodnotenia. Bežne sa používa v odporúčacích systémoch a vyhľadávaní.

**Cold-start item**
Situácia, keď systém má odporučiť novú položku bez dostatočných historických dát. Vyžaduje špeciálne metódy, ako napríklad využitie metadát.

**Cold-start user**
Podobne ako cold-start item, ide o nového používateľa bez histórie správania. Systém mu môže odporúčať na základe všeobecných trendov alebo dotazníkov.

**ILD**
(Intra-List Diversity) meria rozmanitosť položiek v zozname odporúčaní. Vyššia hodnota ILD znamená, že zoznam obsahuje rôznorodé položky.

**Popularity-penalty**
Technika, ktorá znižuje váhu príliš populárnych položiek v odporúčaniach. Cieľom je podporiť diverzitu a objavovanie nových možností.

**Ablácie**
Testovacia metóda, pri ktorej sa zámerne odstraňujú alebo menia časti modelu či systému, aby sa zistil ich vplyv na výsledok. Pomáha odhaliť dôležitosť jednotlivých komponentov.

**IPS/DR**
(Inverse Propensity Scoring / Doubly Robust) sú štatistické metódy používané na vyhodnocovanie odporúčacích systémov z neúplných dát. Pomáhajú eliminovať skreslenie pri hodnotení.

**Team-Draft Interleaving**
Technika porovnávania dvoch vyhľadávacích alebo odporúčacích algoritmov tak, že sa ich výsledky striedavo miešajú do jedného zoznamu. Používatelia interagujú s týmto zoznamom a ich správanie sa vyhodnocuje.

**Save-rate@K**
Percento položiek z odporúčaného zoznamu dĺžky K, ktoré si používateľ uloží. Používa sa na meranie užitočnosti odporúčaní.

**Guardrails**
Bezpečnostné a kontrolné mechanizmy, ktoré zabraňujú nežiaducemu alebo riskantnému správaniu systému. Môžu byť implementované v kóde alebo v procesoch.

**CUPED**
(Control Using Pre-Experiment Data) je štatistická metóda znižovania variability výsledkov experimentu. Využíva historické dáta na presnejšie odhady efektu.

**p-hacking**
Praktika manipulácie s experimentálnymi alebo štatistickými postupmi tak, aby výsledky vyšli štatisticky významné. Považuje sa za neetické a vedie k nespoľahlivým záverom.

**Simpsonov paradox**
Štatistický jav, pri ktorom sa trend pozorovaný v jednotlivých skupinách môže po ich spojení zmeniť alebo úplne zmiznúť. Poukazuje na dôležitosť správneho rozdelenia a interpretácie dát.

**Shilling útoky**
Úmyselné manipulácie s odporúčacím systémom pomocou falošných recenzií alebo hodnotení s cieľom zvýšiť či znížiť popularitu konkrétnych položiek. Používa sa v konkurenčnom boji alebo pri propagácii vlastných produktov.

**Trust score**
Metrika hodnotiaca dôveryhodnosť používateľa, zariadenia alebo transakcie. Zohľadňuje históriu správania, geolokáciu, reputáciu a ďalšie signály.

**Low-data mód**
Režim aplikácie, ktorý minimalizuje prenos dát a využíva menej náročné zdroje. Je určený pre pomalé alebo drahé internetové pripojenie.

**BlurHash/ThumbHash**
Algoritmy na generovanie malých vizuálnych náhľadov obrázkov v podobe farebných vzorov alebo rozmazaných blokov. Slúžia na rýchle načítanie náhľadu ešte pred stiahnutím originálneho obrázka.

**Lazy loading**
Technika načítavania obsahu až v momente, keď je potrebný, napríklad pri zobrazení na obrazovke. Znižuje čas načítania stránky a šetrí zdroje.

**TTFR**
(Time To First Render) meria čas od začiatku načítania stránky alebo aplikácie po prvé zobrazenie obsahu. Je kľúčovým ukazovateľom rýchlosti a používateľského komfortu.

**Error budget**
Povolená miera chýb alebo výpadkov, ktorú si tím stanoví bez porušenia dohodnutých úrovní služieb (SLA). Pomáha vyvážiť spoľahlivosť systému a rýchlosť dodávania nových funkcií.

**Android Studio/ADB**
Android Studio je oficiálne IDE pre vývoj Android aplikácií. ADB (Android Debug Bridge) je nástroj na komunikáciu s Android zariadením na účely testovania, ladenia a nasadzovania aplikácií.

**Network Link Conditioner**
Nástroj na simulovanie rôznych sieťových podmienok, ako je nízka rýchlosť, vysoká latencia či strata paketov. Používa sa pri testovaní odolnosti a výkonu aplikácií.

**Chrome DevTools Throttling**
Funkcia v Chrome DevTools umožňujúca obmedziť rýchlosť siete alebo výkon procesora pri testovaní webových aplikácií. Pomáha identifikovať problémy v rôznych podmienkach.

**Chatty API**
API, ktoré pri bežnej interakcii vyžaduje príliš veľa volaní, čím zvyšuje zaťaženie siete a latenciu. Optimalizácia zvyčajne zahŕňa zlučovanie požiadaviek.

**Protobuf/MessagePack**
Formáty binárnej serializácie dát, ktoré sú efektívnejšie než JSON alebo XML. Umožňujú rýchlejší prenos a menšiu veľkosť dát.

**AARRR**
Model merania rastu produktu – Acquisition, Activation, Retention, Referral, Revenue. Pomáha sledovať životný cyklus používateľa a optimalizovať stratégie.

**WAU**
(Weekly Active Users) metrika, ktorá udáva počet jedinečných používateľov, ktorí sa zapojili do aplikácie aspoň raz za týždeň. Slúži na sledovanie zapojenia a rastu.

**Diversity (ILD)**
Ukazovateľ, ako rôznorodé sú odporúčané položky. Vyššia hodnota znamená väčšiu variabilitu odporúčaní.

**Haveibeenpwned API**
API služby Have I Been Pwned umožňuje overiť, či bol e-mail alebo heslo kompromitované pri úniku dát. Slúži na zvýšenie bezpečnosti používateľov.

**IDOR**
(Insecure Direct Object Reference) zraniteľnosť, pri ktorej aplikácia umožňuje prístup k objektom (napr. súborom, záznamom) na základe predvídateľných identifikátorov bez riadneho overenia oprávnení.

**UUID**
(Universally Unique Identifier) 128-bitový identifikátor, ktorý je prakticky jedinečný v čase a priestore. Používa sa na označovanie objektov, transakcií či relácií.

**MITM útoky**
(Man-in-the-Middle) útoky, pri ktorých útočník zachytáva a mení komunikáciu medzi dvoma stranami bez ich vedomia. Používajú sa na krádež údajov alebo manipuláciu prenosu.

**DoS**
(Denial of Service) útok, ktorého cieľom je zneprístupniť službu pre oprávnených používateľov preťažením systému. Často sa realizuje zahltením siete alebo servera požiadavkami.

**Credential stuffing**
Útok, pri ktorom útočník využíva zoznamy kompromitovaných prihlasovacích údajov z iných služieb na prihlásenie sa do cieľovej aplikácie. Spolieha sa na opakované používanie hesiel.

**Scam odkazy**
Podvodné odkazy, ktoré sa vydávajú za legitímne a snažia sa získať citlivé údaje alebo peniaze od používateľov. Často vedú na phishingové stránky.

**Model poisoning**
Útok na strojové učenie, pri ktorom útočník manipuluje trénovacie dáta s cieľom zmeniť správanie modelu. Môže viesť k nesprávnym predikciám alebo zníženiu výkonu.

**Opt-in na tracking**
Mechanizmus, pri ktorom používateľ výslovne súhlasí so sledovaním svojho správania. Vyžaduje sa v mnohých legislatívach na ochranu súkromia.

**Logický COT**
(Chain of Thought) logický reťazec uvažovania používaný pri riešení problémov alebo rozhodovaní. V AI kontexte označuje generovanie medzikrokov vedúcich k finálnej odpovedi.

**RPA**
(Robotic Process Automation) Technológia na automatizáciu opakovaných manuálnych úloh pomocou softvérových robotov. V testovaní sa používa buď ako predmet testovania (overujeme správnosť robotov), alebo ako nástroj na automatizáciu testovacích scenárov, najmä tam, kde chýbajú API.

**PAY by square**
Štandardizovaný QR kód používaný na Slovensku a v Česku pre platby. Obsahuje údaje ako IBAN, suma, variabilný symbol či poznámka. Tester overuje správne načítanie kódu, kompatibilitu s aplikáciami bánk a validáciu údajov.

**Spinner**
Grafický prvok (zvyčajne kruhová animácia), ktorý indikuje, že aplikácia načítava alebo spracúva požiadavku. Pri testovaní sa kontroluje, či sa spinner zobrazuje len počas skutočného spracovania a či nezostáva „zaseknutý“.

**Maintenance mód**
Režim údržby, v ktorom je aplikácia dočasne nedostupná. Tester overuje, či sa zobrazuje správna informačná stránka, či sa neodosielajú transakcie a či sa aplikácia po skončení režimu obnoví do funkčného stavu.

**Fraud detection**
Systémy na detekciu podvodov sledujú transakcie a správanie používateľov, aby identifikovali podozrivé aktivity. Tester overuje správne nastavenie pravidiel, reakcie systému a integráciu s ďalšími procesmi (napr. blokácia účtu).

**IBAN**
(International Bank Account Number) medzinárodný formát čísla účtu. Pri testovaní sa kontroluje dĺžka, formát a kontrolná suma podľa krajiny.

**SWIFT/BIC**
(Society for Worldwide Interbank Financial Telecommunication / Bank Identifier Code) – identifikátor banky v medzinárodných prevodoch. Tester overuje validáciu, správnosť párovania k bankám a kompatibilitu s platobnými systémami.

**SWIFT/MT**
Správy v staršom formáte „Message Type“, používané v SWIFT sieti (napr. MT940). Tester overuje, či sa správy generujú a spracujú v správnej štruktúre.

**Reverzácie**
Storno transakcie, ktorá bola už spracovaná alebo autorizovaná. Tester overuje správne vykonanie reverzácie, účtovanie a zobrazenie v histórii účtu.

**Multicurrency**
Podpora viacerých mien v systéme. Testovanie zahŕňa kurzy, prevody, zaokrúhľovanie, účtovanie a zobrazovanie zostatkov v rôznych menách.

**SEPA**
Jednotná oblasť platieb v eurách. Tester kontroluje správnosť polí (IBAN, BIC, suma, dátum), maximálne limity a súlad s pravidlami SEPA schémy.

**MCC**
(Merchant Category Code) štvorciferný kód určujúci typ obchodníka. Pri testovaní sa sleduje správne mapovanie MCC na poplatky, limity alebo blokácie.

**PAN**
(Primary Account Number) číslo platobnej karty. Tester overuje maskovanie, správne formáty a bezpečné spracovanie.

**TTFN**
(time-to-first-notification) metrika merajúca čas od udalosti po doručenie prvej notifikácie. V testovaní sa sleduje oneskorenie a spoľahlivosť notifikačného systému.

**Offline mode – notifikácie**
Schopnosť aplikácie správne spracovať notifikácie, keď je zariadenie offline, a doručiť ich po opätovnom pripojení. Tester overuje správnu synchronizáciu.

**Airplane mode -notifikácie**
Testovanie správania aplikácie pri zapnutom režime lietadlo. Dôležité je, či sa neodosielajú požiadavky a či sa čakajúce notifikácie doručia po obnovení spojenia.

**Idempotentné kľúče **
(unikátne ID transakcie) identifikátor, ktorý zaručí, že rovnaká operácia nebude vykonaná viackrát (napr. duplicitná platba). Tester overuje, či server správne rozpozná opakovanú požiadavku.

**Dedupikácia na klientoch/servery**
Mechanizmus zabraňujúci spracovaniu rovnakej požiadavky viackrát. Testuje sa, či duplicity nevznikajú a či nedochádza k strate platných požiadaviek.

**DKIM/SPF/DMARC**
Bezpečnostné mechanizmy na ochranu e-mailovej komunikácie. Tester kontroluje, či sú správne nastavené DNS záznamy a či správy nie sú označené ako spam.

**FCM/APNS tokeny**
Identifikátory zariadení pre push notifikácie (Firebase Cloud Messaging pre Android, Apple Push Notification Service pre iOS). Tester overuje správne prideľovanie a expiráciu tokenov.

**D&R (Detection & Response)**
(Detection & Response) bezpečnostný prístup zameraný na rýchlu detekciu incidentov a reakciu na ne. Tester overuje, či sú incidenty logované, vyhodnocované a či existuje reakčný proces.

**BBAN**
(Basic Bank Account Number) národný formát čísla účtu. Tester overuje správnosť konverzie medzi BBAN a IBAN.

**FX – prepočty kurzov**
Foreign Exchange – výmeny mien. Tester kontroluje správne načítanie kurzov, ich aktualizáciu a aplikáciu pri transakciách.

**Rounding mode**
Spôsob zaokrúhľovania (nahor, nadol, najbližšie). Tester overuje, či aplikácia používa správny režim podľa legislatívy alebo interných pravidiel.

**Rate expiry**
Platnosť výmenného kurzu v čase. Tester overuje, či systém správne odmieta alebo prepočíta transakcie po uplynutí platnosti kurzu.

**SHA**
(Secure Hash Algorithm) rodina kryptografických hashovacích funkcií. Tester overuje implementáciu a kompatibilitu (napr. SHA-256).

**BEN/OUR**
Spôsoby úhrady poplatkov pri zahraničných platbách. BEN – poplatky znáša príjemca, OUR – poplatky znáša odosielateľ. Tester kontroluje, či sa poplatky aplikujú správne.

**AML rules**
(Anti-Money Laundering) pravidlá proti praniu špinavých peňazí. Tester overuje scenáre, pri ktorých sa majú transakcie blokovať alebo hlásiť.

**Anti-fraud**
Mechanizmy na ochranu pred podvodmi (limity, monitorovanie vzorov správania, blokácie). Tester sleduje, či fungujú podľa pravidiel.

**Velocity checks**
Kontroly rýchlosti – napríklad počet transakcií za určitý čas. Tester overuje, či systém správne blokuje alebo obmedzuje podozrivé správanie.

**Settlement**
Vyrovnanie transakcií medzi bankami alebo systémami. Tester overuje správne účtovanie, načasovanie a konsistenciu.

**Cutoff time**
Časový limit, do ktorého musí byť transakcia zadaná, aby bola spracovaná v ten istý deň. Tester overuje, či systém po prekročení cutoff time správne presunie spracovanie na ďalší deň.

**Routing fields**
Polia, ktoré určujú trasovanie transakcie cez rôzne banky alebo siete. Tester overuje, či sa správne vypĺňajú a spracujú.

**POI/PEP**
(Point of Interest / Politically Exposed Person) – POI sú dôležité miesta alebo body, PEP sú osoby s politickou funkciou. Tester overuje, či sú tieto kategórie správne identifikované a aplikované v pravidlách AML.

**Reconciliation**
Proces porovnania a zosúladenia záznamov medzi dvoma systémami (napr. bankou a clearingovým centrom). Tester kontroluje rozdiely a výnimky.

**SWIFT/ISO20022 adaptéry**
Komponenty umožňujúce prevod správ zo starého SWIFT MT formátu do nového ISO 20022 štandardu. Tester overuje správnosť mapovania a kompatibilitu.

**MT940**
Štandardizovaný výpis zo SWIFT siete, ktorý obsahuje informácie o transakciách na účte. Tester kontroluje jeho správnu štruktúru a import.

**ISO 4217**
Medzinárodný štandard kódov mien (napr. EUR, USD). Tester overuje správne používanie a validáciu.

**DKIM/SPF**
Opätovná zmienka mechanizmov ochrany e-mailov – tester sleduje, či sú implementované bez duplicitných konfliktov.

**Reverzácie**
Tester overuje konzistenciu pojmu s inými časťami systému – pri duplicitách sa má terminológia zjednotiť.

**Chargeback**
Proces, pri ktorom klient reklamuje transakciu a peniaze sa vracajú späť cez kartové schémy. Tester sleduje správne spracovanie a komunikáciu s poskytovateľom.

**PAdES**
(PDF Advanced Electronic Signatures) je štandard pre elektronické podpisy v PDF dokumentoch. Umožňuje vytvárať a validovať podpisy, ktoré sú priamo súčasťou PDF súboru. Tester kontroluje, či podpis spĺňa legislatívne požiadavky a či je dokument po podpise nemodifikovaný.

**XAdES**
(XML Advanced Electronic Signatures) je štandard pre elektronické podpisy v XML dokumentoch. Obsahuje viacero úrovní (napr. XAdES-BES, XAdES-T), ktoré definujú, aké údaje podpis uchováva (časové pečiatky, certifikáty). Tester overuje správnosť formátu a integritu XML.

**CAdES**
(CMS Advanced Electronic Signatures) je štandard pre elektronické podpisy v CMS (Cryptographic Message Syntax). Používa sa najmä pri podpise binárnych dát a e-mailov (S/MIME). Tester sleduje kompatibilitu podpisu a validitu certifikátov.

**ASiC**
(Associated Signature Containers) je formát kontajnera, ktorý spája podpisovaný dokument s elektronickým podpisom alebo časovou pečiatkou. Často sa používa na archiváciu (napr. ASiC-E, ASiC-S). Tester kontroluje, či kontajner obsahuje všetky potrebné časti a či je možné ho validovať.


**User case**
Prípad použitia – opis interakcie používateľa so systémom. Tester z neho vychádza pri návrhu testov.

**SRS (špecifikácia požiadaviek na softvér)**
Dokument popisujúci funkčné a nefunkčné požiadavky. Slúži ako základ pre vývoj a testovanie.

**ERD**
(Entity-Relationship Diagram) diagram znázorňujúci vzťahy medzi entitami v databáze. Pomáha testerom pochopiť dátový model.

**Sekvenčný diagram**
Diagram UML znázorňujúci poradie výmeny správ medzi objektmi. Tester ho využíva pri analýze tokov.

**OWASP**
(Open Web Application Security Project) nezisková organizácia, ktorá publikuje zoznam najčastejších zraniteľností webových aplikácií (OWASP Top 10).

**Race condition**
Situácia, keď výsledok závisí od poradia spracovania paralelných operácií. Tester overuje, či systém správne zvláda súbežný prístup.

**ABO**
Formát platobných príkazov používaný v Českej republike. Tester overuje kompatibilitu a správnosť exportov/importov.

**KYC**
(Know Your Customer) proces overenia identity klienta. Tester overuje kroky, dokumenty a bezpečnosť.

**Foto liveness**
Kontrola, či ide o živú osobu pri fotokontrole (napr. mrknutie, otočenie hlavy). Tester overuje, či systém nezlyhá pri fotografii.

**Video liveness**
Pokročilejšia verzia liveness, pri ktorej sa overuje video namiesto fotky. Tester sleduje presnosť a odolnosť voči podvodom.

**Retry a idempotencia**
Opakované pokusy o vykonanie operácie kombinované s idempotenciou – aby opakovaná požiadavka neviedla k duplikátu. Tester kontroluje správnu implementáciu opakovaní a odolnosť voči duplicitám.

**Sériový prepočet**
Postupné spracovanie alebo prepočet transakcií či dát v presne určenom poradí. Tester overuje, či sa transakcie spracujú sekvenčne bez vynechania alebo preskočenia krokov.

**Súbežné transakcie (concurrent)**
Situácia, keď viac transakcií prebieha naraz a systém musí zabezpečiť ich konzistentné spracovanie. Tester kontroluje riziko race conditions, deadlockov a správnu izoláciu transakcií.

**Reversal/refund**
Reversal je zvrátenie transakcie ešte pred zúčtovaním, refund je vrátenie peňazí po zúčtovaní. Tester overuje, či sa obe akcie správne zobrazujú v histórii a či účtovanie zodpovedá realite.

**Clearing**
Proces vyrovnávania finančných operácií medzi bankami alebo spracovateľmi platieb pred samotným zúčtovaním (settlement). Tester overuje, či dáta o clearingu sedia s vykonanými transakciami.

**Card-gateway**
Platobná brána sprostredkujúca platby kartami medzi obchodníkom, bankou a kartovou spoločnosťou. Tester sleduje správne presmerovanie, validáciu kariet a odozvu brány.

**BIM + GIS**
Integrácia Building Information Modeling (BIM) a Geografických informačných systémov (GIS). Tester overuje správnosť zobrazovania a prepojenia dát zo stavebných modelov a geografických vrstiev.

**WMS/WFS služby **
Štandardy **OGC** (Open Geospatial Consortium) pre zdieľanie mapových dát:
•	**WMS** (Web Map Service) poskytuje mapové obrázky (rastrové dáta).
•	**WFS** (Web Feature Service) poskytuje vektorové dáta (body, línie, polygóny).
Tester overuje správne načítanie, formát a kompatibilitu so softvérom.

**3D zobrazenie**
Vizualizácia objektov alebo dát v trojrozmernom priestore. Tester sleduje funkčnosť 3D modelov, interakcie (otáčanie, zoom) a výkon aplikácie pri väčších dátach.

**WGS84**
Svetový geodetický systém používaný v GPS. Tester kontroluje správnu interpretáciu súradníc (zemepisná šírka/dĺžka) a prevody na iné systémy.

**S-JTSK**
Slovenský/Juhoslovanský trigonometrický kartografický systém používaný pre mapy na území SR a ČR. Tester overuje správne prepočty medzi S-JTSK a WGS84.

**UTM**
(Univerzálny transverzálny Mercator) mapová projekcia rozdelená do zón. Tester overuje správne zobrazovanie údajov podľa príslušnej zóny.

**SHP**
Formát súborov ESRI Shapefile na ukladanie vektorových geografických dát. Tester sleduje kompatibilitu, integritu dát a import/export do GIS systémov.

**GeoJSON**
Formát založený na JSON pre ukladanie geografických objektov. Tester overuje správnosť štruktúry, kompatibilitu s knižnicami a validitu súradníc.

**KML**
(Keyhole Markup Language) formát pre geografické dáta využívaný v Google Earth a podobných aplikáciách. Tester kontroluje správne zobrazenie vrstiev a atribútov.

**GPX**
(GPS Exchange Format) formát založený na XML pre výmenu GPS trás, bodov a stôp. Tester overuje správne načítanie súradníc a kompatibilitu so zariadeniami.

**Polygon**
Geometrický útvar v GIS reprezentujúci plochu (napr. parcely, územia). Tester sleduje správne vykreslenie, výpočty plochy a spracovanie priestorových vzťahov.

**PostGIS**
Rozšírenie databázy PostgreSQL o podporu priestorových dát. Tester overuje funkčnosť priestorových dotazov (napr. bod v polygóne) a výkon pri väčších datasetoch.

**IoT**
(Internet of Things) sieť prepojených zariadení, ktoré komunikujú medzi sebou (senzory, čidlá, smart zariadenia). Tester sleduje spoľahlivosť prenosu dát, bezpečnosť a škálovanie.

**GML**
(Geography Markup Language) XML formát pre opis geografických prvkov a ich vzťahov. Tester kontroluje validitu XML schém a kompatibilitu s GIS aplikáciami.

**ECMWF**
(European Centre for Medium-Range Weather Forecasts) – európske centrum, ktoré prevádzkuje numerické modely pre strednodobé predpovede počasia. Dáta ECMWF sa často využívajú aj v GIS aplikáciách a IoT systémoch. Tester overuje správne načítanie dátových súborov, ich časovú platnosť a vizualizáciu.

**GFS**
(Global Forecast System) – globálny numerický model predpovede počasia prevádzkovaný v USA (NOAA). Poskytuje otvorené dáta vo viacerých formátoch (napr. GRIB). Tester sleduje správnu interpretáciu dát, porovnanie s inými modelmi a ich integráciu do aplikácií (napr. mapové vrstvy).

**Politika retention**
(Politika uchovávania dát) – pravidlá určujúce, ako dlho sa uchovávajú záznamy, logy alebo osobné údaje. Tester overuje, či sú dáta po uplynutí retenčnej lehoty správne anonymizované alebo zmazané podľa GDPR a interných pravidiel.

**Shadow DOM**
Časť DOM stromu izolovaná od zvyšku webovej stránky, používaná vo Web Components. Umožňuje zapuzdrenie štýlov a štruktúry. Tester overuje viditeľnosť, interakciu a správne renderovanie prvkov v rámci tieňového DOM-u.

**Web Components**
Súbor technológií (Custom Elements, Shadow DOM, HTML Templates), ktoré umožňujú vytvárať opakovane použiteľné komponenty vo webových aplikáciách. Tester kontroluje integráciu, kompatibilitu medzi prehliadačmi a správne správanie komponentov.

**WebSockets**
Protokol umožňujúci obojsmernú (full-duplex) komunikáciu medzi klientom a serverom v reálnom čase. Tester sleduje spoľahlivosť spojenia, odolnosť pri prerušení, oneskorenie a správne odosielanie/prijímanie správ.

**Locator**
Identifikátor prvku na stránke (napr. ID, XPath, CSS selektor), ktorý umožňuje automatizovanému testu s prvkom interagovať. Tester overuje, či sú lokátory stabilné a nemenné medzi verziami aplikácie.

**XPath**
Jazyk na vyhľadávanie prvkov v XML/HTML štruktúre. V testovaní sa používa na presné označenie elementov, najmä ak nemajú unikátne ID. Tester kontroluje, či sú XPath výrazy dostatočne špecifické, ale nie krehké.

**CSS selektor**
Alternatíva k XPath na identifikáciu prvkov podľa štýlov alebo štruktúry HTML. Tester rozhoduje, ktorý prístup je stabilnejší pre daný projekt.

**Headless mód**
Režim spúšťania testov bez grafického rozhrania (napr. v prehliadači ChromeHeadless). Tester ho využíva pre rýchlejšie a automatizované testy v CI/CD pipeline.
Wait (explicit/implicit)
Mechanizmy čakania v automatizácii – explicitný čaká na konkrétnu podmienku, implicitný čaká pevne daný čas. Tester sleduje, aby sa testy nesekali a neboli zbytočne pomalé.

**Selenium WebDriver**
Najrozšírenejší nástroj na automatizáciu testov webových aplikácií. Tester definuje scenáre v kóde, ktoré simulujú akcie používateľa (klik, zadanie textu, overenie výsledku).

**Playwright**
Moderný open-source nástroj od Microsoftu pre end-to-end testovanie webových aplikácií. Podporuje viac prehliadačov, paralelné testy, nahrávanie videí a prácu s viacerými záložkami.

**Cypress**
Framework pre webové testovanie, ktorý beží priamo v prehliadači. Tester ocení rýchlu spätnú väzbu, automatické čakania a interaktívne debugovanie.

**Page Object Model (POM)**
Vzorec (pattern), ktorý oddeľuje logiku testov od implementácie prvkov na stránke. Tester udržiava testy prehľadné a ľahko upraviteľné aj pri zmenách UI.

**Data-driven testing**
Testovacia technika, kde sa jeden test spúšťa s rôznymi vstupnými dátami (napr. z CSV alebo Excelu). Umožňuje pokryť viac scenárov bez duplicitného kódu.

**Keyword-driven testing**
Metodika, kde testovacie kroky sú definované pomocou „kľúčových slov“ (napr. klikni, zadaj, over). Tester vďaka tomu oddeľuje logiku testu od implementácie.

**Fixture**
Predpripravený stav alebo súbor dát, ktorý test potrebuje pred spustením. Tester ho využíva na opakované nastavenie rovnakých podmienok (napr. prihlásený používateľ).

**Mock/Stub**
Simulácia závislostí – mock napodobňuje správanie objektu, stub vracia fixné hodnoty. Tester ich používa, keď reálne služby ešte nie sú dostupné.

**Assertion library**
Knižnica, ktorá poskytuje funkcie ako assertEqual, assertTrue, expect(). Tester overuje očakávaný výsledok v rámci automatizovaného testu.

**Parallel testing**
Spúšťanie viacerých testov naraz (napr. v rôznych prehliadačoch alebo zariadeniach). Tester sleduje stabilitu a správne rozdelenie zdrojov.

**Test runner**
Nástroj, ktorý organizuje, spúšťa a reportuje výsledky testov (napr. pytest, Jest, Mocha, NUnit). Tester kontroluje, či sú výsledky správne zaznamenané a logy čitateľné.

**Continuous Integration (CI)**
Proces, kde sa testy automaticky spúšťajú pri každej zmene kódu. Tester sleduje, či testy prechádzajú pred nasadením a či build nepadá.

**Continuous Delivery (CD)**
Nadstavba CI – automatizované doručenie testovanej verzie až do produkčného prostredia. Tester sleduje kvalitu pred spustením release.

**Retry mechanism**
Opakované spustenie testu pri náhodnom zlyhaní (napr. sieťová chyba). Tester kontroluje, či retry nezakrýva reálne chyby.

**Selector flakiness**
Problém, keď sa lokátory menia alebo sú nejednoznačné, čo vedie k nestabilným testom. Tester identifikuje a stabilizuje selektory (napr. pomocou dátových atribútov).

**CI pipeline**
(Continuous Integration pipeline) – sekvencia krokov, ktorá automaticky spúšťa build, testy a analýzy po každej zmene v kóde. Tester sleduje, či sa testy spúšťajú v správnom poradí, či sa ukladajú reporty a či sa pipeline nezastaví na chybnom kroku.

**Docker runner**
Izolované prostredie (kontajner) používané na spúšťanie testov v CI/CD. Tester overuje, či runner obsahuje všetky potrebné závislosti, správne pracuje s volumes a poskytuje opakovateľné výsledky.

**Test hooky**
Metódy, ktoré sa spúšťajú pred a po testoch – napr. beforeAll(), afterEach(). Tester ich používa na prípravu testovacích dát, inicializáciu prehliadača alebo čistenie prostredia.

**Allure report**
Nástroj na vizualizáciu výsledkov automatizovaných testov. Poskytuje prehľadné grafy, screenshoty, logy a prepojenia na testovacie prípady. Tester kontroluje, či sa výsledky správne zbierajú a reportujú.

**Headed vs Headless**
Headed režim spúšťa test s viditeľným prehliadačom, Headless bez GUI. Tester volí režim podľa potreby – Headed na ladenie, Headless pre CI/CD.

**Accessibility tree**
Štruktúra, ktorú používajú asistívne technológie (napr. čítačky obrazovky) na interpretáciu UI. Tester overuje, či sú elementy správne popísané (ARIA atribúty, labely).

**Parallel shardovanie**
Rozdelenie testov do viacerých častí (shardov), ktoré sa spúšťajú paralelne na viacerých strojoch. Skracuje čas testovania. Tester sleduje správnu distribúciu a konsistenciu výsledkov.

**Test retry policy**
Politika opakovania zlyhaných testov – určuje, koľkokrát sa test smie zopakovať, kým sa označí ako neúspešný. Tester sleduje, aby politika neprekrývala reálne chyby.

**Test tagging**
Označovanie testov podľa typu, priority alebo prostredia (napr. @smoke, @regression). Tester vďaka tagom rýchlo vyberá testy na spustenie.

**Test fixture scope**
Rozsah platnosti fixture – napr. per-test, per-class alebo per-session. Tester definuje, ako dlho má fixture zostať aktívna a kedy sa má zničiť.

**Cross-browser testing**
Overovanie správania aplikácie v rôznych prehliadačoch (Chrome, Firefox, Safari, Edge). Tester sleduje rozdiely v renderovaní a funkčnosti.

**Cross-platform testing**
Testovanie aplikácie na viacerých operačných systémoch alebo zariadeniach (Windows, macOS, Linux, Android, iOS). Tester overuje kompatibilitu a výkon.

**Browser context**
Izolované prostredie v rámci prehliadača (napr. Playwright podporuje viac kontextov naraz). Tester ho používa na simuláciu viacerých používateľov v jednom teste.

**Test flakiness**
Nestabilita testov – raz prejdú, inokedy zlyhajú bez zmeny kódu. Tester analyzuje príčiny (synchronizácia, závislosti, dáta) a eliminuje ich.

**Dynamic waits**
Čakanie, ktoré sa prispôsobuje aktuálnemu stavu aplikácie. Tester kontroluje, či čakacie podmienky reagujú na zmeny v DOM a nepredlžujú testy zbytočne.

**Screenshot capture**
Zachytenie obrazu obrazovky počas testu – pri chybe alebo ako dôkaz úspechu. Tester sleduje, či sú snímky čitateľné a správne priradené k prípadu.

**Video recording**
Záznam priebehu testu vo forme videa, používaný pri Playwrighte alebo Cypress-e. Tester ho využíva na analýzu zlyhaní a dokumentáciu.

**Mock server**
Simulácia backendového rozhrania, ktorá vracia preddefinované odpovede. Tester ju používa, ak API ešte nie je dostupné alebo sa testuje offline scenár.

**Test isolation**
Zásada, že každý test by mal byť nezávislý od iného. Tester overuje, že testy si neovplyvňujú dáta ani stav aplikácie.

**Selenium Grid**
Nástroj, ktorý umožňuje spúšťať testy paralelne na viacerých zariadeniach, prehliadačoch a operačných systémoch. Tester overuje, či sa testy správne rozdeľujú, výsledky konsolidujú a či nedochádza ku kolíziám medzi uzlami.

**TestContainers**
Knižnica (napr. pre Python, Java, .NET), ktorá umožňuje spúšťať databázy, message brokery či iné závislosti v Docker kontajneroch priamo počas testu. Tester overuje izoláciu, rýchlosť štartu a korektnosť konfigurácie.

**CI artifacts**
(Výstupy pipeline) – výsledné súbory z behu testov, napr. logy, screenshoty, reporty. Tester sleduje, či sa artefakty správne generujú, uchovávajú a dajú spätne stiahnuť.

**Pipeline triggers**
Udalosti, ktoré spúšťajú CI/CD pipeline (napr. push do vetvy, merge request, cron plánovač). Tester kontroluje, či sa pipeline nespúšťa zbytočne a či reaguje na zmeny v správnych vetvách.

**Flaky test detection**
Mechanizmus na identifikáciu nestabilných testov, ktoré raz prejdú a inokedy zlyhajú. Tester analyzuje logy, výsledky viacerých behov a používa automatické označovanie flaky testov.

**Monkey testing**
Náhodné kliknutia, gestá alebo vstupy simulujúce nepredvídateľné správanie používateľa. Tester sleduje stabilitu aplikácie, deteguje pády alebo zablokovania UI.

**Contract testing**
Testovanie zmluvy medzi dvoma systémami (napr. frontend a backend). Overuje, že API odpovedá v očakávanom formáte a že zmeny na jednej strane nerozbijú integráciu. Tester používa nástroje ako Pact.

**Visual regression testing**
Automatické porovnávanie snímok obrazovky, aby sa zistilo, či sa UI nezmenilo neočakávane. Tester overuje prah odchýlky a ignoruje šum (napr. timestampy).

**Synthetic users**
Virtuálni používatelia, ktorí simulujú správanie reálnych ľudí v testovacom prostredí (napr. načítanie stránky, kliky, loginy). Tester sleduje výkon, odozvy a zaťaženie systému.

**Data mocking**
Vytváranie falošných dát namiesto reálnych z databázy alebo API. Tester používa nástroje na generovanie (napr. Faker, Mockaroo) a sleduje, aby dáta reprezentovali realistické scenáre.

**API assertions**
Overovanie odpovedí API – kódu odpovede, obsahu JSON, hlavičiek, časov odozvy. Tester používa nástroje ako Postman, pytest, RestAssured či SuperTest.

**Test scheduler**
Systém, ktorý riadi, kedy sa testy spúšťajú – napr. denne o polnoci, po nasadení buildu alebo po zmenách v repozitári. Tester sleduje správnu frekvenciu a plánovanie.

**CI cache**
Mechanizmus, ktorý uchováva závislosti alebo buildy medzi behmi pipeline. Skracuje čas testovania. Tester kontroluje, či cache neobsahuje zastarané dáta.

**Blue-green deployment**
Technika nasadzovania dvoch identických prostredí (blue a green), kde sa nové verzie testujú v jednom z nich. Tester overuje plynulé prepnutie bez výpadku.

**Canary release**
Postupné nasadzovanie novej verzie len malej časti používateľov. Tester sleduje správanie aplikácie a chyby pred plošným nasadením.

**Rollback**
Návrat k predchádzajúcej verzii po zlyhaní release. Tester overuje, či rollback prebehne bez straty dát a bez narušenia konzistencie systému.

**Log analysis**
Analýza logov z testov, aplikácie alebo CI. Tester využíva nástroje ako Kibana, Grafana alebo ElasticSearch na identifikáciu chýb a výkonových problémov.

**Test analytics**
Zber a vizualizácia metrik testovania (úspešnosť, trvanie, flakiness, pokrytie). Tester sleduje trendy a používa ich na optimalizáciu testov.

**Environment variables**
Premenné prostredia definujúce konfiguráciu testov (napr. URL, tokeny, credentials). Tester kontroluje, či nie sú uložené v kóde a správne sa načítavajú.

**Secret management**
Bezpečné ukladanie hesiel, API kľúčov a tokenov. Tester sleduje, že tajomstvá nie sú uložené v repozitári a sú načítané z bezpečného trezoru (napr. HashiCorp Vault, GitHub Secrets).

**Performance testing**
Testovanie výkonu aplikácie – zisťuje, ako rýchlo systém reaguje pri bežnej záťaži. Tester sleduje metriky ako čas odozvy, využitie CPU, pamäte či databázové dotazy.

**Load testing**
Záťažové testovanie – overuje správanie systému pri vysokom, ale očakávanom zaťažení. Tester postupne zvyšuje počet požiadaviek alebo používateľov a sleduje, kde nastáva degradácia výkonu.

**Stress testing**
Extrémne testovanie nad rámec bežného používania s cieľom zistiť, kde sa systém „zlomí“. Tester overuje, či aplikácia pri zlyhaní padne kontrolovane a obnoví sa po odľahčení.

**Spike testing**
Typ záťažového testu, ktorý simuluje náhle zvýšenie počtu používateľov (napr. po marketingovej kampani). Tester sleduje, či systém zvládne prudký nárast požiadaviek.
Soak testing
Dlhodobé testovanie stability (napr. 24–72 hodín). Tester sleduje úniky pamäte, degradáciu výkonu a kumulatívne chyby počas dlhého behu.

**Capacity testing**
Overuje, aký maximálny počet používateľov alebo transakcií systém zvládne bez výpadku. Tester vytvára model rastu záťaže a sleduje hranice kapacity.

**Benchmark**
Referenčný test, ktorý porovnáva výkon rôznych verzií aplikácie alebo konfigurácií. Tester sleduje zmeny medzi buildmi a vyhodnocuje regresie výkonu.

**Bottleneck**
Úzke miesto systému – komponent, ktorý spomaľuje celkový výkon (napr. databáza, API, fronta). Tester využíva profilovacie nástroje na identifikáciu úzkych miest.

**JMeter**
Open-source nástroj pre load a performance testing. Tester konfiguruje počet vlákien, scenáre a reportuje výsledky.

**k6**
Moderný nástroj pre skriptovateľné výkonnostné testy (JavaScript syntax). Tester ho používa na integráciu s CI/CD pipeline a vizualizáciu metrík.

**Gatling**
Framework na záťažové testovanie v Scale, používaný v CI prostrediach. Tester píše scenáre ako kód a generuje HTML reporty s grafmi.

**Synthetic monitoring**
Monitorovanie systému pomocou „falošných“ používateľov, ktorí pravidelne vykonávajú testovacie akcie (napr. prihlásenie, nákup). Tester sleduje dostupnosť a čas odozvy v reálnom čase.

**Real user monitoring (RUM)**
Zber údajov o správaní skutočných používateľov v produkcii. Tester porovnáva výsledky s testovacími metrikami, aby overil reálnu výkonnosť.

**Error handling**
Mechanizmy, ktoré zachytávajú a spracovávajú chyby. Tester overuje, či sú chyby logované, či majú zrozumiteľné hlášky a či neunikajú interné informácie.

**Graceful degradation**
Schopnosť systému fungovať aj pri čiastočnom výpadku (napr. ak nefunguje časť služby, ostatné moduly bežia ďalej). Tester overuje správanie pri chybových stavoch.

**Failover**
Automatické prepnutie na záložné prostredie alebo server pri výpadku. Tester overuje čas prepnutia a konzistenciu dát medzi uzlami.

**Chaos engineering**
Metodika, pri ktorej sa zámerne vnášajú chyby do systému (napr. výpadky sietí, uzlov), aby sa overila jeho odolnosť. Tester používa nástroje ako Chaos Monkey alebo Gremlin.
 
**Circuit breaker**
Vzorec, ktorý dočasne preruší volanie služby, ak opakovane zlyháva. Tester overuje, či sa breaker správne aktivuje, sleduje obnovu po uplynutí času a správne logovanie.

**Retry policy (pre služby)**
Nastavenie, ako často a s akým oneskorením sa má služba pokúsiť o opakované volanie po zlyhaní. Tester overuje, či retry nezvyšuje záťaž alebo nevedie k duplikáciám.

**Alerting**
Systém upozornení na základe prahových hodnôt (napr. vysoká latencia, výpadok endpointu). Tester overuje, či sa alerty spúšťajú korektne a či ich notifikácie prichádzajú správnym adresátom.

**Observability**
Schopnosť systému poskytovať dostatok dát na pochopenie svojho správania. Tester sleduje metriky, logy a trace dáta, aby mohol rýchlo diagnostikovať problém.

**Distributed tracing**
Zaznamenávanie priebehu požiadaviek naprieč viacerými službami (napr. OpenTelemetry, Jaeger). Tester overuje, či trace obsahuje všetky kroky a či sa dá spätne dohľadať chyba.

