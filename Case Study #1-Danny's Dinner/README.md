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

2. How many days has each customer visited the restaurant?

![image](https://github.com/user-attachments/assets/6f00c51b-7fdd-4821-847a-3b730a079f28)

**Steps:**
* We can calculate the number of days each customer visited the restaurant by using **COUNT(order_date)** and grouping the results by customer_id,  **GROUP BY customer_id** clause
* To get the number of unique days a customer visited (ignoring multiple orders on the same day), we use **COUNT(DISTINCT order_date)**

**Answer**

![image](https://github.com/user-attachments/assets/bf8ea451-d5ee-4340-8eb7-d37160a0bc8a)

