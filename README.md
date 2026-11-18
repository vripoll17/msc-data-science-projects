# MSc Data Science Projects

This repository is a collection of practical projects developed as part of my
Master's degree in Data Science.

The projects cover complementary stages of the data science workflow, including
exploratory data analysis, data visualization, statistical techniques,
predictive modelling, model evaluation, and the communication of results. The
analyses are primarily implemented in R and documented through Jupyter
notebooks and reports.

## Projects

| Project | Description | Main techniques |
|---|---|---|
| [Boston Housing](./boston-housing/) | Analysis of housing prices and socioeconomic variables in Boston. The project studies which factors are associated with median house values and develops a linear regression model for prediction. | EDA, correlation, PCA, ANOVA, linear regression |
| [Customer Churn Analysis](./churn-analysis/) | Analysis of customer behavior in a telecommunications company to identify patterns associated with churn and build an interpretable logistic regression model. | EDA, PCA, Mutual Information, logistic regression |

## Boston Housing

The [Boston Housing project](./boston-housing/) explores a dataset containing
housing prices and socioeconomic information from Boston.

The analysis includes:

- Exploratory data analysis and visualizations
- Correlation and principal component analysis
- ANOVA tests
- Comparison and selection of linear regression models
- Evaluation using R-squared, RMSE, and MAE

The project concludes that variables related to room availability and
socioeconomic status are strongly associated with housing prices. It also
provides a detailed PDF report and an R notebook with the complete workflow.

## Customer Churn Analysis

The [Customer Churn project](./churn-analysis/) studies customer activity and
behavior in an Indian telecommunications company.

The analysis includes:

- Exploratory data analysis and missing-value assessment
- PCA and Mutual Information analysis
- Development of multiple logistic regression models
- Model evaluation using Recall, ROC-AUC, confusion matrices, and AIC
- Business-oriented recommendations for customer retention

The selected model identifies important churn signals related to early payment
activity, reward purchases, and permissions. It is designed as an interpretable
decision-support tool, with further validation and model improvement needed
before production use.

## Repository structure

```text
msc-data-science-projects/
├── boston-housing/
├── churn-analysis/
└── README.md
```

Each project contains its own README, data, notebooks, and, where applicable,
exported reports.