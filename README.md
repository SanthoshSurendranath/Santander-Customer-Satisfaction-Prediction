# Santander Customer Satisfaction Prediction

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python) ![scikit-learn](https://img.shields.io/badge/scikit--learn-1.2.2-orange?logo=scikit-learn) ![pandas](https://img.shields.io/badge/pandas-2.x-150458?logo=pandas) ![Status](https://img.shields.io/badge/Status-Complete-brightgreen) ![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## Overview

This project builds an end-to-end machine learning pipeline to predict customer satisfaction for Santander using anonymized banking data. The objective is to identify dissatisfied customers early and support retention, service recovery, and customer experience initiatives through a repeatable classification workflow.

The problem is framed as a binary prediction task where the model estimates whether a customer is likely to be dissatisfied based on structured transactional and behavioral features.

---

## Business Objective

Enable Santander to identify customers likely to be dissatisfied so the business can:

- Prioritize proactive outreach for at-risk accounts
- Improve retention through earlier intervention
- Reduce churn risk with targeted service actions
- Support data-driven customer experience decisions

---

## Dataset

| Dataset | Records | Features | Target | Source |
|---|---:|---:|---|---|
| `train` | 76,020 | 370 predictor features + 1 target column | `TARGET` (0 = satisfied, 1 = dissatisfied) | Kaggle competition data |
| `test` | 76,020 | 370 predictor features | — | Kaggle competition data |

### Data Characteristics

| Item | Value |
|---|---|
| Problem type | Binary classification |
| Feature type | Anonymized numeric variables |
| Target label | `TARGET` |
| Class meaning | `0` = satisfied, `1` = dissatisfied |
| Modeling challenge | Strong class imbalance and high-dimensional feature space |

> The dataset is well suited for baseline classifiers, feature selection, and ensemble modeling.

---

## Feature Summary

The Santander competition data contains hundreds of anonymized features, which are typically grouped into the following modelling considerations:

| Category | Description |
|---|---|
| Raw numeric variables | Input features provided in anonymized form |
| Sparse / low-variance fields | Candidates for filtering during preprocessing |
| Correlated features | Useful for feature reduction and stability checks |
| Selected modelling features | Final feature set used for training and validation |

---

## Project Structure

```
Santander-Customer-Satisfaction-Prediction/
│
├── README.md
├── notebooks/                  # Exploratory analysis and model development
├── src/                        # Reusable preprocessing and modelling scripts
├── data/                       # Raw and processed datasets
└── models/                     # Saved models and prediction outputs
```

---

## Methodology

### 1. Data Loading
- Import the training and test datasets
- Separate the `TARGET` column from the predictors
- Review missing values, data types, and overall structure

### 2. Exploratory Data Analysis
- Assess target distribution and class imbalance
- Inspect variable distributions and data sparsity
- Review correlation patterns and unstable features

### 3. Feature Engineering
- Remove low-information or noisy variables
- Apply scaling or transformation where needed
- Select a compact, high-signal feature set for modelling

### 4. Model Development
The project is designed for experimentation with standard classification models:

| Model | Purpose |
|---|---|
| Logistic Regression | Interpretable baseline |
| Decision Tree Classifier | Simple rule-based benchmark |
| Random Forest Classifier | Robust ensemble baseline |
| Gradient Boosting / XGBoost | Strong non-linear learner |
| LightGBM | High-performance boosting model |

### 5. Evaluation
- Measure performance using validation metrics such as AUC or accuracy
- Compare models across the same train/validation split
- Select the best-performing model for final predictions

### 6. Prediction Generation
- Apply the chosen model to the test dataset
- Export predictions in submission-ready format
- Document the final output for reproducibility

---

## Results

### Dataset Values

| Metric | Value |
|---|---:|
| Training rows | 76,020 |
| Test rows | 76,020 |
| Predictive features | 370 |
| Target column | `TARGET` |
| Positive class | `1` (dissatisfied) |
| Negative class | `0` (satisfied) |

### Model Performance

Use this section to add your final validation and Kaggle scores once the modelling notebook is finalized.

| Model | Validation Score | Kaggle Public Score |
|---|---:|---:|
| Logistic Regression | TBD | TBD |
| Decision Tree | TBD | TBD |
| Random Forest | TBD | TBD |
| XGBoost / Gradient Boosting | TBD | TBD |
| LightGBM | TBD | TBD |
| Final Ensemble | TBD | TBD |

---

## Key Findings

- The dataset is highly suitable for supervised learning because the target is clearly defined and the feature space is consistent across train and test.
- Class imbalance must be handled carefully to avoid a model that simply favors the majority class.
- Feature selection and correlation filtering are important because the dataset contains many anonymized variables with overlapping signal.
- Ensemble methods are often the strongest candidates for this type of binary classification problem.

---

## Technologies Used

| Library / Tool | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical computation |
| Scikit-learn | Model training and evaluation |
| Jupyter Notebook | Interactive analysis and modelling |
| Matplotlib / Seaborn | Visualization and EDA |

---

## Setup

Clone the repository and install the required dependencies:

```bash
git clone https://github.com/SanthoshSurendranath/Santander-Customer-Satisfaction-Prediction.git
cd Santander-Customer-Satisfaction-Prediction
pip install -r requirements.txt
```

If a `requirements.txt` file is not available, install the core libraries manually:

```bash
pip install pandas numpy scikit-learn jupyter matplotlib seaborn
```

---

## How to Run

1. Open the notebook or Python script used for the analysis.
2. Load the training and test datasets.
3. Run preprocessing and feature engineering.
4. Train and validate the model.
5. Generate final predictions and export the output file.

Example:

```bash
jupyter notebook
```

---

## Key Deliverables

- Cleaned and prepared dataset
- Exploratory analysis and feature insights
- Trained classification model(s)
- Validation metrics and performance comparison
- Final prediction output for the test set

---

## Future Enhancements

Potential next steps for this project include:

- Hyperparameter tuning for improved performance
- Feature selection to reduce dimensionality
- Cross-validation for more robust evaluation
- Model interpretation using feature importance or SHAP
- Deployment of the scoring pipeline into a production workflow

---

## Author

**Santhosh Surendranath**  
Data Scientist

---

## License

This project is licensed under the MIT License. See `LICENSE` for details.
