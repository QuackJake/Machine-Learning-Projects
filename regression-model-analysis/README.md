# Diabetes Prediction Model Comparison

A machine learning project comparing multiple regression models on the Diabetes dataset from scikit-learn, including exploratory data analysis, baseline comparison, model evaluation, feature analysis, and visual diagnostics.

## Overview

This project analyzes the relationship between clinical measurements and diabetes disease progression using five regression approaches — Linear Regression, Polynomial Regression, Elastic Net, Random Forest, and Gradient Boosting. The goal is to compare how each algorithm predicts diabetes progression and to determine which modeling approaches provide the most useful balance of predictive performance, interpretability, and generalization.

The workflow moves through exploratory data analysis, baseline modeling, regression model development, performance evaluation, feature analysis, hyperparameter testing, and visualization of model results.

## Repository Structure

| File / Folder             | Description                                            |
| ------------------------- | ------------------------------------------------------ |
| `EDA.ipynb`               | Exploratory data analysis of the Diabetes dataset      |
| `BaselineModel.ipynb`     | Mean-prediction baseline model for comparison          |
| `ModelTraining.ipynb`     | Regression model development, training, and comparison |
| `HyperparamTesting.ipynb` | Hyperparameter testing and model refinement            |
| `results/`                | Generated analysis results and visualizations          |
| `Lab2.pdf`                | Project/lab takeaways                                  |
| `requirements.txt`        | Python dependencies                                    |

## Dataset

Uses the built-in Diabetes dataset from scikit-learn (`sklearn.datasets.load_diabetes`):

* **Samples**: 442 diabetes observations
* **Features**: 10 standardized clinical measurements, including age, sex, body mass index, blood pressure, and six blood serum measurements
* **Target**: A quantitative measure of diabetes disease progression one year after baseline

## Preprocessing

* **Feature Scaling** — the Diabetes dataset features are already standardized by scikit-learn, allowing the regression models to operate on comparable feature scales.
* **Train/Test Splitting** — the dataset was divided into training and testing sets so model performance could be evaluated on observations that were not used during training.
* **Baseline Comparison** — a mean predictor was established as a simple reference point, allowing each regression model to be evaluated against a non-learning baseline.
* **Model Diagnostics** — predictions and residuals were examined visually to identify systematic errors and differences in model behavior.

## Methods Implemented

1. **Linear Regression** — a simple and highly interpretable regression approach that models the target as a linear combination of the input features. Serves as an important baseline for determining whether more complex models provide meaningful improvements.

2. **Polynomial Regression** — extends linear regression by introducing polynomial feature relationships, allowing the model to capture nonlinear patterns between the clinical measurements and diabetes progression. Its additional flexibility is balanced against the potential for overfitting.

3. **Elastic Net** — combines L1 and L2 regularization to constrain model coefficients and reduce the influence of less useful features. This provides a balance between regularization and feature selection while maintaining the interpretability of a linear model.

4. **Random Forest** — an ensemble of decision trees that can capture nonlinear relationships and interactions between features without requiring a specific functional form. Model performance can also be examined through feature importance scores.

5. **Gradient Boosting** — builds an ensemble of decision trees sequentially, with each new tree attempting to correct errors made by previous trees. This provides a flexible approach for capturing complex relationships in the data and can be tuned through hyperparameter testing.

## Usage

1. Clone the repository and install dependencies:

```bash
git clone https://github.com/QuackJake/regression-model-analysis.git
cd regression-model-analysis
pip install -r requirements.txt
```

2. Launch Jupyter:

```bash
jupyter notebook
```

3. Run `EDA.ipynb` first for exploratory analysis, followed by `BaselineModel.ipynb` to establish the baseline.

4. Run `ModelTraining.ipynb` to train and compare the regression models, then use `HyperparamTesting.ipynb` to investigate model configuration and performance.

5. Review the generated results and visualizations in `results/`.

## Results

### Model Comparison

The five regression algorithms provide different approaches to predicting diabetes progression, with each offering different advantages in terms of flexibility, interpretability, and resistance to overfitting.

| Model                 | Key Strength                                                                | Key Limitation                                           |
| --------------------- | --------------------------------------------------------------------------- | -------------------------------------------------------- |
| Linear Regression     | Simple, interpretable, and effective baseline                               | Limited to linear relationships                          |
| Polynomial Regression | Captures nonlinear relationships between features                           | Greater risk of overfitting as complexity increases      |
| Elastic Net           | Regularized model that balances feature selection and coefficient shrinkage | Requires tuning of regularization parameters             |
| Random Forest         | Captures nonlinear relationships and feature interactions                   | Less interpretable than linear models                    |
| Gradient Boosting     | Strong predictive flexibility and sequential error correction               | More sensitive to hyperparameter choices and overfitting |

Linear Regression provides an important reference point because of its simplicity and interpretability, while Polynomial Regression introduces additional flexibility for nonlinear relationships. Elastic Net adds regularization to the linear approach, while Random Forest and Gradient Boosting use tree-based ensembles to model more complex patterns.

The comparison demonstrates why evaluating multiple regression approaches is useful: model performance depends not only on predictive accuracy, but also on how well each model generalizes and how understandable its predictions remain.

### Model Quality Assessment

Several evaluation methods are used to compare the regression models:

* **Mean Absolute Error (MAE)** measures the average magnitude of prediction errors.
* **Mean Squared Error (MSE)** places greater emphasis on larger prediction errors.
* **Root Mean Squared Error (RMSE)** provides error measurements in the same units as the target variable.
* **R²** measures how much of the variation in diabetes progression is explained by the model.
* Training and test metrics are compared to identify potential overfitting.
* Predicted-vs-actual plots show how closely model predictions follow observed values.
* Residual plots reveal systematic patterns in model errors.
* A mean predictor baseline provides context for determining whether the trained models provide meaningful predictive value.

### Feature Analysis

Feature coefficients and importance scores provide insight into which clinical measurements contribute most strongly to model predictions.

Linear and Elastic Net models provide coefficient-based interpretations of feature influence, while tree-based models such as Random Forest and Gradient Boosting provide feature importance measurements based on their learned decision structures.

Comparing feature importance across different model families can help identify measurements that consistently contribute to predictions while also showing how different modeling assumptions affect the interpretation of the dataset.

### Practical Applications

Although this analysis uses a relatively small academic dataset, the regression pipeline demonstrates how predictive modeling could be applied to diabetes-related research and health data analysis more broadly:

* **Disease progression research** — estimating quantitative measures of diabetes progression from baseline measurements
* **Risk analysis** — investigating relationships between clinical characteristics and future disease progression
* **Feature analysis** — identifying measurements that contribute strongly to predictive models
* **Model comparison** — evaluating whether more complex algorithms provide meaningful improvements over simpler approaches
* **Clinical research** — providing a framework for exploring predictive relationships in larger medical datasets

With larger and more representative datasets, similar modeling pipelines could be expanded to incorporate additional patient information and more robust validation procedures.

### Limitations & Future Work

**Limitations**

* The dataset contains only 442 observations.
* The available features represent a limited set of baseline clinical measurements.
* Regression performance depends on the train/test split and selected hyperparameters.
* More complex models can become difficult to interpret compared with linear approaches.
* Strong predictive performance on this dataset does not necessarily generalize to other patient populations.
* The dataset is intended for educational and research purposes rather than direct clinical decision-making.

**Future Work**

* Cross-validation for more robust model evaluation
* Ensemble and stacked regression approaches
* More extensive hyperparameter optimization
* Additional regularization and feature-selection techniques
* Explainable machine learning methods such as SHAP
* Larger and more diverse clinical datasets
* External validation using an independent dataset
* Longitudinal analysis using additional measurements collected over time

### Ethical Considerations

The Diabetes dataset contains health-related measurements, making responsible use and interpretation particularly important. Predictive models trained on medical data can produce misleading conclusions if they are treated as universally applicable or used outside the population represented by the training data.

Real-world deployment would require careful consideration of privacy, data security, demographic representation, potential bias, and model validation. A model's predictions should not automatically be interpreted as medical diagnoses or treatment recommendations.

Responsible use would call for clear documentation of what data is collected, how models are trained and evaluated, what the predictions represent, the limitations of the dataset, and who has access to the underlying information. Any clinical application would also require substantially more validation and appropriate professional oversight.

## Technologies & Libraries

* Python
* Jupyter Notebook
* NumPy
* Pandas
* Scikit-learn
* Matplotlib
* Seaborn
* SciPy

## Summary

This project demonstrates how multiple regression algorithms can be used to predict diabetes disease progression and compare different approaches to supervised learning. Linear Regression provides an interpretable baseline, while Polynomial Regression and Elastic Net demonstrate nonlinear modeling and regularization techniques. Random Forest and Gradient Boosting provide more flexible ensemble-based approaches capable of capturing nonlinear relationships and feature interactions.

The comparison of MAE, MSE, RMSE, R², feature importance, predicted-vs-actual plots, and residual diagnostics provides a broader evaluation than relying on a single performance metric. The project demonstrates the importance of comparing both simple and complex models when determining which regression approach is most appropriate for a given dataset.

## License

This project uses the Diabetes dataset from scikit-learn, which is in the public domain.
