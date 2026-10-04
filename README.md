# Breast Cancer Prediction using Machine Learning

A machine-learning classification workflow for predicting breast cancer diagnosis from clinical diagnostic features. The project focuses on systematic data preprocessing, feature standardization, model selection, cross-validation, hyperparameter optimization, and comparative evaluation of supervised learning algorithms.

---

## Project Overview

Breast cancer classification is a binary prediction problem in which diagnostic features are used to distinguish between malignant and benign cases.

This project implements and compares two supervised learning approaches:

- **K-Nearest Neighbors (KNN)**
- **Logistic Regression**

The workflow emphasizes the effect of preprocessing and model configuration on predictive performance, using feature imputation, standardization, cross-validation, and systematic hyperparameter search.

---

## Objectives

The project aims to:

- Explore and preprocess clinical diagnostic data
- Handle missing feature values using statistical imputation
- Standardize numerical features for distance- and scale-sensitive models
- Develop a K-Nearest Neighbors classification model
- Determine an appropriate value of `K` using cross-validation
- Develop a Logistic Regression classification model
- Optimize model hyperparameters using `GridSearchCV`
- Apply repeated stratified cross-validation for robust model selection
- Compare classification performance using quantitative evaluation metrics

---

## Machine Learning Workflow
```text
Raw Dataset
     │
     ▼
Exploratory Data Analysis
     │
     ▼
Data Cleaning
     │
     ├── Missing-value detection
     └── Mean-value imputation
     │
     ▼
Feature / Target Separation
     │
     ▼
Feature Standardization
     │
     ▼
Train / Test Split
     │
     ├──────────────────────┐
     ▼                      ▼
KNN Classification    Logistic Regression
     │                      │
     ▼                      ▼
Cross-Validation       GridSearchCV
     │                 + RepeatedStratifiedKFold
     ▼                      │
Optimal K             Best Hyperparameters
     │                      │
     └──────────┬───────────┘
                ▼
        Model Evaluation
                │
                ▼
   Comparative Classification Analysis
```

---

# Data Preprocessing

The preprocessing pipeline includes:

### 1. Missing-Value Handling

Missing observations are identified and replaced using mean-value imputation to produce a complete feature matrix for downstream modelling.

### 2. Feature Standardization

Numerical features are standardized using `StandardScaler` so that variables with different numerical ranges contribute comparably during model training.

This is particularly important for KNN because its prediction mechanism depends on distance between observations.

### 3. Train-Test Separation

The dataset is separated into training and testing subsets before model evaluation, providing an independent hold-out set for assessing predictive performance.
---

# Models

# 1. K-Nearest Neighbors

KNN is implemented as a distance-based classification algorithm.

The workflow evaluates different values of `K` using cross-validation to determine an appropriate neighbourhood size rather than selecting the parameter arbitrarily.

## Key Concepts Explored

- Euclidean-distance-based neighbour selection
- Neighbourhood size (`K`)
- Feature scaling
- Cross-validation
- Bias-variance trade-off
- Classification accuracy

## 2. Logistic Regression

Logistic Regression is implemented as a linear probabilistic classification model for binary breast-cancer prediction.

Hyperparameter optimization is performed using:

- `GridSearchCV`
- `RepeatedStratifiedKFold`
- Cross-validation
- Systematic parameter search

This provides a structured approach for identifying a robust model configuration.

---

## Model Selection

### KNN

Multiple values of `K` are evaluated through cross-validation.

```text
Candidate K Values
       │
       ▼
Cross-Validation
       │
       ▼
Validation Performance
       │
       ▼
Select Optimal K
       │
       ▼
Train Final KNN Model
```
---

### Logistic Regression

The Logistic Regression model is optimized using an exhaustive grid-search strategy.

```text
Hyperparameter Grid
        │
        ▼
Repeated Stratified K-Fold CV
        │
        ▼
Evaluate Parameter Combinations
        │
        ▼
Select Best Configuration
        │
        ▼
Final Logistic Regression Model
```

---

## Cross-Validation

The project uses cross-validation to reduce dependence on a single train/validation partition.

For Logistic Regression, **Repeated Stratified K-Fold cross-validation** is used to maintain class proportions across folds while repeating the validation process across multiple splits.

This provides a more robust estimate of model performance and supports systematic hyperparameter selection.

---

## Evaluation

The trained models are evaluated using classification metrics including:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix
- Classification report

The evaluation framework allows comparison of model discrimination and class-specific prediction behaviour.

---

## Technologies

### Programming

- Python
- Jupyter Notebook

### Data Analysis

- Pandas
- NumPy

### Machine Learning

- Scikit-learn
- K-Nearest Neighbors
- Logistic Regression
- GridSearchCV
- RepeatedStratifiedKFold
- Cross-validation
- StandardScaler
- Mean-value imputation

### Visualization

- Matplotlib
- Seaborn

---

## Key Concepts Demonstrated

This project demonstrates practical implementation of:

- Supervised learning
- Binary classification
- Exploratory data analysis
- Data preprocessing
- Missing-value imputation
- Feature scaling
- KNN classification
- Logistic Regression
- Hyperparameter optimization
- Grid search
- Cross-validation
- Stratified sampling
- Repeated cross-validation
- Model evaluation
- Confusion-matrix analysis
- Bias-variance considerations
- Comparative model analysis

---

## Repository Structure

```text
Breast-Cancer-Prediction/
│
├── breast-cancer-prediction.ipynb
├── README.md
└── requirements.txt
```

---

## Reproducibility

### Clone the Repository

```bash
git clone https://github.com/Harshini-Suresha/Breast-Cancer-Prediction.git
cd Breast-Cancer-Prediction
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
breast-cancer-prediction.ipynb
```

and execute the notebook sequentially.

---

## Disclaimer

This project is an educational machine-learning implementation and is intended for research and demonstration purposes only. The predictions generated by the models are not intended for clinical diagnosis or medical decision-making.
