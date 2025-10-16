# 🍳 Recipe Site Traffic Prediction

**Author:** Jacob Paul  
**Certification:** DataCamp – Data Scientist Professional Practical Exam  
**Project Type:** Supervised Machine Learning (Classification)  

---

## 📖 Overview

This project predicts whether a recipe will generate **high site traffic** based on its nutritional and categorical features.  
It demonstrates the complete data science workflow — from validation and EDA to model selection, evaluation, and business recommendations.

---

## 🧩 Dataset

- **File:** `data/raw/recipe_site_traffic_2212.csv`
- **Records:** 947  
- **Columns:**
  - `recipe`: Recipe ID  
  - `calories`, `carbohydrate`, `sugar`, `protein`: Nutritional attributes  
  - `category`: Recipe type (Breakfast, Beverages, Meat, etc.)  
  - `servings`: Number of servings  
  - `high_traffic`: Target variable (High/Low)

---

## ⚙️ Project Workflow

### **1. Data Validation**
- Cleaned inconsistent entries and removed extra RTF markup.
- Converted numerical columns to `float64` and categorical columns to `category`.
- Median-imputed missing numeric values.
- Verified column ranges and ensured no duplicates.

### **2. Exploratory Data Analysis (EDA)**
- **Univariate Analysis:**  
  - Right-skewed calorie distribution.
  - Beverages and Breakfast most frequent categories.  
- **Multivariate Analysis:**  
  - Higher calories and protein → more likely high-traffic recipes.
- Included visualizations for calorie distribution, category counts, and scatterplots.

### **3. Model Development**
- Binary classification problem: Predicting `high_traffic`.
- Compared:
  - Logistic Regression (baseline)
  - Random Forest (comparison)
- Implemented data pipelines with scaling and encoding using `ColumnTransformer`.

### **4. Model Evaluation**
| Model | Precision | Recall | ROC-AUC |
|--------|------------|--------|---------|
| Logistic Regression | 0.803 | 0.847 | 0.90 |
| Random Forest | 0.775 | 0.802 | 0.88 |

**Selected Model:** Logistic Regression  
**Decision Threshold:** 0.311 (Precision ≈ 0.80 target)

### **5. Business Metric**
- **Key Metric:** Precision (minimize false positives)
- Average precision: **0.907**
- Recall maintained above **0.84**, providing a balanced recommendation strategy.

### **6. Recommendations**
- Highlight high-protein, high-calorie recipes for homepage features.
- Prioritize “Meat” and “One Dish Meal” categories.
- Retrain model quarterly to capture evolving preferences.
- Add engagement and cost/time features for future iterations.

---

## 📊 Results Summary
- **Best Model:** Logistic Regression  
- **Precision:** 0.803  
- **Recall:** 0.847  
- **AUC:** 0.90  
- **Business Value:** Improves homepage engagement by promoting truly popular recipes while avoiding low-traffic ones.

---

## 📁 Repository Structure

