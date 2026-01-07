# Diabetes Prediction Model Comparison

A comprehensive machine learning project comparing multiple regression models on the diabetes dataset from scikit-learn.

## Overview

This Jupyter notebook implements and evaluates several regression algorithms to predict diabetes progression. The project includes model training, performance evaluation, and visualization of results.

## Features

- **Multiple Model Comparison**: Evaluates 5+ regression algorithms side-by-side
- **Comprehensive Metrics**: Tracks MAE, MSE, RMSE, and R² scores for both training and test sets
- **Feature Analysis**: Extracts and ranks feature importances/coefficients
- **Visual Diagnostics**: Generates predicted vs. actual plots and residual plots for model evaluation
- **Baseline Comparison**: Includes a mean predictor baseline for context

## Models Implemented

1. **Baseline (Mean Predictor)**: Simple average predictor for comparison
2. **Linear Regression**: Standard linear regression model
3. **Polynomial Regression**: 2nd-degree polynomial features with linear regression
4. **Elastic Net**: Regularized regression combining L1 and L2 penalties
5. **Random Forest**: Ensemble method using decision trees
6. **Gradient Boosting**: Sequential ensemble learning algorithm

## Dataset

Uses the built-in diabetes dataset from scikit-learn:
- **Samples**: 442 patients
- **Features**: 10 baseline variables (age, sex, BMI, blood pressure, and 6 blood serum measurements)
- **Target**: Quantitative measure of disease progression one year after baseline

## Usage

1. Install required dependencies
2. Open the Jupyter notebook
3. Run all cells sequentially
4. Review the results table and visualizations

## Output

### Results Table
Displays comprehensive metrics for each model including:
- Training time
- Training and test performance metrics (MAE, MSE, RMSE, R²)
- Feature importances (when available)

### Visualizations
For each model:
- **Predicted vs. Actual**: Scatter plot showing prediction accuracy
- **Residual Plot**: Shows prediction errors across predicted values

## Key Insights

The results table allows you to:
- Compare model performance across multiple metrics
- Identify overfitting (large gap between training and test scores)
- Evaluate training efficiency (training time)
- Understand which features drive predictions (feature importances)

## License

This project uses the diabetes dataset from scikit-learn, which is in the public domain.