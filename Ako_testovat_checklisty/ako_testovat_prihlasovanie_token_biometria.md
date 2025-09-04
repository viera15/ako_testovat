# Ako testovať prihlasovanie pomocou mobilného tokenu alebo biometrie<br><br>

Predstavte si mobilnú bankovú aplikáciu, kde sa zákazník neprihlasuje heslom, ale potvrdí vstup buď odtlačkom prsta, rozpoznaním tváre, alebo jednorazovým kódom cez mobilný token. Tento spôsob je dnes bežný v bankovníctve – heslo je slabé miesto, biometria či token výrazne zvyšujú bezpečnosť.<br><br>

## Ako to otestovať?<br><br>

1. **Základné scenáre**<br>
- Over, či funguje úspešné prihlásenie pomocou všetkých podporovaných metód (biometria – odtlačok prsta, tvár; mobilný token – jednorazový kód).<br>
- Skontroluj, že aplikácia korektne reaguje aj pri nesprávnych vstupoch (odmietnutý odtlačok, chybný kód).<br><br>

2. **Bezpečnosť**<br>
- Otestuj počet pokusov: po viacerých neúspešných overeniach musí aplikácia zablokovať prihlásenie alebo vyžadovať iný postup.<br>
- Skontroluj, či tokeny/kódy nie je možné použiť opakovane.<br>
- Pri biometrickom prihlasovaní over, že sa nedá obísť napr. fotkou alebo videom.<br><br>

3. **Zariadenie a prostredie**<br>
- Skús prihlásenie na rôznych verziách operačných systémov (Android/iOS).<br>
- Over, ako sa správa aplikácia po reštarte telefónu, zapnutí/vypnutí letového režimu, alebo pri slabom internete.<br>
- Skontroluj, čo sa stane pri zmene nastavení biometrie v telefóne (zmazanie odtlačku, pridanie nového).<br><br>

4. **Použiteľnosť**<br>
- Pri biometrickom prihlasovaní otestuj, či aplikácia jasne informuje používateľa, keď je odtlačok alebo tvár neprijatá.<br>
- Skontroluj, že pri problémoch je vždy dostupná alternatívna metóda (napr. PIN alebo heslo).<br>
- Over, či sa tokeny doručujú rýchlo a čitateľne (napr. push notifikácia, SMS).<br><br>

5. **Negatívne scenáre**<br>
- Čo ak používateľ stratí prístup k biometrickým údajom (poškodený senzor, poranený prst)?<br>
- Čo ak mobil nemá pripojenie k internetu a token sa nedá overiť online?<br>
- Čo ak dôjde k oneskoreniu doručenia tokenu?<br><br>

Testovanie prihlasovania cez token či biometriu vyžaduje kombináciu funkčných, bezpečnostných a negatívnych testov. Ide o oblasť, kde je nevyhnutná dôslednosť – aj malá chyba môže znamenať veľké bezpečnostné riziko.<br>
