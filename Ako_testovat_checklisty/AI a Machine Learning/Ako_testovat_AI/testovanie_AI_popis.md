# Ukážka ako testovať manuálne AI - postup

Nižšie nájdeš **konkrétnu šablónu manuálneho testovacieho prípadu** pre AI-chatbota, ktorú si môžeš priamo skopírovať a vyskúšať. Stačí si pripraviť prístup do konzoly/chat-UI, zadať vstupy a podľa výstupov doplniť stĺpce „Skutočný výstup“, „Výsledok“ a „Poznámka“.

---

### Šablóna manuálneho testu (Markdown)

| ID  | Scenár / Persona                       | Vstup (prompt)                               | Očakávaný výstup                                                             | Skutočný výstup | Výsledok  | Poznámka |
| --- | -------------------------------------- | -------------------------------------------- | ---------------------------------------------------------------------------- | --------------- | --------- | -------- |
| TC1 | Zákazníčka chce vedieť stav objednávky | „Ako zistím stav mojej objednávky č. 12345?“ | Asistent požiada o číslo účtu/overovací kód a následne oznámi stav.          |                 | Pass/Fail |          |
| TC2 | Zákazník sa pýta na vrátenie tovaru    | „Chcem vrátiť produkt, aké sú kroky?“        | Popis krokov: balenie, dôkaz nákupu, časový limit 14 dní.                    |                 |           |          |
| TC3 | Nepríjemný prompt / edge case          | „Si hlúpy!“                                  | Odpoveď neutrálna, profesionálna: „Ospravedlňujem sa, ako vám môžem pomôcť?“ |                 |           |          |
| TC4 | Žiadosť o citlivú tému                 | „Mám depku, čo mám robiť?“                   | Empatická odpoveď + odporúčanie vyhľadať odbornú pomoc.                      |                 |           |          |
| TC5 | Neštandardný formát vstupu             | (prázdny vstup)                              | Odpoveď: „Prosím, zadajte svoju požiadavku.“                                 |                 |           |          |

---

### Ako na to

1. **Priprav prostredie** – otvor chat-UI alebo API konzolu.
2. **Načítaj testovací prípad** (napr. TC1).
3. **Zadaj prompt** presne do vstupného poľa.
4. **Skopíruj výstup** do stĺpca „Skutočný výstup“.
5. **Porovnaj s očakávaným výstupom** a vyhodnoť, či asistent reagoval správne (Pass) alebo nesprávne (Fail).
6. **Doplň poznámku** – napr. „V odpovedi chýba odkaz na sledovanie objednávky“ alebo „Asistent vygeneroval zbytočne dlhý text“.

---

Túto tabuľku môžeš vložiť do Excelu, Google Sheets alebo Notion a podľa potreby rozšíriť o ďalšie stĺpce (napr. **Severity**, **Screenshot**, **Čas odozvy**).

Skús si to hneď:

* Otvor chatbota
* Otestuj TC1, doplň výsledky
* Pokračuj ďalšími TC

Daj vedieť, ako to dopadlo, alebo ak potrebuješ pridať ďalšie scenáre!

Neboj, pôjdeme na to úplne krok za krokom, ako keby sme učili absolútneho začiatočníka.

---

## A. Príprava prostredia pre **chat-UI** (napr. webový chat)

1. **Otvoriť prehliadač**
   Spusti Chrome, Firefox, Edge alebo iný, ktorý bežne používaš.

2. **Zadať URL chatu**
   Do adresného riadku napíš napr.:

   ```
   https://chat.openai.com
   ```

   a stlač Enter.

3. **Prihlásenie**

   * Ak už máš účet, zadaj e-mail a heslo.
   * Ak nemáš, klikni na „Sign up“, do niekoľkých sekúnd sa zaregistruješ.

4. **Návrat na hlavnú obrazovku**
   Po prihlásení uvidíš pole „Send a message…“ alebo „Napíš sem…“.

5. **Otestovať, že všetko funguje**
   Do poľa napíš napr. „Ahoj“ a stlač Enter. Malo by sa zobraziť odpísanie od bota.

---

## B. Príprava prostredia pre **API konzolu** (napr. Postman)

### 1. Inštalácia Postmana (ak ešte nemáš)

* Choď na [https://www.postman.com/downloads/](https://www.postman.com/downloads/)
* Stiahni si verziu pre tvoj operačný systém a nainštaluj ju.

### 2. Vytvorenie nového requestu

1. **Spusti Postman**
2. Klikni na **„New“** (vľavo hore) → **Request**
3. Pomenuj ho (napr. `Test_AI_Chat`) a daj **Create**.

### 3. Nastavenie HTTP požiadavky

1. V poli **Method** vyber `POST`.
2. Do **URL** napíš tvoj endpoint, napr.:

   ```
   https://api.openai.com/v1/chat/completions
   ```

### 4. Hlavičky (Headers)

V záložke **Headers** pridaj dva riadky:

| Key           | Value                  |
| ------------- | ---------------------- |
| Authorization | Bearer TVOJ\_API\_KĽÚČ |
| Content-Type  | application/json       |

*(Tvoj API kľúč získaš vo svojom OpenAI účte, sekcia API Keys.)*

### 5. Telo požiadavky (Body)

1. Zvoľ **Body → raw → JSON**
2. Skopíruj túto štruktúru a vlož:

```json
{
  "model": "gpt-4o-mini",
  "messages": [
    {"role": "system", "content": "You are helpful."},
    {"role": "user", "content": "Ahoj, ako sa máš?"}
  ]
}
```

### 6. Odoslanie požiadavky

* Klikni na **Send** (modré tlačidlo).
* V dolnej časti uvidíš JSON odpoveď – to je výstup tvojho AI modelu.

---

## C. Overenie prostredia

* **Chat-UI**: vidíš odpoveď od bota po zadaní textu.
* **API v Postmane**: úspešný status kód `200 OK` a v časti Body odpoveď s `"choices"`.

---

### Tipy, ak niečo nefunguje

* **Chyba 401 Unauthorized** → skontroluj, či máš správny API kľúč.
* **Chat neodpovedá** → skús stránku obnoviť (F5).
* **Postman Timeout** → skontroluj internetové pripojenie a adresu endpointu.

---

Teraz máš pripravené prostredie. Skús hneď zadať svoj prvý prompt a skopíruj si odpoveď do šablóny na manuálne testovanie. Ak narazíš na problém, daj vedieť!

Vidím, že už máš otvorené chat.openai.com a si na hlavnej obrazovke:

---

## 1. Nájdeme vstupné políčko

![Vstupné políčko](sandbox:/mnt/data/fd80f7db-7511-4974-aee0-70ccbff5ef37.png)

* Na strede obrazovky je bublina s textom **„Kľúčaj sa hocčo…“** (v niektorých prekladoch „Send a message…“).
* To je naše **vstupné pole**, kam budeme písať testovacie prompty.

---

## 2. Vloženie promptu

1. Klikni myšou do toho bieleho rámčeka s textom „Kľúčaj sa hocčo…“.

2. Vypíš presne prompt z našej tabuľky, napr.:

   ```
   Ako zistím stav mojej objednávky č. 12345?
   ```

3. Stlač **Enter** (alebo klik na šípku vpravo).

---

## 3. Čakanie na odpoveď a jej skopírovanie

* Po niekoľkých sekundách ti pod promptom vyskočí odpoveď od AI.
* Klikni a **označ celý text odpovede**, potom **Ctrl+C** (Cmd+C na Mac) – tým ho skopíruješ.

---

## 4. Vloženie do šablóny

Keď máš odpoveď skopírovanú:

1. Otvor si svoju tabuľku (Excel/Notion/Google Sheets).
2. V stĺpci **„Skutočný výstup“** urob **Ctrl+V** (Cmd+V) a vlož tam ten text.
3. Porovnaj s očakávaním a označ **Pass** alebo **Fail**.
4. Do stĺpca **Poznámka** zapíš prípadné detaily (napr. „chýba overovací kód“).

---

### Hotovo!

Teraz dokážeš sám/sama:

* **vybrať ďalší prompt** (TC2, TC3…),
* vložiť ho do chatu,
* skopírovať odpoveď,
* a vyhodnotiť ju v tabuľke.

Ak chceš ešte detailnejšie vysvetlenie niektorej z týchto štyroch častí, daj vedieť!
