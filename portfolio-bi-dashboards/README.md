# Portfolio BI Dashboards

A collection of **Power BI** dashboards suitable for graduate-level portfolio work.  
It includes clean sample datasets (Sales, Marketing, HR), suggested visuals, DAX measures, and publishing instructions.

## 🔧 What’s inside
- **/data** – clean CSVs for three domains (sales, marketing, HR)
- **/powerbi** – put your `.pbix` files here (after you build them in Power BI Desktop)
- **/docs/screenshots** – add PNGs/JPGs of your dashboards here for the README
- **/docs/architecture.mmd** – Mermaid diagram of the analytics flow
- **LICENSE** – MIT

## 📊 Dashboard Modules (recommended)
1. **Sales Performance**
   - Visuals: KPI cards (Revenue, Units, Margin), Time-series line chart, Region map, Product hierarchy drill-down, Decomposition tree
   - DAX ideas:
     ```DAX
     Total Revenue := SUM(Sales[Revenue])
     Total Units   := SUM(Sales[Units])
     Margin %      := DIVIDE(SUM(Sales[Revenue]) - SUM(Sales[COGS]), SUM(Sales[Revenue]))
     YoY Revenue % := DIVIDE(
        CALCULATE([Total Revenue], DATEADD('Calendar'[Date], -1, YEAR)),
        [Total Revenue]
     ) - 1
     ```
2. **Marketing Funnel & ROI**
   - Visuals: Funnel chart (Impressions → Clicks → Leads → Opportunities → Wins), Cost vs. CAC by channel, ROI scatter
   - DAX ideas:
     ```DAX
     Total Cost := SUM(Marketing[Cost])
     CAC := DIVIDE([Total Cost], SUM(Marketing[Leads]))
     ROI := DIVIDE(SUM(Marketing[RevenueAttributed]) - [Total Cost], [Total Cost])
     ```
3. **HR & Workforce**
   - Visuals: Headcount by dept, Attrition rate, Hiring pipeline, Diversity breakdown, Tenure distribution
   - DAX ideas:
     ```DAX
     Headcount := DISTINCTCOUNT(HR[EmployeeID])
     Attrition Rate % := DIVIDE(SUM(HR[AttritionFlag]), [Headcount])
     Avg Tenure (yrs) := AVERAGE(HR[TenureYears])
     ```

## 🚀 Quickstart
1. Open **Power BI Desktop**.
2. **Get Data → Text/CSV** and load the 3 CSVs from `/data`.
3. Create a **Calendar table** and relate it to date columns in Sales/Marketing/HR.
4. Build the visuals listed above. Save the file as:
   - `powerbi/Sales-Performance.pbix`
   - `powerbi/Marketing-Funnel.pbix`
   - `powerbi/HR-Workforce.pbix`
5. Add screenshots to `/docs/screenshots` and embed them in this README.
6. (Optional) Publish to Power BI Service and add links.

## 🧪 Data Notes
- The CSVs are **synthetic**, reproducible, and shaped for typical BI modeling:
  - **Sales** columns: Date, Region, ProductCategory, Product, Units, Revenue, COGS, Channel
  - **Marketing** columns: Date, Channel, Impressions, Clicks, Leads, Opportunities, Wins, Cost, RevenueAttributed
  - **HR** columns: EmployeeID, Gender, Ethnicity, Dept, Role, Location, TenureYears, AttritionFlag, HireDate

## 🧭 Folder Structure
```
portfolio-bi-dashboards/
├─ data/
│  ├─ sales.csv
│  ├─ marketing.csv
│  └─ hr.csv
├─ powerbi/                # place your .pbix files here after building
├─ docs/
│  ├─ architecture.mmd
│  └─ screenshots/
├─ LICENSE
└─ README.md
```

## 🖼️ Screenshots
Place images in `/docs/screenshots` and link them here, e.g.:
```
![Sales Dashboard](docs/screenshots/sales-dashboard.png)
```

## 📜 License
MIT © 2025 Hemanth Kori