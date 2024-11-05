# CUSTOMER'S SUBSCRIPTION ANALYSIS
This repository contains an Excel-based data analysis project which involves analyzing customer data for a subscription service to identify segments and trends. The projects provides insights through data cleaning, visualization, dashboard creation. The Dataset is made up of 9 columns and 33788 rows. The columns include:

- CustomerID: A unique identitifier assigned to a customer, used to track and manage customer interactions, transactions and relationships.
- Customer Name: The name of an individual or organization that purchases product or services from buisness.
- Region: A geographic area defined by political, economic or cultural boundaries
- Subscription Type: A classification of subscription plans offered to customers, defining the terms and benefits of the subscription.
- Subscription Start and End Date: The date that define the duration of a subscription, specifying when the subscription begins and ends.
- Revenue: The income generated by a buisness or organization from its normal operations.
-Subscription Duration in Days- The length of time a subscription remains active, measured in days.

### Data Sources

The Primary Datasets used for this analysis is the https://drive.google.com/file/d/1e5_oWTeEtl3FqnG05-vWh1vjW092orcW/view?usp=drive_link file,containing detailed information about each sales made by the retail store.

### Tools Used

-Microsoft Excel:This was used for Data Cleaning and also Data Visulization

- SQL Server : This was used for Data Analysis
  
- Power Bi : This was used for creating reports. 

### Data Cleaning/Preparation

-Steps Involved includes:

Data Importation (Collected and imported data from various sources)

Data Profiling

Data Validation (Checked for null values)

Data Transformation (Performed Data Calculations)

Error Detection (identification of Duplicate records)

### Exploratory Data Analysis

EDA involved the sales data to answer key questions, such as:

- The total number of sales for each region
- Most popular subscription types by the number of customers
- The total revenue by subscription type
- The top 3 regions by subscription cancellations
- The total number of active and canceled subscriptions.

  ### Data Analysis

Used SQL Server for the Data Analysis and the code used to answer the Key questions above include the following:

```Sql
 Select * from [dbo].[LITA Capstone Dataset11]
```
- The Total Number of Sales for each Region
```
SELECT Region, count(CustomerID) as NumberofCustomers
from [dbo].[LITA Capstone Dataset11]
Group By Region
Order by Region
```

- Most Popular Subscription type by number of customers
```
Select  Max(SubscriptionType) as MostPopularsubscriptiontype, Revenue
from [dbo].[LITA Capstone Dataset11]
Group By Revenue
Order By Revenue DESC;
```

- The total Revenue by subscription type
```
Select SubscriptionType, sum(Revenue) as TotalRevenuebySubscriptioType
from [dbo].[LITA Capstone Dataset11]
Group by SubscriptionType
```

- The top 3 regions by subscription cancelation
```
 Top 3 Region,count (Canceled)
From [dbo].[LITA Capstone Dataset11]
Group By Region
```

- The total number of active and canceled subscriptions
```
Select 
Count(case when Canceled = 'False' then 1 else 0 end) as Activesubscriptions,
Count(case when Canceled = 'True' then 1 else 0 end) as canceledsubscriptions
From [dbo].[LITA Capstone Dataset11]
```

### Results/Findings







