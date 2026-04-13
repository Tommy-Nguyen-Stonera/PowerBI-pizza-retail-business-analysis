# Pizza Retail Business Analysis (Power BI)

[View Interactive Report](https://htmlpreview.github.io/?https://raw.githubusercontent.com/Tommy-Nguyen-Stonera/PowerBI-pizza-retail-business-analysis/main/Pizza%20Business%20Analysis%20Report.html)

## Overview

This project analyses a full year of pizza retail transactions to understand when revenue peaks, which products lead, and what a typical order looks like. The goal was to give restaurant managers a clear picture of demand patterns and product performance so they can make better decisions on staffing, menu focus, and promotions.

## Dataset

- Source: data_pizza.xlsx (full year of pizza retail transactions)
- Key columns: order_id, order_date, order_time, pizza_id, pizza_name, pizza_category, pizza_size, quantity, unit_price, total_price
- Single flat table, no joins required

## Research Questions

1. Which days of the week generate the most revenue, and is there a clear peak day?
2. Which pizza categories and sizes lead in both order count and total revenue?
3. Are there seasonal revenue trends across the year, or is demand relatively flat?
4. Which individual pizzas are the top performers, and which are consistently at the bottom?
5. What does a typical order look like in terms of items, size, and spend?

## Data Model

Single flat table: transaction-level pizza orders. Each row is one pizza line within an order, with date, time, category, size, and price. Revenue and order summaries are built through DAX measures and Power BI aggregations.

## What Was Analysed

- Revenue by day of week to identify peak and trough days
- Revenue and order count by pizza category (Classic, Supreme, Veggie, Chicken)
- Revenue and order count by pizza size (S, M, L, XL, XXL)
- Monthly revenue trend across the full year
- Individual pizza performance ranked by revenue and by quantity sold
- Average order value and average items per order

## Key Insights

1. Friday is the highest-revenue day of the week, and weekends follow close behind. Midweek (Tuesday to Wednesday) sees the lowest volumes.
2. Classic pizza leads all four categories in both revenue and quantity sold. Supreme is second. Veggie and Chicken trail by a meaningful margin.
3. Peak hours are 12:00 to 13:00 and 17:00 to 19:00, which maps to lunch and dinner rushes. These two windows drive the bulk of daily revenue.
4. The single highest daily revenue was recorded on 27 November (Thanksgiving), confirming holiday weekends as the strongest demand events in the calendar.
5. Large size pizzas drive the most revenue. XL and XXL sizes have low order volume but high ticket value per order.

## Recommendations

1. Staff up on Fridays and across the lunch and dinner windows (12 to 1pm, 5 to 7pm). These are the most predictable high-volume periods and understaffing them directly caps revenue.
2. Build Thanksgiving and holiday weekend promotions into the annual calendar. The data confirms these are the highest-demand days and they should be planned for, not reacted to.
3. Focus menu innovation on the Classic and Supreme categories where customer preference is strongest. Introducing new variants there has higher trial potential than extending Veggie or Chicken.
4. Review XL and XXL sizing strategy. These sizes generate high per-order revenue but low order counts. A targeted group-order promotion could grow this segment without cannibalising the core.

## Tools

Power BI, Excel

## Files

- `Pizza Retail Business Analysis.pbix` - Power BI dashboard file
- `Pizza Business Analysis Report.html` - Interactive HTML report
- `data_pizza.xlsx` - Source sales data
- `data_dictionary.xlsx` - Column definitions
