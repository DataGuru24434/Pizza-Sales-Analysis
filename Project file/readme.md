
# 🍕 Analysis of Pizza Sales

## 🔹 Goal:

The main aim of this analysis is to uncover key trends and patterns from the pizza sales data. Specifically:

- Identify the **time of day** when orders peak and when they are at their lowest.
- Determine which **day of the week** receives the highest number of orders.
- Find the **most popular pizza varieties** based on order volumes.
- Identify which pizza **generated the highest total sales**.
- Provide actionable insights into **peak hours**, **bestsellers**, and **underperforming items**.

---

## 🔹 Recommended Analysis:

✅ How many **customers do we have each day**?
✅ How many **pizzas are typically in an order**?
✅ How much **revenue did we generate this year**?
✅ Are there **seasonal trends or fluctuations** in sales?
✅ Which **pizzas should we promote or discontinue**?

---

## 🔹 Data Transformation:

- Renamed the table and column headings to match the report format.
- Promoted row to headers.
- Performed data type checks to match the appropriate format (integer, datetime, etc.).
- Replaced **null values with zeros** to avoid inaccuracies in calculations.
- Checked column **quality and distribution** in Power Query view.

---

## 🔹 Data Modelling:

- Established relationships between tables.
- Created measures to compute total sales, average orders per day, and number of customers.
- Created a new column “Time Slot” to categorize orders into peak hours.
- Calculated peak hours by analyzing order volumes across different time slots.

---

## 🔹 Visualizations:

- Average orders per day
- Total sales over time
- Average number of pizzas per order
- Peak hours of the day
- Top 5 and bottom 5 best-selling pizzas
- Preferred pizza category and size
- Peak days of the week

---

## 🔹 Summary:

This analysis highlights key patterns in pizza orders and sales.  
✅ It shows when orders peak, which pizza varieties are most popular, and how much each contributes to total sales.  
✅ The results can help the business maximize profits by focusing promotions on bestsellers, addressing slow-selling products, and optimizing staffing during peak hours.

---

## 🔹 Tools:

- **Microsoft Power BI**
- **DAX (Data Analysis Expressions)**
- **Power Query**
________________________________________
🔹2️⃣ Sample DAX Formulas you might find helpful:
✅ Total Sales:
Total Sales = SUM(Orders[TotalPrice])
✅ Average Orders per Day:
Average Orders per Day = DIVIDE(COUNT(Orders[Order_ID]), DISTINCTCOUNT(Orders[Order_Date]))

✅ Bestsellers (Top 5) — Top N by Quantity:
Top 5 Pizzas = TOPN(5, ALL(Products[Pizza_Name]), SUM(Orders[Quantity]), DESC )
✅ Peak Hour (using a new column “Time Slot”)
Count by Time Slot = COUNTROWS(FILTER(Orders, Orders[Time Slot] = "Peak"))
✅ Weekday Orders:
Weekday Orders = ADDCOLUMNS(Orders, "Weekday", WEEKDAY(Orders[Order_Date], 2))
✅ Here, WEEKDAY() with 2 starts the week from Monday (1).


