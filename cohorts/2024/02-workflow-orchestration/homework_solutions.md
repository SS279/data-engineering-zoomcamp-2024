## Module 2 Solutions

## Question 1. Data Loading

Once the dataset is loaded, what's the shape of the data?

* 266,855 rows x 20 columns

![Solution 1](<Images/Solution 1.png>)

## Question 2. Data Transformation

Upon filtering the dataset where the passenger count is equal to 0 _or_ the trip distance is equal to zero, how many rows are left?

* 139,370 rows

![Solution 2](<Images/Solution 2.png>)

## Question 3. Data Transformation

Which of the following creates a new column `lpep_pickup_date` by converting `lpep_pickup_datetime` to a date?

* data['lpep_pickup_date'] = data['lpep_pickup_datetime'].dt.date

![Solution 3](<Images/Solution 3.png>)

## Question 4. Data Transformation

What are the existing values of `VendorID` in the dataset?

* 1 or 2

![Solution 4](<Images/Solution 4.png>)

## Question 5. Data Transformation

How many columns need to be renamed to snake case?

* 4

## Question 6. Data Exporting

Once exported, how many partitions (folders) are present in Google Cloud?

* 96

![Solution 6](<Images/Solution 6.png>)
