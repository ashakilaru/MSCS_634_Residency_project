# MSCS_634_ProjectDeliverable_4

## Project Overview

This repository contains the final phase of my Medicare Part B Drug Spending analysis project. Rather than introducing new models, this deliverable brings together the work completed throughout the previous phases and summarizes the insights gained from applying multiple data mining techniques to the same healthcare dataset. Looking at the problem through different analytical approaches made it possible to understand not only which models performed well, but also why different techniques highlighted different aspects of Medicare spending.

---

## Dataset

The analysis uses the CMS Medicare Quarterly Part B Drug Spending dataset, which contains information on beneficiary counts, claim volume, total spending, average spending per beneficiary, and average spending per claim. I selected this dataset because it represents a realistic healthcare scenario where spending is influenced by several related factors instead of a single variable. It also provided enough variation to compare regression, classification, clustering, and association rule mining within one consistent analytical workflow.

---

## Project Steps

The project was completed in four phases. The first phase focused on preparing the dataset through cleaning, exploratory data analysis, visualization, and feature engineering. This stage helped identify data quality issues and better understand the relationships among the variables before building predictive models.

The second phase concentrated on regression analysis to estimate Medicare spending. Comparing different regression models demonstrated how regularization affected prediction performance and model stability.

The third phase expanded the analysis by applying classification, clustering, and association rule mining. Instead of asking a single question about the data, these techniques examined the problem from multiple perspectives by identifying high-spending drugs, grouping similar utilization patterns, and uncovering relationships among key healthcare variables.

This final phase consolidates the complete workflow, interprets the results across all analytical methods, and summarizes the practical insights gained throughout the project.

---

## Major Findings

One observation that became clear during the analysis was that no single technique provided a complete understanding of the dataset. Regression models explained spending trends; classification models helped distinguish high-spending drugs; clustering revealed groups with similar utilization behavior; and association rule mining uncovered patterns not immediately visible through prediction alone.

The project also reinforced the importance of careful data preparation. Decisions made during cleaning, feature engineering, and exploratory analysis influenced every model that followed, making those early stages just as important as the modeling itself. Bringing the results together showed how different analytical methods complement one another when applied to a real healthcare dataset rather than serving as isolated machine learning exercises.
