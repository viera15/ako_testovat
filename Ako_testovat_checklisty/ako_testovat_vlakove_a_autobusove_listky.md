# Ako testovať vlakové a autobusové lístky (miestenky, e-tikety)

Príklad
Predstav si, že používateľ si kupuje lístok z Bratislavy do Košíc s miestenkou.  
Po zaplatení dostane e-ticket e-mailom, no na miestenke má uvedené *„miesto 0“*.  
Po príchode do vlaku zistí, že miesto neexistuje.  
Zákazník podá reklamáciu a dopravca musí riešiť nielen vrátenie peňazí, ale aj reputačný problém.  
Takéto situácie vznikajú, keď sa neotestuje párovanie medzi predajným systémom a rezervačným modulom dopravcu.

## Ako otestovať

1. **Základné scenáre nákupu**
- Nákup jednosmerného, spiatočného a lístka s viacerými prestupmi (napr. **Bratislava – Žilina – Košice**).  
- Kombinácia dopravcov (napr. **ZSSK + Leo Express**).  
- Kontrola cien, zliav a typov taríf (študent, senior, dieťa).

2. **Rezervácia miesteniek**
- Over, že voľné miesta sa aktualizujú v reálnom čase.  
- Otestuj výber konkrétneho miesta (okno/chodba, 1. alebo 2. trieda).  
- Pri plnej kapacite sa miestenka nedá pridať — systém má zobraziť správnu chybovú správu.

3. **Generovanie e-ticketu**
- Kontrola údajov (názov stanice, dátum, čas, číslo spoja, QR alebo čiarový kód).  
- Formát PDF alebo mobilného zobrazenia.  
- Jazykové mutácie (napr. SK, EN, DE) podľa nastavení používateľa.

4. **Integrácia s platobnou bránou**
- Simuluj úspešnú aj neúspešnú platbu.  
- Over reakciu systému po prerušení platby (či sa lístok negeneruje).  
- Testuj duplicitné platby a refundácie.

5. **Kontrola a validácia lístkov**
- Testuj skener QR kódu v aplikácii revízora.  
- Over, že lístok sa dá načítať aj offline (bez pripojenia).  
- Kontroluj časovú platnosť a zneplatnenie po použití.

6. **Zmeny a storno**
- Prebookovanie na iný spoj alebo dátum.  
- Over, či sa správne aktualizuje miestenka.  
- Výpočet storno poplatku a generovanie refundácie.

7. **Testovanie offline režimu a mobilných zariadení**
- Správanie aplikácie bez internetu.  
- Synchronizácia po opätovnom pripojení.  
- Kompatibilita s Android/iOS a rôzne rozlíšenia displeja.

8. **Výkonnosť a spoľahlivosť systému**
- Testuj špičky (napr. pred sviatkami alebo v pondelok ráno).  
- Súbežné rezervácie na posledné miesto.  
- Odolnosť pri výpadku integrácie (rezervačný systém ↔ platobná brána).
