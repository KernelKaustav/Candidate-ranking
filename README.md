---
title: Candidate Ranking
emoji: 🔴
colorFrom: red
colorTo: indigo
sdk: streamlit
sdk_version: 1.47.1
app_file: app.py
pinned: false
---

# 🔴 Redrob — Intelligent Candidate Ranker (Live Sandbox)

> Live Hugging Face Space for **team elabs'** submission to the *Data & AI — Intelligent Candidate Discovery* challenge (Redrob | H2S | INDIA.RUNS).
> This Space is also tracked as a git submodule of the main project: [CandidateRanking-System](https://github.com/KernelKaustav/CandidateRanking-System).

🤗 **Try it live:** [huggingface.co/spaces/Kaustav27/Candidate_ranker](https://huggingface.co/spaces/Kaustav27/Candidate_ranker)

---

## 🎯 What This Is

A two-phase candidate ranking system that reads up to 100,000 candidate profiles and returns the top-fit candidates for a role, each with a factual, grounded explanation — not just a score.

This Space wraps that pipeline in an interactive Streamlit sandbox: upload a candidates JSON, and get back a ranked, explainable shortlist.

## ⚡ Why It's Fast

All heavy computation — BGE embedding of 100K profiles, FAISS indexing, and behavioral scoring — runs offline, once. The live ranking step only loads pre-built artifacts and finishes in seconds, well under the 5-minute / CPU-only / no-network constraints of the challenge.

## 🔬 What Makes It Different

- Real semantic embeddings via **BGE-small-en-v1.5** + cosine similarity over a **FAISS** index — the same two-stage retrieval architecture used at companies like Google and LinkedIn.
- Scoring goes beyond keyword/skill match to model **behavioral hire probability** (recency, response rate, interview completion, notice period).
- **80+ honeypot profiles** with impossible resumes (timeline inflation, implausible skill claims) are automatically detected and penalized to near-zero.

---

## 🛠️ Built With

- Python, Streamlit
- `sentence-transformers` (BGE-small-en-v1.5, 384-dim, 22M params)
- FAISS (`IndexFlatIP`, cosine similarity search)
- pandas, NumPy, scikit-learn
- Docker (Hugging Face Spaces deployment)

## ⚙️ How It Works

1. Upload a Job Description.
2. Upload candidate profiles (JSON).
3. Features are extracted per candidate (skills, experience, company type, title relevance, behavioral signals).
4. Candidates are scored with a weighted formula combining semantic similarity, skill match, experience fit, and behavioral signals — then multiplied by penalty factors for disqualifiers, consulting-only careers, or honeypot detection.
5. Factual, template-based reasoning is generated for every candidate (zero LLM calls at rank time — fully reproducible, no hallucination risk).
6. Results are ranked and returned as a downloadable CSV.

## 📊 Output

- Overall candidate score and rank
- Matching percentage against the JD
- Plain-language, fact-grounded reasoning per candidate
- Downloadable results (CSV)

---

## 🖥️ Run Locally

```bash
git clone https://github.com/KernelKaustav/Candidate-ranking.git
cd Candidate-ranking

pip install -r requirements.txt

streamlit run app.py
```

---

## 🤝 Relationship to the Main Project

This repository is the deployment target for the Hugging Face Space and is included as a **git submodule** inside [CandidateRanking-System](https://github.com/KernelKaustav/CandidateRanking-System), which holds the full pipeline, scoring methodology, architecture docs, and test suite (`rank.py`, `features.py`, `scorer.py`, `reasoning.py`, `test_pipeline.py`).

Use this repo to try the ranking system interactively. Use the main repo to read about how it works, reproduce the full 100K-candidate pipeline, or review the source for the hackathon submission.

---

## 👥 Team elabs

| Role | Name |
|---|---|
| Leader | Kaustav Ghosh |
| Member | Nishant Dudhe |
| Member | Subhayan Dutta |

- GitHub: [github.com/KernelKaustav](https://github.com/KernelKaustav)
- Hugging Face: [huggingface.co/Kaustav27](https://huggingface.co/Kaustav27)
- Main repo: [github.com/KernelKaustav/CandidateRanking-System](https://github.com/KernelKaustav/CandidateRanking-System)

---

⭐ If you found this Space useful, consider starring the [GitHub repo](https://github.com/KernelKaustav/Candidate-ranking)!
