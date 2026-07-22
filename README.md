# 📒 TermLedger — Bank Marketing Campaign Intelligence

**Turning 41,188 cold-call records into a call list worth prioritizing.**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=plotly&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

---

## 🧭 What is this?

TermLedger is an end-to-end analysis of a Portuguese bank's phone marketing campaign for term deposits. It goes from raw call records → statistical insight → a leakage-free predictive model → a business report → an interactive dashboard, with **one goal**: help a bank decide who to call next, and why.

> 📉 Only **11.3%** of contacted clients ever said yes. This project figures out where that 11.3% is hiding.

---

## 🗂️ What's inside

| File | What it is |
|---|---|
| 📓 `Bank_Marketing_Inspection.ipynb` | Full technical notebook — EDA + feature engineering + modeling, fully executed |
| 📄 `Bank_Marketing_Business_Insights_Report.docx` / `.pdf` | Polished business report for non-technical stakeholders |
| 🖥️ `Bank_Marketing_Analytics_Dashboard.html` | Self-contained interactive dashboard — open it in any browser, no server needed |
| 📊 `bankmarketing.csv` | Source dataset (UCI Bank Marketing, 41,188 rows) |

---

## 🔍 Key findings

- 🎓 **Students and retirees** subscribe at 2–4× the rate of blue-collar/services workers
- 📅 **Timing beats volume** — March, Sept, Oct, and Dec convert 4–5× higher than the high-volume May–Aug months
- 🔁 **Warm beats cold** — clients with a successful prior campaign convert at **65%**, vs. **8.8%** for no prior history
- 📈 **Macroeconomics matter more than demographics** — Euribor rate, employment level, and employment variation rank as the top 3 predictive features, ahead of any individual client attribute
- ⚠️ **Duration is a trap** — call duration near-perfectly predicts the outcome but is only known *after* the call ends, so it's excluded from modeling to avoid leakage

---

## 🤖 Modeling snapshot

Two models, evaluated on a held-out 20% stratified test set, **without** the leaky `duration` feature:

| Model | Precision (yes) | Recall (yes) | F1 | ROC-AUC |
|---|:---:|:---:|:---:|:---:|
| Logistic Regression | 0.37 | 0.65 | 0.47 | 0.801 |
| 🏆 **Random Forest** | **0.42** | **0.64** | **0.51** | **0.814** |

Class imbalance (89/11) handled via `class_weight='balanced'` rather than oversampling.

---

## 🛠️ Tech stack

- 🐍 **Python** — pandas, NumPy for data wrangling
- 🧠 **scikit-learn** — Logistic Regression, Random Forest, pipelines, `ColumnTransformer`
- 📊 **Matplotlib & Seaborn** — all statistical visualizations
- 📓 **Jupyter** — exploratory + modeling notebook
- 🌐 **HTML / CSS / vanilla JS** — the interactive dashboard (no frameworks, no build step)
- 📝 **python-docx pipeline** — the Word/PDF business report

---

## 🚀 Running it

```bash
# clone and install
git clone   https://github.com/MayankJaiswal1/Bank-Marketing-Campaign-Intelligence.git
cd termledger
pip install pandas numpy scikit-learn matplotlib seaborn jupyter

# open the analysis
jupyter notebook Bank_Marketing_Inspection.ipynb
```

For the dashboard, just open `Bank_Marketing_Analytics_Dashboard.html` directly in any browser — no install required. 🖱️

---

## 👤 Author

**Mayank**
 

---

## 📚 Dataset

[UCI Machine Learning Repository — Bank Marketing Data Set](https://archive.ics.uci.edu/dataset/222/bank+marketing)

---

⭐ If this helped you understand imbalanced classification or leakage-aware modeling, consider starring the repo!
