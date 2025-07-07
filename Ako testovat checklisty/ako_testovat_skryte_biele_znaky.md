# Ako testovať skryté biele znaky<br><br>

Keď hovoríme o “skrytých bielych znakoch” (medzery, tabulátory, nezlomiteľné medzery a pod.), ide o vstupy, ktoré sú vizuálne prázdne, no môžu obchádzať validačné pravidlá (napr. keď používateľ zadá do povinného poľa iba pár medzier). Tu je, ako ich otestovať:<br>

1. **Jednoduché medzery**<br>

- Do každého textového poľa vložte napr. " " (4 obyčajné medzery).<br>
- Očakávanie: pole by sa malo považovať za “prázdne” a hlásiť chybu „Pole je povinné“.<br>

2. **Tabulátory**<br>

- Skopírujte znak tabulátora (↹) viackrát a vložte ho do poľa.<br>
- Očakávanie: rovnako ako medzery, validátor by mal trimovať alebo považovať vstup za neplatný.<br>

3. **Nezlomiteľné medzery ( )**<br>

- Vložte do poľa znak   (HTML nezlomiteľná medzera) alebo jeho Unicode ekvivalent U+00A0.<br>
- Očakávanie: aplikácia musí tieto znaky trimovať rovnako ako bežné medzery, resp. považovať za prázdne.<br>

4. **Kombinácie bielych znakov**<br>

- Skombinujte medzery, taby a nové riadky (\n, \r\n) do jedného reťazca a vložte ho.<br>
- Očakávanie: ak je pole povinné, musí hlásiť chybu; ak sú vstupy nepovinné, trimované hodnoty sa odosielajú ako prázdne.<br>

5. **Neviditeľné Unicode znaky**<br>

- Vyskúšajte “zero-width space” (U+200B) alebo „zero-width no-break space“ (U+FEFF).<br>
- Očakávanie: systém by mal tieto znaky odstrániť počas sanitizácie, aby sa predišlo zneužitiu (napr. v XSS útokoch) a zároveň neumožili vytvoriť “neviditeľný” vstup.<br>

6. **Automatizované testy**<br>

- V skriptoch (Selenium, Cypress) naprogramujte testy, ktoré do polí pošlú rôzne biele znaky a potom overia chybové hlásenia.<br>
- Overte, že API (ak existuje) tiež trimuje alebo validuje tieto znaky na serverovej strane.<br>

7. **Edge-case scenáre**<br>

- Vloženie bielych znakov okolo platných údajov: " John Doe " – malo by sa trimovať na "John Doe".<br>
- Vstupy pozostávajúce výhradne z bielych znakov a diakritiky (napr. č ) – validátor by mal najprv trimovať a potom kontrolovať, či zostáva nejaký platný text.<br><br>

Tým, že tieto scenáre otestujete, zabezpečíte, že formulár neakceptuje “prázdne” ale technicky ne-null vstupy, a zároveň správne spracuje legitímne údaje s okrajovými znakmi.<br>
