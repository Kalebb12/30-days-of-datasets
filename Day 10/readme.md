# 📊 30 Days of Datasets — Day 10
### 🧠 Linear Regression with TensorFlow

---

## 🎯 Objective
Today’s challenge focuses on building a **simple linear regression model using TensorFlow**.  
We generated synthetic data and trained a small neural network to learn the linear relationship between two input features and one output target.

---

## 🧩 Step-by-Step Overview

### 1. Importing Libraries
```python
import tensorflow as tf
import matplotlib.pyplot as plt
import numpy as np
```

### 2. Data Generation
We simulate a dataset that follows a linear relationship:
𝑦 = 2𝑥 − 3𝑧 + 5 +noise
```python
observations = 1000
xs = np.random.uniform(low=-10, high=10, size=(observations, 1))
zs = np.random.uniform(low=-10, high=10, size=(observations, 1))
noise = np.random.uniform(-1, 1, (observations, 1))

generated_inputs = np.column_stack((xs, zs))
generated_targets = 2 * xs - 3 * zs + 5 + noise
```

### 3. Model Definition (TensorFlow)
A simple Sequential model is defined with one dense layer containing a single neuron:
```python
model = tf.keras.Sequential([
    tf.keras.layers.Dense(1)
])
```

### 4. Model Compilation
We use stochastic gradient descent (SGD) as the optimizer and mean squared error (MSE) as the loss function:
```python
custom_optimizer = tf.keras.optimizers.SGD(learning_rate=0.02)
model.compile(optimizer=custom_optimizer, loss='mean_squared_error')
```

### 5. Model Training
The model is trained for 100 epochs on the generated data:
```python
model.fit(training_data['inputs'], training_data['targets'],epochs=100, verbose=2)
```

### 6. Extracting Learned Parameters
After training, we can inspect the weights and bias to see how closely they match the true values (2, -3, 5):
```python
model.layers[0].get_weights()
```

### 7. Predictions and Visualization
The trained model is used to predict outputs on the training inputs:
```python
predictions = model.predict_on_batch(training_data['inputs']).round(1)
```

```python
plt.plot(np.squeeze(predictions), np.squeeze(training_data['targets']))
plt.xlabel('outputs')
plt.ylabel('targets')
plt.show()
```
## Concepts Learned
Generating synthetic datasets for regression
Building and training models with TensorFlow Keras API
Understanding weights, bias, and gradient descent
Visualizing model performance

## Tools Used
Python
TensorFlow
NumPy
Matplotlib