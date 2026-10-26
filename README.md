# CreditWise Loan System

A machine-learning decision-support project that predicts whether a loan application is likely to be approved or rejected before human review.

## Goal

Help loan officers review applications faster and more consistently using historical applicant, financial, and credit information.

The model supports human decision-making; final approval should remain with a human reviewer.

## Data

The dataset includes applicant income, employment, credit score, existing loans, debt-to-income ratio, savings, collateral value, loan details, and location-related fields.

Target:

- `Yes` / `1` - Loan approved
- `No` / `0` - Loan rejected

`Applicant_ID` is excluded because it is only an identifier. `Gender` is excluded so it cannot directly influence predictions.

## Method

- Stratified 60/20/20 train-validation-test split
- Missing values, encoding, and scaling are fitted using training data only
- Models evaluated: Logistic Regression, K-Nearest Neighbors, and Gaussian Naive Bayes
- Validation data is used for model comparison
- The test set is reserved for final evaluation

## Current Final Result

| Metric | Score |
| --- | ---: |
| Accuracy | 86.8% |
| Precision | 81.8% |
| Recall | 75.0% |
| F1 Score | 78.3% |

Precision is important because approving a high-risk applicant can lead to financial loss.

## Run Locally

1. Keep `loan_approval_data.csv` in the same folder as `credit_wise_final.ipynb`.
2. Install dependencies:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```

3. Open the notebook:

   ```bash
   jupyter notebook credit_wise_final.ipynb
   ```

4. Run all cells from top to bottom.

## Limitations

- Results are based on one dataset and one held-out test split.
- Removing Gender prevents direct use of that field, but does not prove predictions are completely bias-free.
- The model should be used as decision support, not as a fully automated approval system.
