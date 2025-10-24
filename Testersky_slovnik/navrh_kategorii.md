# Návrh kategórií pre testerský slovník

Návrh vychádza z aktuálnych hesiel v súbore `testersky_slovnik.md`. Každá kategória zahŕňa typické témy a konkrétne príklady
hesiel, aby sa dali položky v slovníku priradiť jednotne a konzistentne. Odporúčaný postup:

1. Vyber primárnu kategóriu podľa hlavného významu hesla.
2. Ak má pojem presah do viacerých oblastí, doplň aj sekundárnu kategóriu.
3. Pri nových heslách používaj rovnaké názvy kategórií, aby sa dali filtrovať alebo zoskupovať.

## Prehľad kategórií

| Kategória | Popis | Príklady hesiel |
| --- | --- | --- |
| **Testovanie softvéru a kvalita** | Všetko, čo priamo súvisí s testovaním, stratégiou kvality, technikami a artefaktmi testovacieho procesu. | test case, test plan, test report, test suite, test evidence, exploratory testing, regression test, smoke test, sanity test, session-based testing, mutation testing |
| **Riadenie defektov a incidentov** | Postupy, nástroje a metriky na prácu s chybami a incidentmi. | bug lifecycle, defect triage, bug bash, blocker, bug reproducibility, zombie bug, boomerang bug, known issue |
| **Automatizácia a technická podpora testov** | Pojmy viazané na infraštruktúru testov, automatizáciu a súvisiace nástroje. | assert, mocking, CI/CD, test harness, build number, version endpoint, stacktrace, debug logy |
| **Vývoj softvéru a architektúra** | Koncepty z vývoja, infraštruktúry a návrhu systému, ktoré tester v praxi rieši. | API, endpoint, rollback, soft delete, environment variables, SDLC, waterfall, agile, scrum, sprint, backlog, seed data, sandbox, session management |
| **Front-end a UX** | Prvky používateľského rozhrania a interakcie, ktoré sa testujú na úrovni UI. | dropdown, checkbox, tooltip, label, happy path, golden path |
| **Produktové riadenie a agilné procesy** | Artefakty a ceremónie agilného vývoja, plánovanie práce, komunikácia so stakeholdermi. | user story, acceptance criteria, definition of done, sprint review, sprint retrospective, velocity, backlog grooming |
| **Dáta a analytika** | Práca s dátami, metrikami a analýzou výsledkov. | test data, test data management, data lineage, data governance, A/B testing, cohort analysis, KPI |
| **Biznis, ekonomika a produkt** | Termíny z produktového a ekonomického pohľadu, ktoré ovplyvňujú testovanie. | business case, ROI, SLA, quality gate, test debt |
| **Bankovníctvo a finančné služby** | Špecifické doménové pojmy zo sveta finančných produktov a regulácií. | IBAN, AML, KYC, clearing, settlement, chargeback, PSD2 |
| **Logistika a doprava** | Pojmy spojené s dopravou, zásobovaním a sledovaním zásielok. | waybill, manifest, delivery note, fulfillment, lead time, tracking number, fleet management |
| **Zákaznícka podpora a prevádzka** | Procesy a tímy, ktoré riešia komunikáciu so zákazníkom, incidenty a prevádzku systémov. | SLA, incident management, operations handbook, NOC, alerting |
| **Právo, regulácie a bezpečnosť** | Bezpečnostné opatrenia, regulačné požiadavky a auditné mechanizmy. | GDPR, anonymizácia, penetration testing, vulnerability, compliance report, audit log, CSP, CORS, HSTS, X-Frame-Options |
| **Sieťové protokoly a infraštruktúra** | Technické základy sieťovej komunikácie, ktoré ovplyvňujú testovanie systémov. | HTTP, HTTPS, TLS, DNS, redirect, SMTP, latency |
| **Databázy a integrita dát** | Koncepty práce s databázou a konzistenciou údajov. | integrity constraints, orphan records, cache invalidation |
| **Logika, matematika a základné pojmy** | Základné logické a matematické operácie, ktoré sa v texte slovníka objavujú. | XOR, XNOR, XAND |
| **AI a pokročilé prístupy** | Testovanie umelej inteligencie a využitie AI v testovaní. | AI-under-test, AI-assisted testing, fuzzy testing |

## Vrstvenie kategórií

* Primárna kategória by mala vystihovať hlavný účel hesla (napr. `test case` → Testovanie softvéru a kvalita).
* Sekundárnu kategóriu použijeme vtedy, keď je dôležitá pre pochopenie kontextu (napr. `SLA` → Biznis, ekonomika a produkt + Zákaznícka podpora a prevádzka).
* Ak pojem pokrýva proces aj techniku, priraď ho k obom (napr. `quality gate` → Testovanie softvéru a kvalita + Biznis, ekonomika a produkt).

## Tipy pre budúce rozširovanie

* Pri každom novom hesle si over, či už existuje vhodná kategória. Ak nie, doplň novú iba vtedy, keď pojem nezapadá do žiadnej z
  uvedených oblastí.
* V poznámke k heslu môžeš uviesť sekundárne kategórie alebo súvisiace pojmy. Pomôže to pri filtrovaní a vyhľadávaní.
* Raz za čas si prejdite celý slovník a skontrolujte, či sa nové heslá zoskupujú konzistentne. Ak sa vyskytne veľká skupina nových
  pojmov (napr. ďalšie logistické výrazy), zvážte vytvorenie podkategórie.

## Poznámka k testom

Tento návrh mení iba dokumentáciu a nesúvisí so spúšťaním kódu alebo skriptov, preto nevyžaduje spustenie automatických testov.
Ak zmeny zasiahnu do kódu alebo konfigurácie, treba štandardne spustiť príslušné testy a lint nástroje.
