# Tower Height Prediction Model

## Overview
This repository contains the machine learning models for predicting cellular tower heights using four different algorithms. The models were trained on 1,000 realistic tower samples across four terrain types.

## Dataset

| Aspect | Details |
|--------|---------|
| **Samples** | 1,000 rows |
| **Features** | 11 predictors |
| **Target** | tower_height_m (18-100m) |
| **Terrains** | Dense Urban, Urban, Suburban, Rural |
| **Data Quality** | No missing values, realistic RF parameters |

### Key Features

| Category | Features |
|----------|----------|
| **Environment** | terrain_type, population_density_km2 |
| **Frequency** | frequency_band_mhz, bandwidth_mhz, coverage_radius_km |
| **Network Planning** | inter_site_distance_km |
| **Antenna/Transmission** | antenna_gain_dbi, transmission_power_w |
| **RF Signal Quality** | sinr_db, rsrp_dbm, rsrq_db |

---

## Model Performance

### Model Comparison

| Model | R² Score | MAE (m) | RMSE (m) |
|-------|----------|---------|----------|
| **Random Forest** | **0.9674** | **3.25** | **4.25** |
| Gradient Boosting | 0.9658 | 3.33 | 4.36 |
| XGBoost | 0.9653 | 3.39 | 4.39 |
| Linear Regression | 0.9610 | 3.73 | 4.65 |

### Best Model: Random Forest 🏆

- **R² Score**: 0.9674 (explains 96.7% of variance)
- **MAE**: 3.25 meters (average prediction error)
- **RMSE**: 4.25 meters (penalizes larger errors)

The Random Forest model outperformed all other models, achieving excellent accuracy in predicting tower heights.

---

## Key Insights

### What Drives Tower Height?

| Correlation Type | Feature | Value | Relationship |
|------------------|---------|-------|--------------|
| **Positive** | coverage_radius_km | +0.952 | Larger coverage → Taller towers |
| **Positive** | inter_site_distance_km | +0.902 | More site spacing → Taller towers |
| **Negative** | sinr_db | -0.876 | Poor signal → Taller towers |
| **Negative** | frequency_band_mhz | -0.807 | Lower frequency → Taller towers |
| **Negative** | rsrp_dbm | -0.748 | Weaker signal → Taller towers |

### Real-World Patterns

| Terrain | Height Range | Signal Quality |
|---------|--------------|----------------|
| **Dense Urban** | 18-40m | High SINR, strong signal |
| **Urban** | 25-50m | Good signal, moderate coverage |
| **Suburban** | 25-50m | Medium signal, medium coverage |
| **Rural** | 50-100m | Low SINR, weak signal |

---

## Sample Predictions

| Terrain | Coverage (km) | SINR (dB) | RSRP (dBm) | Predicted Height |
|---------|--------------|-----------|------------|------------------|
| Urban | 0.3 | 28.0 | -55 | 33.4m |
| Urban | 0.8 | 22.0 | -65 | 34.6m |
| Suburban | 2.5 | 16.0 | -78 | 33.7m |
| **Rural** | **12.0** | **8.0** | **-95** | **74.3m** |
| **Rural** | **18.0** | **5.0** | **-105** | **84.0m** |

---

## Business Impact

- **Faster site planning** for network deployment
- **Cost optimization** by predicting height requirements
- **Better coverage decisions** based on terrain and signal quality
- **Data-driven decisions** moving from intuition to evidence-based planning

---

## Author: Edder Gutierrez


