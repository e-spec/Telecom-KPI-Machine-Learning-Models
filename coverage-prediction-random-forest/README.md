# Coverage Prediction Using Random Forest Regressor

This folder contains a Jupyter notebook that uses a Random Forest Regressor to predict RSRP values for telecom coverage analysis.

## Files
- `CoveragePrediction.ipynb` — loads the dataset, trains the Random Forest model, generates RSRP predictions, and evaluates model performance.
- `radio_propagation_data.csv` — required input dataset used by the notebook.
- `README.md` — folder overview.

## Required CSV file
To run the notebook, make sure this file is available in the same folder:
- `radio_propagation_data.csv`

## What the notebook does
The notebook:
- reads `radio_propagation_data.csv`
- uses `distance_km`, `frequency_mhz`, `tx_power_dbm`, and `antenna_height_m` as input features
- predicts `rsrp_dbm`
- trains a `RandomForestRegressor`
- evaluates results using MAE, MSE, RMSE, and R²
