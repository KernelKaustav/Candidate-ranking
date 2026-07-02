---
title: Candidate Ranking
emoji: 📄
colorFrom: blue
colorTo: indigo
sdk: streamlit
sdk_version: 1.47.1
app_file: app.py
pinned: false
---

# 📄 Candidate Ranking

An AI-powered resume ranking application that evaluates candidates against a Job Description (JD) and generates transparent, explainable rankings using Large Language Models (LLMs).

## 🚀 Features

- 🎯 Rank candidates against a Job Description
- 📄 Upload and analyze multiple resumes
- 🤖 AI-assisted candidate evaluation
- 📊 Weighted scoring across multiple criteria
- 💬 Explainable reasoning for every score
- 📈 Recruiter-friendly ranking output

---

## 🛠️ Built With

- Python
- Streamlit
- Hugging Face Inference API
- Transformers
- Sentence Transformers
- Pandas
- NumPy
- Scikit-learn

---

## ⚙️ How it Works

1. Upload a Job Description.
2. Upload candidate resumes.
3. The system extracts relevant information.
4. Candidates are scored based on:
   - Skills
   - Experience
   - Education
   - Projects
   - Semantic similarity with the JD
5. AI generates reasoning for every candidate.
6. Candidates are ranked based on the final score.

---

## 📊 Output

The application provides:

- Overall Candidate Score
- Rank
- Matching Percentage
- AI-generated Reasoning
- Downloadable Results

---

## 🖥️ Run Locally

```bash
git clone https://github.com/KernelKaustav/Candidate-ranking.git
cd Candidate-ranking

pip install -r requirements.txt

streamlit run app.py
```

---

## 🤝 Integration

This repository powers the candidate ranking component of the **CandidateRanking-System** and can also be used as a standalone resume ranking application.

---

## 👨‍💻 Author

**Kaustav Ghosh**

- GitHub: https://github.com/KernelKaustav
- Hugging Face: https://huggingface.co/Kaustav27

---

⭐ If you found this Space useful, consider giving the GitHub repository a star!
