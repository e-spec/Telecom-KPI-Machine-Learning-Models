# Throughput Prediction MLR

This folder contains a Jupyter notebook that uses Multiple Linear Regression (MLR) to predict telecom network throughput from KPI data.

## What the notebook does
- Loads data from `telecom_mlr_dataset.csv`
- Uses `throughput_mbps` as the prediction target
- Trains a `LinearRegression` model on telecom KPI features
- Evaluates predictions with MAE, MSE, RMSE, and R² score
- Visualizes results with actual vs predicted and residual plots

## Input features
- `bandwidth_mhz`
- `mimo_layers`
- `active_users`
- `prb_util_dl`
- `sinr_db`
- `cqi`
- `packet_loss`
- `latency_ms`
- `weekend`

## Model summary
- Algorithm: Multiple Linear Regression
- Train/test split: 80% / 20%
- Random state: 42

## Reported performance
- MAE: 1.96
- MSE: 5.22
- RMSE: 2.29
- R² Score: 0.97
