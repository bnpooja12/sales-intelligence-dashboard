# 📊 Sales Intelligence Dashboard

> Advanced data analytics project: transforming 10,000+ messy sales records into actionable revenue intelligence using Excel and Power BI — with a 15% revenue opportunity discovered in the process.

[![Power BI](https://img.shields.io/badge/Built_with-Power_BI-F2C811?style=for-the-badge&logo=powerbi)](https://powerbi.microsoft.com)
[![Excel](https://img.shields.io/badge/Excel-Advanced_Analytics-217346?style=for-the-badge&logo=microsoftexcel)](https://microsoft.com/excel)
[![Certificate](https://img.shields.io/badge/Microsoft_PL--300_Prep-Coursera_Certified-0078D4?style=for-the-badge)](https://coursera.org/verify/professional-cert/CRQLEVPD3G34)
[![Status](https://img.shields.io/badge/Status-Complete-28a745?style=for-the-badge)]()

---

## 🎯 Business Context

Every sales organisation has the same problem: data exists everywhere — CRM exports, spreadsheets, regional reports — but nobody has a clear answer to:

- *Which product lines are actually growing vs. coasting on brand inertia?*
- *Is Q4 performance genuinely strong, or just seasonal noise?*
- *Which regions are underperforming relative to their market size?*

This project takes a raw 10,000+ row sales dataset and builds the dashboards and analysis to answer exactly those questions — ending with a quantified revenue opportunity.

---

## 📊 Key Results

| Metric | Value |
|--------|-------|
| Dataset Size | **10,000+ records** across regions, products, periods |
| Revenue Opportunity Found | **15%** uplift identified from segmentation analysis |
| Reporting Time Reduction | **40%** through automated dashboard vs. manual reports |
| Data Quality Issues Resolved | **Standardised** inconsistent formats, nulls, duplicates |
| Dashboard Views Built | **5** interactive Power BI views |

---

## 🗂️ Project Structure

```
sales-intelligence-dashboard/
├── README.md                              ← You are here
├── data/
│   ├── raw-sales-data.xlsx               ← Original dataset (anonymised)
│   └── cleaned-sales-data.xlsx           ← Post-ETL clean version
├── excel-analysis/
│   ├── data-cleaning-log.xlsx            ← All transformations documented
│   ├── pivot-analysis.xlsx               ← Pivot tables + Excel charts
│   └── formula-reference.md             ← Key formulas used + explanations
├── powerbi/
│   ├── sales-dashboard.pbix             ← Full Power BI report file
│   └── dashboard-screenshots/           ← PNG exports of all 5 views
│       ├── 01-executive-overview.png
│       ├── 02-regional-breakdown.png
│       ├── 03-product-performance.png
│       ├── 04-trend-analysis.png
│       └── 05-opportunity-map.png
└── insights/
    └── findings-report.md                ← Written analysis + recommendations
```

---

## 🔧 Methodology: Step by Step

### Phase 1 — Data Ingestion & Assessment
```
Raw dataset received: 10,247 rows × 14 columns
Issues identified:
  - 340 rows with null values in Revenue column
  - Inconsistent date formats (DD/MM/YYYY vs MM-DD-YY)
  - Product names with 12 different spelling variants
  - 83 duplicate transaction IDs
  - Region codes missing in 5% of rows
```

### Phase 2 — Data Cleaning (Excel)

| Issue | Resolution | Tool |
|-------|-----------|------|
| Null revenue rows | Flagged + excluded from main analysis; kept in separate audit tab | Excel Filter + ISBLANK() |
| Date format inconsistency | Standardised to ISO 8601 (YYYY-MM-DD) using TEXT() | Excel TEXT() + DATEVALUE() |
| Product name variants | Lookup table created; VLOOKUP mapped all variants to canonical names | VLOOKUP + IF() |
| Duplicate IDs | Identified with COUNTIF(), reviewed, removed confirmed duplicates | COUNTIF() + Remove Duplicates |
| Missing regions | Filled from secondary ZIP-to-Region reference table | VLOOKUP + IFERROR() |

**Outcome:** Clean dataset of **9,804 valid rows**, with all transformations logged for reproducibility.

### Phase 3 — Exploratory Analysis (Excel Pivot Tables)

Built 8 pivot tables to understand the data before building dashboards:

1. **Revenue by Region × Quarter** — identified Q3 regional anomaly
2. **Product Category Performance YoY** — found 2 declining SKUs masked by category growth
3. **Customer Segment × Average Order Value** — segmented high-value vs volume buyers
4. **Rep Performance Distribution** — top 20% generating 61% of revenue
5. **Seasonality Pattern (monthly)** — confirmed Q4 spike, but also found Q2 dip hypothesis
6. **Return/Refund Rate by Product** — 1 product line with 3× avg return rate
7. **New vs Returning Customer Revenue Split** — retention rate lower than industry benchmark
8. **Deal Size Distribution (histogram)** — bimodal: clear SMB vs Enterprise segments

### Phase 4 — Power BI Dashboard (5 Views)

**View 1: Executive Overview**
- Total Revenue (current period vs prior)
- Revenue vs Target (gauge chart)
- Top 5 products by revenue (bar)
- KPI cards: deals closed, average deal size, win rate

**View 2: Regional Breakdown**
- Choropleth map: revenue density by geography
- Drill-down: region → state → city
- Period comparison slider (YoY / QoQ)
- Underperforming regions highlighted with conditional formatting

**View 3: Product Performance**
- Revenue contribution by product category (treemap)
- Product growth rate scatter plot (growth vs volume)
- Quadrant analysis: Stars / Cash Cows / Question Marks / Dogs
- Declining product alert cards

**View 4: Trend Analysis**
- Revenue trend line (24-month rolling)
- Seasonality decomposition
- Moving averages (30-day, 90-day)
- Forecast projection (3-month forward, confidence interval)

**View 5: Revenue Opportunity Map**
- Segment gap analysis: actual vs benchmark revenue per region
- Product penetration rate by region (heatmap)
- **Opportunity sizing: 15% uplift = ~$2.3M annualised**

---

## 💡 Key Findings & The 15% Opportunity

### Finding 1: Hidden Regional Underperformance
The East region appeared healthy in aggregate but was being carried by a single metro. Removing that outlier revealed 40% lower revenue per sales rep compared to the West. Root cause: product mix — East was selling lower-margin SKUs at higher volume.

**Recommendation:** Product training + mix incentives for East region reps. Conservative uplift estimate: 8–10%.

### Finding 2: Two Product Lines Masking Decline
"Category B" showed 12% growth overall — but this was entirely driven by one new SKU launched mid-year. Three legacy SKUs in the same category were declining at 18–22% YoY, invisible in category-level reporting.

**Recommendation:** Immediate review of legacy SKU roadmap. Either invest in refresh or sunset gracefully to free up sales effort. Estimated revenue recapture from reallocated sales effort: 3–5%.

### Finding 3: Bimodal Deal Size = Two Products Needed
Deal size histogram revealed a clear bimodal distribution: peaks at $2K–5K (SMB) and $40K–80K (Enterprise). Sales collateral, pricing pages, and sales process were built for one buyer type. Enterprise deals were being handled with SMB-style collateral.

**Recommendation:** Segment sales process, collateral, and CS handoff by deal size. Enterprise deals need custom decks; SMB deals need self-serve. Estimated conversion rate improvement: 2–3%.

**Combined opportunity: ~15% revenue uplift** from regional mix optimisation + SKU rationalisation + segmentation.

---

## 🛠️ Technical Skills Demonstrated

**Excel:**
`VLOOKUP` · `INDEX/MATCH` · `SUMIFS` · `COUNTIFS` · `TEXT` · `DATEVALUE` · `IFERROR` · `Pivot Tables` · `Pivot Charts` · `Conditional Formatting` · `Data Validation` · `Power Query (M)`

**Power BI:**
`Data Modelling` · `DAX measures` · `Calculated columns` · `Relationships` · `Slicers` · `Cross-filtering` · `Drill-through` · `Custom visuals` · `Row-level security` · `Published reports`

**Analytical:**
`EDA` · `Segmentation Analysis` · `Trend Analysis` · `Outlier Detection` · `Opportunity Sizing` · `Variance Analysis` · `KPI Definition`

---

## 📬 Author

**BN Pooja** — Product Manager × Data Analyst

[![Portfolio](https://img.shields.io/badge/Portfolio-bnpooja12.github.io-c8410a?style=flat-square)](https://bnpooja12.github.io/portfolio/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-BN_Pooja-0077B5?style=flat-square&logo=linkedin)](https://linkedin.com/in/b-n-pooja-13279b280/)
[![Certification](https://img.shields.io/badge/Microsoft_Power_BI_Certified-Verify-F2C811?style=flat-square)](https://coursera.org/verify/professional-cert/CRQLEVPD3G34)

---

*Microsoft Power BI Data Analyst Professional Certificate · Coursera · Jan 2026*
