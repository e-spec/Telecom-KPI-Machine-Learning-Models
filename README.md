# Telecom KPI Machine Learning Models

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange)
![scikit-learn](https://img.shields.io/badge/ML-scikit--learn-f7931e)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

A focused portfolio of machine learning notebooks for telecom network analytics using KPI-driven modeling.  
The repository covers four use cases: **coverage prediction**, **fault detection**, **throughput estimation**, and **capacity risk classification**.

---

## Repository Structure

```text
.
├── coverage_prediction.ipynb          # RSRP prediction with Random Forest Regression
├── fault_detection.ipynb              # Network fault classification with Random Forest
├── throughput_prediction.ipynb        # Throughput estimation with Multiple Linear Regression
├── capacity_risk_classification.ipynb # Capacity risk classification with Random Forest
├── telecom_capacity_risk_dataset_300.csv
├── telecom_mlr_dataset.csv
├── requirements.txt
├── LICENSE
└── README.md
```

---

## Projects

### 1. Coverage Prediction
**File:** `coverage_prediction.ipynb`  
**Model:** `RandomForestRegressor`

Predicts **RSRP** from:
- distance
- frequency
- transmit power
- antenna height

**Why this algorithm was selected:**  
Random Forest Regression was chosen because radio coverage behavior is often **nonlinear** and influenced by interactions between engineering variables. It is well suited for small structured datasets and provides more flexibility than a simple linear model.

---

### 2. Fault Detection
**File:** `fault_detection.ipynb`  
**Model:** `RandomForestClassifier`

Classifies telecom network states as **faulty** or **normal** using KPIs such as:
- RSRP, RSRQ, SINR, CQI
- transmit power, VSWR, temperature
- PRB utilization
- drop call rate, handover failure rate
- packet loss, latency, alarm count

**Why this algorithm was selected:**  
Random Forest Classification was selected because telecom faults usually depend on **multiple KPI interactions rather than a single threshold**. The model is robust, interpretable through feature importance, and performs well on structured classification tasks.

---

### 3. Throughput Prediction
**File:** `throughput_prediction.ipynb`  
**Model:** `LinearRegression`

Estimates **throughput (Mbps)** from:
- bandwidth
- MIMO layers
- active users
- PRB utilization
- SINR
- CQI
- packet loss
- latency
- weekend indicator

**Why this algorithm was selected:**  
Multiple Linear Regression was chosen as a strong **baseline model** because throughput is often influenced by several measurable KPIs in a way that can be approximated linearly. It also provides clear interpretability through coefficients, making it useful for analysis and explanation.

---

### 4. Capacity Risk Classification
**File:** `capacity_risk_classification.ipynb`  
**Model:** `RandomForestClassifier`

Predicts **capacity risk** using:
- DL and UL PRB utilization
- active users
- SINR
- average modulation order
- packet loss
- latency
- drop call rate
- downlink throughput
- weekend indicator

Includes:
- confusion matrix
- classification report
- feature importance
- decision tree visualization

**Why this algorithm was selected:**  
Random Forest was chosen because capacity risk is typically driven by **complex nonlinear relationships** among utilization, user load, radio quality, and service KPIs. It captures these interactions effectively while still allowing feature-level interpretation.

---

## Results Snapshot

Summary of model evaluation metrics across all four notebooks:

| Project | Model | Key Metric(s) |
|---|---|---|
| Coverage Prediction | Random Forest Regressor | MAE: 3.82 dBm · RMSE: 4.16 dBm · R²: 0.89 |
| Fault Detection | Random Forest Classifier | Accuracy: 1.00 · Precision: 1.00 · Recall: 1.00 · F1: 1.00 |
| Throughput Prediction | Multiple Linear Regression | MAE: 1.96 Mbps · RMSE: 2.29 Mbps · R²: 0.97 |
| Capacity Risk Classification | Random Forest Classifier | Accuracy: 1.00 · Precision: 1.00 · Recall: 1.00 · F1: 1.00 |

> **Note:** Metrics are computed on the sample datasets bundled with this repository. See [Dataset Notes](#dataset-notes) for context.

---

## Dataset Notes

The CSV files included in this repository (`telecom_capacity_risk_dataset_300.csv` and `telecom_mlr_dataset.csv`) are **sample / demo datasets** generated for illustrative purposes. They are intended to demonstrate modeling workflows and are not derived from a production network or real operator data. Metrics and feature importance values reflect performance on these synthetic samples and should not be interpreted as benchmarks for production deployment.

---

## Setup

**Prerequisites:** Python 3.8 or later and `pip`.

```bash
# 1. Clone the repository
git clone https://github.com/e-spec/Telecom-KPI-Machine-Learning-Models.git
cd Telecom-KPI-Machine-Learning-Models

# 2. (Optional) Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt
```

---

## How to Run

```bash
# Launch Jupyter
jupyter notebook
```

Open any of the four notebooks in your browser and run all cells from top to bottom (`Kernel → Restart & Run All`).

Each notebook is self-contained: it loads data, preprocesses it, trains the model, and prints evaluation metrics inline.

---

## Tools and Libraries

- Python 3.x
- Jupyter Notebook
- pandas
- numpy
- matplotlib
- scikit-learn

---

## Objective

These notebooks demonstrate practical applications of machine learning in telecom engineering, with emphasis on:
- structured KPI modeling,
- regression and classification workflows,
- model evaluation,
- and result interpretation.

---

## License

This project is licensed under the [MIT License](LICENSE).
