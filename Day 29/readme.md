Here is a `README.md` tailored to your notebook and the specific analysis you performed for Day 29.

***

# Day 29: Titanic Survival Analysis 🚢

This repository contains the work for **Day 29 of the 30 Days of Datasets** challenge. Today's notebook focuses on Exploratory Data Analysis (EDA) and cleaning of the famous Titanic dataset (`tested.csv`).
[kaggle dataset](https://www.kaggle.com/datasets/brendan45774/test-file)

## 📂 Project Overview

The goal of this project was to clean the raw data, handle missing values using statistical grouping, and analyze the correlations between passenger class, gender, and survival rates.

**Dataset:** Titanic Dataset (`tested.csv`)
**Rows:** 418
**Columns:** 12

## 🛠️ Tech Stack

*   **Python**
*   **Pandas** (Data manipulation)
*   **Matplotlib** (Visualization)
*   **Seaborn** (Heatmaps and styling)

## 📊 Workflow & Data Cleaning

1.  **Missing Value Imputation**:
    *   **Age:** Missing values were filled using the median age grouped by `Sex` and `Pclass` (Passenger Class) to ensure accuracy.
    *   **Fare:** Missing values were filled using the median fare grouped by `Pclass`.
    *   **Cabin:** The column was dropped due to a high volume of missing data.
2.  **Duplicate Check**: Confirmed no duplicate rows existed in the dataset.
3.  **Visualization**: Created histograms and bar charts to understand the demographics.

## 🔍 Key Findings

*   **Passenger Class Correlation**: There is a negative correlation between `Pclass` and `Survived`.
    *   **1st Class:** Highest average survival rate (~46%).
    *   **3rd Class:** As class number increases (to 3), survival chances decrease (~33%).
*   **Gender Split**: The dataset shows a distinct survival pattern based on sex:
    *   **Females:** 152 survivors (100% survival rate in this specific subset).
    *   **Males:** 266 non-survivors (0% survival rate in this specific subset).
    *   *Note: This specific distribution is characteristic of the Titanic `test.csv` often found on Kaggle, where the ground truth for the test set often defaults to the "Gender-Based Model".*

## 📈 Visualizations

The notebook generates the following plots:
*   **Age Distribution:** Histogram of passenger ages.
*   **Gender Distribution:** Bar chart comparing Male vs. Female count.
*   **Embarked Distribution:** Count of passengers boarding from Southampton, Cherbourg, and Queenstown.
*   **Survival Distribution:** Overview of Survived vs. Deceased.
*   **Correlation Heatmap:** Visualizing the relationship between Class and Survival.

## 🚀 How to Run

1.  Clone this repository.
2.  Install dependencies:
    ```bash
    pip install pandas matplotlib seaborn
    ```
3.  Ensure the dataset is located at `data/tested.csv`.
4.  Run the notebook:
    ```bash
    jupyter notebook notebook.ipynb
    ```

---

*Day 29 completed! One day left!* 🚀