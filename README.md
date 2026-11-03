# Boston Housing Data Analysis

This project analyzes a dataset containing housing prices and socioeconomic information from Boston.

## Project contents

- `notebooks/`: R notebook with the complete exploratory and statistical analysis.
- `data/`: Boston housing dataset in CSV format.
- `reports/`: Exported PDF report with the detailed explanation of the analysis.

## Analysis performed

- Dataset exploration and visualization.
- Quantitative and qualitative variable analysis.
- Correlation analysis and principal component analysis (PCA).
- ANOVA tests.
- Linear regression model selection and evaluation.
- Prediction analysis using training and test datasets.

## Main results

- `rooms_per_dwelling` has a positive relationship with the median house value.
- `lower_status` has a negative relationship with the median house value.
- `c_river_variable` and `highway_index` have statistically significant effects on house prices.
- The first two principal components explain 60.41% of the variance.
- The final regression model achieves an R-squared of approximately 71.91% on the cleaned training data and 63.00% on the test data.
- The model obtains an RMSE of approximately 5.456 and an MAE of 3.78.

The complete interpretation of these results, including the visualizations, statistical tests, regression diagnostics, and conclusions, is available in the PDF report in the `reports/` folder.

## Requirements

The notebook requires R and the following packages:

- `ggplot2`
- `gridExtra`
- `GGally`
- `nortest`
- `caret`
- `lmtest`

## How to run

1. Open `notebooks/MD004VicentRipollBaradatAC03.ipynb` in Jupyter Notebook with an R kernel.
2. Make sure the CSV file in `data/` is available in the notebook's working directory.
3. Run the cells in order.

The analysis focuses on identifying the variables that best explain the median value of Boston homes and building a simple linear regression model for prediction.