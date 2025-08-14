# Heart Disease Prediction

## Objective
The goal of this project is to build a model that predicts whether a person is at risk of heart disease based on their health data.

## Dataset
- **Source:** Heart Disease UCI Dataset (available on Kaggle)
- **Target Column:** `target` (1 = presence of heart disease, 0 = absence)

---

## Steps Performed

### 1. Data Loading and Cleaning
- Loaded the dataset using **Pandas**.
- Checked for missing values and found none.
- Verified data types and ensured they were correct for modeling.

### 2. Exploratory Data Analysis (EDA)
- Displayed basic dataset statistics using `describe()`.
- Counted the distribution of the target variable to check class balance.
- Generated correlation matrix heatmap to identify relationships between features.

**Key Insights:**
- Certain features like `cp` (chest pain type), `thalach` (max heart rate), and `oldpeak` show strong relationships with heart disease risk.

### 3. Feature Selection and Splitting
- Selected all independent features (`X`) and the target (`y`).
- Split the dataset into **training (80%)** and **testing (20%)** sets.

### 4. Model Training
Two models were trained for comparison:
1. **Logistic Regression**
2. **Decision Tree Classifier**

### 5. Model Evaluation
- **Metrics Used:**
  - Accuracy Score
  - Confusion Matrix
  - ROC Curve and AUC Score

#### Logistic Regression:
- Accuracy: **78%**
- ROC-AUC Score: **0.88**
- Performed well and showed a smooth ROC curve.

#### Decision Tree:
- Accuracy: **99%**
- ROC-AUC Score: **0.99**
- Good compared to Logistic Regression.

**Confusion Matrix:** Provided insight into true positives, false positives, true negatives, and false negatives for both models.

### 6. Feature Importance
- **Logistic Regression:** Showed the impact of each feature via model coefficients.
- **Decision Tree:** Showed feature importance directly; most important features were `cp`, `thalach`, and `oldpeak`.

---

## Conclusion
- **Best Model:** Decision Tree
- **Reason:** Higher accuracy and ROC-AUC score compared to the Logistic regression. Also generalizes better to unseen data.
- **Important Features:** `cp` (chest pain type), `thalach` (max heart rate achieved), and `oldpeak` (ST depression induced by exercise).

---

## Skills Demonstrated
- Binary classification
- Data cleaning & preprocessing
- EDA with visualization
- Model evaluation using Accuracy, ROC, and Confusion Matrix
- Feature importance analysis
