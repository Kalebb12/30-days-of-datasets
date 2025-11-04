# 📊 Day 9 – Simple Linear Regression (From Scratch)

## 🎯 Objective
Today’s goal was to **build and train a simple linear regression model from scratch** using only **NumPy**.  
No machine learning libraries — just the math behind it.

---

## 🧩 Steps

### 1. Generate Synthetic Data
- Created 1,000 random data points with two features (`x`, `z`).
- Defined target values using:
- Added uniform noise for realism.

### 2. Visualize the Data
A 3D scatter plot shows how the target depends on both input features.

### 3. Initialize Model Parameters
Random small weights and bias were set before training.

### 4. Train with Gradient Descent
- Computed predictions:  
`y_pred = XW + b`
- Calculated loss using Mean Squared Error.
- Updated weights and bias iteratively.

### 5. Evaluate the Model
After 100 epochs, the learned parameters closely approximate:
`weights = [[ 2.....][-2.....]] bias = [5......]`

## 🧠 Concepts Learned
- Linear regression fundamentals
- Matrix operations in NumPy
- Gradient descent optimization
- Data visualization in 3D

---

## 🧰 Tools Used
- **Python**
- **NumPy**
- **Matplotlib (3D plotting)**

---

## 📸 Sample Visuals
### Training Data
![3D Data Plot](images/3dviz.png)

### Model Performance
![Outputs vs Targets](images/final_viz.png)

---

## ✅ Outcome
Built a simple regression model that learned the relationship:
\[
y = 2x - 3z + 5
\]
purely through **mathematical computation**, reinforcing the fundamentals of machine learning.