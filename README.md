# Adventure-Works-Bike-Shop

## Table of Contents:
- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Tools](#tools)
- [Data Cleaning/Preparation](#data-cleaning/preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results/Findings](#results/findings)
- [Recommendations](#recommendations)
- [Limitations](#limitations)

### Project Overview
The goal is to design and deliver an end-to-end data analytics solution for Sales Department

![Screenshot 2024-06-09 233623](https://github.com/user-attachments/assets/a52d24d3-7511-4686-b6e0-eb69df8721fb)



### Data Source

Sales Data: The primary source for this data are:
 - AdventureWorks Sales_FULL.xlsx
 - AW_Customer.csv
 - AW_Product.csv
 - AW_Reseller.csv
 - AW_Sales_Data.csv
 - AW_Sales_Order_Data.csv
 - AW_Sales_Territory.csv
 - Date.csv

### Tools:
Microsoft Power BI

### Data Cleaning/Preparation:

In the Initial data preparation phase, we performed the following tasks:

- Data loading and inspections
- Importing the dataset by creating a new table and then filling out the data
- Handling missing values
- Data Cleaning and formatting

### Exploratory Data Analysis:

EDA involved exploring the sales data to answer key questions such as:
1. What fiscal year gained the highest revenue?
2. What are the TOP 3 products based on revenue?
3. Where did we gained the highest sales?

### Data Analysis

Power BI
```
    Source = Excel.Workbook(File.Contents("C:\Users\kea\Downloads\Dataset - AdventureWorks Sales (MSLearn)-20240607T053450Z-001\Dataset - AdventureWorks Sales (MSLearn)\AdventureWorks Sales_FULL.xlsx"), null, true),

= Source{[Item="Sales_data",Kind="Sheet"]}[Data],

= Table.PromoteHeaders(Sales_data_Sheet, [PromoteAllScalars=true]),

= Table.TransformColumnTypes(#"Promoted Headers",{{"SalesOrderLineKey", Int64.Type}, {"ResellerKey", Int64.Type}, {"CustomerKey", Int64.Type}, {"ProductKey", Int64.Type}, {"OrderDateKey", Int64.Type}, {"DueDateKey", Int64.Type}, {"ShipDateKey", Int64.Type}, {"SalesTerritoryKey", Int64.Type}, {"Order Quantity", Int64.Type}, {"Unit Price", type number}, {"Extended Amount", type number}, {"Unit Price Discount Pct", Int64.Type}, {"Product Standard Cost", type number}, {"Total Product Cost", type number}, {"Sales Amount", type number}})

```
### Results/Findings:

1. At $4,886,045.02, FY2020 had the highest Sum of Sales Amount and was 723.81% higher than FY2018, which had the lowest Sum of Sales Amount at $593,106.38.
2. FY2020 had the highest Sum of Sales Amount at $4,886,045.42, followed by FY2019 at $2,191,569.33 and FY2018 at $593,106.38.
3. Bike, components and clothing gained the highest revenue for three consecutive year, with bike as the highest achieving, 94,620,526.21 USD.
4. Among six countries, United States got the highest revenue with 8,999,859.53 USD.

### Recommendations:

1. We should improve our sales strategy in Canada, considering it as the lowesr performing country when it comes to bike sales, gaining only 1,977,844.86 USD for three consecutive years, particularly with bike accessories.

### Limitation:
1. There are some undocumented place where the sales takes place which was labelled "not applicable" that could possibly affect the result of the revenues and the place it took place.

