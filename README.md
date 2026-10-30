# ApnoMart Sales Dashboard (Power BI)

Three-page Power BI dashboard analysing **1,200 retail orders** for ApnoMart (1 May 2026 – 28 Oct 2026): revenue, profit margin and customer behaviour, with DAX measures, custom tooltips, a custom teal and gold theme and business recommendations.

## The One Big Thing

Apno Mart earns **16.26M revenue at a 27.18% margin**, but **Electronics is the leak**: 18.2% of revenue yet only 12.6% of profit (18.88% margin). **Office Supplies** is the star: 20.8% of revenue and 26.6% of profit (34.80% margin).

## Dashboard Pages

| Page | Focus | Preview |
|---|---|---|
| 1. Revenue Overview | Revenue, profit, orders, category share, regions, top products, weekly pattern | ![Page 1](images/page1-revenue-overview.png) |
| 2. Profitability Deep-Dive | Margin by category and region, profit share vs revenue share, loss orders, discount impact | ![Page 2](images/page2-profitability.png) |
| 3. Customer Segmentation | Segments, payment methods, average order value by segment and payment | ![Page 3](images/page3-customers.png) |

## Key Metrics

- Total Revenue: **16.26M**
- Total Profit: **4.42M**
- Profit Margin: **27.18%**
- Total Orders: **1,200**
- Average Order Value: **13.55K**
- Loss-making orders: **61** (about 5%)

## Key Insights

1. **Electronics has the lowest margin (18.88%)** and a profit share (12.6%) well below its revenue share (18.2%).
2. **Office Supplies is the most profitable category** at 34.80% margin.
3. **East is the top region** by revenue (3.44M); North is the lowest (2.98M).
4. **Wednesday is the best day** (2.62M) and **Sunday the weakest** (1.95M).
5. **Discounts do not raise margin**: margin stays between 26.3% and 28.7% across 0–25% discounts, and 15% is the best level.
6. **All four customer segments earn about 27% margin**; Corporate leads on revenue (4.31M).

## Recommendations

- Review Electronics pricing, discounts and supplier costs to lift its margin.
- Push Office Supplies with bundles and promotions, since it converts revenue into profit best.
- Cap discounts around 15%; deeper discounts add no margin.
- Run weekend promotions to lift the weakest day (Sunday).
- Investigate the 61 loss-making orders.

## DAX Measures

```DAX
Total Revenue = SUM(Orders[Sales])
Total Profit = SUM(Orders[Profit])
Profit Margin % = DIVIDE([Total Profit], [Total Revenue])
Margin vs Company = [Profit Margin %] - CALCULATE([Profit Margin %], ALL(Orders))
Revenue vs Avg Day % =
VAR avgDay = AVERAGEX(ALL(Orders[Day_of_Week]), [Total Revenue])
RETURN DIVIDE([Total Revenue] - avgDay, avgDay)
```

## Advanced Features

- Calculated field: Profit Margin % (DAX)
- Multi-page dashboard (Revenue, Profitability, Customers)
- Data story banner ("Key Insight") on Page 1
- Custom report-page tooltips with context (for example, "13% above the average day")
- Custom teal and gold theme

## Files

- `Apno mart sales dashboard.pbix`: the Power BI report (open with Power BI Desktop)
- `apnomart-sales-data.csv`: the dataset (1,200 orders)
- `images/`: dashboard screenshots

## Tools

Power BI Desktop, DAX, Power Query

## Author

Your Name · [LinkedIn](https://www.linkedin.com/) · Online internship project
