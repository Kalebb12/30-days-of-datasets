# Day 23: Loan Eligibility Prediction

Picked up from day 22

---

# Loan Eligibility Prediction Model

This project builds a machine learning model to predict whether a loan application will be approved. The model is a Logistic Regression classifier trained on a dataset of historical loan application data. The entire process, from data preprocessing to model evaluation, is contained within the `Untitled.ipynb` notebook.

## Project Workflow

The project follows these key steps:

1.  **Data Loading**: The `Loan Eligibility Prediction.csv` dataset is loaded into a pandas DataFrame.
2.  **Data Preprocessing**:
    *   **Encoding Binary Variables**: Categorical features with two options (like `Gender`, `Married`, `Education`, `Self_Employed`, and the target `Loan_Status`) are converted into numerical format (0s and 1s).
    *   **One-Hot Encoding**: The `Property_Area` feature, which has multiple categories, is converted into numerical format using one-hot encoding.
    *   **Feature Selection**: The `Customer_ID` column is dropped as it is not relevant for prediction.
3.  **Data Splitting**: The dataset is split into an 80% training set and a 20% testing set. Stratification is used to ensure that the proportion of approved and denied loans is the same in both the train and test splits.
4.  **Feature Scaling**: The numerical features are scaled using `StandardScaler` to ensure that all features contribute equally to the model's performance. This prevents features with larger ranges from dominating the model.
5.  **Model Training**: A **Logistic Regression** model is trained on the preprocessed training data. The `class_weight='balanced'` parameter is used to handle the imbalance between approved and rejected loans in the dataset.
6.  **Model Evaluation**: The trained model's performance is evaluated on the unseen test data using several metrics:
    *   Accuracy Score
    *   Classification Report (Precision, Recall, F1-Score)
    *   Confusion Matrix

## Results

The model achieved an overall **accuracy of approximately 80.5%** on the test set.

### Classification Report

The detailed performance for each class is as follows:

```
              precision    recall  f1-score   support

           0       0.73      0.58      0.65        38
           1       0.83      0.91      0.87        85

    accuracy                           0.80       123
   macro avg       0.78      0.74      0.76       123
weighted avg       0.80      0.80      0.80       123
```

-   The model is highly effective at identifying applicants who should be **approved** (Class 1), with a precision of 83% and recall of 91%.
-   It is moderately effective at identifying applicants who should be **denied** (Class 0), with a precision of 73% and a recall of 58%.

### Confusion Matrix

```
[[22 16]
 [ 8 77]]
```

-   **True Positives (Approved): 77** - Correctly predicted as approved.
-   **True Negatives (Denied): 22** - Correctly predicted as denied.
-   **False Positives (Type I Error): 16** - Incorrectly predicted as approved (were denied).
-   **False Negatives (Type II Error): 8** - Incorrectly predicted as denied (were approved).

## How to Run This Project

1.  **Prerequisites**: Make sure you have Python and the following libraries installed:
    -   `pandas`
    -   `numpy`
    -   `scikit-learn`
    -   `matplotlib`
    -   `seaborn`
    -   `jupyter notebook` or `jupyter lab`

    You can install them using pip:
    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn jupyterlab
    ```

2.  **Dataset**: Place the `Loan Eligibility Prediction.csv` file inside a folder named `data` in the same directory as the notebook.

3.  **Execute the Notebook**: Launch Jupyter Lab/Notebook and open the `Untitled.ipynb` file. Run the cells in sequential order to replicate the analysis and model training.