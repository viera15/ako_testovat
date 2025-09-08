# Ako testovať bankovú mobilnú aplikáciu (Android / iOS)<br><br>

Príklad:<br>
Banka spustila novú mobilnú aplikáciu, ktorá má klientom umožniť rýchle a bezpečné zadávanie platieb, kontrolu zostatkov a notifikácie o pohyboch na účte. Tester dostane úlohu overiť, či aplikácia funguje spoľahlivo na rôznych zariadeniach a neohrozuje bezpečnosť klientov.<br><br>

## Ako otestovať?<br><br>

1. **Funkčnosť**<br>
- Overiť prihlásenie: biometria (odtlačok prsta, Face ID), PIN, heslo.<br>
- Skontrolovať základné funkcie: zobrazenie zostatku, histórie transakcií, zadanie platby, nastavenie trvalého príkazu.<br>
- Otestovať notifikácie: príde upozornenie pri odchádzajúcej platbe?<br><br>

2. **Použiteľnosť (UX/UI)**<br>
- Je navigácia jednoduchá a konzistentná?<br>
- Dá sa rýchlo nájsť najpoužívanejšia funkcia (napr. zadanie platby)?<br>
- Je aplikácia čitateľná a prístupná aj pre používateľov so zhoršeným zrakom (kontrast, veľkosť písma)?<br><br>

3. **Bezpečnosť**<br>
- Skontrolovať, či sa aplikácia po určitom čase nečinnosti sama odhlási.<br>
- Overiť, že sa dá prihlásiť len jedným zariadením naraz (ak to politika banky vyžaduje). Napríklad: ak sa používateľ prihlási na druhom telefóne, mal by sa na prvom automaticky odhlásiť, alebo mu aplikácia druhé prihlásenie nepovolí.<br>
- Otestovať šifrovanie komunikácie (HTTPS/TLS).<br><br>

4. **Kompatibilita a výkon**<br>
- Spustiť testy na rôznych verziách Androidu a iOS, vrátane starších zariadení.<br>
- Otestovať aplikáciu na slabšom internete (napr. simulované 3G, obmedzená rýchlosť cez developer tools alebo dátové obmedzenia od operátora).<br><br>

5. **Negatívne scenáre**<br>
- Zadanie nesprávneho PINu/hesla viackrát – je účet dočasne blokovaný?<br>
- Prerušenie internetového pripojenia počas zadania platby.<br>
- Aktualizácia aplikácie – zostanú dáta používateľa zachované?<br><br>

Testovanie bankovej aplikácie nie je len o "kliknutí si" – ide o komplexné overenie bezpečnosti, funkčnosti a dôveryhodnosti.<br>
