# ShopperLens: Customer Segmentation with Machine Learning and Power BI

Groups mall customers into clear, marketing-ready segments based on their income and spending, then presents the results in an interactive Power BI dashboard.

## Problem
A mall wants to understand its customers instead of marketing to everyone the same way. The question: **which natural groups of customers exist, and how should each group be targeted?**

## Dataset
**Mall Customers** dataset: 200 customers, 5 columns. There are no missing values or duplicates.

| Column | Description |
|---|---|
| CustomerID | Unique customer number |
| Gender | Female / Male |
| Age | 18–70 |
| Annual Income (k$) | 15–137 |
| Spending Score (1-100) | Assigned by the mall from purchase behaviour |

## Tools
Python (pandas, NumPy, scikit-learn, matplotlib, seaborn, Plotly), Google Colab, Power BI, DAX

## Approach
1. **Exploratory analysis:** distributions, outliers, age groups, correlations, and a density map that shows natural customer groups.
2. **Clustering:** K-Means on Annual Income and Spending Score, with **k = 5** chosen by the elbow method. A second model adds Age (3D clustering).
3. **Segment profiling:** clusters named from their centres, then compared with boxplots, a heatmap and a radar chart.
4. **Dashboard:** results exported to CSV and visualised in a 2-page Power BI report with DAX measures.

## Results

| Segment | Customers | Avg Age | Avg Income (k$) | Avg Spending | Suggested strategy |
|---|---|---|---|---|---|
| Premium Spenders | 39 | 32.7 | 86.5 | 82.1 | VIP loyalty programme, early access |
| Careful Wealthy | 35 | 41.1 | 88.2 | 17.1 | Quality/value messaging, personalised offers |
| Standard Customers | 81 | 42.7 | 55.3 | 49.5 | Seasonal campaigns, points programme |
| Impulsive Buyers | 22 | 25.3 | 25.7 | 79.4 | Flash sales, bundles |
| Budget Conscious | 23 | 45.2 | 26.3 | 20.9 | Discount days, coupons |

**Key insights**
- **Careful Wealthy** customers earn as much as Premium Spenders but spend far less. They're the biggest growth opportunity.
- **Impulsive Buyers** are the youngest group (avg age 25) and spend heavily despite low income.
- Spending decreases with age, while income and spending on their own show almost no linear relationship.

## Power BI Dashboard
- **Page 1 – Overview:** KPI cards (customers, avg age, income, spending), segment share donut, spending by age group and gender, gender slicer.
- **Page 2 – Segments:** income vs spending scatter by segment, segment averages matrix, strategy table, gender mix per segment.

## How to Run
1. Upload `Mall_Customers.csv` to Google Drive (`MyDrive/`).
2. Open `Customer_segmentation_Final.ipynb` in Google Colab → **Runtime → Run all**.
3. The exported files appear in `MyDrive/PowerBI_Customer_Segmentation/`.
4. In Power BI Desktop: **Get data → Text/CSV**, load both CSVs, and apply `segment_theme.json` (**View → Themes**).

## Project Files
| File | Purpose |
|---|---|
| `Customer_segmentation_Final.ipynb` | Full analysis and clustering notebook |
| `customers_segmented.csv` | One row per customer with segment (Power BI) |
| `segment_summary.csv` | One row per segment with averages and strategy (Power BI) |
| `segment_theme.json` | Power BI colour theme |
| `*.pbix` / `*.pdf` | Power BI dashboard and PDF export |
