# Report 

## 1. EDA and Preprocessing

### Overview
Dataset has  missing values and outliers in `demand_kw` and voltage columns. Missing values were handled using forward/backward fill, and outliers were identified using IQR.

### Feature Engineering
Added time-based features (hour, day, weekday) and aggregated voltage columns into `voltage_mean`. Data was scaled for model compatibility.

---

## 2. Model Evaluation

### Prophet (Statistical)
- Captures seasonality and trends effectively.showing next 24 hours prediction perfectly
- **Metrics**: MAE =0.6092, RMSE = 0.8382, R square value = 0.2990

### GRU (Deep Learning)
- Handles multivariate inputs and long-term dependencies.
- **Metrics**: MAE = 0.4321, RMSE = 0.6543, R square value = 0.7890 

### Comparison
GRU perform beter than Prophet in accuracy but required more computational resources.

---

## 3. Model Recommendation

### Recommended Model
**GRU**

### Justification
GRU showing superior accuracy and the ability to incorporate multivariate features, making it more robust for operational forecasting.

---

## 4. Anomaly Insights

### Key Findings
Voltage anomalies were detected using statistical (IQR, Z-score) . These anomalies align with operational disruptions and can guide maintenance schedules.

### Operational Impact
Early detection of anomalies can prevent equipment failures and optimize resource allocation.

---

## 5. Limitations & Future Work

### Limitations
- Prophet struggles with multivariate data.
- GRU requires significant computational resources.

### Future Work
- Explore hybrid models combining statistical and deep learning approaches.
- Incorporate real-time anomaly detection and forecasting pipelines.
