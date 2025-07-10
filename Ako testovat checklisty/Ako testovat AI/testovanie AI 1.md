**Testovanie AI (umelej inteligencie)** sa líši od klasického testovania softvéru hlavne tým, že výsledok nie je vždy jednoznačný a očakávaný výstup môže byť do istej miery „približný“ alebo „pravdepodobný“. Napriek tomu existujú overené prístupy, ako testovať AI systematicky:<br><br>
________________________________________
🔹 1. Typy AI, ktoré testujeme<br>
Najčastejšie testované sú:<br>
•	ML modely (napr. klasifikátory, regresné modely)<br>
•	Generatívne modely (napr. ChatGPT, DALL·E)<br>
•	Rekognícia/rozpoznávanie (napr. OCR, hlas, obraz)<br>
•	Rekordéry a odporúčacie systémy<br><br>
________________________________________
🔹 2. Dôležité oblasti testovania AI<br>
Oblasť	Popis<br>
Funkčnosť (Functionality)	AI model robí to, čo má (napr. predikuje triedu správne)<br>
Presnosť (Accuracy)	Aká je miera správnych predikcií/testov<br>
Robustnosť (Robustness)	Ako model reaguje na šum, neštandardné vstupy<br>
Zaujatosti (Bias & Fairness)	Či model nefavorizuje určité skupiny<br>
Výkon (Performance)	Latencia, využitie CPU/GPU, pamäť<br>
Interpretovateľnosť	Dôvody rozhodnutia modelu (napr. SHAP, LIME)<br>
Bezpečnosť (Security)	Odolnosť voči manipulácii vstupov (napr. adversarial attacks)<br><br>
________________________________________
🔹 3. Konkrétne techniky testovania<br>
✅ Jednotkové testy a integrácia:<br>
•	Testovanie jednotlivých komponentov (napr. predspracovanie, predikcia).<br>
•	Napr. pomocou pytest v Pythone.<br>
✅ Testovacie datasety:<br>
•	Oddelenie tréningového, validačného a testovacieho datasetu.<br>
•	Používaj benchmarkové sady (napr. MNIST, CIFAR, SQuAD).<br>
✅ Golden test cases (očakávané vstup/výstup):<br>
•	Pri rovnakom vstupe očakávame konzistentné a zmysluplné výstupy.<br>
•	Vhodné hlavne pre NLP alebo generatívne AI.<br>
✅ Metamorfické testovanie:<br>
•	Testovanie konzistencie modelu pri zmenách vstupu, ktoré by nemali ovplyvniť výstup.<br>
•	Príklad: ak vetu "Pes beží." nahradíme za "Pes beží rýchlo.", mala by sa zachovať kategória Zvieratá.<br>
✅ Exploratory testing:<br>
•	Skúšanie modelu „na slepo“ s rôznymi vstupmi na odhalenie nečakaných chýb.<br>
✅ Automatizované testy:<br>
•	V prostredí, ako je Selenium + PyTest, možno testovať aj frontend výstupy AI systémov.<br><br>
________________________________________
🔹 4. Metriky pre hodnotenie AI modelov<br>
Typ úlohy	Metodika hodnotenia<br>
Klasifikácia	Accuracy, Precision, Recall, F1-score<br>
Regresia	RMSE, MAE, R²<br>
NLP (texty)	BLEU, ROUGE, perplexity<br>
Generatívne AI	Human eval., similarity, hallucination rate<br>
Recommenders	Precision@k, Recall@k, NDCG<br>
________________________________________
🔹 5. Ako testovať etiku a zaujatosti<br>
•	Zbieraj demografické dáta (ak sú povolené) na analýzu fairness.<br>
•	Over, či model nemá systematickú odchýlku (napr. častejšie nesprávne výstupy pre isté menšiny).<br>
•	Simuluj rôzne typy používateľov pomocou testovacích person.<br><br>
________________________________________
Ak mi povieš, aký konkrétny AI systém chceš testovať (napr. klasifikátor chorôb, chatbot, obrazová analýza), môžem navrhnúť presnejší testovací plán alebo ukážku testov v Pythone. Chceš?<br>
Skvelé! Tu je stručný a prehľadný úvod do testovania AI, ktorý ti pomôže pochopiť, v čom je testovanie AI iné než testovanie bežných softvérových systémov:<br><br>
________________________________________
🧠 Čo je špecifické pre testovanie AI?<br>
1. Nevieš vždy presne, čo očakávať<br>
•	V klasickom testovaní: ak zadám A, očakávam výstup B.<br>
•	V AI: výstup je často pravdepodobný, nie deterministický.<br>
o	Napr. pre rovnaký vstup môžu byť 2 „správne“ odpovede.<br><br>
________________________________________
2. Testuješ nielen funkciu, ale aj správanie modelu<br>
•	AI systém môže byť „formálne správny“, ale stále dávať nevhodné alebo neetické výstupy.<br>
•	Hodnotí sa aj kvalita, vhodnosť, zrozumiteľnosť a férovosť výstupu.<br><br>
________________________________________
3. Výsledky ovplyvňuje tréningový set<br>
•	Chyby v údajoch → chyby v predikciách.<br>
•	Preto musíš testovať aj kvalitu dát (napr. zaujatosť, chýbajúce hodnoty, duplicity).<br><br>
________________________________________
4. Zohľadňuješ metriky špecifické pre AI<br>
•	Napr. accuracy (presnosť), recall (zachytenie), F1-score (vyváženie presnosti a zachytenia).<br>
•	Pre generatívne modely (ako GPT) sa často robí subjektívne hodnotenie výstupu (ľudské hodnotenie alebo heuristiky).<br>
________________________________________
🧪 Typy testov, ktoré sa používajú<br>
| Typ testu	| Cieľ testu|
| --- | --- |
| Jednotkové testy	| Fungujú jednotlivé časti kódu správne? |
| Testovacie datasety	| Ako dobre model predikuje na nových dátach? |
| Metamorfické testy	| Zostáva výstup stabilný pri miernych zmenách vstupu? |
| Robustnosť	| Ako reaguje model na „divné“ alebo chybné vstupy? |
| Fairness	| Správa sa rovnako ku všetkým typom používateľov? |
________________________________________
🧰 Čo používaš pri testovaní AI<br>
•	Python + PyTest – bežné pre ML systémy.<br>
•	MLFlow, Weights & Biases – na sledovanie experimentov.<br>
•	Selenium – ak testuješ výstup AI v GUI.<br>
•	SHAP/LIME – na vysvetlenie výstupu modelu.<br><br>
________________________________________
Ak ti to pomohlo, môžeme nabudúce rozobrať:<br>
•	Ako písať testovacie prípady pre AI<br>
•	Ako spraviť baseline testovanie modelu<br>
•	Ako nastaviť metriky pre hodnotenie modelu<br>
•	Ako automatizovať testovanie výstupov<br><br>
Stačí povedať, čo ťa zaujme.<br>
Výborne! Písanie testovacích prípadov pre AI je trochu odlišné od klasických systémov – vyžaduje kombináciu technického myslenia, štatistiky a empatie k používateľovi.<br><br>
________________________________________
🧾 1. Čo je testovací prípad pre AI?<br>
Je to jasne definovaný vstup, očakávaný (alebo prijateľný) výstup a kritérium úspešnosti, ktoré určuje, či model reaguje správne.<br>
V prípade AI ale výstup často nie je jednoznačný → preto sa pracuje s:<br>
•	očakávaným rozsahom výsledkov<br>
•	pravdepodobnosťami<br>
•	akceptačnými metrikami<br>
________________________________________
🧠 2. Základná štruktúra testovacieho prípadu pre AI<br>
| Pole	            | Príklad|
| --- | --- |
| Názov prípadu	    | Test_NLP_Klasifikácia_pozitívneho_textu |
| Vstup	            | Text: „Milujem tento produkt, bol úžasný!“ |
| Očakávaný výstup	| Trieda: „pozitívne“ |
| Typ testu	        | Klasifikácia / Metamorfický / Robustnosť / Výkon |
| Kritérium úspechu	| Presnosť >= 90 % alebo výstup ∈ [pozitívne, neutrálne] |
| Dôvod testu	    | Overenie schopnosti rozpoznať sentiment v pozitívnom texte | 
________________________________________
🧪 3. Typy testovacích prípadov pre AI<br>
🟢 A. Klasické vstup-výstup testy<br>
•	Vhodné pre klasifikáciu, regresiu, odporúčanie.<br>
•	Overuješ, že AI model pri určitých vstupoch vráti správnu kategóriu/hodnotu.<br><br>


```
def test_sentiment_positive():
    vstup = "Toto je najlepší produkt, aký som kedy mal!"
    vystup = sentiment_model.predict(vstup)
    assert vystup == "pozitívne" 
```
<br>

________________________________________
🟡 B. Metamorfické testy<br>
•	Meníš vstup tak, že by nemal ovplyvniť výstup.<br>
•	Napr. pridáš zbytočné slovo, zmeníš poradie slov, nahradíš synonymá.<br><br>

```
def test_sentiment_synonym():
    vstup1 = "Milujem tento výrobok"
    vstup2 = "Zbožňujem tento výrobok"
    assert model.predict(vstup1) == model.predict(vstup2)
```
<br>

________________________________________
🔴 C. Robustnostné testy (edge cases)<br>
•	Zadávaš modelu zmätočné, neúplné alebo nezmyselné vstupy.<br><br>

```
def test_sentiment_empty_input():
    vstup = ""
    with pytest.raises(ValueError):
        model.predict(vstup)
```
<br>

________________________________________
🔵 D. Testy zaujatosti (bias/fairness)<br>
•	Overuješ, či sa model správa férovo k rôznym demografickým skupinám.<br><br>

```
def test_gender_bias():
    vstup_muz = "He is a brilliant scientist."
    vstup_zena = "She is a brilliant scientist."
    assert abs(score(vstup_muz) - score(vstup_zena)) < 0.1
```
<br>

________________________________________
🟣 E. Testy výkonnosti<br>
•	Napr. meranie rýchlosti odpovede modelu.<br><br>

```
def test_prediction_time():
    start = time.time()
    model.predict("Aký bude zajtra deň?")
    elapsed = time.time() - start
    assert elapsed < 0.5  # sekundy
```
<br>

________________________________________
📌 4. Odporúčania<br>
•	Používaj realistické vstupy – čím bližšie k produkcii, tým lepšie.<br>
•	Pridaj metriky (presnosť, recall, F1) – nie len „áno/nie“.<br>
•	Zaznamenávaj aj výsledky mimo očakávania (false positives/negatives).<br>
•	Pravidelne aktualizuj testy, najmä ak sa mení tréningový dataset.<br><br>
________________________________________
Ak chceš, môžem ti pripraviť aj šablónu testovacích prípadov vo forme tabuľky alebo YAML/JSON pre automatizované spracovanie. Alebo ukážku v rámci projektu so Seleniom či PyTestom. Čo by sa ti hodilo?<br>
Nastavenie metrík pre hodnotenie modelu je kľúčové pre správne testovanie AI, pretože ti umožní objektívne zhodnotiť, či model spĺňa očakávania – a ak nie, čo treba zlepšiť.<br>
________________________________________
📐 1. Krok po kroku: ako nastaviť metriky<br>
    🔹 1. Urči, aký typ úlohy riešiš:<br>
        Každý typ AI modelu používa iné metriky:<br>
| Typ úlohy       | Príklady                   | Vhodné metriky                                     |
|-----------------|----------------------------|----------------------------------------------------|
| Klasifikácia    | Spam/ham, sentiment        | Accuracy, Precision, Recall, F1-score, ROC AUC     |
| Regresia        | Predikcia cien, dopyt      | MSE, RMSE, MAE, R²                                 |
| NLP generovanie | Preklady, sumarizácie      | BLEU, ROUGE, METEOR, Perplexita                    |
| Odporúčanie     | Čo si kúpi používateľ      | Precision@k, Recall@k, NDCG                        |
| Klastrovanie    | Zoskupenie zákazníkov      | Silhouette score, Davies–Bouldin index             |

________________________________________
🔎 2. Najčastejšie metriky a ich význam<br>
✅ Klasifikácia (napr. "áno/nie")<br>
| Metrika	        | Vysvetlenie |
|----------------|-------------|
| Accuracy	        | Koľko predikcií bolo správnych (celkovo)? |
| Precision	        | Z tých, čo model označil ako „pozitívne“, koľko ich skutočne bolo pozitívnych? |
| Recall	        | Z tých, čo sú naozaj pozitívne, koľko ich model zachytil? | 
| F1-score	        | Harmonický priemer presnosti a zachytenia – vhodný pri nevyvážených dátach. |
| ROC AUC	        | Ako dobre model rozlišuje medzi triedami pri rôznych prahoch. |
📝 Použi napr. from sklearn.metrics import accuracy_score, f1_score<br><br>
________________________________________
✅ Regresia (napr. predikcia ceny)<br>
| Metrika	        | Vysvetlenie |
|----------------|-------------|
| MAE	            | Priemerná absolútna odchýlka predikcie od reality |
| MSE	            | Priemer štvorcov rozdielov (trestá veľké chyby) |
| RMSE	            | Druhá odmocnina MSE, interpretuje sa v pôvodných jednotkách |
| R² (R-squared)	| Koľko variability reálnych dát vysvetľuje model |
📝 Použi napr. mean_squared_error(y_true, y_pred) zo sklearn.metrics<br><br>
________________________________________
✅ NLP / Generovanie textu<br>
| Metrika	        | Vysvetlenie |
|----------------|-------------|
| BLEU	            | Zhodnosť s referenčným prekladom (strojový preklad) |
| ROUGE	            | Koľko z referenčných slov/fráz sa objavilo v generovanom texte |
| Perplexita	    | Ako je model „zmätený“ z textu – nižšia je lepšia |
Human eval.	Subjektívne hodnotenie kvality (napr. zmysel, konzistentnosť)<br><br>
________________________________________
⚙️ 3. Ako vybrať správne metriky<br>
✳️ Kedy použiť F1-score?<br>
•	Pri nevyvážených dátach (napr. 95 % zdravých pacientov, 5 % chorých).<br>
•	Nechceš len „správnosť“, ale citlivosť a presnosť zároveň.<br>
✳️ Kedy použiť RMSE?<br>
•	Pri predikcii reálnych hodnôt (napr. výška nájomného) – RMSE trestá veľké chyby viac.<br>
✳️ Kedy použiť ROC AUC?<br>
•	Keď potrebuješ vedieť, ako dobre model triedi pri rôznych prahoch.<br>
________________________________________
🎯 4. Nastavenie cieľových hodnôt<br>
Uveď v špecifikácii, čo model považujeme za úspešný:<br>
metrics:<br>
  accuracy: >= 0.90<br>
  f1_score: >= 0.85<br>
  latency: <= 0.5s<br>
Príklad pre testovací prípad:<br>
„Model dosiahne F1-score aspoň 0.85 pri predikcii sentimentu v testovacom datasete.“<br><br>
________________________________________
✅ Záver<br>
Nastavenie metrík je:<br>
•	technické rozhodnutie (čo vieme zmerať)<br>
•	biznis rozhodnutie (čo je „dostatočne dobré“ pre prax)<br>
Metriky nie sú len čísla – ovplyvňujú vývoj, testovanie aj nasadenie modelu.<br>
________________________________________
Chceš aj ukážku, ako tieto metriky vypočítať v Pythone pre tvoj model? Alebo pripraviť YAML šablónu na ich automatické sledovanie?<br>
Tu je ukážka troch rôznych testov v pytest pre jednoduchý model umelej inteligencie – napr. sentimentálny klasifikátor textov. Predpokladáme, že model má metódu predict(text), ktorá vracia string: "pozitívne", "negatívne" alebo "neutrálne".<br>
________________________________________
🧪 Príprava: Fiktívny model (na účely testu)<br>
# sentiment_model.py**<br><br>

````
class SentimentModel:
    def predict(self, text):
        text = text.lower()
        if "milujem" in text or "super" in text:
            return "pozitívne"
        elif "nenávidím" in text or "hrozný" in text:
            return "negatívne"
        else:
            return "neutrálne"
````
<br>

________________________________________
✅ Test 1: Klasický test očakávaného výstupu<br>
# test_sentiment.py<br>

````
from sentiment_model import SentimentModel

def test_pozitivna_predikcia():
    model = SentimentModel()
    vstup = "Tento produkt milujem!"
    vystup = model.predict(vstup)
    assert vystup == "pozitívne"
````

<br>
________________________________________
✅ Test 2: Metamorfický test (synonymum by nemalo zmeniť výsledok)<br><br>

````
def test_synonymum_pozitivneho_slova():
    model = SentimentModel()
    text1 = "Tento produkt milujem!"
    text2 = "Tento produkt zbožňujem!"
    vystup1 = model.predict(text1)
    vystup2 = model.predict(text2)
    assert vystup1 == vystup2  # očakávame rovnaký sentiment
````
<br>
(🧠 Tento test by zlyhal s aktuálnym modelom – ale práve preto je užitočný!)<br><br>

________________________________________
✅ Test 3: Robustnostný test (neštandardný vstup)<br><br>

````
import pytest

def test_prazdny_text():
    model = SentimentModel()
    vstup = ""
    vystup = model.predict(vstup)
    assert vystup == "neutrálne"  # Ak sa tak rozhodneme v špecifikácii
````
<br>

________________________________________
🚀 Spustenie testov<br>
V termináli:<br>

`pytest test_sentiment.py -v`
<br>

________________________________________
Ak chceš, môžem doplniť test s metrikami (napr. presnosť nad testovacou množinou) alebo ukážku s reálnym ML modelom (napr. sklearn.pipeline). Mám pokračovať týmto smerom?<br>
Super! Teraz ukážem, ako napísať testy v pytest pre reálny ML model, napríklad sentimentálny klasifikátor trénovaný pomocou sklearn. Zameriame sa na:<br>
1.	Test presnosti na testovacej množine<br>
2.	F1-score vyššie než prah<br>
3.	Predikcia nepadne na chybe (robustnosť)<br><br>
________________________________________
🧰 Príprava modelu (ak ho ešte nemáš)<br>
# model_pipeline.py<br>

```
from sklearn.pipeline import make_pipeline
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.linear_model import LogisticRegression

def build_model():
    X = [
        "Milujem tento produkt", 
        "Úžasný zážitok", 
        "Nenávidím to", 
        "Bolo to hrozné",
        "Fajn, ale nič extra"
    ]
    y = ["pozitívne", "pozitívne", "negatívne", "negatívne", "neutrálne"]

    pipeline = make_pipeline(
        CountVectorizer(),
        LogisticRegression()
    )
    pipeline.fit(X, y)
    return pipeline

```
<br>

________________________________________
🧪 Testovací súbor test_model_pipeline.py<br>

```
import pytest
from model_pipeline import build_model
from sklearn.metrics import accuracy_score, f1_score

model = build_model()

def test_presnost_na_testovacich_datoch():
    test_texty = [
        "Tento produkt je skvelý", 
        "Je to hrozné", 
        "Dalo sa to vydržať"
    ]
    ocakavane = ["pozitívne", "negatívne", "neutrálne"]
    predikcie = model.predict(test_texty)
    
    presnost = accuracy_score(ocakavane, predikcie)
    print(f"Presnosť: {presnost}")
    assert presnost >= 0.66  # minimálne 2 z 3 správne

def test_f1_skore_minimum():
    test_texty = [
        "Úžasné", "Nenávidím to", "Normálne"
    ]
    ocakavane = ["pozitívne", "negatívne", "neutrálne"]
    predikcie = model.predict(test_texty)

    f1 = f1_score(ocakavane, predikcie, average="macro")
    print(f"F1-score: {f1}")
    assert f1 >= 0.6

def test_nepadne_na_prazdnom_vstupe():
    try:
        predikcia = model.predict([""])[0]
        assert predikcia in ["pozitívne", "negatívne", "neutrálne"]
    except Exception as e:
        pytest.fail(f"Model padol na prázdnom vstupe: {e}")

```
<br>

________________________________________
▶️ Spustenie testov<br>

`pytest test_model_pipeline.py -v`
<br>

________________________________________
✅ Výhody tohto prístupu:<br>
•	Vieš automatizovať kontrolu kvality modelu.<br>
•	Pri každom re-tréningu overíš, či nedošlo k regresii výkonu.<br>
•	Vďaka pytest vieš tieto testy ľahko zapojiť do CI/CD pipeline.<br><br>
________________________________________
Ak chceš, môžeme ďalej:<br>
•	Zabaliť testy do testovacej triedy<br>
•	Pridať testy pomocou fixture a parametrizáciu<br>
•	Vizualizovať metriky<br>
•	Exportovať metriky do logu alebo HTML<br>
Chceš niečo z toho? Alebo ísť smerom testovania generatívnej AI (napr. jazykový model)?<br>



