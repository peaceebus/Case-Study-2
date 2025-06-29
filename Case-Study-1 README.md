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




# Case-Study-1
### DSA Project: Amazon Product Review Analysis 

**The pivot table and dashboard will be pasted via screenshot link**

![Screenshot (3)](https://github.com/user-attachments/assets/5f262f42-d737-4b8a-936a-78a3e1951bf6)

![Screenshot (4)](https://github.com/user-attachments/assets/b02edb3c-80a4-4196-946f-8bbce283eef6)

![Screenshot (5)](https://github.com/user-attachments/assets/875231d4-be23-4184-8d0c-12ca7311d2d2)

![Screenshot (6)](https://github.com/user-attachments/assets/54638620-d52e-4bac-8954-1d1da7919070)

![Screenshot (7)](https://github.com/user-attachments/assets/9eac2da0-3c2d-48f7-a42d-347385a957b9)

![Screenshot (8)](https://github.com/user-attachments/assets/fce58586-ea9a-4ef6-b8ac-2e6a8c0deae9)

![Screenshot (9)](https://github.com/user-attachments/assets/131495ea-005d-4592-816b-2db4616361fa)

![Screenshot (10)](https://github.com/user-attachments/assets/36f0aa2b-4667-4b25-bfc0-ded45bc3c3a4)

![Screenshot (11)](https://github.com/user-attachments/assets/7a16f4c0-7dff-4102-b7ff-8eafbadf095a)

![Screenshot (12)](https://github.com/user-attachments/assets/9cefa866-eb7d-4e4b-a795-768a18f634f3)

![Screenshot (13)](https://github.com/user-attachments/assets/e29c1587-6f8a-4a81-b9a9-00525603529a)

![Screenshot (14)](https://github.com/user-attachments/assets/b0effb72-aaa9-4afc-bbe7-5ba6a03595b0)

![Screenshot (15)](https://github.com/user-attachments/assets/45dab284-fe48-4099-a46c-7a509e397833)

![Screenshot (16)](https://github.com/user-attachments/assets/629405cc-ab4d-4e5d-b27c-4f3f16bb7de9)

![Screenshot (17)](https://github.com/user-attachments/assets/609c37b1-80dc-493b-8670-51fd9a93cdd5)

![Screenshot (18)](https://github.com/user-attachments/assets/0c057204-7f21-415c-b5be-c34ae9362609)

![Screenshot (19)](https://github.com/user-attachments/assets/7ed894b7-3e31-4814-9a0b-51a6b8bd7104)

![Screenshot (20)](https://github.com/user-attachments/assets/3a6c91c9-e753-4dc4-9398-0bb250a34b58)

![Screenshot (21)](https://github.com/user-attachments/assets/484c6aa6-4774-43d1-b3ac-27df01cedc42)

![Screenshot (22)](https://github.com/user-attachments/assets/225d24a8-fc74-468d-a75f-2206dc83e475)

![Screenshot (23)](https://github.com/user-attachments/assets/0349f0c2-470e-4d3e-9393-4d16823eab7e)

**The following questions that require formula;**

7. How many products have a discount of 50% or more?

   ANSWER: =IF(B3 >=50%, "Yes", "No")

9. What is the total potential revenue (actual_price × rating_count) by category?

    ANSWER: =B5 * C5

10. What is the number of unique products per price range bucket (e.g., <₹200, ₹200–₹500, >₹500)?

    ANSWER: =IF(C4 < 200, "<200", IF(C4 <=500, "200-500", ">500"))

12.  How many products have fewer than 1,000 reviews?

    ANSWER: =COUNTIF(B4, "<1000")





