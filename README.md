# California Housing Price Prediction: End-to-End Machine Learning Pipeline

This repository contains an end-to-end Machine Learning project to predict the **median house value** for districts in California, utilizing a robust data cleaning, feature engineering, and hyperparameter tuning pipeline built with Python and Scikit-learn.

The final optimized model is a **Random Forest Regressor** that achieved a Test Set **RMSE of $\$46,111.30$**.

## 🚀 Key Performance Summary

The final model shows strong predictive capability on unseen data, explaining over 83% of the variance in housing prices.

| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **Test Set RMSE** | **\$46,111.30** | The average prediction error (in USD) for median house value. |
| **Test Set $\text{R}^2$ Score** | **0.8369** | The model explains 83.69% of the variance in the target variable. |

## 🧠 Key Findings: Feature Importance

The model interpretation reveals the most influential factors driving California housing prices:

| Rank | Feature | Importance Score | Insight |
| :--- | :--- | :--- | :--- |
| **1** | **median_income** | 0.3193 | Unsurprisingly, household income is the single greatest predictor, accounting for nearly a third of the model's predictive power. |
| **2** | **ocean_proximity_INLAND** | 0.1518 | Proximity to the coast (specifically being *Inland*) acts as a strong negative predictor of price. |
| **3** | **population_per_household** | 0.1059 | This engineered feature (a density metric) is more important than raw population count, suggesting neighborhood density is critical. |
| 4 | bedrooms_per_room | 0.0880 | Another strong engineered feature, suggesting the balance of space within a unit matters significantly. |
| 5 | longitude | 0.0821 | Geographic location remains highly influential after accounting for other factors. |

## 🛠️ Methodology Highlights

The solution leverages a flexible Scikit-learn pipeline, ensuring robust and consistent data transformation:

1.  **Stratified Sampling:** Data was split based on income categories to ensure representative training and test sets.
2.  **Custom Feature Engineering:** Added key ratio features (`population_per_household`, `bedrooms_per_room`).
3.  **Cross-Validation:** Benchmarked three models, confirming Random Forest was the strongest candidate (initial RMSE: $\text{\$50,435.58}$).
4.  **Hyperparameter Tuning:** Used `GridSearchCV` to optimize the Random Forest, achieving the final $\text{RMSE}$ reduction.

Refer to the **`Data-Housing-Machine-Learning.ipynb`** notebook for the full analysis, pipeline code, and residual plot diagnostics.