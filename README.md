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

[Download](https://github.com/queen-byte/CAPSTONE-PROJECT/blob/dd9ef5b99f65778805b4423acc257e1e14a84a73/Screenshot%20(194).png)


2. Summarize Total Sales by Region
 
This illustration highlighs the total amount generated from the sales in a particular region . Whereby, it also showcases the region with the highest sales to the lowest.

[Download](https://github.com/queen-byte/CAPSTONE-PROJECT/blob/f7ac6c76fd343b6335ffe0319097b1878eafff2e/Screenshot%20(195).png)


3. Summarize Total Sales by Product and Region
  
 This pivot table summarizes the total sales of various products across four regions (South, East, North, and West), with a grand total of 2,101,090.

[Download](https://github.com/queen-byte/CAPSTONE-PROJECT/blob/c49ef7b776175442a424fa397e4bbd6a536c3592/Screenshot%20(197).png)

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

[Download](https://github.com/queen-byte/CAPSTONE-PROJECT/blob/c49ef7b776175442a424fa397e4bbd6a536c3592/Screenshot%20(198).png)

 - Top Performers :
   - Shoes and Shirt have the highest average sales per order at 309 and 327, respectively. This suggests that these products consistently perform well in terms of individual order value.

 - Moderate Sales :
    - Gloves and Hat have mid-range average sales, which could indicate stable demand but lower per-order sales compared to Shirts and Shoes.

 - Lower-Average Products:
    - Jackets and Socks have the lowest average sales per order, with Socks at 122. These items may require promotional efforts or bundling strategies to increase their average sales
  
5. Summarize Average Sales by Region

[Download](https://github.com/queen-byte/CAPSTONE-PROJECT/blob/c49ef7b776175442a424fa397e4bbd6a536c3592/Screenshot%20(199).png)

- South Region: Has the highest average total sales at 374. This suggests that the South region is the strongest performer on average, with high sales across the products.
  
- East Region: Has an average total sales of 196, which is less than South but still significant. This indicates moderate demand for products in this region.
  
- North Region: Has an average total sales of 156, which is lower than both South and East, showing relatively less sales activity.
  
- West Region: Has the lowest average total sales at 121, which is significantly lower than the other regions. This may indicate lower demand, lower market penetration, or other issues that could be investigated


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
    
 With the NULL values erased, gave room for proper analysis

 1. Total sales by product category
   
   `select PRODUCT, SUM(TOTAL_SALES) AS TOTAL_SALES
FROM SALES_DATA
GROUP BY PRODUCT
order by 2 desc`

KEY INSIGHTS

  - Shoes as the Top-Selling Product: Shoes lead in total sales with 613,380, indicating high demand across regions. This suggests a need to prioritize stock and possibly introduce variations or related accessories to capitalize on this demand.
  - 
  - Shirts Show Strong Demand: With total sales of 485,600, shirts are another popular product. Consistent inventory and targeted promotions for shirts can help sustain and possibly grow this segment.

  - Lower Sales for Jackets and Socks: Jackets (208,230) and Socks (180,785) have the lowest total sales. They may need a targeted sales strategy or product re-evaluation to determine if these are worth continued investment or if they require modifications to meet customer preferences.

  - Product Prioritization for Maximum ROI: Given the high sales for Shoes and Shirts, these products should be prioritized in terms of stock, marketing, and potential new product variations. Meanwhile, sales strategies for lower-performing products like Jackets and Socks should be evaluated to improve their market appeal.


 2. Total sales by Region category

 `select REGION, sum(TOTAL_SALES) AS TOTAL_SALES
FROM SALES_DATA
GROUP BY REGION
ORDER BY 2 DESC`

KEY INSIGHTS

 - South Region Dominance: The South region is the top performer, with a total sales of 927,820. This suggests it’s a key market and could benefit from further investment in inventory, targeted marketing, and customer engagement strategies to maximize its potential.
   
  - Growth Opportunities in the East: With total sales of 485,925, the East region shows moderate sales strength. Enhancing marketing efforts or introducing more tailored products could help increase its market share.

  - Underperformance in the North and West: The North (387,000) and West (300,345) regions have the lowest sales, especially the West. These regions may need targeted analysis to understand demand, improve brand presence, and explore opportunities for sales growth.
    
  - Strategic Focus Areas: Investing in high-performing regions like the South can maximize returns, while developing strategies for regions like the West could help achieve balanced growth across all regions.

 
3. Total sales by product category and region was calculated
  
  `select PRODUCT, region,
   sum(TOTAL_SALES) AS TOTAL_SALES
   FROM SALES_DATA
   GROUP BY PRODUCT, region
   ORDER BY 3 DESc`

KEY INSIGHTS

   - High Demand for Shoes in the South: Shoes have the highest regional sales in the South at 546,300. This indicates that the South region is a key market for this product, making it essential to maintain inventory and possibly introduce complementary products or special promotions for Shoes in this area.
     
   - Shirt Sales Strong in Multiple Regions: Shirts show significant sales in both the North (248,000) and East (237,600). This suggests broad appeal across regions, making Shirts a versatile product with potential for continued demand if inventory and targeted marketing are maintained.

   - Gloves as a Popular Item in the South: Gloves have high sales in the South (247,600), suggesting this product resonates well with customers in this region. This could indicate a seasonal or regional preference that can be leveraged with focused marketing efforts in the South.

   - West Region Preference for Hats: The highest regional sales for Hats are in the West (174,300), making it a top product in this area. Focusing on promotional efforts for Hats in the West may help sustain and grow this demand

   - Underperformance of Certain Products in Some Regions: Products like Socks, Jacket, and Shoes have lower sales in certain regions (e.g., Shoes in the West at 29,880). These low-performing items may require tailored strategies, such as region-specific promotions, product bundling, or seasonal sales, to improve performance in these areas.



4.  Monthly sales trends for the current year. In this case the current year is 2024

  `SELECT MONTH(OrderDate) AS month, SUM(Total_Sales) AS total_sales
FROM 
sales_data
WHERE 
    YEAR(OrderDate) = YEAR(GETDATE())  
GROUP BY 
    MONTH(OrderDate)
ORDER BY 
    month`

KEY INSIGHTS 

   - Strong Start to the Year: January and February have the highest sales totals, with 198,400 and 298,800, respectively. This indicates a strong start to the year, potentially due to seasonal demand, new product launches, or successful early-year promotions.

   - Significant Drop in March to May: Sales drop sharply in March (54,780), April (39,440), and May (44,640), which could signal a seasonal lull, reduced consumer interest, or possible stock limitations. Addressing this drop with targeted campaigns or promotions could help improve sales during this period in future years.

   - Sales Recovery in June: Sales increase significantly in June, reaching 148,200. This upward trend might be due to mid-year sales, seasonal factors, or an effective marketing campaign. Building on this momentum could enhance future sales performance in the middle of the year.

   - Peak in August: August has the third-highest sales at 174,300, suggesting increased demand or effective marketing efforts towards the end of summer. This could be due to back-to-school shopping, late-summer promotions, or seasonal factors that can be leveraged further in the future.

   - Consistency Challenges: The large fluctuations from month to month suggest that sales are inconsistent. Focusing on understanding the factors driving high sales in certain months (like January, February, June, and August) could provide insights for stabilizing sales across the year.

    
5.  Monthly sales trends for the previous year. In this case the previous year is 2023

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

6. Top 5 customers
   
`select top 5 customer_id,  sum(TOTAL_SALES) AS TOTAL_SALES 
FROM SALES_DATA
GROUP BY customer_id
ORDER BY total_sales desc`



  

  
  
