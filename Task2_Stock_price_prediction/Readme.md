# Stock Price Prediction

## Objective
The goal of this project is to build a model that predicts short-term future stock prices based on historical price data.

## Dataset
- **Source:** Fetched using the Yahoo Finance API (`yfinance`)
- **Stock Symbol:** `AAPL` (Apple Inc.)
- **Target Column:** Close price (USD)

---

## Steps Performed

### 1. Data Loading
- Used **yfinance** to fetch 1 year of historical Apple stock data.
- Loaded data into a Pandas DataFrame and displayed the first few rows for verification.

### 2. Data Preparation
- Selected features relevant for short-term prediction: `Open`, `High`, `Low`, and `Volume`.
- Target variable set as `Close` price.
- Split data into **training (80%)** and **testing (20%)** sets.

### 3. Model Training
Two models were trained for performance comparison:
1. **Linear Regression**
2. **Random Forest Regressor**

### 4. Model Evaluation
**Metrics Used:**
- Mean Squared Error (MSE)
- R² Score
- Mean Absolute Percentage Error (MAPE)
- Accuracy (100 - MAPE)

#### Linear Regression:
- Achieved reasonable accuracy for short-term predictions.
- Prediction plot showed trends matching actual prices but with minor deviations.

#### Random Forest Regressor:
- Lower MSE compared to Linear Regression.
- Higher R² score, indicating better model fit.
- More accurate prediction curves compared to actual stock prices.

**Visualization:**
- Plotted **Actual vs Predicted Closing Prices** for both models.

---

## Conclusion
- **Best Model:** Random Forest Regressor
- **Reason:** Lower error metrics and better accuracy than Linear Regression.
- **Key Observations:** Stock price movement shows non-linear patterns better captured by ensemble methods.
