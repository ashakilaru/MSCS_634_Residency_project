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
