# LITA-PROJECT
## PROJECT TITLE : SALES PERFORMANCE ANALYSIS
### Table of content
### Project Overview
The Data Analysis projects aims to generate insights to the Sales performance project over the past years. By analyzing the various parameter in the data received we seek to gather enough insight to make reasonable decisions which then enable us to compelling stories around our data from insight gotten and to know the best performance  from our data


### Data Source
The primary source of Data used here is Data Sales.csv and this is an open source data that can be freely downloaded from an open source online3 such as Kaggle or FRED or any other data repository sites. 

### Tools Used
- Microsoft Excel [Download Here](https://www.microsoftexcel.com)
    1.	For Data Cleansing
    2.	For Analysis
    3.	For Data Visualization
- SQL – Structured Query Language for Data Query
- Microsoft Power BI for Data Cleaning, Analysis and Visualization
- Github for portfolio building


### Data Cleaning and Preparation
In the initial face of data cleaning and preparation, we performed the following actions
1.	Data Loading and Inspection
2.	Handling Missing Variables
3.	Data Cleaning and Formatting

### Exploratory Data Analysis
EDA involves the exploring of Data to answer some Questions about the data such as: 
Calculating average sales per product and total revenue
Retrieving Total Salres for each product
Sales Overview etc

### Data Analysis
This is where we include some basic lines of codes oe queries or even some of the DAX expression used during the analysis

```SQL
SELECT*
FROM[dbo].[Sales Data]

Q1 Retrieve the total sales for each product category
SELECT Product ,SUM(Quantity*UnitPrice) as Total_Sales
FROM [dbo].[Sales Data]
GROUP BY Product

Q2 Find the number of sales transaction in each region
SELECT Region, SUM(Quantity*UnitPrice) as Total_Sales
FROM [dbo].[Sales Data]
GROUP BY Region

Q3 Find the highest-selling product by total sales value.
SELECT Product,SUM(Quantity*UnitPrice) as Total_Sales
FROM [dbo].[Sales Data]
GROUP BY Product

Q4 Calculate total revenue per product..
SELECT Product,SUM(Revenue) As Total_Revenue
FROM [dbo].[Sales Data]
GROUP BY Product

--ALTER TABLE[dbo].[Sales Data]
--ADD OrderMonth nvarchar(50)
--UPDATE [dbo].[Sales Data]
--SET OrderMonth = DATENAME (MONTH, OrderDate)


--ALTER TABLE[dbo].[Sales Data]
--ADD OrderYear int

--UPDATE[dbo].[Sales Data]
--SET OrderYear = Year(OrderDate)
---Revenue Column---
---ALTER TABLE[dbo].[Sales Data]
--ADD Revenue int
---UPDATE[dbo].[Sales Data]
---SET Revenue = (Quantity*UnitPrice)


SELECT*
FROM[dbo].[Sales Data]

--Q5 Calculate monthly sales totals for the current year (2024)--
SELECT OrderMonth,
SUM(Quantity*UnitPrice) as Total_Sales
FROM [dbo].[Sales Data]
WHERE OrderYear = 2024
GROUP BY OrderMonth

---Q6 find the top 5 customers by total purchase amount
SELECT Top 5 Customer_Id, SUM(Quantity) AS Total_Purchase
FROM[dbo].[Sales Data]
GROUP By Customer_Id
ORDER BY Total_Purchase DESC

---Q7 calculate the percentage of total sales contributed by each region.
SELECT Region,SUM(Revenue)/SUM(Quantity*UnitPrice)*0.1 AS Percentage_of_Total_Sales
FROM[dbo].[Sales Data]
GROUP BY Region
ORDER BY Percentage_of_Toal_Sales

---Q8 identify product with no sales in the last quarter
SELECT Product,SUM(Quantity) AS Sales
FROM [dbo].[Sales Data]
WHERE MONTH(OrderDate) BETWEEN 10 AND 12 -- Months 10, 11, and 12 (October to December)
GROUP BY Product
HAVING SUM(Quantity)=0

SELECT*
FROM[dbo].[Sales Data]
```
### Data Visualization
