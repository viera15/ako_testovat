Ako testovať generovanie mesačných výpisov


Klientovi neprišiel augustový výpis. Po prihlásení do internetbankingu ho síce vidí, ale v PDF chýba posledných 6 platieb a úvodný zostatok nesedí o 0,23 €. Príčina? Dávkový proces bežal ešte pred uzávierkou, cron sa kvôli letnému času posunul o hodinu a konverzia CZK→EUR zaokrúhlila inak v exporte než v účtovníctve. Tento mix drobností stačil na reklamáciu.

Ako otestovať (praktické kroky)

Uzávierka a plánovanie

Over čas uzávierky (cut-off), časové pásmo a prechod na letný/zimný čas.

Spusť generovanie ručne aj plánovane (cron/scheduler), sleduj opakované pokusy pri zlyhaní.

Kompletnosť dát

Porovnaj výpis vs. hlavná kniha: počet položiek, sumy, poplatky, úroky.

Skontroluj transakcie v hraničných časoch (23:59:59, 00:00:00), reverzácie/chargebacky (zrušené alebo reklamované platby).

Zostatky a výpočty

Over vzorec: počiatočný stav + obraty = koncový stav.

Testuj viac mien (ISO 4217), kurzy, zaokrúhľovanie a fixné/percentuálne poplatky.

Formát a obsah výpisu

PDF/CSV/MT940/Excel: čitateľnosť, poradie stĺpcov, hlavičky, kódovanie, diakritika.

Lokalizácia: jazyk, dátum, tisícky/desatinná čiarka, symbol meny.

Identifikácia: číslo výpisu, IBAN/BIC, názov účtu, obdobie, stránkovanie, QR/čiarový kód.

Filtre a segmentácia

Účet bez pohybov (nulový výpis).

Veľa pohybov (stránkovanie, veľkosť súboru, limit riadkov).

Filtrovanie podľa produktu (bežný účet, karta, sporiaci).

Distribúcia a doručenie

Inbox v app/web: dostupnosť, rýchlosť, link s expiráciou.

E-mail: predmet, preposielanie, DKIM/SPF (ochrana e-mailov, podpis a povolené servery), príloha vs. odkaz, bounce scenáre.

Notifikácie (push/SMS) a opakované poslanie.

Bezpečnosť a súlad

Maskovanie citlivých údajov, GDPR (meno/adresa), vodoznak „Kópia“.

Podpis/pečať PDF (PAdES), kontrola integrity, verzovanie výstupov.

Právne náležitosti: over, či výpis obsahuje povinné disclaimery (právne doložky a upozornenia), logo, kontakty a identifikáciu banky.

Archív a re-generácia

Dostupnosť historických výpisov, SLA načítania (dohodnutý čas načítania výpisov), verzia šablóny.

Re-run pre minulé obdobie (oprava kurzov/bugfix) a audit trail zmien.

Výkon a odolnosť

Load test pre koniec mesiaca (n-tisíc výpisov naraz).

Zlyhania: nedostatok miesta, výpadok šablónového servera, retry/backoff, čiastkové generovanie a report chýb.

Monitoring a audit

Logy s korelačným ID, metriky (počet/čas zbehu/zlyhania), alerty.

Export kontrolného zoznamu (checklist) do test plánu/regresie.



#testing #qa #banking #fintech #reporting #datavalidation #automation #security #compliance #ux



