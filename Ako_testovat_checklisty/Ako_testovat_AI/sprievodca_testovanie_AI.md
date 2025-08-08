Tu je **podrobný sprievodca** testovaním aplikácií a programov s podporou AI, rozdelený do logických častí – od plánovania cez manuálne testovanie až po plne automatizovaný proces v CI/CD.

---

## 1. Plánovanie testovania AI-aplikácie

1. **Definuj rozsah a ciele**

   * *Funkčná* časť: čo má aplikácia poskytovať (knihovňa klasifikácie, chatbot, doporučovací engine…).
   * *Nefunkčná* časť: výkon, latencia, bezpečnosť, etickosť (biznis pravidlá).

2. **Identifikuj komponenty systému**

   * **Predspracovanie dát** (cleaning, tokenizácia, normalizácia).
   * **Model** (ML pipeline, inferenčný engine).
   * **Ovládacie API / UI** (rozhranie pre zadanie vstupu/výstupu).
   * **Monitoring a logovanie**.

3. **Zostav testovaciu stratégiu**

   * **Manuálne testovanie** → kvalitatívna zhodnocovanie výstupov.
   * **Automatizované testovanie** → metriky, regresné testy, CI pipeline.
   * **Sledovanie metrik** → F1-score, latency, throughput, fairness KPI.

---

## 2. Manuálne testovanie AI-aplikácie

### 2.1 Ciele manuálneho testovania

* Overenie kvality a relevantnosti výstupov, najmä u generatívnych alebo adaptívnych častí.
* Posúdenie UX, etických a kultúrnych aspektov.

### 2.2 Príprava prostredia

* **Web UI** alebo **Postman collection** pre REST API.
* Jednoduchý **notebook** (Jupyter) s pripravenými bunkami na zadanie vstupov.
* **Šablóna v Exceli / Notione** na evidenciu: vstup, výstup, očakávanie, hodnotenie, poznámky.

### 2.3 Postup manuálneho testovania

1. **Vyber vstup** (prompt, text, obrázok…).
2. **Zadaj do systému** a skopíruj výstup.
3. **Vyhodnoť**:

   * ✅ funkčnosť (správna kategória/predikcia)
   * ✅ kvalita (jazyk, štylistika, relevancia)
   * ✅ etika (bez predsudkov, toxického obsahu)
   * ✅ výkonnosť (rezponzívnosť UI)
4. **Zaznamenaj** do šablóny:

   | Vstup                      | Očakávané správanie   | Skutočný výstup | Výsledok | Poznámka                 |
   | -------------------------- | --------------------- | --------------- | -------- | ------------------------ |
   | „Daj mi recept.“           | Recept na zdravý obed | Recept + video… | ✅        | OK                       |
   | „Som z detskej onkológie.“ | Empatická odpoveď     | Suchý text      | ❌        | Doplniť empatickejší tón |

### 2.4 Tipy a triky

* Používaj **testovacie persony** (dieťa, senior, cudzinec…).
* Hľadaj **edge cases** (prázdne vstupy, zlý formát, nevhodné témy).
* Dokumentuj **kultúrne/regionálne odlišnosti** (vyskytlo sa v tvojom jazyku).

---

## 3. Automatizované testovanie AI-aplikácie

### 3.1 Komponenty automatizácie

* **Testovacie datasety** (JSON/CSV s párom vstup–výstup).
* **Testovací framework**: `pytest` (Python), prípadne BDD `Behave`/`Cucumber`.
* **CI/CD pipeline** (GitHub Actions, GitLab CI, Jenkins).

### 3.2 Príprava testovacích dát

* Rozdeľ dáta na **train/validation/test**.
* Pre testovanie použij samostatné **testovacie datasety** mimo tréningu.
* Zahrň do dát **corner cases** a **metamorfické testy**.

### 3.3 Implementácia testov v `pytest`

```python
# conftest.py
import pytest
from model_pipeline import build_model

@pytest.fixture(scope="session")
def model():
    return build_model()

# test_functional.py
def test_sentiment_positive(model):
    vstup = "Tento produkt milujem!"
    vystup = model.predict([vstup])[0]
    assert vystup == "pozitívne"

# test_metamorphic.py
@pytest.mark.parametrize("text1,text2", [
    ("Milujem to", "Zbožňujem to"),
    ("Hrozný zážitok", "Katastrofálny zážitok"),
])
def test_metamorphic(model, text1, text2):
    assert model.predict([text1])[0] == model.predict([text2])[0]

# test_metrics.py
from sklearn.metrics import accuracy_score, f1_score

def test_metrics_on_dataset(model):
    import json
    data = json.load(open("tests/test_data.json"))
    texts = [d["in"] for d in data]
    true = [d["out"] for d in data]
    pred = model.predict(texts)
    acc = accuracy_score(true, pred)
    f1 = f1_score(true, pred, average="macro")
    assert acc >= 0.90
    assert f1 >= 0.85

# test_performance.py
import time
def test_latency(model):
    start = time.time()
    _ = model.predict(["Ako bude počasie zajtra?"])
    assert (time.time() - start) < 0.5
```

### 3.4 CI/CD a reportovanie

* **Spúšťaj testy** pri každom Pull Request.
* **Publikuj report** metrík do HTML (napr. `pytest-html`) a grafov (napr. `MLflow`).
* **Alertovanie**: ak akákoľvek metrika klesne pod stanovený prah → upozorni tím.

---

## 4. Sledovanie a dohľad (Monitoring)

* **Logovanie** každého volania API (vstup, výstup, latency).
* **Dashboard** (Grafana, MLflow UI) s trendmi metrík.
* **Detekcia driftu** – ak sa mení rozdelenie vstupov či kvalita výstupov.

---

## 5. Najlepšie praktiky

1. **Verzionovanie modelu a dát** (Git + DVC).
2. **Testovanie dátovej integrity** (chýbajúce hodnoty, duplikáty).
3. **Pravidelná retréningová pipeline** + **regresné testy**.
4. **Etické zhodnotenie** – zapoj domain expertov, používaj fairness tooly.
5. **Dokumentuj** všetky testovacie scenáre a výsledky v test manažmente.

---

**Záver**
Testovanie AI-podporovaných aplikácií kombinuje klasické softvérové testovanie (funkčnosť, výkon) s **dátovým a behaviorálnym** hodnotením modelov. Bez dôsledného manuálneho aj automatizovaného testovania by sa do produkcie mohli dostať nepresné, pomalé či dokonca neetické systémy.

Ak potrebuješ pomoc s konkrétnou časťou (šablóna Excel, konfigurácia CI, etické testovanie), daj vedieť!
