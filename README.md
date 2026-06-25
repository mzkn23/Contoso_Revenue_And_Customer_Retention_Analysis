# Contoso Revenue and Customer Retention Analysis


## Overview

Analysis of an e-commerce company's customer behaviour, retention, lifetime value with the intention to enhance customer retention and revenue.

## Business Questions

1. **Customer segmentation:** Who are the most valuable customers?
2. **Cohort Analysis:** In what way do different customer groups generate revenue?
3. **Retention Analysis:** Which customers have been inactive recently?

## Tech Stack

- **Database:** PostgreSQL
- **Extraction:** DBeaver
- **Data Visualisation:** Excel
- **Version Control & Documentation:** Git, Github, and VS Code

## Data Clean Up

The view table cleaned up and created can be found here:

[View cohort_view_table](Scripts/cohort_view_table.sql)

- Sales and customer data aggregated into revenue metrics.
- First purchase dates calculated for cohort analysis.
- View combining transactions and customer details created.


## Analysis

### 1. Customer Segmentation

**Query:** [customer_segmentation.sql](Scripts/customer_segmentation.sql)

**Visualisation:**

Total Life Time Value Distribution:

![contoso_customer_segmentation_chart](Assets/contoso_customer_segmentation_chart.png)

**Key Findings:**

- High-Value segment (25% of customers) account for 66% of revenue ($135.4M)
- Mid-Value segment (50% of customers) account for 32% of revenue ($66.6M)
- High-Value segment (25% of customers) account for 25% of revenue ($4.3M)

**Business Insights:**

- **VIP Retention Strategy (High-Value):** Implement a retention program for the 12,372 VIP customers. Due to the prominent value they contribute, even the loss of one customer can significantly destabilise incoming revenue.
- **Revenue optimisation (Mid-Value):** Employ personalised upgrade incentives and product-bundling strategies to migrate high-frequency "Mid-Value" customers to the "High-Velue" tier.
- **Re-engagement Scheme (Low-Value):** Utilise automated re-engagement campaigns and promotions, giving more focus to purchase frequency.

### 2. Cohort Analysis

**Query**: [cohort_analysis.sql](Scripts/cohort_analysis.sql)

- Cohorts grouped into the year of their first purchase
- Aggregations performed to determine revenue and customers count per cohort
- Analysed customer retention throughout the cohorts

**Visualisation**

Customer Revenue by Cohort based on First Year of Purchase

![first_year_revenue](Assets/contoso_cohort_analysis_first_year_revenue_chart.png)

Yearly Net Revenue & Total Customer Count Comparison

![customer_count](Assets/contoso_cohort_analysis_customer_count_chart.png)

**Key Findings**

- Noticeable decline in customer revenue, where older cohorts (2015-2019) spent over $2500, whereas more recent cohorts (2022+) present a reduction in spending year on year reaching ~1900.
- The revenue and customer count peaked in 2022, however a steep drop follows in the years following, implying retention issues.
- High volatility in revenue and customer count elucidated by sharp changes in both factors.


**Business Insights**

- **Cohort Quality Analysis:** Between the 2016 cohort (~$2,800) and the 2024 cohort (~$1900) there is a 30% decrease suggesting a need for re-engagement measures through personalised offers.
- **Volatility Management:** Tight correlation between customer count and revenue, meaning revenue drop is linked to drop in customers. Introduce loyalty programs or subscriptions to incentivise long-term spending.
- **Strategy Revision:** Examine older, high-spending cohorts (2016-2018) for successful strategies and revive them to newer ones.

### 3. Customer Retention

**Query:** [retention_analysis.sql](Scripts/retention_analysis.sql)

- Distinguished customers at risk of churning.
- Analysed last purchase patterns.
- Calculated customer-specific metrics.

**Visualisation:**

![retention_analysis](Assets/contoso_retention_analysis_active_churn_chart.png)

**Key findings:**

- After 2-3 years cohort churn stabilises at ~90%, alluding to long-term retention pattern.
- Across all cohorts consistently low retention rates (8-10%) are prevalent, implying systemic retention issues rather than year-specific.
- More recent cohorts (2022-2023) display similar churn trajectories, indicating that the same pattern will follow future cohorts if no intervention takes place.

**Business Insights:**

- **Retention Threshold:** A 90% churn rate confirms the current business model heavily relies on new customer acquisition. Implement onboarding incentives, loyalty rewards, and personalised offers to improve long-term retention.
- **Regain High-Value Churned Customers:** Focus on targeting returning of high-value customers as they yield much greater contributions to revenue.
- **Early Intervention:** Predict and preempt churn risks and utilise warning indicators for early intervention for users at risk of being lost.


