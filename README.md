# 🖥️ GPU Performance & Market Insights — NVIDIA Business Analytics

> Business analytics case study for NVIDIA's analytics division — predicting price-to-performance ratios, analysing energy efficiency, and segmenting the GPU market using machine learning.

![Python](https://img.shields.io/badge/Python-3.12-blue?style=flat&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.4-orange?style=flat&logo=scikit-learn&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-green?style=flat)
![Dataset](https://img.shields.io/badge/Dataset-Kaggle-20BEFF?style=flat&logo=kaggle&logoColor=white)

---

## 📌 Overview

NVIDIA faces growing competitive pressure in three key areas — price-to-performance ratios, energy efficiency, and market segmentation across gaming, workstation, and AI workload GPUs. This project takes the perspective of a **data analyst in NVIDIA's analytics division**, using GPU benchmark data to derive actionable business insights across all three challenges.

Built as part of the M.Sc. Big Data & Business Analytics program at **FOM University of Applied Sciences, Essen**.

---

## 🎯 Business Problems & Results

| # | Business Problem | Method | Result |
|---|---|---|---|
| 1 | Price-to-Performance Optimisation | Random Forest Regression | **R² = 0.91** |
| 2 | Energy Efficiency Improvements | Random Forest Regression | **R² = 0.96** |
| 3 | Market Segmentation by Use Case | K-Means Clustering (k=4) | 4 distinct GPU segments |

---

## 🔑 Key Findings

**Price-to-Performance:**
- `G3DMark` (benchmark score) is the dominant driver of customer value — accounting for **80.9%** of feature importance
- `Price` contributes 13.6%, suggesting customers heavily prioritise raw performance over cost
- NVIDIA can optimise pricing strategies by focusing on benchmark improvements in the budget GPU segment

**Energy Efficiency:**
- `G3DMark` again dominates energy efficiency predictions (**82.2%** importance)
- `TDP` contributes 15.9% — reducing thermal power is the clearest lever for data centre and portable GPU improvements
- Higher benchmark scores consistently correlate with better performance-per-watt ratios

**Market Segmentation:**
- 4 distinct GPU clusters identified via K-Means + Elbow Method:
  - **Cluster 0** — Budget/entry-level GPUs (low price, low performance)
  - **Cluster 1** — Mid-range performers (balanced price/performance)
  - **Cluster 2** — Premium workstation GPUs (high price, very high performance)
  - **Cluster 3** — Performance-per-watt optimised GPUs (data centre focus)

---

## 📊 Dataset

- **Source:** [GPU Benchmarks — Kaggle](https://www.kaggle.com/datasets/alanjo/gpu-benchmarks)
- **Features:** `gpuName`, `G3Dmark`, `G2Dmark`, `price`, `gpuValue`, `TDP`, `powerPerformance`, `testDate`, `category`
- **Preprocessing:** KNN imputation for missing values, RobustScaler for feature scaling, LabelEncoder for categorical variables, RandomForestClassifier to predict unknown GPU categories

---

## 🛠️ Tech Stack

- **Language:** Python 3.12
- **ML Models:** Random Forest Regressor, Random Forest Classifier, K-Means Clustering
- **Preprocessing:** KNNImputer, RobustScaler, LabelEncoder
- **Evaluation:** R², RMSE, Silhouette Score
- **Visualisation:** Matplotlib, Seaborn (feature importance charts, elbow method, cluster pairplots)
- **Environment:** Jupyter Notebook

---

## 🔍 Methodology

```
GPU Benchmarks Dataset (Kaggle)
           ↓
Data Preprocessing
(KNN imputation, label encoding, robust scaling)
           ↓
Unknown Category Prediction
(RandomForestClassifier on known categories)
           ↓
┌──────────────────────────────────────────┐
│  Problem 1: Price-to-Performance         │
│  → Random Forest Regression on gpuValue  │
│  → Feature importance analysis           │
├──────────────────────────────────────────┤
│  Problem 2: Energy Efficiency            │
│  → Random Forest Regression on           │
│    powerPerformance                      │
│  → TDP and G3DMark driver analysis       │
├──────────────────────────────────────────┤
│  Problem 3: Market Segmentation          │
│  → K-Means Clustering (Elbow Method)     │
│  → 4 GPU market segments identified      │
└──────────────────────────────────────────┘
           ↓
Business Recommendations for NVIDIA
```

---

## 📁 Repository Structure

```
gpu-market-analytics/
│
├── GPU.ipynb                          # Main analysis notebook
├── README.md                          # Project documentation
```

---

## 🚀 How to Run

1. Clone the repository
```bash
git clone https://github.com/Anurag101723/gpu-market-analytics.git
cd gpu-market-analytics
```

2. Download the dataset from Kaggle
```
https://www.kaggle.com/datasets/alanjo/gpu-benchmarks
```

3. Install dependencies
```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

4. Open the notebook
```bash
jupyter notebook GPU.ipynb
```

---

## 👤 Author

**Anurag Rathore**
M.Sc. Big Data & Business Analytics — FOM University of Applied Sciences
📧 anuragakrathore@gmail.com
🔗 [LinkedIn](https://linkedin.com/in/anurag1017) · [Portfolio](https://Anurag101723.github.io)
