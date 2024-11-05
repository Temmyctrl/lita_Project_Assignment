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


Hint – You need to load the dataset into your SQL Server environment to write and 
validate your queries.
Write queries to extract key insights based on the following questions. 
o retrieve the total sales for each product category.
o find the number of sales transactions in each region.
o find the highest-selling product by total sales value.
o calculate total revenue per product.
o calculate monthly sales totals for the current year.
o find the top 5 customers by total purchase amount.
o calculate the percentage of total sales contributed by each region.
o identify products with no sales in the last quarter.
3. Power BI:
o Create a dashboard that visualizes the insights found in Excel and SQL. The 
dashboard should include a sales overview, top-performing products, and 
regional breakdowns

### structured Querylanguage

