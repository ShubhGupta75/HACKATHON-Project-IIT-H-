# Model Artifacts - Track A: Predictive Modeling

## Model Information
- **Model Type**: XGBoost
- **Accuracy**: 95.94%
- **R² Score**: 0.902524
- **Training Date**: 2026-03-09 18:57:06
- **Training Samples**: 7420
- **Test Samples**: 1310

## Files Description

1. **best_model.pkl** - Trained model (use with joblib.load())
2. **scaler.pkl** - RobustScaler for input preprocessing
3. **feature_metadata.json** - Feature names and model metadata
4. **performance_metrics.json** - Detailed performance metrics
5. **feature_importance.json** - Feature importance scores
6. **feature_importance.csv** - Feature importance (sorted)
7. **target_statistics.json** - Target variable statistics
8. **sample_prediction.json** - Sample input/output for testing
9. **api_documentation.json** - API endpoint documentation

## Usage Example
```python
import joblib
import numpy as np
import pandas as pd

# Load model and scaler
model = joblib.load('best_model.pkl')
scaler = joblib.load('scaler.pkl')

# Prepare input data (must match training features)
input_data = pd.DataFrame([{ ... }])  # Your input features

# Scale the input
input_scaled = scaler.transform(input_data)

# Make prediction
predictions = model.predict(input_scaled)

# predictions will be array with 6 values:
# [Hardness, Content_Uniformity, Dissolution_Rate, Tablet_Weight, Friability, Disintegration_Time]
```

## Target Variables
Hardness, Content_Uniformity, Dissolution_Rate, Tablet_Weight, Friability, Disintegration_Time

## Performance by Target

- **Hardness**: R²=0.9837, Accuracy=97.29%
- **Content_Uniformity**: R²=0.9126, Accuracy=98.93%
- **Dissolution_Rate**: R²=0.7738, Accuracy=97.87%
- **Tablet_Weight**: R²=0.8728, Accuracy=99.54%
- **Friability**: R²=0.8984, Accuracy=89.04%
- **Disintegration_Time**: R²=0.9737, Accuracy=92.95%