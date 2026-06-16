# Downtilt Prediction Using MLR

This folder contains a Jupyter notebook that builds a Multiple Linear Regression (MLR) model to predict antenna downtilt from telecom KPI features.

## Files
- `downtilt_linear_regression_notebook.ipynb` — loads the dataset, preprocesses features, trains the MLR model, evaluates performance, and visualizes results.
- `downtilt_dataset_300.csv` — main required dataset loaded by the notebook.
- `test_combinations.csv` — additional file for testing/input combinations, if used separately.
- `README.md` — folder overview.

## Required CSV files
To run the notebook, make sure this CSV file is present in the same folder:
- `downtilt_dataset_300.csv`

## What the notebook does
The notebook:
- reads `downtilt_dataset_300.csv`
- prepares input features and target variable (`downtilt_deg`)
- trains a Multiple Linear Regression model
- evaluates the model using MAE, RMSE, R², and cross-validation
- shows feature importance and prediction plots
