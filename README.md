# Titanic Survival Prediction 🚢

This repository contains my **Titanic Machine Learning Project**, where I analyze the dataset, engineer features, build a predictive model, and optimize it using Bayesian optimization with Optuna.

👉 [View the Kaggle Notebook here](https://www.kaggle.com/code/serayustun/titanic-machine-learning-from-disaster)

## 📂 Dataset

The dataset is provided by [Kaggle Titanic Competition](https://www.kaggle.com/c/titanic).  
We use:
- Training set: `/kaggle/input/titanic/train.csv`
- Test set: `/kaggle/input/titanic/test.csv`

## 📝 Project Overview

- Perform **Exploratory Data Analysis (EDA)** with visualizations
- Clean missing data and engineer new features
- Encode categorical variables
- Build and tune a **Random Forest Classifier** using Optuna
- Evaluate the final model with accuracy, classification report, and ROC curve

## 📊 Key Steps

### 1️⃣ Exploratory Data Analysis
- Survival distribution (pie & bar charts)
- Distributions of `Age` and `Fare`
- Survival by `Pclass`, `Sex`, and `Embarked`
- Age distribution by survival

### 2️⃣ Data Cleaning
- Fill missing `Age` (median) and `Embarked` (mode)
- Drop `Cabin` due to excessive missing values

### 3️⃣ Feature Engineering
- `FamilySize` = `SibSp + Parch + 1`
- `IsAlone` = 1 if passenger is alone, else 0
- Extract `Title` from `Name` and group rare titles
- Bin `Fare` and `Age` into categories (`FareBins`, `AgeBins`)

### 4️⃣ Data Preparation
- Drop irrelevant columns: `SibSp`, `Parch`, `Age`, `Fare`, `Name`, `Ticket`, `PassengerId`
- Encode categorical features with one-hot encoding
- Split into training and test sets (`80/20`)

### 5️⃣ Model Training & Optimization
- Train a Random Forest Classifier
- Hyperparameter tuning with **Optuna** (100 trials)
- Best cross-validated accuracy: ~0.83
- Final test set accuracy: ~0.82

---

## 📈 Results

| Metric               | Score  |
|-----------------------|--------|
| Test Accuracy         | **0.82** |
| ROC AUC               | ~0.89  |

## 🔍 Evaluation Metrics
### 🟢 **Classification Report:**

(result_images/result.png)

### 🟢 **Confusion Matrix**

(result_images/confusion_matrix.png)

### 🟢 **ROC AUC Curve**

(result_images/roc_auc)

## 🧾 Conclusions

- The model achieved **82% accuracy** and an AUC of **0.89**, showing strong performance in predicting survival.
- The ROC curve indicates the model significantly outperforms random guessing.
- Feature engineering (e.g., `Title`, `FamilySize`, `IsAlone`) improved prediction performance.
- The main misclassifications occurred in detecting survivors, which could be further reduced with more complex models or additional features.

## 📚 References

- [Kaggle Titanic Competition](https://www.kaggle.com/c/titanic)
- Scikit-learn documentation: https://scikit-learn.org/
- Optuna documentation: https://optuna.org/

  
