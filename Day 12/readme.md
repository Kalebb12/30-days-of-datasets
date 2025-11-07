# Global Earthquake-Tsunami Risk Assessment Dataset

## Overview
The Global Earthquake-Tsunami Risk Assessment Dataset is a comprehensive, machine learning-ready dataset containing seismic characteristics and tsunami potential indicators for 782 significant earthquakes recorded globally from 2001 to 2022. This dataset is specifically designed for tsunami risk prediction, earthquake analysis, and seismic hazard assessment applications.

## Dataset Information
Total Records: 782 earthquakes
Time Period: January 1, 2001 to December 31, 2022 (22 years)
Geographic Coverage: Global (Latitude: -61.85° to 71.63°, Longitude: -179.97° to 179.66°)
File Format: CSV
File Size: ~41KB
Missing Values: None (100% complete dataset)
Target Variable: Tsunami potential indicator (binary classification)

## Key Features
🌊 Tsunami Classification
Non-Tsunami Events: 478 records (61.1%)
Tsunami-Potential Events: 304 records (38.9%)
Balanced Dataset: Suitable for binary classification tasks

## Machine Learning Applications
Tsunami Risk Prediction: Binary classification using seismic parameters
Early Warning Systems: Real-time tsunami threat assessment
Hazard Mapping: Geographic risk zone identification
Magnitude Estimation: Earthquake strength prediction from network data

## Citation
Original Source:(Earthquake Dataset on Kaggle)[https://www.kaggle.com/datasets/warcoder/earthquake-dataset]

## 📘 Dataset Overview

| Column | Description |
|--------|--------------|
| `magnitude` | Earthquake magnitude (Richter scale) |
| `cdi` | Community Determined Intensity (felt shaking) |
| `mmi` | Modified Mercalli Intensity (instrumental shaking) |
| `sig` | Significance – overall impact metric |
| `nst` | Number of stations that reported the event |
| `dmin` | Distance to nearest reporting station (degrees) |
| `gap` | Azimuthal gap between reporting stations |
| `depth` | Earthquake depth (km) |
| `latitude`, `longitude` | Epicenter coordinates |
| `Year`, `Month` | Date of occurrence |
| `tsunami` | Target variable (1 = tsunami occurred, 0 = no tsunami) |

 **Key Takeaways**
- Tsunami label strongly tied to **network coverage (nst, dmin)**, not magnitude.
- “Year” correlates with many variables — indicates **dataset bias or structural shift**.
- Intensity metrics (MMI/CDI) are strongly interrelated; handle multicollinearity carefully.
---

## 1. Station Network Effects

### dmin (Distance to Nearest Station)
- Tsunami=1 events have **higher medians** and a **wider spread**, with many large outliers.  
- 🔍 *Interpretation:* Tsunami-generating quakes are typically **offshore**, so the nearest station is farther away.

### nst (Number of Reporting Stations)
- Tsunami=1 events show **lower medians** and **tighter lower quartiles**, with few high outliers.  
- 🔍 *Interpretation:* Offshore events are recorded by **fewer stations**, consistent with the negative `nst ↔ dmin` relationship.

**Combined Insight:**  
Tsunami events = larger `dmin` + fewer `nst`.  
However, both features reflect **monitoring coverage** rather than purely physical causes.

---

## 2. Temporal Drift (Structural Break Around 2013–2014)

| Trend | Observation |
|-------|--------------|
| **NST** | Drops sharply from 400–600 to near zero, then partially recovers after 2021 |
| **DMIN** | Jumps from ~0 to 1.5–4+ and remains high |
| **Tsunami Frequency** | Rises from near 0 to 0.6–0.8 consistently after 2014 |

**Interpretation:**  
This indicates a **coverage and data source shift**, not a physical phenomenon.  
Later years represent mostly **offshore events** (fewer stations, greater station distance) — which also coincide with many tsunami flags.

**Modeling Implication:**  
Strong confounding between `Year`, `NST`, `DMIN`, and `tsunami`.  
Using `Year` (or proxies) may cause **data leakage** and **spurious correlations**.

---

## 3. Depth–Intensity Relationship

- Clear **negative relationship**: as `depth` increases, felt intensity (`MMI`) decreases.
- **High MMI (7–9)** occurs almost exclusively at **shallow depths (<100 km)**.
- **Deep events (>300 km)** mostly have **low intensity (MMI 2–4)**, with few exceptions for massive quakes.
- Shallow events show large spread → other factors (magnitude, site effects, population distance) matter.

**Implications:**  
- Depth is a strong predictor of **surface shaking**.  
- Matches earlier correlation (mmi vs depth ≈ −0.5).  
- Shallow earthquakes = higher potential for local damage and tsunami generation.

---

## 4. Magnitude–Significance Relationship

- **Positive trend:** larger magnitudes generally → higher significance (`r ≈ 0.52`).
- **Rising lower envelope:** large quakes are rarely low significance.
- **Large variance:** significance also depends on **depth, proximity, intensity**, etc.
- **Heteroscedasticity:** variance of `sig` increases with magnitude — use **robust regression** instead of plain OLS.

---

## 5. Geographic Patterns

- **Tsunami events cluster along coastlines and subduction zones**, particularly:
  - Japan–Kuril arc  
  - Philippines–Indonesia  
  - Tonga–Kermadec  
  - Alaska–Aleutians  
  - Central & South America  
  - Southwest Pacific islands
- **Non-tsunami** quakes appear both along boundaries and inland regions.

**Interpretation:**  
- Confirms offshore clustering of tsunami events.  
- Matches earlier findings (larger `dmin`, fewer `nst`).  
- Regional imbalance likely reflects catalog coverage after 2014.

---

## Overall Insights

| Theme | Summary |
|--------|----------|
| **Data Quality** | Significant temporal and spatial biases post-2013; network drift dominates patterns. |
| **Physical Relationships** | Depth ↔ Intensity strong; Magnitude ↔ Significance moderate; Tsunami ↔ Network variables confounded. |
| **Modeling Risks** | Avoid raw `Year` and correlated variables (`nst`, `dmin`) as predictors without decorrelation or stratification. |
| **Next Step** | Apply feature engineering and build classification models (logistic regression, tree-based, or XGBoost) using **depth, intensity, and spatial features** for tsunami prediction. |

---

## 🪄 Visual Summary (Recommended Plots)

| Plot | Purpose |
|------|----------|
| Boxplots: `tsunami` vs (`dmin`, `nst`) | Offshore vs onshore signature |
| Lineplots: `Year` vs (`nst`, `dmin`, `tsunami`) | Detect data drift |
| Scatter: `depth` vs `mmi` | Physical attenuation |
| Scatter: `magnitude` vs `sig` | Impact scaling |
| Map: `longitude` vs `latitude` | Spatial clustering of tsunami events |

---

> **Conclusion:**  
> The dataset shows clear relationships between monitoring coverage, event location, and tsunami labeling.  
> Physical predictors like **depth** and **intensity** remain more robust than raw magnitude.  
> Future modeling must handle **temporal drift and multicollinearity** to avoid misleading tsunami predictions.
