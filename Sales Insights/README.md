# Sales Insights Data Analysis Project
## Dashboard : [Click Here for Interactive Dashboard](https://app.powerbi.com/view?r=eyJrIjoiNjcyOTRiMGYtZGIwYy00MDRlLTgzZGItMTZlNjk4NGM4ZmQyIiwidCI6IjAwMTM5NDg3LWRkNDUtNDQ2MS04OWU0LWViZWI1NzgxYmRlOCJ9&pageName=ReportSection)

![logo](https://github.com/Sohail00786/Power-BI-projects/blob/05248060f13914d34f8e89847e8a4c7614ef0693/Sales%20Insights/D.gif)


![logo](https://github.com/Sohail00786/Power-BI-projects/blob/5432d89fc2d3e20dfc8cabda5583c1a6a23d6dbd/Sales%20Insights/D2.gif)

![logo](https://github.com/Sohail00786/Power-BI/blob/eb0367dc1e803efcf4a332ed9db2de73537fae43/Accenture%20Data%20Analytics/Screenshot%20(26).png)


### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`


Data Analysis Using Power BI
============================

1. Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`



