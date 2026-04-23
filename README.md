# Pizza Retail Business Analysis (Power BI)

**Live report:** [pizza-retail-analysis.vercel.app](https://pizza-retail-analysis.vercel.app)

A one-year sales analysis of a pizza retail business. The dashboard answers five questions a restaurant owner actually asks on a Monday morning: when the money comes in, what's driving it, how customers order, and what to do next.

## What's in this repo

| File | What it is |
|---|---|
| `Pizza Retail Business Analysis.pbip` | Power BI project pointer file (open this in Desktop) |
| `Pizza Retail Business Analysis.Report/` | Report layer (pages, visuals, theme, bookmarks) |
| `Pizza Retail Business Analysis.SemanticModel/` | Data model (tables, measures, M queries) |
| `Pizza Retail Business Analysis.pbix` | Legacy single-file format for older Desktop versions |
| `Pizza Business Analysis Report.html` | Static companion website (same content as the Vercel site) |
| `data_pizza.xlsx` | Source transactions, one year |
| `data_dictionary.xlsx` | Column-by-column reference |
| `vercel/` | Deployable source for the live site (index.html + vercel.json + downloads) |

The `.pbip` folders are the authoritative source. Edits are made on the JSON/TMDL layer directly, so the `.pbix` may lag behind. If you want the latest state, open the `.pbip`.

## Dataset

One flat table, 48 columns, ~49k rows. Transaction-level pizza orders with date, time, category, size, quantity, and price. No joins required.

Key columns: `order_id`, `order_date`, `order_time`, `pizza_id`, `pizza_name`, `pizza_category`, `pizza_size`, `quantity`, `unit_price`, `total_price`. Full reference in `data_dictionary.xlsx`.

## Research questions

1. How is the business doing right now (revenue, orders, AOV, basket, YoY)?
2. When does the money come in (hour, weekday, seasonality)?
3. What actually drives revenue (category, size, individual SKUs)?
4. How do customers order (solo vs multi-item, pairings, ingredient concentration)?
5. What do we do Monday morning (protect, retire, promote, staffing)?

## Report structure

Five pages, each tied to one research question:

1. **Executive Summary** — headline KPIs with deltas, revenue trend, category mix.
2. **Demand Rhythm** — hour-x-weekday heatmap, hourly bars, weekday bars, MTD pacing.
3. **Menu Performance** — price-vs-volume scatter, category revenue, size revenue, rank table.
4. **Order Behaviour** — basket size distribution, solo vs multi, ingredient concentration, pairings.
5. **Action & Decisions** — top to protect, bottom to test-retire, premium to promote.

## Key insights

1. Friday and the weekend carry the week. Tuesday-Wednesday is the lowest-volume stretch.
2. Classic is the clear category leader. Supreme is a solid second. Veggie and Chicken trail.
3. Peak hours are 12:00-13:00 and 17:00-19:00. Those two windows drive most of the daily take.
4. Thanksgiving was the single biggest day of the year. Holiday weekends are predictable demand events.
5. Large and XL sizes drive ticket value. XXL is low-volume, high-revenue-per-order.

## Recommendations

1. Staff up for Fridays and the two peak hour windows. Understaffing those caps revenue directly.
2. Plan holiday weekends into the annual calendar rather than reacting to them.
3. Focus menu innovation on Classic and Supreme where customer preference is strongest.
4. Test a group-order promotion for XL/XXL to grow ticket value without cannibalising core sizes.

## Tools

Power BI Desktop (PBIR project format), DAX, Power Query (M), Excel.

## Running the Vercel site locally

```bash
cd vercel
npx vercel dev
```

Or redeploy the live site from the same folder:

```bash
cd vercel
vercel --prod --yes
```
