# Task 35: Regression Model Evaluation

## Project Overview
**Track:** AI & ML Track  
**Objective:** Evaluate a Linear Regression model using Mean Absolute Error (MAE) and Mean Squared Error (MSE) and explain the results.

---

## Tools & Technologies
* **Python**
* **Pandas & NumPy** (Data manipulation and numerical operations)
* **Scikit-learn** (Model training and evaluation metrics)
* **Matplotlib** (Data visualization)
* **Jupyter Notebook**

---

## Dataset Description
The project uses a **Salary vs. Experience** dataset consisting of 30 records. 
* **Feature (X):** `YearsExperience` (Continuous numerical value representing years worked)
* **Target (y):** `Salary` (Continuous numerical value representing annual compensation)

The dataset was split into an 80% training set (24 records) and a 20% testing set (6 records) using `random_state=42`.

---

## Model Results

### 1. Actual vs. Predicted Values
Below is the comparison of the actual test salaries against the values predicted by the Linear Regression model:

| Index | Actual Salary | Predicted Salary |
| :--- | :--- | :--- |
| **27** | 112635 | 115790.21 |
| **15** | 67938 | 71498.28 |
| **23** | 113812 | 102596.87 |
| **17** | 83088 | 75267.80 |
| **8** | 64445 | 55477.79 |
| **9** | 57189 | 60189.70 |

### 2. Evaluation Metrics
* **Mean Absolute Error (MAE):** 6286.45
* **Mean Squared Error (MSE):** 49830096.86
* **Root Mean Squared Error (RMSE):** 7059.04

---

## Interpretation of Results
1. **Mean Absolute Error (MAE - 6286.45):** On average, the model's salary predictions deviate from the actual salaries by approximately 6286.45 units. Because MAE treats all errors linearly, it gives a direct and easily interpretable measure of average error magnitude.
2. **Mean Squared Error (MSE - 49830096.86):** By squaring the residuals before averaging, MSE penalizes larger prediction errors more heavily (such as index 23, where the difference is over 11,200 units). Taking the square root gives an RMSE of 7059.04, which is slightly higher than the MAE due to these larger individual variances.
3. **Overall Fit:** The scatter plot and regression line demonstrate a strong positive linear correlation between years of experience and salary, confirming that Linear Regression is an appropriate baseline model for this dataset.

---

## Interview Questions & Answers

### Q1: What is MAE (Mean Absolute Error)?
**Answer:** MAE is the average of the absolute differences between predicted values and actual values. It measures the average magnitude of errors in a set of predictions without considering their direction (overestimation vs. underestimation). Because it uses absolute values, it treats all errors equally and is robust against outliers compared to MSE.

### Q2: What is MSE (Mean Squared Error)?
**Answer:** MSE is the average of the squared differences between predicted and actual values. By squaring the errors, MSE gives disproportionately higher weight to larger errors. This makes it useful when large errors are particularly undesirable in a business context, though its output is in squared units (which is why Root Mean Squared Error, RMSE, is often calculated alongside it to return to the original scale).

### Q3: Why are evaluation metrics important?
**Answer:** Evaluation metrics provide a quantitative, objective standard to measure how well a machine learning model generalizes to unseen data. They allow data scientists to:
1. Compare different algorithms or hyperparameter configurations to select the best-performing model.
2. Identify specific weaknesses or error patterns in predictions.
3. Track performance improvements systematically during model iteration and optimization.
