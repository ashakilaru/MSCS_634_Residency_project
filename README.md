# MSCS 634 Project Deliverable 1

**Authors:** Asha Kilaru and Venkatappareddy Monukonda

## Dataset Summary
This project uses a CMS healthcare dataset from the CMS Data API. The dataset contains 1,000 records and 10 attributes related to healthcare products, including brand name, generic name, HCPCS code, description, year, total beneficiaries, total claims, total spending, average spending per beneficiary, and average spending per claim.

## Why This Dataset Is Appropriate
The dataset is appropriate for this project because it:
- contains more than 500 records,
- includes both categorical and numerical variables,
- supports exploration of relationships between claims, spending, and healthcare product categories,
- provides a strong foundation for future regression, classification, clustering, and association-rule work.

## Why This Dataset Was Chosen
This dataset was selected because it represents a practical healthcare analytics problem that combines financial and utilization information in a structured and interpretable format. It reflects real-world Medicare Part B drug spending behavior and provides multiple quantitative variables that are well suited for data mining techniques such as regression, classification, clustering, and association rule mining.

Because I work in the healthcare industry, this dataset is especially meaningful to me. It allows me to explore how beneficiary counts, claim volumes, and spending measures interact in a way that connects directly to healthcare operations, reimbursement planning, and cost monitoring. The project is therefore not only a technical exercise, but also a way to apply data-driven analysis to issues that are relevant in real healthcare decision-making.

## Major Steps Taken
1. Loaded the dataset directly from the CMS API using Python.
2. Inspected the structure, data types, and missing values.
3. Cleaned the dataset by converting numeric fields, removing duplicates, filling missing values, and extracting a year feature.
4. Performed exploratory data analysis with visualizations for spending distribution, spending by generic name, claims vs. spending, and spending over time.

## Key Insights
- The dataset contains a strong positive relationship between total claims and total spending.
- Total spending is highly skewed, suggesting that a small number of records may contribute disproportionately to total cost.
- Some generic healthcare categories appear to account for a large share of spending.

## Challenges and How They Were Addressed
- Some columns contained missing values, which were handled by filling numeric values with medians and categorical values with placeholders.
- The Year column had mixed formats, so a cleaning function was used to extract a consistent numeric year.
- The spending variable showed possible outliers, which were identified using the IQR method for awareness during analysis.

## Files Included
- MSCS_634_ProjectDeliverable_1.ipynb: main notebook with code, comments, and visualizations
- cms_healthcare_claims_cleaned.csv: cleaned dataset exported for reuse

## Day 2 Continuation
## MSCS_634_ProjectDeliverable_2
Regression Modeling and Performance Evaluation
## Dataset and Modeling Process
This deliverable continues the analysis using the cleaned CMS Medicare Quarterly Part B Spending by Drug dataset prepared in Deliverable 1. To improve prediction performance, I created additional features that describe utilization patterns, including claims per beneficiary, reporting year, reporting quarter, log-transformed claim counts, log-transformed beneficiary counts, and frequency-based features for brand and generic drug names.

After preparing the data, I split it into training and testing sets and applied preprocessing using median imputation, feature scaling, and one-hot encoding. Two regression models were then developed and compared: Linear Regression and Ridge Regression.

## Evaluation Results
Model performance was evaluated using Test R-squared (R²), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and five-fold cross-validation. The notebook also includes actual versus predicted plots, residual analysis, and model comparison charts to visualize prediction performance.

Ridge Regression produced the strongest overall results by achieving the highest R² while generating more stable predictions than the standard Linear Regression model.

## Key Insights
The comparison showed that feature engineering improved the ability of the models to capture Medicare spending patterns. Regularization also proved beneficial because it reduced the effect of correlated predictors and produced more consistent predictions. Although spending remained difficult to predict due to the large variation between drugs, Ridge Regression provided the best balance between prediction accuracy and model stability.

## Challenges
The greatest challenge during modeling was the highly skewed distribution of Medicare spending. A relatively small number of drugs account for exceptionally large expenditures, making prediction more difficult. Rather than removing these observations, I preserved them and relied on preprocessing, feature engineering, and Ridge Regression to improve model stability while maintaining the original characteristics of the data.

## Day 3 Deliverable: Classification, Clustering, and Pattern Mining
## MSCS_634_ProjectDeliverable_3
## Purpose
The purpose of this deliverable was to explore the CMS Medicare Quarterly Part B Spending by Drug dataset using multiple data mining techniques rather than relying on a single predictive model. We applied classification, clustering, and association rule mining to understand the data from different perspectives. This approach allowed us to identify high-spending drugs, discover natural groups with similar utilization patterns, and uncover relationships among spending and beneficiary characteristics.

## What We Did
We began by loading the cleaned dataset from Deliverable 1 and creating a binary target variable that identified high-spending records based on the 75th percentile of total Medicare spending. Additional features, including the reporting year, quarter, and claims per beneficiary, were created to improve the predictive models while avoiding target leakage.

For the classification task, we compared four machine learning algorithms: Decision Tree, K-Nearest Neighbors, Naive Bayes, and Support Vector Machine. Each model was trained using the same preprocessing pipeline that handled missing values, standardized numerical features, and encoded categorical variables. Model performance was evaluated using accuracy, precision, recall, and F1 score before selecting the best-performing classifier.

The selected model was then examined using a confusion matrix and ROC curve to understand better its ability to distinguish between regular- and high-spending records.

For unsupervised learning, we applied K-Means clustering using spending and utilization variables. Cluster quality was evaluated with the silhouette score, and Principal Component Analysis (PCA) was used to visualize the resulting clusters in two dimensions.

Finally, association rule mining was performed using the Apriori algorithm after transforming selected numerical variables into categorical indicators. Frequent itemsets and association rules were analyzed using support, confidence, and lift to identify meaningful relationships within the Medicare spending data.

## Key Results
Among the classification models, Naive Bayes achieved the highest F1 score and was selected as the final classifier. Although its overall accuracy was moderate, it was the most effective model for identifying high-spending records.

K-Means clustering produced three distinct groups with a silhouette score of approximately 0.663, indicating reasonably well-separated clusters. Most observations belonged to one large cluster, while two much smaller clusters represented drugs with noticeably different spending and utilization behavior.

Association rule mining identified several strong relationships among beneficiaries, claims, and spending measures. The highest lift values showed that drugs with a large number of beneficiaries were also likely to generate a high number of claims and higher average spending per beneficiary.

What We Learned
This deliverable demonstrated that different data mining techniques provide complementary insights when applied to the same dataset. Classification helped identify records associated with high Medicare spending, clustering revealed hidden utilization patterns, and association rule mining highlighted relationships that were not immediately visible through predictive modeling alone. Combining these techniques produced a more complete understanding of Medicare drug utilization and spending behavior than any individual method could provide by itself.
