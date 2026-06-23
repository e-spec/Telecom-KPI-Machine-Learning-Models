# Telecom KPI Machine Learning Models

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange)
![scikit-learn](https://img.shields.io/badge/ML-scikit--learn-f7931e)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

A focused portfolio of machine learning notebooks for telecom network analytics using KPI-driven modeling.  
The repository covers five use cases: **coverage prediction**, **fault detection**, **throughput estimation**, **capacity risk classification**, and **downtilt prediction**.

## Projects

### 1. Coverage Prediction
**File:** `CoveragePrediction.ipynb`  
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
**File:** `FAULTDETECTIONv2.ipynb`  
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
**File:** `MLR for TPUT.ipynb`  
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
**File:** `CapacityRisk w-RandomForestClass.ipynb`  
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

### 5. Downtilt Prediction
**File:** `downtilt_linear_regression_notebook.ipynb`  
**Model:** `LinearRegression` (Multiple Linear Regression)

Predicts **antenna downtilt angle (degrees)** from telecom KPI features.

**Key Features:**
- loads and preprocesses `downtilt_dataset_300.csv`
- prepares input features and target variable (`downtilt_deg`)
- trains a Multiple Linear Regression model
- evaluates performance using MAE, RMSE, R², and cross-validation
- visualizes feature importance and prediction plots

**Required Files (place in same folder):**
- `downtilt_dataset_300.csv` — main dataset required by the notebook
- `test_combinations.csv` — additional file for testing/input combinations (if used separately)

**Why this algorithm was selected:**  
Multiple Linear Regression was selected as an interpretable baseline for downtilt prediction because downtilt is often a function of multiple measurable network parameters. The linear approach provides clear coefficient interpretation, making it useful for engineering analysis and understanding the relationship between KPIs and downtilt settings.

---

#### EDA for Downtilt Dataset
**Folder:** `EDA for Downtilt Dataset/`  
**File:** `downtilt_eda.ipynb`

Exploratory Data Analysis for the downtilt prediction dataset.

**Key Insights:**
- **Target:** `downtilt_deg` ranges 1.0°–11.33° (mean: 5.91°, median: 6.15°)
- **Environment:** Urban (8-11°), Suburban (5-7°), Rural (1-3°)
- **Top Correlations:**
  - Positive: `user_density` (+0.77), `traffic_load` (+0.75), `capacity_utilization` (+0.72)
  - Negative: `inter_site_distance` (-0.79), `coverage_km2` (-0.73)
- **Data Quality:** No missing values. Outliers reflect real urban/rural diversity.
- **Multicollinearity:** `site_height_m` and `antenna_height_m` are nearly identical (r = 0.99) – consider dropping one.

**Visualizations:** Distribution plots, correlation heatmap, environment comparison, feature scatter plots, outlier detection, and pairplot.

**How to Run:** Place `downtilt_dataset_300.csv` in the same folder and run `downtilt_eda.ipynb`.

---

## Tools and Libraries

- Python
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

## Suggested GitHub Description

**Machine learning notebooks for telecom KPI analytics, including coverage prediction, fault detection, throughput estimation, capacity risk modeling, and downtilt prediction.**
