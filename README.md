# 🫀 Heart Disease Prediction: A Strategic Machine Learning Approach
**Course Project: BAN644/BAN744 - Applied Machine Learning for Business Analytics with Python**
## Key Highlights
* **Best Performing Model:** Random Forest (Tuned)
* **Model Accuracy:** 93.44% (0.9344)
* **Target Metric (Healthcare Focus):** Recall (96.43%) and ROC-AUC (96.43%)

## Objective
The goal of this project is to apply machine learning classification techniques to solve a real-world healthcare analytics problem: predicting whether a patient has heart disease based on clinical parameters.

## Step-by-Step Process

### 1. Data Collection
* **Source:** UCI Machine Learning Repository (Cleveland Heart Disease Dataset).
* **Task:** Binary Classification (Target: 1 = Heart Disease Present, 0 = No Heart Disease).

### 2. Data Preprocessing
* **Missing Values:** Handled missing values in `ca` and `thal` columns using median imputation.
* **Outlier Detection:** Capped outliers in continuous variables (`age`, `trestbps`, `chol`, `thalach`, `oldpeak`) using the Interquartile Range (IQR) method.
* **Categorical Encoding:** Applied One-Hot Encoding (`pd.get_dummies`) to categorical variables (`cp`, `restecg`, `slope`, `thal`).
* **Feature Scaling:** Applied `StandardScaler` to ensure all features contribute equally to distance-based algorithms and gradient descent optimization.

### 3. Exploratory Data Analysis (EDA)
* Visualized class distributions (No Disease vs. Heart Disease).
* Analyzed continuous features using histograms grouped by the target variable.
* Evaluated feature correlations using a heatmap to identify multicollinearity and top univariate predictors.

### 4. Feature Selection
* Employed a dual-method approach to prevent the "Curse of Dimensionality" and improve clinical interpretability:
    * **ANOVA F-test (`SelectKBest`):** To identify significant linear relationships.
    * **Random Forest Feature Importance:** To capture non-linear dependencies.
* Selected the **Top 10** most predictive features for final model training.

### 5. Model Development
* Split the dataset into 80% training and 20% testing sets (stratified to maintain class balance).
* Trained multiple baseline algorithms to compare performance:
    * Logistic Regression
    * Decision Tree
    * Random Forest
    * Gradient Boosting
    * Support Vector Machines (SVM)
    * K-Nearest Neighbors (KNN)

### 6. Model Optimization
* Utilized `GridSearchCV` with 5-fold cross-validation to fine-tune hyperparameters for the ensemble models (Random Forest and Gradient Boosting).
* Optimized parameters such as `n_estimators`, `max_depth`, `min_samples_split`, and `min_samples_leaf` based on the ROC-AUC scoring metric.

### 7. Model Evaluation
* Evaluated models beyond standard accuracy, focusing on clinical impact metrics.
* Generated Confusion Matrices to visualize False Positives vs. False Negatives.
* Plotted ROC Curves to assess the trade-off between True Positive Rate and False Positive Rate across different thresholds.

---

## Business Insights & Recommendations

### Key Predictors & Their Impact
1. **thalach (Max Heart Rate Achieved):** Lower maximum heart rate strongly predicts disease.
2. **oldpeak (ST Depression):** Higher ST depression indicates reduced blood flow.
3. **ca (Major Vessels Blocked):** More blocked vessels correlate with a significantly higher risk.
4. **cp (Chest Pain Type):** Asymptomatic chest pain is paradoxically a high-risk indicator in this cohort.
5. **age:** Cardiovascular risk rises sharply after age 50.

### Strategic Recommendations
1. **Triage Tool Implementation:** Deploy the model in clinics as a preliminary screening tool. Patients with a predicted probability > 0.6 should be fast-tracked for specialized cardiology referrals.
2. **Prioritize Key Tests:** Make measuring maximum heart rate (`thalach`) and ST-depression (`oldpeak`) mandatory in every routine check-up, as these are the two most predictive features.
3. **Age-Based Screening Campaigns:** Launch targeted heart-health awareness and screening campaigns specifically for the 50-70 age bracket, where the disease prevalence exceeds 55%.
4. **Adjust Clinical Thresholds:** In healthcare, missing a sick patient (False Negative) is far more dangerous than over-testing a healthy one (False Positive). Lowering the probability threshold from 0.5 to 0.4 prioritizes Recall and reduces missed diagnoses.
5. **Gender-Aware Protocols:** Since male patients showed higher prevalence in the dataset, establishing gender-specific thresholds may further improve precision in practical deployment.

