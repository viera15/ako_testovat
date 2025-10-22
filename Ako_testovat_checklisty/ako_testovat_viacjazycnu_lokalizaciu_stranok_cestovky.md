# Ako testovať viacjazyčnú lokalizáciu stránok cestovky<br><br>

Príklad<br>
Predstav si klienta z Rakúska, ktorý navštívi slovenskú stránku cestovnej kancelárie.  
Po zmene jazyka na nemčinu sa síce titulky preložia, ale ceny sa stále zobrazujú v eurách s formátom podľa slovenského štandardu (1 234,56 €) namiesto nemeckého (1.234,56 €).  
Navyše, pri rezervácii zájazdu sa v e-maile objaví mix jazykov: nadpis v nemčine, telo správy po slovensky a footer po anglicky.  
Takéto detaily pôsobia neprofesionálne a môžu viesť k zmäteniu či strate dôvery.  
Testovanie lokalizácie preto nie je len o prekladoch, ale aj o konzistentnosti – naprieč celým rezervačným procesom.  

<br><br>

## Ako otestovať

**1. Jazykové verzie a preklady**  
- Over, že všetky texty na stránke (`menu`, `tlačidlá`, `formuláre`, `chybové hlášky`) majú správnu jazykovú verziu.  
- Testuj aj obsah, ktorý sa načítava dynamicky (napr. popisy hotelov z `API` partnera).  
- Skontroluj fallback jazyk – ak chýba preklad, musí sa zobraziť predvolený text, nie *undefined*.  
- Over, že preklady sú gramaticky aj kultúrne primerané cieľovej krajine.  

<br>

**2. Formáty dátumu, času a čísiel**  
- Testuj formáty podľa lokalizácie: `12. 7. 2025` vs. `07/12/2025`; 24-hodinový vs. 12-hodinový formát.  
- Skontroluj číselné a menové formáty – poradie meny, oddeľovače, zaokrúhľovanie.  
- Over, že pri zmene jazyka sa automaticky mení aj formát (napr. anglický vs. francúzsky).  

<br>

**3. Dynamický obsah a API partnerov**  
- Ak cestovka čerpá popisy hotelov či zájazdov z externých zdrojov, over, že `API` vracia lokalizovaný text.  
- Testuj, čo sa stane, ak partner poskytuje len anglický popis – má sa použiť fallback alebo oznámenie *„Preklad nie je dostupný“*.  
- Over, že v exportoch (napr. `PDF` voucher, e-mail) sa zobrazí rovnaká jazyková verzia ako na webe.  

<br>

**4. Proces rezervácie**  
- Prejdi celý proces v každej jazykovej mutácii – od výberu termínu až po potvrdenie.  
- Sleduj, či sa počas prepínania jazyka nestrácajú zadané údaje alebo košík.  
- Otestuj texty v potvrdení, faktúre a notifikáciách – všetky musia byť v rovnakom jazyku ako pri objednávke.  

<br>

**5. SEO a meta údaje**  
- Over, že každá jazyková verzia má vlastné meta tagy (`title`, `description`, `hreflang`).  
- Skontroluj správne smerovanie odkazov – z nemeckej verzie nesmie viesť link na slovenskú.  
- Validuj `sitemap.xml` a `robots.txt` – musia obsahovať všetky jazykové verzie.  

<br>

**6. Používateľská skúsenosť (UX)**  
- Over, že texty sa nezalamujú alebo nepretekajú mimo tlačidiel pri dlhších prekladoch.  
- Skontroluj `RTL` jazyky (arabčina, hebrejčina) – zrkadlové rozloženie a smer písma.  
- Testuj, ako sa jazykové mutácie správajú na mobilných zariadeniach.  

<br>

**7. Testy e-mailov, voucherov a PDF výstupov**  
- E-mailové šablóny musia rešpektovať jazyk objednávky.  
- Skontroluj, že `PDF` potvrdenia, zmluvy a vouchery majú rovnakú lokalizáciu – vrátane diakritiky a formátu dátumov.  
- Over, že priložené dokumenty (napr. všeobecné podmienky) sú v správnom jazyku.  

<br>

**8. Automatizované testy a regresia**  
- Nastav testovacie skripty (napr. v `Selenium` alebo `Playwright`) pre kontrolu kľúčových slov na stránke.  
- Využi vizuálne regresné testy – porovnaj screenshoty medzi jazykmi, aby si odhalil posuny a rozbitý layout.
<br>