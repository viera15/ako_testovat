Ako testovať zahraničné platby v rôznych menách (vrátane „exotických“)

Príklad 
Predstav si, že klient zadá platbu v CZK, systém ju prevedie do EUR so zlým zaokrúhlením — príjemca dostane o pár centov menej, zákazník volá na support a reputácia trpí. Testovanie zahraničných platieb nie je len o „odoslať peniaze“ — ide o kurzy, poplatky, formáty, settlement a súlad s legislatívou.

Ako testovať (praktické kroky)

Základná validácia polí
• Over IBAN/BBAN, SWIFT/BIC a lokálne čísla účtov pre cieľové krajiny.
• Validuj menu podľa ISO 4217 a povolené kombinácie (mena pár).

Scenáre s kurzami (FX)
• Testuj rôzne kurzy: spot, bankový spread, fixné zmluvné kurzy.
• Over presnosť a zaokrúhľovanie (decimály, rounding mode).
• Simuluj rate expiry — čo ak sa kurz zmení pred settlementom?

Poplatky a rozdelenie (SHA/BEN/OUR)
• Over správne účtovanie poplatkov (národná banka, correspondent bank, príjemca).
• Testuj kumulované poplatky cez correspondent chain.

Limity a bezpečnosť (AML, fraude)
• Testuj denné/mesačné limity podľa meny.
• Scenáre pre AML/watchlist/PEP — blokovanie alebo eskalácia.
• Velocity checks, rate-limit a anti-fraud pravidlá.

Settlement, cutoffy a časové okná
• Platby po cutoff time, rozdiely v pracovných dňoch, víkendy a sviatky prijímateľských/odosielateľských krajín.
• Testy D+N pravidiel pre rôzne clearingy.

Formáty správ (SWIFT/MT ↔ ISO20022)
• Over mapovanie polí medzi formátmi (MT103 ↔ pain.001/pacs.008).
• Negatívne testy: chýbajúce povinné pole, zlé mená, zlé kódovanie.

Edge-cases mien
• Nulové desatinné meny (JPY, KRW, VND…), trojdesatinné (KWD, BHD…), ne-decimálne podjednotky (MRU, MGA).
• Scenáre “currency not supported”, refundy a reject flows.

Fallbacky a idempotentnosť
• Simuluj výpadok FX API — last known rate + notifikácia.
• Testuj retry, idempotency keys a správanie pri duplicitách.

Korešpondenčné banky a routing
• Over vyplnenie routing fields, correspondent details a započítanie intermediárnych poplatkov.
• Scenáre, keď correspondent odmietne transakciu.

Notifikácie, reporting a rekonciliácia
• Stavové notifikácie (pending/settled/rejected).
• GL entries, reporty, audit trail a metriky (počet reklamácií, čas do settlementu).

Výkonnosť, sieť a obnoviteľnosť
• Batchy SEPA/SWIFT, špičky, latencia volaní na FX a banky.
• Partial failures, timeouty, rollbacky — žiadne „visace“ transakcie bez stavu.

Testovacie prostredia a automatizácia
• Používaj sandboxy, separované test účty a anonymizované produkčné vzorky.
• Automatizované e2e testy API + DB reconciliácia + manuálne exploratory scenáre.

Dokumentácia
• Zaznamenaj reproducovateľné kroky, použité kurzy, UTC timestampy a request/response payloady.



#banking #payments #fx #qa #testing #compliance #fintech



