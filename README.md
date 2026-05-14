# Hi, I'm Aayush Yagol 👋

**Insurance Data Analyst** based in Canberra, Australia.

I build predictive models, data pipelines, and Generative AI systems for insurance and financial services — and I work inside the industry I model. Currently a Claims Advisor at Suncorp Group, I bring frontline domain knowledge of claims operations, reserve setting, and regulatory compliance directly into my data work.

---

## 🛠️ Tech Stack

**Languages & Libraries**

![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)

**Generative AI & RAG**

![LlamaIndex](https://img.shields.io/badge/LlamaIndex-6B48FF?style=for-the-badge&logoColor=white)
![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6B35?style=for-the-badge&logoColor=white)
![Claude API](https://img.shields.io/badge/Claude_API-CC785C?style=for-the-badge&logoColor=white)

**BI & Visualisation**

![Tableau](https://img.shields.io/badge/Tableau-E97627?style=for-the-badge&logo=tableau&logoColor=white)
![Power BI](https://img.shields.io/badge/PowerBI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)

**Data Engineering**

![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

---

## 📌 Featured Projects

### 🤖 [Claims Document Intelligence — RAG Assistant](https://github.com/ayusyagol11/claims-rag-assistant)
> Grounded LLM responses for Workers Compensation queries — built by a practising Claims Advisor.

Retrieval-Augmented Generation system grounding answers in authoritative Australian insurance documents: ACT Workers Compensation Act 1951, SIRA NSW Standards of Practice, Comcare guidelines, and APRA GPS 320. Full pipeline: PDF ingestion → SentenceSplitter (800 chars/100 overlap) → local embeddings (all-MiniLM-L6-v2) → ChromaDB vector store → cosine similarity retrieval (Top-k=5) → Claude API with a system prompt enforcing grounding and inline `[Source N]` citations.

Evaluated across 20 labelled Q&A pairs: **75% mean term coverage, 100% source match rate**. Out-of-scope refusals validated correctly (2/2). Documented retrieval failure mode (vocabulary collision) with three production mitigations. Responsible AI by design: grounding enforced, citations visible in UI, explicit decision-support disclaimer.

`LlamaIndex` `ChromaDB` `Sentence-Transformers` `Claude API` `Streamlit` `Python`

---

### 📈 [Macroeconomic Resilience in General Insurance](https://github.com/ayusyagol11)
> Can Australian macroeconomic indicators predict insurance claim severity with a 2–6 quarter lead time?

Built a full analytics pipeline ingesting ABS, RBA, and APRA data → 18 engineered macro features (CPI, WPI, PPI, RBA cash rate) → OLS/Ridge/Lasso regression modelling → Streamlit dashboard with lag correlation heatmaps and four stress-test scenarios (stagflation, rate shock, stagnation). Ridge identified as more defensible than OLS, which overfitted to R²=1.0 under limited post-AASB 17 data. Spearman correlation of −0.67 between RBA cash rate and Motor loss ratio. Stakeholder outputs tailored to three personas: Head of Claims, CFO, Underwriting.

`Python` `Scikit-learn` `Streamlit` `Plotly` `ABS/RBA/APRA Data` `SQL`

---

### 🌊 [NFIP Insurance Data Warehouse](https://github.com/ayusyagol11/nfip-insurance-data-warehouse)
> 2.7M FEMA flood insurance records. Medallion Architecture. Seven KPI analytics views.

Ingested FEMA National Flood Insurance Program claims and policy data across 5 states (FL, LA, TX, NJ, NY) via REST API with pagination and retry logic. Medallion Architecture (Bronze → Silver → Gold) on Azure SQL Edge in Docker. Star schema with 2 fact tables and 5 dimensions. Seven analytics views answering specific underwriting questions: loss ratio by state, claims frequency/severity, large loss concentration (95th percentile), premium adequacy, claims development, and portfolio summary — the same KPIs I work with daily in a live claims environment.

`T-SQL` `Azure SQL Edge` `Docker` `Python` `Medallion Architecture` `Star Schema`

---

### 🛡️ [Predictive Claims Liability Model](https://github.com/ayusyagol11/claims-liability-predictor)
> Forecasting Pure Premium across 677,991 motor insurance policies. [[Live Dashboard]](https://claims-liability-predictor-dgw3wokbgkfzrhm4yfdlrh.streamlit.app/)

Implemented a **Tweedie Regressor** (p=1.5, compound Poisson-Gamma) — the actuarially correct distribution for zero-inflated claims data. Modular Scikit-learn pipeline includes ColumnTransformer (OHE + scaling), exposure weighting for policy duration, and serialised model via pickle. Deployed as a live Streamlit dashboard enabling non-technical stakeholders to explore risk segments by key rating factors.

`Python` `Tweedie Regression` `Scikit-learn` `Streamlit` `Pandas`

---

### 📊 [Predicting Customer Churn — ML Model Benchmarking](https://github.com/ayusyagol11/multimodal_churn_prediction)
> Class imbalance as the core challenge — not accuracy.

Benchmarked five classification algorithms (Logistic Regression, SVM, KNN, Random Forest, Gradient Boosting) on 10,000 bank customer records. Identified class imbalance as the defining challenge: baseline GBM recall on churners was 48.9%. Systematically evaluated three remediation approaches — SMOTE oversampling (66.3% recall), sample weighting (75.9% recall), and threshold adjustment (60.0% recall) — with GridSearchCV hyperparameter optimisation throughout. Sample weighting identified as the strongest strategy for this dataset. Attribution error (Random Forest importance displayed for GBM) documented and corrected.

`Python` `Scikit-learn` `GBM` `SMOTE` `GridSearchCV` `Imbalanced Classification`

---

## 📈 GitHub Stats

[![GitHub Streak](https://streak-stats.demolab.com?user=ayusyagol11&theme=default&hide_border=true)](https://github.com/ayusyagol11)

[![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=ayusyagol11&layout=compact&hide_border=true&theme=default&langs_count=6)](https://github.com/ayusyagol11)

---

## 🎓 Certifications

- 🟠 **Databricks Fundamentals** — Databricks (Jan 2026)
- 🔵 **IBM Data Analyst Professional Certificate** — IBM / Coursera (Mar 2025)
- 🟢 **Generative AI: Enhance Your Data Analytics Career** — IBM (2025)
- 🔷 **Deloitte Australia Data Analytics Job Simulation** — Deloitte (2025)
- 🟡 **Tata Data Visualisation: Empowering Business with Effective Insights** — Tata Group (2025)

---

## 📫 Let's Connect

[![Portfolio](https://img.shields.io/badge/Portfolio-aayushyagol.com-black?style=for-the-badge)](https://aayushyagol.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/aayush-yagol-046874145/)
