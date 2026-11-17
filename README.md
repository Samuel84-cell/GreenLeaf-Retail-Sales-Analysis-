# GreenLeaf Retail Sales Performance Analysis

---

## Dashboard Preview
<img width="1065" height="503" alt="image" src="https://github.com/user-attachments/assets/16be4a30-953d-4fd3-8bf2-3b5382c15a8d" />

---

## Table of Contents

1. [Introduction](#1-introduction)
   - [About the Project](#11-about-the-project)
   - [How This Report Is Organised](#12-how-this-report-is-organised)
2. [Executive Summary](#2-executive-summary)
3. [Business Problem and Objectives](#3-business-problem-and-objectives)
   - [Business Context](#31-business-context)
   - [Business Problem Statement](#32-business-problem-statement)
   - [Business Question](#33-business-question)
   - [Project Objectives](#34-project-objectives)
4. [Tools and Technologies](#4-tools-and-technologies)
5. [Data Collection and Overview](#5-data-collection-and-overview)
6. [Data Exploration](#6-data-exploration)
7. [Data Cleaning and Preparation](#7-data-cleaning-and-preparation)
8. [Data Analysis](#8-data-analysis)
   - [Analysis Approach and Formulas](#81-analysis-approach-and-formulas)
   - [Branch Performance](#82-branch-performance)
   - [Product Category Performance](#83-product-category-performance)
   - [Product Performance](#84-product-performance)
   - [Monthly Sales Trend](#85-monthly-sales-trend)
   - [Payment Method Behaviour](#86-payment-method-behaviour)
   - [New vs Returning Customers](#87-new-vs-returning-customers)
9. [Key Performance Indicators](#9-key-performance-indicators)
10. [Dashboard Development](#10-dashboard-development)
11. [Business Insights](#11-business-insights)
    - [Key Insights](#111-key-insights)
    - [Direct Answers to the Business Questions](#112-direct-answers-to-the-business-questions)
12. [Limitations and Assumptions](#12-limitations-and-assumptions)
13. [Recommendations](#13-recommendations)
14. [Conclusion and Next Steps](#14-conclusion-and-next-steps)
15. [Appendix](#15-appendix)

---

## 1. Introduction

Retail businesses generate large volumes of transaction data every day, but raw records rarely answer management's questions on their own. They arrive with inconsistent dates, missing values, duplicate rows and unreliable figures, and they need to be cleaned, validated and structured before they can support a decision.

This project takes the 2025 sales transactions of **GreenLeaf Retail Stores Nigeria**, a fictional mid-sized retailer with seven branches, from a raw and inconsistent dataset to a validated dataset, a set of business KPIs, and an interactive Excel dashboard. The aim is to show where sales are generated, where performance and discounting need attention, and what management can do about it.

The work follows the standard data analysis lifecycle: **ask, prepare, process, analyse, share and act**. Every cleaning decision, formula and assumption is documented so that the results can be traced and reproduced.

### 1.1 About the Project

| Item | Detail |
|---|---|
| **Analyst** | Adekanmi Samuel |
| **Programme** | Analytics Hub Africa, Data Analyst Launchpad, Cohort 1.0 |
| **Project period** | July – October 2026 |
| **Business** | GreenLeaf Retail Stores Nigeria (fictional) |
| **Dataset** | 1,537 raw transaction rows, cleaned to 1,500 transactions |
| **Period analysed** | January – December 2025 |
| **Tools** | Microsoft Excel, Power Query, PivotTables and PivotCharts, Excel formulas, slicers |
| **Deliverables** | Cleaned dataset, KPI summary, interactive Excel dashboard, insights and recommendations |

### 1.2 How This Report Is Organised

| Phase | What happens | Sections |
|---|---|---|
| **Ask** | Define the business problem, question and objectives | [3](#3-business-problem-and-objectives) |
| **Prepare** | Identify the tools, collect the data and profile its quality | [4](#4-tools-and-technologies), [5](#5-data-collection-and-overview), [6](#6-data-exploration) |
| **Process** | Clean, standardise and validate the data | [7](#7-data-cleaning-and-preparation) |
| **Analyse** | Analyse performance and calculate KPIs | [8](#8-data-analysis), [9](#9-key-performance-indicators) |
| **Share** | Build the dashboard and communicate insights | [10](#10-dashboard-development), [11](#11-business-insights) |
| **Act** | State limitations, recommend actions and conclude | [12](#12-limitations-and-assumptions), [13](#13-recommendations), [14](#14-conclusion-and-next-steps) |

---

## 2. Executive Summary

This project analyses GreenLeaf's retail sales performance using Microsoft Excel to identify sales trends, evaluate branch and product category performance, and understand customer purchasing patterns. The analysis covers **1,500 transactions** recorded between **January and December 2025**, providing insight into revenue generation, discount distribution, product performance and customer contribution.

The raw dataset was cleaned by removing duplicate records and standardising text, dates and numeric fields. The cleaned data was then analysed across branches, product categories, individual products, months, payment methods and customer types.

**Key results**

- Total sales of **₦152,589,400.50** from **9,614 units** across **1,500 transactions**, with an average order value of **₦101,726.27**.
- Gross sales before discounts were **₦158,488,374.00**; total discounts were **₦5,898,973.50**, or **3.72%** of gross sales.
- **Kano** is the highest-selling branch; **Abuja** is the lowest among the named branches.
- **Groceries, Household and Electronics** are the leading categories, together contributing about **59%** of sales.
- **Enugu (4.70%)** and **Port Harcourt (4.68%)** have the highest branch-level discount rates.
- **New and returning customers contribute almost equally** to total sales.

Because the dataset has no product cost, gross profit, net profit or margin fields, the analysis focuses on **sales performance, not profitability**.

---

## 3. Business Problem and Objectives

### 3.1 Business Context

GreenLeaf Retail Stores Nigeria is a **fictional** mid-sized retail business selling electronics, groceries, household goods, fashion items and personal care products across seven locations: **Port Harcourt, Lagos, Abuja, Kano, Ibadan, Enugu and Benin City**.

### 3.2 Business Problem Statement

GreenLeaf needs a reliable and consistent view of its sales performance across branches, products and customer segments. Without a structured analysis, management may struggle to identify top-performing branches, understand changes in sales over time, evaluate the contribution of each product category, and monitor the effect of discounts and payment methods on revenue.

The raw dataset also contains data quality issues, including inconsistent date formats, missing values, questionable numeric entries and sales figures that need validation. Left unaddressed, these issues would compromise the accuracy of calculations, reports and business insights.

This project therefore cleans, validates and analyses the sales data to produce accurate performance metrics and meaningful insights for management decision-making.

### 3.3 Business Question

> **Where is GreenLeaf generating the most sales, which branches and product categories require attention, and what actions can management take to improve overall sales performance?**

### 3.4 Project Objectives

1. Examine the raw sales dataset and identify data quality issues that could affect accuracy.
2. Clean and standardise dates, categories and numeric fields.
3. Handle missing, duplicate and invalid records using documented data-cleaning methods.
4. Validate sales figures using quantity, unit price and discount information.
5. Analyse sales performance across branches, product categories, products, months, payment methods and customer types.
6. Identify the highest- and lowest-performing branches, products and categories by sales.
7. Calculate key sales KPIs and present the findings clearly.
8. Build an interactive Excel dashboard with filtering by branch.
9. Provide practical recommendations on sales monitoring, discount management and performance improvement.

---

## 4. Tools and Technologies

| Tool | How it was used |
|---|---|
| **Microsoft Excel** | Primary tool for inspecting the dataset, performing calculations, summarising transactions and calculating KPIs |
| **Power Query** | Data type correction, date standardisation, text cleaning, duplicate removal, missing-value handling and numeric validation |
| **PivotTables and PivotCharts** | Summarising sales by branch, category, product, month, payment method and customer type, and visualising the results |
| **Excel Formulas** | Calculating and validating total sales, discount amounts and rates, quantity, transaction counts and average order value |
| **Dashboard and Slicers** | Combining KPIs and charts in one view, with a Branch slicer for interactive filtering |

---

## 5. Data Collection and Overview

The raw sales data was supplied as an Excel workbook of GreenLeaf's 2025 transactions.

| Item | Detail |
|---|---|
| **Source workbook** | `GreenLeaf_Retail_Sales_Raw.xlsx` |
| **Source sheet** | Raw Sales Data |
| **Original size** | 1,537 rows × 13 columns |
| **Period** | January – December 2025 |
| **Transaction grain** | One row per sales transaction |
| **Key dimensions** | Branch, Region, Product Category, Product Name, Payment Method, Sales Rep, Customer Type |
| **Key measures** | Quantity, Unit Price, Discount %, Total Sales |

---

## 6. Data Exploration

Before cleaning, the dataset was profiled to find what could affect the accuracy of the analysis. The issues below were identified after duplicate removal.

| Issue | Observed level |
|---|---|
| Duplicate transactions | 37 exact duplicate rows |
| Text inconsistencies | Mixed case, extra spaces and synonymous labels |
| Date inconsistencies | 5 date formats; 194 ambiguous slash dates |
| Quantity | 60 missing/placeholder and 15 non-positive values |
| Unit Price | 45 missing/placeholder and 10 negative values |
| Discount | 120 missing/placeholder values |
| Total Sales | 105 missing/placeholder values |
| Categorical gaps | Branch 30; Region 1; Category 90; Payment 75; Rep 45; Customer 90 |

---

## 7. Data Cleaning and Preparation

Data cleaning was treated as a separate stage before any analysis. Each issue found in [Section 6](#6-data-exploration) was handled with a documented rule. Where the transaction arithmetic supported a correction, it was used to recover the value. Where reliable recovery was not possible, a product-level imputation rule was applied, or the categorical value was retained as `Unknown`.

### Step 1: Remove duplicates
Removed 37 exact duplicate rows, reducing 1,537 rows to 1,500 transactions.

### Step 2: Standardise text
Cleaned spacing and mapped branch, category, payment, sales rep and customer-type labels to consistent values.

### Step 3: Standardise dates
ISO, month-name and dot-formatted dates were parsed directly. Slash-formatted dates were interpreted as **DD/MM/YYYY** when both components were 12 or less. Where a month/day combination was impossible, the component greater than 12 resolved the date. The resulting date range is **1 January 2025 to 31 December 2025**.

### Step 4: Fix and recover numeric fields
- **Quantity:** reverse-calculated from Total Sales where possible; remaining gaps filled with the product-level median.
- **Unit Price:** negative signs corrected where the arithmetic supported it; reverse-calculated where possible; remaining gaps filled with the product-level median.
- **Discount:** inferred where transaction arithmetic matched a valid rate (0%, 5%, 10% or 15%); remaining gaps filled with the most common valid discount for the same product.
- **Total Sales:** calculated after Quantity, Unit Price and Discount were cleaned.

### Step 5: Handle categorical gaps
Applied source-based repairs where possible; otherwise retained the value as `Unknown` rather than inventing information.

### Step 6: Validate
The prepared dataset contains **1,500 transactions**. Cleaned Quantity, Unit Price, Discount and Total Sales fields are populated with non-negative values, and transaction totals reconcile after the cleaning rules were applied.

### Cleaning Summary

| Issue | Action taken |
|---|---|
| Duplicate transactions | Removed exact duplicate rows |
| Text inconsistencies | Cleaned spacing; mapped labels to consistent values |
| Date inconsistencies | Parsed to true 2025 dates using the DD/MM/YYYY rule |
| Quantity | Reverse-calculated from Total Sales; product-level median for the rest |
| Unit Price | Corrected negative signs; reverse-calculated; product-level median for the rest |
| Discount | Inferred from arithmetic; product-level mode for the rest |
| Total Sales | Calculated after other numeric fields were cleaned |
| Categorical gaps | Source-based repairs; otherwise retained as `Unknown` |

Detailed counts for each action are in the [Appendix](#15-appendix).

---

## 8. Data Analysis

### 8.1 Analysis Approach and Formulas

After cleaning and validating the dataset, transactions were summarised across branches, product categories, individual products, months, payment methods and customer types. Monthly performance was reviewed to see how revenue changed through the year, and discount levels were compared across branches, payment methods and customer types. Results were built with PivotTables and PivotCharts.

| Metric / analysis | Formula / logic |
|---|---|
| Gross Sales | `Quantity × Unit Price` |
| Discount Amount | `Gross Sales × Discount %` |
| Total Sales | Recorded transaction sales; missing values calculated as `Gross Sales − Discount Amount` |
| Discount % of Gross Sales | `Discount Amount ÷ Gross Sales` |
| Average Order Value | `Total Sales ÷ Number of transactions` |
| Branch performance | Total Sales, Discount %, Quantity, Transactions and AOV by branch |
| Category / product performance | Total Sales, Discount %, Quantity and Transactions by category or product |
| Monthly trend | Total Sales aggregated by month |

> **Note:** The branch, category, payment method and customer type tables below show named values only. Records retained as `Unknown` are excluded, so these tables do not sum to the full ₦152.59M total.

### 8.2 Branch Performance

| Branch | Transactions | Quantity | Sales | Discount | Discount % | AOV |
|---|---:|---:|---:|---:|---:|---:|
| **Kano** | 228 | 1,469 | ₦26,248,511.50 | ₦966,926.15 | 3.55% | ₦115,125.05 |
| Lagos | 212 | 1,394 | ₦22,191,207.00 | ₦693,767.00 | 3.03% | ₦104,675.50 |
| Enugu | 207 | 1,326 | ₦21,541,970.00 | ₦1,062,210.00 | **4.70%** | ₦104,067.49 |
| Ibadan | 216 | 1,334 | ₦21,524,754.00 | ₦495,546.00 | 2.25% | ₦99,651.64 |
| Port Harcourt | 210 | 1,378 | ₦20,157,898.50 | ₦988,691.50 | **4.68%** | ₦95,989.99 |
| Benin City | 205 | 1,269 | ₦19,102,531.50 | ₦840,820.85 | 4.22% | ₦93,183.08 |
| **Abuja** | 192 | 1,237 | ₦18,686,261.50 | ₦750,138.50 | 3.86% | ₦97,324.28 |

- **Kano** has the highest sales at ₦26.25M from 228 transactions.
- **Abuja** has the lowest sales among the seven named branches at ₦18.69M from 192 transactions.
- **Enugu** has the highest discount rate (4.70%), closely followed by **Port Harcourt** (4.68%). **Ibadan** has the lowest (2.25%).

### 8.3 Product Category Performance

| Category | Transactions | Quantity | Sales | Discount % | AOV |
|---|---:|---:|---:|---:|---:|
| **Groceries** | 299 | 2,001 | ₦30,336,967.50 | 2.88% | ₦101,461.43 |
| Household | 270 | 1,740 | ₦30,180,992.00 | 3.99% | ₦111,781.45 |
| Electronics | 286 | 1,833 | ₦29,474,137.00 | 3.37% | ₦103,056.42 |
| Fashion | 276 | 1,746 | ₦26,909,144.00 | **4.46%** | ₦97,496.90 |
| Beauty & Personal Care | 279 | 1,710 | ₦26,682,266.00 | 4.15% | ₦95,635.36 |

- **Groceries** lead with ₦30.34M, followed by **Household** (₦30.18M) and **Electronics** (₦29.47M). Together, these three account for about **59%** of cleaned sales.
- **Fashion** has the highest discount rate among the five categories (4.46%), followed by Beauty & Personal Care (4.15%).

### 8.4 Product Performance

#### Top 10 Products by Sales

| Rank | Product | Transactions | Sales | Discount % | AOV |
|---:|---|---:|---:|---:|---:|
| 1 | Shea Butter Cream | 42 | ₦7,392,188.50 | 3.54% | ₦176,004.49 |
| 2 | Plastic Chair Set | 48 | ₦6,917,746.50 | 5.92% | ₦144,119.72 |
| 3 | Cleaning Mop | 40 | ₦6,888,287.50 | 3.77% | ₦172,207.19 |
| 4 | Power Bank 20000mAh | 48 | ₦6,724,255.00 | 3.35% | ₦140,088.65 |
| 5 | Handbag | 44 | ₦5,313,961.00 | 4.97% | ₦120,771.84 |
| 6 | Milo 500g | 55 | ₦5,256,959.00 | 2.09% | ₦95,581.07 |
| 7 | Rice Cooker | 40 | ₦5,162,673.50 | 5.06% | ₦129,066.84 |
| 8 | Tomato Paste Carton | 36 | ₦4,919,371.00 | 1.94% | ₦136,649.19 |
| 9 | Home Theatre System | 45 | ₦4,902,334.50 | 2.54% | ₦108,940.77 |
| 10 | Spaghetti Pack | 39 | ₦4,772,074.00 | 4.33% | ₦122,360.87 |

**Shea Butter Cream** has the highest product sales at ₦7.39M. Plastic Chair Set, Cleaning Mop and Power Bank 20000mAh follow at approximately ₦6.92M, ₦6.89M and ₦6.72M.

#### Bottom 5 Products by Sales

| Product | Transactions | Sales | Discount % | AOV |
|---|---:|---:|---:|---:|
| LED TV 43" | 29 | ₦1,758,779.50 | 3.70% | ₦60,647.57 |
| Kids Sneakers | 36 | ₦2,002,129.50 | 6.34% | ₦55,614.71 |
| Toothpaste Pack | 36 | ₦2,306,319.00 | 2.19% | ₦64,064.42 |
| Laundry Basket | 32 | ₦2,318,348.00 | 4.70% | ₦72,448.38 |
| Storage Basket | 33 | ₦2,473,092.50 | 4.29% | ₦74,942.20 |

**LED TV 43"** has the lowest sales at ₦1.76M, followed by **Kids Sneakers** at ₦2.00M. These are lower *sales* outcomes, not proof of lower *profitability*, since product cost and margin data are unavailable.

#### Products with Higher Discount Rates

| Product | Sales | Discount % |
|---|---:|---:|
| Deodorant Roll-on | ₦2,606,801.00 | 6.59% |
| Kids Sneakers | ₦2,002,129.50 | 6.34% |
| Plastic Chair Set | ₦6,917,746.50 | 5.92% |
| Hair Relaxer Kit | ₦2,775,349.50 | 5.85% |
| Baby Diaper Pack | ₦3,101,465.50 | 5.66% |
| Office Blazer | ₦3,631,153.00 | 5.57% |

All six products sit well above the overall **3.72%** discount rate.

### 8.5 Monthly Sales Trend

| Month | Transactions | Quantity | Sales | Discount % | AOV |
|---|---:|---:|---:|---:|---:|
| 2025-01 | 133 | 830 | ₦14,862,389.50 | 4.04% | ₦111,747.29 |
| 2025-02 | 133 | 875 | ₦12,779,002.00 | 5.59% | ₦96,082.72 |
| 2025-03 | 134 | 774 | ₦12,993,499.00 | 2.28% | ₦96,966.41 |
| 2025-04 | 113 | 735 | ₦11,920,091.00 | 3.45% | ₦105,487.53 |
| 2025-05 | 121 | 802 | ₦10,694,727.50 | 3.46% | ₦88,386.18 |
| 2025-06 | 123 | 827 | ₦12,162,395.50 | 3.79% | ₦98,881.26 |
| 2025-07 | 124 | 762 | ₦11,190,344.00 | 2.05% | ₦90,244.71 |
| 2025-08 | 126 | 864 | ₦13,695,620.00 | 4.19% | ₦108,695.40 |
| 2025-09 | 124 | 791 | ₦12,005,431.00 | 3.28% | ₦96,817.99 |
| 2025-10 | 122 | 761 | ₦14,257,267.00 | 4.05% | ₦116,862.84 |
| 2025-11 | 119 | 791 | ₦12,839,324.50 | 3.41% | ₦107,893.48 |
| 2025-12 | 128 | 802 | ₦13,189,309.50 | 4.56% | ₦103,041.48 |

- **January** is the highest month (₦14.86M); **May** is the lowest (₦10.69M).
- Sales rise **33.31%** from May to October, then December is **7.49%** below October.
- **H2 sales (₦77.18M)** are **2.34%** above **H1 sales (₦75.41M)**.
- **February** has the highest monthly discount rate (5.59%); **July** has the lowest (2.05%).

### 8.6 Payment Method Behaviour

| Payment method | Transactions | Transaction share | Sales | Sales share | Discount % |
|---|---:|---:|---:|---:|---:|
| Cash | 395 | 26.33% | ₦40,574,679.00 | 26.59% | 2.52% |
| Card | 345 | 23.00% | ₦37,618,950.50 | 24.65% | 3.76% |
| Bank Transfer | 340 | 22.67% | ₦35,865,831.00 | 23.50% | 3.87% |
| POS | 345 | 23.00% | ₦32,123,010.00 | 21.05% | **4.98%** |

**Cash** is the largest payment channel by sales (₦40.57M, 26.59%), followed by Card (₦37.62M), Bank Transfer (₦35.87M) and POS (₦32.12M).

### 8.7 New vs Returning Customers

| Customer type | Transactions | Sales share | Sales | AOV | Discount % |
|---|---:|---:|---:|---:|---:|
| Returning | 718 | 47.48% | ₦72,455,606.00 | ₦100,913.10 | 3.93% |
| New | 692 | 47.33% | ₦72,214,658.00 | ₦104,356.44 | 3.68% |

Returning customers generate ₦72.46M from 718 transactions; new customers generate ₦72.21M from 692. New customers have a slightly higher AOV (about **3.41%** above returning customers).

---

## 9. Key Performance Indicators

| KPI | Result | Definition |
|---|---|---|
| **Total Sales (Revenue)** | ₦152,589,400.50 | Net transaction sales after recorded discounts |
| **Gross Sales** | ₦158,488,374.00 | Sales before recorded discounts |
| **Total Discount Given** | ₦5,898,973.50 | Estimated currency value of discounts granted |
| **Discount Rate** | 3.72% | Discount Amount ÷ Gross Sales |
| **Total Quantity Sold** | 9,614 | Total units in the cleaned transactions |
| **Average Order Value** | ₦101,726.27 | Total Sales ÷ Total Transactions |
| **Total Transactions** | 1,500 | Unique transaction rows after duplicate removal |

---

## 10. Dashboard Development

The **GreenLeaf Retail Sales Dashboard** was built in Microsoft Excel to bring the main KPIs and supporting charts onto one page, so a reviewer can see overall performance first, then compare branches, categories, months, payment methods and customer types.

| Component | Implementation |
|---|---|
| **KPI 1** | Total Revenue (₦) |
| **KPI 2** | Total Transactions |
| **KPI 3** | Total Discount Given (₦) |
| **KPI 4** | Discount Rate (% of Gross Sales) |
| **KPI 5** | Total Quantity Sold |
| **KPI 6** | Average Order Value |
| **Chart 1** | Total Sales by Branch: bar chart sorted by sales |
| **Chart 2** | Discount by Branch: chart comparing branch discount values/rates |
| **Chart 3** | Sales by Product Category: bar chart |
| **Chart 4** | Monthly Sales Trend: line chart |
| **Chart 5** | Sales by Payment Method: bar chart sorted by sales |
| **Chart 6** | Sales by Customer Type: doughnut chart |
| **Filter** | Branch slicer connected to the PivotTables and PivotCharts for consistent interactive filtering |

---

## 11. Business Insights

### 11.1 Key Insights

- **Sales are concentrated.** Kano is the largest branch (₦26.25M). Groceries, Household and Electronics contribute about 59% of sales.
- **Abuja trails.** It has the lowest branch sales (₦18.69M from 192 transactions).
- **Discount intensity varies independently of sales.** Enugu (4.70%) and Port Harcourt (4.68%) have the highest branch discount rates, while Ibadan has the lowest (2.25%).
- **Some products carry heavy discounts.** Six products have rates between 5.57% and 6.59%, well above the 3.72% overall rate.
- **Sales were strongest in January and October,** and weakest in May. H2 sales were 2.34% above H1.
- **POS carries the highest payment-channel discount rate** (4.98%) against 2.52% for Cash.
- **New and returning customers contribute almost equally** to sales.

### 11.2 Direct Answers to the Business Questions

**Where is GreenLeaf generating sales?**  
The dataset has no cost or profit fields, so it cannot show accounting profit. It does show where sales are concentrated: **Kano** is the largest branch at ₦26.25M, and **Groceries, Household and Electronics** are the three largest categories, contributing about 59% of sales.

**Where is GreenLeaf losing ground by branch?**  
**Abuja** has the lowest sales at ₦18.69M. **Enugu** and **Port Harcourt** have the highest discount rates (4.70% and 4.68%).

**Which categories generate sales but also face discount pressure?**  
Groceries lead with ₦30.34M and a 2.88% discount rate. Household generates ₦30.18M at 3.99%, and Electronics ₦29.47M at 3.37%. **Fashion** has the highest category discount rate at 4.46%.

**How do customers pay?**  
Cash is the largest channel by sales, followed by Card, Bank Transfer and POS. POS has the highest discount rate (4.98%).

**How do new and returning customers compare?**  
They contribute nearly equal sales. New customers have a slightly higher AOV; returning customers account for slightly more transactions.

---

## 12. Limitations and Assumptions

- **No profitability analysis.** The dataset has no cost, margin or profit field, so actual profit and margin cannot be calculated.
- **Limited customer analysis.** Customer analysis is limited to New vs Returning. Without a Customer ID, repeat-customer frequency and cohort retention cannot be reliably calculated.
- **Unknown values.** Where the data did not support a reliable repair, the value was retained as `Unknown` rather than invented.
- **Ambiguous dates.** Slash-formatted dates were standardised using the DD/MM/YYYY default when both components were 12 or less.
- **Imputation.** Some numeric fields were imputed using transaction arithmetic or product-level statistics. Row-level cleaning actions were recorded for traceability.
- **Discount is a pressure indicator,** not a substitute for accounting profit.

---

## 13. Recommendations

| Priority area | Evidence | Recommended action |
|---|---|---|
| **Branch discount governance** | Enugu (4.70%) and Port Harcourt (4.68%) have the highest branch discount rates | Review discount approvals, promotion reasons and product mix. Compare discounted products with sales outcomes before extending promotions |
| **Abuja sales improvement** | Lowest branch sales at ₦18.69M and 192 transactions | Investigate transaction volume, category mix, stock availability and sales-rep activity before changing prices |
| **Protect core categories** | Groceries, Household and Electronics contribute about 59% of sales | Prioritise stock availability and disciplined promotions across these categories |
| **Review high-discount products** | Several products have discount rates above 5.5% | Test whether discounts generate enough additional volume to justify the reduction in sales value |
| **Improve data completeness** | `Unknown` values remain in branch, category, payment and customer fields | Validate required fields at point of sale and track completeness as a data-quality KPI |
| **Monitor payment-channel patterns** | POS discount rate is 4.98% vs 2.52% for Cash | Review whether channel-linked promotions generate incremental sales and whether discount rules differ by payment method |
| **Balance acquisition and retention** | New and returning customers contribute nearly equal sales | Report acquisition and retention separately rather than assuming one group drives performance |

---

## 14. Conclusion and Next Steps

This project gives a structured view of GreenLeaf's 2025 retail sales performance across branches, categories, products, payment methods and customer types. Kano has the highest branch sales, Abuja the lowest, Enugu and Port Harcourt the highest discount rates, Groceries, Household and Electronics dominate category sales, and new and returning customers contribute almost equal sales.

**Recommended next step:** combine the current sales and discount analysis with cost-of-goods, inventory, promotion and customer-identifier data. This would move the analysis beyond sales reporting to assess profitability, margins, customer retention and customer value directly.

---

## 15. Appendix

### Key Data Quality Counts

| Field / issue | Count / result |
|---|---:|
| Original rows | 1,537 |
| Duplicate rows removed | 37 |
| **Cleaned transaction rows** | **1,500** |
| Ambiguous slash-formatted dates | 194 |
| Quantity inferred from Total Sales | 69 |
| Quantity filled by product median | 6 |
| Unit Price inferred from Total Sales | 42 |
| Unit Price sign-corrected | 10 |
| Unit Price filled by product median | 3 |
| Discount inferred from Total Sales | 110 |
| Discount inferred with Unit Price | 4 |
| Discount filled by product mode | 6 |
| Total Sales calculated | 105 |

---

<div align="center">

**Project by Adekanmi Samuel** · Analytics Hub Africa, Data Analyst Launchpad Cohort 1.0

*GreenLeaf Retail Stores Nigeria is a fictional business created for this capstone project.*

</div>

