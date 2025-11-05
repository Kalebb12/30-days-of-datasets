# 🎓 Student Performance Prediction (Day 1 — 30 Days of Datasets)

This project is part of my **#30DaysOfDatasets** challenge, where I work with a new dataset each day to strengthen my data science and machine learning skills.  

On **Day 1**, I explored the classic **Student Performance Dataset**, analyzing factors that influence final grades and building a model to predict student outcomes.

---

## 📊 Project Overview

The goal of this project was to:
1. Explore the dataset to understand relationships between student attributes and final grades.
2. Visualize patterns in study habits, support systems, and performance.
3. Build a simple regression model to predict students’ **final grade (G3)** based on earlier grades and related features.

---

## 🧠 Dataset Description

The dataset contains information on student demographics, academic performance, and support systems.

| Feature | Description |
|----------|--------------|
| `G1`, `G2`, `G3` | First, second, and final grades (0–20) |
| `studytime` | Weekly study time (numeric) |
| `failures` | Number of past class failures |
| `schoolsup` | Extra educational support (yes/no) |
| `absences` | Number of school absences |
| `sex` | Student gender |
| ... | Other socio-academic attributes |

**Target variable:** `G3` (final grade)

---

## 🔍 Exploratory Data Analysis (EDA)

Key findings:
- The distribution of final grades (`G3`) is **roughly bell-shaped**, with most students scoring mid-range.  
- **Male students** tend to have slightly higher grades and a wider performance spread.  
- Students **without extra educational support** performed better on average — possibly indicating that students needing support were already struggling.
- Some features such as prior grades (`G1`, `G2`) show strong correlation with `G3`.

Example visualization:  
![Actual vs Predicted Final Grades](images/image.png)

---

## ⚙️ Modeling

A **Linear Regression** model was used to predict final grades (`G3`).

### Model Performance
| Metric | Value | Interpretation |
|---------|--------|----------------|
| **Mean Absolute Error (MAE)** | 1.63 | Predictions are off by ~1.6 points on average |
| **Root Mean Squared Error (RMSE)** | 2.38 | Larger errors are slightly penalized |
| **R² Score** | 0.72 | Model explains ~72 % of the variance in final grades |

---

## 📈 Insights

- Prior grades (`G1`, `G2`) are strong predictors of final performance.  
- Absences and extra educational support show inverse relationships with grades.  
- The linear model captures the main trends, but some variance remains unexplained — likely due to nonlinear relationships or external factors not in the dataset.

---