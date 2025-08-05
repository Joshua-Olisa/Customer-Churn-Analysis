# Customer Churn Analysis

This repository contains a Jupyter Notebook (`Customer-Churn Analysis.ipynb`) in which I performed exploratory data analysis (EDA) on a bank’s customer dataset to understand drivers of churn. I explored demographics, account balances, satisfaction scores, and geography to generate insights and recommendations.

---

## Table of Contents

1. [Setup & Data Loading](#setup--data-loading)  
2. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)  
3. [Correlation Analysis](#correlation-analysis)  
4. [Age-Based Churn Analysis](#age-based-churn-analysis)  
5. [Balance-Based Churn Analysis](#balance-based-churn-analysis)  
6. [Satisfaction Score Analysis](#satisfaction-score-analysis)  
7. [Geography-Based Churn Analysis](#geography-based-churn-analysis)  
8. [Next Steps](#next-steps)  

---

## Setup & Data Loading

- **Import libraries**: pandas, numpy, seaborn, matplotlib.  
- **Load dataset**: Read `Customer-Churn-Records.csv` into a DataFrame.  
- **Inspect data**:  
  - `df.info()` to check data types & nulls  
  - `df.describe()` for summary statistics  

---

## Exploratory Data Analysis (EDA)

- **Data overview**: Displayed first few rows to confirm column names and sample entries.  
- **Statistical summary**: Used `describe()` to see distribution of numeric features.  

---

## Correlation Analysis

- **Select numeric features**: Filtered DataFrame to numeric columns only.  
- **Compute correlation matrix**: Used `numeric_df.corr()`.  
- **Visualize**: Plotted a heatmap of correlations with `sns.heatmap(..., annot=True)`.  
- **Interpretation**:  
  - Noted which features correlate strongly with `Exited`.  
- **Recommendations**:  
  - Investigate high-correlation drivers (e.g. CreditScore, Tenure)  
  - Prioritize retention initiatives around those factors  

---

## Age-Based Churn Analysis

- **Define bins**: Created age groups (e.g., 18–33, 34–57, 58–66, 67+).  
- **Assign groups**: Added `Age_Group` column via `pd.cut()`.  
- **Compute churn rate**: Grouped by `Age_Group` and calculated mean of `Exited`.  
- **Visualize & summarize**:  
  - Bar plot of churn rate by age group.  
  - **Key takeaways**:  
    - Middle-aged customers (34–57) show highest churn.  
    - Older customers (67+) are most loyal.  
    - Young customers (18–33) also have strong retention.  
- **Recommendations**:  
  - Tailor engagement programs for middle-aged segment.  
  - Leverage loyalty of 67+ segment in marketing.  

---

## Balance-Based Churn Analysis

- **Summary statistics**: Grouped by `Exited` and ran `describe()` on `Balance`.  
- **Box plot**: Compared distribution of balances for churned vs. retained customers.  
- **Insights**:  
  - Customers who exit have higher average balance (~91K vs. 73K).  
  - Upper-quartile balances especially skewed among churners.  
- **Potential investigations**:  
  - Survey high-balance customers to identify pain points.  
  - Review premium product offerings and fee structures for high balances.  

---

## Satisfaction Score Analysis

- **Segment by balance**:  
  - Defined “High” segment as top 25% balances.  
  - Created `Balance_Segment` (`Low-Medium` vs. `High`).  
- **Compute mean satisfaction**: Grouped by `Balance_Segment` and averaged `Satisfaction_Score`.  
- **Key takeaways**:  
  - High-balance customers report slightly lower satisfaction.  
  - Indicates targeted service improvements may be needed for wealthier clients.  
- **Recommendations**:  
  - Deep dive into support experience for high-value customers.  
  - Introduce premium service tiers or exclusive perks.  

---

## Geography-Based Churn Analysis

- **Customer counts**: Counted total customers by `Geography`.  
- **Churn rates**: Calculated churn percentage for each country.  
- **Customer distribution**: Listed share of customers per region.  
- **Key takeaways**:  
  - France: largest base, low churn (~16.2%).  
  - Germany: smaller base, high churn (≈20%).  
  - Spain: moderate base & churn (~16.7%).  
- **Recommendations**:  
  - Investigate localized factors in Germany (service quality, competition).  
  - Apply best practices from France to other regions.  

---

## Next Steps

- Build a predictive churn model (e.g., logistic regression, decision trees).  
- Incorporate additional features (e.g., product usage, customer complaints).  
- Automate regular churn‐analysis reporting for business stakeholders.  
- Test targeted interventions (e.g., special offers) in high-risk segments and track lift.

---

*End of README*  
