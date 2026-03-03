# IEEE ML Arena - Binary Classification with LightGBM

## Project Overview
This project implements a LightGBM-based binary classification model for the IEEE ML Arena competition with stratified k-fold cross-validation.

## 1. PREPROCESSING STEPS

### 1.1 Data Loading
- Training Dataset: 43,776 samples × 48 features
- Test Dataset: 10,944 samples × 48 features
- Features: F01 through F47 (47 numerical features)
- Target: Binary classification (Class: 0 or 1)

### 1.2 Data Quality Assessment
 - Missing Values: 0 in both train and test
 - Duplicate Records: 738 removed, Final size: 43,038 samples

### 1.3 Class Distribution
- Class 0: 26,465 (60.46%)
- Class 1: 17,311 (39.54%)

### 1.4 Feature Correlation (Top 10)
1. F01: 0.3829
2. F09: 0.3727
3. F29: 0.3602
4. F19: 0.3550
5. F21: 0.3441

## 2. TRAINING STEPS

### 2.1 Model: LightGBM Classifier
- n_estimators: 5,000
- learning_rate: 0.03
- num_leaves: 31
- random_state: 42

### 2.2 Cross-Validation: 5-Fold Stratified
- Fold 1 AUC: 0.9993
- Fold 2 AUC: 0.9994
- Fold 3 AUC: 0.9989
- Fold 4 AUC: 0.9993
- Fold 5 AUC: 0.9988

### 2.3 Training Configuration
- Early Stopping: 100 rounds
- Validation Metric: AUC
- Ensemble: Average predictions across 5 folds

## 3. VALIDATION STEPS

### 3.1 Performance Metrics
- Accuracy: 0.9881 (98.81%)
- Precision: 0.9915 (99.15%)
- Recall: 0.9788 (97.88%)
- F1-Score: 0.9851 (98.51%)
- ROC AUC: 0.9990 (99.90%)

### 3.2 Confusion Matrix
- True Negatives: 25,582
- False Positives: 145
- False Negatives: 367
- True Positives: 16,944
- Total Errors: 512 (1.19%)

### 3.3 Validation Checks: All Passed
- Missing values check
- Duplicate removal
- Cross-fold consistency
- No data leakage
- Strong generalization

**Project Date**: 2026-03-03
**Repository**: ianmolbisht/ieeeML_arena

## Project Setup Guide

### 1️ Clone the Repository

```bash
git clone https://github.com/ianmolbisht/ieeeML_arena/blob/main/code.ipynb
cd ieeeML_arena
```

---

### 2️ Create Virtual Environment (Recommended)

#### Windows
```bash
python -m venv venv
venv\Scripts\activate
```

#### Mac/Linux
```bash
python3 -m venv venv
source venv/bin/activate
```

---

###  Install Dependencies

```bash
pip install -r requirements.txt
```

---

###  Run the Jupyter Notebook

#### Option 1: Using Jupyter Notebook
```bash
jupyter notebook
```

#### Option 2: Using Jupyter Lab
```bash
jupyter lab
```

Then open the `.ipynb` file from the browser interface.

---

###  (If Jupyter Not Installed)

```bash
pip install notebook
```

or

```bash
pip install jupyterlab
```

---

All set!
