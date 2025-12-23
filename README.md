
# 📘 Student Performance Prediction using Machine Learning

## 📌 Project Overview

This project focuses on **analyzing student behavioral and academic data** to predict their **performance level** (`Low`, `Medium`, `High`).
Using **Exploratory Data Analysis (EDA)** and multiple **classification algorithms**, we identify the most influential factors affecting student outcomes and build robust predictive models.

Dataset used: **xAPI-Edu-Data.csv**

---

## 🎯 Objectives

* Perform **data cleaning & feature selection**
* Conduct **EDA** to understand student behavior patterns
* Build and compare **multiple ML classification models**
* Address **overfitting** using hyperparameter tuning
* Identify **key factors influencing student performance**

---

## 🗂️ Dataset Description

The dataset contains:

* **Demographics:** Gender, Nationality, Relation
* **Academic attributes:** StageID, GradeID, Topic
* **Behavioral metrics:** RaisedHands, VisitedResources, AnnouncementsView, Discussion
* **Target Variable:**

  * `Class` → Student performance

    * `L` = Low
    * `M` = Medium
    * `H` = High

---

## 🧹 Data Preprocessing Steps

### 1️⃣ Initial Exploration

* Checked:

  * Data types
  * Null values (No missing data found)
  * Unique values for each column
* Generated descriptive statistics

---

### 2️⃣ Feature Engineering & Selection

* Added a dummy `Institute` column to demonstrate **singularity handling**
* Dropped features based on:

  * **Singularity:** `Institute`
  * **Domain knowledge:** `SectionID`, `Semester`
  * **High cardinality:** `Topic`

✔️ Result: Reduced dimensionality and improved model generalization

---

### 3️⃣ Encoding

* Applied **Label Encoding** to categorical variables
* Used **manual ordinal encoding** for target variable:

```text
L → 0 | M → 1 | H → 2
```

---

### 4️⃣ Feature Scaling

* Applied **StandardScaler** to normalize numerical features
* Ensures fair contribution of all variables to ML models

---

## 📊 Exploratory Data Analysis (EDA)

### 🔹 Numerical Analysis

* Histograms revealed:

  * High engagement in **VisitedResources**
  * Lower participation in **AnnouncementsView** and **Discussion**
  * Moderate activity in **RaisedHands**

### 🔹 Pair Plots

* High and Low performers are **clearly separable**
* Medium performers are **scattered**, overlapping both extremes

### 🔹 Categorical Insights

* **Gender:**

  * Male students are more in number
  * Female students show **higher proportion of high performers**
* **Absenteeism:**

  * Students absent **< 7 days** are significantly more successful
* **Parental involvement & satisfaction** impact outcomes noticeably

---

## 🤖 Machine Learning Models Used

### 1️⃣ Logistic Regression

* Baseline multi-class classifier
* Good interpretability
* Moderate accuracy

📌 Observations:

* Works well for linear decision boundaries
* Limited performance for complex patterns

---

### 2️⃣ Decision Tree Classifier

* Captures non-linear relationships
* Initial model showed **overfitting**

  * High training accuracy
  * Lower test accuracy

#### 🔧 Overfitting Control:

Applied:

* `max_depth`
* `min_samples_leaf`

✔️ Result:

* Balanced training & test performance
* Improved generalization

---

### 3️⃣ Random Forest Classifier

* Ensemble of decision trees
* Reduced variance and overfitting
* Higher accuracy than single tree

---

### 4️⃣ Hyperparameter Tuning

Used **RandomizedSearchCV** to optimize:

* `n_estimators`
* `max_depth`
* `min_samples_leaf`

✔️ Result:

* Best performing model
* Improved cross-validation score
* Strong generalization on unseen data

---

## 📈 Model Evaluation Metrics

* **Confusion Matrix**
* **Accuracy Score**
* **Precision, Recall, F1-Score**
* **Train vs Test Accuracy comparison**

Heatmaps were used for intuitive visualization of classification performance.

---

## 🔍 Feature Importance Analysis

* Decision Tree & Random Forest identified:

  * `VisitedResources`
  * `RaisedHands`
  * `AnnouncementsView`
  * `Discussion`

as the **most influential features** in predicting performance.

---

## 🧪 Final Optimized Model Performance

| Model                 | Test Accuracy |
| --------------------- | ------------- |
| Logistic Regression   | Moderate      |
| Decision Tree (Tuned) | High          |
| Random Forest (Tuned) | **Highest** ✅ |

---

## 🏁 Conclusion

* **Student engagement metrics** are stronger predictors than demographics
* Absenteeism is a **critical risk indicator**
* Ensemble models outperform individual classifiers
* Proper feature selection & tuning significantly improve accuracy

---

## 🚀 Future Enhancements

* Apply **XGBoost / LightGBM**
* Perform **SMOTE** for class imbalance
* Deploy model using **Flask / Streamlit**
* Add explainability using **SHAP values**

---

## 🛠️ Tech Stack

* **Python**
* **Pandas, NumPy**
* **Matplotlib, Seaborn**
* **Scikit-Learn**

---


