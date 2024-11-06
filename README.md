# lita_Project_Assignment
## Project 1: Sales Performance Analysis for a Retail Store
----
 In this project, i am tasked with analyzing the sales performance of a retail store. 
i will need to explore sales data to uncover key insights such as top-selling products, regional 
performance, and monthly sales trends. The goal is to produce an interactive Power BI 
dashboard that highlights these findings.
## Data Analysis
---
The following process where used to analyse the data
- Excel
- Sql
- Power Bi

## Excel
---
The Data was cleaned and analysed to enhance to the data to give a detailed information on the data.
what i did was to find the totalsales data regarding each product (shirt, shoes, jacket, Gloves and Hat)

### Pivot table
---
According to the questions we were told to Perform an initial exploration of the sales data. Use pivot tables to summarize 
total sales by product, region, and month.'
The total sales of each product was analysed, Region and also the monthly report of each product.this is clearing stated in the diagram attached below.

![image](https://github.com/user-attachments/assets/28df454e-a386-4cca-899b-da994ca7d11f)

The pivot graph for each analyses is found below:

![image](https://github.com/user-attachments/assets/6589cde7-dfd5-4547-9c8a-25dd3ff677cf)

Graphical Representation of Sum of total Sales Against Product 

![image](https://github.com/user-attachments/assets/ede9d1a0-4203-4caa-afac-b6a64610cee8)

Graphical Representation of the sum of total sales against region

![image](https://github.com/user-attachments/assets/271bb429-776a-4976-9500-06c9c8892bea)

Graphical Representation of the sum of total sales against order date

### calculate metrics such as average sales per product and total revenue by region.
---
### Average sales for each product
---
```AVERAGEIF(C3:C50002,C1,H3:H50001)=#327 (Shirt)
```AVERAGEIF(C3:C50002,C2,H3:H50002)=#309  (shoes)
```AVERAGEIF(C4:C50003,C3,H4:H50003)= #159  (hat)
```AVERAGEIF(C5:C50004,C4,H5:H50004)= #122 (socks)
```AVERAGEIF(C6:C50005,C5,H6:H50005)= #140 (Jacket)
```AVERAGEIF(C7:C50006,C7,H7:H50006)= #200 (Gloves)

###Total revenue
---
```SUMIF(D2:D50001,D2,H2:H50001) = North (# 1,950,000)
```SUMIF(D3:D50002,D3,H3:H50002) = South (# 4,675,000)
```SUMIF(D4:D50003,D4,H4:H50003) = west (# 2,450,000)
```SUMIF(D5:D50004,D5,H5:H50004)= East (# 1,512,500)


### structured Querylanguage
 
---
```Create database lita_Project1

Select *from [dbo].[Sales data _project]
--------retrieve the total sales for each product categories-----
Select PRODUCT,sum (total_sales) as product_total_sales from [dbo].[Sales data _project]
group by PRODUCT
select PRODUCT, sum (quantity)as Quantity_revenue From [dbo].[Sales data _project]
Group by PRODUCT

-----Find the number of sales transaction in each region-----
Select region,count (customer_id) as sales_by_region from [dbo].[Sales data _project]
group by region
------ find the highest selling product by total sales value-----
select PRODUCT,SUM(total_sales) as Sales_by _region from[dbo].[Sales data _project]
group by product
--------calculate total revenue per product------------
select PRODUCT,Sum(total_sales) as Product_total_sales from [dbo].[Sales data _project]
group by product
---------------calculate monthly sales totals for the current year--------------
select orderdate, sum(total_sales) as totalsales from [dbo].[Sales data _project]
where orderdate >='2024-01-01'
group by orderdate

--------find the top 5 costumer by total purchase Amount-------
select customer_id ,sum (total_sales) as totalsales from [dbo].[Sales data _project]
group by Customer_Id
order by totalsales desc
-------calculate the percentage of total sales cotributed by each region-----
select Region, Sum (Total_sales) as regionalsales,
(Sum (Total_sales) / CAST ((select sum(Total_sales) From [dbo].[Sales data _project])
As Decimal(10, 2)) * 100) AS Salespercetage
From [dbo].[Sales data _project]
group by region

----------identify products with no sales in the last quarter--------
select distinct product from[dbo].[Sales data _project]
where Product not in (select Product from [dbo].[Sales data _project]
where OrderDate >= DATEADD ( quarter, -1, getdate()))

