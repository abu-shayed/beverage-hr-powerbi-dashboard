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
|<img width="1919" height="1079" alt="sales_dashboard" src="https://github.com/user-attachments/assets/f868c6bc-052d-453d-a038-f0e622e54110" />
|<img width="1917" height="1079" alt="HR_Overview" src="https://github.com/user-attachments/assets/7ff2cb60-039b-41d8-8dba-a3e8c8e36c38" />
|<img width="1919" height="1079" alt="HR_Trends" src="https://github.com/user-attachments/assets/817f0d1a-a9f0-4d7f-9124-61d15f30c345" />
|


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
