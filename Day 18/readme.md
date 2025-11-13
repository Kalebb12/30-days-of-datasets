# 🚗 Day 18 — Car Price Prediction (Exploratory Analysis)

This day focuses on understanding and preparing the Car Price Prediction dataset. The goal is to explore the data, understand the relationships between features, engineer useful variables, and prepare the dataset for modeling.

## 📘 Dataset Overview

The dataset contains detailed information about cars including brand, model, year, mileage, condition, and fuel type — all useful for predicting the car's price.

**Columns:**

| Column | Description |
| :--- | :--- |
| **Car ID** | Unique identifier for each record |
| **Brand** | Car manufacturer (e.g., Tesla, BMW, Audi) |
| **Model** | Specific model (e.g., Model X, A4, Mustang) |
| **Year** | Year of manufacturing |
| **Engine Size** | Engine capacity in liters |
| **Fuel Type** | Petrol, Diesel, Electric, Hybrid |
| **Transmission** | Manual or Automatic |
| **Mileage** | Total distance traveled |
| **Condition** | New, Used, Like New |
| **Price** | Target variable |

## 🔍 Exploratory Data Analysis (EDA)

#### ✔ Checked:
- Data types
- Unique values for each categorical variable
- Distribution of conditions, brands, fuel types
- Basic summary statistics
- Initial correlations

#### 🟦 Categorical Summary Sample:
- **Brand**
  - 7 unique brands
  - Most common: Toyota, Audi, BMW, Mercedes
- **Fuel Type**
  - Diesel (655), Petrol (630), Electric (614), Hybrid (601)
- **Transmission**
  - Manual (1308), Automatic (1192)
- **Condition**
  - Used (855), Like New (836), New (809)

#### 📊 Visualizations
Several plots were created to understand relationships and distributions:
- Distribution of car prices
- Price vs Brand
- Price vs Fuel Type
- Price vs Transmission
- Price vs Condition
- Scatter plots for Year and Mileage
- Correlation heatmap for numeric features

## 🧪 Key Insight

Raw numeric features (like `Year` or `Mileage`) did not show strong simple linear correlations with `Price`. This suggested that:
- Relationships may be nonlinear.
- Some fields might need transformation.
- Categorical features likely carry stronger predictive signals.

## 🧱 Feature Engineering

To improve prediction quality, several preparation steps were taken:

#### ✔ Removed Useless Columns
- `Car ID` dropped (no predictive value).

#### ✔ Created a More Useful Feature
- `Car_Age = 2025 - Year`
- *Age models depreciation better than the raw year.*

#### ✔ Cleaned Categorical Labels
- Ensured consistent formatting (e.g., stripping whitespace, applying title case).

#### ✔ Prepared Encoding Strategy
- **Low-cardinality categories** → One-hot encoding
- **High-cardinality** (`Model`) → Label encoding

These processed features will be used tomorrow for building regression models.

***

## 🎯 Progress Summary for Today
- Loaded and inspected the dataset
- Explored categorical distributions
- Created meaningful visualizations
- Identified weak numeric correlations
- Engineered `Car_Age`
- Cleaned categorical variables
- Planned encoding strategy
- Prepared data for modeling