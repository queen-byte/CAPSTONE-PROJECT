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
- Identification of top customers and products with no sales in the last quarter
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

### Clean Data
 
 

  
  
