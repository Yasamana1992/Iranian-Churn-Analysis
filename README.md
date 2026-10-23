# Customer Churn Analysis and Prediction

## Project Overview

This project analyzes customer churn in a telecommunications dataset and compares machine learning models to identify customers who are at risk of leaving the service.

The goal is to explore customer behavior, evaluate predictive performance, and develop data-driven recommendations that could support customer retention strategies.

## Dataset

The project uses the Iranian Churn Dataset from the UCI Machine Learning Repository.

- Source: "UCI Machine Learning Repository — Iranian Churn Dataset" (https://archive.ics.uci.edu/dataset/563/iranian+churn+dataset)
- Number of records: 3,150 customers
- Input features: 13
- Target variable: "Churn"
  - "1": Customer churned
  - "0": Customer did not churn

The features describe customer activity during the first nine months, while churn is measured at the end of month 12.

The dataset is associated with a single Iranian telecommunications company, so the findings may not generalize to other providers or markets.

License: CC BY 4.0
DOI: "10.24432/C5JW3Z" (https://doi.org/10.24432/C5JW3Z)

## Tools and Libraries

- Python
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Methodology

1. Inspected the dataset structure, data types, missing values, and descriptive statistics.
2. Explored churn rates and customer behavior across selected features.
3. Analyzed correlations between selected variables and churn.
4. Split the data into training and testing sets using stratified sampling.
5. Compared six classification models using stratified 5-fold cross-validation:
   - Logistic Regression
   - Decision Tree
   - Random Forest
   - Gaussian Naive Bayes
   - K-Nearest Neighbors (KNN)
   - Support Vector Machine (SVM)
6. Compared Random Forest performance across three feature sets.
7. Examined feature importance and evaluated the selected model using a confusion matrix and classification report.

## Key Findings

- The dataset's churn rate is approximately 15.71%.
- Lower call usage and lower customer value were associated with higher churn in the exploratory analysis.
- "Seconds of Use" and "Frequency of use" showed a strong positive correlation.
- Random Forest achieved the best overall F1-score among the evaluated models in the recorded cross-validation results.
- Retaining all 13 features outperformed the two tested feature-removal alternatives.

## Model Evaluation

On the current test split, the selected Random Forest model achieved:

Metric for the churn class| Result
Precision| 89%
Recall| 86%
F1-score| 88%
Overall accuracy| 96%

The model identified 85 of the 99 customers who churned, missed 14 churned customers, and incorrectly flagged 10 customers who did not churn.

Evaluation caveat: The test set was consulted during earlier feature-selection experiments. Therefore, these test results should not be treated as a fully independent estimate of generalization performance.

## Business Recommendations

A telecommunications company could use churn-risk predictions to prioritize customer retention efforts.

Potential actions include:

- Offering personalized support to customers with high predicted churn risk.
- Considering customer value and intervention costs when prioritizing retention campaigns.
- Measuring campaign outcomes to determine whether interventions actually reduce churn and generate positive financial returns.

These are proposed applications; the project does not establish that any specific retention intervention will prevent churn.

## Limitations

- The dataset represents a single telecommunications company.
- Correlations and feature importance do not establish causal relationships.
- The model has not been validated through a real-world retention campaign.
- A more rigorous evaluation using an untouched holdout set is needed.
- Hyperparameter and prediction-threshold optimization have not been fully explored.

## How to Run

1. Clone or download this repository.
2. Install the required Python libraries.
3. Obtain the dataset from the "UCI Machine Learning Repository" (https://archive.ics.uci.edu/dataset/563/iranian+churn+dataset) and place the CSV file at "data/Customer_Churn.csv".
4. Open "01_data_audit.ipynb" in Jupyter Notebook or VS Code.
5. Run the notebook cells in order.

## License and Attribution

The dataset is distributed under the CC BY 4.0 license. Please consult the original dataset page for attribution and reuse requirements.

Dataset citation:
"UCI Machine Learning Repository — Iranian Churn Dataset" (https://doi.org/10.24432/C5JW3Z)