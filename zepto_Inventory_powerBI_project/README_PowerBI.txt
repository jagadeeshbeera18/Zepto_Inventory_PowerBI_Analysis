Power BI handoff

1. Load Zepto_Pricing_Data.csv and name the table Zepto.
2. Add measures from Zepto_Pricing_Measures.dax.
3. Use Category as the category dimension and Product as a product name (not a unique product ID).
4. Use the category comparison and product ranking visuals in Zepto_Category_Product_Analysis.html as a layout reference.

Analysis files:
- Zepto_Category_Summary.csv: 14 category-level aggregates.
- Zepto_Product_Analysis.csv: enriched row-level listings with cross-category matching counts.

Data: 3,732 catalog listings across 14 category labels, with 1,674 distinct product names. Source MRP and discountedSellingPrice values are paise and are divided by 100 to INR. Source discount percentage is retained; savings are derived as MRP minus selling price. No date, transaction, units-sold or competitor fields are present; use for catalog pricing comparisons only, not realized revenue or trends. One row has zero MRP.

Data quality: 3,212 rows (86.1%) have the same product/price/availability signature in more than one category. Four exact category assortment overlaps are flagged in the analysis. Treat category comparisons cautiously and validate the source taxonomy before using them for assortment decisions.
