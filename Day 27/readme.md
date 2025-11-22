# Day 27 – Diamond Price Prediction Model

## 📌 Overview

On Day 27 of the *30 Days of Datasets* challenge, we focused on building a **machine learning model to predict diamond prices** using the popular Diamonds dataset. This followed yesterday's exploratory analysis where we examined distributions, identified outliers, and cleaned duplicate records.

The goal for today was to move beyond analysis and build a **working regression model** capable of accurately estimating the price of a diamond based on its physical and categorical attributes.

---

## 📊 Dataset Features

The dataset includes the following variables:

* **carat** – weight of the diamond (most important feature)
* **cut** – quality of the cut (Fair, Good, Very Good, Premium, Ideal)
* **color** – diamond color grading (D–J)
* **clarity** – purity measure (I1 to IF)
* **depth** – total depth %
* **table** – width of top of diamond
* **x, y, z** – physical dimensions in mm
* **price** – target variable (USD)

After identifying duplicates during exploration, we kept the **first occurrence** of each duplicate row.

---

## 🧼 Data Preparation

Before training the model, we performed several preprocessing steps:

### ✔ Dropped duplicate rows

This ensured no repeated observations would bias the model.

### ✔ Split the data

We separated the dataset into **training** and **testing** sets using an 80/20 split.

### ✔ Encoded categorical variables

We applied **One-Hot Encoding** to:

* cut
* color
* clarity

### ✔ Model Input Setup

Numerical features were passed through unchanged:

* carat, depth, table, x, y, z

---

## 🤖 Model Training

We trained a **Random Forest Regressor**, a powerful ensemble model that performs well on structured datasets.

The model pipeline included:

1. Preprocessing (One-Hot Encoding + numerical passthrough)
2. Random Forest with 300 trees

Training was done with:

```
RandomForestRegressor(n_estimators=300, random_state=42)
```

---

## 📈 Model Performance

After training, the model was evaluated on the test set using RMSE, MAE, and R².

### **Results:**

* **RMSE:** 587.63
* **MAE:** 282.85
* **R² Score:** 0.9773

### 💡 Interpretation

* The model explains **97.7% of all price variation**.
* Average prediction error is only **$282**.
* Errors remain low even with high-value diamonds.

This is an **excellent performance**, and well within expectations for this dataset.

---

## 📚 What We Achieved Today

* Cleaned and prepared the diamonds dataset
* Encoded categorical features
* Built an end-to-end machine learning pipeline
* Trained a high-performing Random Forest Regressor
* Evaluated the model using standard regression metrics
* Achieved near state-of-the-art accuracy for price prediction

---

## 🚀 Next Steps

For tomorrow (Day 28), we can:

* Plot **feature importance** to see what drives price the most
* Compare multiple models (Linear Regression, XGBoost, etc.)
* Tune hyperparameters for improved accuracy
* Deploy or save the trained model

Let me know what direction you'd like to take next!
