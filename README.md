# 🚗 Salifort Motors — Employee Retention Prediction

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-Pipeline-orange?logo=scikit-learn&logoColor=white)
![Framework](https://img.shields.io/badge/Framework-PACE-purple)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📌 Project Overview

Salifort Motors' HR department collected data from ~15,000 employees and asked:
**"What is likely to make an employee leave the company?"**

This project analyzes the HR dataset and builds a machine learning model to predict
employee attrition — enabling the company to intervene proactively, reduce turnover,
and improve employee satisfaction.

---

## 🗂️ Project Structure

    salifort-motors-retention/
    │
    ├── notebook/
    │   └── salifort_motors_retention.ipynb
    │
    ├── data/
    │   └── HR_capstone_dataset.csv
    │
    ├── visuals/
    │   ├── feature_importance.png
    │   └── eda_plots/
    │
    └── README.md

---

## 🔬 Framework

This project follows the **PACE** framework:

| Stage | Description |
|---|---|
| **Plan** | Define scope, stakeholders, business problem, and ethical considerations |
| **Analyze** | Data cleaning, EDA, attrition pattern analysis |
| **Construct** | Feature engineering, model building, hyperparameter tuning |
| **Execute** | Model interpretation, HR recommendations, executive summary |

---

## 📊 Dataset

| Feature | Description |
|---|---|
| `satisfaction_level` | Employee-reported job satisfaction [0–1] |
| `last_evaluation` | Score of last performance review [0–1] |
| `number_project` | Number of projects assigned |
| `average_monthly_hours` | Average hours worked per month |
| `time_spend_company` | Tenure in years |
| `work_accident` | Whether employee had a work accident |
| `promotion_last_5years` | Whether employee was promoted in last 5 years |
| `department` | Employee's department |
| `salary` | Salary level (low / medium / high) |
| `left` | **Target** — whether employee left (1) or stayed (0) |

- **Rows:** ~15,000 (11,991 after cleaning)
- **Class balance:** 83% stayed / 17% left

---

## 🧠 Models Built

| Model | Recall | F1 Score | ROC-AUC |
|---|---|---|---|
| Logistic Regression | 0.8417 | 0.5644 | 0.8512 |
| Decision Tree | 0.9271 | 0.9145 | 0.9536 |
| **Random Forest (Final)** | **0.9221** | **0.9532** | **0.9792** |

> **Recall** was the primary metric — minimizing false negatives (missing at-risk employees)
> is more costly than a false alarm in this business context.

---

## 🔑 Key Findings

Two distinct leaver archetypes were identified:

**Archetype 1 — The Burned Out Employee**
- 250–300 monthly hours, 6–7 projects
- Satisfaction near 0.0 despite high evaluation scores
- No promotion in 5 years
- Interpretation: High performers being overworked with no career recognition

**Archetype 2 — The Disengaged Employee**
- 120–150 monthly hours, only 2 projects
- Satisfaction ~0.4, no promotion
- Interpretation: Underutilized employees who feel overlooked and quietly disengage

**Other key signals:**
- Attrition peaks sharply at **year 5** (45.4% attrition rate)
- No promotion → **4× higher attrition** vs. promoted employees
- Low salary is a consistent attrition driver across all departments
- Employees on 7 projects show **100% attrition** in the dataset

---

## ✅ Recommendations

| Priority | Action |
|---|---|
| High | Cap project assignments at 3–5 per employee |
| High | Launch retention conversations at the 3-year tenure mark |
| High | Link high evaluation scores to promotion or compensation review |
| Medium | Conduct compensation benchmarking for low-salary employees |
| Medium | Re-engage underutilized employees with stretch assignments |
| Low | Deploy model to score current workforce and re-run quarterly |

---

## 🛠️ Tech Stack

- **Language:** Python 3.8+
- **Environment:** Jupyter Notebook
- **Libraries:** pandas, numpy, matplotlib, seaborn, scikit-learn
- **Modeling:** Random Forest, Decision Tree, Logistic Regression
- **Pipeline:** scikit-learn Pipeline + ColumnTransformer + GridSearchCV

---

## 🚀 How to Run

    # 1. Clone the repository
    git clone https://github.com/vatsun07-web/salifort-motors-retention.git

    # 2. Navigate to the project folder
    cd salifort-motors-retention

    # 3. Install dependencies
    pip install -r requirements.txt

    # 4. Launch the notebook
    jupyter notebook notebook/salifort_motors_retention.ipynb

---

## 📁 Requirements

    pandas
    numpy
    matplotlib
    seaborn
    scikit-learn
    jupyter

---

## ⚠️ Limitations

- Dataset reflects a snapshot in time — attrition drivers may shift over time
- `left = 1` does not distinguish voluntary resignation from termination
- Model should be monitored for drift as workforce composition changes

---

## 👤 Author

**Seiha Vat**
Data Scientist
[LinkedIn](www.linkedin.com/in/seiha-vat-49014b242) · [GitHub](https://github.com/vatsun07-web)

---

## 📄 License

This project is for educational purposes only.
