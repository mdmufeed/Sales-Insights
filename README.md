# 🛒 Sales Insights Dashboard | Power BI + MySQL

## 📊 Project Overview
This project showcases an end-to-end data analysis solution using **MySQL** for backend data extraction and **Power BI** for interactive visualization. The data includes sales transactions across multiple currencies and dates, joined with product and customer dimensions.

## 🔧 Tools & Technologies
- **Power BI** for dashboard creation
- **MySQL** for data storage and SQL querying
- **DAX** for custom calculations
- **Power Query** for data transformation

## 📁 Data Sources
- `transactions` table: Includes `order_date`, `sales_amount`, `currency`, etc.
- `date` table: Includes `year`, `month_name`, etc.
- Data queried using `.sql` scripts, then visualized in `.pbix` file

## 📈 Key Visuals
- **Total Sales by Year & Month**
- **Sales by Currency (USD/INR)**
- **Top Performing Regions**
- **Profitability KPIs**
- **Interactive slicers** for year, month, and currency

## 📌 SQL Highlights
```sql
SELECT SUM(transactions.sales_amount)
FROM transactions
INNER JOIN date ON transactions.order_date = date.date
WHERE date.year = 2020
  AND date.month_name = 'January'
  AND transactions.currency IN ('INR', 'USD');
