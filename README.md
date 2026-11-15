
# Revenue Leakage & Strategic Account Churn Analysis | Power BI

## Project Overview

This Power BI project analyzes **$52.74 million in lost Annual Recurring Revenue (ARR)** to identify the customer segments, churn reasons, and industries associated with the greatest revenue losses.

Using DAX measures, interactive dashboards, and an AI-assisted decomposition tree, the analysis explores revenue leakage patterns and provides data-driven recommendations for improving customer retention.

## Tools & Skills

- Power BI Desktop
- DAX (Data Analysis Expressions)
- Data Visualization
- Interactive Dashboard Design
- AI-Assisted Decomposition Tree Analysis
- Customer Churn Analysis
- Business Intelligence Reporting
- Strategic Business Recommendations

---

## Business Objectives

1. Measure total lost Annual Recurring Revenue.
2. Identify customer segments contributing the most revenue loss.
3. Analyze the leading recorded reasons for customer churn.
4. Determine which industries experience the highest revenue losses.
5. Recommend strategies to reduce revenue leakage and improve retention.

---

## Dashboard Overview

### Page 1: Revenue Leakage Overview & AI Analysis

This dashboard provides a high-level overview of revenue leakage using KPI cards and an AI-assisted decomposition tree.

**Key Performance Indicators**

| KPI | Value |
|---|---:|
| Total Lost ARR | $52,741,848 |
| Average Pre-Churn Health Score | 64.6 |
| Average Customer Tenure | 27.0 Months |
| Enterprise Lost ARR % | 72.3% |

**Dashboard Features**

- Four DAX-based KPI measures
- AI-assisted decomposition tree
- Interactive Industry, Region, and Competitor slicers
- Detailed exploration of Enterprise revenue-loss paths

### Page 2: Key Insights & Strategic Recommendations

This page summarizes the findings from the decomposition tree and presents strategic recommendations for reducing revenue leakage.

### Page 3: Customer Churn & Revenue Drivers

This dashboard compares lost ARR across subscription tiers, industries, and churn reasons.

**Visualizations**

- Lost ARR by Industry
- Lost ARR by Subscription Tier
- Lost ARR by Churn Reason
- Interactive Subscription Tier slicer

---

## Key Business Findings

### 1. Enterprise Revenue Exposure

Enterprise customers account for **$38.14M (72.3%)** of total lost ARR.

| Subscription Tier | Lost ARR |
|---|---:|
| Enterprise | $38.14M |
| Mid-Market | $10.53M |
| SMB | $4.07M |

Enterprise represents the largest revenue-loss segment, highlighting the importance of proactive high-value customer retention.

### 2. Leading Churn Reasons

| Churn Reason | Lost ARR |
|---|---:|
| Price | $17.7M |
| Product Bugs | $14.5M |
| Competitor | $14.0M |
| Poor Support | $6.6M |

Price and Product Bugs represent the two largest recorded churn reasons by lost ARR, suggesting opportunities to investigate pricing competitiveness and product reliability.

### 3. Industry Revenue Concentration

| Industry | Lost ARR |
|---|---:|
| FinTech | $13.4M |
| E-Commerce | $13.3M |
| SaaS B2B | $10.3M |
| Healthcare | $10.3M |
| Logistics | $5.5M |

FinTech and E-Commerce together account for approximately **50.6% of total lost ARR**, highlighting opportunities for industry-specific retention strategies.

### 4. AI-Assisted Enterprise Revenue Leakage Analysis

The decomposition tree identified the following progressively narrower revenue-loss path:

| Decomposition Stage | Lost ARR |
|---|---:|
| Enterprise | $38.14M |
| No Support Escalation | $17.82M |
| Core Software | $8.58M |
| Annual Billing | $4.41M |
| Price | $1.65M |
| No Recorded Competitive Destination | $791.5K |
| E-Commerce | $256.9K |

These values represent nested segments within the same revenue-loss path and should not be added together.

The findings highlight substantial Enterprise revenue exposure among accounts without recorded support escalations.

---

## Strategic Recommendations

**1. Strengthen Enterprise Customer Retention**

Prioritize proactive account reviews and personalized retention strategies for high-value Enterprise customers.

**2. Monitor Customer Health and Engagement**

Track customer health scores and product usage, where available, to identify early signs of disengagement.

**3. Improve Renewal Management**

Initiate renewal discussions approximately three months before contract expiration to address concerns and demonstrate product value.

**4. Review Pricing and Product Reliability**

Investigate pricing concerns and recurring product issues. Consider flexible subscription packages for price-sensitive customers.

**5. Develop Industry-Specific Retention Strategies**

Conduct targeted investigations within FinTech and E-Commerce to identify customer needs and opportunities to reduce revenue loss.

---

## DAX Measures

### Total Lost ARR

```dax
Total Lost ARR =
SUM('AuraTech Advanced Revenue_Leakage'[Lost_ARR])
```

### Average Customer Health Score

```dax
Average Customer Health Score =
AVERAGE(
    'AuraTech Advanced Revenue_Leakage'[Health_Score_Pre_Churn]
)
```

### Average Customer Lifespan

```dax
Average Customer Lifespan =
AVERAGE(
    'AuraTech Advanced Revenue_Leakage'[Account_Tenure_Months]
)
```

### Enterprise Lost ARR %

```dax
Enterprise Lost ARR % =
DIVIDE(
    CALCULATE(
        [Total Lost ARR],
        'AuraTech Advanced Revenue_Leakage'[Subscription_Tier] = "Enterprise"
    ),
    CALCULATE(
        [Total Lost ARR],
        REMOVEFILTERS(
            'AuraTech Advanced Revenue_Leakage'[Subscription_Tier]
        )
    ),
    0
)
```

---

## Data Model

The report uses a single-table Power BI data model.

**Dataset Fields**

- Account_Region
- Account_Tenure_Months
- Billing_Frequency
- Competitive_Destination
- Health_Score_Pre_Churn
- Industry_Vertical
- Lost_ARR
- Primary_Churn_Reason
- Product_Category
- Subscription_Tier
- Support_Escalation_Path

---

## Analytical Methodology

1. Developed DAX measures to calculate business KPIs.
2. Analyzed revenue loss across subscription tiers, industries, and churn reasons.
3. Used an AI-assisted decomposition tree to investigate high-value Enterprise revenue-loss paths.
4. Configured interactive slicers for segment-level exploration.
5. Translated findings into actionable business recommendations.

---

## Analytical Limitations

- The analysis focuses on lost ARR rather than overall customer churn rates.
- The findings identify associations and do not establish causation.
- No recorded support escalation does not necessarily mean the customer never contacted support.
- Customer health scores are descriptive indicators rather than validated churn predictions.
- Static insight text does not automatically change with slicer selections.
- Strategic recommendations require further validation before implementation.


---

## Conclusion

This project demonstrates how Power BI, DAX, interactive dashboards, and AI-assisted decomposition analysis can be used to investigate revenue leakage and customer churn.

The findings highlight significant revenue exposure among Enterprise customers, with pricing concerns, product reliability, and industry concentration emerging as important areas for further investigation.

By combining technical analysis with strategic business recommendations, the project demonstrates the ability to translate complex business data into actionable insights that support customer retention planning.
