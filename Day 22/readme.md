# Day 22: Loan Eligibility Prediction Dataset

## Overview

This project is part of the "30 Days of Datasets" challenge. The goal of this challenge is to explore various datasets, perform exploratory data analysis (EDA), and derive meaningful insights. For Day 22, the focus is on a loan eligibility prediction dataset to understand the factors that influence loan approval.

The primary objective is to determine whether a loan applicant is eligible for loan approval based on a variety of demographic, financial, and credit-related factors. This is a classic classification problem in machine learning and is crucial for financial institutions to automate the loan approval process.

## Dataset

The dataset used in this project is the "Loan Eligibility Prediction" dataset, which is publicly available and commonly used for machine learning and data analysis projects. It contains historical data on loan applicants.

The dataset includes the following features:

*   **Customer_ID**: A unique identifier for each customer.
*   **Gender**: The gender of the applicant (Male/Female).
*   **Married**: The marital status of the applicant (Yes/No).
*   **Dependents**: The number of dependents the applicant has.
*   **Education**: The education level of the applicant (Graduate/Not Graduate).
*   **Self_Employed**: Whether the applicant is self-employed (Yes/No).
*   **Applicant_Income**: The income of the applicant.
*   **Coapplicant_Income**: The income of the co-applicant.
*   **Loan_Amount**: The loan amount requested.
*   **Loan_Amount_Term**: The term of the loan in months.
*   **Credit_History**: Whether the applicant has a credit history (1 for yes, 0 for no).
*   **Property_Area**: The location of the property (Urban/Semiurban/Rural).
*   **Loan_Status**: The final status of the loan (Y for approved, N for not approved).

The dataset consists of 614 rows and 13 columns. There are no missing values in this particular version of the dataset.

## Exploratory Data Analysis (EDA)

The EDA process involved several steps to understand the distribution of the data and the relationships between different variables. The key findings from the EDA are:

*   **Loan Status Distribution**: The majority of loans in the dataset were approved (68.9%) compared to those that were not approved (31.1%). This was visualized using a pie chart.
*   **Gender Distribution**: The dataset is skewed towards male applicants, who constitute the majority of the loan applicants.
*   **Marital Status Distribution**: A significant portion of the loan applicants are married.
*   **Dependents Distribution**: The distribution of the number of dependents for each applicant was also analyzed.

## Key Questions and Insights

Several key questions were explored to understand the factors influencing loan approval:

### Do longer loan terms correlate with higher approval rates?

To answer this, a cross-tabulation of `Loan_Amount_Term` and `Loan_Status` was performed. The analysis shows that there isn't a clear linear relationship between the length of the loan term and the approval rate. While some shorter and longer terms have high approval rates, the most common loan term (360 months) has a 70% approval rate. This suggests that the loan term alone is not a strong predictor of loan approval.

### Is there a relationship between credit history and loan status?

A stacked bar chart was created to visualize the relationship between `Credit_History` and `Loan_Status`. The visualization clearly indicates that applicants with a credit history (Credit_History = 1) have a significantly higher loan approval rate. This suggests a strong positive relationship between having a good credit history and getting a loan approved.

### Is credit history the strongest predictor of loan approval?

To quantify the strength of the relationship between different features and loan approval, a correlation analysis was performed. The categorical variables were converted to numeric representations to facilitate this analysis.

The correlation coefficients with `Loan_Status_Numeric` are as follows:

| Feature | Correlation |
|---|---|
| Credit_History | 0.523961 |
| Married_Numeric | 0.086673 |
| Education_Numeric | 0.085884 |
| Gender_Numeric | 0.009357 |
| Applicant_Income | -0.004710 |

The correlation analysis confirms that **Credit History is the strongest positive predictor of loan approval** among the analyzed features, with a correlation coefficient of approximately 0.52. This is a moderate positive correlation, indicating that as the credit history status improves (from no history to having a history), the likelihood of loan approval increases.

Other factors like marital status and education have a much weaker positive correlation, while applicant income shows a negligible negative correlation in this dataset.

## Conclusion

The analysis of the Loan Eligibility Prediction dataset reveals that a good credit history is the most critical factor in determining loan approval. While other demographic and financial factors play a role, their impact is significantly less pronounced. This insight is valuable for financial institutions in automating their loan approval processes and for individuals seeking loans to understand the importance of maintaining a good credit history.