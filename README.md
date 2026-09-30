# Large Group Health Insurance Sales Closing Ratio

## Project Overview

This project analyzes a synthetic dataset of qualified Large Group health insurance sales opportunities to investigate a decline in sales close rate from **55% in 2025 to 25% in 2026**.

The objective was to identify the factors most strongly associated with **Closed-Won vs. Closed-Lost opportunities**, evaluate competing business hypotheses, and develop an actionable recommendation for improving sales performance.

The analysis was designed as an executive decision-support exercise rather than a purely predictive modeling project.

---

## Business Question

**What factors are most strongly associated with the decline in Large Group sales close rate, and what actions should sales leadership test to improve performance?**

The analysis evaluated three primary hypotheses:

1. **Personnel / Relationship Disruption**  
   Sales team personnel changes may have disrupted established customer relationships.

2. **Changing Opportunity & Engagement Mix**  
   Changes in how sales teams engaged with qualified opportunities may be associated with lower close rates.

3. **Relative Pricing Deterioration**  
   Higher rate increases relative to competitors may have reduced win probability.

---

## Data

The project uses a **synthetic dataset** created specifically for analytical demonstration.

- **200 qualified Large Group sales opportunities**
- **100 opportunities in 2025**
- **100 opportunities in 2026**
- One row represents one qualified sales opportunity
- Binary outcome:
  - `Won = 1`
  - `Lost = 0`
- Dataset includes both **numeric measures** and **categorical dimensions**

The synthetic data incorporates business rules covering areas such as:

- Sales activity
- Meaningful customer engagement
- Low-touch activity
- Relationship maturity
- Lead source
- Market segment
- Geography
- Salesperson
- Pricing
- Competitive rate changes
- Opportunity characteristics

No confidential or proprietary Wellmark data was used.

---

## Analytical Approach

The analysis followed a structured exploratory workflow:

### 1. Define the Analytical Unit and Outcome

The analytical unit is one qualified Large Group sales opportunity.

The dependent variable is the sales outcome:

`Closed-Won = 1`  
`Closed-Lost = 0`

### 2. Broad Exploratory Data Analysis

All available attributes were screened before selecting variables for deeper investigation.

For **numeric measures**, Pearson correlation with the binary Won/Lost outcome was used. With a binary outcome, this is equivalent to point-biserial correlation.

For **categorical dimensions**, Cramér's V was used to measure the strength of association with Won/Lost outcomes.

Associations were calculated separately for 2025 and 2026 to identify attributes whose relationship with winning changed most substantially.

### 3. Hypothesis Investigation

Signals identified during EDA were evaluated against the three competing business hypotheses.

### 4. Executive Recommendation

The strongest actionable signals were translated into recommendations that could be tested through a controlled sales-process intervention.

---

## Key Finding: Meaningful Sales Engagement

The broad EDA identified **Meaningful Engagement Rate** as the largest year-over-year change in association with winning.

Meaningful Engagement Rate was calculated as:

**Meaningful Engagements / Total Sales Activities**

Meaningful engagements include higher-value interactions such as:

- In-person meetings
- Lunches
- Microsoft Teams meetings
- Phone calls
- Drop-ins
- Customer entertainment

Low-touch activities include:

- Emails
- Voicemails
- Text messages

The analysis indicated that **how the sales team engaged was more informative than simply how much activity occurred**.

---

## 2026 Engagement Analysis

The 2026 opportunities were ranked by Meaningful Engagement Rate and divided into approximately equal thirds.

| Meaningful Engagement Level | Close Rate |
|---|---:|
| Low | 13.5% |
| Medium | 16.1% |
| High | 46.9% |

The highest-engagement third of opportunities closed at approximately **47%**, compared with approximately **14–16%** among the lower two groups.

Won opportunities also averaged:

- **5.00 meaningful engagements per opportunity**
- **6.92 low-touch activities per opportunity**

Lost opportunities averaged:

- **3.35 meaningful engagements per opportunity**
- **7.59 low-touch activities per opportunity**

This suggests the opportunity may not be simply generating more sales activity, but shifting activity toward higher-value customer engagement.

---

## Pricing Analysis

Relative pricing was retained as a secondary factor.

In 2026, opportunities were grouped by Wellmark's rate differential relative to competitors:

| Competitive Rate Differential | Close Rate |
|---|---:|
| ≤ 1.5 points | 29.2% |
| 1.5–3.0 points | 28.2% |
| > 3.0 points | 18.9% |

The results suggest that larger competitive pricing gaps were associated with lower close rates, particularly above a three-percentage-point differential.

However, substantial overlap remained between Won and Lost opportunities, indicating that pricing alone did not explain the decline.

---

## Relationship Analysis

The personnel-disruption hypothesis was not supported as the primary explanation.

In 2026:

- **Inherited relationships:** 37.5% close rate
- **Non-inherited relationships:** 16.7% close rate

Relationship maturity also showed:

- **Established:** 40.0%
- **Developing:** 20.0%
- **New:** 14.3%

Inherited and established relationships performed better rather than worse, so the available evidence did not support personnel disruption as the primary driver of the close-rate decline.

---

## Recommendation

### Primary Recommendation

Pilot a Large Group sales-process intervention designed to increase **meaningful customer engagement**, using the observed benchmark of approximately **5+ meaningful activities per qualified opportunity**.

The objective should not simply be increasing total sales activity. The intervention should focus on increasing the proportion of activity represented by direct, higher-value customer interactions.

### Secondary Recommendation

Continue monitoring relative pricing, particularly when Wellmark's rate increase exceeds competitors by more than approximately three percentage points.

### Validation

These findings represent **associations, not proof of causation**.

A controlled pilot should compare comparable opportunities or seller groups and measure:

- Meaningful Engagement Rate
- Meaningful Engagements per opportunity
- Close Rate
- Competitive pricing differential

The intervention should be validated before being scaled broadly.

---

## Future Analytical Opportunities

With expanded historical and CRM data, the analysis could be extended through:

- **Logistic regression** to evaluate engagement, pricing, relationships, lead source, segment, and salesperson simultaneously
- **Tree-based machine learning models** to identify nonlinear relationships and interactions
- **CRM text analytics** to analyze notes and activity descriptions for patterns distinguishing Closed-Won from Closed-Lost opportunities
- **Power BI monitoring** of validated engagement, pricing, opportunity-mix, and close-rate measures
- Additional CRM variables including opportunity age, stage progression, decision-maker engagement, competitors, and reason lost

---

## Tools

- Python
- pandas
- NumPy
- SciPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- Microsoft Excel
- PowerPoint

---

## Repository Contents

```text
Large-Group-Health-Insurance-Sales-Closing-Ratio/
│
├── README.md
├── data/
│   └── synthetic_large_group_opportunities.csv
│
├── notebooks/
│   └── large_group_sales_analysis.ipynb
│
└── presentation/
    └── large_group_close_rate_analysis.pdf
