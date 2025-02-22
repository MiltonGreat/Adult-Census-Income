# Adult Census Income Classification

### Overview

This project focuses on building a machine learning model to predict whether an individual earns more or less than $50,000 per year. 

This project uses the **Adult Census Income** dataset extracted from the 1994 Census Bureau database to predict income levels (`<=50K` or `>50K`). It demonstrates the application of **one-hot encoding** and **normalization** for preprocessing data and evaluates models such as **Logistic Regression** and **Random Forest Classifier** for classification tasks. 

### Quality Issues

Data Problems:
- Missing or inconsistent values (e.g., ? in workclass or occupation).
- Imbalanced target variable (<=50K dominates).

Cleaning:
- Replace ? with NaN and impute or drop rows/columns as needed.
- Normalize numerical features for models like Logistic Regression.
- Address class imbalance using SMOTE or cost-sensitive learning.

Known Limitations:
- Imbalanced target variable.
- Data is from 1994, so it may not reflect current demographic or economic trends.

### Dataset

The dataset includes 32,561 records and 15 attributes. Key attributes include:
- **Numerical Features**: `age`, `fnlwgt`, `education.num`, `capital.gain`, `capital.loss`, `hours.per.week`.
- **Categorical Features**: `workclass`, `education`, `marital.status`, `occupation`, `relationship`, `race`, `sex`, `native.country`, `income`.

#### Class Distribution
- **<=50K**: Majority class (approximately 75% of records).
- **>50K**: Minority class (approximately 25% of records).

### Project Workflow

#### 1. Data Preprocessing
- **Handling Missing Values**:
  - Replaced `?` with `NaN` and dropped rows with missing values.
- **One-Hot Encoding**:
  - Encoded categorical features into numerical format using `OneHotEncoder`.
- **Normalization**:
  - Scaled numerical features using `StandardScaler` for improved model performance.

#### 2. Train-Test Split
- Split the dataset into **80% training** and **20% testing** sets.

#### 3. Model Training and Evaluation
- **Logistic Regression**:
  - Model trained with a maximum of 1000 iterations.
  - Achieved an accuracy of **84.20%**.
- **Random Forest Classifier**:
  - Used 100 decision trees for the ensemble.
  - Achieved an accuracy of **84.24%**.

### Key Insights

The Random Forest classifier achieved an overall accuracy of 84%. However, the model exhibited lower performance for the minority class (>50K), with precision and recall of 67% and 70%, respectively, highlighting the challenge of class imbalance.

Fairness analysis revealed a significant discrepancy in model performance across genders, with higher accuracy for females (92.42%) compared to males (79.90%). This indicates potential bias in the model, which warrants further investigation and mitigation to ensure equitable predictions. Interpretability tools like LIME provided insights into the model's decision-making process, revealing that features such as education level, marital status, and capital gains played a significant role in predictions.

While the model demonstrates strong predictive capabilities, there is room for improvement. Future work could focus on addressing class imbalance through advanced resampling techniques, mitigating bias by incorporating fairness-aware algorithms, and optimizing hyperparameters to enhance performance for the minority class. Additionally, feature engineering and the exploration of alternative models, such as XGBoost or neural networks, could further improve predictive accuracy and robustness.

### Future Improvements

- Perform hyperparameter tuning for Logistic Regression and Random Forest.
- Experiment with ensemble models like Gradient Boosting or LightGBM.
- Analyze feature importance using SHAP or LIME for better interpretability.

### Source

Dataset: [Adult Census Income Dataset on Kaggle](https://www.kaggle.com/datasets/uciml/adult-census-income)
