# 🌊 Day 13 — Earthquake Tsunami Prediction

## 📘 Overview

This project explores the relationship between earthquake characteristics and the likelihood of a **tsunami event**.
The dataset contains global seismic event information (magnitude, depth, intensity, number of stations, etc.), and the goal is to build a model that can **predict whether an earthquake generates a tsunami**.

This analysis prioritizes **physical interpretability** over blind accuracy — ensuring that predictions reflect **real-world geophysical behavior** rather than **dataset bias**.

---

## 📊 Dataset Description

| Feature                 | Description                                             |
| ----------------------- | ------------------------------------------------------- |
| `magnitude`             | Richter scale measure of earthquake energy              |
| `cdi`                   | Community Decimal Intensity (publicly reported shaking) |
| `mmi`                   | Modified Mercalli Intensity (instrumental shaking)      |
| `sig`                   | USGS significance score (composite impact metric)       |
| `nst`                   | Number of reporting seismic stations                    |
| `dmin`                  | Distance to nearest station (degrees)                   |
| `gap`                   | Azimuthal gap in station coverage                       |
| `depth`                 | Depth of the earthquake in km                           |
| `latitude`, `longitude` | Geographic coordinates of the epicenter                 |
| `Year`, `Month`         | Event time                                              |
| `tsunami`               | Target variable (1 = tsunami generated, 0 = none)       |

---

## 🔍 Exploratory Analysis Summary

### Correlation Insights

* **Strong positive correlation**: `magnitude ↔ sig` (larger quakes = higher significance)
* **Negative correlation**: `mmi ↔ depth` (deep quakes produce weaker surface shaking)
* **Monitoring bias**: `Year ↔ tsunami`, `Year ↔ nst`, `Year ↔ dmin` — later years have fewer stations but more tsunami flags

### Key Observations

* Tsunami events have **larger station distances (dmin)** and **fewer stations (nst)** — consistent with **offshore origin**.
* **Shallow earthquakes (<100 km)** produce higher surface intensity (`mmi`), increasing tsunami potential.
* A **structural break** around **2013–2014** shows fewer stations and higher tsunami frequency, suggesting **data collection drift**, not a geophysical shift.

### Implications

* Avoid using `Year`, `nst`, and `dmin` directly in prediction to prevent **data leakage**.
* Use physically meaningful predictors (`magnitude`, `depth`, `mmi`, etc.).

---

## 🤖 Modeling Approach

### Step 1: Data Preparation

* Removed temporal and monitoring bias columns (`Year`, `Month`).
* Checked multicollinearity (high correlation among `sig`, `mmi`, and `cdi`).
* Selected robust physical predictors for the base model.

### Step 2: Models Tested

| Model                   | Scaling  | Class Weight | Notes                       |
| ----------------------- | -------- | ------------ | --------------------------- |
| **Logistic Regression** | Scaled   | Balanced     | Interpretable baseline      |
| **Random Forest**       | Unscaled | Balanced     | Captures nonlinear patterns |

### Step 3: Evaluation Metrics

* **Accuracy**: Overall prediction correctness
* **Precision**: How many predicted tsunamis are correct
* **Recall**: How many actual tsunamis are detected (critical)
* **F1-score**: Balance between precision and recall
* **ROC-AUC**: Discrimination ability between tsunami/non-tsunami

---

## 🔢 Model Results (Baseline)

| Metric                | Logistic Regression | Random Forest |
| --------------------- | ------------------- | ------------- |
| Accuracy              | 0.62                | 0.62          |
| Precision (tsunami=1) | 0.54                | 0.52          |
| Recall (tsunami=1)    | 0.21                | 0.48          |
| F1-score (tsunami=1)  | 0.31                | 0.50          |
| ROC-AUC               | 0.55                | 0.60          |

### Interpretation
* **Logistic Regression**: Linear model underfits nonlinear tsunami generation behavior. High precision, poor recall.
* **Random Forest**: Better recall and overall balance; recognizes some complex interactions.
* Both models confirm that **pure magnitude** is insufficient — spatial and depth-related features matter.

---

## 🛠️ Next Steps (Fine-Tuning Plan)

1. **Balance the dataset** using SMOTE to improve tsunami recall.
2. **Hyperparameter tuning** for Random Forest (grid search on `max_depth`, `n_estimators`, etc.).
3. **Test XGBoost model** for boosted nonlinear learning.
4. **Evaluate feature importances** to identify top geophysical predictors.
5. **Validate temporal robustness** by testing model performance across different years.

---

## 💡 Key Takeaways

* Dataset exhibits **monitoring bias**; physically driven modeling is essential.
* **Depth** and **intensity (MMI)** are robust tsunami indicators; **Year** and **station coverage** introduce bias.
* Random Forest outperforms linear methods but needs tuning and class balancing.
* Future models should combine **geophysical insight** and **robust ML techniques** to ensure generalizability.

---

## 📈 Visualization Highlights

* **Heatmap:** Revealed multicollinearity among `sig`, `mmi`, `cdi`.

---

## 👩‍💻 Learning Reflections
> This project emphasized that building a reliable ML model isn’t just about accuracy.
> It’s about **understanding the data-generating process**, avoiding leakage, and respecting physical reality.
> The next phase will fine-tune the Random Forest and XGBoost models with balanced data for improved tsunami recall.
