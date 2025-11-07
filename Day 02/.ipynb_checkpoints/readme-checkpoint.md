# 📘 Day 2 — How Education Drives Economic Growth

This analysis explores how **education and health indicators** influence **economic performance** across countries and continents.  
The dataset includes metrics such as literacy rate, physician density, GDP (and related measures), unemployment rate, and continent classification.

---

## 🧠 Objective
To understand how **human capital**—measured through education and health—drives **national prosperity**.  
Specifically:
- Does higher literacy correlate with greater economic output (GDP per capita)?
- How does physician density (health infrastructure) affect economic performance?
- What is the relationship between unemployment and literacy across regions?

---

## 📊 Dataset Overview
**Columns:**
- `Country`
- `Continent`
- `Literacy Rate (%)`
- `Physician Density`
- `GDP (Current USD)`
- `GDP Growth (% Annual)`
- `GDP per Capita (Current USD)`
- `GDP per Capita Category`
- `Unemployment Rate (%)`

**Source:** Public dataset combining global education, health, and economic indicators.  

---

## ⚙️ Steps Performed

### 1️⃣ Data Cleaning & Preparation
- Renamed columns for consistency (e.g., spaces → underscores)
- Checked for missing or invalid data
- Ensured numeric columns were properly typed

### 2️⃣ Exploratory Data Analysis (EDA)
- **Distribution plots** for literacy and GDP metrics  
- **Scatter plots**:
  - Literacy Rate vs GDP per Capita  
  - Physician Density vs GDP per Capita  
  - Unemployment Rate vs GDP per Capita  
  - Literacy Rate vs Unemployment Rate *(key new insight)*  
- **Boxplots** to compare GDP per Capita across continents  
- **Correlation heatmap** to summarize relationships between education, health, and economic factors  

## 📈 Key Findings

- **Education fuels prosperity:** Higher literacy rates strongly correlate with higher GDP per capita, confirming education’s role in economic growth.  
- **Nonlinear effect:** The benefit of literacy flattens after ~90%, suggesting other factors (innovation, infrastructure, governance) drive further growth.  
- **Health complements education:** Higher physician density is associated with greater national income, showing the value of healthy human capital.  
- **Employment connection:** Literacy correlates negatively with unemployment — more educated nations tend to have stronger labor markets.  
- **Regional disparities:** Europe and North America lead both in literacy and GDP per capita, while Africa and parts of Asia lag behind, reflecting global inequality.

---

## 🧩 Conclusion

> Education and healthcare together form the foundation of economic prosperity.  
> While literacy and physician access raise GDP per capita, true long-term growth requires translating human capital into innovation, jobs, and equitable opportunity.

---

## 💻 Tools Used
- **Python**
- **Pandas** — data manipulation  
- **Seaborn / Matplotlib** — visualization  