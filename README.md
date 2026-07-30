# Nikhil Adhikari

MSc Data Science, AI & Digital Business @ GISMA University of Applied Sciences (Berlin).
Headed for ML Engineering / MLOps / ML Reliability Engineering.

**I build ML systems that don't just work — they stay working.**

Most ML portfolios show a model that runs once. Mine show three systems that keep running — one for each point where ML systems break in production.

---

## The three failure points

**Bad data gets in. The model quietly drifts. The same failure repeats because nobody learned from it.** Each project below hardens one of those points.

### 1. Bad data getting in — [Data Quality Checker](https://github.com/kai2055/csv-health-tracker)

Validates data *before* it reaches a model, so corrupt input gets caught at the door instead of silently poisoning training or scoring.

Without it: garbage in, garbage out, and no one notices until the downstream numbers are wrong.

Deployed and runnable on GCP Cloud Run.

### 2. The model drifting after launch — [ML Reliability Pipeline](https://github.com/kai2055/ml-reliability-pipeline)

Watches a model in production so degradation shows up as a metric, not as a complaint. A model that passed every test on launch day doesn't stay correct forever.

Without it: the first sign of a decaying model is an angry user.

Deployed and runnable.

### 3. The same failure repeating — [Incident Post-Mortem Retrieval Assistant](https://github.com/kai2055/incident-postmortem-assistant)

When a system goes down, an engineer describes the failure in plain English and gets back the most relevant past incidents, their root causes, and how confident the system is that they match. Past outages become searchable instead of buried in a wiki.

**What makes it more than a search box:** the evaluation framework is the point. A 39-query ground-truth suite measures whether retrieval can actually be trusted, and a CI gate **blocks a merge the moment that quality drops**. It also knows what it doesn't know — when no past incident matches, it declines rather than inventing a confident wrong answer.

Three complete layers: retrieval → a LangGraph diagnostic agent that separates root cause from symptom → an automated regression gate. Built on LangGraph, ChromaDB, and local LLMs via Ollama. **Finished.**

---

**Foundations:** [python-llm-guided-practice](https://github.com/kai2055/python-llm-guided-practice) · [ml-study-lab](https://github.com/kai2055/ml-study-lab) · [sql-practice](https://github.com/kai2055/sql-practice) — daily practice, retyped from spec, not skimmed.
