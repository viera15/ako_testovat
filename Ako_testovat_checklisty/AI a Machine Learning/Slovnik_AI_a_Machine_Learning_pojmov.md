# Slovník AI a Machine Learning pojmov

## 📑 Prehľad kategórií
1. 🧠 Základné pojmy AI/ML  
2. 📚 Typy Machine Learningu  
3. 🧩 Jazykové modely (LLM) a generatívna AI  
4. 💬 Parametre, roly a kontext LLM  
5. 🏗️ Architektúry modelov  
6. 📊 Dátová kvalita a integrita  
7. 🧩 Monitorovanie a údržba modelov  
8. ⚖️ Etické princípy a regulácie AI  
9. 🤖 Praktická práca s AI a agentmi  
10. ⚙️ Automatizácia a infraštruktúra  
11. 🧰 Nástroje a frameworky  

---

## 🧠 Základné pojmy AI/ML
**Artificial Intelligence (AI)**  
Umelá inteligencia – schopnosť systému učiť sa, rozhodovať a adaptovať sa na základe dát bez explicitného programovania.

**Machine Learning (ML)**  
Strojové učenie – podmnožina AI, ktorá využíva algoritmy na odhaľovanie vzorov a predikciu na základe historických dát.

**Deep Learning**  
Typ strojového učenia využívajúci viacvrstvové neurónové siete, ktoré dokážu spracovávať zložité nelineárne vzťahy.

**Neural Network (neurónová sieť)**  
Model inšpirovaný štruktúrou mozgu, pozostávajúci z uzlov (neurónov) a váh medzi nimi, ktoré upravujú význam signálu.

---

## 📚 Typy Machine Learningu
**Supervised Learning (učenie s učiteľom)**  
Algoritmy trénované na dátach s vopred známymi výstupmi (labelmi), využívané napr. pri klasifikácii alebo regresii.

**Unsupervised Learning (učenie bez učiteľa)**  
Algoritmy, ktoré objavujú skryté štruktúry a vzory v dátach bez vopred daných výstupov.

**Semi-Supervised Learning**  
Prístup kombinujúci označené a neoznačené dáta na zvýšenie presnosti modelu.

**Reinforcement Learning (posilňované učenie)**  
Model sa učí rozhodovať prostredníctvom spätnej väzby vo forme odmien a trestov.

**Transfer Learning**  
Znovupoužitie modelu trénovaného na inom probléme, čím sa urýchli učenie a zníži potreba dát.

**Online Learning**  
Priebežné učenie modelu z nových dát v reálnom čase.

---

## 🧩 Jazykové modely (LLM) a generatívna AI
**Large Language Model (LLM)**  
Veľký jazykový model trénovaný na obrovských množstvách textov, schopný generovať, sumarizovať a analyzovať text.

**Tokenizer**  
Mechanizmus, ktorý rozdeľuje text na menšie jednotky (tokeny), s ktorými model pracuje.

**Embedding**  
Vektorová reprezentácia slov, viet alebo dokumentov, ktorá zachytáva ich význam a vzájomnú podobnosť.

**Context Window**  
Maximálny počet tokenov, ktoré môže model naraz spracovať a udržať v pamäti.

**Prompt**  
Vstupné zadanie pre jazykový model, ktoré určuje, čo má model vykonať alebo odpovedať.

**Fine-tuning**  
Doplňujúce trénovanie modelu na špecifických dátach pre konkrétnu doménu alebo úlohu.

**RAG (Retrieval-Augmented Generation)**  
Technika kombinujúca generovanie textu s vyhľadávaním relevantných informácií z externých zdrojov.

**Knowledge Graph Integration**  
Prepojenie jazykového modelu so znalostnou databázou (knowledge graph) pre presnejšie odpovede.

**Hallucination (halucinácia)**  
Stav, keď model vymýšľa nepravdivé alebo neexistujúce informácie s vysokou sebadôverou.

**System Prompt**  
Vnútorné inštrukcie, ktoré definujú správanie modelu alebo rolu agenta.

**Chain of Thought (Reťaz úvah)**  
Schopnosť modelu generovať medzikroky logického uvažovania pred konečnou odpoveďou.

**Multimodal Model**  
Model schopný spracovať viac druhov vstupov (text, obraz, zvuk, video) a prepájať ich informácie.

**RLHF (Reinforcement Learning from Human Feedback)**  
Metóda dolaďovania modelu pomocou spätnej väzby od ľudí, ktorá zlepšuje kvalitu odpovedí.

**Model Alignment**  
Zladenie modelu s ľudskými hodnotami a očakávaniami, aby bol bezpečný a spoľahlivý.

---

## 💬 Parametre, roly a kontext LLM
**Seed**  
Náhodné počiatočné číslo, ktoré určuje deterministické správanie modelu – pri rovnakom *seed* model generuje identické výstupy.

**Temperature**  
Parameter určujúci mieru náhodnosti pri generovaní odpovedí – nižšia hodnota znamená konzervatívne, vyššia kreatívne odpovede.

**Top-k Sampling**  
Metóda, ktorá obmedzuje výber tokenov len na *k* najpravdepodobnejších kandidátov.

**Top-p Sampling (nucleus sampling)**  
Metóda, ktorá zvažuje len tokeny, ktorých kumulatívna pravdepodobnosť dosiahne prah *p* (napr. 0,9), čím udržuje rovnováhu medzi tvorivosťou a presnosťou.

**Max Tokens**  
Parameter definujúci maximálnu dĺžku výstupu modelu v tokenoch.

**Stop Sequence**  
Reťazec alebo skupina reťazcov, pri ktorých model automaticky ukončí generovanie textu.

**Style (štýl)**  
Určuje formu výstupu modelu – napr. formálny, neformálny, technický, konverzačný alebo kreatívny.

**Tone (tón)**  
Vyjadruje emocionálne zafarbenie alebo postoj výstupu, napr. neutrálny, empatický, odborný alebo motivačný.

**Role (rola)**  
Definuje, v akej úlohe model vystupuje (napr. učiteľ, tester, analytik, editor) a podľa toho prispôsobuje odpovede.

**Context (kontext)**  
Súbor informácií, ktoré model používa na pochopenie situácie a udržanie súvislostí v rámci dialógu alebo úlohy.

**System Message (systémová správa)**  
Vnútorné inštrukcie, ktoré určujú základné správanie modelu – napr. jeho štýl, osobnosť či limity odpovedí.

**User Message (správa používateľa)**  
Vstupné zadanie od človeka, ktoré definuje, čo model má spracovať alebo vytvoriť.

**Assistant Message (správa asistenta)**  
Odpoveď generovaná modelom ako reakcia na používateľský vstup.

**Persona**  
Simulovaná identita alebo profil modelu, ktorý ovplyvňuje jeho štýl, spôsob vyjadrovania a prioritu informácií.

**Chain of Thoughts (reťazec myšlienok)**  
Skrytý alebo explicitný proces vnútorného uvažovania modelu, ktorý vedie k záveru alebo odpovedi.
