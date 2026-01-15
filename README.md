# Credit Card Default Prediction

Predict whether a credit card client will default using supervised classification. This repo includes two notebooks:

- **01_workbook.ipynb** — full class workflow + notes (EDA → preprocessing → modeling → tuning)
- **02_clean.ipynb** — minimal, portfolio-ready version with a concise conclusion

---

## Problem
Given historical credit card client data, predict **default vs. non-default**.  
Because missed defaults are typically more costly than false alarms, this project emphasizes **recall** and discusses metric tradeoffs.

---

## Skills Demonstrated
- **Exploratory Data Analysis (EDA):** Used `pandas` and `matplotlib` to examine feature distributions, class imbalance, and skewness (e.g., payment/billing amounts).
- **Feature Engineering & Preprocessing:** Performed binary encoding and one-hot encoding (`pd.get_dummies`) to convert categorical variables into model-ready numeric features.
- **Model Training & Evaluation:** Trained and evaluated multiple tree-based models (Decision Tree, Bagging, Random Forest, Extra Trees) using `classification_report`.
- **Metric Selection & Tradeoffs:** Focused on **recall** as the key metric (missing a true default is typically more costly than a false alarm) and analyzed accuracy vs. recall tradeoffs.
- **Hyperparameter Tuning:** Tuned Random Forest hyperparameters (e.g., `criterion`, `n_estimators`) to maximize recall and discussed the risk of overfitting to a single test split.

---

## Project Workflow
### 1) Data Cleaning & EDA
- Loaded the dataset and checked data quality.
- Explored distributions and imbalance in the target.
- Visualized skewness in numerical features (e.g., `PAY_AMT`, `BILL_AMT`) to understand scale and outliers.

### 2) Preprocessing
- Converted features to a purely numeric format for scikit-learn:
  - Binary encoding (e.g., `SEX`)
  - One-hot encoding for multi-category variables (e.g., `EDUCATION`, `MARRIAGE`)

### 3) Baseline Modeling + Tuning
- Trained multiple tree-based classifiers to establish a baseline.
- Selected **recall** as the primary metric due to the business impact of false negatives.
- Performed a staged hyperparameter search for Random Forest to maximize recall.

---

## Results (Summary)
- The best recall observed in the notebook was ~**0.416**, achieved by a Random Forest configuration that effectively behaved like a single tree (`n_estimators=1`, `criterion='gini'`).
- This illustrates an important lesson: **optimizing for a specific metric can lead to counterintuitive “best” settings**, and more complex models are not always superior.
- The notebook concludes with a note on **test-set overfitting risk** when repeatedly selecting models based on a single split.

---

## Repo Contents
- `01_workbook.ipynb` — full workflow + notes
- `02_clean.ipynb` — minimal version for portfolio review
- `credit_card_data.xlsx` — dataset file (placed alongside notebooks)

---

## How to Run
### Prerequisites
- Python 3.x
- Install dependencies:
  ```bash
  pip install pandas numpy matplotlib scikit-learn
  ```
Ensure `credit_card_data.xlsx` is in the same folder as the notebooks.

---

## Acknowledgments
Completed as part of the Applied Machine Learning Bootcamp (Columbia University).
Dataset: Default of Credit Card Clients (UCI Machine Learning Repository).
