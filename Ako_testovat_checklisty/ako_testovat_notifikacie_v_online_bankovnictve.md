# Ako testovať notifikácie v online bankovníctve (push, SMS, e-mail)<br><br>

Príklad:<br>
Zákazník si v aplikácii zapne notifikácie pre karty: platby nad 20 €, výbery z bankomatu a prihlásenia do IB. Po platbe kartou 35 € očakáva push do 10 sekúnd, ak nie je online tak SMS do 1 minúty, a súhrnný e-mail na konci dňa. V praxi sa mu zobrazí push s nesprávnym zostatkom, SMS príde duplicitne a e-mail dorazí s chybným formátovaním sumy. Cieľ testovania: odhaliť nesprávne dáta, duplicity, meškanie, problémy s preferenciami a bezpečnosťou.<br><br>

## Ako otestovať:<br><br>

1. **Nastavenia a preferencie**<br>
– Aktivácia/deaktivácia kanálov (push/SMS/e-mail), prahy súm, tiché hodiny, jazyk a časové pásmo.<br>
– Predvolené nastavenia pri novom účte vs. migrované účty.<br>
– Zmena telefónneho čísla/e-mailu a okamžitý dopad na doručovanie.<br><br>

2. **Spúšťače udalostí**<br>
– Transakcie: platby kartou (online/offline), výbery z bankomatu, reverzácie, multicurrency, poplatky, trvalé príkazy, SEPA/medzibankové prevody.<br>
– Nepeňažné: prihlásenie, zmena limitov, pripojenie nového zariadenia, zamietnutie transakcie, podozrivá aktivita.<br>
– Hraničné hodnoty: presne 20,00 €, 19,99 €, 20,01 €; domáce vs. zahraničné meny.<br><br>

3. **Obsah a lokalizácia**<br>
– Korektné dáta: suma, mena, obchodník/MCC, čas, posledný zostatok, maskovaný IBAN/PAN.<br>
– Formáty: medzery v IBAN, oddeľovače desatinných čísel, kódovanie diakritiky.<br>
– Jazykové mutácie a fallback, šablónovanie podľa typu udalosti a verzie šablóny.<br><br>

4. **Doručenie a latencia**<br>
– SLA pre push, SMS a e-mail; meraj čas doručenia.<br>
– Offline/airplane mode: frontovanie push, doručenie po opätovnom pripojení.<br>
– Retry mechanizmy, fallback kanál (napr. SMS, ak push zlyhá).<br><br>

5. **Duplicitné a chýbajúce správy**<br>
– Idempotentné kľúče (unikátne ID transakcie), ktoré zabezpečia, že ak tá istá notifikácia príde viackrát, spracuje sa iba raz. Dedupikácia na klientoch/servery znamená, že aplikácia alebo backend podľa týchto kľúčov rozpozná duplicity a ignoruje ich.<br><br>
– Súhrnné e-maily na konci dňa vs. okamžité správy.<br>
– Záťažové testy pri špičke (výplaty, Black Friday).<br><br>

6. **Bezpečnosť a súlad**<br>
– Žiadne citlivé údaje v push preview na zamknutej obrazovke (konfigurovateľné).<br>
– Bezpečné odkazy: deep link vedie do aplikácie, ak web tak len HTTPS.<br>
– Ochrana proti phishingu: konzistentná doména/odosielateľ, DKIM/SPF/DMARC pre e-maily.<br>
– GDPR: odhlásenie z marketingu ≠ vypnutie bezpečnostných notifikácií.<br><br>

7. **Negatívne scenáre**<br>
– Neplatné/expirujúce FCM/APNS tokeny, plná SMS schránka, bounce e-mailu.<br>
– Zablokované číslo/antispam filter, roaming, zmena času (letný/zimný).<br>
– Rollback release: kompatibilita staršej app s novými šablónami.<br><br>

8. **Použiteľnosť**<br>
– Jasný text bez bankovej hantírky, krátky predmet e-mailu, čitateľný push.<br>
– Možnosť prekliku na detail udalosti a správa preferencií jedným ťukom.<br>
– História notifikácií v app, vyhľadávanie a filtrovanie.<br><br>

9. **Monitorovanie a observabilita**<br>
– Korelácia ID: transakcia ↔ notifikácia v logoch a v analytike.<br>
– Alerty na oneskorenie, nárast chýb, pokles doručiteľnosti.<br>
– A/B testovanie textov a prahov, meranie CTR a odhlásení.<br>
