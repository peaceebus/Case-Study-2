# Case-Study-2
## DSA PROJECT WORK: Kultra Mega Stores 


------ table

Import KMS table

When importing the KMS table, i made Row_ID as the primary and allow null for Product_Base_Margin

select * from KMS ( It is used to check the table that was imported)

## CASE SCENARIO I

(1). Which product category had the highest sales?

ANSWER; 

select Product_Category, sum(Sales) as TotalSales

from KMS

group by Product_Category

order by TotalSales DESC

Conclusion: Using this sql query, i was able to ascertain the product category with the highest sale.
The product category include; Technology, Furniture	and Office Supplies.

(2). What are the Top 3 and Bottom 3 regions in terms of sales?

ANSWER;

(A) Top 3 Regions in terms of sales:

select Top 3 Region, sum(Sales) as TotalSales

from KMS

Group by Region

Order by TotalSales DESC

(B) Bottom 3 Regions in terms of sales:

select Top 3 Region, sum(Sales) as TotalSales

from KMS

Group by Region

Order by TotalSales ASC

Using the ascending and descending order to determine the top and bottom 3 regions in terms of sales, the top and bottom 3 regions includes the following respectively;
West, Ontario, Prarie and Nunavut, Northwest Territories, Yukon.

(3).	What were the total sales of appliances in Ontario?

ANSWER;

Select sum(Sales) as TotalSales

from KMS

Where 'Appliances' = Product_Sub_Category and 'Ontario' = Region

Based on the findings; The total sales of appliances in ontario is 202346.839630127.

(4).	Advise the management of KMS on what to do to increase the revenue from the bottom 10 customers.

ANSWER;

i) The management of KMS should advertise more to the customers on availablity of product.

ii) The Kultra Mega Stores management should offer discounts to its customers.

iii) They should ensure that the customer service in the store is improved.

iv) Most times the management should provide opportunity for its customers to air their view.

v) Analyse their purchase history and perferences.

**THE SQL QUERY**

select TOP 10 Customer_Name, Sum(Sales) as TotalSales

from KMS

Group by Customer_Name

Order by TotalSales ASC

Using this sql query, I was able the ascertain the customers with the lowest revenue.

(5). KMS incurred the most shipping cost using which shipping method?

ANSWER;

Select Ship_Mode, Sum(Shipping_cost) as TotalShipping_Cost

from KMS

Group by Ship_Mode

Order by TotalShipping_Cost DESC

Findings: Kultra Mega Stores incurred the most shipping cost using Delivery Truck, Regular Air and Express Air.

## Case Scenario II 
(6).	Who are the most valuable customers, and what products or services do they typically purchase? 

ANSWER;

Select Customer_Name, Product_Name, Sum(Sales) as TotalSales

from KMS

Group by Customer_Name, Product_Name

Order by TotalSales DESC

Conclusion: Using Descending order to determine the most valuable customers from top to bottom.

(7).	Which small business customer had the highest sales? 

ANSWER;

Select Customer_Name, Sum(Sales) as TotalSales

from KMS

where Customer_Segment = 'Small Business'

Group by Customer_Name

Order by TotalSales DESC

Comment: Using an sql query to determine the small business customer that has the highest sales and applying the descending order to show from the highest to lowest.

(8).	Which Corporate Customer placed the most number of orders in 2009 – 2012? 

ANSWER;

Select Customer_Name, Order_Date, Count(Order_ID) as TotalOrders

from KMS

where Customer_Segment = 'Corporate'

Group by Customer_Name, Order_Date

Order by TotalOrders DESC

Findings: I was able to determine the corporate customer placed in different years by using the applicable sql query.

(9).	Which consumer customer was the most profitable one?

Alter table KMS

Alter column Profit decimal (10, 3)

ANSWER;

Select Customer_Name, sum(Profit) as TotalProfit

from KMS

Where Customer_Segment = 'Consumer'

Group by Customer_Name

Order by TotalProfit DESC

Comment: Before executing the sql query, The Profit data type needed to be changed to decimal (10, 3) since it was imported with a data type of nvarchar.

(10).	Which customer returned items, and what segment do they belong to? 

ANSWER;

Select distinct Customer_Name, Customer_Segment

from KMS

Where Profit < 0

Using the sql query, I was able to determine the customers that returned items and their segments.

(11).	If the delivery truck is the most economical but the slowest shipping method and Express Air is the fastest but the most expensive one, do you think 
the company appropriately spent shipping costs based on the Order Priority? 

ANSWER;

SELECT Order_Priority, Ship_Mode, Sum(Shipping_Cost) as TotalShipping_Cost

from KMS

Group by Order_Priority, Ship_Mode

Order by Order_Priority, TotalShipping_Cost DESC

Based on the analysis, The company, Kultra Mega Stores shipping cost does not align with the order priority.
