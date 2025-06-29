## Store Sales - Linear Regression Solution
A linear regression approach for the Store Sales - Time Series Forecasting Kaggle competition.

## Overview
This repository contains a complete model for forecasting store sales using linear regression. The solution leverages modern data science best practices and a modular codebase, following the Cookiecutter Data Science project structure.

The goal is to predict daily sales for a large Ecuadorian grocery retailer, using historical sales data, promotions, oil prices, holidays, and store information.

## Note

**Looking for a more complete solution?**

Check out the [Deep Learning Solution repository](https://github.com/TommMakk/store-sales-deep-learning) for a more comprehensive approach.

- Includes a Streamlit dashboard for interactive data exploration
- Implements advanced feature engineering and modeling
- Achieves better forecasting performance for this competition

## Project Organization

```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default mkdocs project; see www.mkdocs.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── pyproject.toml     <- Project configuration file with package metadata for 
│                         store_sales and configuration for tools like black
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.cfg          <- Configuration file for flake8
│
└── store_sales   <- Source code for use in this project.
    │
    ├── __init__.py             <- Makes store_sales a Python module
    │
    ├── config.py               <- Store useful variables and configuration
    │
    ├── dataset.py              <- Scripts to download or generate data
    │
    ├── features.py             <- Code to create features for modeling
    │
    ├── modeling                
    │   ├── __init__.py 
    │   ├── predict.py          <- Code to run model inference with trained models          
    │   └── train.py            <- Code to train models
    │
    └── plots.py                <- Code to create visualizations
```

--------

## Linear Regression Approach

### Methodology

Our solution utilizes a robust linear regression pipeline tailored for time series forecasting in the retail domain. The key steps include:

1. **Data Preprocessing & Cleaning**  
   - Raw sales, oil, holiday, and store data are merged.  
   - Missing values are handled, and categorical variables are encoded using one-hot encoding.

2. **Feature Engineering**  
   - Generate lag-based features, rolling statistics, and calendar-based features (e.g., day of week, holidays, paydays) to capture temporal patterns and external influences on sales.

3. **Exploratory Data Analysis (EDA)**  
   - Visualize data distributions, trends, and correlations to inform feature selection and model design.

4. **Model Development**  
   - Use a regularized linear regression model (such as Ridge or Lasso), implemented with scikit-learn.  
   - Train the model on engineered features to predict daily sales.

5. **Training Strategy**  
   - Train using historical data, with cross-validation to select optimal regularization parameters and prevent overfitting.

6. **Evaluation**  
   - Monitor model performance using Mean Squared Error (MSE) and Mean Absolute Error (MAE) on a validation set.  
   - Save the final model and use it for inference on the test set.

### Model Structure

- **Input:** Engineered features for each store-date-family combination.  
- **Model:** Linear regression (optionally with Ridge/Lasso regularization).  
- **Output:** Predicted sales value for each record.

### Training and Optimization

- **Optimizer:** Closed-form solution or coordinate descent (as implemented in scikit-learn)  
- **Loss Function:** Mean Squared Error (MSE)  
- **Regularization:** L2 (Ridge) or L1 (Lasso) to prevent overfitting  
- **Cross-Validation:** Used to select regularization strength


## Conclusion

This linear regression solution achieved a public leaderboard score of 1.21559 on the Kaggle Store Sales - Time Series Forecasting competition, using default model settings and without further optimization.

**Key factors for predictive performance:**

- Use of promotion indicators, reflecting the significant impact of promotions on sales.
- Incorporation of oil price fluctuations, which significantly affected sales due to Ecuador's status as an oil-dependent country. Changes in oil prices influenced both consumer purchasing power and operational costs, making them an important feature in the forecasting model.
- During model development, the main assumptions of linear regression (such as linearity, independence, homoscedasticity, and normality of residuals) were carefully tested. However, these assumptions were not fully satisfied for this dataset, which is common in complex, real-world time series problems.

Rather than focusing on advanced improvements to linear regression, the project transitioned to deep learning models, which are better suited to capture the non-linear relationships and intricate patterns present in the data.

**Real-world business applications of accurate sales forecasting:**

- Inventory management: Reduce overstock and stockouts.
- Food waste reduction: Better match supply with demand, especially for perishable goods.
- Supply chain optimization: Improve ordering and logistics planning.
- Staffing and resource planning: Align workforce and resources with expected demand.
- Promotional planning: Evaluate and optimize the impact of marketing campaigns.

While linear regression offers valuable insights and a strong starting point, more advanced models—such as deep learning—are recommended for achieving higher accuracy in this context. Classical approaches such as ARIMA, SARIMA, Exponential Smoothing, or tree-based models like XGBoost often provide competitive or superior results with less computational overhead and easier interpretability.



## References

- [Kaggle Competition Overview](https://www.kaggle.com/competitions/store-sales-time-series-forecasting/overview)
- [Cookiecutter Data Science](https://drivendata.github.io/cookiecutter-data-science/)

---

## License

This project is open source and available under the [MIT License](LICENSE).

---

[![CCDS Project template](https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter)](https://cookiecutter-data-science.drivendata.org/)