# Portfolio BI Dashboards

A polished set of **Power BI** dashboards showcasing Sales, Marketing, and HR analytics using clean, reproducible datasets. Built for graduate‑level portfolio review.

## ✨ Highlights
- Interactive dashboards with slicers & drilldowns
- Clear DAX measures (YoY, CAC, ROI, Attrition)
- Mermaid architecture diagram
- Clean sample data (3 domains) + reproducible steps

## 🔗 Quick Links
- **Sales Dashboard:** `powerbi/Sales-Performance.pbix`
- **Marketing Funnel:** `powerbi/Marketing-Funnel.pbix`
- **HR Workforce:** `powerbi/HR-Workforce.pbix`

## 🖼️ Screenshots
> Put PNGs in `docs/screenshots/` and reference them below.
![Sales](docs/screenshots/sales-dashboard.png)
![Marketing](docs/screenshots/marketing-dashboard.png)
![HR](docs/screenshots/hr-dashboard.png)

## 🧠 DAX Cheatsheet
```DAX
Total Revenue := SUM(Sales[Revenue])
YoY Revenue % := DIVIDE(CALCULATE([Total Revenue], DATEADD('Calendar'[Date], -1, YEAR)), [Total Revenue]) - 1
CAC := DIVIDE(SUM(Marketing[Cost]), SUM(Marketing[Leads]))
Attrition Rate % := DIVIDE(SUM(HR[AttritionFlag]), DISTINCTCOUNT(HR[EmployeeID]))
![Sales Dashboard](docs/screenshots/sales-dashboard.png)
![License](https://img.shields.io/github/license/hemanthkori/portfolio-bi-dashboards)
![Last Commit](https://img.shields.io/github/last-commit/hemanthkori/portfolio-bi-dashboards)
![Issues](https://img.shields.io/github/issues/hemanthkori/portfolio-bi-dashboards)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)
