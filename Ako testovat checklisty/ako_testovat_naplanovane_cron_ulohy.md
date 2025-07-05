# Ako testovať naplánované CRON úlohy (napr. nočné e-maily)<br>

Ukážka situácie: Nočné CRON úlohy pre odosielanie e-mailov<br>

V aplikácii existuje CRON úloha, ktorá „každú noc o 02:00“ spracuje zoznam používateľov a „odosiela im sumarizačný e-mail s dennými notifikáciami“ (napr. neprečítané správy, nové úlohy, zmeny v kalendári). Úla je naplánovaná cez `cron` príkaz na serveri, volá backendový skript, ktorý pracuje s databázou a e-mailovým serverom.<br><br>


## Čo testovať a ako<br>

1. **Správne časovanie CRON úlohy**<br>

<u>Cieľ:</u> Úloha sa má spustiť presne o 02:00 každý deň.<br>

<u>Ako testovať:</u><br>

- Skontroluj nastavenie CRON výrazu (napr. `0 2 * * *`).<br>
- V testovacom prostredí uprav CRON na kratší interval (napr. každých 5 minút).<br>
- V logoch/monitoringu skontroluj presný čas začiatku a ukončenia úlohy.<br>
- Využi nástroje ako Cronitor, Healthchecks, Sentry cron monitor, Grafana alerty.<br><br>


 1. **Správne podmienky spustenia**<br>

<u>Cieľ:</u> Úloha sa má spustiť iba ak sú splnené určité podmienky (napr. databáza je dostupná, používateľ má zapnuté notifikácie, systém nie je v režime údržby).<br>

<u>Ako testovať:</u><br>

- Simuluj výpadok závislostí (napr. vypni databázu alebo e-mailový server).<br>
- Over, či úloha správne preskočí alebo zaloguje chybu.<br>
- Pridaj testovacieho používateľa s rôznymi stavmi (zapnuté/zakázané e-maily, chýbajúca adresa).<br><br>


1. **Oneskorené spracovanie alebo výpadok**<br>

<u>Cieľ:</u> Overiť, čo sa stane, ak sa CRON nespustí načas.<br>

<u>Ako testovať:</u><br>

- Spusť CRON skript neskôr.<br>
- Over, či sa e-maily odošlú alebo či systém kontroluje duplicitnosť.<br>
- Skontroluj, či existuje retry mechanizmus alebo záznam o zlyhaní.<br><br>


1. **Zamedzenie duplicitného spustenia**<br>
   
<u>Cieľ:</u> CRON sa nemá spustiť viackrát naraz.<br>

<u>Ako testovať:</u><br>

- Spusť úlohu manuálne paralelne.<br>
- Over zámky (`lock file`, redis zámok, `is\_running` flag).<br>
- Over, či sa e-maily neodoslali duplicitne.<br><br>


 1. **Správny obsah a adresáti e-mailov**<br>

<u>Cieľ:</u> Každý používateľ dostane to, čo mu patrí.<br>

<u>Ako testovať:</u><br>

- Použi testovacie účty so seed data.<br>
- Over e-mailové hlavičky, subject, obsah.<br>
- Použi sandbox ako Mailtrap alebo Mailhog.<br>
- Over jazyk, podpis, kódovanie.<br><br>


1. **Záznam do logu a monitoring**<br>

<u>Cieľ:</u> Každé spustenie je zaznamenané.<br>

<u>Ako testovať:</u><br>

- Over logy (timestamp, počet e-mailov, chyby).<br>
- Skontroluj monitoring (upozornenia pri chybe).<br>
- Simuluj zlyhanie a sleduj záznam.<br><br>


1. **Možnosť manuálneho spustenia**<br>

<u>Cieľ:</u> Overiť, či sa dá úloha spustiť mimo CRON.<br>

<u>Ako testovať:</u><br>

- Spusť úlohu cez CLI alebo API.<br>
- Over rovnaké podmienky a správanie.<br><br>


1. **Unit a integračné testy logiky**<br>

<u>Cieľ:</u> Otestovať funkcie ako `get\_users()`, `send\_email()` samostatne.<br>

<u>Ako testovať:</u><br>

- Použi `pytest` alebo podobný framework.<br>
- Mockuj závislosti (SMTP, DB).<br>
- Testuj hraničné prípady (0 používateľov, 1000 používateľov, neplatný e-mail).<br><br>

#cronjobs #testovanie #automatizacia #qualityassurance #emailtesting #devops #pytest #backendtesting #scheduledtasks #monitoring

