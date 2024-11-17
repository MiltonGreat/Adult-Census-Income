# Adult Census Income Classification Project

### Overview

This project uses the **Adult Census Income** dataset extracted from the 1994 Census Bureau database to predict income levels (`<=50K` or `>50K`). It demonstrates the application of **one-hot encoding** and **normalization** for preprocessing data and evaluates models such as **Logistic Regression** and **Random Forest Classifier** for classification tasks. 

The dataset contains both numerical and categorical features, making it a great candidate for showcasing preprocessing techniques in machine learning.

### Dataset

- **File Name**: `adult.csv`
- **Source**: UCI Machine Learning Repository
- **Dataset Features**:
  - **Categorical Features**: `workclass`, `education`, `marital.status`, `occupation`, `relationship`, `race`, `sex`, `native.country`, `income`
  - **Numerical Features**: `age`, `fnlwgt`, `education.num`, `capital.gain`, `capital.loss`, `hours.per.week`

#### Target Variable
- **Income**: Binary classification into `<=50K` and `>50K`.

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

#### 4. Results
- **Classification Reports**:
  - Show precision, recall, and F1-scores for each income class.
- **Confusion Matrices**:
  - Visualized using heatmaps for both models to analyze predictions.

### Key Results

| Model                  | Accuracy | Precision (<=50K) | Recall (<=50K) | F1-Score (<=50K) | Precision (>50K) | Recall (>50K) | F1-Score (>50K) |
|------------------------|----------|-------------------|----------------|------------------|------------------|---------------|-----------------|
| Logistic Regression    | 84.20%   | 87%               | 92%            | 90%              | 72%              | 60%           | 65%             |
| Random Forest Classifier | 84.24%   | 88%               | 92%            | 90%              | 72%              | 61%           | 66%           |

### Future Improvements

    Hyperparameter Tuning:
        Use GridSearchCV or RandomizedSearchCV for optimizing model performance.
    Feature Engineering:
        Explore additional features like interaction terms or polynomial transformations.
    Addressing Class Imbalance:
        Use techniques like SMOTE (Synthetic Minority Oversampling) to balance the dataset.

### Source

https://www.kaggle.com/datasets/uciml/adult-census-income
