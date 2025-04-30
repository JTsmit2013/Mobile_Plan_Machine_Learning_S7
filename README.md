# Mobile_Plan_Machine_Learning_S7

## Binary Classification of Mobile Plan Users

### 📌 Project Objective
Build a machine learning model to classify users into two categories:
- **'Ultra' plan users**
- **Non-'Ultra' plan users**

The project includes:
- Data cleaning and preprocessing
- Training and evaluating multiple classification models
- Selecting the best-performing model using accuracy as the primary metric

---

### 📊 Dataset Overview
- **Rows:** 3,214
- **Target Variable:** `is_ultra`  
  - `1`: Ultra user  
  - `0`: Non-ultra user
- **Features Include:**
  - Number of calls
  - Total minutes
  - Messages sent
  - Data usage (MB)
- **No missing data, duplicates, or outliers**

---

### 🔄 Workflow Summary

#### 1. Data Analysis
- Verified no missing/duplicate values
- Confirmed target distribution and binary nature

#### 2. Data Splitting & Preprocessing
- Train/test split: 80/20
- **Scaling:**  
  - Applied `StandardScaler` to linear models  
  - Skipped for tree-based models

#### 3. Model Training & Tuning
- **DecisionTreeClassifier**  
  - Tuned `max_depth`, `min_samples_split`, `min_samples_leaf`
- **RandomForestClassifier**  
  - Tuned `n_estimators`, `max_depth`, `min_samples_leaf`
- **LogisticRegression**  
  - Tuned regularization parameter `C`

Used `GridSearchCV` and cross-validation for tuning.

---

### ✅ Best Model: RandomForestClassifier
- **Hyperparameters:**
  - `n_estimators = 100`
  - `max_depth = 8`
  - `min_samples_leaf = 3`
- **Test Accuracy:** 0.85

---

### 🚀 Future Improvements
- Collect more diverse or updated user data
- Engineer new features capturing deeper user behavior
- Explore stacking or boosting techniques for higher accuracy

---

### 🔧 Dependencies
- Python 3.x
- `scikit-learn`
- `pandas`
- `numpy`
- `matplotlib`

---

### 📌 Conclusion
The tuned RandomForest model effectively classifies users by mobile plan type, enabling telecom providers to improve targeting, retention strategies, and resource allocation.
