# Exotické meny

---

## Nulové desatinné miesta (žiadne „centy“)
JPY (japonský jen), KRW (kórejský won), VND (vietnamský dong), IDR (indonézska rupia), CLP (chilské peso), PYG (paraguajský guaraní), UGX, RWF, VUV, XAF/XOF/XPF a pod.  
- tieto meny sa často spracúvajú bez desatinných miest. *(docs.payments.stonex.io)*

---

## Trojmiestne desatinné (3 decimal places)
KWD (kuvajtský dinár), BHD (bahrajnský dinár), JOD (jordánsky dinár), OMR (ománsky rial), LYD (libyjský dinár), TND (tunisijský dinár), IQD (iracký dinár).  
- pri týchto menách sa bežne počíta s tromi desatinnými miestami. *(Wikipedia)*

---

## Nie sú-desatinné / „ne-decimálne“ (5:1)
MRU (mauritánska ouguiya) a MGA (malgašský ariary).  
- tieto majú tradične podjednotky v pomere 5:1 (napr. „khoum“ alebo „iraimbilanja“) a preto treba so zápisom/správami zaobchádzať opatrne. *(Wikipedia)*

---

## Ďalšie, na ktoré si dať pozor
Niektoré služby / PSP (payment providers) očakávajú, že aj nulodesatinné meny budú pri zasielaní v „minor units“ (t.j. ako integer — cents), alebo naopak — budú mať odlišné požiadavky.  
- preto si over formát u každého integračného partnera. *(docs.adyen.com)*

---

## Krátke praktické testovacie tipy (čo konkrétne overiť)
- Validácia formátu a počet desatinných miest pri vstupe/výstupe (UI, API, DB).  
- Ukladaj interné sumy ako integer „minor units“ podľa ISO 4217 (ale over, či tvoj PSP očakáva iné). *(ISO)*  
- Rounding/zaokrúhľovanie: testuj bankové pravidlá pre JPY/IDR vs KWD/BHD (iný počet desiatin = iné zaokrúhľovanie).  
- Negatívne scenáre: čo keď používateľ zadá 2 desatinné miesta pre JPY alebo 4 pre KWD — systém musí korektne zamietnuť alebo normalizovať.  
- Reprodukcia a logovanie: ulož request/response s použitým počtom desatinných miest a timestampom, aby si vedela riešiť reklamácie.  
- Integrácia so zmenárňami/FX-API: over, či FPS/PSP vracajú kurzy a amounts v rovnakom formáte (minor/major units). *(docs.adyen.com)*
