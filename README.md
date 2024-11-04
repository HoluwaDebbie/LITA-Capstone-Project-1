# LITA-Capstone-Project-1
---

### Project Title: Sales Performance Analysis for a Retail Store
---

### Table of Content

[Objective](#objective).

[Tools used](#tools-used).

[Data Cleaning and Preparations](#data-cleaning-and-preparations).

[Exploratory Data Analysis](#exploratory-data-analysis).

[Key Formulas used in Excel](#key-formulas-used-in-excel).

[Data Analysis and Visualization](#data-analysis-and-visualization).

---

### Objective

 To analyze retail sales data to extract insights on product performance, regional sales distribution, and monthly sales patterns. The goal is to use these findings to optimize store performance by identifying high-demand products, seasonal trends, and region-specific opportunities.

 ---

 ### Tools used

 1. **Excel**: Used for data aggregation, formula-based calculations, and pivot tables.
2. **SQL**: Utilized for data querying, filtering, and advanced calculations on total sales and revenue metrics.
3. **Power BI**: Built interactive visualizations, including bar charts, pie charts, and line graphs for monthly trends and regional comparisons.
4. **GitHub**: Used for portfolio building.
   
---

### Data Cleaning and Preparations

Before analysis, data cleaning steps were necessary to ensure accuracy:

1. **Data Import and Format Check**: Data was imported into Excel and SQL, with checks to ensure correct data types for all fields.
2. **Handling Missing Values**: There were no missing values in the dataset.
3. **Data Consistency Checks**: Verified uniformity in product names, regions, and dates by eliminating duplicates and standardizing text formatting.
4. **Derived Columns**: Created additional columns in Excel for metrics like Total Revenue (Quantity * Unit Price) and Monthly Sales (month extraction from date).

---

### Exploratory Data Analysis

The goal was to answer several strategic questions using the sales data:

1. **Which products drive the highest sales (quantity) and revenue?**
2. **What regions contribute most significantly to total sales and revenue, and where are the potential growth opportunities?**
3. **How do sales vary month-to-month, and are there identifiable seasonal trends?**
4. **Who are the top customers by purchase value, and what purchasing patterns are observed?**

These questions guided a deep dive into the data to reveal product, region, and customer-specific insights.

### Key Formulas Used in Excel

- **Average Sales by Product**: `=TotalSalesperProduct/ COUNTIF( ProductRange, "ProductName")`
  
- **Average Quantity Sold by Month**: `=AVERAGEIFS(QuantityRange, MonthRange, "Month")`
  
- **Total Sales by Product**: `=SUMIF(ProductRange, "ProductName", QuantityRange)`
  
- **Total Revenue by Region**: `=SUMIFS(TotalRevenue, RegionRange, "RegionName")`
  
- **Total Revenue for Each Product**: `=SUMIF(ProductRange, "ProductName", RevenueRange)`

### Data Analysis and Visualization

1. **Excel Analysis**: I used excel online, so you can get the file here [Download Here](https://onedrive.live.com/personal/41bec79bae4bb512/_layouts/15/doc.aspx?resid=1dccafa3-7b83-4a87-8775-03d8fe7f4f4f&cid=41bec79bae4bb512&ct=1730713976060&wdOrigin=OFFICECOM-WEB.START.EDGEWORTH&wdPreviousSessionSrc=HarmonyWeb&wdPreviousSession=f07e323f-4750-4a65-a586-c21a601268a0).
   - **Pivot Tables**: Created summary tables for metrics like product sales volume and regional distribution.
     
    Visualization:  
   - **Key Excel-Based Findings**:
     
     - **Top Products by Quantity (Total Sales)**: Hats (15,929 units), Shoes (14,402 units), Shirts (12,388 units), Gloves (12,369 units).
     - **Regional Sales Summary**: South region leads with 24,298 units (35.49% of total sales); East follows at 20,361 units (29.74%).
     - **Monthly Sales Peaks**: Highest sales volume in February (9,930 units) and June (9,904 units); lowest sales volume in May (2,482 units) and December (2,465 units).
