# Airline-Loyalty-Program-Performance-Dashboard
Analyzing loyalty program enrollments, cancellations and flights booked for Northern Lights Air (NLA), a Canadian airline looking to boost enrollment for their loyalty program.

The data source can be found on website at [this link](https://www.kaggle.com/datasets/divu2001/coffee-shop-sales-analysis/data/). The main objective of this project is to evaluate the sales of three coffee shop locations using Power BI.

[Preview_Dashboard](https://github.com/David-Tu-Nguyen/Coffee_Shop_Sales_Analysis/blob/main/PowerBI_Dashboard/Dashboard_Snapshot.gif/). 

## Main objective
- **Prepare data for modeling**:
  + Explore and QA the data, and ensure that column headers and data types are accurate
  + Add columns to the Customer Loyalty History table to calculate the enrollment start of month and cancellation start of month
  + Add a column to Customer Flight Activity to calculate the flight booked start of month
  + Add a binary column to Customer Loyalty History to flag if a customer has canceled
- **Model and enhance data for analysis**:
  + Build a data model to connect the Calendar, Customer Loyalty History and Customer Flight Activity tables all the “start of month” fields.
  + Create DAX measures to calculate total enrollments (based on loyalty number) and total flights booked (based on flight activity). 
  + Create measures to calculate total cancellations and net loyalty members.
  + Create a measure to calculate the running total of net loyalty members over time
  + Create measures to calculate flights booked by loyalty members (based on start of month) and flights booked by loyalty members the previous year
- **Analyze loyalty program**:
  + Insert line charts to show total enrollments and cancellations by month. 
  + Insert column charts to show net loyalty members and the running total of net loyalty members by month. 
  + Insert a line chart to show loyalty member flights booked for the current and previous year, trended by month. Adjust layout & formatting for clarity.
  + Insert a stacked column chart to show loyalty member flights booked by enrollment type, trended by month, and add a slicer to filter the page by enrollment type.

The questions we will answer through this analysis are the following :
- Was the promotional campaign successful in driving customer engagement and bookings?
- How did the campaign influence loyalty program enrollment and cancellation rates?
- Did the campaign appeal more strongly to specific demographic segments (e.g., age, gender, location)?
- Which travel season is most preferred by newly enrolled loyalty members?

## Data dictionary
- Number of Rows: 412,230 
- Number of Columns: 28
  
Column Name | Data Type | Description
| ------------- |:-------------:| :-------------:|
Transaction_ID | Integer | Unique identifier for each transaction.
Transaction_Date | DateTime | Date and time when the transaction occurred.
Product_Name | Varchar | Name of the product sold (e.g., Espresso, Latte).
Product_Category | Varchar | Category of the product (e.g., Hot Beverage, Cold Beverage, Pastry).
Quantity_Sold | Integer | Number of units sold in the transaction.
Unit_Price | Float | Price per unit of the product.
Total_Sales | Float | Total revenue from the transaction (Quantity_Sold × Unit_Price).
Payment_Method | Varchar | Mode of payment used (e.g., Cash, Credit Card, Mobile Payment).
Customer_Age_Group | Varchar | Age group of the customer (e.g., 18-24, 25-34).
Customer_Gender | Varchar | Gender of the customer (e.g., Male, Female).
Store_Location | Varchar | Location of the store where the transaction took place.
Day_of_Week | Varchar | Day of the week when the transaction occurred (e.g., Monday, Tuesday).
Time_of_Day | Varchar | Time period of the day (e.g., Morning, Afternoon, Evening).
Season | Varchar | Season during which the transaction occurred (e.g., Winter, Summer).

## Methodology and tools used
Tables
| Step  | Used Tools |
| ------------- |:-------------:|
|First Exploratory Data Analysis & Joining Tables     |     |
|Data Cleaning, Advanced Exploratory Data Analysis & First Visualizations  |  |
|Advanced Data Visualizations & Dashboard    |  Power BI     |

## Data Cleaning and Transformations
I cleaned the data in Power Query and created the following;
- **Created measures**: Total Sales, Total Orders, Total quantity,...
- **Created calculated columns**: Time of Day, Date Hierarchy, Linear Regression Prediction,...

## Insights
**Revenue and transactions**
- Monthly sales have consistently grown since the second month (February), reaching their peak in the sixth month (June) across all stores.
- 72.06% of revenue is generated during weekdays for all stores
- On weekdays, Hell's Kitchen experiences its highest sales on Friday and Tuesday, signifying these as the busiest days. Similarly, Astoria's busiest weekdays are Thursday and Monday. Lower Manhattan's busiest weekday is Monday.

**Store hours**
- Hell's Kitchen and Lower Manhattan operate from 6:00 to 20:00, while Astoria is open from 7:00 to 19:00.
- Peak hours for Hell's Kitchen and Lower Manhattan are between 6:00 AM and 10:00 AM.
- Astoria experiences its busiest period from 7:00 to 10:00, consistently throughout the week and on weekends.
  
> Although Lower Manhattan generates the lowest total revenue, it records the highest sales during peak hours compared to the other locations. In contrast, Astoria achieves the highest sales during non-peak hours among all stores, despite having shorter operating hours.

**Top 3 product and category across all 3 stores.**

a) **Coffee** generated $269,952 in revenue, accounting for 38.6% of total sales, making it the highest-performing product category across all branches.
- Top coffee item at each location:
* Astoria: Barista Espresso (~$27K)
* Hell’s Kitchen: Barista Espresso (~$32K)
* Lower Manhattan: Barista Espresso (~$31K)

b) **Tea** sales make up 27.7% of the total combined revenue from the three stores, amounting to $196,406.
- Leading tea products by store:
* Astoria: Brewed Chai Tea (Spicy Eye Opener Chai, Large) – approx. $27K
* Hell’s Kitchen: Brewed Chai Tea (Morning Sunrise Chai, Regular) – approx. $26K
* Lower Manhattan: Brewed Chai Tea (Morning Sunrise Chai, Regular) – approx. $24K

c) **Bakery** items generated $82,316 in sales, contributing 12.3% to the total revenue across all stores, ranking as the third best-selling product category.

## Recommendations
- Leverage data from peak hours and top-performing days to optimize staffing and inventory distribution.
- Target underperforming locations for improvement while replicating successful strategies from high-performing stores.
- Distribute marketing resources according to the revenue share of each product category.
