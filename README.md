# 🌊 Supervised Bit Classification for Underwater Optical Communication (UWOC)

Machine Learning-Based Robust Bit Detection Under Varying Turbidity (NTU) Conditions

---

## 📌 Project Overview

Underwater Optical Wireless Communication (UWOC) enables high-speed underwater communication using optical signals. However, water turbidity (NTU) causes scattering and absorption of light, resulting in signal degradation and increased bit errors.

Traditional receivers use a fixed threshold to classify received signals as bit 0 or bit 1. Since turbidity changes signal strength, a fixed threshold often becomes unreliable.

This project explores the use of Supervised Machine Learning models to accurately recover transmitted bits under varying turbidity conditions and compares their performance against traditional threshold-based detection.

---

## 🎯 Problem Statement

In UWOC systems, transmitted binary bits travel through water as optical signals. Due to varying turbidity levels, the received signal intensity changes significantly.

Challenges include:

- Signal attenuation caused by scattering and absorption.
- Overlap between bit 0 and bit 1 signal distributions.
- Increased Bit Error Rate (BER).
- Reduced reliability of fixed-threshold detection.

### Research Question

Can supervised machine learning models classify transmitted bits (0/1) more robustly than fixed-threshold detection under varying turbidity conditions?

---

## 🎯 Objectives

- Understand the UWOC communication problem.
- Analyze received optical signal behavior under different NTU levels.
- Build a reproducible data preprocessing pipeline.
- Compare fixed-threshold detection with machine learning classifiers.
- Evaluate model performance using standard classification metrics and BER.
- Analyze robustness across different turbidity conditions.
- Identify failure cases and limitations.

---

# 📂 Dataset Description

The dataset contains received optical signal measurements collected under multiple turbidity (NTU) levels.

## Features

| Feature | Description |
|----------|------------|
| Analog Value | Received signal intensity |
| Analog Voltage | Voltage corresponding to received signal |
| NTU | Turbidity level |
| Binary Bit S | Actual transmitted bit (Target Variable) |

## Target Variable

| Value | Meaning |
|---------|---------|
| 0 | Transmitted Bit 0 |
| 1 | Transmitted Bit 1 |

---

# 📊 Dataset Summary

| Property | Value |
|-----------|--------|
| Total Samples | 399 |
| Features | 3 |
| Missing Values | 0 |
| Duplicate Rows | 0 |
| Invalid Labels | 0 |

### Class Distribution

| Class | Count | Percentage |
|---------|---------|---------|
| Bit 0 | 242 | 60.65% |
| Bit 1 | 157 | 39.35% |

---

# 🔬 Methodology

## Overall Workflow

```text
Dataset
   ↓
EDA
   ↓
Data Cleaning
   ↓
Feature Engineering
   ↓
Scaling
   ↓
Train-Test Split
   ↓
Model Training
   ↓
Evaluation
```

---

## 1️⃣ Dataset Inspection

- Dataset structure analysis
- Feature verification
- Target validation

### 📷 Dataset Overview

[Dataset Overview](INSERT_DATASET_IMAGE_LINK)

---

## 2️⃣ Exploratory Data Analysis (EDA)

Performed:

- Class distribution analysis
- Signal distribution analysis
- NTU-wise behavior analysis
- Correlation analysis
- Feature separability analysis


### 📓 Notebook

[EDA Notebook](INSERT_EDA_NOTEBOOK_LINK)

---

## 3️⃣ Data Cleaning

Performed:

- Missing value inspection
- Duplicate verification
- Invalid label checking
- Class balance analysis

### Results

| Check | Result |
|---------|---------|
| Missing Values | 0 |
| Duplicates | 0 |
| Invalid Labels | 0 |

### 📓 Notebook

[Data Cleaning Notebook](INSERT_DATA_CLEANING_NOTEBOOK_LINK)

---

## 4️⃣ Feature Engineering

Performed:

- NTU Label Encoding
- Correlation Analysis
- Feature Importance Analysis

### Feature Importance

| Feature | Importance |
|---------|---------|
| Analog Voltage | 0.45 |
| Analog Value | 0.44 |
| NTU | 0.11 |


### 📓 Notebook

[Feature Engineering Notebook](INSERT_FEATURE_ENGINEERING_NOTEBOOK_LINK)

---

## 5️⃣ Feature Scaling

### Technique Used

```python
StandardScaler()
```

Purpose:

- Normalize feature ranges.
- Improve model convergence.
- Prevent feature dominance.

### 📓 Notebook

[Preprocessing Notebook](INSERT_PREPROCESSING_NOTEBOOK_LINK)

---

## 6️⃣ Train-Test Split

```python
train_test_split(
    test_size=0.3,
    stratify=y,
    random_state=42
)
```

Purpose:

- Preserve class distribution.
- Prevent biased sampling.

---

# 🤖 Models Evaluated

## Baseline Method

### Fixed Threshold Detection

Traditional signal classification technique based on predefined threshold values.

---

## Machine Learning Models

### Logistic Regression

- Linear classifier
- Fast inference
- High interpretability

### Support Vector Machine (SVM)

- Robust decision boundary
- Effective for overlapping signals
- Best overall performer

### Random Forest

- Ensemble learning approach
- Feature importance estimation

### Multi-Layer Perceptron (MLP)

- Neural network classifier
- Learns nonlinear relationships

---

# ⚙ Hyperparameter Tuning

## Logistic Regression

```python
{
    "C": 0.1,
    "solver": "lbfgs"
}
```

## Support Vector Machine

```python
{
    "C": 0.1,
    "kernel": "linear"
}
```

### Technique Used

```python
GridSearchCV(cv=5)
```

### 📓 Notebook

[Hyperparameter Tuning Notebook](INSERT_TUNING_NOTEBOOK_LINK)

---

# 📈 Evaluation Metrics

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix
- BER (Bit Error Rate)
- Inference Time

---

# 🏆 Model Comparison

| Model | Accuracy | Precision | Recall | F1 Score | BER |
|---------|---------|---------|---------|---------|---------|
| Logistic Regression | 74.17% | 66.95% | 61.70% | 65.17% | 0.258 |
| SVM | 75.83% | 84.62% | 46.81% | 60.27% | 0.242 |
| Random Forest | 70.83% | 63.04% | 61.70% | 62.37% | 0.292 |
| MLP | 75.00% | 71.79% | 59.57% | 65.12% | 0.250 |

---

## 🥇 Best Model

### Support Vector Machine (SVM)

Reasons:

- Highest Accuracy
- Highest Precision
- Lowest BER
- Better robustness across NTU levels

### 📓 Notebook

[Model Comparison Notebook](INSERT_MODEL_COMPARISON_CHART)

---

# 🌊 NTU Robustness Analysis

NTU-wise evaluation was performed to assess classifier performance under different turbidity conditions.

### 📓 Notebook

[NTU Robustness Analysis Notebook](INSERT_TUNING_NOTEBOOK_LINK)



---

# ❌ Error Analysis

## Prediction Summary

| Metric | Value |
|---------|---------|
| Correct Predictions | 91 |
| Incorrect Predictions | 29 |
| Accuracy | 75.83% |

### Error Distribution

| NTU Level | Errors |
|-----------|---------|
| 2–3 NTU | 2 |
| 3–4 NTU | 2 |
| 4–5 NTU | 9 |
| 5–6 NTU | 16 |

### Observations

- Errors increase as turbidity increases.
- Signal overlap becomes severe at high NTU.
- High NTU conditions produce most classification failures.



### 📓 Notebook

[Error Analysis Notebook](INSERT_ERROR_ANALYSIS_NOTEBOOK_LINK)

---

# 📌 Key Findings

- Fixed-threshold detection becomes unreliable under high turbidity conditions.
- Machine learning improves bit classification performance.
- SVM achieved the best overall performance.
- BER increases significantly as NTU increases.
- Turbidity is the dominant factor affecting UWOC signal quality.

---

# ⚠ Limitations

- Small dataset size (399 samples)
- Moderate class imbalance
- Limited feature set
- High-NTU performance degradation
- No real-time deployment validation

---

# 🚀 Future Work

- Collect larger UWOC datasets.
- Evaluate advanced models such as XGBoost and LightGBM.
- Explore deep learning architectures.
- Incorporate additional environmental parameters.
- Deploy on embedded systems for real-time testing.
- Improve robustness under highly turbid conditions.

---

# 📁 Repository Structure

```text
UWOC-Bit-Classification/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── EDA.ipynb
│   ├── Preprocessing.ipynb
│   ├── Feature_Engineering.ipynb
│   ├── Model_Training.ipynb
│   ├── Hyperparameter_Tuning.ipynb
│   ├── Error_Analysis.ipynb
│   └── Final_Validation.ipynb
│
├── models/
│   ├── svm_model.pkl
│   └── scaler.pkl
│
├── results/
│
├── report/
│
└── README.md
```

---

# ▶️ Installation

Clone the repository:

```bash
git clone YOUR_REPOSITORY_LINK
cd UWOC-Bit-Classification
```

Install dependencies:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
Final_Validation.ipynb
```

Run all cells sequentially.

---

# 📚 Project Resources

| Resource | Link |
|----------|------|
| EDA Notebook | INSERT_LINK |
| Preprocessing Notebook | INSERT_LINK |
| Feature Engineering Notebook | INSERT_LINK |
| Model Training Notebook | INSERT_LINK |
| Hyperparameter Tuning Notebook | INSERT_LINK |
| Error Analysis Notebook | INSERT_LINK |
| Final Validation Notebook | INSERT_LINK |
| Final Report | INSERT_LINK |
| Presentation | INSERT_LINK |

---

# 👨‍💻 Author

**Prashanth M**  
Pre-Final Year, Computer Science Engineering  
Shiv Nadar University Chennai

---

# 📜 Acknowledgement

This work was carried out as part of the **TIH IIT Guwahati 4-Week Online Internship Project** on **Underwater Optical Communication (UWOC) Bit Classification**.

---

# ⭐ If you found this project useful, consider giving the repository a star.
