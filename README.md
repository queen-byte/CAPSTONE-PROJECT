# CAPSTONE-PROJECT

## SALES PERFORMANCE FOR A RETAIL STORE

### Project Overview
This project involves analyzing the sales performance of a retail store by exploring its sales data. Through the use of tools like Excel, SQL and Power BI. wherby, the goal is to uncover insights such as top selling products, regional performance, monthly sales trends and many more. The final Deliverable is an interactive power BI dashboard that visually depicts key findings for easy interpretation.

### Tools
1. Excel
2. SQL
3. Power BI

### Objectives ;
1. Sales Data exploration using Excel: This includes generating summary tables of total sales by product, region, and month using pivot tables. Also, Calculations such as average sales per product and total revenue by region.
2. Sales Data exploration using SQL. Whereby, Queries will answer questions like:
- Total sales by product category and region.
- Highest-selling products by total sales value.
- Monthly sales trends for the current year.
- Identify products with no sales the last quater.
   3.  Sales Data exploration using Power BI : this would mostly entail key visualisation of the entire insights extracted prom the data as a whole.

 ### Raw Data
  here is the path link to the raw data that will be worked on LITA Capstone Dataset
  [download](https://github.com/queen-byte/CAPSTONE-PROJECT/blob/a12c14bd76ce34905a69e55a21a3129444b0d34f/LITA%20Capstone%20Dataset%20(SalesData).csv)

 ### Detailed Excel Analysis for the Sales Data
 The initial step taken in analyzing the sales data was the removal of duplicates
 1. Removal of Duplicates
 #### Steps taken
 - Select data range (CTRL A)
 - Click Data in the excel ribbon, where the ''Remove duplicates'' option will be seen
 - a total of 40,079 was removed out of the 50,000 data set
 - the unique set of data amounted to 9,921
2. Creation of the column "Total Sales"
 #### Steps taken
 - at first glance, the sales data has both "quantity" and "unit price". The perfect combo for the creatiom of Total sales where it is lacking
 - The formula for total sales was entered in the new column. The formula used was `= Quantity_Cell * Unit_Price_Cell` [`=F2*G2`]. in this case F2 represents quantity amd G2 price
 - Filled the column down, to ensure other rows had its total sales.

3. Creating a Pivot Table for Sales Data Analysis
####  Purpose of the Pivot Table
- Summarize Total Sales by Product
This illustration highlighs the total amount generated from the sale of a particular product. Whereby, it also showcases the product with the highest sales to the lowest.


- Summarize Total Sales by Region
This illustration highlighs the total amount generated from the sales in a particular region . Whereby, it also showcases the region with the highest sales to the lowest.


- Summarize Total Sales by Product and Region
This illustration highlighs the total amount generated from the sale of a particular product in a particular region. It is able to distinguish where each product was sold.


- Summarize Average Sales by Product
This illustration highlighs the Average amount generated from the sale of a particular product. Whereby, it also showcases the product with the highest sales to the lowest.

### Clean Data
  Here is the path link to the clean data that has been worked on [Download](https://github.com/queen-byte/CAPSTONE-PROJECT/blob/6c720e386d1aa7f28e8b652d01c5050fc75e1d4d/Cleaned%20(SalesData).csv)



 ### Detailed SQL Analysis for the Sales Data
 SQL Server Management Studio 20 was used for further anlyzation of the data. Whereby the use of various queries was used.
 #### Steps taken
 - First thing was to import the already cleaned file from Excel into the SQL server
 - a problem arose when some part of the Data was showing null, but this was rectified by issuing the query
   
  `DELETE
    FROM [dbo].[SALES_DATA]
    WHERE OrderId  IS NULL`
- With the NULL values erased, gave room for proper analysis
- Total sales by product category and region was calculated
  
  `select PRODUCT, region,
   sum(TOTAL_SALES) AS TOTAL_SALES
   FROM SALES_DATA
   GROUP BY PRODUCT, region
   ORDER BY 3 DESc`
- Highest-selling products by total sales value
  
  `select PRODUCT, SUM(TOTAL_SALES) AS TOTAL_SALES
FROM SALES_DATA
GROUP BY PRODUCT
ORDER BY 2 DESC`

-  Monthly sales trends for the current year. In this case the current year is 2024

  `SELECT MONTH(OrderDate) AS month, SUM(Total_Sales) AS total_sales
FROM 
sales_data
WHERE 
    YEAR(OrderDate) = YEAR(GETDATE())  
GROUP BY 
    MONTH(OrderDate)
ORDER BY 
    month`
    
-  Monthly sales trends for the previous year. In this case the previous year is 2023

`SELECT 
 MONTH(OrderDate) AS month,
 SUM(Total_Sales) AS total_sales
FROM 
sales_data
WHERE 
    YEAR(OrderDate) = YEAR(GETDATE()) - 1 
GROUP BY 
    MONTH(OrderDate)
ORDER BY 
    month`




  

  
  
