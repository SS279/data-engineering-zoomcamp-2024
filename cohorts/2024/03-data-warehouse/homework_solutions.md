## Module 3 Solutions

## Question 1:
Question 1: What is count of records for the 2022 Green Taxi Data??

840,402

![Solution 1](<Images/Solution 1.png>)

## Question 2:
Write a query to count the distinct number of PULocationIDs for the entire dataset on both the tables.</br> 
What is the estimated amount of data that will be read when this query is executed on the External Table and the Table?

0 MB for the External Table and 6.41MB for the Materialized Table

![Solution 2.1](<Images/Solution 2.1.png>)

![Solution 2.2](<Images/Solution 2.2.png>)

## Question 3:
How many records have a fare_amount of 0?

1,622

![Solution 3](<Images/Solution 3.png>)

## Question 4:
What is the best strategy to make an optimized table in Big Query if your query will always order the results by PUlocationID and filter based on lpep_pickup_datetime?

Partition by lpep_pickup_datetime and Cluster on PUlocationID

![Solution 4](<Images/Solution 4.png>)

## Question 5:
Write a query to retrieve the distinct PULocationID between lpep_pickup_datetime
06/01/2022 and 06/30/2022 (inclusive)

12.82 MB for non-partitioned table and 1.12 MB for the partitioned table

![Solution 5.1](<Images/Solution 5.1.png>)

![Solution 5.2](<Images/Solution 5.2.png>)

## Question 6: 
Where is the data stored in the External Table you created?

GCP Bucket


## Question 7:
It is best practice in Big Query to always cluster your data:

False


## (Bonus: Not worth points) Question 8:
No Points: Write a SELECT count(*) query FROM the materialized table you created. How many bytes does it estimate will be read? Why?

