# Customer Churn Analysis

## Overview  
Customer churn is a critical challenge for businesses, impacting revenue and long-term growth. This project aims to analyze churn patterns using SQL and data visualization techniques. By examining key customer attributes such as credit scores, balances, product engagement, and demographics, we derive actionable insights to improve retention strategies.  

## Objective  
- Identify factors influencing customer churn.  
- Segment customers based on churn risk and financial stability.  
- Propose data-driven strategies to retain high-value customers and reduce exit rates.  

## Dataset Description  
The dataset includes customer attributes relevant to churn analysis:  

### 1. Demographics  
- **Geography:** Customers are from France, Germany, and Spain.  
- **Gender:** Male and Female distribution.  
- **Age:** Customers are categorized into three age groups – **Under 30, 30-50, and Above 50**.  

### 2. Financial Information  
- **Credit Score:** Categorized into **High (>700), Medium (500-700), and Low (<500)**.  
- **Account Balance:** Divided into **High (>100K), Low (<100K), and No Balance** categories.  

### 3. Product Engagement  
- **Number of Products:** Customers use between 1 and 4 products.  
- **Churn Status:** Identifies whether a customer has exited (`1`) or remained (`0`).  

---

## Key Insights from Analysis  

### 1. Credit Score & Churn Trends  
- **High Credit Score (>700):** Customers with strong financial profiles are more likely to remain, especially those using multiple products.  
- **Medium Credit Score (500-700):** A significant proportion of customers fall into this category, with moderate churn rates.  
- **Low Credit Score (<500):** Customers with low scores show higher churn, especially those with low balances or single-product usage.  

### 2. Balance & Exit Trends  
- **High Balance (>100K):** These customers have the lowest churn rates and are typically engaged with multiple products.  
- **Low Balance (<100K):** Many exited customers fall into this category, particularly those with low credit scores.  
- **No Balance:** A surprising number of customers with no balance have exited, even those with high credit scores, indicating potential dissatisfaction.  

### 3. Product Engagement & Retention  
- Customers using **multiple products tend to stay longer**.  
- Those with **only one product have higher exit rates**, particularly in low credit score groups.  
- Encouraging customers to **increase product adoption can improve retention**.  

### 4. Geography & Churn Behavior  
- **France:** The highest number of customers, but also a significant churn rate in the 30-50 age group.  
- **Germany:** Similar patterns to France, with more male customers exiting.  
- **Spain:** The smallest customer base, with balanced gender distribution but notable churn in the low balance segment.  

---

## Proposed Action Plan for Churn Reduction  

Based on these findings, the following strategies can help improve customer retention:  

### 1. Target At-Risk Customers  
- **Low credit score customers** should receive personalized financial solutions to improve engagement.  
- **Customers with low balances and fewer products** need better incentives and tailored offers to increase product adoption.  

### 2. Strengthen Customer Engagement  
- Introduce **multi-product bundles** to encourage usage beyond a single product.  
- Offer **personalized recommendations and exclusive benefits** to improve customer satisfaction.  

### 3. Improve Loyalty & Customer Support  
- **Implement a loyalty program** with special incentives for long-term customers.  
- **Enhance customer service** to address pain points, especially for high-exit demographics.  

### 4. Gender-Specific & Age-Specific Marketing  
- **Males in the 30-50 age group** show the highest churn; personalized retention efforts should focus on this segment.  
- **Older customers (Above 50)** can be targeted with tailored services to increase engagement.  

---

## Technologies Used  
- **SQL(PostgreSQL):** Data extraction, transformation, and aggregation for churn analysis.  

## Final Query (SQL)  
```sql
SELECT 
    customer_id, credit_score, balance, num_of_products, exited
FROM 
    customer_data
WHERE 
    exited = 1;
