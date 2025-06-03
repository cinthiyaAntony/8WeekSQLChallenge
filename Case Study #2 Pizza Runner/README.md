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


