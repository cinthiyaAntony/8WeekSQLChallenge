**Case Study #1 - Danny's Diner**

![image](https://github.com/user-attachments/assets/eb2b1acf-401b-404f-b457-85ee51830986)

**Table of Content**

Business Task 
       
Entity Relationship Diagram

Question and Solution


**Business Task**

Danny's Dinner restaurant has collected foundational data about its operations, and our goal is to leverage SQL queries to extract valuable insights and answer key business questions

**Entity Relationship Diagram**

![image](https://github.com/user-attachments/assets/95388376-43e2-4aea-8ccd-f5da68b482eb)

**Question and Solution**

1. What is the total amount each customer spent at the restaurant?

![image](https://github.com/user-attachments/assets/b01bcd81-f9f9-471b-9b56-bd25ae0470cc)

**Steps:**
* Retrieve the price for each product in the **sales** table by performing a **JOIN** operation between the **sales** and **menu** tables using the **product_id**
* sum the prices for each customer using an aggregate function with a **GROUP BY customer_id** clause

**Answer**

![image](https://github.com/user-attachments/assets/ffb45e5b-5443-4ec4-9ac6-e0a5fcfb5b4f)

-------------------------------------------------------------------------------------------------------------------------------------------

2. How many days has each customer visited the restaurant?

![image](https://github.com/user-attachments/assets/6f00c51b-7fdd-4821-847a-3b730a079f28)

**Steps:**
* We can calculate the number of days each customer visited the restaurant by using **COUNT(order_date)** and grouping the results by customer_id,  **GROUP BY customer_id** clause
* To get the number of unique days a customer visited (ignoring multiple orders on the same day), we use **COUNT(DISTINCT order_date)**

**Answer**

![image](https://github.com/user-attachments/assets/bf8ea451-d5ee-4340-8eb7-d37160a0bc8a)

-------------------------------------------------------------------------------------------------------------------------------------------

3. What was the first item from the menu purchased by each customer?

![image](https://github.com/user-attachments/assets/15ad8b85-67e4-4eec-a80b-e1468f614406)

**Steps:**
* Using Common Table Expression CTE, We use DENSE_RANK() function to rankand parition by customer id to divide the data and order by to rank based on order date
* In Outer Query, apply a Where clause to retrive the rows which have rank 1

**Answer**
![image](https://github.com/user-attachments/assets/6f32b641-9450-4a40-8ed1-5f05f3f5cdcf)

* Here, Customer C has ordered ramen two times on first date, we can use GROUP BY customer_id, product_name clause collapses rows where both the customer and the product name are the same.
* Instead of DENSE_RANK(), we could use ROW_NUMBER(), which assigns consecutive ranks even when rows have the same values. However, since order_date lacks timestamp information to distinguish order times, DENSE_RANK() is preferable
-------------------------------------------------------------------------------------------------------------------------------------------

4. What is the most purchased item on the menu and how many times was it purchased by all customers?

![image](https://github.com/user-attachments/assets/bcb41f5f-d259-465a-87c4-4c8180619769)

**Steps:**

* To determine the most purchased item, we use COUNT(product_id) to count purchases for each product, group the results by product_name
* Then order the results by the purchase count in descending order, and finally, retrieve the top row.  

**Answer**
![image](https://github.com/user-attachments/assets/8c734137-0feb-4130-bd92-a2267ca5c7e4)

-------------------------------------------------------------------------------------------------------------------------------------------
5. Which item was the most popular for each customer?

![image](https://github.com/user-attachments/assets/7bb67171-2564-4d0c-9def-8ab7cec63863)

**Steps:**
* Create a CTE named tmp, join the table menu and sales table using the productid column
* Group by customer id and product name and count(product_id) to find the occurences for each group
* Using DENSE_RANK() window function, to calculate the ranking of each customer_id based on the count of orders COUNT(product_id) in descending order
* In outer query, Select the appropriate column and WHERE clause to retrive the rowN column equals to 1, represent the highest popular item for each customer

**Answer**

![image](https://github.com/user-attachments/assets/c8381b50-21e5-4f65-9810-2a8b3e74d604)

-------------------------------------------------------------------------------------------------------------------------------------------
6. Which item was purchased first by the customer after they became a member?

7. Which item was purchased just before the customer became a member?



