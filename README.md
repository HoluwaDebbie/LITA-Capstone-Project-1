# LITA-Capstone-Project-1
---

### Project Title: Sales Performance Analysis for a Retail Store
---

### Table of Content

[Project Overview](#project-overview).

[Objectives](#objectives).

[Tools used](#tools-used).

[Data Cleaning and Preparations](#data-cleaning-and-preparations).

[Exploratory Data Analysis](#exploratory-data-analysis).

[Data Analysis and Visualization](#data-analysis-and-visualization).

[Key Findings](#key-findings).

[Recommendations](#recommendations).

[Conclusion](#conclusion).

---

### Project Overview

This project aims to analyze sales data from a retail store to uncover insights into product performance, regional trends, and seasonal variations. The analysis uses Excel, SQL, and Power BI to drive data-driven recommendations for improving sales, optimizing inventory, and enhancing regional strategies.

---

### Objectives

 To evaluate retail sales data with the following goals:

- Identify high-demand products and their contribution to revenue.
- Analyze regional sales distribution to uncover areas with growth potential.
- Determine monthly sales patterns to inform inventory and promotional strategies.

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

---

### Data Analysis and Visualization

1. **Excel Analysis**: I used excel online, so you can get the file here [Download Here](https://1drv.ms/x/c/41bec79bae4bb512/EaOvzB2De4dKh3UD2P5_T08BaV3IeyUJoaf8c_w6c3HF8w?e=Ne8teT).
   
   - **Key Formulas Used in Excel**

- *Average Sales by Product*: `=TotalSalesperProduct/ COUNTIF( ProductRange, "ProductName")`
  
- *Average Quantity Sold by Month*: `=AVERAGEIFS(QuantityRange, MonthRange, "Month")`
  
- *Total Sales by Product*: `=SUMIF(ProductRange, "ProductName", QuantityRange)`
  
- *Total Revenue by Region*: `=SUMIFS(TotalRevenue, RegionRange, "RegionName")`
  
- *Total Revenue for Each Product*: `=SUMIF(ProductRange, "ProductName", RevenueRange)`

   - **Pivot Tables**: Created summary tables for metrics like product sales volume and regional distribution.
     
    Visualization: [Pivot Table for Sales Data](https://github.com/user-attachments/assets/497ffdab-5551-4020-b9ea-cc678fba4665)

   - **Key Excel-Based Findings**:
     
     - **Top Products by Quantity (Total Sales)**: Hats (15,929 units), Shoes (14,402 units), Shirts (12,388 units), Gloves (12,369 units).
     - **Regional Sales Summary**: South region leads with 24,298 units (35.49% of total sales); East follows at 20,361 units (29.74%).
     - **Monthly Sales Peaks**: Highest sales volume in February (9,930 units) and June (9,904 units); lowest sales volume in May (2,482 units) and December (2,465 units).

2. **SQL Analysis**:
   
   - Executed queries to calculate total sales quantities, and revenue metrics, assess customer purchases, and analyze top customers by revenue contribution. Notable SQL queries include:
     - **Total Sales by Product**:
       ```SQL
       SELECT Product, SUM(Quantity) AS Total_Sales
       FROM "Sales Data"
       GROUP BY Product
       UNION ALL
       SELECT 'Total', SUM(Quantity)
       FROM "Sales Data";
       ```
     
       This query calculated the total units sold per product and provided an overall total sales quantity.

   Visualization: [SQL Total Sales by Product](https://github.com/user-attachments/assets/7ffef65f-fa5a-438b-9d29-3dc0c0ebb3de)


     - **Total Revenue by Product**:
       ```SQL
       SELECT Product, SUM(Quantity * UnitPrice) AS Total_Revenue
       FROM "Sales Data"
       GROUP BY Product
       UNION ALL
       SELECT 'Total', SUM(Quantity * UnitPrice)
       FROM "Sales Data";
       ```
**Visualization**: [SQL total revenue per product](https://github.com/user-attachments/assets/519d415c-87b5-4c02-8bf2-d7b5149839d4)

- **Monthly Sales Trends**:
       ```SQL
       SELECT strftime('%Y-%m', OrderDate) AS Month, SUM(Quantity) AS Monthly_Total_Sales
       FROM "Sales Data"
       WHERE strftime('%Y', OrderDate) = '2024'
       GROUP BY Month
       UNION ALL
       SELECT 'Total', SUM(Quantity)
       FROM "Sales Data"
       WHERE strftime('%Y', OrderDate) = '2024';
       ```
       This query identified sales quantity peaks and lows across different months.

  **Visualization**: [SQL monthly sales totals for the current year](https://github.com/user-attachments/assets/455969b2-fad7-40d0-80cb-2643895332fe)


     - **Number of Sales Transactions in each Region**:
       ```SQL
       SELECT Region, COUNT(OrderID) AS Sales_Transactions
       FROM "Sales Data"
       GROUP BY Region
       UNION ALL
       SELECT 'Total', COUNT(OrderID)
       FROM "Sales Data";

       ```
   
  **Visualization**: [SQL number of sales transactions in each region](https://github.com/user-attachments/assets/df44eb48-2268-444b-812c-5cea612078dc)


3. **Power BI Visualization**: Sales Performance Comparison (2023 vs. 2024) You can get the file here [Download Here](https://app.powerbi.com/groups/me/reports/1defa032-0b23-405a-9b42-7e89fdb081b6?ctid=b6de804f-51cd-47ef-a151-26514ed475f0&pbi_source=linkShare&bookmarkGuid=c26374cf-d21e-4a4f-8c66-1f0883790118).
   
 An interactive comparison of sales performance between 2023 and 2024, highlighting changes in quantity, revenue, and average unit price.
- *Key Metrics*
- 2023: 38.7K units, $1.1M revenue, Avg. Price/Unit: $30.69
- 2024: 29.8K units, $996K revenue, Avg. Price/Unit increased slightly
  
- *Regional Revenue Share*
- 2023: South 43.5%, West 35.6%, East 13%, North 7.8%
- 2024: South 44.9%, East 24.4%, West 21.5%, North 9.2%
  
- *Product Analysis*
- Top Products by Quantity:
- 2023: Shirt (9K), Hat (8K), Shoes (8K)
- 2024: Hat (10K), Shoes (7K), Gloves (6K)
  
- Top Products by Revenue:
- 2023: Shirt ($0.29M), Shoes ($0.28M)
- 2024: Shoes ($0.34M), Hat ($0.23M), Shirt ($0.20M)
  
- *Visualization Highlights*
- Bubble Chart (Product Analysis): Compares Total Revenue, Sales Volume, and Average Price per Unit for each product.
- Quarterly Revenue: Showcases revenue trends per quarter for both years, highlighting significant growth in Q1 of 2024.
  
The Power BI dashboard enables quick, interactive insights for stakeholders, helping identify strengths, weaknesses, and strategic opportunities.

**Visualization**: 

[Sales Dashboard](https://github.com/user-attachments/assets/d52daa07-09ee-435d-a7a2-d13b26aa0cb4)

[Sales Dashboard 2023](https://github.com/user-attachments/assets/edc5939b-dbae-440e-a403-2eaf333b1b09)

[Sales Dashboard 2024](https://github.com/user-attachments/assets/b742044a-8578-41dd-a1cd-e81b228f5ec3)

[Sales Overview ](https://github.com/user-attachments/assets/ea997f7a-7ae7-4ced-ba41-1d57e4eb4c4d)

---

### Key Findings

**What is Working** 
- *Top Products*: Shoes and Hats show strong sales performance and are reliable revenue drivers.
- *Regional Strength*: The South and East regions consistently contribute to revenue, with the East showing growth potential.
- *Seasonal Peaks*: February and June are high-sales months; targeted campaigns during these periods could boost sales further.

**What Needs Improvement**
- Low-Sales Months: Sales dip in May and December, suggesting the need for seasonal promotions.
- Underperformance in the West Region: Limited sales growth in the West region calls for targeted marketing efforts.
- Lower Revenue for Some Products: Products like Jackets and Socks contribute minimally to revenue; they may require adjusted pricing or bundling strategies.

---

### Recommendations
- Inventory Optimization: Focus on maintaining high inventory levels for top-performing products (Shoes and Hats).
- Targeted Regional Marketing: Develop campaigns for the West and North regions to increase sales.
- Seasonal Promotions: Implement discounts and bundled offers in May and December to address low demand.
- Product Mix Review: Consider revising the pricing or marketing strategies for low-performing items to maximize their contribution to revenue.

---

### Conclusion
This analysis offers a comprehensive view of the retail store's sales performance, identifying key opportunities for growth and optimization. Through strategic inventory adjustments, targeted regional marketing, and seasonal campaigns, the store can drive higher revenue and establish a more resilient sales structure. The combination of Excel, SQL, and Power BI provides a robust framework for ongoing data-driven decision-making, positioning the store for sustainable growth.

---
