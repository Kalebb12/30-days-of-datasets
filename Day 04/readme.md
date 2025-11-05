# 🩺 Day 3 — Patient Data Preprocessing

Today’s focus was on **cleaning and preparing patient data** for analysis and future modeling.  
Data preprocessing ensures the dataset is reliable, consistent, and machine-learning-ready.

---

## 🎯 Objective
Prepare the dataset by:
- Handling missing values  
- Removing duplicates  
- Validating numeric data  
- Encoding categorical values in the `Diagnosis` column  

---

## ⚙️ Steps Performed

### 1️⃣ Handle Missing Values
Filled missing entries in the `Diagnosis` column with `"Unknown"` to prevent data loss:
```python
raw_data['Diagnosis'].fillna('Unknown', inplace=True)
```
### 2️⃣ Remove Duplicates
```python
raw_data.drop_duplicates(inplace=True)
```
### 3️⃣ Validate Numeric Data
```python
raw_data = raw_data[(raw_data['Age'] > 0) & (raw_data['LabResult'] > 0)]
```
### 4️⃣ Encode Diagnosis Column
```python
raw_data['Diagnosis_Encoded'] = raw_data['Diagnosis'].map({
    'Unknown': 0,
    'Diabetes': 1,
    'Hypertension': 2,
    'Flu': 3,
    'Common Cold': 4
})
```
## 📊 Results

✅ Missing values filled
✅ Duplicates dropped
✅ Invalid entries removed
✅ Diagnoses encoded numerically