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
  #### Removal of Duplicates
  Steps taken
 - Select data range (CTRL A)
 - Click Data in the excel ribbon, where the ''Remove duplicates'' option will be seen
 - a total of 40,079 was removed out of the 50,000 data set
 - the unique set of data amounted to 9,921
 #### Creation of the column "Total Sales"
 ##### Steps taken
 - at first glance, the sales data has both "quantity" and "unit price". The perfect combo for the creatiom of Total sales where it is lacking
 - The formula for total sales was entered in the new column. The formula used was `= Quantity_Cell * Unit_Price_Cell` [`=F2*G2`]. in this case F2 represents quantity amd G2 price
 - Filled the column down, to ensure other rows had its total sales.

 #### Creating a Pivot Table for Sales Data Analysis
#####  Purpose of the Pivot Table

1. Summarize Total Sales by Product
 
This illustration highlighs the total amount generated from the sale of a particular product. Whereby, it also showcases the product with the highest sales to the lowest.

[Screenshot (194).png](path/to/image.png)


2. Summarize Total Sales by Region
 
This illustration highlighs the total amount generated from the sales in a particular region . Whereby, it also showcases the region with the highest sales to the lowest.

![Screenshot (195)](https://github.com/user-attachments/assets/445bf9a2-2746-4f4c-8656-9ec054f0c2b3)


3. Summarize Total Sales by Product and Region
  
 This pivot table summarizes the total sales of various products across four regions (South, East, North, and West), with a grand total of 2,101,090.

 ![Screenshot (197)](https://github.com/user-attachments/assets/e164c732-7116-444a-9789-ad97c2218980)

 - Total Sales by Region
   * South: Highest sales overall, totaling 927,820, with significant sales in Shoes (546,300) and Gloves (247,600).
   * East: Total sales of 485,925, led by Shirt sales at 237,600.
   * North: Total sales of 387,000, with Shirt being the top-selling product at 248,000.
   * West: Lowest total sales at 300,345, with Hat as the highest-selling item at 174,300

- Product Performance Across Regions:
    - Shoes: Major contributor in South with 546,300 but has relatively low sales in West (29,880).
    - Shirt: Strong sales in East and North but does not appear in South.
    - Hat: Consistent sales across regions, but particularly strong in West (174,300).
    - Gloves and Socks: Moderate sales across regions, with notable performance in South

- Regional Insights: 
   - South and East regions account for the largest portions of total sales, with South leading in overall sales.
   - West shows the least sales, indicating potential areas for growth or improvement in product promotion.

- Top Products per Region
   - South: Shoes dominate the market, suggesting high demand or popularity.
   - East: Shirt is the most popular, contributing nearly half of the region’s total sales.
   - North: Shirt again leads, showing regional demand consistency.
   - West: Hat takes the lead, possibly due to seasonal or regional preferences.

- Recommendation
  - South Region: Given the high sales, it is encouraged to focus on maintaining product availability and possibly expanding inventory for high-demand items like Shoes.
  - West Region: The West has the lowest sales figures overall. With Hats doing well, we could try promoting similar seasonal products here.
  - East and North Regions: Shirts perform well in both regions, so promotional efforts could focus on this.
  - It is also advised to continue monitoring trends in product demand across regions to identify shifts in consumer preferences.


4. Summarize Average Sales by Product
This illustration highlighs the Average amount generated from the sale of a particular product. Whereby, it also showcases the product with the highest sales to the lowest.

![Screenshot (198)](https://github.com/user-attachments/assets/43301a2d-784c-4d25-a01f-cd0b5e93eb0e)

 - Top Performers :
   - Shoes and Shirt have the highest average sales per order at 309 and 327, respectively. This suggests that these products consistently perform well in terms of individual order value.

 - Moderate Sales :
    - Gloves and Hat have mid-range average sales, which could indicate stable demand but lower per-order sales compared to Shirts and Shoes.

 - Lower-Average Products:
    - Jackets and Socks have the lowest average sales per order, with Socks at 122. These items may require promotional efforts or bundling strategies to increase their average sales

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




  

  
  
