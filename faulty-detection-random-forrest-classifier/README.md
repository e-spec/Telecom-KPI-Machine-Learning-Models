# Faulty Detection Random Forrest Classifier

This folder contains a Jupyter notebook for faulty hardware detection using a Random Forest classifier on telecom KPI data.

## What the notebook does
- Loads telecom KPI data from `telecom_kpi_data.csv`
- Uses the `faulty` column as the target label
- Splits the dataset into training and test sets
- Trains a `RandomForestClassifier`
- Evaluates the model with accuracy, precision, recall, F1 score, confusion matrix, and classification report
- Displays feature importance for the trained model

## Input features
The model uses telecom KPIs such as:
- `rsrp_dbm`
- `rsrq_db`
- `sinr_db`
- `cqi`
- `tx_power_dbm`
- `vswr`
- `temperature_c`
- `prb_util_dl`
- `drop_call_rate`
- `ho_fail_rate`
- `rrc_sr`
- `cell_availability`
- `packet_loss`
- `latency_ms`
- `alarm_count`

## Model summary
- Algorithm: Random Forest Classifier
- Train/test split: 70% / 30%
- Random state: 42
- Estimators: 100

## Reported results
- Accuracy: 91.33%
- Precision: 82.14%
- Recall: 74.19%
- F1 score: 77.97%

The notebook shows strong overall performance, with room to improve recall for faulty hardware detection.
