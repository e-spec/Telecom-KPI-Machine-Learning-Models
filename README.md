# Telecom KPI Machine Learning Models

A focused portfolio of machine learning notebooks for telecom network analytics using KPI-driven modeling.  
The repository covers **six use cases**: coverage prediction, fault detection, throughput estimation, capacity risk classification, downtilt prediction, and tower height prediction.

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

### 6. Tower Height Prediction

**Folder:** `tower-height-prediction-with-4-ML-models/`  
**Models:** `RandomForestRegressor`, `GradientBoostingRegressor`, `XGBRegressor`, `LinearRegression`

Predicts **cellular tower height (meters)** using RF and network planning parameters.

**Key Features:**
- **Dataset**: 1,000 realistic tower samples across 4 terrain types
- **Features**: 11 predictors including `coverage_radius_km`, `sinr_db`, `frequency_band_mhz`, `rsrp_dbm`
- **Target**: `tower_height_m` (18-100m)
- **EDA**: Comprehensive exploratory analysis with correlation heatmaps and feature importance
- **Model Comparison**: Evaluates 4 models with performance metrics

**Performance:**

| Model | R² Score | MAE (m) | RMSE (m) |
|-------|----------|---------|----------|
| **Random Forest** | **0.9674** | **3.25** | **4.25** |
| Gradient Boosting | 0.9658 | 3.33 | 4.36 |
| XGBoost | 0.9653 | 3.39 | 4.39 |
| Linear Regression | 0.9610 | 3.73 | 4.65 |

**Why these algorithms were selected:**  
Multiple algorithms were tested to find the best performer. Random Forest was selected as the final model because it achieved the highest R² (0.9674) while maintaining robustness and interpretability. The ensemble approach handles non-linear relationships between RF parameters and tower height effectively.

**Required Files (place in same folder):**
- `tower_height_dataset_1000rows.csv` — main dataset with 11 features
- `EDA-for-Tower-Dataset/` — exploratory analysis notebooks and outputs

---

## Tools and Libraries

- Python
- Jupyter Notebook
- pandas
- numpy
- matplotlib
- scikit-learn
- XGBoost (for tower height project)

## Objective

These notebooks demonstrate practical applications of machine learning in telecom engineering, with emphasis on:
- structured KPI modeling,
- regression and classification workflows,
- model evaluation,
- and result interpretation.
