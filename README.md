# Mobile_Plan_Machine_Learning_S7

# Binary Classification of Mobile Plan Users

## Project Objective
The goal of this project is to build a machine learning model that classifies users into one of two categories:
- 'Ultra' plan users
- Non-'Ultra' plan users

The analysis includes:
1. Cleaning and preprocessing the dataset.
2. Training various classification models to identify the best-performing one.
3. Evaluating the chosen model on a test dataset.

---

## Dataset Overview
The dataset contains behavioral data about users' mobile usage, including:
- Number of calls made
- Total minutes of calls
- Number of messages sent
- Data usage (MB)
- Binary target variable `is_ultra`:
  - 1: 'Ultra' plan user
  - 0: Non-'Ultra' plan user

### Key Stats:
- **Rows**: 3,214
- **No Missing Data**
- **No Duplicates**
- **No Outliers**

---

## Project Workflow
### Step 1: Initial Data Analysis
- Checked for missing values (`isnull().sum()`), duplicates (`duplicated().sum()`), and data consistency.
- Confirmed the target variable is binary and well-distributed.

### Step 2: Data Splitting
- Split the dataset into training (80%) and test (20%) sets.
- Preprocessing:
  - Scaled numerical features using `StandardScaler` for linear models.
  - Skipped scaling for tree-based models.

### Step 3: Model Selection
Trained the following models:
1. **DecisionTreeClassifier**
   - Tuned `max_depth`, `min_samples_split`, and `min_samples_leaf`.
2. **RandomForestClassifier**
   - Tuned `n_estimators`, `max_depth`, and `min_samples_leaf`.
3. **LogisticRegression**
   - Tuned the regularization parameter `C`.

Hyperparameter tuning was conducted using **GridSearchCV** with cross-validation.

---

## Model Evaluation
### Metrics:
- **Accuracy** (primary metric for model selection).
- Cross-validation scores guided hyperparameter selection.

### Best Model:
The **RandomForestClassifier** achieved the highest validation and test accuracy.
Tuned Hyperparameters:
- `n_estimators=100`
- `max_depth=8`
- `min_samples_leaf=3`

**Test Accuracy:** **0.85**

---

## Future Improvements
1. Collect more diverse data to improve model generalization.
2. Engineer additional features to capture more behavioral patterns.
3. Experiment with ensemble stacking or boosting methods for further accuracy gains.

---

## Conclusion
The RandomForestClassifier successfully classifies mobile users with high accuracy.
This model can help mobile operators predict user behavior, personalize marketing efforts, and optimize operational strategies.

---

## Dependencies
- Python 3.x
- scikit-learn
- pandas
- numpy
- matplotlib
"""
