# EDA for Tower Dataset

## Overview
Exploratory Data Analysis (EDA) for the Tower Height Prediction project. This analysis examines 1,000 cellular tower samples to identify patterns and relationships between network parameters and tower height.

## Key Findings

### Top Predictors of Tower Height
| Feature | Correlation |
|---------|-------------|
| coverage_radius_km | **+0.952** |
| inter_site_distance_km | **+0.902** |
| sinr_db | **-0.876** |
| frequency_band_mhz | **-0.807** |
| rsrp_dbm | **-0.748** |

### Real-World Patterns
| Terrain | Height Range | Signal Quality |
|---------|--------------|----------------|
| Dense Urban | 18-40m | Excellent |
| Urban | 25-50m | Good |
| Suburban | 25-50m | Moderate |
| Rural | 50-100m | Poor |

## Key Insights
- **Positive Correlation**: Larger coverage → Taller towers
- **Negative Correlation**: Poorer signal → Taller towers
- **Bimodal Distribution**: Two distinct peaks at 30-35m and 75-85m
- **Clean Dataset**: No missing values, ready for modeling

## Files
- `tower_height_dataset_1000rows.csv` - Main dataset
- `EDA_Tower_Height_Prediction.ipynb` - Jupyter Notebook

## Next Steps
Proceed to ML modeling using the top 5 correlated features with expected R² > 0.85.

---
Edder Gutierrez
