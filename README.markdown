# SuperStore Data Analysis Project

## Overview
This project analyzes the SuperStore dataset to derive insights into sales performance, customer behavior, product trends, geographic variations, and order operations. The dataset is provided in the "Sample - standard data.xls" file, which includes tabs for Orders, Returns, and People. The analysis uses Excel with a star schema data model, data transformations, DAX measures, and an interactive dashboard with multiple reports.

## Dataset Description
The dataset consists of the following sheets:
- **Orders**: Contains 9994 rows of transaction data with fields like Row ID, Order ID, Order Date, Ship Date, Ship Mode, Customer ID, Customer Name, Segment, Country, City, State, Postal Code, Region, Product ID, Category, Sub-Category, Product Name, Sales, Quantity, Discount, and Profit.
- **Returns**: Lists returned orders with fields Returned (Yes) and Order ID, covering 296 entries.
- **People**: Maps sales persons to regions with fields Person and Region, including 4 entries (Anna Andreadi - West, Chuck Magee - East, Kelly Williams - Central, Cassandra Brandow - South).

## Data Model
A star schema was implemented in Excel (using Power Pivot). The data model structure is as follows:

![Data Model](https://github.com/HazemMedhat/Super-Store-Analysis-/blob/60fe5317d0a3af275a66b4c057db0c392dae7de6/New%20Data%20Model.png)

- **Fact Table: Orders** (enhanced with calculated columns for Revenue and Ship Duration).
- **Dimension Tables**: Customers (derived or inferred from Orders), Products (from Orders), Returns, and People.
- Relationships: 
  - Orders to Returns via Order ID (many-to-one).
  - Orders to People via Region (many-to-one, assuming linkage through Customers).
  - Other dimensions linked via Customer ID, Product ID, etc.

## Work Done
1. **Data Model Setup**: Configured a star schema in Excel's Power Pivot to connect fact and dimension tables for efficient querying.
2. **Data Cleaning and Transformation**: 
   - Cleaned the dataset for consistency (e.g., date formats, missing values).
   - Added two calculated columns:
     - **Revenue**: Likely calculated as Sales * (1 - Discount), adjusted for context (e.g., Profit or net figures).
     - **Ship Duration**: Computed as the difference between Ship Date and Order Date in days.
3. **DAX Measures**: Created custom measures for key metrics, including:
   - Total Products: 1,862
   - Total Orders: 5,009
   - Total Items Sold: 37,873
   - AVG Ship Duration: 3.96 days
   - Total Revenue: $1,974,619
   - Profit: -$478,191
   - Profit Margin: -24%
   - Total Discount Amount: $322,582
   - Return Rate: 5.91%
   - Purchase Frequency: 6.32
   - AOV (Average Order Value): $394
   - ARPU (Average Revenue Per User): $2,490
   - Net Revenue: $1,819,010
4. **Interactive Dashboard**: Built using PivotTables, PivotCharts, slicers, and timelines in Excel, featuring multiple reports:
   - **Overview Report**: Displays total sales, discounts, profit margin, return rate, and trends over time.
   - **Customer Report**: Analyzes customer count, revenue per user, top customers, segment distribution, and ship mode preferences.
   - **Product Report**: Evaluates top products, sales/revenue by category, orders/items sold, and return rates.
   - **Orders & Geo Report**: Tracks order volume, ship duration, sales/revenue by region, and regional ship mode/return distributions.

## Objectives
As outlined by the stakeholder:
- Gain actionable insights to optimize inventory, marketing, reduce returns, and improve customer satisfaction.
- Drive revenue growth and market share.

## Business Questions Addressed
The analysis covers:
- **Overview**: Total sales ($2,297,201), revenue trends, return impact ($155,609 returned vs. $1,819,010 net), and monthly order/item trends.
- **Customer Behavior**: Total customers (793), ARPU ($2,490), top revenue customers (e.g., Tamara Chand at $18,945), segment distribution (Consumer 50%, Corporate 23%, Home Office 27%), and ship mode preferences.
- **Product Performance**: Top 10 products (e.g., Canon imageCLASS 2200 at $42,000), category sales/revenue (e.g., Technology $836,154), and return rates (e.g., Furniture 19.17%).
- **Geography Insights**: Orders (5,009), AVG ship duration (3.96 days), sales/revenue by region (e.g., West $606,423/$764,634), and regional return rates (e.g., South 35.79%).
- **Orders Analysis**: Order trends over time, ship mode distribution, and category/sub-category impacts.

## Key Findings
- **Overview**: Total sales reached $2,297,201, but a -24% profit margin and $322,582 in discounts highlight profitability challenges. Returns ($155,609) reduce net revenue to $1,819,010, with a 5.91% return rate.
- **Customer Behavior**: 793 customers generate an ARPU of $2,490, with Consumer segments dominating (50%) and higher return rates (11%) compared to Corporate (20%) and Home Office (33%).
- **Product Performance**: Technology leads with $836,154 net revenue, but Furniture has the highest return rate (19.17%). Top product Canon imageCLASS 2200 generates $42,000 in sales.
- **Geography Insights**: West region performs best ($606,423 net revenue), while South has the highest return rate (35.79%). AVG ship duration is 3.96 days, with regional variations.
- **Orders Analysis**: 5,009 orders show a steady increase over time, with Standard Class (59%) as the preferred ship mode.

## Methodology
- Imported data into Excel and used Power Query for cleaning/transformations.
- Built relationships in Power Pivot.
- Defined DAX measures for calculations.
- Created dashboard sheets with interactive elements for filtering by date, region, category, etc.

## Dashboard
The interactive dashboard provides a comprehensive view of the analysis:

![Overview Dashboard](https://github.com/HazemMedhat/Super-Store-Analysis-/blob/47b9ce2d493f9876d92371504a83b9d5fcce904c/Overview%20Report.png)
![Customer Dashboard](https://github.com/HazemMedhat/Super-Store-Analysis-/blob/47b9ce2d493f9876d92371504a83b9d5fcce904c/Customer%20Report%20.png)
![Product Dashboard](https://github.com/HazemMedhat/Super-Store-Analysis-/blob/47b9ce2d493f9876d92371504a83b9d5fcce904c/Product%20Report.png)
![other Dashboard](https://github.com/HazemMedhat/Super-Store-Analysis-/blob/47b9ce2d493f9876d92371504a83b9d5fcce904c/Orders%20%26%20Geo%20Rep.png)

- **Overview Report**: Highlights total sales ($2,297,201), discounts ($322,582), profit margin (-24%), return rate (5.91%), and trends over time.
- **Customer Report**: Shows 793 customers, ARPU ($2,490), top 5 customers by revenue and frequency, segment distribution, and ship mode preferences.
- **Product Report**: Features top 10 products, sales/revenue by category, orders/items sold per category, and return rates.
- **Orders & Geo Report**: Displays 5,009 orders, AVG ship duration (3.96 days), sales/revenue by region, and regional ship mode/return distributions.

## Files Included
- `Sample - standard data.xls`: Raw dataset.
- `Project.xlsx`: Excel file with data model, transformations, DAX measures, and interactive dashboard. (Assuming this is the output file; rename as needed.)
