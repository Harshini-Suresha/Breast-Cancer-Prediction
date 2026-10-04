# Breast Cancer Prediction using Machine Learning

A machine-learning classification workflow for predicting breast cancer diagnosis from
clinical diagnostic features. The project focuses on systematic data preprocessing,
feature standardization, model selection, cross-validation, hyperparameter optimization,
and comparative evaluation of supervised learning algorithms.

---

## Project Overview

Breast cancer classification is a binary prediction problem in which diagnostic features
are used to distinguish between malignant and benign cases.

This project implements and compares two supervised learning approaches:

- **K-Nearest Neighbors (KNN)**
- **Logistic Regression**

The workflow emphasizes the effect of preprocessing and model configuration on predictive
performance, using feature imputation, standardization, cross-validation, and systematic
hyperparameter search.

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
