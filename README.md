# E-commerce

# Table of content
- [Executive Summary](#executive-summary)
- [Data Sources and Tools](#data-sources-and-tools)
- [Data Cleaning and Pre-processing](#data-cleaning-and-pre-processing)
- [Exploratory Data Analysis](exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Result And Findings](#result-and-findings)
- [Recomendation](#recomendation)
- [Limitations](#limitations)
- [Reference](#reference) 


### Executive Summary
This report analyzes e-commerce sales data from 01/12/2010 to 09/12/2011 for a UK-based online retail company selling unique all-occasion gifts. The analysis provides insights into sales trends, customer behavior, and product performance. 

### Data Sources and Tools
- Data Source: Ecommerce.csv dataset
- Tools: Excel (data cleaning), SQL Server (data analysis), Power BI (data visualization) download here{https://www.kaggle.com/datasets/carrie1/ecommerce-data}

  ### Data Cleaning and Pre-processing
The following tasks were performed to ensure data quality:
1. Data loading and inspection
2. Fixing un-standardized date format
3. Handling duplicates and foreign characters
4. Data cleaning and formatting

### Exploratory Data Analysis (EDA)
1. What's the sales trend over time
2. Total sales for each product (stockcode)
3. Which country has the highest numbers of customers
4. Top ten(10) product
5.  What are the distribution of sales across different countries?

### Data Analysis
```SQL
1. Select YEAR(InvoiceDate)as year,
FORMAT(InvoiceDate,'MMM') as month,SUM(Quantity* Unitprice) as totalsales
From E_commerce
Group by YEAR(InvoiceDate), MONTH(InvoiceDate),FORMAT(InvoiceDate,'MMM')
Order ![Power BI Desktop 4_26_2025 7_05_46 AM](https://github.com/user-attachments/assets/ba434db7-9cad-4c9b-8a5e-2e23583477c7)
by totalsales desc;


2. Select Stockcode, SUM(Quantity *Unitprice) as Product_sales
From E_commerce
group by StockCode;

3. Select Country, APPROX_COUNT_DISTINCT (CustomerID) as number_of_customers 
from E_commerce
group by Country
order by number_of_customers desc;

4.Select  top 10 stockcode, sum(Quantity * Unitprice) as totalsales
from E_commerce
group by stockcode
order by totalsales desc;

5. Select country,sum(Quantity * Unitprice) as totalsales
from E_commerce
group by country;
```
### Result And Findings
- Steady sales growth over time with seasonal fluctuations.
- Top-revenue products
 - Country with the highest number of customers

### Recomendation
1. Optimize Product Offerings: Focus on high-revenue products and stock codes.
2. Target High-Value Customers: Develop targeted marketing campaigns for customers in the country with the highest sales revenue.
3. Improve Sales Strategies: Identify and capitalize on patterns in invoice dates to maximize sales.
4. Enhance Customer Experience: Consider offering personalized service or loyalty programs to increase customer satisfaction and loyalty.
5. Monitor and Analyze Sales Performance: Review sales data regularly to identify trends, opportunities, and challenges.


### Limitations
I had to remove some data due to irregularity in the data set like blank spaces, spacial characters and others during the cleaning process

### Reference 
- https://www.youtube.com/watch?v=0N9xekdKCwk
- Team effort
- Other dataset
- 





