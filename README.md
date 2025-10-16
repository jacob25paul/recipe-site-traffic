# 🍽️ Recipe Site Traffic Prediction

This project was completed as part of the **Data Science Professional Certification**.  
The goal is to **predict which recipes will drive high site traffic**, helping content teams prioritize what to feature on the homepage.

---

## 📊 Project Overview

This project analyzes recipe data (calories, nutrients, category, and servings) to determine the likelihood of a recipe generating high website traffic.  
We performed data validation, exploratory analysis, and model comparison between **Logistic Regression** and **Random Forest** to identify the best-performing classifier.

---

## 📁 Repository Structure

recipe-site-traffic/
│
├── data/ # Dataset (recipe_site_traffic_2212.csv)
├── notebooks/ # Jupyter Notebook: DSP_Recipe_Traffic.ipynb
├── docs/ # Report & Presentation
│ ├── Practical_DSP_Recipe_Site_Traffic.pdf
│ └── Recipe_Site_Traffic_Presentation_JacobPaul.pptx
├── DSP_Recipe_Traffic.html # HTML export of the notebook
├── README.md # Project overview (this file)
└── requirements.txt # (Optional) Dependencies

yaml
Copy code

---

## 🧹 1. Data Validation & Cleaning

- Verified column types and handled missing values (e.g., `calories`, `protein`, `high_traffic`).
- Ensured valid ranges (no negative servings or nutrient values).
- Confirmed uniqueness of `recipe` IDs.
- Encoded categorical variables and standardized numerical features.

---

## 📈 2. Exploratory Data Analysis

### Single-Variable Insights
- **Distribution of Calories:** Right-skewed; most recipes under 500 calories.
- **Recipe Count by Category:** Breakfast and Chicken recipes appear most frequently.

### Multi-Variable Insights
- **Calories vs Protein by Traffic Level:** No strong linear correlation, but higher-protein, moderate-calorie meals tend to have higher traffic.

| Example Visuals |
|-----------------|  
| ![Calories Distribution](docs/images/calories_dist.png) |
| ![Recipe Categories](docs/images/category_count.png) |
| ![Calories vs Protein](docs/images/calories_vs_protein.png) |

---

## 🤖 3. Model Development

Two models were compared:
- **Baseline:** Logistic Regression
- **Comparison:** Random Forest

Data was processed through a Scikit-Learn `Pipeline` with:
- One-Hot Encoding for categorical data  
- StandardScaler for numeric features  
- Train/test split: 80/20

---

## 📏 4. Model Evaluation

Evaluated using **Precision-Recall curves** with `average_precision_score`.

| Model | Average Precision (AP) | Recall@Threshold |
|--------|-------------------------|------------------|
| Logistic Regression | 0.907 | 0.847 |
| Random Forest | 0.877 | 0.823 |

→ **Best Model:** Logistic Regression (higher precision and overall AP)

![Precision Recall Curves](docs/images/precision_recall.png)

---

## 💼 5. Business Metric

**Goal:** Optimize for precision at a chosen decision threshold.  
The content manager wants to minimize showing unpopular recipes (false positives).  
- **Primary Metric:** Precision for “High” traffic  
- **Secondary Metric:** Recall at threshold

---

## 🧠 6. Final Summary & Recommendations

**Problem:**  
Predict high-traffic recipes to drive homepage engagement while avoiding unpopular ones.

**Approach:**  
Validated data, explored feature relationships, and trained Logistic Regression and Random Forest models using a consistent pipeline.

**Metric:**  
Precision for “High” recipes, targeting ~0.80, with recall tracked secondarily.

**Result:**  
Best model = Logistic Regression with Precision = 0.803 and Recall = 0.847.

**Recommendation:**  
Deploy Logistic Regression behind a decision threshold targeting 0.80 precision.  
If traffic volume is low, accumulate scores and only feature recipes exceeding this threshold.

---

## 🧩 Technologies Used

- Python 3.x  
- pandas, numpy  
- scikit-learn  
- matplotlib, seaborn  
- Jupyter Notebook

---

## 👤 Author

**Jacob Paul**  
📧 jacob25paul@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/jacob25paul)

---

## 🗂️ License

This project is for educational and portfolio purposes as part of the **DataCamp Data Scientist Professional Certification**.
