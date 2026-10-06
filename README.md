# E-Commerce Profitability Analysis

### Project Overview

This project analyzes the true profitability of an e-commerce business across
product categories, sales channels, customer returns, and marketing activities.
The analysis identifies major profitability drivers and provides
data-supported recommendations for improving financial performance.

### Business Context

An e-commerce retailer sells products across multiple categories through
**Website, Mobile App, Marketplace, and Social Commerce** channels. Although
sales revenue appears healthy, revenue alone does not provide a complete view
of business profitability.

Product costs, shipping costs, discounts, platform fees, transaction fees,
customer returns, and marketing spend can significantly reduce margins.
Management requires a clearer understanding of which product
categories, sales channels, and marketing activities generate sustainable
profit and where costs or returns are reducing financial performance.

### Objective

Analyze transaction, product and marketing data to evaluate **e-commerce
profitability across product categories and sales channels**.

The analysis focuses on:
- Revenue, costs, profit, and profit margins
- Profitability differences across product categories and sales channels
- Customer return rates and refunded revenue
- Marketing efficiency using ROAS, CPC, and CPA
- Historical marketing performance to support a 20% budget reduction scenario

###  Goal

The project aims to translate financial data into actionable
business insights that support profitability improvement.

The analysis identifies:
- High- and low-margin product categories
- Strong and underperforming sales channels
- Cost components contributing to margin pressure
- Return-related revenue leakage
- High- and low-efficiency marketing activity
- Lower-ROAS platform-month periods for marketing budget review

The final recommendations focus on **shipping-cost control, channel
profitability improvement, return management, and marketing budget
optimization**.
---

### Business Questions

The analysis addresses five key business questions:

1. What is the profit margin by product category, and what recorded cost
   components help explain the differences?

2. How does profitability vary across Website, Mobile App, Marketplace,
   and Social Commerce?

3. What are return rates by category and channel, and how much recorded
   revenue was refunded?

4. Which marketing platforms generate the strongest aggregate ROAS,
   CPC, and CPA performance?

5. If marketing spend must be reduced by 20%, which historically
   lower-ROAS platform-month combinations should be prioritized for review?

---

## Datasets

      Three datasets support the analysis.
      orders: order-level transactions, 
      products: a product catalog with cost data, 
      marketing_spend: monthly marketing spend by platform
---

## Tools

- Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook

---

## Project Workflow

### 1. Data Preparation

Data preparation includes:

- Dataset structure and grain assessment
- Missing-value checks
- Duplicate checks
- Business-key validation
- Data-type validation
- Categorical consistency checks
- Financial reconciliation
- Data cleaning
- Data Transformation
- Dataset relationship validation
- Final data validation

Financial calculations were validated using:

`Net Revenue = Gross Revenue - Discount Amount - Refund Amount`

`Total Costs = Product Cost + Shipping Cost + Platform Fee + Transaction Fee`

`Profit = Net Revenue - Total Costs`

### 2. Relationship Validation (modeling)

The orders dataset does not contain `product_id`, preventing a reliable
order-to-product-level join.

Joining orders and products using category would create a many-to-many
relationship and could duplicate financial values.

Marketing data is recorded at month-platform level and does not contain an
order-level marketing attribution key. Marketing performance is therefore
analyzed at the appropriate aggregated grain.

### 3. Business Analysis

The analysis covers:

- Overall profitability
- Category profitability
- Sales channel profitability
- Cost and margin drivers
- Return performance
- Monthly trends
- Marketing efficiency
- 20% marketing budget reduction scenario

---

## Headline KPIs

| KPI | Result |
|---|---:|
| Total Orders | 2,000 |
| Gross Revenue | $277,969.13 |
| Discounts | $21,068.31 |
| Refunds | $20,582.45 |
| Net Revenue | $236,318.37 |
| Total Costs | $179,984.54 |
| Total Profit | $56,333.83 |
| Profit Margin | 23.84% |
| Returned Orders | 144 |
| Return Rate | 7.20% |

Aggregate profit margin is calculated as:

`Total Profit / Total Net Revenue`

---

## Key Findings

### 1. Product Category Profitability

**Electronics** generated the strongest category performance with approximately
**$13,973 in profit** and a **31.13% profit margin**.

**Books** recorded the lowest margin at **11.94%**, followed by **Beauty at
17.39%**.

Shipping costs represented approximately **27.94% of gross revenue for Books**
and **24.79% for Beauty**, compared with only **13.50% for Electronics**.

High shipping-cost pressure is associated with weaker margins, particularly
for Books and Beauty.

### 2. Sales Channel Profitability

**Website** generated the highest total profit at approximately **$25,118**.

**Mobile App** achieved the highest profit margin at **29.76%**, followed by
**Website at 27.01%**.

**Marketplace** recorded the lowest margin at **13.03%**. Marketplace platform
fees represented approximately **13.79% of gross revenue**.

**Social Commerce** generated a **15.37% margin** and recorded the highest
channel return rate at **9.14%**.

Direct channels therefore retained a larger proportion of revenue as profit
than Marketplace and Social Commerce.

### 3. Return Performance

A total of **144 out of 2,000 orders were returned**, resulting in an overall
return rate of **7.20%**.

Recorded refunds totaled approximately **$20,582**.

Higher category return rates included:

- Electronics: **8.61%**
- Books: **8.37%**
- Clothing: **8.19%**

Social Commerce recorded the highest channel return rate at **9.14%**.

Return performance requires evaluation alongside profitability. Electronics,
for example, maintained the highest category profit margin despite a relatively
high return rate.

### 4. Marketing Performance

Aggregate marketing ratios were recalculated from total spend, clicks,
conversions, and attributed revenue rather than averaging monthly ratios.

| Platform | ROAS | CPC | CPA |
|---|---:|---:|---:|
| TikTok Ads | 24.02x | $0.15 | $3.06 |
| Influencer | 22.70x | $0.17 | $3.39 |
| Instagram Ads | 15.73x | $0.21 | $4.70 |
| Google Ads | 14.38x | $0.25 | $4.72 |
| Facebook Ads | 11.45x | $0.32 | $6.27 |
| Email Marketing | 4.81x | $0.94 | $17.86 |

**TikTok Ads** and **Influencer Marketing** generated the strongest historical
revenue efficiency.

**Email Marketing** recorded the weakest aggregate ROAS and the highest CPC
and CPA.

### 5. Marketing Budget Reduction

Total recorded marketing spend was approximately **$503,506.14**.

A 20% reduction requires approximately **$100,701.23**, leaving approximately
**$402,804.91** in the marketing budget.

Budget review was prioritized using the lowest historical platform-month ROAS.

The weakest observed period was **Email Marketing in December 2025**:

- Spend: **$1,796.66**
- Attributed Revenue: **$1,198.99**
- ROAS: **0.67x**

Additional lower-performing periods appeared across Email Marketing,
Facebook Ads, and Google Ads.

Historical ROAS ranking identified **34 platform-month observations for
review** to reach the approximately **$100,701 budget-reduction target**,
including a partial reduction in the final boundary observation.

Historical ROAS provides a prioritization framework rather than a causal
forecast of future revenue impact.

---

## Recommendations

### 1. Review Shipping Economics in Books and Beauty

Books and Beauty generated relatively weak margins while shipping represented
**27.94%** and **24.79% of gross revenue**, respectively.

Shipping rates, fulfillment arrangements, free-shipping thresholds, and
product-bundling opportunities should receive priority review.

Operational data should be used to quantify potential savings before
implementation.

### 2. Improve Marketplace and Social Commerce Economics

Marketplace generated only a **13.03% profit margin**, compared with
**29.76% for Mobile App** and **27.01% for Website**.

Marketplace platform fees represented approximately **13.79% of gross
revenue**.

Social Commerce also recorded the highest channel return rate at **9.14%**.

Marketplace pricing, promotions, product mix, platform fees, and appropriate
direct-channel opportunities should receive further review. Social Commerce
return drivers should also be investigated.

### 3. Prioritize Lower-ROAS Marketing Periods for Budget Review

The required 20% marketing reduction equals approximately **$100,701**.

Budget review should begin with historically lower-ROAS platform-month
combinations rather than applying equal reductions across every platform.

Weak Email Marketing periods should receive particular attention, followed
by lower-performing Facebook Ads and Google Ads periods where necessary.

Historically stronger TikTok Ads and Influencer Marketing activity should
receive lower priority for reductions.

Budget adjustments should be gradual, with continued monitoring of
conversions, attributed revenue, and profitability.

---



## Repository Structure

```text
ecommerce-profitability-analysis/
│
├── data/
│   ├── raw/
│   │   ├── orders.csv
│   │   ├── products.csv
│   │   └── marketing_spend.csv
│   │
│   └── processed/
│       ├── orders.csv
│       ├── products.csv
│       └── marketing.csv
│
├── notebooks/
│   ├── 01_data_preparation.ipynb
│   └── 02_profitability_analysis.ipynb
│
├── outputs/
│   ├── images/
│   └── tables/
│
└── README.md
