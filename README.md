# Beverage Sales & HR Analytics Dashboard (Power BI)

Two interactive Power BI dashboards built from one Excel workbook: **beverage sales performance** and **HR attrition analysis**.

![Beverage Sales](images/beverage_sales.png)

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
| ![<img width="1919" height="1079" alt="sales_dashboard" src="https://github.com/user-attachments/assets/819e68f5-2e36-4ca1-9910-edfef8fbb681" />
](images/beverage_sales.png) 
| ![<img width="1917" height="1079" alt="HR_Overview" src="https://github.com/user-attachments/assets/632f5313-caaf-4dc9-97b0-5f9cfcf9433a" />
](images/hr_overview.png) | ![<img width="1919" height="1079" alt="HR_Trends" src="https://github.com/user-attachments/assets/274cc981-f459-405f-8a57-0e8a7f6b9cfc" />
](images/hr_trends.png) |

## Key Insights
- [Insight 1, e.g. which brand leads on revenue and profit]
- [Insight 2, e.g. the month or weekday with the highest revenue]
- Termination rate is [x]% ([237] of [1,470] employees)
- [Insight 4, e.g. which satisfaction level has the most terminations]

## Data
Source file: `[2026-10-18T11-07-44.076Z-2026-09-09T09-42-29.602Z-2026-08-18T12-35-28.112Z-2026-07-16T13-47-32.018Z-Final Assignmen (1).xlsx](https://github.com/user-attachments/files/34115850/2026-10-18T11-07-44.076Z-2026-09-09T09-42-29.602Z-2026-08-18T12-35-28.112Z-2026-07-16T13-47-32.018Z-Final.Assignmen.1.xlsx)
`

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
