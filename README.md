# econ3916-lab16-regularization

# Regularization: Buying Bias to Sell Variance

## Objective
In this lab, I explored how LASSO and Ridge regularization reduce overfitting and improve predictions compared to OLS.

## Methodology
- I created a simulated dataset with 200 predictors, but only 5 were actually useful, and used 105 rows for training.
- I fitted OLS, LASSO, and Ridge models and compared their training and test MSEs.
- I traced the LASSO coefficient path to see how variables entered the model as the penalty changed.
- I used 5-fold cross-validation to choose the best penalty, with StandardScaler fitted separately inside each fold.
- I compared LASSO's selected variables with the known true predictors.
- I tested LASSO and Ridge with two highly correlated predictors to see how they handled similar variables.
- I used AI to help write a cross-validation loop and checked its results against my original results.

## Key Findings
- OLS had a test MSE of 12.9587, Ridge had 10.1128, and LASSO had 1.4219. LASSO performed the best on the test data.
- All 5 true predictors entered the LASSO path by step 6, while the first noise variable entered at step 17.
- The best penalty from 5-fold cross-validation was 0.1995, with a CV MSE of 1.5502.
- LASSO selected all 5 true predictors but also included 11 false positives.
- With two nearly identical predictors, LASSO gave one a coefficient of 4.462 and the other 0. Ridge split the weight between them, with coefficients of 1.618 and 1.609.
- I completed 2 rounds of AI-assisted coding. All four checks passed in both rounds, and the results matched my original cross-validation results with 0% difference.

## Conclusion
This lab showed me that a model with a lower training error does not always make better predictions. LASSO introduced some bias but greatly reduced the test error by removing many unnecessary variables. I also learned why scaling and cross-validation are important when choosing a penalty.
