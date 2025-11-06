# 🍜 Day 11: Ramen Ratings Analysis

**Goal:** To analyze global ramen ratings and discover which countries and brands produce the best instant ramen.

---

## 📊 Dataset Overview

| Column            | Description                               |
| ----------------- | ----------------------------------------- |
| **Review #**      | Unique review identifier                  |
| **Brand**         | Name of the ramen manufacturer            |
| **Variety**       | Specific flavor or type of ramen          |
| **Style**         | Packaging type (Cup, Pack, Bowl, etc.)    |
| **Country**       | Country of origin                         |
| **Stars**         | Star rating (text or float)               |
| **Top Ten**       | Indicates if it appeared in a top 10 list |
| **Stars_numeric** | Cleaned numeric version of the rating     |

---

## 🧩 Key Questions

1. What is the general distribution of ramen ratings?
2. Which countries dominate the ramen market by review count?
3. Which style of ramen is most popular?
4. Which countries produce the highest-rated ramen?
5. Which brands have the best and most consistent ratings?
6. How have ramen ratings changed over time?

---

## 📈 Visual Insights

### ⭐ Distribution of Ratings

* Ratings mostly range between **3.0 and 5.0**.
* The **average rating** is approximately **3.65**, indicating overall satisfaction.

### 🌏 Top Countries by Reviews

* **Japan**, **USA**, **South Korea**, and **Taiwan** dominate by total reviews.
* Suggests global popularity with East Asian leadership.

### 🍜 Reviews by Style

* The **Pack** style is the most common, followed by **Cup** and **Bowl**.
* Indicates packet ramen is still the dominant product type.

### 🥇 Average Rating by Country

* Countries with top average ratings include **Malaysia**, **Singapore**, **Indonesia**, **Japan**, and **Hong Kong**.
* **Malaysia** stands out for consistent high-quality ramen products.

### 🧃 Average Rating by Style

* **Bar** and **Box** ramen styles have higher ratings, though less common.
* **Cup** and **Pack** ramen maintain stable averages around **3.6–3.8**.

### 📦 Rating Distribution by Style

* **Cup** and **Pack** styles show wider variation, meaning quality differs greatly between brands.
* **Bowl** styles tend to have more consistent ratings.

### 🏆 Top Brands

* By volume: **Nissin**, **Nongshim**, **Maruchan**, and **Mama** lead globally.
* By quality: **MyKuali (Malaysia)**, **Yamachan (Japan)**, and **KOKA (Singapore)** dominate with average ratings near **5.0**.

### ⏳ Rating Trends Over Time

* Average ratings have increased over time, now nearing **4.0**.
* Suggests improving ramen quality or evolving reviewer standards.

---

## 🧭 Highlight: Country with the Best Brand

Using the cleaned dataset, we grouped data by brand and country, filtered for brands with at least **10 reviews**, and found:

| Brand       | Country      | Avg Rating | Review Count |
| ----------- | ------------ | ---------- | ------------ |
| **MyKuali** | **Malaysia** | **4.95**   | 12           |

> 🏅 **Malaysia** produces the top-rated brand, **MyKuali**, known for its high-quality and flavor-rich instant noodles.

---

## 🧮 Methods

* Data cleaning (handling missing and non-numeric ratings)
* Grouping and aggregation (`groupby` in pandas)
* Statistical analysis for averages and distributions
* Visualizations using `matplotlib` and `seaborn`

---

## 🧠 Key Takeaways

* Ramen ratings are generally positive, with an upward trend over time.
* Packet ramen remains the most common, but cups and bowls are popular alternatives.
* Malaysia and Japan are home to some of the best ramen brands.
* Top brands like **MyKuali**, **KOKA**, and **Yamachan** consistently deliver near-perfect products.

---

## 📷 Visualization Summary

![Ramen Ratings Plots](images/ramen_eda_visualizations.png)

---

### ✅ Next Steps

* Explore flavor or variety-based trends (e.g., spicy vs. non-spicy).
* Examine year-over-year brand performance.
* Build a recommendation model for ramen selection.

---

**Author:** Caleb
**Project:** 30 Days of Datasets — *Day 11: Ramen Ratings Analysis*
