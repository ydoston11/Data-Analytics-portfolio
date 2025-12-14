# Credit Card Churn Analysis: A 4-Year Evolution

> *"Reviewing the old helps us learn the new"* — Confucius

This repository contains two analyses of the same dataset, separated by 4 years of learning:

| Version | Year | Approach | Outcome |
|---------|------|----------|---------|
| [Original](archive/2021_cerge_ei_original.py) | 2021 | Exploratory | "Here I got stuck" |
| [Revisited](notebooks/2025_revisited.ipynb) | 2025 | Prescription-oriented | 5 actionable recommendations |

**The dataset didn't change. I did, so I decided to make reflection on the my learnings and an old gold dataset**

---

## Project Overview

### Business Problem
A bank wants to reduce credit card customer churn (currently 16.1%). They need to know:
1. **Why** are customers leaving?
2. **Who** is most at risk?
3. **What** should we do about it?

### Key Findings

| Finding | Evidence | Business Impact |
|---------|----------|-----------------|
| Transaction count is #1 churn driver | Effect size r = 0.59 (Large) | Monitor customers with <50 transactions/year |
| Card type doesn't matter | Cramér's V = 0.015 (Negligible) | Don't segment retention by card tier | (reconsideration)
| Model identifies 82% of churners | By targeting 25% of customers | 3.3x more efficient than random outreach |
| Retention program ROI: 96% | $97K net return on $101K investment | Program pays for itself at 12.7% success rate |

---

## 📁 Repository Structure

```
credit-card-churn-evolution/
│
├── README.md                 # You are here
├── requirements.txt          # Python dependencies
├── .gitignore               
│
├── archive/                  # 2021 Original Analysis
│   └── 2021_cerge_ei_original.py
│
├── notebooks/                # 2025 Revisited Analysis
│   └── 2025_revisited.ipynb
│
├── data/                     # Dataset
│   └── BankChurners.csv
│
└── outputs/                  # Generated outputs
    └── figures/              # Visualizations
```

---

## Methodology

### 2025 Analysis Structure

| Section | Purpose | Key Techniques |
|---------|---------|----------------|
| **1. Context** | Frame the business problem | Stakeholder questions |
| **2. Data Understanding** | Explore the dataset | Distributions, missing values |
| **3. Hypothesis-Driven EDA** | Test 4 specific hypotheses | Segmented analysis |
| **4. Statistical Validation** | Rigorous testing | Chi-square, Mann-Whitney, Bootstrap CIs |
| **5. Prescription** | Rule-based risk scoring & recommendations | Statistical thresholds, ROI model |
| **6. Reflection** | Document growth | 2021 vs 2025 comparison |

### Why No Machine Learning?

This analysis deliberately uses **rule-based risk scoring** instead of ML models because:

1. **The patterns are simple** — Transaction count alone (r = 0.59) explains most of the risk
2. **Rules are interpretable** — Anyone can understand "flag customers with < 50 transactions"
3. **Rules are auditable** — Each threshold traces to statistical evidence
4. **Rules are maintainable** — No model drift, no retraining needed

### Statistical Rigor

This analysis goes beyond p-values:

- **Effect sizes** with interpretation (Cramér's V, rank-biserial r) (reconsideration)
- **Bootstrap confidence intervals** (2,000 iterations) (reconsideration)
- **Hodges-Lehmann estimator** for robust differences (reconsideration)
- **Rule-based thresholds** derived from statistical evidence

---

## Results Summary

### Rule-Based Risk Tier Distribution

| Tier | % of Customers | Actual Churn Rate | % of All Churners |
|------|----------------|-------------------|-------------------|
| Critical | 7% | 73% | 33% |
| High | 16% | 35% | 35% |
| Medium | 30% | 12% | 22% |
| Low | 32% | 4% | 9% |
| Minimal | 15% | 2% | 2% |

### Risk Identification Rules

| Rule | Threshold | Effect Size |
|------|-----------|-------------|
| Low Transaction Count | < 50/year | r = 0.59 (Large) |
| Zero Utilization | < 5% | r = 0.38 (Medium-Large) |
| High Contacts | >= 4/year | r = 0.25 (Medium) |
| Extended Inactivity | >= 3 months | r = 0.17 (Small-Medium) |
| Declining Trend | Q4/Q1 < 0.7 | EDA validated |

---

## 🚀 Quick Start

### Prerequisites
```bash
python >= 3.8
```

### Installation
```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/credit-card-churn-evolution.git
cd credit-card-churn-evolution

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook notebooks/2025_revisited.ipynb
```

### Data
The dataset is from Kaggle: [Credit Card Customers](https://www.kaggle.com/datasets/sakshigoyal7/credit-card-customers)

Download and place `BankChurners.csv` in the `data/` folder.

---

## The Growth Story

### What Changed in 4 Years

| Dimension | 2021 | 2025 |
|-----------|------|------|
| **Problem Framing** | None — just exploring | "What decision will this enable?" |
| **Statistical Testing** | None | Effect sizes + confidence intervals |
| **Risk Identification** | None | Rule-based scoring from statistical thresholds |
| **Business Value** | None | ROI model with sensitivity analysis |
| **Judgment** | Use every tool available | Know when NOT to use complex methods |
| **Outcome** | "Here I got stuck" | 5 prioritized actions with expected ROI |

### The Lesson

> *"In 2021, I asked: 'What patterns are in this data?'*  
> *In 2025, I ask: 'What decisions will this analysis enable?'*"

---

## 🛠️ Technologies Used

- **Python 3.10+**
- **pandas** — Data manipulation
- **numpy** — Numerical computing
- **scipy** — Statistical testing
- **matplotlib / seaborn** — Visualization

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **CERGE-EI** — Where the 2021 original was created during Introduction to Data Science
- **Kaggle** — For hosting the [Credit Card Customers dataset](https://www.kaggle.com/datasets/sakshigoyal7/credit-card-customers)

---

## 📬 Contact

**Doston** — [LinkedIn](https://www.linkedin.com/in/doston-yusupov/) | [GitHub](https://github.com/ydoston11)

*Feel free to reach out if you have questions about this analysis or want to discuss data science career growth!*

