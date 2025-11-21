# Sales Data Analysis Dashboard

**Project:** Sales Data Analysis Dashboard
**Description:** Interactive Power BI dashboard that visualizes sales performance by product, city, month, and time-of-day. Includes KPIs, trend charts, category breakdowns and a map view.

---

## Files

* Dataset (CSV): `/mnt/data/Sales Data Analysis.csv`
* Dashboard preview image: `/mnt/data/sa.png`

> If you publish this repo to GitHub, replace the local dataset path above with a relative path (for example `data/Sales Data Analysis.csv`) and add the `data/` file to the repository or a Git LFS solution if the file is large.

---

## How to open & reproduce (Power BI)

1. Open **Power BI Desktop**.
2. Get Data → **Text/CSV** → select the dataset: `/mnt/data/Sales Data Analysis.csv`.
3. In **Power Query Editor** clean and transform as needed (see *Power Query notes* below). Click **Close & Apply**.
4. Recreate visuals (or load the provided PBIX if you include one):

   * Line chart: Sales by Month
   * Column chart: Sales by City
   * Bar chart: Sum of Sales by Product
   * Donut chart: Category share
   * Pie chart: Sales by Time of Day
   * KPI cards: Current month sales, City sales vs. goal
   * Map (or Filled Map): Geo sales distribution
5. Add tooltips, slicers, and drill-through pages for detail.

---

## Power Query (M) notes

* Steps commonly used:

  * `Promote Headers`
  * `Change Type` for dates/numeric columns
  * `Split Column` (if product or city combined)
  * `Group By` to create summary tables for visuals
  * `Merge Queries` when joining lookup tables (products, cities)
* Suggested M functions to include:

  * Calculated date columns (Month, Year, MonthName)
  * Normalize city/product names (Trim, Lowercase)
  * Remove duplicates and null rows

---

## DAX measures (suggested)

* `Total Sales = SUM('Sales'[Amount])`
* `Sales This Month = CALCULATE([Total Sales], FILTER(ALL('Date'), 'Date'[Month] = MONTH(TODAY()) && 'Date'[Year] = YEAR(TODAY())))`
* `Sales vs Goal = DIVIDE([Total Sales], [Target Sales])`
* Time-of-day buckets using `HOUR('Sales'[Time])` and `SWITCH` or `IF` logic

---

## Data schema (example)

* `Date` — transaction date
* `Time` — transaction time (or datetime)
* `City` — customer city
* `Product` — product name
* `Category` — product category
* `Quantity` — units sold
* `Amount` — sales value (INR)

Adjust column names to match the CSV headers.

---

## Key insights (to highlight in README / project summary)

* Top products by revenue (e.g., MacBook Pro, iPhone, ThinkPad)
* Highest-performing cities and underperforming regions
* Monthly seasonality and end-of-month spikes
* Peak purchasing times (morning/afternoon/evening)
* Progress toward monthly/quarterly sales goals

---

## Suggested repository structure

```
/ (root)
├─ README.md
├─ data/
│  └─ Sales Data Analysis.csv
├─ images/
│  └─ sa.png
├─ pbix/
│  └─ Sales_Data_Analysis.pbix
└─ docs/
   └─ project_report.pdf
```

---

## License

This project is available under the **MIT License** — feel free to reuse and adapt.

---

If you want, I can:

* Produce a ready-to-upload `README.md` file in the repo structure above.
* Create a cleaned `data/` CSV (with cleaned column names) and save it for you.
* Draft a short `project_report.pdf` or a resume-ready project blurb.

Which one should I create next? (I can directly reference your local dataset at `/mnt/data/Sales Data Analysis.csv` when producing files.)
# Company_Attendance_Report_Dashboard
