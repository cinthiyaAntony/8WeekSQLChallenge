**Case Study #2 - Pizza Runner**

![image](https://github.com/user-attachments/assets/3d23f9a6-6927-4ae3-a4c5-3c0283dc6a46)

**Table of Content**

Business Task

Entity Relationship Diagram

Question and Solution

**Business Task**

Danny launched Pizza Runner and began recruiting “runners” to deliver fresh pizza from Pizza Runner Headquarters (also known as Danny’s house). He also maxed out his credit card to pay freelance developers to build a mobile app for accepting customer orders. Now, he has collected some data and needs assistance cleaning it and performing basic calculations to help better direct his runners and optimize Pizza Runner’s operations


**Entity Relationship Diagram**

![image](https://github.com/user-attachments/assets/f9e4093a-e0ca-4a15-ac86-307c374d2826)

-------------------------------------------------------------------------------------------------------------------------------------------

**Data Cleaning & Transformation**

**Table: customer_orders**
The exclusions and extras columns will need to be cleaned up before using them
![image](https://github.com/user-attachments/assets/c70b164b-e346-43cf-8fa7-51a2c60322fb)

Our course of action to clean the table:

Create a table with all the columns
Remove null values in exlusions and extras columns and replace with blank space ' '.
![image](https://github.com/user-attachments/assets/2d9ff284-6736-45a8-a7eb-f3083ab258f9)


The  customer_orders_tmp looks like a below and we will use this table to run all our queries.
![image](https://github.com/user-attachments/assets/41188a3d-2739-4c70-a2eb-b6fcd035fd9c)

**Table: runner_orders**
The Pickup_time, Distance, Duration and Cancellation need to be  cleaned up
![image](https://github.com/user-attachments/assets/a5b9867a-c407-4e8f-8579-0129a66a55c7)

Our course of action to clean the table:

In pickup_time column, remove nulls and replace with blank space ' '.
In distance column, remove "km" and nulls and replace with blank space ' '.
In duration column, remove "minutes", "minute" and nulls and replace with blank space ' '.
In cancellation column, remove NULL and null and and replace with blank space ' '.


**#runner_orders_tmp**
![image](https://github.com/user-attachments/assets/ebab35fb-59ca-480d-9cd0-1d0adcd542dc)

Alter the pickup_time, distance and duration columns to the correct data type.
![image](https://github.com/user-attachments/assets/f06ec1d6-6054-49b0-9f5a-7fc40e8b31a8)

===========================================================================================================================================
**A. Pizza Metrics**

1. How many pizzas were ordered?


![image](https://github.com/user-attachments/assets/0eb7fb1b-6dd8-4938-80e0-bcf77c0b728f)

**Answer:**

![image](https://github.com/user-attachments/assets/c1531dff-142c-4fd1-80df-ac6c4671057e)

-------------------------------------------------------------------------------------------------------------------------------------------
2. How many unique customer orders were made?
![image](https://github.com/user-attachments/assets/59f3e0d8-486c-44eb-a185-245288ee6025)

**Answer:**
![image](https://github.com/user-attachments/assets/f15e060f-90f0-41fe-b0a0-0d1351d95417)

----------------------------------------------------------------------------------------------------------------------------------------
3. How many successful orders were delivered by each runner?
![image](https://github.com/user-attachments/assets/15dc9c58-80b2-4158-85f0-da296ad1edb2)

**Answer:**
![image](https://github.com/user-attachments/assets/14db117a-73ce-422e-84f0-4632ffc1e331)

-------------------------------------------------------------------------------------------------------------------------------------------
4. How many of each type of pizza was delivered?

**Error:**
![image](https://github.com/user-attachments/assets/e5155c30-8eaa-4c04-9b7a-1d5e01b2c865)

The pizza_name is DataType is a Text, Since SQL server does not allow GROUP BY, ORDER BY on text, ntext. We have to change the data type first.

**Solution:**

![image](https://github.com/user-attachments/assets/c4f354e6-9f69-4dad-b735-6e6a4a9c47d8)


**Answer:**
![image](https://github.com/user-attachments/assets/5b60836e-de87-4b3a-90a9-319f71065c3d)

![image](https://github.com/user-attachments/assets/bf2b2271-992a-4647-9568-081b881b49e2)

------------------------------------------------------------------------------------------------------------------------------------------
5. How many Vegetarian and Meatlovers were ordered by each customer?

![image](https://github.com/user-attachments/assets/1853a6ee-bb58-4ae1-b5f6-2f0fdce874e7)

**Answer:**

![image](https://github.com/user-attachments/assets/ccd87a16-72c5-4c62-8712-7283af9bffef)

------------------------------------------------------------------------------------------------------------------------------------------
6. What was the maximum number of pizzas delivered in a single order?

![image](https://github.com/user-attachments/assets/d5075ec1-964e-4ba9-97e1-6977bd27358e)

**Answer:**

![image](https://github.com/user-attachments/assets/74982350-d9af-492f-a72a-09471d37db0b)

-----------------------------------------------------------------------------------------------------------------------------------------

7. For each customer, how many delivered pizzas had at least 1 change and how many had no changes?

![image](https://github.com/user-attachments/assets/0ba3425d-02e8-4711-89fc-138cdc9c4fa1)

**Answer:**

![image](https://github.com/user-attachments/assets/a91325d6-b222-43a8-9de7-184563c743ae)

------------------------------------------------------------------------------------------------------------------------------------------

8. How many pizzas were delivered that had both exclusions and extras?

![image](https://github.com/user-attachments/assets/8ae9cc0c-dd9a-4371-b14f-3936ce54273e)

**Answer:**

![image](https://github.com/user-attachments/assets/df42540f-abd7-4b9a-b446-7f349f6a5837)

-----------------------------------------------------------------------------------------------------------------------------------------

9. What was the total volume of pizzas ordered for each hour of the day?

![image](https://github.com/user-attachments/assets/9b3db75c-1a3e-4237-9664-793955e6c2a9)

**Answer:**

![image](https://github.com/user-attachments/assets/c2ee88f5-5332-4d89-8c17-060b864461e1)

------------------------------------------------------------------------------------------------------------------------------------------
10.  What was the volume of orders for each day of the week?

![image](https://github.com/user-attachments/assets/32acb3ee-2235-43a1-bddc-bc660e973c91)

**Answer:**

![image](https://github.com/user-attachments/assets/c3b776d9-fdb8-452b-b840-9001956358ea)

------------------------------------------------------------------------------------------------------------------------------------------

**B. Runner and Customer Experience**

1. How many runners signed up for each 1 week period? (i.e. week starts 2021-01-01)

![image](https://github.com/user-attachments/assets/630cb5b5-427e-40db-9123-ea8d59729fc8)

**Answer:**

![image](https://github.com/user-attachments/assets/daaf5412-01e1-49d6-aac3-990ec305819a)

-----------------------------------------------------------------------------------------------------------------------------------------

2. What was the average time in minutes it took for each runner to arrive at the Pizza Runner HQ to pickup the order?

![image](https://github.com/user-attachments/assets/8258e15a-4fa9-4f55-a647-c09fda923d26)

**Answer:**

![image](https://github.com/user-attachments/assets/4d5678fd-8f68-49cd-8995-fd4e33464a5a)

------------------------------------------------------------------------------------------------------------------------------------------

3. Is there any relationship between the number of pizzas and how long the order takes to prepare?

![image](https://github.com/user-attachments/assets/1eafdb14-dba7-45dc-b81a-4a90abe77217)

**Answer:**

![image](https://github.com/user-attachments/assets/fea36af1-20e2-49a6-8a3b-ef33f1e39e79)
------------------------------------------------------------------------------------------------------------------------------------------

4. What was the average distance travelled for each customer?

![image](https://github.com/user-attachments/assets/cdcbd6b4-249d-48ec-9399-d6db36a0b6e8)


**Answer:**

![image](https://github.com/user-attachments/assets/8ff03817-0b9d-4401-a956-cbb3e1fb0aa8)

------------------------------------------------------------------------------------------------------------------------------------------

5. What was the difference between the longest and shortest delivery times for all orders?

![image](https://github.com/user-attachments/assets/405bcdd2-812f-43d6-a295-0258fa7c8db5)

**Answer:**

![image](https://github.com/user-attachments/assets/3edcab25-cea6-4dd2-a5d8-d4ff3668d290)

------------------------------------------------------------------------------------------------------------------------------------------

