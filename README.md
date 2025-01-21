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
The dataset contains behavioral data about users' mobile usage, such as:
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
- Check for missing values, duplicates, and data consistency.
- Confirm target variable is binary and well-balanced.

### Step 2: Data Splitting
- Split the dataset into training (80%) and test (20%) sets.
- Preprocessing:
  - Scale numerical features using `StandardScaler` for linear models.
  - Skip scaling for tree-based models.

### Step 3: Model Selection
Train the following models:
1. **DecisionTreeClassifier**
   - Investigate parameters: `max_depth`, `min_samples_split`, and `min_samples_leaf`.
2. **RandomForestClassifier**
   - Investigate parameters: `n_estimators`, `max_depth`, and `min_samples_leaf`.
3. **LogisticRegression**
   - Investigate parameter: `C` (inverse of regularization strength).

---

## Model Evaluation
### Metrics:
- Accuracy (primary metric for model selection).
- Cross-validation used for hyperparameter tuning.

### Best Model:
The RandomForestClassifier provided the highest accuracy on validation data. The tuned hyperparameters are:
- `n_estimators=100`
- `max_depth=8`
- `min_samples_leaf=3`

Test Accuracy: **0.85**

---

## Future Improvements
1. Collect more data to reduce potential overfitting in the models.
2. Explore additional features for richer behavioral insights.
3. Experiment with ensemble techniques for further accuracy improvements.

---

## Conclusion
The RandomForestClassifier successfully classifies users with high accuracy. This model can be deployed to help mobile operators predict user behavior and optimize their marketing and operational strategies.
