# 📚 E-Learning Activity Score Prediction

Predicting student e-learning activity scores using Multiple Linear Regression (MLR) and Support Vector Regression (SVR) with data preprocessing, hyperparameter tuning, and model evaluation.

---

## 📖 Overview

This project aims to predict student E-Learning Activity Scores based on demographic, academic, and learning behavior data.

The project implements and compares two regression algorithms:

- Multiple Linear Regression (MLR)
- Support Vector Regression (SVR)

The workflow includes:

- Exploratory Data Analysis (EDA)
- Correlation Analysis
- Data Preprocessing
- Feature Scaling
- Hyperparameter Tuning
- Model Training
- Model Evaluation
- Cross Validation
- Performance Comparison

---

## 🎯 Objectives

- Analyze factors affecting student e-learning activity.
- Develop predictive models using machine learning.
- Compare Multiple Linear Regression and Support Vector Regression.
- Determine the best-performing model for predicting student engagement.

---

## 🗂️ Dataset

The dataset contains student demographic, academic, and learning activity information.

### Features

| Feature | Description |
|----------|-------------|
| Age | Student age |
| Gender | Student gender |
| Marital Status | Marital status |
| Academic Status | Academic status |
| Attendance (%) | Attendance percentage |
| Discussion Participation | Discussion participation score |
| Assignment Score | Average assignment score |
| LMS Login Frequency | Weekly LMS login frequency |
| E-Learning Activity Score | Target variable |

### Target Variable

```text
E-Learning Activity Score
```

---

# 🔄 Project Workflow

```text
Dataset
   │
   ▼
Data Understanding
   │
   ▼
Exploratory Data Analysis
   │
   ▼
Correlation Analysis
   │
   ▼
Data Preprocessing
 ├─ Encoding
 ├─ Outlier Detection
 ├─ Train-Test Split
 └─ Standardization
   │
   ▼
Model Development
 ├─ Multiple Linear Regression
 └─ Support Vector Regression
   │
   ▼
Hyperparameter Tuning
   │
   ▼
Model Evaluation
   │
   ▼
Cross Validation
   │
   ▼
Model Comparison
```

---

# 📊 Exploratory Data Analysis

## Categorical Variable Distribution

Distribution analysis for:

- Gender
- Marital Status
- Academic Status

<img width="650" alt="plot_eda_kategorikal" src="https://github.com/user-attachments/assets/d7956a88-e4fe-41c8-a415-410b7d774405" />

---

## Numerical Variable Distribution

Distribution analysis for:

- Attendance
- Discussion Participation
- Assignment Score
- Login Frequency
- E-Learning Activity Score

<img width="650" alt="plot_distribusi_numerik" src="https://github.com/user-attachments/assets/cba260cc-6d26-4dfe-9968-8b139fafa57d" />

---

## Target Variable Analysis

Histogram and boxplot of the target variable.

<img width="2067" height="732" alt="plot_target_variable" src="https://github.com/user-attachments/assets/9cccb3ac-d259-4be0-9e4e-ab6518999458" />

---

# 🔥 Correlation Analysis

Understanding relationships among variables.

## Correlation Heatmap

<img width="650" alt="plot_heatmap_korelasi (1)" src="https://github.com/user-attachments/assets/97ff6107-a1be-4360-a743-39758c19cae7" />

---

## Correlation with Target Variable

<img width="650" alt="plot_korelasi_target" src="https://github.com/user-attachments/assets/f34b1e70-ed9b-46cc-9352-85c78f734b95" />

---

# ⚙️ Data Preprocessing

## Label Encoding

Categorical variables are converted into numerical values.

Variables encoded:

- Gender
- Marital Status
- Academic Status

---

## Outlier Detection

Outliers are detected using the Interquartile Range (IQR) method.

```python
Q1 = data.quantile(0.25)
Q3 = data.quantile(0.75)
IQR = Q3 - Q1
```

---

## Train-Test Split

```python
test_size = 0.2
random_state = 42
```

Training Data: 80%

Testing Data: 20%

---

## Feature Scaling

```python
StandardScaler()
```

Applied before training Support Vector Regression.

---

# 🤖 Multiple Linear Regression (MLR)

## Model Training

```python
from sklearn.linear_model import LinearRegression

mlr = LinearRegression()
mlr.fit(X_train, y_train)
```

---

## Regression Coefficients

<img width="650" alt="plot_residual_mlr (3)" src="https://github.com/user-attachments/assets/92a2c1dc-f972-4360-855f-a203c0aae068" />

---

## Actual vs Predicted

<img width="650" alt="plot_prediksi_mlr" src="https://github.com/user-attachments/assets/bc378d79-ef62-47e2-9150-44d7082a748d" />

---

## Residual Analysis

<img width="650" alt="image" src="https://github.com/user-attachments/assets/0d036673-178c-4713-a189-4c1a7087b0d7" />

---

# 🚀 Support Vector Regression (SVR)

## Hyperparameter Tuning

GridSearchCV is used to find optimal parameters.

```python
param_grid = {
    'kernel': ['linear', 'rbf'],
    'C': [0.1, 1, 10, 100],
    'gamma': ['scale', 'auto'],
    'epsilon': [0.01, 0.1, 0.5]
}
```

---

## Actual vs Predicted

<img width="650" alt="image" src="https://github.com/user-attachments/assets/5ade7d26-fc8a-476b-936c-db264ce910c7" />

---

## Residual Analysis

<img width="650" alt="image" src="https://github.com/user-attachments/assets/b9bdd294-f45d-4a54-b7df-6b05ccd13430" />

---

# 📈 Model Evaluation

Evaluation metrics:

| Metric | Description |
|----------|------------|
| MAE | Mean Absolute Error |
| MSE | Mean Squared Error |
| RMSE | Root Mean Squared Error |
| R² | Coefficient of Determination |
| MAPE | Mean Absolute Percentage Error |

---

# 🔄 Cross Validation

10-Fold Cross Validation is applied to evaluate model stability.

```python
KFold(n_splits=10)
```

## Cross Validation Result

<img width="1184" alt="image" src="https://github.com/user-attachments/assets/7e5e1c80-641b-4072-97e1-a304aed8eb17" />

---

# 🏆 Model Comparison

Comparison between MLR and SVR.

Metrics compared:

- MAE
- RMSE
- R²
- MAPE

<img width="1184" alt="image" src="https://github.com/user-attachments/assets/434f72f4-c331-4238-9cf4-5c0d059c2429" />


---

## Prediction Comparison

Actual values vs predicted values.

<img width="1384" alt="image" src="https://github.com/user-attachments/assets/aedd3854-3ab6-4dd4-a7ae-7c5f7b5f5eeb" />

---

# 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- Statsmodels
- SciPy
- Google Colab

---

# 📌 Results

The project evaluates and compares Multiple Linear Regression and Support Vector Regression to determine the most effective model for predicting student e-learning activity scores.

The best model is selected based on:

- Lowest RMSE
- Lowest MAE
- Highest R²
- Stable Cross Validation Performance

---

# 🚀 Future Work

- Deploy model using Streamlit
- Develop an interactive dashboard
- Add more educational features
- Compare with Random Forest Regression
- Compare with XGBoost Regression

---

## 👨‍💻 Author

Machine Learning Project for Educational Data Mining and Student Engagement Prediction.
