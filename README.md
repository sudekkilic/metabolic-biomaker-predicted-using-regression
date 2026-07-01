# Metabolic Biomarker Prediction Using Regression

This project predicts metabolic biomarkers, especially **Triglycerides** and **HDL cholesterol**, using regression-based machine learning models on NHANES 2011-2018 data. It also evaluates whether predicted biomarker values can be used to detect clinically important risk thresholds.

## Project Objective

The main goal is to build and compare machine learning models that estimate:

- **Triglycerides** level in mg/dL
- **HDL cholesterol** level in mg/dL

The project also converts model predictions into clinical risk decisions using medical thresholds:

- High triglycerides: **> 150 mg/dL**
- Low HDL:
  - Men: **< 40 mg/dL**
  - Women: **< 50 mg/dL**

## Dataset

The notebook uses an extended NHANES 2011-2018 dataset containing demographic, body measurement, blood pressure, laboratory, and dietary variables.

The raw dataset is not included in this repository. In the notebook, the data is loaded from Google Drive:

```python
/content/SudeDrive/MyDrive/ML metabolic biomaker/NHANES_2011_2018_ExtendedComplete (1).csv
```

To run the notebook, update the dataset path according to your local or Google Drive environment.

## Repository Contents

```text
.
|-- G07_M11_code.ipynb   # Main project notebook
|-- README.md            # Project documentation
|-- LICENSE              # MIT License
`-- .gitignore           # Ignored files and generated artifacts
```

## Workflow

The notebook follows a complete machine learning workflow:

1. Data understanding and exploratory data analysis
2. Data cleaning and leakage control
3. Preprocessing with scaling and target transformation
4. Medical and physiological feature engineering
5. Feature configuration comparison
6. Feature reduction with PCA and tree-based importance
7. Regression model training and hyperparameter tuning
8. Ensemble modeling with stacking
9. Feature importance analysis
10. Medical threshold evaluation
11. Direct classification models for clinical risk detection

## Feature Engineering

The project creates engineered features based on metabolic and physiological reasoning, including:

- BMI squared
- Waist-to-height ratio
- BMI and age interaction
- Mean arterial pressure
- Pulse pressure
- Glucose to HbA1c ratio
- Sugar to fiber ratio
- Saturated fat to total fat ratio
- Fat intake normalized by calories
- Fat to carbohydrate ratio

## Models Used

Regression models:

- Linear Regression
- Ridge Regression
- Lasso Regression
- Random Forest Regressor
- Gradient Boosting Regressor
- XGBoost Regressor
- Stacking Regressor

Classification models for clinical risk detection:

- Logistic Regression
- Random Forest Classifier

## Evaluation

Regression performance is evaluated with common continuous prediction metrics such as error and goodness-of-fit scores. The project also evaluates clinical threshold detection using:

- Accuracy
- Sensitivity
- Specificity

For the classification part, direct risk prediction is compared against the regression-then-threshold approach.

## Requirements

The notebook uses Python and common data science libraries:

```text
numpy
pandas
matplotlib
seaborn
scikit-learn
xgboost
scipy
```

If running in Google Colab, most dependencies are already available. If running locally, install the required packages with:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn xgboost scipy
```

## How to Run

1. Open `G07_M11_code.ipynb` in Google Colab or Jupyter Notebook.
2. Make sure the NHANES dataset is available.
3. Update the CSV path in the data loading cell if needed.
4. Run the notebook cells in order.

## License

This project is licensed under the MIT License.
