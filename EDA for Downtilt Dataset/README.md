# EDA for Downtilt Dataset

## Overview
This folder contains the Exploratory Data Analysis (EDA) for the **Downtilt Prediction** project. The goal of this analysis is to understand the structure, relationships, and key patterns in the dataset before building predictive models.

## Dataset
- **Source:** `downtilt_dataset_300.csv`
- **Total Records:** 300 cell towers
- **Target Variable:** `downtilt_deg` (Antenna downtilt angle in degrees)
- **Features:** 16 (15 numeric, 1 categorical)

## Key Insights from EDA

### Target Variable (downtilt_deg)
- **Range:** 1.0° to 11.33°
- **Mean:** 5.91° | **Median:** 6.15°
- **Distribution:** Right-skewed (long tail toward high urban values)
- **Interpretation:** Most towers fall in the 4-8° range (suburban), with extremes representing rural (low) and dense urban (high) environments.

### Top Correlations with Downtilt
| Feature | Correlation | Interpretation |
|---------|-------------|----------------|
| `user_density` | +0.774 | Dense areas → More downtilt |
| `traffic_load_pct` | +0.753 | Busy towers → More downtilt |
| `capacity_utilization_pct` | +0.718 | Overloaded towers → More downtilt |
| `inter_site_distance_km` | -0.794 | Farther apart → Less downtilt |
| `coverage_km2` | -0.726 | Larger coverage → Less downtilt |

### Environment Breakdown
- **Urban:** High downtilt (8-11°), high density, high traffic
- **Suburban:** Moderate downtilt (5-7°), balanced features
- **Rural:** Low downtilt (1-3°), wide coverage, sparse users

### Data Quality
- **Missing Values:** None detected
- **Outliers:** Present (e.g., 44 outliers for `coverage_km2`, 40 for `inter_site_distance_km`) but represent real network diversity (urban vs rural extremes) – not errors.

### Multicollinearity Warning
- `site_height_m` and `antenna_height_m` are nearly identical (`r = 0.992`). **Recommendation:** Drop one to reduce redundancy.

## Notebook Contents
- `downtilt_eda.ipynb` – Main notebook with all visualizations and analysis

## Key Visualizations
1. **Target Distribution** – Histogram, boxplot, violin plot of `downtilt_deg`
2. **Correlation Heatmap** – Full correlation matrix of numeric features
3. **Environment Comparison** – Downtilt by environment (urban, suburban, rural)
4. **Feature Relationships** – Scatter plots of top features vs downtilt
5. **Outlier Analysis** – IQR-based outlier detection per feature
6. **Pairplot** – Relationships between top features

## How to Run
1. Ensure the dataset (`downtilt_dataset_300.csv`) is in the same directory.
2. Run the Jupyter notebook `downtilt_eda.ipynb`.
3. All plots will be generated inline.

## Next Steps
- Use insights from EDA to guide feature selection for the regression model.
- Address multicollinearity (drop redundant height features).
- Prepare data for model training (preprocessing, train/test split).

## Author
- **Edder Gutierrez**

## Date
- **June 2026**
