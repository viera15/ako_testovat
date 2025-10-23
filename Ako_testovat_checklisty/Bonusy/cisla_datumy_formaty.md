# Čísla, dátumy, formáty

## 1. Číselné formáty

### 1.1 Desatinné čísla
- **Slovenský spôsob:** používa **desatinnú čiarku**, napr. `3,14`
- **Anglosaský (americký):** používa **desatinnú bodku**, napr. `3.14`
- **Testovať:**
  - správna lokalizácia podľa jazykovej mutácie (sk → „,“ / en → „.“)
  - import/export medzi systémami (Excel, CSV, JSON)
  - zaokrúhľovanie pri konverzii formátov

### 1.2 Oddeľovanie tisícov
- **Slovensko/EÚ:** medzera ako oddeľovač – `1 234 567,89`
- **USA/UK:** čiarka ako oddeľovač – `1,234,567.89`
- **Alternatívy (technické formáty):** bez oddeľovača – `1234567.89`
- **Testovať:**
  - či sa číselné formáty nemenia pri exporte (napr. PDF vs. XLSX)
  - spracovanie čísel pri kopírovaní do polí formulára
  - validácia polí, ktoré nesmú obsahovať medzery

### 1.3 Znamienka, percentá, meny
- **Znamienka:** `+10 %`, `-5 %`, `+12,5 °C`
- **Meny (lokalizácia):**
  - Slovensko: `10,50 €`
  - USA: `$10.50`
  - Poľsko: `10,50 PLN`
- **Testovať:**
  - pozícia symbolu meny (pred/za číslom)
  - počet desatinných miest
  - zaokrúhľovanie cien (bankové zaokrúhlenie, matematické, smerom nahor)

---

## 2. Dátumy a časy

### 2.1 Štandardné formáty dátumu
| Lokalita | Formát | Príklad |
|-----------|---------|---------|
| Slovensko | DD.MM.YYYY | 11.10.2025 |
| EÚ (ISO) | YYYY-MM-DD | 2025-10-11 |
| USA | MM/DD/YYYY | 10/11/2025 |

**Testovať:**
- správne zoradenie dátumov podľa lokalizácie
- validáciu neexistujúcich dátumov (31.02., 29.02. v neprestupnom roku)
- export/import medzi systémami (napr. `2025-10-11` → `11.10.2025`)

### 2.2 Formáty času
| Typ | Príklad | Poznámka |
|------|----------|-----------|
| 24-hodinový | 14:35 | používaný v EÚ |
| 12-hodinový | 2:35 PM | používaný v USA |
| S milisekundami | 14:35:12.458 | pre logy a databázy |
| ISO formát | 2025-10-11T14:35:00Z | univerzálny v API |

**Testovať:**
- správne prepočty medzi 12/24h formátom
- konverziu časových pásiem (UTC ↔ CET)
- zobrazenie času pri prechode na letný/zimný čas

---

## 3. Časové pásma

| Skratka | Popis | Posun od UTC |
|----------|--------|---------------|
| UTC | Koordinovaný svetový čas | ±0 |
| CET | Central European Time | +1 |
| CEST | Central European Summer Time | +2 |
| EST | Eastern Standard Time | -5 |
| PST | Pacific Standard Time | -8 |

**Testovať:**
- zobrazovanie správneho lokálneho času používateľa
- logovanie udalostí v UTC (audit trail)
- výpočty trvania medzi časmi v rôznych pásmach

---

## 4. Typografické prvky a znaky

### 4.1 Úvodzovky
| Jazyk | Otváracie/Zatváracie | Príklad |
|--------|------------------------|----------|
| Slovenské | „ “ | „Text v úvodzovkách“ |
| Český variant | „ “ | „Text“ |
| Anglické | “ ” alebo ' ' | “Text” alebo 'Text' |

**Testovať:**
- automatickú zámenu rovnakých úvodzoviek ( " " → „ “ )
- správne uzatváranie párov
- kompatibilitu pri exporte do HTML, PDF, JSON

### 4.2 Pomlčky a spojovníky
| Typ | Znak | Použitie | Príklad |
|------|------|-----------|----------|
| Spojovník | - | spojenie slov | česko-slovenský |
| En-dash | – | rozsahy | 10–20 hodín |
| Em-dash | — | oddeľovanie myšlienky | Všetko — okrem detailov — bolo jasné. |

**Testovať:**
- automatickú konverziu pomlčiek v textovom editore
- správne zobrazenie vo výstupe (HTML, PDF)

### 4.3 Zátvorky a iné párové znaky
| Typ | Znak | Príklad |
|------|------|----------|
| Okrúhle | ( ) | (poznámka) |
| Hranaté | [ ] | [voliteľný parameter] |
| Zložené | { } | {JSON objekt} |
| Uvozovky | „ “ | „text“ |
| Úkosové | ‹ › | ‹citát› – typografické použitie |

**Testovať:**
- párové uzatváranie zátvoriek
- správne escapovanie v kóde a regexoch
- zobrazenie v exportoch (napr. JSON, XML)

---

## 5. Ďalšie špecifiká formátov

- **Dátumy s názvami mesiacov:** 11. október 2025 vs. October 11, 2025  
- **Časové intervaly:** `od 10:00 do 12:30`, `10:00–12:30`
- **Telefonické čísla:** +421 905 123 456 / (0905) 123 456  
- **Adresy:** Ulica 12, 811 01 Bratislava vs. 12 Street, Bratislava 81101  
- **E-maily:** kontrola veľkých/malých písmen v doméne (nerozlišujú sa)  
- **URL:** rozlíšenie medzi `http://`, `https://`, `ftp://`

---

## 6. Zhrnutie pre testera

Pri testovaní formátov údajov sa zamerať na:
1. **Lokalizáciu (i18n/L10n):** či aplikácia rozpozná krajinu/jazyk používateľa.
2. **Konzistentnosť:** rovnaký formát na všetkých obrazovkách, výstupoch a exportoch.
3. **Validáciu:** vstupné polia akceptujú len správny formát podľa jazyka.
4. **Konverziu:** pri prechode medzi systémami sa formát nesmie poškodiť.
5. **Zobrazenie:** správna typografia vo výstupoch (úvodzovky, pomlčky, symboly).


# Porovnanie typov míľ

## 1. Základné typy

| Typ míle | Použitie | Dĺžka v kilometroch | Dĺžka v metroch | Poznámky |
|-----------|-----------|---------------------|-----------------|-----------|
| **Statútová (anglická, imperial mile)** | Veľká Británia, USA (bežné vzdialenosti) | **1,609344 km** | 1 609,344 m | Základný typ, používaný v cestnej doprave, GPS v USA. |
| **Americká míľa** | USA, dopravné značenie, šport | **≈ 1,609344 km** | 1 609,344 m | Rovnaká ako britská, líši sa len historicky názvom. |
| **Námorná míľa (nautical mile)** | Lodná a letecká navigácia | **1,852 km** | 1 852 m | Odvodená od 1 oblúkovej minúty zemepisnej šírky. Používa sa v GPS, mapách, letectve. |
| **Geografická míľa (geographical mile)** | Zemepisné výpočty, kartografia | **1,8553 km** | 1 855,3 m | Založená na dĺžke jednej oblúkovej minúty po rovníku. |
| **Talianska míľa (miglio italiano)** | Historická, antická | **1,479 km** | 1 479 m | Používaná v antickom Ríme; rôzne lokálne verzie. |
| **Škandinávska míľa („mil“) ** | Švédsko, Nórsko (moderná verzia) | **10 km** | 10 000 m | Dnes oficiálne definovaná ako 10 km, používa sa v hovorovej reči a bežeckých pretekoch. |
| **Rímska míľa (mille passus)** | Staroveký Rím | **1,479 km** | 1 479 m | „Tisíc krokov“ (1 000 × dvojkrok), základ mnohých historických definícií. |

---

## 2. Prepočty

- **1 námorná míľa = 1,15078 statútovej míle**  
- **1 statútová míľa = 0,8684 námornej míle**  
- **1 míľa ≈ 1,61 km**  
- **1 km ≈ 0,621 míle**

---

## 3. Kde sa používajú

| Oblasť | Používaná míľa | Príklad |
|---------|----------------|----------|
| **Cestná doprava (USA, UK)** | Statútová / americká | vzdialenosť Los Angeles – San Diego: ~ 120 mi |
| **Letecká a námorná navigácia** | Námorná | vzdialenosť prepočítaná z GPS súradníc |
| **Škandinávia (hovorovo)** | Škandinávska (10 km) | „Bežal som 1 mil“ = 10 km |
| **Historické merania** | Rímska, talianska | archeologické a kartografické pramene |

---

## 4. Zhrnutie

Pri testovaní a konverziách v systémoch (GIS, letecké plány, športové aplikácie) je dôležité rozlišovať, aký typ míle systém používa.  
Rozdiel medzi statútovou a námornou míľou predstavuje až **15 % odchýlku**, čo môže významne ovplyvniť výpočty vzdialeností.


