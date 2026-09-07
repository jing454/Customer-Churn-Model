## 1. Load and understand the data

Use the raw file in `Data/` and inspect its rows, columns, data types, missing values, duplicate records, and category values. Identify `churn` as the target. Keep `customer_id` only to identify customers; do not use it to fit the model.

## 2. Clean the data

Complete this in `Notebooks/Data_clean.ipynb`.

1. Remove duplicates, if there are any.
2. Correct column data types.
3. Handle missing values.
4. Check for impossible values, such as negative tenure or charges.
5. Standardize category names, so labels such as `Yes`, `yes`, and `YES` are not treated as different values.
6. Save the cleaned data to `Cleaned_Data/Cleaned_Churn.csv`.

## 3. Explore the data with graphs

Complete this in `Notebooks/Graph.ipynb`.

1. Make a bar chart showing the number or percentage of customers who churned.
2. Make churn-rate bar charts for `contract`, `payment_method`, and `internet_service`.
3. Compare churn rates for customers with and without `tech_support` and `online_security`.
4. Use box plots or histograms to compare `tenure`, `monthly_charges`, `total_charges`, and `support_calls` for churners versus non-churners.
5. Check graphs for unusual values, skewed distributions, and outliers.
6. Write down the most important findings.

## 4. Prepare the data for the model

Complete this in `Notebooks/Training.ipynb`.

1. Convert `churn` from `Yes`/`No` into a binary target.
2. Remove `customer_id` from the model features.
3. Keep numeric features: `tenure`, `monthly_charges`, `total_charges`, and `support_calls`.
4. Convert categorical features—`contract`, `payment_method`, `internet_service`, `tech_support`, and `online_security`—into a numeric format the model can use.
5. Scale numeric features if the model needs it, such as logistic regression.
6. Split the data into training and test sets, preserving approximately the same churn percentage in both sets.

## 5. Fit models

Start with a simple model and then compare it with a stronger model.

1. Fit logistic regression as the baseline.
2. Fit a tree-based model, such as a decision tree, random forest, or gradient boosting model.
3. Use a validation split or cross-validation on the training data to compare models and settings.
4. Do not use the test set to choose the best model.

## 6. Evaluate the model

Test the selected final model on the unseen test data. Review:

1. Accuracy.
2. Confusion matrix.
3. Precision for churn.
4. Recall for churn.
5. F1 score.
6. ROC-AUC.

For churn, focus particularly on recall (how many real churners the model finds) and precision (how often a predicted churner really churns). Accuracy by itself can be misleading because non-churners are more common.

## 7. Select a churn threshold

The model gives each customer a churn probability. Choose the probability cutoff that marks a customer as high risk.

1. Compare several cutoffs.
2. At each cutoff, review the number of customers contacted, churners captured, precision, and recall.
3. Pick a cutoff that matches the capacity and cost of the retention campaign.

## 8. Interpret the results

Identify which features most influence churn predictions. Compare them with your graphs. Review contract type, tenure, monthly charges, support calls, tech support, and online security. Treat these patterns as associations, not proof of cause.

## 9. Create final predictions

Create a customer-level results table containing:

1. `customer_id`.
2. Churn probability.
3. Predicted churn label (`Yes` or `No`) based on the chosen threshold.
4. Optional risk level: high, medium, or low.

Use the high-risk customer list for retention actions.

## 10. Summarize the project

Record the data-cleaning choices, important graphs, models compared, final metrics, selected threshold, main churn drivers, and recommended retention actions.
