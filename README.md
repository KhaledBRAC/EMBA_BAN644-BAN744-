# 🫀 Heart Disease Prediction: A Machine Learning Approach
**Course Project: BAN644/BAN744 - Applied Machine Learning for Business Analytics with Python**

## 📌 Project Objective
The goal of this project is to apply classification machine learning techniques to solve a critical healthcare analytics problem: predicting the presence of heart disease in patients. By accurately categorizing patients, healthcare administrators can improve risk management, optimize diagnostic resources, and prioritize high-risk patient interventions.

## 📊 Dataset
This project utilizes a structured dataset containing patient health metrics (e.g., age, cholesterol levels, chest pain type). 
* **Target Variable:** Presence of Heart Disease (Categorical: Yes/No)

## 🛠️ Methodology & Workflow
This project strictly follows a professional data science pipeline, avoiding "black-box" implementation by prioritizing mathematical understanding and model optimization.

1. **Data Preprocessing:** Handled missing values, removed duplicates, and applied `StandardScaler` to normalize numerical features.
2. **Exploratory Data Analysis (EDA) & Feature Selection:** Utilized Seaborn heatmaps to analyze correlation matrices, identifying and managing highly collinear features to reduce model noise.
3. **Model Development:** Developed baseline classification models using **Logistic Regression** and **Random Forest Classifier**.
4. **Model Optimization:** Implemented hyperparameter tuning using `GridSearchCV` to systematically discover the mathematically optimal configuration for the models.
5. **Evaluation:** Assessed models prioritizing **Recall** over Accuracy, ensuring the minimization of false negatives, which is the most critical metric in clinical diagnostics.

## 🚀 Key Business Insights
The optimized model serves as a strategic asset for healthcare operations. It can be deployed as a secondary backend validation tool to audit existing diagnostic workflows, eventually scaling to a frontline triage assistant. This optimizes dispute management (e.g., justifying diagnostic decisions to insurance providers) and streamlines overall resource allocation.

## 💻 Technologies Used
* **Language:** Python
* **Libraries:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn
* **Environment:** Google Colaboratory

---
*Created by Md Khaled Saifulla*
