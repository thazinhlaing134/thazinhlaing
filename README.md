# Sale Monitor-Dashboard

### Dashboard Link : 
https://app.powerbi.com/view?r=eyJrIjoiMmJjZjIyZWUtNWUwNy00ZTJjLTk2NjUtM2VjYzAxMDljODUwIiwidCI6IjJkZmJlMjkzLWI5NTMtNDI0OC1iZjhhLWIxMWZhYWZiMWRlNCIsImMiOjEwfQ%3D%3D
### AdventureWorks Database  Link : 
https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorksDW2019.bak

## Problem Statement
Sale Manager want to move from static report to dashboard that can monitor internet sales data by product and customer. 
Sale manger also provided buget data that have delivered by month in excel file. 
The dashboard will also need to show comparison of actual sales performance against budgeted targets, with a historical view spanning in 2019 and 2020.

## Data Extraction, Cleasing and Transformation

- Step 1 : Download AdventureWork database and restore this database to Microsoft SQL Server Management Studio (SSMS)
- Step 2 : Extract the fields that want to use in report from tables. The tables that will be used are FactInternetSale, DimCustomer, DimProduct and DimDate table.
- Step 3 : Extract necessary fields from tables:

![Untitled](https://github.com/user-attachments/assets/f7b815a0-9738-4684-830f-3be98808ea1d)

- Step 4 : Export the result data as .csv format from database. Load files into Power BI Desktop. Also load excel file of Budget by month provided by sale manager.
- Step 5 : Create three pages of dashboard : Sale Overview, Customer Details, Product Details.
- Step 6 : The report was then published to Power BI Service.

## Data Analysis from Dashboard
### Sales vs Budget :

    Total Sales: The dashboard displays total sales of 22.24M, surpassing the budget of 21.10M by 1.14M. 
    This indicates an overall successful performance with sales consistently outperforming the budget.
![image](https://github.com/user-attachments/assets/a6c407e6-0160-4f8b-a936-0b41fcafa8ef)

### Sales by Product Category:

    Bikes dominate the sales, accounting for 95.3% of the total sales (approximately 21.2M).
    Accessories and Clothing contribute smaller portions, with Accessories making up 3.2% (approximately 0.7M) and Clothing only contribute 1.5%.
![image](https://github.com/user-attachments/assets/d270b1a1-256c-4afd-b4ac-df71aa4daf03)

### Sales by Customer:

    Jordan Turner is the highest-grossing customer, with total sales of 15.999K. December was particularly strong for this customer, contributing 5.311K.
    Other notable customers include Maurice Shan (12.910K), Janet Munoz (12.489K), and Lisa Cai (11.469K). These customers have consistent sales throughout the year, with notable contributions in both mid-year and end-of-year peaks.
    The top 10 customers all have sales figures ranging from 9.9K to 16.0K.
![image](https://github.com/user-attachments/assets/c6c48247-018e-495f-8cef-35ce73e0d7ea)

### Sales by Product Name:

    Mountain Bikes are the best-selling product, with multiple variations listed as top sellers, with sales figures ranging from 1.37M to 1.26M.
    Road Bikes also feature prominently, with sales figures ranging from 0.73M to 0.62M.
![image](https://github.com/user-attachments/assets/f7271093-a2bf-4b23-bfd1-078bd71c66fd)

### Monthly Sale and Budget Trend:

    Monthly Sales Peaks: The sales trend shows a noticeable peak in June with sales     reaching 2.2M, and another significant increase in December with sales close to 2.5M. This suggests strong sales activity during these months, possibly due to seasonal demand or successful promotional campaigns.

    Budget Comparison: Throughout the year, sales exceeded the budget, particularly in the second half of the year. The months of October, November, and December were especially strong, with sales consistently higher than the budget.
![image](https://github.com/user-attachments/assets/c1b2a5b4-addf-4656-b892-95a0d2082996)

### Sales by Customer City:

    The map highlights significant sales concentrations in Europe and parts of North America. These regions are critical markets, driving a substantial portion of total sales.
    Other areas such as Asia and Australia also contribute, though to a lesser extent compared to Europe and North America.

![image](https://github.com/user-attachments/assets/1ffa8951-feae-4ebb-9cb3-b826bb26eaed)

### Product Performance:

    Bikes: The Bikes category dominates the sales, contributing over 19.9M out of the total 22.24M. This category is the primary driver of revenue and shows strong performance across all months, particularly in May, June, and December.
    Clothing: The Clothing category generated 2.4M in sales, with steady contributions each month. Notable months include December (2.1M) and June (1.9M).
    Accessories: The Accessories category contributed 0.7M, with sales peaking in December (67,930), indicating some seasonal demand for accessories during the holiday season
![image](https://github.com/user-attachments/assets/86310969-6393-4e84-84f7-5892e7158daf)

#### Following DAX expression was written:
        Budget = SUM(Budget[Budget])
        Sale = SUM(FACT_InternetSales[SalesAmount])
        Sale vs Budget = SUM(FACT_InternetSales[SalesAmount]) - SUM(Budget[Budget])
        Sale_Budget_Percent = SUM(FACT_InternetSales[SalesAmount] )/ SUM(Budget[Budget])

### Snapshot of Dashboard (Power BI Service)
![Screenshot 2024-08-13 110727](https://github.com/user-attachments/assets/94d6ebc2-9120-46c9-8ab4-4991d5fd95d9)
![Screenshot 2024-08-14 140827](https://github.com/user-attachments/assets/36c17368-c677-4e66-a41e-7e550b509173)
![Screenshot 2024-08-14 140845](https://github.com/user-attachments/assets/eaba91d4-7de5-4cb4-b4ce-287c481a88ff)

 
### Report Snapshot (Power BI DESKTOP)
![image](https://github.com/user-attachments/assets/fb980ad4-109f-445c-b671-f912bc2655cb)

## Insights Summary

#### 1. Total Sales vs. Budget:
   The company achieved total sales of 22.24 million, exceeding the budget of 21.1 million by 1.14 million. This indicates effective sales strategies and strong market demand.

#### 2. Product Category Performance:
   Bikes are the dominant product category, contributing 95.3% to the overall sales, with Mountain Bikes leading the sales figures.
   Accessories and Clothing categories account for a smaller portion of sales, suggesting an opportunity to explore strategies to boost these categories.

#### 3. Monthly Sales Trends:
   Sales exhibited consistent growth throughout the year, with peaks in June, September, and December. The end-of-year spike suggests seasonal demand or successful year-end promotions.
   Sales aligned closely with budget expectations each month, with some months surpassing the budget, indicating strong performance management.

#### 4. Top Customers:
   Jordan Turner is the highest-spending customer, contributing 16,000 in sales, followed by Maurice Shan and Janet Munoz. This highlights the importance of retaining top customers who contribute significantly to revenue.
   The top 10 customers collectively contribute a substantial portion of the total sales, emphasizing the importance of maintaining strong relationships with key clients.

#### 5. Geographical Sales Distribution:
   The majority of sales are concentrated in North America and Europe, which are the strongest performing regions. There is a potential opportunity to expand market reach in underperforming regions such as South America and Asia.

#### 6. Product-Specific Insights:
   Mountain Bikes are consistently the top-selling products, with multiple models leading in sales figures.
   Road Bikes also perform well, but there is a significant gap between them and Mountain Bikes, indicating a clear preference in the market.
   Sales for Clothing and Accessories fluctuate throughout the year, showing potential for targeted marketing or product bundling to increase sales in these categories.
