# Smartphone Price Prediction System

> End-to-end ML pipeline predicting smartphone prices from Flipkart data — benchmarking XGBoost, Random Forest, Ridge Regression & Gradient Boosting with SHAP explainability and a full business strategy report.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-FF6600?style=flat&logo=xgboost&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)

---

## Overview

This project solves a real pricing intelligence problem for e-commerce and consumer electronics:

**Given a smartphone's specs, what should its market price be — and which features drive that price most?**

Built a production-ready ML pipeline on real Flipkart listing data, engineering 14+ features, benchmarking 4 algorithms with hyperparameter tuning, and delivering a SHAP-based explainability report with actionable pricing strategy recommendations.

---

## Project Pipeline

```
Raw Flipkart Data (Processed_Flipdata.xlsx)
        │
        ▼
Data Cleaning & Preprocessing
  - Handle missing values & inconsistencies
  - Encode categorical variables
  - Log-transform skewed price target
        │
        ▼
Feature Engineering (14+ features)
  - RAM × Processor Tier interaction
  - Brand frequency encoding
  - 5G flag (binary)
  - Storage-to-price ratio
  - Camera spec aggregation
        │
        ▼
Exploratory Data Analysis
  - Price distribution analysis
  - Correlation heatmap
  - Brand-wise pricing patterns
  - Spec-vs-price scatter analysis
        │
        ▼
Model Benchmarking (4 algorithms)
  - XGBoost Regressor
  - Random Forest Regressor
  - Ridge Regression
  - Gradient Boosting Regressor
        │
        ▼
Hyperparameter Tuning
  - RandomizedSearchCV (60+ combinations)
        │
        ▼
SHAP Explainability
  - Feature importance ranking
  - Individual prediction explanations
        │
        ▼
Business Report & Pricing Strategy
  - ProjectReport_SmartphonePricePrediction.pdf
```

---

## Dataset

| Property | Detail |
|---|---|
| Source | Flipkart smartphone listings |
| File | `Processed_Flipdata.xlsx` |
| Features | RAM, Storage, Processor, Camera, Battery, Brand, 5G, Display size, OS |
| Target | Smartphone price (INR) |
| Preprocessing | Log-transformation applied to correct right-skewed price distribution |

---

## Feature Engineering

| Feature | Description | Rationale |
|---|---|---|
| RAM × Processor Tier | Interaction term | Premium RAM + flagship chip commands exponential price premium |
| Brand Frequency Encoding | Brand mapped to market frequency | Captures brand premium vs. budget brand discount |
| 5G Flag | Binary (0/1) | 5G commands consistent price uplift across all brands |
| Log Price | `log(SalePrice)` | Normalises right-skewed INR price distribution |

---

## Model Results

| Model | Performance | Tuning |
|---|---|---|
| **XGBoost** ⭐ | Best R² score | RandomizedSearchCV, 60+ combos |
| Gradient Boosting | Strong performance | Hyperparameter tuned |
| Random Forest | Good generalisation | Ensemble, tuned |
| Ridge Regression | Baseline linear | L2 regularisation |

> XGBoost achieved best-in-class R² with lowest prediction error across train/validation/test splits. Full metrics available in `ProjectReport_SmartphonePricePrediction.pdf`.

---

## SHAP Explainability

Used SHAP (SHapley Additive exPlanations) to make the model interpretable for non-technical stakeholders:

- **Top price driver:** RAM × Processor Tier interaction
- **Second:** Brand tier (premium brands = strong positive SHAP values)
- **Third:** 5G flag — consistent uplift regardless of other specs
- **Biggest negative driver:** Budget brand encoding with low storage

This means the model doesn't just predict — it explains *why* a phone is priced the way it is.

---

## Business Deliverables

A full pricing strategy report (`ProjectReport_SmartphonePricePrediction.pdf`) identifies **3 actionable levers** for product and pricing teams:

1. **RAM + Processor bundling** — upgrading both together yields non-linear price premium; upgrading only one has diminishing returns
2. **5G as a pricing floor** — 5G-enabled devices should be priced at a minimum threshold regardless of other specs
3. **Brand positioning gap** — mid-tier brands with flagship specs are consistently underpriced relative to model predictions, representing a repositioning opportunity

---

## File Structure

```
mobile-pricing-ml-project/
│
├── MOBILEPRICINGPROJECT.ipynb              # Full ML pipeline notebook (1,624 lines)
├── Processed_Flipdata.xlsx                 # Cleaned Flipkart smartphone dataset
├── ProjectReport_SmartphonePricePrediction.pdf  # Business strategy report
└── README.md
```

---

## How to Run

```bash
# Clone the repo
git clone https://github.com/SumeetRajput/mobile-pricing-ml-project.git
cd mobile-pricing-ml-project

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn xgboost shap openpyxl jupyter

# Launch notebook
jupyter notebook MOBILEPRICINGPROJECT.ipynb
```

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Python | Core language |
| Pandas & NumPy | Data manipulation & feature engineering |
| Matplotlib & Seaborn | EDA visualisations |
| Scikit-learn | Random Forest, Ridge, Gradient Boosting, preprocessing |
| XGBoost | Best-performing model |
| SHAP | Model explainability |
| RandomizedSearchCV | Hyperparameter optimisation |
| openpyxl | Excel data loading |
| Jupyter Notebook | Development environment |

---

## Key Takeaways

- **14+ engineered features** outperformed raw spec inputs — domain knowledge matters as much as model choice
- **Log-transforming the target** was critical — without it, all models underperformed on premium-priced devices
- **SHAP > accuracy metrics** for business stakeholders — knowing *why* a model predicts matters more than the R² score alone
- **XGBoost + interaction features** is the winning combination for tabular pricing data

---

## Related Files

- Full project report with metrics, charts, and business recommendations: [`ProjectReport_SmartphonePricePrediction.pdf`](./ProjectReport_SmartphonePricePrediction.pdf)

---

## Author

**Sumeet Rajput**
[LinkedIn](https://www.linkedin.com/in/sumeet-rajput-a82211385) · [GitHub](https://github.com/SumeetRajput)
