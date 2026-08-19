# Nikhil Adhikari

**MSc Data Science, AI & Digital Business — GISMA University of Applied Sciences, Berlin**
Headed for **MLOps · ML Reliability · ML Engineering**

> I build ML systems that don't just work — they stay working.

---

### 🟢 Open to work — Werkstudent & Internship (Berlin) · available immediately

**Core focus:** MLOps · ML Reliability Engineering
**Also open to:** ML Engineering · Data Engineering · AI / LLM Engineering · Backend Engineering (Python) · Data Science

📧 nikhiladhikari1@gmail.com &nbsp;·&nbsp; 💼 [LinkedIn](https://www.linkedin.com/in/nikhil-adhikari)

---

## Four systems, one theme

Most ML portfolios show a model that runs once. Mine show **four systems that keep running**. ML systems break at four predictable points — each project below hardens one, in the order a running system meets them:

**bad data gets in → the model drifts → live data shifts under it → the same failure repeats.**

---

## 1. [CSV Health Tracker](https://github.com/kai2055/csv-health-tracker)
*data quality validation service*

> ⚠️ **Bad data doesn't announce itself.** A model won't reject a broken file — it trains on it and hands back confident, wrong answers.

It checks every incoming CSV *before* it reaches the pipeline, so corruption gets caught at the door instead of surfacing three steps downstream where it's expensive to trace.

**What it caught:**
- 🧪 Run against a real **545,751-row** U.S. government dataset
- 🚩 Flagged **5 columns that were 76–97% empty** in seconds — the silent rot that quietly poisons any model trained on it

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![Cloud Run](https://img.shields.io/badge/GCP%20Cloud%20Run-4285F4?logo=googlecloud&logoColor=white)
![YAML config](https://img.shields.io/badge/config-YAML%20thresholds-CB171E?logo=yaml&logoColor=white)
![tests](https://img.shields.io/badge/tests-16-brightgreen)

🔗 **[Live API](https://csv-health-tracker-127482995435.europe-west3.run.app/docs)** &nbsp;·&nbsp; 📄 [Case study](https://kai2055.github.io/csv-health-tracker/) &nbsp;·&nbsp; 🎥 Demo *(coming)* <!-- replace with: 🎥 [Watch demo](VIDEO_URL) -->

<details>
<summary>▸ How it's built (engineering detail)</summary>

The first project in a deliberate MLOps sprint — a small problem on purpose, so the focus stayed on production patterns. Ships a `v1-simple-script` next to the `v2-modular` refactor so the diff itself carries the architectural reasoning. Custom exception hierarchy, structured logging, thresholds fully decoupled into `config.yaml` (re-tune strictness with no code change and no redeploy). Same validation logic exposed both as a CLI and a hosted Cloud Run endpoint. It never mutates source data — it only reports.
</details>

---

## 2. [ML Reliability Pipeline](https://github.com/kai2055/ml-reliability-pipeline)
*production ML monitoring & drift detection*

> ⚠️ **The world changes; the model doesn't.** A model that passed every test on launch day slowly goes wrong — and the first sign is usually an angry user.

It watches a live model against its training baseline, so decay shows up as a number on a dashboard instead of a complaint in your inbox.

**What it caught:**
- 🏦 Trained on 2010–2019 U.S. loan data, then watched 2020 applicants after COVID hit
- 📉 Detected the shift directly: **7 of 12 features drifted significantly**, the largest by **1.46 standard deviations** — a model judging today's borrowers by yesterday's world

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![PSI drift](https://img.shields.io/badge/drift-PSI-orange)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?logo=mlflow&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![Cloud Run](https://img.shields.io/badge/GCP%20Cloud%20Run-4285F4?logo=googlecloud&logoColor=white)
![tests](https://img.shields.io/badge/tests-112-brightgreen)
![ADRs](https://img.shields.io/badge/ADRs-27-blue)

🔗 **[Live API](https://ml-reliability-pipeline-1061232555311.europe-west1.run.app/docs)** &nbsp;·&nbsp; 📄 [Case study](https://kai2055.github.io/ml-reliability-pipeline/) &nbsp;·&nbsp; 🎥 Demo *(coming)* <!-- replace with: 🎥 [Watch demo](VIDEO_URL) -->

<details>
<summary>▸ How it's built (engineering detail)</summary>

Four separated layers — data / models / monitoring / serving — each with one job and no cross-layer imports the contracts don't demand. The monitoring layer snapshots a PSI baseline at training time, then scores production data against it under a documented drift policy. CI runs ruff, mypy, a coverage gate, codespell, and a Docker build on every push. Every non-trivial decision is captured as an Architecture Decision Record — the code tells you *what*, the 27 ADRs tell you *why*. Deployed and publicly reachable on Cloud Run.
</details>

---

## 3. [Berlin Transit Delay Intelligence](https://github.com/kai2055/berlin-transit)
*end-to-end data & ML engineering platform*

> ⚠️ **Live data never sits still.** A model fed a constantly-shifting real-time feed is the hardest kind to keep honest — the data moves under its feet.

It collects live Berlin/VBB departure data every ~10 minutes and predicts one thing — *will this train be more than 3 minutes late?* — with the full reliability discipline applied end to end, from ingestion to a deployed public API and dashboard.

**What it shows:**
- 🎯 The first model tried to predict exact delay in seconds and **lost to a "just guess zero" baseline** (MAE ~45s) — kept in the repo, not hidden
- 🔁 Reframed as binary classification → **XGBoost, ROC-AUC 0.886**; *service type* (U-Bahn vs. RE vs. ICE) mattered more than station or time of day

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![BigQuery](https://img.shields.io/badge/BigQuery-669DF6?logo=googlebigquery&logoColor=white)
![dbt](https://img.shields.io/badge/dbt-FF694B?logo=dbt&logoColor=white)
![PySpark](https://img.shields.io/badge/PySpark-E25A1C?logo=apachespark&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-337AB7)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?logo=mlflow&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?logo=terraform&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?logo=grafana&logoColor=white)
![ROC-AUC](https://img.shields.io/badge/ROC--AUC-0.886-brightgreen)
![ADRs](https://img.shields.io/badge/ADRs-14-blue)

🔗 **[Live API](https://transit-api-184545841057.us-central1.run.app)** &nbsp;·&nbsp; **[Live dashboard](https://transit-dashboard-184545841057.us-central1.run.app)** &nbsp;·&nbsp; 📄 [Case study](https://kai2055.github.io/berlin-transit/) &nbsp;·&nbsp; 🎥 Demo *(coming)* <!-- replace with: 🎥 [Watch demo](VIDEO_URL) -->

<details>
<summary>▸ How it's built (engineering detail)</summary>

Single-cloud GCP, running inside the always-free tier. GitHub Actions scrapes live departures → Google Cloud Storage (raw vault) → BigQuery (warehouse) → dbt (staging → intermediate → mart, with tests) and a PySpark lake-ETL job → scikit-learn / XGBoost with MLflow tracking → FastAPI on Cloud Run, with a Streamlit dashboard. Orchestrated by a Cloud Run job + Cloud Scheduler, observed via Prometheus + Pushgateway + Grafana, provisioned with Terraform, and demonstrated on a local `kind` Kubernetes cluster. 14 ADRs record every course-correction, including the regression-to-classification reframe.
</details>

---

## 4. [Incident Post-Mortem Retrieval Assistant](https://github.com/kai2055/incident-postmortem-assistant)
*RAG + LangGraph agent for incident search*

> ⚠️ **The same outage happens twice** — because nobody could find the write-up from the first one.

Describe a failure in plain English and get back the most relevant past incidents, their root causes, and how confident the match is. When nothing matches, it **refuses to answer** rather than inventing a convincing wrong one.

**What it does well:**
- 🎯 Retrieves the right past incident **every time** (hit rate **1.00**, MRR **0.92**)
- 🚦 A CI gate **blocks any merge the moment retrieval quality drops** — the evaluation framework is the point, not an afterthought

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![RAG](https://img.shields.io/badge/RAG-6E56CF)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C)
![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6F61)
![Ollama](https://img.shields.io/badge/Ollama-000000?logo=ollama&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white)
![hit rate](https://img.shields.io/badge/hit%20rate-1.00-brightgreen)
![eval suite](https://img.shields.io/badge/eval-39%20queries-blue)

📄 [Case study](https://kai2055.github.io/incident-postmortem-assistant/) &nbsp;·&nbsp; 🎥 Demo *(coming)* <!-- replace with: 🎥 [Watch demo](VIDEO_URL) -->

<details>
<summary>▸ How it's built (engineering detail)</summary>

Three layers, each answering a different question. **Retrieval:** section-aware chunks embedded into ChromaDB, grounded generation that cites its sources and declines below a distance threshold (0.30, chosen from a documented sweep — not guessed). **Diagnosis:** a LangGraph 4-node agent (decompose → retrieve → assess → diagnose) that separates root cause from symptom, with a grounding filter that strips any citation the model invented. **Regression gate:** CI re-runs the full metric suite on every push and fails the build the moment quality regresses. Models run locally via Ollama (`qwen3:8b` + `nomic-embed-text`). Known failure patterns are named in the README, not silently patched.
</details>

---

## Foundations

Daily practice, retyped from spec, not skimmed:
[python-llm-guided-practice](https://github.com/kai2055/python-llm-guided-practice) · [ml-study-lab](https://github.com/kai2055/ml-study-lab) · [sql-practice](https://github.com/kai2055/sql-practice)

---

*A slow, deep learner — I prioritize first-principles understanding over breadth, and I write down the* why *(every project above ships its decision log).*
