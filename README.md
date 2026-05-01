# 🚒 London Fire Brigade — Greenwich Incident Analysis (2019–2022)

A data mining project analysing 12,861 LFB incident records from the 
London Borough of Greenwich using Python. Built as part of the 
MSc Data Science programme at London South Bank University.

---

## 📋 Project Overview

This project follows the CRISP-DM data mining methodology to analyse 
real-world incident data from the London Fire Brigade (LFB). The analysis 
addresses three business problems using classification, regression, 
and clustering techniques.

**Borough:** Greenwich (E09000011)  
**Dataset:** LFB Incidents 2019–2022 (12,861 records)  
**Tools:** Python, pandas, scikit-learn, matplotlib, seaborn

---

## ❓ Business Problems

| # | Problem | Approach |
|---|---|---|
| BP1 | Can incident type (Fire/False Alarm/Special Service) be predicted from property type, time, and call volume? | Classification |
| BP2 | What factors influence first pump attendance time, and can it be predicted? | Regression |
| BP3 | Are there natural clusters of incidents sharing similar resource consumption profiles? | Clustering |

---

## 🔍 Key Findings

- **40.4%** of all Greenwich incidents were False Alarms — nearly equal to fires and special services combined
- **High call volume (3+ calls)** is the strongest predictor of a genuine fire regardless of property type
- **2020** recorded the lowest incident count (2,882) — consistent with COVID-19 lockdown restrictions
- **Incident duration** is the strongest cost driver (r=0.619 with Notional Cost), more so than pump count
- **K-Means (K=3)** identified three distinct incident profiles:
  - Cluster 0: Routine low-resource incidents (90.5%, mean cost £379)
  - Cluster 1: Major fire incidents (2.0%, mean cost £1,958)
  - Cluster 2: Multi-pump residential incidents (7.6%, mean cost £891)
- **BP2 regression R²=0.028** — attendance time is driven by factors absent from the dataset (traffic, station distance, crew availability)

---

## 🤖 Models Built

| Model | Task | Train Score | Test Score |
|---|---|---|---|
| Decision Tree Classifier | BP1 Classification | 62.4% accuracy | 58.5% accuracy |
| Logistic Regression | BP1 Classification | 60.7% accuracy | 57.6% accuracy |
| Decision Tree Regressor | BP2 Regression | R²=0.042 | R²=0.028 |
| Linear Regression | BP2 Regression | R²=0.029 | R²=0.025 |
| K-Means Clustering (K=3) | BP3 Clustering | Silhouette=0.735 | — |

---

## 📊 Visualisations

| Figure | Description |
|---|---|
| EDA Overview | Incident distribution, yearly trends, hourly patterns, property categories |
| Outlier Detection | IQR-based boxplots for attendance time, cost, and pump count |
| Confusion Matrices | BP1 classification performance comparison |
| Actual vs Predicted | BP2 regression scatter plots |
| Elbow + Silhouette | K selection for K-Means clustering |
| Cluster Profiles | Mean feature values and incident composition per cluster |
| Correlation Heatmap | Pearson correlations between resource variables |

---

## 🛠️ Technologies Used

- **Python 3.x**
- **pandas** — data manipulation and preprocessing
- **NumPy** — numerical operations
- **matplotlib / seaborn** — data visualisation
- **scikit-learn** — machine learning models and evaluation
- **scipy** — statistical analysis

---

## 📁 Repository Structure

```
LFB-Greenwich-Incident-Analysis/
│
├── README.md
├── DMA-Coursework.ipynb
├── requirements.txt
└── figures/
    ├── fig_eda_overview.png
    ├── fig_outliers.png
    ├── fig_bp1_confusion.png
    ├── fig_bp2_regression.png
    ├── fig_kmeans_k.png
    ├── fig_clusters.png
    └── fig_correlation.png
```
---

## ⚙️ How to Run

1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/LFB-Greenwich-Incident-Analysis.git
```

2. Install dependencies
```bash
pip install -r requirements.txt
```

3. Download the LFB dataset from the
[London Datastore](https://data.london.gov.uk) and place it in the 
root folder as `LFB_2019_22.csv`

4. Open and run the notebook
```bash
jupyter notebook DMA-Coursework.ipynb
```

---

## 📌 Recommendations to LFB Greenwich

1. **Integrate call volume monitoring** into dispatch prioritisation — 3+ calls strongly indicates a genuine fire
2. **Target AFA management** in non-residential properties — majority of false alarms originate from commercial buildings
3. **Use Cluster 1 profile** (mean 2.58 pumps, 9.89 hours, £1,958 cost) as a benchmark for major incident resource planning
4. **Collect richer data** — station distance, traffic conditions, and crew availability would significantly improve attendance time prediction

---

## 🎓 Academic Context

**Module:** CSI_7_DMA — Data Mining and Analysis  
**Programme:** MSc Data Science  
**University:** London South Bank University  
**Year:** 2025–26

---

## 📄 License

This project is for academic and portfolio purposes.  
Dataset source: London Fire Brigade via London Datastore.
