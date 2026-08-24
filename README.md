# Customer Total Spend Prediction (Linear Regression)

Predicting total customer spend (`Total_Spend`) for an online retail business, using linear regression on customer demographic and behavioural data.

## Problem
Understanding what drives customer spending helps a business identify high-value customers, tailor retention strategies, and forecast revenue more accurately.

## Data
Online retail customer dataset including attributes such as age, gender, annual income, years as customer, number of purchases, number of returns, support contacts, satisfaction score, email opt-in status, promotion response, and churn status.

## Approach
- Checked and handled missing values
- Converted categorical variables (Gender, Promotion_Response) into dummy/indicator variables
- Scaled numeric features using StandardScaler
- Split data into 80% training / 20% testing sets
- Trained a Linear Regression model to predict `Total_Spend`
- Evaluated performance using MAE, RMSE, and R²
- Interpreted feature coefficients to identify key spending drivers

## Results
- **R²:** ~0.05 — the model explains a modest share of the variance in spend, indicating spend is influenced by factors beyond what's captured in this dataset
- **MAE / RMSE:** used to quantify average prediction error in dollar terms

## Key Insight
Customer loyalty (`Years_as_Customer`) and purchase frequency (`Num_of_Purchases`) show the strongest positive relationship with total spend, while satisfaction score has surprisingly little effect — suggesting spend is driven more by engagement history than sentiment.

## Tools & Libraries
Python, pandas, scikit-learn, matplotlib

## Notebook
Open `Customer_Spend_Prediction.ipynb` directly on GitHub to view the full code, outputs, and visualisations.
