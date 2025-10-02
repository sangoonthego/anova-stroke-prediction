# 🧠 Stroke Prediction Project  

## 🎉 Author
- Name: Nguyen Tuan Ngoc

## 📌 Introduction  
This project aims to build a model that predicts the risk of stroke based on demographic information and health indicators such as age, BMI, average glucose level, smoking status, heart disease, and hypertension.  

Main objectives:  
- Explore the relationship between health variables and stroke risk.  
- Build a predictive model to support healthcare professionals in risk assessment.  
- Ensure **model interpretability (explainability)** for practical application.  

---

## 📊 Data & Preprocessing  
- The original dataset is **highly imbalanced** (stroke cases ~4%).  
- Missing BMI values handled using **mean imputation** and **KNN imputation**.  
- Standardized numeric features and one-hot encoded categorical variables.  

---

## ⚙️ Models & Results  

### 🔹 Logistic Regression (class_weight='balanced')  
- **ROC-AUC (CV):** ~0.84 ± 0.01  
- **PR-AUC (CV):** ~0.19 ± 0.02  
- Advantages: Highly interpretable, effective on imbalanced data.  

### 🔹 Random Forest / XGBoost (default settings)  
- **ROC-AUC:** ~0.80 and ~0.75  
- **PR-AUC:** ~0.13 and ~0.12  
- Lower performance compared to Logistic Regression (not hyperparameter tuned yet).  

---

## 🔍 Interaction Analysis  
- **Age × Hypertension:** Older individuals with hypertension face the highest risk.  
- **BMI × Smoking Status:** Weak, not clearly separable.  
- **Avg Glucose Level × Hypertension:** Strong effect → high glucose combined with hypertension greatly increases stroke risk.  

---

## 📈 Model Explainability  
Using **SHAP values**, the most important features are:  
1. Age  
2. Average Glucose Level  
3. Hypertension  

---

## ✅ Conclusion  
- **Logistic Regression (with class_weight)** is the best-performing model so far.  
- Confirmed that **older age, hypertension, and high glucose** are the main stroke risk factors.  
- The **glucose × hypertension** interaction plays a significant role, aligning with clinical knowledge.  

---

## 🚀 Next Steps  
- Hyperparameter tuning for **RandomForest** and **XGBoost**.  
- Try advanced oversampling techniques (SMOTE-NC, ADASYN).  
- Deploy as a **risk scoring tool** to support healthcare professionals.  

---

## 📦 Installation  
Clone the repository and install dependencies:  

```bash
git clone https://github.com/sangoonthego/welch-ttest-stroke-prediction.git
cd stroke-prediction
pip install -r requirements.txt
