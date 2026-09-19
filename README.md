# Walmart Market Business Intelligence Dashboard (Power BI)

An end-to-end Power BI report for a multinational retailer operating in Canada, Mexico and the USA. It tracks transactions, profit, returns and revenue against targets, drills from country down to store city, and benchmarks every KPI against the previous month.

## Business Questions

1. How do Total Transactions, Profit, Returns and Revenue compare with last month and with target?
2. Which countries, states and store cities drive performance?
3. Which product brands deliver the most volume and margin, and which carry high return rates?
4. What should leadership act on this month?

## Report Structure

- Topline Performance: executive dashboard with KPI cards, brand matrix, map, treemap, weekly revenue and a revenue vs target gauge.
- Notes: written market report and insights, with bookmark buttons that jump back to the supporting visuals.
- DAXF Verify: validation page that reconciles Total Returns, Last Month Returns and Revenue, and checks Revenue Target by Year, Quarter, Month and Day.

## Key Features

### Brand Matrix (Top 30 brands via Top N filter)
- Columns: Total Transactions, Total Profit, Profit Margin and Return Rate by product brand.
- Data bars on Transactions.
- White-to-green color scale on Profit Margin.
- White-to-red color scale on Return Rate.

### KPI Cards (current month vs last month)
- Transactions, Profit and Returns, each with a trend line and a comparison value.
- Returns uses "lower is better" logic, so an increase shows in red.

### Geographic Analysis
- Map of Total Transactions by store city, with a country slicer (USA, Mexico, Canada).
- Treemap with drill-down from Country to State to City.

### Weekly Revenue Trend
- Column chart of Total Revenue by week, filtered to 1998 with a page-level filter on Year.

### Revenue vs Target Gauge
- Total Revenue against Revenue Target for the latest period, suited to executive summary views.

### Interactivity
- Bookmarks for the key insights and button navigation between pages.
- Visual interactions turned off where cross-filtering would mislead.

## Data Model

The model is a star schema. Two fact tables (Transaction_Data and Return_Data) connect to the Products, Calendar, Stores and Regions dimensions, and a separate Measure table holds the DAX.

- Transaction_Data (fact): quantity, stock date, transaction date, and product, store and customer keys.
- Return_Data (fact): quantity, return date, and product and store keys.
- Products (dimension): product brand.
- Stores (dimension): store country, state and city.
- Regions (dimension): sales region and sales district.
- Calendar (date dimension): Start of Week, Start of Month, and a Year / Quarter / Month / Day hierarchy.
- Measure (measure table): all DAX measures.

## DAX Measures

- Total Transactions: count of transactions in the current filter context.
- Last Month Transactions: the same measure shifted to the previous month.
- Total Profit and Last Month Profit: profit, and profit for the previous month.
- Profit Margin: profit as a share of revenue.
- Total Returns and Last Month Returns: returned units, and returned units for the previous month.
- Return Rate: returns as a share of transactions.
- Total Revenue: revenue in the current filter context.
- Revenue Target: the target used by the gauge.

## Key Insights

- Portland passed 1,000 sales in December, making it a top-performing city.
- The top 10 product brands generate about a quarter of total revenue and exceed the revenue target.
- Current-month transactions (18,325, up 5.7%) and profit ($71,682, up 5.6%) beat the previous month, but returns rose 2.9% (496 vs 482), which points to a product or service quality issue worth investigating.
- Mexico outperformed the previous month on both profit and revenue and warrants closer review and investment.

The data covers 1997-1998, so "current month" means the latest month in the dataset (December 1998). The report simulates a live market-reporting workflow.

## Tools and Skills

Power BI Desktop, DAX, Data Modeling, Conditional Formatting, Drill-Down, Slicers, Bookmarks, Data Storytelling.

