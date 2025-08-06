# Ako testovať prechod medzi prostrediami (napr. vývoj → test → produkcia)?<br><br>

Príklad:<br>
Predstavte si, že testujete aplikáciu, kde sa v testovacom prostredí zobrazuje nové tlačidlo „Exportovať report“. Na vývoji to fungovalo, ale na teste sa to správa inak – neodosiela žiadosť na server. Na produkcii sa tlačidlo ani nezobrazuje. Problém? Zlá konfigurácia prostredí.<br><br>

Pri testovaní medzi prostrediami sa nekontroluje len funkcionalita, ale aj správna konfigurácia, verzie, feature toggles či dáta. Tu je zoznam, čo si pri tom treba postrážiť:<br><br>

Čo všetko otestovať pri prechode medzi prostrediami:<br><br>

1. **Konfiguračné rozdiely**<br>
- Skontroluj, či má každé prostredie správne nastavené URL, porty, API kľúče, CORS, SMTP, databázy, externé integrácie a ďalšie parametre.<br>
- Porovnaj config súbory (napr. `config.yml`, `.env`, `application.properties`) alebo si prebehni výpisy z CI/CD nástrojov (napr. GitLab CI, Jenkins).<br><br>

2. **Feature toggles/flags**<br>
- Napr. `DHL=1` v config.sys aktivuje export zásielok pre DHL.<br>
- Funkcionalita je nasadená, ale aktivovaná len tam, kde je pripravená.<br><br>

3. **Verzia aplikácie**<br>
- Over, či má test aj produkcia rovnakú verziu (build number, commit hash).<br>
- Môžeš použiť UI (verzia v pätičke) alebo endpoint `/version`.<br><br>

4. **Testovanie dát**<br>
- Sú testovacie dáta realistické a bez citlivých údajov?<br>
- Pri migrácii dát over konzistenciu (vzťahy, počty, štruktúra).<br>
- Over úplnosť a korektnosť importu dát.<br><br>

5. **Prístupové práva a role**<br>
- Otestuj oprávnenia pre všetky role na každom prostredí.<br>
- Práva admina na teste môžu byť iné než na produkcii.<br><br>

6. **Logy a monitorovanie**<br>
- Sú logy aktívne? Nepíšu sa debug logy na produkcii?<br>
- Funguje napojenie na monitoring (Grafana, Kibana, Sentry...)?<br><br>

7. **Bezpečnosť a obmedzenia**<br>
- Over SSL certifikáty, redirecty, HTTP headers (CSP, X-Frame-Options).<br>
- Test prostredie by nemalo byť verejne prístupné ako produkcia.<br><br>

8. **Prístupnosť prostredí**<br>
- Je aplikácia dostupná zo siete, v ktorej testuješ?<br>
- Over DNS, latency a samotnú dostupnosť stránky.<br><br>

9. **Fallbacky a defaulty**<br>
- Čo sa stane, ak niečo chýba v konfigu?<br>
- Aplikácia by mala mať predvolené hodnoty alebo aspoň logickú chybu.<br><br>

**Záver:**<br>

Tester nie je len "klikací overovač", ale strážca kontextu – rozumie rozdielom medzi prostrediami a vie, že aj najlepšia funkcia zlyhá, ak má zlé podmienky na beh.<br>
