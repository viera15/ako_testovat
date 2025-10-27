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

---

🏗️ Architektúry modelov

Transformer
Základná architektúra moderných jazykových modelov založená na mechanizme pozornosti (attention), ktorá umožňuje paralelné spracovanie sekvencií.

Encoder-Decoder
Architektúra používaná pri prekladoch a generovaní textu, kde encoder spracuje vstup a decoder generuje výstup.

Self-Attention (samopozornosť)
Mechanizmus, ktorý modelu umožňuje hodnotiť vzťahy medzi všetkými časťami vstupu a zohľadniť kontext celého textu.

Attention Mechanism
Technika, ktorá určuje, ktoré časti vstupu majú pre aktuálny výstup najväčší význam.

Positional Encoding
Metóda pridávania informácie o poradí slov do vektorových reprezentácií, keďže transformery spracúvajú dáta paralelne.

LoRA (Low-Rank Adaptation)
Efektívna technika adaptácie modelov, ktorá umožňuje upravovať len malú časť váh namiesto celého modelu.

Adapter Layers
Dodatočné vrstvy vložené do existujúceho modelu, ktoré umožňujú jeho prispôsobenie novým úlohám bez úplného preučenia.

Mixture of Experts (MoE)
Architektúra využívajúca viaceré špecializované podsiete („expertov“), z ktorých model vyberá podľa typu vstupu.

Sparse Attention
Optimalizovaný variant pozornosti, ktorý znižuje výpočtové nároky pri spracovaní veľmi dlhých sekvencií.

Recurrent Neural Network (RNN)
Staršia architektúra neurónových sietí, ktorá spracováva sekvencie po jednom prvku a uchováva vnútorný stav pre kontext.

LSTM (Long Short-Term Memory)
Variant RNN určený na spracovanie dlhších sekvencií bez straty kontextu v čase.

GRU (Gated Recurrent Unit)
Zjednodušená verzia LSTM s podobnou schopnosťou zachovania informácií v čase.

📊 Dátová kvalita a integrita

Data Quality (kvalita dát)
Miera, do akej sú dáta presné, úplné, konzistentné, aktuálne a relevantné pre svoj účel.

Data Integrity (integrita dát)
Zachovanie presnosti a konzistencie dát počas ich životného cyklu, vrátane prenosu, ukladania a spracovania.

Data Lineage
Sledovanie pôvodu dát, ich transformácií a pohybu naprieč systémami – dôležité pre audit a vysledovateľnosť.

Data Provenance
Záznam o pôvode dát vrátane zdrojov, procesov a metadát, ktoré pomáhajú overiť ich dôveryhodnosť.

Bias (predsudok)
Systémová odchýlka v dátach alebo modeloch, ktorá môže viesť k diskriminačným alebo neobjektívnym výsledkom.

Data Drift
Zmena rozloženia vstupných dát v čase, ktorá spôsobuje zníženie výkonu modelu.

Concept Drift
Zmena vzťahov medzi vstupmi a výstupmi, čo vedie k neaktuálnosti modelu.

Outlier (odľahlá hodnota)
Neobvyklý dátový bod, ktorý sa výrazne odlišuje od ostatných a môže ovplyvniť výsledky analýzy alebo učenia.

Data Governance Framework
Súbor pravidiel, procesov a štandardov, ktoré definujú správu a zodpovednosť za kvalitu a bezpečnosť dát v organizácii.

Synthetic Data (syntetické dáta)
Umelo generované dáta, ktoré napodobňujú reálne údaje a používajú sa na trénovanie modelov bez ohrozenia súkromia.

Data Anonymization
Proces úpravy dát tak, aby znemožnil identifikáciu konkrétnych osôb alebo subjektov.

Data Validation
Overovanie správnosti a konzistencie dát pred ich spracovaním alebo použitím v modeloch.

Data Catalog
Centralizovaný zoznam dátových zdrojov s popisom ich obsahu, formátu a vlastníkov.

🧩 Monitorovanie a údržba modelov

Model Monitoring (monitorovanie modelov)
Proces nepretržitého sledovania výkonu modelu po jeho nasadení s cieľom identifikovať odchýlky, degradáciu alebo chyby.

Performance Metrics (výkonnostné metriky)
Ukazovatele ako presnosť, recall, F1-score, AUC, ktoré pomáhajú vyhodnocovať kvalitu modelu v čase.

Drift Detection (detekcia posunu dát)
Sledovanie zmien v dátach alebo predikciách, ktoré naznačujú, že model prestáva odrážať aktuálnu realitu.

Concept Drift Detection
Identifikácia zmien vo vzťahoch medzi vstupmi a výstupmi, ktoré môžu spôsobiť zníženie presnosti modelu.

Model Degradation (zhoršovanie modelu)
Postupná strata výkonu modelu spôsobená starnutím dát, sezónnosťou alebo zmenami správania používateľov.

Retraining Cycle (cyklus preučenia)
Pravidelne plánovaný proces, v ktorom sa model znovu trénuje na nových alebo aktualizovaných dátach.

Continuous Learning (nepretržité učenie)
Prístup, pri ktorom model automaticky integruje nové dáta do svojho učenia bez nutnosti manuálneho zásahu.

Feedback Loop (spätná väzba)
Mechanizmus, v ktorom sa výstupy modelu využívajú na jeho ďalšie zlepšovanie a prispôsobovanie.

Alerting System (systém upozornení)
Automatizované notifikácie pri prekročení prahových hodnôt metrík alebo zistení chýb vo výkone modelu.

Observability (pozorovateľnosť)
Schopnosť komplexne sledovať stav modelov, dátových tokov a výpočtov pomocou logov, metrík a tracingu.

Explainability in Monitoring
Integrácia vysvetliteľnosti do monitoringu, ktorá umožňuje pochopiť príčiny zmien v správaní modelu.

Model Registry Integration
Napojenie monitorovacích nástrojov na systém evidencie modelov (registry) pre sledovanie verzií a histórie.

Shadow Deployment Monitoring
Sledovanie výkonu nového modelu v paralelnom prostredí pred jeho plným nasadením.

Anomaly Detection (detekcia anomálií)
Identifikácia neobvyklých trendov alebo správania modelu, ktoré môžu signalizovať technický alebo dátový problém.

Data Pipeline Monitoring
Kontrola spoľahlivosti a kvality dátových tokov, ktoré zásobujú model aktuálnymi vstupmi.

Model Lifecycle Management
Kompletný proces správy modelov od vývoja cez nasadenie až po vyradenie z prevádzky.

---

⚖️ Etické princípy a regulácie AI

AI Act (Európsky zákon o umelej inteligencii)
Legislatívny rámec Európskej únie, ktorý určuje pravidlá pre bezpečné, etické a transparentné používanie AI podľa úrovne rizika.

Etické zásady AI
Základné princípy ako spravodlivosť, zodpovednosť, transparentnosť, súkromie a dôveryhodnosť, ktoré riadia vývoj a používanie AI.

Zodpovednosť (Accountability)
Povinnosť organizácií a vývojárov niesť dôsledky za rozhodnutia a výsledky AI systémov.

Transparentnosť
Schopnosť vysvetliť, ako model dospel k svojmu rozhodnutiu, a umožniť kontrolu procesov učenia a dát.

Auditovateľnosť
Možnosť spätne overiť správanie modelu, pôvod dát a zmeny vo verziách pre účely regulácie a bezpečnosti.

Data Governance
Súbor pravidiel a procesov, ktoré zabezpečujú správu, kvalitu, ochranu a dostupnosť dát v rámci organizácie.

Explainability (vysvetliteľnosť)
Schopnosť modelu poskytnúť zrozumiteľné vysvetlenie svojich výstupov používateľovi.

Fairness (spravodlivosť)
Zabezpečenie, aby model neobsahoval diskriminačné vzory alebo predsudky voči skupinám používateľov.

Privacy by Design
Prístup, ktorý integruje ochranu osobných údajov priamo do návrhu a vývoja AI systémov.

Human-in-the-Loop
Koncept, pri ktorom je človek zapojený do rozhodovacieho procesu AI s cieľom dohľadu a korekcie.

Trustworthy AI
Dôveryhodná AI – rámec, ktorý spája bezpečnosť, etiku, technickú spoľahlivosť a spoločenskú zodpovednosť pri vývoji AI.

AI Risk Management
Identifikácia, hodnotenie a mitigácia rizík spojených s vývojom, nasadením a používaním AI systémov.

🤖 Praktická práca s AI a agentmi

OpenAI Actions
Rozhranie umožňujúce AI agentom komunikovať s externými API službami prostredníctvom definovaných schém.

Tool Calling (Custom GPT)
Mechanizmus, ktorý umožňuje modelom vykonávať konkrétne funkcie alebo príkazy počas konverzácie.

Handover (odovzdanie kontroly)
Proces, pri ktorom AI agent odovzdáva úlohu inému agentovi alebo človeku bez straty kontextu.

Multi-agentný orchestrátor
Systém koordinujúci viacero agentov s rôznymi rolami, ktorí spolupracujú na dosiahnutí cieľa.

API integrácia
Prepojenie AI riešenia s externými aplikáciami prostredníctvom aplikačného rozhrania (API).

Zapier / n8n
Nástroje na automatizáciu workflow, ktoré prepájajú AI modely s inými aplikáciami bez potreby kódovania.

CrewAI
Rámec umožňujúci spoluprácu viacerých špecializovaných agentov (napr. vývojár, editor, analytik) na spoločnej úlohe.

AutoGen (Microsoft)
Knižnica na tvorbu autonómnych agentov, ktorí si navzájom odovzdávajú výsledky a úlohy v iteratívnych cykloch.

LangGraph
Orchestrátor AI agentov postavený na grafe stavov (state graph), ktorý riadi prechody a závislosti medzi úlohami.

Knowledge Graph
Reprezentácia znalostí vo forme uzlov (entít) a vzťahov medzi nimi, často používaná na inferenciu alebo odporúčanie.

MCP (Model Context Protocol)
Štandardizovaný protokol pre komunikáciu medzi AI modelmi, nástrojmi a dátovými zdrojmi.

Composio
Platforma umožňujúca bezpečné napájanie AI modelov na externé aplikácie prostredníctvom akčných endpointov.

Supply-chain riziko (v AI ekosystéme)
Hrozba spojená s reťazcom prepojených AI služieb, nástrojov a API, ktorá môže viesť k úniku dát alebo zneužitiu modelov.

---

