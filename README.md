# Student Performance Prediction

This project aims to predict whether a student is likely to **fail** based on features such as parental education, support systems, and lifestyle choices. It uses the [UCI Student Performance Dataset](https://archive.ics.uci.edu/ml/datasets/Student+Performance), and employs machine learning with preprocessing techniques like SMOTE to handle class imbalance.

---

## Dataset

- Source: UCI Machine Learning Repository  
- File used: `student-mat.csv`  
- Total records: 649 students

---

## Project Goals

1. **Binary Classification** of students as either:  
   - `0` → did **not** fail  
   - `1` → **failed** (based on the original `failures` column)
2. **Model Training** with:
   - Random Forest (and optionally XGBoost)
   - SMOTE for class imbalance
   - GridSearchCV for hyperparameter tuning
3. **EDA** to understand how features like `studytime`, `absences`, and `goout` relate to grades

---

## Features Used

| Feature     | Description                        |
|-------------|------------------------------------|
| `age   `    | Student age                        | 
| `famsup`    | Family educational support         |
| `schoolsup` | Extra educational support at school|
| `studytime` | Weekly study time                  |
| `activities`| Participation in extracurriculars  |
| `absences`  | Number of school absences          |
| `internet`  | Internet access at home            |
| `Fedu`      | Father's education level           |
| `Medu`      | Mother's education level           |
| `goout`     | Going out with friends             |

We exlude the student grades as students who score high are guaranteed to pass.


A new binary target column `failed` was created from the `failures` column.

---

## Preprocessing

- **Missing Values**: None present  
- **Categorical Encoding**: Used `LabelEncoder` and `get_dummies` as needed  
- **Feature Scaling**: Not required for tree-based models  
- **Class Imbalance**: Addressed using **SMOTE**

---

## Exploratory Data Analysis (EDA)

Plots used:
- Average grade (`G3`) vs. `studytime`
- Boxplot of `G3` vs. `goout`
- Countplot of `studytime` by `failed`
- Correlation heatmap of features vs. grade

Findings:
- Higher `studytime` tends to correlate with better grades
- Going out a lot generally corresponds with lower performance
- Absences show weak negative correlation with final grade

---


