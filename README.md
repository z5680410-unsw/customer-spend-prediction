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
- Split data into 80% training / 20% testing sets (fixed `random_state=42` for reproducibility)
- Trained a Linear Regression model to predict `Total_Spend`
- Evaluated performance using MAE, RMSE, and R²
- Checked correlations between individual features and `Total_Spend` to diagnose model performance
- Interpreted feature coefficients to identify patterns, despite the model's weak fit

## Results
- **R²: -0.035** — the model performs worse than simply predicting the average spend for every customer. It explains essentially none of the variance in `Total_Spend`.
- **MAE: ~2,443.56 / RMSE: ~2,777.99** — the average prediction error is large relative to the spend range in the data.
- A correlation check confirmed why: every individual feature has a near-zero correlation with `Total_Spend` (the strongest, `Years_as_Customer`, is only 0.085). This indicates the dataset itself carries little to no linear signal relating these attributes to spend, rather than a flaw in the modelling approach.
- The feature coefficients themselves are unstable across different train/test splits — both their size and sign can shift noticeably between runs — a further symptom of the model not capturing any real, stable relationship in the data.

## Key Insight
No feature shows a meaningful relationship with `Total_Spend` — correlations across the board are close to zero, and this holds for both numeric features (e.g. `Years_as_Customer`, `Num_of_Purchases`) and categorical ones (e.g. `Gender`, `Promotion_Response`, `Churned`). This suggests either that spend in this dataset isn't meaningfully driven by these attributes, or that the underlying relationship (if any) is non-linear. A useful next step would be testing non-linear models (e.g. Random Forest, Gradient Boosting) to check whether they can extract any signal a linear model can't.

## Tools & Libraries
Python, pandas, scikit-learn, matplotlib

## Notebook
Open `Customer_Total_Spend_Prediction.ipynb` directly on GitHub to view the full code, outputs, and visualisations.
