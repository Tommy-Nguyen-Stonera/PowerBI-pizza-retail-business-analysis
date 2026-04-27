# Pizza Retail Business Analysis

**[Power BI dashboard](https://pizza-retail-analysis.vercel.app)**
Live and embedded in the browser. No login. Slicers, cross-filtering, drill-down, and tooltips all work the way they do in Desktop. Best viewed on a laptop or wider. Click the page tabs at the bottom of the dashboard to move between the five pages.

A year of pizza transactions, cleaned up and turned into five pages that tell a shop owner where the money comes from and what to do about it. The last page is a short list of actions. That was the goal from the start.

## What's in this repo

| File | What it does |
|---|---|
| `Pizza Retail Business Analysis.pbip` | The pointer file. Open this in Power BI Desktop. |
| `Pizza Retail Business Analysis.Report/` | Report layer. All pages, visuals, theme, bookmarks. |
| `Pizza Retail Business Analysis.SemanticModel/` | The model behind the report. Tables, calculated measures, query steps. You won't open this folder directly. Power BI loads it for you when you open the .pbip. |
| `Pizza Business Analysis Report.html` | Standalone HTML walkthrough of the same five pages. Useful as offline reference. |
| `data_pizza.xlsx` | Raw transactions, one year. |
| `data_dictionary.xlsx` | Column reference. Open this before you guess what a column means. |

If you need a single-file download, grab the zipped pbip from the live site. The button on the report page pulls the same tree above, packaged so Desktop can open it in one go.

## The data

One flat table. Transaction-level pizza orders for twelve months. Each row is one pizza line in one order, with date, time, category, size, quantity, unit price, total price. No joins, no fuss.

The key columns are `order_id`, `order_date`, `order_time`, `pizza_id`, `pizza_name`, `pizza_category`, `pizza_size`, `quantity`, `unit_price`, `total_price`. The full column reference lives in `data_dictionary.xlsx`.

## Questions I wanted answered

1. How is the shop doing right now? Revenue, orders, average ticket, basket size, all with year-over-year deltas so the numbers mean something.
2. When does the money actually come in? Which hour, which day, which season.
3. What drives revenue? Which categories, which sizes, which specific pizzas.
4. How do customers order? Solo or multi, what pairs with what, how concentrated the basket is around a handful of ingredients.
5. What do I do with this on Monday morning? That last page is the whole reason I built the thing.

## Report pages

Five pages, one per question, in that order.

1. **Executive Summary.** Headline numbers with deltas, revenue trend, category mix. If you only have five minutes, this is the page.
2. **Demand Rhythm.** Hour-by-weekday heatmap, hourly bars, weekday bars, month-to-date pacing card.
3. **Menu Performance.** Price-vs-volume scatter for every SKU, category revenue, size revenue, ranked table.
4. **Order Behaviour.** Basket distribution, solo vs multi, ingredient concentration, pairings.
5. **Action & Decisions.** Top to protect, bottom to test-retire, premium low-volume to promote.

## What the data actually said

1. Friday wins the week. The weekend holds up. Tuesday and Wednesday are the quiet stretch where nothing much happens.
2. Classic pizza outsells everything else, and it isn't close. Supreme is a respectable second. Veggie and Chicken are far behind.
3. Two time windows carry the day. Lunch from twelve to one, dinner from five to seven. Those hours do most of the work.
4. Thanksgiving was the single biggest day of the year. Holiday weekends are predictable events, not surprises, so they should be planned.
5. Large pizzas bring in the most revenue. XL and XXL are low volume but high ticket value. That's a segment with room to grow.

## What to do about it

1. Staff the lunch and dinner windows properly, every Friday and every weekend. Understaff those and you cap revenue. I've seen it happen.
2. Plan holiday weekends into the calendar. Don't react to Thanksgiving, prepare for it.
3. New menu ideas should land in Classic or Supreme first. That's where customers already trust you to experiment.
4. Run a group-order test for XL and XXL. The ticket value is already there. What's missing is volume, and that's the part a promotion can actually move.

## Tools

Power BI Desktop (PBIR project format), DAX, Power Query (M), Excel. Published to Power BI Service (Microsoft Fabric) and embedded in a Vercel-hosted page so visitors can interact with the dashboard directly in the browser without signing in.
