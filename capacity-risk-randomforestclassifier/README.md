# Capacity Risk RandomForest Classifier

This folder contains a Jupyter notebook for predicting telecom capacity risk using a Random Forest classifier.

## What the notebook does
- Loads data from `telecom_capacity_risk_dataset_300.csv`
- Uses `capacity_risk` as the target label
- Splits the dataset into training and test sets
- Trains a `RandomForestClassifier`
- Evaluates the model with accuracy, precision, recall, F1 score, confusion matrix, and classification report
- Includes an example decision-tree-style interpretation of capacity risk rules

## Input features
The model uses telecom KPI features such as:
- `prb_util_dl`
- `prb_util_ul`
- `active_users`
- `sinr_db`
- `avg_mod_order`
- `packet_loss`
- `latency_ms`
- `drop_call_rate`
- `dl_throughput`
- `weekend`

## Model summary
- Algorithm: Random Forest Classifier
- Train/test split: 75% / 25%
- Stratified split enabled
- Random state: 42
- Estimators: 200
- Max depth: 6

This notebook is designed to classify whether a cell is at capacity risk based on observed KPI behavior.
