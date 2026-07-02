# Nikhil Adhikari

MSc Data Science, AI & Digital Business @ GISMA University of Applied Sciences (Berlin).
Headed for ML Engineering / MLOps / ML Reliability Engineering.

**I build ML systems that don't just work — they stay working.**

Most ML portfolios show a model that runs once. Mine show systems that keep
running: data validated before it enters, models watched in production, and
failures turned into measurable, deployment-gating feedback. One principle,
three layers.


## The three layers

ML systems fail at three points: bad data gets in, the model drifts in production, or the same failure repeats because nobody learned from it. Each project below hardens one of those points.

### 1. Data layer — [Data Quality Checker](https://github.com/kai2055/csv-health-tracker)
Catches bad input before it ever reaches a model.
*What breaks without it:* silent garbage-in-garbage-out — the model trains or scores on corrupt data and no one notices until the numbers are wrong downstream.
Deployed on GCP Cloud Run.

### 2. Model layer — [ML Reliability Pipeline](https://github.com/kai2055/ml-reliability-pipeline)
Keeps a model working after it ships, not just on the day it's deployed.
*What breaks without it:* a model that passed every test on launch day quietly degrades in production, and the first sign is an angry user, not a metric.

### 3. System layer — [Incident Post-Mortem Retrieval Assistant](https://github.com/kai2055/incident-postmortem-assistant)
Turns past failures into searchable, deployment-gating feedback — a three-layer RAG system that retrieves, diagnoses, and evaluates engineering post-mortems.
*What breaks without it:* the same outage happens twice because the lesson from the first one is buried in a wiki.
Built on LangGraph, ChromaDB, and local LLMs via Ollama, with a RAGAS-backed evaluation framework. *Layer 1 complete; diagnostic agent in progress.*

---

**How I build the foundation:** [python-llm-guided-practice](https://github.com/kai2055/python-llm-guided-practice) · [ml-study-lab](https://github.com/kai2055/ml-study-lab) · [sql-practice](https://github.com/kai2055/sql-practice) — daily practice, retyped from spec, not skimmed.

<!--
**kai2055/kai2055** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
