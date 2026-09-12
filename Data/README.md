
# Data

Raw dataset powering the [Swiggy Sales Analysis Dashboard](../).

## File

| File | Description |
|---|---|
| `Swiggy Raw Data Excel.xlsx` | Flat, order/dish-level dataset — 197,430 rows × 10 columns, single sheet (`Swiggy Data`) |

## Data Dictionary

| Column | Type | Description | Example |
|---|---|---|---|
| `State` | Text | Indian state where the order was placed | `Karnataka` |
| `City` | Text | City within the state | `Bengaluru` |
| `Order Date` | Date | Date the order was placed (1 Jan 2025 – 31 Aug 2025) | `2025-06-29` |
| `Restaurant Name` | Text | Name of the restaurant fulfilling the order | `Anand Sweets & Savouries` |
| `Location` | Text | Locality / neighborhood of the restaurant | `Rajarajeshwari Nagar` |
| `Category` | Text | Restaurant-defined menu category for the item | `Snack`, `Recommended`, `Main Course` |
| `Dish Name` | Text | Name of the dish ordered | `Butter Murukku-200gm` |
| `Price (INR)` | Numeric | Price of the line item in ₹ | `133.9` |
| `Rating` | Numeric | Restaurant/dish rating (1.5 – 5.0) | `4.5` |
| `Rating Count` | Numeric | Number of ratings backing that rating value | `25` |

## Coverage

| Metric | Value |
|---|---|
| Rows | 197,430 |
| Date range | 1 Jan 2025 – 31 Aug 2025 |
| States | 28 |
| Cities | 28 |
| Localities | 977 |
| Restaurants | 993 |
| Distinct category labels | 4,972 (restaurant-defined, not a fixed taxonomy) |
| Price range | ₹0.95 – ₹8,000 |
| Rating range | 1.5 – 5.0 |
| Missing values | None across all 10 columns |

Total revenue (`sum(Price (INR))`) reconciles to **₹53.01M**, average price to **₹268.51**, and total `Rating Count` to **5.59M** — matching the KPI cards shown on the dashboard.

## Engineered Fields (not in this raw file)

The interactive dashboard workbook (see [`Dashboard/`](../Dashboard)) augments this raw table with a few fields computed for slicing and charting, built with Excel formulas rather than shipped in the raw export:

- **Day** — weekday derived from `Order Date`
- **Week** / **Quarter** — calendar period derived from `Order Date`
- **Food Type** — Veg / Non-Veg tag derived from `Category` / `Dish Name`

See [`Screenshots/`](../Screenshots) for a preview of these engineered columns in place.
