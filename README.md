# Credit Risk Scoring Model

### Overview

Credit risk scoring is essential for financial institutions to assess the likelihood of a borrower defaulting on credit obligations. This project uses a dataset with client financial and behavioral data to predict whether a client is likely to face serious delinquency. The predictive model provides actionable insights for lenders to manage risk, allocate resources, and set credit policies.

### Dataset

The "Give Me Some Credit" dataset includes features like revolving utilization, debt ratio, monthly income, and more, with the target variable indicating serious delinquency within two years.

Source: Kaggle - Give Me Some Credit

Files Included:

- cs-training.csv: Training data with labeled outcomes
- cs-test.csv: Test data without labels (for challenge submission)
- Data Dictionary.xls: Dictionary describing the dataset variables
- sampleEntry.csv: Sample format for challenge submissions

### Project Workflow

1. Data Preprocessing:
    - Loaded and inspected data for missing values and outliers.
    - Imputed missing values using median for MonthlyIncome and zero for NumberOfDependents.
    - Standardized numerical features using StandardScaler.

2. Exploratory Data Analysis:
   - Examined data distributions, correlations, and potential predictive relationships.
   - Assessed the impact of class imbalance between "safe" and "risky" clients.

4. Model Training:
   - Built a Random Forest Classifier to predict the probability of serious delinquency.
   - Tuned hyperparameters using Grid Search for optimal performance.

6. Model Evaluation:
   - Evaluated accuracy, AUC-ROC score, and classification report (precision, recall, and F1-score).
   - Analyzed model performance on imbalanced data, with a focus on capturing high-risk clients.

### Model Performance

The model achieved the following results on the validation set:

- Accuracy: 93.92%
- AUC-ROC Score: 0.8630
- Classification Report:
      - Precision for high-risk clients: 61%
      - Recall for high-risk clients: 18%
      - F1 Score for high-risk clients: 28%

These results indicate strong overall performance but highlight the challenges of identifying high-risk clients due to class imbalance.

### Key Findings

Model Strengths:
- High accuracy and AUC-ROC score indicate the model reliably differentiates between safe and risky clients.
- Effective at identifying safe clients, minimizing false positives in lending decisions.

### Challenges:
- Class Imbalance: Low recall for high-risk clients reflects the class imbalance, as the model tends to predict more safe clients.
- Recall Improvements Needed: For real-world applications, capturing more high-risk clients is crucial to avoid potential defaults.

### Future Improvements

To enhance the model’s ability to identify high-risk clients, consider:

- Balancing the Dataset: Implement oversampling (e.g., SMOTE) or undersampling techniques to address class imbalance.
- Ensemble Learning: Use ensemble methods, like Gradient Boosting or XGBoost, to improve recall for high-risk clients.
- Cost-Sensitive Learning: Assign higher misclassification costs for risky clients to encourage the model to prioritize recall.

### Source
[
Thank you to Kaggle for providing this dataset. This project demonstrates how credit risk modeling can aid financial institutions in managing risk and optimizing credit policies effectively.](https://www.kaggle.com/datasets/brycecf/give-me-some-credit-dataset)
