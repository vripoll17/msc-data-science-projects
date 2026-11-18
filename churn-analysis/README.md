# Customer Churn Analysis

This project analyzes customer churn in an Indian telecommunications dataset and
develops an interpretable model to identify users who are at risk of leaving the
service.

The analysis is implemented in an R notebook and combines exploratory data
analysis, statistical techniques, and logistic regression.

## Project structure

```text
churn-analysis/
├── data/
│   └── customer_churn_data.csv
├── notebooks/
│   └── notebook.ipynb
└── README.md
```

## Dataset

The dataset contains 104.142 customer records and 18 variables, including:

- Customer attributes such as age, city, and device
- Payment and reward activity during the first seven days
- Referral status and platform permissions
- `is_churned`, the binary target variable

The target distribution is imbalanced: 71.32% of customers did not churn and
28.68% churned.

## Analysis workflow

The notebook covers the following stages:

1. **Exploratory data analysis**
   - Data structure, summary statistics, and missing-value analysis
   - Distributions of numerical and categorical variables
   - Relationships between customer characteristics and churn
2. **Statistical analysis**
   - Principal Component Analysis (PCA) to study relationships and redundancy
     among numerical variables
   - Mutual Information to identify variables associated with churn
   - Missing-value handling and construction of the `permission_type` feature
3. **Predictive modelling**
   - Seven logistic regression models with progressively selected predictors
   - Evaluation using confusion matrices, Recall, ROC-AUC, and AIC
   - A 70/30 train-test split using a fixed seed (`123`)
4. **Business interpretation**
   - Identification of potential churn signals
   - Recommendations for retention experiments

## Main result

The selected model is **Model 5**, a logistic regression using:

- `first_payment_amount`
- `reward_purchase_missing`
- `permission_type`

It was selected because it provides a good balance between interpretability and
predictive performance:

- **Recall:** 52.62%
- **ROC-AUC:** 0.75
- Only three predictor variables

The analysis identifies the absence of reward-purchase activity during the first
seven days as an especially relevant churn signal. Payment activity and platform
permissions are also associated with churn.

The model should be used as a decision-support tool rather than an automatic
retention rule. Its Recall indicates that approximately half of the customers
who churn would still be missed, so further modelling and validation are needed
before production use.

## Requirements

- R
- Jupyter Notebook with an R kernel (`IRkernel`)

The notebook uses the following R packages:

```r
install.packages(c(
  "dplyr",
  "ggplot2",
  "gridExtra",
  "purrr",
  "FSelectorRcpp",
  "tidyr",
  "forcats",
  "caret",
  "pROC"
))
```

## Running the notebook

1. Start Jupyter with an R kernel.
2. Open `notebooks/notebook.ipynb`.
3. Set the working directory to the `data/` folder, or update the data-loading
   line in the notebook so that it points to
   `data/customer_churn_data.csv`.
4. Run the cells from top to bottom.

The notebook generates the tables, visualizations, statistical analyses, model
comparisons, and ROC curves reported in this project.

## Recommendations and future work

The analysis suggests testing retention initiatives focused on:

- Encouraging customers to make their first payment
- Promoting reward activity early in the customer journey
- Simplifying the process for obtaining platform permissions

These recommendations describe associations, not causal effects. Controlled
experiments should be used to measure their impact. Future work should also
evaluate alternative machine-learning models, improve churn Recall, and perform
additional validation and multicollinearity analysis.