# 🌦️ Day 15: Weather Prediction Model

## 📘 Project Overview

For Day 15 of the **30 Days of Datasets Challenge**, we explored weather data to build a model capable of predicting the type of weather (sun, rain, fog, snow, or drizzle) using features like temperature, wind, and precipitation.

The dataset captures daily weather patterns showing a cyclical trend — cooler at the start of the year, peaking mid-year, and dropping again towards the end.

---

## 🧾 Dataset Summary

| Feature         | Description                                |
| --------------- | ------------------------------------------ |
| `date`          | Observation date                           |
| `precipitation` | Amount of rainfall or snow (mm)            |
| `temp_max`      | Maximum daily temperature                  |
| `temp_min`      | Minimum daily temperature                  |
| `wind`          | Wind speed (m/s)                           |
| `weather`       | Categorical weather type (target variable) |

The dataset included categories: `drizzle`, `rain`, `sun`, `snow`, and `fog`.

---

## 🧠 Model Building

We trained multiple models to classify weather types based on meteorological features. The key steps were:

1. **Data Preprocessing:**

   * Encoded categorical values.
   * Handled missing data and outliers.
   * Split dataset into training and testing sets.

2. **Baseline Model:** Logistic Regression achieved ~82% accuracy but poor balance across rare weather types.

3. **Improved Model:** Random Forest with class balancing improved recall for underrepresented classes.

4. **Hyperparameter Tuning:** Used `GridSearchCV` to find the best combination of model parameters.

**Best Parameters:**

```python
{
  'max_depth': 20,
  'max_features': 'sqrt',
  'min_samples_leaf': 2,
  'min_samples_split': 10,
  'n_estimators': 300
}
```

**Best Macro F1 Score:** `0.5857`

---

## 📊 Final Model Performance

| Class   | Precision | Recall | F1-Score | Support |
| ------- | --------- | ------ | -------- | ------- |
| Drizzle | 0.18      | 0.22   | 0.20     | 9       |
| Fog     | 0.25      | 0.20   | 0.22     | 25      |
| Rain    | 0.96      | 0.91   | 0.94     | 120     |
| Snow    | 0.57      | 0.50   | 0.53     | 8       |
| Sun     | 0.77      | 0.84   | 0.81     | 131     |

**Accuracy:** `0.78`
**Macro Avg F1:** `0.54`
**Weighted Avg F1:** `0.78`

---

## 🧩 Insights

* The model performs **best** for `rain` and `sun` conditions.
* There is **improvement** in minority classes (`snow`, `drizzle`, `fog`) after tuning.
* Despite a small drop in total accuracy, the model is **more balanced** and fair across all weather types.

---

## 💡 Next Steps

* Apply **SMOTE** or **oversampling** to improve minority class recall.
* Experiment with **Gradient Boosting** (XGBoost, CatBoost, or LightGBM).
* Add **time-related features** like `month` or `season` to capture seasonal patterns.

---

## 🏁 Summary

| Metric          | Result                   |
| --------------- | ------------------------ |
| Model           | Random Forest Classifier |
| Accuracy        | 78%                      |
| Macro F1        | 0.54                     |
| Best Parameters | Tuned via GridSearchCV   |

> The final model shows strong predictive ability for common weather patterns and improved fairness across all classes.
