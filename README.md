# Beverage Sales & HR Analytics Dashboard (Power BI)

Two interactive Power BI dashboards built from one Excel workbook: **beverage sales performance** and **HR attrition analysis**.

## Business Questions

**Beverage Sales**
- How do revenue, units sold and average price vary by division, district and brand?
- What are the monthly and day-of-week revenue trends?
- Which brands generate the most revenue and profit?

**HR Analytics**
- How many employees are current vs terminated, and what is the termination rate?
- How do gender, education, job satisfaction and work-life balance relate to headcount and attrition?
- How do hiring, terminations and salary trend over time?
- How does salary relate to years at the company and total working experience?

## Dashboard Preview

| Beverage Sales | HR Overview | HR Trends |
|---|---|---|
<img width="1919" height="1079" alt="sales_dashboard" src="https://github.com/user-attachments/assets/1feb35e2-5ebc-4b78-b990-7e07c1555f11" /><img width="1919" height="1079" alt="HR_Trends" src="https://github.com/user-attachments/assets/6f0cd468-a55d-4589-8d45-ed7b9588bfc1" />
<img width="1917" height="1079" alt="HR_Overview" src="https://github.com/user-attachments/assets/d6ef3eb0-cb37-4dee-8667-ddbb2fc2f99a" />




## Key Insights
- [Insight 1, e.g. which brand leads on revenue and profit]
- [Insight 2, e.g. the month or weekday with the highest revenue]
- Termination rate is [x]% ([237] of [1,470] employees)
- [Insight 4, e.g. which satisfaction level has the most terminations]

| Table | Description |
|---|---|
| Data | Beverage sales transactions (date, brand, division, district, price, units) |
| Dates | Calendar table |
| Cost | Production cost per unit by brand |
| Dataset | HR records: 1,470 employees, 38 columns |

## Methodology
1. **Power Query:** set data types, removed formula columns, added `Status`, `Hire Quarter`, `Termination Quarter`, `Termination Month`, `Start Month`.
2. **Data model:** `Data` → `Dates` (many-to-one); `Dates` marked as date table; `Dataset` kept standalone.
3. **DAX measures:**
   - `Revenue = SUMX(Data, Data[Price per Unit] * Data[Units Sold])`
   - `Profit = [Revenue] - SUMX(Data, Data[Units Sold] * LOOKUPVALUE(Cost[Cost per Unit], Cost[Beverage Brand], Data[Beverage Brand]))`
   - `Termination Rate = DIVIDE([Terminated], [Total Employees])`
4. **Design:** custom backgrounds, themed colour palettes, page navigation, slicers on every page.

## Tools
Power BI Desktop · Power Query · DAX · Excel

## Repository Structure
```
├── data/        Final_Assignment.xlsx
├── images/      dashboard screenshots
├── report/      Beverage_Sales_and_HR_Analytics_Dashboard.pbix + PDF export
└── README.md
```

## Author
**Abu Shayed**,www.linkedin.com/in/abu-shayed-data/ · [abushayed.ba@gmail.com]
