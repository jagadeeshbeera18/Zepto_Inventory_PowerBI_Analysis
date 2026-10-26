# Zepto Catalog & Inventory Analytics

A set of interactive, browser-based dashboards for exploring the Zepto catalog’s assortment, pricing, category performance, and stock availability. The dashboards are standalone HTML files; open one in a web browser to use its filters and search. No install or server is required.

## Start here

Open **`Zepto_Overall_Dashboard.html`** for a project-wide overview and links to the focused reports.

## Dashboards

| File | Purpose |
|---|---|
| `Zepto_Overall_Dashboard.html` | Portfolio KPIs and category comparisons for assortment, discounts, and stock availability; links to the focused reports. |
| `Zepto_Category_Performance.html` | Category assortment size, discount rate, price, and availability scorecard; search, sort, and focus controls. |
| `Zepto_Pricing_Analysis_preview.html` | Listed prices, discount depth by category, pricing KPIs, and searchable product price list; category, stock, and discount filters. |
| `Zepto_Inventory_Management.html` | Stock status and quantity summary, category availability, quantity bands, and a filterable stock watchlist. |
| `Zepto_Product_Assortment_Premium.html` | Product-name and variant counts, assortment by category, and an adjustable premium MRP threshold. |

Each dashboard includes its data, styles, and interactions in the HTML file. The reports are snapshots and do not connect to a live data source.

## Power BI file

`zepto_inventory_Power BI_Analytics.pbix` is the native Power BI export of the report that was open in Power BI when the file was downloaded. It contains that report’s `Category_Analysis` page and embedded data. The custom standalone HTML dashboards above are **not** embedded as report pages in this PBIX.

`Zepto_Pricing_Measures.dax` contains pricing measures for use in Power BI. `Zepto_Pricing_Data.csv`, `Zepto_Product_Analysis.csv`, and `Zepto_Category_Summary.csv` are supporting analysis exports.

## Metric definitions

- **Catalog listings** count category-tagged rows in the source. A product may appear under more than one category.
- **Distinct product names** deduplicate by the exact product name. The same product can still have multiple pack or price variants.
- **Distinct stock / assortment records** deduplicate matching product, pack, price, discount, and availability attributes across repeated category tags. Category-level counts can overlap and should not be summed as unique inventory.
- **Average discount** uses the source’s listed discount percentage. Currency values in the pricing data were converted from paise to Indian rupees (INR).
- **Available quantity** is treated as the snapshot quantity for a product/pack/price record. **Estimated on-hand value** is available quantity multiplied by listed selling price, after deduplication.
- **Premium** is a configurable price tier based on MRP. The product report defaults to MRP ≥ ₹200 (about one quarter of the deduplicated variants); this is not a product-quality classification.
- Inventory low-quantity flags are review cues only. The dataset does not include sales velocity, lead time, or reorder policy.

## Snapshot and limitations

The analyzed dataset contains 3,732 category-tagged listings across 14 categories and 1,674 exact distinct product names. At the all-category baseline, average listed discount is 7.6%, the in-stock listing rate is 87.9%, and 453 category-tagged listings are out of stock. After deduplicating repeated category tags, it contains 1,801 product/pack/price/availability records, including 217 out-of-stock records and 7,197 available-quantity units. Estimated on-hand value at listed selling price is approximately ₹10.58 lakh. These are catalog snapshot figures. The source has no date series or sales transactions, so the reports cannot measure revenue, sell-through, demand, price elasticity, or trends.

