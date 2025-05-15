# Cardiovascular Disease Risk Analysis and Prediction

Cardiovascular diseases (CVD) are among the leading causes of death worldwide. This project utilizes a dataset of over 4,000 patient records and 14 clinical attributes to analyze CVD risk factors, perform exploratory data analysis (EDA), and build predictive models for disease classification.

---

## 📌 Project Objectives

- Identify key factors that significantly influence heart disease.
- Conduct in-depth exploratory data analysis (EDA).
- Build and evaluate predictive models to classify patients as diseased or healthy.
- Create an interactive Tableau dashboard to visualize insights.

---

## 📊 Data Overview

The dataset includes 14 features such as age, sex, cholesterol, and heart rate measurements, along with a binary target variable indicating heart disease presence (1) or absence (0).

---

## 🧹 Data Inspection & Cleaning

- **Duplicates**: Removed using `.drop_duplicates()`
- **Missing Values**: Present in `ca` and `thal`; imputed using mode.
- **Data Types**: No inconsistencies found.

---

## 📈 Statistical Summary

- **Age**: Mean ≈ 54 years | SD ≈ 9
- **Cholesterol** (`chol`): Mean ≈ 246 mg/dL (right-skewed)
- **Max Heart Rate** (`thalach`): Mean ≈ 150 bpm
- **Target**: Binary (1 = Heart Disease, 0 = No Disease)

---

## 🔍 Exploratory Data Analysis (EDA)

### Categorical Features:
- Variables: `sex`, `cp`, `fbs`, `restecg`, `exang`, `slope`, `ca`, `thal`
- Visualized using count plots for distribution.

### Age vs. CVD:
- Most CVD cases occur between ages **50–60**.
- Lower incidence for those <40 and >70.

### Blood Pressure:
- Extremely high/low `trestbps` values associated with higher CVD occurrence.

### Gender Distribution:
- **Males** dominate the dataset and show higher heart disease prevalence.

### Cholesterol Levels:
- High cholesterol not always indicative of CVD.
- Some normal-cholesterol patients still developed heart disease.

### Peak Heart Rate (`thalach`):
- **Inverse relationship** with CVD.
- Healthy individuals reach higher heart rates during exercise.

### Thalassemia (`thal`):
- `thal = 7` (reversible defect) strongly linked to heart disease.
- Other important predictors: `cp`, `oldpeak`, `ca`, `thalach`.

---

## 🧠 Predictive Modeling

### 1. Logistic Regression
- **Accuracy**: **89%**
- **Confusion Matrix**: **[[25 4]**  **[ 3 29]]**

- **Performance**:
- Class 1 (Diseased): High recall (0.91) and F1-score (0.89)
- Model slightly favors detecting disease (minimizing false negatives)
- Balanced performance between precision and recall

### 2. Random Forest Classifier
- **Accuracy**: 88%
- **Observations**:
- 7 misclassifications
- FN cases are more concerning in medical diagnostics
- Strong overall performance with balanced precision and recall

### 3. Gradient Boosting
- **Accuracy**: 84%
- Slightly lower than Random Forest, but strong F1-score

---

## 🧰 Feature Engineering

Interaction terms were introduced to improve model performance:
- `CP_Thal`, `exang_thal`, `thalach_restecg`
- Helped enhance logistic regression accuracy and generalizability

---

## 📊 Visualization with Tableau

- Interactive dashboards using filters by `age`, `sex`, and `cp`
- Visual separation of healthy vs. diseased patients based on key features like `thal`, `cp`, and `thalach`

---

## 🔑 Key Insights

- **Top Predictors**:
- `cp` (chest pain type)
- `thalach` (maximum heart rate achieved)
- `oldpeak` (ST depression)
- `ca` (number of major vessels)
- `thal` (type of thalassemia)

- Logistic regression achieved the highest accuracy (**89%**)
- Cholesterol is not a sole determinant of heart disease
- Visualization aids clinicians in interpreting model predictions and risk profiles

---

## ✅ Conclusion

- A clean, well-prepared dataset and smart feature engineering enabled strong model performance.
- Logistic Regression emerged as the best-performing model.
- Tableau dashboards provide intuitive insights for medical professionals and stakeholders.

---

## 📁 Project Structure
- ├── data/ # Raw and cleaned data
- ├── notebooks/ # Jupyter notebooks for EDA and modeling
- ├── models/ # Saved models
- ├── tableau_dashboard/ # Tableau workbook and screenshots
- ├── README.md # Project overview
- └── requirements.txt # Dependencies

---

## 📌 Requirements

- Python 3.x
- pandas, numpy, seaborn, matplotlib
- scikit-learn
- Tableau (for visualization)

---




