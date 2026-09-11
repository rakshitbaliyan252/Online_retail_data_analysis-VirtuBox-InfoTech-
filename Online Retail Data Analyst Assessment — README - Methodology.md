# Online Retail Data Analyst Assessment

## 1. Project Overview

This project analyzes an online retail transactional dataset to understand sales performance, customer value, product performance, geographic markets, and return behavior.

The main objective is to transform raw transaction data into meaningful business insights and actionable recommendations that can support management decision-making.

---

## 2. Dataset Information

**Dataset:** Online Retail II

**Source:** UCI Machine Learning Repository

**Original Dataset Size:** 1,067,371 rows and 8 columns

**Columns:**
- Invoice
- StockCode
- Description
- Quantity
- InvoiceDate
- Price
- Customer ID
- Country

The dataset contains transactional information about products purchased by customers across different countries and dates.

---

## 3. Tools Used

The following tools were used during the analysis:

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Google Colab
- Google Sheets
- Looker Studio

Python and Pandas were primarily used for data cleaning, transformation, KPI calculation, and exploratory analysis.

---

## 4. Data Cleaning and Preparation

The raw dataset was cleaned and transformed before performing the business analysis.

### Major cleaning steps

1. **Duplicate records**
   - 34,335 duplicate rows were identified and removed.
   - This prevents duplicate transactions from inflating sales results.

2. **Missing product descriptions**
   - 4,382 records had missing descriptions.
   - These records were removed for reliable product-level analysis.

3. **Missing Customer IDs**
   - 243,007 records had missing Customer IDs.
   - These records were retained for overall sales analysis.
   - They were excluded from customer-level analysis because the customer could not be identified reliably.

4. **Invalid prices**
   - Transactions with zero or negative prices were excluded from normal revenue analysis.
   - This prevents invalid values from distorting revenue calculations.

5. **Negative quantities**
   - Negative quantities were retained and treated as potential returns/cancellations rather than automatically deleting them.
   - This allows return-related business analysis.

6. **Date conversion**
   - InvoiceDate was converted into a proper datetime format.

7. **Calculated Sales field**
   - A new field was created:

   `Sales = Quantity × Price`

8. **Additional fields**
   - Year
   - Month
   - Year-Month
   - Month Name
   - Day of Week
   - Is_Return
   - Is_Cancelled
   - Has_Customer_ID

These fields were created to support time-series, return, customer, and business analysis.

---

## 5. Key Performance Indicators

After cleaning and processing the data, the following KPIs were calculated:

| KPI | Value |
|---|---:|
| Total Sales | 19,014,209.84 |
| Total Orders | 48,369 |
| Total Customers | 5,939 |
| Total Products | 4,932 |
| Average Order Value | 393.11 |
| Return Transaction Rate | 1.86% |

These KPIs are also used as the foundation for the management dashboard.

---

## 6. Analysis Performed

The analysis focused on the following areas:

### Sales Performance
Monthly sales were analyzed to understand changes in revenue over time.

### Product Performance
Products were compared based on sales revenue and quantity sold to identify high-performing products.

### Geographic Performance
Sales were aggregated by country to identify the strongest markets and potential growth opportunities.

### Customer Performance
Customer-level sales were analyzed for customers with available Customer IDs to identify high-value customers.

### Return and Cancellation Analysis
Negative-quantity transactions were investigated as potential returns or cancellations to understand their impact on the business.

---

## 7. Business Insights

The analysis is designed to identify:

- Overall revenue and order performance.
- Changes in sales over time.
- High-performing products.
- High-value customers.
- Strong geographic markets.
- Return-related business risks.
- Opportunities for improving customer retention and product management.

The exact insights presented in the assessment are based on calculated outputs from the cleaned dataset rather than assumptions.

---

## 8. Business Recommendations

### Recommendation 1 — Prioritize High-Performing Products

Management should identify products generating strong sales and demand and use this information for inventory and merchandising decisions.

**Responsible teams:** Inventory and Merchandising

**Expected outcome:** Better product availability and improved sales opportunities.

**Metric:** Product revenue and quantity sold.

---

### Recommendation 2 — Focus on High-Value Customers

Customers generating high revenue should be prioritized for retention and engagement activities.

**Responsible teams:** Marketing and CRM

**Expected outcome:** Increased repeat purchases and customer value.

**Metric:** Customer revenue and repeat-purchase rate.

---

### Recommendation 3 — Investigate Returns

Products and transactions associated with frequent returns should be investigated to identify potential product, fulfillment, or customer-experience issues.

**Responsible teams:** Operations and Product teams

**Expected outcome:** Lower avoidable returns and improved net revenue.

**Metric:** Return rate and net sales.

---

## 9. Data Quality Issues and Limitations

### Missing Customer IDs

A significant number of transactions do not contain Customer IDs. Therefore, customer-level analysis does not represent the complete transaction population.

### Duplicate Transactions

Duplicate records can artificially increase sales and transaction counts. These were removed during cleaning.

### Returns and Cancellations

Negative quantities can represent legitimate returns or cancellations. They should not automatically be treated as incorrect data.

### Extreme Values

The dataset contains unusually large quantities and transaction values. These values require investigation before being classified as errors.

### Dataset Limitations

The dataset does not contain:

- Product cost
- Profit margin
- Marketing expenditure
- Customer demographics
- Detailed customer acquisition information

Therefore, revenue should not be interpreted as profitability.

For example, a product with the highest sales revenue cannot safely be called the "most profitable product" without cost or margin information.

---

## 10. Dashboard

An interactive Looker Studio dashboard is created using the analysis-ready data.

The dashboard focuses on:

- Total Sales
- Total Orders
- Total Customers
- Average Order Value
- Return Rate
- Monthly Sales Trend
- Product Performance
- Country Performance
- Customer Performance

Filters and interactive visualizations allow management to explore different segments of the business.

---

## 11. Presentation

A management presentation accompanies the analysis and covers:

1. Business Problem
2. Data and Methodology
3. Key Findings
4. Deep-Dive Analysis
5. Recommendations
6. Expected Business Impact
7. Limitations and Next Steps

---

## 12. AI Usage

**AI Tool Used:** ChatGPT

AI was used to:

- Understand the assessment requirements.
- Structure the analysis workflow.
- Assist with Python/Pandas logic.
- Develop business questions and hypotheses.
- Explain data-cleaning concepts.
- Assist in forming business recommendations.

### Example of AI Assistance

AI helped identify that negative quantities should potentially be treated as returns/cancellations instead of automatically deleting them.

### Verification

AI-generated suggestions and calculations were verified against the actual dataset using Python. Numerical findings included in the assessment were based on the calculated dataset outputs.

---

## 13. Final Deliverables

The final submission contains:

- Google Sheet with assessment worksheets
- Analysis-ready dataset
- Google Colab notebook containing Python code
- Looker Studio dashboard
- Management presentation
- README / Methodology document

---

## 14. Conclusion

The analysis provides a structured view of the online retail business by examining revenue, orders, products, customers, geographic markets, and return behavior.

The findings can help management prioritize high-performing products, focus on valuable customers, and investigate return-related issues. Further analysis using product cost, profit margin, marketing, and customer demographic data would enable more advanced profitability and customer-value analysis.