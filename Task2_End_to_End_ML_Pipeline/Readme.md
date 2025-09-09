# 📊 Customer Churn Prediction with Scikit-learn Pipeline

## 📌 Overview
This project builds an **end-to-end machine learning pipeline** using the **Scikit-learn Pipeline API** to predict **customer churn**.  
The dataset used is the **Telco Customer Churn dataset (IBM sample dataset)**.  

Key highlights:
- End-to-end pipeline with preprocessing + model in one workflow  
- Supports both **Logistic Regression** and **Random Forest**  
- Hyperparameter tuning using **GridSearchCV**  
- Exportable model pipeline with **joblib** for production  

---

## 📂 Dataset
- **Name:** WA_Fn-UseC_-Telco-Customer-Churn.csv  
- **Source:** [Kaggle: Telco Customer Churn Dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)  
- **Rows:** ~7,043 customers  
- **Target variable:** `Churn` (Yes = customer will leave, No = customer will stay)  

### Features:
- **Demographics:** Gender, SeniorCitizen, Partner, Dependents  
- **Services signed up:** PhoneService, InternetService, StreamingTV, StreamingMovies, etc.  
- **Account info:** Contract, Tenure, MonthlyCharges, TotalCharges  

---

## ⚙️ Methodology
1. **Data Loading**  
   Load dataset into Pandas DataFrame.  

2. **Preprocessing**  
   - Drop `customerID` column  
   - Convert `TotalCharges` to numeric (fix missing values)  
   - Encode categorical features with `OneHotEncoder`  
   - Scale numerical features with `StandardScaler`  

3. **Pipeline Setup**  
   - Use `ColumnTransformer` for preprocessing  
   - Create reusable pipelines for:  
     - **Logistic Regression**  
     - **Random Forest**  

4. **Model Training & Hyperparameter Tuning**  
   - Use **GridSearchCV** for both models  
   - Logistic Regression hyperparameters: `C`, `solver`  
   - Random Forest hyperparameters: `n_estimators`, `max_depth`  

5. **Evaluation**  
   - Metrics: Accuracy, Precision, Recall, F1-score  
   - Confusion Matrix visualization  

6. **Export**  
   - Save best-performing pipeline with **joblib**  

---

## 📈 Results
Final evaluation on **test set (20% split)**:

| Model               | Accuracy | Notes |
|----------------------|----------|-------|
| Logistic Regression  | ~0.80    | Baseline linear model |
| Random Forest        | ~0.82–0.85 | Performs better with tuned parameters |

✅ The **Random Forest model** achieved better performance compared to Logistic Regression.

---

## 🚀 Deployment
The **best model pipeline** is saved as `churn_pipeline.joblib`.  
This file can be loaded directly into any Python environment for prediction:

```python
import joblib
import pandas as pd

# Load pipeline
model = joblib.load("churn_pipeline.joblib")

# Example new customer data
sample = pd.DataFrame([{
    "gender": "Female",
    "SeniorCitizen": 0,
    "Partner": "Yes",
    "Dependents": "No",
    "tenure": 12,
    "PhoneService": "Yes",
    "MultipleLines": "No",
    "InternetService": "Fiber optic",
    "OnlineSecurity": "No",
    "OnlineBackup": "Yes",
    "DeviceProtection": "Yes",
    "TechSupport": "No",
    "StreamingTV": "Yes",
    "StreamingMovies": "Yes",
    "Contract": "Month-to-month",
    "PaperlessBilling": "Yes",
    "PaymentMethod": "Electronic check",
    "MonthlyCharges": 70.35,
    "TotalCharges": 850.50
}])

# Predict churn (1 = Yes, 0 = No)
prediction = model.predict(sample)
print("Churn Prediction:", prediction[0])