# 🌸 Day 25 — Iris Dataset Analysis

## 📌 **Dataset Description**

The Iris dataset is a classic and widely used dataset in machine learning. It contains three species of iris:

* *setosa*
* *versicolor*
* *virginica*

### **Features Used**

| Feature        | Description                                  |
| -------------- | -------------------------------------------- |
| `sepal_length` | Length of the sepal (cm)                     |
| `sepal_width`  | Width of the sepal (cm)                      |
| `petal_length` | Length of the petal (cm)                     |
| `petal_width`  | Width of the petal (cm)                      |
| `species`      | Target label representing the flower species |

---

## 🛠️ **Data Preprocessing**

### **1. Encoding**

`species` was encoded using LabelEncoder:

* Setosa → 0
* Versicolor → 1
* Virginica → 2

### **2. Feature Scaling**

Since KNN is distance-based, features were scaled using **StandardScaler**. Scaling helps models treat all features fairly.

### **3. Train-Test Split**

Dataset was split into:

* **75% training**
* **25% testing**

---

## 🤖 **Modeling**

We trained two beginner-friendly models:

### **1. K-Nearest Neighbors (k = 3)**

* Accuracy: **0.947**
* Performs very well because iris features naturally form clusters.
* Perfectly classifies Setosa.

### **2. Logistic Regression**

* Accuracy: **0.921**
* Performs slightly lower due to linear decision boundaries.

### **Model Comparison**

| Model               | Accuracy  |
| ------------------- | --------- |
| KNN (k=3)           | **0.947** |
| Logistic Regression | **0.921** |

**KNN performed best** on this dataset.

---

## 🧠 **Key Insights**

* Petal features are the most important for classification.
* Setosa is the easiest species to classify.
* There is some slight overlap between Versicolor and Virginica.
* Scaling improves the performance of KNN.

---

## ❓ **Unanswered Research Questions**

1. Would tuning KNN (trying different k values) improve accuracy further?
2. Which two features combined give the highest separability besides the petals?
3. Can a decision tree visually explain how the species are separated?

---

## ✅ **Conclusion**

Day 25 introduced classification modeling using the Iris dataset. Through visualization, preprocessing, scaling, and model training, we achieved high accuracy with simple models. This dataset is an excellent beginner-friendly introduction to machine learning and supervised classification.
