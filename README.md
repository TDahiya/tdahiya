# Hi, I'm Tanishq Dahiya 👋

**AI Engineer** building assistants, retrieval systems and evaluation harnesses that run in production.
MSc Computing (AI) · **First Class Honours** · Dublin City University · graduated Sep 2026

📍 Dublin, Ireland
🌐 [tdahiya.github.io/website](https://tdahiya.github.io/website/) &nbsp;|&nbsp; 📧 tanishqd423@gmail.com &nbsp;|&nbsp; [![LinkedIn](https://img.shields.io/badge/LinkedIn-tdahiya2845-0078D6?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/tdahiya2845/)

---

## What I'm building

### 🔴 [Kaia](https://github.com/TDahiya/kaia) · [live](https://kaia-ai.duckdns.org/try)
A personal AI assistant in production, not on a laptop. Text chat, browser voice, and real inbound and outbound
phone calls, with Claude tool-calling across Google Calendar, Gmail and a Sheets CRM.

Two decisions worth the writeup:
- **Spreadsheets do not touch the retrieval path.** Retrieval returns rows that *look* like the answer, so the
  model invents a confident total. Instead it inspects the real schema, writes pandas, and the code runs in an
  isolated subprocess as an unprivileged user under CPU, memory, file-descriptor and process limits.
- **0.20s first-audio** once each sentence stopped being its own HTTPS request. One socket stays open and LLM
  tokens stream straight into it.

`FastAPI` `Next.js 15` `Claude` `Deepgram` `Telnyx` `Supabase` `Docker` `Hetzner`

### [Hybrid RAG over EU & Irish law](https://github.com/TDahiya/eu-irish-legal-rag) · [live](https://eu-irish-law-rag.onrender.com)
Legal questions come in two incompatible shapes: exact citations that embeddings blur, and conceptual queries
that share no vocabulary with the statute answering them. Both retrievers run and Reciprocal Rank Fusion merges
them by rank, so two incompatible score scales never need normalising.

**recall@10 93.3%** against 91.7% and 86.7% for the single retrievers · multi-hop recall **80% to 100%** ·
**95.2% faithfulness**, **4.8% hallucination** over 68 questions including 10 unanswerable traps.

The evaluation layer deleted one of this project's own features: a retry gate that measurement proved never
fired, and that was inversely correlated with the quality it gated on.

### [Prompt Firewall](https://github.com/TDahiya/prompt-firewall) · [live](https://prompt-firewall-kdwm.onrender.com)
Two-layer injection filter. A sub-millisecond regex pass catches known signatures, base64 blobs and Unicode
homoglyphs; only genuine ambiguity reaches the LLM classifier. The ordering is the design.

### [Multi-Agent Research Assistant](https://github.com/TDahiya/research-agent) · [live](https://research-agent-b8k4.onrender.com)
Retrieval, summarisation and fact-checking agents collaborating through LangGraph with structured handoffs,
each validating the last, behind a human approval gate.

---

## 🔬 Research

**[LLM Safety Consistency Under Adversarial Paraphrasing](https://github.com/TDahiya/llm-safety-adversarial)** · MSc Practicum, DCU · 2025–2026

Safety benchmarks test one phrasing at a time. If a model refuses one wording and complies with a semantically
identical rewrite, nothing catches it.

- 329 adversarial seed prompts grounded in 14 MITRE ATT&CK techniques, expanded to **1,645 variants** across
  4 controlled paraphrasing strategies
- 5 autonomous agents querying a different production LLM each (Claude, GPT-4o, DeepSeek, Mistral, Qwen):
  **8,225 responses**, scored by a 3-judge G-EVAL consensus into **24,675 verdicts**
- Proposed the **IIR (Intent-level Inconsistency Rate)** metric. Found **60.2% strict inconsistency**, and that
  the *safest* model (MSA 59%) was the *least* consistent (IIR 72.6%). Alignment and behavioural consistency
  are independent properties, so a single safety number tells you less than it appears to.

---

## 🛠 Stack

**Agents & LLMs**
![Claude](https://img.shields.io/badge/Claude-D97757?style=flat&logo=anthropic&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat&logo=langchain&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=flat)
![CrewAI](https://img.shields.io/badge/CrewAI-000000?style=flat)
![FAISS](https://img.shields.io/badge/FAISS-00599C?style=flat)
![ChromaDB](https://img.shields.io/badge/ChromaDB-FFB000?style=flat)

**Backend & Real-time**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs&logoColor=white)
![Postgres](https://img.shields.io/badge/Postgres-4169E1?style=flat&logo=postgresql&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat&logo=supabase&logoColor=white)

**ML**
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white)

**Data & Infra**
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white)
![dbt](https://img.shields.io/badge/dbt-FF694B?style=flat&logo=dbt&logoColor=white)
![Snowflake](https://img.shields.io/badge/Snowflake-29B5E8?style=flat&logo=snowflake&logoColor=white)
![Spark](https://img.shields.io/badge/Apache%20Spark-E25A1C?style=flat&logo=apachespark&logoColor=white)
![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=flat&logo=databricks&logoColor=white)
![Airflow](https://img.shields.io/badge/Airflow-017CEE?style=flat&logo=apacheairflow&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat&logo=githubactions&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazonaws&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat&logo=microsoftazure&logoColor=white)

---

## 📚 Education

- **MSc Computing (AI)** · First Class Honours (1:1) · Dublin City University, Ireland · 2025–2026
- **BSc Computer Science** · First Division · University of Delhi, India · 2021–2024
- Amazon AI/ML Summer School 2023

Eligible to work full-time in Ireland (Stamp 1G) · open to relocating

---

![Tanishq's GitHub stats](https://github-readme-stats.vercel.app/api?username=TDahiya&show_icons=true&theme=default&hide_border=true)
![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=TDahiya&layout=compact&theme=default&hide_border=true)
