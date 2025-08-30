# mAIeutic-Reasoning
# mAIeutica: Induzione di Reasoning e Consapevolezza Simulata nei LLM tramite Tecniche Dialogiche

Questo repository contiene il codice, i materiali sperimentali e la documentazione di supporto alla tesi di laurea **"mAIeutica: Induzione di Reasoning e Consapevolezza Simulata nei LLM tramite Tecniche Dialogiche"**.  
L'obiettivo del progetto è esplorare la possibilità di trasformare i Large Language Models (LLM) da semplici generatori probabilistici di testo a **agenti dialogici riflessivi**, capaci di esibire comportamenti assimilabili a forme primitive di ragionamento e consapevolezza simulata.  

---

## 📖 Descrizione del Progetto

Gli LLM di ultima generazione, pur eccellendo nella generazione linguistica, presentano criticità legate alla mancanza di un vero ragionamento: bias cognitivi, *hallucination*, incoerenze semantiche e tendenza a convergenze premature.  
Il progetto **mAIeutica** affronta questo problema utilizzando un approccio ispirato alla maieutica socratica e alla psicologia cognitiva, progettando una pipeline basata su **Retrieval-Augmented Generation (RAG)** per:  

- Creare **un finto system prompt dinamico**, capace di guidare il comportamento del modello esclusivamente tramite il linguaggio.  
- Strutturare l'interazione con l'LLM come un **dialogo riflessivo**, che induce il modello a interrogarsi, valutare alternative e correggere errori.  
- Validare l'approccio tramite benchmark consolidati (BigCodeBench, MMLU Pro, TruthfulQA).  

---

## 🔬 Metodologia

1. **Costruzione delle Skills Comportamentali**  
   Ogni skill è definita come un file JSON contenente:  
   - Contesto e obiettivo  
   - Principi guida  
   - Blocchi comportamentali ed esempi  
   
2. **Indicizzazione Vettoriale**  
   - Gli skill sono trasformati in embedding tramite `sentence-transformers/all-MiniLM-L6-v2`.  
   - FAISS è usato per il retrieval semantico della skill più rilevante rispetto alla query.  

3. **Prompt Dinamico**  
   - La skill recuperata viene trasformata in un prompt dettagliato che funge da **system prompt simulato**.  
   - GPT-4.1-mini interagisce con questo prompt per generare risposte più ragionate e riflessive.  

4. **Valutazione Sperimentale**  
   - Benchmark: BigCodeBench (code generation), MMLU Pro (reasoning), TruthfulQA (veridicità).  
   - Metriche chiave: `pass@1` per la generazione di codice, accuratezza su reasoning e truthfulness.  

---


