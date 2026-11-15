# Bank Marketing Campaign Prediction

This project uses machine learning to predict whether a customer will subscribe to a term deposit (`y`) after a bank marketing campaign. The project includes data preparation and four model workflows. **Version 2 is the final version**; the older notebooks are kept in `version1(old-version)` for reference.

## Project structure

```text
gp27_pjWork/
├── raw_data/
│   └── bank-full.csv
├── cleaned_data/
│   ├── train_data.csv
│   ├── test_data.csv
│   └── X_test_selected_rf.csv
├── models/                         # Saved model and comparison outputs
├── version1(old-version)/          # Previous notebooks
└── version2(final-version)/        # Use these notebooks
    ├── data_cleansing2.ipynb
    ├── logistic_regression_model.ipynb
    ├── random_forest.ipynb
    ├── XGboost.ipynb
    └── model_comparison.ipynb
```

## Version 2 workflow

Run the notebooks in this order from their folder (`gp27_pjWork/version2(final-version)`). The notebook paths expect this working directory.

1. **`data_cleansing2.ipynb`** — reads `../raw_data/bank-full.csv`, prepares the data, and writes the train and test files to `../cleaned_data/`.
2. **`logistic_regression_model.ipynb`** — trains and evaluates logistic regression; saves the fitted model under `../models/`.
3. **`random_forest.ipynb`** — trains and evaluates random forest; saves its model and selected test features used for comparison.
4. **`XGboost.ipynb`** — trains and evaluates XGBoost; saves its model under `../models/`.
5. **`model_comparison.ipynb`** — compares the trained models and writes a comparison summary to `../models/`.

The model notebooks use the prepared CSV files, so run data cleansing first. Keep the project directory layout intact so their relative paths resolve.

## Requirements

Use Python 3 with Jupyter Notebook or JupyterLab. Install the packages used by the notebooks:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn joblib xgboost jupyter
```

## Run

From the project root:

```bash
cd "gp27_pjWork/version2(final-version)"
jupyter notebook
```

Open the notebooks above and run their cells from top to bottom. Model training may take some time because the notebooks tune model parameters.

## Data and target

The input is the Bank Marketing dataset in `gp27_pjWork/raw_data/bank-full.csv`. The target column is `y`, indicating whether the customer subscribed (`yes` or `no`). The version 2 cleaning notebook removes `duration` to avoid target leakage and prepares train/test data for model training.

## Outputs

Model files (`*.pkl`) and comparison results are generated under `gp27_pjWork/models/`. These are outputs of the notebooks and may not be present before running the workflow.
